# Vendor data snapshot — load closure / BOM-034

**Data verifica:** 18 settembre 2026  
**Stato:** `WEB/OEM SNAPSHOT / PREZZI BENCHMARK / RFQ INSTALLATO ANCORA RICHIESTO`

## 1. Regola

Questo file registra dati pubblici verificati oggi. Non sostituisce:
- offerta commerciale firmata;
- verifica CEI/DSO;
- dimensionamento sul lotto;
- misura reale;
- commissioning/SAT.

Priorità fonti: OEM/manuale ufficiale > distributore/retailer per prezzo > aggregatore solo come cross-check.

## 2. BESS / backup

### TESLA Group STILLA

Fonte OEM:
https://teslagroup.eu/our-products/stilla/

Dati pubblici correnti:
- PCS: 30 / 60 kW;
- overload: 33 / 66 kW;
- 400 V ±10%, 50 Hz;
- PF 0.1…1 leading/lagging;
- peak efficiency 97.3%;
- battery: 61 / 122 kWh nominal;
- LFP, up to 0.5C;
- DoD up to 100%;
- capacity guarantee statement: 80% @ 3500 cycles;
- operating temperature: -20…45 °C dichiarata non-derating;
- Modbus TCP;
- IP55+;
- peso ~2.800 kg;
- cabinet integrato con inverter, battery racks, cablaggi, control, fire-safety, temperature management, commissioning/documentation;
- prezzo: RFQ/on demand.

Stato Carnia:
- candidato C&I AC-coupled molto coerente con 30 kW / ~60 kWh;
- restano aperti CEI/DSO Italia, island/black-start, transfer waveform, usable EOL, service FVG e prezzo installato.

### Fronius Verto 30.0 Plus

OEM/manuale:
https://manuals.fronius.com/html/4204260552/it.html

Pagina prodotto:
https://www.fronius.com/it-it/italy/energia-solare/commerciale/prodotti-e-soluzioni/fronius-verto-verto-plus-massima-flessibilit-massima-sicurezza

Dati correnti:
- nominal output: 29,99 kW;
- nominal Full Backup: 29,99 kW;
- Backup Power Boost: fino a 50 kVA per 5–10 s, con sufficiente potenza PV/batteria e condizioni applicabili;
- IP66;
- standby/night consumption: 16 W;
- current manual: Rapid switch mode <20 ms;
- Rapid switch richiede Fronius Backup Controller 63A;
- Verto Plus 25–33,3 kW può essere Parallel Backup coordinator.

Nota documentale:
- il datasheet pubblico precedente riporta ~11 s per la configurazione Full Backup standard;
- il manuale corrente riporta anche tabella standard <35 s e, separatamente, Rapid switch <20 ms;
- per P0 Carnia conta solo l'architettura esatta Rapid switch validata, non il valore standard.

Prezzi benchmark:
- Fronius shop Austria Verto 30.0 Plus: €7.182 osservati;
- retailer Italia GreenEconomy: €4.647,61 osservati;
- prezzi non installati; batteria, Backup Controller 63A, switchgear, meter, posa e commissioning separati.

Stato Carnia:
- **promosso da semplice comparison a candidato tecnico da RFQ rapido**;
- non ancora selezionato: verificare disponibilità/configurazione Backup Controller 63A per 30 kW in Italia, batteria compatibile, CEI/DSO, interfaccia EMS, black-start, PV topology e blackout SAT reale.

## 3. Metering

### Schneider PM5340

OEM Italia:
https://www.se.com/it/it/product/METSEPM5340/

- prezzo ufficiale osservato: €1.469;
- Ethernet / Modbus TCP/IP;
- Class 0.5S;
- harmonic measurement fino alla 31a.

### Schneider PM5341 MID

OEM Italia:
https://www.se.com/it/it/product/METSEPM5341/

- prezzo ufficiale osservato: €1.694;
- MID;
- Ethernet / Modbus;
- Class 0.5S.

Listino Schneider Italia 01/07/2026:
https://www.se.com/it/it/download/document/SE_Listino/

Stato:
- candidati per PCC/high-value metering;
- branch meter economici ancora da RFQ.

## 4. Irrigazione

### Grundfos CR 10-6 A-A-A-E-HQQE — 96500984

Benchmark retailer Italia:
https://www.tavolla.com/grundfos-96500984-cr-10-6-a-a-a-e-hqqe-pompa-centrifuga-verticale-multistadio-con-porte-di-aspirazione-e-scarico-sullo-stesso-livello-6-giranti/

Dati pubblicati:
- P2 2,2 kW;
- 3×220–240D / 380–415Y V;
- corrente nominale 8,00 / 4,60 A;
- start current 840–920% della nominale;
- cosφ 0,86–0,80;
- Q nominale 10 m³/h;
- H nominale 48,3 m;
- Hmax 61,2 m;
- prezzo €1.946,78 IVA 22% inclusa;
- lead time dichiarato ~3–5 settimane.

Stato:
- ottimo benchmark elettrico per EL-IRR-P1/P2;
- duty Q/H definitivo e comportamento con VFD restano da progetto/RFQ.

## 5. PDC

### Kensol KHP-R290-22-3

Current seller/market references:
https://www.senetic.de/product/KHP-R290-22-3
https://www.idealo.it/lista/122127157/pompa-di-calore-monoblocco-r290.html

Dati già verificati nel package termico:
- 380–415 V / 3N / 50 Hz;
- max input 9 kW;
- max current 15,8 A;
- A7/W35 electrical input 1,48–5,90 kW;
- A2/W35 1,45–5,50 kW;
- R290;
- 202 kg.

Prezzi:
- Senetic EU: €3.616,74 ex VAT osservati;
- Idealo Italia / senetic.it: €4.412,42 IVA compresa osservati;
- Italia installazione/garanzia/commissioning: RFQ.

Stato:
- EL-PDC-1/2/3: dato elettrico catalogo migliorato;
- restano A-7/A-10/A-15, defrost netto, curve reali, corrente/start behavior e assistenza Italia.

## 6. Deumidificazione

### DryGair DG-3 50 Hz — current OEM

https://drygair.com/dehumidifiers/dg-3-50hz/

- 3~, 400 V, 50 Hz;
- electricity consumption: 2,3 kW;
- I operating max: 14 A;
- water extraction: 11 L/h @18 °C, 80% RH;
- ~4.500 m³/h;
- operating 10–35 °C;
- prezzo: RFQ.

### DryGair DG-12 50 Hz Standard — current OEM

https://drygair.com/dehumidifiers/dg-12-50hz-standard/

- 3~, 400 V, 50 Hz;
- electricity consumption: 9,55 kW;
- I operating max: 30 A;
- water extraction: 43 L/h @18 °C, 80% RH;
- ~20.000 m³/h;
- operating 10–35 °C;
- prezzo: RFQ.

Nota:
- esiste ancora materiale pubblico della generazione precedente DG-12 con 12 kW / 48 L/h;
- per il registro corrente usare la pagina OEM nuova 9,55 kW / 43 L/h e chiedere in RFQ revisione/modello offerto.

## 7. Celle fredde — benchmark monoblocchi R290

### GGM KDC800N

https://www.ggmgastro.com/it-it-eur/unita-a-soffitto-refrigerante-tipo-monoblocco-tn-per-volumi-fino-a-50-0m3-grado-di-protezione-ip-20-per-it-kdc800n

- 400 V / 3N / 50 Hz;
- compressor power: 2,25 kW;
- current: 4,2 A;
- R290 0,15 kg;
- -5…+15 °C;
- 50 m³ @32 °C / 31,3 m³ @43 °C;
- Modbus + Bluetooth;
- prezzo netto osservato: €5.399,99;
- lead time: 5–6 settimane;
- unità senza cella.

### GGM KDC600N

https://www.ggmgastro.com/it-it-eur/unita-a-soffitto-refrigerante-tipo-monoblocco-tn-per-volumi-fino-a-35-1m3-grado-di-protezione-ip-20-kdc600n

- 400 V / 3N / 50 Hz;
- compressor power: 1,48 kW;
- current: 2,8 A;
- R290 0,15 kg;
- -5…+15 °C;
- 35,1 m³ @32 °C / 21 m³ @43 °C;
- Modbus + Bluetooth;
- prezzo netto osservato: €4.899,99;
- lead time: 5–6 settimane;
- unità senza cella.

Stato:
- questi dati chiudono meglio il benchmark elettrico EL-CR-A/B;
- non chiudono il load sizing frigorifero da kg prodotto / pull-down / estate.

## 8. Dati ancora realmente mancanti

P0:
- server/network/PLC real W/kVA/PF e ride-through;
- BESS auxiliary W normal/winter;
- security/fire/access circuits.

P1:
- fertigation total;
- greenhouse actuators/HAF subset;
- animal welfare;
- safety lighting;
- retail refrigeration.

Transitori:
- Grundfos con VFD scelto;
- cold-room LRA/start profile;
- PDC startup/inverter behavior;
- DryGair start profile.

Economia:
- BESS installed RFQ;
- Fronius rapid-switch topology installed RFQ;
- switchgear/critical bus;
- fire engineering;
- DSO/grid package;
- annual service/spares.

## 9. Azione successiva

Inviare RFQ comparabile a:
1. TESLA Group / integratore Italia;
2. Fronius partner Italia per Verto 30.0 Plus + storage + Rapid switch <20 ms;
3. almeno un terzo integratore C&I BESS AC-coupled;
4. fornitori di dominio per dati startup e installed cost.

Il risultato va riportato in `LOAD_DATA_CAPTURE_TEMPLATE.csv` e poi nel CAPEX consolidato.
