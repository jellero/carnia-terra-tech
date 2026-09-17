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
- `03_SERRA/` — struttura, comparti, coperture, aperture, schermi, HAF, fogging, supporti coltura, drenaggi, porte, recupero pioggia e cantiere;
- `04_ACQUA_E_FERTIRRIGAZIONE/` — fonte, accumulo, filtri, pompe, dosaggio, drenaggio;
- `05_TERMICO_E_CLIMA/` — carico termico, PDC, accumulo, distribuzione, deumidificazione, emergenza;
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

Documenti: `PROJECT_CHARTER.md`, `KPI_GUARDRAILS.md`, `DECISION_GATES.md` in `00_VISIONE_E_PRINCIPI/`.

## 4. Stato punto 01 — Terreno e masterplan

**Stato: RAFFINATO / IN ATTESA DI LOTTO REALE.**

Il metodo è chiuso; diventa `VALIDATO` solo con lotto reale che supera due diligence, masterplan test e costo totale del sito.

## 5. Stato punto 02 — Agronomia

**Stato: RAFFINATO / PORTAFOGLIO E METODO DEFINITI / DATI COLTURALI DA VALIDARE.**

Portafoglio working: C1 pomodoro premium; C2 peperone; C3 lattuga; C4 lattuga/leaf flessibile; C5 baby leaf/rucola/spinacio; C6 basilico + vivaio + prove.

Il punto diventa `VALIDATO` coltura per coltura con sito, sistema, cultivar, resa vendibile, ore uomo, mercato, prezzo e marginalità.

## 6. Stato punto 03 — Serra

**Stato: RAFFINATO COME ARCHITETTURA / BOM-001…008 STRUTTURATE / VALIDAZIONE BLOCCATA DA DATI REALI.**

Package/BOM sviluppati:

- BOM-001 HAF;
- BOM-002 schermi climatici;
- BOM-003 aperture/attuatori/reti;
- BOM-004 copertura/film/fissaggi;
- package struttura/fondazioni;
- BOM-005 fogging;
- BOM-006 supporti coltura + drenaggio;
- BOM-007 porte, compartimentazioni, gronde e pluviali;
- BOM-008 attrezzatura e consumabili montaggio.

Matrice di chiusura: `03_SERRA/POINT_03_CLOSURE_MATRIX.md`.

Il punto 03 è sufficientemente coperto per proseguire, ma non è progetto esecutivo. Restano dipendenze da lotto, geotecnica, crop card, layout, analisi acqua, calcoli e preventivi.

## 7. Stato punto 05 — Termico e clima

**Stato: ARCHITETTURA DI BASE DEFINITA / BOM-009, BOM-010 E BOM-011 SVILUPPATE / CARICO E PRESTAZIONI SOTTOZERO DA VALIDARE.**

Documenti principali:

- `05_TERMICO_E_CLIMA/README.md`;
- `05_TERMICO_E_CLIMA/THERMAL_LOAD_METHOD.md`;
- `05_TERMICO_E_CLIMA/HYDRONIC_DISTRIBUTION.md`;
- `05_TERMICO_E_CLIMA/RFQ_HYDRONIC_DISTRIBUTION.md`;
- `05_TERMICO_E_CLIMA/THERMAL_STORAGE_PRIMARY.md`;
- `05_TERMICO_E_CLIMA/RFQ_THERMAL_STORAGE_PRIMARY.md`;
- `05_TERMICO_E_CLIMA/HEAT_PUMP_CASCADE.md`;
- `05_TERMICO_E_CLIMA/RFQ_HEAT_PUMPS.md`;
- `19_BOM_PRODOTTI_FORNITORI/TERMICO_DISTRIBUZIONE_IDRONICA.md`;
- `19_BOM_PRODOTTI_FORNITORI/TERMICO_ACCUMULO_PRIMARIO.md`;
- `19_BOM_PRODOTTI_FORNITORI/TERMICO_PDC_MODULARI.md`;
- `22_FONTI_NORME_PREVENTIVI/TERMICO_DISTRIBUZIONE_SOURCES.md`;
- `22_FONTI_NORME_PREVENTIVI/TERMICO_ACCUMULO_PRIMARIO_SOURCES.md`;
- `22_FONTI_NORME_PREVENTIVI/TERMICO_PDC_SOURCES.md`.

### BOM-009 — distribuzione idronica

Architettura: accumulo -> collettore secondario -> 6 circuiti indipendenti -> terminali near-crop.

Il working 2.700–3.000 m di terminali non è quantità d'ordine. Tubi greenhouse-specific restano preferenza da RFQ; PE-Xa è benchmark economico, non scelta definitiva.

### BOM-010 — accumulo + primario + scambiatore

Working architecture:

`PDC -> primario corto protetto -> HX -> 30 m³ acqua tecnica -> BOM-009`, con predisposizione 40–50 m³.

Energia teorica acqua:

- 30 m³: ~349 kWh/10 K; ~698 kWh/20 K; ~1.047 kWh/30 K;
- 40 m³: ~465 / 930 / 1.395 kWh;
- 50 m³: ~581 / 1.163 / 1.744 kWh.

Scenari serbatoi da RFQ: 6×5 m³, 3×10 m³, oppure 1×30 m³ custom solo se TCO e affidabilità lo giustificano.

La pompa integrata nelle Kensol è confermata; pompe primarie esterne restano condizionali alla curva Q/H e alle perdite reali.

### BOM-011 — PDC modulari 3+1

Candidato: Kensol KHP-R290-22-3.

Dati correnti verificati:

- A7/W35: 7,8–22,0 kW, COP 3,73–5,27;
- A2/W35: 6,69–18,8 kW, COP 3,42–4,61;
- SCOP W35 5,13; W55 3,84;
- max input 9 kW / 15,8 A;
- portata nominale 2,9 m³/h;
- pompa SHIMGE integrata;
- R290 1,30 kg;
- 202 kg;
- 47 dB(A) pressione sonora / 62 dB(A) potenza sonora.

Capacità massima aggregata:

- 3 unità: 66 kW A7/W35, 56,4 kW A2/W35;
- 4 unità: 88 kW A7/W35, 75,2 kW A2/W35.

Prezzo hardware osservato: €3.616,74 + IVA/unità; tre unità €10.850,22 + IVA, quattro €14.466,96 + IVA.

Open gate critici:

- A-7/A-10/A-15 e W45;
- capacità media netta durante defrost;
- chiarimento discordanza datasheet/manuale su assorbimento e idraulica;
- curva pompa integrata/prevalenza residua;
- cascata OEM o protocollo PLC;
- requisiti R290 per 3–4 macchine affiancate;
- garanzia 5+2 e assistenza Italia/FVG;
- carico termico reale e decisione se installare subito la quarta unità.

### Dipendenze punto 05

Servono ancora:

- carico termico C1–C6 e scenari produzione/economia/sopravvivenza;
- temperature acqua;
- prestazioni PDC sottozero alle temperature di mandata reali;
- defrost netto;
- perdite di carico/P&ID;
- materiale near-crop definitivo;
- volume accumulo 30/40/50 m³ e architettura;
- numero/taglia HX;
- concentrazione glicole;
- espansione/sicurezze;
- boost/deumidificazione/emergenza;
- preventivi professionali.

## 8. R&D trasversale — laser, vision e manutenzione robotica

Documento: `07_AUTOMAZIONE_DATI_AI/LASER_ROBOTICS_RND.md`.

Stato: `R&D CANDIDATO / NON BASELINE CAPEX`.

Linee correnti: potatura robotica con visione e microforbice/cutter come baseline R&D; laser solo confinato; controllo insetti laser solo con classificazione `TARGET / UTILE-PROTETTO / INCERTO` e nessuna attivazione su incerto.

## 9. Modulo futuro — centro trasformazione conto terzi

Documento: `09_TECH_BARN_E_POST_RACCOLTA/CENTRO_TRASFORMAZIONE_CONTO_TERZI.md`.

Stato: `MODULO FUTURO AD ALTO POTENZIALE / DA BUSINESS CASE / NON ANCORA NEL CAPEX BASE`.

Perimetro: mele, pere, piccoli frutti, succhi, puree, confetture/composte; lavoro proprio e conto terzi; tariffa, compensazione in prodotto, acquisto materia prima o modello ibrido. Il masterplan deve predisporre spazio e utilities senza obbligare l'acquisto iniziale.

## 10. Metodo BOM obbligatorio

Per ogni oggetto o sottosistema si analizzano funzione, requisiti, quantità, alternative, prezzo, IVA/trasporto, installazione, consumi, manutenzione, ricambi, vita utile, sicurezza, failure mode, fallback, contributi, dipendenze, espansione e stato decisionale.

## 11. Stato attuale dei grandi blocchi

I file in `docs/` restano sorgenti durante la migrazione. Sono nel perimetro robot tagliaerba, automazione area galline, fattoria didattica, spaccio 24/7, pergolati/vite/verde/relax, sostenibilità personale, R&D robotica/laser e centro trasformazione conto terzi.

## 12. Sequenza BOM

### Già strutturate

- Serra BOM-001…008;
- BOM-009 distribuzione termica idronica;
- BOM-010 accumulo termico + primario/scambiatore;
- **BOM-011 PDC modulari 3+1**.

### Prossimo package

**Boost/deumidificazione/emergenza termica:** aerotermi idronici o altra soluzione, funzione anti-condensa, potenza per comparto, rumore, ventilazione, tubi/valvole, controllo, fail-safe e costo.

### Coda successiva

1. boost/deumidificazione/emergenza;
2. gocciolatori e linee irrigue;
3. filtrazione acqua;
4. pompe principali irrigazione;
5. pompe dosatrici;
6. serbatoi fertilizzanti;
7. accumulo acqua 300 m³;
8. moduli FV e inverter;
9. AMR;
10. sollevatore/mezzo multifunzione;
11. robot tagliaerba;
12. sistema pulizia area galline;
13. celle frigorifere;
14. attrezzatura raccolta e packaging;
15. pergolato/vite/area relax;
16. fattoria didattica;
17. spaccio automatico 24/7;
18. centro trasformazione conto terzi: capacity model + BOM succo/confetture + CAPEX/OPEX + domanda locale.

La sequenza può cambiare quando una dipendenza tecnica rende necessario anticipare un blocco.
