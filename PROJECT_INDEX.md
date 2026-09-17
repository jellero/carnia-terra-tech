# Carnia TerraTech — Project Index

**Ruolo:** indice operativo e mappa di copertura del progetto.  
**Aggiornato:** 17 settembre 2026.

## 1. Scopo

Il repository deve permettere di progettare l'azienda senza lasciare aree scoperte. Ogni decisione deve essere collegata a costi, manutenzione, sicurezza, dipendenze, crescita e qualità della vita.

## 2. Struttura target

La riorganizzazione procede senza cancellare i documenti storici finché il contenuto non è stato migrato e verificato.

- `00_VISIONE_E_PRINCIPI/` — missione, KPI, guardrail e decision gates;
- `01_MASTERPLAN_E_TERRENO/` — lotto, vincoli, accessi, drenaggi, espansioni;
- `02_AGRONOMIA/` — colture, calendari, rese, vite, luppolo, siepi, outdoor;
- `03_SERRA/` — struttura, comparti, coperture, aperture, schermi, HAF, fogging;
- `04_ACQUA_E_FERTIRRIGAZIONE/` — fonte, accumulo, filtri, pompe, dosaggio, drenaggio;
- `05_TERMICO_E_CLIMA/` — PDC, accumulo, distribuzione, deumidificazione, emergenza;
- `06_ENERGIA_ELETTRICA_FV/` — FV, inverter, rete, UPS, generatore, EMS;
- `07_AUTOMAZIONE_DATI_AI/` — PLC, I/O, sensori, rete, edge, vision, cybersecurity;
- `08_MACCHINE_E_LOGISTICA/` — AMR, sollevatore, piattaforme, raccolta, carrelli;
- `09_TECH_BARN_E_POST_RACCOLTA/` — celle, confezionamento, officina, magazzini;
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

Documenti:

- `00_VISIONE_E_PRINCIPI/PROJECT_CHARTER.md`;
- `00_VISIONE_E_PRINCIPI/KPI_GUARDRAILS.md`;
- `00_VISIONE_E_PRINCIPI/DECISION_GATES.md`.

Il punto 00 può essere aggiornato se emergono nuovi requisiti, ma è sufficientemente definito per governare i blocchi successivi.

## 4. Stato punto 01 — Terreno e masterplan

**Stato: RAFFINATO / IN ATTESA DI LOTTO REALE.**

Documenti:

- `01_MASTERPLAN_E_TERRENO/README.md`;
- `01_MASTERPLAN_E_TERRENO/SITE_REQUIREMENTS.md`;
- `01_MASTERPLAN_E_TERRENO/DUE_DILIGENCE_GATE.md`;
- `01_MASTERPLAN_E_TERRENO/MASTERPLAN_REQUIREMENTS.md`;
- `01_MASTERPLAN_E_TERRENO/SITE_EVALUATION_TEMPLATE.md`;
- `01_MASTERPLAN_E_TERRENO/LAND_COST_MODEL.md`;
- `01_MASTERPLAN_E_TERRENO/OFFICIAL_SOURCES.md`.

Il metodo del punto 01 è chiuso. Il punto diventa `VALIDATO` solo con un lotto reale che supera due diligence, masterplan test e costo totale del sito.

## 5. Stato punto 02 — Agronomia

**Stato: RAFFINATO / PORTAFOGLIO E METODO DEFINITI / DATI COLTURALI DA VALIDARE.**

Documenti:

- `02_AGRONOMIA/README.md` — regole agronomiche e gate di validazione;
- `02_AGRONOMIA/CROP_PORTFOLIO.md` — portafoglio, allocazione dei comparti e diversificazione;
- `02_AGRONOMIA/CROP_CARD_TEMPLATE.md` — scheda obbligatoria coltura per coltura;
- `02_AGRONOMIA/GREENHOUSE_CROPS.md` — pomodoro, peperone, lattuga/leaf, baby leaf e basilico/vivaio;
- `02_AGRONOMIA/CALENDAR_AND_CAPACITY.md` — calendario settimanale, occupazione comparti, picchi lavoro e prodotto;
- `02_AGRONOMIA/YIELD_LABOR_ECONOMICS.md` — resa vendibile, ore uomo, costi e marginalità;
- `02_AGRONOMIA/IPM_BIOSECURITY.md` — prevenzione, scouting, IPM e separazione dei comparti;
- `02_AGRONOMIA/OUTDOOR_PERENNIALS.md` — outdoor, vite, siepi, verde e luppolo;
- `02_AGRONOMIA/OFFICIAL_SOURCES.md` — ERSA, ARPA/OSMER, Commissione UE e CREA.

Portafoglio di lavoro mantenuto:

- C1 pomodoro premium;
- C2 peperone;
- C3 lattuga;
- C4 lattuga/leaf flessibile;
- C5 baby leaf/rucola/spinacio;
- C6 basilico + vivaio + prove.

Non sono state inventate rese, cultivar, densità o calendari definitivi. Il punto 02 diventa `VALIDATO` coltura per coltura solo quando sono disponibili sito, sistema di coltivazione, cultivar, resa vendibile con fonte/prova, ore uomo, mercato, prezzo e marginalità.

## 6. Stato punto 03 — Serra

**Stato: RAFFINATO COME ARCHITETTURA / DA DIMENSIONARE SUL LOTTO REALE / BOM IN CORSO.**

Documenti principali:

- `03_SERRA/README.md`;
- `03_SERRA/STRUCTURE_FOUNDATIONS.md`;
- `03_SERRA/ENVELOPE_COVERING.md`;
- `03_SERRA/OPENINGS_COMPARTMENTS.md`;
- `03_SERRA/SCREENS_SHADING.md`;
- `03_SERRA/RFQ_SCREENS.md`;
- `03_SERRA/RFQ_OPENINGS_NETS.md`;
- `03_SERRA/FOGGING_HUMIDITY.md`;
- `03_SERRA/CROP_SUPPORTS_LOGISTICS.md`;
- `03_SERRA/MAINTENANCE_SAFETY.md`;
- `03_SERRA/RFQ_GREENHOUSE_STRUCTURE.md`;
- `03_SERRA/BOM_REGISTER.md`;
- `03_SERRA/OFFICIAL_SOURCES.md`.

BOM serra sviluppate:

- **BOM-001 — Ventilazione HAF**: `19_BOM_PRODOTTI_FORNITORI/SERRA_HAF_VENTILATION.md`;
- **BOM-002 — Schermi termici/ombreggianti**: `19_BOM_PRODOTTI_FORNITORI/SERRA_SCHERMI_TERMICI_OMBREGGIANTI.md`;
- **BOM-003 — Aperture, attuatori e reti anti-insetto**: `19_BOM_PRODOTTI_FORNITORI/SERRA_APERTURE_RETI_ANTIINSETTO.md`.

BOM-003 registra come working range 6–12 gruppi laterali motorizzati, da calcolare sul layout. Sono stati identificati attuatori professionali e scenari di rete N1/N2/N3. Le reti fini per tripidi non vengono adottate automaticamente perché la riduzione di ventilazione deve essere compensata nel progetto.

Il punto 03 diventa `VALIDATO` solo dopo lotto, carichi reali, geotecnica, calcolo strutturale, layout esecutivo e preventivi confrontabili.

## 7. Metodo BOM obbligatorio

Per ogni oggetto o sottosistema si analizzano, in ordine:

1. funzione;
2. requisiti tecnici e operativi;
3. quantità;
4. alternative reali acquistabili;
5. prezzo trovato / prezzo da preventivo / stima;
6. IVA, trasporto e accessori esclusi/inclusi;
7. installazione e minuteria;
8. alimentazioni e consumi;
9. manutenzione ordinaria;
10. manutenzione straordinaria;
11. ricambi critici;
12. vita utile e sostituibilità;
13. sicurezza e certificazioni;
14. failure mode;
15. fallback manuale o ridondanza;
16. compatibilità con contributi;
17. dipendenze da altri sistemi;
18. predisposizione per espansione;
19. stato documentale secondo `DECISION_GATES.md`.

## 8. Stato attuale dei grandi blocchi

I file in `docs/` restano sorgenti durante la migrazione. Sono già parte esplicita del progetto robot tagliaerba, automazione pulizia area galline, fattoria didattica, spaccio 24/7, pergolati/vite/verde/relax e sostenibilità personale durante il lancio.

## 9. Sequenza BOM

### Candidati già sviluppati

- BOM-001 — HAF;
- BOM-002 — schermi climatici;
- BOM-003 — aperture/attuatori/reti anti-insetto.

### In lavorazione successiva

**BOM-004 — copertura serra + profili + fissaggi + minuteria + riparazione/sostituzione.**

### Coda immediata

1. RFQ struttura/fondazioni;
2. fogging;
3. tubi, collettori e pompe circuito termico;
4. gocciolatori e linee irrigue;
5. filtrazione acqua;
6. pompe principali irrigazione;
7. pompe dosatrici;
8. serbatoi fertilizzanti;
9. accumulo termico 30–50 m³;
10. accumulo acqua 300 m³;
11. moduli FV e inverter;
12. AMR;
13. sollevatore/mezzo multifunzione;
14. robot tagliaerba;
15. sistema pulizia area galline;
16. celle frigorifere;
17. attrezzatura raccolta e packaging;
18. pergolato/vite/area relax;
19. fattoria didattica;
20. spaccio automatico 24/7.

La sequenza può cambiare quando una dipendenza tecnica rende necessario anticipare un blocco.
