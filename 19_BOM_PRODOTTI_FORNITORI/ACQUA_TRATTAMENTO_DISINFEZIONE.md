# BOM-032 — Trattamento e disinfezione acqua

**Aggiornato:** 18 settembre 2026  
**Ambito:** W0 source -> W1 irrigazione, W2 aerosol/fogging, W3 potable/food interface, predisposizione W4 reuse.  
**Stato:** `ARCHITETTURA STRUTTURATA / UV PRIMARY CANDIDATE / ANALISI, UVT, MICROBIOLOGIA E RFQ BLOCCANTI`.

## 1. Regola

BOM-032 non sostituisce BOM-014.

BOM-014:
- solidi;
- sabbia;
- 120 mesh;
- controlavaggio.

BOM-032:
- qualità;
- microbiologia;
- UV;
- biofilm;
- sanitation;
- verification.

## 2. Distinta

| Codice | Voce | Q.tà working | Stato | Benchmark |
|---|---|---:|---|---:|
| WT-ANA-W0 | source water baseline analysis | 1 per source + seasonal | OBBLIGATORIO | lab RFQ |
| WT-ANA-MIC | microbiology W0/W1 | multiple | OBBLIGATORIO | lab RFQ |
| WT-ANA-UVT | UVT254 | multiple | OBBLIGATORIO | lab/portable RFQ |
| WT-ANA-W2 | aerosol/fogging panel | if used | CONDITIONAL | lab RFQ |
| WT-ANA-W3 | potable/process full panel | if own W3 source | CONDITIONAL | accredited lab RFQ |
| WT-SAMPLE | professional sampling | per campaign | BASELINE | ARPA FVG public tariff reference: €26 surface/groundwater sample; analyses extra |
| WT-UV-A | UV reactor train A | 1 | WORKING | ProMinent DULCODES LP class, RFQ |
| WT-UV-B | UV reactor train B | 1 | REDUNDANCY CANDIDATE | RFQ |
| WT-UV-LOW | non-process 10 m3/h UV market lower-bound | ref only | NON-COMPARABLE | ~€1.813–3.603 retail pool-class observed |
| WT-UV-CTRL | UV controller/intensity/dose | 1 per reactor | BASELINE | included/RFQ |
| WT-UV-FLOW | validated flow input/meter | 1 | BASELINE | interface existing flow/RFQ |
| WT-UV-BYP | monitored maintenance bypass | 1 | BASELINE | normally closed |
| WT-UV-ISO | full-bore isolation valves | per train | BASELINE | RFQ |
| WT-UV-NRV | non-return valves | P&ID | BASELINE | RFQ |
| WT-UV-SP1 | spare UV lamp | >=1/type | SPARE | RFQ |
| WT-UV-SP2 | spare quartz sleeve | >=1/type | SPARE | RFQ |
| WT-UV-SP3 | O-rings/seals | 1 lot | SPARE | RFQ |
| WT-UV-SP4 | ballast/power module strategy | 1 | SPARE/SLA | RFQ |
| WT-RECIRC | tank recirculation manifold | 1 | BASELINE | RFQ |
| WT-REC-A | tank A return/isolation | 1 | BASELINE | RFQ |
| WT-REC-B | tank B return/isolation | 1 | BASELINE | RFQ |
| WT-SP0 | source sample point | per source | BASELINE | RFQ |
| WT-SP1A | tank A sample point | 1 | BASELINE | RFQ |
| WT-SP1B | tank B sample point | 1 | BASELINE | RFQ |
| WT-SP2 | pre-UV sample point | 1 | BASELINE | RFQ |
| WT-SP3 | post-UV sample point | 1 | BASELINE | RFQ |
| WT-SP5 | end-line representative sample point | 1+ | BASELINE | RFQ |
| WT-TURB | online turbidity | 0–1 | CANDIDATE | RFQ |
| WT-UVT | online UVT254 | 0–1 | OPTIONAL INITIALLY | RFQ |
| WT-PH | pH measurement | shared/dedicated | BASELINE | interface BOM-016 |
| WT-EC | EC measurement | shared/dedicated | BASELINE | interface BOM-016 |
| WT-TTEMP | tank water temperature | 2 | BASELINE | RFQ |
| WT-CHEM-SKID | sanitation dosing skid | 0–1 | PREDISPOSED/CONDITIONAL | RFQ |
| WT-CHEM-PUMP | disinfectant dosing pump | 0–1 duty + spare path | CONDITIONAL | gamma/X / beta/X / DFXa class RFQ |
| WT-CHEM-TANK | dedicated chemical tank | 0–1 | CONDITIONAL | RFQ |
| WT-CHEM-BUND | secondary containment | 0–1 | CONDITIONAL | RFQ |
| WT-CHEM-LEVEL | continuous/low-low level | 0–1 set | CONDITIONAL | RFQ |
| WT-CHEM-LEAK | leak sensor | 0–1 | CONDITIONAL | RFQ |
| WT-CHEM-FLOW | dosing verification | 0–1 | CONDITIONAL | RFQ |
| WT-ORP | ORP sensor | 0–1 | PROCESS-DEPENDENT | not universal concentration measurement |
| WT-CL | free chlorine sensor | 0–1 | IF HYPOCHLORITE | RFQ |
| WT-H2O2 | peroxide monitoring | 0–1 | IF H2O2 | method/vendor RFQ |
| WT-PAA | PAA monitoring | 0–1 | IF PAA | method/vendor RFQ |
| WT-NAOCL-COST | sodium hypochlorite 14–15%, 25 kg | consumable ref | COST-CLASS ONLY | ~€27,50–85 retail observed; authorization/suitability separate |
| WT-H2O2-COST | H2O2 35% 25 L high-purity reference | ref only | NON-INDUSTRIAL COST REF | €297 observed SAFC; industrial RFQ |
| WT-PAA-COST | PAA 15% 25 kg pro retail reference | ref only | COST-CLASS ONLY | ~€79,99 incl. VAT observed; suitability/authorization separate |
| WT-W2-FILT | fogging fine filtration | 0–1 | W2 CONDITIONAL | RFQ |
| WT-W2-UV | fogging UV/other treatment | 0–1 | W2 CONDITIONAL | RFQ |
| WT-W2-RO | fogging RO | 0–1 | HARDNESS/NOZZLE CONDITIONAL | RFQ |
| WT-W3-BFP | backflow prevention W3/W1 | 1+ | BASELINE IF W3 | RFQ |
| WT-W3-TREAT | own-source potable treatment | 0–1 | ALTERNATIVE TO MAINS | RFQ |
| WT-PLC | local treatment permissive logic | 1 | BASELINE | INTERNAL/PLC |
| WT-SERVER | server integration/lab result registry | 1 | BASELINE | INTERNAL |
| WT-COM | commissioning/validation | 1 | OBBLIGATORIO | RFQ/internal |
| WT-SAN-SOP | tank/line sanitation SOP | 1 | OBBLIGATORIO | internal + specialist |
| WT-LAB-SCHED | water sampling scheduler | 1 | BASELINE | server/internal |

## 3. UV benchmark

### DULCODES LP general

Current OEM table:
- 1×80 LP: max 8,8 m3/h, 110 W connected;
- 1×230 LP: max 35 m3/h, 310 W connected.

### DULCODES LP certified reference

At published 98%/cm UVT basis:
- 1×80: 6,4 m3/h;
- 1×230: 20,7 m3/h.

Meaning:

**flow rating cannot be copied without UVT and validated dose basis.**

Final item:
- `WT-UV-A/B = RFQ`.

## 4. UV retail lower bound

Observed generic/pool-class 10 m3/h UV listings:
- ~€1.812,79;
- ~€2.463,95;
- ~€3.603,49 depending listing/configuration.

These are **not approved BOM candidates**.

Use only to detect absurd RFQ orders of magnitude.

A process/validated UV system with:
- dose validation;
- sensor;
- controls;
- hygienic/process materials;
- service;
- redundancy;

is not economically comparable to a pool sterilizer.

## 5. UV power

Illustrative ProMinent connected load:

### 2×1×80 class
- 2×110 W = 220 W when both active.

At 10 m3/h total:
- ~0,022 kWh/m3 UV electrical order-of-magnitude before pumps/controls.

### 1×230 class
- 310 W.

At 10 m3/h:
- ~0,031 kWh/m3.

These are arithmetic illustrations from OEM connected load, not guaranteed operating energy.

## 6. Chemical cost caution

Chemical purchase price is a small part of chemical-treatment TCO.

Need include:

- authorized product;
- transport dangerous goods;
- storage life;
- decay;
- tank;
- bund;
- pump;
- monitoring;
- PPE;
- training;
- residual analysis;
- disposal.

Cheap hypochlorite is not evidence continuous chlorination is the best architecture.

## 7. Chlorate control

If hypochlorite is used:

- record supplier;
- manufacturing/expiry date;
- concentration;
- storage temperature;
- lot;
- age.

Reason:
- chlorine disinfectants can contribute to chlorate residues;
- chlorate MRL rules exist for food.

Use only amount needed by validated process.

## 8. Dedicated dosing

Disinfection chemistry **must not reuse BOM-016 nutrient/acid dosing lines**.

Hard separation:

- nutrient A;
- nutrient B;
- acid;
- disinfectant.

Especially:
- acid and hypochlorite kept physically separated.

## 9. Lab economics

ARPA FVG tariff page currently lists sampling references such as:

- potable-water first sample: €21;
- subsequent sample: €10;
- surface/groundwater sample: €26.

These are sampling tariffs, **not the full analytical panel cost**.

Final lab budget:
- accredited lab RFQ by analyte/panel;
- campaign frequency.

## 10. Initial sampling plan budget structure

Before commissioning:

- each source × 2–3 seasonal/condition samples;
- tank A/B;
- pre/post UV;
- end-line.

After commissioning:
- intensified first month;
- normalize only after stable trend.

Do not optimize lab cost before understanding source variability.

## 11. Tank recirculation

Use shared pumps/filters/UV when possible to avoid duplicate skid.

Controls:

- select tank A or B;
- confirmed valve positions;
- no unwanted cross-connect;
- flow minimum;
- recirc timer/volume;
- stop on treatment fault.

Cost:
- incremental pipe/valves/sensors, RFQ.

## 12. W2 cost boundary

Fogging treatment is incremental:

- high-quality filter;
- possible RO;
- UV;
- dedicated clean reservoir/loop if required.

Do not force RO on 30–35 m3/day irrigation volume merely because fogging nozzles need low mineral water.

## 13. W3 cost boundary

Prefer separate potable network/source.

If own treatment:
- analyze to potable standard;
- higher documentation/material/monitoring burden.

CAPEX/OPEX must be kept separate from W1 irrigation.

## 14. Biofilm maintenance cost

Track:

- line flush water;
- sanitation chemical;
- operator time;
- emitter replacement;
- tank cleaning;
- analysis.

KPI:
- biofilm interventions / 1000 m3;
- emitter CV/flow drift;
- microbiological trend.

## 15. OPEX formula

`OPEX = UV_electric + lamp_amortization + sleeve/sensor + lab + chemicals + sanitation_water + backwash + operator_hours + waste`.

Compute:
- €/m3 W1;
- €/m3 W2;
- €/m3 W3 separately.

## 16. Spare strategy

Minimum if UV is critical:

- spare lamp;
- sleeve;
- seals;
- controller/ballast fast path;
- isolation valve parts.

If only one dosing pump is installed:
- complete spare pump or same-day compatible replacement preferred.

## 17. Purchase gate

No final UV/chemical order before:

1. source;
2. Q peak;
3. UVT worst-case;
4. turbidity;
5. Fe/Mn;
6. hardness/alkalinity;
7. microbiology;
8. W1 risk assessment;
9. W2 decision;
10. W3 strategy;
11. U1/U2 redundancy;
12. validation target;
13. lab plan;
14. chemical authorization/product choice;
15. RFQ installed.
