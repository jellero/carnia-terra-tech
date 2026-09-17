# BOM-016 — Fertirrigazione e dosaggio A/B/acido

**Aggiornato:** 17 settembre 2026  
**Ambito:** acqua filtrata/pressurizzata -> dosaggio A/B/acido -> misura pH/EC/T -> distribuzione irrigua.  
**Stato:** `ARCHITETTURA DEFINITA / CANDIDATI REALI / TAGLIE DA RICETTE E ANALISI ACQUA`.

## 1. Distinta principale

| Codice | Voce | Quantità working | Stato | Benchmark / nota |
|---|---|---:|---|---|
| FRT-PMP-A | pompa dosatrice A | 1 | DA CALCOLO | eOne MF candidato |
| FRT-PMP-B | pompa dosatrice B | 1 | DA CALCOLO | eOne MF candidato |
| FRT-PMP-AC | pompa dosatrice acido | 1 | DA CALCOLO | eOne MF / Tekna APG candidato |
| FRT-PMP-4 | predisposizione quarto canale | 1 | PREDISPOSIZIONE | I/O, spazio, attacco |
| FRT-SUC-001 | lancia aspirazione | 3 | DA RFQ | materiali compatibili |
| FRT-SUC-002 | valvola/filtro fondo | 3 | REQUISITO | se non integrata nel kit |
| FRT-LVL-001 | livello basso A/B/acido | 3 | REQUISITO | interlock locale |
| FRT-TUB-001 | tubo aspirazione | 3 linee | DA DISTINTA | dedicato e marcato |
| FRT-TUB-002 | tubo mandata | 3 linee | DA DISTINTA | pressione/chimica |
| FRT-INJ-001 | valvola iniezione/check | 3 | REQUISITO | anti-sifone/backflow |
| FRT-BPV-001 | back-pressure valve | 0–3 | CONDIZIONALE | da curva/installazione |
| FRT-REL-001 | relief/sicurezza mandata | 0–3 | CONDIZIONALE | da OEM/P&ID |
| FRT-ISO-001 | valvole isolamento | per canale | REQUISITO | manutenzione |
| FRT-CAL-001 | colonna/cilindro calibrazione | 1–3 | PREFERENZA | verifica l/h reale |
| FRT-FVS-001 | flow verification dose | 0–3 | OPZIONE/PREFERENZA | se affidabile e TCO valido |
| FRT-INJMAN-001 | collettore/punti iniezione | 1 package | DA PROGETTO | evitare contatto concentrati |
| FRT-MIX-001 | static mixer/tratto miscelazione | 1+ | DA CALCOLO | Δp/tempo residenza |
| FRT-SMP-001 | cella campione pH/EC/T | 1 | REQUISITO | bypass isolabile |
| FRT-PH-TR-001 | trasmettitore pH | 1 | CANDIDATO | combinato o separato |
| FRT-PH-PRB-001 | sonda pH processo | 1 + eventuale spare | DA RFQ | PVDF/PTFE preferenziale |
| FRT-EC-TR-001 | trasmettitore EC | 1 | CANDIDATO | combinato o separato |
| FRT-EC-PRB-001 | sonda EC processo | 1 | DA RFQ | in-line, compensazione T |
| FRT-T-001 | misura temperatura soluzione | 1 | REQUISITO | integrata o separata |
| FRT-TR-CAN | Hanna HI98143-22 pH+EC | candidato | PREZZO TROVATO | €615 + IVA, sonde escluse |
| FRT-PH-CAN | Hanna HI8614LN | alternativa | PREZZO TROVATO | €670 + IVA benchmark UE |
| FRT-EC-CAN | Hanna HI8936 | alternativa | PREZZO TROVATO | da €327 + IVA; LCD ~€505 |
| FRT-EC-PROBE-CAN | Hanna HI7638 | benchmark | PREZZO TROVATO | ~€420–441 + IVA |
| FRT-PH-PROBE-CAN | process pH PVDF classe HI1006 | benchmark | PREZZO TROVATO | ~€400 + IVA |
| FRT-PORT-001 | pH/EC portatile indipendente | 1 | PREFERENZA | Hanna HI9814 €315 + IVA IT |
| FRT-BUF-4 | buffer pH 4.01 | scorta | CONSUMABILE | ~€36 + IVA benchmark |
| FRT-BUF-7 | buffer pH 7.01 | scorta | CONSUMABILE | ~€36 + IVA benchmark |
| FRT-STD-EC | standard EC | scorta | CONSUMABILE | ~€20 + IVA / 500 ml benchmark |
| FRT-SPILL-001 | leak/spill sensor | 1+ zone | REQUISITO | blocco dosaggio |
| FRT-BUND-001 | contenimento secondario | BOM-017 | OBBLIGATORIO | dimensionare su tank reali |
| FRT-ELC-001 | alimentazioni/protezioni | 1 package | DA RFQ | 230 Vac/24 Vdc secondo componenti |
| FRT-AI-001 | ingressi analogici pH/EC/T | 3+ | REQUISITO | PLC locale |
| FRT-AO-001 | uscite analogiche pompe | 3 | REQUISITO | 4–20 mA se scelto |
| FRT-DI-001 | ingressi stato/allarme/livello | da distinta | REQUISITO | hard interlock dove opportuno |
| FRT-COM-001 | calibrazione pompe | 1 lotto | OBBLIGATORIO | curva comando→l/h |
| FRT-COM-002 | calibrazione pH/EC | 1 lotto | OBBLIGATORIO | standard tracciabili |
| FRT-COM-003 | test interlock | 1 lotto | OBBLIGATORIO | no-flow, level, sensor fault, high EC |
| FRT-COM-004 | test ricette | C1–C6 | OBBLIGATORIO | dopo crop recipes |
| FRT-DOC-001 | P&ID/as-built/SDS/parametri | 1 lotto | OBBLIGATORIO | manutenzione e sicurezza |

## 2. Pompe candidate — prezzi

### Etatron eOne MF

Prezzi pubblici IVA esclusa osservati:

- 6/7: **€492**;
- 10/12: **€593**;
- 15/5: **€509**;
- 20/7: **€626**;
- 30/5: **€701**.

Caratteristiche rilevanti: 4–20 mA, flow sensor input, underload/overload, PTFE, PP/PVDF, ceramica, 100–250 Vac.

Benchmark tre canali:

- 2×20/7 + 1×6/7 = **€1.744 + IVA**;
- 2×30/5 + 1×6/7 = **€1.894 + IVA**.

`BENCHMARK / NON TAGLIA D'ORDINE`.

### SEKO Tekna EVO APG

APG 603 PVDF-T: **€329 IVA inclusa** presso retailer UE osservato; altro prezzo ~€288 nella variante/kit osservato.

Supporta 4–20 mA/digitale, PVDF, PTFE, IP65.

`PREZZO TROVATO / ALTERNATIVA ECONOMICA`.

### ProMinent gamma/X

Range famiglia circa 1 ml/h–45 l/h; materiali PP/PVDF/PTFE/inox e diagnostica avanzata.

`PREZZO DA PREVENTIVO / ALTERNATIVA PREMIUM`.

## 3. Dimensionamento

Per ogni canale:

`q_dose,max [l/h] = Q_water,max [m³/h] × recipe_stock [l/m³]`

Verificare anche q minimo stabile, non solo q massimo.

Una pompa da 20 l/h non è automaticamente sufficiente perché il limite dipende da:

- Q irrigazione simultanea;
- concentrazione stock;
- ricetta massima;
- pressione punto iniezione;
- viscosità/densità;
- margine operativo.

## 4. Misura pH/EC — benchmark

### Hanna HI98143-22

- 0–14 pH;
- 0–10 mS/cm;
- due segnali 4–20 mA isolati;
- 12–24 Vdc;
- IP54;
- **€615 + IVA**;
- sonde escluse.

### Soluzione separata

- HI8614LN pH transmitter: **€670 + IVA** benchmark;
- HI8936 EC transmitter: **da €327 + IVA**, LCD ~€505;
- HI7638 EC probe: **~€420–441 + IVA**;
- sonda pH processo PVDF classe HI1006: **~€400 + IVA**.

### Verifica indipendente

Hanna HI9814 portatile pH/EC/TDS/T: **€315 + IVA** Italia.

## 5. Logica di controllo

Baseline:

1. verifica flusso acqua;
2. attiva ricetta comparto/settore;
3. dosa A e B secondo feed-forward da portata e limiti ricetta;
4. misura EC dopo miscelazione/tempo trasporto;
5. trim lento EC entro limiti;
6. correzione pH con canale acido separato e limiti hard;
7. registra volumi A/B/acido e m³ acqua;
8. allarme se risposta processo non è coerente con comando.

Evitare controllo aggressivo solo su pH/EC istantanei: ritardo idraulico e mixing possono causare overshoot.

## 6. KPI

- L A / m³ acqua;
- L B / m³ acqua;
- L acido / m³ acqua;
- deviazione EC target/reale;
- deviazione pH target/reale;
- numero calibrazioni;
- drift sonda;
- ore/corse pompe;
- errori underload/overload;
- volume fertilizzante per kg vendibile futuro;
- costo fertilizzante/m³ e per kg vendibile.

## 7. Ricambi iniziali

Da finalizzare per modello:

- una testa/kit valvole o kit manutenzione per famiglia pompa;
- membrana se prevista come ricambio;
- valvole iniezione/check;
- tubo aspirazione/mandata;
- O-ring/tenute compatibili;
- elettrodo pH di scorta o lead time garantito;
- standard calibrazione;
- fusibili/alimentatore/relè necessari.

## 8. Gate

1. analisi acqua e alcalinità;
2. ricette C1–C6;
3. stock A/B definiti;
4. acido e concentrazione definiti;
5. Q acqua min/max;
6. q dose min/max;
7. pressione iniezione;
8. compatibilità materiali;
9. P&ID/mixing/cella misura;
10. serbatoi BOM-017;
11. interlock PLC;
12. RFQ e test commissioning.