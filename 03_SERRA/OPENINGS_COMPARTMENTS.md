# Carnia TerraTech — Openings, Doors & Compartments

**Aggiornato:** 17 settembre 2026  
**Stato:** `REQUISITI DEFINITI / BOM-003 E BOM-007 SVILUPPATE / GEOMETRIA DA DIMENSIONARE`.

BOM collegate:

- `19_BOM_PRODOTTI_FORNITORI/SERRA_APERTURE_RETI_ANTIINSETTO.md`;
- `19_BOM_PRODOTTI_FORNITORI/SERRA_PORTE_COMPARTIMENTI_GRONDE.md`.

RFQ porte/compartimenti/gronde:

- `03_SERRA/RFQ_DOORS_PARTITIONS_GUTTERS.md`.

Note di validazione aggiuntive:

- `03_SERRA/BOM007_VALIDATION_NOTES.md`.

## 1. Funzione

Le aperture devono gestire ventilazione naturale, sicurezza vento/pioggia e separazione dei sei comparti senza creare un singolo failure domain.

La rete anti-insetto è parte del sistema di ventilazione: non può essere aggiunta dopo il dimensionamento perché modifica la portata d'aria disponibile.

Porte e compartimentazioni sono parte della strategia IPM e della logistica, non semplici chiusure architettoniche.

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

Working concept:

- fino a 6 varchi controllati dal corridoio tecnico ai comparti, da confermare col layout;
- accessi esterni logistici separati;
- C6 predisposto per eventuale vestibolo/airlock se il piano IPM lo giustifica.

Per i varchi interni la preferenza iniziale è una porta scorrevole professionale quando compatibile con sicurezza e tenuta, perché non invade la corsia e facilita AMR/carrelli.

Regole:

- soglia il più possibile a raso;
- binari/rulli accessibili e pulibili;
- guarnizioni/spazzole sostituibili;
- apertura manuale sempre disponibile;
- contatto stato porta dove utile;
- motorizzazione futura solo se giustificata dai flussi e dall'AMR;
- una porta motorizzata non deve diventare single point of failure per l'accesso o l'evacuazione.

Benchmark aggiuntivo registrato: ACD `Patio door alu`, porta scorrevole laterale greenhouse, €349 osservati. È solo benchmark accessorio, non porta professionale di progetto.

Working requirement storico: accessi utili circa 2,5–3 m dove devono transitare AMR, carrelli o attrezzature. La quota finale dipende dai mezzi reali.

## 8. Compartimentazione

I sei comparti devono limitare propagazione di:

- problemi climatici;
- parassiti/patogeni;
- guasti impiantistici;
- errori di ricetta;
- schizzi e materiale vegetale durante pulizia/manutenzione.

Working quantity: **5 separazioni principali** tra 6 comparti, da correggere col layout reale.

Tre scenari da quotare:

- **P1 leggero:** film/telo tecnico completo;
- **P2 ibrido — preferenza iniziale:** fascia bassa rigida/lavabile + parte superiore leggera;
- **P3 rigido:** pannello policarbonato o equivalente a tutta altezza.

P2 parte favorito come concetto perché concentra robustezza e lavabilità nella zona di urto senza caricare inutilmente tutta la struttura, ma resta da confrontare economicamente e fitosanitariamente.

Tutte le penetrazioni di tubi/cavi/canaline devono usare passaparete, guarnizioni o piastre rimovibili; evitare fori aperti che annullino la separazione.

Benchmark materiali:

- policarbonato trasparente 10 mm FVG 2026: €25,50/m² materiale;
- PE 200 µm flame-retardant FVG SUN 4 FR: €4,40–4,60/m² IVA inclusa come benchmark P1; conformità/applicazione italiana da verificare.

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

## 10. Meteo e pioggia

Il PLC deve disporre di segnali locali affidabili almeno per:

- velocità vento;
- raffica;
- pioggia;
- temperatura esterna;
- eventualmente direzione vento.

La perdita del server o di Internet non deve impedire la protezione locale della serra.

Per gronde, pluviali e troppo-pieno, il dimensionamento del sito reale userà **RainMap FVG** / LSPP regionali con coordinate, durata e tempo di ritorno appropriati. Il serbatoio da 300 m³ serve al bilancio idrico ma non sostituisce il dimensionamento della portata istantanea.

Il troppo-pieno deve funzionare in modo passivo/failure-safe anche con serbatoio pieno e PLC offline.

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

Per porte, compartimentazioni, gronde e pluviali usare la distinta completa di BOM-007.

## 12. Gate

Aperture/reti diventano `DA PREVENTIVARE` definitivamente quando sono noti geometria, lati apribili, mesh, coppie, strategia meteo e interfacce PLC.

Porte/compartimenti/gronde diventano `VALIDATI` solo con:

- layout e flussi persone/AMR definiti;
- dimensioni nette dei varchi;
- piano IPM e necessità eventuale airlock;
- shop drawing dei divisori;
- dettagli delle penetrazioni;
- gronde integrate col costruttore della serra;
- RainMap/calcolo idraulico del sito;
- percorso di troppo-pieno verificato;
- RFQ confrontabili;
- commissioning e lista ricambi.
