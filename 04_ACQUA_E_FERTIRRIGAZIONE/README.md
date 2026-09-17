# Carnia TerraTech — Punto 04: Acqua e fertirrigazione

**Aggiornato:** 17 settembre 2026  
**Stato:** `ARCHITETTURA IN SVILUPPO / BOM-013…017 SVILUPPATE / TRATTAMENTO, DRENAGGIO E ACCUMULO DA SVILUPPARE`.

## 1. Obiettivo

Distribuire acqua e soluzione nutritiva in modo misurabile, uniforme, manutenibile e indipendente per comparto/settore.

Principi:

- 6 comparti indipendenti;
- working 4 settori per comparto = 24 settori, da confermare;
- logica vitale in PLC locale;
- pressione, portata, pH, EC, volumi e stati misurabili;
- filtrazione scelta sulla qualità reale dell'acqua;
- pompe principali 1+1 reali;
- fertirrigazione A/B/acido modulare e non black-box;
- stock chimici separati, misurati e contenuti secondariamente;
- niente riuso automatico drenaggio prima di validazione tecnica/sanitaria/normativa.

## 2. Architettura working

Con accumulo atmosferico:

`tank acqua 300 m³ -> presa/griglia grossolana -> pompe principali 1+1 -> idrociclone/filtrazione fine pressurizzata -> misura portata -> dosaggio A/B/acido -> miscelazione -> pH/EC/T -> collettore principale -> 6 comparti -> working 24 settori -> emettitori`

Stock chimici:

`tank A/B/acido dedicati -> livello continuo + low-low -> pompe dosatrici BOM-016`.

La sequenza precisa viene congelata con fonte reale, analisi acqua, ricette e SDS.

## 3. BOM-013 — distribuzione irrigua

C1/C2/C6: Netafim PCJ/LCNL/HCNL candidato; 2 l/h solo riferimento. C3–C5: dripline/ala da selezionare per letto, ciclo e meccanizzazione.

Working 24 settori. Ogni settore: isolamento, elettrovalvola NC, eventuale regolazione pressione, misura/presa pressione, flush e PLC.

Benchmark 1.000 punti completi: **~€470–515 + IVA** prima di dorsali/valvole/posa.

## 4. BOM-014 — filtrazione

Requisito working **120 mesh / ~130 µm**.

Candidati/prezzi:

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

VFD Danfoss FC-51 2,2 kW: **€895,30 + IVA/cad** benchmark. Taglia finale bloccata da Q/H/NPSH, filtri, controlavaggio e rete.

## 6. BOM-016 — fertirrigazione A/B/acido

Tre canali indipendenti più predisposizione quarto.

Regola: **i concentrati A/B/acido non devono incontrarsi prima di essere sufficientemente diluiti nell'acqua di processo**.

Interlock minimi: no flow=no dose, low level=stop, sensor fault=stop automatico, EC high=stop A/B, limite pH=stop acido, spill=stop, dose max ciclo/ora.

Candidato prioritario Etatron eOne MF. Benchmark sole pompe:

- 2×20/7 + 6/7 = **€1.744 + IVA**;
- 2×30/5 + 6/7 = **€1.894 + IVA**.

Hanna HI98143-22 pH+EC 4–20 mA: **€615 + IVA**, sonde escluse. Verifica indipendente Hanna HI9814: **€315 + IVA**.

## 7. BOM-017 — serbatoi fertilizzanti e contenimento

Tre stock iniziali separati: A, B, acido. Scenario dimensionale per RFQ, non selezione:

- A 500 L;
- B 500 L;
- acido 200 L.

Il volume vero deriva da:

`V_operativo = consumo massimo giornaliero × giorni autonomia`

con margine per freeboard, fondo non pescabile, agitazione e riempimento.

### Serbatoi benchmark

- Pack Services PFF-CH0500 PE chimici 500 L: **€188,73 + IVA**;
- Pack Services PFF-CH0200 PE chimici 200 L: **€131,94 + IVA**;
- ELBI CHL-500 500 L: **€219 IVA incl.**;
- stazione PE 200 L con vasca di contenimento: **€202,77 + IVA**.

Scenario 500/500/200 con PFF-CH: **€509,40 + IVA di soli serbatoi**.

### Contenimento

Baseline prudente:

- contenimento singolo almeno pari al volume nominale del relativo serbatoio;
- acido in bacino dedicato;
- A+B in bacino comune solo se compatibilità dimostrata.

Benchmark:

- DENIOS PE 600 L: **€560 + IVA**;
- vasca PE 500 L Gaesco: **€641,72 IVA incl.**.

Le norme italiane che usano criteri 30%/1/3 + serbatoio maggiore riguardano specifici casi di rifiuti pericolosi e sono solo benchmark: l'obbligo applicabile ai fertilizzanti va verificato su sostanza/SDS/sito.

### Livello

Ogni tank: continuo + low-low indipendente + high/high-high.

Benchmark:

- Novus TL400 laser 4–20 mA: da **€130** pubblicati, IVA da confermare;
- WIKA ILT-C01 radar: **€390,09 + IVA**;
- Elesa HFLT-E/HFL-E limite: da **€39,18 / €60,41 + IVA**.

### Agitazione

A/B: agitatore o ricircolo solo se richiesto da solubilità/stabilità. Acido: nessun agitatore di default.

Benchmark professionale 0,37 kW AISI316 fino a 500 L: **€1.835 + IVA**, usato solo come riferimento alto.

### Sicurezza/operatività

- riempimenti dedicati e identificati;
- high-level stop;
- spill sensor;
- bacini con drenaggio controllato normalmente chiuso;
- sfiati dimensionati;
- per acido, sfiato convogliato/scrubber solo se SDS lo richiede;
- pavimento resistente alla chimica reale;
- niente travaso ordinario con secchi/imbuti;
- SDS, etichettatura, spill kit e DPI;
- lavaocchi/doccia da valutazione rischio con punto 12.

## 8. Misure/KPI

- m³ acqua;
- L A/B/acido;
- livello e autonomia residua stock;
- pH/EC/T;
- pressione e portata;
- kWh pompe;
- drift/calibrazioni sonde;
- numero sversamenti/allarmi;
- consumo nutrienti/m³ e futuro costo nutrienti/kg vendibile.

## 9. Failure modes principali

- pompa irrigazione/dosatrice guasta;
- VFD guasto;
- filtro intasato;
- dosaggio senza flusso;
- sensore pH/EC/livello guasto;
- stock esaurito;
- serbatoio/passaparete perde;
- bacino insufficiente/pieno;
- travaso nel tank sbagliato;
- contaminazione A/B/acido;
- sfiato ostruito;
- agitatore guasto;
- PLC/I/O/bus guasto.

Fallback: failover P1/P2, stop dosaggio, isolamento chimico, misura manuale pH/EC, recupero sversamento dal bacino e procedura degradata solo se sicura/agronomicamente ammessa.

## 10. Package sviluppati

- `IRRIGATION_DISTRIBUTION.md` + RFQ;
- `FILTRATION_ARCHITECTURE.md` + RFQ;
- `PUMP_STATION_ARCHITECTURE.md` + RFQ;
- `FERTIGATION_DOSING.md` + RFQ;
- `TANKS_CONTAINMENT_ARCHITECTURE.md` + `RFQ_FERTILIZER_TANKS_CONTAINMENT.md`;
- BOM-013…017 in `19_BOM_PRODOTTI_FORNITORI/`;
- fonti dedicate in `22_FONTI_NORME_PREVENTIVI/`.

## 11. Gate punto 04

Restano necessari:

- layout/portate C1–C6;
- fonte/analisi acqua + alcalinità;
- Q/H/NPSH pompe;
- filtrazione/controlavaggio finali;
- ricette e concentrazioni stock;
- acido reale/SDS/compatibilità;
- volumi A/B/acido e autonomia;
- agitazione/ricircolo;
- layout locale chimici e contenimento applicabile;
- trattamento/disinfezione se necessario;
- drenaggio/riuso;
- **BOM-018 accumulo acqua 300 m³**;
- backup elettrico;
- RFQ e commissioning.
