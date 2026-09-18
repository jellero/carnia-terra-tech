# DSO / TICA connection readiness — BOM-019 + BOM-034

**Aggiornato:** 18 settembre 2026  
**Stato:** `PRE-APPLICATION PACKAGE / LOTTO-POD-DSO E POTENZE FINALI BLOCCANTI`

## 1. Obiettivo

Preparare la richiesta di connessione dell'impianto FV + BESS senza assumere a tavolino:
- DSO;
- BT o MT;
- potenza disponibile in prelievo;
- potenza richiesta in immissione;
- limite export;
- soluzione tecnica di connessione.

Il pacchetto diventa inviabile appena sono noti lotto reale, POD/connessione esistente se presente e potenze finali.

## 2. Quadro normativo verificato al 18/09/2026

Riferimenti correnti:
- TICA ARERA — connessioni attive;
- CEI 0-21:2026-07 per utenti attivi/passivi BT, valida da agosto 2026;
- CEI 0-16:2026-07 per utenti attivi/passivi MT/AT, valida da agosto 2026;
- CEI 57-142 per interfacce/cybersecurity CCI quando applicabile;
- Allegato A.72 Terna Rev.03, gennaio 2026;
- deliberazioni ARERA 385/2025/R/eel e 564/2025/R/eel per CCI/PF2 nei casi applicabili.

Fonti:
- https://www.arera.it/atti-e-provvedimenti/dettaglio/08/099-08arg
- https://www.ceinorme.it/documenti-gratuiti/norme-cei-0-16-e-0-21/
- https://download.terna.it/terna/Allegato_A.72_8ddd5a25c22a644.pdf
- https://www.arera.it/en/comunicati-operatore/dettaglio/modifiche-norma-cei-0-16-appr-cei-attuazione-delib-3852025reel-25

## 3. Configurazione Carnia da presentare al DSO

Dati già consolidati:
- FV DC iniziale: **120,32 kWp**;
- predisposizione futura: **150–180 kWp DC**;
- inverter AC da confrontare:
  - I1 = 2×50 kW = **100 kW AC**;
  - I2 = 2×60 kW = **120 kW AC**;
- BESS: PCS **30 kW class**, energia 60/90/120 kWh useful ancora da scegliere;
- autoconsumo prioritario;
- BESS con possibilità di carica/scarica lato AC;
- islanding solo dopo separazione fisica dalla rete pubblica e secondo schema approvato;
- EMS custom non sostituisce protezioni/CCI/SLI certificati.

## 4. Decisione potenza in immissione — non congelare prima del preventivo

Il TICA consente che la potenza richiesta in immissione sia inferiore alla potenza nominale di produzione, ma l'esercizio deve rispettare il valore richiesto; eventuali limiti richiedono architettura SLI/export-limit coerente con CEI/DSO.

Scenari da chiedere esplicitamente al progettista/DSO:

| Scenario | FV AC | Potenza richiesta immissione | Nota |
|---|---:|---:|---|
| G100 | 100 kW | 100 kW | confine economico/procedurale interessante |
| G120 | 120 kW | 120 kW | nessun cap artificiale se rete lo consente |
| G120-CAP100 | 120 kW | 100 kW | solo con SLI/export control validato |
| GEXP | 120 kW iniziali | da definire per 150–180 kWp future | evitare rifacimenti se espansione credibile |

Non scegliere G120-CAP100 solo per ridurre il costo della domanda: confrontare perdita di energia, costo SLI, vincoli DSO e capacità futura.

## 5. Corrispettivo ottenimento preventivo — riferimento corrente DSO

La guida e-distribuzione Ed. 8.0 maggio 2026 riporta:
- >50 kW e <=100 kW: **€200 + IVA**;
- >100 kW e <=500 kW: **€500 + IVA**.

Fonte:
https://www.e-distribuzione.it/connessione-alla-rete/Regole_tecniche.html

Questi importi sono riferimento TICA/DSO e non sono il costo della connessione.

Applicazione Carnia:
- G100: fascia €200 + IVA se il DSO applica la medesima struttura TICA corrente;
- G120: fascia €500 + IVA;
- differenza domanda = €300 + IVA, economicamente marginale rispetto a una scelta tecnica di rete/inverter.

## 6. Tempi preventivo — riferimento corrente

La guida e-distribuzione 2026 riporta per BT/MT:
- fino a 100 kW: 20 giorni lavorativi;
- da 100 kW fino a 1.000 kW: 45 giorni lavorativi;
- oltre 1.000 kW: 60 giorni lavorativi.

Sono tempi di messa a disposizione del preventivo in condizioni ordinarie del processo; coordinamenti/integrazioni possono incidere.

## 7. Dati da avere prima dell'invio

### Sito
- indirizzo/catasto;
- coordinate;
- titolo disponibilità area;
- planimetria;
- layout preliminare FV/BESS;
- distanza dai possibili punti di rete;
- accessibilità cabina/contatori.

### Connessione esistente
Se presente:
- POD;
- DSO;
- tensione;
- potenza disponibile in prelievo;
- potenza già disponibile in immissione;
- schema fornitura;
- bollette/dati tecnici;
- corrente di corto circuito se disponibile.

### Produzione
- tecnologia FV;
- 120,32 kWp DC;
- inverter scelti o range 100/120 kW AC;
- potenza nominale complessiva rilevante ai fini della pratica;
- potenza richiesta in immissione;
- eventuale limitazione export;
- producibilità preliminare.

### Accumulo
- topology AC-coupled/hybrid;
- PCS kW;
- nominal/useful kWh;
- massima carica/scarica;
- modalità grid-connected;
- comportamento in blackout;
- anti-islanding / separazione rete;
- certificazioni della configurazione.

### Carichi
- potenza richiesta in prelievo;
- potenza disponibile desiderata;
- master load register;
- PDC e carichi motore;
- eventuali picchi/import contemporanei con carica BESS.

## 8. Elaborati preliminari

Preparare:
1. single-line diagram v0;
2. planimetria sito con PCC/POD, FV, BESS, main switchboard;
3. tabella inverter;
4. tabella BESS;
5. import/export operating envelope;
6. protezioni previste;
7. meter map;
8. schema islanding;
9. dichiarazione che l'isola non può restare in parallelo non autorizzato con DSO;
10. cronoprogramma stimato.

## 9. BT vs MT — regola

Non decidere da soli il livello di connessione.

### BT
Riferimento CEI 0-21:2026-07.

Possibili vantaggi:
- architettura più semplice;
- niente cabina MT se il DSO la concede.

Possibili limiti:
- capacità locale;
- corrente elevata a 100–120 kW;
- vincoli di tensione/export;
- eventuali opere di rete.

### MT
Riferimento CEI 0-16:2026-07.

Implica tipicamente:
- cabina/trasformatore;
- protezioni MT;
- SPI/DDI secondo soluzione;
- maggiore engineering/commissioning;
- se FV/eolico >=100 kW e caso applicabile: CCI + PF2 e comunicazioni richieste.

Il preventivo DSO decide la soluzione reale.

## 10. CCI / PF2 gate

Il quadro corrente estende CCI e funzione PF2 ai nuovi impianti FV/eolici in MT nella classe >=100 kW prevista dal framework corrente.

Per Carnia:
- 120,32 kWp DC e 100/120 kW AC rendono il gate **materiale**;
- l'applicabilità finale va determinata sulla potenza normativa della configurazione e sulla connessione MT reale;
- se BT, non inserire CCI MT per automatismo;
- se MT e applicabile, inserire hardware, comunicazione, certificati, commissioning e costi nel preventivo.

## 11. SLI / export limitation gate

La CEI 0-21:2026-07 e la CEI 0-16:2026-07 includono il framework corrente per SLI.

Se il DSO impone o si sceglie un limite di immissione:
- controllo aggregato FV + BESS + carico;
- sistema compliant e fail-safe;
- meter/sensor al PCC;
- perdita comunicazione -> comportamento conforme;
- custom Carnia EMS sopraordinato solo economicamente, non come dispositivo certificato.

## 12. Protezioni e studi da chiedere

RFQ progettista/integratore:
- Ik max/min al PCC;
- load flow;
- voltage rise;
- harmonic assessment;
- PF/Q requirements;
- phase balance;
- earthing/neutral;
- SPI/DDI;
- CCI/SLI se applicabili;
- selectivity/cascading;
- grid-mode fault;
- island inverter-limited fault;
- reconnection;
- emergency isolation;
- settings report.

## 13. Costi da separare

Non usare un forfait unico.

- corrispettivo domanda preventivo;
- corrispettivo connessione DSO;
- eventuale cabina MT;
- trasformatore;
- switchgear/protezioni;
- SPI/DDI;
- CCI/PF2;
- SLI;
- meter/TA/TV;
- progettazione;
- studi rete;
- iter autorizzativo rete;
- GAUDÌ/GSE support;
- collaudi;
- commissioning;
- opere civili;
- cavi/trincee;
- telecontrollo/telecom;
- manutenzione annuale.

## 14. Gate invio domanda

La richiesta è pronta quando sono chiusi:
- [ ] lotto;
- [ ] DSO competente;
- [ ] nuova connessione vs adeguamento;
- [ ] POD se esistente;
- [ ] potenza prelievo richiesta;
- [ ] FV AC 100 vs 120 kW;
- [ ] potenza immissione richiesta;
- [ ] BESS topology e 30 kW PCS;
- [ ] planimetria;
- [ ] SLD v0;
- [ ] deleghe/intestatario;
- [ ] autorizzazione/addebito corrispettivo;
- [ ] data target entrata in esercizio.

## 15. Decisione corrente

**Non presentare ancora una domanda reale** senza lotto/DSO/POD.

Ma il package è ora pronto per trasformare quei dati in una pratica senza rifare l'analisi tecnica.
