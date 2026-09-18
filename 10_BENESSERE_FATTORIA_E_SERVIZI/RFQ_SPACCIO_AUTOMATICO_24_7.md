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
- sistema pagamento cashless;
- telemetria;
- fiscalizzazione/corrispettivi;
- logging temperature;
- quadro/linee elettriche;
- rete;
- videosorveglianza;
- illuminazione;
- software inventario;
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
- desiderata cashless;
- esigenze accessibilità;
- CCTV/NVR disponibile;
- backup elettrico disponibile.

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

## 6. Lotto C — payment

Quotare cashless all-in-one.

Working candidate:
- Nayax VPOS Touch / VPOS Media 4 / equivalente.

Dichiarare:

- acquisto hardware;
- setup;
- SIM;
- canone mensile;
- fee transazione per fascia importo;
- minimum fee;
- carte supportate;
- Apple Pay/Google Pay;
- protocollo MDB;
- telemetry;
- inventory;
- refund;
- remote management;
- offline mode;
- settlement;
- API/export;
- contratto minimo;
- SLA.

Cash module:
- OPTIONAL;
- prezzo separato;
- manutenzione e rischio separati.

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

## 10. Lotto G — continuity

Quotare:

### G1 electronics UPS
Per:
- router;
- switch;
- NVR;
- controller;
- payment/telemetry.

Dichiarare runtime a carico reale.

### G2 integration backup generale
- interface con generatore/EMS aziendale;
- priority load;
- power fail signal.

Non proporre UPS piccola come backup prolungato del compressore senza calcolo.

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
- UPS;
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

## 13. Lotto J — software inventory

Richiedere:

- SKU master;
- slot map;
- stock;
- expiry;
- price;
- lot;
- sales;
- refill list;
- waste;
- telemetry;
- alarm;
- CSV/API;
- user roles;
- audit log.

Dichiarare:
- cloud/on-prem;
- cost/month;
- API;
- backup;
- export on termination.

## 14. Lotto K — signage/customer support

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

## 15. Lotto L — spares

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

## 16. SLA

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

## 17. Acceptance

Prima del saldo:

1. installazione meccanica;
2. electrical test;
3. network segmentation;
4. payment 50 test transactions;
5. refund test;
6. fiscal flow test;
7. temperature pull-down;
8. high-temp alarm;
9. simulated power fail;
10. simulated network fail;
11. expiry lockout;
12. 500 vending cycles mixed SKU;
13. jam handling;
14. camera field/privacy check;
15. NVR retention check;
16. inventory reconciliation;
17. 24 h unattended soak test;
18. cleaning procedure;
19. as-built;
20. training.

## 18. Formato economico

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

## 19. Varianti da confrontare

- Gusto 8 standard vs Lift;
- spirale vs drum/locker;
- single temperature vs stratified;
- kiosk protetto vs true outdoor certified;
- Nayax vs secondo provider cashless;
- cloud vendor vs export/API integration;
- 1 camera vs 2;
- electronics UPS vs no UPS + generator interface.

Ogni variante deve avere TCO a 5 anni.
