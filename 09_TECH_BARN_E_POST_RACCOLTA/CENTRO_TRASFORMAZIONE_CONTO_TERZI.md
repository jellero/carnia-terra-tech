# Carnia TerraTech — Centro trasformazione conto terzi / comunitario — BOM-029

**Aggiornato:** 18 settembre 2026  
**Stato:** `WORKING ARCHITECTURE / BUSINESS CASE, DOMANDA LOCALE, LAYOUT FOOD E RFQ BLOCCANTI / CAPACITY MODEL DEFINITO`.

## 1. Obiettivo

Realizzare, in fase successiva rispetto al core serra, un centro di trasformazione vegetale capace di:

- valorizzare eccedenze e seconda scelta sana della produzione Carnia TerraTech;
- trasformare materia prima di aziende agricole locali;
- offrire lavorazioni conto terzi;
- produrre private label;
- creare succhi, puree, confetture/composte e futuri trasformati vegetali;
- alimentare lo spaccio BOM-028;
- ridurre waste e stagionalità;
- produrre dati reali su resa, domanda, costi e qualità.

Il modulo resta **fuori dal CAPEX base** finché il business case non raggiunge il gate economico.

## 2. Perimetro prodotto

### Fase 1 — baseline

- mele;
- pere;
- cotogne;
- piccoli frutti;
- frutta compatibile con linea succo/purea;
- succhi;
- puree;
- bag-in-box;
- confetture;
- composte.

### Fase 2 — conditional

- pomodoro;
- passate;
- salse vegetali;
- altri vegetali acidificati o trattati termicamente.

Fase 2 richiede:
- ricette validate;
- hazard analysis dedicata;
- processo termico validato;
- verifica pH/aw/shelf-life;
- eventuale diversa impiantistica.

### Fuori baseline

- carne;
- latte;
- uova;
- prodotti ittici;
- ready-to-eat complessi;
- processi che richiedono riconoscimenti/autorizzazioni specifiche ulteriori.

## 3. Quattro modelli commerciali

### M1 — conto lavorazione

Cliente conferisce materia prima e paga:
- €/kg ingresso;
- €/L succo;
- €/vaso;
- setup lotto;
- packaging;
- etichettatura;
- analisi;
- stoccaggio extra.

### M2 — compensazione in prodotto

Possibile solo con:
- contratto;
- resa misurata;
- proprietà chiarita;
- fiscalità/IVA;
- quota definita dopo costi reali.

Non fissare percentuali prima del pilot.

### M3 — acquisto materia prima

Carnia TerraTech compra la materia prima e vende il trasformato.

Pro:
- controllo ricetta;
- standardizzazione;
- libertà commerciale.

Contro:
- capitale circolante;
- rischio invenduto;
- rischio prezzo materia prima.

### M4 — pooled/community batch

Piccoli conferitori possono essere aggregati in lotti compatibili.

Serve:
- regola di equivalenza;
- specifica qualità minima;
- proprietà;
- tracciabilità;
- resa;
- credito prodotto;
- consenso esplicito a non ricevere necessariamente il proprio identico lotto fisico.

## 4. Domanda: cosa sappiamo e cosa no

ERSA stimava per il 2024 in FVG:

- superficie melo: **1.098 ha**;
- resa: **62,6 t/ha**;
- produzione mele: **68.735 t**;
- prezzo medio all'origine osservato: **€0,80/kg**.

Questo dimostra che la materia prima regionale esiste in scala significativa, ma **non dimostra la domanda conto terzi in Carnia**.

Una linea da 200 t/anno assorbirebbe circa lo 0,3% della produzione regionale mele 2024: tecnicamente una quota piccola, ma il vero gate resta la disponibilità economicamente raggiungibile entro il bacino logistico reale.

### Demand validation obbligatoria

Prima dell'ordine:

- 30–50 interviste strutturate a produttori;
- kg/anno conferibili;
- periodo raccolta;
- distanza;
- prodotto richiesto;
- lotto minimo accettabile;
- disponibilità a pagare;
- packaging;
- restituzione prodotto vs vendita;
- private label;
- bisogno di analisi/ricetta.

Target:
- almeno 3 lettere di interesse o accordi quadro;
- volume potenziale >= 1,5× capacità minima economica della linea working.

## 5. Capacity model

La linea viene dimensionata sul collo di bottiglia complessivo:

`capacity_real = min(wash, crush, press, thermal, fill, labor, CIP/changeover)`

Non usare la capacità nominale della sola pressa.

### Scenario S0 — pilot/community micro

- input frutta: ~100–250 kg/h;
- pastorizzazione: ~90–180 L/h;
- 1–2 operatori;
- batch piccoli;
- 20–60 t/anno.

Uso:
- validazione mercato;
- lotti speciali;
- R&D.

Non è la baseline economica per un centro conto terzi stabile.

### Scenario S1 — compact professional

- input: ~250–400 kg/h;
- output succo: ~170–300 L/h a seconda resa;
- 2 operatori;
- 50–120 t/anno.

Adatto se:
- domanda locale frammentata;
- molti piccoli lotti;
- forte valore €/kg;
- stagionalità corta.

### Scenario S2 — working candidate

- input frutta: **600–700 kg/h**;
- pressa benchmark Voran 100P2/EBP500: fino a 600–700 kg/h;
- resa dichiarata fino a ~75% su prodotti compatibili;
- output succo teorico: ~420–525 L/h;
- pastorizzatore: classe 500–750 L/h;
- filler bag-in-box: classe ~750 L/h;
- 2–3 operatori diretti;
- capacità stagionale realistica da modellare: **150–300 t/anno**.

Esempio:
- 700 kg/h;
- 5 h produttive nette/giorno;
- 80 giorni;
- = 280 t/anno input teorico prima di downtime/inefficienze.

**S2 è il candidato working.**

### Scenario S3 — regional hub

- input >1.000 kg/h;
- pastorizzazione 750–1.500+ L/h;
- automazione superiore;
- 4+ operatori/turno;
- >500 t/anno.

Non ordinare senza contratti/volumi confermati.

## 6. Layout e zoning

Flusso base:

`ricezione -> pesatura -> quarantena/accettazione -> cernita -> lavaggio -> preparazione -> processo -> trattamento termico -> riempimento -> chiusura -> raffreddamento -> etichetta -> finito -> spedizione`

Zone:

### Z1 — dirty/raw
- scarico;
- bins;
- casse sporche;
- ricezione;
- cernita primaria;
- lavaggio.

### Z2 — prep/process
- frangitura;
- pressatura;
- preparazione frutta;
- cottura;
- puree.

### Z3 — high hygiene / fill
- trattamento termico a valle;
- riempimento;
- chiusura;
- packaging primario aperto.

### Z4 — finished goods
- raffreddamento;
- etichettatura;
- cartoni;
- pallet;
- stock.

### Z5 — utility/CIP
- detergenti;
- CIP;
- acqua calda;
- pompe;
- scambiatori;
- compressore;
- quadro.

### Z6 — QC
- pH;
- Brix;
- temperatura;
- peso;
- campioni;
- retain samples.

### Z7 — personnel
- lavamani;
- spogliatoio;
- servizi;
- DPI;
- accesso igienico.

### Z8 — waste/by-products
- sansa/polpa;
- scarti;
- rifiuti;
- lavaggio contenitori;
- uscita separata.

Regola:
- flussi sporco/pulito non devono incrociarsi senza procedura controllata.

## 7. Linea succo — architettura S2

Working chain:

1. bins/cassette;
2. bilancia piattaforma;
3. tramoggia/ricezione;
4. lavaggio;
5. cernita;
6. frangitura;
7. pressatura;
8. tank/buffer;
9. eventuale filtrazione;
10. pastorizzazione;
11. bag-in-box;
12. bottiglia opzionale;
13. etichetta/lotto;
14. pallet/stock.

### Working references

**Voran WA LC40**
- fino a 3.000 kg/h;
- 6,2 kW;
- AISI 304.

Sovradimensionata rispetto a S2 ma utile per non fare del lavaggio il bottleneck.

**Voran RM2.2**
- fino a 1.000 kg/h;
- 2,2 kW;
- AISI 304.

**Voran 100P2**
- fino a 600 kg/h;
- resa dichiarata fino a 75%;
- 1,5 kW;
- press force 24 t.

**Voran EBP500**
- fino a 700 kg/h;
- resa dichiarata fino a 75%;
- belt press;
- 3 L/min acqua pulizia.

Confrontare:
- 100P2: batch/manualità maggiore, CAPEX presumibilmente inferiore;
- EBP500: continuous, lavaggio e throughput più lineari.

**Voran PA500/PA750 class**
- PA750: 750 L/h;
- thermal rating 70 kW;
- 1,1 kW elettrico per ausiliari;
- gas o altra fonte a seconda versione.

Per Carnia TerraTech chiedere anche soluzione elettrica/heat-pump-compatible se tecnicamente disponibile, evitando di imporre combustibile fossile se non necessario.

**Voran MBF750**
- bag-in-box 3/5/10/20 L;
- ~750 L/h su 10 L;
- load-cell dosing;
- AISI 304.

## 8. Linea confetture/composte

Working baseline:
- tavolo prep;
- taglio/passatura;
- cuocitore/miscelatore;
- dosaggio ingredienti;
- Brix;
- pH;
- hot-fill;
- chiusura twist-off;
- eventuale tunnel/vasca post-process;
- raffreddamento;
- etichetta;
- retain sample.

### Scala iniziale

Non serve un impianto continuo grande.

Scenario:
- 100–200 L/batch class;
- 2–6 batch/giorno secondo ricetta, tempo termico e pulizia.

Benchmark retail/pro:
- pentole motorizzate Polsinelli 100–200 L: ordine di grandezza ~€416–492 nella pagina catalogo osservata;
- questi valori sono **benchmark del recipiente/agitatore**, non di una linea industriale completa né di un cooker jacketed automatico.

Per produzione professionale conto terzi richiedere RFQ per:
- jacketed kettle;
- agitazione;
- controllo temperatura;
- scarico sanitario;
- CIP;
- data logging;
- eventuale vacuum cooking.

## 9. QC minimo

Strumenti:

- pH meter food-grade;
- rifrattometro °Brix;
- bilancia precisione;
- termometri calibrabili;
- logger processo;
- bilancia packaging;
- sample jars;
- retain sample storage.

Benchmark semplice:
- rifrattometro high-Brix manuale 58–90 Brix: ~€21,31;
- questo è solo controllo operativo, non sostituisce strumentazione calibrata/validata richiesta dal piano qualità.

Ogni prodotto deve avere:
- recipe ID;
- batch ID;
- ingredient lot;
- pH target;
- Brix target;
- temperature/time profile;
- fill temperature;
- closure check;
- yield;
- deviations;
- release status.

## 10. Packaging

### Succhi

Baseline:
- bag-in-box 3/5 L;
- 10/20 L per conto terzi/B2B;
- bottle filling come optional.

Perché BIB:
- minor lavoro;
- buona logistica;
- facile differenziazione lotti;
- shelf-life da validare sul processo reale.

### Confetture

Working:
- 212–314 mL retail;
- larger food-service optional.

Benchmark Polsinelli:
- ERGO 212 mL bulk: ~€688,52 / 1.728 pz;
- ERGO 314 mL bulk: ~€696,72 / 1.344 pz.

Sono benchmark packaging retail, non offerta industriale definitiva.

## 11. CIP e cleaning

CIP non è una "pompa con detergente".

Deve definire:
- circuiti;
- return;
- concentrazione;
- T;
- tempo;
- turbulence/flow;
- rinse;
- chemical segregation;
- verification.

Working levels:

### C1 — manual/COP
Per parti smontabili e micro-lotti.

### C2 — semi-CIP
Tank + pump + return + spray balls su apparecchi predisposti.

### C3 — automated CIP
Recipes, conductivity, temperature, dosing, return recovery.

S2:
- almeno C2;
- C3 se più clienti/lotti/giorno rendono il changeover critico.

## 12. Acqua

Servizi:
- potable process water;
- wash water;
- CIP;
- handwash;
- floor wash;
- cooling.

Monitorare:
- L/kg input;
- L/CIP;
- temperature;
- detergenti.

Separare:
- acqua a contatto food;
- acqua tecnica non-food se ammessa.

## 13. Reflui

I reflui possono avere:
- solidi;
- zuccheri;
- carico organico;
- detergenti;
- pH variabile.

Prima del layout definitivo:
- verificare scarico;
- portata;
- equalizzazione;
- griglia/filtro;
- grassi/solidi se pertinenti;
- compatibilità detergenti;
- autorizzazioni.

Non mandare automaticamente tutto nella rete esistente del Tech Barn.

## 14. Energia e calore

Carichi:
- washer/crusher/press;
- pompe;
- pastorizzazione;
- cooking;
- hot water;
- cooling;
- packaging;
- CIP.

Il server centrale deve pianificare batch e CIP rispetto a:
- FV;
- BESS;
- serra;
- celle;
- priorità carichi.

Working energy strategy:
- recupero calore dove utile;
- accumulo acqua calda;
- elettrico/heat pump dove compatibile;
- resistenza/boost;
- combustibile solo se T/peak duty o CAPEX lo giustificano.

## 15. Food safety

Riferimenti:
- Reg. (CE) 852/2004;
- Reg. (CE) 178/2002;
- Reg. (UE) 1169/2011;
- notifica OSA/SUAP FVG;
- autocontrollo/HACCP.

La pagina SUAP FVG vigente richiede notifica per attività di trasformazione alimentare e identifica l'OSA quale responsabile del rispetto della legislazione alimentare.

Gate:
- master list attività;
- NIA;
- layout;
- acqua;
- pest control;
- allergeni;
- cleaning;
- traceability;
- recall;
- shelf-life;
- labels;
- waste/reflui.

## 16. Tracciabilità digitale

Il server centrale gestisce:

`supplier -> incoming lot -> weight -> QC -> process batch -> recipe -> CCP/process data -> packaging lot -> finished lot -> customer -> invoice/return`

Per conto terzi aggiungere:
- owner of goods;
- service order;
- yield;
- loss;
- packaging supplied by;
- quantity returned;
- quantity retained;
- release document.

Ogni movimento produce event log.

## 17. Personale

S2 working:
- 2 operatori minimo in produzione;
- 3 nei picchi/pack;
- manutenzione condivisa;
- QC/HACCP role definito;
- reception/admin separabile temporalmente.

Il server pianifica:
- receiving slots;
- process batch;
- cleaning;
- fill;
- labeling;
- dispatch.

Non sovrapporre ricezione cliente e high-hygiene fill se il layout/personale non lo permette.

## 18. Conto terzi e small lots

Il mercato mostra laboratori conto terzi che accettano anche 10–12 kg e strutture da ~80 kg/giorno: dimostra l'esistenza di un segmento micro-batch, ma non è automaticamente il modello economico di Carnia TerraTech.

Per S2:
- definire minimum lot;
- setup fee;
- CIP fee;
- packaging fee;
- label fee;
- storage fee.

Piccoli lotti senza setup fee distruggono la produttività.

## 19. By-products

Polpa/sansa:
- pesare;
- registrare;
- separare contaminanti;
- destinare a compost/vermicompost solo se appropriato;
- valutare feed/other use solo con verifica normativa.

Integrare con modulo cicli materia.

## 20. Contributi

Il bando FVG **SRD13** riguarda investimenti per trasformazione/commercializzazione dei prodotti agricoli.

Situazione al 18/09/2026:
- graduatoria pubblicata 15/09/2026;
- bando 2025 già chiuso;
- graduatoria valida 24 mesi;
- esistono domande ammesse e anche ammesse ma non finanziabili per carenza risorse.

**Regola:** nessun contributo entra come certo nel business case.

Monitorare:
- SRD13;
- successivi bandi;
- SRD17/strumenti finanziari;
- programmi regionali pertinenti.

## 21. CAPEX model

Separare:

### Building
- walls/food finishes;
- drains;
- doors;
- hygiene;
- services;
- changing room;
- utilities.

### Juice
- wash;
- sort;
- mill;
- press;
- tanks;
- pasteurizer;
- BIB;
- bottle optional.

### Jam
- prep;
- kettle;
- fill;
- close;
- post-process;
- cooling.

### Shared
- pumps;
- CIP;
- hot water;
- compressed air;
- electrical;
- server/traceability;
- QC;
- pallet handling.

### Working capital
- packaging;
- ingredients;
- labels;
- customer lots;
- finished stock.

## 22. OPEX model

Per batch:

`OPEX_batch = labor + energy + water + detergents + packaging + ingredients + analyses + waste + maintenance + depreciation + admin`

Per conto terzi:

`price_batch >= OPEX_batch + changeover_cost + risk_allowance + margin`

Misurare:
- kg input;
- finished yield;
- operator minutes;
- wash minutes;
- kWh;
- thermal kWh;
- L water;
- chemical dose;
- packaging;
- rejects.

## 23. Business-case gate

Non costruire se manca uno di questi:

1. domanda documentata;
2. almeno 150–300 t/anno potenziali per S2 o scenario ridimensionato coerente;
3. tariffario testato;
4. minimum lot;
5. layout approvabile;
6. acqua/scarichi;
7. energy model;
8. 3 RFQ comparabili;
9. staffing;
10. margin per batch;
11. break-even;
12. working capital;
13. food-safety plan;
14. expansion route.

## 24. Acceptance commissioning

Prima di produzione commerciale:

1. water test;
2. drain test;
3. hygiene zoning walkthrough;
4. dry run;
5. wet run;
6. CIP verification;
7. 3 process batches per family;
8. temperature calibration;
9. pH/Brix QC;
10. fill weight;
11. closure;
12. label/lot;
13. traceability recall test;
14. mass balance;
15. waste balance;
16. energy/water measurement;
17. cleaning verification;
18. customer order/release flow;
19. server event reconciliation;
20. HACCP sign-off.

## 25. Decisione corrente

**BOM-029 = sviluppare come business unit futura predisposta nel masterplan, non ancora nel CAPEX core.**

Working candidate:
- Scenario **S2 600–700 kg/h input** per linea succo;
- jam/composte modulari 100–200 L/batch;
- bag-in-box baseline;
- bottle line optional;
- semi-CIP minimo;
- server centrale per scheduling, batch genealogy e cost accounting.

Il passo che può promuoverlo a CAPEX reale non è un'altra brochure tecnica: è la domanda locale documentata.
