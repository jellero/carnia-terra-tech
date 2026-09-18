# Piano misure e RFQ carichi — closure BOM-034

**Aggiornato:** 18 settembre 2026  
**Stato:** `ESECUTIVO / TEMPLATE PRONTO / DATI REALI DA RACCOGLIERE`  
**Dipendenza:** [MASTER_LOAD_REGISTER.md](MASTER_LOAD_REGISTER.md)

## 1. Obiettivo

Chiudere i campi `MEASURE`, `OEM-RFQ` e `DESIGN` del master load register con dati utilizzabili per:

- confermare o rivedere il PCS BESS da 30 kW;
- scegliere 60 / 90 / 120 kWh useful;
- dimensionare critical bus e protezioni;
- definire restart groups RG0–RG5;
- emettere RFQ BESS/quadri comparabili;
- alimentare CAPEX/OPEX finale.

Nessun valore viene assunto per analogia quando il dato può cambiare la taglia di BESS, quadro o protezione.

## 2. Ordine operativo

### Fase M0 — data request OEM

Prima di misurare, per ogni asset già selezionato/candidato chiedere:

- marca e modello;
- P input nominale e massima;
- tensione/fasi;
- corrente nominale;
- PF/cosφ;
- kVA;
- inrush/LRA o overload;
- durata startup;
- VFD/inverter;
- restart delay;
- comportamento dopo perdita rete;
- comando remoto enable/disable;
- Modbus/API/contatto disponibile;
- derating temperatura;
- standby/auxiliary consumption;
- garanzia e ricambi;
- prezzo netto;
- IVA;
- trasporto;
- installazione;
- commissioning;
- manutenzione annua;
- lead time;
- esclusioni.

### Fase M1 — misura P0

Priorità assoluta:

1. PLC/control;
2. edge gateway;
3. network core e PoE;
4. NODE-A/B/QNODE + storage minimo;
5. security/fire/access essenziale;
6. cold-room controls/logger;
7. irrigation controls;
8. ausiliari BESS appena il modello è selezionato.

Per ogni P0 registrare:

- idle;
- normale;
- 95° percentile;
- massimo;
- startup;
- power loss/restart;
- kW/kVA/PF;
- corrente per fase;
- eventuale fase dominante.

### Fase M2 — misura/RFQ P1 e >1 kW

Ordine:

1. pompa irrigazione duty;
2. CR-A;
3. CR-B;
4. UV W1;
5. fertirrigazione;
6. attuatori serra survival;
7. HAF subset;
8. animal welfare;
9. safety lighting;
10. retail refrigeration/payment;
11. PDC #1;
12. DG-3.

PDC #2/#3, DG-12 e charging P3 vengono chiusi subito dopo per dimensionare restart e grid-mode demand.

## 3. Finestra di acquisizione

Per ogni asset:

| Fenomeno | Risoluzione minima | Durata |
|---|---:|---:|
| startup/inrush | 1 s o migliore se strumento disponibile | evento completo |
| transitorio operativo | 1–10 s | più cicli |
| profilo operativo | 1 min | almeno ciclo operativo rappresentativo |
| domanda | 15 min | campagna estesa |
| energia | giornaliera | campagna estesa |

Quando il carico è stagionale, il dato deve essere marcato `NON RAPPRESENTATIVO` finché non è osservato nella condizione di progetto.

## 4. Durata minima campagna

### Pre-installazione / procurement

Se l'impianto reale non esiste:

- usare dati OEM garantiti;
- misure su demo/candidato quando possibili;
- mantenere margine esplicito;
- non trasformare benchmark catalogo in misura reale.

### Commissioning

Obiettivo minimo:

- 72 h log continuo dopo messa in servizio;
- almeno un ciclo completo irrigazione;
- almeno 10 partenze compressore per cella;
- almeno 5 partenze PDC per unità disponibile;
- almeno 3 prove restart controllate;
- almeno 1 blackout SAT completo;
- almeno 1 ritorno rete con sequenza RG0–RG5.

Per profilo energetico definitivo, estendere la raccolta alla stagionalità utile del progetto.

## 5. Strumentazione / servizio da RFQ

Non viene imposto un marchio unico.

Richiedere all'integratore strumenti idonei a misurare:

- trifase 400 V;
- kW, kvar, kVA;
- PF;
- tensioni/correnti per fase;
- frequency;
- phase imbalance;
- demand 15 min;
- energia import/export;
- logging esportabile CSV;
- timestamp sincronizzato;
- transitori/startup compatibilmente con la classe dello strumento.

Per misure permanenti usare la meter map BOM-034.

Per campagne temporanee il costo va quotato separatamente come:

- noleggio strumento;
- installazione TA/sonde;
- giorni logging;
- scarico dati;
- report;
- trasferta;
- sicurezza elettrica;
- eventuale fermo impianto.

## 6. Scheda RFQ per singolo asset

Ogni fornitore compila:

| Campo | Risposta richiesta |
|---|---|
| Asset ID | EL-... |
| Marca/modello | testo |
| Quantità | n |
| Alimentazione | V / fasi / Hz |
| P nominale | kW |
| P input max | kW |
| S max | kVA |
| PF min/nominale | valore |
| Corrente nominale | A/fase |
| Inrush/LRA | A o multiplo + durata |
| Startup | s |
| VFD/inverter | sì/no + tipo |
| Restart delay | s/min |
| Standby | W |
| Aux | W |
| Duty cycle | % / profilo |
| Island compatible | sì/no/condizioni |
| Remote shed | protocollo/contatto |
| Modbus/API | specifica |
| Temperatura | range + derating |
| Prezzo netto | € |
| IVA | %/€ |
| Trasporto | € |
| Installazione | € |
| Commissioning | € |
| Service annuo | € |
| Ricambi critici | elenco + € |
| Lead time | settimane |
| Garanzia | anni/ore |
| Esclusioni | testo |
| Datasheet URL | link |
| Manuale URL | link |
| Offerta ref/data | ID + data |

## 7. Quality gate dati

Un asset è `CLOSED` soltanto se:

- il dato ha fonte identificabile;
- marca/modello sono definiti oppure è esplicitamente una classe RFQ;
- kW e kVA/PF non sono confusi;
- startup è noto per motori/compressori;
- il costo specifica almeno netto/IVA/installazione;
- è chiaro se il valore è catalogo, offerta o misura;
- la data è registrata;
- il documento sorgente è linkato;
- eventuali condizioni/derating sono riportati.

## 8. Output calcolati

Dopo la raccolta si calcolano:

- `P0_normal_kW`;
- `P0_max_kW`;
- `P0_max_kVA`;
- `P1_normal_kW`;
- `P1_max_kW`;
- worst permitted simultaneous startup;
- RG0–RG5 max kW/kVA;
- 15-min site demand;
- island steady-state budget;
- minimum PCS continuous;
- minimum overload requirement;
- 60/90/120 kWh autonomy at BOL/EOL;
- SOC reserve sensitivity;
- CAPEX delle alternative.

## 9. Decision rule PCS 30 kW

I 30 kW vengono confermati solo se:

`P0P1_max + allowed_P2 + reserve_power_margin <= P_PCS_derated`

e tutti i casi startup autorizzati rispettano:

- kW;
- kVA;
- corrente;
- overload-duration;
- phase balance;
- protection/selectivity.

In caso contrario:

1. ridurre simultaneità;
2. modificare restart groups;
3. spostare carichi fuori island;
4. modificare hardware;
5. aumentare PCS.

Non si forza il risultato per mantenere 30 kW.

## 10. Decision rule energia BESS

Per ogni scenario outage:

`E_required = integral(P0 + P1 + permitted_P2) dt`

Correggere per:

- reserve SOC;
- PCS/battery losses;
- ausiliari;
- inverno;
- EOL SoH;
- margine di disponibilità.

La scelta 60/90/120 kWh viene fatta soltanto dopo questo calcolo e il confronto economico.

## 11. File operativo

Usare:

- [MASTER_LOAD_REGISTER.csv](MASTER_LOAD_REGISTER.csv) come anagrafica;
- [LOAD_DATA_CAPTURE_TEMPLATE.csv](LOAD_DATA_CAPTURE_TEMPLATE.csv) per dati OEM/misure/costi;
- [RFQ_EMS_BESS_GRID.md](RFQ_EMS_BESS_GRID.md) per il package BESS/connessione.

## 12. Deliverable richiesto all'integratore

1. registro carichi compilato;
2. raw CSV;
3. report strumenti e accuratezza;
4. grafici startup per carichi critici;
5. profilo 1 min;
6. profilo 15 min;
7. matrice simultaneità;
8. RG0–RG5 numerici;
9. P0/P1 summary;
10. scenario island;
11. raccomandazione PCS documentata;
12. scenario 60/90/120 kWh;
13. CAPEX installato per alternativa;
14. elenco assunzioni residue;
15. firma/data/responsabile tecnico.
