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

## 8. Pagamenti

Baseline:

- cashless;
- carte;
- contactless;
- wallet NFC;
- nessun obbligo di smartphone del cliente;
- modalità offline/fault definita.

Cash:
- non baseline;
- aumenta rischio furto;
- richiede monete/banconote;
- aumenta manutenzione e riconciliazione.

Working candidate vending:
- Nayax VPOS Touch / equivalente MDB;
- pagamento + telemetria;
- 4G/SIM;
- inventory/operations opzionali;
- canone e fee da TCO.

Alternative:
- terminale POS retail separato solo se l'architettura dello spaccio lo richiede;
- self-checkout/micro-market solo come scenario futuro.

Il sistema di pagamento deve essere verificato per:
- Italia;
- acquirer;
- fee;
- chargeback;
- rimborsi;
- compliance PCI gestita dal provider;
- integrazione fiscale;
- API/export dati.

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

## 13. Inventario

Inventario minimo per slot:
- SKU;
- lotto;
- quantità;
- data carico;
- TMC/scadenza;
- temperatura target;
- prezzo;
- vendite;
- scarti.

Eventi:
- load;
- sale;
- refund;
- jam;
- temperature fault;
- manual removal;
- expiry;
- waste;
- reconciliation.

Non basare inventario solo sul decremento teorico:
- prevedere audit fisico.

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

## 19. Continuità elettrica

Non dimensionare una piccola UPS per tenere acceso il compressore per ore.

Architettura:

### Tier 1 — electronics UPS
Mantiene:
- router;
- switch;
- controller;
- NVR;
- telemetria;
- eventualmente payment terminal.

### Tier 2 — refrigeration continuity
Da BOM-006/continuità aziendale:
- rete;
- generatore/backup generale se previsto;
- priorità carico;
- allarme power fail.

### Tier 3 — fail-safe food
Se il freddo non è garantito:
- vendita bloccata;
- valutazione prodotto.

## 20. Cybersecurity

Segmenti distinti:

- VLAN VENDING;
- VLAN CCTV;
- guest/customer se presente;
- OT aziendale separato.

Principi:
- deny by default verso PLC/OT;
- accesso remoto vendor limitato;
- MFA;
- account nominativi;
- credenziali non condivise;
- aggiornamenti;
- inventario firmware;
- export dati;
- log;
- backup configurazione.

Cloud vending accettabile solo dopo verifica:
- disponibilità;
- SLA;
- data export;
- lock-in;
- costo annuo;
- comportamento offline.

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
| power fail | perdita freddo/pagamento | alert + backup generale + stop vendita |
| rete assente | telemetria offline | macchina secondo policy offline; OT isolato |
| payment offline | no vendite / doppio addebito | stato chiaro + retry/refund |
| jam spirale | cliente non riceve prodotto | refund + slot disable |
| prodotto fragile cade | danno/reso | Lift/locker + test pack |
| logger guasto | perdita verifica indipendente | sostituzione + sensore macchina |
| camera guasta | security ridotta | alert e ripristino |
| NVR pieno | perdita registrazioni | retention/capacity management |
| porta kiosk bloccata | cliente intrappolato/accesso negato | uscita sempre sicura + apertura manuale |
| vandalismo | fermo/vetro rotto | antiscasso + CCTV + parti di ricambio |
| stockout | vendite perse | min stock + refill alert |
| scadenza | vendita non conforme | expiry lockout |
| prezzo errato | contestazione | master data single source |
| fiscale offline | non conformità | procedura vendor/commercialista |
| cloud vendor down | gestione remota assente | vendita/fallback definito offline |

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
- payment;
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
- fee payment;
- SIM/cloud;
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
11. payment provider;
12. fiscalizzazione;
13. rete/4G;
14. power/backup;
15. videosorveglianza/privacy;
16. accessibilità;
17. layout rifornimento;
18. HACCP;
19. RFQ installato;
20. TCO 5 anni;
21. test 500 vendite;
22. commissioning e go-live controllato.
