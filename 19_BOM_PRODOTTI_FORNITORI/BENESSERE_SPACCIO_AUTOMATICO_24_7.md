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
| SH-VEND-FASPRO | FAS Pro 900 class | 0–1 | ALTERNATIVA | €8.840 net benchmark listing; payment incluso nel listing NON baseline e da escludere/sostituire |
| SH-VEND-EASY | FAS Easy Food | 0–1 | ALTERNATIVA LOCKER | RFQ |
| SH-VEND-OUT | FAS Skudo outdoor class | 0–1 | OUTDOOR CANDIDATE | RFQ |
| SH-PAY-UX700 | Verifone UX700 via Stripe Terminal | 1 per punto unattended | CANDIDATO STRIPE | RFQ Stripe Sales; hardware unattended ufficiale |
| SH-PAY-STRIPE | Stripe Terminal processing | per transazione | OPEX | Italia: 1,4% + €0,10 carte SEE; 2,9% + €0,10 non-SEE benchmark corrente |
| SH-PAY-INTEG | integrazione server Stripe PaymentIntent/webhook/refund | 1 | INTERNAL DEVELOPMENT | software Carnia TerraTech |
| SH-PAY-REC | reconciliation payment-vend-fiscal | 1 | INTERNAL DEVELOPMENT | server centrale |
| SH-FISCAL | fiscal interface/service | 1 | OBBLIGATORIO | RFQ |
| SH-VEND-API | API/protocol adapter vending -> server centrale | 1 per modello | BASELINE | RFQ/in-house adapter |
| SH-SERVER | central orchestration server integration | 1 | BASELINE | INTERNAL / shared platform |
| SH-FORECAST | demand/supply forecast + refill scheduler | 1 | BASELINE | INTERNAL DEVELOPMENT |
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
| SH-BESS | interfaccia BESS aziendale 30 kW + load shedding | 1 | INTERFACE | shared energy system; kWh/autonomia DA VERIFICARE |
| SH-BACKUP-CTRL | power-fail / backup-state integration server | 1 | BASELINE | INTERNAL / electrical interface |
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

## 10. Payment — Stripe Terminal

Stripe è il payment processor scelto per BOM-028.

### Ambiente unattended

La documentazione Stripe corrente indica **Verifone UX700** come device Terminal dedicato agli ambienti retail non presidiati/vending.

Caratteristiche pubblicate:

- EMV chip;
- contactless e wallet;
- Ethernet/Wi-Fi;
- IP65;
- IK08;
- operating range pubblicato -30 °C…70 °C;
- server-driven integration;
- disponibilità Italia nella matrice Stripe corrente;
- offline mode come capability del device.

Prezzo UX700:
- **RFQ / Stripe Sales**.

### Fee Stripe Italia — benchmark corrente

Stripe pubblica per Terminal:

- carte SEE: **1,4% + €0,10** per pagamento riuscito;
- carte non SEE: **2,9% + €0,10**.

Le condizioni effettive dipendono dal contratto e vanno aggiornate nel TCO.

### Architettura

Il server Carnia TerraTech gestisce:

- order;
- inventory reservation;
- PaymentIntent;
- webhook;
- vend authorization;
- vend_ack;
- refund;
- reconciliation.

Non si paga un canone inventory/payment vendor separato se non serve a una funzione tecnica specifica.

Il cloud vending, se presente, resta diagnostico e non diventa system of record.

## 11. Server centrale — software operativo

La piattaforma software è sviluppata internamente.

Il server centrale coordina:

- produzione;
- raccolta;
- celle;
- stock;
- personale;
- logistica;
- AMR;
- vending;
- Stripe;
- manutenzione;
- energia;
- refill;
- demand forecasting;
- supply forecasting.

Per BOM-028 il software non viene trattato come SaaS esterno.

Costi da contabilizzare, se rilevanti:

- server/compute condiviso;
- storage;
- backup;
- connettività;
- eventuali servizi cloud scelti;
- tempo di sviluppo/manutenzione;
- monitoraggio.

Architettura di riferimento:
`07_AUTOMAZIONE_DATI_AI/CENTRAL_ORCHESTRATION_SERVER.md`.

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
- alimentazione su BESS aziendale;
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

## 15. Elettrico e continuità BESS

### Vending

Dimensionare da:

- potenza nominale;
- spunto;
- temperatura ambiente;
- duty cycle;
- energia giornaliera.

### Continuità

**Nessuna UPS locale nella baseline.**

Lo spaccio usa il BESS aziendale con **30 kW di potenza** disponibile come architettura di backup condivisa.

Da chiudere nel package energia:

- kWh utili;
- autonomia;
- potenza continua/picco;
- islanding;
- transfer time;
- SOC reserve;
- load shedding.

Il server centrale deve ricevere almeno:

- grid_available;
- bess_online;
- SOC;
- backup_mode;
- low_SOC;
- available_power.

Priorità working:

- P0 server/rete/controller/payment;
- P1 vending refrigerato/logger;
- P2 CCTV/illuminazione;
- P3 carichi differibili.

Se il freddo non può essere mantenuto:
- stop-vend;
- allarme;
- procedura HACCP.

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

- Stripe fees;
- compute/storage/connettività server;
- eventuali servizi cloud non-core;
- protocol/API support vendor;
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

`TCO_5y = CAPEX + 5×fixed_opex + Stripe_transaction_fees + energy + maintenance + waste + software_operations`.

## 19. Gate di acquisto

Nessun ordine vending prima di:

1. regime SUAP;
2. HACCP;
3. SKU matrix;
4. shelf-life;
5. temperature;
6. pack dimensions;
7. pilot sample;
8. Stripe Terminal TCO;
9. fiscal architecture + collegamento Stripe/RT ove applicabile;
10. RFQ Italia;
11. support/SLA;
12. electrical + BESS 30 kW / autonomia;
13. network/security;
14. CCTV/privacy;
15. 5-year TCO.
