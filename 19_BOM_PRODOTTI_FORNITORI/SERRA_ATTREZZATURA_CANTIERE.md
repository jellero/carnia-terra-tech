# BOM-008 — Attrezzatura e consumabili di montaggio serra

**Aggiornato:** 17 settembre 2026  
**Ambito:** montaggio serra ~4.200 m², copertura, schermi, aperture, HAF, fogging, supporti coltura, porte e sottosistemi accessori.  
**Stato:** `DISTINTA CANTIERE DEFINITA / PREZZI BENCHMARK REALI / QUANTITÀ E GIORNI NOLEGGIO DA CRONOPROGRAMMA`.

## 1. Obiettivo

Separare il costo reale del cantiere dagli elementi permanenti della serra. Non usare una voce unica `attrezzatura cantiere`.

Ogni elemento viene classificato come:

- `ACQUISTO` se utile anche dopo il montaggio per manutenzione ordinaria/straordinaria;
- `NOLEGGIO` se costoso, ingombrante, soggetto ad abilitazioni/verifiche o usato solo per finestre limitate;
- `CONSUMABILE` se si esaurisce durante il lavoro;
- `DPI/SICUREZZA` se obbligatorio per la lavorazione prevista;
- `SERVIZIO` se richiede operatore esterno o lavorazione specialistica.

## 2. Strategia buy vs rent

### Acquisto preferenziale

- piattaforma utensili a batteria comune;
- avvitatori/impattatori;
- trapani/rotomartelli;
- smerigliatrici;
- chiavi dinamometriche;
- utensili manuali;
- strumenti misura elettrica/meccanica;
- prolunghe, quadri mobili e illuminazione cantiere;
- aspirazione/pulizia;
- DPI individuali;
- kit piccoli sollevamenti e movimentazione compatibili con carichi reali.

### Noleggio preferenziale

- PLE/scissor lift;
- piattaforme articolate se necessarie;
- telescopico/gru/autogru;
- piattaforme autocarrate;
- gruppi elettrogeni di grande taglia se la rete di cantiere è già disponibile;
- attrezzature specialistiche di uso breve.

La decisione usa:

`costo noleggio + trasporto + assicurazione + giorni inattivi` versus `prezzo acquisto + manutenzione + stoccaggio + valore residuo + utilità futura`.

## 3. Lavori in quota — PLE e trabattelli

### PLE verticale elettrica 10–12 m

Benchmark noleggio pubblico:

- piattaforma verticale elettrica 10 m: **€55–65/giorno**;
- piattaforma verticale elettrica 12 m: **€80/giorno**;
- trasporto separato; un'offerta pubblica mostra trasporto da **€100**.

Fonti:
- https://rentforwork.it/it/marketplace/listing/noleggio-piattaforma-verticale-elettrica-10-mt-verona-verona-17bbfb90
- https://www.erental.it/fosso/noleggio-piattaforma-semovente/piattaforma-semovente

Classificazione: `PREZZO NOLEGGIO TROVATO / BENCHMARK`.

Per lavori con sbraccio/ostacoli, benchmark articolata elettrica ~15,6 m:

- **€155/giorno** fino a 5 giorni;
- **€142/giorno** 6–10 giorni;
- **€129/giorno** 11–20 giorni;
- **€118/giorno** oltre 20 giorni;
- trasporto separato.

Fonte: https://www.noleggiolorini.com/it/piattaforme-aeree/piattaforme-aeree-semoventi/articolata-elettrica-alt-lavoro-1560-mt

Non fissare giorni di noleggio prima del cronoprogramma per fasi.

### Trabattello professionale

Benchmark acquisto:

- alluminio, altezza lavoro ~7,7–8,1 m: **€3.131–3.360 IVA inclusa**.

Fonti:
- https://www.trabattelli.it/home/98-trabattello-alluminio-roller-plus-s-modulo-abcd-altezza-l-770-mt.html
- https://www.trabattelli.it/trabattelli-professionali/163-trabattello-alluminio-roller-l-modulo-abc-altezza-l-590-mt.html

Benchmark noleggio trabattello fino a ~7,7 m: **€65/giorno**.

Fonte: https://www.erental.it/mestre/noleggio-attrezzatura-sollevamento

Decisione: confrontare acquisto se resta poi disponibile per manutenzione periodica della serra; noleggio se ingombro/stoccaggio e frequenza d'uso non giustificano proprietà.

## 4. Avvitatura e serraggio

### Impattatore medio

Bosch Professional GDX 18V-200:

- 200 Nm classe utensile;
- benchmark Bosch kit 2 batterie 4 Ah + caricatore: **€379 + IVA** prezzo consigliato;
- corpo/valigetta: **€199 + IVA** prezzo consigliato.

Fonte: https://www.bosch-professional.com/it/it/gdx-18v/

### Impattatore alta coppia

Makita DTW700ZJ:

- 700 Nm max dichiarati;
- benchmark mercato da circa **€240** corpo/macpac.

Usare l'impattatore per velocizzare; il serraggio finale dei giunti critici deve seguire coppie/procedure del costruttore, non il numero di impulsi.

### Chiavi dinamometriche

Benchmark 1/2" 40–200 Nm: **€69,90–79,90 IVA inclusa** per fascia retail/prosumer.

Fonte: https://www.leroymerlin.it/prodotti/chiave-dinamometrica-dexter-82612446-1-2-40-200-nm-82612446.html

Per bulloneria strutturale richiedere intervalli di coppia reali e usare utensili con certificato/taratura appropriata. Prevedere almeno due range se la distinta bulloni lo richiede.

## 5. Foratura e lavorazione acciaio

### Trapano magnetico

Benchmark professionale Makita HB350:

- capacità acciaio fino a ~35 mm dichiarata;
- prezzi mercato osservati ~**€736–962** secondo canale.

Fonte comparativa: https://www.idealo.it/cat/15397F1774126/trapani.html

Alternative economiche esistono da ~€340–550, ma per uso di cantiere valutare precisione, ricambi, magnete, protezione sovraccarico e disponibilità frese.

### Consumabili foratura

BOM separata:

- frese carotatrici per diametri reali;
- punte HSS/cobalto;
- punte muratura/calcestruzzo;
- maschi e filiere se ammessi;
- olio/lubrificante da taglio;
- svasatori;
- estrattori bulloni;
- scorta mandrini/adattatori.

Nessuna quantità viene stimata senza shop drawing e metodo di montaggio.

## 6. Taglio, sbavatura e finitura

Prevedere:

- smerigliatrici 125 mm a batteria/rete;
- eventuale 230 mm solo se giustificata;
- dischi taglio acciaio;
- dischi lamellari;
- spazzole inox/acciaio compatibili;
- lime/sbavatori;
- protezioni schermo facciale e occhiali;
- aspirazione/pulizia trucioli.

La zincatura non deve essere rimossa o ripristinata senza procedura definita. Ogni taglio/modifica in cantiere deve essere autorizzata dal sistema costruttivo e avere trattamento anticorrosione previsto.

## 7. Saldatura — non baseline strutturale

Le connessioni principali della serra devono preferire componenti progettati/imbullonati dal costruttore quando previsto. La saldatura in campo non è automaticamente autorizzata sulla carpenteria zincata/strutturale.

Per officina/riparazioni non strutturali, benchmark multiprocesso Telwin Technomig 210 Dual Synergic: **~€787–856** sul mercato osservato.

La saldatura strutturale richiede specifica, procedimento, qualifica e controllo appropriati; non viene trattata come normale utensile di assemblaggio.

## 8. Alimentazione elettrica temporanea

Prima scelta: quadro temporaneo alimentato da fornitura di cantiere correttamente dimensionata.

BOM minima:

- quadro da cantiere con differenziali/protezioni;
- prese CEE;
- prolunghe industriali;
- avvolgicavo;
- messa a terra/equipotenziale secondo progetto;
- illuminazione temporanea LED;
- caricabatterie utensili;
- protezione pioggia/urti;
- etichettatura.

Gruppo elettrogeno: solo se necessario per fasi senza rete o come fallback. Benchmark Pramac ES8000 classe ~8 kVA: circa **€1.800–1.920** per versioni commerciali 230 V; eventuale trifase va specificato separatamente e non dedotto dal nome commerciale.

## 9. DPI e anticaduta

BOM personale minima da definire con DVR/POS/metodo di lavoro:

- casco con sottogola dove richiesto;
- occhiali;
- guanti appropriati;
- scarpe S3 o specifica scelta;
- alta visibilità;
- protezione udito;
- respiratoria per lavorazioni che la richiedono;
- imbracatura;
- cordini/assorbitori/retrattili compatibili col sistema;
- kit soccorso/recupero dove necessario.

Benchmark kit anticaduta professionale con imbracatura + doppio cordino con assorbitore: ~**€125–158 IVA inclusa** in offerte correnti. Soluzioni complete di posizionamento/lavoro possono superare €600.

Fonti:
- https://www.manomano.it/p/delta-plus-elara280-kit-anti-caduta-ponteggi-pronto-alluso-arancio-1238972
- https://www.canevari.it/kit-anticaduta-per-lavori-di-ponteggio-coverguard-mo71640/50601/scheda

La scelta del DPI dipende dal sistema reale di accesso, fattore di caduta, tirante d'aria, ancoraggi e procedura di recupero.

## 10. Sicurezza PLE e attrezzature

INAIL conferma che le PLE rientrano tra le attrezzature che richiedono specifica abilitazione dell'operatore ai sensi dell'art. 73 del D.Lgs. 81/2008 e relativo quadro formativo. Nel noleggio il datore di lavoro deve indicare operatori formati/abilitati secondo i requisiti applicabili.

Fonti:
- https://www.inail.it/portale/formazione/it/corsi-inail/catalogo-corsi/dettaglio-corso.2024.01.corso-di-formazione-per-l-abilitazione-degli-operatori-delle-attrezzature.html
- https://www.inail.it/portale/prevenzione-e-sicurezza/it/come-fare-per/conoscere-il-rischio/attrezzature-di-lavoro/il-noleggio-e-la-concessione-in-uso.html

Per PLE nuove, il riferimento tecnico corrente richiamato da INAIL è EN 280-1:2022; la vecchia EN 280:2013+A1:2015 è stata ritirata nel 2025.

## 11. Movimentazione e sollevamento materiali

Da dimensionare con pesi reali dei colli del fornitore:

- transpallet manuale/elettrico;
- carrelli di cantiere;
- cavalletti;
- paranchi;
- tirfor/argani;
- fasce/catene/grilli marcati e dimensionati;
- eventuale telescopico/gru/autogru a noleggio;
- supporti temporanei per archi/travi;
- area scarico/stoccaggio protetta.

Non sollevare persone con attrezzature non previste/certificate per persone.

## 12. Misura, controllo e commissioning

Acquisto consigliato perché riutilizzabile in manutenzione:

- multimetro TRMS;
- pinza amperometrica;
- misuratore isolamento se necessario;
- cercafase/strumenti sicurezza elettrica;
- laser distanza/livello;
- livello digitale;
- termometro IR;
- manometri/strumenti di riferimento per commissioning;
- anemometro portatile;
- lux/PAR solo dove utile al collaudo agronomico;
- etichettatrice industriale;
- tablet/telefono rugged o soluzione equivalente per check-list e foto as-built.

Gli strumenti che influenzano accettazione/coppie/misure critiche devono avere accuratezza e verifica adeguate.

## 13. Consumabili e minuteria cantiere

Distinta separata, non forfait:

- bulloneria aggiuntiva solo se approvata;
- dadi/rondelle/nyloc specificati;
- fascette UV;
- pressacavi;
- capicorda/ferrule;
- morsetti;
- guaine termorestringenti;
- nastro elettrico;
- nastro butilico/tenuta se approvato;
- sigillanti compatibili;
- detergenti;
- marcatori;
- etichette;
- spray zincante/ripristino solo secondo specifica;
- lubrificanti;
- lame/dischi/punte;
- sacchi/aspirazione;
- teli protezione;
- materiale pulizia finale.

Ogni consumabile chimico deve essere compatibile con film, plastiche, guarnizioni e zincatura circostante.

## 14. Struttura costi

Il costo cantiere deve essere modellato come:

`acquisti utensili + noleggi × giorni + trasporti + assicurazioni + consumabili + DPI + formazione/abilitazioni + manutenzione attrezzature + energia/carburante + ore operatore + eventuali servizi specialistici`.

Non includere il lavoro dei soci a costo zero: registrare ore e valorizzazione economica separata anche quando il cash-out non avviene immediatamente.

## 15. BOM minima

| Codice | Voce | Strategia | Stato |
|---|---|---|---|
| SITE-PLE-01 | PLE verticale 10–12 m | noleggio | prezzo benchmark trovato |
| SITE-PLE-02 | PLE articolata | noleggio condizionale | prezzo benchmark trovato |
| SITE-TWR-01 | trabattello professionale | buy-vs-rent | benchmark trovato |
| SITE-IMP-01 | impattatore medio | acquisto | candidato reale |
| SITE-IMP-02 | impattatore alta coppia | acquisto se distinta lo richiede | candidato reale |
| SITE-TQ-01 | dinamometrica/e | acquisto | benchmark trovato |
| SITE-MAG-01 | trapano magnetico | buy-vs-rent | candidati reali |
| SITE-GRN-01 | smerigliatrici | acquisto | da piattaforma batteria scelta |
| SITE-WELD-01 | saldatrice | condizionale | non baseline strutturale |
| SITE-ELEC-01 | quadro/prolunghe/luci cantiere | acquisto | da distinta elettrica |
| SITE-GEN-01 | generatore | condizionale | benchmark trovato |
| SITE-LIFT-01 | telescopico/gru/autogru | noleggio | da pesi/cantiere |
| SITE-RIG-01 | fasce/grilli/paranchi | acquisto/noleggio | da carichi |
| SITE-DPI-01 | DPI generali | acquisto personale | obbligatorio |
| SITE-DPI-02 | anticaduta | acquisto personale | da metodo lavoro |
| SITE-MET-01 | strumenti misura | acquisto | da commissioning |
| SITE-CONS-01 | punte/dischi/lame | consumabile | da distinta |
| SITE-CONS-02 | sigillanti/nastri/chimici | consumabile | compatibilità obbligatoria |
| SITE-CONS-03 | elettrico/minuteria | consumabile | da distinta |
| SITE-TRN-01 | formazione/abilitazioni | servizio | da ruoli/attrezzature |
| SITE-LAB-01 | ore montaggio | lavoro | da cronoprogramma reale |

## 16. Gate

BOM-008 diventa `VALIDATO` quando:

- esiste metodo di montaggio del fornitore;
- sono noti altezza, pesi e colli principali;
- cronoprogramma definisce giorni PLE/mezzi;
- layout cantiere definisce accessi e portanza;
- responsabile sicurezza definisce DPI/attrezzature e procedure;
- sono note coppie serraggio e lavorazioni ammesse;
- ogni noleggio ha trasporto/assicurazione/accessori esplicitati;
- quantità consumabili derivano dalla distinta reale;
- ore uomo e ore macchina sono registrate.
