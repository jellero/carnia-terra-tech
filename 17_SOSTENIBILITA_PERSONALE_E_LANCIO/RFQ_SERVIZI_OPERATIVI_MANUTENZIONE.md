# RFQ — Servizi operativi, manutenzione e reperibilità — BOM-031

**Progetto:** Carnia TerraTech  
**Aggiornato:** 18 settembre 2026  
**Stato:** `RFQ TEMPLATE / FORNITORI E SLA DA VALIDARE SUL SITO REALE`.

## 1. Obiettivo

Contrattualizzare le competenze specialistiche che non devono diventare un onere interno permanente.

Il preventivo deve separare:

- canone;
- chiamata;
- ore;
- trasferta;
- ricambi;
- reperibilità;
- SLA;
- esclusioni.

## 2. Classi di criticità

### C1 — produzione/cold-chain/safety critical

Richiedere opzioni:
- risposta remota <30 min;
- presenza onsite 4 h;
- presenza onsite 8 h;
- next business day.

Il fornitore deve indicare quali SLA può realmente garantire in Carnia.

### C2 — produzione degradata

- remote same-day;
- onsite same/next business day.

### C3 — non critical

- scheduled maintenance;
- 2–5 business days.

## 3. Lotto A — refrigerazione

Ambito:

- CR-A;
- CR-B;
- vending refrigeration if needed;
- future process cooling.

Richiedere:

- F-gas/refrigerant competence applicable;
- natural refrigerant competence where used;
- preventive maintenance;
- leak/fault diagnostics;
- compressor/fan/control service;
- spare strategy;
- logger verification.

Quote:

- annual PM;
- emergency call;
- travel;
- hourly rates;
- C1 SLA;
- critical spare kit.

## 4. Lotto B — electrical/BESS/inverter

Ambito:

- LV panels;
- protections;
- PV inverter;
- BESS;
- EMS interface;
- grounding;
- emergency faults.

Operator internal boundary:
- visual/status/reset only where authorized.

Vendor boundary:
- live electrical work;
- internal inverter/BESS;
- protection settings;
- statutory tests.

Quote:
- annual inspection;
- emergency;
- 4/8 h SLA;
- remote diagnostics;
- spare/loan unit policy.

## 5. Lotto C — water/fertigation

Ambito:

- pumps;
- filters;
- dosing;
- valves;
- sensors;
- pipework;
- fertigation controller.

Quote:
- seasonal startup;
- preventive;
- pump seal/service;
- dosing calibration;
- emergency leak/pump failure;
- spare pump strategy.

## 6. Lotto D — greenhouse/climate

Ambito:

- vents;
- screens;
- HAF;
- fogging;
- heating distribution;
- sensors;
- controller.

Quote:
- pre-season PM;
- winter critical SLA;
- actuator spare;
- controller support;
- emergency manual procedure.

## 7. Lotto E — AMR/robotics/lifting

Ambito:

- AMR;
- lawn robot;
- chicken cleaning rover;
- lift/telescopic.

Quote:
- annual PM;
- remote support;
- battery;
- safety inspection;
- parts;
- emergency disable/recovery;
- replacement/loan.

Production fallback should remain manual where feasible.

## 8. Lotto F — IT hardware/network

Software/application support is internal baseline.

External hardware scope:

- server hardware;
- NIC/storage;
- switch;
- cabling;
- hardware replacement.

Quote:
- NBD warranty;
- 4 h optional;
- onsite;
- spare parts;
- remote hands.

No managed SaaS takeover required.

## 9. Lotto G — metrology

Ambito:

- receiving scales;
- packaging scales;
- smart retail legal-for-trade modules;
- process/QC scales where subject.

Quote:
- initial conformity/support;
- periodic verification;
- calibration;
- seal/repair;
- certificates.

## 10. Lotto H — occupational safety

Quote if external:

- RSPP support;
- DVR;
- machinery/risk review;
- training matrix;
- emergency planning;
- annual review;
- incident investigation.

Separate statutory from optional consultancy.

## 11. Lotto I — occupational physician

Where required by DVR/law:

- health protocol;
- preventive/periodic visits;
- judgement;
- site visit;
- records;
- scheduling.

Quote per employee + annual fixed costs.

## 12. Lotto J — payroll/labour consultant

Scope:

- hiring;
- classification;
- CCNL/CPL;
- payslips;
- time/overtime;
- INPS/INAIL;
- seasonal workers;
- contract changes;
- termination;
- annual statements.

Critical requirement:
- confirm current Udine/provincial agricultural wage tables and bilateral obligations.

## 13. Lotto K — food/HACCP

Activate when BOM-029 becomes operational.

Scope:

- NIA/SUAP support;
- HACCP;
- process validation;
- label review;
- allergen;
- shelf-life;
- recall;
- sanitation.

Not needed as permanent onsite FTE baseline.

## 14. Lotto L — pest control

For food/Tech Barn/store where required:

- monitoring plan;
- traps;
- reports;
- corrective actions;
- trend data.

Prefer digital export/API only if it reduces work; PDF reports acceptable.

## 15. Response matrix

Vendor fills:

| Fault class | Remote response | Onsite | Nights | Weekend | Included in fee |
|---|---:|---:|---|---|---|
| C1 | | | | | |
| C2 | | | | | |
| C3 | | | | | |

## 16. Geography

Vendor must state:

- technician base;
- actual travel km/time;
- Carnia coverage;
- winter weather limitation;
- backup technician.

Do not accept generic national SLA that does not apply to the site postcode.

## 17. Spare strategy

For each subsystem state:

- part;
- failure probability;
- lead time;
- onsite spare yes/no;
- vendor stock;
- substitute;
- expected replacement time.

Spare onsite when:

`expected downtime cost > spare carrying cost`.

## 18. Preventive maintenance format

For every PM:

- frequency;
- duration;
- downtime;
- consumables;
- operator preparation;
- report;
- measurements;
- acceptance limits.

Server imports/saves:
- work order;
- date;
- findings;
- parts;
- next due.

## 19. Incident handoff

Internal operator provides:

- asset ID;
- alarm;
- timestamp;
- photos/log;
- what changed;
- reset attempted yes/no;
- safety state.

Vendor provides:
- diagnosis;
- work;
- parts;
- root cause;
- prevention;
- release to service.

No phone-only undocumented repair.

## 20. Contract exit

Require:

- customer owns service history;
- config export;
- no proprietary lock on normal maintenance data;
- spare list;
- passwords/keys transferred securely where applicable.

## 21. Economic format

| Campo | Richiesto |
|---|---|
| annual fee | € |
| remote support | included/€ |
| callout | € |
| hourly weekday | € |
| hourly night | € |
| hourly holiday | € |
| km/travel | € |
| 4h SLA | € |
| 8h SLA | € |
| PM visit | € |
| spare kit | € |
| warranty | yes |
| contract duration | months |
| cancellation | terms |
| exclusions | yes |

## 22. Selection rule

Do not select on hourly rate alone.

Score:

- site response;
- competence;
- spare access;
- documentation;
- remote diagnostics;
- ability to support selected OEMs;
- total annual TCO;
- communication quality.

For C1 systems, response reliability is worth more than lowest hourly price.
