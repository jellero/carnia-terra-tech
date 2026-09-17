# Carnia TerraTech — Punto 08: Macchine e logistica

**Aggiornato:** 17 settembre 2026  
**Stato:** `ARCHITETTURA AMR IN SVILUPPO / BOM-020 SVILUPPATA / DEMO SITO, SAFETY E ASSISTENZA UE BLOCCANTI`.

## 1. Obiettivo

Automatizzare il trasporto ripetitivo dentro e fra serra e Tech Barn senza creare un nuovo collo di bottiglia, mantenendo sicurezza con persone, funzionamento locale e possibilità di usare la stessa piattaforma per scouting, imaging e inventario.

Il primo AMR non sostituisce il mezzo multifunzione con forche/piattaforma e non trasporta persone.

## 2. Missioni iniziali

- trasporto cassette e materiali fra comparti, corridoio tecnico e Tech Barn;
- traino carrelli standardizzati se economicamente migliore del carico diretto;
- ritorno automatico vuoti;
- scouting visivo programmato;
- raccolta dati e inventario;
- missioni notturne a bassa velocità;
- docking/ricarica automatica;
- futura piattaforma per sensori o piccoli attrezzi, solo dopo analisi rischio dedicata.

## 3. Vincoli fisici working

- larghezza robot preferita <= 0,75 m; envelope completo con carico da verificare;
- corsie serra working >= 1,20 m;
- aree di inversione/turning working ~2–2,5 m;
- superfici, pendenze, soglie e drenaggi da masterplan reale;
- niente affidamento su pavimento perfettamente asciutto come requisito implicito;
- docking fuori dalle zone di lavaggio e spruzzo diretto.

## 4. Candidati

### Burro Verde — candidato funzionale prioritario da demo/RFQ

Progettato esplicitamente per serre e trasporto indoor/outdoor:

- larghezza 68,5 cm;
- payload 227 kg;
- traino fino a 908 kg su piano duro;
- LiDAR 360°, 12 camere, RTK, elaborazione onboard;
- navigazione anche GPS-denied;
- IP65 dichiarato;
- batterie LFP 2,56 kWh;
- autonomia dichiarata fino a 10 miglia, dipendente da carico/velocità;
- BOSS PRO con funzioni flotta/missioni.

**Prezzo:** `PREZZO DA PREVENTIVO`. Benchmark terzo 2026: classe commerciale < US$50k, con canone BOSS annuale; non convertirlo in CAPEX Italia senza offerta europea completa.

Criticità: ingresso mercato europeo annunciato per 2026; verificare CE/DoC applicabile, distributore/assistenza Italia, ricambi, SLA, docking e condizioni del canone.

### MiR250 — benchmark industriale safety/API, non baseline serra umida

- 250 kg payload;
- 580 × 800 × 300 mm;
- fino a 2 m/s;
- passaggi dichiarati fino a 800 mm;
- autonomia max payload fino a ~13 h;
- safety laser scanner e funzioni di sicurezza;
- progettato rispetto a ISO 3691-4 e norme correlate;
- API REST e MiR Fleet.

**Problema bloccante:** la specifica ufficiale corrente dichiara uso indoor, 5–40 °C, umidità non condensante, **IP21** e pavimento senza acqua/olio/sporco. Quindi non va acquistato per la serra senza validazione ambientale scritta del costruttore.

Prezzi benchmark:

- base: €44.284 + IVA in un listino UE;
- integrazione Italia da €53.141 + IVA;
- MiR Charge 48 V: €6.075 + IVA benchmark;
- Shelf Carrier integrato da €63.614 + IVA;
- Hook integrato da €78.514 + IVA.

### AgileX Bunker Mini / Pro — R&D, non AMR collaborativo baseline

Bunker Mini 2.0:

- ~570–584 mm larghezza secondo revisione/scheda;
- 25 kg payload;
- IP67;
- CAN, SDK/open software;
- base osservata €9.350 IVA tedesca inclusa;
- kit ROS2 pronto allo sviluppo ~€20.500 + IVA.

Bunker Pro: fino a 120 kg, IP67, CAN/ROS/open SDK, ma resta una piattaforma di sviluppo. Senza safety system e conformità completa dell'integrazione non deve circolare autonomamente fra lavoratori come macchina di produzione.

## 5. Architettura scelta per il pilot

Non esiste ancora un ordine. La sequenza decisionale è:

1. demo Burro Verde su geometria/umidità realistica;
2. offerta Europa/Italia completa, inclusi conformità, canone, supporto e docking;
3. MiR250 come benchmark industriale di safety, API e TCO, ma solo se l'ambiente operativo può essere separato/asciutto o se il costruttore approva l'applicazione;
4. AgileX soltanto per R&D/scouting in area controllata finché non viene progettata e validata una safety architecture completa.

## 6. Integrazione

Il robot deve ricevere missioni dal livello edge/supervisione locale con API documentata. Il PLC non delega al robot le proprie funzioni di sicurezza di processo.

Stati minimi:

`available / mission / charging / blocked / safety-stop / fault / manual / low-battery`.

Eventi minimi:

- richiesta trasporto;
- mission accepted/started/completed/failed;
- posizione/zona;
- batteria;
- obstacle/blockage;
- E-stop/safety event;
- docking/charging;
- manutenzione richiesta.

Cloud opzionale: perdita Internet non deve impedire il trasporto locale essenziale.

## 7. Scouting

Non assumere che le camere native del robot diano accesso ai dati grezzi necessari al nostro AI stack.

Optional payload indipendente:

- OAK-D Pro PoE / W PoE, enclosure IP65 nella famiglia S2 PoE;
- camera RGB + stereo/depth + IR/IMU;
- benchmark ~€671–769 IVA inclusa a seconda della variante/retailer;
- Jetson Orin Nano Super come edge payload economico: benchmark ~€382,40, regime IVA da verificare;
- mast, illuminazione, enclosure, cablaggio e storage da progetto.

Questa separazione preserva proprietà dei dati e possibilità di cambiare AMR in futuro.

## 8. Safety

Riferimento AMR/driverless industrial trucks: ISO 3691-4:2023; una nuova edizione è già in sviluppo nel 2026. Per una macchina acquistata/immessa sul mercato dopo il 20 gennaio 2027 verificare anche il Regolamento (UE) 2023/1230.

Prima del servizio:

- risk assessment dell'intero sistema robot + top module/carrello + ambiente;
- velocità per zona;
- attraversamenti pedonali;
- porte automatiche e compartimenti;
- visibilità negli incroci;
- comportamento con foglie/cassette/tubi a terra;
- stop distance al massimo carico;
- stabilità del carico;
- E-stop accessibili;
- recupero manuale sicuro;
- test perdita Wi-Fi/Internet/RTK;
- test condensa, acqua, fango e illuminazione reale.

## 9. Failure mode e fallback

Failure modes: navigazione persa, ostacolo persistente, batteria, sensore safety, ruota/motore, rete, docking, top module, software, mappa non aggiornata, acqua/condensa, carico instabile.

Fallback:

- corsie sempre utilizzabili con carrelli manuali;
- robot trainabile/spostabile in sicurezza secondo OEM;
- missioni ridotte alle aree sane;
- batterie/ricambi critici o SLA;
- nessun raccolto deve diventare irraggiungibile per guasto AMR.

## 10. Package sviluppati

- `AMR_ARCHITECTURE.md`;
- `RFQ_AMR.md`;
- `19_BOM_PRODOTTI_FORNITORI/MACCHINE_AMR_SERRA.md` — BOM-020;
- `22_FONTI_NORME_PREVENTIVI/MACCHINE_AMR_SOURCES.md`.

## 11. Gate BOM-020

1. layout reale e prove ingombro;
2. massa/volume dei carichi e carrelli;
3. pavimenti, pendenze, soglie, acqua/condensa;
4. demo con persone e ostacoli reali;
5. CE/DoC e standard applicati alla configurazione completa;
6. assistenza/ricambi Italia;
7. API e funzionamento offline;
8. docking e infrastruttura;
9. canoni software e TCO 5–8 anni;
10. top module/carrelli;
11. risk assessment e commissioning;
12. KPI pilot e decisione go/no-go.
