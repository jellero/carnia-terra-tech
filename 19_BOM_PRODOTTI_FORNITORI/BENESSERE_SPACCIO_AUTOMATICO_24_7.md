# BOM-028 — Spaccio automatico self-service 24/7

**Aggiornato:** 18 settembre 2026  
**Ambito:** vendita automatica prodotti aziendali + refrigerazione + payment + fiscal + CCTV + rete.  
**Stato:** `ARCHITETTURA STRUTTURATA / REGIME SUAP, SKU E TEMPERATURE DA VALIDARE / VENDING E PAYMENT DA RFQ / BENCHMARK UNITARI DISPONIBILI`.

## 1. Regola di lettura

La BOM separa:

- infrastruttura;
- macchina vending;
- pagamento;
- fiscalità;
- temperature;
- sicurezza;
- software;
- OPEX.

Non viene scelto il distributore prima del test con i packaging reali BOM-025.

Stati:

- `BASELINE`;
- `CANDIDATO`;
- `ALTERNATIVA`;
- `OPTIONAL`;
- `INTERFACE`;
- `RFQ`;
- `DA SKU`;
- `DA SUAP`.

Prezzi osservati il 18 settembre 2026, salvo indicazione.

## 2. Distinta pezzo per pezzo

| Codice | Voce | Q.tà working | Stato | Benchmark |
|---|---|---:|---|---:|
| SH-LEGAL | verifica regime vendita diretta agricola / vending | 1 | OBBLIGATORIO | consulenza/SUAP |
| SH-COMM | comunicazione vendita diretta agricola, se applicabile | 1 | DA SUAP | costo pratica da verificare |
| SH-SCIA | SCIA vending retail, se applicabile | 0–1 | CONDITIONAL | costo comunale da verificare |
| SH-NIA | notifica impresa alimentare / variazione | 1 | OBBLIGATORIO IF FOOD | tariffa sanitaria nazionale FVG €20 reference |
| SH-HACCP | aggiornamento autocontrollo spaccio | 1 | OBBLIGATORIO | interno/consulenza |
| SH-KIOSK | locale/kiosk protetto | 1 | BASELINE | RFQ |
| SH-KIOSK-HVAC | ventilazione/HVAC kiosk, se richiesto | 0–1 | CONDITIONAL | RFQ |
| SH-VEND-G8 | Necta Gusto 8 / Food | 0–1 | CANDIDATO | ~€5.900 benchmark EU seller, regime IVA da verificare |
| SH-VEND-G8L | Necta Gusto 8 Lift | 0–1 | CANDIDATO PRIORITARIO FRAGILI | ~€7.200 benchmark EU seller, regime IVA da verificare |
| SH-VEND-DRUM | Necta Gusto Drum | 0–1 | ALTERNATIVA | ~€10.600–13.199 benchmark EU |
| SH-VEND-FASPRO | FAS Pro 900 class | 0–1 | ALTERNATIVA | €8.840 net benchmark listing incl. Nayax, options da verificare |
| SH-VEND-EASY | FAS Easy Food | 0–1 | ALTERNATIVA LOCKER | RFQ |
| SH-VEND-OUT | FAS Skudo outdoor class | 0–1 | OUTDOOR CANDIDATE | RFQ |
| SH-PAY-NAYAX | Nayax VPOS Touch | 1 per machine | CANDIDATO | €430 hardware official EU benchmark |
| SH-PAY-SVC | Nayax operations/payment service | 1 per terminal | OPEX | €15,75/mese official benchmark |
| SH-PAY-FEE | processing cashless | per transazione | OPEX | 1,45–3,5% official benchmark by ticket band |
| SH-PAY-POS | SumUp Terminal retail | 0–1 | BENCHMARK NON-VENDING | €139 promo / €169,58 IVA incl. observed |
| SH-FISCAL | fiscal interface/service | 1 | OBBLIGATORIO | RFQ |
| SH-TELEM | telemetry/inventory cloud | 1 | BASELINE | vendor RFQ/canone |
| SH-TLOG | Testo 160 T temperature logger | 1 per zona critica | CANDIDATO | €124 net / €151,28 incl. IVA |
| SH-TLOG-FOOD | Testo 162 food-capable class | 0–1+ | HIGHER-GRADE | RFQ |
| SH-TLOG-SP | spare independent logger | 1 | SPARE | RFQ |
| SH-ROUTER | router/firewall | 1 | BASELINE | existing/IT RFQ |
| SH-4G | 4G failover/SIM | 0–1 | CANDIDATO | RFQ |
| SH-SWITCH | managed PoE switch | 1 | BASELINE | existing/IT RFQ |
| SH-CAM | Ubiquiti G5 Turret Ultra | 1–2 | CANDIDATO | €80/cad EU Store benchmark |
| SH-CAM-JB | camera junction/arm mount | DA LAYOUT | OPTIONAL | €45 class official benchmark |
| SH-NVR | local NVR/storage | 1 | BASELINE | existing/RFQ |
| SH-CCTV-SIGN | privacy CCTV sign | ingressi | OBBLIGATORIO IF CCTV | stampa/RFQ |
| SH-UPS-IT | UPS electronics/network/NVR | 1 | BASELINE | RFQ from load/runtime |
| SH-BACKUP | generator/EMS refrigeration interface | 1 | INTERFACE | BOM energy/continuity |
| SH-ENERGY | submeter vending | 1 | CANDIDATO | RFQ |
| SH-LIGHT | kiosk/customer lighting | DA LAYOUT | BASELINE | RFQ / existing BOM refs |
| SH-SIGN | insegna / instructions / contacts | 1 set | BASELINE | RFQ |
| SH-REFUND | QR/refund/support label | 1 per machine | BASELINE | internal |
| SH-BIN | customer waste bin | 1 | BASELINE | RFQ |
| SH-CLEAN | cleaning kit | 1 | BASELINE | RFQ |
| SH-SP-MOTOR | vending motor/drive spare | 1–2 | SPARE | RFQ |
| SH-SP-SENSOR | vending sensor spare | 1 lot | SPARE | RFQ |
| SH-SP-LOCK | lock/key spare | 1 | SPARE | RFQ |
| SH-SP-FAN | fan/filter spare | 1 lot | SPARE | RFQ |
| SH-SP-PAY | payment cable/spare path | 1 | SPARE | RFQ |
| SH-SP-NET | Ethernet surge protector | 1 | SPARE | €12 Ubiquiti benchmark if selected |
| SH-COM | commissioning + 500-cycle acceptance | 1 | OBBLIGATORIO | RFQ |
| SH-SLA | annual service | 1 | OPEX | RFQ |

## 3. Regime vendita — baseline economica

### R1 — produttore agricolo

Il SUAP FVG include i distributori automatici tra le modalità della vendita diretta di prodotti agricoli.

Il D.Lgs. 228/2001 permette la vendita di:

- prodotti aziendali;
- prodotti agricoli/alimentari acquistati direttamente da altri imprenditori agricoli;

purché siano rispettati i requisiti di prevalenza previsti.

**Working baseline:** costruire lo spaccio prima di tutto come canale di vendita diretta agricola.

### R2 — vending retail

Se l'assortimento o la configurazione non rientra in R1:

- applicare la procedura vending retail;
- SCIA;
- requisiti soggettivi/professionali applicabili;
- food notification;
- altri procedimenti collegati.

Nessun costo beneficio del regime R1 viene dato per acquisito prima della verifica SUAP.

## 4. Notifica sanitaria

Il portale FVG indica una tariffa nazionale di **€20** per nuova sede operativa NIA o variazione VIA a partire dal 2022.

Usare come benchmark amministrativo.

Non include:
- consulenza;
- planimetrie;
- HACCP;
- pratiche commerciali;
- opere.

## 5. Necta Gusto 8

Specifiche OEM osservate:

- fino a 44 selezioni;
- ~900 mm larghezza;
- ~270–300 kg;
- MDB/Executive;
- R290;
- versione Food;
- capacità fino a 360 prodotti;
- 500 W nominali versione Food;
- layout catalogo con 0–3 °C, 5–7 °C, 8–12 °C;
- classe energetica C dichiarata.

Benchmark di mercato EU 2026:
- Gusto 8: **€5.900** prezzo visualizzato presso seller europeo;
- altro prezzo/listino visualizzato circa €7.411 prima di sconto.

**Non ancora RFQ Italia.**

## 6. Necta Gusto 8 Lift

Specifiche OEM:

- SoftVend elevator;
- dichiarato per prodotti fragili;
- fino a 40 selezioni;
- fino a 240 prodotti;
- ~280 kg;
- ~900 mm larghezza;
- R290;
- Food 0–4 °C;
- 220 W nominali nella configurazione tecnica visualizzata.

Benchmark EU 2026:
- **€7.200** prezzo visualizzato presso seller europeo;
- prezzo non include automaticamente delivery, payment, install, fiscal.

**Working preference:** testare questa classe prima della spirale standard per tomato/premium packs.

## 7. Necta Gusto Drum

OEM:

- 24/7;
- tamburi;
- FIFO;
- expiry management;
- Food 0–4 °C;
- fino a 360 prodotti;
- 360 W nominali;
- R290.

Benchmark:
- **€10.600** prezzo visualizzato seller EU;
- **€13.199** altro benchmark retail EU.

Il costo maggiore può essere giustificato solo se:
- fragilità;
- FIFO;
- capacità;
- zero-drop;
- format dei pack;

producono reale vantaggio.

## 8. FAS Pro / outdoor

Benchmark corrente listing 2026 FAS Pro 900:

- acquisto **€8.840 net**;
- listing comprende Nayax VPOS Touch;
- Wi-Fi/BLE;
- FAS Cloud+/IoT Vend;
- configurazione/options da verificare.

Non usare il listing come RFQ Italia definitivo.

FAS nel 2026 presenta la nuova Skudo come riprogettata per installazioni outdoor, con copertura protettiva opzionale per standalone outdoor.

**Gate outdoor:** ottenere specifica tecnica, temperatura ambiente, IP/IK, neve/acqua/sole e garanzia scritte.

## 9. FAS Easy Food

OEM:

- locker/dischi fresh-food;
- 8 dischi;
- 4/6/8/12/16/24/48 compartimenti per disco;
- display 10";
- 1830×910×790 mm;
- 323 kg;
- 450 W nominali;
- temperatura minima interna +3 °C;
- sicurezza frigo;
- CO2 refrigerante;
- cloud;
- QR.

Prezzo: **RFQ**.

Potenzialmente adatto a:
- prodotti delicati;
- click&collect;
- ordini preparati;
- pack grandi.

## 10. Payment — Nayax

Official EU shop benchmark:

- VPOS Touch hardware: **€430**;
- cashless/operations/inventory: **€15,75/mese**;
- processing indicato:
  - fino a €1,99: 3,5%;
  - €2–4,99: 3%;
  - €5–10: 1,8%;
  - oltre €10: 1,45%.

Le condizioni possono differire per paese/contratto.

### Impatto ticket

Su ticket piccoli la fee percentuale è materiale.

Il business case deve quindi modellare:
- ASP;
- basket;
- min price;
- multivend;
- pack bundle.

Non scegliere il payment provider solo dal costo hardware.

## 11. SumUp Terminal — benchmark

Prezzo osservato Italia:
- promo **€139**;
- **€169,58 IVA inclusa** prezzo indicato;
- Wi-Fi + 4G;
- stampante integrata;
- no canone hardware dichiarato nella pagina.

Non è baseline per vending MDB.

Serve come:
- benchmark costo POS;
- fallback operatore;
- pop-up/mercato;
- eventuale desk manuale futuro.

## 12. Temperature logger

Testo 160 T:

- **€124 net**;
- **€151,28 IVA incl.**;
- Wi-Fi;
- 32.000 valori;
- battery ~1,5 anni;
- allarmi cloud/app;
- cloud/licenze da verificare.

Per food-critical deployment preferire in RFQ un sistema/sonda adatto alla validazione HACCP.

Logger vending e logger indipendente devono essere due sorgenti distinte.

## 13. CCTV

Ubiquiti G5 Turret Ultra official EU:

- **€80/cad** benchmark;
- 2K;
- PoE;
- weatherproof;
- tamper-resistant.

Mount/junction:
- circa **€45** per alcune opzioni ufficiali.

Costi aggiuntivi:
- NVR;
- HDD;
- switch PoE;
- UPS;
- cablaggio;
- cartelli;
- progettazione privacy;
- installazione.

## 14. Fiscalità vending

Non viene attribuito un prezzo fittizio.

Richiedere a vendor:
- hardware fiscale;
- attivazione;
- canone;
- censimento;
- SIM/dati;
- aggiornamenti;
- assistenza;
- commercialista export.

Costo finale `SH-FISCAL = RFQ`.

## 15. Elettrico e backup

### Vending

Dimensionare da:
- nominale;
- spunto;
- temperatura ambiente;
- duty cycle.

### UPS

UPS dedicata solo a:
- IT;
- NVR;
- networking;
- telemetry;
- payment.

Dimensionamento:
`VA/W = measured electronics load × runtime target × engineering margin`.

### Refrigerazione

Backup:
- generator/EMS interface;
- non UPS desktop.

## 16. Packaging vending

Per ogni SKU registrare:

| Campo | Necessario |
|---|---|
| L×W×H | sì |
| peso | sì |
| rigidità | sì |
| venting | se applicabile |
| condensation | test |
| drop damage | test |
| spiral pitch | se spirale |
| elevator | se Lift |
| drum compartment | se Drum |
| barcode/QR | sì |
| label visible | sì |
| shelf life | sì |
| vending temp | sì |

## 17. Pilot minimo

### Phase P1 — lab
- 100 erogazioni/SKU critico.

### Phase P2 — unattended
- 500 vendite miste;
- almeno 7 giorni;
- power/network fault simulation;
- refund;
- temp alarms;
- replenishment;
- stock audit.

### Acceptance KPI
- vend success >=99%;
- refund workflow 100% tested;
- no unhandled temperature fault;
- inventory variance target <2% after reconciliation;
- zero access OT from guest/vending networks;
- no privacy blind spot/overreach found in field review.

I target sono acceptance criteria di progetto, non dati di vendor.

## 18. OPEX 5 anni

Obbligatorio calcolare:

- payment fees;
- SaaS;
- SIM;
- telemetry;
- fiscal service;
- cloud logger;
- maintenance;
- refrigeration;
- energy;
- cleaning;
- camera/NVR;
- replacements;
- waste;
- insurance;
- refund leakage.

Formula:

`TCO_5y = CAPEX + 5×fixed_opex + variable_payment_fees + energy + maintenance + waste`.

## 19. Gate di acquisto

Nessun ordine vending prima di:

1. regime SUAP;
2. HACCP;
3. SKU matrix;
4. shelf-life;
5. temperature;
6. pack dimensions;
7. pilot sample;
8. payment TCO;
9. fiscal architecture;
10. RFQ Italia;
11. support/SLA;
12. electrical;
13. network/security;
14. CCTV/privacy;
15. 5-year TCO.
