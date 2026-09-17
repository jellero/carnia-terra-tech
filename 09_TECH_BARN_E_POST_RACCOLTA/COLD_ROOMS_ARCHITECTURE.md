# Architettura celle frigorifere — BOM-024

**Aggiornato:** 17 settembre 2026  
**Stato:** WORKING ARCHITECTURE / DUE TEMPERATURE / CARICO PRODOTTO E RFQ BLOCCANTI.

## 1. Funzioni

1. rimuovere rapidamente il calore di campo quando necessario;
2. mantenere qualità, turgore e shelf-life;
3. separare prodotti incompatibili per temperatura/etilene;
4. bufferizzare raccolta e spedizione;
5. mantenere tracciabilità e cold chain;
6. funzionare localmente anche senza cloud.

## 2. Celle

### CR-A — COLD-LEAF

Working setpoint: **1–3 °C**, regolabile 0–5 °C.

Destinazione: C3/C4/C5 e altri prodotti compatibili.

Lattuga: vicino a 0 °C e RH >95% è il riferimento qualitativo; a 5 °C la shelf-life si riduce. Lattuga è inoltre sensibile all'etilene, altro motivo per separarla dal pomodoro.

### CR-B — COOL-SENSITIVE

Working setpoint: **10–12 °C**, regolabile circa 7–15 °C.

Destinazione: pomodoro, peperone, basilico, nursery/post-raccolta sensibile.

Non è una temperatura perfetta per tutti:
- peperone: optimum circa 7,5 °C, >95% RH;
- basilico: chilling sensitive, tenere sopra 10 °C;
- pomodoro: temperatura dipende dallo stadio; il prodotto firm-ripe è nell'ordine 10–12,5 °C, mature-green più alto.

La permanenza in CR-B è quindi breve e gestita per crop card.

## 3. Layout

Working scenario:

- 2 celle ~5×5 m di ordine di grandezza;
- 2,5–2,7 m interni;
- 25 m²/cella;
- 60–70 m³/cella;
- area filtro/packing davanti;
- porta utile >=1,2 m working, da validare su cassette/pallet/carrello;
- protezioni porte/pareti da urti.

Il benchmark pubblico più vicino censito è una cella 4,74×4,74×2,54 m senza gruppo a €6.775,99 + IVA. Non scalare linearmente a 5×5.

## 4. Pavimento

Preferenza: soletta del Tech Barn predisposta con:

- isolamento continuo;
- barriera vapore;
- resistenza ai carichi ruota;
- finitura food-grade antiscivolo;
- quota flush con packing;
- giunti igienici.

Un pavimento pannellato commerciale può avere limiti di carico ruota incompatibili con uno stoccatore. Verificare BOM-021: massa macchina + pallet + geometria ruote.

Condensa evaporatore scaricata a drenaggio controllato; evitare ristagni e pozzetti aperti non necessari dentro la cella.

## 5. Involucro

RFQ:

- 100 mm PIR/PUR baseline;
- lambda/U dichiarati;
- reazione al fuoco;
- facce interne lavabili e compatibili con detergenti;
- giunti sigillati;
- ponti termici;
- corner/coving;
- ceiling suspension/fixings;
- pressure relief se richiesto;
- riparabilità pannelli.

## 6. Porte

Per cella:

- porta scorrevole o battente isolata;
- clear opening da layout logistico;
- emergency release interna;
- auto-close dove utile;
- door contact;
- anti-impact;
- guarnizioni sostituibili;
- soglia flush;
- eventuale strip curtain/air curtain solo se igienicamente e logisticamente sensato.

## 7. Cooling load

Qtotal = Qtrans + Qinfil + Qproduct + Qresp + Qinternal + Qdefrost + margin.

Qproduct = m × cp × ΔT / t.

Esempi illustrativi con cp=3,8 kJ/kgK:

- 1.000 kg, 25 -> 2 °C, 6 h = ~4,05 kW;
- 500 kg, stesso profilo = ~2,02 kW;
- 1.000 kg, 25 -> 10 °C, 8 h = ~1,98 kW.

Sono esempi, non dati di dimensionamento.

Input obbligatori: kg/lotto, kg/giorno, T ingresso, T target, tempo target, packaging, respiration, aperture porta, ambienti adiacenti, Tamb estiva, persone, luci, ventilatori.

## 8. Precooling

UC Davis indica per lattughe vacuum/hydrovac/hydrocooling come metodi comuni; forced-air è possibile ma più lento e può aumentare perdita di acqua.

Baseline Carnia: predisporre un **forced-air precooling** semplice e modulare prima/dentro CR-A.

Elementi:
- plenum/telo;
- EC fans;
- cassette con aperture coerenti;
- Δp;
- product probe;
- timer/recipe;
- logging;
- condensa/drip management.

## 9. Gruppi frigoriferi

### Candidate class M — R290 monoblock

Benchmark GGM KDC800N:
- R290 0,15 kg;
- -5…+15 °C;
- max room 50 m³ dichiarati;
- compressor 2,25 kW;
- 400 V;
- €5.399,99 netto benchmark.

Per una working cell 60–70 m³ è un riferimento di costo, **non una taglia valida**.

KDC600N:
- max 35,1 m³ a 32 °C / 21 m³ a 43 °C;
- R290 0,15 kg;
- compressor 1,48 kW;
- €4.899,99 netto.

Possibile scenario 2× per cella da verificare con costruttore, load calculation e airflow; le capacità nominali non si sommano automaticamente come criterio di selezione.

### Candidate class S — remote/split low-GWP

Danfoss Optyma family:
- outdoor low-GWP A1/A2L;
- indoor R290;
- MBP/LBP;
- microchannel;
- sizing da software/OEM.

Prezzo: RFQ.

Vantaggi: condensatore esterno, maggiore libertà evaporatore e controllo RH. Svantaggi: installazione frigorista, linee e più variabili.

## 10. Ridondanza

CR-A è più critica.

RFQ deve confrontare:

- A1: 1×100%;
- A2: 2×~60% o simile, con sequenza lead/lag;
- A3: 1×100% + predisposizione rapida spare/rental.

Il criterio è capacità di **holding** dopo un guasto, non solamente capacità di pull-down.

## 11. Refrigerante e safety

Regolamento UE 2024/573:

- dal 1/1/2025 i self-contained refrigeration equipment con fluorinated GWP >=150 sono vietati salvo eccezioni safety;
- dal 1/1/2030 per altra stationary refrigeration il limite >=150 si estende, salvo safety exceptions.

R290 è preferito quando la configurazione e EN 378/risk assessment lo consentono. Per A2L, richiedere carica, classificazione area, leak detection/ventilation se necessarie e competenze installatore.

## 12. Monitoraggio e controllo

Primary controller OEM + supervisory PLC/edge.

Segnali:
- T room x2/3;
- T evaporator;
- RH;
- door;
- compressor/fan/defrost;
- alarm;
- energy;
- condensate/flood optional.

Independent logger:
- Testo 160 TH benchmark €180 + IVA/cella;
- oppure equivalente con history e alarm.

Controller benchmark:
- Carel IR33 ~€144–215 + IVA secondo versione;
- RS485 module ~€80,72 + IVA.

Non duplicare componenti se già integrati nel gruppo.

## 13. Commissioning

- leak/safety test;
- controller/sensor calibration;
- temperature mapping vuota;
- temperature mapping carica;
- door-open recovery;
- pull-down test con massa simulata/reale;
- defrost test;
- condensate test;
- alarm/UPS/network loss;
- failure of one circuit if modular;
- product core temperature;
- 72 h trend minimum;
- as-built + settings backup.

## 14. Gate

1. crop-card postharvest;
2. peak kg/day and lot;
3. incoming field temperature;
4. required pull-down time;
5. crate/pallet plan;
6. actual room dimensions;
7. insulated floor/wheel loads;
8. RH strategy;
9. precooling choice;
10. refrigeration architecture;
11. summer design ambient;
12. refrigerant/risk assessment;
13. electric/generator budget;
14. installed RFQ;
15. service SLA and spares;
16. HACCP and monitoring plan.
