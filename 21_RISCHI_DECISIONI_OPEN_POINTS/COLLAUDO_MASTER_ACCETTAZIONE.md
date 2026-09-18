# Collaudo master e accettazione integrato — Carnia TerraTech

**Aggiornato:** 18 settembre 2026  
**Stato:** `SAT MASTER / ESECUZIONE DA IMPIANTO REALE`

## 1. Obiettivo

Definire una sola sequenza di collaudo che dimostri che i sottosistemi funzionano:
- singolarmente;
- nelle interfacce;
- in modalità di guasto;
- in modalità degradata;
- sotto carico reale;
- con dati/log verificabili;
- con operatori formati.

Il messa in servizio non è la somma dei singoli "ON".

## 2. Regola di accettazione

Ogni test ha uno stato:
- `NOT READY`;
- `READY`;
- `PASS`;
- `PASS WITH ACTIONS`;
- `FAIL`;
- `WAIVED` solo con approvazione motivata.

Un test critical non può essere `WAIVED`.

## 3. Verifica prima del SAT integrato

Prima del SAT integrato devono essere chiusi:
- as-built SLD/P&ID/layout;
- software/firmware inventory;
- IP/MAC/device registry;
- I/O list;
- meter map;
- alarm matrix;
- safety interlock list;
- backup config;
- manuali;
- ricambi critici;
- responsabile per subsystem;
- procedure emergency/rollback;
- open lista anomalie classificata.

## 4. Sequenza collaudo

### C0 — documentazione e verifiche statiche
- serial/model check;
- CE/DoC/certificati;
- torque/termination;
- labeling;
- cable/pipe continuity;
- grounding/bonding;
- valve/damper position;
- sensor identity;
- network segregation;
- access control;
- firmware configurazione base.

### C1 — energizzazione / collaudo a secco
- alimentazione quadro per quadro;
- PLC/edge/network;
- strumenti;
- BESS auxiliaries;
- drive/VFD;
- controls local;
- emergency stop;
- alarm horn/beacon.

Nessun processo automatico full-load.

### C2 — prova funzionale del sottosistema
Per ogni BOM:
- normal mode;
- manual mode;
- local fallback;
- sensor fail;
- comms fail;
- power loss/restart;
- alarm;
- emergency stop;
- interlock.

### C3 — collaudo con fluidi/carico
- acqua con portata reale;
- termico con portata/T reali;
- cold room con massa;
- packaging con SKU;
- retail con pack/pagamento;
- AMR con carico;
- BESS con P0/P1.

### C4 — integrazione tra domini
Test interfacce:
- water <-> fertigation;
- water <-> drain reuse;
- thermal <-> greenhouse;
- cold-chain <-> server;
- retail <-> inventory/payment;
- AMR <-> doors/tasks;
- BESS <-> load shedding;
- DSO <-> export control;
- server <-> PLC/edge.

### C5 — guasti e modalità degradata
- internet loss;
- server loss;
- PLC/edge loss;
- meter loss;
- sensor drift/fail;
- pump fail;
- cold compressor fail;
- PDC fail;
- BESS low SOC;
- grid blackout;
- blocked valve/flow;
- comms loss;
- Stripe outage;
- AMR offline;
- treatment fail.

### C6 — endurance
Minimo:
- 72 h integrated log per critical systems;
- nessun unexplained reset;
- nessun alarm flood;
- no data gap non spiegato;
- reconciliation complete.

Subsystem che richiedono ciclo più lungo mantengono il loro test specifico.

### C7 — prontezza operativa
- operator training;
- maintenance handover;
- spare stock;
- escalation contacts;
- SOP;
- emergency response;
- backup/ripristino;
- calibration schedule;
- cleaning schedule;
- permits/documentation.

### C8 — messa in servizio review
Messa in servizio solo se:
- critical FAIL = 0;
- safety actions = 0 aperte;
- P0/P1 blackout acceptance PASS;
- water/food/cold-chain release signed;
- regulatory blockers closed;
- residual lista anomalie has responsabile/date/risk.

## 5. Master acceptance matrix

| ID | Domain | Test | Critical | Acceptance |
|---|---|---|---|---|
| SAT-EL-01 | grid | PCC meter/config | sì | polarity, direction, P/Q/S/PF/energy correct |
| SAT-EL-02 | BESS | full charge/discharge | sì | capacity/power/telemetry within fornitore acceptance |
| SAT-EL-03 | BESS | 30 kW continuous island | sì | sustained without trip/overtemp |
| SAT-EL-04 | BESS | grid-loss P0 no-reboot | **sì** | NODE-A/B/QNODE/network/PLC no reboot |
| SAT-EL-05 | BESS | black-start | sì | dead-grid -> P0 -> P1 sequence successful |
| SAT-EL-06 | BESS | low SOC shedding | sì | P3/P2 shed in correct order; P0 preserved |
| SAT-EL-07 | BESS | grid return | sì | controlled reconnect, no mass restart |
| SAT-EL-08 | DSO | export limit / PF2 / CCI if applicable | sì | DSO command and fail-safe verified |
| SAT-WA-01 | water | pump duty point | sì | Q/H/kW within design |
| SAT-WA-02 | water | 1+1 failover | sì | standby pickup without unsafe pressure loss |
| SAT-WA-03 | water | low-level dry-run | sì | pump inhibited/tripped correctly |
| SAT-WA-04 | filtration | backwash cycle | no | sequence, pressure, waste route correct |
| SAT-WA-05 | fertigation | dosing permissive | sì | no dosing without validated flow |
| SAT-WA-06 | fertigation | high/low pH/EC fail | sì | safe hold/alarm |
| SAT-WA-07 | reuse | HOLD/treatment fail | sì | no release to clean tank |
| SAT-WA-08 | reuse | mass balance | no | 24 h + 7 d within agreed tolerance |
| SAT-TH-01 | PDC | unit enable/disable | sì | local + supervisory control correct |
| SAT-TH-02 | PDC | one unit failure | no | cascade degrades predictably |
| SAT-TH-03 | thermal | pump/zone fail | sì | affected zone safe; others continue |
| SAT-TH-04 | thermal | tank sensors/energy | no | T/flow/energy coherent |
| SAT-TH-05 | climate | dehumidification mode | no | humidity-ratio logic and limits verified |
| SAT-GH-01 | greenhouse | vent actuator fail | sì | safe fallback |
| SAT-GH-02 | greenhouse | HAF/fogging interlock | no | no unsafe conflicting mode |
| SAT-GH-03 | greenhouse | compartment isolation | sì | one zone isolated without losing others |
| SAT-CR-01 | cold | sensor calibration | sì | mapped/reference within spec |
| SAT-CR-02 | cold | empty mapping | no | no unacceptable hot/cold spots |
| SAT-CR-03 | cold | loaded pull-down | sì | product core reaches crop-card target |
| SAT-CR-04 | cold | door-open recovery | no | recovery within agreed time |
| SAT-CR-05 | cold | defrost/drain | sì | no freeze/flood/uncontrolled warming |
| SAT-CR-06 | cold | network loss | sì | local control remains functional |
| SAT-SRV-01 | server | compute-node failover | sì | service continuity within SLO |
| SAT-SRV-02 | server | DB PITR/restore | sì | restore proven |
| SAT-SRV-03 | server | NATS single-node loss | sì | critical streams continue |
| SAT-SRV-04 | server | edge offline/replay | sì | buffered events replay without duplication |
| SAT-SRV-05 | server | RBAC denied action | sì | prohibited action blocked/logged |
| SAT-SRV-06 | server | offsite restore | sì | usable restore proven |
| SAT-RT-01 | retail | payment-vend reconciliation | sì | no double charge/double vend |
| SAT-RT-02 | retail | temp excursion | sì | affected sale blocked/alarmed |
| SAT-RT-03 | retail | webhook delayed | sì | state remains correct/reconciles |
| SAT-AMR-01 | logistics | mission + door | no | mission succeeds with interlock |
| SAT-AMR-02 | logistics | network loss | sì | safe stop/recovery |
| SAT-AMR-03 | logistics | emergency stop | sì | safe stop and reset procedure |
| SAT-SAFE-01 | site | emergency stop map | sì | every E-stop verified and documented |
| SAT-SAFE-02 | site | fire interface | sì | alarms/isolations per design |
| SAT-SAFE-03 | site | loss of Internet | sì | safety and production local mode continue |
| SAT-SAFE-04 | site | loss of server | sì | local controllers safe/autonomous |
| SAT-END-01 | site | 72 h integrated endurance | sì | no unexplained reboot/trip/data corruption |
| SAT-END-02 | site | shift handover | no | alarms/tasks/history understandable |
| SAT-END-03 | site | operator emergency drill | sì | correct response without hidden expert dependency |

## 6. Water collaudo

Minimum:
1. flush/clean;
2. leak test;
3. tank levels calibrated;
4. pump curve;
5. VFD limits;
6. pressure sensors cross-check;
7. flow meters;
8. failover;
9. dry-run;
10. filter backwash;
11. fertigation permissives;
12. no-flow dosing prevention;
13. pH/EC calibration;
14. emergency HOLD;
15. drain routes.

Evidence:
- Q/H/kW;
- calibration sheet;
- trend/log;
- photos/as-built;
- valve matrix.

## 7. Thermal/climate collaudo

Minimum:
- hydraulic flushing;
- glycol concentration;
- expansion/pressure;
- pump curves;
- HX ΔT/Δp;
- PDC enable/cascade;
- tank stratification;
- zone valve/pump;
- temperature sensors;
- heat meter;
- low-temp behavior when season permits;
- defrost observation;
- HAF/boost;
- D1/D2/D3 logic if installed.

A warm-weather collaudo cannot close winter performance; mark seasonal SAT open.

## 8. Cold-chain collaudo

Follow BOM-024:
- leak/safety;
- calibration;
- empty mapping;
- loaded mapping;
- door recovery;
- pull-down;
- defrost;
- condensate;
- alarms;
- network loss;
- modular circuit failure if applicable;
- core temperature;
- >=72 h trends;
- settings backup.

Product release only after crop-card acceptance.

## 9. Server/automation collaudo

Follow:
- `07_AUTOMAZIONE_DATI_AI/SERVER_ACCEPTANCE_DR_RUNBOOK.md`

Required before chiusura:
- DB restore;
- compute failover;
- NATS R3 single-node loss;
- edge replay;
- BESS transfer;
- delayed Stripe webhook;
- RBAC denial;
- offsite restore.

## 10. Energy/BESS collaudo

Follow BOM-034 acceptance:
1. meter validation;
2. charge/discharge;
3. 30 kW island;
4. overload/start;
5. grid loss;
6. no-reboot P0;
7. black-start;
8. low SOC;
9. load >30 kW;
10. P3 shed;
11. P2 shed;
12. irrigation pump start;
13. cold compressor restart;
14. optional PDC start;
15. PV loss;
16. PV-island if claimed;
17. server/internet/controller/meter comms loss;
18. grid return;
19. DSO/export command;
20. E-stop;
21. fire alarm.

## 11. Retail/payment acceptance

Minimum:
- known SKU;
- inventory reservation;
- PaymentIntent;
- terminal payment;
- vend command;
- vend_ack;
- refund path;
- delayed webhook;
- network outage behavior;
- reconciliation;
- temperature block;
- no duplicate vend/refund.

No messa in servizio if accounting state can diverge from physical inventory without a recovery procedure.

## 12. Integrated scenario blackout

Run with representative P0/P1:
1. normal grid;
2. P0/P1 logging active;
3. cut grid;
4. verify separation;
5. verify no reboot;
6. shed P3;
7. validate P1 sequence;
8. start irrigation pump;
9. restart cold-room compressor according RG;
10. optional one PDC if permitted;
11. run >=30 min;
12. force/simulate low SOC logic;
13. restore grid;
14. verify delayed restart;
15. verify BESS reserve restoration;
16. review logs.

Critical fail:
- any P0 reboot;
- unsafe parallel;
- protection misoperation;
- uncontrolled simultaneous restart.

## 13. Integrated scenario perdita server

1. stop central server;
2. PLC/edge remain safe;
3. irrigation local control continues if permitted;
4. cold room continues;
5. BESS/island controller independent;
6. AMR receives no unsafe new mission;
7. retail behavior follows tested policy;
8. edge buffers;
9. restore server;
10. reconcile.

## 14. Integrated scenario perdita Internet

Expected:
- farm core stays operational;
- no cloud dependency for safety;
- fornitore cloud features degrade only;
- payment policy follows tested Stripe capability;
- remote support unavailable but local control remains.

## 15. Razionalizzazione allarmi

Before messa in servizio:
- every alarm has priority;
- responsabile;
- condition;
- debounce/delay;
- escalation;
- acknowledgement;
- recovery condition;
- no duplicate alarms across PLC/server/fornitore;
- nuisance alarms removed.

Target:
- no P3 informational alarm wakes on-call staff;
- P0/P1 actionable alarms are unmistakable.

## 16. Lista anomalie policy

Class A — safety/regulatory/critical:
- must close before messa in servizio.

Class B — production/quality:
- close before relevant subsystem production use.

Class C — optimization/documentation:
- may remain with responsabile/date if risk accepted.

Every punch item:
- ID;
- domain;
- severity;
- responsabile;
- due;
- workaround;
- evidence;
- chiusura date.

## 17. Consegna finale

Required:
- as-built;
- source files;
- credentials handover;
- firmware/version list;
- backups;
- spare list;
- service contacts;
- warranties;
- collaudo data;
- calibration certificates;
- training attendance;
- SOP;
- emergency procedures;
- preventive-maintenance plan;
- warranty start dates.

## 18. Accettazione stagionale

Some tests cannot be honestly closed in one collaudo window.

Remain open where necessary:
- PDC at design low temperature;
- frost protection;
- summer cold-room worst case;
- peak irrigation;
- heavy transpiration/humidity;
- snow/wind-related operational checks.

Use status:
`PROVISIONAL ACCEPTANCE / SEASONAL TEST DUE`.

Retention/warranty/payment terms should preserve fornitore obligation until seasonal SAT where contractually possible.

## 19. Messa in servizio decision

`GO` only if:
- A lista anomalie = 0;
- critical SAT = PASS;
- regulatory documentation available;
- trained operator coverage exists;
- backup/ripristino proven;
- BESS blackout test PASS;
- food/cold-chain critical controls PASS;
- emergency paths PASS.

Otherwise:
- `LIMITED GO-LIVE` only for explicitly isolated, safe subset;
- or `NO-GO`.

## 20. Dopo la messa in servizio

First 30 days:
- daily alarm review;
- daily data-gap review;
- weekly maintenance review;
- weekly energy/water balance;
- weekly incident/near-miss;
- supplier punch chiusura.

At day 30:
- collaudo closeout review;
- update CAPEX/OPEX;
- update SOP/PM;
- update spares;
- update risk register.

At day 90:
- reliability/TCO configurazione base;
- compare design vs measured;
- re-tune thresholds;
- close remaining nonseasonal punch items.
