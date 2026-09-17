# BOM-026 — Pergolato, vite e area relax

**Aggiornato:** 18 settembre 2026  
**Ambito:** pergolato strutturale + vite/rampicanti + area relax + impianti esterni.  
**Stato:** `ARCHITETTURA STRUTTURATA / QUANTITÀ DA MASTERPLAN / STRUTTURA E FONDAZIONI DA CALCOLO / PREZZI UNITARI BENCHMARK`.

## 1. Regola di lettura

Questa BOM contiene **prezzi unitari e riferimenti**, non una quantità inventata per chiudere artificialmente il totale.

Le colonne `DA LAYOUT`, `DA CALCOLO` e `RFQ` sono intenzionali.

Prezzi osservati il 18 settembre 2026 salvo diversa indicazione. I prezzi retail sono benchmark di acquisto e non sostituiscono un'offerta professionale/installata.

## 2. Distinta pezzo per pezzo

| Codice | Voce | Q.tà | UM | Stato | Benchmark unitario |
|---|---|---:|---|---|---:|
| PG-SURVEY | rilievo/layout esecutivo area | 1 | lotto | BASELINE | RFQ |
| PG-ENG-STR | calcolo strutturale neve/vento/fondazioni | 1 | lotto | BASELINE | RFQ |
| PG-GEO | integrazione geotecnica specifica, se necessaria | 0–1 | lotto | CONDITIONAL | RFQ |
| PG-PERMIT | pratiche/verifiche edilizie-strutturali | 1 | lotto | BASELINE | RFQ |
| PG-POST-GL24 | legno lamellare GL24h classe montante | DA CALCOLO | cad/m³ | CANDIDATO | retail reference 120×120×6000: €83,50/cad |
| PG-BEAM-GL24 | legno lamellare GL24h classe trave primaria | DA CALCOLO | cad/m³ | CANDIDATO | retail reference 120×160×4000: €74,90/cad |
| PG-RAFTER-GL24 | legno lamellare GL24h classe secondaria | DA CALCOLO | cad/m³ | CANDIDATO | retail reference 80×120×4000: €39,90/cad |
| PG-STEEL-ALT | struttura acciaio zincato | DA CALCOLO | kg/lotto | ALTERNATIVA | RFQ |
| PG-CONN | staffe/piastre/connessioni strutturali | DA CALCOLO | lotto | BASELINE | RFQ |
| PG-BOLT | bulloneria strutturale | DA CALCOLO | lotto | BASELINE | RFQ |
| PG-BRACE | controventi/tiranti strutturali | DA CALCOLO | lotto | BASELINE | RFQ |
| PG-POST-BASE | scarpe/piedi strutturali | DA CALCOLO | cad | BASELINE | RFQ |
| PG-WOOD-FIN | ciclo finitura/protezione legno | DA SUPERFICIE | lotto | IF WOOD | RFQ |
| PG-FND-EXC | scavi plinti | DA CALCOLO | m³ | BASELINE | prezzario/RFQ |
| PG-FND-CONC | calcestruzzo fondazioni | DA CALCOLO | m³ | BASELINE | FVG 2026 C25/30 direct foundations: €237,52/m³, esclusi ferro/casseforme |
| PG-FND-REBAR | acciaio armatura | DA CALCOLO | kg | BASELINE | prezzario/RFQ |
| PG-FND-FORM | casseforme | DA CALCOLO | m² | BASELINE | prezzario/RFQ |
| PG-FND-ANCHOR | tirafondi/ancoraggi | DA CALCOLO | set | BASELINE | RFQ |
| PG-FND-SCREW | vite di fondazione certificata | DA CALCOLO | cad | CONDITIONAL | RFQ + geotecnica/pull test |
| PG-TRELLIS-WIRE | cavo/fune griglia vite | DA LAYOUT | m | BASELINE | RFQ |
| PG-TRELLIS-TENS | tenditore | DA LAYOUT | cad | BASELINE | RFQ |
| PG-TRELLIS-END | terminali/occhielli/ancoraggi | DA LAYOUT | lotto | BASELINE | RFQ |
| PG-SHADE | rete/telo ombreggiante removibile | DA LAYOUT | m² | OPTIONAL | RFQ |
| PG-SHADE-HW | ferramenta telo removibile | DA LAYOUT | lotto | OPTIONAL | RFQ |
| PG-VINE | barbatella vite da tavola resistente, benchmark vivaio | DA LAYOUT | cad | CANDIDATO | €5,95/cad retail benchmark |
| PG-VINE-GUARD | tutore/protezione giovane pianta | DA LAYOUT | cad | BASELINE | RFQ |
| PG-VINE-TIE | legacci sostituibili | DA LAYOUT | lotto | BASELINE | RFQ |
| PG-IRR-KIT | kit goccia 100 m², riferimento componenti | 0–1 ref | kit | BENCHMARK | €54,90 retail |
| PG-IRR-VALVE | valvola/elettrovalvola zona | 1 | cad | BASELINE | RFQ |
| PG-IRR-FILTER | filtrazione/regolazione dedicata se richiesta | 1 | set | BASELINE | RFQ / interface BOM-014 |
| PG-IRR-PE | linea PE e raccordi | DA LAYOUT | m | BASELINE | RFQ |
| PG-IRR-EMIT | gocciolatori/ala | DA LAYOUT | cad/m | BASELINE | RFQ |
| PG-IRR-DRAIN | punto lavaggio/svuotamento | 1 | set | BASELINE | RFQ |
| PG-SURF-EXC | preparazione piano | DA LAYOUT | m²/m³ | BASELINE | prezzario/RFQ |
| PG-SURF-GEOTEX | geotessile ove richiesto | DA LAYOUT | m² | CONDITIONAL | prezzario/RFQ |
| PG-SURF-BASE | sottofondo granulare | DA LAYOUT | m³ | BASELINE | FVG 2026 reference €44,80/m³ for granular foundation material |
| PG-SURF-GRAVEL | ghiaietto/drenante | DA LAYOUT | m³ | BASELINE | FVG 2026 reference €32,41/m³ mechanical placing; exact layer by design |
| PG-SURF-GRID | griglia permeabile salvaprato/stabilizzazione | DA LAYOUT | m² | CANDIDATO | €17,71/m² retail hardware benchmark |
| PG-EDGE | bordo/contenimento finitura | DA LAYOUT | m | BASELINE | RFQ |
| PG-DRAIN | canaletta/pozzetto locale | DA DRENAGGIO | m/cad | CONDITIONAL | RFQ |
| PG-TABLE-8 | tavolo outdoor ~8 posti | DA LAYOUT | cad | CANDIDATO | €310 retail benchmark |
| PG-SET-8 | set tavolo + 8 sedute | DA LAYOUT | set | ALTERNATIVA | €629,99 retail promo benchmark |
| PG-BENCH | panca outdoor | DA LAYOUT | cad | OPTIONAL | RFQ |
| PG-FURN-COVER | protezione/stoccaggio arredi | DA ARREDO | lotto | OPTIONAL | RFQ |
| PG-LIGHT | apparecchio LED outdoor IP65 classe 10 W | DA FOTOMETRIA | cad | CANDIDATO | €62,66 IVA incl. benchmark |
| PG-LIGHT-HW | staffe/scatole/accessori luce | DA LAYOUT | lotto | BASELINE | RFQ |
| PG-LIGHT-CTRL | timer/astronomico + override | 1 | set | CANDIDATO | RFQ |
| PG-SOCKET | presa outdoor IP55 16 A classe Gewiss GW27841 | DA LAYOUT | cad | BASELINE | prezzo RFQ |
| PG-ELEC-CABLE | FG16OR16 3×2,5 mm² reference | DA ROUTE | m | BENCHMARK | €3,10/m retail |
| PG-CONDUIT-40 | cavidotto doppia parete 40 mm | DA ROUTE | m | BASELINE | FVG 2026 €1,83/m reference |
| PG-ELEC-BOX | scatole/derivazioni outdoor | DA LAYOUT | cad | BASELINE | RFQ |
| PG-ELEC-PROT | protezioni quadro circuito outdoor | 1 | set | BASELINE | DA PROGETTO/RFQ |
| PG-ELEC-SPD | protezione sovratensione se richiesta | 0–1 | set | CONDITIONAL | DA PROGETTO/RFQ |
| PG-ELEC-INSTALL | posa/prove/documentazione elettrica | 1 | lotto | BASELINE | RFQ |
| PG-NET-CAT6A | cavo Cat6A outdoor PE | DA ROUTE | m | BASELINE | ~€78,03/100 m benchmark catalogo |
| PG-NET-AP | Ubiquiti U7 Outdoor | 1 | cad | CANDIDATO | €185 |
| PG-NET-ETHSPD | Ubiquiti Ethernet Surge Protector | 1 | cad | CANDIDATO | €12 |
| PG-NET-POE | PoE switch/injector se non già disponibile | 0–1 | cad | CONDITIONAL | RFQ |
| PG-NET-INSTALL | terminazioni, test e configurazione | 1 | lotto | BASELINE | RFQ |
| PG-SP-TRELLIS | kit cavo/tenditore/terminali di ricambio | 1 | set | SPARE | RFQ |
| PG-SP-IRR | gocciolatori/raccordi ricambio | 1 | set | SPARE | RFQ |
| PG-SP-ELEC | guarnizioni/accessori elettrici critici | 1 | set | SPARE | RFQ |
| PG-SP-NET | surge protector/rete ricambio | 0–1 | set | SPARE | RFQ |
| PG-COM | commissioning + as-built + training | 1 | lotto | BASELINE | RFQ |

## 3. Struttura in legno — benchmark, non dimensionamento

Riferimenti retail Binderholz/GL24h osservati:

- 80×120×4000 mm: **€39,90/cad**;
- 120×120×6000 mm: **€83,50/cad**;
- 120×160×4000 mm: **€74,90/cad**;
- 100×200×6000 mm: **€118,50/cad**.

Queste sezioni servono esclusivamente per costruire un costo unitario di mercato.

**Non costituiscono la scelta strutturale.**

La distinta finale deve essere generata dal calcolo e riportare volume totale di legno, lunghezze commerciali e sfrido.

## 4. Fondazioni — come leggere €237,52/m³

Il Prezzario FVG 2026 riporta un riferimento per calcestruzzo C25/30 in fondazioni dirette pari a **€237,52/m³** nella voce consultata, con esclusioni indicate dalla voce per armature e casseforme.

Quindi:

`costo_plinto != volume × 237,52`

Il costo installato comprende anche:

- scavo;
- eventuale magrone;
- armatura;
- casseforma;
- tirafondi;
- piastra/scarpa;
- reinterro;
- ripristino;
- trasporto/mezzi;
- posa;
- eventuale drenaggio.

Il volume è `DA CALCOLO`.

## 5. Griglia vite

La griglia deve essere una distinta propria, non “filo incluso nella pergola”.

Richiedere quantità e costo di:

- metri di cavo;
- tenditori;
- terminali;
- ancoraggi;
- protezioni estremità;
- manodopera tensionamento;
- ricambio iniziale.

Il carico della vite e la pretensione entrano nel calcolo strutturale.

## 6. Vite

Benchmark pubblico di vivaio specializzato per viti da tavola resistenti:

- **€5,95/cad** per diverse varietà osservate.

Il costo pianta è però una parte piccola del costo reale di impianto.

Aggiungere:

- trasporto;
- tutore;
- protezione;
- legacci;
- preparazione punto impianto;
- irrigazione;
- eventuali fallanze;
- ore di potatura/legatura.

La varietà resta `DA AGRONOMIA/MICROCLIMA`.

## 7. Irrigazione

Benchmark retail kit 100 m²:

- ala/goccia 2 L/h classe;
- raccordi;
- filtro;
- **€54,90/kit** osservato.

Usarlo per controllo prezzo componenti, non come progetto definitivo.

Il sistema reale deve interfacciarsi con BOM-013/BOM-014 e avere propria intercettazione e possibilità di svuotamento invernale.

## 8. Superficie e drenaggio

Riferimenti:

- materiale granulare per fondazione stradale, Prezzario FVG 2026: **€44,80/m³** nella voce consultata;
- ghiaia drenante con posa meccanica, riferimento Prezzario FVG 2026: **€32,41/m³** nella voce consultata;
- griglia permeabile retail: **€17,71/m²** hardware benchmark.

Non sommare questi numeri senza stratigrafia.

Servono prima:

- area netta;
- quote;
- spessori;
- terreno;
- capacità portante;
- percorrenza pedonale/carrabile;
- gestione acque.

## 9. Arredi

Due benchmark separati:

- tavolo outdoor allungabile ~8 posti: **€310**;
- set tavolo + 8 sedute: **€629,99** prezzo promo osservato.

Decisione dopo layout.

L'area può partire con arredo essenziale e aggiungere sedute in seguito senza impatto sulla struttura, purché affollamento e vie di passaggio restino coerenti col progetto.

## 10. Illuminazione

Benchmark apparecchio LED outdoor:

- 10 W;
- 3000 K;
- IP65;
- **€62,66 IVA inclusa/cad** osservato.

Non fissare il numero di apparecchi senza layout e verifica illuminotecnica.

Costi da aggiungere:

- supporti;
- scatole;
- cavo;
- cavidotto;
- comando;
- protezioni;
- posa;
- prova;
- eventuale scavo.

## 11. Prese e distribuzione elettrica

Candidato classe prodotto:

- Gewiss GW27841, presa 2P+T 16 A, IP55;
- prezzo da RFQ/distributore.

Benchmark cavo:

- FG16OR16 3×2,5 mm²: **€3,10/m** retail osservato.

Benchmark cavidotto:

- doppia parete Ø40 mm: **€1,83/m** da Prezzario FVG 2026 nella voce consultata.

Sezioni, numero linee e protezioni sono `DA PROGETTO ELETTRICO`.

## 12. Rete

Working candidate:

- Ubiquiti U7 Outdoor: **€185**;
- Ethernet Surge Protector: **€12**.

Cavo Cat6A outdoor 100 m:

- benchmark catalogo ~**€78,03/100 m**, prima di verificare regime IVA/spedizione del fornitore.

Aggiungere:

- terminazioni;
- patch;
- PoE;
- switch/injector se necessario;
- posa;
- certificazione/test tratta;
- configurazione;
- eventuale secondo AP solo dopo survey.

## 13. Pergola bioclimatica — benchmark alternativo

Prezzi pubblici osservati mostrano un ordine di grandezza molto variabile:

- PERGOLUX collection: da circa **€3.339**;
- pergola 4×4 manuale retail: circa **€8.190**;
- pergola 6×4 motorizzata retail: circa **€9.170**.

Questi prezzi **non sono comparabili direttamente** con il pergolato progettato BOM-026 perché possono differire per:

- dimensioni;
- carico neve;
- vento;
- fondazioni;
- posa;
- pratiche;
- drenaggio;
- elettrico;
- garanzia;
- compatibilità con vite.

Servono solo per evitare di sottostimare o sovrastimare a priori l'alternativa.

## 14. OPEX/manutenzione da contabilizzare

La BOM finale deve attribuire almeno:

| Attività | Driver |
|---|---|
| potatura invernale | n. piante / forma allevamento |
| potatura verde/legature | vigoria / stagione |
| raccolta frutto | n. piante / destinazione |
| pulizia foglie/frutti | superficie / stagione |
| trattamento/protezione legno | ciclo fornitore |
| controllo ferramenta | n. connessioni |
| ritensionamento cavi | n. linee |
| rimozione/rimontaggio telo | m² / sistema |
| lavaggio irrigazione | n. zone |
| invernaggio irrigazione | n. zone |
| pulizia drenaggi | m / n. pozzetti |
| verifica elettrica | impianto |
| ricambio LED/driver | vita reale |
| manutenzione AP/rete | apparati |

Ore/anno da misurare dopo layout e prima dell'approvazione finale.

## 15. Vita utile e ricambi

Richiedere dal fornitore la vita utile dichiarata di:

- struttura;
- zincatura/protezione;
- finitura legno;
- telo;
- cavi/tenditori;
- arredi;
- luci/driver;
- prese/scatole;
- AP;
- irrigazione.

Ricambi minimi:

- tenditore + terminali;
- legacci;
- emettitori/raccordi;
- minuteria;
- accessori elettrici soggetti a danneggiamento;
- surge protector rete.

## 16. Costo finale

Il costo non viene chiuso finché mancano quantità.

Formula di controllo:

`CAPEX_026 = Σ(qty_i × unit_cost_i) + posa + progettazione + trasporto + scavi + mezzi + commissioning + pratiche`.

Per ogni preventivo riportare separatamente:

- netto;
- IVA;
- installazione;
- trasporto;
- opere civili;
- progettazione;
- ricambi;
- OPEX annuo.

## 17. Gate di acquisto

Nessun ordine strutturale prima di:

1. layout approvato;
2. dati sito neve/vento;
3. verifica regime edilizio;
4. geotecnica sufficiente;
5. calcolo;
6. fondazioni;
7. scelta materiale;
8. RFQ comparabile;
9. costo installato;
10. piano manutenzione.

Nessun ordine vite prima di:

1. esposizione;
2. uso del frutto;
3. forma di allevamento;
4. disponibilità varietale;
5. irrigazione;
6. piano fitosanitario/agronomico.

Nessun ordine elettrico prima di schema e percorso reale.
