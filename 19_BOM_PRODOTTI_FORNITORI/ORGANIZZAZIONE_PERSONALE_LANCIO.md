# BOM-031 — Organizzazione, personale e lancio operativo

**Aggiornato:** 18 settembre 2026  
**Ambito:** organico, formazione, turni, reperibilità, manutenzione esterna, ramp-up e sostenibilità operativa.  
**Stato:** `WORKING MODEL DEFINITO / COSTO DA CPL UDINE + INQUADRAMENTI REALI / HEADCOUNT DA VALIDARE CON 90 GIORNI DI DATI`.

## 1. Regola economica

Il costo del personale non si costruisce dal solo minimo nazionale.

Formula:

`COSTO_PERSONA = retribuzione_CPL + mensilità_aggiuntive + contributi_datore + TFR + bilateralità + ferie/copertura + straordinari/festivi + PPE + formazione + sorveglianza_sanitaria + payroll + welfare/bonus`.

Per gli OTD usare tariffa e terzo elemento applicabili secondo contratto corrente/provinciale.

## 2. Distinta

| Codice | Voce | Q.tà working | Stato | Benchmark / regola |
|---|---|---:|---|---|
| HR-R0 | owner / operations-tech lead | 1 | BASELINE | tempo interno da valorizzare, non gratuito |
| HR-R1 | crop & production lead | 1 FTE | L1 BASELINE | salary RFQ/market + CPL |
| HR-R2 | farm ops polyvalent A | 1 FTE | L1 BASELINE | CPL/inquadramento |
| HR-R3 | farm ops polyvalent B | 1 FTE | L1 TARGET | CPL/inquadramento |
| HR-R4 | seasonal peak pool | 0–3 equiv. | VARIABLE | OTD / CPL |
| HR-L2 | additional polyvalent/specialist | 0–1 | TRIGGERED | add only from measured load |
| HR-FOOD | transformation operators | 0 / 2–3 process days | BOM-029 CONDITIONAL | separate staffing |
| HR-PAYROLL | labour/payroll consultant | 1 | BASELINE EXT | RFQ annual/monthly |
| HR-RSPP | RSPP/safety support | 1 | EXT / as applicable | RFQ |
| HR-MED | occupational physician | 1 | IF REQUIRED | RFQ |
| HR-TRAIN-W | worker safety training | per worker | OBBLIGATORIO | 8/12/16 h by risk class under current agreement |
| HR-TRAIN-P | preposto training | assigned roles | IF ROLE | current Agreement 2025 |
| HR-FIRST | first-aid training/refresh | assigned | DVR | RFQ |
| HR-FIRE | fire/emergency training | assigned | DVR | RFQ |
| HR-EQUIP | equipment-specific training | assigned | IF REQUIRED | RFQ |
| HR-PPE | PPE initial kit | per person | BASELINE | RFQ |
| HR-PPE-ANN | PPE replacement | annual | OPEX | by task/use |
| HR-SEASON-POOL | recruiting/onboarding seasonal | annual | BASELINE | internal/agency if used |
| HR-CROSS | cross-training hours | per person | BASELINE | scheduled paid time |
| HR-ONCALL | on-call compensation | by rota | DA CONTRATTO | CPL/payroll validation |
| HR-OT | overtime/festive budget | variable | CONTINGENCY | not structural baseline |
| HR-REFRIG | refrigeration support contract | 1/y | BASELINE EXT | RFQ |
| HR-ELECT | electrical/BESS support | 1/y | BASELINE EXT | RFQ |
| HR-WATER | pumps/fertigation support | 1/y | BASELINE EXT | RFQ |
| HR-GH | greenhouse/climate support | 1/y | BASELINE EXT | RFQ |
| HR-MACH | AMR/lifting/machinery support | 1/y | BASELINE EXT | RFQ |
| HR-METRO | legal metrology support | 1/y/as needed | CONDITIONAL | RFQ |
| HR-HACCP | HACCP/food specialist | 0–1 | BOM-029 CONDITIONAL | RFQ |
| HR-PEST | pest-control service | 1/y | IF FOOD/NEEDED | RFQ |
| HR-SOP | SOP authoring/maintenance | 1 system | BASELINE | INTERNAL |
| HR-SKILL | skill matrix management | 1 | BASELINE | INTERNAL |
| HR-RAMP | 180-day ramp-up program | 1 | BASELINE | INTERNAL |
| HR-DRILL | holiday/sick-day drills | quarterly/annual | BASELINE | INTERNAL |
| HR-KPI | workforce KPI dashboard | 1 | BASELINE | INTERNAL / server |
| HR-ALARM | alert routing/escalation | 1 | BASELINE | INTERNAL / server |

## 3. National minimum reference — 1 June 2026

CCNL agricultural workers national minimum area:

| Area | Monthly minimum |
|---|---:|
| Area 1 | €1.532,999 |
| Area 2 | €1.398,093 |
| Area 3 | €1.042,434 |

These are national floor references only.

Actual Carnia TerraTech payroll must use:
- applicable province;
- current CPL;
- role classification;
- fixed provincial elements;
- current renewal increases.

## 4. 2026 renewal

Agreement signed 28 May 2026:

- +3,4% from 1 June 2026;
- +1,7% from 1 January 2027;
- total +5,1% over the 2026–2027 first biennium.

Existing provincial contractual wages are subject to the agreed increases according to the renewal framework.

## 5. Employer contribution reference

INPS 2026 detailed table for OTI general agricultural employers:

- employer total contribution: **33,953%**;
- industrial-type agricultural production: **35,753%**;
- worker pension share: **8,84%**.

Actual payroll calculation remains with payroll consultant.

## 6. OTI floor sanity check

Illustrative only.

Assumptions:
- national monthly minimum;
- 14 monthly payments;
- 33,953% employer contributions;
- simple TFR accrual approximation = annual gross / 13,5.

Results:

| Area | Gross 14-month floor | Employer-cost floor* |
|---|---:|---:|
| Area 1 | ~€21.462 | ~€30.339 |
| Area 2 | ~€19.573 | ~€27.669 |
| Area 3 | ~€14.594 | ~€20.630 |

*Before provincial wage uplift, bilateral body, overtime, training, PPE, medical, payroll, bonus, leave-replacement and other costs.

Do not use these values as salary offers or final budget.

## 7. Working L1 staffing envelope

Core:

- R1 = 1 FTE;
- R2 = 1 FTE;
- R3 = 1 FTE;
- R0 owner/tech separately valued;
- R4 seasonal variable.

This is an **engineering staffing hypothesis**, not a hiring mandate.

Validation period:
- first 90 operating days.

## 8. Why two farm operators

One operator only creates:

- holiday SPOF;
- sick-day SPOF;
- no parallel harvest/pack;
- no safe coverage for maintenance;
- owner pulled into manual work.

Two polyvalent operators allow:

- rotation;
- task parallelism;
- backup;
- weekend duty;
- training.

## 9. Why not 5–6 permanent employees immediately

Automation and seasonal demand make premature fixed headcount expensive.

Add FTE only when data shows:

- >85% planned utilization;
- structural overtime;
- deferred holidays;
- PM backlog;
- service/quality misses;
- owner routine labor above target.

## 10. Owner/tech cost

Internal development time must be logged.

Suggested cost accounting:

`owner_hours × internal_loaded_rate`.

Rate is management/accounting decision.

Use in:
- software TCO;
- automation ROI;
- incident cost;
- product-development cost.

Do not set to zero because there is no payslip.

## 11. Seasonal labour

Use for:

- harvest peaks;
- transplant;
- cleaning;
- packing;
- temporary BOM-029 campaigns.

Before each season:
- forecast demand;
- forecast crop supply;
- convert kg/day into labor hours;
- book seasonal pool early.

No last-minute assumption that workers are available.

## 12. Recruitment risk

FVG 2026 Excelsior shows persistent difficulty recruiting many profiles.

Implication:
- predictable schedules;
- stable core contracts;
- cross-training;
- good tools;
- accommodation/transport analysis if site requires;
- seasonal contacts maintained year-to-year.

## 13. Overtime reserve

Budget overtime as exception/contingency.

Planning rule:
- if overtime >5–8% of scheduled hours for 8 weeks, investigate capacity/process.

Do not make overtime a cheaper substitute for headcount.

## 14. On-call budget

Budget separately from normal hours.

Cost drivers:
- standby;
- intervention;
- night/festive;
- travel;
- vendor callout.

Actual treatment:
- CPL/payroll consultant.

Operational target:
- reduce P1 alerts through redundancy and good controls.

## 15. External maintenance reserve

Do not invent an annual lump sum before RFQ.

Budget by asset criticality:

`annual_service = fixed_PM + expected_callouts + travel + critical_spares`.

At minimum RFQ:
- refrigeration;
- electrical/BESS;
- water/fertigation;
- greenhouse;
- AMR/machines.

## 16. Training cost

Include:

- course fees;
- employee paid hours;
- travel;
- refresher;
- replacement coverage.

Training hours are labor hours.

Do not count only the invoice from the trainer.

## 17. PPE

Define by risk assessment.

Typical categories may include:
- footwear;
- gloves;
- eye protection;
- hearing protection;
- weather/thermal;
- chemical-specific PPE;
- hi-vis;
- food-area clothing.

No generic kit substitutes task-specific assessment.

## 18. Launch reserve

First 90 days require more labor than steady state.

Budget:

- vendor presence;
- training;
- commissioning;
- double-checks;
- data cleanup;
- procedure writing.

Do not judge long-term FTE from week 1.

## 19. Staff utilization model

Available productive capacity is not:

`FTE × 39 h × 52`.

Subtract:
- holidays;
- training;
- meetings;
- sick leave assumption;
- safety;
- maintenance;
- admin;
- breaks/nonproductive necessary time.

For scheduling, use measured net productive capacity by role.

## 20. Labour €/kg

Core KPI:

`labor_cost_per_kg = loaded direct labor + allocated support labor / sellable kg`.

Also track:
- harvest labor €/kg;
- pack labor €/kg;
- maintenance €/kg;
- retail refill €/order;
- transformation labor €/batch.

## 21. Vendor vs internal decision

Internalize when:

- task frequent;
- response time critical;
- skill reusable;
- training reasonable;
- tools cost justified.

Outsource when:

- task rare;
- certification required;
- specialized equipment;
- liability/high risk;
- vendor has better spare chain.

## 22. Approval gate

BOM-031 cost model closes only after:

1. legal employer/entity defined;
2. province/site defined;
3. current CPL table obtained;
4. actual role classification;
5. consultant payroll simulation;
6. seasonal model;
7. vendor SLA quotes;
8. 90-day measured workload;
9. owner-time accounting method;
10. annual holiday/on-call rota test.
