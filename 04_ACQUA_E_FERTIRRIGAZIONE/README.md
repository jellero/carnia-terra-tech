# Carnia TerraTech — Punto 04: Acqua e fertirrigazione

**Aggiornato:** 17 settembre 2026  
**Stato:** `ARCHITETTURA IN SVILUPPO / BOM-013…016 SVILUPPATE / SERBATOI, TRATTAMENTO, DRENAGGIO E ACCUMULO DA SVILUPPARE`.

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
- niente riuso automatico drenaggio prima di validazione tecnica/sanitaria/normativa.

## 2. Architettura working

Con accumulo atmosferico:

`tank 300 m³ -> presa/griglia grossolana -> pompe principali 1+1 -> idrociclone/filtrazione fine pressurizzata -> misura portata -> dosaggio A/B/acido -> miscelazione -> pH/EC/T -> collettore principale -> 6 comparti -> working 24 settori -> emettitori`

La sequenza precisa di pretrattamento, iniezione e misura verrà congelata con fonte reale, analisi acqua e ricette.

## 3. BOM-013 — distribuzione irrigua

C1/C2/C6:

- Netafim PCJ / LCNL / HCNL candidato;
- 2 l/h solo riferimento;
- microtubo + punto goccia/picchetto;
- PE cieco dimensionato.

C3–C5: dripline/ala da selezionare per letto, ciclo e meccanizzazione.

Working 24 settori. Ogni settore: isolamento, elettrovalvola NC, eventuale regolazione pressione, misura/presa pressione, flush e PLC.

Benchmark:

- PCJ standard 1.000 pz €261 + IVA;
- microtubo €38/200 m + IVA;
- punto goccia €95/1.000 + IVA;
- 1.000 punti completi ~€470–515 + IVA prima di dorsali/valvole/posa.

## 4. BOM-014 — filtrazione

Requisito working: **120 mesh / ~130 µm**.

Candidati/prezzi:

- Arkal Leader 2" €182 + IVA;
- Arkal Dual 2" €241 + IVA;
- Spin-Klin singolo €2.574 + IVA;
- Spin-Klin doppio €4.321 + IVA;
- ScreenGuard da €2.988 + IVA;
- idrociclone 2" €363 + IVA.

Con tank atmosferico la filtrazione fine automatica è normalmente sul lato pressurizzato delle pompe; il controlavaggio entra nel duty point della stazione.

## 5. BOM-015 — pompe principali 1+1

Baseline **2×100%**, una duty e una standby, un VFD per pompa.

Candidato di classe Grundfos CR 10-6:

- 10 m³/h nominali;
- 48,3 m nominali, 61,2 m max;
- 2,2 kW 3~;
- €1.946,78 IVA incl./cad retail IT osservato.

VFD Danfoss FC-51 2,2 kW: €895,30 + IVA/cad benchmark.

Alternativa OEM Grundfos Hydro Multi-E 2 CRE 10-3 U2: €12.185 listino 2026.

Taglia finale bloccata da Q/H/NPSH, filtri, controlavaggio e rete.

## 6. BOM-016 — fertirrigazione A/B/acido

Baseline tre canali indipendenti:

- A;
- B;
- acido;
- predisposizione quarto canale futuro.

Regola: **i concentrati A/B/acido non devono incontrarsi tra loro prima di essere sufficientemente diluiti nell'acqua di processo**.

Ogni canale prevede pompa dedicata, aspirazione, livello minimo, tubo dedicato, valvola iniezione/check, eventuale back-pressure/relief, isolamento, calibrazione e contenimento.

### Controllo

Interlock minimi:

- no flow = no dose;
- livello basso = stop canale;
- pH/EC sensor fault = stop automatico;
- EC high = stop A/B;
- pH hard limit = stop acido;
- leak/spill = stop;
- dose massima per ciclo/ora;
- watchdog locale.

Il controllo combina feed-forward da portata/ricetta con trim lento pH/EC dopo il tempo reale di miscelazione/trasporto.

### Pompe candidate

**Etatron eOne MF** — candidato prioritario:

- 4–20 mA;
- flow sensor;
- underload/overload;
- PTFE, PP/PVDF, ceramica;
- 100–250 Vac.

Prezzi + IVA:

- 6/7 €492;
- 10/12 €593;
- 15/5 €509;
- 20/7 €626;
- 30/5 €701.

Benchmark tre pompe:

- 2×20/7 + 6/7 = **€1.744 + IVA**;
- 2×30/5 + 6/7 = **€1.894 + IVA**.

**SEKO Tekna EVO APG 603 PVDF-T** — alternativa economica: ~€329 IVA incl. osservati, 4–20 mA/digitale, PVDF/PTFE, IP65; taglia da verificare.

**ProMinent gamma/X** — alternativa premium: famiglia ~1 ml/h–45 l/h; prezzo da RFQ.

### pH/EC

Candidato combinato Hanna HI98143-22:

- pH 0–14;
- EC 0–10 mS/cm;
- 4–20 mA isolati;
- €615 + IVA, sonde escluse.

Alternative separate:

- HI8614LN pH ~€670 + IVA;
- HI8936 EC da €327 + IVA, LCD ~€505;
- HI7638 EC probe ~€420–441 + IVA;
- process pH probe PVDF classe HI1006 ~€400 + IVA.

Verifica indipendente: Hanna HI9814 portatile pH/EC/TDS/T, €315 + IVA Italia.

## 7. Dimensionamento fertirrigazione

Per ogni canale:

`q_dose,max [l/h] = Q_water,max [m³/h] × recipe_stock [l/m³]`

Servono anche q minimo stabile, pressione iniezione, viscosità/densità, concentrazione stock e compatibilità materiali.

Se il fabbisogno supera stabilmente la classe ~20–45 l/h/canale, valutare pompe a membrana motorizzate/peristaltiche industriali, non molte piccole pompe in parallelo per default.

## 8. Misure/KPI

- m³ acqua;
- L A/B/acido;
- pH target/reale;
- EC target/reale;
- T soluzione;
- pressione;
- stato P1/P2 e filtri;
- kWh pompe;
- drift/calibrazioni sonde;
- allarmi dosing.

KPI futuri: L fertilizzante/m³, costo fertilizzante/m³, kWh/m³ e costo nutrienti/kg vendibile.

## 9. Failure modes principali

- pompa irrigazione o dosatrice guasta;
- VFD guasto;
- cavitazione;
- filtro intasato;
- dosaggio senza flusso;
- sifonamento;
- linea chimica che pesca aria;
- stock esaurito;
- pH/EC drift;
- miscelazione insufficiente;
- ricetta errata;
- scambio A/B;
- perdita/sversamento;
- PLC/I/O/bus guasto.

Fallback: failover P1/P2, stop dosaggio, acqua sola o ricetta degradata solo se agronomicamente ammessa, misura pH/EC manuale, isolamento del canale guasto.

## 10. Package sviluppati

- `IRRIGATION_DISTRIBUTION.md` + RFQ;
- `FILTRATION_ARCHITECTURE.md` + RFQ;
- `PUMP_STATION_ARCHITECTURE.md` + RFQ;
- `FERTIGATION_DOSING.md`;
- `RFQ_FERTIGATION_DOSING.md`;
- BOM-013…016 in `19_BOM_PRODOTTI_FORNITORI/`;
- fonti dedicate in `22_FONTI_NORME_PREVENTIVI/`.

## 11. Gate punto 04

Restano necessari:

- layout/portate C1–C6;
- fonte/analisi acqua e alcalinità;
- quote tank/tech barn;
- Q/H/NPSH pompe;
- filtrazione finale/controlavaggio;
- ricette e stock A/B;
- acido/concentrazione;
- taglie pompe dosatrici;
- **BOM-017 serbatoi fertilizzanti e contenimento**;
- trattamento/disinfezione se necessario;
- drenaggio/riuso;
- accumulo acqua 300 m³;
- backup elettrico;
- RFQ e commissioning.