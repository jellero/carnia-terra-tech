# Fonti — BOM-024 Celle frigorifere

**Aggiornato:** 17 settembre 2026  
**Regola:** prezzi pubblici sono benchmark osservati e vanno riconfermati al preventivo/ordine.

## 1. Postharvest — UC Davis

Lettuce romaine/leaf:
https://postharvest.ucdavis.edu/produce-facts-sheets/lettuce-romaine
- optimum near 0 °C;
- shelf-life ~21 d near 0 °C vs ~14 d at 5 °C;
- RH >95%;
- vacuum/hydrovac/hydrocooling common; forced-air possible but slower and more moisture loss.

Lettuce crisphead:
https://postharvest.ucdavis.edu/produce-facts-sheets/lettuce-crisphead
- RH >95%;
- ethylene sensitive.

Bell pepper:
https://postharvest.ucdavis.edu/produce-facts-sheets/bell-pepper
- ~7,5 °C optimum for max shelf-life;
- >95% RH;
- chilling injury risk with prolonged lower temperatures.

Tomato:
https://postharvest.ucdavis.edu/produce-facts-sheets/tomato
- temperature depends maturity;
- firm-ripe short storage around 10–12,5 °C;
- RH 90–95%.

Fresh herbs:
https://postharvest.ucdavis.edu/produce-facts-sheets/herbs-fresh-culinary
- basil/shiso chilling-sensitive;
- store above 10 °C;
- RH >95%.

Postharvest manual:
https://ucanr.edu/sites/Postharvest_Technology_Center_/files/231952.pdf
- summary table: leaf lettuce ~0 °C; pepper ~8 °C; ripe tomato ~10 °C; green tomato ~12 °C.

## 2. F-gas

Regulation (EU) 2024/573:
https://eur-lex.europa.eu/eli/reg/2024/573/oj

Annex IV:
- self-contained refrigeration with fluorinated GWP >=150: prohibition from 1 Jan 2025, subject to safety exceptions;
- other stationary refrigeration with fluorinated GWP >=150: prohibition from 1 Jan 2030, subject to safety exceptions.

Use this as procurement guardrail, not as substitute for EN 378/site risk assessment.

## 3. Food hygiene

Regulation (EC) 852/2004:
https://eur-lex.europa.eu/eli/reg/2004/852/oj
- temperature-controlled storage must have sufficient capacity;
- temperature must be monitorable/recordable where necessary;
- cold chain and HACCP requirements.

Regulation 37/2005 applies to quick-frozen foodstuffs, not the fresh-produce baseline:
https://eur-lex.europa.eu/eli/reg/2005/37

Do not incorrectly present its EN 12830 recording obligation as directly mandatory for all fresh vegetables. EN 12830-compatible logging remains a useful procurement benchmark.

## 4. Danfoss Optyma

Official:
https://www.danfoss.com/it-it/products/dcs/condensing-units/products/optyma-condensing-units/

- outdoor A1 low-GWP and A2L multi-refrigerant options;
- indoor R290 range;
- MBP/LBP;
- microchannel;
- cold-room selection material.

Price: RFQ.

## 5. GGM R290 monoblocks

KDC800N:
https://www.ggmgastro.com/it-it-eur/unita-a-soffitto-refrigerante-tipo-monoblocco-tn-per-volumi-fino-a-50-0m3-grado-di-protezione-ip-20-per-it-kdc800n

Observed:
- €5.399,99 net;
- R290 / 0,15 kg;
- -5…+15 °C;
- max room 50 m³ stated;
- compressor 2,25 kW;
- 400 V;
- Modbus/Bluetooth.

KDC600N:
https://www.ggmgastro.com/it-it-eur/unita-a-soffitto-refrigerante-tipo-monoblocco-tn-per-volumi-fino-a-35-1m3-grado-di-protezione-ip-20-kdc600n

Observed:
- €4.899,99 net;
- R290 / 0,15 kg;
- 35,1 m³ @32 °C ambient / 21 m³ @43 °C;
- compressor 1,48 kW;
- 400 V.

Vendor note on small units references EN 378 risk assessment and 0,15 kg circuit charge:
https://www.ggmgastro.com/it-it-eur/unita-a-soffitto-refrigerante-tipo-monoblocco-tn-per-volumi-fino-a-9-7m3-grado-di-protezione-ip-20-kdc200n

Do not generalise this statement to other equipment/charges.

## 6. Cold-room shell benchmark

Ristoattrezzature:
https://www.ristoattrezzature.com/linee-professionali/refrigerazione-professionale/celle-refrigerate/celle-frigorifere/cella-frigorifero-altezza-2540-mm-prezzo-escluso-motore-4740x4740x2540h-mm.html

Observed:
- 4.740×4.740×2.540 mm;
- €6.775,99 + IVA;
- refrigeration excluded.

GGM shell cross-check:
https://www.ggmgastro.com/it-it-eur/cella-frigorifera-2825x5275mm-25-98m3-con-pavimento-pannello-100mm-tc2852
- 25,98 m³;
- 100 mm;
- floor included;
- €8.899,99 net;
- refrigeration excluded;
- published wheel load limit 200 kg/rubber wheel: reason to verify stacker compatibility.

## 7. Small turnkey R290 benchmark

TEFCOLD CRPF1830:
https://www.horeca.com/it/product/130628/tefcold-crpf1830-cella-frigorifera-completa-di-monoblocco

Observed:
- 12,34 m³;
- 0…+8 °C;
- R290;
- 905 W;
- 80 mm;
- €7.467.

Small-room market benchmark only.

## 8. Monitoring

Testo 160 TH via RS:
https://it.rs-online.com/web/p/datalogger/2687883
- T/RH Wi-Fi;
- €180 + IVA observed.

Testo 160 T:
https://it.rs-online.com/web/p/datalogger/0619082
- €120 + IVA observed;
- listing cites EN 12830.

Carel IR33:
https://it.rs-online.com/web/p/termoregolatori-pid/5117440
- €143,84 + IVA observed.

Carel IR33 230 V variant:
https://it.rs-online.com/web/p/termoregolatori-pid/7457951
- €215,02 + IVA observed.

RS485 interface:
https://it.rs-online.com/web/p/moduli-di-espansione-per-plc/7458005
- €80,72 + IVA observed.

## 9. Open points

DA VERIFICARE:
- actual shell price at 25–30 m²/cell;
- wide pallet doors;
- floor build-up;
- actual refrigeration load;
- installed remote system prices;
- R290/A2L site safety;
- RH/humidifier need;
- forced-air precool cost;
- racks;
- installation/certification;
- grant eligibility.
