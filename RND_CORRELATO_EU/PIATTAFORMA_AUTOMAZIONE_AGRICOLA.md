# CTT-PAA — Piattaforma di Automazione Agricola Carnia TerraTech

**Tipo:** progetto R&S correlato, separato dal progetto agricolo principale  
**Stato:** `CONCETTO / DA TRASFORMARE IN PROPOSTA R&S`  
**Aggiornato:** 18 settembre 2026.

## 1. Problema di ricerca

Le aziende agricole ad alta automazione tendono a integrare sottosistemi eterogenei: PLC, sensori, robot, visione artificiale, sistemi energetici, software gestionali e dispositivi commerciali con protocolli e modalità di guasto differenti.

Il problema non è solo "collegare dispositivi". Il tema R&S candidato è come ottenere una piattaforma che:

- mantenga una rappresentazione coerente dello stato operativo;
- pianifichi persone, macchine, colture, energia e logistica;
- coordini robot di fornitori differenti;
- continui a funzionare in modalità degradata quando server, rete o servizi esterni non sono disponibili;
- lasci sicurezza e cicli di controllo in tempo reale ai controlli locali;
- riconcili eventi e stato dopo guasti o disconnessioni;
- usi visione artificiale e fusione sensoriale senza rendere una singola AI punto unico di guasto;
- sia replicabile in aziende differenti.

## 2. Ipotesi tecnologica

Un'architettura a tre livelli può fornire automazione avanzata senza centralizzare impropriamente la sicurezza.

### L0 — sicurezza e controllo locale

PLC, circuiti di sicurezza, protezioni macchina, interblocchi, limiti hardware e ripieghi deterministici.

### L1 — elaborazione periferica e autonomia locale

Verificaway, memoria locale, acquisizione sensori, inferenza locale, adattatori di protocollo, coda comandi e buffer eventi.

### L2 — orchestrazione e governo centrale

Sistema autorevole dei dati, registro eventi, modello digitale dello stato, pianificatore, coordinamento flotte, previsione, pianificazione manutenzione, pianificazione energetica e API.

Principio invariato dal progetto principale:

`server non disponibile != impianto non sicuro`

## 3. Domande di ricerca candidate

RQ1. Come mantenere consistenza operativa fra server centrale, edge e PLC dopo perdita rete, riavvio o eventi duplicati?

RQ2. Come modellare attività, risorse, vincoli agronomici, persone, robot ed energia in un pianificatore unico senza accoppiare il sistema a uno specifico fornitore?

RQ3. Come orchestrare robot eterogenei con modello di capacità, contratto di missione e ripieghi comuni?

RQ4. Quale fusione sensoriale permette di passare da osservazioni probabilistiche a eventi operativi affidabili e verificabili?

RQ5. Come quantificare il beneficio di automazione includendo ore uomo eliminate, qualità, rischio operativo, energia e costo totale di possesso?

RQ6. Come separare decisioni AI da funzioni critiche per la sicurezza mantenendo comunque autonomia utile?

## 4. Pacchetti di lavoro

### PL0 — Stato dell'arte, requisiti e TRL

- confronto scientifico e industriale;
- mappa della novità;
- requisiti dai moduli Carnia TerraTech;
- TRL iniziale/finale per componente;
- modello delle minacce e delle modalità di guasto;
- criteri di completamento R&S.

**Condizione di passaggio:** nessuna candidatura finché la novità non è difendibile.

### PL1 — Architettura di riferimento e modello digitale dello stato

- modello asset/capacità;
- schema eventi;
- correlazione/causalità;
- idempotenza;
- proiezioni dello stato;
- contratti API;
- versionamento;
- verificabilità.

Interfaccia con il progetto principale: `07_AUTOMAZIONE_DATI_AI/CENTRAL_ORCHESTRATION_SERVER.md`.

### PL2 — Interoperabilità edge/PLC e funzionamento degradato controllato

- adattatori e verificaway di protocollo;
- conferma ricezione comandi;
- memorizzazione e inoltro;
- funzionamento senza rete;
- riconciliazione;
- sorveglianza dello stato;
- recupero dopo guasto parziale.

La sicurezza resta fuori dal server R&S.

### PL3 — Orchestrazione autonoma della flotta

- modello capacità robot;
- astrazione delle missioni;
- instradamento e assegnazione attività;
- aggancio/ricarica;
- pianificazione ricarica;
- coordinamento traffico;
- telemetria indipendente dal fornitore;
- stati operativi persona/robot.

Le piattaforme fisiche vengono trattate come banchi prova, non come prodotto finale obbligatorio.

### PL4 — Visione, sensori e fusione sensoriale

- monitoraggio colture;
- rilevazione anomalie;
- localizzazione oggetti/asset;
- fusione massa/visione/posizione;
- modello di confidenza;
- dataset e versionamento;
- inferenza edge;
- conferma umana sulle ambiguità.

### PL5 — Pianificatore multi-risorsa

Vincoli candidati:

- agronomia;
- disponibilità persone;
- robot e batterie;
- irrigazione;
- raccolta;
- celle e capacità post-raccolta;
- manutenzione;
- finestre visitatori;
- FV/BESS/rete;
- priorità e scadenze.

Obiettivo R&S: confrontare regole semplici, metodi di ottimizzazione e metodi assistiti da AI senza rendere l'AI indispensabile alla sicurezza.

### PL6 — Dimostratori nel sito operativo

Carnia TerraTech fornisce ambiente reale di prova. I dimostratori sono indipendenti e possono essere attivati in fasi diverse.

**D1 — Operazioni in serra**
- generazione attività;
- monitoraggio;
- logistica AMR;
- riconciliazione edge/server.

**D2 — Vendita intelligente con fusione sensoriale**
- cassetta intelligente;
- carrello intelligente;
- rilevazione prelievo/restituzione;
- riconciliazione eventi;
- conferma umana;
- interfaccia pagamento separata dalla misura metrologica legale.

**D3 — Ispezione e manutenzione assistita delle parti alte**
- ispezione di copertura, gronde, aperture e attuatori;
- visione per anomalie/manutenzione;
- assistenza operatore da PLE/piattaforma;
- localizzazione del punto di guasto;
- raccolta dati manutentivi;
- eventuali utensili robotici solo dopo analisi rischio.

La capacità di accesso in quota appartiene al core agricolo; l'autonomia robotica della manutenzione resta R&S opzionale.

### PL7 — Affidabilità, cybersicurezza e osservabilità

- controllo accessi basato su ruoli;
- identità per asset;
- segmentazione;
- gestione segreti;
- comandi firmati/validati dove applicabile;
- telemetria;
- tracciamento distribuito;
- ricostruzione incidenti;
- backup/ripristino;
- prove di ripristino da disastro.

### PL8 — Replicabilità e industrializzazione

- modello di configurazione per aziende differenti;
- profilo di installazione;
- adattatori per fornitori;
- licenze e proprietà intellettuale;
- modello di assistenza;
- costo totale di possesso;
- piano di sfruttamento;
- percorso verso prodotto commerciale.

## 5. KPI R&S — da deliberare

Non vengono fissati valori arbitrari prima del protocollo sperimentale.

Famiglie KPI:

- tasso di successo missioni;
- tempo completamento attività;
- tasso di intervento umano;
- accuratezza riconciliazione eventi;
- tempo di ripristino dopo perdita rete/server;
- indisponibilità evitata;
- falsi positivi/negativi della visione;
- energia per missione/attività;
- ore uomo eliminate;
- percentuale di operazioni possibili senza rete;
- portabilità fra fornitori;
- tempo di integrazione di un nuovo asset;
- incidenti/violazioni di sicurezza: obiettivo coerente con l'analisi del rischio, non KPI commerciale.

## 6. TRL

Il repository non assegna un TRL unico alla piattaforma.

Ogni sottosistema deve essere classificato separatamente dopo stato dell'arte e prova disponibile. La candidatura deve dichiarare:

- `TRL_INIZIALE`;
- evidenza del TRL iniziale;
- attività necessarie per avanzare;
- `TRL_FINALE`;
- ambiente di validazione.

Fino a quella valutazione: `TRL DA VERIFICARE`.

## 7. Partner candidati

Ruoli da cercare, non partner già selezionati:

- università/centro di ricerca robotica;
- gruppo AI/visione artificiale;
- integratore OT/PLC;
- produttore AMR/robot o sistemi di ispezione/manutenzione;
- specialista cybersicurezza/edge;
- partner agricoli aggiuntivi per validazione multi-sito;
- eventuale partner economico/gestione innovazione.

Carnia TerraTech: proprietario del caso d'uso, sito operativo reale, requisiti, sperimentazione e validazione operativa.

## 8. Proprietà intellettuale e separazione dal progetto principale

Tre categorie:

- **PI pre-esistente:** tecnologia già esistente prima del progetto;
- **risultati di progetto / nuova PI:** algoritmi, software, dataset, adattatori, meccanismi di orchestrazione e prototipi sviluppati nella R&S;
- **know-how agricolo principale:** configurazioni e processi necessari alla normale conduzione agricola.

L'accordo di consorzio dovrà evitare che l'accesso alla tecnologia R&S renda l'azienda agricola dipendente da proprietà intellettuale non controllabile per funzioni vitali.

## 9. Regola in caso di insuccesso

Un esperimento R&S può fallire.

Il fallimento di un pacchetto di lavoro o dimostratore non deve:

- fermare irrigazione;
- rendere insicura la serra;
- bloccare il controllo climatico minimo;
- impedire operazioni manuali essenziali;
- compromettere produzione già commercialmente impegnata.

Per ogni dimostratore deve esistere un ripiego e una procedura di ritorno alla configurazione precedente.

## 10. Esito atteso

L'esito positivo non è "Carnia TerraTech è automatizzata".

L'esito è una piattaforma e un insieme di componenti dimostrati, misurati e trasferibili, con evidenza tecnica sufficiente per:

- ulteriore R&S;
- industrializzazione;
- concessione in licenza;
- spin-off/prodotto;
- candidatura a strumenti di crescita quando il TRL lo consente.
