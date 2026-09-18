# CTT-AFP — Carnia TerraTech Autonomous Farm Platform

**Tipo:** progetto R&S correlato, separato dal core agricolo  
**Stato:** `CONCEPT / DA TRASFORMARE IN PROPOSTA R&S`  
**Aggiornato:** 18 settembre 2026.

## 1. Problema di ricerca

Le aziende agricole ad alta automazione tendono a integrare sottosistemi eterogenei: PLC, sensori, robot, computer vision, sistemi energetici, software gestionali e dispositivi commerciali con protocolli e failure mode differenti.

Il problema non è solo "collegare dispositivi". Il tema R&S candidato è come ottenere una piattaforma che:

- mantenga una rappresentazione coerente dello stato operativo;
- pianifichi persone, macchine, colture, energia e logistica;
- coordini robot di fornitori differenti;
- continui a funzionare in modalità degradata quando server/rete/cloud non sono disponibili;
- lasci safety e loop real-time ai controlli locali;
- riconcili eventi e stato dopo fault o disconnessioni;
- usi vision e sensor fusion senza rendere una singola AI punto unico di guasto;
- sia replicabile in aziende differenti.

## 2. Ipotesi tecnologica

Una architettura a tre livelli può fornire automazione avanzata senza centralizzare impropriamente la safety:

### L0 — safety e controllo locale

PLC, circuiti di sicurezza, protezioni macchina, interblocchi, limiti hardware e fallback deterministici.

### L1 — edge e autonomia locale

Gateway, cache, acquisizione sensori, inferenza locale, adattatori protocollo, command queue e buffer eventi.

### L2 — orchestration/control plane

System of record, event ledger, digital state model, scheduler, fleet coordination, forecasting, maintenance planning, energy-aware planning e API.

Principio invariato dal core:

`server down != impianto unsafe`

## 3. Research questions candidate

RQ1. Come mantenere consistenza operativa fra server centrale, edge e PLC dopo perdita rete, riavvio o eventi duplicati?

RQ2. Come modellare task, risorse, vincoli agronomici, persone, robot ed energia in uno scheduler unico senza accoppiare il sistema a uno specifico vendor?

RQ3. Come orchestrare robot eterogenei con capability model, mission contract e fallback comuni?

RQ4. Quale sensor fusion permette di passare da osservazioni probabilistiche a eventi operativi affidabili e auditabili?

RQ5. Come quantificare il beneficio di automazione includendo ore uomo eliminate, qualità, rischio operativo, energia e TCO?

RQ6. Come separare decisioni AI da funzioni safety-critical mantenendo comunque autonomia utile?

## 4. Work package di lavoro

### WP0 — Stato dell'arte, requisiti e TRL

- benchmark scientifico e industriale;
- novelty map;
- requisiti dai moduli Carnia TerraTech;
- TRL iniziale/finale per componente;
- threat model e failure model;
- definition of done R&S.

**Gate:** nessuna candidatura finché la novelty non è difendibile.

### WP1 — Reference architecture e digital state model

- asset/capability model;
- event schema;
- correlation/causation;
- idempotency;
- state projections;
- API contracts;
- versioning;
- auditability.

Interfaccia core: `07_AUTOMAZIONE_DATI_AI/CENTRAL_ORCHESTRATION_SERVER.md`.

### WP2 — Edge/PLC interoperability e graceful degradation

- adapters/protocol gateway;
- command acknowledgement;
- store-and-forward;
- offline operation;
- reconciliation;
- watchdog e health model;
- recovery after partial failure.

La safety resta fuori dal server R&S.

### WP3 — Autonomous fleet orchestration

- robot capability model;
- mission abstraction;
- routing/task allocation;
- docking;
- charge scheduling;
- traffic coordination;
- vendor-independent telemetry;
- human/robot operational states.

Possibili piattaforme fisiche vengono trattate come testbed, non come prodotto finale obbligatorio.

### WP4 — Vision, sensing e sensor fusion

- crop scouting;
- anomaly detection;
- object/asset localisation;
- mass/vision/location fusion;
- confidence model;
- dataset/versioning;
- edge inference;
- human confirmation sulle ambiguità.

### WP5 — Multi-resource scheduler

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

Obiettivo R&S: confrontare policy semplici, optimisation-based e AI-assisted senza rendere l'AI indispensabile alla safety.

### WP6 — Demonstrator e living lab

Carnia TerraTech fornisce ambiente reale di test. I demonstrator sono indipendenti e possono essere attivati in fasi diverse.

**D1 — Greenhouse operations**
- task generation;
- scouting;
- AMR logistics;
- edge/server reconciliation.

**D2 — Smart retail sensor fusion**
- smart crate;
- smart cart;
- pick/return detection;
- event reconciliation;
- human confirmation;
- interfaccia payment separata dalla misura metrologica legale.

**D3 — Mixed-surface service robotics**
- rover su superfici dure/prato/ricovero;
- perception;
- path planning;
- safe interaction;
- docking/cleaning workflow.

D3 resta opzionale finché novelty e fattibilità non sono validate.

### WP7 — Reliability, cybersecurity e observability

- RBAC;
- identity per asset;
- segmentazione;
- secrets;
- signed/validated commands dove applicabile;
- telemetry;
- distributed tracing;
- incident reconstruction;
- backup/restore;
- disaster recovery exercises.

### WP8 — Replicabilità e industrializzazione

- configuration model per aziende differenti;
- deployment profile;
- vendor adapters;
- licensing/IP;
- support model;
- TCO;
- exploitation plan;
- percorso verso prodotto commerciale.

## 5. KPI R&S — da deliberare

Non vengono fissati valori arbitrari prima del protocollo sperimentale.

Famiglie KPI:

- mission success rate;
- task completion time;
- intervention rate;
- event reconciliation accuracy;
- recovery time dopo perdita rete/server;
- downtime evitato;
- false positive/negative per vision;
- energia per missione/task;
- ore uomo eliminate;
- percentuale di operazioni possibili offline;
- portabilità fra vendor;
- tempo di integrazione di un nuovo asset;
- incidenti/safety violations: target coerente con analisi del rischio, non KPI commerciale.

## 6. TRL

Il repository non assegna un TRL unico alla piattaforma.

Ogni sottosistema deve essere classificato separatamente dopo stato dell'arte e prova disponibile. La candidatura deve dichiarare:

- `TRL_START`;
- evidenza del TRL iniziale;
- attività necessarie per avanzare;
- `TRL_END`;
- ambiente di validazione.

Fino a quella valutazione: `TRL DA VERIFICARE`.

## 7. Partner candidati

Ruoli da cercare, non partner già selezionati:

- università/centro ricerca robotica;
- gruppo AI/computer vision;
- integratore OT/PLC;
- produttore AMR/robot;
- cybersecurity/edge;
- partner agricoli aggiuntivi per validazione multi-sito;
- eventuale partner economico/innovation management.

Carnia TerraTech: use-case owner, living lab, requisiti, sperimentazione e validazione operativa.

## 8. IP e separazione dal core

Tre categorie:

- **Background IP:** tecnologia già esistente prima del progetto;
- **Project results / foreground:** algoritmi, software, dataset, adapters, meccanismi di orchestrazione e prototipi sviluppati nella R&S;
- **Core farm know-how:** configurazioni e processi necessari alla normale conduzione agricola.

L'accordo di consorzio dovrà evitare che l'accesso alla tecnologia R&S renda l'azienda agricola dipendente da IP non controllabile per funzioni vitali.

## 9. Failure rule

Un esperimento R&S può fallire.

Il fallimento di un WP o demonstrator non deve:

- fermare irrigazione;
- rendere insicura la serra;
- bloccare il controllo climatico minimo;
- impedire operazioni manuali essenziali;
- compromettere produzione già commercialmente impegnata.

Per ogni demonstrator deve esistere un rollback/fallback.

## 10. Esito atteso

L'esito positivo non è "Carnia TerraTech è automatizzata".

L'esito è una piattaforma e un insieme di componenti dimostrati, misurati e trasferibili, con evidenza tecnica sufficiente per:

- ulteriore R&S;
- industrializzazione;
- licensing;
- spin-off/prodotto;
- candidatura a strumenti di scale-up quando il TRL lo consente.
