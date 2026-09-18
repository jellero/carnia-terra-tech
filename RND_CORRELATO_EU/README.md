# R&D correlato UE — progetto non-core

**Stato:** `PROGETTO CORRELATO / NON CORE / PRE-CANDIDATURA R&S`  
**Aggiornato:** 18 settembre 2026.

> Questa directory è intenzionalmente fuori dalla numerazione `00_...22_` del progetto principale.
> Il suo contenuto NON modifica la baseline agricola di Carnia TerraTech, NON è necessario per avviare l'azienda e NON deve essere usato per gonfiare il CAPEX core.

## 1. Relazione con Carnia TerraTech

Carnia TerraTech resta il progetto principale: azienda agricola, serra, acqua, energia, logistica, Tech Barn, sicurezza, organizzazione e sostenibilità economica/personale.

Il progetto R&S correlato usa Carnia TerraTech come:

- living lab;
- sito di prototipazione;
- ambiente reale di validazione;
- fonte di requisiti operativi e failure mode;
- primo demonstrator di tecnologie potenzialmente replicabili in altre aziende.

La relazione è quindi:

`CORE AGRICOLO -> requisiti/interfacce -> R&S CORRELATA -> prototipi/validazione`

e non:

`CORE AGRICOLO dipende dalla R&S per poter funzionare`.

## 2. Nome di lavoro

**Carnia TerraTech Autonomous Farm Platform (CTT-AFP)**

Obiettivo: sviluppare e validare una piattaforma modulare di automazione agricola capace di orchestrare software, edge, PLC, robot, computer vision e sistemi energetici mantenendo safety e controllo real-time locali.

Il prodotto R&S non è "la fattoria Carnia TerraTech". Il prodotto candidato è una tecnologia trasferibile e riutilizzabile.

## 3. Perimetro R&S candidato

Aree ammesse al programma di ricerca, da trasformare in work package e verificare per TRL:

- orchestration server e digital state model;
- event ledger e tracciabilità end-to-end;
- scheduler operativo multi-risorsa;
- interoperabilità server/edge/PLC;
- graceful degradation e riconciliazione dopo fault/rete offline;
- fleet orchestration di AMR/robot eterogenei;
- computer vision e sensor fusion;
- scouting e anomaly detection;
- mission planning e docking;
- ottimizzazione coordinata produzione/energia/logistica;
- smart crate + smart cart e reconciliation;
- rover mixed-surface e altri demonstrator robotici sperimentali;
- cybersecurity e osservabilità dell'architettura distribuita.

## 4. Fuori perimetro

Restano nel progetto agricolo principale, salvo una quota sperimentale documentata e ammessa da uno specifico bando:

- acquisto terreno;
- serra standard;
- opere civili ordinarie;
- impianto irriguo commerciale;
- PDC, serbatoi e FV standard;
- macchine acquistate esclusivamente per produzione ordinaria;
- celle e packaging ordinari;
- costi di costituzione e lancio della società;
- capitale circolante dell'azienda agricola;
- normale manutenzione e gestione corrente.

## 5. Regola anti-confusione

Ogni voce collegata alla R&S deve riportare uno dei seguenti stati:

- `RND-CORE-INTERFACE` — requisito/interfaccia proveniente dal core, non costo R&S automatico;
- `RND-RESEARCH` — attività con incertezza tecnico-scientifica reale;
- `RND-PROTOTYPE` — prototipo/test/validazione;
- `RND-DEMONSTRATOR` — uso del living lab per prova in ambiente rilevante;
- `RND-NOT-ELIGIBILITY-ASSESSMENT` — trattamento economico ancora da verificare sul bando;
- `CORE-NON-RND` — rimane integralmente nel progetto principale.

La presenza di un oggetto nel progetto R&S NON implica automaticamente che il suo costo sia finanziabile.

## 6. Documenti

- [AUTONOMOUS_FARM_PLATFORM.md](AUTONOMOUS_FARM_PLATFORM.md) — concept tecnico, work package e demonstrator;
- [FUNDING_AND_COST_BOUNDARY.md](FUNDING_AND_COST_BOUNDARY.md) — separazione costi e canali UE candidati.

## 7. Gate prima di una candidatura

Prima di presentare un progetto europeo devono essere chiusi almeno:

1. novelty statement rispetto allo stato dell'arte;
2. TRL iniziale e finale per ogni tecnologia;
3. research questions e rischi tecnici;
4. work package, deliverable e milestone misurabili;
5. proprietà intellettuale pre-esistente e nuova;
6. partner mancanti;
7. budget separato dal CAPEX agricolo;
8. regole del topic/call specifico;
9. piano di sfruttamento commerciale oltre Carnia TerraTech;
10. dimostrazione che il core agricolo resta operativo anche se la R&S fallisce o ritarda.

## 8. Principio di governo

Il progetto correlato può generare tecnologia utile al core, ma non deve trasformare Carnia TerraTech in un laboratorio incapace di produrre senza prototipi.

**Produzione agricola e sicurezza hanno priorità. La R&S deve essere isolabile, disattivabile e sostituibile con fallback commerciali o manuali.**
