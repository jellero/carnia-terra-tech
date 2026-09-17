# Architettura robot tagliaerba — BOM-022

**Aggiornato:** 17 settembre 2026  
**Stato:** `WORKING ARCHITECTURE / SUPERFICIE PRATO E PILOT SITO BLOCCANTI`.

## 1. Funzione

Ridurre il lavoro ripetitivo di manutenzione del verde senza interferire con colture, persone, animali, viabilità e aree di servizio.

Il robot tagliaerba non è un sistema vitale: la priorità è **safe stop / park** in caso di errore di navigazione, rete o posizionamento, non la continuità a ogni costo.

## 2. Non confondere prato e area agricola esterna

Il working outdoor agricolo 700–1.500 m² non è automaticamente la superficie da falciare. Prima dell'ordine il masterplan deve separare:

- prato/verde ornamentale realmente falciabile;
- fasce di servizio attorno a Tech Barn e parcheggi;
- bordi serra e vasche;
- siepi, frutteto, vite e aree biodiversità;
- orto/colture outdoor;
- area galline;
- area didattica e relax;
- fossi/scarpate/acqua;
- viabilità mezzi.

La quantità d'ordine dipende dalla **superficie netta di prato robotizzabile**, non dai m² totali del lotto.

## 3. Classi dimensionali

### M1 — prato <=1.500 m²

Candidato Kress KR171E RTKⁿ + OAS, prezzo ufficiale Italia 2026 €1.699 IVA inclusa.

### M2 — prato 1.500–5.000 m²

Candidato Kress KR174E RTKⁿ + OAS:

- 5.000 m²;
- 647×470×290 mm;
- 12,6 kg;
- pendenza max 40%;
- IPX5;
- 4G/app/OTA;
- navigazione sistematica;
- obstacle avoidance;
- prezzo ufficiale Italia €2.999 IVA inclusa (€2.458,20 + IVA).

Questa è la **classe working prioritaria** finché il prato reale non supera 5.000 m².

### M3 — terreno difficile / forte pendenza <=5.000 m²

Mammotion LUBA 2 AWD 5000X:

- AWD;
- 5.000 m²;
- pendenza dichiarata fino a 80% (38°), bordo 45%;
- larghezza taglio 400 mm;
- 30 zone per la versione 5.000 m²;
- vision + RTK, binocular vision + ultrasonic radar + bumper;
- IPX6 macchina e dock, IPX7 stazione RTK;
- 4G + Wi-Fi + Bluetooth;
- prezzo ufficiale Italia osservato €2.499 IVA inclusa in promozione, listino €2.999; disponibilità osservata esaurita.

Alternativa 4×4 Kress EyePilot KR285E 5.000 m², €4.499 IVA inclusa, da approfondire se pendenze/terreno lo richiedono.

### M4 — >5.000 m² / uso professionale intensivo

Husqvarna Automower 560 EPOS:

- 12.000 m²;
- 50% pendenza interna;
- 59 cm larghezza;
- 17,3 kg;
- IPX5;
- 26 cm taglio, 20–60 mm;
- 150 min lavoro / 55 min carica;
- 57 kWh/mese dichiarati al massimo utilizzo;
- radar object detection;
- Fleet Services, GPS anti-theft, FOTA;
- prezzo ufficiale Italia €6.994 IVA inclusa;
- richiede EPOS RS5: €1.019 IVA inclusa;
- hardware base complessivo **€8.013 IVA inclusa** prima di Vision AI/installazione.

Il 580 EPOS, 16.000 m² e €9.054, è benchmark superiore ma sovradimensionato finché il masterplan non dimostra la necessità.

## 4. Posizionamento e zone

Preferire perimetri virtuali RTK/GNSS/vision rispetto al cavo fisico, ma il pilot deve provare:

- ombra GNSS di Tech Barn/serra/alberi;
- zone strette e corridoi;
- passaggi fra aree separate;
- prossimità a metallo/strutture;
- ritorno al dock;
- comportamento senza 4G/Wi-Fi/servizio correzione;
- recovery dopo perdita posizione.

No-go permanenti:

- vasche, fossi e drop-off;
- il prato condiviso con le galline non è un no-go permanente: è una zona a lockout dinamico quando gli animali sono presenti;
- colture e aiuole;
- aree tecniche sensibili;
- carreggiate non segregate;
- punti in cui la lama potrebbe raggiungere reti/teli/tubi.

No-go/lockout dinamici:

- prato/verde condiviso con galline durante libero accesso degli animali;
- riabilitazione del prato al rasaerba solo dopo conferma hens-clear da gate/porta/stato operatore;
- area didattica durante presenza pubblico;
- area relax occupata;
- piazzali durante carico/scarico;
- zone di cantiere/manutenzione.

## 5. Safety persone, animali e fauna

Regole Carnia:

1. **nessun taglio notturno** come default;
2. niente funzionamento in area con bambini/pubblico;
3. prato condiviso con galline: rasaerba abilitato soltanto quando un interlock conferma gli animali confinati/segregati; una finestra utile è prima dell'apertura mattutina del ricovero, comunque in luce diurna;
4. animali domestici e fauna non devono essere affidati soltanto all'object detection;
5. mappa e zone vietate verificate dopo ogni modifica del masterplan;
6. lame originali/compatibili certificate, viti sostituite secondo OEM;
7. stop/lift/tilt e bumper testati al commissioning;
8. dock installato fuori da allagamenti, traffico e spruzzi diretti.

Leibniz-IZW segnala collisioni notturne con robot rasaerba come rischio significativo per i ricci; il progetto adotta quindi una finestra operativa diurna.

## 6. Integrazione digitale

Il controllo remoto è utile ma non vitale.

Requisiti RFQ:

- stato robot/dock;
- batteria;
- posizione/area;
- avvio/stop/park;
- errori;
- manutenzione;
- export log se disponibile;
- eventuale API documentata;
- costo SIM/cloud/RTK service;
- comportamento senza Internet.

Non assumere API locale per Kress/Husqvarna/Mammotion finché il costruttore non la documenta. Se non esiste, accettare gestione tramite app/fleet purché la perdita cloud produca un comportamento sicuro.

## 7. Dock e infrastruttura

- 230 V protetta secondo ambiente;
- SPD/protezione elettrica se necessaria;
- base drenante e in piano;
- posizione fuori da traffico telescopico/AMR;
- spazio manutenzione;
- riferimento RTK con visibilità cielo dove richiesto;
- protezione meccanica del cavo alimentazione;
- eventuale garage soltanto se non degrada ricezione/raffreddamento e autorizzato OEM.

Husqvarna RS5 copre fino a 500 m di raggio e può servire più unità EPOS nella stessa installazione.

## 8. Manutenzione e ricambi

Minimi:

- set lame + viti;
- spazzole/ruote se previste;
- kit pulizia;
- fusibili/alimentatore/dock secondo SLA;
- eventuale batteria da TCO, non automaticamente a stock;
- backup mappa/configurazione;
- pulizia sottoscocca e sensori;
- controllo usura cuscinetti/ruote;
- rimessaggio stagionale secondo OEM.

Benchmark lame:

- Kress KA0002 6 lame lunga durata: €22,90 IVA inclusa;
- Husqvarna Endurance HSS 6 pz: €31 IVA inclusa; 45 pz: €188 IVA inclusa nel listino 2026;
- Mammotion lame ricambio: €55 IVA inclusa osservati sul sito ufficiale.

## 9. Failure mode / fallback

Failure modes:

- perdita GNSS/RTK;
- perdita rete/cloud;
- mappa errata;
- robot bloccato;
- dock non raggiunto;
- batteria degradata;
- lama/disco danneggiato;
- sensore obstacle/lift guasto;
- ruota impantanata;
- furto;
- ingresso in area non autorizzata.

Fallback:

- stop/park;
- recupero manuale;
- taglio manuale con rasaerba/decespugliatore di backup;
- esclusione temporanea di una zona;
- nessuna dipendenza del core agricolo dal robot.

## 10. Gate BOM-022

1. mappa prato netto e zone escluse;
2. pendenze e fondo reali;
3. copertura GNSS/RTK/4G/Wi-Fi;
4. orari pubblico/animali e interlock con porta/gate automatici del ricovero;
5. scelta M1/M2/M3/M4;
6. demo su sito o mock-up rappresentativo;
7. comportamento offline;
8. assistenza e ricambi Italia;
9. TCO 5–8 anni inclusi lame/batteria/cloud;
10. DoC/manuali e standard di sicurezza applicati;
11. commissioning zone/no-go;
12. prova safe-stop e recovery.