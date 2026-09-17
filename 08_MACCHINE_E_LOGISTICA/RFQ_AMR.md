# RFQ — AMR serra Carnia TerraTech

**Aggiornato:** 17 settembre 2026

## 1. Oggetto

Richiesta offerta per una piattaforma AMR/cobot mobile destinata a serra agricola compartimentata e Tech Barn, con funzioni di trasporto, traino, scouting, imaging e docking autonomo.

L'offerta deve essere separata per:

- robot base;
- top module/piattaforma;
- gancio/traino;
- carrelli compatibili;
- docking/charger;
- licenze software;
- canoni annuali;
- fleet manager;
- API/integrazione;
- commissioning;
- formazione;
- ricambi;
- assistenza/SLA;
- trasporto;
- eventuale connettività/cloud.

## 2. Ambiente

Richiedere risposta esplicita, non generica, su:

- funzionamento in serra agricola;
- umidità relativa ammessa;
- condensa;
- grado IP dell'intera macchina e dei singoli componenti critici;
- acqua sul pavimento;
- nebbia/fogging;
- residui vegetali/polvere;
- temperatura minima/massima;
- transizioni indoor/outdoor;
- luce solare diretta/riflessi;
- pendenze e soglie ammesse;
- tipo pavimento richiesto.

Il fornitore deve dichiarare esplicitamente se una delle condizioni invalida garanzia o safety certification.

## 3. Ingombri e prestazioni

Fornire:

- L×W×H;
- massa;
- ground clearance;
- turning circle/envelope;
- corridoio minimo con e senza carico;
- velocità max e velocità configurabili;
- pendenza max a vuoto e carico;
- payload carry;
- towing rating e condizioni;
- stabilità carico;
- capacità arresto a pieno carico;
- rumorosità.

Working site constraints da verificare:

- corsie ~1,20 m;
- turning/intersezioni ~2–2,5 m;
- robot preferito <=0,75 m di larghezza.

## 4. Navigazione

Specificare:

- LiDAR/vision/radar/ultrasuoni;
- GPS/RTK e capacità GPS-denied;
- SLAM/localization;
- mappe locali;
- teach-and-repeat;
- row following;
- dynamic obstacle avoidance;
- capacità di fermarsi/ripartire con corridoio temporaneamente bloccato;
- comportamento con vegetazione mobile e ostacoli bassi;
- comportamento con perdita sensore/localizzazione;
- missioni indoor/outdoor senza intervento umano.

## 5. Safety e conformità

Allegare:

- EU Declaration of Conformity o documento applicabile alla versione venduta in Italia;
- marcatura CE;
- standard applicati;
- valutazione rispetto a ISO 3691-4:2023 dove applicabile;
- ISO 13849-1 / PL delle safety functions dove applicabile;
- stop distance e protective fields;
- E-stop;
- bumper;
- warning lights/audio;
- manual/recovery mode;
- gestione trailer/top module;
- limiti di modifica ammessi senza invalidare conformità.

Dichiarare chi assume il ruolo di integratore/costruttore se viene montato un nostro payload custom.

## 6. Batteria e charging

Fornire:

- chimica;
- kWh;
- runtime a carico realistico;
- cicli garantiti;
- tempo 0–80 e 0–100%;
- possibilità battery swap;
- costo batteria ricambio;
- SOH disponibile via API;
- dock automatico;
- corrente/potenza caricatore;
- requisiti ambiente charging;
- comportamento blackout;
- costo stazione di ricarica.

## 7. Software e integrazione

Requisito preferenziale: controllo locale documentato.

Fornire:

- API locale;
- REST/MQTT/OPC UA/Modbus/ROS o altri protocolli;
- autenticazione;
- rate limits;
- documentazione sviluppatore;
- esempi codice;
- webhooks/eventi;
- accesso mission state;
- accesso fault/safety state;
- accesso SOC/SOH;
- log/export dati;
- API fleet;
- licenza API;
- dipendenze cloud;
- comportamento senza Internet;
- durata grace/offline;
- OTA update policy;
- cybersecurity;
- ownership dati.

Specificare se raw camera/LiDAR data sono accessibili e a quali condizioni/licenze.

## 8. Scouting/imaging

Quotare separatamente eventuale camera/scouting OEM.

Se non disponibile, confermare:

- payload elettrico disponibile;
- tensioni/ampere;
- punti di fissaggio;
- Ethernet/PoE;
- trigger/I-O;
- limite massa e baricentro;
- compatibilità con mast custom;
- conseguenze sulla conformità/safety.

## 9. Docking, porte e stazioni

Richiedere:

- tolleranza docking;
- area libera;
- fissaggi;
- protezioni;
- tempi medi docking;
- API charge state;
- interfaccia per porte automatiche;
- I/O o API per request/open/confirm/close;
- gestione attraversamento comparti.

## 10. Manutenzione e ricambi

Quotare e dichiarare lead time per:

- batteria;
- ruota/pneumatico/cingolo;
- motore/gearbox;
- safety scanner/LiDAR;
- camera;
- bumper;
- charger/dock;
- controller/IPC;
- connettori;
- fusibili;
- filtri/ventole;
- bumper switch;
- E-stop.

Fornire piano manutenzione 1.000/2.000/5.000 h o equivalente.

## 11. TCO

Fornire CAPEX e OPEX su 5 e 8 anni:

- hardware;
- licenze perpetue;
- subscription annuali;
- SIM/cloud;
- fleet management;
- supporto;
- manutenzione;
- ricambi;
- batterie;
- aggiornamenti;
- formazione;
- commissioning;
- travel/trasferta assistenza;
- costi di riattivazione dopo scadenza canone.

## 12. Pilot

L'offerta deve includere opzione demo/pilot su sito o ambiente equivalente con:

- corridoio 1,20 m;
- porte;
- persone;
- carrello/cassette;
- area umida compatibile con rating;
- docking;
- missione indoor/outdoor;
- rete locale e simulazione Internet assente;
- almeno 8 h di ciclo operativo o durata concordata.

## 13. Acceptance test

Acceptance minima:

- 100 missioni consecutive con KPI concordati;
- nessun contatto non previsto con persone/impianto;
- docking >=99% nel test concordato;
- recovery da obstacle/network fault;
- API integration completa;
- stop/restart documentato;
- prova carico massimo di progetto;
- test porte;
- esportazione log;
- manuali/as-built/backup configurazione consegnati.
