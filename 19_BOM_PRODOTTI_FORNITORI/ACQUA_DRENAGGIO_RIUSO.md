# BOM-033 — Drenaggio, raccolta e riuso acqua

**Aggiornato:** 18 settembre 2026  
**Ambito:** drenaggio colturale, misura, dirty/HOLD, trattamento reuse, clean tank, blending, bleed/discharge, stormwater segregation.  
**Stato:** `ARCHITETTURA STRUTTURATA / R0 MISURA+HOLD BASELINE / RIUSO R1 DOPO PILOT 30–60 GIORNI / PORTATE E TANK DA CROP CARD`.

## 1. Regola

Implementazione staged:

### R0 — baseline obbligatoria
- gutter/collectors;
- C1/C2 segregati;
- volume;
- EC/pH/T;
- HOLD;
- sampling;
- discharge route predisposition.

### R1 — dopo pilot
- treatment;
- clean tank;
- partial blend;
- controlled bleed.

### R2 — ottimizzazione
- variable reuse;
- nutrient mass balance;
- higher closed-loop fraction.

## 2. Distinta

| Codice | Voce | Q.tà working | Stato | Benchmark / nota |
|---|---|---:|---|---|
| DR-C1-BR | C1 drain branches | DA LAYOUT | BASELINE | interface BOM-006 |
| DR-C2-BR | C2 drain branches | DA LAYOUT | BASELINE | interface BOM-006 |
| DR-C6-BR | C6 reusable drain branch | 0–1 | FUTURE/IF SOILLESS | DA CROP |
| DR-COLL-C1 | C1 dedicated collector | 1 | BASELINE | DN/slope DA CALCOLO |
| DR-COLL-C2 | C2 dedicated collector | 1 | BASELINE | DN/slope DA CALCOLO |
| DR-CO | clean-out/inspection points | DA LAYOUT | BASELINE | RFQ |
| DR-FLOW-C1 | C1 drain volume/flow measurement | 1 | BASELINE | mag/tank/tipping option |
| DR-FLOW-C2 | C2 drain volume/flow measurement | 1 | BASELINE | mag/tank/tipping option |
| DR-EC-C1 | C1 EC measurement | 1 | BASELINE | process transmitter RFQ |
| DR-PH-C1 | C1 pH measurement | 1 | BASELINE | process transmitter RFQ |
| DR-T-C1 | C1 drain temperature | 1 | BASELINE | RFQ |
| DR-EC-C2 | C2 EC measurement | 1 | BASELINE | RFQ |
| DR-PH-C2 | C2 pH measurement | 1 | BASELINE | RFQ |
| DR-T-C2 | C2 drain temperature | 1 | BASELINE | RFQ |
| DR-HOLD-V | abnormal/HOLD routing valve set | 1 lot | BASELINE | feedback + fail state |
| DR-DIRTY-5 | opaque PE tank 5 m³ | 0–2 | RFQ SCENARIO | retail external 5.000 L ~€1.159 only lower-bound tank benchmark |
| DR-DIRTY-10 | dirty/HOLD tank 10 m³ | 0–2 | RFQ SCENARIO | installed process tank RFQ |
| DR-DIRTY-LVL | dirty tank continuous level | 1/tank | BASELINE | radar/hydrostatic RFQ |
| DR-DIRTY-HH | independent high-high | 1/tank | BASELINE | RFQ |
| DR-DIRTY-SP | sample point | 1/tank | BASELINE | RFQ |
| DR-CLEAN-5 | clean/reuse tank 5 m³ | 0–1 | R1 SCENARIO | RFQ |
| DR-CLEAN-10 | clean/reuse tank 10 m³ | 0–1 | R1 SCENARIO | RFQ |
| DR-CLEAN-LVL | clean tank level | 1 | R1 | RFQ |
| DR-CLEAN-EC | clean tank EC | 1 | R1 | RFQ |
| DR-CLEAN-PH | clean tank pH | 1 | R1 | RFQ |
| DR-CLEAN-T | clean tank temperature | 1 | R1 | RFQ |
| DR-PUMP-TREAT | dirty -> treatment pump | 1+spare path | R1 | RFQ |
| DR-PUMP-BLEND | clean -> blend pump | 1+spare path | R1 | RFQ |
| DR-FILT-REUSE | pre-treatment filtration | 1 | R1 | DA TREATMENT |
| DR-UV-REUSE | validated UV drain-water treatment | 0–1 | R1 CANDIDATE | separate envelope from BOM-032 W1 |
| DR-HEAT | heat treatment reuse | 0–1 | ALT | RFQ |
| DR-UF | UF/membrane treatment | 0–1 | ALT | RFQ |
| DR-OZONE | ozone/AOP | 0–1 | ALT | RFQ |
| DR-TREAT-FLOW | treatment flow meter | 1 | R1 | RFQ |
| DR-TREAT-PLC | treatment permissive | 1 | R1 | PLC/local |
| DR-BLEND-FRESH | fresh water flow/control | 1 | R1 | interface BOM-015/016 |
| DR-BLEND-REUSE | reuse flow/control | 1 | R1 | RFQ |
| DR-BLEND-CHECK | non-return/backflow | 2+ | R1 | RFQ |
| DR-BLEND-MIX | blend/mixing section | 1 | R1 | RFQ |
| DR-BLEED-FLOW | final bleed/discharge meter | 0–1 | LEGAL ROUTE DEPENDENT | RFQ |
| DR-BLEED-SP | final discharge sample point | 0–1 | LEGAL ROUTE DEPENDENT | RFQ |
| DR-BLEED-V | controlled discharge valve | 0–1 | LEGAL ROUTE DEPENDENT | lock/feedback |
| DR-LAB-ION | Na/Cl + ion panel | pilot + periodic | BASELINE | accredited lab RFQ |
| DR-LAB-PATH | crop pathogen panel | risk-based | BASELINE/R1 | lab RFQ |
| DR-TURB | turbidity drain/treatment | 0–1 | CANDIDATE | RFQ |
| DR-SAMPLE-C1 | C1 sample point | 1 | BASELINE | RFQ |
| DR-SAMPLE-C2 | C2 sample point | 1 | BASELINE | RFQ |
| DR-SAMPLE-POST | post-treatment sample | 0–1 | R1 | RFQ |
| DR-SAMPLE-FEED | blended feed sample | 1 | R1 | RFQ |
| DR-STORM-SEP | stormwater/drain segregation | 1 lot | BASELINE | masterplan/civil |
| DR-WASH-SEP | floor wash segregation | 1 lot | BASELINE | civil/P&ID |
| DR-BACKWASH | BOM-014 backwash routing | 1 | BASELINE | classify before reuse |
| DR-ENDCYCLE | end-of-cycle solution routing | 1 | BASELINE | HOLD |
| DR-PIPE-EXT | external drainage piping | DA LAYOUT | BASELINE | FVG 2026 category 50 / RFQ |
| DR-CHAMBER | inspection/manholes | DA LAYOUT | BASELINE | FVG 2026 category 50 |
| DR-GRAVEL | drainage gravel | DA LAYOUT | CONDITIONAL | FVG 2026 €38,50/m³ reference |
| DR-SERVER | drain batch genealogy | 1 | BASELINE | INTERNAL |
| DR-MASSBAL | water/nutrient mass-balance software | 1 | BASELINE | INTERNAL |
| DR-REUSE-ALG | reuse ratio/Na-Cl guardrail | 1 | R1 | INTERNAL |
| DR-COM-PILOT | one-compartment 30–60 day pilot | 1 | OBBLIGATORIO | internal + lab |
| DR-COM-DYE | dye/cross-connect test | 1 | OBBLIGATORIO | commissioning |
| DR-COM-MASS | 24 h + 7 d mass balance | 1 | OBBLIGATORIO | commissioning |
| DR-SPARES | valves/sensor seals/spares | 1 lot | BASELINE | RFQ |

## 3. Tank benchmark caution

Observed retail:
- external PE 5.000 L rainwater tank: ~€1.159.

This is only a **tank shell lower-bound**.

Not included:
- chemical/nutrient compatibility confirmation;
- level;
- fittings;
- cleanable drain;
- bund/foundation;
- overflow;
- process valves;
- installation.

Therefore:
- DR-DIRTY/CLEAN process tanks remain RFQ.

## 4. Tank sizing

Do not order 5 or 10 m³ simply because they are BOM scenarios.

Dirty tank:

`V_dirty = max drainage accumulated before next treatment window × operational factor + freeboard`.

Clean tank:

`V_clean = treatment batch + irrigation timing buffer + reserve`.

Inputs:
- actual C1/C2 drainage;
- treatment capacity;
- reuse timing;
- weekend mode;
- emergency hold.

## 5. Drain fraction upper-bound sanity check

Project historical gross irrigation peak:
- ~30–35 m³/day all water users.

If an illustrative 30% drain fraction were incorrectly applied to all irrigation:
- 9–10,5 m³/day.

But only selected soilless circuits are candidates.

Therefore this is **not a tank design figure**.

Measure actual C1/C2 drain before sizing.

## 6. Sensors

Reuse existing technology classes where possible.

EC/pH:
- industrial 4–20 mA/Modbus;
- removable/calibratable;
- separate from nutrient-control sensors if sharing would create blind spots.

Sensor economics:
- BOM-016 Hanna HI98143-22 class was benchmarked ~€615 + IVA excluding probes.

This price is useful only as order-of-magnitude.

Drain sensors need:
- correct range;
- fouling access;
- continuous immersion/bypass compatibility.

## 7. Piping/civils

FVG Prezzario 2026:
- category 50 covers external disposal/containment systems including piping, manholes, drains and accessories;
- drainage gravel item 10.3.CP1.01 = **€38,50/m³**.

Use exact 2026 item after:
- DN;
- SN class;
- burial;
- road load;
- material.

Do not use electrical conduit price as drainage pipe proxy.

## 8. Legal cost

Budget separate:

- technical classification memo;
- SUAP/AUA application if required;
- lab;
- final discharge sample point;
- flow meter;
- civil connection fees;
- sewer utility charges where applicable.

No fixed regulatory CAPEX before municipality/recipient.

## 9. Treatment selection

### UV

Use only if:
- drain UVT sufficient;
- validated pathogen target;
- nutrient solution does not cause unmanageable fouling.

### Heat

Potentially robust:
- higher energy;
- HX/storage integration possible.

### Membrane

Potential:
- solids/pathogen barrier;
- fouling + reject stream.

### Ozone/AOP

Potential:
- strong oxidation;
- higher safety/control burden.

Final technology by pilot.

## 10. Nutrient recovery value

For each batch:

`€_nutrient_recovered = Σ kg_i_reused × purchase_cost_i`.

Do not value drain only as avoided fresh water.

But do not value nutrients that cannot safely be reused.

## 11. Controlled bleed value

Bleed is sometimes necessary to control:
- Na;
- Cl;
- nutrient imbalance;
- contamination.

A lower reuse percentage can be more profitable than crop loss.

Decision metric:

`net benefit reuse = water + nutrients + avoided discharge - treatment - lab - labor - risk`.

## 12. Pathogen loss risk

One pathogen incident propagated by reuse can exceed years of water savings.

Therefore treatment validation and hydraulic isolation are CAPEX protection, not optional "quality extras".

## 13. Pilot economics

Pilot records:

- m³ feed;
- m³ drain;
- m³ treated;
- m³ reused;
- m³ bled;
- EC;
- Na;
- Cl;
- fertilizer correction;
- kWh;
- lab;
- operator minutes;
- crop outcome.

After 30–60 days calculate:
- €/m³ recovered;
- kg fertilizer recovered;
- treatment OPEX;
- projected annual payback.

## 14. Stormwater boundary

D0 roof rainwater:
- BOM-018.

D4 clean/contaminated stormwater:
- masterplan/FVG PRTA.

D1 nutrient drain:
- BOM-033.

These are separate cost centers and pipelines.

## 15. OPEX

`OPEX033 = pump + treatment + lab + sensors + cleaning + maintenance + bleed/discharge + operator`.

Track:
- €/m³ drainage collected;
- €/m³ reuse;
- kWh/m³ treatment;
- lab €/month;
- maintenance h/month.

## 16. CAPEX structure

Final installed CAPEX:

`collection + sensors + dirty/HOLD + treatment + clean tank + blending + discharge interface + civils + controls + commissioning`.

Report separately:
- R0;
- R1 incremental;
- R2 incremental.

This allows construction of R0 now and later reuse only if economics/agronomy support it.

## 17. Gate

No R1 full-order before:

1. 30–60 day pilot;
2. actual drainage;
3. Na/Cl;
4. pathogen strategy;
5. treatment proof;
6. tank sizing;
7. legal discharge path;
8. installed RFQ;
9. lifecycle economics;
10. agronomic approval.
