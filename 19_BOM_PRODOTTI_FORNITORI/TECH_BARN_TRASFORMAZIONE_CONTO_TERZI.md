# BOM-029 — Centro trasformazione conto terzi

**Aggiornato:** 18 settembre 2026  
**Ambito:** trasformazione vegetale conto terzi / succo / puree / confetture / utilities / QC / CIP / tracciabilità.  
**Stato:** `ARCHITETTURA E CAPACITY MODEL STRUTTURATI / S2 600–700 KG/H WORKING / DOMANDA LOCALE E RFQ BLOCCANTI / CAPEX CORE NON ANCORA APPROVATO`.

## 1. Regola di lettura

Questa distinta usa:

- `BASELINE`;
- `WORKING`;
- `OPTIONAL`;
- `FUTURE`;
- `RFQ`;
- `INTERFACE`;
- `DA LAYOUT`;
- `DA DOMANDA`.

I prezzi web sono benchmark di controllo e non sostituiscono un'offerta installata.

## 2. Distinta

| Codice | Voce | Q.tà working | Stato | Benchmark |
|---|---|---:|---|---:|
| TF-LEGAL | verifica attività / SUAP / OSA | 1 | OBBLIGATORIO | consulenza/pratica |
| TF-HACCP | piano autocontrollo + process family | 1 | OBBLIGATORIO | consulenza/interno |
| TF-LAYOUT | food layout + dirty/clean zoning | 1 | OBBLIGATORIO | tecnico/RFQ |
| TF-DEMAND | indagine domanda locale 30–50 operatori | 1 | OBBLIGATORIO | internal/consulting |
| TF-RECV-SCALE | platform scale ricezione | 1 | BASELINE | RFQ legal metrology if required |
| TF-PALLET | transpallet/handling | 1–2 | BASELINE | interface BOM-025/021 where possible |
| TF-RAW-BINS | raw material bins/cassette | DA DOMANDA | BASELINE | RFQ |
| TF-WASH | washer WA LC40 class | 1 | WORKING | RFQ OEM; capacity up to 3.000 kg/h reference |
| TF-SORT | roller sorting table | 1 | BASELINE | RFQ; up to 3.000 kg/h class |
| TF-MILL | fruit mill RM2.2 class | 1 | WORKING | RFQ OEM; up to 1.000 kg/h |
| TF-PRESS-H | hydraulic 100P2 class | 0–1 | ALT | RFQ; up to 600 kg/h |
| TF-PRESS-B | belt EBP500 class | 0–1 | WORKING ALT | RFQ; up to 700 kg/h |
| TF-BUF-1 | juice buffer tank | 1 | BASELINE | RFQ |
| TF-BUF-2 | secondary/CIP buffer tank | 1 | CANDIDATE | RFQ |
| TF-PUMP | sanitary product pump | 2+ | BASELINE | RFQ |
| TF-PIPE | sanitary piping/hoses/valves | 1 lot | BASELINE | RFQ |
| TF-PAST-500 | pasteurizer 500 L/h class | 0–1 | S1/S2 ALT | RFQ |
| TF-PAST-750 | pasteurizer 750 L/h class | 0–1 | S2 WORKING | RFQ; Voran PA750 class 70 kW thermal |
| TF-BIB | MBF750 bag-in-box filler class | 1 | WORKING | RFQ; ~750 L/h @10 L reference |
| TF-BIB-3 | Bag-in-box 3 L + bag | initial 100 | CONSUMABLE | ~€114,75/100 avana; apple-branded retail benchmark similar class |
| TF-BIB-5 | Bag-in-box 5 L + bag | initial 100 | CONSUMABLE | ~€127,05/100 benchmark |
| TF-BIB-10 | Bag-in-box 10 L + bag | initial 100 | B2B | ~€204,10/100 generic wine-class benchmark; food suitability/format to verify |
| TF-BOTTLE-FILL | bottle filler | 0–1 | OPTIONAL | RFQ |
| TF-BOTTLE-CAP | bottle capper | 0–1 | OPTIONAL | €1.385,25 pneumatic Starcap benchmark; production config RFQ |
| TF-JAM-100 | agitated jam vessel 100 L | 0–1 | PILOT BENCHMARK | ~€416,39 simple motorized vessel benchmark |
| TF-JAM-200 | agitated jam vessel 200 L | 0–1 | PILOT BENCHMARK | ~€491,80 simple motorized vessel benchmark |
| TF-JAM-COOK | jacketed controlled cooker 100–200 L | 1 | WORKING | RFQ; professional heated process equipment |
| TF-JAM-FILL | semi-auto hot filler | 1 | BASELINE | RFQ |
| TF-JAM-CAP | twist-off capper | 1 | BASELINE | RFQ |
| TF-JAM-POST | post-fill pasteurization/cooling | 0–1 | PROCESS DEPENDENT | RFQ/validation |
| TF-JAR-212 | glass jar ~212 mL | pallet | CONSUMABLE | ~€688,52/1.728 pcs benchmark |
| TF-JAR-314 | glass jar ~314 mL | pallet | CONSUMABLE | ~€696,72/1.344 pcs benchmark |
| TF-LABEL | semi-auto labeler ETI 10H class | 1 | CANDIDATE | ~€3.754,10 |
| TF-CODER | lot/date coder | 1 | BASELINE | RFQ |
| TF-CIP-TANK | semi-CIP tank | 1–2 | BASELINE | RFQ |
| TF-CIP-PUMP | CIP pump | 1 | BASELINE | RFQ |
| TF-CIP-HEAT | CIP heating/HW interface | 1 | BASELINE | RFQ |
| TF-CIP-DOS | detergent dosing | 1 | BASELINE | RFQ |
| TF-CIP-COND | conductivity monitoring | 0–1 | CANDIDATE | RFQ |
| TF-HW | process hot-water buffer | 1 | BASELINE | RFQ |
| TF-HX | thermal HX | 1+ | BASELINE | RFQ |
| TF-AIR | food-compatible compressed air | 0–1 | IF REQUIRED | RFQ |
| TF-FLOOR | food-grade floor/coving | DA LAYOUT | BASELINE | regional construction RFQ |
| TF-DRAIN | trench/point drains inox | DA LAYOUT | BASELINE | RFQ |
| TF-HAND | hygiene handwash | DA LAYOUT | BASELINE | RFQ |
| TF-CHM | chemical cabinet/segregation | 1 | BASELINE | RFQ |
| TF-PH | food pH meter | 1 | BASELINE | RFQ calibrated instrument |
| TF-BRIX-H | high-Brix refractometer | 1 | BASELINE | ~€21,31 manual 58–90 Brix operational benchmark |
| TF-BRIX-L | low-Brix refractometer | 1 | BASELINE | ~€20,41 manual 0–32 Brix benchmark |
| TF-TEMP | calibrated thermometer set | 2+ | BASELINE | RFQ |
| TF-LOGGER | process temp logger | 1+ | BASELINE | RFQ |
| TF-QC-SCALE | precision scale | 1 | BASELINE | ~€251,64 HLD class benchmark |
| TF-RETAIN | retain sample shelf/storage | 1 | BASELINE | RFQ |
| TF-POMACE | pomace/by-product bins | 2+ | BASELINE | RFQ |
| TF-SCREEN | drain solids screen | 1 | BASELINE | RFQ |
| TF-WASTE-SCALE | by-product scale | 1 | CANDIDATE | interface receiving scale if workflow allows |
| TF-TRACE | batch genealogy/server integration | 1 | BASELINE | INTERNAL DEVELOPMENT |
| TF-API | machine API/gateway | 1 lot | BASELINE | RFQ/in-house |
| TF-ENERGY | submeter electricity/thermal | 1 lot | BASELINE | RFQ |
| TF-WATER | process water meter | 1+ | BASELINE | RFQ |
| TF-BESS | BESS/EMS scheduling integration | 1 | INTERFACE | existing 30 kW backup architecture |
| TF-SPARES | critical spare kit | 1 | BASELINE | RFQ |
| TF-SAT | commissioning/SAT | 1 | OBBLIGATORIO | RFQ |
| TF-TRAIN | operator/maintenance training | 1 | OBBLIGATORIO | RFQ |

## 3. Working process match

### Juice S2

Target:

- raw feed: 600–700 kg/h;
- press yield: actual from pilot, OEM references up to 75%;
- juice flow: ~420–525 L/h theoretical;
- thermal: 500–750 L/h;
- fill: >=750 L/h.

Therefore:
- WA LC40 not bottleneck;
- RM2.2 not bottleneck;
- 100P2 ~600 kg/h at upper limit;
- EBP500 ~700 kg/h aligned;
- PA500 may become bottleneck at high yield;
- PA750 gives more thermal margin;
- MBF750 aligned.

## 4. Press decision

### Hydraulic 100P2

Advantages:
- batch separation;
- visual process;
- small-lot friendly;
- lower complexity.

Disadvantages:
- cloth handling;
- more labor;
- batch cycling.

### Belt EBP500

Advantages:
- continuous;
- stable throughput;
- easier integration with scheduler.

Disadvantages:
- belt sanitation;
- water consumption;
- more continuous cleaning discipline.

**Working:** request both, decide from labor+CIP+yield TCO.

## 5. Thermal decision

Do not default to fuel just because OEM catalog models use it.

RFQ energy cases:
- electric resistance;
- hot-water HX;
- heat-pump + buffer + boost;
- gas benchmark.

Decision metric:

`€/L processed + peak kW + CO2 + integration cost + resilience`

## 6. Jam equipment caution

The low Polsinelli prices in this BOM are a control benchmark for an agitated stainless vessel.

They do **not** represent:
- industrial jacket;
- automatic thermal control;
- vacuum;
- sanitary skid;
- validated process;
- installation.

The real working cooker is `TF-JAM-COOK = RFQ`.

## 7. Packaging benchmark

### BIB

Observed 18/09/2026:
- 3 L, 100 pcs: ~€114,75 -> ~€1,15/unit;
- 5 L, 100 pcs: ~€127,05 -> ~€1,27/unit;
- apple-juice graphic 3 L retail: ~€1,48/unit in single format.

For industrial volumes:
- RFQ custom print;
- bag compatibility with fill temperature/process;
- pallet MOQ.

### Jars

Observed:
- 212 mL, 1.728 pcs: ~€688,52 -> ~€0,40/jar;
- 314 mL, 1.344 pcs: ~€696,72 -> ~€0,52/jar.

Add separately:
- lid;
- label;
- carton;
- pallet;
- breakage.

## 8. Demand proxy

Regional apple production 2024:
- ~68.735 t.

S2 at:
- 150 t/y = ~0,22% of regional apple production;
- 300 t/y = ~0,44%.

This is only a scale check.

It does **not** prove that this volume is reachable in Carnia at an acceptable logistics cost.

## 9. Minimum lot economics

Every third-party batch has fixed costs:

`setup + receiving + traceability + cleaning + CIP + label/admin + release`.

Tariff model must therefore have either:

- minimum kg;
- minimum batch fee;
- setup/CIP fee;
- or combination.

No "small lot at the same €/kg" baseline.

## 10. Costing model

For each batch:

`COGS_service = labor + energy + thermal + water + chemicals + packaging + ingredients + QC + waste + maintenance + admin + depreciation`

Quote output:
- €/kg raw;
- €/L juice;
- €/BIB;
- €/jar;
- setup;
- storage.

## 11. Working capacity economics

Illustrative capacity only:

### 60 days × 4 net h/day × 600 kg/h
= 144 t/y.

### 80 days × 5 net h/day × 700 kg/h
= 280 t/y.

### 100 days × 6 net h/day × 700 kg/h
= 420 t/y.

Use actual:
- demand;
- changeover;
- downtime;
- yield;
- labor.

## 12. Server integration

Central server stores:

- supplier;
- order;
- inbound lot;
- gross/net weight;
- QC;
- process batch;
- recipe version;
- machine;
- CCP/process readings;
- yield;
- packaging lot;
- finished lot;
- destination;
- invoice/service fee;
- cleaning record.

Scheduler reserves:
- line;
- operator;
- CIP;
- packaging;
- hot water;
- energy window;
- cell storage.

## 13. Spares

RFQ minimum:
- press cloth/belt;
- seals;
- bearings;
- pump seal kit;
- sanitary gaskets;
- temperature probe;
- flow sensor;
- solenoid;
- filler seal;
- capper wear parts;
- heater safety parts;
- motor/drive critical;
- PLC/HMI backup;
- labeler wear parts.

## 14. CAPEX structure

Do not sum benchmark retail products into a fake project total.

Final CAPEX only after installed RFQ:

`building + utilities + juice + jam + CIP + QC + packaging + integration + commissioning + contingency`.

Report separately:
- VAT;
- freight;
- civil works;
- design;
- permits;
- validation;
- spares;
- working capital.

## 15. Contribution gate

FVG SRD13:
- relevant intervention family;
- latest known 2025 call closed;
- ranking published 15/09/2026;
- do not assume new funds/call.

No contribution in base NPV until awarded.

## 16. Decision gate

Promote BOM-029 from FUTURE to funded CAPEX only when:

1. >=150 t/y credible volume for S2, or right-size lower scenario;
2. willingness-to-pay validated;
3. minimum lot defined;
4. three RFQs;
5. installed CAPEX;
6. utilities;
7. HACCP/layout;
8. staffing;
9. margin;
10. payback/NPV;
11. contribution scenario separated from no-aid case.
