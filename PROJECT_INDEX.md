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

**RAFFINATO / BASE DI GOVERNO DEL PROGETTO.**

## 4. Stato punto 01 — Terreno e masterplan

**RAFFINATO / IN ATTESA DI LOTTO REALE.**

## 5. Stato punto 02 — Agronomia

**RAFFINATO / PORTAFOGLIO E METODO DEFINITI / DATI COLTURALI DA VALIDARE.**

Working portfolio: C1 pomodoro premium; C2 peperone; C3 lattuga; C4 lattuga/leaf flessibile; C5 baby leaf/rucola/spinacio; C6 basilico + vivaio + prove.

## 6. Stato punto 03 — Serra

**RAFFINATO COME ARCHITETTURA / BOM-001…008 STRUTTURATE / VALIDAZIONE BLOCCATA DA DATI REALI.**

Matrice: `03_SERRA/POINT_03_CLOSURE_MATRIX.md`.

## 7. Stato punto 04 — Acqua e fertirrigazione

**ARCHITETTURA STRUTTURATA / BOM-013…018 SVILUPPATE / TRATTAMENTO-DISINFEZIONE E DRENAGGIO-RIUSO DA SVILUPPARE / VALIDAZIONE BLOCCATA DA LOTTO, ACQUA E CROP CARD.**

Documenti principali:

- `04_ACQUA_E_FERTIRRIGAZIONE/README.md`;
- distribuzione, filtrazione, stazione pompe, fertirrigazione, tank chimici e accumulo acqua con relativi RFQ;
- BOM-013…018 in `19_BOM_PRODOTTI_FORNITORI/`;
- fonti dedicate in `22_FONTI_NORME_PREVENTIVI/`.

### BOM-013 — distribuzione irrigua

Working 24 settori. C1/C2/C6: Netafim PCJ/LCNL/HCNL candidato; C3–C5: dripline/ala da definire. Benchmark 1.000 punti **~€470–515 + IVA** prima di dorsali/valvole/posa.

### BOM-014 — filtrazione

Requisito 120 mesh / ~130 µm. Candidati Arkal Leader/Dual, Spin-Klin, ScreenGuard, idrociclone condizionale. Hardware pubblico da €182 + IVA fino a €4.321 + IVA per i candidati censiti.

### BOM-015 — pompe principali irrigazione 1+1

Baseline 2×100% con VFD dedicato e failover locale. Grundfos CR 10-6 benchmark: 10 m³/h, 48,3 m, 2,2 kW, **€1.946,78 IVA incl./cad**; Danfoss FC-51 2,2 kW **€895,30 + IVA/cad**. Taglia finale da Q/H/NPSH.

### BOM-016 — fertirrigazione A/B/acido

Tre canali indipendenti + quarto predisposto. Etatron eOne MF candidato. Benchmark sole pompe **€1.744–1.894 + IVA** negli scenari working. Hanna HI98143-22 pH+EC 4–20 mA **€615 + IVA**, sonde escluse.

### BOM-017 — serbatoi fertilizzanti/contenimento

Scenario RFQ A/B/acido 500/500/200 L, non ordine. Soli serbatoi PE benchmark **€509,40 + IVA**. Contenimento acido separato; livelli continui + low-low + high-high; agitazione solo se necessaria.

### BOM-018 — accumulo acqua 300 m³

Baseline **2×150 m³ working**, indipendenti/isolabili, predisposti a espansione 400–500 m³.

- 300 m³ con 30–35 m³/giorno = **8,6–10 giorni teorici**;
- 14 giorni = 420–490 m³;
- 4.200 m²: 1 mm pioggia = 4,2 m³ teorici;
- overflow da RainMap/intensità di progetto;
- usare sempre volume utile dichiarato, non nome commerciale.

Benchmark: bladder 150 m³ €3.799–4.270 + IVA/cad; steel 200 m³ €6.630 + IVA; ABEKO ~200 m³ utili €7.807 + IVA + cover.

### Gate punto 04

Restano layout/portate, fonte/analisi acqua, bilancio idrico, lotto/geotecnica/RainMap, RFQ tank, duty point pompe, ricette/SDS, trattamento/disinfezione, drenaggio/riuso, backup elettrico e commissioning.

## 8. Stato punto 05 — Termico e clima

**ARCHITETTURA STRUTTURATA / BOM-009…012 SVILUPPATE / VALIDAZIONE BLOCCATA DA LOTTO, CARICHI E RFQ.**

Matrice: `05_TERMICO_E_CLIMA/POINT_05_CLOSURE_MATRIX.md`.

## 9. Stato punto 06 — Energia elettrica e FV

**ARCHITETTURA FV IN SVILUPPO / BOM-019 MODULI+INVERTER SVILUPPATA / CONNESSIONE, UPS, GENERATORE ED EMS DA SVILUPPARE.**

Documenti:

- `06_ENERGIA_ELETTRICA_FV/README.md`;
- `06_ENERGIA_ELETTRICA_FV/PV_ARCHITECTURE.md`;
- `06_ENERGIA_ELETTRICA_FV/RFQ_PV_INVERTERS.md`;
- `19_BOM_PRODOTTI_FORNITORI/ENERGIA_FV_MODULI_INVERTER.md` — BOM-019;
- `22_FONTI_NORME_PREVENTIVI/ENERGIA_FV_SOURCES.md`.

### BOM-019 — FV e inverter

Working candidate moduli: **Trina Vertex S+ TSM-470NEG9R.28**.

- 256 × 470 W = **120,32 kWp**;
- ~511,5 m² di sola superficie modulo;
- ~5,38 t di soli moduli;
- prezzi pubblici UE osservati ~€68,90 netto business fino a ~€99/modulo retail;
- soli moduli ~**€17,6–25,3k** benchmark, trasporto/IVA Italia esclusi o da verificare.

Scenari inverter:

- I1 2×50 kW AC: DC/AC ~1,20;
- Sungrow SG50CX-P2 ~€1.899/cad;
- Huawei SUN2000-50KTL-M3 ~€2.379–2.399/cad;
- SMA Sunny Tripower X 50 ~€2.695/cad;
- I2 2×60 kW SMA Sunny Tripower X 60 ~€2.865/cad, DC/AC iniziale ~1,00 e famiglia dichiarata fino al 150%.

Regole:

- niente FV opaco sopra colture principali come baseline;
- stringhe dimensionate con Voc a Tmin reale;
- CEI 0-21:2026 per BT / CEI 0-16:2026 per MT;
- livello BT/MT da preventivo DSO/TICA, non deciso a tavolino;
- VVF 2025 se impianto su attività soggetta a prevenzione incendi;
- monitoraggio locale e interfaccia EMS documentata;
- predisposizione 150–180 kWp.

Il vecchio input `moduli+struttura ~€200/kWp` resta `DA VERIFICARE`: i moduli da soli nei benchmark correnti sono ~€147–211/kWp.

### Gate punto 06

- masterplan/superfici/ombre;
- neve/vento e struttura;
- Tmin/Tmax;
- profilo carichi e PVGIS;
- preventivo DSO e BT/MT;
- scelta 2×50 vs 2×60;
- string design;
- BOS/protezioni/antincendio;
- RFQ installato;
- strategia UPS/generatore/EMS da package successivi.

## 10. R&D trasversale — laser, vision e manutenzione robotica

Documento: `07_AUTOMAZIONE_DATI_AI/LASER_ROBOTICS_RND.md`. Stato: `R&D CANDIDATO / NON BASELINE CAPEX`.

## 11. Modulo futuro — centro trasformazione conto terzi

Documento: `09_TECH_BARN_E_POST_RACCOLTA/CENTRO_TRASFORMAZIONE_CONTO_TERZI.md`. Stato: `MODULO FUTURO AD ALTO POTENZIALE / DA BUSINESS CASE / NON ANCORA NEL CAPEX BASE`.

## 12. Metodo BOM obbligatorio

Per ogni oggetto/sottosistema: funzione, requisiti, quantità, alternative, prezzo, IVA/trasporto, installazione, consumi, manutenzione, ricambi, vita utile, sicurezza, failure mode, fallback, contributi, dipendenze, espansione e stato decisionale.

## 13. Stato attuale dei grandi blocchi

Restano nel perimetro robot tagliaerba, automazione galline, fattoria didattica, spaccio 24/7, pergolati/vite/verde/relax, sostenibilità personale, R&D robotica/laser e centro trasformazione conto terzi.

## 14. Sequenza BOM

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
- BOM-017 serbatoi fertilizzanti e contenimento;
- BOM-018 accumulo acqua 300 m³;
- **BOM-019 FV e inverter**.

### Prossimo package

**BOM-020 — AMR serra:** piattaforma mobile autonoma per trasporto/scouting/imaging/inventario/docking, portata, dimensioni, sicurezza, navigazione, batteria, ricarica, API/ROS/PLC, manutenzione, ricambi e costo.

### Coda successiva

1. AMR;
2. sollevatore/mezzo multifunzione;
3. robot tagliaerba;
4. sistema pulizia area galline;
5. celle frigorifere;
6. attrezzatura raccolta e packaging;
7. pergolato/vite/area relax;
8. fattoria didattica;
9. spaccio automatico 24/7;
10. centro trasformazione conto terzi: capacity model + BOM succo/confetture + CAPEX/OPEX + domanda locale.

La sequenza può cambiare quando una dipendenza tecnica rende necessario anticipare un blocco.