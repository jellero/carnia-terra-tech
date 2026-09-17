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
- `08_MACCHINE_E_LOGISTICA/` — AMR, sollevatore, piattaforme, raccolta, carrelli e robot verde;
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

Working candidate Trina Vertex S+ TSM-470NEG9R.28:

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

**ARCHITETTURA IN SVILUPPO / BOM-020 AMR + BOM-021 SOLLEVAMENTO + BOM-022 TAGLIAERBA SVILUPPATE / MASTERPLAN, PILOT E RFQ BLOCCANTI.**

Documenti: `08_MACCHINE_E_LOGISTICA/README.md` più package dedicati AMR, lifting e lawn mower; BOM-020…022 in `19_BOM_PRODOTTI_FORNITORI/`; fonti dedicate in `22_FONTI_NORME_PREVENTIVI/`.

### BOM-020 — AMR serra

Missioni: trasporto, traino, ritorno vuoti, scouting/imaging, inventario e docking.

- Burro Verde prioritario da pilot: 68,5 cm, payload 227 kg, towing 908 kg, IP65, prezzo UE/Italia da preventivo;
- MiR250 benchmark industriale ma non baseline serra finché resta indoor-only/IP21/non-condensing;
- AgileX Bunker per R&D/scouting, non AMR collaborativo baseline;
- scouting vendor-independent OAK-D + Jetson opzionale.

Gate: demo realistica, CE/DoC, IP/condensa, offline/API, dock, canoni/TCO, ricambi Italia e acceptance >=100 missioni.

### BOM-021 — sollevatore / mezzo multifunzione

Architettura a due livelli:

- L1 telescopico elettrico: **Merlo EW25.5-90** candidato prioritario; 2.500 kg, ~4,8–5 m, ~1,54 m larghezza; benchmark demo ~€69k + IVA con forche / ~€75k + IVA con navicella e radiocomando; nuovo `DA PREVENTIVO`;
- alternative Manitou MLT 625 e e JCB 525-60E;
- L2 stoccatore: EP EST122 benchmark 1.200 kg, 792 mm, ~3 m, da ~€2.900.

Nessun telescopico entra nelle corsie coltura ~1,20 m. Piattaforma persone solo OEM e abbinamento autorizzato.

### BOM-022 — robot tagliaerba

La taglia dipende dalla **superficie netta di prato robotizzabile**, da derivare dal masterplan.

Scenari:

- <=1.500 m²: Kress KR171E, €1.699 IVA incl.;
- 1.500–5.000 m² regolare: **Kress KR174E**, €2.999 IVA incl., candidato working;
- <=5.000 m² difficile/pendente: Mammotion LUBA 2 AWD 5000X €2.499 promo / €2.999 listino, oppure Kress 4×4 KR285E €4.499;
- >5.000 fino a ~12.000 m²/professionale: Husqvarna 560 EPOS €6.994 + RS5 €1.019 = **€8.013 IVA incl.** hardware base.

Guardrail:

- no mowing at night;
- area didattica/relax occupata = stop/no-go;
- prato condiviso con galline = lockout dinamico; rasaerba solo con hens-clear/gate chiuso;
- buffer da vasche, fossi, viabilità e drop-off;
- obstacle detection non sostituisce segregazione;
- perdita cloud/RTK -> safe stop/park.

Ricambi benchmark: Kress KA0002 6 lame €22,90; Husqvarna Endurance HSS 6 pz €31; Mammotion lame €55.

Gate: mappa prato, pendenze, GNSS/RTK/network coverage, pilot, offline behavior, assistenza/ricambi, TCO 5–8 anni e commissioning zone/no-go.

## 11. Stato punto 10 — Benessere, fattoria e servizi

**BOM-023 PULIZIA GALLINE FREE-RANGE SVILUPPATA / TESTATA PRATO R&D / LAYOUT E PILOT BLOCCANTI.**

Vincolo consolidato: galline libere nel dominio dedicato composto da ricovero, portico, parcheggi/superfici dure e prato.

BOM-023:
- manure belt/scraper sotto posatoi;
- rover sanitario dedicato su tutto il dominio galline;
- hard-floor spot pickup su portico/parcheggi;
- grass spot-pickup vision R&D, senza aspirazione continua;
- dirty dock per svuotamento, ricarica e wash;
- gate automatici per separazione temporale galline/veicoli;
- nessun ingresso del rover sanitario in aree food.

Candidati/benchmark: Burro Verde base agricola all-area; AgileX Bunker Pro 2.0 ~€22,1k ex VAT R&D; Gausium Beetle 2.0 ~€20k + IVA hard-floor; Big Dutchman SIMBA manure-belt; ChickenGuard/Omlet porte automatiche piccole.

La letteratura dimostra fattibilità su superfici avicole progettate, ma non esiste ancora un COTS provato per gallina + prato + parcheggio: pilot mixed-surface obbligatorio.

Documenti:
- 10_BENESSERE_FATTORIA_E_SERVIZI/CHICKEN_FREE_RANGE_CLEANING_ARCHITECTURE.md;
- 10_BENESSERE_FATTORIA_E_SERVIZI/RFQ_CHICKEN_FREE_RANGE_CLEANING.md;
- 19_BOM_PRODOTTI_FORNITORI/BENESSERE_GALLINE_PULIZIA_AUTONOMA.md;
- 22_FONTI_NORME_PREVENTIVI/BENESSERE_GALLINE_PULIZIA_SOURCES.md.

Correzione BOM-022: il prato condiviso con le galline è lockout dinamico, non no-go permanente; rasaerba solo con hens-clear/gate chiuso.

## 12. R&D trasversale — laser, vision e manutenzione robotica

Documento: `07_AUTOMAZIONE_DATI_AI/LASER_ROBOTICS_RND.md`. Stato: `R&D CANDIDATO / NON BASELINE CAPEX`.

## 13. Modulo futuro — centro trasformazione conto terzi

Documento: `09_TECH_BARN_E_POST_RACCOLTA/CENTRO_TRASFORMAZIONE_CONTO_TERZI.md`. Stato: `MODULO FUTURO AD ALTO POTENZIALE / DA BUSINESS CASE / NON ANCORA NEL CAPEX BASE`.

## 14. Metodo BOM obbligatorio

Per ogni oggetto/sottosistema: funzione, requisiti, quantità, alternative, prezzo, IVA/trasporto, installazione, consumi, manutenzione, ricambi, vita utile, sicurezza, failure mode, fallback, contributi, dipendenze, espansione e stato decisionale.

## 15. Stato attuale dei grandi blocchi

Restano nel perimetro fattoria didattica, spaccio 24/7, pergolati/vite/verde/relax, sostenibilità personale, R&D robotica/laser e centro trasformazione conto terzi.

## 16. Sequenza BOM

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
- BOM-020 AMR serra;
- BOM-021 sollevatore / mezzo multifunzione;
- BOM-022 robot tagliaerba;
- **BOM-023 pulizia galline free-range**.

### Prossimo package

**BOM-024 — celle frigorifere:** due celle a temperatura differenziata, pannelli, porte, gruppi frigoriferi, evaporatori, sbrinamento, drenaggi, monitoraggio, allarmi, backup, ricambi, installazione, consumi e costo.

### Coda successiva

1. celle frigorifere;
2. attrezzatura raccolta e packaging;
3. pergolato/vite/area relax;
4. fattoria didattica;
5. spaccio automatico 24/7;
6. centro trasformazione conto terzi: capacity model + BOM succo/confetture + CAPEX/OPEX + domanda locale.

La sequenza può cambiare quando una dipendenza tecnica rende necessario anticipare un blocco.