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
- `03_SERRA/` — struttura, comparti, coperture, aperture, schermi, HAF, fogging, supporti coltura e drenaggi;
- `04_ACQUA_E_FERTIRRIGAZIONE/` — fonte, accumulo, filtri, pompe, dosaggio, drenaggio;
- `05_TERMICO_E_CLIMA/` — PDC, accumulo, distribuzione, deumidificazione, emergenza;
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

**Stato: RAFFINATO COME ARCHITETTURA / BOM PRINCIPALI IN SVILUPPO / DIMENSIONAMENTO BLOCCATO DAL LOTTO E DALLE CROP CARD.**

Documenti principali includono struttura/fondazioni, copertura, aperture/reti, schermi, fogging, supporti coltura/logistica, manutenzione/sicurezza e relativi RFQ.

Package/BOM sviluppati:

- **BOM-001 — HAF**: `19_BOM_PRODOTTI_FORNITORI/SERRA_HAF_VENTILATION.md`;
- **BOM-002 — schermi climatici**: `19_BOM_PRODOTTI_FORNITORI/SERRA_SCHERMI_TERMICI_OMBREGGIANTI.md`;
- **BOM-003 — aperture/attuatori/reti**: `19_BOM_PRODOTTI_FORNITORI/SERRA_APERTURE_RETI_ANTIINSETTO.md`;
- **BOM-004 — copertura/film/fissaggi**: `19_BOM_PRODOTTI_FORNITORI/SERRA_COPERTURA_FILM_FISSAGGI.md`;
- **package struttura/fondazioni**: `19_BOM_PRODOTTI_FORNITORI/SERRA_STRUTTURA_FONDAZIONI.md`;
- **BOM-005 — fogging**: `19_BOM_PRODOTTI_FORNITORI/SERRA_FOGGING.md`;
- **BOM-006 — supporti coltura + drenaggio**: `19_BOM_PRODOTTI_FORNITORI/SERRA_SUPPORTI_COLTURA_DRENAGGIO.md`.

RFQ BOM-006: `03_SERRA/RFQ_CROP_SUPPORT_DRAINAGE.md`.

### BOM-006 — stato corrente

Sono separati e prezzati dove possibile:

- filo/cavo high-wire e ancoraggi;
- hook/roller;
- spago PP o biodegradabile;
- clip PP o biodegradabili;
- gutter/canaline;
- staffe, giunti, terminali e scarichi;
- collettore drenaggio;
- lavaggio/ispezione;
- sensori volume/EC/pH/T come interfaccia col punto 04.

Benchmark correnti registrati:

- ReelHook 30 m: €7,01 + IVA/cad prima degli sconti quantità;
- ECOTWINE 400 N ~3.350 m: €54,70–62,70 + IVA/bobina;
- Bato clip 22 mm: €77,50 + IVA/10.000;
- clip biodegradabile 22 mm: €30,95 + IVA/1.000;
- gutter professionale metallico: `PREZZO DA PREVENTIVO`;
- canaline plastiche/NFT: benchmark pubblici solo per confronto, non baseline C1/C2.

Le quantità restano correttamente aperte finché non sono definiti steli/m², file/lunghezze, sistema lowering, slab e pendenze.

Il punto 03 diventa `VALIDATO` solo dopo lotto, carichi reali, geotecnica, layout esecutivo, crop card, analisi acqua e preventivi confrontabili.

## 7. R&D trasversale — laser, vision e manutenzione robotica

Documento: `07_AUTOMAZIONE_DATI_AI/LASER_ROBOTICS_RND.md`.

Stato: `R&D CANDIDATO / NON BASELINE CAPEX`.

Linee correnti: potatura robotica con visione e microforbice/cutter come baseline R&D; laser solo confinato; controllo insetti laser solo con classificazione `TARGET / UTILE-PROTETTO / INCERTO` e nessuna attivazione su incerto.

## 8. Modulo futuro — centro trasformazione conto terzi

Documento: `09_TECH_BARN_E_POST_RACCOLTA/CENTRO_TRASFORMAZIONE_CONTO_TERZI.md`.

Stato: `MODULO FUTURO AD ALTO POTENZIALE / DA BUSINESS CASE / NON ANCORA NEL CAPEX BASE`.

Perimetro: mele, pere, piccoli frutti, succhi, puree, confetture/composte; lavoro proprio e conto terzi; tariffa, compensazione in prodotto, acquisto materia prima o modello ibrido. Il masterplan deve predisporre spazio e utilities senza obbligare l'acquisto iniziale.

## 9. Metodo BOM obbligatorio

Per ogni oggetto o sottosistema si analizzano funzione, requisiti, quantità, alternative, prezzo, IVA/trasporto, installazione, consumi, manutenzione, ricambi, vita utile, sicurezza, failure mode, fallback, contributi, dipendenze, espansione e stato decisionale.

## 10. Stato attuale dei grandi blocchi

I file in `docs/` restano sorgenti durante la migrazione. Sono nel perimetro robot tagliaerba, automazione area galline, fattoria didattica, spaccio 24/7, pergolati/vite/verde/relax, sostenibilità personale, R&D robotica/laser e centro trasformazione conto terzi.

## 11. Sequenza BOM

### Candidati/package già sviluppati

- BOM-001 HAF;
- BOM-002 schermi;
- BOM-003 aperture/reti;
- BOM-004 copertura;
- struttura/fondazioni: package economico + RFQ;
- BOM-005 fogging + RFQ;
- BOM-006 supporti coltura + drenaggio + RFQ.

### In lavorazione successiva

**Porte + compartimentazioni interne + gronde/pluviali:** accessi persone, logistica/AMR, divisori tra comparti, sigillature, gronde, pluviali, troppo-pieni, manutenzione e collegamento ai 300 m³ di accumulo acqua.

### Coda immediata

1. porte/compartimenti/gronde/pluviali;
2. attrezzatura e consumabili montaggio;
3. chiusura punto 03 / matrice costi aperti;
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
21. spaccio automatico 24/7;
22. centro trasformazione conto terzi: capacity model + BOM succo/confetture + CAPEX/OPEX + domanda locale.

La sequenza può cambiare quando una dipendenza tecnica rende necessario anticipare un blocco.
