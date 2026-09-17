# RFQ — Pompe principali irrigazione 1+1

**Ambito:** Carnia TerraTech, stazione booster irrigazione/fertirrigazione con due pompe in ridondanza reale, fonte atmosferica o pressurizzata da definire.

## 1. Regola offerta

Non accettare una voce unica `gruppo pompe irrigazione`.

Separare almeno:

- pompa 1;
- pompa 2;
- motori;
- VFD 1 e VFD 2;
- collettore aspirazione;
- collettore mandata;
- valvole isolamento;
- non ritorno;
- giunti/riduzioni;
- eventuale strainer grossolano aspirazione;
- sensori pressione/livello/portata;
- eventuale vaso autoclave;
- quadro elettrico e protezioni;
- PLC/I/O e logica failover;
- skid/supporti;
- cablaggio;
- posa;
- commissioning;
- ricambi;
- documentazione.

Per ogni riga: quantità, marca/modello/codice, prezzo unitario/totale, IVA, trasporto, garanzia, lead time e ricambi.

## 2. Duty point

Il fornitore deve dimensionare sulle condizioni fornite dal progetto, dichiarando almeno:

- Q di progetto irrigazione;
- H statica;
- perdita filtrazione pulita/sporca;
- perdita fertirrigazione;
- perdita dorsali/valvole;
- pressione minima richiesta a valle;
- scenario controlavaggio;
- scenario flush;
- margine utilizzato.

Fornire curve Q/H, rendimento, P1/P2, NPSHr e punto di lavoro marcato.

Non proporre una pompa solo sulla base del diametro attacchi o dei kW motore.

## 3. Ridondanza

Quotare almeno:

- R1 — 2×100%, una duty + una standby;
- R2 — eventuale proposta alternativa con capacità degradata, esplicitando Q/H residui e rischio operativo.

R1 è la baseline progettuale.

Ogni pompa deve poter essere rimossa/manutenuta con l'altra in servizio.

## 4. Aspirazione

Dichiarare:

- livello minimo/massimo fonte;
- quota asse pompa;
- DN collettore aspirazione;
- velocità massima aspirazione;
- perdite di carico;
- NPSHa calcolato;
- NPSHr pompa;
- margine NPSH;
- requisiti anti-vortice;
- necessità/non necessità valvola di fondo;
- strainer/griglia e relativa perdita pulito/sporco.

Preferire aspirazione allagata quando possibile.

## 5. Mandata

Per ogni ramo pompa quotare separatamente:

- non ritorno;
- valvola isolamento;
- raccordo smontabile;
- eventuale giunto antivibrante;
- presa pressione;
- scarico.

Il collettore comune deve essere dimensionato per Q di progetto e transitori.

## 6. VFD e controllo

Baseline: un VFD per pompa.

Per ogni VFD indicare:

- marca/modello;
- tensione/fasi;
- corrente nominale;
- overload;
- grado IP;
- EMC/RFI;
- Modbus/RS485 o altro bus;
- ingressi/uscite disponibili;
- STO se disponibile/necessario;
- protezioni motore;
- ventilazione quadro;
- temperatura ambiente ammessa;
- ricambi e lead time.

Quotare controller locale o integrazione PLC con:

- PID pressione;
- alternanza lead/standby;
- runtime balancing;
- test standby programmabile;
- failover automatico;
- manual override;
- allarmi hardwired/locali;
- nessuna dipendenza cloud.

## 7. Sensori

Quotare almeno:

- 2× trasmettitori pressione 4–20 mA 0–6/10 bar o configurazione equivalente;
- manometro locale;
- pressostato di sicurezza se proposto;
- livello minimo tank hardwired;
- integrazione flow meter centrale;
- misura energia elettrica.

Specificare accuratezza, IP, materiale parti bagnate, attacco e calibrazione.

## 8. Vaso autoclave

Quotare come opzione 50–100 l e motivarne la necessità.

Dichiarare:

- volume totale/utile;
- precarica;
- Pmax;
- membrana;
- attacco;
- funzione nel controllo VFD.

Non sovradimensionare il vaso come sostituto di una corretta regolazione PID.

## 9. Filtrazione e controlavaggio

La stazione deve essere verificata insieme a BOM-014.

Per filtri automatici indicare se la pompa può sostenere:

- irrigazione + controlavaggio simultanei;
- oppure irrigazione sospesa durante il lavaggio.

Dichiarare pressione residua minima in entrambi i casi.

## 10. Failure modes e prove

Commissioning obbligatorio:

- curva pressione-portata misurata;
- verifica setpoint a domanda minima/media/massima;
- avviamento da zero;
- test pompa 1 fault -> pompa 2;
- test pompa 2 fault -> pompa 1;
- perdita sensore pressione;
- livello basso tank;
- assenza portata;
- valvola ramo chiusa;
- blackout/ripristino;
- controlavaggio filtro;
- stop emergenza se previsto.

Consegnare log dei test.

## 11. Ricambi/SLA

Quotare separatamente:

- tenuta meccanica;
- kit valvola non ritorno;
- trasmettitore pressione;
- pressostato;
- VFD completo;
- fusibili/contattori/protezioni specifiche;
- motore o pompa completa se strategicamente conveniente.

Indicare lead time Italia/FVG e centro assistenza.

## 12. Documentazione

Richiesti:

- curve certificate;
- datasheet;
- P&ID;
- schema elettrico;
- lista I/O;
- parametri VFD;
- as-built;
- manuale manutenzione;
- lista ricambi;
- certificazioni applicabili;
- dichiarazioni CE;
- verbale commissioning.