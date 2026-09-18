# RFQ — EMS, BESS e connessione elettrica — BOM-034

**Progetto:** Carnia TerraTech  
**Aggiornato:** 18 settembre 2026  
**Stato:** `RFQ TEMPLATE / 30 kW BESS POWER BASELINE / kWh, BT-MT, ISLANDING E FIRE DESIGN DA CHIUDERE`.

## 1. Oggetto

Richiesta di offerta separata e comparabile per:

- BESS C&I 30 kW class;
- batterie LFP;
- PCS/grid-forming;
- quadro BESS;
- commutazione rete/isola;
- critical bus;
- metering;
- EMS/local power controller;
- protezioni;
- CCI/SLI se applicabile;
- eventuale cabina/trasformatore se DSO richiede MT;
- fire design;
- installazione;
- commissioning;
- manutenzione e ricambi.

## 2. Vincoli consolidati

- potenza backup target: 30 kW continuous class;
- nessuna UPS locale baseline;
- server/network/PLC P0 devono superare blackout senza reboot;
- PV iniziale ~120.32 kWp DC;
- predisposizione PV 150–180 kWp;
- BESS deve funzionare localmente senza cloud;
- EMS Carnia TerraTech remains supervisory/economic layer;
- safety/BMS/protection logic local.

## 3. Lotto A — load study

Vendor/integrator to build:

- complete load register;
- single-line load map;
- phase balance;
- 1–15 min profile;
- startup/inrush profile;
- grid mode max demand;
- island mode P0/P1 demand;
- simultaneous motor-start cases;
- future-load envelope.

Use existing known anchors but verify:

- irrigation pump 2.2 kW class;
- heat-pump module up to 9 kW electrical max declared;
- 3-unit PDC aggregate up to 27 kW;
- cold-room compressors ~1.48–2.25 kW class plus auxiliaries;
- dehumidification 2.3 / 9.55 kW class;
- server/network to be measured;
- future BOM-029 P3.

Deliverable:
- spreadsheet/load register;
- 15-min design profile;
- transient profile;
- island scenario matrix.

## 4. Lotto B — BESS/PCS

Quote minimum scenarios:

### B1
- 30 kW PCS;
- ~60 kWh useful target.

### B2
- 30 kW PCS;
- ~90 kWh useful target.

### B3
- 30 kW PCS;
- ~120 kWh useful target.

For each state separately:

- battery nominal kWh;
- guaranteed usable kWh at BOL;
- guaranteed usable kWh at warranty/EOL;
- continuous discharge kW;
- peak discharge kW + duration;
- continuous charge kW;
- peak charge kW;
- C-rate;
- round-trip efficiency;
- PCS efficiency;
- auxiliary consumption;
- standby consumption;
- chemistry;
- cell/rack manufacturer;
- cycle warranty;
- calendar warranty;
- guaranteed SoH;
- throughput warranty;
- operating temperature;
- derating;
- IP rating;
- noise;
- dimensions/weight.

## 5. Candidate benchmark

Use TESLA Group STILLA 30 kW / 61 kWh LFP only as an order-of-magnitude technical comparator.

RFQ must not assume equivalence unless vendor proves:
- Italy grid compliance;
- island operation;
- transfer performance;
- local support;
- fire documentation;
- warranty.

## 6. Islanding

Vendor shall describe exact topology:

- point of common coupling;
- DDI/SPI;
- island contactor/breaker;
- neutral/earthing arrangement;
- grid-forming control;
- protection changes in island;
- short-circuit behavior;
- reconnection.

Required modes:
- grid-connected;
- zero/export-limited where required;
- island;
- black-start;
- grid-return sync/reconnect.

## 7. P0 no-reboot requirement

Mandatory acceptance:

1. run production-like P0 load;
2. remove DSO supply;
3. record voltage/frequency waveform;
4. verify NODE-A/B, QNODE, network core and PLC stay online;
5. verify no database/event corruption;
6. restore grid;
7. verify controlled resynchronization.

The quoted transfer time alone does not close acceptance.

If architecture cannot satisfy this without a local UPS:
- vendor must propose a no-UPS alternative architecture;
- identify additional static transfer/DC ride-through components;
- cost separately.

Mechanical ATS with multi-second interruption is not accepted for P0 continuity.

## 8. Black-start

Quote/test:

- black-start from dead grid;
- minimum SOC required;
- energization sequence;
- P0 pickup;
- P1 pickup;
- motor start capability;
- repeated black-start limit;
- behavior at cold temperature.

## 9. PV in island

Quote two variants:

### I-A BESS-only island
- PV disconnected during outage.

### I-B microgrid island
- BESS forms V/f;
- PV continues;
- PV curtailment;
- battery full behavior;
- reverse power protection;
- exact compatible PV inverter list.

Do not claim PV-island compatibility from generic Modbus support.

## 10. Lotto C — battery location / fire

Working preference:
- external dedicated cabinet/container.

Quote/site study:
- clearances;
- foundation;
- ventilation/HVAC;
- fire detection;
- fire suppression where part of OEM design;
- gas/smoke detection if provided;
- emergency stop;
- emergency isolation;
- drainage/runoff;
- firefighting access;
- signage;
- separation from occupied, food and chemical areas.

Provide documentation suitable for fire-risk assessment under current VVF guidance.

## 11. Lotto D — critical bus

Quote:

- critical switchboard;
- P0 outgoing feeders;
- P1 outgoing feeders;
- contactors/remote breakers for shed groups;
- manual bypass/maintenance;
- metering;
- SPD;
- surge/short-circuit protection;
- selective coordination.

Design must work in:
- grid fault level;
- island inverter-limited fault level.

## 12. Lotto E — load shedding

At least four groups:

- P0;
- P1;
- P2;
- P3.

Local controller shall support:
- SOC thresholds;
- available kW;
- frequency/voltage;
- P0/P1 actual load;
- ordered shed;
- restart delay;
- max simultaneous restart kW.

Server Carnia TerraTech sends targets but cannot defeat local limits.

## 13. Lotto F — metering

Quote meters for:

- M0 PCC;
- M1 PV aggregate/per inverter;
- M2 BESS;
- M3 heat pumps;
- M4 CR-A;
- M4b CR-B;
- M5 water/fertigation;
- M6 Tech Barn/process;
- M7 retail;
- M8 server/IT;
- M9 mobile charging.

For each:
- accuracy class;
- Modbus TCP/RTU;
- V/I/P/Q/S/PF/frequency;
- energy import/export;
- demand;
- harmonics if offered;
- MID if needed;
- CTs;
- installed cost.

PM5110/PM5340/PM5341 are benchmark classes, not mandatory vendor.

## 14. Meter sampling

System to support:
- fast local reading for power control;
- 1–10 s telemetry where useful;
- 1 min ops trends;
- 15 min demand aggregation;
- daily/monthly energy accounting.

## 15. Lotto G — EMS interface

Required read data:

- SOC;
- SoH;
- charge/discharge available kW;
- battery temp;
- cell/rack alarms;
- PCS state;
- grid/island;
- import/export;
- charge/discharge energy;
- fault codes;
- reserve state.

Required write interface where OEM allows:
- active power setpoint;
- charge limit;
- discharge limit;
- SOC reserve;
- operating mode;
- remote enable.

Preferred:
- Modbus TCP;
- local API;
- documented protocol.

Cloud-only API is not acceptable for critical operation.

## 16. Lotto H — connection study

Quote:

- load flow;
- short circuit;
- voltage rise;
- harmonic assessment;
- phase balance;
- reactive power;
- protection selectivity;
- earth/neutral arrangement;
- BT vs MT design;
- DSO application support;
- TICA documentation;
- GAUDI/production-storage registration support where applicable.

Final BT/MT remains DSO-dependent.

## 17. CEI 0-21 / 0-16

Vendor shall confirm design against current editions in force at commissioning.

Current project references:
- CEI 0-21:2026-07 for BT;
- CEI 0-16:2026-07 for MT/AT.

Quote any:
- SPI;
- DDI;
- interface relay;
- CCI;
- SLI;
- power-quality meter;
- communication gateway;
- certification/documentation.

## 18. CCI / PF2

If final new PV plant is connected in MT and falls in current >=100 kW class:
- include CCI;
- include PF2 active-power limitation;
- DSO communication;
- commissioning;
- test evidence.

Do not include CCI cost blindly in BT option.

## 19. SLI/export limit

If connection specifies export cap:

quote compliant aggregate control of:
- PV;
- BESS;
- site load.

Failure behavior:
- safe export limitation according CEI/DSO;
- not dependent on central farm server.

## 20. Protection / switchgear

Quote:
- MCCB/ACB;
- contactors/breakers;
- SPD;
- RCD only where applicable;
- busbars;
- CT/VT;
- protection relay;
- emergency isolation;
- labels;
- arc/fire considerations;
- enclosure/IP.

Provide:
- Icu/Ics;
- selectivity/cascading;
- thermal derating;
- island fault-current assumptions.

## 21. Lotto I — BESS auxiliaries

Quote separately:
- HVAC;
- heaters;
- pumps/fans;
- fire system;
- controls;
- idle consumption.

State annual auxiliary kWh under:
- 25°C;
- 0°C;
- project winter design case.

## 22. Low-temperature test/data

Provide charge/discharge curves at:
- +25°C;
- 0°C;
- -10°C;
- minimum rated temperature.

State:
- usable kWh;
- max charge kW;
- max discharge kW;
- heating time;
- auxiliary power;
- black-start limits.

## 23. Degradation

Provide warranty matrix vs:
- cycles;
- throughput;
- temperature;
- DoD;
- C-rate;
- calendar years.

Required:
- expected SoH year 5;
- expected SoH year 10;
- guaranteed minimum;
- module replacement policy.

## 24. Economic dispatch

Vendor EMS optional, but Carnia server remains master business scheduler.

Functions to expose:
- peak shaving;
- PV self-consumption;
- time-of-use arbitrage;
- reserve SOC;
- blackout mode.

No mandatory subscription for basic local operation.

## 25. Commissioning tests

1. firmware/version inventory;
2. meter validation;
3. CT polarity;
4. full charge;
5. full controlled discharge;
6. 30 kW continuous test;
7. overload test;
8. grid outage P0 no-reboot;
9. black-start;
10. low SOC shed;
11. >30 kW load request;
12. cold-room start;
13. irrigation pump start;
14. optional one PDC start;
15. server offline;
16. internet offline;
17. Modbus loss;
18. battery alarm;
19. fire interface;
20. PV curtailment;
21. island PV test if variant I-B;
22. grid return;
23. export cap/CCI command where applicable;
24. emergency isolation;
25. 72 h logged operation.

## 26. Documentation

Require:
- single-line diagram;
- protection settings;
- short-circuit study;
- selectivity report;
- BESS datasheet;
- battery warranty;
- CE declarations/certifications;
- CEI/DSO compliance package;
- fire-risk design inputs;
- P&ID/thermal if HVAC;
- network/register map;
- backup configuration;
- as-built;
- emergency response procedure;
- maintenance manual;
- spare list.

## 27. Economic format

| Campo | Richiesto |
|---|---|
| BESS nominal kWh | yes |
| useful BOL/EOL kWh | yes |
| PCS continuous kW | yes |
| island continuous kW | yes |
| peak kW/duration | yes |
| transfer time | yes |
| net equipment | € |
| VAT | separate |
| freight | separate |
| foundation/civil | separate |
| switchgear | separate |
| fire systems | separate |
| install | separate |
| commissioning | separate |
| DSO/grid-study | separate |
| annual service | € |
| software/subscription | € |
| warranty | years/MWh |
| efficiency | % |
| auxiliary kWh/y | yes |
| lead time | yes |
| exclusions | yes |

## 28. TCO

Compare 10-year:

`CAPEX + losses + auxiliaries + service + subscription + degradation + replacement - PV_selfconsumption_value - peak_shaving_value - outage_avoided_loss`.

Keep grid-service revenue at zero baseline unless a real contract/market route is validated.