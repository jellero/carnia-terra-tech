# RFQ — Drenaggio, raccolta e riuso acqua — BOM-033

**Progetto:** Carnia TerraTech  
**Aggiornato:** 18 settembre 2026  
**Stato:** `RFQ TEMPLATE / GEOMETRIA, VOLUMI DRENATO, CLASSIFICAZIONE SCARICHI E PILOT BLOCCANTI`.

## 1. Oggetto

Richiesta di offerta separata e comparabile per:

- raccolta drenaggio per comparto;
- misura volume/portata;
- EC/pH/T;
- collettori;
- dirty/HOLD tank;
- clean/reuse tank;
- pompe;
- trattamento reuse;
- valvole/interlock;
- campionamento;
- scarico/bleed;
- stormwater segregation;
- server/PLC integration;
- commissioning.

Interfacce:

- BOM-006 gutter/supporti coltura;
- BOM-013 irrigazione;
- BOM-014 filtrazione;
- BOM-016 fertirrigazione;
- BOM-018 raw-water storage;
- BOM-032 treatment/disinfection;
- BOM-030 server.

## 2. Dati da fornire al vendor

- layout C1–C6;
- file/lunghezze gutter;
- substrate/slab;
- crop;
- Q irrigation min/max;
- expected drain fraction working range;
- daily drain measured/predicted;
- EC/pH feed;
- EC/pH drain;
- Na/Cl;
- water source chemistry;
- treatment concept;
- receiving/discharge route;
- frost exposure;
- available head/gravity;
- electrical/BESS;
- server protocols.

## 3. Lotto A — compartment collection

Quote for C1 and C2 separately.

Required:

- drain outlets from gutters;
- branch collectors;
- slope;
- clean-outs;
- inspection;
- removable joints where useful;
- chemical compatibility;
- drainage under maximum simultaneous irrigation.

Vendor to state:

- pipe/gutter material;
- diameter;
- slope;
- max flow;
- number of joints;
- minimum cleaning access;
- frost measures.

No common header before compartment measurement unless explicitly justified.

## 4. Lotto B — flow/volume measurement

Quote alternatives.

### B1 magnetic flowmeter

For full-pipe conditions.

Require:
- DN;
- min/max velocity;
- conductivity requirement;
- accuracy;
- empty-pipe detection;
- pulse/4–20 mA/Modbus.

### B2 calibrated tank/level balance

Require:
- level transmitter;
- tank geometry;
- resolution;
- calibration.

### B3 tipping/collection meter

For low/intermittent flow.

State:
- range;
- resolution;
- solids tolerance;
- cleaning.

Provide installed cost and expected maintenance.

## 5. Lotto C — drain quality sensors

Per C1/C2:

- EC;
- pH;
- temperature.

Quote:

- sensor;
- holder/bypass cell;
- transmitter;
- cleaning;
- calibration;
- spare electrode.

Optional:
- turbidity.

Do not quote online Na/Cl baseline unless validated accuracy/TCO are demonstrated.

## 6. Lotto D — dirty/HOLD tanks

Quote scenarios:

### D1 — 5 m³ class
- one per crop or central modular.

### D2 — 10 m³ class

### D3 — 2×5 m³ modular

Requirements:

- opaque PE/GRP/stainless suitable;
- closed/covered;
- level continuous;
- low/high/high-high;
- sample port;
- bottom drain;
- mixing only if required;
- cleaning access;
- overflow to controlled containment;
- isolation.

Provide:
- nominal volume;
- usable volume;
- footprint;
- connections;
- empty weight;
- installation;
- UV/weather rating if outside.

Tank final size remains DA MASS BALANCE.

## 7. Lotto E — clean/reuse tank

Quote same 5/10 m³ classes.

Requirements:

- physically separate from dirty;
- released-water only;
- EC/pH/T;
- level;
- sample point;
- drain;
- no backflow;
- cleanable.

## 8. Lotto F — transfer pumps

Quote:

- dirty -> treatment;
- clean -> blend/header;
- duty/standby option.

Provide:

- Q/H curve;
- material;
- VFD if useful;
- dry-run protection;
- energy;
- seal/maintenance.

Working preference:
- pump only when gravity cannot provide reliable process flow.

## 9. Lotto G — reuse filtration/treatment

Quote at least:

### G1 filter + UV
- validated on actual nutrient solution UVT.

### G2 filter + heat
- separate energy estimate.

### G3 UF/membrane optional

### G4 ozone/AOP optional

For every option:

- pathogen reduction target;
- Q;
- UVT/turbidity limits;
- nutrient impact;
- EC impact;
- pressure;
- energy;
- backwash/reject;
- cleaning chemicals;
- spare parts;
- service.

Do not quote W1 UV catalog flow as automatically valid on drain nutrient solution.

## 10. Lotto H — blending skid

Quote:

- fresh/makeup branch;
- reuse branch;
- control valves;
- flowmeters;
- check valves;
- static/mixing volume;
- EC/pH measurement.

Control:

`feed = fresh + reuse + fertilizer correction`.

Server provides target reuse ratio; local PLC enforces max/min limits.

## 11. Lotto I — bleed/discharge

Quote physical connection only after legal route identified.

Potential options:

- sewer;
- authorized surface discharge;
- dedicated treatment/storage.

Provide:

- dedicated flow meter;
- sample point;
- valve;
- lock/control;
- pipe;
- backflow protection.

No soil infiltration baseline.

## 12. Lotto J — abnormal/HOLD routing

Quote valve architecture for:

- normal D1;
- D2 abnormal/flush;
- dirty tank;
- emergency containment.

Every automatic valve requires:
- position feedback;
- manual override;
- fail position.

## 13. Lotto K — stormwater segregation

Quote where within vendor scope:

- roof-water path;
- clean external stormwater;
- potentially contaminated yard water;
- inspection chambers;
- isolation/interception.

Stormwater design must remain independent from nutrient reuse circuit.

## 14. Lotto L — sampling points

Minimum:

- C1 drain;
- C2 drain;
- dirty tank;
- post-treatment;
- clean tank;
- final feed blend;
- bleed/discharge.

Require:
- representative;
- labeled;
- accessible;
- safe;
- flushable.

## 15. Lotto M — lab package

Quote initial 30–60 day pilot.

Baseline:

- EC/pH confirmation;
- Na;
- Cl;
- nitrate;
- K;
- Ca;
- Mg;
- sulfate;
- alkalinity;
- B;
- Fe/Mn where relevant.

Plant health:
- targeted pathogen tests by crop/risk.

Vendor/lab must state:
- method;
- LOQ;
- sample bottle;
- preservation;
- turnaround;
- unit price.

## 16. Lotto N — controls

Local PLC:

- tank level;
- high-high;
- pump;
- valve;
- treatment permissive;
- flow;
- clean/HOLD release.

Server:

- batch genealogy;
- reuse ratio;
- ion mass balance;
- lab result;
- scheduler;
- OPEX.

Interface:
- Modbus TCP;
- OPC UA;
- MQTT/REST via edge.

## 17. Fail-safe

Required behavior:

### Sensor fail
- no automatic increase in reuse ratio;
- HOLD where classification is uncertain.

### Treatment fail
- no clean-tank release.

### High-high dirty
- stop/limit contributing irrigation if agronomically safe;
- otherwise approved emergency containment.

### Wrong valve position
- stop pump.

### Server loss
- local validated fallback only.

## 18. Commissioning

Required tests:

1. C1 dye test;
2. C2 dye test;
3. no C1/C2 crossflow before measurement;
4. max flow;
5. slope/ponding;
6. flowmeter calibration;
7. EC/pH calibration;
8. dirty tank high-high;
9. HOLD route;
10. treatment failure;
11. clean tank protection;
12. blend 0/25/50% test;
13. simulated high EC;
14. simulated Na/Cl limit;
15. discharge meter/sample point;
16. stormwater cross-connect inspection;
17. 24 h mass balance;
18. 7 day mass balance.

## 19. Pilot one compartment

Before full reuse rollout:

- choose C1 or C2;
- collect 30–60 days;
- measure feed/drain;
- lab ions;
- treatment test;
- limited blend;
- crop response;
- pathogen monitoring.

Pilot output:

- actual drain m³/day;
- actual reuse possible;
- bleed reason;
- €/m³ reused;
- fertilizer recovered;
- labor/maintenance.

## 20. Documentation

Require:

- P&ID;
- hydraulic calculation;
- slopes;
- tank volume;
- valve matrix;
- I/O;
- material compatibility;
- treatment validation;
- sampling plan;
- maintenance;
- spare list;
- as-built;
- commissioning results.

## 21. Economic format

| Campo | Richiesto |
|---|---|
| code | yes |
| make/model | yes |
| qty | yes |
| net price | yes |
| VAT | separate |
| freight | separate |
| install | separate |
| civil works | separate |
| controls | separate |
| commissioning | separate |
| annual service | separate |
| consumables | separate |
| lab | €/sample |
| power | kW/kWh |
| water loss | m³ |
| cleaning | h/month |
| warranty | yes |
| lead time | yes |
| exclusions | yes |

## 22. TCO comparison

Compare:

- R0 measure/hold only;
- R1 partial reuse;
- R2 high reuse;
- separate C1/C2 tanks vs common dirty tank;
- 5 vs 10 m³;
- UV vs heat vs membrane;
- internal lab sampling vs service contract.

## 23. Purchase gate

No full reuse plant order before:

1. C1/C2 drain pilot;
2. 30–60 day chemistry;
3. source Na/Cl;
4. treatment validation;
5. legal discharge route;
6. tank sizing;
7. RFQ installed;
8. agronomic sign-off.
