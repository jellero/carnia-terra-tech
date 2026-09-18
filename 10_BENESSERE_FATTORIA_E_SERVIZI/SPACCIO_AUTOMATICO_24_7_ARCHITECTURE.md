# Architettura spaccio automatico self-service 24/7 — BOM-028

**Aggiornato:** 18 settembre 2026  
**Stato:** `WORKING ARCHITECTURE / PERCORSO SUAP, SKU, TEMPERATURE, FISCALITÀ E RFQ BLOCCANTI / CANDIDATI HARDWARE DISPONIBILI`.

## 1. Obiettivo

Realizzare un punto vendita automatico self-service 24/7 che consenta di vendere prodotti aziendali con minimo presidio continuativo, mantenendo:

- sicurezza alimentare;
- catena del freddo dove necessaria;
- tracciabilità;
- continuità elettrica ragionevole;
- pagamenti elettronici;
- fiscalizzazione/corrispettivi coerenti con la configurazione reale;
- inventario;
- videosorveglianza conforme;
- accessibilità;
- facilità di rifornimento e pulizia;
- separazione netta dal core produttivo;
- ripiego manuale quando il sistema automatico non è disponibile.

Lo spaccio non deve diventare un secondo negozio tradizionale da presidiare.

## 2. Due regimi da tenere separati

### R1 — vendita diretta agricola

Configurazione base preferita per Carnia TerraTech se ricorrono i requisiti:

- imprenditore agricolo iscritto nella sezione speciale del Registro Imprese;
- prodotti provenienti in misura prevalente dall'azienda;
- eventuali prodotti agricoli/alimentari di altri imprenditori agricoli acquistati direttamente, mantenendo la prevalenza del fatturato dei prodotti propri;
- osservanza delle norme igienico-sanitarie;
- comunicazione/notifica secondo il canale SUAP applicabile.

Il D.Lgs. 228/2001 consente la vendita diretta al dettaglio dei prodotti agricoli e la pagina SUAP FVG include esplicitamente la vendita tramite distributori automatici tra le modalità possibili per il produttore agricolo.

### R2 — vendita automatica al dettaglio generica

Da applicare/verificare se:

- il mix prodotti esce dal perimetro della vendita diretta agricola;
- lo spazio viene configurato come locale esclusivamente destinato a vendita automatica commerciale;
- vengono introdotti prodotti/servizi che richiedono diverso titolo.

La pagina SUAP FVG per vendita mediante apparecchi automatici prevede SCIA e, per alimenti, requisiti e comunicazioni sanitarie specifiche.

**Verifica bloccante:** prima dell'ordine macchine, definire con SUAP/commercialista il regime effettivo del punto vendita.

## 3. Non confondere vendita con somministrazione

Configurazione base BOM-028:

- prodotto confezionato o comunque venduto;
- nessun servizio assistito;
- nessuna preparazione di cibi nel punto vendita;
- nessuna cucina;
- nessuna area attrezzata specificamente per somministrazione.

Il consumo immediato di prodotti agricoli venduti può avere una disciplina propria, ma non viene assunto automaticamente come configurazione base.

Se il layout introduce tavoli/attrezzature finalizzati al consumo sul posto, verificare se si ricade nella disciplina della somministrazione.

### Evoluzione agrituristica opzionale

È stato separato un **piano extra autonomo** di ristoro agrituristico evolutivo, documentato in `../EXTRA_AGRITURISMO_EVOLUTIVO/README.md`.

Questo percorso:
- non modifica la configurazione base non presidiato BOM-028;
- opera solo in finestre presidiate;
- mantiene vendita automatica e somministrazione come funzioni distinte;
- privilegia la variante senza cottura per ridurre CAPEX, impianti e carico di lavoro;
- richiede verifica bloccante SUAP/sanitario e menu verificato prima di qualsiasi acquisto.

## 4. Modello fisico

Architettura di lavoro:

`accesso cliente -> area vendita automatica -> selezione/pagamento -> ritiro -> uscita`

Con retro-servizio separato:

`Tech Barn / stock -> controllo lotto -> rifornimento -> inventario -> vendita`

### Configurazione base preferita

- piccolo locale/chiosco protetto;
- distributore refrigerato principale;
- eventuale modulo temperatura ambiente/cool separato;
- nessun accesso cliente allo stock posteriore;
- quadro elettrico e rete non accessibili;
- macchina ancorata/protetta;
- telecamera su ingresso e area distribuzione automatica;
- illuminazione;
- cestino;
- eventuale display/wayfinding;
- accesso rifornimento separato o in finestra chiusa al pubblico.

### Outdoor puro

Non è configurazione base salvo macchina esplicitamente progettata/certificata dal costruttore per installazione esterno nella configurazione proposta.

Le macchine interno non vengono esposte direttamente a:

- pioggia;
- neve;
- irraggiamento;
- gelo;
- condensa;
- vandalismo non previsto;
- polvere/acqua di lavaggio.

La FAS Skudo presentata nel 2026 come soluzione riprogettata per esterno è un benchmark di categoria da RFQ, non un acquisto già deciso.

## 5. Matrice SKU/temperatura

Non esiste una sola temperatura valida per tutti i prodotti.

### Classe T-A — ortaggi a foglia refrigerati

Esempi:
- lattuga;
- baby leaf;
- rucola;
- spinacio.

Interfaccia con BOM-024 CR-A.

Richiede:
- temperatura coerente con shelf-life validata;
- macchina certificata/configurata per food refrigerato;
- logger indipendente;
- blocco vendita in caso di escursione fuori soglia quando necessario.

### Classe T-B — ortofrutta sensibile al freddo

Esempi:
- pomodoro;
- peperone;
- basilico.

Interfaccia con BOM-024 CR-B.

Questi SKU non vengono messi automaticamente in una macchina a 0–4 °C.

Servono:
- setpoint idoneo;
- durata permanenza;
- confezionamento;
- verifica chilling injury/shelf-life.

Necta Gusto 8 dichiara layout stratificati con zone 0–3 °C, 5–7 °C e 8–12 °C. Questo rende la piattaforma interessante da testare, ma **non prova da solo** che ogni SKU aziendale sia idoneo a ciascuna zona.

### Classe T-C — temperatura ambiente

Prodotti che non richiedono refrigerazione nella finestra di vendita prevista.

Da validare SKU per SKU.

## 6. Strategia macchina

### Candidato 1 — Necta Gusto 8

Punti interessanti:
- fino a 44 selezioni;
- fino a 360 prodotti dichiarati;
- vari layout;
- versione Food;
- R290;
- protocollo MDB/Executive;
- possibilità di layout multi-temperatura;
- ~900 mm larghezza.

Limiti:
- erogazione a spirale;
- rischio urto/caduta su ortofrutta delicata;
- prezzo Italia da RFQ;
- esterno non assunto.

### Candidato 2 — Necta Gusto 8 Lift

Punti interessanti:
- ascensore SoftVend;
- dichiarato dal produttore per erogazione sicura di prodotti fragili;
- fino a 40 selezioni;
- fino a 240 prodotti;
- R290;
- 0–4 °C in configurazione Food.

Per pomodori premium, vaschette delicate o pack fragili è candidato da testare prima del Gusto 8 standard.

### Candidato 3 — Necta Gusto Drum

Punti interessanti:
- servizio 24/7;
- compartimenti a tamburo;
- FIFO;
- gestione scadenza;
- fino a 360 prodotti;
- 0–4 °C;
- R290.

Limiti:
- non adatto a tutti gli SKU;
- maggiore costo;
- 0–4 °C non compatibile automaticamente con CR-B.

### Candidato 4 — FAS Easy Food

Sistema a locker/dischi refrigerati:
- fresco;
- cloud;
- QR;
- CO2 refrigerante;
- temperatura minima +3 °C con sicurezza frigo;
- 450 W nominali.

Interessante per:
- box/vaschette;
- ritiro prenotazioni;
- prodotti fragili;
- ordini prepagati.

Da valutare se lo spaccio integra e-commerce/click&collect.

### Regola

Nessuna macchina viene scelta solo da:
- capacità nominale;
- prezzo;
- estetica.

Serve pilot con confezionamento reale.

## 7. Packaging e interfaccia BOM-025

Lo spaccio eredita da BOM-025:

- etichetta/lotto;
- codice a barre/QR;
- confezionamento retail;
- tracciabilità.

Vincoli distribuzione automatica:
- dimensione pack compatibile;
- peso;
- scorrevolezza;
- rigidità;
- assenza di apertura accidentale;
- resistenza a caduta/spirale/ascensore;
- leggibilità etichetta;
- condensa.

Test richiesti:
- 100 erogazioni per SKU critico;
- zero inceppamento;
- zero rottura pack;
- danno prodotto entro soglia accettata;
- lettura lotto;
- recupero prodotto in fault.

## 8. Pagamenti — Stripe nativo

Stripe è il infrastruttura di pagamento unico di progetto; infrastruttura di pagamento alternativi non fanno parte della configurazione base.

Il server centrale Carnia TerraTech è il proprietario del flusso ordine/pagamento/vendita e usa Stripe come gestore dei pagamenti.

### Terminal non presidiato

Per un temperatura ambientee realmente non presidiato/distribuzione automatica, il candidato Stripe Terminal è **Verifone UX700**.

La documentazione Stripe corrente lo identifica come dispositivo self-service/non presidiato e ne indica, tra le caratteristiche:

- EMV chip;
- contactless/wallet;
- Ethernet/Wi-Fi;
- IP65;
- IK08;
- integrazione server-driven;
- disponibilità Italia nella matrice corrente;
- modalità offline come capability del dispositivo.

La combinazione esatta offline + server-driven + configurazione italiana va verificata nel pilot e nella documentazione Stripe vigente.

### Flusso transazionale di lavoro

`selezione -> prenotazione inventario -> order -> PagamentoIntent -> Stripe Terminal -> pagamento confermato -> autorizza erogazione -> vend_ack -> chiudi ordine`

Il pagamento riuscito **non equivale** a vendita completata finché il sistema non riceve conferma dell'erogazione.

Se l'erogazione fallisce:

- ordine resta in stato recupero;
- slot/machine può essere disabilitato;
- il server esegue retry soltanto se sicuro;
- altrimenti avvia rimborso/cancel coerente con lo stato Stripe.

### Requisiti software

- PagamentoIntent;
- webhook;
- idempotency key;
- correlation id;
- state machine esplicita;
- reconciliation;
- rimborso API;
- registro di controllo;
- gestione delayed webhook;
- protezione da doppia erogazione/double-rimborso.

Le credenziali Stripe restano lato server; nessuna secret key nel controller distribuzione automatica.

## 9. Corrispettivi e fiscalità

Il D.Lgs. 127/2015 disciplina memorizzazione/trasmissione telematica dei corrispettivi, incluse cessioni tramite distributori automatici secondo la configurazione applicabile.

La BOM non congela una soluzione fiscale senza:
- modello macchina;
- sistema master;
- periferica di pagamento;
- eventuale controller telemetrico;
- regime impresa;
- configurazione del punto vendita.

RFQ deve chiedere esplicitamente:
- compatibilità con adempimenti fiscali italiani;
- modalità censimento/macchina;
- telemetria fiscale;
- aggiornamenti normativi;
- export;
- responsabilità del fornitore vs esercente;
- assistenza.

Validazione finale con commercialista e fornitore fiscale prima del go-live.

## 10. Sicurezza alimentare

Riferimenti operativi:
- Reg. (CE) 852/2004;
- procedure HACCP/autocontrollo;
- notifica/registrazione OSA dove applicabile;
- normativa nazionale specifica sui distributori automatici.

Design:
- superfici lavabili;
- vano vendita protetto da contaminazione;
- pest control;
- nessuna esposizione a sorgenti di calore;
- manutenzione programmata;
- gestione scadenze;
- FIFO;
- registrazione temperature per gli SKU refrigerati;
- segregazione prodotto non conforme.

## 11. Temperature e fail-safe

Ogni zona refrigerata deve avere:

1. sensore macchina;
2. logger indipendente;
3. soglia preallarme;
4. soglia blocco vendita;
5. timestamp;
6. allarme remoto;
7. procedura verifica prodotto;
8. riavvio controllato.

Non basta vedere "compressore ON".

### Fault mode

Se temperatura esce dalla finestra accettata:
- bloccare le selezioni coinvolte;
- non continuare a vendere "finché sembra freddo";
- generare allarme;
- classificare il lotto;
- decidere scarto/rientro secondo HACCP.

## 12. Logger indipendente

Di lavoro candidate:
- Testo 160 T o classe equivalente;
- Wi-Fi;
- memoria locale;
- allarmi;
- alimentazione a batteria;
- monitoraggio indipendente dal controller della distribuzione automatica.

Per impiego alimentare definitivo, preferire logger/sistema specificamente adatto al contesto HACCP e alla validazione richiesta.

## 13. Inventario, logistica e pianificatore centrale

Il fornitore distribuzione automatica non è il sistema autorevole dei dati.

Il **server centrale Carnia TerraTech** mantiene per ogni slot:

- SKU;
- lotto;
- quantità;
- data carico;
- TMC/scadenza;
- temperatura target;
- prezzo;
- vendite;
- scarti;
- stato macchina;
- ultima riconciliazione.

Eventi:

- load;
- sale;
- payment;
- rimborso;
- vend_command;
- vend_ack;
- inceppamento;
- temperature fault;
- manual removal;
- expiry;
- scarto;
- reconciliation.

Il server incrocia questi dati con:

- celle BOM-024;
- confezionamento BOM-025;
- raccolta prevista;
- ordini;
- personale disponibile;
- logistica/AMR;
- storico vendite;
- meteo/stagionalità;
- previsione domanda/offerta.

Output operativo:

- refill target;
- task al personale;
- missioni logistiche;
- quantità da trasferire da cella a spaccio;
- reorder/stock target;
- candidato a sconto/promozione;
- rischio esaurimento scorte;
- rischio scarto.

L'inventario teorico viene sempre riconciliato con registro di controllo fisico e feedback macchina.

## 14. Prezzi e dati anagrafici principali

Ogni SKU deve avere:
- prezzo;
- unità;
- lotto;
- origine;
- informazioni obbligatorie applicabili;
- allergeni se rilevanti;
- peso/prezzo quando applicabile;
- foto/descrizione opzionale.

Il prezzo visualizzato deve corrispondere al prezzo addebitato.

## 15. Videosorveglianza

Scopo:
- tutela beni;
- deterrenza;
- ricostruzione eventi.

Configurazione base:
- 1 camera ingresso;
- 1 camera area distribuzione automatica, se il layout lo richiede;
- niente audio;
- niente riconoscimento facciale;
- niente analytics biometrici;
- campo limitato alla pertinenza necessaria;
- cartello prima dell'ingresso nella zona ripresa;
- informativa estesa accessibile;
- retention definita e motivata;
- accessi alle registrazioni tracciati/limitati.

Se le telecamere possono riprendere lavoratori:
- verificare preventivamente gli adempimenti dell'art. 4 Statuto dei lavoratori e relative autorizzazioni/accordi.

Di lavoro candidate hardware:
- Ubiquiti G5 Turret Ultra o equivalente PoE esterno/tamper-resistant;
- storage locale;
- nessun cloud obbligatorio per registrazione base, se architettura scelta lo consente.

## 16. Accesso e sicurezza fisica

Possibili livelli:

### S0 — macchina accessibile dall'esterno
Solo se macchina e installazione sono espressamente esterno.

### S1 — chiosco sempre aperto
Accesso cliente a piccola area coperta, macchine protette.

### S2 — locale con porta
Ingresso sempre libero o controllato.

Configurazione base di lavoro:
- S1/S2;
- nessun badge cliente obbligatorio;
- porta/verifica bloccante solo se necessario per meteo/sicurezza.

Non introdurre registrazione identità del cliente senza un bisogno reale.

## 17. Illuminazione

Requisiti:
- ingresso visibile;
- area acquisto leggibile;
- telecamera non abbagliata;
- niente zone d'ombra critiche;
- consumo contenuto;
- comando crepuscolare/astronomico;
- comando manuale;
- apparecchi esterno/IP adeguati.

Interfaccia con BOM-026/impianto elettrico generale se fisicamente vicino.

## 18. Elettrico

Carichi separati:
- distribuzione automatica/refrigerazione;
- POS/payment;
- network;
- camera/NVR;
- lighting;
- eventuale HVAC chiosco.

Richiedere:
- linea dedicata;
- protezioni;
- SPD secondo progetto;
- messa a terra;
- sezionamento;
- presa/manutenzione;
- energy meter per distribuzione automatica;
- as-built.

## 19. Continuità elettrica — BESS aziendale

**Nessuna UPS locale nella configurazione base BOM-028.**

Il progetto dispone di backup a batterie con **30 kW di potenza** e lo spaccio viene integrato in quel sistema di continuità.

Da verificare nel package energia:

- capacità utile in kWh;
- potenza continua;
- picco;
- tempo di trasferimento;
- autonomia al SOC di riserva;
- funzionamento in isola;
- riavvio da rete assente se previsto.

Carichi BOM-028 da includere nel distacco selettivo dei carichi:

### P0 — controllo/transazioni
- server/control plane minimo;
- rete;
- Stripe/reader connectivity;
- controller distribuzione automatica;
- logger critici.

### P1 — catena del freddo
- distribuzione automatica refrigerato;
- eventuale HVAC tecnico necessario.

### P2 — security/operations
- CCTV/NVR;
- illuminazione minima;
- servizi non critici.

In stato BESS limitato il server centrale deve poter disattivare o rinviare carichi non essenziali prima di perdere controllo o catena del freddo.

Se la temperatura non è più garantita:
- stop-vend;
- alarm;
- classificazione lotto secondo HACCP.

## 20. Server centrale, orchestrazione e cybersicurezza

BOM-028 usa `07_AUTOMAZIONE_DATI_AI/CENTRAL_ORCHESTRATION_SERVER.md` come architettura di riferimento.

Il server centrale gestisce:

- catalogo;
- ordini;
- Stripe;
- inventory;
- lot tracking;
- refill;
- task personale;
- logistica;
- distribuzione automatica state;
- temperature;
- scadenze;
- rimborso;
- manutenzione;
- previsioneing domanda/offerta.

Segmenti distinti:

- VLAN VENDING;
- VLAN CCTV;
- guest/customer se presente;
- OT aziendale separato.

Principi:

- server come sistema autorevole dei dati;
- fornitore cloud solo come integrazione opzionale, non master;
- negazione predefinita verso PLC/OT;
- MFA;
- account di servizio separate;
- segreti lato server;
- idempotency;
- registro di controllo log;
- backup/restore;
- monitoring;
- inventario firmware.

Se una distribuzione automatica espone soltanto MDB o telemetria proprietaria insufficiente, prevedere verifica bloccanteway locale/protocol adapter per produrre eventi e comandi integrabili nel server centrale.

Il server pianifica e coordina; safety locale e interblocchi macchina restano indipendenti.

## 21. Privacy pagamenti e clienti

Configurazione base:
- nessun account cliente necessario;
- nessun loyalty obbligatorio;
- no riconoscimento facciale;
- no profilazione non necessaria.

Se in futuro vengono introdotti:
- app;
- loyalty;
- notifiche;
- e-commerce;
- prenotazioni;

creare valutazione privacy separata.

## 22. Rifornimento

Rifornimento preferito:
- durante finestra poco frequentata;
- distribuzione automatica temporaneamente in modalità manutenzione;
- sportello area cliente segregato;
- carrello standard;
- scanner;
- verifica lotto/quantità;
- pulizia prima/contestuale;
- FIFO.

KPI:
- minuti/rifornimento;
- errori slot;
- esaurimento scorte;
- invenduto;
- scarto;
- vendite/SKU/giorno.

## 23. Pulizia

### Giornaliera/visita rifornimento
- vano ritiro;
- superfici contatto cliente;
- pavimento;
- cestino;
- controllo perdite;
- check odori/insetti.

### Settimanale
- ripiani;
- guarnizioni accessibili;
- filtri/condensatore secondo fornitore;
- camera/lenti;
- signage;
- touch.

### Programmata
- gruppo frigo;
- sbrinamento;
- scarico condensa;
- ventilatori;
- sensori;
- verifica temperatura;
- electrical check;
- payment terminal.

## 24. Waste e scadenze

Regole:
- min/max stock per SKU;
- markdown/discount solo se sistema lo gestisce correttamente;
- stop automatico a scadenza;
- ritiro anticipato per SKU sensibili;
- registrazione scarto;
- nessun reset manuale della scadenza senza nuova validazione.

## 25. Resi/rimborsi

Un non presidiato store senza procedura rimborso è incompleto.

Prevedere:
- numero/QR assistenza;
- ID macchina;
- timestamp transazione;
- selezione;
- procedura inceppamento;
- rimborso cashless;
- SLA;
- registro reclami.

Non aprire un vano resi food self-service senza progetto igienico specifico.

## 26. Modalità di guasto

| Modalità di guasto | Conseguenza | Ripiego |
|---|---|---|
| frigo guasto | rischio prodotto | blocco selezioni + allarme + HACCP |
| mancanza alimentazione | perdita freddo/pagamento | BESS 30 kW + distacco selettivo dei carichi + stop-vend se catena del freddo non garantita |
| BESS low SOC | autonomia insufficiente | priorità P0/P1, riduzione carichi P2/P3 |
| server centrale non disponibile | pianificatore/payment workflow indisponibile | local safe mode; niente nuove vendite se stato non riconciliabile |
| database/bus eventi non disponibile | perdita consistenza | queue/buffer dove sicuro, stop nuove transazioni critiche |
| Internet assente | Stripe/cloud non disponibili | policy offline validata; nessun doppia erogazione |
| Stripe/API non disponibile | no nuove autorizzazioni | machine unavailable per nuovi acquisti, recupero pagamenti pending |
| webhook ritardato | ordine ambiguo | state machine pending + reconciliation, mai doppia erogazione |
| pagamento confermato ma vend fallisce | cliente addebitato senza prodotto | automatic recupero/rimborso |
| inceppamento spirale | cliente non riceve prodotto | rimborso + disabilitazione vano |
| prodotto fragile cade | danno/reso | Lift/locker + test pack |
| logger guasto | perdita verifica indipendente | sostituzione + sensore macchina |
| camera guasta | sicurezza ridotta | alert e ripristino |
| NVR pieno | perdita registrazioni | retention/capacity management |
| porta chiosco bloccata | accesso/uscita compromessi | uscita sempre sicura + apertura manuale |
| vandalismo | fermo | antiscasso + CCTV + ricambi |
| esaurimento scorte | vendite perse | previsione + refill pianificatore |
| scadenza | vendita non conforme | expiry lockout |
| prezzo errato | contestazione | dati anagrafici principali unico sul server |
| fiscale offline | non conformità | procedura validata con fornitore/commercialista |
| cloud fornitore distribuzione automatica down | feature fornitore assente | server centrale continua sulle interfacce locali disponibili |

## 27. Manutenzione e ricambi

Ricambi minimi da RFQ:
- motore spirale/slot;
- sensore;
- ventola;
- filtro;
- guarnizione;
- serratura;
- chiavi service;
- fusibili/alimentatori;
- controller/payment cable;
- display/touch se modulare;
- lettore pagamento spare path;
- logger;
- camera;
- surge protector;
- switch PoE.

Richiedere:
- SLA Italia;
- tecnico FVG/NE Italia;
- tempo di consegna ricambi;
- canoni;
- fine vita;
- disponibilità 7–10 anni.

## 28. Cassetta intelligente + carrello intelligente senza scansione

Documento dedicato:
`SMART_CRATE_SMART_CART_ARCHITECTURE.md`.

### Decisione di lavoro

Il rullo con camera+pesa viene mantenuto come ripiego/diagnostica, non come checkout principale.

La direzione R&D prioritaria è:

`cassetta intelligente + carrello intelligente + fusione sensoriale + server centrale`

Ogni prelievo produce segnali correlabili:

- `crate -Δm`;
- `cart +Δm`;
- prossimità/localizzazione;
- evento camera;
- SKU noto dalla posizione crate;
- cart/session ID.

Il server genera un evento `ITEM_ADDED` soltanto quando il indice di confidenza supera la soglia; altrimenti chiede conferma al cliente sul display.

Il ritorno prodotto è simmetrico con `ITEM_REMOVED`.

### Schermo

- ESL/e-paper su ogni posizione SKU/cassetta;
- LCD/OLED 7–10" sul cart;
- niente display per singolo pezzo;
- prezzo e informazioni sempre derivati dallo stesso master server.

### Metrologia

Le celle di carico economiche sono rilevazione.

La misura che determina un prezzo a peso deve essere legalmente idonea.

Pilot:
- M1 modulo idoneo alla vendita a peso sulla cassetta intelligente/cluster;
- M3 stazione certificata di conferma/ripiego;
- M2 cart-scale soltanto se validata dal punto di vista metrologico.

### Pagamento

Configurazione base:
- basket già completo sul cart;
- Stripe UX700 fisso al verifica bloccante;
- solo tap/pay all'uscita;
- nessuna scansione.

Futuro:
- payment sul cart;
- sessione con metodo di pagamento associato all'ingresso.

### Uscita

Verifica bloccante state:

`PAID && CART_RECONCILED && !BLOCKING_ANOMALY`

Il verifica bloccante non deve mai impedire l'esodo delle persone e deve avere emergency/manual release.

### Rientro

Configurazione base:
- rientro e ricarica annidati.

Futuro:
- un rover/tug recupera una fila di cart se parcheggio e volumi lo giustificano.

Non motorizzare ogni cart configurazione base.

## 29. Regola economica

Separare:

`CAPEX`
- chiosco/shell;
- distribuzione automatica;
- Stripe Terminal / UX700 o hardware Stripe non presidiato compatibile;
- fiscal interface;
- electrical;
- network;
- CCTV;
- logging;
- lighting;
- signage;
- civil works;
- install/commissioning;
- cassetta intelligente pilot;
- carrello intelligentes;
- ESL/e-paper;
- legal metrology hardware;
- exit verifica bloccante/dock.

`OPEX`
- fee Stripe;
- connettività/compute/storage server;
- fiscal service;
- energia;
- refrigerazione;
- manutenzione;
- pulizia;
- assicurazione;
- consumabili;
- scarto;
- connectivity.

`COGS/retail`
- confezionamento;
- etichettas;
- commissioni;
- IVA/fiscalità;
- scarti.

## 30. Verifica bloccante BOM-028

1. regime R1 vendita diretta agricola vs R2 distribuzione automatica retail;
2. verifica SUAP;
3. notifica/comunicazione alimentare;
4. mix SKU;
5. temperatura per SKU;
6. confezionamento;
7. shelf-life;
8. capienza giornaliera;
9. macchina shortlist;
10. pilot erogazione;
11. Stripe Terminal non presidiato / UX700 e integrazione server;
12. fiscalizzazione;
13. rete/4G;
14. integrazione BESS 30 kW / autonomia in kWh;
15. videosorveglianza/privacy;
16. accessibilità;
17. layout rifornimento;
18. HACCP;
19. RFQ installato;
20. TCO 5 anni;
21. test 500 vendite + reconciliation server/Stripe/vend;
22. cassetta intelligente/cart sensor-fusion pilot;
23. metrologia legale su SKU venduti a peso;
24. paid-exit verifica bloccante safety validation;
25. commissioning e go-live controllato.
