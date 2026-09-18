# RFQ — Spaccio automatico self-service 24/7 BOM-028

**Progetto:** Carnia TerraTech  
**Aggiornato:** 18 settembre 2026  
**Stato:** `RFQ TEMPLATE / SKU, REGIME SUAP, TEMPERATURE E LAYOUT DA VALIDARE`.

## 1. Oggetto

Richiesta di offerta separata e comparabile per:

- vending food refrigerato;
- vending/locker per prodotti fragili;
- eventuale modulo ambient/cool;
- kiosk/shell o protezione outdoor;
- integrazione Stripe Terminal unattended;
- telemetria macchina verso server centrale;
- fiscalizzazione/corrispettivi;
- logging temperature;
- quadro/linee elettriche;
- rete;
- videosorveglianza;
- illuminazione;
- API/protocol adapter verso server centrale;
- smart crate / smart cart / ESL / exit gate R&D;
- installazione;
- training;
- SLA e ricambi.

L'offerta deve distinguere hardware, licenze, fee transazione, installazione e OPEX.

## 2. Dati da fornire al vendor

Prima dell'offerta definitiva:

- indirizzo/installazione;
- ambiente indoor/protetto/outdoor;
- temperature min/max locali;
- lista SKU;
- dimensioni e peso pack;
- temperatura target per SKU;
- vendite/giorno attese;
- refill frequency;
- picchi;
- alimentazione disponibile;
- rete Ethernet/Wi-Fi/4G;
- regime fiscale/commerciale;
- account/architettura Stripe già scelta;
- esigenze accessibilità;
- CCTV/NVR disponibile;
- backup elettrico BESS aziendale 30 kW; capacità/autonomia in kWh da confermare.

## 3. Lotto A — vending machine

Quotare almeno tre configurazioni:

### A1 — food refrigerato a spirale
Classe Necta Gusto 8 Food o equivalente.

### A2 — food con ascensore
Classe Necta Gusto 8 Lift o equivalente.

### A3 — drum/locker
Classe Necta Gusto Drum / FAS Easy Food o equivalente.

Per ciascuna indicare:

- marca/modello;
- configurazione;
- numero selezioni;
- capacità;
- dimensioni;
- peso;
- potenza nominale;
- consumo annuo certificato se disponibile;
- refrigerante;
- temperature configurabili;
- numero zone;
- classe energetica;
- protocollo MDB/Executive;
- payment compatibility;
- telemetry;
- vend control;
- expiry/FIFO;
- vandal resistance;
- accessibilità;
- rumore;
- scarico condensa;
- intervallo temperatura ambiente ammesso;
- indoor/outdoor rating;
- garanzia;
- ricambi;
- assistenza Italia.

## 4. Test SKU obbligatorio

Prima dell'ordine definitivo il vendor deve accettare test con packaging reale:

- pomodoro;
- peperone;
- lattuga/leaf;
- baby leaf;
- basilico;
- eventuali trasformati futuri.

Per ogni SKU:

- dimensioni;
- peso;
- slot;
- temperatura;
- caduta;
- jam;
- deformazione;
- danno;
- tempo refill.

Acceptance:
- >=100 cicli per SKU critico;
- target jam <1%;
- nessun danno sistematico;
- refund workflow verificato.

## 5. Lotto B — protezione kiosk/outdoor

Se macchina non certificata outdoor, quotare:

- shell/locale;
- tetto;
- pareti;
- ventilazione;
- anticondensa;
- protezione sole;
- pavimento;
- porta cliente;
- porta service;
- ancoraggi;
- drenaggio;
- illuminazione;
- serrature;
- manutenzione.

Dichiarare:

- range termico interno;
- carichi struttura;
- neve/vento se struttura esterna;
- compatibilità manutenzione vending;
- passaggi cavi;
- accessibilità.

## 6. Lotto C — Stripe Terminal unattended

Stripe è il payment stack richiesto; non quotare payment stack alternativi.

Quotare/validare una soluzione Stripe Terminal per ambiente realmente unattended.

Working candidate:
- **Verifone UX700** tramite Stripe Terminal, o successivo dispositivo unattended ufficialmente supportato in Italia.

Richiedere:

- disponibilità Italia;
- hardware e accessori;
- montaggio;
- alimentazione;
- Ethernet/Wi-Fi;
- IP/IK;
- temperatura ambiente;
- integrazione server-driven/API;
- PaymentIntent;
- webhook;
- refund;
- reconciliation;
- device management;
- modalità offline supportata nella configurazione proposta;
- behavior in perdita Internet;
- behavior in perdita server;
- PCI/EMV;
- SLA.

Il server Carnia TerraTech gestisce ordine, stato vendita e riconciliazione. Il terminale non deve diventare il database commerciale.

Flusso da supportare:

`reserve_stock -> create PaymentIntent -> collect payment -> webhook/confirm -> vend command -> vend_ack -> close order`

Requisito bloccante:
- nessuna doppia erogazione in caso di retry;
- nessun ordine chiuso prima del `vend_ack`;
- refund automatico/assistito quando pagamento e vend divergeno.

Le fee Stripe vengono modellate separatamente dal costo hardware.

## 7. Lotto D — fiscalizzazione

Richiedere soluzione/documentazione per configurazione italiana.

Indicare:

- modello operativo;
- censimento macchina;
- modulo fiscale richiesto;
- telemetria;
- dati memorizzati;
- trasmissione;
- gestione fault;
- aggiornamenti normativi;
- canone;
- assistenza;
- responsabilità operative del gestore;
- export dati commercialista;
- compatibilità con payment provider.

Non accettare "fiscal ready" senza descrizione tecnica e contrattuale.

## 8. Lotto E — temperature monitoring

Quotare:

- logger indipendente per ogni zona critica;
- sonda;
- memoria locale;
- Wi-Fi/LTE;
- allarmi;
- cloud;
- licenze;
- calibrazione;
- batteria/alimentazione;
- report export;
- spare logger.

Working benchmark:
- Testo 160 T / sistema Testo 162 food-capable / equivalente.

## 9. Lotto F — electrical

Quotare:

- linea vending;
- linea IT/security;
- quadro;
- magnetotermici/differenziali;
- SPD;
- prese/manutenzione;
- sezionatore;
- energy meter;
- cavi;
- cavidotti;
- scavi;
- messa a terra;
- as-built;
- prove.

Separare alimentazione compressore da elettronica critica.

## 10. Lotto G — continuity / BESS

**Non quotare UPS locali.**

Il sito dispone di backup a batterie con **30 kW di potenza**.

Richiedere soltanto:

- potenza nominale vending;
- spunto;
- duty cycle;
- energia giornaliera;
- power-fail output;
- restart behavior;
- recovery dopo ritorno rete;
- compatibilità con alimentazione da BESS/inverter;
- priorità carico;
- eventuali requisiti di tempo di trasferimento.

Il package energia deve chiudere:

- capacità BESS utile in kWh;
- autonomia;
- islanding;
- SOC reserve;
- load shedding.

Lo spaccio deve poter ricevere dal server uno stato energia:
- NORMAL;
- BACKUP;
- LOW_SOC;
- SHED_NONCRITICAL.

Nessuna UPS desktop o dedicata entra nel CAPEX BOM-028.

## 11. Lotto H — network

Quotare:

- Ethernet;
- 4G backup;
- router;
- switch;
- PoE;
- VLAN;
- firewall;
- remote access;
- surge protection;
- monitoring.

Requisito:
- nessuna reachability non necessaria verso PLC/OT.

## 12. Lotto I — CCTV

Working:
- 1–2 camera PoE classe Ubiquiti G5 Turret Ultra o equivalente;
- NVR locale;
- storage;
- alimentazione sul BESS aziendale;
- cartello;
- configurazione privacy.

Dichiarare:
- campo visivo;
- IP/IK;
- IR;
- risoluzione;
- retention calcolata;
- storage;
- export;
- access control;
- no audio baseline.

## 13. Lotto J — integrazione macchina con server centrale

Non quotare un software vendor come system of record.

Il server Carnia TerraTech gestisce direttamente:

- SKU master;
- slot map;
- stock;
- lotto;
- expiry;
- price;
- sales;
- Stripe payment state;
- vend state;
- refill;
- waste;
- temperature;
- alarms;
- maintenance;
- task personale;
- logistica;
- forecasting domanda/offerta.

Il vendor deve quindi dichiarare e quotare:

- API/SDK/protocollo;
- documentazione;
- event feed;
- vend command;
- vend result/ack;
- slot state;
- door/service events;
- faults;
- temperature readout;
- remote disable;
- simulator/test mode;
- rate limits;
- licensing API;
- support versioning.

Preferiti:
- REST/HTTP;
- MQTT;
- WebSocket;
- protocollo documentato.

Se disponibile solo MDB/protocollo proprietario:
- quotare gateway/adattatore;
- fornire protocol documentation sufficiente;
- nessun lock-in sul dato operativo.

Il cloud vendor può restare opzionale per diagnostica, ma il server aziendale deve poter funzionare come master operativo.

## 14. Lotto K — frictionless smart crate / smart cart

Quotare separatamente, come pilot R&D, senza inglobare nel vending base:

### K1 smart crate

Per 3–10 cassette pilota:

- struttura/base;
- load cells;
- ADC/edge I/O;
- tare management;
- temperature/environment rating;
- removable crate interface;
- calibration;
- API/event output;
- service access.

Dichiarare esplicitamente se la catena di misura è:
- solo sensing;
- oppure legal-for-trade.

Non accettare celle di carico commodity presentate come bilancia commerciale senza documentazione metrologica.

### K2 weighing legal-for-trade

Richiedere proposta tecnica per prodotti venduti a peso:

- M1 modulo certificato per smart crate/cluster;
- M3 stazione di conferma certificata/fallback;
- M2 cart scale solo come alternativa se realmente certificabile.

Richiedere:
- normativa applicata;
- marcature;
- classe;
- portata/divisione;
- tara;
- verifica periodica;
- installazione;
- display cliente;
- API/export;
- costo verifica/manutenzione.

### K3 smart cart

1–2 carrelli pilota:

- display 7–10";
- SBC/edge;
- Wi-Fi/BLE;
- UWB opzionale;
- camera;
- mass sensor cross-check;
- battery;
- dock;
- IP/mechanical protection;
- cart ID;
- API.

Il display deve ricevere dal server:
- basket;
- peso;
- prezzo;
- totale;
- payment state;
- error/customer confirmation.

### K4 ESL/e-paper

Quotare:

- 30 / 60 / 100 etichette;
- waterproof fresh-area option;
- BLE/infrastructure;
- API;
- battery life;
- mounting;
- spare rate;
- price update latency;
- optional LED/pick-to-light.

L'ESL è una per posizione SKU/cassetta, non una per singolo prodotto.

### K5 event cameras / localization

Quotare:

- overhead camera;
- cart camera;
- BLE/UWB anchors;
- event timestamping;
- privacy masking;
- API/event stream.

No face recognition.

### K6 exit gate

Quotare:

- gate;
- cart identification;
- server input;
- paid-state input;
- emergency release;
- fire/evacuation override;
- anti-tailgating solo se compatibile con safety;
- manual opening;
- accessibility.

Il gate non deve impedire l'esodo delle persone.

### K7 cart return

Baseline:
- nested return/charging dock.

Optional:
- hitch/cart train compatibile con futuro recovery rover.

Non quotare ogni carrello come veicolo autonomo baseline.

## 15. Lotto L — signage/customer support

Quotare:

- insegna;
- istruzioni acquisto;
- prezzi;
- contatti assistenza;
- QR refund;
- privacy CCTV;
- allergen/label info support;
- accessibilità;
- cartello temporaneo out-of-service.

## 16. Lotto M — spares

Kit iniziale:
- motors/spirals;
- sensors;
- locks;
- keys;
- fans;
- filters;
- fuses;
- power supply;
- payment cable;
- spare payment path;
- logger;
- Ethernet surge protector;
- camera spare or fast SLA.

## 17. SLA

Richiedere prezzi separati:

- remote response;
- on-site response;
- weekday;
- weekend;
- refrigeration;
- payment;
- telemetry;
- fiscal;
- spare shipping.

Target da quotare:
- P1 refrigeration/payment full stop <= next business day;
- P2 telemetry/camera <= 2 business days;
- ricambi critici stocked in Italy/NE Italy preferred.

## 18. Acceptance

Prima del saldo:

1. installazione meccanica;
2. electrical test;
3. network segmentation;
4. Stripe Terminal 50 test transactions;
5. refund test;
6. fiscal flow test;
7. temperature pull-down;
8. high-temp alarm;
9. simulated power fail;
10. simulated network fail + delayed webhook;
11. expiry lockout;
12. 500 vending cycles mixed SKU;
13. smart crate/cart add-return test su almeno 10 SKU;
14. jam handling;
15. camera field/privacy check;
16. NVR retention check;
17. inventory reconciliation server/vending/cart/crate;
18. 24 h unattended soak test con scheduler centrale;
19. cleaning procedure;
20. as-built;
21. training;
22. metrology acceptance for all weight-priced flows.

## 19. Formato economico

Per ogni riga:

| Campo | Richiesto |
|---|---|
| codice | sì |
| marca/modello | sì |
| quantità | sì |
| prezzo netto | sì |
| IVA | separata |
| installazione | separata |
| trasporto | separato |
| setup | separato |
| canone | €/mese |
| fee | % / transazione |
| cloud | €/mese/anno |
| SIM | €/mese |
| fiscal service | €/mese/anno |
| maintenance | €/anno |
| spare kit | € |
| garanzia | mesi |
| SLA | ore/giorni |
| lead time | giorni/settimane |

## 20. Varianti da confrontare

- Gusto 8 standard vs Lift;
- spirale vs drum/locker;
- single temperature vs stratified;
- kiosk protetto vs true outdoor certified;
- Stripe UX700 unattended vs successivo device unattended ufficialmente supportato;
- API nativa vending vs gateway/protocol adapter;
- vendor cloud diagnostics only vs no vendor cloud;
- 1 camera vs 2;
- smart crate M1 vs M3 legal-for-trade strategy;
- Stripe UX700 fixed exit vs reader-on-cart future;
- nested charging vs recovery-rover interface;
- priorità BESS/load shedding diverse, senza UPS locale.

Ogni variante deve avere TCO a 5 anni.
