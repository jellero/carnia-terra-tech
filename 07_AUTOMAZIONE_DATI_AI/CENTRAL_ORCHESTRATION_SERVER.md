# Central orchestration server — architettura di governo aziendale

**Aggiornato:** 18 settembre 2026  
**Stato:** `BOM-030 ARCHITETTURA DEPLOYMENT STRUTTURATA / 2 COMPUTE + WITNESS/EDGE + BACKUP SEPARATO / SOFTWARE STACK E ACCEPTANCE DEFINITI / HARDWARE TARGET DA RFQ`.

## 1. Principio

Carnia TerraTech usa un **server centrale** come control plane dell'azienda.

Il server non è un semplice dashboard. È il sistema che:

- conosce lo stato dell'azienda;
- raccoglie gli eventi;
- mantiene il registro storico;
- pianifica il lavoro;
- assegna attività a persone e macchine;
- coordina logistica e produzione;
- gestisce inventario e lotti;
- coordina ordini e pagamenti;
- calcola priorità;
- prevede domanda e offerta;
- propone o esegue il piano operativo;
- misura deviazioni tra piano e realtà.

Il server è il **sistema autorevole dei dati** per le operazioni aziendali.

## 2. Separazione fondamentale: pianificazione vs sicurezza/controllo

Il server centrale può decidere **cosa** fare e **quando** farlo.

Non deve essere l'unico elemento che garantisce la sicurezza fisica o i loop real-time.

Restano locali:

- safety PLC e circuiti di sicurezza;
- arresti di emergenza;
- protezioni elettriche;
- interblocchi macchina;
- limiti temperatura hardware;
- protezioni pompe/compressori;
- controllo climatico minimo fail-safe;
- protezioni inverter/BESS;
- anti-overflow;
- anti-dry-run;
- motion safety AMR/robot;
- chiusura locale valvole quando necessaria.

Regola:

`server non disponibile != impianto unsafe`

In caso di perdita server, ogni sottosistema deve:

1. completare o interrompere in sicurezza la fase corrente;
2. mantenere il minimo locale necessario;
3. impedire nuove operazioni che richiedono autorizzazione centrale;
4. registrare localmente gli eventi recuperabili;
5. riconciliarsi al ritorno del server.

## 3. Domini gestiti

Il control plane comprende almeno:

### Produzione
- crop plan;
- semine/trapianti;
- turni irrigui;
- fertirrigazione;
- clima;
- raccolta;
- rese;
- qualità.

### Acqua
- livelli;
- disponibilità;
- consumi;
- filtrazione;
- pompe;
- allarmi;
- bilancio idrico.

### Energia
- FV;
- BESS;
- rete;
- carichi;
- priorità;
- peak shaving;
- backup;
- stato di isola se disponibile.

### Macchine
- AMR;
- sollevatori;
- robot prato;
- rover pulizia;
- docking;
- missioni;
- manutenzione.

### Tech Barn
- celle;
- packaging;
- stock;
- ordini;
- spedizioni;
- lotti.

### Spaccio 24/7
- catalogo;
- prezzi;
- slot;
- stock;
- cassetta intelligente;
- carrello intelligente;
- ESL/e-paper;
- Stripe;
- cancello di uscita dopo pagamento;
- pick/return event;
- vend;
- refund;
- temperatura;
- scadenze;
- conferma cliente;
- reconciliation fusione sensoriale.

### Personale
- calendario;
- competenze;
- disponibilità;
- task;
- carichi di lavoro;
- priorità;
- completamento;
- eccezioni.

### Manutenzione
- asset registry;
- ore/cicli;
- PM;
- manutenzione su condizione;
- ricambi;
- ordine di manutenzione;
- storico guasti.

### Visitatori
- calendario visite;
- MODALITÀ VISITA;
- zone interdette;
- lockout dinamici;
- personale.

## 4. Registro eventi

Ogni evento rilevante deve produrre una registrazione timestamped.

Esempi:

- sensor_sample;
- setpoint_change;
- irrigation_started;
- irrigation_completed;
- pump_fault;
- crop_task_created;
- crop_task_completed;
- harvest_lot_created;
- lot_moved;
- cold_room_alarm;
- stock_loaded;
- smart_crate_mass_changed;
- smart_cart_mass_changed;
- retail_pick_detected;
- retail_return_detected;
- retail_event_confirmed;
- customer_confirmation_requested;
- esl_price_updated;
- vending_sale_created;
- stripe_payment_authorized;
- cart_reconciled;
- exit_gate_authorized;
- vend_confirmed;
- refund_created;
- worker_task_assigned;
- AMR_mission_created;
- AMR_mission_completed;
- maintenance_work_order_closed;
- BESS_mode_changed;
- visitor_mode_enabled.

Per gli eventi critici:

- timestamp;
- asset;
- actor;
- source;
- correlation id;
- causation id;
- old state/new state;
- payload;
- outcome;
- version.

Preferenza architetturale:
- append-only event/audit log;
- viste/materializzazioni per stato corrente;
- idempotency sulle azioni esterne.

## 5. Sistema autorevole dei dati

Il server centrale mantiene dati anagrafici principali per:

- asset;
- persone/ruoli;
- colture;
- parcelle/comparti;
- ricette;
- SKU;
- packaging;
- clienti;
- fornitori;
- lotti;
- ordini;
- listini;
- manutenzione;
- magazzino;
- task;
- turni;
- mezzi;
- regole operative.

I controller macchina non diventano database paralleli dell'azienda.

Quando un fornitore mantiene il proprio cloud:
- il server importa gli eventi necessari;
- non delega al cloud fornitore il master aziendale;
- deve poter esportare tutti i dati;
- il sistema deve sopravvivere alla sostituzione del fornitore.

## 6. Pianificatore operativo

Il pianificatore genera un piano temporale unico combinando:

- domanda;
- disponibilità prodotto;
- maturazione prevista;
- capacità serra;
- capacità celle;
- capacità packaging;
- disponibilità personale;
- disponibilità macchine;
- manutenzioni;
- energia;
- acqua;
- ordini;
- finestre visitatori;
- meteo;
- vincoli agronomici.

Output:

- task persone;
- missioni robot;
- finestre raccolta;
- finestre packaging;
- refill spaccio;
- replenishment stock;
- manutenzioni;
- delivery;
- irrigazioni;
- carichi differibili.

Il piano viene ricalcolato quando cambia una condizione significativa.

## 7. Motore di priorità

Ogni task può avere:

- deadline;
- earliest start;
- duration estimate;
- skill;
- asset required;
- dependency;
- location;
- food-safety class;
- urgency;
- economic value;
- crop-risk score;
- energy constraint;
- weather constraint.

Esempio concettuale:

`priority = safety + crop_risk + SLA + perishability + economic_value - switching_cost`

La formula effettiva resta configurabile e auditabile.

## 8. Forecast domanda

Input possibili:

- storico vendite;
- giorno settimana;
- ora;
- meteo;
- festività;
- turismo/eventi;
- visite fattoria;
- stagionalità;
- prezzi;
- promozioni;
- stockout history;
- shelf-life;
- lead time;
- vendite canali diversi.

Output:

- domanda per SKU/giorno;
- intervallo di confidenza;
- refill target;
- stock target;
- suggerimento raccolta/pack;
- rischio stockout;
- rischio overstock/waste.

Il modello non deve confondere zero vendite con zero domanda se lo SKU era stockout.

## 9. Forecast offerta

Input:

- crop plan;
- data trapianto;
- fenologia;
- climate history;
- radiazione/temperatura;
- irrigazione;
- varietà;
- raccolte precedenti;
- qualità;
- malattie/stress;
- immagini/vision se disponibili.

Output:

- kg previsti per giorno/settimana;
- qualità prevista;
- finestra raccolta;
- rischio deviazione;
- disponibilità vendibile.

Il server confronta:

`forecast_supply vs forecast_demand`

e genera azioni:

- variazione raccolta;
- variazione pack;
- refill;
- promozione;
- spostamento canale;
- riduzione prezzo;
- trasformazione futura;
- acquisto da altra azienda se strategicamente/normativamente ammesso;
- stop di campagne/promozioni se offerta insufficiente.

## 10. Personale

Il server non tratta il personale come risorsa anonima.

Ogni persona ha:

- ruolo;
- skill;
- autorizzazioni;
- disponibilità;
- ore;
- task assegnabili;
- formazione;
- restrizioni;
- storico lavoro.

Lo pianificatore deve:
- minimizzare cambi attività inutili;
- evitare sovraccarico;
- rispettare pause/orari/vincoli applicabili;
- raggruppare task per zona;
- distinguere attività delegabili a robot.

Il completamento task alimenta tempi reali e previsioni future.

## 11. Logistica

Ogni movimento fisico rilevante deve essere tracciabile:

`lot -> container -> posizione -> missione -> destinazione`

Esempi:
- serra -> packing;
- packing -> CR-A/CR-B;
- cella -> spaccio;
- cella -> spedizione;
- reso -> quarantine;
- waste -> compost/scarto.

AMR e operatori ricevono missioni dallo stesso pianificatore.

## 12. Spaccio e Stripe

Il server centrale gestisce:

- carrello/ordine;
- prezzo;
- promozioni;
- inventory reservation;
- PaymentIntent;
- stato pagamento;
- autorizzazione vendita;
- comando vending;
- conferma erogazione;
- refund;
- riconciliazione;
- fiscal event;
- audit.

Flusso di lavoro:

`selection -> reserve stock -> create PaymentIntent -> collect/confirm -> payment webhook -> authorize vend -> vend -> vend_ack -> close order`

Se il prodotto non viene erogato:
- non considerare l'ordine completato;
- avviare recovery/refund secondo stato PaymentIntent e policy.

Tutte le operazioni esterne devono usare:
- idempotency key;
- correlation id;
- retry controllato;
- state machine esplicita.

## 13. Frictionless retail event correlation

Per `SMART_CRATE_SMART_CART_ARCHITECTURE.md` il server centrale è il motore di correlazione degli eventi retail.

Input tipici:

- crate_id;
- SKU/lot della crate;
- `Δmass_crate`;
- cart_id/session_id;
- `Δmass_cart`;
- cart/crate proximity;
- camera event;
- timestamp;
- confidence dei singoli sensori;
- price snapshot.

Il motore produce:

- `ITEM_ADDED`;
- `ITEM_REMOVED`;
- `AMBIGUOUS_EVENT`;
- `CUSTOMER_CONFIRMATION_REQUIRED`;
- `SHRINK_ANOMALY`.

Regole:

- nessun addebito da un singolo sensore debole;
- delta peso negativo/positivo devono essere correlati quando disponibili;
- price snapshot immutabile nell'evento acquisto;
- ritorni devono invertire correttamente quantità/prezzo;
- eventi duplicati devono essere idempotenti;
- l'inventario si aggiorna da eventi confermati, non dal solo video.

State machine cart:

`OPEN -> SHOPPING -> RECONCILING -> READY_TO_PAY -> PAYMENT_PENDING -> PAID -> EXIT_AUTHORIZED -> CLOSED`

Il gate riceve soltanto uno stato autorizzativo, non logica commerciale completa.

### Metrology boundary

Il server può leggere sensori commodity, ma deve sapere quale sorgente è legalmente valida per il peso commerciale.

Ogni measurement event deve avere:

- `measurement_source`;
- `legal_for_trade=true/false`;
- `instrument_id`;
- `verification/calibration state`;
- `gross/tare/net`;
- `unit`.

Se il prodotto è venduto a peso e non esiste una misura legalmente valida, la sessione non può passare a `READY_TO_PAY` per quella riga.

### Refill prediction

Gli eventi di cassetta intelligente aggiungono dati ad alta frequenza:

- pick rate;
- return rate;
- depletion rate;
- near-stockout;
- dwell/interest proxy;
- stock discrepancy.

Il server usa questi segnali per anticipare:
- refill;
- trasferimento da cella;
- raccolta/pack;
- markdown;
- staff task.

## 14. Stripe Terminal unattended

Per lo spaccio 24/7 realmente non presidiato, il candidato Stripe Terminal è **Verifone UX700**.

Requisiti architetturali:
- integrazione Stripe;
- lettore registrato alla location;
- gestione device state;
- server API;
- webhook;
- PaymentIntent;
- refund;
- reconciliation.

La compatibilità esatta tra modalità offline, server-driven e configurazione italiana deve essere verificata nel pilot e nella documentazione Stripe corrente.

Stripe è il payment stack unico della configurazione base.

## 15. Integrazione vending

Preferenza:
- macchina con API/SDK/protocollo documentato;
- accesso a vend result;
- slot state;
- temperature;
- door/service events;
- faults;
- inventory telemetry.

MDB da solo può essere insufficiente per l'orchestrazione completa.

Se il fornitore non espone API adeguate:
- gateway locale;
- controller I/O/protocol adapter;
- event bridge verso server.

Il server deve sapere la differenza tra:
- pagamento riuscito;
- comando erogazione inviato;
- erogazione fisicamente confermata.

## 16. BESS e continuità

Il progetto dispone di backup a batterie con **30 kW di potenza**.

BOM/server devono quindi evitare UPS locali ridondanti salvo requisito tecnico futuro specifico.

Da chiudere nel package energia:

- capacità utile in kWh;
- potenza continua;
- potenza di picco;
- autonomia;
- tempo di trasferimento;
- capacità di funzionamento in isola;
- carichi prioritari;
- SOC reserve;
- black start se disponibile.

Il server deve classificare i carichi:

### P0 safety/control
- rete/control plane minimo;
- PLC/edge essenziali;
- sicurezza;
- monitoraggio critico.

### P1 food/cold-chain
- celle;
- vending refrigerato;
- logger;
- network necessario.

### P2 production continuity
- pompe/controlli selezionati;
- IT operativo.

### P3 deferrable
- carichi rinviabili;
- charging non urgente;
- comfort/non-critical.

Con BESS attivo, lo pianificatore può ridurre o rimandare P3 prima di sacrificare P0/P1.

## 17. Database

Architettura logica consigliata:

- relational DB per dati anagrafici principali/transazioni;
- time-series storage per telemetry;
- object storage per immagini/documenti;
- event queue/bus;
- cache;
- backup separato.

Non serve adottare un microservice per ogni funzione.

Preferenza:
- modular monolith o pochi servizi ben delimitati all'inizio;
- contratti API chiari;
- event-driven solo dove produce valore.

## 18. API e integrazioni

Ogni integrazione deve avere:

- versioning;
- auth;
- idempotency;
- timeout;
- retry;
- circuit breaker;
- observability;
- schema eventi;
- test simulator.

Classi:

- REST/HTTP;
- WebSocket;
- MQTT;
- OPC UA;
- Modbus gateway;
- fornitore API;
- Stripe webhooks;
- file/CSV solo come ripiego.

## 19. Offline/edge

Ogni sottosistema critico deve poter degradare con ordine.

Edge buffer:
- cache ultimi setpoint autorizzati;
- queue eventi;
- local timestamp;
- retry;
- state snapshot.

Non consentire:
- doppie missioni;
- doppio pagamento;
- doppia irrigazione;
- doppio task;
- replay non idempotente.

## 20. Human interface

Dashboard unica con viste per ruolo:

- operations;
- agronomia;
- maintenance;
- logistics;
- sales;
- energy;
- owner/admin.

La UI mostra:
- stato;
- eccezioni;
- piano;
- task;
- alert;
- forecast;
- KPI.

Principio:
- mostrare eccezioni prima dei grafici decorativi.

## 21. Audit e tracciabilità

Ogni cambio manuale rilevante deve avere:

- chi;
- quando;
- cosa;
- perché se override;
- stato precedente;
- stato nuovo.

Per task automatici:
- regola/model version;
- input;
- decision;
- outcome.

Forecast e AI non devono modificare silenziosamente vincoli safety/HACCP.

## 22. AI/forecast governance

Distinguere:

- prediction;
- recommendation;
- automatic execution.

Ogni modello deve avere:
- versione;
- dataset window;
- metriche;
- drift monitoring;
- ripiego;
- limiti operativi.

Azioni ad alto impatto richiedono regole deterministicamente verificabili anche se suggerite da AI.

## 23. Cybersicurezza

Configurazione base:

- RBAC;
- MFA per utenti privilegiati;
- service accounts separate;
- secrets manager;
- TLS;
- network segmentation;
- least privilege;
- immutable/offsite backup;
- patch management;
- asset inventory;
- audit log;
- restore test.

Il server non espone direttamente PLC/OT su Internet.

## 24. Osservabilità

Metriche:
- uptime;
- queue lag;
- task latency;
- API failures;
- device offline;
- webhook failures;
- DB health;
- forecast error;
- pianificatore replan rate;
- payment reconciliation mismatch;
- inventory variance.

Alert con severity e owner.

## 25. Modalità di guasto

| Guasto | Comportamento |
|---|---|
| server non disponibile | local safe mode + no nuove missioni non sicure |
| DB non disponibile | stop nuove transazioni critiche, queue dove sicuro |
| event bus down | local buffer + backpressure |
| Internet down | operazioni locali consentite secondo policy; cloud integrations degradate |
| Stripe down | niente nuove vendite che richiedono pagamento |
| webhook delayed | state machine resta pending, no double-vend |
| vending controller non disponibile | slot/machine disabled |
| forecast servizio non disponibile | pianificatore usa configurazione base/rules |
| BESS low SOC | load shedding P3/P2 secondo policy |
| clock drift | alert + reject critical ordering if timestamp integrity lost |

## 26. KPI

- forecast WAPE/MAE per SKU;
- stockout rate;
- waste rate;
- order fill rate;
- inventory accuracy;
- labor hours/kg;
- task on-time rate;
- AMR utilization;
- refill minutes;
- cold-chain excursions;
- energy cost/kg;
- water l/kg;
- downtime;
- maintenance MTBF/MTTR;
- payment-vend reconciliation.

## 27. BOM-030 — obiettivo di implementazione

La configurazione base non è un singolo PC e non è un cluster Kubernetes.

Architettura di lavoro:

`NODE-A + NODE-B + QNODE/EDGE + BACKUP TARGET + BESS 30 kW`

### NODE-A / NODE-B — compute

Due server x86_64 near-edge/server-grade con:

- CPU Xeon E-2400 / Xeon 6300 class o equivalente;
- ECC RAM;
- **64 GB ECC minimo, 128 GB target**;
- 2× NVMe enterprise 1,92 TB o superiori in mirror per workload;
- storage OS separabile se conveniente;
- almeno 2 interfacce di rete, con 10 GbE per interconnect/storage preferito;
- TPM 2.0;
- BMC/iDRAC/iLO;
- ventole/alimentazione monitorabili;
- supporto 3–5 anni.

Reference hardware:
- Dell PowerEdge T160;
- HPE ProLiant MicroServer Gen11 / server equivalente.

Il prezzo catalogo di una configurazione base non è il prezzo del nodo target: RAM ECC, NVMe enterprise, NIC e supporto vanno quotati nella configurazione effettiva.

### QNODE / EDGE

Terzo nodo leggero indipendente per:

- quorum/qdevice;
- etcd/coordination dove richiesto;
- terza replica NATS JetStream per stream critici;
- NTP/chrony reference locale;
- bridge MQTT/field;
- health watchdog.

Non esegue il database primario né workload AI pesanti.

Target:
- x86_64 fanless/mini-server;
- 16–32 GB RAM;
- storage SSD mirrored preferito;
- 2 NIC;
- TPM;
- alimentazione da BESS.

### BACKUP

Backup fisicamente distinto dal mirror locale:

- NAS/server 8-bay class;
- ZFS/Btrfs/RAID appropriato;
- snapshot;
- Proxmox Backup Server o repository backup dedicato;
- copia DB con WAL;
- copia off-site cifrata.

Synology DS1825+ è un riferimento di confronto di classe:
- 8 bay SATA;
- 2× M.2 NVMe;
- 2×2,5 GbE;
- Ryzen V1500B.

Non viene usato come primary database storage.

## 28. Virtualizzazione e sistema operativo

Di lavoro configurazione base:
- **Proxmox VE 9.2** sui due compute node;
- QNODE su Debian 13 stabile;
- guest Debian 13;
- container OCI/system containers solo dove utili.

Proxmox VE 9.2, rilasciato nel maggio 2026, è basato su Debian 13.5 e include HA, KVM/LXC, ZFS e netdi lavoro/SDN.

Debian stable al 18/09/2026 è la serie **13 Trixie**, point release corrente 13.7.

### Perché virtualizzazione, ma non Kubernetes configurazione base

VM/LXC separano:

- database;
- app;
- identity;
- observability;
- integration gateways.

Vantaggi:
- snapshot;
- migrazione;
- restore;
- resource limits;
- isolamento aggiornamenti.

Kubernetes resta `OPZIONALE / FUTURO`.

Per il numero di servizi previsto:
- systemd;
- Docker/Podman Compose;
- LXC/VM;

sono sufficienti e riducono modalità di guasto operative.

## 29. Distribuzione dei carichi applicativi

### VM/istanza DB
- PostgreSQL primario/replica;
- risorse riservate;
- niente noisy-neighbor.

### APPLICAZIONI
- API;
- pianificatore;
- workers;
- Stripe integration;
- retail correlation;
- traceability;
- maintenance.

Eseguire almeno due istanze stateless quando il servizio è P0/P1.

### EVENT
- NATS;
- bridge MQTT;
- command/event workers.

### IDENTITY
- Keycloak/OIDC;
- reverse proxy;
- internal CA/secrets integration.

### OBS
- Prometheus;
- Grafana;
- Loki;
- Grafana Alloy / OpenTelemetry collectors.

### FORECAST
- training/inference;
- batch jobs;
- isolabile dalle transazioni.

Il forecast può essere spento senza compromettere produzione/safety.

## 30. Database della configurazione base

**PostgreSQL è il database transazionale centrale.**

Versione di lavoro:
- PostgreSQL 18 current supported series;
- al 13/08/2026 la release pubblicata è 18.6.

PostgreSQL contiene:

- dati anagrafici principali;
- inventory;
- lots;
- orders;
- tasks;
- schedules;
- maintenance;
- payment state;
- recipes;
- asset registry;
- digital twin state;
- append-only business events.

### Telemetry

Configurazione base iniziale:
- PostgreSQL partitioned tables;
- retention policy;
- downsampling/materialized aggregates;
- cold archive su file Parquet/object storage.

TimescaleDB è opzionale dopo riferimento di confronto e verifica compatibilità.

Non introdurre un secondo database time-series obbligatorio se PostgreSQL sostiene il carico reale.

### Event IDs

Preferenza:
- UUIDv7 per eventi/entità temporali dove utile;
- monotonic/source sequence sui dispositivi;
- correlation_id;
- causation_id.

## 31. PostgreSQL HA

Di lavoro target:

- primary su NODE-A;
- synchronous/near-synchronous replica su NODE-B per transazioni critiche;
- WAL archive sul backup target;
- automatic failover solo dopo test.

Candidate:
- Patroni + 3-node DCS/quorum;
- oppure failover orchestrato internamente con runbook se la complessità Patroni non è giustificata.

RPO target:
- ordini/pagamenti/lotti: ~0 o pochi secondi;
- task/stato operativo: <30 s;
- telemetry non critica: <1–5 min accettabile grazie a edge buffering.

RTO target:
- checkout/ordini: <2–5 min;
- pianificatore: <5 min;
- dashboard: <15 min;
- analytics storiche: <4 h.

## 32. Bus eventi

Di lavoro:
- **NATS + JetStream**.

Perché:
- pub/sub;
- request/reply;
- durable streams;
- consumer state;
- replay;
- at-least-once;
- client multipiattaforma.

NATS documenta JetStream come persistence layer con replay e delivery at-least-once.

### HA

Stream business-critical:
- R3 su NODE-A, NODE-B e QNODE.

NATS raccomanda un numero dispari di server per il quorum JetStream; tre nodi consentono la perdita di un nodo mantenendo la maggioranza.

Non tutti gli stream devono essere R3.

Esempi R3:
- orders;
- payment;
- inventory;
- lot movement;
- task command;
- machine command ack;
- audit security.

Telemetry ad alta frequenza può essere:
- non persistente;
- R1;
- buffer edge + batch DB;

a seconda del valore.

## 33. MQTT e OT ingress

Molti sensori/controller parlano MQTT, Modbus o OPC UA.

Pattern:

`field -> edge gateway -> normalized event -> NATS/PostgreSQL`

MQTT broker edge:
- Eclipse Mosquitto o equivalente.

Regola:
- il field device non deve conoscere schema interno del database;
- gateway valida unità, timestamp, asset ID e qualità.

OT ingress:
- OPC UA;
- Modbus TCP/RTU;
- fornitore REST;
- serial gateway.

Ogni adapter ha:
- health;
- retry;
- dead-letter/error stream;
- last-seen;
- firmware/config version.

## 34. Digital twin / state model

Ogni asset ha:

- static identity;
- capabilities;
- observed state;
- desired state;
- health;
- location;
- owner subsystem;
- maintenance state;
- command eligibility.

Pattern:

`desired_state != command != observed_state`

Il server non dichiara successo perché ha inviato il comando.

Serve:
- command_id;
- accepted;
- started;
- completed;
- failed;
- observed confirmation.

Per macchine safety-critical, il controller locale può rifiutare un comando centrale.

## 35. API contracts

### Synchronous
- REST/HTTP;
- OpenAPI 3.1;
- JSON;
- explicit versioning.

### Asynchronous
- NATS subjects;
- AsyncAPI/schema registry in repository;
- JSON Schema o Protobuf per eventi stabili.

Naming di lavoro:

`domain.entity.event.v1`

Esempi:
- `inventory.lot.moved.v1`;
- `retail.cart.item_added.v1`;
- `energy.bess.mode_changed.v1`;
- `irrigation.zone.completed.v1`.

### Commands

Separare semanticamente:
- event = fatto accaduto;
- command = richiesta;
- query = lettura.

Mai usare un event name come comando.

## 36. Device registry

Tabella/servizio centrale:

- device_id;
- asset_id;
- fornitore;
- model;
- serial;
- protocol;
- IP/MAC;
- certificate;
- firmware;
- location;
- owner;
- last seen;
- maintenance;
- config hash.

Onboarding:
1. inventory;
2. identity;
3. network segment;
4. certificate/credential;
5. protocol profile;
6. simulator test;
7. production enable.

## 37. Pianificatore architecture

Pianificatore custom, non ERP esterno.

Componenti:

### Planner
Costruisce piano ottimizzato a orizzonte:
- ore;
- giorno;
- settimana.

### Dispatcher
Trasforma piano in:
- worker task;
- AMR mission;
- process job;
- irrigation job;
- refill.

### Reconciler
Confronta:
- planned;
- accepted;
- started;
- actual;
- failed.

### Replanner
Ricalcola solo quando trigger significativo cambia:
- stockout;
- fault;
- forecast;
- weather;
- worker absence;
- batch delay;
- BESS state.

Non ricalcolare l'intera azienda a ogni sensor sample.

## 38. Forecasting stack

Configurazione base:
- Python service o libreria equivalente;
- feature pipeline versionata;
- model registry semplice nel repository/DB;
- metrics per SKU/crop.

Prima modelli:
- seasonal configurazione base;
- moving/exp smoothing;
- gradient boosting/regression dove migliora;
- quantile intervals.

Non partire da deep learning se non supera configurazione base.

Demand metrics:
- WAPE;
- MAE;
- bias;
- stockout-adjusted error.

Supply:
- kg/day error;
- harvest-window error;
- quality-class error.

Automatic execution consentita solo entro guardrail deterministici.

## 39. Identity e RBAC

Di lavoro:
- Keycloak/OIDC class per persone;
- service accounts separate per macchine;
- MFA admin;
- short-lived tokens;
- mTLS/certificates per servizi/edge dove utile.

Ruoli:
- admin;
- operations;
- agronomy;
- maintenance;
- logistics;
- sales;
- food/QC;
- visitor;
- read-only.

Non condividere account tra operatori.

## 40. Secrets

Configurazione base:
- niente secret in Git;
- SOPS/age o secret manager equivalente;
- rotation;
- separate prod/dev;
- device credentials individuali.

Stripe secret:
- solo server;
- restricted keys dove possibile;
- webhook secrets separati.

## 41. Network

Segmenti minimi:

- MGMT;
- SERVER;
- OT;
- EDGE;
- CCTV;
- VENDING;
- GUEST;
- BACKUP.

Inter-VLAN:
- default deny;
- allowlist.

Server interconnect:
- 10 GbE preferito tra compute/backup.

Riferimento di confronto netdi lavoro:
- UniFi Pro Max 24: €405 EU Store;
- Pro XG 10 PoE: €629 EU Store, 10×10GbE + 2×SFP+;
- DAC 10G da €12;
- SFP+ multimode da €18.

La scelta switch finale dipende dalla topologia totale, non dalla sola BOM-030.

## 42. Remote access

Configurazione base:
- VPN WireGuard/site VPN;
- MFA;
- bastion/admin path;
- no exposed Proxmox/Postgres/PLC admin UI on public Internet.

Fornitore access:
- disabled by default;
- time-limited;
- logged;
- scoped to asset/VLAN.

## 43. Observability

Di lavoro stack:
- Prometheus;
- Grafana;
- Loki;
- Grafana Alloy/OpenTelemetry.

Prometheus:
- usare release supportata; Prometheus 3.13 è LTS fino al 31/07/2027, mentre 3.14.0 è current release 17/08/2026.

Alloy:
- collector unico per metrics/logs/traces dove utile.

Dashboard principali:
- platform;
- DB;
- queue;
- device health;
- integration;
- pianificatore;
- payments;
- cold chain;
- BESS.

Alert severity:
- INFO;
- WARNING;
- P2;
- P1.

Ogni alert P1/P2 deve avere owner e runbook.

## 44. Logs e audit

Separare:

### application logs
Debug/operations.

### audit events
Immutabili logicamente:
- login;
- permission change;
- manual override;
- price change;
- payment action;
- command;
- recipe change;
- QC release.

Audit non deve essere cancellato dal normale log rotation.

Retention da politica aziendale/privacy e requisiti applicabili.

## 45. Backup strategy

Regola **3-2-1** di lavoro:

1. dato primario;
2. backup locale separato;
3. copia off-site cifrata.

### PostgreSQL
- streaming replica;
- base backup;
- continuous WAL archive;
- restore test.

### VM/LXC
- Proxmox Backup Server class;
- deduplication/incremental;
- retention.

### Object/files
- snapshots;
- checksum;
- offsite copy.

### Config
- Git;
- encrypted secrets backup;
- device config export.

Un backup non testato non è un backup.

## 46. Backup software

Candidate:
- Proxmox Backup Server 4.2;
- pgBackRest for PostgreSQL;
- restic/rclone class for encrypted offsite files.

Proxmox Backup Server subscription è opzionale:
- Community riferimento di confronto €560/year per server;
- Basic €1.120/year;
- software resta open source.

## 47. Proxmox support

PVE può funzionare senza subscription.

Per produzione di lavoro:
- Basic o Standard da valutare.

Prezzi ufficiali correnti:
- Community €120/year per occupied CPU socket;
- Basic €370/year/socket;
- Standard €550/year/socket;
- Premium €1.100/year/socket.

Con 2 compute single-socket:
- Basic = €740/year;
- Standard = €1.100/year.

Non contabilizzare automaticamente Premium.

## 48. BESS integration

**Nessuna UPS locale configurazione base.**

Rack/server/network sono P0/P1 sul BESS da 30 kW.

Il server legge:
- grid status;
- inverter status;
- SOC;
- available power;
- estimated autonomy;
- island mode.

Il server non controlla le protezioni BESS.

In LOW_SOC:
1. stop training/forecast heavy;
2. reduce historical analytics;
3. defer charging/optional jobs;
4. keep DB/event/network/edge;
5. preserve cold-chain control connectivity.

Dimensionare backup sull'energia utile in kWh, ancora da chiudere.

## 49. Capacity sizing

La farm automation non richiede hyperscale.

Initial target per compute node:
- 8–16 physical cores class;
- 64–128 GB ECC;
- 2×1,92 TB enterprise NVMe mirror;
- 10 GbE;
- remote management.

Budget RAM indicative:
- DB: 16–32 GB;
- app/workers: 8–16 GB;
- observability: 8–16 GB;
- identity/infra: 4–8 GB;
- forecast burst: 8–32 GB.

Non overcommit DB RAM.

Vision training pesante:
- workstation/GPU dedicata o cloud;
- non sul control-plane primary.

Inference edge:
- Jetson/OAK/edge node già previsti per i domini specifici.

## 50. Environments

Separare:
- DEV;
- STAGING/SIM;
- PROD.

Staging deve includere simulatori:
- PLC;
- AMR;
- vending;
- Stripe test mode;
- BESS;
- temperature sensor.

Nessun test distruttivo direttamente su produzione.

## 51. Deployment pipeline

Di lavoro:
- Git;
- CI tests;
- image build;
- signed/tagged release;
- staging;
- migration check;
- manual production approval;
- rollback.

Database:
- forward-compatible migrations;
- backup before risky migration;
- no automatic destructive schema migration.

## 52. Cybersecurity configurazione base

- inventory;
- patch cadence;
- CVE review;
- MFA;
- RBAC;
- least privilege;
- VLAN/firewall;
- TLS;
- certificate rotation;
- host firewall;
- disk encryption where appropriate;
- secure boot/TPM where supported;
- immutable/offsite backup;
- restore drill;
- incident log.

No direct inbound Internet to OT.

## 53. SLO / RPO / RTO

Di lavoro SLO:

| Servizio | Availability target | RPO | RTO |
|---|---:|---:|---:|
| payment/order | 99,9% | ~0–5 s | <2–5 min |
| core inventory/lot | 99,9% | <30 s | <5 min |
| pianificatore | 99,5% | <1 min | <5 min |
| OT event ingress | 99,5% | edge-buffered | <10 min |
| dashboards | 99% | n/a | <15 min |
| analytics/forecast | 95% | <24 h | <4 h |

Questi sono target di progetto, non SLA fornitore.

## 54. Scenari di disastro

### NODE-A dies
- NODE-B takes core workloads;
- QNODE keeps quorum;
- alert;
- no safety impact.

### NODE-A + NODE-B unavailable
- edge local safe mode;
- PLC continue;
- store/payment unavailable;
- restore from backup/replacement hardware.

### Internet dies
- local production continues;
- Stripe transactions follow tested offline policy;
- fornitore clouds unavailable;
- events buffered.

### NAS/backup dies
- production continues;
- repair backup before maintenance risk increases.

### Database corruption
- stop destructive writes;
- promote clean replica only after checks;
- PITR from WAL if required.

### Ransomware/admin compromise
- isolate;
- preserve audit;
- revoke credentials;
- restore from offsite/immutable backup.

## 55. Acceptance test BOM-030

1. NODE-A power-off during production simulation;
2. NODE-B failover;
3. QNODE loss;
4. switch/link failure;
5. Internet loss;
6. BESS mode;
7. low SOC;
8. PostgreSQL primary failure;
9. NATS node failure;
10. event replay;
11. duplicate event/idempotency;
12. delayed Stripe webhook;
13. MQTT edge buffer/replay;
14. backup full;
15. point-in-time DB restore;
16. VM restore;
17. offsite restore;
18. Keycloak/identity outage;
19. expired certificate;
20. pianificatore worker failure;
21. forecasting unavailable;
22. clock drift;
23. RBAC unauthorized action;
24. device credential revoke;
25. simulated incident/runbook.

## 56. BOM-030 decision

**Di lavoro configurazione base:**
- 2 server-grade compute nodes;
- 1 lightweight witness/edge node;
- 1 physically separate backup target;
- 10 GbE server interconnect;
- Proxmox VE;
- Debian;
- PostgreSQL;
- NATS JetStream;
- MQTT edge ingress;
- Keycloak/OIDC;
- Prometheus/Grafana/Loki/Alloy;
- Git/CI;
- BESS 30 kW as shared backup.

**Explicitly not configurazione base:**
- Kubernetes;
- Ceph;
- SAN;
- GPU nel piano di controllo;
- UPS locale;
- database solo cloud;
- ERP proprietario come sistema autorevole dei dati.

## 57. Verifica prima dell'acquisto

Prima dell'ordine:

1. rack/posizione;
2. calore/polvere/ambiente;
3. BESS kWh/autonomy;
4. dimensionamento calcolo;
5. obiettivo RAM ECC;
6. durata storage;
7. 10GbE topology;
8. QNODE;
9. backup capacity/retention;
10. offsite target;
11. Proxmox support level;
12. three hardware quotes where practical;
13. restore test design;
14. commissioning plan.

Documenti BOM-030:
- `CENTRAL_ORCHESTRATION_SERVER.md`;
- `RFQ_CENTRAL_ORCHESTRATION_SERVER.md`;
- `SERVER_ACCEPTANCE_DR_RUNBOOK.md`;
- `EVENT_API_CONTRACTS.md`;
- `19_BOM_PRODOTTI_FORNITORI/AUTOMAZIONE_SERVER_CENTRALE.md`;
- `22_FONTI_NORME_PREVENTIVI/AUTOMAZIONE_SERVER_CENTRALE_SOURCES.md`.
