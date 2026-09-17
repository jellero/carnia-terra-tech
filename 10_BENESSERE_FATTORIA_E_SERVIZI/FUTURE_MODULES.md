# Carnia TerraTech — Benessere, fattoria e servizi futuri

**Aggiornato:** 18 settembre 2026.  
**Stato:** BOM-023 pulizia galline e BOM-026 pergolato/vite/relax sviluppate; fattoria didattica e spaccio 24/7 da sviluppare.

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

### Obiettivo

Creare in una fase successiva un'area in cui tecnologia, agricoltura, acqua, energia, compostaggio, biodiversità e animali possano essere mostrati in modo sicuro e comprensibile.

### Elementi da prevedere già nel masterplan

- percorso visitatori separabile dalla logistica produttiva;
- punti di osservazione sicuri verso serra e impianti;
- area coperta/pergolato per gruppi;
- servizi igienici adeguati alla fase di apertura al pubblico;
- lavaggio mani;
- recinzioni e separazione aree tecniche;
- accessibilità;
- parcheggio/punto raccolta;
- cartellonistica e didattica digitale;
- gestione emergenze e primo soccorso;
- assicurazioni e requisiti regionali da verificare prima dell'avvio;
- calendario visite compatibile con i picchi di lavoro agricolo.

**Fase:** dopo stabilizzazione del core produttivo, salvo opportunità di contributo che giustifichi una predisposizione anticipata.

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
