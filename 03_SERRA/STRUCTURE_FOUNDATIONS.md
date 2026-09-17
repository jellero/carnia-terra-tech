# Carnia TerraTech — Structure & Foundations

**Aggiornato:** 17 settembre 2026  
**Stato:** `REQUISITI DEFINITI / PACKAGE COSTI SVILUPPATO / CALCOLO BLOCCATO DAL LOTTO`.

## 1. Norma e responsabilità

Per la serra produttiva professionale il riferimento europeo da verificare in esecutivo è **EN 13031-1:2019 + AC:2022**. Il progettista deve inoltre verificare NTC 2018, relativa Circolare e ogni prescrizione vigente al momento del progetto.

Il repository non sostituisce il progetto strutturale firmato.

## 2. Regola economica

La struttura non viene stimata con un semplice €/m². Devono essere noti almeno:

- kg acciaio per famiglia;
- sezioni/spessori/materiale;
- lavorazioni;
- zincatura/protezione;
- bulloneria/giunti/staffe;
- quantità e tipo fondazioni;
- trasporto/scarico;
- montaggio/mezzi;
- calcoli/shop drawing/as-built;
- ricambi.

Package economico dettagliato: `19_BOM_PRODOTTI_FORNITORI/SERRA_STRUTTURA_FONDAZIONI.md`.

## 3. Azioni da considerare

Il calcolo deve esplicitare almeno:

- peso proprio struttura;
- copertura/fissaggi;
- neve del sito;
- vento del sito;
- sisma quando applicabile;
- schermi e meccanismi;
- aperture e attuatori;
- HAF e componenti sospesi;
- fogging;
- tubazioni/cavi/canaline;
- linee coltura e carichi sospesi pomodoro/peperone;
- canaline drenaggio/supporti;
- carichi manutenzione;
- combinazioni di carico;
- condizioni durante montaggio e sostituzione copertura.

Nessun componente sospeso è considerato trascurabile senza verifica.

## 4. Dati di sito obbligatori

Prima del calcolo definitivo:

- coordinate/quota;
- topografia;
- esposizione;
- stratigrafia e parametri geotecnici;
- relazione geologica/geotecnica quando richiesta;
- vento/neve;
- effetti topografici;
- falda/drenaggio;
- aggressività/corrosività del terreno quando rilevante.

## 5. Fondazioni: nessuna soluzione assunta a priori

Confrontare almeno:

- F1 pali/manicotti infissi;
- F2 plinti/pedestalli puntuali in c.a.;
- F3 viti/eliche di fondazione strutturali con dati e prove in sito;
- F4 sistema misto quando tecnicamente giustificato.

Per ogni soluzione verificare:

- trazione/estrazione;
- compressione;
- azioni orizzontali;
- cedimenti;
- gelo/drenaggio;
- durabilità;
- tolleranze;
- riparabilità;
- interferenze con sottoservizi.

I prezzi retail di piccole viti da recinzione/pergolato non vengono usati per dimensionare né quotare una fondazione strutturale della serra.

## 6. Materiali e durabilità

Richiedere:

- qualità acciaio dichiarata;
- sezioni e spessori reali;
- processo/spessore zincatura o protezione;
- certificazioni/tracciabilità;
- bulloneria compatibile;
- gestione di tagli/fori in cantiere;
- dettagli contro ristagni;
- protezione delle aree esposte a condensa, fertilizzanti e lavaggi.

## 7. Benchmark costi di controllo

### Carpenteria FVG 2026

Prezzario regionale, carpenteria in profilati cavi:

- S235 €7,56/kg;
- S275 €7,65/kg;
- S355 €7,84/kg;
- zincatura a caldo +€1,50/kg.

Questi sono benchmark di lavori pubblici generici, non prezzi della serra agricola.

Fonte: https://www.regione.fvg.it/rafvg/cms/RAFVG/infrastrutture-lavori-pubblici/lavori-pubblici/prezzario-2026/?cod=20.6.IH2.01

### Calcestruzzo FVG 2026

Fornitura C25/30: ~€111,84–113,17/m³ secondo consistenza; fondazioni/platee in opera C25/30 ~€287–290/m³ con ferro escluso.

Fonti:

- https://www.regione.fvg.it/rafvg/cms/RAFVG/infrastrutture-lavori-pubblici/lavori-pubblici/prezzario-2026/?cod=Y8.1.165.02
- https://www.regione.fvg.it/rafvg/cms/RAFVG/infrastrutture-lavori-pubblici/lavori-pubblici/prezzario-2026/?cod=16.5.EQ4.02

### Benchmark agricolo

Tuttoserre professionale 8×40 m / 320 m²: €6.832 IVA inclusa, struttura Ø60 mm, passo pali 2,5 m, gronda 3,2 m, teli e montaggio esclusi; prezzo dichiarato indicativo da ricalcolare.

Fonte: https://www.tuttoserre.it/serre/18-serra-professionale.html

Non scalare linearmente a 4.200 m².

## 8. Bulloneria e minuteria

La distinta deve separare:

- bulloni;
- dadi;
- rondelle;
- staffe/piastre;
- cavallotti/morsetti;
- giunti/manicotti;
- controventi/tiranti;
- tirafondi/ancoraggi;
- viteria secondaria;
- ricambi.

Per ogni famiglia: quantità, materiale/trattamento, classe quando applicabile e scorta motivata.

## 9. Interfacce da congelare prima dell'ordine

La struttura non passa a `ORDINABILE` finché non sono definite le interfacce con:

- schermi;
- aperture/reti;
- HAF;
- fogging;
- colture sospese;
- tubazioni termiche;
- irrigazione;
- elettrico/dati;
- telecamere/sensori;
- AMR;
- porte;
- gronde;
- espansioni future.

## 10. Dati obbligatori dal fornitore

Richiedere nel preventivo:

- peso totale acciaio;
- peso per famiglia strutturale;
- numero e sezione di colonne/archi/travi;
- quantità controventi/tiranti;
- quantità bulloneria/giunti principali;
- quantità e tipologia fondazioni;
- m³ cls/kg armatura se soluzione in c.a.;
- carichi di progetto;
- vita/durabilità dichiarata;
- manuale montaggio;
- piano ispezioni/manutenzione;
- lista ricambi.

RFQ: `03_SERRA/RFQ_GREENHOUSE_STRUCTURE.md`.

## 11. Ispezione e vita utile

Prevedere controlli documentati per:

- corrosione;
- serraggio bulloni;
- deformazioni;
- fondazioni/ancoraggi;
- controventi;
- danni post neve/vento;
- urti mezzi;
- punti di contatto con copertura;
- meccanismi mobili.

I controlli confluiranno nell'asset register del punto 13.

## 12. Gate

Diventa `VALIDATO` solo dopo:

- lotto e geotecnica;
- carichi locali;
- calcolo firmato;
- shop drawing;
- distinta pesi/quantità;
- fondazione verificata;
- almeno 2–3 offerte confrontabili;
- costo completo inserito nel CAPEX.