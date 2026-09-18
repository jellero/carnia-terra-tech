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
- fallback manuale quando il sistema automatico non è disponibile.

Lo spaccio non deve diventare un secondo negozio tradizionale da presidiare.

## 2. Due regimi da tenere separati

### R1 — vendita diretta agricola

Baseline preferita per Carnia TerraTech se ricorrono i requisiti:

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

**Gate:** prima dell'ordine macchine, definire con SUAP/commercialista il regime effettivo del punto vendita.

## 3. Non confondere vendita con somministrazione

Baseline BOM-028:

- prodotto confezionato o comunque venduto;
- nessun servizio assistito;
- nessuna preparazione di cibi nel punto vendita;
- nessuna cucina;
- nessuna area attrezzata specificamente per somministrazione.

Il consumo immediato di prodotti agricoli venduti può avere una disciplina propria, ma non viene assunto automaticamente come baseline.

Se il layout introduce tavoli/attrezzature finalizzati al consumo sul posto, verificare se si ricade nella disciplina della somministrazione.

## 4. Modello fisico

Working architecture:

`accesso cliente -> area vendita automatica -> selezione/pagamento -> ritiro -> uscita`

Con retro-servizio separato:

`Tech Barn / stock -> controllo lotto -> rifornimento -> inventario -> vendita`

### Baseline preferita

- piccolo locale/kiosk protetto;
- distributore refrigerato principale;
- eventuale modulo ambient/cool separato;
- nessun accesso cliente allo stock posteriore;
- quadro elettrico e rete non accessibili;
- macchina ancorata/protetta;
- telecamera su ingresso e area vending;
- illuminazione;
- cestino;
- eventuale display/wayfinding;
- accesso rifornimento separato o in finestra chiusa al pubblico.

### Outdoor puro

Non è baseline salvo macchina esplicitamente progettata/certificata dal costruttore per installazione outdoor nella configurazione proposta.

Le macchine indoor non vengono esposte direttamente a:

- pioggia;
- neve;
- irraggiamento;
- gelo;
- condensa;
- vandalismo non previsto;
- polvere/acqua di lavaggio.

La FAS Skudo presentata nel 2026 come soluzione riprogettata per outdoor è un benchmark di categoria da RFQ, non un acquisto già deciso.

## 5. Matrice SKU/temperatura

Non esiste una sola temperatura valida per tutti i prodotti.

### Classe T-A — cold leafy

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

### Classe T-B — cool-sensitive produce

Esempi:
- pomodoro;
- peperone;
- basilico.

Interfaccia con BOM-024 CR-B.

Questi SKU non vengono messi automaticamente in una macchina a 0–4 °C.

Servono:
- setpoint idoneo;
- durata permanenza;
- packaging;
- verifica chilling injury/shelf-life.

Necta Gusto 8 dichiara layout stratificati con zone 0–3 °C, 5–7 °C e 8–12 °C. Questo rende la piattaforma interessante da testare, ma **non prova da solo** che ogni SKU aziendale sia idoneo a ciascuna zona.

### Classe T-C — ambient

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
- outdoor non assunto.

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

Serve pilot con packaging reale.

## 7. Packaging e interfaccia BOM-025

Lo spaccio eredita da BOM-025:

- label/lotto;
- barcode/QR;
- packaging retail;
- traceability.

Vincoli vending:
- dimensione pack compatibile;
- peso;
- scorrevolezza;
- rigidità;
- assenza di apertura accidentale;
- resistenza a drop/spirale/ascensore;
- leggibilità etichetta;
- condensa.

Test richiesti:
- 100 erogazioni per SKU critico;
- zero jam;
- zero rottura pack;
- danno prodotto entro soglia accettata;
- lettura lotto;
- recupero prodotto in fault.

## 8. Pagamenti — Stripe nativo

Stripe è il payment stack unico di progetto; payment stack alternativi non fanno parte della baseline.

Il server centrale Carnia TerraTech è il proprietario del flusso ordine/pagamento/vendita e usa Stripe come payment processor.

### Terminal unattended

Per un ambiente realmente unattended/vending, il candidato Stripe Terminal è **Verifone UX700**.

La documentazione Stripe corrente lo identifica come dispositivo self-service/unattended e ne indica, tra le caratteristiche:

- EMV chip;
- contactless/wallet;
- Ethernet/Wi-Fi;
- IP65;
- IK08;
- integrazione server-driven;
- disponibilità Italia nella matrice corrente;
- modalità offline come capability del dispositivo.

La combinazione esatta offline + server-driven + configurazione italiana va verificata nel pilot e nella documentazione Stripe vigente.

### Flusso transazionale working

`selection -> inventory reservation -> order -> PaymentIntent -> Stripe Terminal -> payment confirmed -> authorize vend -> vend_ack -> close order`

Il pagamento riuscito **non equivale** a vendita completata finché il sistema non riceve conferma dell'erogazione.

Se l'erogazione fallisce:

- ordine resta in stato recovery;
- slot/machine può essere disabilitato;
- il server esegue retry soltanto se sicuro;
- altrimenti avvia refund/cancel coerente con lo stato Stripe.

### Requisiti software

- PaymentIntent;
- webhook;
- idempotency key;
- correlation id;
- state machine esplicita;
- reconciliation;
- refund API;
- audit;
- gestione delayed webhook;
- protezione da double-vend/double-refund.

Le credenziali Stripe restano server-side; nessuna secret key nel controller vending.

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
3. soglia warning;
4. soglia stop vendita;
5. timestamp;
6. allarme remoto;
7. procedura verifica prodotto;
8. restart controllato.

Non basta vedere "compressore ON".

### Fault mode

Se temperatura esce dalla finestra accettata:
- bloccare le selezioni coinvolte;
- non continuare a vendere "finché sembra freddo";
- generare allarme;
- classificare il lotto;
- decidere scarto/rientro secondo HACCP.

## 12. Logger indipendente

Working candidate:
- Testo 160 T o classe equivalente;
- Wi-Fi;
- memoria locale;
- allarmi;
- alimentazione a batteria;
- monitoraggio indipendente dal controller della vending.

Per impiego alimentare definitivo, preferire logger/sistema specificamente adatto al contesto HACCP e alla validazione richiesta.

## 13. Inventario, logistica e scheduler centrale

Il vendor vending non è il system of record.

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
- refund;
- vend_command;
- vend_ack;
- jam;
- temperature fault;
- manual removal;
- expiry;
- waste;
- reconciliation.

Il server incrocia questi dati con:

- celle BOM-024;
- packaging BOM-025;
- raccolta prevista;
- ordini;
- personale disponibile;
- logistica/AMR;
- storico vendite;
- meteo/stagionalità;
- forecast domanda/offerta.

Output operativo:

- refill target;
- task al personale;
- missioni logistiche;
- quantità da trasferire da cella a spaccio;
- reorder/stock target;
- markdown/promotion candidate;
- rischio stockout;
- rischio waste.

L'inventario teorico viene sempre riconciliato con audit fisico e feedback macchina.

## 14. Prezzi e master data

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

Baseline:
- 1 camera ingresso;
- 1 camera area vending, se il layout lo richiede;
- niente audio;
- niente facial recognition;
- niente analytics biometrici;
- campo limitato alla pertinenza necessaria;
- cartello prima dell'ingresso nella zona ripresa;
- informativa estesa accessibile;
- retention definita e motivata;
- accessi alle registrazioni tracciati/limitati.

Se le telecamere possono riprendere lavoratori:
- verificare preventivamente gli adempimenti dell'art. 4 Statuto dei lavoratori e relative autorizzazioni/accordi.

Working candidate hardware:
- Ubiquiti G5 Turret Ultra o equivalente PoE outdoor/tamper-resistant;
- storage locale;
- nessun cloud obbligatorio per registrazione base, se architettura scelta lo consente.

## 16. Accesso e security fisica

Possibili livelli:

### S0 — macchina accessibile dall'esterno
Solo se macchina e installazione sono espressamente outdoor.

### S1 — kiosk sempre aperto
Accesso cliente a piccola area coperta, macchine protette.

### S2 — locale con porta
Ingresso sempre libero o controllato.

Baseline working:
- S1/S2;
- nessun badge cliente obbligatorio;
- porta/gate solo se necessario per meteo/sicurezza.

Non introdurre registrazione identità del cliente senza un bisogno reale.

## 17. Illuminazione

Requisiti:
- ingresso visibile;
- area acquisto leggibile;
- telecamera non abbagliata;
- niente zone d'ombra critiche;
- consumo contenuto;
- comando crepuscolare/astronomico;
- manual override;
- apparecchi outdoor/IP adeguati.

Interfaccia con BOM-026/impianto elettrico generale se fisicamente vicino.

## 18. Elettrico

Carichi separati:
- vending/refrigerazione;
- POS/payment;
- network;
- camera/NVR;
- lighting;
- eventuale HVAC kiosk.

Richiedere:
- linea dedicata;
- protezioni;
- SPD secondo progetto;
- messa a terra;
- sezionamento;
- presa/manutenzione;
- energy meter per vending;
- as-built.

## 19. Continuità elettrica — BESS aziendale

**Nessuna UPS locale nella baseline BOM-028.**

Il progetto dispone di backup a batterie con **30 kW di potenza** e lo spaccio viene integrato in quel sistema di continuità.

Da verificare nel package energia:

- capacità utile in kWh;
- potenza continua;
- picco;
- tempo di trasferimento;
- autonomia al SOC di riserva;
- funzionamento in isola;
- black-start se previsto.

Carichi BOM-028 da includere nel load shedding:

### P0 — controllo/transazioni
- server/control plane minimo;
- rete;
- Stripe/reader connectivity;
- controller vending;
- logger critici.

### P1 — cold-chain
- vending refrigerato;
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

## 20. Server centrale, orchestrazione e cybersecurity

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
- vending state;
- temperature;
- scadenze;
- refund;
- manutenzione;
- forecasting domanda/offerta.

Segmenti distinti:

- VLAN VENDING;
- VLAN CCTV;
- guest/customer se presente;
- OT aziendale separato.

Principi:

- server come system of record;
- vendor cloud solo come integrazione opzionale, non master;
- deny by default verso PLC/OT;
- MFA;
- service account separate;
- secrets server-side;
- idempotency;
- audit log;
- backup/restore;
- monitoring;
- firmware inventory.

Se una vending espone soltanto MDB o telemetria proprietaria insufficiente, prevedere gateway locale/protocol adapter per produrre eventi e comandi integrabili nel server centrale.

Il server pianifica e coordina; safety locale e interblocchi macchina restano indipendenti.

## 21. Privacy pagamenti e clienti

Baseline:
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
- vending temporaneamente in service mode;
- sportello area cliente segregato;
- carrello standard;
- scanner;
- verifica lotto/quantità;
- pulizia prima/contestuale;
- FIFO.

KPI:
- minuti/rifornimento;
- errori slot;
- stockout;
- invenduto;
- waste;
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
- filtri/condensatore secondo vendor;
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

Un unattended store senza procedura rimborso è incompleto.

Prevedere:
- numero/QR assistenza;
- ID macchina;
- timestamp transazione;
- selezione;
- procedura jam;
- refund cashless;
- SLA;
- registro reclami.

Non aprire un vano resi food self-service senza progetto igienico specifico.

## 26. Failure modes

| Failure mode | Conseguenza | Fallback |
|---|---|---|
| frigo guasto | rischio prodotto | blocco selezioni + allarme + HACCP |
| power fail | perdita freddo/pagamento | BESS 30 kW + load shedding + stop-vend se cold-chain non garantita |
| BESS low SOC | autonomia insufficiente | priorità P0/P1, riduzione carichi P2/P3 |
| server centrale down | scheduler/payment workflow indisponibile | local safe mode; niente nuove vendite se stato non riconciliabile |
| database/event bus down | perdita consistenza | queue/buffer dove sicuro, stop nuove transazioni critiche |
| Internet assente | Stripe/cloud non disponibili | policy offline validata; nessun double-vend |
| Stripe/API down | no nuove autorizzazioni | machine unavailable per nuovi acquisti, recovery pagamenti pending |
| webhook ritardato | ordine ambiguo | state machine pending + reconciliation, mai doppia erogazione |
| payment confirmed ma vend fallisce | cliente addebitato senza prodotto | automatic recovery/refund |
| jam spirale | cliente non riceve prodotto | refund + slot disable |
| prodotto fragile cade | danno/reso | Lift/locker + test pack |
| logger guasto | perdita verifica indipendente | sostituzione + sensore macchina |
| camera guasta | security ridotta | alert e ripristino |
| NVR pieno | perdita registrazioni | retention/capacity management |
| porta kiosk bloccata | accesso/uscita compromessi | uscita sempre sicura + apertura manuale |
| vandalismo | fermo | antiscasso + CCTV + ricambi |
| stockout | vendite perse | forecast + refill scheduler |
| scadenza | vendita non conforme | expiry lockout |
| prezzo errato | contestazione | master data unico sul server |
| fiscale offline | non conformità | procedura validata con fornitore/commercialista |
| cloud vendor vending down | feature vendor assente | server centrale continua sulle interfacce locali disponibili |

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
- lead time ricambi;
- canoni;
- fine vita;
- disponibilità 7–10 anni.

## 28. Regola economica

Separare:

`CAPEX`
- kiosk/shell;
- vending;
- Stripe Terminal / UX700 o hardware Stripe unattended compatibile;
- fiscal interface;
- electrical;
- network;
- CCTV;
- logging;
- lighting;
- signage;
- civil works;
- install/commissioning.

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
- waste;
- connectivity.

`COGS/retail`
- packaging;
- labels;
- commissioni;
- IVA/fiscalità;
- scarti.

## 29. Gate BOM-028

1. regime R1 vendita diretta agricola vs R2 vending retail;
2. verifica SUAP;
3. notifica/comunicazione alimentare;
4. mix SKU;
5. temperatura per SKU;
6. packaging;
7. shelf-life;
8. capienza giornaliera;
9. macchina shortlist;
10. pilot erogazione;
11. Stripe Terminal unattended / UX700 e integrazione server;
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
22. commissioning e go-live controllato.
