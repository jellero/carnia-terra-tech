# BOM-003 — Aperture, attuatori e reti anti-insetto serra

**Aggiornato:** 17 settembre 2026  
**Ambito:** 6 comparti indipendenti, ~4.200 m² complessivi.  
**Stato:** `CANDIDATI REALI / GEOMETRIA E QUANTITÀ DA DIMENSIONARE`.

## 1. Funzione

Il sottosistema deve garantire ventilazione naturale controllabile senza compromettere eccessivamente la protezione fitosanitaria. Aperture, attuatori e reti sono quindi un unico problema di progetto: una rete più fine aumenta la protezione ma riduce il flusso e può richiedere più superficie apribile, aperture zenitali o strategie climatiche diverse.

## 2. Architettura preliminare

Ogni comparto deve rimanere indipendente almeno per comando, feedback e gestione guasti.

Da confrontare sul layout esecutivo:

- aperture laterali roll-up su uno o due lati;
- aperture laterali con cinematismo rigido;
- eventuali aperture zenitali a cremagliera/push-pull;
- rete anti-insetto integrata senza bypass ai bordi;
- motorizzazione segmentata per limitare il failure domain.

**Working quantity laterali:** `6–12 gruppi motorizzati`, corrispondenti indicativamente a uno o due lati indipendenti per comparto. Non è una quantità d'ordine: la lunghezza delle campate, la coppia necessaria e la possibilità di accorpare tratti devono essere calcolate.

Quantità motori zenitali: `DA GEOMETRIA / DA CALCOLO FORZA`.

## 3. Candidati attuazione laterale

### A — Ridder RW45-L

**Classificazione:** `CANDIDATO PROFESSIONALE / PREZZO TROVATO`.

Rivenditore Sleegers Farm Equipment, articolo Ridder 531113:

- prezzo osservato: **€675,49 + IVA**;
- IP55;
- riduttore a vite senza fine autobloccante;
- finecorsa lineare RSU integrato;
- range finecorsa dichiarato fino a 97 giri dell'albero;
- feedback posizione RPU opzionale;
- applicazioni dichiarate: ventilazione e schermatura di serre in film/vetro.

Fonte: https://webshop.sleso.nl/products/rw45l-motorreductoren

Il modello esatto, coppia, rpm, alimentazione e cinematismo vanno selezionati dal calcolo della singola apertura.

**Benchmark quantità:**

- 6 unità: €4.052,94 + IVA;
- 12 unità: €8.105,88 + IVA.

Sono esclusi staffe, alberi, giunti, cremagliere/catene, quadri, cavi e posa.

### Ricambio motore RW45-1L

Sleegers elenca il motore di ricambio originale Ridder 65/9/09/230/1/4P, articolo 761001, a **€192,28 + IVA** nella pagina prodotto verificata.

Fonte: https://webshop.sleso.nl/products/ridder-losse-motor-65-9-09-230-1-4p-tbv-rw45-1l

**Classificazione:** `PREZZO TROVATO / RICAMBIO CANDIDATO`, solo se la variante finale è compatibile.

### B — motoriduttori professionali alternativi

Il catalogo corrente di Sistemas Hortícolas Almería espone come benchmark:

- motore 100 Nm 0,09 kW con catene/pignoni: **€410 + IVA**;
- motore 240 Nm 0,25 kW: **€450 + IVA**;
- motore 400 Nm 0,37 kW: **€480 + IVA**;
- motore 800 Nm 0,75 kW: **€830 + IVA**.

Fonte: https://www.sistemashorticolasalmeria.com/ventilaciones-y-motorreductores/

**Classificazione:** `PREZZI TROVATI / MODELLI DA VALIDARE`.

### C — roll-up 24 V per tratte compatibili

Woosung Hitec WSM-4035 / Northern Polytunnels:

- 24 VDC;
- 40 Nm nominali, fino a 60 Nm massimi dichiarati;
- 62 W nominali;
- ~3,5 rpm;
- 1–35 giri;
- prezzo: **£159 + VAT / £190,80 incl. VAT**.

Fonte: https://northernpolytunnels.co.uk/product/motorised-vent-winder-24vdc-40nm/

Sistemas Hortícolas Almería mostra inoltre un piccolo roll-up 24 V a **€200 + IVA** e un roll-up maggiore a **€480 + IVA**.

Questi sistemi vanno valutati solo sulle tratte per cui coppia, duty-cycle, IP, lunghezza e supporto ricambi risultano adeguati; non diventano baseline solo perché più economici.

## 4. Aperture zenitali

Le aperture zenitali restano `DA VALUTARE`, ma il progetto della struttura deve permettere una decisione informata prima dell'ordine della serra.

Una soluzione professionale tipica comprende:

- motoriduttore autobloccante;
- albero di trasmissione;
- cremagliere/pignoni o push-pull;
- giunti;
- supporti/cuscinetti;
- staffe;
- finecorsa;
- feedback posizione;
- protezione sovraccarico;
- comando locale/PLC.

Ridder dispone di famiglie drive/rack dedicate a ventilazione di serre; modello e quantità devono derivare da geometria, peso, vento, corsa e forza richiesta, non da un numero generico di motori.

Fonte produttore: https://ridder.com/drive-systems

## 5. Reti anti-insetto — candidati Arrigoni Air Plus

La rete viene scelta per **parassita obiettivo + perdita di ventilazione**, non per il solo numero “mesh”.

### N1 — BIORETE 50 AIR PLUS, 3353BT

- foro: 0,33 × 0,68 mm;
- peso: ~78 g/m²;
- ombreggiamento: ~11%;
- indice passaggio aria: ~47%;
- riduzione ventilazione dichiarata: ~30%;
- target indicato: mosche bianche / Bemisia spp.

**Uso candidato:** aree dove il rischio target consente una rete più aperta e il carico di ventilazione estiva è prioritario.

### N2 — BIORETE 60 AIR PLUS, 3363BT

- foro: ~0,33 × 0,45 mm;
- peso: ~90 g/m²;
- ombreggiamento: ~12–13%;
- passaggio aria: ~40%;
- riduzione ventilazione: ~31%;
- target indicato: Bemisia tabaci / afidi.

**Uso candidato:** compromesso da verificare comparto per comparto.

### N3 — BIORETE 80 AIR PLUS, 3382BT

- foro: 0,15 × 0,31 mm;
- peso: ~130 g/m²;
- ombreggiamento: ~17%;
- passaggio aria: ~26%;
- riduzione ventilazione: ~42%;
- target indicato: Frankliniella occidentalis / Thrips tabaci.

**Uso candidato:** comparti in cui l'esclusione dei tripidi è requisito forte, compensando il maggiore impatto sulla ventilazione.

### 90 Air Plus

- foro: ~0,15 × 0,17 mm;
- passaggio aria: ~22%;
- riduzione ventilazione: ~45%;
- target: tripidi.

Non viene assunta come scelta standard: la penalizzazione di ventilazione è troppo rilevante per essere accettata senza una necessità fitosanitaria esplicita.

Fonte tecnica principale: https://arrigoni.it/agrotextile/applicazioni/protezione-dagli-insetti/

## 6. Benchmark prezzo rete

### Arrigoni BIORETE 50 Mesh standard

Sala Laurus mostra BIORETE 50 Mesh a **€1,49** con selezione quantità in “metri”. Specifiche dichiarate: foro 0,27 × 0,79 mm, 128 g/m², 13% ombreggiamento, 36% passaggio aria.

Fonte: https://salalaurus.it/products/biorete-50-mesh

**Classificazione:** `PREZZO TROVATO MA UNITÀ ECONOMICA DA CONFERMARE PRIMA DI USARLO IN CAPEX`.

Non si usa €1,49/m² finché il venditore non conferma esattamente larghezza/metro lineare/variante.

I prezzi delle versioni Air Plus professionali restano `PREZZO DA PREVENTIVO` per il progetto.

## 7. Strategia per comparto da validare

Non installare automaticamente la stessa rete sui sei comparti.

Working logic:

- **C1 pomodoro:** confrontare 50/60 Air Plus con 80 Air Plus sulla base di Tuta, Bemisia, tripidi, IPM e capacità di ventilazione;
- **C2 peperone:** forte attenzione ai tripidi; 80 Air Plus è candidato ma richiede compensazione aerodinamica;
- **C3–C5 leafy:** mesh da definire su vettori/parassiti reali e rischio di surriscaldamento;
- **C6 vivaio/basilico:** può giustificare protezione più severa per biosicurezza del materiale giovane, ma solo dopo analisi specifica.

La decisione finale appartiene al piano IPM del punto 02 e al calcolo climatico del punto 03/05.

## 8. Effetto rete sul dimensionamento delle aperture

Per ogni scenario il fornitore deve dichiarare o consentire di calcolare:

- area geometrica dell'apertura;
- area netta di rete;
- percentuale di area aperta;
- coefficiente/perdita di pressione o dato equivalente;
- portata/ricambi d'aria attesi con vento e differenza termica;
- effetto di sporcamento della rete;
- modalità di pulizia.

Una rete con riduzione ventilazione dichiarata del 42% non può essere trattata come se fosse un'apertura libera. Se necessaria per IPM, si valuta aumento area apribile, zenitali, HAF e strategie di gestione del calore.

## 9. BOM meccanica/elettrica per ogni gruppo laterale

| Codice | Voce | Quantità | Stato |
|---|---|---:|---|
| VNT-MOT | motoriduttore | 6–12 working | DA CALCOLO |
| VNT-TUBE | tubo/albero avvolgimento | m da layout | DA PREVENTIVO |
| VNT-GUIDE | guide/profili | m da layout | DA PREVENTIVO |
| VNT-JNT | giunti | da distinta | DA PREVENTIVO |
| VNT-BRG | supporti/cuscinetti | da distinta | DA PREVENTIVO |
| VNT-TRN | catena/pignoni/rack/push-pull | da architettura | DA PREVENTIVO |
| VNT-LIM | finecorsa sicurezza | 1 set/gruppo | INTEGRATO O SEPARATO |
| VNT-POS | feedback posizione | 1/gruppo | DA VALUTARE |
| VNT-BRK | staffe/piastre | da distinta | DA PREVENTIVO |
| VNT-HDW | bulloneria | da distinta | DA PREVENTIVO |
| VNT-ISO | sezionatore locale | 1/motore | DA PREVENTIVO |
| VNT-PROT | protezione motore | 1/motore | DA PREVENTIVO |
| VNT-CAB | cavi potenza/segnale | m da layout | DA PREVENTIVO |
| VNT-LOC | comando locale | 1/gruppo | DA PREVENTIVO |
| VNT-PLC | I/O PLC | per gruppo | verificare I/O già previsti |
| NET-TEX | rete anti-insetto | m² da layout | DA PREVENTIVO |
| NET-PRO | profili fissaggio rete | m da layout | DA PREVENTIVO |
| NET-SEAL | guarnizioni/sigillatura bordi | da layout | DA PREVENTIVO |
| NET-SP | rete/clip/profili di scorta | lotto | DA DEFINIRE |
| VNT-LAB | posa/regolazione | ore o lotto | DA PREVENTIVO |
| VNT-COM | commissioning | 1 lotto | DA PREVENTIVO |

## 10. Sensori e logica di sicurezza

Input minimi al controllo:

- temperatura/UR per comparto;
- stazione meteo locale;
- vento velocità + raffica;
- direzione vento quando utile;
- pioggia;
- stato/finecorsa;
- feedback posizione ove previsto;
- overload/fault motore.

Principio:

`desired position → command → acknowledgement → observed position/state`.

La posizione di sicurezza in vento forte/pioggia deve essere definita con il costruttore della serra e il calcolo strutturale; non viene inventata genericamente.

## 11. Failure modes

Da testare nel commissioning:

- motore bloccato;
- finecorsa guasto;
- rete strappata;
- albero disaccoppiato;
- apertura asimmetrica;
- mancanza alimentazione;
- perdita comunicazione PLC;
- sensore vento guasto;
- improvviso vento forte durante apertura;
- impossibilità di chiudere una zona.

Ogni comparto deve poter essere isolato senza rendere ciechi gli altri cinque.

## 12. Manutenzione e ricambi

Prevedere:

- pulizia periodica reti;
- ispezione bordi e sigillature;
- controllo tensione film/rete;
- lubrificazione solo dove prevista dal produttore;
- test finecorsa e feedback;
- controllo bulloneria/staffe;
- prova manovra manuale;
- storico cicli/ore motore;
- motore o componenti di ricambio standardizzati quando economicamente sensato;
- metri di rete e profili/clip di riparazione a stock.

## 13. Stato economico

Sono disponibili benchmark reali per gli attuatori, ma non esiste ancora un totale affidabile perché mancano:

- lunghezze reali aperture;
- uno/due lati per comparto;
- eventuali zenitali;
- coppia/forza richiesta;
- superficie rete;
- mesh per comparto;
- meccanica completa;
- cablaggio e posa.

La BOM-003 è quindi pronta per essere trasformata in RFQ appena esiste il layout geometrico della serra.
