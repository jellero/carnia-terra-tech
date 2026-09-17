# BOM-024 — Tech Barn: celle frigorifere

**Aggiornato:** 17 settembre 2026  
**Ambito:** due celle positive indipendenti + precooling.  
**Stato:** ARCHITETTURA E CANDIDATI / TAGLIE FINALI DA KG-PRODOTTO E RFQ.

## 1. Distinta

| Codice | Voce | Q.tà working | Stato | Benchmark / nota |
|---|---|---:|---|---|
| COLD-ROOM-A | cella COLD-LEAF | 1 | BASELINE | ~25 m², 1–3 °C |
| COLD-ROOM-B | cella COOL-SENSITIVE | 1 | BASELINE | ~25 m², 10–12 °C |
| COLD-PAN-100 | pannelli 100 mm class | ~2 cells | DA RFQ | PIR/PUR hygienic |
| COLD-FLOOR | insulated structural floor | 2 | CANTIERE/RFQ | stacker wheel load |
| COLD-DOOR | insulated logistics door | 2 | DA LAYOUT | >=1.2 m working |
| COLD-DOOR-SW | door contact | 2 | OBBLIGATORIO | controller + logger |
| COLD-IMPACT | wall/door guards | 1 lot | OBBLIGATORIO | pallet/carts |
| COLD-REF-A | refrigeration CR-A | 1 system | DA LOAD | compare 1×100 vs modular |
| COLD-REF-B | refrigeration CR-B | 1 system | DA LOAD | independent |
| COLD-EVAP-A | low-TD evaporator | 1–2 | DA LOAD | high RH |
| COLD-EVAP-B | low-TD evaporator | 1–2 | DA LOAD | gentle airflow |
| COLD-COND | condensers / monoblocks | 2–4 | DA SCENARIO | heat rejected outside |
| COLD-DEF | defrost | per evap | DA DESIGN | off-cycle/electric/hot gas |
| COLD-DRAIN | condensate drains | 2+ | BASELINE | trapped/controlled |
| COLD-CTRL | refrigeration controller | 2 | OEM/BASELINE | local |
| COLD-RS485 | comms | 2 | REQUISITO | local supervision |
| COLD-TEMP | room temperature probes | 4–6 | COMMISSIONING | map then final positions |
| COLD-RH | RH probes | 2 | OBBLIGATORIO | crop quality |
| COLD-LOGGER | independent T/RH logger | 2 | OBBLIGATORIO | Testo class |
| COLD-ALARM | horn/beacon/remote alarm | 1 system | OBBLIGATORIO | independent relay |
| COLD-ENERGY | energy meter | 2 | OBBLIGATORIO | per cell |
| COLD-LIGHT | LED cold room lighting | 2 systems | BASELINE | door logic |
| COLD-ESTOP | local electrical isolation | 2 | BASELINE | service |
| COLD-UPS | control/logger UPS | 1 | BASELINE | no compressor |
| COLD-PRE | forced-air precool module | 0–1 | CANDIDATO FORTE CR-A | kg/batch from harvest |
| COLD-RACK | hygienic racks | DA LAYOUT | SEPARATE BOM | pallet/crates |
| COLD-SP-CTRL | spare controller | 1 | PREFERENZA | if common family |
| COLD-SP-PROBE | spare T probe | 2 | RICAMBIO | common type |
| COLD-SP-FAN | evaporator fan | 1 | DA SLA | critical |
| COLD-SP-GASKET | door gasket | 1 set | RICAMBIO | model-specific |
| COLD-COM | commissioning package | 1 | OBBLIGATORIO | mapping/pull-down/alarm |

## 2. Temperature architecture

CR-A:
- 1–3 °C working;
- leaf lettuce/baby leaf/spinach;
- high RH;
- ethylene-sensitive products separated from tomato.

CR-B:
- 10–12 °C working;
- tomato/pepper/basil;
- adjustable;
- crop-specific dwell limits.

Basil does not go into CR-A as routine.

## 3. Shell benchmark

Ristoattrezzature 4,74×4,74×2,54 m, refrigeration excluded:

- **€6.775,99 + IVA** observed;
- floor area ~22,47 m²;
- two shells = **€13.551,98 + IVA** benchmark.

PREZZO TROVATO. Not project quote. Do not scale linearly to 5×5.

GGM room example 2,825×5,275×2,19 m / 25,98 m³ / 100 mm / floor:
- €8.899,99 net;
- refrigeration excluded.

Different geometry and use, only cross-check.

## 4. R290 monoblock benchmarks

GGM KDC800N:
- R290 / 0,15 kg;
- -5…+15 °C;
- room max 50 m³ stated;
- compressor 2,25 kW;
- 400 V;
- Modbus/Bluetooth;
- **€5.399,99 net**.

Two = €10.799,98 net hardware, but **not enough evidence for our working cells** because room volume alone and product pull-down are unresolved.

GGM KDC600N:
- R290 / 0,15 kg;
- max 35,1 m³ at 32 °C, 21 m³ at 43 °C;
- compressor 1,48 kW;
- 400 V;
- **€4.899,99 net**.

Four units (2/cell) = €19.599,96 net benchmark for a modular concept. This does not prove sizing or 50% redundancy.

TEFCOLD CRPF1830 turnkey small-room benchmark:
- 12,34 m³;
- 0…+8 °C;
- R290;
- 905 W connection;
- 80 mm panels;
- €7.467 observed.

Useful only to cross-check market order of magnitude.

## 5. Controls / loggers

Testo 160 TH:
- T + RH Wi-Fi logger;
- **€180 + IVA/cad**;
- two = €360 + IVA.

Carel IR33 class:
- ~€143,84–215,02 + IVA depending variant;
- RS485 option ~€80,72 + IVA.

If OEM controller already covers functionality, avoid duplicate purchase; independent logger remains desirable.

## 6. Catalog benchmark stacks

Catalog lower-bound, not design:

- 2 shells 4,74×4,74: €13.551,98 + IVA;
- 2× KDC800N: €10.799,98 net;
- 2× logger: €360 + IVA;
- subtotal catalog items ~**€24,7k + IVA**, but refrigeration is likely undersized for 60–70 m³ cells/product pull-down.

Modular comparison:
- same shells;
- 4× KDC600N: €19.599,96 net;
- loggers €360;
- subtotal ~**€33,5k + IVA** before doors upgrades, structural floor, electrical, install, drains, humidity, precooling, racking and commissioning.

These are BENCHMARK, not CAPEX project.

## 7. Cost buckets still RFQ

- building-integrated insulated floor;
- wide doors;
- custom refrigeration/split;
- electrical boards/cabling;
- condensate;
- humidification if needed;
- precool module;
- installation;
- refrigerant safety;
- racks;
- service contract;
- commissioning;
- backup/generator integration.

## 8. Refrigerant rule

Default 2026:
- R290/natural where safe/appropriate;
- otherwise refrigerant GWP <150.

Avoid new stationary architecture based on refrigerants likely to be blocked by 2030 F-gas placement restrictions.

## 9. Failure modes

- compressor/fan failure;
- controller/sensor drift;
- door left open;
- iced evaporator;
- blocked drain;
- high humidity condensation;
- low humidity dehydration;
- blackout;
- overfilled room / poor airflow;
- product entering too warm;
- refrigerant leak;
- network failure.

Fallback:
- local control survives network;
- independent logger/alarm;
- product transfer;
- alternate room setpoint if agronomically acceptable;
- emergency refrigerated rental;
- service SLA;
- manual temperature check.

## 10. Gate

Do not order until:
- peak harvest kg/day;
- batch mass;
- field temperature;
- pull-down time;
- crate/pallet geometry;
- floor/door logistics;
- room dimensions;
- summer ambient;
- RH strategy;
- precool choice;
- load calculation;
- refrigerant risk assessment;
- installed RFQ;
- electrical/generator strategy;
- service/spares;
- HACCP/monitoring plan.
