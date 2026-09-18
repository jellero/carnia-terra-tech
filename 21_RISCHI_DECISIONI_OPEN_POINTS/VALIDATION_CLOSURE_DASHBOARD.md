# Validation / closure dashboard — Carnia TerraTech

**Aggiornato:** 18 settembre 2026  
**Stato:** `MASTER STATUS / DOCUMENTAZIONE STRUTTURATA / ESECUZIONE REALE ANCORA DA DATI-SITO-RFQ-PILOT-SAT`

## 1. Scopo

Questo file è il punto unico per capire:
- cosa è già strutturato;
- cosa è realmente chiuso;
- cosa resta bloccato;
- quale evidenza sblocca il passo successivo.

Non sostituisce i documenti tecnici: li orchestra.

## 2. Stato closure 1–8

| # | Blocco | Stato | Evidenza già pronta | Blocco reale |
|---:|---|---|---|---|
| 1 | lotto/masterplan/geotecnica/layout | STRUCTURED / EXECUTION BLOCKED | `20_CANTIERE_E_CRONOPROGRAMMA/PIANO_OPERATIVO_AVVIO/01_TERRENO_E_MASTERPLAN.md` + criteri punti 01/03 | lotto reale, titolo, rilievo, geotecnica, accessi, utilities |
| 2 | crop card + carichi reali acqua/termico/elettrico | STRUCTURED / EXECUTION BLOCKED | `20_CANTIERE_E_CRONOPROGRAMMA/PIANO_OPERATIVO_AVVIO/02_AGRONOMIA_P1.md` + metodi/BOM di dominio | crop card finali, stagione, meteo sito, analisi acqua, layout, misure reali |
| 3 | master load register 1–15 min + P0/P1 | STRUCTURED | MASTER_LOAD_REGISTER, measurement plan, vendor snapshot, capture CSV | misure P0/P1 e transitori + OEM/RFQ mancanti |
| 4 | DSO/TICA BT/MT import/export/protezioni | STRUCTURED | DSO readiness, data request, BT/MT matrix, grid RFQ, cost scenarios | lotto, DSO, POD, potenze finali, preventivo reale |
| 5 | installed RFQ / procurement | STRUCTURED | PROCUREMENT_CLOSURE_REGISTER + classi Q1–Q5 | RFQ reali comparabili, layout/carichi dove necessari |
| 6 | pilot obbligatori | STRUCTURED | MASTER_PILOT_REGISTER, result/cost template, decision record | vendor demo, sito reale, SKU/crop/impianto reale |
| 7 | commissioning / end-to-end SAT | STRUCTURED | MASTER_COMMISSIONING_ACCEPTANCE + checklist | impianto installato e condizioni stagionali |
| 8 | CAPEX/OPEX/cashflow/risk/decision gates | STRUCTURED | FINANCIAL_CLOSURE_CONTROL + DG0–DG8 | installed RFQ, contratti, actuals, concessioni/finanziamenti reali |

## 3. Ciò che è chiuso documentalmente

Sono già disponibili:
- BOM core 001–034;
- fonti e benchmark per i principali package;
- RFQ template per i package tecnici;
- master load register;
- load measurement plan;
- vendor data snapshot;
- DSO/TICA pre-application package;
- procurement register;
- pilot governance;
- commissioning/SAT;
- financial closure control;
- master decision gates.

Quindi il problema non è più "manca un documento".

Il problema è sostituire progressivamente:
- `E0/E1` -> `E2/E3/E4/E5`;
- benchmark -> RFQ;
- RFQ -> contratto;
- ipotesi -> misura;
- pilot plan -> pilot evidence;
- SAT plan -> SAT PASS.

## 4. Analisi problematiche e rischi

Riferimenti:
- `ANALISI_PROBLEMATICHE_RISCHI.md`;
- `ANALISI_PROBLEMATICHE_RISCHI.csv`.

La lettura trasversale distingue **problematiche già presenti** da **rischi futuri**. Le problematiche oggi più bloccanti sono: chiusura finanziaria non ancora actual, lotto non validato, crop card P1 non congelate, major CAPEX ancora prevalentemente E0/E1, profilo P0/P1 non misurato, DSO/POD/BT-MT non determinati, pilot e SAT non eseguiti, OPEX non misurato e domanda P1 ancora da validare.

Le concentrazioni di rischio principali sono:
- finanza -> lotto -> RFQ;
- lotto -> geotecnica/DSO/layout;
- crop card -> acqua/termico/freddo/packaging;
- load register -> BESS/DSO;
- mercato -> P2;
- integrazione -> go-live.

Trigger di escalation immediata:
- major package >20% sopra envelope;
- installed forecast >€950k;
- uso della riserva operativa per CAPEX;
- criticità urbanistica/geotecnica/idraulica del lotto;
- DSO con MT/opere inattese;
- carico P0/P1 oltre envelope BESS;
- pilot critical FAIL;
- reboot P0 in blackout;
- failure food/cold/water safety;
- scarico/riuso non autorizzato;
- cambio materiale della configurazione vendor;
- skill P0 dipendente da una sola persona.

La severità indica la **conseguenza potenziale**; la probabilità resta `TBD` finché non esistono dati sito, misure, vendor evidence o actuals.

## 5. Piano operativo P1 già collegato

Il master operativo corrente è:
- `20_CANTIERE_E_CRONOPROGRAMMA/PIANO_OPERATIVO_AVVIO/README.md`;
- `00_FINANZA_E_CASSA.md`;
- `01_TERRENO_E_MASTERPLAN.md`;
- `02_AGRONOMIA_P1.md`.

Questi documenti rendono eseguibili F0/F1 e preparano P1, ma non sostituiscono concessioni, lotto o crop card finali.

## 6. Prossime azioni che si possono fare prima del lotto

### A. Budgetary RFQ
Aprire:
1. BOM-034 BESS/PCS + rapid-switch / AC-coupled alternative;
2. grid engineering budgetary RFQ;
3. BOM-019 inverter/FV;
4. BOM-011 PDC;
5. BOM-030 server;
6. BOM-015 pompe/VFD;
7. BOM-025 packaging bench/RFQ;
8. BOM-024 cold room budgetary sizing;
9. BOM-012 DryGair/boost;
10. BOM-021 telescopico/demo.

Stato offerta:
`BUDGETARY / NOT FOR ORDER`.

### B. Vendor demo
Possibili senza sito definitivo o con ambiente equivalente:
- PIL-AMR;
- PIL-PACK;
- PIL-RETAIL;
- evidence/demo BESS transfer architecture.

### C. Finanza
Chiudere evidenze di:
- concessione;
- anticipo;
- garanzia;
- finanziamento;
- linea IVA;
- bridge;
- riserva operativa.

## 7. Azioni immediatamente dopo identificazione lotto

Attivare in parallelo:

### Lotto
- due diligence;
- rilievo;
- geotecnica;
- masterplan;
- accessi;
- drenaggi;
- acqua;
- utilities;
- neve/vento/meteo.

### Energia
- DSO/POD;
- TICA;
- BT/MT;
- Ik;
- import/export;
- layout FV/BESS.

### Serra
- struttura/fondazioni;
- layout comparti;
- porte/corridoi;
- HAF/fogging;
- drenaggi.

### Visitor/logistics
- AMR path;
- mower area;
- didactic zoning;
- parking/drop-off;
- service access.

## 8. Azioni dopo crop card / processo reale

- Q irrigazione;
- fertigation recipes;
- drainage target;
- thermal load;
- climate/VPD;
- humidity balance;
- peak harvest kg/day;
- cold-room pull-down;
- packaging SKU;
- retail SKU/temp;
- labour/task model.

Questi dati sostituiscono le classi di benchmark con dimensionamenti reali.

## 9. Dipendenze critiche

### Lotto sblocca
- geotecnica;
- serra;
- drenaggi;
- DSO;
- FV;
- BESS location;
- visitor layout;
- machine paths.

### Crop card sblocca
- acqua;
- fertirrigazione;
- termico;
- deumidificazione;
- post-harvest;
- packaging;
- OPEX.

### Load register reale sblocca
- PCS;
- BESS kWh;
- critical bus;
- DSO import power;
- restart groups;
- electrical CAPEX.

### RFQ installed sblocca
- CAPEX validato;
- funding schedule;
- contract award;
- procurement release.

### Pilot PASS sblocca
- AMR;
- retail automation;
- drain reuse scaling;
- mower;
- chicken cleaning;
- packaging automation.

### SAT PASS sblocca
- go-live;
- acceptance payment;
- warranty baseline;
- operations handover.

## 10. Hard stop conditions

Non procedere a ordine irreversibile se:
- DG0 financial close non PASS;
- specifica tecnica non chiusa;
- Q3 senza pilot PASS;
- prezzo ancora solo benchmark su major package;
- installed scope non separa posa/commissioning;
- safety/regulatory blocker aperto;
- operational reserve viene usata per coprire CAPEX;
- configurazione offerta differisce materialmente dal design approvato.

## 11. Maturity ladder

Per ogni major package:

1. `DESIGN`
2. `BENCHMARK`
3. `BUDGETARY RFQ`
4. `INSTALLED RFQ`
5. `PILOT PASS` se richiesto
6. `ORDER RELEASED`
7. `INSTALLED`
8. `SAT PASS`
9. `ACTUAL COST/OPEX`
10. `90-DAY REVIEW`

## 12. Core documents

Energy:
- `06_ENERGIA_ELETTRICA_FV/MASTER_LOAD_REGISTER.md`
- `06_ENERGIA_ELETTRICA_FV/LOAD_MEASUREMENT_AND_RFQ_PLAN.md`
- `06_ENERGIA_ELETTRICA_FV/DSO_TICA_CONNECTION_READINESS.md`

Closure:
- `21_RISCHI_DECISIONI_OPEN_POINTS/PROCUREMENT_CLOSURE_REGISTER.md`
- `21_RISCHI_DECISIONI_OPEN_POINTS/MASTER_PILOT_REGISTER.md`
- `21_RISCHI_DECISIONI_OPEN_POINTS/MASTER_COMMISSIONING_ACCEPTANCE.md`
- `21_RISCHI_DECISIONI_OPEN_POINTS/MASTER_DECISION_GATE_REGISTER.md`
- `21_RISCHI_DECISIONI_OPEN_POINTS/ANALISI_PROBLEMATICHE_RISCHI.md`

Finance:
- `18_CAPEX_OPEX_CASHFLOW/BUDGET_AVVIO_IDEALE.md`
- `18_CAPEX_OPEX_CASHFLOW/FINANCIAL_CLOSURE_CONTROL.md`
- `18_CAPEX_OPEX_CASHFLOW/AVVIO_CASSA_E_RAMPA_PRODUTTIVA.md`

## 13. Stato corrente sintetico

La progettazione documentale non è più il collo di bottiglia principale.

I blocker reali sono ora:
1. esecuzione F0 finanza reale;
2. lotto reale;
3. crop/process data;
4. misure;
5. installed RFQ;
6. pilot;
7. commissioning.

Nessuno di questi deve essere sostituito con numeri inventati.
