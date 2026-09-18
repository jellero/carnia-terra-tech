# Drenaggio, raccolta e riuso acqua — BOM-033

**Aggiornato:** 18 settembre 2026  
**Stato:** `WORKING ARCHITECTURE / MASS BALANCE, CLASSIFICAZIONE SCARICHI, CROP CARD E RFQ BLOCCANTI / RIUSO SOLO SU FLUSSI SEGREGATI E VALIDATI`.

## 1. Obiettivo

Chiudere il ciclo idrico dove è tecnicamente, agronomicamente e legalmente sensato senza creare un sistema che:

- diffonde fitopatogeni;
- accumula sodio/cloruri o altri ioni non assorbiti;
- confonde acque meteoriche, drenato nutritivo e reflui;
- scarica nutrienti senza misura;
- rende impossibile capire da dove proviene una contaminazione;
- obbliga al riuso quando la qualità richiede bleed/discharge.

Principio:

`segregate -> measure -> classify -> treat -> blend/reuse OR hold/discharge`

Non:

`anything wet -> reuse tank`.

## 2. Classi di flusso

### D0 — rainwater clean capture

Origine:
- coperture serra;
- superfici di captazione dedicate.

Destinazione:
- BOM-018 storage/raw-water source.

Non miscelare automaticamente con drenato colturale.

### D1 — crop drainage candidato riuso

Origine:
- gutter/slab C1;
- gutter/slab C2;
- future soilless systems;
- eventuali banchi C6 dedicati.

Contiene:
- fertilizzanti residui;
- sali accumulati;
- root exudates/organics;
- possibile inoculo fitopatogeno.

È il solo flusso baseline candidato al closed-loop.

### D2 — crop flush / first-drain / abnormal nutrient stream

Origine:
- startup/fine ciclo;
- flush con EC anomala;
- line sanitation;
- cambio ricetta;
- acqua con prodotto fitosanitario/cleaner dove applicabile.

Stato:
- HOLD.

Non entra in D1 finché non classificato.

### D3 — floor/wash water

Origine:
- lavaggi corsie;
- attrezzature;
- pavimenti;
- aree tecniche.

Può contenere:
- detergenti;
- terra;
- organico;
- olio/grasso;
- residui chimici.

Rete separata.

### D4 — stormwater site

Origine:
- viabilità;
- parcheggi;
- superfici esterne.

Separare:
- meteorica pulita;
- meteorica potenzialmente contaminata.

Gestione secondo masterplan, PRTA FVG, invarianza idraulica e autorizzazioni applicabili.

### D5 — process wastewater

Origine:
- BOM-029 futuro;
- CIP;
- lavaggi food;
- processo trasformazione.

Rete e autorizzazione separate da D1.

### D6 — domestic wastewater

Servizi igienici/usi domestici.

Fuori dal circuito agricolo.

## 3. Scope del riuso

Baseline riuso:

**solo D1**.

D2 può essere ammesso soltanto dopo:
- identificazione causa;
- analisi/parametri;
- compatibilità coltura;
- nessuna chimica di cleaning incompatibile;
- release documentata.

D3/D4/D5/D6:
- non entrano nella nutrient recirculation baseline.

## 4. Architettura D1

Per ogni comparto soilless:

`gutter -> branch collector -> drain flow measurement -> EC/pH/T -> compartment drain header -> DIRTY/HOLD tank -> treatment -> CLEAN/REUSE tank -> blend/makeup -> BOM-016 fertigation -> crop`

Alternative:
- un dirty tank per C1 e C2;
- dirty tank comune con segregazione temporale tracciata;
- central dirty + compartment batch IDs.

**Working preference:** mantenere C1 e C2 misurabili separatamente almeno fino al punto di classificazione.

## 5. Perché misurare per comparto

Il drenaggio è contemporaneamente:

- acqua recuperabile;
- fertilizzante residuo;
- segnale agronomico.

KPI per C1/C2:

`drain_fraction = V_drain / V_irrigated`

`EC_delta = EC_drain - EC_feed`

`pH_delta = pH_drain - pH_feed`

`ion_recovery_i = C_drain_i × V_drain`

Questi dati mostrano:

- uptake;
- salinity accumulation;
- over/under irrigation;
- emitter issues;
- nutrient imbalance.

## 6. Nessuna percentuale fissa

Netafim usa in un esempio tecnico greenhouse/soilless drenaggi del 30% o più e riporta potenziali risparmi 30–40% su acqua/fertilizzante con riuso.

Carnia TerraTech **non assume 30% come setpoint universale**.

Il drain target dipende da:

- crop;
- substrate;
- radiation;
- irrigation frequency;
- salinity;
- rootzone EC;
- stage.

Il server registra il valore reale e il crop model ne modifica il target.

## 7. Mass balance acqua

Per intervallo t:

`V_in = V_crop_uptake + V_drain + V_evap_losses + ΔV_substrate`

Per il circuito reuse:

`V_makeup + V_reuse = V_feed`

`V_drain = V_reuse_candidate + V_bleed + V_loss + ΔV_storage`

Il sistema deve poter spiegare ogni m³.

## 8. Mass balance nutrienti

Per ogni ion i:

`M_in_i = V_fresh*C_fresh_i + V_reuse*C_reuse_i + M_fertilizer_i`

`M_out_i = M_crop_i + V_bleed*C_bleed_i + M_losses_i + ΔM_storage_i`

Critical ions:
- Na;
- Cl;
- N-NO3;
- K;
- Ca;
- Mg;
- sulfate;
- bicarbonate/alkalinity;
- micronutrients where relevant.

EC da sola non identifica quale ione sta accumulando.

## 9. Sodium/chloride rule

Closed-loop has a physical limit when ions not sufficiently taken up accumulate.

Research on soilless greenhouse tomato shows NaCl accumulation can progressively increase EC and force replacement/bleed depending management.

Therefore:

- define crop-specific Na threshold;
- define crop-specific Cl threshold;
- trend concentration;
- calculate predicted accumulation;
- trigger lower reuse ratio / bleed before root-zone limit.

No "100% reuse forever" promise.

## 10. Reuse ratio

Working variable:

`R = V_reuse / V_feed`

Limits:

`R <= min(R_EC, R_Na, R_Cl, R_pathogen, R_process)`

The scheduler/fertigation engine can choose:
- 0%;
- partial blend;
- high reuse;

within agronomic guardrails.

Human-approved limits remain authoritative.

## 11. Dirty tank

Purpose:
- hydraulic buffer;
- homogenization limited/controlled;
- treatment feed;
- HOLD capability.

Sizing formula:

`V_dirty >= peak drain collected between treatment windows + reserve + freeboard`

Do not size from daily irrigation volume alone.

RFQ comparison:
- 5 m³ class;
- 10 m³ class;
- modular 2× smaller tanks.

Final = crop-card/mass balance.

## 12. Clean/reuse tank

Purpose:
- treated/released water;
- stable feed for blending.

Rules:
- separate from dirty;
- isolated;
- level/EC/pH/T;
- sample point;
- overflow controlled;
- no dirty backflow.

Sizing:
- treatment batch size;
- irrigation demand timing;
- required reserve.

RFQ compare 5 and 10 m³ classes.

## 13. HOLD architecture

Any questionable batch goes to HOLD rather than automatic reuse.

Trigger examples:
- abnormal EC;
- abnormal pH;
- high Na/Cl result;
- pathogen alert;
- treatment fault;
- chemical-cleaning event;
- unknown source;
- pesticide/biocide event incompatible with reuse;
- sensor disagreement.

States:

`COLLECTING -> CLASSIFYING -> HOLD -> TREATING -> RELEASED / BLEED / DISPOSAL`.

## 14. Treatment W4

BOM-032 W1 UV unit sits before fertilizer addition and is optimized for raw irrigation water.

D1 contains nutrient solution and may have different:
- UVT;
- organics;
- turbidity;
- Fe/precipitates.

Therefore future-reuse treatment gets **its own validated operating envelope**.

Candidate barriers:

### R-UV
- filtration + UV;
- preferred first test if UVT supports it.

### R-HEAT
- heat treatment;
- broad pathogen capability;
- thermal/energy penalty.

### R-O3/AOP
- ozone or advanced oxidation;
- more complex safety/control.

### R-MEM
- membrane/ultrafiltration as relevant;
- fouling/concentrate handling.

### R-ELECTRO
- electrochemical disinfection R&D/alternative.

Select by:
- pathogen target;
- flow;
- nutrient stability;
- energy;
- maintenance;
- by-products.

## 15. Pathogens

Recirculating nutrient solution can spread root pathogens system-wide.

Research documents risk for:
- Fusarium;
- Pythium;
- Phytophthora;
- viruses/pathogen vectors depending crop/system.

Therefore:
- no untreated common return;
- separate crop-compartment traceability;
- treatment validation;
- positive event isolation.

The economic value of nutrient recovery never overrides crop-loss risk.

## 16. Crop isolation

If C1 develops a suspected root pathogen:

- close C1 reuse;
- HOLD C1 drain;
- C2 reuse remains independent if hydraulic segregation is proven;
- clean/sanitize affected return loop;
- sample;
- release only after agronomic/plant-health decision.

Avoid one common dirty manifold that cannot isolate crop families.

## 17. Drain sensors

Per C1/C2 working:

- cumulative drain volume;
- instantaneous/interval flow where useful;
- EC;
- pH;
- T;
- tank level.

Central reuse:
- turbidity;
- UV intensity/dose if UV;
- flow;
- treatment status;
- clean tank EC/pH/T.

Lab/periodic:
- Na;
- Cl;
- macro/micronutrients;
- plant pathogen testing when indicated.

## 18. Drain flow measurement options

### Batch weighing / tank level

Good for:
- robust daily mass balance;
- low flow.

### Electromagnetic flow meter

Good if:
- line remains full;
- conductivity adequate;
- flow within range.

### Tipping bucket / calibrated drain collector

Good for:
- compartment/sample monitoring;
- agronomy.

Final choice by hydraulic regime.

## 19. Nutrient analysis

Do not install online ion-selective sensors for every nutrient baseline.

Baseline:
- EC/pH/T online;
- periodic lab ion panel;
- fertilizer dosing mass balance.

Add online specific ion sensing only if:
- validated accuracy;
- maintenance acceptable;
- measurable economic benefit.

## 20. Bleed

Bleed is a controlled process stream, not "open valve to ground".

Each bleed event stores:

- volume;
- source crop/compartment;
- EC;
- pH;
- known nutrient concentrations;
- cause;
- destination;
- authorization basis.

Potential destinations require legal validation:
- authorized sewer;
- authorized surface-water discharge;
- authorized treatment;
- other lawful recovery/disposal.

**No default discharge to soil.**

## 21. Regulatory classification gate

D.Lgs. 152/2006:

- art. 124: scarichi require prior authorization;
- art. 103: discharge to soil is generally prohibited except defined cases;
- art. 104: direct discharge to groundwater/subsoil is prohibited except narrow derogations;
- art. 101 establishes general discharge criteria and contains cases of agricultural wastewater assimilated to domestic.

Do not pre-classify nutrient drainage as:
- domestic-equivalent;
- industrial;
- waste;
- irrigation reuse stream;

until actual company activity, source and destination are reviewed with SUAP/Regione/gestore.

FVG:
- AUA can include discharge authorization;
- authority depends on nature/recipient;
- PRTA applies.

## 22. AUA / discharge design

Before final design identify:

- exact municipality;
- sewer availability/manager;
- receiving body;
- discharge classification;
- expected max flow;
- average flow;
- nutrient load;
- monitoring point;
- sampling access;
- AUA/other title.

If discharge is industrial to sewer, FVG SUAP procedure requests technical documentation and includes flow-meter details among the listed forms.

Therefore provide a dedicated final-discharge meter/sample point if required.

## 23. Stormwater segregation

Roof water D0:
- capture/reuse BOM-018;
- overflow to stormwater design.

Clean site stormwater:
- separate drainage.

Potentially contaminated stormwater:
- separate intercept/management according FVG PRTA and site risk.

Never connect nutrient bleed to clean stormwater just because both are "water".

## 24. Floor and wash segregation

Greenhouse floor wash:
- do not send into D1 if it can contain dirt/detergent/oil/chemical.

Create:
- drain map;
- valve state;
- clean vs dirty cleaning SOP.

Chemical-room bund:
- no automatic floor drain to any water reuse line.

## 25. Treatment reject/backwash

BOM-014 filter backwash and BOM-032 treatment cleaning streams must be classified.

Could contain:
- solids;
- nutrients;
- sanitation chemical.

Do not automatically return filter wash to D1.

Mass balance includes:
- backwash volume;
- recovered water if separately validated;
- discharge.

## 26. End-of-cycle solution

At crop termination:

- slab/tank nutrient inventory measured;
- reusable fraction identified;
- concentrated/contaminated fraction held;
- no uncontrolled dumping.

Zero-liquid-discharge research in greenhouse soilless identifies end-of-crop residual nutrient solution and filter rinse water among practical causes of discharge.

Design these events from day one.

## 27. Drainage physical design

Requirements:

- gravity preferred from gutters;
- continuous slope;
- clean-outs;
- no stagnant traps;
- inspectable joints;
- chemical/fertilizer resistance;
- frost protection where external;
- access without removing crop;
- leak detection by mass balance;
- replaceable branches.

No buried uninspectable common header before compartment flow measurement if avoidable.

## 28. Storm overflow

Tank overflow paths:

- passive;
- visible/monitored;
- no return to clean tank;
- no flooding electrical/chemical areas.

Sizing:
- max inflow/treatment failure scenario;
- not only average drain.

## 29. Freeze protection

Carnia winter design:

- exterior drains sloped/drainable;
- buried below relevant frost exposure where required;
- no stagnant water in exposed small lines;
- heat trace only where justified;
- valves accessible.

## 30. Server model

Entities:

- drain_stream;
- crop_compartment;
- drain_batch;
- dirty_tank;
- treatment_batch;
- clean_tank;
- lab_sample;
- reuse_release;
- blend_batch;
- bleed_event;
- discharge_event.

Each reuse batch links:

`crop -> drain -> treatment -> analysis -> release -> new fertigation batch -> crop`.

## 31. Server control rules

Server may calculate:
- predicted drain;
- reuse ratio;
- blend;
- sodium accumulation;
- treatment schedule;
- tank capacity;
- lab due date.

Local PLC controls:
- pumps;
- valves;
- tank high-high;
- low-low;
- treatment permissive.

Server loss:
- reuse freezes at validated local mode;
- no unknown/HOLD tank is released.

## 32. Water-saving KPI

Measure separately:

`gross_reuse = V_reuse / V_drain`

`fresh_water_reduction = V_reuse / total_irrigation_demand`

`nutrient_recovery_i = kg_i_reused / kg_i_drain`

`bleed_fraction = V_bleed / V_drain`

Avoid marketing "90% recycled water" without denominator.

## 33. OPEX model

`OPEX_reuse = pumps + treatment_energy + filters + lab + cleaning + sensors + labor + bleed/disposal + replacement`

Benefit:

`BENEFIT = fresh_water_avoided + fertilizer_avoided + discharge_cost_avoided + resilience_value`

Decision:

`reuse if lifecycle benefit > lifecycle cost + agronomic risk premium`.

## 34. Failure modes

| Failure | Response |
|---|---|
| gutter leak | isolate branch/repair |
| collector blocked | overflow alarm + manual route |
| flow meter fail | use tank balance / HOLD automatic reuse |
| EC/pH sensor fail | lab/manual check + conservative mode |
| dirty tank high-high | stop inflow/route to approved emergency containment |
| wrong valve | position confirmation/interlock |
| treatment fail | HOLD |
| pathogen positive | isolate crop loop |
| Na/Cl high | reduce reuse/bleed |
| clean tank contaminated | HOLD + sanitize |
| stormwater cross-connect | isolate/correct |
| sewer unavailable | stop bleed / store within capacity |
| server down | PLC keeps last safe permissive |
| frost blockage | isolate/thaw/backup storage |

## 35. Commissioning

1. dye test each drain branch;
2. verify C1/C2 segregation;
3. slope/ponding inspection;
4. calibrated volume test;
5. tank high-high/overflow;
6. dirty/clean cross-contamination test;
7. HOLD valve test;
8. treatment permissive;
9. failed treatment -> no release;
10. end-line sample;
11. Na/Cl lab baseline;
12. mass balance 24 h;
13. mass balance 7 days;
14. simulated high EC;
15. simulated pathogen HOLD;
16. stormwater cross-connect inspection;
17. discharge route/title verified;
18. server genealogy.

## 36. Decision current

**BOM-033 baseline = collect and meter now; reuse capability staged.**

Phase R0:
- gutters and segregated drains;
- C1/C2 measurement;
- dirty/HOLD tank;
- sample points;
- no automatic reuse.

Phase R1:
- treatment validated;
- clean tank;
- partial blend/reuse;
- Na/Cl monitoring;
- controlled bleed.

Phase R2:
- dynamic reuse ratio;
- nutrient mass-balance optimization;
- high reuse if crop/source data prove it.

This avoids buying a complex closed-loop before we know actual drain chemistry.

## 37. Gate BOM-033

1. crop-card substrate/soilless decision;
2. C1/C2 irrigation volumes;
3. measured drain fraction;
4. drain chemistry;
5. Na/Cl source baseline;
6. pathogen risk;
7. drain routing geometry;
8. dirty/clean tank size;
9. treatment candidate;
10. discharge classification/authorization;
11. stormwater masterplan;
12. RFQ;
13. pilot one compartment;
14. 30–60 day mass balance;
15. agronomic sign-off before scaling.
