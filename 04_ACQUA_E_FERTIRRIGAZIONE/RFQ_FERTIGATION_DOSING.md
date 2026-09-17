# RFQ — Fertirrigazione A/B/acido

**Data:** 17 settembre 2026  
**Oggetto:** fornitura componenti e supporto al dimensionamento di fertirrigazione modulare PLC-based per serra 6 comparti.

## 1. Architettura richiesta

Offerta separata per:

- canale A;
- canale B;
- canale acido;
- predisposizione quarto canale;
- iniezione e non ritorno;
- miscelazione;
- misura pH/EC/T;
- calibrazione;
- cablaggio/interfaccia PLC;
- commissioning;
- ricambi.

Il sistema non deve richiedere cloud o controller proprietario per le funzioni vitali.

## 2. Dati che il fornitore deve dichiarare per ogni pompa

- marca/modello/codice completo;
- portata min/max alla pressione reale;
- curva portata/pressione;
- turndown utile e accuratezza/ripetibilità;
- frequenza massima;
- materiali testa, membrana, sfere, sedi, guarnizioni;
- compatibilità chimica certificata per i prodotti che comunicheremo;
- alimentazione e potenza;
- IP;
- ingresso 4–20 mA;
- ingressi impulsi/flow sensor;
- uscite allarme/stato;
- diagnostica dry-run/underload/overpressure;
- valvola sfiato/degasaggio;
- kit installazione incluso/escluso;
- garanzia;
- ricambi e lead time.

Quotare almeno una configurazione economica e una industriale con diagnostica completa.

## 3. Componenti per canale — quotare separatamente

- pompa dosatrice;
- lancia aspirazione;
- filtro/valvola di fondo;
- sensore livello;
- tubo aspirazione;
- tubo mandata;
- valvola iniezione/check;
- valvola contropressione;
- relief/pressure safety se richiesta;
- valvole isolamento;
- raccordi/unioni;
- colonna calibrazione;
- flow verification se disponibile;
- supporti;
- ricambi iniziali.

## 4. pH/EC

Quotare due alternative:

### M1 — trasmettitore combinato

- pH + EC + compensazione T;
- due uscite 4–20 mA isolate o equivalente;
- sonde in linea;
- portasonde/cella;
- valvole isolamento;
- standard di calibrazione;
- elettrodo pH di scorta.

### M2 — trasmettitori separati

- pH industriale;
- EC 4-elettrodi/4-anelli o tecnologia equivalente;
- T;
- segnali standard verso PLC.

Dichiarare accuratezza, range, pressione, temperatura, materiali, vita attesa elettrodi, manutenzione, frequenza calibrazione raccomandata e costo ricambi.

## 5. Miscelazione

Proporre e dimensionare:

- punti iniezione;
- distanza minima fra A/B/acido;
- static mixer se richiesto;
- volume/tempo di residenza;
- cella campionamento pH/EC;
- perdita di carico.

Non è accettabile una soluzione che permetta il contatto diretto dei concentrati prima della diluizione.

## 6. Controllo/interlock

Il sistema deve accettare controllo da PLC locale e permettere almeno:

- enable/disable canale;
- comando proporzionale;
- stato marcia;
- allarme generale;
- eventuale feedback portata dosata.

Interlock richiesti:

- assenza portata acqua;
- livello basso;
- pH/EC sensor fault;
- EC high;
- pH hard limit;
- leak/spill alarm;
- pompa fault;
- watchdog.

## 7. Scenari da quotare

- S1: A/B 15–20 l/h + acido 5–10 l/h;
- S2: A/B 30 l/h + acido 5–10 l/h;
- S3: soluzione superiore se le nostre ricette richiedono >30 l/h/canale.

Le portate sono scenari RFQ, non quantità già selezionate.

## 8. Commissioning

Includere:

- verifica tenuta;
- calibrazione pompe a più punti;
- verifica q reale a contropressione reale;
- calibrazione pH/EC;
- test no-flow/no-dose;
- test low-level;
- test sensore guasto;
- test over-dose limit;
- verifica miscelazione/tempo di risposta;
- test modalità manuale;
- as-built e parametri PLC.

## 9. Formato economico

Separare:

- hardware;
- sensori;
- accessori idraulici;
- quadro/cablaggio;
- installazione;
- commissioning;
- trasporto;
- ricambi;
- manutenzione annua consigliata;
- IVA;
- validità offerta;
- tempi consegna.