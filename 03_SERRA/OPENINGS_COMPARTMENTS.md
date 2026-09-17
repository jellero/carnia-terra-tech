# Carnia TerraTech — Openings, Doors & Compartments

**Aggiornato:** 17 settembre 2026  
**Stato:** `REQUISITI DEFINITI / CANDIDATI ATTUATORI E RETI IDENTIFICATI / GEOMETRIA DA DIMENSIONARE`.

BOM collegata: `19_BOM_PRODOTTI_FORNITORI/SERRA_APERTURE_RETI_ANTIINSETTO.md`.

## 1. Funzione

Le aperture devono gestire ventilazione naturale, sicurezza vento/pioggia e separazione dei sei comparti senza creare un singolo failure domain.

La rete anti-insetto è parte del sistema di ventilazione: non può essere aggiunta dopo il dimensionamento perché modifica la portata d'aria disponibile.

## 2. Aperture laterali

Ogni comparto deve poter essere comandato indipendentemente.

Da definire nel progetto esecutivo:

- superficie apribile;
- altezza e posizione;
- corsa;
- uno o due lati apribili;
- lunghezza di ogni tratta;
- roll-up, cremagliera o altra architettura;
- coppia e velocità apertura/chiusura;
- numero massimo giri/corsa;
- comportamento con vento forte;
- protezione pioggia;
- finecorsa;
- misura posizione reale;
- modalità manuale di emergenza.

Working quantity iniziale per studio costi: **6–12 gruppi laterali motorizzati**. È un intervallo di progetto, non una quantità d'ordine.

## 3. Candidati attuatori

### Ridder RW45-L

Candidato professionale per ventilazione/schermatura. Prezzo osservato presso Sleegers: **€675,49 + IVA** per articolo Ridder 531113. IP55, vite senza fine autobloccante, finecorsa RSU integrato, feedback RPU opzionale.

Fonte: https://webshop.sleso.nl/products/rw45l-motorreductoren

### Alternative professionali

Sistemas Hortícolas Almería pubblica benchmark per gruppi con catena/pignoni:

- 100 Nm / 0,09 kW: €410 + IVA;
- 240 Nm / 0,25 kW: €450 + IVA;
- 400 Nm / 0,37 kW: €480 + IVA;
- 800 Nm / 0,75 kW: €830 + IVA.

Il prezzo non sostituisce il dimensionamento della coppia.

### Roll-up 24 V

Per tratte compatibili possono essere valutati attuatori 24 V specifici da serra. Benchmark Woosung Hitec WSM-4035: 40 Nm nominali / 60 Nm max dichiarati, 62 W nominali, prezzo £159 + VAT presso Northern Polytunnels.

Questa classe non viene usata automaticamente al posto di un sistema industriale: verificare duty-cycle, IP, coppia, lunghezza tratta, ricambi e integrazione.

## 4. Aperture zenitali

Restano da valutare in base a struttura, rete anti-insetto e bilancio di ventilazione.

Se presenti devono includere:

- cinematismo;
- alberi/cremagliere/push-pull;
- motoriduttori;
- supporti;
- finecorsa;
- feedback posizione;
- protezione sovraccarico;
- logica vento/pioggia;
- possibilità di isolamento di un guasto.

La necessità di zenitali deve essere verificata soprattutto negli scenari con reti fini ad alta perdita di ventilazione.

## 5. Reti anti-insetto

La rete non viene scelta solo per numero di mesh.

Candidati Arrigoni Air Plus registrati nella BOM:

- **50 Air Plus 3353BT:** foro 0,33×0,68 mm, passaggio aria ~47%, riduzione ventilazione ~30%;
- **60 Air Plus 3363BT:** foro ~0,33×0,45 mm, passaggio aria ~40%, riduzione ventilazione ~31%;
- **80 Air Plus 3382BT:** foro 0,15×0,31 mm, passaggio aria ~26%, riduzione ventilazione ~42%, indicata per tripidi;
- **90 Air Plus 3386BT:** passaggio aria ~22%, riduzione ventilazione ~45%, da usare solo se la necessità fitosanitaria giustifica la penalizzazione.

Fonte: https://arrigoni.it/agrotextile/applicazioni/protezione-dagli-insetti/

Per ogni comparto partire dai parassiti obiettivo e verificare:

- apertura reale della maglia;
- percentuale area aperta;
- perdita di pressione/flusso;
- effetto sulla ventilazione estiva;
- durata UV;
- pulibilità;
- sporcamento nel tempo;
- sostituzione;
- sigillatura dei bordi.

## 6. Regola di scelta mesh

Non adottare automaticamente una rete molto fine su tutti i comparti.

La scelta deve incrociare:

1. rischio fitosanitario del comparto;
2. vettore/parassita target;
3. coltura;
4. strategia IPM;
5. superficie apribile;
6. disponibilità di zenitali;
7. HAF;
8. temperature estive del sito;
9. possibilità di pulire la rete;
10. costo e vita utile.

Se la rete necessaria riduce significativamente la ventilazione, il progetto deve compensare con area apribile o architettura climatica, non accettare implicitamente temperature più alte.

## 7. Porte e accessi

Separare almeno:

- porte persone;
- porte materiali/carrelli;
- accessi AMR;
- accessi mezzi/manutenzione dove previsti;
- uscite di emergenza quando richieste.

Working requirement già esistente: accessi utili circa 2,5–3 m dove devono transitare AMR, carrelli o attrezzature. La quota finale dipende dai mezzi reali.

## 8. Compartimentazione

I sei comparti devono limitare propagazione di:

- problemi climatici;
- parassiti/patogeni;
- guasti impiantistici;
- errori di ricetta.

Da progettare:

- pareti/divisori;
- porte tra comparti;
- passaggi tecnici sigillabili;
- eventuali vestiboli o zone filtro nei punti ad alto rischio;
- percorsi di materiale e personale.

## 9. Automazione

Principio di comando:

`desired position → command → acknowledgement → observed state`.

Non è sufficiente inviare un comando e assumere che l'apertura si sia mossa.

Prevedere:

- comando locale;
- comando PLC;
- finecorsa;
- feedback posizione dove utile;
- allarme incoerenza;
- sovraccarico motore;
- interblocco con meteo;
- watchdog;
- fallback sicuro;
- possibilità di manovra manuale.

La posizione sicura con vento/pioggia deve essere definita dal costruttore e dal progetto strutturale, non assunta genericamente.

## 10. Meteo per sicurezza

Il PLC deve disporre di segnali locali affidabili almeno per:

- velocità vento;
- raffica;
- pioggia;
- temperatura esterna;
- eventualmente direzione vento.

La perdita del server o di Internet non deve impedire la protezione locale della serra.

## 11. BOM minima per ogni gruppo apertura

- motoriduttore;
- cremagliere/pignoni, catena o cinematismo;
- alberi/tubi avvolgimento;
- giunti;
- supporti/cuscinetti;
- staffe;
- finecorsa;
- sensore/feedback posizione;
- quadro/protezioni;
- sezionatore locale;
- cavo potenza;
- cavo comando/dati;
- comando locale;
- morsetti/pressacavi;
- rete anti-insetto;
- profili e fissaggi rete;
- guarnizioni/sigillature;
- bulloneria;
- posa;
- commissioning;
- ricambi critici.

## 12. Gate

Il sottosistema diventa `DA PREVENTIVARE` in modo definitivo quando sono noti:

- geometria della serra;
- lunghezza e altezza di ogni apertura;
- lati apribili;
- eventuali zenitali;
- mesh per comparto;
- forza/coppia richiesta;
- strategia meteo;
- interfacce PLC/elettriche.
