# RFQ — PDC modulari 3+1

**Ambito:** Carnia TerraTech, serra ~4.200 m², accumulo termico 30 m³ espandibile 40–50 m³, distribuzione a 6 comparti.

## 1. Fornitura richiesta

Quotare separatamente:

- 3 × Kensol KHP-R290-22-3;
- opzione 4ª unità acquistata subito;
- opzione predisposizione completa per 4ª unità acquistata in fase 2;
- trasporto;
- primo avviamento/commissioning;
- eventuale estensione garanzia;
- accessori obbligatori;
- controller/interfacce dati;
- ricambi critici.

Non accettare una voce unica `centrale PDC`.

## 2. Identificazione prodotto

Per l'offerta indicare:

- modello esatto;
- revisione hardware;
- revisione firmware;
- data/versione datasheet;
- data/versione manuale;
- serial range se rilevante;
- paese/condizioni garanzia;
- soggetto autorizzato al primo avviamento.

## 3. Matrice prestazionale obbligatoria

Fornire capacità termica, assorbimento e COP almeno ai seguenti punti, distinguendo min/nom/max se disponibili:

- A7/W35;
- A7/W45;
- A2/W35;
- A2/W45;
- A-2/W35;
- A-2/W45;
- A-7/W35;
- A-7/W45;
- A-10/W35;
- A-10/W45;
- A-15/W35;
- eventuale limite inferiore operativo.

Per ogni punto dichiarare norma/metodo di prova.

## 4. Defrost

Fornire dati specifici su:

- logica di attivazione;
- durata tipica/massima;
- intervallo tipico nelle condizioni umide fredde;
- energia elettrica durante defrost;
- energia sottratta al circuito acqua;
- capacità termica media netta su 1 h e 24 h includendo defrost;
- gestione simultanea di 3–4 unità in cascata;
- possibilità di sfalsare i defrost per evitare caduta simultanea di potenza.

## 5. Circuito idraulico integrato

Confermare per KHP-R290-22-3:

- marca/modello circolatore integrato;
- curva Q/H completa;
- controllo velocità;
- portata minima;
- portata nominale;
- portata massima;
- perdita di carico interna completa;
- prevalenza residua disponibile esternamente;
- pressione minima/massima circuito;
- flow switch/sensore integrato;
- qualità acqua richiesta;
- percentuale glicole ammessa e derating.

Spiegare per iscritto la differenza tra documentazione corrente che riporta 65 kPa / 100 kPa e manuale 6/26 che riporta 45 kPa / 6,9 m.

## 6. Chiarimento assorbimento elettrico

Confermare quale dato è valido per la revisione offerta:

- datasheet corrente: max range A7/W35 5,90 kW;
- manuale 6/26: max range A7/W35 6,90 kW;
- massima potenza elettrica generale dichiarata: 9 kW.

Fornire:

- corrente nominale;
- corrente massima;
- eventuali picchi/inrush inverter;
- alimentazione ausiliari;
- potenza resistenze carter/base;
- eventuale heater elettrico integrato/opzionale;
- protezione raccomandata;
- sezione cavo raccomandata;
- RCD/differenziale richiesto;
- schema elettrico.

## 7. Cascata

Dichiarare se il prodotto supporta nativamente una cascata di 2–4 unità.

Se sì, indicare:

- controller OEM richiesto;
- numero massimo unità;
- lead/lag;
- rotazione ore;
- staging;
- setpoint comune;
- gestione allarmi;
- defrost sfalsato;
- limitazione potenza;
- comportamento in caso di perdita comunicazione;
- costo hardware/licenze.

Se no, fornire interfacce necessarie per controllo PLC esterno.

## 8. Protocollo dati

Fornire documentazione completa per Modbus/RS485/BACnet/altro, se disponibile.

Richiesti almeno:

- enable/disable;
- setpoint mandata;
- modalità heat/cool;
- temperatura ingresso/uscita;
- temperatura esterna;
- stato compressore;
- frequenza/potenza compressore se disponibile;
- stato pompa;
- stato ventole;
- stato defrost;
- assorbimento/potenza se disponibile;
- codice allarme;
- reset allarme autorizzato;
- limitazione potenza;
- ore lavoro.

Il funzionamento vitale deve restare locale anche senza Internet/cloud.

## 9. Installazione esterna / R290

Confermare per installazione plurima:

- distanze minime tra unità;
- distanza da pareti/ostacoli;
- zona di sicurezza refrigerante R290;
- distanze da fonti di ignizione, aperture, pozzetti e quadri elettrici;
- requisiti per basamento;
- antivibranti;
- protezione neve;
- protezione vento;
- gestione scarico condensa e ghiaccio;
- requisiti per tettoia eventuale;
- accesso manutenzione;
- limitazioni in presenza di più macchine affiancate.

Il manuale disponibile mostra A>500 mm, B>1500 mm, C>1000 mm, D>500 mm per una singola unità; verificare se tali distanze cambiano in batteria 3–4 macchine.

## 10. Acustica

Fornire:

- potenza sonora EN 12102;
- pressione sonora e distanza/metodo;
- eventuale silent/night mode;
- perdita capacità in silent mode;
- dati spettrali se disponibili;
- raccomandazioni antivibranti.

## 11. Garanzia e assistenza Italia

Indicare:

- garanzia base;
- condizioni `5+2 anni`;
- manutenzioni obbligatorie;
- primo avviamento obbligatorio;
- installatori autorizzati in Italia/FVG;
- tempi medi intervento;
- disponibilità ricambi;
- sede magazzino ricambi;
- costo uscita/diagnosi fuori garanzia;
- effetto del collegamento a PLC esterno sulla garanzia.

## 12. Ricambi

Quotare almeno:

- pompa circolazione completa;
- scheda principale;
- inverter/comando compressore se separato;
- controller/display;
- motore ventilatore;
- sensori temperatura;
- sensori pressione;
- flow switch;
- eventuali valvole/attuatori sostituibili.

Per ogni ricambio indicare lead time.

## 13. Prezzo scomposto

Separare:

- PDC;
- controller/interfaccia;
- accessori;
- antivibranti;
- basamenti se forniti;
- trasporto;
- commissioning;
- formazione;
- garanzia estesa;
- ricambi;
- eventuale contratto manutenzione.

## 14. Acceptance test

Prima della chiusura commessa prevedere:

- verifica matricole/revisioni;
- prova comunicazione PLC;
- prova accensione sequenziale;
- prova isolamento di una unità;
- prova allarme/guasto simulato;
- verifica portate e ΔT;
- verifica carica accumulo;
- test logica lead/lag;
- verifica defrost quando le condizioni lo consentono;
- registrazione kW elettrici e kW termici;
- consegna parametri, backup configurazioni e manuali.
