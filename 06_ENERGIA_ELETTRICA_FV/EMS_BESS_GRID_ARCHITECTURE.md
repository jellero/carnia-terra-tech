# EMS, BESS e connessione elettrica — BOM-034

**Aggiornato:** 18 settembre 2026  
**Stato:** `WORKING ARCHITECTURE / BESS 30 kW POWER CONSTRAINT CONSOLIDATED / kWh, ISLANDING, PCC BT-MT, SHORT-CIRCUIT E RFQ BLOCCANTI`.

## 1. Obiettivo

Trasformare il requisito esistente "backup batterie 30 kW" in una specifica elettrica completa e verificabile.

Il progetto deve definire separatamente:

- potenza BESS/PCS [kW/kVA];
- energia nominale [kWh];
- energia utile [kWh];
- SOC reserve;
- potenza continua;
- overload/start current;
- C-rate;
- transfer time;
- islanding;
- black-start;
- autonomia per classi di carico;
- power quality;
- connessione DSO;
- EMS e load shedding;
- degrado e TCO.

**30 kW non significa 30 kWh e non definisce l'autonomia.**

## 2. Gerarchia

`protezioni elettriche / BMS / PCS local controller > PLC power controller > EMS site > server scheduler > cloud`

Il server centrale può ottimizzare.

Non può:
- bypassare BMS;
- bypassare protezioni;
- creare parallelo rete/isola non consentito;
- impedire un comando DSO;
- mantenere un carico se il power controller deve shedarlo per salvare il bus.

## 3. Architettura working

```
DSO GRID
   |
PCC + fiscal/DSO meter
   |
DDI/SPI / CCI-SLI as applicable
   |
MAIN AC BUS ---------------- PV inverters
   |                         |
   |                         +-- production metering
   |
   +------ BESS PCS 30 kW <----> LFP battery
   |             |
   |             +-- BMS / fire / HVAC / local controller
   |
   +------ NORMAL LOAD BUS
   |
   +------ CRITICAL BUS P0/P1
              |
              +-- server/network/PLC
              +-- alarms/security
              +-- essential water
              +-- cold-room holding
              +-- selected greenhouse survival loads
```

During island:

1. physical separation from DSO;
2. BESS establishes or maintains local grid;
3. P0/P1 remain powered within limit;
4. P2 only by EMS permission;
5. P3 shed;
6. PV island support only if inverter/PCS interoperability is explicitly validated.

## 4. AC-coupled baseline

Working preference:
- AC-coupled C&I BESS;
- independent from final PV inverter family;
- 400 V three-phase;
- grid-forming/islanding-capable PCS;
- local Modbus TCP/IEC protocol;
- OEM-supported black-start where required.

Benefits:
- PV BOM-019 remains modular;
- BESS can be replaced independently;
- easier expansion;
- clear metering.

Hybrid PV+battery inverter remains an alternative only if:
- it meets site load;
- backup transition;
- CEI/DSO;
- C&I service;
- 120 kWp PV topology;
- expansion plan.

## 5. 30 kW power constraint

Working:
- **PCS continuous output = 30 kW minimum in island mode**;
- 3-phase 400 V;
- power factor capability per selected PCS;
- short-duration overload/start capability documented;
- phase unbalance capability documented.

Do not assume:
- 30 kW charge = 30 kW discharge;
- 30 kW grid-connected = 30 kW island;
- inverter peak = continuous rating.

RFQ must state all three.

## 6. Energy scenarios

Compare useful energy **after technical limits**, not catalogue nominal only.

### E1 — 60 kWh useful
At constant load:
- 30 kW -> 2 h;
- 20 kW -> 3 h;
- 15 kW -> 4 h;
- 10 kW -> 6 h.

### E2 — 90 kWh useful
- 30 kW -> 3 h;
- 20 kW -> 4.5 h;
- 15 kW -> 6 h;
- 10 kW -> 9 h.

### E3 — 120 kWh useful
- 30 kW -> 4 h;
- 20 kW -> 6 h;
- 15 kW -> 8 h;
- 10 kW -> 12 h.

These are ideal arithmetic autonomy figures.

Final autonomy includes:
- PCS efficiency;
- battery temperature;
- ageing;
- auxiliary loads;
- SOC reserve;
- actual load profile.

## 7. Nominal vs useful kWh

Formula:

`E_useful = E_nominal × usable_DoD × SoH_design × availability_margin`

For sizing:
- use end-of-life guaranteed SoH;
- not beginning-of-life nameplate.

Example:
A 61 kWh nameplate product is **not automatically 61 kWh guaranteed critical-load autonomy for year 10**.

## 8. C-rate

For 30 kW:

- 60 kWh -> 0.5C;
- 90 kWh -> 0.33C;
- 120 kWh -> 0.25C.

Lower C-rate generally reduces cell stress and provides more autonomy, but raises CAPEX/footprint.

Final selection from:
- outage risk;
- daily cycling;
- peak shaving;
- warranty;
- site space.

## 9. Candidate class — TESLA Group STILLA

OEM public current data:

- 30 or 60 kW PCS;
- 61 or 122 kWh nominal;
- LFP;
- up to 0.5C;
- 400 V;
- peak efficiency 97.3%;
- Modbus TCP;
- integrated cabinet/system;
- >12 year stated lifetime on current product page;
- price: RFQ.

Why relevant:
- 30 kW / 61 kWh matches E1 order of magnitude.

Open gates:
- Italy CEI 0-21/0-16 certification/configuration;
- DSO acceptance;
- islanding/black-start;
- actual transition time;
- fire design;
- service FVG;
- end-of-life warranty;
- nominal vs guaranteed usable capacity.

**Candidate class, not selected.**

## 10. Hybrid comparison — Fronius Verto Plus

Current C&I hybrid family:
- 15–33.3 kW;
- full three-phase backup;
- Verto Plus 30 kW class;
- battery ecosystem;
- up to 63.2 kWh with Reserva in public C&I page, with other compatible battery variants documented separately.

Important update 18/09/2026:
- standard public documentation is configuration/revision dependent: older datasheet ~11 s; current manual standard table <35 s;
- **current OEM manual separately documents Rapid switch mode <20 ms**;
- Rapid switch requires **Fronius Backup Controller 63A**;
- Verto Plus 30.0 is documented at 29.99 kW Full Backup and up to 50 kVA Backup Power Boost for 5–10 s subject to source/battery/environment conditions;
- this makes the Verto 30.0 Plus architecture a credible P0 continuity candidate, but no-reboot is still closed only by exact Italy-supported topology + measured blackout SAT.

Use:
- priority technology/RFQ comparison alongside an AC-coupled C&I BESS;
- request exact battery + Backup Controller 63A + meter/switchgear BOM, CEI/DSO evidence and installed price;
- do not treat the standard seconds-level backup mode as P0-compatible.

## 11. Transfer-time hard requirement

User constraint:
- **nessuna costellazione di UPS consumer/distribuiti come baseline**;
- è invece ammesso e deve essere confrontato un **ride-through P0 professionale dedicato** (UPS online industriale, DC buffer o soluzione equivalente) se riduce rischio/TCO rispetto a imporre al BESS dell'intero sito il trasferimento senza riavvio.

Therefore:

### P0 critical bus acceptance
On grid loss:
- compute nodes do not reboot;
- network core does not reboot;
- PLC/edge does not reboot;
- database/event bus remains available or fails over without power loss.

Specification:
- target no-break or <=10 ms transfer where architecture supports it;
- final criterion is **measured no-reboot**, not marketing transfer time.

A conventional mechanical ATS with second-scale interruption is insufficient for P0 without another ride-through mechanism.

Possible architectures:
- always-online/grid-forming BESS critical bus;
- fast hybrid/PCS backup certified for exact combination;
- STS only when two valid live sources exist;
- dedicated DC ride-through for specific control equipment only if later justified.

No UPS desktop casuali o non governati.

Decisione da chiudere con RFQ/SAT:
- **A — BESS/PCS + critical bus con trasferimento no-break misurato**;
- **B — BESS + ride-through P0 professionale dedicato**;
- **C — altra architettura equivalente certificabile/manutenibile**.

La scelta deve minimizzare single point of failure, manutenzione e TCO, non rispettare un divieto ideologico di UPS.

## 12. Black-start

RFQ must prove whether BESS can:

1. start from dead grid;
2. energize P0 critical bus;
3. energize P1 sequentially;
4. accept motor starts;
5. synchronize/accept PV generation in island if supported;
6. reconnect to DSO safely after grid return.

Black-start is separate from normal island transfer.

## 13. PV during island

Do not assume standard PV inverters operate when DSO disappears.

Two allowed designs:

### I-A — BESS-only island
- PV disconnected in blackout;
- autonomy from battery only;
- simplest validation.

### I-B — BESS grid-forming + PV microgrid
- BESS forms V/f;
- selected PV inverters follow local grid;
- EMS curtails PV when load+battery cannot absorb production;
- OEM interoperability required.

I-B preferred for long daytime outage only if vendor validates exact PV/PCS combination.

## 14. Load classes

### P0 — must survive

Examples:
- safety PLC/controls;
- critical edge gateways;
- network core;
- server core;
- alarms;
- fire/BESS monitoring;
- essential access/security;
- minimum controls for cold chain/water.

Target:
- no interruption/reboot.

### P1 — survival / product protection

Examples:
- one irrigation pump as required;
- fertigation control;
- cold-room holding;
- essential greenhouse actuators;
- animal welfare;
- essential lighting.

P1 may cycle/duty-limit.

### P2 — production continuity

Examples:
- one heat pump if thermal survival requires and SOC allows;
- selected dehumidifier;
- packaging;
- smart retail;
- AMR mission completion;
- noncritical ventilation;
- workshop task.

P2 enabled dynamically.

### P3 — deferrable

Examples:
- full PDC cascade;
- heavy dehumidification;
- BOM-029 processing;
- EV/AMR charging;
- battery charging of mobile equipment;
- noncritical compute/AI;
- bulk backups;
- optional lighting;
- discretionary workshop loads.

P3 shed immediately on island unless explicitly released.

## 15. Known load anchors from repository

Not final load inventory:

- irrigation duty pump candidate: 2.2 kW;
- PDC module max electrical declared: up to 9 kW each;
- 3 PDC aggregate declared max: up to 27 kW;
- 4 PDC: up to 36 kW;
- DryGair DG-3: 2.3 kW;
- DryGair DG-12: 9.55 kW;
- cold-room reference compressors: ~1.48 and 2.25 kW class, plus fans/defrost/aux;
- server/network: meter in BOM-034, final RFQ load;
- UV/water treatment: sub-kW to low-kW class depending final unit;
- BOM-029 process: future P3, separate power model.

Consequence:

**30 kW backup cannot be treated as "whole farm full power".**

The EMS must select loads.

## 16. Thermal resilience

Electrical BESS is not the only energy store.

Carnia TerraTech also has thermal storage BOM-010.

Blackout strategy:
1. use hot-water thermal inventory first;
2. maintain circulation/controls;
3. only start one PDC if thermal state + SOC + outside temperature require;
4. shed noncritical electric load.

This can provide more crop-survival hours per battery kWh than powering all PDC continuously.

## 17. Load register

Every electrical load record includes:

- asset_id;
- nominal kW;
- measured typical kW;
- start/inrush;
- phase;
- power factor;
- harmonics class if relevant;
- duty cycle;
- P0/P1/P2/P3;
- can_shed;
- minimum off time;
- restart delay;
- energy task deadline;
- island eligibility.

No load enters automatic EMS without these fields.

## 18. Metering architecture

### M0 — PCC
- import/export;
- voltage/current;
- P/Q/S;
- PF;
- frequency;
- energy;
- demand;
- power quality where needed.

### M1 — PV
- per inverter + aggregate.

### M2 — BESS
- AC charge/discharge;
- DC battery energy;
- SOC/SoH;
- losses.

### M3 — thermal
- PDC aggregate;
- preferably each PDC.

### M4 — cold rooms
- CR-A;
- CR-B.

### M5 — water
- pumps;
- fertigation/treatment.

### M6 — Tech Barn/process

### M7 — retail/visitor

### M8 — IT/server/network

### M9 — mobile charging

Minimum:
- 1–10 s internal samples for control/diagnostics;
- 15 min energy/demand aggregation;
- daily/monthly accounting.

## 19. Meter candidate class

Schneider PowerLogic PM5000:

- PM5110 official IT list price observed €700;
- Class 0.5S;
- Modbus RS485;
- harmonic monitoring.

PM5340:
- official IT list price observed €1,469;
- Modbus TCP/IP Ethernet;
- Class 0.5S;
- up to 31st harmonic in current product page.

PM5341 MID:
- €1,694 official IT list price;
- Ethernet/Modbus and MID features.

Use:
- M0/high-value submeter candidate class.

For simple branch energy:
- cheaper DIN Modbus meters can be RFQ alternatives.

Do not install €1.5k meter on every 2 kW branch without value.

## 20. Load shedding local controller

Power controller runs locally.

Inputs:
- grid present;
- island;
- BESS SOC;
- BESS available kW;
- battery temp;
- SoH;
- P0/P1 bus load;
- thermal store state;
- cold-room state;
- water demand.

Outputs:
- contactor/enable groups;
- PDC setpoints;
- charger disable;
- process hold;
- EV/AMR charging limit.

Server sends:
- economic targets;
- schedule;
- forecast;
- preferred SOC.

Local controller can override.

## 21. SOC states

Do not freeze values until outage study.

State model:

### SOC_NORMAL
Economic optimization allowed above reserve.

### SOC_RESERVE
Stop discretionary discharge.

### SOC_ISLAND
P3 shed, P2 controlled.

### SOC_LOW
P2 shed, P1 duty-minimized.

### SOC_CRITICAL
P0 only + selected biological survival action.

Working simulations should compare:
- 20%;
- 30%;
- 40% normal reserve.

Final reserve from outage probability/value and PV/weather.

## 22. Peak shaving

BESS can limit import peak:

`P_grid_target = P_load - P_PV - P_BESS_discharge`

But backup reserve has priority.

EMS shall not discharge to save demand charges if doing so violates:
- SOC reserve;
- outage resilience;
- cycle warranty;
- next-day forecast.

## 23. PV self-consumption

Priority working:

1. current load;
2. charge BESS if below target;
3. flexible loads;
4. export within DSO limit;
5. curtail only if required.

This order can change with:
- tariff;
- export price;
- battery degradation cost;
- outage forecast.

## 24. Battery degradation accounting

Track:
- SoH;
- cycle throughput MWh;
- equivalent full cycles;
- average SOC;
- high-SOC hours;
- min/max temperature;
- C-rate;
- DC efficiency;
- calendar age.

Internal battery cost:

`degradation_cost_per_kWh = expected replacement/value loss / lifetime throughput`

EMS arbitrage only if economic benefit exceeds degradation + losses.

## 25. Fire safety

BESS placement requires specific risk assessment.

Current VVF FV guideline 2025 states:
- Li-ion BESS can present fire/explosion risk from thermal runaway;
- when BESS is associated with PV, a specific fire/explosion risk assessment is required;
- DCPREV 21021 of 23/12/2024 is a referenced BESS fire-safety guideline.

Working preference:
- external dedicated BESS cabinet/container;
- separation from occupied/food/chemical areas;
- access for emergency response;
- thermal monitoring;
- OEM fire detection/suppression as designed;
- emergency isolation;
- signage;
- runoff/containment evaluation where relevant.

Exact distances/measures:
- by fire engineer and selected system.

## 26. Chemistry

Working preference:
- **LFP** for stationary BESS candidate evaluation.

Reasons:
- common C&I chemistry;
- thermal stability advantages vs some other Li-ion chemistries;
- long cycle-life potential.

Still:
- LFP can undergo thermal runaway;
- fire risk is not zero;
- OEM/fire design remains mandatory.

No generic "LFP is safe" claim.

## 27. Grid connection

Final voltage level remains:
- **DA DSO**.

### If BT
- CEI 0-21:2026-07 current reference;
- active/passive user connection;
- BESS/PV configuration;
- SLI where required by connection/export design.

### If MT
- CEI 0-16:2026-07;
- SPI/protections;
- CCI as applicable;
- DSO interfaces.

The current CEI catalogue confirms both July 2026 editions effective from August 2026.

## 28. CCI / PF2 — MT >=100 kW

For a new wind/PV plant in MT in the >=100 kW and <500 kW class, Terna A.72 Rev.03 / ARERA framework requires CCI with PF2 active from service/connection under current rules.

The current PV working case is ~120.32 kWp DC.

Therefore:
- **if the final connection is MT and the final plant falls in the applicable class, design CCI/PF2 from day one**.

Do not add CCI blindly if final connection is BT.

## 29. SLI / export limiting

If DSO connection authorizes less export than installed generation/storage capability:

- use compliant System of Limitation of Injection where applicable;
- meter at PCC;
- controller limits aggregate PV+BESS export;
- failure mode must meet CEI/DSO requirements.

The general Carnia server is not assumed automatically compliant as SLI.

Use:
- certified OEM/approved controller architecture;
- server can supply economic targets above it.

## 30. DSO priority

DSO/connection controller commands outrank local economic optimization.

Priority:

`grid safety / DSO -> protection -> BMS/PCS -> island power controller -> farm EMS economics`.

If PF2 curtailment arrives:
- comply;
- re-optimize loads/BESS within limits.

## 31. Grid quality / short circuit

Before final switchgear:

- Ik max/min at PCC;
- voltage level;
- transformer if MT;
- neutral/earthing system;
- harmonic study;
- reactive power requirements;
- voltage rise;
- motor starts;
- selectivity;
- arc/short-circuit withstand.

BESS island fault current can be much lower than grid fault current.

Therefore:
- protections must be verified in both grid and island modes.

## 32. Reclosing / grid return

Island -> grid:

1. verify DSO stable;
2. synchronize if architecture requires;
3. transfer/reconnect using approved scheme;
4. hold P2/P3 restart delays;
5. prevent simultaneous motor restart;
6. recharge BESS gradually;
7. restore reserve before economic dispatch.

No "everything starts at once".

## 33. Restart sequence

After blackout:

1. switchgear/control;
2. network/PLC/server;
3. water/fertigation readiness;
4. cold-chain holding;
5. greenhouse survival;
6. selected P2;
7. chargers/process;
8. full optimization.

Random autonomous restart of every VFD/compressor is prohibited.

## 34. BESS auxiliary loads

RFQ must report:
- standby W;
- HVAC;
- fire system;
- heaters;
- fans;
- night idle;
- low-temp heating.

These loads reduce autonomy.

Carnia winter temperature makes auxiliary load important.

## 35. Low-temperature performance

Vendor to supply at:
- +25°C;
- 0°C;
- -10°C;
- project Tmin.

Need:
- charge power;
- discharge power;
- usable kWh;
- warm-up/heating;
- derating;
- black-start.

Do not accept room-temperature-only battery data.

## 36. Cycling scenarios

Compare:

### B1 resilience-first
- high SOC reserve;
- limited daily cycling.

### B2 balanced
- reserve + PV self-consumption + peak shaving.

### B3 aggressive economics
- more daily cycling.

B3 allowed only if:
- warranty;
- degradation;
- outage value;

remain acceptable.

## 37. Communications

BESS/PCS:
- Modbus TCP preferred;
- documented register map;
- local API if available;
- no cloud-only control.

Required:
- SOC;
- SoH;
- cell/rack alarms;
- available charge kW;
- available discharge kW;
- temp;
- PCS state;
- grid/island;
- energy counters;
- fault.

Write commands restricted:
- power setpoint;
- charge/discharge limit;
- operating mode;
- enable where OEM supports.

## 38. Cybersecurity

BESS network:
- OT/energy VLAN;
- no public Internet admin;
- vendor remote via time-limited VPN;
- unique credentials;
- firmware inventory;
- signed/controlled update path where supported.

Loss of cloud:
- no loss of islanding/safety.

## 39. Acceptance tests

1. PCC meter accuracy/config;
2. load-meter mapping;
3. BESS full charge/discharge test;
4. 30 kW continuous island test;
5. overload/start test;
6. grid loss;
7. **P0 no-reboot test**;
8. black-start;
9. low SOC;
10. high load >30 kW;
11. P3 shed;
12. P2 shed;
13. one irrigation pump start;
14. cold-room compressor restart sequence;
15. optional one PDC start;
16. PV loss;
17. PV island operation if claimed;
18. internet loss;
19. server loss;
20. BESS controller comms loss;
21. meter comms loss;
22. grid return;
23. DSO/export-limit command where applicable;
24. emergency stop/isolation;
25. fire alarm interface.

## 40. Current decision

**Baseline architecture:**
- 30 kW C&I LFP BESS class;
- useful-energy scenarios 60 / 90 / 120 kWh;
- external dedicated installation preferred;
- local grid-forming/islanding controller;
- P0/P1 critical bus;
- no distributed consumer UPS; professional P0 ride-through remains an allowed design option;
- submetering;
- local load shed;
- central EMS/server optimization;
- DSO/CEI interface separated from custom business server.

**Not yet selected:**
- battery kWh;
- PCS vendor;
- BT vs MT;
- PV-in-island;
- normal SOC reserve;
- SLI/CCI exact hardware;
- switchgear size.

## 41. Gate BOM-034

1. master load register;
2. 4+ weeks measured 1–15 min profile if existing loads available;
3. design-day electrical model for future loads;
4. P0/P1 measured/estimated profile;
5. outage/autonomy target;
6. thermal survival strategy;
7. battery EOL autonomy;
8. Tmin battery site;
9. location/fire assessment;
10. grid-loss transfer architecture;
11. short-circuit/selectivity grid + island;
12. DSO connection quote;
13. BT/MT;
14. CCI/SLI requirement;
15. PV island compatibility;
16. three RFQs;
17. TCO/degradation;
18. blackout commissioning test.
