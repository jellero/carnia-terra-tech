# Distribuzione irrigua serra — architettura e criteri

**Aggiornato:** 17 settembre 2026  
**Stato:** `ARCHITETTURA DEFINITA / PORTATE E QUANTITÀ DA CROP CARD E CALCOLO IDRAULICO`.

## 1. Architettura

Working architecture:

`fertirrigazione -> collettore principale -> 6 collettori comparto -> 4 settori/comparto -> linee di distribuzione -> emettitori`.

I 24 settori sono una scelta modulare iniziale. Possono diventare 18, 30 o altro se crop card e layout lo rendono tecnicamente migliore.

## 2. Testa settore

Ogni settore deve prevedere, in modo separato e accessibile:

- valvola manuale di isolamento;
- elettrovalvola NC;
- regolatore/riduttore di pressione se necessario;
- manometro o presa di pressione;
- raccordi smontabili;
- identificazione fisica e digitale;
- flush a valle;
- eventuale sensore pressione locale;
- eventuale feedback posizione/portata.

Non incorporare componenti in punti non accessibili senza svuotare o smontare l'intero comparto.

## 3. Gocciolatore candidato per fuori suolo

### Netafim PCJ / PCJ LCNL

Punti verificati:

- autocompensante;
- autopulente in continuo;
- versioni anti-drenaggio LCNL/HCNL;
- 2,0 l/h disponibile;
- PCJ LCNL 2 l/h: range pressione 0,7–4,0 bar, chiusura ~0,12 bar;
- filtrazione raccomandata 120 mesh / 130 micron;
- inserimento in PE cieco di spessore 0,9–1,2 mm;
- materiali UV-resistant e compatibili con nutrienti agricoli standard secondo produttore.

**Stato:** `CANDIDATO PRIORITARIO C1/C2/C6 / PORTATA E VARIANTE DA VALIDARE`.

La variante anti-drenaggio è preferibile per irrigazioni pulsate perché evita lo svuotamento della linea tra cicli e riduce il ritardo di erogazione alle piante più lontane.

## 4. Collegamento finale

Configurazione candidata:

`PE cieco -> PCJ LCNL -> microtubo PE 3/5 mm -> punto goccia/picchetto -> substrato`.

Benchmark Netafim:

- microtubo PE 5 mm OD / ~3,3 mm ID, bobina 200 m;
- punto goccia 14 cm, confezione 1.000 pz;
- asta guidata 3/5 mm, confezione 1.000 pz;
- gruppo preassemblato a 2/4 uscite disponibile per configurazioni multi-punto.

Lunghezza capillare reale va definita sul layout. Evitare lunghezze inutili che aumentano perdite, disordine e rischio piega.

## 5. C3–C5 leafy

Per leafy non assumere un punto goccia per pianta. Confrontare:

- dripline PC permanente;
- ala gocciolante leggera con passo definito;
- 1 o più linee per letto;
- lavaggio/disinfezione tra cicli;
- compatibilità con raccolta meccanica futura.

La scelta deve minimizzare lavoro di posa/rimozione e non ostacolare la meccanizzazione.

## 6. Dimensionamento idraulico

Per ogni settore:

1. definire numero emettitori o metri di dripline;
2. calcolare portata nominale;
3. applicare simultaneità/scenario massimo;
4. calcolare perdite in PE, valvole, raccordi e regolatori;
5. verificare pressione minima all'emettitore più sfavorito;
6. verificare velocità e colpo d'ariete;
7. dimensionare collettore e valvola;
8. confermare filtrazione e flush.

Formula base per punti singoli:

`Q [m³/h] = N × q[l/h] / 1000`.

Esempio puramente matematico: 1.000 gocciolatori da 2 l/h = 2 m³/h. Non implica che un settore Carnia TerraTech avrà 1.000 punti.

## 7. Pressioni

Obiettivo: usare la pressione minima che garantisce l'intero settore nel range autocompensante, riducendo stress su raccordi e consumi elettrici.

Non usare un regolatore 1–1,5 bar per default se il gocciolatore/linea e le perdite richiedono altro. La taratura deriva dal calcolo e dalla misura in campo.

## 8. Linee PE

Benchmark economici correnti, solo materiale:

- PE BD PN4 Ø25, 100 m: ~€40 IVA incl.;
- PE BD PN4 Ø32, 100 m: ~€55 IVA incl.;
- PE100 PN10/PN16 per dorsali robuste costa sensibilmente di più.

Il PN4 è adatto come benchmark per linee irrigue a bassa pressione ma non va assunto idoneo a una dorsale permanentemente pressurizzata o interrata.

## 9. Elettrovalvole

Benchmark BERMAD 1" 24 VAC:

- IR-21T PN10: ~€23,15 IVA incl. su retailer UE;
- 100DTV 1" PN10: ~€28,53 IVA incl. su retailer italiano;
- versioni professionali/dimensioni maggiori da RFQ in funzione di portata e perdita di carico.

24 valvole da €23,15 sarebbero ~€555,60 di solo hardware; non è il costo delle 24 teste settore.

## 10. Regolazione pressione

Benchmark Netafim Italia:

- regolatore PP 3/4": €9,89–18 + IVA a seconda della configurazione;
- 1,5": €41 + IVA;
- 2": €139 + IVA;
- 2" ottone multiregolazione: €316 + IVA.

La quantità e posizione dei regolatori dipendono dalla pressione comune e dalla necessità di ricette idrauliche diverse.

## 11. Strumentazione

Preferenza:

- 1 flow meter per comparto almeno;
- pressione comparto;
- sensori aggiuntivi sui settori critici o diagnostica mediante prese/manometri;
- contatore centrale di riferimento;
- lettura digitale integrata al PLC per allarmi.

Con 24 flow meter economici si ottiene granularità massima ma aumentano costo, manutenzione e punti guasto. La granularità definitiva va scelta con TCO.

## 12. Commissioning

Per ogni settore registrare:

- pressione ingresso/estremità;
- portata totale;
- tempo di pressurizzazione;
- uniformità campionata degli emettitori;
- volume per impulso;
- tempo di drenaggio/chiusura CNL;
- flush rate;
- eventuali perdite;
- baseline digitale per manutenzione predittiva.

## 13. Ricambi minimi

Da finalizzare, ma prevedere a scaffale:

- gocciolatori;
- microtubo;
- punti goccia/picchetti;
- tappi riparazione foro PE;
- raccordi;
- 1–2 elettrovalvole standardizzate;
- solenoidi;
- regolatore pressione;
- manometri/sensori;
- valvole flush.
