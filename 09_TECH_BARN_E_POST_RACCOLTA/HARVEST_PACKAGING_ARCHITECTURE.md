# Architettura raccolta e packaging — BOM-025

**Aggiornato:** 17 settembre 2026  
**Stato:** `WORKING ARCHITECTURE / QUANTITÀ DA PEAK HARVEST E CANALE VENDITA / LAVAGGIO RTE NON BASELINE`.

## 1. Obiettivo

Portare il prodotto dalla raccolta alla spedizione con:

- minimo handling;
- ergonomia;
- rintracciabilità;
- riduzione danni;
- compatibilità con BOM-020 AMR e BOM-021 stoccatore;
- ingresso rapido in BOM-024 celle;
- materiali food-contact verificati;
- layout pulibile;
- possibilità di vendere sia B2B in cassette sia retail confezionato.

## 2. Tre flussi, non una sola linea

### F1 — pomodoro e peperone

Baseline:

`raccolta in cassetta bassa -> ricevimento/pesatura -> selezione manuale -> eventuale pulizia a secco -> confezione B2B o retail -> CR-B/spedizione`.

Evitare lavaggio automatico come default. Se richiesto dal cliente, progettare acqua e asciugatura dedicate.

### F2 — lattuga cespo / leafy intera

Baseline:

`raccolta delicata -> cassetta food-grade -> pre-cooling -> selezione/trimming -> confezione -> CR-A`.

Lavaggio solo se necessario e validato.

### F3 — baby leaf / rucola / spinacio / basilico

Due business mode separati:

- **F3-A prodotto fresco NON ready-to-eat:** raccolta, selezione, raffreddamento, confezionamento con minimo processo;
- **F3-B lavato / ready-to-eat:** futuro modulo con wash-water control, centrifuga/asciugatura, maggiore zoning igienico, validazione microbiologica e HACCP dedicato.

F3-B non entra nel CAPEX baseline finché mercato e margini non lo giustificano.

## 3. Standard logistico 600×400

Preferenza per contenitori Euro 600×400 per:

- compatibilità carrelli/dolly;
- palletizzazione;
- celle;
- AMR/top module futuro;
- lavaggio e stoccaggio ordinato.

Non basta che una cassetta sia 600×400: per contatto diretto con prodotto deve esistere dichiarazione/idoneità food-contact applicabile.

### Dimensionamento cassette

`N_crates = peak_kg_in_circuit / kg_per_crate × turnaround_factor`

dove il turnaround factor comprende:

- raccolta;
- pre-cooling/cella;
- prodotto in spedizione;
- cassette sporche/in lavaggio;
- riserva.

Working factor iniziale: **1,3–1,5**, da validare.

Non fissare N prima di crop-card e kg/giorno.

## 4. Ergonomia

Regole:

- sollevamenti ripetitivi evitati;
- cassette su dolly/piattaforma, non a terra;
- almeno una stazione ad altezza regolabile o piano rialzato;
- bilancia e label printer nel raggio mano;
- niente torsione continua per passare prodotto;
- percorsi unidirezionali dove possibile;
- carrelli 600×400 compatibili con porte/celle.

Benchmark ergonomico: carrello a piattaforma rialzata 600×400 da 100 kg.

## 5. Tavoli e stazioni

Working layout ~60–70 m² packing:

1. ricevimento / QC;
2. selezione / trimming;
3. confezionamento;
4. etichettatura / uscita;
5. area wash-tool separata;
6. eventuale future wash/dry leafy.

Tavolo working: inox 1800×700 mm, ripiano inferiore, capacità >200 kg.

Tre tavoli sono un **working scenario**, non quantità d'ordine definitiva.

## 6. Pesatura

### SCALE-30

2 bilance da banco classe 30 kg working:

- una ricevimento/QC;
- una packaging.

Se il peso determina il prezzo o la quantità dichiarata nella transazione, selezionare strumento idoneo all'uso legale/metrologico applicabile.

### SCALE-300

1 bilico/pedana 300 kg working per:

- cassette multiple;
- bins;
- controllo spedizione;
- inventario.

## 7. Packaging

### B2B / ristorazione / gruppi acquisto

Preferenza:

- cassette riutilizzabili;
- liner solo se necessario;
- etichetta lotto/origine/prodotto;
- pallet/roll container se volume.

### Retail diretto

Opzioni:

- sacchetto/flow bag;
- punnet/clamshell;
- vaschetta termosigillata;
- fascetta/cartoncino per alcuni prodotti.

Non congelare materiale e grammatura prima del test shelf-life e del canale.

### MAP

Modified Atmosphere Packaging non è baseline. Richiede:

- film specifico;
- gas;
- validazione respirazione/prodotto;
- controllo saldatura;
- shelf-life study.

## 8. Termosigillatura

Working candidate class:

- manuale: €1,4–2,3k + IVA;
- semi-automatica: ~€2,1–4,0k + IVA.

Baseline preferita: **manuale professionale con stampo intercambiabile**, se gli SKU retail richiedono vaschetta sigillata.

Semi-auto soltanto dopo throughput misurato.

## 9. Etichettatura

Working:

- Zebra ZD421 203 dpi;
- trasferimento termico preferito per etichette che devono resistere meglio a umidità/condensa;
- Ethernet + USB preferiti;
- label size da SKU;
- barcode/QR per lotto;
- stampa locale senza cloud obbligatorio.

Benchmark: ~€500 + IVA per ZD421 TT Ethernet.

Consumabile benchmark:
- etichetta carta termica 100×50: ~€6,90 + IVA / 1.000;
- PPL 100×50 TT: ~€11,80 + IVA / 1.000.

Per cella umida/condensa, valutare PPL/adesivo appropriato invece di carta standard.

## 10. Tracciabilità

ID minimo lotto:

`crop + compartment + harvest_date/time + crew/batch + pack_date + SKU`.

Eventi:

- harvest;
- receiving weight;
- QC;
- cold-room in/out;
- pack;
- shipment;
- waste/regrade.

Barcode/QR deve poter essere letto da telefono/scanner e collegato al database locale.

## 11. Lavaggio: decisione separata

EFSA 2025 sottolinea che l'acqua di processo può diventare veicolo di cross-contamination.

Quindi:

- niente lavaggio "perché sembra più pulito";
- acqua di lavaggio gestita come processo;
- reintegro/ricambio e, se necessario, disinfezione;
- finale con qualità acqua appropriata alla destinazione;
- strumenti di misura e registri;
- separazione dirty-to-clean;
- scarico/riuso solo dopo progetto.

Macchina lava/centrifuga combinata e centrifughe elettriche restano **optional F3-B**.

## 12. Centrifugazione/asciugatura — benchmark

Opzioni:

- manual spinner 20 L ~€118 netto: backup/pilot;
- electric stainless 35 L / 70 kg/h ~€573 netto: candidate pilot;
- electric 70 L / 140 kg/h ~€715 netto: candidate scale-up;
- professional 12 kg/cycle ~€2.841 + IVA: benchmark higher-grade;
- washer+spinner 1,5–4 kg/cycle ~€1.997 + IVA.

La capacità catalogo deve essere verificata su baby leaf reale e danno meccanico.

## 13. Normativa packaging / label

Procurement guardrail:

- food-contact materials: Reg. (CE) 1935/2004;
- GMP FCM: Reg. (CE) 2023/2006, current consolidated version;
- fresh fruit/veg marketing/origin: Reg. delegato (UE) 2023/2429 e norme specifiche applicabili;
- prepacked food information: Reg. (UE) 1169/2011, se applicabile allo SKU.

Per ortofrutta fresca, origine e altre indicazioni richieste devono essere gestite dal master-data della label; non hard-code layout prima della verifica legale per ciascun canale/SKU.

## 14. Failure modes

- crate shortage;
- cassette non food-contact;
- product bruising;
- scale drift;
- legal-for-trade scale unavailable;
- printer/ribbon/label failure;
- wrong lot label;
- sealer temperature drift;
- seal contamination;
- wash water contamination;
- centrifuge damage to leaf;
- packaging shortage;
- scanner/database offline.

Fallback:

- stock cassette;
- second scale;
- spare printhead/label printer path;
- preprinted emergency lot labels;
- manual packing;
- B2B reusable-crate route;
- no wash;
- product directly to cold room.

## 15. Gate BOM-025

1. peak kg/day by crop;
2. peak kg/hour harvest;
3. kg/crate limit by crop;
4. crate count and turnaround;
5. sales mix B2B/retail;
6. SKU and package size;
7. washed vs unwashed leafy strategy;
8. shelf-life tests;
9. legal label template;
10. packaging supplier quotes;
11. actual workstation layout;
12. labor seconds/kg;
13. cell/precool interface;
14. AMR/cart interface;
15. HACCP;
16. commissioning and traceability test.
