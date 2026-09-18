# Central orchestration server — architettura di governo aziendale

**Aggiornato:** 18 settembre 2026  
**Stato:** `ARCHITETTURA BASE / SERVER CENTRALE COME SYSTEM OF RECORD E SCHEDULER / DETTAGLI DEPLOYMENT E BOM HARDWARE DA SVILUPPARE`.

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

Il server è il **system of record** per le operazioni aziendali.

## 2. Separazione fondamentale: planning vs safety/control

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

`server down != impianto unsafe`

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
- Stripe;
- vend;
- refund;
- temperatura;
- scadenze.

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
- condition-based maintenance;
- ricambi;
- work order;
- failure history.

### Visitatori
- calendario visite;
- VISIT MODE;
- zone interdette;
- lockout dinamici;
- staffing.

## 4. Event ledger

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
- vending_sale_created;
- stripe_payment_authorized;
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

## 5. System of record

Il server centrale mantiene master data per:

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

Quando un vendor mantiene il proprio cloud:
- il server importa gli eventi necessari;
- non delega al cloud vendor il master aziendale;
- deve poter esportare tutti i dati;
- il sistema deve sopravvivere alla sostituzione del vendor.

## 6. Scheduler operativo

Il scheduler genera un piano temporale unico combinando:

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

Lo scheduler deve:
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

AMR e operatori ricevono missioni dallo stesso scheduler.

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

Flusso working:

`selection -> reserve stock -> create PaymentIntent -> collect/confirm -> payment webhook -> authorize vend -> vend -> vend_ack -> close order`

Se il prodotto non viene erogato:
- non considerare l'ordine completato;
- avviare recovery/refund secondo stato PaymentIntent e policy.

Tutte le operazioni esterne devono usare:
- idempotency key;
- correlation id;
- retry controllato;
- state machine esplicita.

## 13. Stripe Terminal unattended

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

Stripe è il payment stack unico della baseline.

## 14. Integrazione vending

Preferenza:
- macchina con API/SDK/protocollo documentato;
- accesso a vend result;
- slot state;
- temperature;
- door/service events;
- faults;
- inventory telemetry.

MDB da solo può essere insufficiente per l'orchestrazione completa.

Se il vendor non espone API adeguate:
- gateway locale;
- controller I/O/protocol adapter;
- event bridge verso server.

Il server deve sapere la differenza tra:
- pagamento riuscito;
- comando erogazione inviato;
- erogazione fisicamente confermata.

## 15. BESS e continuità

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

Con BESS attivo, lo scheduler può ridurre o rimandare P3 prima di sacrificare P0/P1.

## 16. Database

Architettura logica consigliata:

- relational DB per master data/transazioni;
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

## 17. API e integrazioni

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
- vendor API;
- Stripe webhooks;
- file/CSV solo come fallback.

## 18. Offline/edge

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

## 19. Human interface

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

## 20. Audit e tracciabilità

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

## 21. AI/forecast governance

Distinguere:

- prediction;
- recommendation;
- automatic execution.

Ogni modello deve avere:
- versione;
- dataset window;
- metriche;
- drift monitoring;
- fallback;
- limiti operativi.

Azioni ad alto impatto richiedono regole deterministicamente verificabili anche se suggerite da AI.

## 22. Security

Baseline:

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

## 23. Observability

Metriche:
- uptime;
- queue lag;
- task latency;
- API failures;
- device offline;
- webhook failures;
- DB health;
- forecast error;
- scheduler replan rate;
- payment reconciliation mismatch;
- inventory variance.

Alert con severity e owner.

## 24. Failure modes

| Failure | Comportamento |
|---|---|
| server down | local safe mode + no nuove missioni non sicure |
| DB down | stop nuove transazioni critiche, queue dove sicuro |
| event bus down | local buffer + backpressure |
| Internet down | operazioni locali consentite secondo policy; cloud integrations degradate |
| Stripe down | niente nuove vendite che richiedono pagamento |
| webhook delayed | state machine resta pending, no double-vend |
| vending controller down | slot/machine disabled |
| forecast service down | scheduler usa baseline/rules |
| BESS low SOC | load shedding P3/P2 secondo policy |
| clock drift | alert + reject critical ordering if timestamp integrity lost |

## 25. KPI

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

## 26. Gate successivo

Da sviluppare come package dedicato:

1. deployment target;
2. server hardware/VM/container strategy;
3. DB/event stack;
4. identity;
5. network topology;
6. edge gateways;
7. device registry;
8. API contracts;
9. data model;
10. scheduler MVP;
11. forecasting MVP;
12. Stripe integration;
13. digital traceability;
14. backup/restore;
15. observability;
16. cybersecurity;
17. acceptance test end-to-end.
