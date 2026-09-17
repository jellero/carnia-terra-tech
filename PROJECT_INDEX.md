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

**Stato: ARCHITETTURA IN SVILUPPO / BOM-013…016 SVILUPPATE / SERBATOI, TRATTAMENTO, DRENAGGIO E ACCUMULO DA SVILUPPARE.**

Documenti principali:

- `04_ACQUA_E_FERTIRRIGAZIONE/README.md`;
- `IRRIGATION_DISTRIBUTION.md` + RFQ;
- `FILTRATION_ARCHITECTURE.md` + RFQ;
- `PUMP_STATION_ARCHITECTURE.md` + RFQ;
- `FERTIGATION_DOSING.md` + `RFQ_FERTIGATION_DOSING.md`;
- BOM-013…016 in `19_BOM_PRODOTTI_FORNITORI/`;
- fonti dedicate in `22_FONTI_NORME_PREVENTIVI/`.

### BOM-013 — distribuzione irrigua

Working 24 settori. C1/C2/C6: Netafim PCJ/LCNL/HCNL candidato; C3–C5: dripline/ala da definire.

Benchmark 1.000 punti: ~€470–515 + IVA prima di dorsali/valvole/posa.

### BOM-014 — filtrazione

Requisito 120 mesh / ~130 µm. Candidati: Arkal Leader/Dual, Spin-Klin, ScreenGuard, idrociclone condizionale.

Prezzi hardware: €182, €241, €2.574, €4.321, ScreenGuard da €2.988, idrociclone €363 + IVA secondo configurazione.

### BOM-015 — pompe principali irrigazione 1+1

Baseline 2×100% con VFD dedicato e failover locale.

Candidato di classe Grundfos CR 10-6: 10 m³/h, 48,3 m, 2,2 kW, €1.946,78 IVA incl./cad retail osservato. Danfoss FC-51 2,2 kW €895,30 + IVA/cad benchmark.

Taglia finale da Q/H/NPSH e controlavaggio.

### BOM-016 — fertirrigazione A/B/acido

Baseline tre canali indipendenti + predisposizione quarto.

Regole:

- PLC locale;
- no flow = no dose;
- concentrati incompatibili mai a contatto prima della diluizione;
- pH/EC/T misurati dopo miscelazione;
- limiti hard su dose, EC e pH;
- contenimento e livello chimici;
- calibrazione reale pompe e sonde.

Candidato prioritario Etatron eOne MF:

- 4–20 mA, flow sensor, under/overload, PTFE, PP/PVDF;
- 6/7 €492 + IVA;
- 10/12 €593 + IVA;
- 15/5 €509 + IVA;
- 20/7 €626 + IVA;
- 30/5 €701 + IVA.

Benchmark sole pompe:

- 2×20/7 + 1×6/7 = **€1.744 + IVA**;
- 2×30/5 + 1×6/7 = **€1.894 + IVA**.

Alternative: SEKO Tekna EVO APG603 PVDF-T ~€329 IVA incl. osservati; ProMinent gamma/X prezzo da RFQ.

Misura pH/EC:

- Hanna HI98143-22 pH+EC 4–20 mA: €615 + IVA, sonde escluse;
- pH transmitter HI8614LN ~€670 + IVA;
- EC transmitter HI8936 da €327 + IVA;
- HI7638 EC probe ~€420–441 + IVA;
- pH process probe classe HI1006 ~€400 + IVA;
- Hanna HI9814 portatile di verifica €315 + IVA.

Taglie dosatrici bloccate da `Q acqua × L stock/m³`, pressione e ricette.

### Gate punto 04

Restano necessari:

- layout/portate C1–C6;
- fonte/analisi acqua + alcalinità;
- Q/H/NPSH pompe;
- filtrazione/controlavaggio finali;
- ricette e concentrazioni stock;
- acido reale e compatibilità;
- **BOM-017 serbatoi fertilizzanti + contenimento**;
- trattamento/disinfezione se necessario;
- drenaggio/riuso;
- accumulo acqua 300 m³;
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
- **BOM-016 fertirrigazione A/B/acido**.

### Prossimo package

**BOM-017 — serbatoi fertilizzanti e contenimento:** volumi A/B/acido, materiali, agitazione, coperchi/sfiati, livelli, riempimento, bacini, travasi, lavaggio, sicurezza chimica, ricambi e costi.

### Coda successiva

1. serbatoi fertilizzanti;
2. accumulo acqua 300 m³;
3. moduli FV e inverter;
4. AMR;
5. sollevatore/mezzo multifunzione;
6. robot tagliaerba;
7. sistema pulizia area galline;
8. celle frigorifere;
9. attrezzatura raccolta e packaging;
10. pergolato/vite/area relax;
11. fattoria didattica;
12. spaccio automatico 24/7;
13. centro trasformazione conto terzi: capacity model + BOM succo/confetture + CAPEX/OPEX + domanda locale.

La sequenza può cambiare quando una dipendenza tecnica rende necessario anticipare un blocco.