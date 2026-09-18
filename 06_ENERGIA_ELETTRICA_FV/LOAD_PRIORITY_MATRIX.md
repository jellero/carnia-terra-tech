# Load priority matrix — BOM-034

**Aggiornato:** 18 settembre 2026  
**Stato:** `WORKING MATRIX / POTENZE REALI E CORRENTI DI SPUNTO DA MISURARE O RFQ`.

## 1. Obiettivo

Definire cosa resta alimentato quando:

- manca la rete;
- BESS entra in island;
- SOC scende;
- potenza richiesta supera 30 kW;
- un carico tenta restart simultaneo.

La classificazione è per **funzione**, non per reparto.

## 2. Priorità

| Classe | Regola |
|---|---|
| P0 | non deve perdere alimentazione o deve superare blackout senza reboot |
| P1 | necessario a survival/prodotto; può essere duty-limited |
| P2 | continuità produttiva utile ma sacrificabile |
| P3 | differibile; shed immediato in island salvo permesso |

## 3. Matrice working

| Asset/funzione | Priorità | Potenza nota/working | Island baseline | Note |
|---|---|---:|---|---|
| PLC safety/control | P0 | DA QUADRO | yes | local logic |
| edge gateway OT | P0 | DA MISURA | yes | buffer events |
| network core | P0 | DA MISURA | yes | server/PLC connectivity |
| server NODE-A/B/QNODE | P0 | DA MISURA | yes | shed only noncritical VMs |
| BESS/BMS/fire controls | P0 | OEM aux | yes | intrinsic |
| fire/security/access | P0 | DA PROGETTO | yes | essential only |
| cold-room controls/logger | P0 | small | yes | control separate from compressors |
| irrigation control | P0 | small | yes | valves/PLC |
| one irrigation pump | P1 | 2.2 kW candidate | yes when needed | BOM-015 |
| standby irrigation pump | P2 | 2.2 kW | normally no | one at a time |
| fertigation dosing | P1 | low-kW/sub-kW | yes when irrigation critical | BOM-016 |
| W1 UV treatment | P1 | ~0.1–0.3 kW class candidate | yes when needed | BOM-032 |
| CR-A holding refrigeration | P1 | compressor class ~2.25 kW + aux | yes | start sequencing |
| CR-B holding refrigeration | P1/P2 | compressor class ~1.48–2.25 kW + aux | conditional | crop/load state |
| greenhouse vents/actuators | P1 | DA RFQ | yes | weather/survival |
| HAF essential subset | P1 | DA BOM | conditional | subset only |
| animal welfare | P1 | DA BOM | yes if needed | not all amenities |
| essential lighting | P1 | DA LAYOUT | limited | safety only |
| PDC module #1 | P2/P1 emergency | up to 9 kW max declared | conditional | only if thermal store insufficient |
| PDC module #2 | P3 | up to 9 kW | no baseline | shed |
| PDC module #3 | P3 | up to 9 kW | no baseline | shed |
| PDC module #4 future | P3 | up to 9 kW | no | shed |
| DG-3 dehumidifier | P2/P3 | 2.3 kW | conditional | crop-risk only |
| DG-12 dehumidifier | P3 | 9.55 kW | no baseline | shed |
| packaging line | P2/P3 | DA RFQ | stop orderly | resume later |
| smart retail refrigeration | P1/P2 | DA RFQ | temperature-driven | store may close |
| retail payment/exit | P1 | low | yes while customers present | otherwise close store |
| AMR charging | P3 | DA RFQ | no | defer |
| AMR mission completion | P2 | battery internal | finish/park | no charging unless allowed |
| mower charging | P3 | DA BOM | no | defer |
| workshop | P3 | DA QUADRO | no | shed |
| visitor/relax services | P3 | DA LAYOUT | no | shed |
| BOM-029 process line | P3 | future | no baseline | controlled stop |
| forecast/AI training | P3 | IT workload | no | pause |
| bulk backup/compaction | P3 | IT workload | no | defer |

## 4. P0 bus

The P0 bus must have:

- measured load;
- max startup/transient;
- dual feed where designed;
- no-break test;
- selective protection in grid/island.

No unknown socket circuit is allowed on P0.

## 5. P1 power budget

P1 is not "everything useful".

Working examples:
- one irrigation pump;
- one/two cold-room holding stages;
- selected greenhouse actuators/fans;
- animal welfare;
- safety lighting.

A 30 kW PCS should have power margin for startup/transients.

Final P1 sum:
- `DA LOAD REGISTER`.

## 6. Thermal strategy

Before starting one 9 kW PDC in island:

1. read thermal tank useful kWh;
2. read compartment Tmin/time-to-limit;
3. read outside forecast;
4. read BESS SOC/available kW;
5. shed P2/P3;
6. start only one module;
7. stage additional thermal load only by emergency rule.

The PDC is an energy source conversion load, not P0 by default.

## 7. Cold-room strategy

During outage:
- holding temperature > aggressive pull-down;
- stagger compressor starts;
- defer defrost if OEM permits and food safety is not compromised;
- door-open alert;
- minimize access.

When power returns:
- do not start CR-A, CR-B and PDC simultaneously.

## 8. Water strategy

Survival watering has priority over:
- noncritical cleaning;
- tank recirculation;
- reuse treatment campaigns;
- backwash unless required for flow.

If one 2.2 kW pump can satisfy critical watering:
- standby remains off.

## 9. Store strategy

If outage:
- ongoing paid customer session may complete only if payment/network policy works;
- otherwise store closes to new entry;
- refrigeration continues by SKU priority;
- displays/noncritical lighting shed.

No "keep store open at all costs".

## 10. Restart groups

### RG0
- switchgear;
- BESS;
- PLC;
- network;
- server.

### RG1
- water controls;
- cold-room controls;
- safety/security.

### RG2
- cold-room compressors staggered;
- irrigation pump if demanded.

### RG3
- greenhouse fans/actuators;
- selected PDC if allowed.

### RG4
- production/logistics.

### RG5
- charging/deferred loads.

Each group:
- delay;
- max simultaneous kW;
- interlock.

## 11. Measurements required

For every >1 kW load:

- true power;
- current per phase;
- PF;
- inrush;
- startup duration;
- duty cycle.

For VFD/inverter loads:
- harmonic/current quality as needed.

For compressor/motor:
- restart delay;
- locked/stall current from OEM where available.

## 12. Load-profile data model

Record:

- 1 s/10 s raw or edge aggregate for transients where useful;
- 1 min ops profile;
- 15 min demand;
- daily energy;
- max demand timestamp.

Fields:
- asset;
- kW;
- kvar;
- kVA;
- PF;
- V;
- A;
- Hz;
- phase imbalance;
- state;
- priority;
- grid/island.

## 13. Island optimizer

Constraint:

`Σ P_active_allowed <= P_BESS_available - reserve_power_margin`

And:

`E_remaining >= E_required_P0P1_to_target_time`

If not:
- shed lowest priority;
- reduce duty;
- delay task;
- notify.

## 14. Power reserve

Do not dispatch to exact 30.0 kW steady-state.

Need reserve for:
- motor start;
- compressor start;
- control error;
- battery derating;
- temperature;
- phase imbalance.

Final margin:
- OEM/system study.

Working simulation:
- compare 20%, 25%, 30% power headroom.

## 15. Acceptance

Test real combined loads:

1. P0 only;
2. P0+P1 normal;
3. P0+P1 max;
4. P0+P1 + one P2 motor start;
5. attempt >30 kW;
6. low SOC;
7. restart after grid return.

No nuisance trip and no hidden unmanaged load.