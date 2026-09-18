# BOM-034 — EMS, BESS e connessione elettrica

**Aggiornato:** 18 settembre 2026  
**Ambito:** accumulo, islanding, EMS, metering, load shedding, connessione DSO.  
**Stato:** `ARCHITETTURA STRUTTURATA / 30 kW POWER BASELINE / kWh-BT-MT-FIRE-RFQ BLOCCANTI`.

## 1. Distinta

| Codice | Voce | Q.tà working | Stato | Benchmark / nota |
|---|---|---:|---|---|
| EN-BESS-PCS30 | PCS C&I 30 kW 3~ | 1 | BASELINE | RFQ |
| EN-BESS-E60 | battery useful ~60 kWh | 0–1 | SCENARIO E1 | RFQ |
| EN-BESS-E90 | battery useful ~90 kWh | 0–1 | SCENARIO E2 | RFQ |
| EN-BESS-E120 | battery useful ~120 kWh | 0–1 | SCENARIO E3 | RFQ |
| EN-BESS-LFP | LFP battery racks | as config | WORKING | OEM RFQ |
| EN-STILLA | TESLA STILLA 30kW/61kWh reference | ref | CANDIDATE CLASS | 30 kW / 61 kWh / LFP / 0.5C / RFQ |
| EN-FRONIUS | Verto Plus 30 kW + storage reference | ref | ALT TECH | up to 63.2 kWh Reserva public C&I configuration; transfer gate |
| EN-PCS-BMS | BMS/PCS local controller | 1 | BASELINE | OEM |
| EN-FIRE | BESS fire detection/protection package | 1 | BASELINE | OEM + fire engineer RFQ |
| EN-HVAC | BESS HVAC/heaters | 1 | BASELINE | OEM |
| EN-ESTOP | emergency isolation | 1 | BASELINE | RFQ |
| EN-FOUND | BESS foundation/bollards | 1 lot | DA LAYOUT | civil RFQ |
| EN-CRIT-BUS | P0/P1 critical switchboard | 1 | BASELINE | RFQ |
| EN-ISLAND | islanding/grid separation device | 1 | BASELINE | exact topology RFQ |
| EN-ATS | mechanical ATSE | 0–1 | CONDITIONAL | not sufficient alone for P0 no-reboot if interruption too long |
| EN-STS | static transfer system | 0–1 | CONDITIONAL | only with two valid live sources |
| EN-SHED-P0 | P0 feeder group | 1 | BASELINE | non-sheddable except emergency |
| EN-SHED-P1 | P1 feeder group | 1 | BASELINE | survival |
| EN-SHED-P2 | P2 feeder group | 1 | BASELINE | shed by SOC/power |
| EN-SHED-P3 | P3 feeder group | 1 | BASELINE | first shed |
| EN-PLC-PWR | local power/load-shed controller | 1 | BASELINE | PLC/industrial controller RFQ |
| EN-M0 | PCC advanced meter | 1 | BASELINE | PM5340 class €1,469 list benchmark |
| EN-M0-MID | PCC/sub-billing MID option | 0–1 | OPTIONAL | PM5341 €1,694 list benchmark |
| EN-M-SIMPLE | branch energy meters | DA LOAD | BASELINE | lower-cost DIN Modbus RFQ |
| EN-M-IT | server/network meter | 1 | BASELINE | RFQ |
| EN-M-PDC | PDC branch/per-unit meters | 1–4 | BASELINE | RFQ |
| EN-M-CR | cold-room meters | 2 | BASELINE | RFQ |
| EN-M-WATER | irrigation/water meter | 1+ | BASELINE | electrical meter, not flow meter |
| EN-M-RETAIL | retail meter | 1 | BASELINE | RFQ |
| EN-PCC-SPD | PCC/main SPD | 1 set | BASELINE | lightning/protection design |
| EN-SPI | interface protection | 0–1 | DSO/TOPOLOGY | CEI/DSO RFQ |
| EN-DDI | interface device | 0–1 | DSO/TOPOLOGY | RFQ |
| EN-CCI | CCI | 0–1 | MT >=100 kW IF APPLICABLE | RFQ |
| EN-SLI | System Limitation of Injection | 0–1 | IF EXPORT LIMIT | certified architecture RFQ |
| EN-DSO | DSO connection application/study | 1 | OBBLIGATORIO | TICA |
| EN-GAUDI | GAUDI registration/support | 1 | AS APPLICABLE | integrator |
| EN-TRAFO | MV/LV transformer/cabin | 0–1 | ONLY IF MT | DSO/RFQ |
| EN-MV | MV switchgear/protection | 0–1 lot | ONLY IF MT | RFQ |
| EN-QA | power-quality / harmonic study | 1 | BASELINE | engineering RFQ |
| EN-SC | short-circuit/selectivity study | 1 | BASELINE | engineering RFQ |
| EN-FIRE-ENG | BESS fire-risk assessment | 1 | BASELINE | fire engineer |
| EN-EMS | site EMS software/control | 1 | BASELINE | INTERNAL + local PLC |
| EN-FORECAST | PV/load/tariff forecast | 1 | BASELINE | BOM-030 internal |
| EN-DEGR | battery degradation accounting | 1 | BASELINE | internal |
| EN-PV-ISLAND | PV microgrid/island integration | 0–1 | OPTIONAL | exact OEM combination |
| EN-BLACKSTART | black-start function | 1 | REQUIREMENT | OEM validation |
| EN-COMMISSION | blackout/island commissioning | 1 | OBBLIGATORIO | RFQ |
| EN-SPARES | critical spares | 1 lot | BASELINE | OEM RFQ |

## 2. Energy scenarios

| Scenario | Useful energy | 10 kW load | 15 kW | 20 kW | 30 kW |
|---|---:|---:|---:|---:|---:|
| E1 | 60 kWh | 6 h | 4 h | 3 h | 2 h |
| E2 | 90 kWh | 9 h | 6 h | 4.5 h | 3 h |
| E3 | 120 kWh | 12 h | 8 h | 6 h | 4 h |

Arithmetic only; losses/reserve/EOL reduce actual autonomy.

## 3. Candidate class benchmark

TESLA Group STILLA current public reference:
- 30–60 kW;
- 61–122 kWh;
- LFP;
- up to 0.5C;
- 400 V;
- 97.3% PCS peak efficiency;
- Modbus TCP;
- price RFQ.

At 30 kW / 61 kWh nominal:
- nameplate ratio ~2.03 h at full power before reserve/losses/EOL.

Do not treat 61 kWh nominal as 60 kWh guaranteed usable EOL.

## 4. Transfer benchmark

Fronius Verto Plus C&I offers ~30 kW full-backup class and public storage configurations up to 63.2 kWh with Reserva.

Published standard Full Backup datasheet shows ~11 s switching in that configuration.

For Carnia P0:
- this fails the no-reboot intent unless another validated rapid-transfer architecture is used;
- therefore transfer behavior is a purchase gate.

## 5. Meter benchmarks

Schneider official Italy current list observations:

- PM5110: €700;
- PM5340: €1,469;
- PM5341 MID: €1,694.

Use advanced meters only where diagnostics/accounting value justifies cost.

Branch meters:
- RFQ low-cost DIN Modbus alternatives;
- no need for PM5340 on every small load.

## 6. Known load anchors

| Load | Working electrical value |
|---|---:|
| irrigation duty pump | 2.2 kW |
| each PDC module max declared | 9 kW |
| 3 PDC max aggregate | 27 kW |
| 4 PDC future max aggregate | 36 kW |
| DG-3 dehumidifier | 2.3 kW |
| DG-12 dehumidifier | 9.55 kW |
| cold-room compressor references | 1.48–2.25 kW each + aux |

These alone prove:
- full-farm simultaneous backup cannot be assumed from 30 kW.

## 7. P0/P1 cost boundary

Core BESS should be sized for:
- P0 no-reboot;
- P1 survival/product protection;
- selected P2 only by state.

Do not size battery for:
- all PDC;
- all dehumidifiers;
- BOM-029;
- all charging;
- full workshop;
unless business case explicitly pays for it.

## 8. Ride-through P0

Non sono ammesse UPS consumer distribuite senza governance.

La baseline di confronto contiene tre architetture:

- **A — BESS no-break:** P0 direttamente sul critical bus se il trasferimento misurato non causa reboot;
- **B — BESS + ride-through P0 dedicato:** UPS online industriale/DC buffer professionale per PLC, rete, server e controlli realmente P0;
- **C — equivalente professionale:** altra soluzione con failure mode, manutenzione e SAT espliciti.

Voce:
`EN-P0-RIDE = 0–1 package / CONDITIONAL / RFQ`.

La decisione deriva da:
- transfer reale;
- affidabilità;
- autonomia necessaria;
- manutenzione;
- batterie/ricambi;
- efficienza;
- TCO 8–10 anni.

Acceptance gate:
- measured grid-loss event;
- no reboot of P0.

If a proposed BESS cannot meet this:
- reject or redesign transfer;
- non aggiungere UPS distribuite in modo implicito; se serve ride-through, inserirlo esplicitamente nel BOM e nel SAT.

## 9. Battery reserve

Simulation cases:
- 20% normal reserve;
- 30%;
- 40%.

Final reserve chosen from:
- outage probability;
- outage duration;
- crop/cold-chain loss;
- weather/PV forecast;
- battery warranty.

## 10. BESS economics

Use cases ranked:

1. resilience;
2. PV self-consumption;
3. peak shaving;
4. tariff shifting;
5. optional future market services.

Do not book revenue from ancillary services baseline.

## 11. Degradation TCO

Track:
- MWh throughput;
- EFC;
- SoH;
- temperature;
- high SOC hours;
- warranty capacity;
- replacement cost.

Dispatch only when:
`energy_value > conversion_losses + degradation_cost + resilience_opportunity_cost`.

## 12. Fire boundary

Current project requires:
- external dedicated location preferred;
- fire/explosion risk assessment;
- OEM fire/HVAC package;
- emergency isolation;
- separation/access defined by fire engineer.

No final distance or extinguishing design before selected BESS.

## 13. BT/MT boundary

Current standard references:
- CEI 0-21:2026-07 BT;
- CEI 0-16:2026-07 MT/AT.

Final:
- DSO connection quote.

If MT and applicable >=100 kW new PV:
- include CCI/PF2.

If BT/export cap:
- evaluate compliant SLI.

## 14. CAPEX structure

`CAPEX034 = BESS + PCS + fire + civil + critical bus + switchgear + meters + protection + DSO/CCI-SLI + engineering + commissioning`.

Do not double-count:
- BOM-019 PV inverter/module;
- BOM-030 server;
- domain load equipment.

## 15. OPEX

`OPEX034 = aux_energy + losses + service + inspections + software_if_any + degradation + meter/calibration + fire maintenance`.

KPI:
- €/kWh throughput;
- €/h outage protected;
- round-trip efficiency;
- self-consumption gain;
- peak reduction;
- battery availability.

## 16. Purchase gate

1. load register;
2. P0/P1 profile;
3. outage target;
4. energy scenario;
5. EOL autonomy;
6. winter derating;
7. fire location;
8. no-reboot transfer;
9. short-circuit study;
10. DSO quote;
11. BT/MT;
12. CCI/SLI;
13. island PV decision;
14. 3 comparable RFQs;
15. blackout SAT.

## 16. DSO/TICA pre-application cost scenarios

Working connection variants:

| Scenario | FV AC | Requested export | Quote-request fee benchmark | Additional gate |
|---|---:|---:|---:|---|
| G100 | 100 kW | 100 kW | €200 + IVA | BT/MT from DSO |
| G120 | 120 kW | 120 kW | €500 + IVA | BT/MT from DSO |
| G120-CAP100 | 120 kW | 100 kW | €200 + IVA | compliant SLI + curtailment study |

Fee source benchmark:
- e-distribuzione Guide Section B Ed. 8.0 May 2026 / current TICA structure.

**Decision rule:** the €300 + IVA difference between the quote-request fee for 100 and 120 kW is not a valid reason by itself to cap export.

Compare total installed economics:
`DSO works + BT/MT + transformer/cabin + protections + CCI/PF2 + SLI + meters + engineering + commissioning + curtailed energy + future expansion cost`.

Project documents:
- `06_ENERGIA_ELETTRICA_FV/DSO_TICA_CONNECTION_READINESS.md`;
- `06_ENERGIA_ELETTRICA_FV/DSO_TICA_DATA_REQUEST.csv`;
- `06_ENERGIA_ELETTRICA_FV/BT_MT_PROTECTION_DECISION_MATRIX.md`;
- `06_ENERGIA_ELETTRICA_FV/RFQ_DSO_GRID_CONNECTION_ENGINEERING.md`;
- `06_ENERGIA_ELETTRICA_FV/GRID_CONNECTION_COST_COMPARISON.csv`.

Current status:
- pre-application engineering package = structured;
- actual DSO request = blocked by real lot/DSO/POD and final import/export powers;
- connection CAPEX = RFQ/DSO, not estimated.
