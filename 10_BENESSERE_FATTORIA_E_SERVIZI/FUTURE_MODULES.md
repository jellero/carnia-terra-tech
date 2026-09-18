# Carnia TerraTech — Benessere, fattoria e servizi futuri

**Aggiornato:** 18 settembre 2026.  
**Stato:** BOM-023 pulizia galline, BOM-026 pergolato/vite/relax e BOM-027 fattoria didattica sviluppate; spaccio 24/7 da sviluppare.

## 1. Obiettivo del blocco

Queste funzioni non sono accessori decorativi: servono a ridurre lavoro indesiderato, migliorare la qualità della vita, aumentare il valore dell'azienda e creare opzioni di ricavo e relazione con il territorio.

Devono però essere introdotte per fasi, senza complicare il core agricolo prima che produzione, cassa e manutenzione siano stabili.

## 2. Robot autonomo per prato e verde

### Funzione

Ridurre quasi a zero il taglio manuale ordinario delle aree a prato e mantenere l'azienda ordinata in modo continuativo.

### Requisiti da chiudere nella BOM dedicata

- superficie reale da mantenere;
- pendenze, strettoie, bordi, fossi e attraversamenti;
- presenza di bambini/visitatori/animali;
- funzionamento senza filo perimetrale preferibile se affidabile sul sito;
- RTK/GNSS o sistema equivalente;
- gestione multi-zona;
- antifurto e geofencing;
- base di ricarica protetta;
- ricambi lame, ruote e batterie;
- manutenzione invernale;
- integrazione con irrigazione e percorsi.

**Stato:** `DA ANALIZZARE` — prevista comparazione di prodotti reali e TCO.

## 3. Pulizia automatizzata area galline

### Funzione

Le galline sono free-range nel dominio aziendale dedicato: ricovero, portico, prato e parcheggi/aree esterne rese accessibili. Il sistema di pulizia deve quindi coprire l'intero dominio accessibile agli animali, non soltanto il ricovero.

### Architettura working

La soluzione viene divisa in quattro livelli coordinati:

1. raccolta concentrata nel ricovero, soprattutto sotto posatoi/zone di riposo, con piano fessurato + nastro/raschiatore o soluzione equivalente;
2. rover sanitario dedicato, che percorre ricovero, portico, parcheggi e prato ma non entra mai nelle aree pulite di serra/Tech Barn;
3. testate/strategie diverse per superficie: raccolta spot e aspirazione/raschiamento sui pavimenti duri; spot-pickup vision a basso impatto sul prato; modalità specifica per ricovero/lettiera;
4. dirty dock per ricarica, svuotamento, lavaggio sottoscocca/ruote e gestione del materiale raccolto.

Non si assume che una spazzatrice commerciale standard raccolga correttamente deiezioni fresche di gallina sul prato. La funzione grass-pickup resta R&D da pilot, con benchmark da robot outdoor e letteratura scientifica avicola.

### Free-range e sicurezza

Le galline restano libere per impostazione normale. Parcheggio e aree veicolari diventano però zone a accesso temporale controllato: durante carico/scarico, arrivo visitatori o manovre mezzi, porte/gate automatici devono poter trattenere temporaneamente gli animali in una zona sicura. Terminata la finestra di rischio, l'accesso viene riaperto.

Il rover può operare a bassa velocità fra gli animali soltanto dopo validazione welfare/safety. Testata di raccolta, ruote, catene, rulli e punti di schiacciamento devono essere completamente carterizzati: nessuna parte mobile scoperta accessibile alle galline.

### Stato

BOM-023 SVILUPPATA / ROVER ALL-AREA + RACCOLTA RICOVERO / TESTATA PRATO R&D / PILOT E LAYOUT BLOCCANTI.

Documento: CHICKEN_FREE_RANGE_CLEANING_ARCHITECTURE.md.

## 4. Fattoria didattica

**BOM-027 SVILUPPATA / RICONOSCIMENTO ERSA, MASTERPLAN VISITATORI, CAPIENZA E RFQ BLOCCANTI.**

La fattoria didattica viene progettata come sottosistema visitatori separato dalla produzione, non come libero accesso all'azienda.

Baseline:

- zoning Z0 pubblico/accoglienza, Z1 percorso protetto, Z2 attività controllate, Z3 no-visitor;
- planimetria ERSA come layer del masterplan: parcheggio, spazi didattici, aree a rischio, servizi, primo soccorso/acqua potabile, percorsi interni/esterni e percorsi accessibili;
- referente formato e presente;
- RC visite;
- primo soccorso vicino a fonte d'acqua potabile;
- servizio igienico adeguato/accessibile;
- spazio coperto, con BOM-026 pergolato come primo candidato da verificare;
- visitor route separata da mezzi, AMR, locali tecnici, chimici, packing/celle e dock;
- observation point per serra, acqua, energia, automazione e galline;
- modulo galline compatibile con BOM-023 e lavaggio mani obbligatorio a valle del contatto/area animale;
- accessibilità dal drop-off a primo soccorso, WC, spazio coperto e parte significativa del percorso;
- pannelli safety distinti dai pannelli didattici;
- didattica digitale read-only su guest network separata dall'OT;
- food tasting/somministrazione NON baseline;
- registro visite e procedure meteo/emergenza;
- visita pilota prima dell'apertura.

Benchmark pubblici già tracciati:

- percorso drenante pedonale FVG 2026: €37,05–39,76/m² nella voce consultata;
- fondazione granulare: €44,80/m³ reference;
- safety signage PVC: ~€34,63–43,46/cad;
- lavamani autonomo backup: €242,10;
- first-aid Allegato 1: €75,90 + IVA valigetta / €117,90 + IVA armadietto maggiorato;
- reintegro: €65,25 + IVA;
- pannello Dibond 70×100 stampato: €90/cad benchmark;
- tavolo picnic accessibile: €439,79 benchmark;
- lavagna 120×90: €85,73 benchmark.

Formazione 2026 osservata:
- corso base fattoria didattica/sociale 12 h, gratuito per categorie ammesse, indicato come parte 1 di 2;
- catalogo include specialistico fattoria didattica da 24 h;
- sequenza e requisito corrente da confermare con ERSA prima di pianificare l'apertura.

Documenti:

- `FATTORIA_DIDATTICA_ARCHITECTURE.md`;
- `RFQ_FATTORIA_DIDATTICA.md`;
- `19_BOM_PRODOTTI_FORNITORI/BENESSERE_FATTORIA_DIDATTICA.md`;
- `22_FONTI_NORME_PREVENTIVI/BENESSERE_FATTORIA_DIDATTICA_SOURCES.md`.

## 5. Spaccio automatizzato self-service 24/7

### Obiettivo

Vendita diretta con minima necessità di presidio continuo, mantenendo sicurezza, tracciabilità, catena del freddo e semplicità per il cliente.

### Architettura da valutare

- locale o kiosk separato dal flusso produttivo;
- accesso controllato o area vending;
- frigoriferi/vending refrigerati;
- scaffali intelligenti o locker;
- POS/contactless;
- videosorveglianza;
- gestione inventario;
- etichette e tracciabilità;
- controllo temperature con allarmi;
- backup elettrico per i carichi critici;
- illuminazione e accessibilità notturna;
- gestione resi/scarti;
- protezione vandalismo/furto;
- procedure di pulizia;
- normativa fiscale, sanitaria e commerciale da verificare prima dell'apertura.

### Integrazione col progetto

Lo spaccio deve poter vendere prodotti freschi aziendali e, se compatibile con la normativa e la strategia commerciale, prodotti trasformati o complementari. La predisposizione di parcheggio, passaggi, fibra/rete, alimentazione e videosorveglianza va considerata nel masterplan anche se l'apertura è futura.

## 6. Pergolato, vite, verde e aree di sosta

**BOM-026 SVILUPPATA / STRUTTURA E COSTI UNITARI IMPOSTATI / DIMENSIONI, NEVE-VENTO, GEOTECNICA E RFQ BLOCCANTI.**

Architettura:

- pergolato aperto con legno lamellare come candidato working e acciaio zincato come alternativa;
- sezioni, numero di elementi e fondazioni solo da calcolo strutturale sul lotto reale;
- azioni neve/vento da NTC e dati del sito, senza usare carichi generici di catalogo;
- plinti in c.a. come riferimento convenzionale; ground screw solo dopo geotecnica e verifica capacità;
- griglia vite indipendente e ispezionabile;
- ombra primaria da vegetazione + telo removibile opzionale;
- telo rimosso/parcheggiato in inverno se non esplicitamente verificato per la neve/vento del sito;
- vite da tavola resistente come classe di benchmark, varietà da microclima e uso del frutto;
- zona irrigua dedicata con filtro, intercettazione, lavaggio e invernaggio;
- pavimentazione permeabile e drenaggio lontano da piedi struttura e colletto piante;
- arredi modulari outdoor;
- illuminazione, prese e rete dati progettate per esterno;
- AP outdoor PoE candidato con protezione sovratensione;
- manutenzione stagionale strutturale, agronomica, drenaggi, irrigazione ed elettrico.

Benchmark pubblici già inseriti nella distinta:

- GL24h retail class: €39,90–118,50/cad secondo sezione/lunghezza osservata, solo per controllo costo;
- calcestruzzo FVG 2026 per fondazioni dirette: €237,52/m³ nella voce consultata, non costo plinto completo;
- barbatelle resistenti da tavola: €5,95/cad benchmark vivaio;
- kit goccia 100 m²: €54,90 benchmark componenti;
- griglia permeabile: €17,71/m² hardware benchmark;
- tavolo outdoor ~8 posti: €310 benchmark;
- LED outdoor IP65 10 W: €62,66 IVA incl. benchmark;
- FG16OR16 3×2,5: €3,10/m benchmark retail;
- cavidotto 40 mm FVG 2026: €1,83/m reference;
- Ubiquiti U7 Outdoor: €185 + surge protector €12.

Nessun totale CAPEX viene inventato prima di layout e calcolo. La BOM usa quantità `DA LAYOUT` / `DA CALCOLO` e costo unitario per ogni riga.

Documenti:

- `PERGOLATO_VITE_AREA_RELAX_ARCHITECTURE.md`;
- `RFQ_PERGOLATO_VITE_AREA_RELAX.md`;
- `19_BOM_PRODOTTI_FORNITORI/BENESSERE_PERGOLATO_VITE_AREA_RELAX.md`;
- `22_FONTI_NORME_PREVENTIVI/BENESSERE_PERGOLATO_VITE_AREA_RELAX_SOURCES.md`.

## 7. Regola economica

Ogni modulo avrà tre numeri distinti:

1. CAPEX reale;
2. OPEX annuo e ore di lavoro residue;
3. valore generato: risparmio ore, ricavo, benessere operativo o combinazione.

Il beneficio di automazione non viene misurato solo in euro: si contabilizzano anche le ore di lavoro sporco/pesante eliminate e il rischio operativo ridotto.
