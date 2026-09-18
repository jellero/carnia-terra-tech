# RFQ — Trattamento e disinfezione acqua — BOM-032

**Progetto:** Carnia TerraTech  
**Aggiornato:** 18 settembre 2026  
**Stato:** `RFQ TEMPLATE / SORGENTE, UVT, MICROBIOLOGIA E PORTATA DA VALIDARE`.

## 1. Oggetto

Richiesta di offerta separata e comparabile per:

- campagna analitica acqua;
- UV reactor train;
- valvole/interlock;
- sampling points;
- recirculation loop;
- eventuale dosing/sanitation skid;
- sensori;
- installazione;
- commissioning;
- validation microbiologica;
- ricambi;
- SLA.

Interfacce esistenti:

- BOM-014 filtrazione meccanica;
- BOM-015 pompe 1+1;
- BOM-016 fertirrigazione;
- BOM-018 accumulo 2×150 m3;
- BOM-030 server centrale.

## 2. Dati da fornire prima RFQ definitivo

- fonte/i acqua;
- analisi stagionali;
- UVT254;
- turbidity;
- Fe/Mn;
- hardness/alkalinity;
- organics;
- microbiology;
- Q min;
- Q normal;
- Q peak;
- pressure;
- tank turnover;
- crop family;
- W1/W2/W3 uses;
- temperature range;
- room/layout;
- desired redundancy.

## 3. Lotto A — analisi acqua

Quotare campionamento e laboratorio.

### A1 baseline W0/W1

Physical:
- turbidity;
- TSS where useful;
- color;
- UVT254;
- temperature.

Chemistry:
- pH;
- conductivity;
- alkalinity;
- hardness;
- Ca/Mg/Na/K;
- chloride;
- sulfate;
- nitrate/nitrite;
- ammonium;
- Fe;
- Mn;
- boron;
- silica if relevant;
- TOC/COD where relevant.

Microbiology:
- E. coli;
- indicator coliforms;
- enterococci or agreed indicator set;
- additional source-specific parameters.

### A2 W2 aerosol

Add:
- aerosol-risk-specific microbiology;
- Legionella where risk assessment requires;
- sampling from representative terminal points.

### A3 W3 potable/process

Quote a compliant accredited panel under D.Lgs. 18/2023 s.m.i.

Do not replace full W3 compliance with the reduced irrigation panel.

## 4. Lotto B — UV system

Quote at least two architectures.

### B1 — split/degraded-capacity

Two smaller reactors in parallel.

Target:
- total validated Q >= peak;
- one train failure leaves useful degraded flow.

### B2 — full duty/standby

2×100% reactors.

Target:
- full peak flow with either single unit.

Reference product family:
- ProMinent DULCODES LP;
- equivalent validated UV system.

Vendor must state:

- validated dose;
- UVT assumption;
- max flow at worst UVT;
- lamp ageing factor;
- sleeve fouling factor;
- intensity sensor;
- automatic power modulation;
- alarms;
- pressure drop;
- water temperature;
- operating pressure;
- lamp hours;
- certifications/validation methodology.

"10 m3/h UV" without validated UVT/dose curve is not acceptable.

## 5. Lotto C — UV hydraulic skid

Quote:

- inlet/outlet manifolds;
- isolation valves;
- non-return;
- flow control;
- drain;
- sample points;
- pressure gauges;
- temperature;
- supports;
- maintenance clearance;
- bypass with monitored valve position.

Bypass must be:
- normally closed;
- identified;
- monitorable;
- lockable where appropriate.

## 6. Lotto D — UV controls

Provide:

- local controller;
- lamp state;
- intensity;
- dose/validated permissive;
- lamp hours;
- cleaning/service status;
- flow input;
- dry contact or Modbus/TCP/API where available.

Required outputs:

- READY;
- LOW_DOSE;
- LAMP_FAIL;
- SENSOR_FAIL;
- SERVICE_DUE;
- FLOW_LIMIT.

Local PLC owns permissive.

Central server logs/trends only.

## 7. Lotto E — tank recirculation

Use existing main pumps/filters/UV where hydraulically practical.

Quote:

- return manifold;
- tank-select valves;
- non-return;
- flow meter;
- sample point;
- safe drain/flush.

Modes:

- recirc tank A;
- recirc tank B;
- treatment to irrigation;
- tank isolation.

No uncontrolled A<->B equalization.

## 8. Lotto F — chemical sanitation skid

Quote as option, not automatic baseline.

At minimum provide compatible options for:

- sodium hypochlorite;
- hydrogen peroxide;
- peracetic acid product family.

Vendor must identify:

- authorized intended use/product;
- material compatibility;
- recommended monitoring;
- safe storage;
- off-gassing;
- decomposition/storage life;
- injection point;
- contact time;
- neutralization/flush needs.

No fixed dose accepted without application basis.

## 9. Dosing pump

Reference classes:

- ProMinent gamma/X;
- beta/X;
- DULCOFLEX DFXa for gassing/viscous chemistry;
- equivalent.

Requirements:

- flow-paced control;
- max dose limit;
- low-low tank;
- no-flow=no-dose;
- calibration cylinder or equivalent;
- injection valve;
- anti-siphon;
- pressure relief;
- leak containment;
- remote run/fault.

## 10. Chemical storage

Quote:

- dedicated tank;
- bund;
- level;
- venting;
- fill connection;
- labeling;
- lock/controlled access.

Hard requirement:

**acid concentrate and hypochlorite shall not share storage/containment/drain paths that permit accidental mixing.**

Vendor to show segregation.

## 11. Lotto G — monitoring sensors

Quote separately:

- UV intensity;
- UVT254 online optional;
- pH;
- EC;
- ORP;
- free chlorine if selected;
- H2O2/PAA monitoring approach if selected;
- tank temperature;
- turbidity online optional.

For each:

- accuracy;
- range;
- calibration;
- maintenance;
- consumables;
- 4–20 mA/Modbus/API;
- spare sensor price.

Do not quote ORP as a universal substitute for disinfectant concentration.

## 12. Lotto H — sampling points

Minimum:

- source;
- tank A;
- tank B;
- pre-UV;
- post-UV;
- end-of-line representative;
- fogging branch;
- W3 point if present.

Requirements:

- representative;
- safe;
- labeled;
- drainable;
- sanitary where use requires.

## 13. Lotto I — W2 fogging branch

Quote dedicated treatment if fogging uses same raw source.

Requirements:

- fine filtration;
- scaling strategy;
- microbial treatment;
- stagnation control;
- sampling;
- optional RO if nozzle/scaling analysis supports it.

RO is not baseline for W1 irrigation.

## 14. Lotto J — W3 potable/process branch

If vendor proposes own-source W3 treatment, quote separately:

- pre-treatment;
- filtration;
- UV;
- optional carbon/RO/other barriers according analysis;
- potable storage if any;
- backflow protection;
- materials suitable for drinking-water use;
- commissioning/validation;
- compliance documentation.

Alternative:
- mains potable supply.

Do not merge W1/W3 pricing.

## 15. Lotto K — spare kit

UV:
- 1 spare lamp per installed lamp type;
- quartz sleeve;
- O-rings;
- ballast/power module strategy;
- intensity sensor spare or fast SLA;
- wiper parts if fitted.

Dosing:
- diaphragm/tube;
- valves;
- injection valve;
- seals;
- level switch;
- dosing pump spare if single point of failure.

Sensors:
- pH/ORP electrodes where used;
- calibration buffers;
- chlorine membrane/electrolyte if applicable.

## 16. Validation test

Required:

### Hydraulic
1. max flow;
2. min flow;
3. pressure drop;
4. recirculation A;
5. recirculation B;
6. one UV train unavailable;
7. bypass alarm.

### UV
8. low-intensity simulation;
9. flow above valid range;
10. lamp fail;
11. sensor fail;
12. permissive stop.

### Microbiology
13. representative pre/post samples;
14. tank samples;
15. end-of-line sample.

No vendor may guarantee microbiological performance solely from catalogue flow rating.

## 17. Chemical skid acceptance, if installed

1. tank low-low;
2. leak detection;
3. no-flow=no-dose;
4. max dose limit;
5. pump fault;
6. calibration;
7. injection check valve;
8. spill response;
9. acid/hypochlorite segregation inspection.

## 18. Documentation

Require:

- P&ID;
- materials;
- electrical;
- I/O list;
- operating envelope;
- dose validation;
- UVT requirement;
- commissioning report;
- maintenance;
- spare list;
- SDS;
- chemical compatibility;
- calibration procedures.

## 19. Economic format

| Campo | Richiesto |
|---|---|
| item/code | yes |
| make/model | yes |
| qty | yes |
| net price | yes |
| VAT | separate |
| freight | separate |
| installation | separate |
| commissioning | separate |
| annual service | separate |
| lamp cost | separate |
| sleeve cost | separate |
| sensor cost | separate |
| chemical €/kg/L | if applicable |
| power W/kW | yes |
| max validated flow | yes |
| UVT basis | yes |
| pressure loss | yes |
| warranty | yes |
| lead time | yes |
| exclusions | yes |

## 20. OPEX quote

Vendor to provide estimated:

- lamp replacement interval;
- electrical kWh/1000 m3;
- sleeve cleaning;
- sensor service;
- annual calibration;
- chemical consumption under stated assumptions;
- operator hours/month.

All assumptions must be explicit.

## 21. Comparison scenarios

Compare:

- two smaller UV trains vs 2×100%;
- UV only vs UV + sanitation skid;
- online UVT vs periodic UVT;
- own-source W3 treatment vs potable mains;
- W2 with/without RO depending actual hardness/nozzle requirement.

## 22. Vendor selection

Weight:

- validated process performance;
- service Italy/FVG;
- spare lead time;
- integration;
- maintenance;
- lifecycle cost;
- clear operating envelope.

Do not select by lowest UV reactor price.
