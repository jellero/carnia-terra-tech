# Carnia TerraTech — Laser & Robotic Crop Maintenance R&D

**Aggiornato:** 17 settembre 2026  
**Stato:** `R&D CANDIDATO / NON BASELINE CAPEX / DA VALIDARE CON TEST E SICUREZZA`.

## 1. Obiettivo

Valutare tecnologie di visione, robotica e laser per ridurre lavoro manuale ripetitivo e fitofarmaci, senza introdurre rischi incompatibili con la filosofia Carnia TerraTech.

Due use case distinti:

1. manutenzione selettiva delle piante (es. eliminazione femminelle/succhioni del pomodoro);
2. controllo selettivo di insetti volanti dannosi in serra.

I due casi non condividono automaticamente lo stesso attuatore o la stessa architettura di sicurezza.

## 2. Potatura/femminelle pomodoro

### Stato tecnico

La computer vision per riconoscere rami laterali e punti di potatura è già oggetto di ricerca avanzata. Nel 2026 è stato pubblicato un metodo per pomodoro in serra con successo di localizzazione del punto di potatura intorno al 92%.

Fonte:
- https://www.sciencedirect.com/science/article/pii/S2772375525009700

### Baseline Carnia TerraTech

Baseline da valutare prima del laser:

`RGB/RGB-D + manipolatore leggero + end-effector meccanico (microforbice/cutter) + visione di verifica del taglio`.

Motivi:

- contatto e risultato più facilmente verificabili;
- minore rischio ottico;
- minore rischio di carbonizzazione/danno termico al tessuto adiacente;
- manutenzione e certificazione potenzialmente più semplici;
- possibilità di usare la stessa piattaforma per scouting e altre operazioni.

### Laser come R&D

Il laser può essere sperimentato solo come attuatore confinato in una testina interbloccata o altra architettura che impedisca emissione accessibile durante il funzionamento normale.

Prima di considerarlo superiore alla microforbice servono prove su:

- precisione del punto di recisione;
- qualità/cicatrizzazione del taglio;
- danno termico al fusto principale o foglie vicine;
- velocità ciclo;
- consumo;
- sporco su ottica;
- rischio incendio;
- comportamento con acqua/condensa;
- manutenzione;
- sicurezza operatori/visitatori/animali;
- costo per ora di lavoro eliminata.

## 3. Controllo insetti volanti con laser

### Stato tecnico

La tecnologia è reale ma non ancora baseline commerciale consolidata per una serra come Carnia TerraTech.

Wageningen University & Research ha pubblicato nel 2025 risultati di ricerca su laser in serra contro tripidi, includendo una barriera laser presso le aperture di ventilazione e scansione mirata sulle piante. Il progetto L.I.G.H.T. prosegue nel periodo 2025–2027.

Fonti:
- https://research.wur.nl/en/publications/starwars-the-use-of-lasers-for-indoor-pest-control/
- https://research.wur.nl/en/projects/lwv22019-lasers-in-greenhouses-and-horticulture-against-thrips-an-2/

Il progetto Intellectual Ventures / Photonic Fence dimostra da anni il principio di identificazione e abbattimento di insetti in volo. Nel 2026 esistono anche prodotti/preordini consumer/prosumer che dichiarano rilevamento LiDAR e abbattimento laser delle zanzare, ma Carnia TerraTech non li considera prova sufficiente di affidabilità agricola o sicurezza per una serra professionale.

Riferimenti:
- https://www.intellectualventures.com/what-we-do
- https://store.photonmatrixlab.com/

### Architettura preferita da esplorare

Ordine di preferenza R&D:

1. **barriera/portale confinato sulle aperture di ventilazione o ingressi**;
2. **trappola attrattiva chiusa con identificazione + trattamento laser**;
3. scansione selettiva della vegetazione solo in condizioni controllate e con sicurezza dimostrata;
4. evitare una torretta laser libera che attraversi il volume di lavoro della serra.

Vantaggio dell'architettura su aperture/trappola: il bersaglio passa in una zona geometrica nota, più facile da schermare e interbloccare.

## 4. Non "tutto ciò che vola tranne le api"

Il classificatore deve lavorare con una **whitelist/blacklist biologica**, non con la regola generica `non-api = dannoso`.

Tra gli organismi utili possono esserci, a seconda del piano IPM:

- api;
- bombi impollinatori;
- sirfidi;
- vespe/parassitoidi utili;
- altri predatori o insetti introdotti per lotta biologica.

Il sistema deve quindi distinguere almeno:

`TARGET DANNO | UTILE/PROTETTO | INCERTO`.

Regola fail-safe: **se la classificazione è incerta, non attivare l'attuatore** e registrare immagine/evento per il training successivo.

## 5. Integrazione con IPM

Il laser non sostituisce automaticamente reti, scouting e lotta biologica.

Possibile ruolo:

- ridurre pressione di ingresso sulle aperture;
- trattare hotspot;
- contare automaticamente popolazioni;
- generare mappe temporali/zone di infestazione;
- attivare interventi biologici o meccanici mirati;
- ridurre trattamenti chimici quando tecnicamente dimostrato.

La telemetria deve confluire nel sistema dati Carnia TerraTech: specie/classificazione, timestamp, zona, confidenza, immagine di verifica, esito intervento e trend popolazione.

## 6. Sicurezza — requisito non negoziabile

Non progettare un sistema open-beam accessibile a operatori, visitatori, animali o mezzi.

Requisiti di principio:

- emissione confinata o schermata;
- interblocchi hardware indipendenti dal software AI;
- arresto sicuro se porta/pannello/protezione è aperto;
- nessuna attivazione con persona/animale nel volume protetto;
- controllo locale fail-safe;
- arresto di emergenza;
- log eventi e fault;
- validazione e certificazione professionale del prodotto/sistema laser;
- procedure specifiche per manutenzione ottica/elettrica.

La progettazione dettagliata dei parametri laser non rientra nel fai-da-te del progetto: usare componenti/sistemi professionali e validazione specialistica.

## 7. Roadmap R&D proposta

### R1 — dataset e classificazione

Usare le telecamere previste per costruire dataset di:

- femminelle/punti di potatura;
- tripidi;
- mosche bianche;
- afidi alati;
- moscerini;
- impollinatori e insetti utili.

### R2 — potatura meccanica robotica

Prototipo con manipolatore + cutter confinato, prima del laser.

### R3 — insect monitoring intelligente

Trappola/camera automatica che conta e classifica senza abbattimento.

### R4 — modulo laser confinato

Solo dopo sufficiente precisione del classificatore e con progetto sicurezza dedicato.

### R5 — pilot limitato

Una sola zona/portale, KPI:

- precisione classificazione;
- falsi positivi sugli utili;
- efficacia sul target;
- ore uomo risparmiate;
- riduzione trattamenti;
- downtime/manutenzione;
- costo per insetto target / per m² / per ora lavoro eliminata.

## 8. Decisione corrente

- **Potatura femminelle:** `R&D SI`, baseline meccanica robotizzata; laser solo candidato futuro.
- **Insetti volanti:** `R&D PRIORITARIO`, specialmente barriera confinata su prese/aperture o trappola chiusa.
- **Sistema laser libero nel volume serra:** `NO COME BASELINE`.
- **Esclusione api soltanto:** insufficiente; serve protezione di tutti gli insetti utili del piano IPM.

Nessun costo viene ancora inserito nel CAPEX base. Creare BOM specifica solo quando esiste un prodotto/fornitore professionale o un pilot definito.