# Carnia TerraTech — Punto 04: Acqua e fertirrigazione

**Aggiornato:** 18 settembre 2026  
**Stato:** `ARCHITETTURA STRUTTURATA / BOM-013…018 + BOM-032 + BOM-033 SVILUPPATE / RIUSO R1 BLOCCATO DA PILOT, Na-Cl, FITOPATOGENI E CLASSIFICAZIONE SCARICHI`.

## 1. Obiettivo

Distribuire acqua e soluzione nutritiva in modo misurabile, uniforme, manutenibile e indipendente per comparto/settore.

Principi:

- 6 comparti indipendenti;
- working 4 settori per comparto = 24 settori, da confermare;
- logica vitale in PLC locale;
- pressione, portata, pH, EC, livelli, volumi e stati misurabili;
- filtrazione scelta sulla qualità reale dell'acqua;
- pompe principali 1+1 reali;
- fertirrigazione A/B/acido modulare e non black-box;
- stock chimici separati, misurati e contenuti secondariamente;
- accumulo acqua manutenibile con ridondanza;
- niente riuso automatico drenaggio prima di validazione tecnica, sanitaria e normativa.

## 2. Architettura working

Con accumulo atmosferico:

`captazione/fonte -> 2×150 m³ working -> presa/griglia grossolana -> pompe principali 1+1 -> idrociclone/filtrazione fine pressurizzata -> UV validated barrier BOM-032 -> misura portata -> dosaggio A/B/acido -> miscelazione -> pH/EC/T -> collettore principale -> 6 comparti -> working 24 settori -> emettitori`

Stock chimici:

`tank A/B/acido dedicati -> livello continuo + low-low -> pompe dosatrici BOM-016`.

La sequenza viene congelata con fonte reale, analisi acqua, ricette, SDS e layout.

## 3. BOM-013 — distribuzione irrigua

C1/C2/C6: Netafim PCJ/LCNL/HCNL candidato; 2 l/h solo riferimento. C3–C5: dripline/ala da selezionare per letto, ciclo e meccanizzazione.

Working 24 settori. Ogni settore: isolamento, elettrovalvola NC, eventuale regolazione pressione, misura/presa pressione, flush e PLC.

Benchmark 1.000 punti completi: **~€470–515 + IVA** prima di dorsali/valvole/posa.

## 4. BOM-014 — filtrazione

Requisito working **120 mesh / ~130 µm**.

Candidati:

- Arkal Leader 2" €182 + IVA;
- Arkal Dual 2" €241 + IVA;
- Spin-Klin singolo €2.574 + IVA;
- Spin-Klin doppio €4.321 + IVA;
- ScreenGuard da €2.988 + IVA;
- idrociclone 2" €363 + IVA.

Con tank atmosferico la filtrazione fine automatica è normalmente sul lato pressurizzato delle pompe; il controlavaggio entra nel duty point.

## 5. BOM-015 — pompe principali 1+1

Baseline **2×100%**, una duty e una standby, un VFD per pompa.

Candidato di classe Grundfos CR 10-6: 10 m³/h nominali, 48,3 m nominali, 2,2 kW 3~, **€1.946,78 IVA incl./cad** retail osservato.

VFD Danfoss FC-51 2,2 kW: **€895,30 + IVA/cad** benchmark. Taglia finale da Q/H/NPSH, filtri, controlavaggio e rete.

## 6. BOM-016 — fertirrigazione A/B/acido

Tre canali indipendenti più predisposizione quarto.

Regola: **i concentrati A/B/acido non devono incontrarsi prima di essere sufficientemente diluiti nell'acqua di processo**.

Interlock minimi: no-flow=no-dose, low-level=stop, sensor fault=stop automatico, EC high=stop A/B, limite pH=stop acido, spill=stop, dose massima ciclo/ora.

Etatron eOne MF candidato prioritario. Benchmark sole pompe:

- 2×20/7 + 6/7 = **€1.744 + IVA**;
- 2×30/5 + 6/7 = **€1.894 + IVA**.

Hanna HI98143-22 pH+EC 4–20 mA: **€615 + IVA**, sonde escluse. Verifica indipendente Hanna HI9814: **€315 + IVA**.

## 7. BOM-017 — serbatoi fertilizzanti e contenimento

Scenario RFQ, non ordine: A 500 L, B 500 L, acido 200 L. Volume vero da consumo massimo × autonomia, con freeboard/fondo non pescabile.

Benchmark:

- PE chimici 500 L: **€188,73 + IVA**;
- PE chimici 200 L: **€131,94 + IVA**;
- scenario 500/500/200: **€509,40 + IVA di soli serbatoi**;
- DENIOS PE 600 L contenimento: **€560 + IVA**;
- WIKA ILT-C01 radar: **€390,09 + IVA**.

Acido in contenimento dedicato; A+B insieme solo con compatibilità documentata. Agitazione A/B solo se necessaria.

## 8. BOM-018 — accumulo acqua 300 m³

Baseline: **2×150 m³ working**, indipendenti e isolabili, con predisposizione a 400–500 m³.

Prima dell'ordine definire se il requisito è 300 m³ **nominali** o **utili**.

### Autonomia

Con working peak 30–35 m³/giorno:

- 300 m³ = **8,6–10 giorni teorici**;
- 14 giorni richiederebbero 420–490 m³;
- 15 giorni 450–525 m³.

Quindi 300 m³ è un primo stadio, non una garanzia di autonomia prolungata.

### Captazione pioggia

Con 4.200 m² nominali:

- 1 mm pioggia = 4,2 m³ teorici;
- 300 m³ = 71,4 mm teorici;
- ~84 mm con resa complessiva 85%.

Overflow dimensionato dalla pioggia di progetto RainMap e dalla superficie captata, non dal volume tank.

### Scenari

- S1 2×150 m³ rigidi con liner — baseline;
- S2 3×100 m³ — maggiore modularità;
- S3 1×300 m³ — CAPEX semplice ma single point of failure;
- S4 2×150 m³ bladder — CAPEX basso/footprint alto;
- S5 GRP/modulare — da RFQ.

### Benchmark

- Labaronne Citaf bladder 150 m³: **€4.270 + IVA/cad**, quindi €8.540 + IVA per due, solo hardware;
- RL Distrib bladder 150 m³: **€3.799 + IVA/cad** benchmark;
- steel 200 m³: **€6.630 + IVA**, trasporto/installazione esclusi;
- ABEKO ~200 m³ utili: **€7.807 + IVA**, cover telo +€725;
- Tanks Direct UK 150.000 L: **£4.650 ex VAT**, benchmark estero.

Nota critica: un prodotto ABEKO denominato “150 m³” pubblica **112 m³ utili**. Per l'ordine vale sempre il volume utile dichiarato.

### Requisiti tank

Ogni unità: ingresso isolabile, calming inlet, overflow passivo, copertura anti-alga, aspirazione sopra fondo, scarico fondo, campionamento, sfiato, radar livello, low-low indipendente, high-high, accesso/ispezione e valvole isolate.

Cross-connect normalmente isolabile; contaminazione/perdita di un tank non deve propagarsi automaticamente all'altro.

Fondazioni da geotecnica + manuale OEM. Un cilindro Ø9,14 m con 150 m³ esercita circa **22,4 kPa** di solo carico medio acqua sul footprint, prima di struttura e carichi locali.

UNI EN 16941-1:2024 è riferimento corrente per sistemi di uso acqua piovana non potabile, oltre agli obblighi locali/nazionali.

## 9. BOM-032 — trattamento e disinfezione

Architettura multi-classe:

- **W0** raw/source;
- **W1** irrigazione root-zone;
- **W2** fogging/aerosol;
- **W3** potable/food-process/handwash;
- **W4** future reclaimed drainage.

Baseline W1:

`tank -> pompe -> BOM-014 filtrazione -> UV -> fertirrigazione`.

Working decision:

- UV come barriera microbiologica primaria **se il risk assessment richiede disinfezione**;
- UV dopo filtrazione e prima dei fertilizzanti;
- sizing da Q + worst-case UVT254 + dose validata, non da portata catalogo;
- due-train architecture U1/U2 preferita rispetto a blind bypass;
- bypass manutenzione normalmente chiuso e monitorato;
- stessa linea trattamento predisposta per recirculation selettiva tank A/tank B;
- nessuna equalizzazione automatica di un tank in HOLD;
- UV non rimuove biofilm esistente: servono design flushable, cleaning e sanitation SOP;
- cloro/H2O2/PAA **non** continuous baseline: soltanto se dati/biofilm/processo lo giustificano;
- acid e hypochlorite fisicamente segregati;
- W2 fogging trattata come classe separata;
- W3 separata e conforme alla disciplina potabile quando applicabile;
- W4 rimandata a BOM-033.

Benchmark tecnici:

- ProMinent DULCODES LP 1×80: 8,8 m³/h general / 6,4 m³/h nella tabella certified a UVT 98%/cm;
- DULCODES LP 1×230: 35 m³/h general / 20,7 m³/h certified reference;
- connected load 110 W / 310 W rispettivamente;
- sistemi retail/pool 10 m³/h osservati ~€1,8–3,6k: **solo lower-bound non comparabile**, non candidati process;
- process UV installato = RFQ;
- ARPA FVG sampling reference: €26 per campione acque superficiali/sotterranee, analisi escluse.

Hard safety:
- acid + hypochlorite can release chlorine gas;
- no common concentrated-chemical suction/storage/drain path.

Documenti:

- `WATER_TREATMENT_DISINFECTION_ARCHITECTURE.md`;
- `RFQ_WATER_TREATMENT_DISINFECTION.md`;
- `19_BOM_PRODOTTI_FORNITORI/ACQUA_TRATTAMENTO_DISINFEZIONE.md`;
- `22_FONTI_NORME_PREVENTIVI/ACQUA_TRATTAMENTO_DISINFEZIONE_SOURCES.md`.

## 10. BOM-033 — drenaggio, raccolta e riuso

Decisione working:

- **R0 obbligatoria:** raccogliere, segregare, misurare e mettere in HOLD;
- **R1 successiva:** trattamento + clean tank + partial reuse dopo pilot 30–60 giorni;
- **R2:** reuse ratio dinamico solo dopo dati reali.

Flussi separati:

- D0 roof rainwater -> BOM-018;
- D1 crop drainage C1/C2 -> candidato riuso;
- D2 abnormal/flush -> HOLD;
- D3 floor/wash -> rete separata;
- D4 stormwater -> masterplan/PRTA;
- D5 BOM-029 process wastewater -> separata;
- D6 domestic -> separata.

C1 e C2 restano misurabili separatamente fino alla classificazione.

KPI:

`drain_fraction = V_drain / V_irrigated`

`gross_reuse = V_reuse / V_drain`

`fresh_water_reduction = V_reuse / V_total_irrigation`

Guardrail:
- EC non basta: monitorare Na e Cl;
- no untreated common drain return;
- positive pathogen -> HOLD/isolation;
- bleed sempre misurato e con destinazione autorizzata;
- no discharge to soil by default;
- stormwater e nutrient drain mai miscelati.

Tank:
- 5/10 m³ sono solo scenari RFQ;
- size finale da peak drain tra treatment windows + reserve + freeboard.

Benchmark:
- PE external 5.000 L ~€1.159 shell-only lower bound;
- FVG 2026 drainage gravel €38,50/m³;
- category 50 Prezzario FVG 2026 per pipes/manholes/drains;
- EC/pH instrumentation class già benchmarked in BOM-016 ~€615 + IVA excluding probes.

Regulatory gate:
- D.Lgs. 152/2006 classification;
- SUAP/AUA where applicable;
- FVG PRTA;
- exact recipient/sewer manager/body;
- sample point + flow meter on final discharge if required.

Documenti:

- `DRAINAGE_REUSE_ARCHITECTURE.md`;
- `RFQ_DRAINAGE_REUSE.md`;
- `19_BOM_PRODOTTI_FORNITORI/ACQUA_DRENAGGIO_RIUSO.md`;
- `22_FONTI_NORME_PREVENTIVI/ACQUA_DRENAGGIO_RIUSO_SOURCES.md`.

## 11. Misure/KPI

- m³ disponibili e autonomia residua;
- m³ captati da pioggia / da fonte;
- m³ irrigati;
- perdite/overflow;
- sedimenti e qualità acqua;
- L A/B/acido;
- pH/EC/T;
- pressione e portata;
- kWh pompe;
- drift/calibrazioni;
- allarmi e ore manutenzione.

## 12. Failure modes principali

- liner/tank perde;
- overflow ostruito/insufficiente;
- fondazione fuori piano;
- contaminazione tank;
- crescita algale/sedimenti;
- low-low/radar guasto;
- cross-connect aperto impropriamente;
- pompa o VFD guasto;
- filtro intasato;
- dosaggio senza flusso;
- stock chimico finito/perdita;
- PLC/I/O/bus guasto.

Fallback: isolamento tank/ramo, esercizio su unità superstite, failover P1/P2, stop dosaggio, fonte esterna autorizzata e modalità irrigazione prioritaria/degradata.

## 13. Package sviluppati

- `IRRIGATION_DISTRIBUTION.md` + RFQ;
- `FILTRATION_ARCHITECTURE.md` + RFQ;
- `PUMP_STATION_ARCHITECTURE.md` + RFQ;
- `FERTIGATION_DOSING.md` + RFQ;
- `TANKS_CONTAINMENT_ARCHITECTURE.md` + RFQ;
- `WATER_STORAGE_ARCHITECTURE.md` + `RFQ_WATER_STORAGE.md`;
- `WATER_TREATMENT_DISINFECTION_ARCHITECTURE.md` + `RFQ_WATER_TREATMENT_DISINFECTION.md`;
- `DRAINAGE_REUSE_ARCHITECTURE.md` + `RFQ_DRAINAGE_REUSE.md`;
- BOM-013…018 + BOM-032 + BOM-033 in `19_BOM_PRODOTTI_FORNITORI/`;
- fonti dedicate in `22_FONTI_NORME_PREVENTIVI/`.

## 14. Gate punto 04

Restano necessari:

- layout/portate C1–C6;
- fonte reale e analisi acqua/alcalinità;
- bilancio idrico mensile e autonomia target;
- lotto/geotecnica/RainMap;
- decisione 300 m³ nominali vs utili;
- RFQ tank/fondazioni/trasporto;
- Q/H/NPSH pompe;
- filtrazione/controlavaggio finali;
- ricette/concentrazioni/SDS;
- validazione BOM-032: UVT/microbiologia/Q/UV redundancy e sampling plan;
- pilot BOM-033 30–60 giorni con volume/EC/Na/Cl e pathogen strategy;
- classification/discharge route SUAP/AUA/PRTA;
- dirty/clean tank sizing e treatment proof;
- BESS/backup elettrico;
- commissioning completo.
