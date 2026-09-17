# Carnia TerraTech — Project Index

**Ruolo:** indice operativo e mappa di copertura del progetto.  
**Aggiornato:** 17 settembre 2026.

## 1. Scopo

Il repository deve permettere di progettare l'azienda senza lasciare aree scoperte. Ogni decisione deve essere collegata a costi, manutenzione, sicurezza, dipendenze, crescita e qualità della vita.

## 2. Struttura target

- `00_VISIONE_E_PRINCIPI/` — missione, KPI, guardrail e decision gates;
- `01_MASTERPLAN_E_TERRENO/` — lotto, vincoli, accessi, drenaggi, espansioni;
- `02_AGRONOMIA/` — colture, calendari, rese, vite, luppolo, siepi, outdoor;
- `03_SERRA/` — struttura, comparti, coperture, aperture, schermi, HAF, fogging, supporti coltura, drenaggi, porte, recupero pioggia e cantiere;
- `04_ACQUA_E_FERTIRRIGAZIONE/` — fonte, accumulo, filtri, pompe, dosaggio, distribuzione, drenaggio;
- `05_TERMICO_E_CLIMA/` — carico termico, PDC, accumulo, distribuzione, boost, deumidificazione, emergenza;
- `06_ENERGIA_ELETTRICA_FV/` — FV, inverter, rete, UPS, generatore, EMS;
- `07_AUTOMAZIONE_DATI_AI/` — PLC, I/O, sensori, rete, edge, vision, cybersecurity e R&D robotica/laser;
- `08_MACCHINE_E_LOGISTICA/` — AMR, sollevatore, piattaforme, raccolta, carrelli;
- `09_TECH_BARN_E_POST_RACCOLTA/` — celle, confezionamento, officina, magazzini e centro trasformazione conto terzi;
- `10_BENESSERE_FATTORIA_E_SERVIZI/` — pergolato, verde, fattoria didattica, robot di servizio, spaccio 24/7;
- `11_VERMICOMPOST_E_CICLI_MATERIA/`;
- `12_SICUREZZA_E_CONTINUITA/`;
- `13_MANUTENZIONE_E_RICAMBI/`;
- `14_ORGANIZZAZIONE_DEL_LAVORO/`;
- `15_MERCATO_E_VENDITE/`;
- `16_SOCIETA_FINANZA_E_CONTRIBUTI/`;
- `17_SOSTENIBILITA_PERSONALE_E_LANCIO/`;
- `18_CAPEX_OPEX_CASHFLOW/`;
- `19_BOM_PRODOTTI_FORNITORI/`;
- `20_CANTIERE_E_CRONOPROGRAMMA/`;
- `21_RISCHI_DECISIONI_OPEN_POINTS/`;
- `22_FONTI_NORME_PREVENTIVI/`.

## 3. Stato punto 00 — Visione e principi

**Stato: RAFFINATO / BASE DI GOVERNO DEL PROGETTO.**

## 4. Stato punto 01 — Terreno e masterplan

**Stato: RAFFINATO / IN ATTESA DI LOTTO REALE.**

## 5. Stato punto 02 — Agronomia

**Stato: RAFFINATO / PORTAFOGLIO E METODO DEFINITI / DATI COLTURALI DA VALIDARE.**

Working portfolio: C1 pomodoro premium; C2 peperone; C3 lattuga; C4 lattuga/leaf flessibile; C5 baby leaf/rucola/spinacio; C6 basilico + vivaio + prove.

## 6. Stato punto 03 — Serra

**Stato: RAFFINATO COME ARCHITETTURA / BOM-001…008 STRUTTURATE / VALIDAZIONE BLOCCATA DA DATI REALI.**

Matrice: `03_SERRA/POINT_03_CLOSURE_MATRIX.md`.

## 7. Stato punto 04 — Acqua e fertirrigazione

**Stato: ARCHITETTURA IN SVILUPPO / BOM-013…017 SVILUPPATE / TRATTAMENTO, DRENAGGIO E ACCUMULO DA SVILUPPARE.**

Documenti principali:

- `04_ACQUA_E_FERTIRRIGAZIONE/README.md`;
- `IRRIGATION_DISTRIBUTION.md` + RFQ;
- `FILTRATION_ARCHITECTURE.md` + RFQ;
- `PUMP_STATION_ARCHITECTURE.md` + RFQ;
- `FERTIGATION_DOSING.md` + RFQ;
- `TANKS_CONTAINMENT_ARCHITECTURE.md` + `RFQ_FERTILIZER_TANKS_CONTAINMENT.md`;
- BOM-013…017 in `19_BOM_PRODOTTI_FORNITORI/`;
- fonti dedicate in `22_FONTI_NORME_PREVENTIVI/`.

### BOM-013 — distribuzione irrigua

Working 24 settori. C1/C2/C6: Netafim PCJ/LCNL/HCNL candidato; C3–C5: dripline/ala da definire.

Benchmark 1.000 punti: **~€470–515 + IVA** prima di dorsali/valvole/posa.

### BOM-014 — filtrazione

Requisito 120 mesh / ~130 µm. Candidati: Arkal Leader/Dual, Spin-Klin, ScreenGuard, idrociclone condizionale.

Prezzi hardware: €182, €241, €2.574, €4.321, ScreenGuard da €2.988, idrociclone €363 + IVA secondo configurazione.

### BOM-015 — pompe principali irrigazione 1+1

Baseline 2×100% con VFD dedicato e failover locale.

Candidato di classe Grundfos CR 10-6: 10 m³/h, 48,3 m, 2,2 kW, **€1.946,78 IVA incl./cad** retail osservato. Danfoss FC-51 2,2 kW **€895,30 + IVA/cad** benchmark.

Taglia finale da Q/H/NPSH e controlavaggio.

### BOM-016 — fertirrigazione A/B/acido

Tre canali indipendenti + predisposizione quarto. No-flow=no-dose, pH/EC/T dopo miscelazione, limiti hard, calibrazione pompe/sonde, contenimento e livelli.

Etatron eOne MF candidato prioritario. Benchmark sole pompe:

- 2×20/7 + 1×6/7 = **€1.744 + IVA**;
- 2×30/5 + 1×6/7 = **€1.894 + IVA**.

Hanna HI98143-22 pH+EC 4–20 mA: **€615 + IVA**, sonde escluse. Hanna HI9814 portatile: **€315 + IVA**.

### BOM-017 — serbatoi fertilizzanti e contenimento

Scenario RFQ, non selezione d'ordine:

- A 500 L;
- B 500 L;
- acido 200 L.

Il volume finale deriva da consumo massimo × autonomia con freeboard e fondo non pescabile.

Serbatoi benchmark:

- Pack Services PE chimici 500 L: **€188,73 + IVA**;
- Pack Services PE chimici 200 L: **€131,94 + IVA**;
- ELBI CHL-500: **€219 IVA incl.**;
- stazione dosaggio PE 200 L con vasca: **€202,77 + IVA**.

Scenario 500/500/200 con PFF-CH: **€509,40 + IVA di soli serbatoi**.

Contenimento:

- acido separato come baseline;
- A+B insieme solo con compatibilità documentata;
- target ingegneristico iniziale per singolo bacino >= volume nominale del serbatoio;
- DENIOS PE 600 L **€560 + IVA**;
- vasca PE 500 L Gaesco **€641,72 IVA incl.**.

Livelli:

- continuo + low-low indipendente + high/high-high per tank;
- Novus TL400 da €130 pubblicati, IVA da confermare;
- WIKA ILT-C01 radar €390,09 + IVA;
- Elesa HFLT-E/HFL-E da €39,18/€60,41 + IVA.

Agitazione A/B solo se necessaria. Benchmark professionale 0,37 kW AISI316 fino a 500 L: **€1.835 + IVA**; acido senza agitatore di default.

Sicurezza: riempimenti dedicati, spill detection, drenaggio bacini normalmente chiuso, sfiati verificati da SDS, pavimento resistente, no travaso ordinario con secchi, SDS/etichette/PPE/spill kit, lavaocchi-doccia da valutazione rischio.

### Gate punto 04

Restano necessari:

- layout/portate C1–C6;
- fonte/analisi acqua + alcalinità;
- Q/H/NPSH pompe;
- filtrazione/controlavaggio finali;
- ricette e concentrazioni stock;
- acido reale/SDS/compatibilità;
- volumi A/B/acido e contenimento applicabile;
- trattamento/disinfezione se necessario;
- drenaggio/riuso;
- **BOM-018 accumulo acqua 300 m³**;
- backup elettrico;
- commissioning.

## 8. Stato punto 05 — Termico e clima

**Stato: ARCHITETTURA STRUTTURATA / BOM-009…012 SVILUPPATE / VALIDAZIONE BLOCCATA DA LOTTO, CARICHI E RFQ.**

Matrice: `05_TERMICO_E_CLIMA/POINT_05_CLOSURE_MATRIX.md`.

## 9. R&D trasversale — laser, vision e manutenzione robotica

Documento: `07_AUTOMAZIONE_DATI_AI/LASER_ROBOTICS_RND.md`.

Stato: `R&D CANDIDATO / NON BASELINE CAPEX`.

## 10. Modulo futuro — centro trasformazione conto terzi

Documento: `09_TECH_BARN_E_POST_RACCOLTA/CENTRO_TRASFORMAZIONE_CONTO_TERZI.md`.

Stato: `MODULO FUTURO AD ALTO POTENZIALE / DA BUSINESS CASE / NON ANCORA NEL CAPEX BASE`.

## 11. Metodo BOM obbligatorio

Per ogni oggetto/sottosistema: funzione, requisiti, quantità, alternative, prezzo, IVA/trasporto, installazione, consumi, manutenzione, ricambi, vita utile, sicurezza, failure mode, fallback, contributi, dipendenze, espansione e stato decisionale.

## 12. Stato attuale dei grandi blocchi

Restano nel perimetro robot tagliaerba, automazione galline, fattoria didattica, spaccio 24/7, pergolati/vite/verde/relax, sostenibilità personale, R&D robotica/laser e centro trasformazione conto terzi.

## 13. Sequenza BOM

### Già strutturate

- Serra BOM-001…008;
- BOM-009 distribuzione termica;
- BOM-010 accumulo/primario/HX;
- BOM-011 PDC 3+1;
- BOM-012 boost/deumidificazione/emergenza;
- BOM-013 distribuzione irrigua;
- BOM-014 filtrazione acqua;
- BOM-015 pompe principali irrigazione 1+1;
- BOM-016 fertirrigazione A/B/acido;
- **BOM-017 serbatoi fertilizzanti e contenimento**.

### Prossimo package

**BOM-018 — accumulo acqua 300 m³:** confronto 2×150 m³ vs alternative modulari, materiale, fondazioni, ingresso pioggia/fonte, livelli, troppo-pieno, svuotamento, sedimentazione, ispezione, qualità acqua, pompe/interfaccia BOM-015, ricambi e CAPEX.

### Coda successiva

1. accumulo acqua 300 m³;
2. moduli FV e inverter;
3. AMR;
4. sollevatore/mezzo multifunzione;
5. robot tagliaerba;
6. sistema pulizia area galline;
7. celle frigorifere;
8. attrezzatura raccolta e packaging;
9. pergolato/vite/area relax;
10. fattoria didattica;
11. spaccio automatico 24/7;
12. centro trasformazione conto terzi: capacity model + BOM succo/confetture + CAPEX/OPEX + domanda locale.

La sequenza può cambiare quando una dipendenza tecnica rende necessario anticipare un blocco.
