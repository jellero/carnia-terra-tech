# Piano scenari di guasto e recovery

**Aggiornato:** 18 settembre 2026  
**Stato:** `MASTER TEST PLAN / DETTAGLIO NEI DOMINI`

## 1. Scopo

Provare il sistema in condizioni degradate prima che il guasto accada realmente.

## 2. Scenari minimi

### Elettrico
- perdita rete;
- BESS low SOC;
- PCS fault;
- ritorno rete;
- black-start se previsto;
- transfer P0;
- avvio di un motore durante isola.

### Acqua
- source unavailable;
- livello basso;
- duty pump failure;
- filtro intasato;
- sensore portata errato;
- valvola bloccata.

### Termico/clima
- una PDC fuori servizio;
- defrost simultaneo/non previsto;
- pompa zona guasta;
- sensore T/RH errato;
- apertura bloccata;
- evento freddo con capacità ridotta.

### IT/OT
- Internet down;
- server NODE-A down;
- NODE-B down;
- QNODE/edge down;
- switch down;
- perdita DNS/NTP dove rilevante;
- restore backup;
- credenziale/operator access issue.

### Post-raccolta
- cella sopra soglia;
- porta lasciata aperta;
- compressor fault;
- logger/controller disagreement.

### Meccanica/logistica
- telescopico indisponibile;
- accessorio guasto;
- PLE/height-access indisponibile;
- robot ragno R&S bloccato in quota.

### Persone
- promotore assente;
- crop lead assente;
- turno ridotto;
- fornitore non raggiungibile.

## 3. Scheda test

Ogni test registra:
- ID;
- configurazione;
- precondizioni;
- trigger;
- expected state;
- observed state;
- allarmi;
- tempo rilevazione;
- tempo fallback;
- tempo recovery;
- interventi manuali;
- near miss;
- corrective action;
- PASS/FAIL;
- evidenze.

## 4. Regola robot ragno

Un robot bloccato in quota non può richiedere una manovra improvvisata.

Prima del pilot:
- recovery path;
- PLE/piattaforma;
- isolamento;
- area sottostante;
- meteo limite;
- traino/rientro;
- owner.

## 5. Exit gate

Go-live solo se:
- tutti i test P0 PASS;
- P1 critici PASS o hanno azione correttiva chiusa;
- nessun fallback dipende da una persona non sostituibile;
- documentazione e ricambi sono disponibili.
