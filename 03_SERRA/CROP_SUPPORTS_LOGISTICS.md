# Carnia TerraTech — Crop Supports & Internal Logistics

**Aggiornato:** 17 settembre 2026  
**Stato:** `REQUISITI DEFINITI / BOM-006 SVILUPPATA / QUANTITÀ DA CROP CARD E LAYOUT`.

## 1. Obiettivo

La struttura della serra deve essere compatibile fin dall'inizio con colture sospese, raccolta, AMR, carrelli, manutenzione e future meccanizzazioni.

Il sistema C1/C2 è trattato come due sottosistemi distinti ma coordinati:

- supporto high-wire della coltura;
- supporto substrato e raccolta drenaggio fuori suolo.

BOM economica: `19_BOM_PRODOTTI_FORNITORI/SERRA_SUPPORTI_COLTURA_DRENAGGIO.md`.  
RFQ: `03_SERRA/RFQ_CROP_SUPPORT_DRAINAGE.md`.

## 2. Pomodoro e peperone

Per C1/C2 prevedere nel calcolo strutturale:

- filo/cavo portante high-wire;
- ancoraggi e tensionatori;
- hook o roller;
- spago;
- clip;
- sistemi di abbassamento/leaning;
- peso piante e frutti;
- carichi dinamici durante manutenzione/raccolta;
- canaline/gutter di drenaggio;
- slab/substrato saturo;
- supporti irrigazione e riscaldamento basso.

Il carico coltura deve essere fornito al progettista strutturale come dato esplicito e prudenziale.

Working geometry esistente: circa 12 file × 30 m per comparto C1/C2. Non è quantità d'ordine finché non sono chiusi steli/m², cultivar e layout.

## 3. Regole high-wire

Il numero di hook/roller deriva dal numero di steli attivi, non dai metri quadri genericamente.

Formule:

`hook = steli attivi + scorta`

`spago = hook × metri caricati per hook`

`clip = consumo clip/stelo/ciclo × steli + scorta`

Il filo portante, gli ancoraggi e i tenditori devono essere parte del calcolo della struttura serra. I benchmark retail non sostituiscono una specifica professionale di carico.

## 4. Drenaggio fuori suolo

La canalina deve:

- sostenere slab/substrato saturo;
- mantenere pendenza stabile;
- raccogliere tutto il drenaggio;
- evitare ristagni;
- essere lavabile e ispezionabile;
- non ostacolare AMR/operatori;
- consentire sostituzione per tratte;
- scaricare in collettore dedicato, non sul pavimento.

Confrontare almeno gutter metallico continuo e sistema plastico/modulare tecnicamente idoneo. La scelta dipende da carico, durata, numero giunti, pulizia, pendenza, costo installato e TCO.

Il drenaggio si collega al punto 04 per volume, EC, pH, temperatura, eventuale trattamento e possibile futuro recupero. Nessun riuso automatico viene previsto prima di validazione agronomica e fitosanitaria.

## 5. Leafy e baby leaf

Per C3–C5 il layout deve mantenere:

- letti modulari;
- corsie regolari;
- passaggi compatibili con future macchine di raccolta;
- linee irrigue facilmente sostituibili;
- drenaggio/pulizia;
- possibilità di riconfigurare la coltura senza modifiche strutturali.

Eventuali canali NFT o sistemi simili restano un'architettura separata da valutare per colture specifiche; non vengono confusi con le canaline per slab di pomodoro/peperone.

## 6. C6 vivaio/jolly

Deve poter accogliere:

- bancali/tavoli;
- piccoli lotti;
- propagazione;
- sensori sperimentali;
- illuminazione locale eventuale futura;
- fogging dedicato;
- layout riconfigurabile.

## 7. Corridoio tecnico

Working requirement: circa 4 m, da validare con mezzi reali.

Deve permettere traffico AMR, carrelli, manutenzione, cassette, accesso a quadri/collettori, evacuazione e pulizia.

## 8. AMR e carrelli

Prima di congelare porte/corsie servono ingombro AMR, raggio di sterzata, carico, docking, pendenze, soglie, pavimentazione e aree di svolta.

Working geometry registrata:

- AMR ~70–90 cm larghezza;
- corsia utile almeno ~1,2 m;
- svolta ~2–2,5 m.

Valori preliminari finché non è scelto il mezzo reale.

## 9. Pavimentazioni e sottoservizi

Distinguere aree coltivate, corsie pedonali, corsie AMR, corridoio tecnico, piazzole manutenzione e soglie.

Evitare tubi/cavi che diventino ostacoli permanenti. Pianificare canaline, passerelle, tubazioni, attraversamenti, pozzetti, derivazioni e riserva ampliamenti.

## 10. Ergonomia

Per ogni layout verificare:

- distanza percorsa/giorno;
- peso movimentato;
- piegamenti/sollevamenti;
- attività trasferibili ad AMR/carrello;
- appoggio utensili/cassette;
- ricarica attrezzature;
- tempo richiesto per lowering, clipping e pulizia fine ciclo.

L'obiettivo è togliere lavoro improduttivo prima di automatizzare processi inefficienti.

## 11. Gate di validazione

Supporti e drenaggio passano a `VALIDATO` solo con:

- crop card C1/C2 chiusa;
- steli/m² e file definitive;
- carichi accettati dal progettista strutturale;
- scelta hook/roller/spago/clip;
- scelta slab/substrato;
- shop drawing gutter/supporti;
- pendenze e collettore drenaggio;
- preventivo completo;
- piano manutenzione, ricambi e fine ciclo.
