# Carnia TerraTech — Openings, Doors & Compartments

**Stato:** `REQUISITI DEFINITI / MECCANISMI DA DIMENSIONARE E PREVENTIVARE`.

## 1. Funzione

Le aperture devono gestire ventilazione naturale, sicurezza vento/pioggia e separazione dei sei comparti senza creare un singolo failure domain.

## 2. Aperture laterali

Ogni comparto deve poter essere comandato indipendentemente.

Da definire nel progetto esecutivo:

- superficie apribile;
- altezza e posizione;
- corsa;
- lati apribili;
- roll-up, cremagliera o altra architettura;
- velocità apertura/chiusura;
- comportamento con vento forte;
- protezione pioggia;
- finecorsa;
- misura/stima della posizione reale;
- modalità manuale di emergenza.

## 3. Aperture zenitali

Da valutare in base a struttura, costo e bilancio di ventilazione.

Se presenti devono includere:

- cinematismo;
- alberi/cremagliere/push-pull;
- motoriduttori;
- supporti;
- finecorsa;
- protezione sovraccarico;
- logica vento/pioggia;
- possibilità di isolamento di un guasto.

## 4. Reti anti-insetto

La rete non viene scelta solo per numero di mesh.

Per ogni comparto si parte dai parassiti obiettivo e si verifica:

- apertura reale della maglia;
- percentuale area aperta;
- perdita di pressione/flusso;
- effetto sulla ventilazione estiva;
- durata UV;
- pulibilità;
- sostituzione;
- sigillatura dei bordi.

Una rete troppo fine può ridurre eccessivamente la ventilazione; il dimensionamento deve quindi essere integrato con aperture e clima.

## 5. Porte e accessi

Separare almeno:

- porte persone;
- porte materiali/carrelli;
- accessi AMR;
- accessi mezzi/manutenzione dove previsti;
- uscite di emergenza quando richieste.

Working requirement già esistente: accessi utili circa 2,5–3 m dove devono transitare AMR, carrelli o attrezzature. La quota finale dipende dai mezzi reali.

## 6. Compartimentazione

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

## 7. Automazione

Principio di comando:

`desired position → command → acknowledgement → observed state`.

Non è sufficiente inviare un comando e assumere che l'apertura si sia mossa.

Prevedere:

- comando locale;
- comando PLC;
- finecorsa o feedback;
- allarme incoerenza;
- interblocco vento/pioggia;
- watchdog;
- fallback sicuro;
- possibilità di manovra manuale.

## 8. BOM minima per ogni gruppo apertura

- motoriduttore;
- cremagliere/pignoni o cinematismo;
- alberi;
- giunti;
- supporti/cuscinetti;
- staffe;
- finecorsa/sensori posizione;
- quadro/protezioni;
- sezionatore locale;
- cavo potenza;
- cavo comando/dati;
- morsetti/pressacavi;
- rete anti-insetto;
- profili e fissaggi rete;
- bulloneria;
- ricambio critico.
