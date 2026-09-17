# BOM-019 — Fotovoltaico, inverter e BOS elettrico

**Aggiornato:** 17 settembre 2026  
**Ambito:** generatore FV ~120 kWp DC -> inverter -> quadro AC/PCC, predisposizione 150–180 kWp.  
**Stato:** `CANDIDATI REALI E PREZZI / LAYOUT, STRINGHE E CONNESSIONE DA LOTTO+DSO`.

## 1. Distinta principale

| Codice | Voce | Quantità working | Stato | Benchmark / nota |
|---|---|---:|---|---|
| FV-MOD-001 | modulo Trina TSM-470NEG9R.28 | 256 | CANDIDATO | 470 W, 120,32 kWp totali |
| FV-MOD-SP | moduli spare | 0–5 | DA TCO | 1–2% da valutare |
| FV-STR-001 | struttura roof/carport/ground | 1 package | DA LOTTO/RFQ | no ombra colture principali |
| FV-STR-CALC | calcolo neve/vento/struttura | 1 | OBBLIGATORIO | sito reale |
| FV-FOUND | fondazioni/pali | da layout | CONDIZIONALE | ground/carport |
| FV-INV-A1 | Sungrow SG50CX-P2 | 2 | CANDIDATO I1 | 50 kVA, ~€1.899/cad benchmark UE |
| FV-INV-A2 | Huawei SUN2000-50KTL-M3 | 2 | CANDIDATO I1 | 50 kW, ~€2.379–2.399/cad benchmark UE |
| FV-INV-A3 | SMA Sunny Tripower X 50 | 2 | CANDIDATO I1 | ~€2.695/cad benchmark UE |
| FV-INV-B | SMA Sunny Tripower X 60 | 2 | CANDIDATO I2 | 60 kW, ~€2.865/cad benchmark UE |
| FV-INV-EXP | terzo inverter / spazio | 0–1 | PREDISPOSIZIONE | scenario 2×50 e crescita |
| FV-DC-CAB | cavo PV1-F | da layout | DA CALCOLO | sezione/caduta/posa |
| FV-DC-CON | connettori DC | per stringa | REQUISITO | stessa famiglia compatibile |
| FV-DC-ISO | sezionamento DC | da modello | REQUISITO | integrato/esterno |
| FV-DC-FUSE | fusibili stringa | 0–n | DA STRING DESIGN | non automatici per default |
| FV-DC-COMB | combiner box | 0–n | DA STRING DESIGN | solo se utile |
| FV-DC-SPD | SPD DC | da progetto | REQUISITO | T2 o T1+T2 da LPS/rischio |
| FV-AC-MCCB | interruttore inverter | 2–3 | REQUISITO | selettività/Icc |
| FV-AC-BUS | quadro raccolta AC | 1 | REQUISITO | predisposizione espansione |
| FV-AC-SPD | SPD AC | 1+ | REQUISITO | coordinato LPS |
| FV-AC-CAB | cavi AC | da layout | DA CALCOLO | portata/caduta/posa |
| FV-PCC-MTR | misura energia PCC | 1 | REQUISITO | import/export |
| FV-PROD-MTR | misura produzione | 1+ | REQUISITO | normativa/EMS |
| FV-SPI | sistema protezione interfaccia | 0–1 package | DA DSO/CEI | esterno se richiesto |
| FV-DDI | dispositivo interfaccia | 0–1 package | DA DSO/CEI | schema reale |
| FV-MT-001 | cabina/trasformatore MT | 0–1 | CONDIZIONALE | solo preventivo DSO |
| FV-GND | terra/equipotenziale | 1 package | REQUISITO | coordinare LPS |
| FV-MON | monitoraggio inverter | 1 package | REQUISITO | locale + remoto |
| FV-EMS | interfaccia EMS locale | 1 package | REQUISITO | Modbus/Ethernet preferito |
| FV-WTH | sensore irradianza/meteo | 0–1 package | PREFERENZA | PR/diagnostica |
| FV-LABEL | etichette/cartellonistica | 1 lotto | OBBLIGATORIO | DC/AC/emergenza |
| FV-SP-001 | connettori/fusibili/SPD spare | 1 lotto | PREFERENZA | standardizzare |
| FV-SP-002 | modulo spare | 0–5 | DA TCO | compatibilità futura |
| FV-COM-001 | test stringhe | 1 lotto | OBBLIGATORIO | Voc/Isc/isolamento/polarità |
| FV-COM-002 | test inverter | 2–3 | OBBLIGATORIO | firmware/protezioni |
| FV-COM-003 | test rete/PCC | 1 | OBBLIGATORIO | DSO/CEI |
| FV-DOC | as-built/string map/seriali | 1 lotto | OBBLIGATORIO | consegna proprietario |

## 2. Modulo candidato

Trina TSM-470NEG9R.28, documentazione 2026:

- 470 Wp;
- Vmp 46,1 V / Imp 10,20 A;
- Voc 54,6 V / Isc 10,89 A;
- 23,5% efficienza;
- 1762×1134×30 mm;
- 21 kg;
- coeff. Pmax -0,29%/°C;
- coeff. Voc -0,24%/°C;
- max system voltage 1500 Vdc;
- 25 A max fuse;
- 25 anni prodotto / 30 anni potenza nella scheda 2026.

### Working quantity

256 × 470 W = **120,32 kWp**.

- area modulo ~1,998 m²;
- area soli moduli ~**511,5 m²**;
- massa soli moduli ~**5.376 kg**.

### Prezzi trovati UE

- pallet business DE: ~**€68,90 netto/modulo**;
- palette/retail UE osservati ~€76,64–99/modulo a seconda di regime/mercato;
- 256 moduli => circa **€17.638–25.344** come range hardware pubblico osservato;
- equivalente ~**€147–211/kWp** di soli moduli.

`PREZZO TROVATO UE / TRASPORTO E TRATTAMENTO IVA ITALIA DA CONFERMARE`.

## 3. Inverter — scenari

### I1 — 2×50 kW AC

120,32/100 = **DC/AC 1,203**.

Sungrow SG50CX-P2:

- 50 kVA;
- 1.100 V max DC;
- IP66, C5;
- 98,5% max;
- ~**€1.899/cad** pubblico UE;
- 2 = ~**€3.798** hardware benchmark.

Huawei SUN2000-50KTL-M3:

- 50 kW nominali, 55 kW max cosφ=1;
- 4 MPPT / 8 inputs;
- 1.100 V max;
- 30 A/MPPT, 20 A/input;
- IP66;
- SPD T2 DC/AC, AFCI, RS485;
- ~**€2.379–2.399/cad**;
- 2 = ~**€4.758–4.798**.

SMA Sunny Tripower X 50:

- 50 kW;
- 5 MPPT, 2 stringhe/MPPT;
- max PV 75 kWp;
- 1.000 V max;
- benchmark ~**€2.695/cad**;
- 2 = ~**€5.390**.

### I2 — 2×60 kW AC

SMA Sunny Tripower X 60:

- 60 kW/cad;
- max PV 90 kWp/cad;
- 5 MPPT;
- 40 A/MPPT, 22 A/stringa;
- DC/AC fino al 150% dichiarato;
- 1.000 V max;
- benchmark ~**€2.865/cad**;
- 2 = ~**€5.730**.

120,32/120 = **DC/AC 1,003** iniziale.

## 4. String sizing

Non congelato. Deve essere verificato con Tmin sito e tolleranza modulo.

Esempio a -20 °C, solo illustrativo:

- Trina 470 Voc cold ~60,5 V;
- 18 moduli ~1.089 V: vicino al limite 1.100 V e richiede margini/tolleranze;
- 17 moduli ~1.028 V: non ammissibile su inverter max 1.000 V;
- 16 moduli ~968 V: classe più gestibile per inverter 1.000 V.

Quindi modulo/inverter/layout vanno progettati insieme.

## 5. Strutture e costo

Non esiste ancora quantità d'ordine.

Benchmark:

- piccoli kit K2 roof-mount lamiera grecata ~€29/modulo ex VAT nella configurazione osservata, circa €62/kWp a 470 W;
- benchmark factory ground-mount steel ~€16–22/kWp materia/fornitura bassa, **NON costo installato UE**.

Il vecchio input `moduli+struttura €200/kWp` è `DA VERIFICARE`: con i moduli da soli oggi ~€147–211/kWp, può funzionare soltanto con procurement favorevole e struttura semplice/economica; non è baseline prudente per ground mount/carport.

## 6. Connessione

Stato: `DA PREVENTIVO DSO`.

- CEI 0-21:2026 per BT;
- CEI 0-16:2026 per MT/AT;
- TICA ARERA;
- eventuale CCI/A.72 e altri requisiti per >=100 kW in MT da verificare sul preventivo;
- eventuale protezione di interfaccia esterna, trasformatore e cabina sono costi separati.

## 7. Sicurezza antincendio

Se installato su edificio/attività soggetta al DPR 151/2011, applicare Linee Guida VVF fotovoltaico aggiornate con Nota 14030/2025 e chiarimenti. Costo eventuali compartimentazioni, distanze, sezionamenti e modifiche copertura: `DA PROGETTO`.

## 8. OPEX/manutenzione

Prevedere:

- ispezione annuale e termografia secondo piano;
- controllo serraggi/connessioni;
- pulizia su performance, non calendario cieco;
- verifica SPD;
- vegetazione/ombra per ground mount;
- aggiornamenti firmware controllati;
- backup configurazioni;
- string map e baseline elettrica.

## 9. Gate

1. masterplan e superfici reali;
2. neve/vento e struttura;
3. Tmin/Tmax sito;
4. profilo carichi 15 min e annuale;
5. PVGIS/producibilità;
6. DSO: BT/MT e potenza immissione;
7. 2×50 vs 2×60;
8. string design;
9. strutture/fondazioni;
10. protezioni e antincendio;
11. offerte comparabili;
12. CAPEX installato ±10–15%;
13. commissioning.