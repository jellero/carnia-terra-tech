# Master decision gate register — Carnia TerraTech

**Aggiornato:** 18 settembre 2026  
**Stato:** `GOVERNANCE BASELINE / GATE EVIDENCE-BASED`

## 1. Regola

Nessuna grande decisione viene chiusa perché "sembra pronta".

Ogni gate ha:
- precondizioni;
- evidenze;
- owner;
- decisione;
- data;
- rischi residui;
- eventuale rollback.

## 2. Gate principali

### DG0 — finanziamento
PASS solo se:
- contributo concesso;
- anticipo realmente attivabile;
- garanzia disponibile;
- finanziamento deliberato;
- linea IVA;
- bridge CAPEX;
- riserva operativa €120k;
- quota non ammissibile coperta.

Decisione:
- GO FINANCE / HOLD.

### DG1 — lotto
PASS solo se:
- titolo/acquisto;
- urbanistica;
- accessi;
- acqua;
- energia;
- drenaggi;
- geotecnica;
- vincoli;
- masterplan fattibile.

Decisione:
- BUY / REJECT / RENEGOTIATE.

### DG2 — design freeze P1
PASS solo se:
- 3 comparti P1 definiti;
- crop card;
- layout;
- carichi acqua/termico/elettrico;
- Tech Barn;
- cold-chain;
- packaging;
- safety;
- future provisions chiare.

Decisione:
- FREEZE P1 / REWORK.

### DG3 — procurement release
PASS per package solo se:
- procurement evidence E3/E4;
- pilot PASS se Q3;
- technical spec chiusa;
- installed price;
- lead time;
- warranty/service;
- funding/eleggibilità;
- no unresolved safety blocker.

Decisione:
- RELEASE ORDER / HOLD / RETEST.

### DG4 — construction start
PASS solo se:
- permits;
- IFC drawings;
- contracts;
- cash schedule;
- site safety;
- long-lead secured;
- change-control attivo.

Decisione:
- START / HOLD.

### DG5 — energization/wet commissioning
PASS solo se:
- static checks;
- electrical safety;
- water/pressure test;
- controls;
- emergency paths;
- commissioning plan;
- vendor presence where required.

Decisione:
- ENERGIZE / WET TEST / HOLD.

### DG6 — subsystem acceptance
PASS solo se:
- subsystem SAT;
- documentation;
- training;
- punch A=0;
- critical B closed or risk-accepted before relevant use.

Decisione:
- ACCEPT / CONDITIONAL / REJECT.

### DG7 — integrated go-live
PASS solo if:
- master SAT critical PASS;
- BESS P0 no-reboot PASS;
- food/cold/water release;
- server restore/failover PASS;
- alarms rationalized;
- operators trained;
- permits active;
- operational reserve intact.

Decisione:
- GO / LIMITED GO / NO-GO.

### DG8 — P1 -> P2 expansion
PASS only if:
- P1 stable;
- recurring demand validated;
- margin positive enough;
- monthly cash burn controlled;
- workload sustainable;
- quality stable;
- maintenance backlog acceptable;
- reserve above threshold;
- CAPEX P2 funding identified.

Decisione:
- EXPAND / HOLD.

## 3. Cross-gate stop conditions

Stop regardless of schedule if:
- safety critical open;
- uncontrolled discharge/environmental issue;
- food/cold-chain critical nonconformity;
- financing withdrawn;
- operational reserve consumed by CAPEX;
- undocumented major design change;
- failed P0 blackout acceptance;
- regulatory title absent;
- vendor configuration materially differs from approved design.

## 4. Change control

Any post-gate change that affects:
- capacity;
- safety;
- cost > threshold;
- schedule;
- grant eligibility;
- grid connection;
- food hygiene;
- environmental discharge;
- visitor/public safety;

must reopen the relevant gate.

## 5. Evidence repositories

Use:
- PROCUREMENT_CLOSURE_REGISTER;
- MASTER_PILOT_REGISTER;
- MASTER_COMMISSIONING_ACCEPTANCE;
- FINANCIAL_CLOSURE_CONTROL;
- domain BOM/RFQ/source files;
- contract/offers;
- raw logs and acceptance records.

## 6. Gate log

Every decision stores:
- gate ID;
- date;
- attendees/approvers;
- evidence revision;
- decision;
- conditions;
- risks;
- owner;
- next review;
- linked commit/document.
