# Trattamento e disinfezione acqua — BOM-032

**Aggiornato:** 18 settembre 2026  
**Stato:** `WORKING ARCHITECTURE / QUALITÀ SORGENTE, UVT, MICROBIOLOGIA E RFQ BLOCCANTI / MULTI-BARRIERA DEFINITA`.

## 1. Obiettivo

Portare ogni acqua alla qualità richiesta dal suo uso reale, senza imporre un trattamento unico a tutta l'azienda.

Principio:

`source quality + use risk -> required barriers -> verification -> release`

Non esiste una sola "acqua trattata" Carnia TerraTech.

## 2. Classi acqua

### W0 — raw/source

Possibili origini:

- pioggia;
- pozzo;
- acquedotto;
- altra fonte autorizzata;
- miscela.

W0 non viene considerata automaticamente idonea né all'irrigazione food crop né al processo alimentare.

### W1 — irrigation root-zone

Uso:

- gocciolatori;
- fertirrigazione;
- substrato/terreno;
- nessun aerosol intenzionale;
- contatto con parte edibile minimizzato per progetto.

Requisito:
- qualità agronomica;
- controllo microbiologico risk-based;
- protezione da contaminazione del prodotto;
- compatibilità con crop/emettitori.

### W2 — aerosol / fogging / spray

Uso:

- fogging;
- nebulizzazione;
- qualunque servizio che può aerosolizzare acqua vicino a lavoratori/visitatori/prodotto.

W2 è separata da W1 perché il rischio cambia.

Richiede:
- hazard analysis dedicata;
- microbiologia più stringente;
- gestione ristagno/temperatura;
- eventuale Legionella risk assessment quando pertinente.

### W3 — potable / food-process / handwash

Uso:

- BOM-029 quando acqua potabile è necessaria per evitare contaminazione;
- lavamani;
- drinking water;
- lavaggi food quando richiesto;
- ingrediente/process water dove applicabile.

W3 deve essere conforme al quadro vigente delle acque destinate al consumo umano quando rientra in tale uso.

**Non assumere che W1 diventi W3 perché è passata attraverso UV.**

### W4 — future reclaimed drainage

Drenaggio colturale eventualmente recuperato.

Non baseline BOM-032.

Passa a BOM-033 con:

- separazione;
- mass balance nutrienti;
- fitopatogeni;
- microbiologia;
- salinità;
- sodio/cloruri;
- pesticidi/contaminanti se pertinenti;
- trattamento;
- blending;
- validation.

## 3. Base normativa / igienica

Per la produzione primaria vegetale, Reg. (CE) 852/2004 richiede di proteggere i prodotti dalla contaminazione e, quando necessario, usare acqua potabile o acqua pulita.

Per BOM-029/food-process, lo stesso regolamento richiede un adeguato approvvigionamento di acqua potabile quando necessario a evitare contaminazione e separazione delle reti non potabili.

Per acqua destinata al consumo umano in Italia:
- D.Lgs. 18/2023;
- modifiche D.Lgs. 102/2025.

Per eventuale riuso di **acque reflue urbane trattate** per irrigazione agricola:
- Reg. (UE) 2020/741;
- classi, monitoraggio e risk management specifici.

Il Reg. 2020/741 non viene applicato automaticamente al drenaggio interno di serra: BOM-033 deve classificare giuridicamente la fonte reale.

## 4. Architettura baseline W1

Working:

`fonte -> accumulo 2x150 m3 -> BOM-015 pompe -> BOM-014 filtrazione -> UV validated reactor -> flow/UV-dose permissive -> BOM-016 fertigation -> sectors`

Con possibilità di recirculation:

`tank A OR tank B -> pumps -> filtration -> UV -> return selected tank`

per:

- turnover;
- trattamento fuori finestra irrigua;
- recovery dopo intervento;
- test.

Non equalizzare automaticamente i due tank durante una contaminazione.

## 5. Perché UV baseline

UV:

- non aggiunge sale;
- non altera direttamente EC;
- non introduce un residuo ossidante nel nutrient solution;
- è automatizzabile;
- è misurabile tramite intensity/dose/permissive;
- riduce il rischio di interazione con fertilizzanti rispetto a un oxidant residual continuo.

Limiti:

- nessun residual downstream;
- performance dipende da UVT/turbidity/fouling/flow;
- non rimuove sali;
- non rimuove sedimenti;
- non "pulisce" biofilm già formato nelle linee;
- non rende automaticamente acqua potabile.

Perciò UV è una barriera, non l'intero water-safety plan.

## 6. Posizione UV

UV viene installato:

- dopo la filtrazione meccanica;
- prima della fertirrigazione;
- in posizione drenabile/manutenibile;
- con campionamento prima/dopo;
- con flow meter;
- con intensity/dose monitoring;
- con interlock.

Evitare baseline:

`fertilizer-rich water -> UV`

perché colore/assorbimento/depositi e composizione possono ridurre la robustezza della dose.

## 7. Sizing UV

Non dimensionare da sola portata nominale.

Richiedere:

- Q min/max;
- UVT254 worst-case;
- turbidity;
- iron/manganese;
- hardness/scaling;
- target UV dose;
- validated flow-dose curve;
- lamp ageing;
- sleeve fouling;
- water temperature.

Il produttore deve fornire il **validated operating envelope**.

### Benchmark ProMinent DULCODES LP

Dati OEM correnti:

- 1×80 LP: fino 8,8 m3/h non-certified general table;
- 1×230 LP: fino 35 m3/h general table;
- certified potable-water series at 98%/cm UVT:
  - 1×80 LP: 6,4 m3/h;
  - 1×230 LP: 20,7 m3/h.

Questi numeri mostrano perché il flow rating cambia con dose/validation/UVT.

## 8. Redundancy UV options

### U1 — two smaller parallel trains

Esempio class:
- 2×6–9 m3/h.

Normal:
- both available / flow split.

Failure:
- degraded irrigation at ~50% flow.

Pro:
- graceful degradation.

### U2 — 2×100% duty/standby

Esempio class:
- 2×20 m3/h each.

Pro:
- full capacity after single failure.

Contro:
- higher CAPEX.

### U3 — single reactor + bypass

Not preferred if UV is a required microbial barrier.

Bypass:
- maintenance only;
- physically identified;
- normally closed;
- position monitored;
- no automatic untreated delivery unless a validated operating mode says water quality remains acceptable.

Working preference:
- U1 or U2 after actual peak flow.

## 9. UV permissive

Irrigation automatic permission requires:

- UV unit healthy;
- lamp ON;
- validated intensity/dose >= setpoint;
- flow <= validated max;
- no UV sensor fault;
- sleeve/temperature state acceptable;
- downstream valve path correct.

If invalid:

- stop/limit flow;
- alert;
- do not silently bypass;
- allow manual degraded mode only if risk assessment defines it.

## 10. Chemical treatment — not continuous baseline

Dedicated chemical disinfection is **conditional**.

Potential uses:

- shock sanitation tanks/lines;
- biofilm recovery;
- source-specific residual control;
- future recycled water;
- sanitation after maintenance.

Candidate families:

- sodium hypochlorite;
- hydrogen peroxide;
- peracetic acid formulations;
- other authorized products/processes.

Selection requires:

- intended use;
- current biocidal authorization/product label;
- crop compatibility;
- material compatibility;
- residue/by-product review;
- SDS;
- worker safety;
- food-residue impact where relevant.

No "dose X ppm everywhere" rule.

## 11. Chlorine caution

Hypochlorite can provide useful residual action, but baseline continuous chlorination is not assumed because:

- crop sensitivity varies;
- fertilizer chemistry varies;
- pH changes active chlorine fraction;
- organic load consumes demand;
- chlorate can arise from chlorine disinfectant use and food MRLs exist;
- concentrated hypochlorite ages and can form chlorate;
- wrong dosing can damage crops/equipment.

If selected:
- dedicated tank;
- dedicated dosing pump;
- bund;
- flow-paced dosing;
- residual/free-chlorine measurement where technically valid;
- max-dose hard limit;
- no-flow=no-dose;
- fresh chemical inventory/age control.

## 12. H2O2 / peracetic candidates

Useful particularly for:

- sanitation;
- biofilm management;
- processes where chlorine residual is undesirable.

But:
- not "safe by default";
- compatibility/concentration/exposure need validation;
- concentrated product is hazardous;
- decomposition and residual need monitoring method;
- do not mix with incompatible chemicals.

Dedicated chemical skid, independent from nutrient A/B/acido.

## 13. Ozone

Ozone is **not baseline**.

Potential benefit:
- powerful oxidation/disinfection;
- no long-lived chlorine residual.

Costs/risks:
- generator;
- mass transfer;
- off-gas destruction;
- worker exposure;
- ORP not equal to ozone dose;
- no durable residual;
- bromate concern if bromide present in relevant applications;
- higher operational complexity.

Evaluate only if UV + sanitation cannot meet requirements or W4 reuse makes it attractive.

## 14. Biofilm strategy

Biofilm control starts with design:

- opaque tanks;
- no sunlight;
- drainable low points;
- minimal dead legs;
- flushable ends;
- sufficient velocity during flush;
- removable/cleanable strainers;
- tank cleaning access;
- isolation of contaminated branch;
- material compatibility.

Monitoring:

- Δp;
- emitter flow;
- ATP optional;
- microbiology;
- visual/slime inspection;
- flushing return;
- trend of treatment demand.

UV alone does not remove established biofilm.

## 15. Tank management

For each 150 m3 tank:

- independent sample point;
- level;
- temperature;
- opaque cover;
- screened vent/overflow;
- sediment management;
- drain;
- cleaning access;
- dedicated isolation;
- recirculation path.

Operational states:

- AVAILABLE;
- FILLING;
- RECIRCULATING;
- HOLD;
- CLEANING;
- OUT_OF_SERVICE.

The server does not blend a HOLD tank into irrigation.

## 16. Source blending

Each source has:

- source_id;
- permit/status;
- conductivity;
- pH;
- alkalinity;
- key ions;
- microbiology;
- turbidity;
- UVT;
- date sampled.

Blend is calculated, not informal.

Server records:

`source volumes -> tank -> treatment -> irrigation batch`.

## 17. Baseline analytical panel — W0/W1

Final panel by agronomist/lab/risk assessment.

Working parameters:

### Physical
- turbidity;
- color;
- UVT254;
- temperature;
- TSS where relevant.

### Agronomic chemistry
- pH;
- EC;
- alkalinity/bicarbonate;
- hardness;
- Ca;
- Mg;
- Na;
- K;
- chloride;
- sulfate;
- nitrate;
- ammonium;
- iron;
- manganese;
- boron where relevant;
- silica where treatment requires;
- TOC/COD proxy if organic load suspected.

### Microbiology
Risk-based:
- E. coli;
- coliform indicators;
- enterococci or other agreed indicators;
- additional organisms according source/use.

For W2 aerosol:
- add specific aerosol/Legionella risk analysis when relevant.

For W3:
- use accredited potable-water panel according D.Lgs. 18/2023 s.m.i., not this reduced irrigation panel.

## 18. Sampling points

SP0 — source each origin.  
SP1A — tank A.  
SP1B — tank B.  
SP2 — after mechanical filtration.  
SP3 — after UV.  
SP4 — nutrient solution header where useful.  
SP5 — representative end-of-line sector.  
SP6 — W2 fogging branch.  
SP7 — W3 food/potable point.  
SP8 — future W4 reuse outlet.

Sample points must be designed for representative sampling and sanitizable where appropriate.

## 19. Sampling frequency

Do not hardcode a single frequency forever.

Initial commissioning:
- source baseline;
- multiple samples during first operation;
- after cleaning;
- seasonal worst-case.

Steady state:
- frequency derived from source stability/use/risk/history.

Trigger extra sampling:
- flood/heavy rain;
- source change;
- tank contamination;
- treatment fault;
- long stagnation;
- maintenance;
- positive microbiology;
- unexplained biofilm/emitter issue.

## 20. W3 potable / food process

Preferred architecture:

- potable mains/source with compliant treatment and separate identified network;
- backflow prevention from irrigation/fertigation;
- no direct cross-connection.

If own source supplies W3:
- full potable-water design;
- D.Lgs. 18/2023 as amended by D.Lgs. 102/2025;
- accredited testing;
- appropriate materials in contact;
- monitoring/risk plan;
- validated treatment.

Do not treat a 300 m3 irrigation tank as a potable reservoir by default.

## 21. W2 fogging

BOM-003/serra fogging water quality must be revisited.

Requirements:

- no nutrient solution;
- dedicated branch;
- fine filtration;
- scaling control;
- microbial risk control;
- drain/stagnation control.

If RO is needed for nozzle/scaling reasons:
- RO belongs to W2 dedicated treatment, not automatically all irrigation water.

## 22. Future W4 drainage reuse

BOM-033 will decide:

- collection;
- segregation;
- storage;
- nutrient balance;
- pathogens;
- treatment;
- bleed;
- blending.

For urban reclaimed wastewater, Reg. (UE) 2020/741 sets minimum classes and monitoring. Example Class A includes:
- E. coli <=10/100 mL;
- BOD5 <=10 mg/L;
- TSS <=10 mg/L;
- turbidity <=5 NTU;
- Legionella <1000 cfu/L where aerosolisation risk exists.

These numbers are a **legal reference for that scope**, not an automatic internal-drainage specification.

## 23. Controls and sensors

Baseline signals:

- source/tank level;
- tank temperature;
- flow;
- pressure;
- Δp filters;
- UV intensity/dose;
- UV lamp hours;
- UV alarm;
- UVT online optional;
- pH;
- EC;
- treatment chemical tank level if used;
- dosing pump stroke/flow confirmation;
- ORP/free chlorine only if process selected and measurement is meaningful.

All critical controls have local permissives.

Server:
- trends;
- predicts cleaning/lamp service;
- schedules samples;
- stores lab results;
- correlates water lot with crop lot.

## 24. UVT online

Optional initially.

Install when:
- source UVT varies materially;
- rain/source blending changes frequently;
- UV dose margin is small;
- W4 reuse starts.

Otherwise:
- lab/portable UVT + UV reactor intensity/dose can be sufficient.

## 25. Chemical skid safety

If oxidant introduced:

- chemical tank separate from A/B/acido;
- bund/secondary containment;
- ventilation if required;
- incompatible products physically separated;
- injection check valve;
- anti-siphon;
- pressure relief;
- leak detection;
- low-low;
- eyewash/emergency provisions by risk assessment;
- SDS accessible;
- labeling.

No shared suction line between acid and hypochlorite.

## 26. Critical incompatibility

**Acid + hypochlorite can release chlorine gas.**

Therefore:
- physically segregated storage;
- separate dosing skids;
- separate bunds where appropriate;
- no common drain that can mix concentrates;
- interlocked maintenance;
- documented spill response.

This is a hard safety constraint.

## 27. Failure modes

| Failure | Response |
|---|---|
| UV lamp failure | degraded train / stop treatment |
| UV dose low | limit/stop flow + alarm |
| UV sensor failed | no automatic "assume OK" |
| UV sleeve fouling | service based on intensity/trend |
| bypass open | alarm + block automatic release |
| turbidity spike | hold/reduce, investigate source/filter |
| positive microbiology | tank HOLD + resample + sanitation |
| tank contamination | isolate one tank, operate other if released |
| chemical overfeed | stop dosing/flow, hold water |
| chemical pump stuck | no-flow/no-dose + flow verification |
| acid/hypochlorite proximity | design prevents mixing |
| biofilm rise | flush/sanitize/inspect |
| source switch | require source profile/release |
| lab result late | risk-based hold or continue per validated rule |
| server down | local PLC permissive remains |

## 28. Maintenance

UV:
- lamp hours;
- quartz sleeve;
- wiping/cleaning;
- intensity sensor;
- seals;
- ballast;
- spare lamp;
- calibration/verification.

Dosing:
- diaphragm/tube;
- check valves;
- calibration;
- injection quill;
- chemical age;
- bund inspection.

Tank:
- sediment;
- cover;
- vent screen;
- drain;
- cleaning.

## 29. Commissioning

1. source analytical baseline;
2. tank hygiene inspection;
3. filter performance;
4. worst-case UVT measurement;
5. UV validated flow envelope;
6. dose/intensity alarm;
7. low-dose automatic response;
8. bypass interlock;
9. sampling points;
10. microbiology pre/post;
11. recirculation tank A;
12. recirculation tank B;
13. single-train UV degraded mode;
14. chemical skid dry test if installed;
15. no-flow/no-dose;
16. leak/spill simulation;
17. server event/log;
18. manual fallback.

## 30. OPEX model

`OPEX_water_treatment = electricity_UV + lamps + sleeves + sensors + lab + chemicals + filter_backwash + cleaning_water + maintenance_hours + waste/disposal`.

Track:

- €/m3 treated;
- kWh/m3;
- chemical g/m3;
- lab €/m3;
- maintenance h/1000m3;
- rejected/hold m3;
- flush m3.

## 31. Architecture decision

**Baseline BOM-032:**

- BOM-014 mechanical filtration retained;
- UV as primary point-of-use microbial barrier for W1 if risk analysis requires disinfection;
- UV flow/dose permissive and no blind bypass;
- existing 2×150 m3 tanks independently isolable;
- use main treatment loop for controlled tank recirculation;
- no continuous chlorine/H2O2/PAA baseline until source/biofilm data justify;
- dedicated sanitation skid/predisposition;
- W2 fogging separate quality class;
- W3 potable/food separate network/qualification;
- W4 future reuse deferred to BOM-033.

## 32. Gate BOM-032

1. final source(s);
2. water rights/availability;
3. source seasonal analyses;
4. UVT worst-case;
5. microbiological baseline;
6. target W1 risk level;
7. W2 fogging use;
8. W3 source strategy;
9. peak flow;
10. U1/U2 redundancy;
11. chemical sanitation choice;
12. material compatibility;
13. lab sampling plan;
14. bypass/interlocks;
15. RFQ;
16. commissioning validation.
