# Fonti — BOM-034 EMS, BESS e connessione elettrica

**Aggiornato:** 18 settembre 2026

## 1. Regola fonti

Priorità:

1. CEI / ARERA / Terna / GSE / VVF;
2. DSO reale del POD;
3. OEM BESS/PCS/switchgear/meters;
4. distributori solo per benchmark prezzo;
5. RFQ installato finale.

## 2. CEI 0-21:2026-07

CEI documenti gratuiti:
https://www.ceinorme.it/documenti-gratuiti/norme-cei-0-16-e-0-21/

Catalogo:
https://mycatalogo.ceinorme.it/cei/item/0000026363?sso=y

Dati correnti:
- pubblicazione 2026-07;
- validità da 2026-08;
- utenti attivi/passivi connessi in BT;
- edizione consolidata con aggiornamenti SLI.

Uso BOM:
- connessione BT;
- eventuale export limitation;
- protezioni/interfaccia;
- storage/PV topology.

## 3. CEI 0-16:2026-07

Catalogo:
https://mycatalogo.ceinorme.it/cei/item/0000026362?sso=y

Dati:
- pubblicazione 2026-07;
- validità da 2026-08;
- utenti attivi/passivi AT/MT;
- rimando CEI 57-142 per interfacce CCI/IEC 61850.

Uso:
- MT if DSO requires;
- CCI/protections.

## 4. ARERA TICA

Current TICA page:
https://www.arera.it/atti-e-provvedimenti/dettaglio/08/099-08arg

Use:
- active connection process;
- final DSO connection requirements;
- do not assume BT or MT before quote.

## 5. ARERA CCI/PF2

Delibera 385/2025/R/eel:
https://www.arera.it/atti-e-provvedimenti/dettaglio/25/385-25

Delibera 564/2025/R/eel:
https://www.arera.it/atti-e-provvedimenti/dettaglio/25/564-25

CEI modification communication:
https://www.arera.it/en/comunicati-operatore/dettaglio/modifiche-norma-cei-0-16-appr-cei-attuazione-delib-3852025reel-25

Points:
- extension of CCI to wind/PV >=100 kW in relevant MT cases;
- PF2 active power limitation mandatory under current framework for applicable plants;
- current timelines distinguish existing/new plants.

## 6. Terna Allegato A.72 Rev.03 — January 2026

https://download.terna.it/terna/Allegato_A.72_8ddd5a25c22a644.pdf

Relevant current provision:
- for new wind/PV connected to MT in class >=100 kW and <500 kW, PF2 via CCI is required from entry into service under the current framework;
- CCI may use category-specific simplifications.

Use:
- BOM-019 ~120.32 kWp plus final connection scenario;
- only if final legal/technical applicability is confirmed.

## 7. GSE — storage registration/technical rules

FAQ storage communication:
https://assistenza.clienti.gse.it/csm/it?id=faq&sys_id=188542fcdba510d4ee7cd127489619fe

Points:
- storage systems are represented in GAUDI/technical process;
- GSE technical rules reference CEI-permitted configurations.

Use:
- registration/document workflow where applicable;
- final integrator/DSO/GSE process must use current rules at commissioning.

## 8. VVF — FV + BESS fire risk

Coordinated FV guideline / Note 01-09-2025 n.14030:
https://www.vigilfuoco.it/sites/default/files/2025-09/COORD_NOTA_01_09_2025_n_14030_linee_guida_FV.pdf

Relevant points:
- Li-ion BESS can present fire/explosion risk associated with thermal runaway;
- where storage is associated with PV, specific fire/explosion risk assessment is required;
- the document points to DCPREV 21021 of 23/12/2024 as useful BESS fire-safety reference.

## 9. DCPREV 21021 / 23-12-2024 BESS

Reference copy:
https://cfpa-e.eu/app/uploads/2025/01/Linea-Guida-BESS-23-12-2024.pdf

Subject:
- fire prevention risk analysis and safety measures for BESS.

Use:
- location;
- separation;
- detection/protection;
- emergency access;
- system-specific fire engineering.

Final design by fire professional on selected BESS/site.

## 10. TESLA Group STILLA

https://teslagroup.eu/our-products/stilla/

Current public data:
- C&I storage;
- 30–60 kW;
- 61–122 kWh;
- LFP;
- up to 0.5C;
- 400 V;
- peak efficiency 97.3%;
- Modbus TCP;
- >12 year lifetime statement on current product page;
- RFQ pricing.

Use:
- technical candidate class for 30 kW / ~60 kWh scenario.

Open:
- Italy CEI/DSO conformity exact configuration;
- island/black-start/transfer;
- service/warranty/fire design.

## 11. Fronius Verto Plus

Italy C&I page:
https://www.fronius.com/it-it/italy/energia-solare/commerciale/prodotti-e-soluzioni/fronius-verto-verto-plus-massima-flessibilit-massima-sicurezza

Manual:
https://manuals.fronius.com/html/4204260552/it.html

Datasheet:
https://www.fronius.com/~/downloads/Solar%20Energy/Datasheets/SE_DS_Fronius_Verto_Plus_EN.pdf

Current public points:
- hybrid C&I inverter up to 33.3 kW;
- Verto 30.0 Plus nominal output 29.99 kW;
- Full Backup nominal 29.99 kW;
- Backup Power Boost up to 50 kVA for 5–10 s when source/battery/environment allow;
- battery operation;
- current manual documents **Rapid switch mode <20 ms**;
- Rapid switch requires a **Fronius Backup Controller 63A**;
- Verto Plus 25–33.3 kW is listed as eligible Parallel Backup coordinator;
- standard public documents are not uniform: older datasheet ~11 s, current manual standard table <35 s, while Rapid switch is a separate <20 ms mode.

Price benchmarks observed 18/09/2026:
- Fronius Austria shop Verto 30.0 Plus: €7,182;
- Italy retailer GreenEconomy: €4,647.61;
- neither is installed-system CAPEX.

Use:
- promote to **technical RFQ candidate** for Carnia P0 because current OEM Rapid switch mode is potentially compatible with no-reboot intent;
- exact 30 kW + Backup Controller 63A availability/topology, Italy support, compatible battery, CEI/DSO and blackout SAT remain mandatory;
- do not use standard ~11 s/<35 s mode for P0 no-reboot.

## 12. EcoFlow PowerOcean Plus — transfer benchmark

https://energy.ecoflow.com/it/products/PowerOcean-Plus

Public statement:
- up to 29.9 kW three-phase backup;
- 20 ms switching.

Use:
- transfer-time technology benchmark;
- not selected as C&I plant baseline.

## 13. Socomec ATyS

2026 manual example:
https://emea.socomec.com/sites/default/files/2026-02/ATyS-g-M---Automatic-Transfer-Switching-_INSTALLATION-AND-OPERATING-MANUAL_2026-02-06-14-23-24_542933E_English_PLURI.pdf

Point:
- open-transition automatic transfer equipment;
- useful for grid/alternate source switching;
- mechanical ATSE interruption alone does not prove P0 no-reboot.

## 14. Socomec STATYS

https://emea.socomec.com/en/solutions/business/data-centres/data-centre-redundancy

Point:
- static transfer system moves sensitive load between healthy live sources in a few milliseconds;
- appropriate concept for critical loads when two valid live sources exist.

Use:
- optional architecture reference;
- not a substitute for grid-forming BESS.

## 15. Schneider PowerLogic PM5000

Range:
https://www.se.com/it/it/product-range/61281-powerlogic-pm5000/

PM5110:
https://www.se.com/it/it/product/METSEPM5110/pm5110-power-meter-96x96-fino-a-15a-h-1OUT-modbus/

Observed official IT list:
- PM5110: €700;
- Class 0.5S;
- Modbus RS485.

PM5340:
https://www.se.com/it/it/product/METSEPM5340/pm5340-power-meter-96x96-fino-a-31a-h-2IN-2OUT%2B2rel%C3%A8-modbus%2Bethernet/

Observed:
- €1,469;
- Ethernet Modbus TCP/IP;
- Class 0.5S;
- harmonic measurement.

PM5341:
https://www.se.com/it/it/product/METSEPM5341/pm5341-power-meter-96x96-fino-a-31a-h-2IN-2OUT%2B2rel%C3%A8-modbus%2Bethernet-mid/

Observed:
- €1,694;
- MID;
- Ethernet/Modbus.

Prices are vendor list references and not installed RFQ.

## 16. Existing project load references

Repository sources:
- BOM-015 irrigation pump candidate: 2.2 kW;
- BOM-011 heat pump: max declared electrical 9 kW/unit;
- 3 modules = up to 27 kW; 4 = 36 kW;
- BOM-012 DG-3 2.3 kW / DG-12 9.55 kW;
- BOM-024 cold-room compressor references 1.48 and 2.25 kW plus auxiliaries.

Use:
- demonstrate need for load priority;
- not final demand study.

## 17. BESS sizing formula

`E_useful_EOL = E_nominal × usable_DoD × guaranteed_SoH × availability_margin`.

Required quote:
- nameplate;
- usable BOL;
- usable EOL;
- reserve behavior;
- winter derating.

## 18. EMS design rule

Custom Carnia server may optimize:
- tariff;
- PV;
- forecast;
- tasks;
- SOC target.

But:
- DSO/protection;
- BMS;
- PCS safety;
- island power controller;

remain autonomous/local.

## 19. Update rule

At final RFQ/commissioning record:

1. DSO/POD;
2. BT/MT;
3. allowed import/export;
4. short-circuit data;
5. BESS make/model;
6. PCS kW/kVA;
7. nominal/useful/EOL kWh;
8. C-rate;
9. transfer waveform;
10. black-start;
11. PV-island compatibility;
12. fire assessment;
13. meter map;
14. SOC reserve;
15. warranty;
16. installed CAPEX;
17. annual OPEX;
18. degradation;
19. blackout SAT.