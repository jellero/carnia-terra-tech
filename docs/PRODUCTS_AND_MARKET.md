# Carnia TerraTech — Products & Market Benchmarks

**Data raccolta originaria:** 17 settembre 2026  
**Revisionato:** 18 settembre 2026  
**Stato:** `ARCHIVIO BENCHMARK / NON SPECIFICA DI PROGETTO / NON BUDGET CORRENTE`

## Avvertenza

Questo file conserva prezzi, prodotti e benchmark raccolti durante la prefattibilità.

Non determina più:
- priorità;
- quantità finali;
- architetture;
- CAPEX;
- scelta fornitori.

Per lo stato corrente usare:
- `../PROJECT_INDEX.md`;
- `../19_BOM_PRODOTTI_FORNITORI/`;
- `../22_FONTI_NORME_PREVENTIVI/`;
- `../21_RISCHI_DECISIONI_OPEN_POINTS/PROCUREMENT_CLOSURE_REGISTER.md`.

Ogni prezzo qui riportato deve essere **ricontrollato** prima di RFQ o decisione.

---

## Aggiornamento strategico 18/09/2026

- telescopico/mezzo multifunzione: **CORE P1**;
- forche + benna: baseline;
- AMR: **P2 / HOLD**, non requisito P1;
- rover galline: **ARCHIVIATO**;
- accesso umano in quota: funzione core;
- robot ragno manutenzione: R&S prioritaria separata;
- humus/vermicompost: core operativo;
- budget complessivo: fare riferimento al control budget €950k, non sommare automaticamente i benchmark di questo file.

---

## 1. Serra

### Tuttoserre — “Serra professionale” 8 × 40 m

- Superficie: **320 m²**
- Prezzo osservato: **€6.832 IVA inclusa**
- Benchmark: **~€21,35/m²**
- Tubi principali: Ø60 mm
- Passo montanti: 2,5 m
- Altezza gronda: 3,20 m
- Controventi inclusi
- **Teli/coperture esclusi**
- **Montaggio escluso**

Uso nel progetto: benchmark per non accettare preventivi struttura sproporzionati. Per 4.200 m² serve un'offerta multicampata specifica, non una semplice moltiplicazione lineare.

Da richiedere al fornitore:

- struttura 4.200 m²;
- verifica neve/vento per Venzone;
- 6 comparti;
- testate e porte;
- gronde;
- coperture;
- trasporto;
- accessori;
- specifica ancoraggi/fondazioni.

---

## 2. Pompe di calore

### Kensol KHP-R290-22-3

- Tipo: monoblocco aria-acqua
- Potenza dichiarata: **22 kW nominali**
- Alimentazione: trifase
- Refrigerante: R290
- Prezzo osservato su Senetic: **€3.616,74 + IVA** / **€4.412,42 IVA inclusa**
- Peso indicato: 202 kg
- Dimensioni indicate: 1380 × 1480 × 570 mm

Link di riferimento:

- Senetic: https://www.senetic.it/product/KHP-R290-22-3
- Produttore/serie Kensol: https://kensol.pl/

### Configurazione di lavoro

- 3 × 22 kW = **66 kW nominali iniziali**
- predisposizione quarta unità → **88 kW nominali**

Costo macchine, basato sul prezzo osservato:

- 3 unità: **€10.850,22 + IVA** circa
- 4 unità: **€14.466,96 + IVA** circa

### Dati da verificare prima dell'ordine

Non comprare solo sulla base dei “22 kW”. Richiedere:

- potenza resa a **A-7/W35** e altre condizioni fredde;
- COP a basse temperature;
- potenza elettrica assorbita;
- portata minima e nominale;
- perdita di carico;
- presenza e prevalenza del circolatore integrato;
- comportamento defrost;
- temperatura massima acqua;
- Modbus/BACnet o controllo esterno disponibile;
- rumorosità;
- requisiti di installazione/commissioning per mantenere garanzia.

---

## 3. Puffer / accumuli tecnici

### PLEION mod. P — 5.000 L senza scambiatori

- Volume: **5.000 L**
- Prezzo osservato: **€6.881**
- Funzione: volano/accumulo tecnico

Il progetto non lo considera più sufficiente come “batteria termica principale”: la batteria energetica target è molto più grande, ~30–50 m³.

### Idrotop — 2.000 L senza serpentino

- Prezzo osservato: **€1.599,89**
- Link: https://www.idrotop.com/riscaldamento/puffer-bollitori/per-uso-riscaldamento/puffer-2000-lt-serbatoio-accumulo-per-acqua-riscaldamento-senza-serpentino/

### Idrotop — 1.000 L con 1 serpentino

- Prezzo osservato: **€1.099,62**
- Materiale: acciaio al carbonio
- Puffer: 4 bar / 95 °C
- Scambiatore: 12 bar / 95 °C
- Isolamento: disponibile 100 mm
- Resistenza elettrica opzionale
- Link: https://www.idrotop.com/riscaldamento/puffer-bollitori/per-uso-riscaldamento/puffer-1000-lt-serbatoio-con-1-serpentino-accumulo-per-acqua-riscaldamento-/

### Prossima ricerca obbligatoria

Cercare soluzioni reali per **30.000 L iniziali, espandibili a 50.000 L**:

- 3 × 10 m³;
- 2 × 15 m³;
- serbatoio unico 30 m³;
- accumulo atmosferico/non pressurizzato + scambiatore a piastre;
- serbatoi coibentati industriali.

Confrontare costo totale inclusi trasporto, isolamento, posa, scambiatori, pompe, sensori e platea.

---

## 4. Fotovoltaico

### Input reale di procurement del promotore

- **~€200/kWp** per pannelli + fissaggi.

Quindi:

- 120 kWp → **~€24.000** pannelli + fissaggi
- 150 kWp → **~€30.000** pannelli + fissaggi

Esclusi:

- inverter;
- quadri;
- SPD;
- cavi;
- string box;
- strutture carport/pensiline;
- pratiche e connessione;
- manodopera.

### Working configuration

- 120 kWp iniziali
- predisposizione 150–180 kWp
- moduli indicativi 450 W → ~267 moduli per 120 kWp
- superfici prioritarie: Tech Barn, carport, vermicompost, pensiline, aree servizi
- evitare ombreggiamento della serra produttiva.

### Inverter

Preferenza per più inverter trifase invece di uno unico, per esempio:

- 3 × ~40 kW, oppure
- 2 × 50 kW + 1 × 20–30 kW.

Modelli specifici ancora da selezionare con ricerca di mercato aggiornata.

---

## 5. PLC e I/O

### WAGO PFC200 750-8215

- Ruolo: PLC/controller centrale
- Prezzo di mercato discusso: **~€1.112**
- Link benchmark: https://www.idealo.it/confronta-prezzi/210489674/wago-controller-pfc200-g2-4eth-can-usb-750-8215.html

### Advantech ADAM-6050-D1

- Funzione: I/O digitali Ethernet
- Working quantity: 6
- Prezzo benchmark discusso: **~€205 cad.**
- Link: https://www.westercom.eu/en/ethernet-i-o-modules-adam-6000/7363/advantech-adam-6050-d1.html

### Advantech ADAM-6017-D

- Funzione: I/O analogici Ethernet
- Working quantity: 6
- Prezzo benchmark discusso: **~€334 cad.**

### Mean Well SDR-240-24

- Alimentatore DIN 24 V / 10 A / 240 W
- Working quantity: 7
- Prezzo benchmark discusso: **~€101 cad.**
- Link: https://www.tme.eu/it/details/sdr-240-24/alimentatori-per-guida-din/mean-well/

---

## 6. Sensori aria e substrato

### XY-MD04 / classe sensore T+RH RS485

- Prezzo osservato: **~€22,99**
- Interfaccia: RS485
- Alimentazione: 5–28 V o variante equivalente
- Working quantity: **18**

Uso: 3 punti T/RH per comparto.

### Tyenaza / sensore suolo RS485

Prodotto osservato su Amazon:

- prezzo: **€42,09 IVA inclusa**
- alimentazione: 12–24 V DC
- RS485
- IP68 dichiarato
- T range dichiarato: -40…80 °C
- umidità: 0–100%
- corpo ABS + acciaio inox 316

Link di riferimento:

https://www.amazon.it/conducibilit%C3%A0-temperatura-dellumidit%C3%A0-giardinaggio-agricoltura/dp/B09HTHRHDN

Working quantity finale: **24**, ma **prima acquistare 4 campioni** e validare:

- stabilità;
- ripetibilità;
- calibrazione;
- registri Modbus;
- comportamento in differenti substrati;
- misura EC realmente disponibile e affidabile.

24 × €42,09 = **€1.010,16**.

---

## 7. CO₂

### Senseair K30

- Tecnologia: NDIR
- Working quantity: 6
- Prezzo benchmark discusso: **~€54 cad.**
- Link benchmark: https://www.digikey.it/it/products/detail/senseair/030-8-0010/13535296

Da verificare versione/interfaccia più adatta all'integrazione industriale prima dell'ordine.

---

## 8. PAR

### Apogee SQ-514-SS

- Uscita: 4–20 mA
- Funzione: PAR 400–700 nm
- Working quantity: 6
- Budget usato: **~€600–700 cad.**
- Prezzo produttore storico discusso: $515 per la famiglia SQ-514

Link:

- https://www.apogeeinstruments.com/quantum-sensor-faqs/
- benchmark europeo: https://alphaomega-electronics.com/en/home/5724-sq-500-ss-full-spectrum-quantum-sensor.html

Questa è una delle misure dove si preferisce strumento serio, non clone economico come riferimento primario.

---

## 9. Meteo

### Davis Vantage Pro2 6252EU

- Funzioni: vento, direzione, pioggia, T, RH
- Budget/prezzo discusso: **~€1.147**
- Link benchmark: https://www.idealo.de/preisvergleich/OffersOfProduct/208697864_-vantage-pro2-6252eu-davis-instruments.html

Nota: per funzioni di sicurezza vento prevedere comunque fallback locale e sensore/contatto indipendente se necessario.

---

## 10. Temperature accumulo

### PT1000 classe A da immersione

- Working quantity: 12–18
- Prezzo benchmark discusso: **~€6,80 + IVA cad.**
- Link benchmark: https://www.automation24.com/resistance-thermometers

Uso: 4–6 quote verticali per serbatoio per leggere stratificazione.

---

## 11. Contatori elettrici

### Eastron SDM630 Modbus

- Trifase
- RS485/Modbus
- Working quantity: 8–12
- Prezzo benchmark: **~€95–100 cad.**
- Link: https://www.idealo.de/preisvergleich/OffersOfProduct/203474842_-sdm630-modbus-mid-v2-eastron.html

Uso per sotto-contabilizzare:

- PDC;
- pompe;
- fertirrigazione;
- ventilazione;
- cella frigo;
- robot;
- Tech Barn;
- FV;
- altre utenze significative.

---

## 12. Telecamere

### Ubiquiti UniFi G6 Bullet

- Working quantity: **12**
- Ruolo: overview fissa, 2 per comparto
- 4K / PoE
- Prezzo ufficiale discusso: **~€179 cad.**
- Link: https://eu.store.ui.com/eu/en/category/physical-security-bullet/products/uvc-g6-bullet

12 × €179 = **€2.148**.

### Ubiquiti UniFi G6 PTZ

Prodotto osservato su WISP Store:

- prezzo: **€414,67 IVA inclusa**
- doppio sensore 4K
- zoom ibrido 10×
- pan 350° / tilt 100°
- IR fino a 30 m
- PoE+
- IP66
- operating range dichiarato -30…+50 °C

Link:

https://wisp.store/unifi/18045-ubiquiti-unifi-camera-g6-ptz-black-uvc-g6-ptz-b.html

Working quantity iniziale: **2**, per perimetro/cortile.

---

## 13. NVR / rete UniFi

### UniFi UNVR Pro

- 7 bay
- Working choice: 1
- Prezzo discusso: **€449**
- Link: https://eu.store.ui.com/eu/en/products/unvr-pro

### Ubiquiti Dream Machine Pro

- gateway/firewall
- Working choice: 1
- Prezzo discusso: **€366**
- Link: https://eu.store.ui.com/eu/en/category/cloud-gateways-large-scale/products/udm-pro

### USW-Pro-24-PoE

- switch PoE centrale
- budget PoE 400 W
- Prezzo discusso: **€629**
- Link: https://eu.store.ui.com/eu/en/category/all-switching/products/usw-pro-24-poe

### HDD surveillance

Working configuration:

- 4 × 12 TB
- budget discusso ~€260 cad.
- totale ~€1.040

Modello specifico ancora da scegliere.

---

## 14. Automazione / visione — budget di lavoro

BOM preliminare già discussa:

| Sistema | Working budget |
|---|---:|
| PLC centrale | €1.112 |
| I/O digitali remoti | €1.230 |
| I/O analogici remoti | €2.004 |
| alimentatori 24 V | €708 |
| T/RH aria | €414 |
| suolo/substrato | €1.010 |
| CO₂ | €324 |
| PAR | €3.900 |
| bagnatura fogliare | €420 |
| pressione irrigazione | €630 |
| portata irrigazione | €1.050 |
| pH online | €800 |
| EC online | €800 |
| livelli | €290 |
| meteo | €1.147 |
| T batteria termica | €150 |
| contatori elettrici | €1.140 |
| energia termica | €1.200 |
| G6 Bullet | €2.148 |
| G6 PTZ | €829 |
| UNVR Pro | €449 |
| HDD | €1.040 |
| UDM Pro | €366 |
| switch PoE | €629 |
| fibra/switch remoti | €1.500 |
| insect cameras | €1.440 |
| depth camera robot | €450 |
| termocamera | €700 |
| edge server + GPU + UPS | €3.000 |
| quadri/cavi/SPD/morsetti | €8.000 |

Totale preliminare discusso: **~€38k**, arrotondato a **€40k di CAPEX di progetto** per questo blocco.

Questo totale è ancora misto tra prezzi trovati e budget tecnici. Va trasformato in BOM definitiva.

---

## 15. Pompe irrigazione / idraulica

Working specification, non ancora modello scelto:

- 2 pompe principali identiche 1+1;
- ~8–10 m³/h ciascuna;
- ~4–4,5 bar;
- ~2,2 kW indicativi;
- multistadio inox;
- inverter/VFD;
- aspirazione allagata se geometria cisterna lo consente.

Ricerca da fare con prodotti reali:

- Grundfos CR/CRE;
- Lowara e-SV;
- Pedrollo / Ebara equivalenti;
- confronto curve Q/H e prezzo reale.

---

## 16. Pompe dosatrici

Working requirements:

- A: 0–60 L/h, ~6 bar, PVDF/PTFE, controllo 4–20 mA/impulsi;
- B: idem;
- acido/pH: 0–10 L/h, 6–8 bar;
- additivo/disinfezione: 0–10/20 L/h;
- 1 dosatrice universale di ricambio.

Marchi da confrontare con mercato reale:

- SEKO;
- Etatron;
- Grundfos DDA/DDE;
- ProMinent.

---

## 17. Ventilazione HAF

Working quantity: **24 ventilatori**, 4 per comparto.

Ancora da ricercare e quotare con prodotti reali. Requisiti:

- ambiente serra;
- motore EC o regolabile;
- IP adeguato;
- buona efficienza;
- ricambi disponibili;
- integrazione 0–10 V / Modbus preferibile quando economicamente sensata.

---

## 18. Tubi termici e collettori

Working quantity:

- **~2.700–3.000 m** di tubo a bassa temperatura.

Da confrontare:

- PE-RT;
- PEX;
- diametro preliminare 20–25 mm;
- collettori di zona, miscelatrici, pompe, bilanciamento e flussimetri.

Prodotti reali ancora da selezionare.

---

## 19. Attrezzatura cantiere

Il montaggio serra viene gestito direttamente con 4 lavoratori esperti pagati.

Working budget attrezzi già discusso: **€18–30k**, da trasformare in lista reale.

Categorie:

- avvitatori/chiavi professionali;
- smerigliatrici;
- seghe;
- perforatori;
- laser;
- dinamometriche;
- DPI anticaduta;
- trabattello/piattaforme;
- generazione/distribuzione elettrica da cantiere;
- utensili installazione pali/ancoraggi;
- consumabili.

Regola: per beni da portare a contributo, cercare **nuovo** salvo ammissibilità esplicita diversa.

---

## 20. Lotti di prova prima degli acquisti massivi

Prima di replicare su 6 comparti:

### Lotto sensoristica

- 4 sensori substrato;
- 3 T/RH;
- 1 CO₂;
- 1 PAR serio;
- 1 ADAM-6017;
- 1 ADAM-6050;
- 1 alimentatore;
- 1 G6 Bullet.

Scopo: 30–60 giorni di prova, registrazione, drift, guasti, comportamento Modbus e manutenzione.

### Regola generale

Nessun lotto da 20–30 sensori low-cost prima di averne validati alcuni contro uno strumento di riferimento.
