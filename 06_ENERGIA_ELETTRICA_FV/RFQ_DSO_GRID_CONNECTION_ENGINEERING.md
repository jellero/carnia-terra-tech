# RFQ — progettazione connessione DSO / TICA / protezioni

**Progetto:** Carnia TerraTech  
**Aggiornato:** 18 settembre 2026  
**Stato:** `RFQ TEMPLATE / LOTTO E DSO REALI DA INSERIRE`

## 1. Oggetto

Richiesta di offerta per:
- pratica connessione attiva TICA;
- studio BT/MT;
- progettazione elettrica di connessione;
- protezioni;
- eventuale CCI/PF2;
- eventuale SLI/export limitation;
- integrazione FV 120,32 kWp + BESS 30 kW;
- studi grid + island;
- documentazione, commissioning e assistenza DSO.

## 2. Dati progetto

- FV iniziale: 120,32 kWp DC;
- FV futuro: 150–180 kWp DC envelope;
- inverter: confronto 100 kW AC vs 120 kW AC;
- BESS PCS: 30 kW class;
- BESS energy: 60/90/120 kWh useful da chiudere;
- P0/P1 critical bus;
- nessuna UPS locale baseline;
- islanding richiesto con separazione DSO;
- custom EMS non sostituisce dispositivi CEI/DSO.

## 3. Scenari da quotare separatamente

### S1 — G100
- FV AC 100 kW;
- export requested 100 kW;
- BESS 30 kW.

### S2 — G120
- FV AC 120 kW;
- export requested 120 kW;
- BESS 30 kW.

### S3 — G120-CAP100
- FV AC 120 kW;
- export cap 100 kW;
- BESS 30 kW;
- SLI/export-control compliant obbligatorio;
- dichiarare perdita attesa di produzione e logica aggregate PV+BESS.

Per ogni scenario:
- variante BT se tecnicamente proponibile;
- variante MT se richiesta/consigliata;
- motivazione tecnica della soluzione.

## 4. Dati DSO da acquisire

Il fornitore deve assistere nell'acquisizione/verifica di:
- DSO competente;
- POD se esistente;
- tensione;
- potenza disponibile import/export;
- Ik max/min;
- rete/cabina di riferimento;
- vincoli export;
- requisiti comunicazione;
- soluzione tecnica minima;
- eventuali opere rete.

## 5. Studi obbligatori

Quotare:
- load flow;
- voltage rise;
- short circuit;
- harmonic assessment;
- reactive power / PF;
- phase balance;
- earthing/neutral;
- selectivity;
- grid fault vs island inverter-limited fault;
- motor/compressor restart;
- reconnection;
- export-control stability.

## 6. Protezioni

Restituire:
- SLD;
- SPI;
- DDI;
- relè;
- MCCB/ACB;
- CT/VT/TA/TV;
- SPD;
- emergency isolation;
- settings;
- Icu/Ics;
- selectivity/cascading;
- fail-safe states.

## 7. CCI / PF2

Se MT e applicabile alla configurazione:
- CCI hardware;
- PF2;
- comunicazione DSO;
- CEI 57-142/cybersecurity dove applicabile;
- certificazione;
- CA certificate/provisioning se richiesto;
- test;
- documentazione Regolamento di Esercizio;
- commissioning;
- canoni/telecom.

Se non applicabile:
- dichiarazione motivata con riferimento normativo/configurazione.

## 8. SLI / export limit

Se richiesto o proposto:
- sistema certificato/compliant;
- meter PCC;
- refresh/control interval;
- aggregate PV+BESS;
- behavior on meter loss;
- behavior on comms loss;
- fail-safe;
- response time;
- maximum transient export;
- compatibility with BESS charging/discharging;
- commissioning test.

Il server Carnia non viene dichiarato SLI.

## 9. BESS / islanding

Richiedere verifica di:
- anti-islanding;
- physical grid separation;
- grid-forming;
- neutral/earthing in island;
- fault current;
- black-start;
- grid return;
- PV operation in island if proposed;
- blackout SAT P0 no-reboot.

## 10. Espansione

Quotare separatamente predisposizioni per:
- 150–180 kWp DC;
- eventuale inverter aggiuntivo;
- quadro;
- sbarre;
- TA/TV;
- meter;
- cabina/trafo se MT;
- cavidotti/spazio.

Nessun sovradimensionamento non motivato.

## 11. Documentazione

Deliverable:
- pratica TICA;
- SLD design + as-built;
- planimetria;
- calculation report;
- protection settings;
- selectivity report;
- short-circuit report;
- harmonic report;
- CEI declarations;
- DSO forms;
- GAUDÌ/GSE support;
- Regolamento di Esercizio;
- commissioning records;
- test reports;
- source files editable.

## 12. Formato economico obbligatorio

Non accettare solo "chiavi in mano €X".

Separare:
- application/DSO fees;
- engineering;
- TICA handling;
- grid studies;
- SLD/design;
- BT switchgear;
- MT switchgear;
- transformer;
- civil cabin;
- cables/trenches;
- SPI/DDI;
- CCI/PF2;
- SLI;
- meters/CT/VT;
- telecom;
- GAUDÌ/GSE;
- authorization support;
- commissioning;
- testing;
- travel;
- annual maintenance;
- subscriptions;
- exclusions;
- VAT;
- lead time.

## 13. Acceptance

Offerta comparabile solo se:
1. copre S1/S2/S3;
2. identifica assunzioni;
3. separa BT/MT;
4. separa CCI/SLI;
5. include installed CAPEX;
6. include recurring OPEX;
7. esplicita lead time;
8. indica responsabilità DSO vs integratore vs cliente;
9. include commissioning;
10. non assume che il custom EMS sia dispositivo normativo.

## 14. Allegati da inviare quando disponibili

- DSO_TICA_CONNECTION_READINESS.md;
- DSO_TICA_DATA_REQUEST.csv compilato;
- BT_MT_PROTECTION_DECISION_MATRIX.md;
- MASTER_LOAD_REGISTER.csv;
- planimetria lotto;
- POD/bolletta;
- datasheet FV/inverter/BESS;
- target COD.
