# Analisi problematiche, rischi e vulnerabilità trasversali — Carnia TerraTech

**Aggiornato:** 18 settembre 2026  
**Stato:** `ANALISI RISCHI MASTER / PROBABILITÀ DA POPOLARE CON DATI REALI`

## 1. Scopo

Questo documento raccoglie in un solo punto:

- problematiche già presenti;
- rischi futuri;
- vulnerabilità di progetto;
- segnale di attivazione di escalation;
- mitigazioni;
- responsabile;
- condizione di chiusura.

Distinzione fondamentale:

- **problematica** = condizione già esistente e verificata che blocca o limita una decisione;
- **rischio** = evento o condizione futura/incerta che può produrre un impatto negativo;
- **vulnerabilità** = caratteristica del progetto che aumenta l'impatto se il rischio si materializza.

Non vengono assegnate probabilità numeriche senza dati reali.

## 2. Classificazione impatto

La severità qui indica **conseguenza potenziale**, non probabilità.

| Classe | Significato |
|---|---|
| I4 — CRITICAL | può bloccare finanziamento, acquisto, costruzione, messa in servizio, safety, conformità o continuità P0 |
| I3 — HIGH | può modificare materialmente CAPEX, tempi, resa, OPEX o operatività |
| I2 — MEDIUM | può degradare performance o creare costi/ritardi recuperabili |
| I1 — LOCAL | impatto circoscritto, recuperabile senza revisione del progetto |

La probabilità resta:
- `TBD`;
- `MEASURED`;
- `VENDOR EVIDENCE`;
- `SITE EVIDENCE`;

finché esistono evidenze sufficienti.

## 3. Problematiche già presenti

| ID | Problematica attuale | Impatto | Perché è reale | Azione di chiusura |
|---|---|---|---|---|
| P-01 | pacchetto finanziario non ancora perfezionato | I4 | contributi, anticipo, garanzia, finanziamento, linea IVA e ponte non sono ancora reale/concessi nel register | chiudere DG0/F0 con atti reali |
| P-02 | lotto reale non ancora acquisito/validato | I4 | blocca geotecnica, layout, DSO, neve/vento, drenaggi, accessi e RFQ installati | due diligence + DG1 |
| P-03 | crop card P1 non finali | I3 | blocca carichi idrici/termici, resa, raccolta, freddo e packaging | completare crop card per i 3 comparti P1 |
| P-04 | major CAPEX ancora prevalentemente E0/E1 | I4 | €850k è control budget, non costo contrattuale | RFQ installati comparabili E3/E4 |
| P-05 | profilo elettrico P0/P1 reale non disponibile | I4 | BESS 30 kW e 60/90/120 kWh non possono essere chiusi | misure 1–15 min + transitori |
| P-06 | DSO/POD/BT-MT non determinati | I4 | non è noto il costo/assetto reale della connessione | lotto + DSO/TICA reale |
| P-07 | pilot Q3 non ancora eseguiti | I3 | AMR, retail, mower, rover galline e riuso non hanno evidence site-specific | eseguire master pilot register |
| P-08 | SAT/commissioning ancora solo pianificato | I4 | continuità, failover e performance non sono ancora provate | eseguire master SAT |
| P-09 | OPEX reale non misurato | I3 | energia, lavoro, manutenzione, packaging e logistica sono ancora di pianificazione | 30/90-day reale review |
| P-10 | domanda P1 da validare commercialmente | I4 | €250k/y è target di validazione, non vendite acquisite | pre-vendita, clienti, ordini e channel validation |

## 4. Rischi finanziari e di cassa

### R-FIN-01 — ritardo o riduzione del sostegno
**Impatto:** I4.

Evento:
- concessione inferiore al previsto;
- anticipo non ottenibile nei tempi;
- garanzia insufficiente;
- SAL/saldo più lento del previsto.

Conseguenza:
- cantiere avviato senza copertura;
- necessità di ponte più elevato;
- erosione della riserva operativa;
- stop lavori.

Mitigazione:
- DG0 prima di ogni spesa irreversibile;
- cashflow mensile;
- payment schedule fornitori;
- ponte dedicato;
- nessuna contabilizzazione di contributi come incassati prima dell'accredito.

Segnale di attivazione:
- finanziamento o contributo inferiore al modello;
- slittamento >1 ciclo di pagamento;
- richiesta di anticipare CAPEX con C4.

### R-FIN-02 — uso della riserva operativa per coprire CAPEX
**Impatto:** I4.

È uno dei principali guasto mode economici del progetto.

Conseguenza:
- impianto costruito ma mancanza di liquidità per personale, input, raccolta, packaging e vendita.

Mitigazione:
- €120k segregati;
- contenitori di cassa;
- stop automatico nuovi ordini se C4 scende sotto soglia approvata.

### R-FIN-03 — CAPEX reale sopra envelope
**Impatto:** I4.

Driver:
- neve/vento;
- fondazioni;
- opere DSO;
- cabina MT;
- BESS;
- Tech Barn;
- opere civili;
- commissioning;
- trasporti;
- esclusioni non viste.

Mitigazione:
- E3 RFQ installati;
- design-to-value;
- contingency separata;
- revisione perimetro P1;
- nessun taglio a safety, freddo, acqua, commissioning o di lavoro capital.

### R-FIN-04 — IVA e timing fiscale
**Impatto:** I3/I4.

Mitigazione:
- linea IVA €120–150k;
- calendario fatture;
- verifica commercialista;
- nessun uso del fondo stipendi per IVA.

## 5. Rischi lotto, strutture e opere civili

### R-SITE-01 — lotto tecnicamente incompatibile o costoso
**Impatto:** I4.

Possibili cause:
- accesso inadeguato;
- vincoli;
- drenaggio;
- ombreggiamento;
- scarsa espandibilità;
- allacci lontani;
- rischio idraulico;
- geologia sfavorevole.

Mitigazione:
- due diligence pre-acquisto;
- masterplan P1 + finale;
- stima allacci;
- geotecnica preliminare;
- reject del lotto se incompatibile.

### R-SITE-02 — fondazioni/struttura più onerose del previsto
**Impatto:** I3/I4.

Segnale di attivazione:
- carichi neve/vento;
- terreno debole;
- falda;
- scavi;
- drenaggi;
- fondazioni speciali.

Mitigazione:
- non congelare costo serra prima di geotecnica;
- 3 RFQ comparabili;
- computo quantità;
- controllo €/m² e peso acciaio.

### R-SITE-03 — masterplan troppo denso
**Impatto:** I3.

Conseguenza:
- percorsi mezzi insufficienti;
- manutenzione difficile;
- AMR incompatibile;
- BESS/serbatoi senza buffer;
- espansione P2 compromessa.

Mitigazione:
- acquistare un lotto che ospita il progetto finale, non solo P1;
- maintenance/access envelope obbligatorio.

## 6. Rischi acqua, fertirrigazione e ambiente

### R-WAT-01 — fonte acqua insufficiente o qualità non idonea
**Impatto:** I4.

Variabili:
- disponibilità stagionale;
- alcalinità;
- EC;
- Na/Cl;
- microbiologia;
- UVT;
- Fe/Mn;
- torbidità.

Mitigazione:
- analisi stagionali;
- water balance;
- trattamento dimensionato su dati reali;
- storage e fonte di fallback legale.

### R-WAT-02 — dimensionamento errato pompe/filtri/fertirrigazione
**Impatto:** I3.

Mitigazione:
- Q/H/NPSH reali;
- curve pompe;
- simultaneità settori;
- backwash;
- wet commissioning.

### R-WAT-03 — riuso drenaggi diffonde fitopatogeni
**Impatto:** I4.

Mitigazione:
- R0 collect/measure/HOLD;
- segregazione C1/C2;
- trattamento validato;
- pathogen monitoring;
- pilot 30–60 giorni;
- no automatic reuse prima del PASS.

### R-WAT-04 — accumulo Na/Cl nel closed loop
**Impatto:** I3/I4.

Mitigazione:
- lab ion panel;
- reuse ratio dinamico;
- bleed controllato;
- crop-specific thresholds.

### R-WAT-05 — scarico non autorizzato o classificazione errata
**Impatto:** I4.

Mitigazione:
- classificazione reale;
- route legale;
- AUA/SUAP dove applicabile;
- flow meter e sample point;
- nessun discharge to soil configurazione base.

## 7. Rischi agronomici e produttivi

### R-AGR-01 — resa inferiore alla crop card
**Impatto:** I4.

Conseguenza:
- mancato raggiungimento del target commerciale;
- costo unitario maggiore;
- sovradimensionamento infrastrutture rispetto ai ricavi.

Mitigazione:
- resa prudente;
- P1 su 3 comparti;
- misure kg/m², €/m², scarto;
- P2 solo dopo dati P1.

### R-AGR-02 — mix P1 non coerente con stagione e mercato
**Impatto:** I3/I4.

Mitigazione:
- crop card prima degli ordini interni;
- pre-validazione commerciale;
- flessibilità C3–C6;
- almeno una coltura rapida e una premium.

### R-AGR-03 — pressione fitosanitaria / disease event
**Impatto:** I4.

Vulnerabilità:
- sistemi soilless e riuso possono amplificare eventi se non segregati.

Mitigazione:
- compartimentazione;
- genealogy;
- isolamento;
- clean/dirty flows;
- SOP fitosanitari;
- no common untreated return.

## 8. Rischi termici e climatici

### R-TH-01 — PDC sottodimensionate in condizioni reali sottozero
**Impatto:** I4.

Problema:
- dati A7/A2 non bastano per Carnia.

Mitigazione:
- A-7/A-10/A-15;
- W45;
- defrost netto;
- meteo sito;
- thermal storage;
- seasonal SAT.

### R-TH-02 — deumidificazione sottostimata
**Impatto:** I3/I4.

Conseguenza:
- malattie;
- condensa;
- qualità;
- energia eccessiva.

Mitigazione:
- kg/h vapore;
- humidity ratio;
- D1/D2/D3 comparative model;
- misura reale.

### R-TH-03 — strategia di emergenza termica dipendente troppo dall'elettrico
**Impatto:** I4.

Mitigazione:
- accumulo termico;
- load shedding;
- survival temperature strategy;
- BESS solo per carichi essenziali.

## 9. Rischi elettrici, rete e BESS

### R-EL-01 — connessione DSO più costosa/complessa
**Impatto:** I4.

Possibili cause:
- MT;
- cabina;
- opere di rete;
- export cap;
- CCI/PF2;
- SLI.

Mitigazione:
- scenari G100/G120/G120-CAP100;
- pre-application package;
- non scegliere cap export solo sul fee domanda.

### R-EL-02 — BESS 30 kW non sostiene i carichi reali
**Impatto:** I4.

Mitigazione:
- load register misurato;
- P0/P1;
- restart groups;
- thermal resilience;
- no "whole farm backup" assumption.

### R-EL-03 — transfer non realmente no-break
**Impatto:** I4.

Mitigazione:
- blackout SAT;
- criterio finale = no reboot P0;
- no affidamento sul solo marketing <20 ms.

### R-EL-04 — black-start / grid-return non affidabili
**Impatto:** I4.

Mitigazione:
- sequenza testata;
- protezioni grid/island;
- delayed restart;
- motor pickup;
- physical DSO separation.

### R-EL-05 — incendio/esplosione BESS
**Impatto:** I4.

Mitigazione:
- installazione esterna dedicata preferita;
- fire risk assessment;
- OEM protections;
- emergency access/isolation;
- no acquisto prima del fire design.

## 10. Rischi cold-chain, packaging e food

### R-FOOD-01 — celle sottodimensionate sul pull-down
**Impatto:** I4.

Mitigazione:
- kg/batch;
- Tin;
- target core T;
- door cycles;
- loaded commissioning.

### R-FOOD-02 — setpoint non coerente fra SKU
**Impatto:** I3/I4.

Mitigazione:
- CR-A/CR-B;
- crop-card postharvest;
- niente 0–4 °C automatico per SKU chilling-sensitive.

### R-FOOD-03 — packaging danneggia prodotto o rallenta troppo
**Impatto:** I3.

Mitigazione:
- PIL-PACK;
- 100 pack/SKU critico;
- throughput, damage, reject, labour.

### R-FOOD-04 — smart retail vende prodotto fuori specifica
**Impatto:** I4.

Mitigazione:
- logger indipendente;
- block-sale;
- inventory genealogy;
- vend/payment reconciliation;
- HACCP/fiscal/SUAP closure.

## 11. Rischi automazione, dati e cybersecurity

### R-IT-01 — server centrale diventa single point of guasto operativo
**Impatto:** I4.

Mitigazione:
- PLC/edge locali;
- no cloud dependency safety;
- failover;
- DR;
- server loss SAT.

### R-IT-02 — perdita/corruzione dati
**Impatto:** I3/I4.

Mitigazione:
- PostgreSQL replica;
- WAL/PITR;
- PBS/offsite;
- restore test;
- event replay.

### R-IT-03 — cybersecurity / compromissione accessi
**Impatto:** I4.

Mitigazione:
- VLAN;
- RBAC;
- MFA/identity;
- remote vendor time-limited;
- logs;
- backup;
- incident runbook.

### R-IT-04 — automazione ottimizza su dati errati
**Impatto:** I3/I4.

Mitigazione:
- plausibility checks;
- sensor calibration;
- local hard limits;
- model cannot override safety/HACCP;
- anomaly flags.

### R-IT-05 — integrazioni vendor/API instabili
**Impatto:** I3.

Mitigazione:
- local API preferred;
- protocol documentation;
- offline mode;
- version inventory;
- integration acceptance test.

## 12. Rischi robotica e mezzi

### R-ROB-01 — AMR non compatibile con serra reale
**Impatto:** I3.

Possibili cause:
- condensa;
- corridoi;
- porte;
- vegetazione;
- riflessi;
- rete;
- docking.

Mitigazione:
- pilot 8 h + 100 missioni;
- nessun ordine full-scale prima del PASS.

### R-ROB-02 — mower non sicuro nelle aree condivise
**Impatto:** I4.

Mitigazione:
- hens-clear;
- visitor lockout;
- no night operation;
- GNSS/offline tests;
- physical no-go.

### R-ROB-03 — rover galline non raggiunge cleaning/welfare target
**Impatto:** I3/I4.

Mitigazione:
- mixed-surface pilot;
- 100 missioni;
- welfare/safety critical = zero.

### R-ROB-04 — telescopico scelto senza uso reale sufficiente
**Impatto:** I2/I3.

Mitigazione:
- demo;
- task analysis;
- buy-vs-rent;
- stoccatore L2 per evitare uso improprio.

## 13. Rischi procurement e supply chain

### R-SUP-01 — preventivi non comparabili
**Impatto:** I3.

Mitigazione:
- separare hardware, posa, commissioning, service, IVA, freight;
- PROCUREMENT_CLOSURE_REGISTER.

### R-SUP-02 — dipendenza dal fornitore
**Impatto:** I3.

Mitigazione:
- protocolli aperti;
- source/config export;
- ricambi;
- second source dove possibile;
- separare supervisory custom da safety OEM.

### R-SUP-03 — lead time e ricambi Italia
**Impatto:** I3/I4.

Mitigazione:
- lead time in RFQ;
- critical spare list;
- service SLA;
- local support;
- long-lead procurement dopo verifica.

### R-SUP-04 — revisione/modello diverso tra benchmark e offerta
**Impatto:** I3.

Mitigazione:
- exact model/revision;
- datasheet;
- firmware;
- conformity;
- change-control prima dell'ordine.

## 14. Rischi personale e organizzazione

### R-HR-01 — difficoltà di reperimento competenze
**Impatto:** I3/I4.

Mitigazione:
- hiring anticipato;
- skill matrix;
- seasonal pool;
- external escalation.

### R-HR-02 — dipendenza eccessiva dal promotore
**Impatto:** I4.

Mitigazione:
- primary + backup;
- runbook;
- responsabile-absence drill;
- ferie testate;
- no founder-as-free-labour assumption.

### R-HR-03 — carico operativo superiore alle stime
**Impatto:** I3/I4.

Mitigazione:
- ore/kg;
- task logs;
- overtime;
- backlog PM;
- add-headcount segnale di attivaziones.

## 15. Rischi mercato e ricavi

### R-MKT-01 — domanda inferiore al target P1
**Impatto:** I4.

Mitigazione:
- pre-vendita;
- famiglie ricorrenti;
- ristorazione selettiva;
- canali multipli;
- P2 subordinata a domanda/margine.

### R-MKT-02 — eccessiva concentrazione su pochi clienti/canali
**Impatto:** I3.

Mitigazione:
- channel mix;
- limite concentrazione da definire sui dati;
- spaccio/ritiro/consegna/B2B.

### R-MKT-03 — prezzo accettato insufficiente
**Impatto:** I4.

Mitigazione:
- test prezzo prima del pieno scaling;
- margine per coltura/canale;
- non inseguire volume negativo.

## 16. Rischi normativi e autorizzativi

### R-REG-01 — requisiti edilizi/urbanistici incompatibili
**Impatto:** I4.

Chiusura:
- lotto + tecnico + titoli.

### R-REG-02 — contributi: eleggibilità/cumulo/doppio finanziamento
**Impatto:** I4.

Mitigazione:
- matrice spesa→bando;
- documentazione;
- no assunzione automatica 60%.

### R-REG-03 — vendita/spaccio regime errato
**Impatto:** I4.

Mitigazione:
- SUAP/commercialista;
- distinzione vendita agricola vs vending retail;
- fiscalità prima del messa in servizio.

### R-REG-04 — fattoria didattica non conforme ai requisiti reali
**Impatto:** I3/I4.

Mitigazione:
- ERSA;
- visitor zoning;
- accessibility;
- RC;
- pilot visita.

## 17. Rischi sicurezza e continuità

### R-SAFE-01 — interazione persone/macchine
**Impatto:** I4.

Aree:
- AMR;
- telescopico;
- mower;
- rover galline;
- visitor route.

Mitigazione:
- zoning;
- interlock;
- procedure;
- no reliance esclusivo su vision/AI.

### R-SAFE-02 — guasto simultanei o cascading
**Impatto:** I4.

Esempi:
- blackout + freddo;
- server + rete;
- pompa + livello basso;
- treatment + tank high-high.

Mitigazione:
- master SAT;
- guasto-mode testing;
- 72 h endurance;
- escalation.

### R-SAFE-03 — allarme eccessivo / alarm fatigue
**Impatto:** I3.

Mitigazione:
- alarm rationalization;
- P0/P1/P2/P3;
- no P3 wake-up;
- responsabile e recovery per ogni allarme.

## 18. Rischi programma e change control

### R-PM-01 — troppe attività parallele prima dei dati reali
**Impatto:** I3/I4.

Conseguenza:
- rework;
- RFQ scaduti;
- incompatibilità tra package.

Mitigazione:
- DG0–DG8;
- freeze P1;
- dependency-based schedule.

### R-PM-02 — espansione incontrollata del perimetro
**Impatto:** I4.

Aree più esposte:
- robotica;
- visitor;
- retail;
- agriturismo;
- R&S;
- trasformazione.

Mitigazione:
- core vs extra separati;
- BOM-029/extra fuori dal CAPEX core;
- change request con costo/cassa.

### R-PM-03 — espansione P2 compromessa da scelte P1
**Impatto:** I3/I4.

Mitigazione:
- dimensionare dorsali e spazi permanenti sul progetto finale quando conveniente;
- non sovradimensionare elettronica obsolescente.

## 19. Rischi manutenzione e ciclo di vita

### R-MNT-01 — progetto acquistabile ma non manutenibile
**Impatto:** I3/I4.

Mitigazione:
- spare list;
- manuals;
- PM plan;
- service;
- training;
- source/config backup.

### R-MNT-02 — ricambi critici con lead time lungo
**Impatto:** I3.

Mitigazione:
- stock onsite;
- second source;
- SLA;
- spare strategy.

### R-MNT-03 — costo ciclo di vita sottostimato
**Impatto:** I3/I4.

Mitigazione:
- TCO 5/8/10 anni;
- consumabili;
- batterie;
- service;
- replacement;
- downtime.

## 20. Top risk concentration

Le concentrazioni di rischio più rilevanti non sono singoli componenti, ma dipendenze:

### A. Finanza -> lotto -> RFQ
Se DG0/F0 non è chiuso, tutto il percorso resta teorico.

### B. Lotto -> DSO/geotecnica/layout
Un lotto errato può rendere inutili molte ottimizzazioni già fatte.

### C. Crop card -> acqua/termico/freddo/packaging
Specifiche premature su questi package aumentano il rischio di sovra/sottodimensionamento.

### D. Load register -> BESS/DSO
Il 30 kW power configurazione base non chiude i kWh né l'import/export.

### E. Mercato -> P2
L'espansione dei 6 comparti non deve precedere dati P1 sufficienti.

### F. Integrazione -> messa in servizio
Ogni singolo sottosistema può funzionare e l'impianto integrato può comunque fallire: per questo SAT end-to-end è verifica obbligatorio.

## 21. Segnale di attivazione di escalation immediata

Aprire/reaprire un decision verifica se si verifica uno dei seguenti:

- CAPEX major package >20% sopra envelope;
- previsione installed CAPEX >€950k;
- richiesta di usare riserva operativa per CAPEX;
- contributo/finanziamento ridotto o ritardato materialmente;
- lotto con criticità geotecnica/idraulica/urbanistica;
- DSO impone MT/opere inattese;
- carico P0/P1 > envelope BESS;
- crop yield/price significativamente sotto target P1;
- pilot critical FAIL;
- P0 reboot in blackout;
- guasto food/cold/water safety;
- scarico/riuso non autorizzato;
- vendor cambia modello/configurazione;
- critical spare/service non disponibile;
- dipendenza da una sola persona per skill P0.

## 22. Chiusura di un rischio

Un rischio non viene marcato `CLOSED` perché esiste una mitigazione scritta.

Stati:
- `OPEN`;
- `MITIGATION DESIGNED`;
- `EVIDENCE PENDING`;
- `CONTROLLED`;
- `ACCEPTED`;
- `CLOSED`;
- `MATERIALIZED`.

Per passare a `CONTROLLED` servono:
- responsabile;
- controllo implementato;
- evidenza;
- test quando applicabile;
- residual risk registrato.

## 23. Governance

Il risk register va rivisto obbligatoriamente:

- prima di DG0;
- prima di acquisto lotto;
- al design freeze P1;
- prima degli ordini major;
- dopo ogni pilot FAIL;
- prima del commissioning;
- prima del messa in servizio;
- a 30 e 90 giorni dal messa in servizio;
- prima di P2.

## 24. Collegamenti

- `VALIDATION_CLOSURE_DASHBOARD.md`;
- `MASTER_DECISION_GATE_REGISTER.md`;
- `PROCUREMENT_CLOSURE_REGISTER.md`;
- `MASTER_PILOT_REGISTER.md`;
- `MASTER_COMMISSIONING_ACCEPTANCE.md`;
- `../18_CAPEX_OPEX_CASHFLOW/FINANCIAL_CLOSURE_CONTROL.md`;
- `../20_CANTIERE_E_CRONOPROGRAMMA/PIANO_OPERATIVO_AVVIO/README.md`.
