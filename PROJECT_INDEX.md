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
- `07_AUTOMAZIONE_DATI_AI/` — PLC, I/O, sensori, rete, edge, vision, cybersecurity e R&D robotica/laser;
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

Documenti: `PROJECT_CHARTER.md`, `KPI_GUARDRAILS.md`, `DECISION_GATES.md` in `00_VISIONE_E_PRINCIPI/`.

## 4. Stato punto 01 — Terreno e masterplan

**Stato: RAFFINATO / IN ATTESA DI LOTTO REALE.**

Il metodo è chiuso; diventa `VALIDATO` solo con lotto reale che supera due diligence, masterplan test e costo totale del sito.

## 5. Stato punto 02 — Agronomia

**Stato: RAFFINATO / PORTAFOGLIO E METODO DEFINITI / DATI COLTURALI DA VALIDARE.**

Portafoglio working: C1 pomodoro premium; C2 peperone; C3 lattuga; C4 lattuga/leaf flessibile; C5 baby leaf/rucola/spinacio; C6 basilico + vivaio + prove.

Il punto diventa `VALIDATO` coltura per coltura con sito, sistema, cultivar, resa vendibile, ore uomo, mercato, prezzo e marginalità.

## 6. Stato punto 03 — Serra

**Stato: RAFFINATO COME ARCHITETTURA / BOM PRINCIPALI IN SVILUPPO / DIMENSIONAMENTO BLOCCATO DAL LOTTO.**

Documenti principali:

- `03_SERRA/README.md`;
- `03_SERRA/STRUCTURE_FOUNDATIONS.md`;
- `03_SERRA/RFQ_GREENHOUSE_STRUCTURE.md`;
- `03_SERRA/ENVELOPE_COVERING.md`;
- `03_SERRA/RFQ_COVERING.md`;
- `03_SERRA/OPENINGS_COMPARTMENTS.md`;
- `03_SERRA/RFQ_OPENINGS_NETS.md`;
- `03_SERRA/SCREENS_SHADING.md`;
- `03_SERRA/RFQ_SCREENS.md`;
- `03_SERRA/FOGGING_HUMIDITY.md`;
- `03_SERRA/RFQ_FOGGING.md`;
- `03_SERRA/CROP_SUPPORTS_LOGISTICS.md`;
- `03_SERRA/MAINTENANCE_SAFETY.md`;
- `03_SERRA/BOM_REGISTER.md`;
- `03_SERRA/OFFICIAL_SOURCES.md`.

Package/BOM sviluppati:

- **BOM-001 — HAF**: `19_BOM_PRODOTTI_FORNITORI/SERRA_HAF_VENTILATION.md`;
- **BOM-002 — schermi climatici**: `19_BOM_PRODOTTI_FORNITORI/SERRA_SCHERMI_TERMICI_OMBREGGIANTI.md`;
- **BOM-003 — aperture/attuatori/reti**: `19_BOM_PRODOTTI_FORNITORI/SERRA_APERTURE_RETI_ANTIINSETTO.md`;
- **BOM-004 — copertura/film/fissaggi**: `19_BOM_PRODOTTI_FORNITORI/SERRA_COPERTURA_FILM_FISSAGGI.md`;
- **package struttura/fondazioni**: `19_BOM_PRODOTTI_FORNITORI/SERRA_STRUTTURA_FONDAZIONI.md`;
- **BOM-005 — fogging**: `19_BOM_PRODOTTI_FORNITORI/SERRA_FOGGING.md`.

### Struttura/fondazioni — stato corrente

Sono definite le righe economiche obbligatorie: peso acciaio per famiglia, zincatura, bulloneria, lavorazioni, trasporto, scarico, montaggio, mezzi, engineering, scavi, cls, ferro, casseri, ancoraggi, prove, rinterri e drenaggi.

Benchmark registrati: Tuttoserre 8×40 m / €6.832 IVA incl. non scalabile; Prezzario FVG 2026 per carpenteria e calcestruzzo come controllo di congruità.

### Fogging — stato corrente

BOM-005 copre C1/C2/C6 e confronta tre architetture:

- F1 centrale singola;
- F2 centrale N+1;
- F3 tre pompe indipendenti.

Sono stati trovati prezzi reali per pompe HP, ugelli, tubi, raccordi, elettrovalvole e filtrazione. Il costo totale resta correttamente aperto perché servono analisi acqua, carico climatico, numero ugelli, metri di linea e trattamento acqua.

Osmosi inversa/softening non sono acquisti automatici: diventano requisito solo se l'analisi acqua e il costruttore li giustificano.

Il punto 03 diventa `VALIDATO` solo dopo lotto, carichi reali, geotecnica, calcolo strutturale, layout esecutivo, analisi acqua e preventivi confrontabili.

## 7. R&D trasversale — laser, vision e manutenzione robotica

Nuovo documento:

- `07_AUTOMAZIONE_DATI_AI/LASER_ROBOTICS_RND.md`.

Stato: `R&D CANDIDATO / NON BASELINE CAPEX`.

Linee correnti:

- femminelle pomodoro: priorità a visione + manipolatore + microforbice/cutter; laser solo candidato futuro in testina confinata;
- insetti volanti: R&D prioritario su barriera laser confinata alle aperture o trappola chiusa, coerente con ricerca greenhouse attiva;
- nessun sistema open-beam libero nel volume di lavoro della serra come baseline;
- classificazione biologica a tre stati `TARGET DANNO / UTILE-PROTETTO / INCERTO`; se incerto, nessuna attivazione;
- non proteggere soltanto le api: il piano IPM può includere bombi, sirfidi, parassitoidi e altri organismi utili.

Il laser non sostituisce automaticamente reti, scouting o lotta biologica: può diventare uno strumento aggiuntivo di IPM dopo pilot, sicurezza e TCO.

## 8. Metodo BOM obbligatorio

Per ogni oggetto o sottosistema si analizzano:

1. funzione;
2. requisiti;
3. quantità;
4. alternative reali;
5. prezzo trovato/preventivo/stima;
6. IVA/trasporto/accessori;
7. installazione/minuteria;
8. consumi;
9. manutenzione ordinaria;
10. manutenzione straordinaria;
11. ricambi;
12. vita utile;
13. sicurezza/certificazioni;
14. failure mode;
15. fallback/ridondanza;
16. contributi;
17. dipendenze;
18. espansione;
19. stato secondo `DECISION_GATES.md`.

## 9. Stato attuale dei grandi blocchi

I file in `docs/` restano sorgenti durante la migrazione. Sono già nel perimetro robot tagliaerba, automazione pulizia area galline, fattoria didattica, spaccio 24/7, pergolati/vite/verde/relax, sostenibilità personale durante il lancio e R&D robotica/laser per manutenzione colture e IPM.

## 10. Sequenza BOM

### Candidati/package già sviluppati

- BOM-001 HAF;
- BOM-002 schermi;
- BOM-003 aperture/reti;
- BOM-004 copertura;
- struttura/fondazioni: package economico + RFQ;
- BOM-005 fogging + RFQ.

### In lavorazione successiva

**Supporti coltura + canaline drenaggio:** fili, ganci, bobine/clip, ancoraggi, sostegni, canaline fuori suolo, staffe, pendenze, raccolta drenaggio, manutenzione e costi.

### Coda immediata

1. supporti coltura/canaline drenaggio;
2. porte/compartimenti/gronde;
3. attrezzatura e consumabili montaggio;
4. tubi, collettori e pompe circuito termico;
5. gocciolatori e linee irrigue;
6. filtrazione acqua;
7. pompe principali irrigazione;
8. pompe dosatrici;
9. serbatoi fertilizzanti;
10. accumulo termico 30–50 m³;
11. accumulo acqua 300 m³;
12. moduli FV e inverter;
13. AMR;
14. sollevatore/mezzo multifunzione;
15. robot tagliaerba;
16. sistema pulizia area galline;
17. celle frigorifere;
18. attrezzatura raccolta e packaging;
19. pergolato/vite/area relax;
20. fattoria didattica;
21. spaccio automatico 24/7.

La sequenza può cambiare quando una dipendenza tecnica rende necessario anticipare un blocco.