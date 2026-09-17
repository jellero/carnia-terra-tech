# Architettura AMR serra

**Aggiornato:** 17 settembre 2026  
**Stato:** `WORKING ARCHITECTURE / PILOT OBBLIGATORIO PRIMA DELL'ORDINE`.

## 1. Funzioni

L'AMR deve essere una piattaforma logistica, non un gadget autonomo.

Missioni di fase 1:

- trasporto cassette/prodotto/materiali;
- traino carrelli;
- ritorno vuoti;
- scouting e imaging programmato;
- inventario/localizzazione carrelli;
- docking autonomo.

Missioni future possibili: supporto manipolatore leggero, sensoristica agronomica, R&D laser/vision, ma solo con nuova analisi rischio.

## 2. Classi di carico

Definire tre use case separati:

- **L1 scouting:** payload sensori <=25–40 kg;
- **L2 carrying:** target 150–250 kg su piattaforma/carrello portato;
- **L3 towing:** target 500–900 kg su pavimento duro piano, se la soluzione a traino vince sul TCO.

Il dimensionamento definitivo usa massa reale cassette, numero contenitori, pendenza, accelerazione/frenata e stabilità.

## 3. Geometria

Working constraints:

- robot base preferibilmente <=750 mm;
- envelope con carico da verificare a ogni curva;
- corsia minima working 1.200 mm;
- turning/intersezioni working 2.000–2.500 mm;
- soglie/rampe da minimizzare;
- spazio docking protetto;
- nessun collo di bottiglia permanente che impedisca il passaggio manuale.

Il masterplan deve essere validato con sagome reali, non con il solo footprint del robot.

## 4. Ambiente

La serra è un ambiente più severo di un magazzino:

- elevata UR;
- possibile condensa;
- bagnatura da lavaggi/perdite;
- foglie/residui;
- luce solare variabile;
- nebbia/fogging;
- superfici riflettenti;
- transizioni interno/esterno;
- temperature non uniformi.

Requisito preferenziale di piattaforma: IP54 minimo pratico, **IP65 preferito** per il robot di produzione; rating inferiore ammesso solo in zone fisicamente separate e asciutte.

## 5. Navigazione

Preferenza:

- LiDAR + vision;
- funzionamento GPS-denied;
- mappa locale;
- route/mission editor;
- localization recovery;
- zone speed limits;
- ostacoli dinamici;
- fleet management futuro;
- API documentata.

RTK/GNSS è utile per esterno ma non deve essere requisito per l'interno serra.

## 6. Safety architecture

Il robot di produzione deve lavorare in presenza di persone solo con safety documentata sulla configurazione completa.

Richiedere:

- dichiarazione UE di conformità/DoC applicabile;
- elenco norme armonizzate/applicate;
- safety functions e performance level;
- scanner/sensori di sicurezza;
- bumper/E-stop;
- stop distance per velocità/carico;
- protective fields configurabili;
- comportamento a perdita localizzazione/comunicazione;
- manual/recovery mode;
- documentazione dell'eventuale top module e dei carrelli trainati.

ISO 3691-4:2023 è riferimento corrente per driverless industrial trucks/AMR. La configurazione agricola va comunque validata sul caso d'uso reale.

## 7. Burro Verde

Fit funzionale molto alto:

- 68,5 cm larghezza;
- 227 kg carrying;
- 908 kg towing su flat concrete;
- IP65;
- 360° LiDAR ~40 m;
- 12 camere;
- RTK + GPS-denied indoor;
- onboard compute;
- 2,56 kWh LFP;
- piattaforma già venduta per greenhouse towing.

Open points:

- disponibilità e supporto Italia/UE;
- CE/DoC per la configurazione europea;
- standard safety dichiarati;
- accesso API e controllo missioni da sistema locale;
- funzionamento senza cloud/BOSS temporaneamente indisponibile;
- costo BOSS PRO annuale;
- docking automatico e costo;
- ricambi/batterie/ruote/sensori;
- disponibilità raw data camera/LiDAR;
- gestione privacy/cybersecurity.

## 8. MiR250

Fit safety/software alto, fit ambiente serra basso senza separazione.

Punti forti:

- 250 kg;
- 580 mm wide;
- REST API/MiR Fleet;
- safety scanners e funzioni secondo ISO 13849-1;
- progettato per ISO 3691-4 e standard correlati;
- ecosistema top modules e assistenza industriale.

Bloccante ambientale ufficiale:

- indoor only;
- IP21;
- 20–95% RH non-condensing;
- floor: no water/oil/dirt.

Un integratore italiano pubblica IP52, ma prevale la scheda ufficiale del costruttore finché non arriva una conferma scritta di una variante/revisione diversa.

## 9. AgileX

Bunker Mini/Pro e Ranger Mini sono utili per R&D perché offrono CAN, SDK/ROS e protezione ambientale elevata in alcune versioni.

Non sono automaticamente una soluzione di produzione collaborativa. Se sviluppiamo internamente autonomia/safety/top module, Carnia TerraTech diventa di fatto integratore/costruttore del sistema macchina e deve gestire progettazione safety, validazione e conformità applicabile.

## 10. Docking e charging

Requisiti:

- docking automatico;
- posizione asciutta, non esposta a lavaggio/fogging;
- accesso manuale;
- interruttore/sezionamento;
- protezioni elettriche;
- ventilazione secondo batteria/OEM;
- telemetria SOC/SOH/cicli;
- missione automatica a carica bassa;
- possibilità di riprendere missione;
- spare battery solo se economicamente utile.

## 11. Interfaccia software

Preferire API locale con autenticazione documentata.

Comandi minimi:

- create/cancel mission;
- go-to station;
- dock/charge;
- pause/resume;
- speed zone/profile;
- payload/task ID.

Telemetria minima:

- pose/zona;
- SOC/SOH;
- mission state;
- fault code;
- safety state;
- obstacle/blockage;
- charging;
- odometro/ore;
- manutenzione.

Il PLC riceve stati utili ma il motion planner resta nel robot. Il server edge orchestra missioni e registra dati.

## 12. Scouting payload indipendente

Se l'API del robot non espone dati utili, installare un payload indipendente:

- OAK-D Pro PoE/W PoE;
- Jetson Orin Nano Super o compute equivalente;
- SSD;
- luce controllata;
- mast regolabile;
- enclosure/cablaggio;
- trigger da encoder/posizione se disponibile.

Obiettivo: immagini confrontabili nel tempo e dataset proprietario Carnia, indipendente dal vendor AMR.

## 13. KPI pilot

- km/ore autonome;
- mission completion rate;
- interventi umani/100 missioni;
- min persi per blocchi;
- kg o cassette trasportati/h;
- ore lavoro manuale evitate;
- Wh/km o kWh/giorno;
- uptime;
- near-miss/safety stop;
- danni a prodotto/impianto;
- qualità immagini scouting;
- costo manutenzione/1000 h;
- disponibilità ricambi.

## 14. Decision gate

Nessun ordine prima di una prova con:

- corridoio 1,2 m;
- curve/intersezioni reali;
- porte automatiche;
- persone;
- cassette/carrelli reali;
- fondo bagnato/umidità compatibile con specifica OEM;
- ostacoli bassi e vegetazione;
- test docking;
- perdita rete/cloud;
- stop e recovery;
- almeno un ciclo completo serra -> Tech Barn -> serra.
