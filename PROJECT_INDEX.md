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

Documenti principali: `04_ACQUA_E_FERTIRRIGAZIONE/README.md`, package distribuzione/filtrazione/pompe/fertirrigazione/tank chimici/accumulo e relativi RFQ; BOM-013…018 e fonti dedicate.

Dati guida:

- BOM-013: 24 settori working; 1.000 punti goccia ~€470–515 + IVA prima di dorsali/valvole/posa;
- BOM-014: filtrazione working 120 mesh/~130 µm;
- BOM-015: pompe 1+1, Grundfos CR10-6 benchmark €1.946,78 IVA incl./cad;
- BOM-016: A/B/acido; sole pompe scenario ~€1.744–1.894 + IVA;
- BOM-017: scenario tank A/B/acido 500/500/200 L; soli contenitori ~€509,40 + IVA;
- BOM-018: 2×150 m³ working, espansione 400–500 m³; 300 m³ = 8,6–10 giorni teorici a 30–35 m³/giorno.

Gate: lotto, analisi acqua, crop card, bilancio idrico, geotecnica/RainMap, RFQ, trattamento/disinfezione, drenaggio/riuso e commissioning.

## 8. Stato punto 05 — Termico e clima

**ARCHITETTURA STRUTTURATA / BOM-009…012 SVILUPPATE / VALIDAZIONE BLOCCATA DA LOTTO, CARICHI E RFQ.**

Matrice: `05_TERMICO_E_CLIMA/POINT_05_CLOSURE_MATRIX.md`.

## 9. Stato punto 06 — Energia elettrica e FV

**ARCHITETTURA FV IN SVILUPPO / BOM-019 MODULI+INVERTER SVILUPPATA / CONNESSIONE, UPS, GENERATORE ED EMS DA SVILUPPARE.**

Documenti: `06_ENERGIA_ELETTRICA_FV/README.md`, `PV_ARCHITECTURE.md`, `RFQ_PV_INVERTERS.md`, BOM-019 e fonti.

### BOM-019 — FV e inverter

Working candidate: Trina Vertex S+ TSM-470NEG9R.28.

- 256×470 W = **120,32 kWp**;
- ~511,5 m² di sola superficie moduli;
- ~5,38 t;
- soli moduli ~€17,6–25,3k benchmark UE;
- inverter 2×50 kW o 2×60 kW da confrontare;
- niente FV opaco sopra colture principali;
- CEI 0-21:2026 / CEI 0-16:2026;
- BT/MT e protezioni da preventivo DSO/TICA;
- predisposizione 150–180 kWp.

## 10. Stato punto 08 — Macchine e logistica

**ARCHITETTURA AMR IN SVILUPPO / BOM-020 SVILUPPATA / PILOT, CONFORMITÀ E ASSISTENZA UE BLOCCANTI.**

Documenti:

- `08_MACCHINE_E_LOGISTICA/README.md`;
- `08_MACCHINE_E_LOGISTICA/AMR_ARCHITECTURE.md`;
- `08_MACCHINE_E_LOGISTICA/RFQ_AMR.md`;
- `19_BOM_PRODOTTI_FORNITORI/MACCHINE_AMR_SERRA.md` — BOM-020;
- `22_FONTI_NORME_PREVENTIVI/MACCHINE_AMR_SOURCES.md`.

### BOM-020 — AMR serra

Missioni: trasporto, traino, ritorno vuoti, scouting/imaging, inventario e docking.

Working site:

- robot preferito <=0,75 m;
- corsie >=1,20 m working;
- turning/intersezioni ~2–2,5 m;
- ambiente umido/condensa da trattare come requisito reale.

**Burro Verde** — candidato funzionale prioritario da pilot/RFQ:

- width 68,5 cm;
- payload 227 kg;
- towing 908 kg su piano duro;
- IP65;
- LiDAR 360°, 12 camere, RTK + GPS-denied;
- LFP 2,56 kWh;
- prezzo Italia/UE `DA PREVENTIVO`; benchmark commerciale terzo 2026 <US$50k + canone BOSS annuale;
- ingresso europeo annunciato nel 2026: CE/configurazione europea, assistenza Italia e ricambi da verificare.

**MiR250** — benchmark industriale safety/API:

- payload 250 kg;
- 580×800 mm;
- REST API/MiR Fleet;
- prezzi base €44.284 + IVA UE / integrazione Italia da €53.141 + IVA;
- MiR Charge benchmark €6.075 + IVA;
- Hook integrato Italia da €78.514 + IVA;
- **non baseline serra** finché non risolta la specifica ufficiale indoor-only/IP21/non-condensing/no-water.

**AgileX Bunker Mini/Pro** — R&D/scouting, non baseline collaborativa: IP67 e stack aperto, ma safety/conformità della macchina integrata restano da sviluppare. Bunker Mini ~€9.350 IVA DE incl.; ROS2 kit ~€20.500 + IVA.

Scouting vendor-independent opzionale: OAK-D Pro PoE ~€671–769 IVA incl. + Jetson Orin Nano Super ~€382 benchmark.

Safety: ISO 3691-4:2023 come riferimento corrente; verificare revisione 2026 e Regolamento (UE) 2023/1230 per macchine immesse dopo l'entrata in applicazione.

Gate: demo con geometria/carichi/persone reali, CE/DoC, IP/condensa, API offline, dock, canoni/TCO 5–8 anni, ricambi Italia, risk assessment e acceptance >=100 missioni.

## 11. R&D trasversale — laser, vision e manutenzione robotica

Documento: `07_AUTOMAZIONE_DATI_AI/LASER_ROBOTICS_RND.md`. Stato: `R&D CANDIDATO / NON BASELINE CAPEX`.

## 12. Modulo futuro — centro trasformazione conto terzi

Documento: `09_TECH_BARN_E_POST_RACCOLTA/CENTRO_TRASFORMAZIONE_CONTO_TERZI.md`. Stato: `MODULO FUTURO AD ALTO POTENZIALE / DA BUSINESS CASE / NON ANCORA NEL CAPEX BASE`.

## 13. Metodo BOM obbligatorio

Per ogni oggetto/sottosistema: funzione, requisiti, quantità, alternative, prezzo, IVA/trasporto, installazione, consumi, manutenzione, ricambi, vita utile, sicurezza, failure mode, fallback, contributi, dipendenze, espansione e stato decisionale.

## 14. Stato attuale dei grandi blocchi

Restano nel perimetro robot tagliaerba, automazione galline, fattoria didattica, spaccio 24/7, pergolati/vite/verde/relax, sostenibilità personale, R&D robotica/laser e centro trasformazione conto terzi.

## 15. Sequenza BOM

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
- BOM-019 FV e inverter;
- **BOM-020 AMR serra**.

### Prossimo package

**BOM-021 — sollevatore/mezzo multifunzione:** forche, portata, altezza, ingombri, pneumatici, sterzo, eventuale piattaforma di lavoro certificata/OEM, alimentazione, ricarica, accessori, sicurezza, manutenzione, ricambi e costi.

### Coda successiva

1. sollevatore/mezzo multifunzione;
2. robot tagliaerba;
3. sistema pulizia area galline;
4. celle frigorifere;
5. attrezzatura raccolta e packaging;
6. pergolato/vite/area relax;
7. fattoria didattica;
8. spaccio automatico 24/7;
9. centro trasformazione conto terzi: capacity model + BOM succo/confetture + CAPEX/OPEX + domanda locale.

La sequenza può cambiare quando una dipendenza tecnica rende necessario anticipare un blocco.