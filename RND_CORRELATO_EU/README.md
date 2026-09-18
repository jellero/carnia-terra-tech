# R&S correlata UE — progetto separato dal progetto principale

**Stato:** `PROGETTO CORRELATO / NON PRINCIPALE / PRE-CANDIDATURA R&S`  
**Aggiornato:** 18 settembre 2026.

> Questa directory è intenzionalmente fuori dalla numerazione `00_...22_` del progetto principale.
> Il suo contenuto NON modifica la configurazione base agricola di Carnia TerraTech, NON è necessario per avviare l'azienda e NON deve essere usato per trasferire artificiosamente costi dal progetto principale alla R&S.

## 1. Relazione con Carnia TerraTech

Carnia TerraTech resta il progetto principale: azienda agricola, serra, acqua, energia, logistica, Tech Barn, sicurezza, organizzazione e sostenibilità economica/personale.

Il progetto R&S correlato usa Carnia TerraTech come:

- laboratorio operativo reale;
- sito di prototipazione;
- ambiente reale di validazione;
- fonte di requisiti operativi e modalità di guasto;
- primo dimostratore di tecnologie potenzialmente replicabili in altre aziende.

La relazione è quindi:

`PROGETTO PRINCIPALE -> requisiti/interfacce -> R&S CORRELATA -> prototipi/validazione`

e non:

`PROGETTO PRINCIPALE dipende dalla R&S per poter funzionare`.

## 2. Nome di lavoro

**CTT-PAA — Piattaforma di Automazione Agricola Carnia TerraTech**

Obiettivo: sviluppare e validare una piattaforma modulare di automazione agricola capace di coordinare software, elaborazione periferica (edge), PLC, robot, visione artificiale e sistemi energetici mantenendo sicurezza e controllo in tempo reale a livello locale.

Il prodotto R&S non è "la fattoria Carnia TerraTech". Il prodotto candidato è una tecnologia trasferibile e riutilizzabile.

## 3. Perimetro R&S candidato

Aree candidate, da trasformare in pacchetti di lavoro e verificare per TRL:

- server di orchestrazione e modello digitale dello stato;
- registro eventi e tracciabilità completa;
- pianificatore operativo multi-risorsa;
- interoperabilità server/edge/PLC;
- funzionamento degradato controllato e riconciliazione dopo guasti o perdita rete;
- orchestrazione di flotte AMR/robot eterogenei;
- visione artificiale e fusione sensoriale;
- monitoraggio colture e rilevazione anomalie;
- pianificazione missioni e ricarica/aggancio;
- ottimizzazione coordinata produzione/energia/logistica;
- cassetta intelligente + carrello intelligente e riconciliazione eventi;
- rover su superfici miste e altri dimostratori robotici sperimentali;
- cybersicurezza e osservabilità dell'architettura distribuita.

## 4. Fuori perimetro

Restano nel progetto agricolo principale, salvo quota sperimentale documentata e ammessa da uno specifico bando:

- acquisto terreno;
- serra standard;
- opere civili ordinarie;
- impianto irriguo commerciale;
- PDC, serbatoi e FV standard;
- macchine acquistate esclusivamente per produzione ordinaria;
- celle e confezionamento ordinari;
- costi di costituzione e lancio della società;
- capitale circolante dell'azienda agricola;
- normale manutenzione e gestione corrente.

## 5. Regola anti-confusione

Ogni voce collegata alla R&S deve riportare uno dei seguenti stati:

- `RND-INTERFACCIA-PRINCIPALE` — requisito/interfaccia proveniente dal progetto principale, non costo R&S automatico;
- `RND-RICERCA` — attività con incertezza tecnico-scientifica reale;
- `RND-PROTOTIPO` — prototipo/prova/validazione;
- `RND-DIMOSTRATORE` — uso del sito reale per prova in ambiente rilevante;
- `RND-AMMISSIBILITA-DA-VERIFICARE` — trattamento economico ancora da verificare sul bando;
- `PRINCIPALE-NON-RND` — rimane integralmente nel progetto principale.

La presenza di un oggetto nel progetto R&S NON implica automaticamente che il suo costo sia finanziabile.

## 6. Documenti

- [PIATTAFORMA_AUTOMAZIONE_AGRICOLA.md](PIATTAFORMA_AUTOMAZIONE_AGRICOLA.md) — concetto tecnico, pacchetti di lavoro e dimostratori;
- [FINANZIAMENTI_E_CONFINI_DI_COSTO.md](FINANZIAMENTI_E_CONFINI_DI_COSTO.md) — separazione costi e canali UE candidati;
- [COLLEGAMENTI_UE_RND.md](COLLEGAMENTI_UE_RND.md) — portali ufficiali, ricerca bandi, programmi di lavoro, CORDIS, NCP, assistenza IP ed EIC.

## 7. Condizioni prima di una candidatura

Prima di presentare un progetto europeo devono essere chiusi almeno:

1. dichiarazione di novità rispetto allo stato dell'arte;
2. TRL iniziale e finale per ogni tecnologia;
3. domande di ricerca e rischi tecnici;
4. pacchetti di lavoro, risultati attesi e traguardi misurabili;
5. proprietà intellettuale pre-esistente e nuova;
6. partner mancanti;
7. budget separato dal CAPEX agricolo;
8. regole del bando e del tema specifico;
9. piano di sfruttamento commerciale oltre Carnia TerraTech;
10. dimostrazione che il progetto agricolo principale resta operativo anche se la R&S fallisce o ritarda.

## 8. Principio di governo

Il progetto correlato può generare tecnologia utile al progetto principale, ma non deve trasformare Carnia TerraTech in un laboratorio incapace di produrre senza prototipi.

**Produzione agricola e sicurezza hanno priorità. La R&S deve essere isolabile, disattivabile e sostituibile con soluzioni commerciali o manuali di emergenza.**
