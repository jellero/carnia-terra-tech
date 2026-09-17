# Filtrazione acqua — architettura e criteri

**Aggiornato:** 17 settembre 2026  
**Stato:** `ARCHITETTURA DEFINITA / TAGLIE E STADI DA ANALISI ACQUA E PORTATE REALI`.

## 1. Obiettivo

Proteggere fertirrigazione, valvole e gocciolatori senza introdurre perdite di carico, manutenzione o consumi di controlavaggio non necessari.

Requisito minimo già imposto da BOM-013 per PCJ: **120 mesh / circa 130 µm**.

Il sistema non viene scelto dalla sola mesh. Servono almeno:

- origine acqua: acquedotto / pozzo / canale-superficiale / recupero pioggia / miscela;
- SST/turbidità;
- sabbia e granulometria;
- sostanza organica/alghe;
- ferro e manganese;
- durezza/alcalinità;
- EC/sali disciolti;
- pH;
- carica microbiologica se pertinente;
- portata di picco e portata di controlavaggio disponibile.

## 2. Architettura working

`fonte/accumulo -> eventuale separatore sabbia -> filtrazione primaria -> filtrazione fine di sicurezza 120 mesh -> pompe/fertirrigazione -> distribuzione BOM-013`

La posizione precisa di pompe e filtri nel P&ID definitivo verrà ottimizzata per NPSH, pressioni di controlavaggio, protezione pompe e compatibilità con fertilizzanti.

## 3. Scenari sorgente

### F1 — acqua pulita / rete / raccolta pioggia ben gestita

Candidato:

- filtro manuale o automatico a dischi/rete 120 mesh;
- filtro di sicurezza secondario se la criticità del processo lo giustifica.

### F2 — pozzo con sabbia

Candidato:

- idrociclone dimensionato sulla portata reale;
- scarico/svuotamento sabbia;
- filtro principale a dischi/rete 120 mesh;
- eventuale secondo filtro di sicurezza.

L'idrociclone non sostituisce il filtro fine.

### F3 — acqua superficiale / organico / alghe

Candidato:

- filtro a dischi automatico o filtro a graniglia/media se qualità difficile;
- filtro secondario 120 mesh;
- controlavaggio automatico se la frequenza manuale diventa onerosa.

### F4 — acqua con sali/durezza/ferro elevati

La filtrazione meccanica non risolve i disciolti. Valutare separatamente:

- acidificazione;
- ossidazione + filtrazione per Fe/Mn dove appropriato;
- addolcimento solo se tecnicamente giustificato;
- RO solo dopo analisi e bilancio concentrato/energia.

## 4. Filtri candidati

### Netafim-Arkal manuale 2" Dual 120 mesh

Benchmark:

- 2" filettato maschio;
- 25 m³/h max;
- 10 bar max;
- 120 mesh;
- **€241 + IVA** prezzo pubblico Netafim Italia.

Uso: filtro principale per acqua di qualità adeguata o secondario di sicurezza.

### Netafim-Arkal 2" Leader 120 mesh

Benchmark:

- prezzo pubblico **€182 + IVA**;
- candidato manuale più economico;
- portata e perdita reale da verificare sulla configurazione scelta.

### Spin-Klin 2" singolo automatico

Dati pubblici:

- 2";
- 20 m³/h nominali, 15 m³/h con acqua media qualità;
- 120 mesh / 130 µm;
- 10 bar standard;
- controlavaggio minimo 2,8 bar standard o 1,5 bar low-pressure;
- **€2.574 + IVA** benchmark shop Netafim Italia.

### Spin-Klin 2" doppio automatico

Dati pubblici:

- 3" DN80;
- 40 m³/h nominali, 30 m³/h acqua media qualità;
- 120 mesh / 130 µm;
- 10 bar standard;
- controlavaggio minimo 2,8 bar standard o 1,5 bar low-pressure;
- **€4.321 + IVA** benchmark shop Netafim Italia.

È il candidato più coerente se il picco reale si avvicina a 20–30 m³/h e si vuole automazione/ridondanza interna di elementi filtranti, ma non viene selezionato prima del calcolo.

### ScreenGuard automatico verticale 2"

Dati pubblici:

- 2";
- 25 m³/h max;
- 10 bar max;
- 2 bar min per controlavaggio;
- rete inox 316;
- pulizia automatica per tempo o Δp;
- **€2.988 + IVA** prezzo base osservato.

Da confrontare con Spin-Klin in funzione della natura dello sporco e della manutenzione.

## 5. Idrociclone candidato

Netafim-Arkal 2" plastica:

- range 15–25 m³/h;
- 10 bar max;
- efficienza dichiarata >90% sulle particelle di sabbia previste dal prodotto;
- **€363 + IVA**.

L'idrociclone è `CONDIZIONALE`: si installa solo se l'analisi/monitoraggio mostra sabbia o particelle pesanti che lo giustificano.

## 6. Ridondanza e bypass

Confrontare tre configurazioni:

- **R0**: un filtro principale + bypass solo manutenzione, fermo irrigazione durante intervento;
- **R1**: due filtri manuali in parallelo, ciascuno capace di una quota o della portata critica;
- **R2**: filtro automatico + filtro manuale di sicurezza/bypass dimensionato per modalità degradata.

Per Carnia TerraTech la preferenza è R1/R2 se il costo marginale è contenuto, perché un filtro intasato non deve diventare un single point of failure dell'intera serra.

## 7. Δp e controllo

Misurare almeno:

- pressione a monte filtro;
- pressione a valle filtro;
- Δp calcolato o trasmettitore differenziale;
- stato controlavaggio;
- volume/tempo controlavaggio;
- portata di linea.

Allarmi:

- Δp alto;
- Δp alto dopo controlavaggio;
- Δp anormalmente basso con portata alta;
- controlavaggio fallito;
- pressione insufficiente per controlavaggio;
- consumo acqua di lavaggio eccessivo.

## 8. Controlavaggio

Il controlavaggio deve essere dimensionato come carico idraulico vero.

Richiedere:

- portata istantanea necessaria;
- pressione minima;
- durata;
- volume per ciclo;
- frequenza prevista a qualità acqua dichiarata;
- scarico/recupero dell'acqua di lavaggio;
- comportamento durante irrigazione attiva.

Non assumere che le pompe di processo riescano automaticamente a sostenere il controlavaggio.

## 9. Ricambi

Minimo candidato:

- 1 pacco dischi 120 mesh per modello installato;
- guarnizioni/O-ring;
- membrana valvola controlavaggio;
- solenoidi/attuatori;
- manometri/trasduttori;
- elemento rete di ricambio se ScreenGuard;
- valvole manuali;
- kit pulizia dischi/rete.

Benchmark pubblico: pacco dischi automatico 120 mesh **€98 + IVA**; membrana Spin-Klin 2x2 **€29 + IVA**; elemento ScreenGuard Mini **€29 + IVA**.

## 10. Failure modes

- filtro progressivamente ostruito;
- rottura rete/dischi;
- bypass lasciato aperto;
- valvola controlavaggio bloccata;
- sensore Δp guasto;
- sabbia che bypassa idrociclone;
- pressione insufficiente al lavaggio;
- scarico controlavaggio ostruito/gelato;
- filtro troppo grande che lavora fuori range;
- filtro troppo piccolo con Δp e lavaggi continui;
- biofilm/precipitati chimici non risolti dalla filtrazione meccanica.

## 11. Gate

BOM-014 diventa ordinabile solo con:

1. analisi acqua rappresentativa e possibilmente nel periodo peggiore;
2. fonte/i e miscelazione acqua definite;
3. portata massima irrigazione simultanea;
4. portata minima disponibile;
5. pressione disponibile;
6. requisito controlavaggio;
7. scelta manuale/automatica;
8. decisione idrociclone sì/no;
9. eventuale media filtration;
10. strategia R0/R1/R2;
11. gestione scarico acqua lavaggio;
12. preventivi comparabili e piano ricambi.