# Carnia TerraTech — Benessere, fattoria e servizi futuri

**Aggiornato:** 17 settembre 2026.  
**Stato:** requisiti di progetto inseriti; BOM specifiche ancora da sviluppare.

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

Il progetto dovrà definire pezzo per pezzo:

- struttura pergolato;
- fondazioni;
- copertura/ombreggiamento;
- vite e altre rampicanti;
- irrigazione;
- arredi;
- illuminazione;
- prese e rete;
- manutenzione/potatura;
- drenaggio;
- sicurezza vento/neve;
- integrazione paesaggistica.

La vite può avere funzione estetica, ombreggiante e produttiva; varietà e conduzione verranno scelte solo dopo aver definito microclima, esposizione, manutenzione e uso del frutto.

## 7. Regola economica

Ogni modulo avrà tre numeri distinti:

1. CAPEX reale;
2. OPEX annuo e ore di lavoro residue;
3. valore generato: risparmio ore, ricavo, benessere operativo o combinazione.

Il beneficio di automazione non viene misurato solo in euro: si contabilizzano anche le ore di lavoro sporco/pesante eliminate e il rischio operativo ridotto.
