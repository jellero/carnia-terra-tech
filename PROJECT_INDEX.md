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

**ARCHITETTURA IN SVILUPPO / BOM-020 AMR + BOM-021 SOLLEVAMENTO SVILUPPATE / PILOT E RFQ BLOCCANTI.**

Documenti:

- `08_MACCHINE_E_LOGISTICA/README.md`;
- `AMR_ARCHITECTURE.md` + `RFQ_AMR.md`;
- `LIFTING_MULTIFUNCTION_ARCHITECTURE.md` + `RFQ_LIFTING_MULTIFUNCTION.md`;
- BOM-020 e BOM-021 in `19_BOM_PRODOTTI_FORNITORI/`;
- fonti dedicate in `22_FONTI_NORME_PREVENTIVI/`.

### BOM-020 — AMR serra

Missioni: trasporto, traino, ritorno vuoti, scouting/imaging, inventario e docking.

Working site: robot <=0,75 m preferito, corsie >=1,20 m, turning ~2–2,5 m, ambiente umido/condensa reale.

- Burro Verde prioritario da pilot: 68,5 cm, payload 227 kg, towing 908 kg, IP65, prezzo UE/Italia da preventivo;
- MiR250 benchmark industriale ma non baseline serra finché resta indoor-only/IP21/non-condensing;
- AgileX Bunker per R&D/scouting, non AMR collaborativo baseline;
- scouting vendor-independent OAK-D + Jetson opzionale.

Gate: demo realistica, CE/DoC, IP/condensa, offline/API, dock, canoni/TCO, ricambi Italia e acceptance >=100 missioni.

### BOM-021 — sollevatore / mezzo multifunzione

Architettura a due livelli:

**L1 telescopico elettrico** — candidato prioritario **Merlo EW25.5-90**:

- 2.500 kg;
- ~4,8–5 m;
- ~1,54 m larghezza e ~1,98 m altezza;
- 4WD versione 90;
- piattaforma persone OEM disponibile nella gamma;
- benchmark demo/usato: ~€69.000 + IVA con forche e ~€75.000 + IVA con forche+navicella/radiocomando; nuovo 2026 `DA PREVENTIVO`.

Alternative:

- Manitou MLT 625 e: 2,5 t / 5,9 m / 1,81 m / 34,8 kWh;
- JCB 525-60E: 2,5 t / 6 m / 1,84 m / 24 kWh.

Nessuno dei tre telescopici entra nelle corsie coltura da ~1,20 m; uso previsto su corridoio tecnico ~4 m, Tech Barn se compatibile e piazzale.

**L2 stoccatore elettrico compatto** per Tech Barn e pallet ordinari:

- EP EST122 benchmark: 1.200 kg, 792 mm, ~3 m, raggio ~1,46 m, prezzo da ~€2.900;
- alternative 1,2 t/3 m ~€1.899–1.900 + IVA; classe professionale Li-ion più costosa.

Safety: piattaforma persone solo OEM e abbinamento autorizzato dal costruttore; niente retrofit DIY. Formazione e verifiche secondo regime vigente, incluso modulo per persone/carichi sospesi se utilizzato.

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
- BOM-020 AMR serra;
- **BOM-021 sollevatore / mezzo multifunzione**.

### Prossimo package

**BOM-022 — robot tagliaerba:** area utile, pendenze, bordo acqua/serra, RTK/GNSS vs beacon, docking, sicurezza persone/animali, lama, autonomia, gestione zone, integrazione locale, ricambi e costo.

### Coda successiva

1. robot tagliaerba;
2. sistema pulizia area galline;
3. celle frigorifere;
4. attrezzatura raccolta e packaging;
5. pergolato/vite/area relax;
6. fattoria didattica;
7. spaccio automatico 24/7;
8. centro trasformazione conto terzi: capacity model + BOM succo/confetture + CAPEX/OPEX + domanda locale.

La sequenza può cambiare quando una dipendenza tecnica rende necessario anticipare un blocco.