# Fonti BOM-020 — AMR serra

**Verificate:** 17 settembre 2026.

## Burro

### Burro Verde — pagina ufficiale
https://burro.ai/burro-verde/

Dati usati:

- soluzione purpose-built per autonomous towing in greenhouses;
- indoor/outdoor;
- LiDAR 360° 40 m;
- 12 camere;
- RTK;
- payload 500 lb / 227 kg;
- towing 2.000 lb / 908 kg su flat hard surfaces;
- width 27 in / 68,5 cm;
- onboard computing;
- 2,56 kWh LFP;
- BOSS PRO.

Classificazione prezzo: `PREZZO DA PREVENTIVO`.

### Burro standard — pagina ufficiale
https://burro.ai/burro/

Usata per:

- IP65 dichiarato sulla piattaforma Burro;
- onboard compute/local processing;
- fleet dashboard/OTA;
- 12 camere;
- data collection/scouting;
- dimensioni/payload della famiglia compatta.

Confermare nell'RFQ che IP65 si applichi esattamente alla configurazione Verde europea ordinata.

### Burro support
https://burro.ai/support/
https://docs.burro.ai/faq

Usate per:

- BOSS/BOSS PRO;
- warranty/service structure;
- docking station come accessorio/support item;
- pricing inquiry diretto.

### Ingresso Europa
Post Burro 2026: “Burro Verde coming to Europe in 2026”.
https://www.linkedin.com/posts/burro-ai_burro-verde-coming-to-europe-in-2026-activity-7399525771461099520-ajFN

Usare solo come prova di ingresso mercato annunciato; distributore/assistenza Italia restano `DA VERIFICARE`.

### Benchmark commerciale terzo
GOFAR — Burro Verde, aggiornamento 2026:
https://www.agricultural-robotics.com/robot/burro-verde

Riporta fascia prezzo <US$50k e costo annuale BOSS. `BENCHMARK ESTERNO / NON QUOTAZIONE DEL COSTRUTTORE`.

## Mobile Industrial Robots — MiR250

### Pagina ufficiale
https://mobile-industrial-robots.com/products/robots/mir250
https://mobile-industrial-robots.com/it/prodotti/robot/mir250/specifiche

Dati usati:

- 250 kg;
- 580×800 mm;
- 2 m/s;
- runtime;
- safety scanners/cameras;
- ISO 3691-4 e norme dichiarate;
- 12 safety functions;
- **indoor only, IP21, non-condensing, no water/oil/dirt**.

La scheda ufficiale prevale su pagine reseller che riportano IP52 finché MiR non chiarisce la revisione offerta.

### REST API / Fleet
https://mobile-industrial-robots.com/it/prodotti/software/mir-fleet
https://academy.mobile-industrial-robots.com/free-skill-paths/software-integration/

Usate per API REST e integrazione di terze parti.

### Prezzi
Elmark Automation:
https://elmark-automation.com/shop/mobile-industrial-robots/autonomous-mobile-robot-mir250

- MiR250 Base €44.284 net;
- Charge 48 V €6.075 net;
- Shelf Carrier €53.012 net nel listino;
- Hook robot €65.428 net;
- Hook module €26.435 net.

Abra Robotics Italia:
https://abrarobotics.com/prodotti/amr-mir250-base.html
https://abrarobotics.com/prodotti/amr-mir250-shelf.html
https://abrarobotics.com/prodotti/amr-mir250-hook.html

- Base da €53.141 + IVA con assessment/sopralluogo indicati;
- Shelf Carrier da €63.614 + IVA;
- Hook da €78.514 + IVA;
- Fleet/licenze/docking e commissioning avanzato separati secondo pagina.

## AgileX

### Bunker Mini official
https://global.agilex.ai/products/bunker-mini

- 690×570×335 mm nella pagina ufficiale;
- 25 kg payload;
- CAN;
- SDK/software resources;
- indoor/outdoor rugged.

### Bunker Pro official
https://global.agilex.ai/products/bunker-pro
https://global.agilex.ai/blogs/robotics/agilex-robotics-launched-tracked-mobile-robot-chassis-bunker-pro-with-ip67-prote

- IP67;
- payload 120 kg;
- CAN/ROS/open SDK;
- ~3 h runtime nella documentazione di lancio.

### Prezzi reseller
MYBOTSHOP:
https://www.mybotshop.de/Agile-X-Bunker-MINI-20
https://www.mybotshop.de/AgileX_1

- Bunker Mini 2.0 €9.350 incl. 19% VAT;
- Bunker Pro 2.0 €22.550 incl. 19% VAT.

Generation Robots:
https://www.generation-robots.com/en/352-outdoor-mobile-robots

- Bunker Mini 2.0 + ROS2 R&D kit da €20.500 ex VAT.

Resale / distributor benchmark:
https://www.resale.uk/en/agilex-bunker-mini-20/No-170097562

- macchina nuova 2026 €7.820 net, business benchmark.

## Scouting payload

### Luxonis OAK-D Pro PoE
https://docs.luxonis.com/hardware/products/OAK-D%20Pro%20PoE
https://docs.luxonis.com/hardware/platform/environmental-specifications/ip-rating

- RGB + stereo + IR + IMU;
- Ethernet/PoE;
- S2 PoE variants IP65.

Reichelt Italia:
https://www.reichelt.com/it/it/shop/prodotto/depthai_oak-d-pro-poe_grandangolare-354221

- benchmark €671,46–768,86 IVA inclusa a seconda variante.

### NVIDIA Jetson
Breakpoint Italia:
https://www.breakpoint.it/Home_i.asp?Id_NewCat=HBT&id_codprod=1362

- Jetson Orin Nano Super Developer Kit benchmark ~€382,40;
- regime IVA/disponibilità da confermare.

## Norme

### ISO 3691-4:2023
https://www.iso.org/standard/83545.html

Standard corrente pubblicato per driverless industrial trucks e relativi sistemi; include esplicitamente gli AMR negli esempi.

Nel 2026 è in sviluppo una nuova edizione:
https://committee.iso.org/standard/88615.html

Verificare la versione applicabile alla macchina ordinata e alla data di messa in servizio.

### Regolamento macchine UE
https://eur-lex.europa.eu/EN/legal-content/summary/machinery-safety-requirements.html

Regolamento (UE) 2023/1230: applicazione generale dal 20 gennaio 2027, con alcune disposizioni applicabili prima.

## Regola fonti

- dati safety/ambiente: preferire sempre costruttore/standard;
- reseller: validi come `PREZZO TROVATO`, non per derogare limiti tecnici ufficiali;
- prezzi esteri: non convertiti automaticamente in prezzo Italia;
- Burro Verde: prezzo Italia/UE e conformità europea restano `DA PREVENTIVO/DA VERIFICARE`.
