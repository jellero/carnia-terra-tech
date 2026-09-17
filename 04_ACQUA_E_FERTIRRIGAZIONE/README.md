# Carnia TerraTech — Punto 04: Acqua e fertirrigazione

**Aggiornato:** 17 settembre 2026  
**Stato:** `ARCHITETTURA IN SVILUPPO / BOM-013 DISTRIBUZIONE, BOM-014 FILTRAZIONE E BOM-015 POMPE 1+1 SVILUPPATE / DOSAGGIO E ACCUMULO DA SVILUPPARE`.

## 1. Obiettivo

Il sistema deve distribuire acqua e soluzione nutritiva in modo misurabile, uniforme, manutenibile e indipendente per comparto/settore.

Principi:

- 6 comparti indipendenti;
- working 4 settori per comparto = 24 settori, da confermare con layout e crop card;
- ogni settore isolabile e comandabile localmente;
- nessuna portata fissata senza numero reale di emettitori/linee;
- niente riuso automatico del drenaggio prima di validazione tecnica, sanitaria e normativa;
- logica vitale in PLC locale;
- misure di pressione, portata e volume per diagnosticare intasamenti, perdite e mancata erogazione;
- filtrazione scelta sulla qualità reale dell'acqua e non soltanto sulla mesh;
- stazione pompe in ridondanza reale, non semplice parallelo senza capacità degradata dichiarata.

## 2. Architettura working aggiornata

La sequenza dipende dalla fonte.

### Accumulo atmosferico

Baseline da verificare:

`tank 300 m³ -> presa/griglia grossolana -> pompe principali 1+1 -> idrociclone/filtrazione fine pressurizzata -> fertirrigazione -> collettore principale -> 6 comparti -> working 24 settori -> emettitori`

### Fonte già pressurizzata

Pozzo/rete con propria pompa può consentire una sequenza diversa, purché siano garantiti pressione di filtrazione/controlavaggio, NPSH e separazione delle funzioni.

**Nota:** il working precedente con filtrazione fine automatica a monte delle pompe non è valido per default con tank atmosferico: Spin-Klin/ScreenGuard richiedono pressione per controlavaggio.

## 3. BOM-013 — distribuzione irrigua

C1/C2/C6:

- candidato Netafim PCJ / PCJ PRO;
- preferenza LCNL/HCNL anti-drenaggio per irrigazione pulsata;
- 2 l/h è solo riferimento iniziale;
- microtubo 3/5 mm + punto goccia/picchetto;
- PE cieco dimensionato su Q/perdite.

C3–C5: confrontare dripline autocompensante permanente, ala leggera/monostagionale e configurazioni compatibili con letti e futura meccanizzazione.

Working: 24 settori, 4 per comparto. Ogni settore: isolamento, elettrovalvola NC, eventuale regolazione pressione, misura/presa pressione, flush e PLC.

Benchmark:

- PCJ standard 2 l/h: €261 + IVA / 1.000;
- microtubo PE 5 mm: €38 + IVA / 200 m;
- punto goccia: €95 + IVA / 1.000;
- asta guidata: €140 + IVA / 1.000;
- 1.000 punti standard: ~€470–515 + IVA prima di dorsali/valvole/posa;
- Bermad 1" 24 VAC: ~€23,15–28,53 IVA incl.

## 4. BOM-014 — filtrazione

Requisito emettitori working: **120 mesh / circa 130 µm**.

Scelta con analisi acqua:

- acqua buona: manuale/automatico + sicurezza;
- sabbia: idrociclone + filtro principale + sicurezza;
- acqua superficiale/organico: dischi automatici o media filtration + secondario;
- sali/durezza/Fe-Mn disciolti: trattamento separato.

Benchmark:

- Arkal Leader 2" manuale €182 + IVA;
- Arkal Dual 2" manuale €241 + IVA, 25 m³/h;
- Spin-Klin singolo €2.574 + IVA, 20 m³/h nominali / 15 media qualità;
- Spin-Klin doppio €4.321 + IVA, 40 / 30 m³/h;
- ScreenGuard 2" da €2.988 + IVA, 25 m³/h;
- idrociclone 2" €363 + IVA, 15–25 m³/h.

Controlavaggio entra nel duty point pompe: Q, P, durata e contemporaneità vanno calcolati.

## 5. BOM-015 — pompe principali 1+1

Baseline: **2×100%**, una duty e una standby.

Requisiti:

- aspirazione allagata preferita dal tank;
- calcolo NPSHa/NPSHr sul livello minimo;
- una valvola isolamento per lato di ogni pompa;
- non ritorno per ramo;
- 1 VFD per pompa;
- sensore pressione + ridondanza/pressostato;
- low-level hardwired/local interlock;
- alternanza lead/standby;
- failover automatico;
- manual override;
- energia e portata misurabili;
- cloud/server non vitali.

### Candidati/benchmark

Grundfos CR 10-6:

- 10 m³/h nominali;
- 48,3 m nominali, 61,2 m max;
- 2,2 kW 3~;
- prezzo retail Italia osservato **€1.946,78 IVA incl./cad**;
- 2 pompe = ~€3.893,56 IVA incl., solo corpi pompa.

Danfoss FC-51 2,2 kW 380–480 V:

- **€895,30 + IVA/cad** benchmark RS Italia;
- 2 VFD = ~€1.790,60 + IVA.

Gruppo OEM integrato benchmark Grundfos Hydro Multi-E:

- 2 CRE 10-3 U2: €12.185 listino 2026;
- 2 CRE 10-5 U2: €13.323 listino 2026;
- IVA/sconto/configurazione da confermare.

Sensori:

- WIKA A-10: da €133,95 + IVA; 0–10 bar RS ~€151,36 + IVA;
- Danfoss MBS 3000 0–10 bar 4–20 mA ~€195,44 + IVA.

Vaso autoclave 50–100 l: condizionale per transitori/anti-cycling, non accumulo di processo. Zilmet Ultra-Pro 100 l ~€475 benchmark listino osservato.

Nessuno di questi candidati è selezionato finché non esiste Q/H reale.

## 6. Duty point e scenari

Calcolare:

`Qdesign = max(Q irrigazione simultanea, Q flush, Q irrigazione + Q backwash se simultanei)`

`Hdesign = Hstatica + perdite aspirazione + filtri + fertirrigazione + rete + pressione residua settore`

Verificare normale, controlavaggio, flush, modalità degradata ed emergenza.

## 7. Misure minime

- portata totale;
- pressione mandata pompe;
- pressione monte/valle filtrazione;
- Δp filtro;
- portata per comparto preferenziale;
- livello tank;
- stato P1/P2 e VFD;
- kWh per pompa;
- allarmi pressione/portata.

KPI operativo futuro: `kWh pompe / m³ erogato`.

## 8. Failure modes principali

- pompa duty guasta;
- standby indisponibile;
- VFD guasto;
- sensore pressione guasto;
- cavitazione/NPSH insufficiente;
- livello tank basso;
- filtro/strainer ostruito;
- non ritorno bloccato;
- perdita tenuta;
- sovrapressione/dead-head;
- controlavaggio non sostenibile;
- elettrovalvola/settore guasto;
- perdita PLC/bus/rete.

Fallback: failover automatico, manual override locale, modalità irrigazione prioritaria/degradata e ricambi standardizzati.

## 9. Package sviluppati

- `IRRIGATION_DISTRIBUTION.md` + RFQ;
- `FILTRATION_ARCHITECTURE.md` + RFQ;
- `PUMP_STATION_ARCHITECTURE.md`;
- `RFQ_MAIN_IRRIGATION_PUMPS.md`;
- `19_BOM_PRODOTTI_FORNITORI/ACQUA_IRRIGAZIONE_DISTRIBUZIONE.md` — BOM-013;
- `19_BOM_PRODOTTI_FORNITORI/ACQUA_FILTRAZIONE.md` — BOM-014;
- `19_BOM_PRODOTTI_FORNITORI/ACQUA_POMPE_PRINCIPALI.md` — BOM-015;
- fonti dedicate in `22_FONTI_NORME_PREVENTIVI/`.

## 10. Gate punto 04

Restano necessari:

- layout C1–C6 e portate;
- fonte/analisi acqua;
- quote tank/tech barn;
- Q/H e NPSH pompe;
- filtrazione finale e controlavaggio;
- pompe dosatrici e miscelazione A/B/acido;
- serbatoi fertilizzanti;
- trattamento/disinfezione se necessario;
- drenaggio/riuso;
- accumulo acqua 300 m³;
- backup elettrico coerente;
- RFQ comparabili e commissioning.