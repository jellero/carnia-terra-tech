# PDC modulari 3+1 — Kensol KHP-R290-22-3

**Aggiornato:** 17 settembre 2026  
**Stato:** `CANDIDATO REALE / DATI A7-A2 VERIFICATI / A-7 E CASCATA DA CONFERMARE OEM`.

## 1. Ruolo nel progetto

Working concept:

- 3 unità KHP-R290-22-3 installate inizialmente;
- predisposizione idraulica/elettrica/logica per una quarta unità;
- accumulo termico come disaccoppiamento energetico;
- primario corto protetto dal gelo;
- controllo locale e orchestrazione PLC/EMS senza dipendenza cloud.

La dicitura `3+1` non significa automaticamente N+1: se la quarta unità non è installata, il sistema iniziale ha tre generatori reali, non tre più uno di riserva.

## 2. Dati verificati — scheda tecnica corrente

Kensol/KENO KHP-R290-22-3:

- alimentazione: 380–415 V / 3N / 50 Hz;
- refrigerante: R290, carica 1,30 kg;
- IPX4;
- compressore: HIGHLY;
- pompa di circolazione integrata: SHIMGE;
- 2 ventilatori DC;
- campo ambiente dichiarato: -25…+43 °C;
- attacchi acqua: 1";
- peso netto: 202 kg;
- dimensioni nette: 1250 × 540 × 1330 mm;
- dimensioni imballo: 1380 × 570 × 1480 mm;
- pressione sonora a 1 m: 47 dB(A);
- potenza sonora EN 12102: 62 dB(A);
- protezione consigliata nella scheda: C16A.

### A7/W35

Condizioni: aria 7/6 °C, acqua 30/35 °C.

- capacità: 7,80–22,00 kW;
- assorbimento: 1,48–5,90 kW;
- COP: 3,73–5,27.

### A2/W35

Condizioni: aria 2 °C, acqua 30/35 °C.

- capacità: 6,69–18,80 kW;
- assorbimento: 1,45–5,50 kW;
- COP: 3,42–4,61.

### Dati stagionali

- SCOP W35, clima temperato: 5,13;
- SCOP W55, clima temperato: 3,84;
- massima potenza elettrica dichiarata: 9 kW;
- massimo assorbimento: 15,8 A;
- portata acqua nominale: 2,9 m³/h;
- massima perdita interna acqua: 65 kPa;
- prevalenza pompa integrata alla portata nominale: 100 kPa.

## 3. Conseguenze della temperatura esterna

La potenza 22 kW è un dato A7/W35, non una potenza garantita a qualunque temperatura.

Capacità massima aggregata dai dati pubblicati:

| Configurazione | A7/W35 | A2/W35 |
|---|---:|---:|
| 1 unità | 22,0 kW | 18,8 kW |
| 2 unità | 44,0 kW | 37,6 kW |
| 3 unità | 66,0 kW | 56,4 kW |
| 4 unità | 88,0 kW | 75,2 kW |

Quindi tra A7 e A2 la capacità massima pubblicata cala di circa il 14,5%.

**Il datasheet pubblico esaminato non contiene A-7/W35 né A-7/W45.** Per Carnia TerraTech questi punti sono obbligatori prima di validare 3 o 4 unità.

## 4. Modularità e capacità minima

Con staging corretto si deve accendere il minor numero di unità compatibile col carico.

Capacità minima pubblicata di una sola unità:

- A7/W35: 7,8 kW;
- A2/W35: 6,69 kW.

Non si devono tenere tre PDC contemporaneamente al minimo se una sola può coprire il carico. Il PLC/controllore di cascata deve gestire:

- lead/lag;
- rotazione ore macchina;
- avvio progressivo;
- isteresi anti-ciclo;
- priorità carica accumulo;
- blocco singola unità guasta;
- derating e allarmi;
- richiesta potenza/temperatura coerente con stato accumulo.

## 5. Ridondanza reale

### Tre unità installate

In guasto singolo restano:

- 44 kW max A7/W35;
- 37,6 kW max A2/W35.

Questa non è ridondanza N+1 se il carico critico supera tali valori.

### Quattro unità installate

Con una unità fuori servizio restano tre unità:

- 66 kW max A7/W35;
- 56,4 kW max A2/W35.

La decisione installare subito la quarta oppure solo predisporla sarà presa confrontando:

- carico sopravvivenza;
- carico produzione;
- prestazione reale a -7/-10/-15 °C;
- costo quarto modulo;
- costo del fermo;
- contributi;
- potenza elettrica disponibile.

## 6. Idraulica integrata

La scheda corrente conferma una pompa SHIMGE integrata.

Dati pubblicati:

- portata nominale 2,9 m³/h per unità;
- prevalenza pompa a portata nominale 100 kPa;
- perdita interna massima 65 kPa.

La differenza aritmetica è 35 kPa, ma **non viene assunta come prevalenza residua garantita all'impianto** senza curva OEM e chiarimento del metodo di misura.

Portata nominale aggregata:

- 3 unità: 8,7 m³/h;
- 4 unità: 11,6 m³/h.

Prima di aggiungere pompe esterne serve la curva Q/H ufficiale della pompa integrata e il punto di lavoro con glicole, HX, filtri, valvole e tubazioni reali.

## 7. Discrepanze documentali da chiudere

Esistono differenze tra la scheda tecnica corrente e il manuale KHP-R290 codice 6/26.

Per la 22 kW:

| Parametro | Scheda corrente | Manuale 6/26 |
|---|---:|---:|
| max assorbimento riscaldamento A7/W35 | 5,90 kW | 6,90 kW |
| perdita interna acqua | 65 kPa | 45 kPa |
| prevalenza pompa | 100 kPa | 6,9 m (~67,7 kPa) |
| rumore | 47 dB(A) pressione / 62 dB(A) potenza | 42–54 dB(A) generico |

Queste differenze possono derivare da revisione hardware, metodo di misura o documenti non allineati. Prima dell'ordine il fornitore deve identificare la revisione esatta offerta e fornire dati coerenti per matricola/versione.

## 8. Dati A-7 e sbrinamento

Per validare la taglia servono almeno, a pieno e parziale carico quando disponibili:

- A7/W35, A7/W45;
- A2/W35, A2/W45;
- A-2/W35, A-2/W45;
- A-7/W35, A-7/W45;
- A-10/W35, A-10/W45;
- A-15/W35 e scenario sopravvivenza.

Per ogni punto chiedere:

- capacità termica;
- assorbimento elettrico;
- COP;
- portata richiesta;
- frequenza/energia persa per defrost;
- capacità netta media comprensiva di sbrinamenti;
- limiti operativi e di mandata acqua.

Non usare il solo campo `-25…43 °C` come prova della capacità utile a -25 °C.

## 9. Elettrico

Ordine di grandezza dalla massima potenza elettrica dichiarata:

- 3 unità: fino a 27 kW di potenza elettrica nominale massima aggregata dichiarata;
- 4 unità: fino a 36 kW.

Ogni unità deve avere almeno:

- linea dedicata;
- sezionamento locale;
- protezioni coordinate col manuale, targa e normativa italiana;
- misura energia individuale o per ramo;
- SPD/protezioni secondo progetto elettrico;
- segnalazione stato/allarme al PLC.

La scheda corrente indica C16A, mentre il manuale contiene tabelle generiche di cablaggio/protezioni: il dimensionamento finale deve essere confermato dall'installatore elettrico e dal costruttore sulla revisione effettivamente acquistata.

## 10. Installazione esterna e R290

Il manuale della serie KHP-R290 richiede:

- installazione esterna ventilata;
- base robusta e livellata;
- drenaggio condensa vicino all'unità;
- assenza di ostacoli a ingresso/uscita aria;
- evitare forti raffiche dirette;
- distanza da fonti di calore e potenziali fonti di ignizione;
- spazio manutenzione.

Clearance minime rappresentate nel manuale per unità con uscita aria orizzontale:

- lato A ingresso: >500 mm;
- lato B uscita: >1500 mm;
- lato C servizio: >1000 mm;
- lato D: >500 mm.

Il progetto definitivo deve verificare inoltre interazione tra quattro unità, ricircolo aria fredda, neve, ghiaccio, condensa, accesso manutenzione e requisiti applicabili al refrigerante R290.

## 11. Controllo e integrazione

Il manuale mostra controllore cablato e interfacce di comando, ma la capacità di gestire una vera cascata 3–4 unità non viene assunta senza documentazione OEM.

Richiedere:

- interfaccia Modbus/RS485 o altro protocollo disponibile;
- mappa registri;
- setpoint remoto;
- enable/disable;
- stato compressore;
- frequenza/potenza richiesta se disponibile;
- T ingresso/uscita;
- stato pompa;
- allarme e codice errore;
- stato defrost;
- limitazione potenza;
- eventuale funzione cascade OEM e numero massimo unità.

Il PLC Carnia TerraTech deve poter gestire il sistema localmente senza dipendenza Internet.

## 12. Prezzo

Prezzo osservato 17/09/2026:

- Senetic DE: €3.616,74 + IVA/unità;
- Idealo IT / Senetic: ~€4.412,42 IVA inclusa/unità.

Solo hardware PDC:

- 3 unità: €10.850,22 + IVA; circa €13.237,26 IVA 22% inclusa;
- 4 unità: €14.466,96 + IVA; circa €17.649,68 IVA 22% inclusa.

Esclusi: trasporto, antivibranti, basamenti, idraulica, glicole, HX, accumulo, elettrico, quadro, controllo, commissioning e assistenza.

## 13. Garanzia e assistenza

La scheda commerciale riporta `5+2 anni di garanzia`, ma le condizioni dell'estensione devono essere acquisite per iscritto.

Senetic avverte che, per mantenere la garanzia del produttore, l'installazione deve essere eseguita da installatore autorizzato dal produttore.

Prima di ordinare servono:

- condizioni di garanzia valide in Italia;
- soggetto che effettua il primo avviamento;
- rete assistenza disponibile per FVG;
- SLA/tempi ricambi;
- prezzo ricambi critici;
- condizioni per estensione +2 anni;
- impatto di integrazione PLC esterna sulla garanzia.

## 14. Gate

Il candidato passa da `CANDIDATO` a `VALIDATO` solo dopo:

1. curva prestazionale a freddo e W35/W45;
2. dati defrost netti;
3. chiarimento ufficiale delle discrepanze documentali;
4. curva pompa integrata e prevalenza residua;
5. conferma cascade/Modbus;
6. carico termico Carnia TerraTech;
7. verifica potenza elettrica disponibile;
8. layout R290/acustico/condensa;
9. garanzia e assistenza Italia;
10. offerta 3 unità + opzione quarta confrontabile.
