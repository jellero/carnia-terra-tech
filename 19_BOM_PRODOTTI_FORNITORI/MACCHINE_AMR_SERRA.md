# BOM-020 — AMR serra, logistica e scouting

**Aggiornato:** 17 settembre 2026  
**Ambito:** AMR per trasporto/scouting/imaging/inventario/docking fra serra e Tech Barn.  
**Stato:** `CANDIDATI REALI / PREZZI BENCHMARK / PILOT E CONFORMITÀ ITALIA BLOCCANTI`.

## 1. Distinta principale

| Codice | Voce | Quantità working | Stato | Benchmark / nota |
|---|---|---:|---|---|
| AMR-BASE-001 | robot produzione serra | 1 | DA PILOT/RFQ | Burro Verde candidato funzionale |
| AMR-BASE-SP | secondo AMR | 0–1 | FUTURO | solo dopo KPI pilot |
| AMR-TOP-001 | pianale/carrying deck | 1 | DA RFQ | 150–250 kg target |
| AMR-TOW-001 | hitch/traino | 0–1 | DA TCO | 500–900 kg target se traino |
| AMR-CART-001 | carrelli standardizzati | 2–n | DA LOGISTICA | ruote, freni, aggancio, stabilità |
| AMR-DOCK-001 | docking/charging station | 1 | OBBLIGATORIO | automatico preferito |
| AMR-REMOTE-001 | remote/manual control | 1 | PREFERENZA | recovery/aggancio |
| AMR-API-001 | licenza/API locale | 1 | OBBLIGATORIO | costo separato |
| AMR-FLEET-001 | fleet manager | 0–1 | FUTURO/CONDIZIONALE | 1 robot non deve dipenderne |
| AMR-SUB-001 | subscription software | annuale | DA RFQ | separare BOSS/Fleet/cloud |
| AMR-SIM-001 | connettività LTE/SIM | 0–1 | CONDIZIONALE | cloud non vitale |
| AMR-SAF-001 | safety package | 1 | OBBLIGATORIO | parte della macchina conforme |
| AMR-DOOR-001 | interfaccia porte | per varco | REQUISITO | API/I-O + consenso porta |
| AMR-BEACON-001 | luci/audio warning | 1 | OBBLIGATORIO | OEM |
| AMR-ESTOP-001 | E-stop | OEM | OBBLIGATORIO | accessibile |
| AMR-REC-001 | kit recovery/traino manuale | 1 | OBBLIGATORIO | secondo OEM |
| AMR-VIS-001 | scouting camera indipendente | 0–1 | OPZIONE | OAK-D Pro PoE/W PoE |
| AMR-CMP-001 | compute scouting | 0–1 | OPZIONE | Jetson Orin Nano Super |
| AMR-MAST-001 | mast camera regolabile | 0–1 | OPZIONE | stabilità/baricentro |
| AMR-LIGHT-001 | illuminazione scouting | 0–1 | OPZIONE | luce controllata |
| AMR-SSD-001 | storage locale | 0–1 | OPZIONE | dataset proprietario |
| AMR-PWR-001 | DC/DC + protezioni payload | 0–1 | OPZIONE | tensione OEM |
| AMR-NET-001 | Ethernet/PoE payload | 0–1 | OPZIONE | isolato/protetto |
| AMR-SP-BAT | batteria ricambio | 0–1 | DA TCO | prezzo OEM |
| AMR-SP-WHL | ruota/pneumatico/cingolo | 1 set critico | DA SLA | lead time |
| AMR-SP-SEN | sensore safety/LiDAR | 0–1 | DA SLA | costo/lead time |
| AMR-SP-BUMP | bumper/switch | 1 | PREFERENZA | ricambio economico |
| AMR-SP-CHG | parti charger/dock | 1 lotto | DA SLA | connettori/fusibili |
| AMR-COM-001 | mapping/site setup | 1 | OBBLIGATORIO | zone/velocità |
| AMR-COM-002 | safety validation | 1 | OBBLIGATORIO | sistema completo |
| AMR-COM-003 | API integration | 1 | OBBLIGATORIO | edge/PLC |
| AMR-COM-004 | 100-mission acceptance | 1 | OBBLIGATORIO | KPI |
| AMR-TRN-001 | formazione operatori | 1 package | OBBLIGATORIO | uso/recovery |
| AMR-DOC-001 | manuali/DoC/as-built/config backup | 1 | OBBLIGATORIO | consegna proprietario |

## 2. Candidato A — Burro Verde

**Funzione:** piattaforma commerciale specifica per serre, indoor/outdoor, carrying + towing.

Dati pubblici verificati:

- larghezza **68,5 cm**;
- lunghezza 138,9 cm;
- massa ~190 kg;
- payload **227 kg**;
- traino **908 kg** su superficie piana dura;
- LiDAR 360° ~40 m;
- 12 camere;
- RTK + navigazione interna GPS-denied;
- elaborazione onboard;
- batteria LFP 2,56 kWh;
- range dichiarato fino a 10 miles, dipendente da carico/velocità;
- **IP65**;
- BOSS PRO per missioni/fleet avanzate.

### Prezzo

- robot Verde: **PREZZO DA PREVENTIVO**;
- GOFAR, scheda commerciale 2026: classe prezzo **< US$50k**, con BOSS annuale — `BENCHMARK ESTERNO, NON QUOTAZIONE`;
- Burro ha annunciato ingresso Verde in Europa nel 2026;
- assistenza/rivenditore Italia: **DA VERIFICARE**;
- trasporto, IVA/import, CE/configurazione europea, dock, subscription e commissioning: **DA PREVENTIVO**.

### Gate specifico Burro

1. EU Declaration of Conformity per versione europea;
2. standard safety applicati;
3. service/ricambi Italia;
4. BOSS PRO prezzo/anno e clausole offline;
5. API locale e accesso dati;
6. dock compatibile Verde;
7. costo batteria/ruote/LiDAR/camere;
8. demo in serra con fogging/umidità.

## 3. Candidato B — MiR250

**Funzione:** benchmark industriale di safety, API, mapping e material handling.

Dati ufficiali correnti:

- payload **250 kg**;
- footprint **800 × 580 mm**;
- velocità max 2 m/s;
- spazi dichiarati fino a 800 mm;
- runtime max payload fino a ~13 h;
- 2 safety laser scanner SICK + 3D cameras;
- 12 safety functions ISO 13849-1;
- progettato rispetto a ISO 3691-4 con eccezioni dichiarate dal costruttore;
- REST API/MiR Fleet.

### Criticità ambiente

La scheda ufficiale MiR corrente dichiara:

- **indoor only**;
- 5–40 °C;
- 20–95% RH **non-condensing**;
- **IP21**;
- floor: no water, oil, dirt.

Quindi è `NON BASELINE SERRA` finché il costruttore non approva per iscritto l'ambiente reale. Un integratore italiano pubblica IP52; la discrepanza deve essere risolta sulla revisione/seriale offerto.

### Prezzi trovati

- MiR250 Base listino UE: **€44.284 + IVA**;
- integratore Italia, Base con assessment/sopralluogo: **da €53.141 + IVA**;
- MiR Charge 48 V: **€6.075 + IVA** benchmark UE;
- Shelf Carrier integrato Italia: **da €63.614 + IVA**;
- Hook integrato Italia: **da €78.514 + IVA**;
- Hook 250 modulo separato in un listino UE: **€26.435 + IVA**.

Benchmark incrociato, non offerta unica:

- Base €44.284 + Charge €6.075 = **€50.359 + IVA** prima di integrazione/top module;
- Base integrata Italia €53.141 + Charge benchmark = **€59.216 + IVA**;
- Hook integrato €78.514 + Charge benchmark = **€84.589 + IVA**, prima di Fleet/licenze/commissioning extra.

## 4. Candidato C — AgileX R&D

### Bunker Mini 2.0

- ~570–584 mm larghezza secondo documentazione/revisione;
- 25 kg payload;
- IP67;
- CAN, SDK/open software;
- 3–4 h charge nei benchmark reseller;
- **€9.350 IVA tedesca inclusa** retail osservato;
- macchina nuova business osservata anche a **€7.820 netto**;
- Bunker Mini + ROS2 R&D kit: **€20.500 + IVA** benchmark.

Uso: scouting/R&D in zona controllata. Non è equivalente a un AMR safety-rated per logistica fra persone.

### Bunker Pro

- fino a 120 kg;
- IP67;
- CAN/ROS/open SDK;
- ~3 h runtime nella documentazione storica;
- retail osservato **€22.550 IVA tedesca inclusa** per Pro 2.0.

Anche qui safety/conformità dell'integrazione restano a carico del progetto se usato come macchina autonoma custom.

## 5. Scouting payload vendor-independent

### Luxonis OAK-D Pro PoE

- Ethernet 1 Gbps/PoE;
- RGB + stereo depth + IMU;
- IR illumination + dot projector;
- enclosure IP65 nelle varianti S2 PoE Pro/W;
- benchmark retail **€671,46–768,86 IVA inclusa** a seconda variante.

### Jetson Orin Nano Super

- edge compute per modelli CV leggeri/medi;
- benchmark Italia **~€382,40**; regime IVA da confermare.

Questi componenti sono `OPZIONE`, perché Burro dispone già di molte camere/compute. Servono se vogliamo accesso dati totalmente indipendente dal vendor.

## 6. Safety e conformità

Riferimenti:

- ISO 3691-4:2023 — driverless industrial trucks e AMR;
- ISO 13849-1 per safety-related controls dove applicabile;
- Regolamento (UE) 2023/1230 applicabile dal 20 gennaio 2027, con date anticipate per alcune disposizioni.

La norma ISO 3691-4 è in revisione nel 2026: verificare edizione applicabile alla data di ordine/CE.

Top module, trailer, mast e accessori custom devono entrare nella valutazione rischio complessiva.

## 7. Cost model obbligatorio

`TCO_8y = robot + top module + dock + carrelli + integrazione + software/licenze + subscription + connettività + energia + manutenzione + batterie + ricambi + assistenza + fermo + formazione`.

Non confrontare Burro da solo contro MiR integrato: confrontare **sistemi funzionanti completi**.

## 8. KPI e decisione

Prima del secondo robot misurare sul primo:

- >=100 missioni acceptance;
- mission completion rate;
- interventi umani/100 missioni;
- downtime;
- ore manuali evitate;
- kg/cassette trasportati;
- costo/missione;
- safety stop e near miss;
- energia;
- manutenzione;
- qualità dati scouting.

Il secondo AMR entra nel CAPEX solo se il primo dimostra saturazione/ROI o necessità di ridondanza operativa.
