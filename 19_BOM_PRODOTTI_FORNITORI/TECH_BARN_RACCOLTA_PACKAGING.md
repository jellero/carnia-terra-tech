# BOM-025 — Raccolta, selezione e packaging

**Aggiornato:** 17 settembre 2026  
**Ambito:** harvest handling + packing Tech Barn.  
**Stato:** `ARCHITETTURA STRUTTURATA / QUANTITÀ CASSETTE E SKU DA PEAK HARVEST / WASHED LEAFY OPTIONAL`.

## 1. Distinta

| Codice | Voce | Q.tà working | Stato | Benchmark |
|---|---|---:|---|---|
| PK-CRATE-S | cassetta shallow 600×400 food-contact | da formula | BASELINE | class €7–16/cad |
| PK-CRATE-M | cassetta medium 600×400 food-contact ventilata | da formula | BASELINE | RFQ / Manutan class |
| PK-CRATE-C | cassa chiusa food-contact | 10–30% crate fleet | CONDITIONAL | wet/retail/tool |
| PK-DOLLY-LOW | dolly 600×400 250–300 kg | 6–12 working | CANDIDATO | €45,50–85,50 + IVA |
| PK-DOLLY-HIGH | ergonomic raised 600×400 100 kg | 2–4 | CANDIDATO | €223,25 + IVA |
| PK-CART-500 | platform cart 500 kg | 1–2 | CANDIDATO | da €409 + IVA |
| PK-TABLE-180 | inox table 1800×700 | 3 working | BASELINE | €217,99–228,99 net |
| PK-TABLE-ADJ | height adjustable station | 1 | CANDIDATO | RFQ |
| PK-SCALE-30 | legal-capable bench scale 30 kg | 2 | BASELINE | €413,99 + IVA/cad benchmark |
| PK-SCALE-300 | platform scale 300 kg | 1 | BASELINE | €710,49 + IVA benchmark |
| PK-PRINTER | Zebra ZD421 TT Ethernet class | 1 | BASELINE | €499,88 + IVA |
| PK-PRINTER-SP | spare print path/head | 1 | DA TCO | RFQ |
| PK-SCANNER | barcode/QR scanner | 2 | BASELINE | RFQ |
| PK-TABLET | packing terminal/tablet | 1–2 | BASELINE | existing/IT RFQ |
| PK-SEAL-M | manual tray sealer | 0–1 | CANDIDATO | €1.408–2.260 + IVA |
| PK-SEAL-SA | semi-auto tray sealer | 0–1 | FUTURE | €2.125–3.958 + IVA |
| PK-DIE | tray-sealer die | per SKU | OBBLIGATORIO IF SEAL | RFQ |
| PK-WASH | washer/spinner | 0–1 | OPTIONAL F3-B | €1.996,99 + IVA class |
| PK-SPIN-20M | manual spinner 20 L | 1 | PILOT/BACKUP | €117,99 net |
| PK-SPIN-35 | electric spinner 35 L / 70 kg/h | 0–1 | CANDIDATO F3-B | €572,99 net |
| PK-SPIN-70 | electric spinner 70 L / 140 kg/h | 0–1 | FUTURE | €714,99 net |
| PK-SPIN-PRO | 12 kg/cycle professional | benchmark | HIGH GRADE | €2.841,49 + IVA |
| PK-SINK | stainless wash/tool sink | 1 | BASELINE | RFQ |
| PK-HOSE | food-area hose/reel | 1 | BASELINE | RFQ |
| PK-DRY-RACK | hygienic drying rack | 1 | BASELINE | RFQ |
| PK-LABEL-PAPER | labels 100×50 paper | OPEX | BASELINE | €6,90 + IVA / 1.000 |
| PK-LABEL-PP | PP labels 100×50 | OPEX | COLD/WET | €11,80 + IVA / 1.000 |
| PK-RIBBON | TT ribbon | OPEX | IF TT | RFQ |
| PK-TRAY | trays/punnets | OPEX | BY SKU | RFQ |
| PK-FILM | sealing film | OPEX | BY SKU | RFQ |
| PK-BAG | bags / microperforated | OPEX | BY SKU | RFQ |
| PK-BOX | outer cardboard | OPEX | SHIPPING | RFQ |
| PK-LOT | lot cards / emergency labels | 1 stock | FALLBACK | print locally |
| PK-SP-WHEEL | dolly wheels | 2–4 | SPARE | common size |
| PK-SP-SCALE | scale adapter/battery | 1 lot | SPARE | RFQ |
| PK-SP-PRINT | printhead/platen | 1 | DA SLA | RFQ |
| PK-SP-SEAL | heater/PTFE/seal consumables | 1 lot | IF SEAL | RFQ |
| PK-COM | commissioning/training | 1 | OBBLIGATORIO | workflow + traceability |

## 2. Crate economics

### Shallow food-contact reference

Polsinelli PE food-contact 600×400×70 mm:
- 13 L;
- stackable;
- €7,13 incl. VAT observed;
- pizza-use product, so produce suitability/ventilation must be tested.

### Food-use Euro container reference

Manutan food-use Euro container class:
- current promo ~€15,59 + IVA/cad for selected size;
- ventilated food-industry family available.

Use RFQ for exact 600×400 geometry and food-contact declaration.

### Fleet formula

Do not order "200 crates because round number".

`N = peak product in loop / target kg per crate × 1,3–1,5`.

Report cost per 100 crates so crop plan can scale.

At €7,13 each:
- 100 = €713 incl. VAT benchmark.

At €15,59 + IVA:
- 100 = €1.559 + IVA benchmark.

## 3. Trolleys

Manutan:
- ABS Euro dolly 600×400, 300 kg: **€45,50 + IVA**;
- PEHD 600×400, 300 kg: **€85,50 + IVA**;
- raised ergonomic 600×400, 100 kg: promo **€223,25 + IVA**;
- platform cart 500 kg: from **€409 + IVA**.

Working scenario 8 low dollies + 2 raised:
- low at €45,50 = €364 + IVA;
- 2 raised = €446,50 + IVA;
- subtotal ~€810,50 + IVA.

Not final quantity.

## 4. Stainless worktables

GGM Gastro 1800×700:
- lower shelf: **€217,99 net**;
- lower shelf + backsplash: **€228,99 net**;
- load 300 kg.

Three-table working stack:
- ~€654–687 net hardware.

For wet processing, RFQ higher-grade welded/hygienic tables separately; budget product is only benchmark.

## 5. Scales

Ristoattrezzature:
- 30 kg approved/omologato class: **€413,99 + IVA**;
- 300 kg / 700×800 platform: **€710,49 + IVA**.

Working 2×30 + 1×300:
- **€1.538,47 + IVA**.

Verify legal-metrology status for actual use before purchase.

## 6. Label printer

Zebra ZD421:
- TT 203 dpi Ethernet+USB: **€499,88 + IVA**;
- TT USB-only: €419 + IVA;
- direct thermal USB: €346,50 + IVA.

Working preference: TT + Ethernet.

Reason: cold/condensation labels and longer legibility benefit from proper media/ribbon; validate media in CR-A.

## 7. Label consumables

100×50:
- direct thermal paper 1.000 pcs: **€6,90 + IVA**;
- PP TT 1.000 pcs: **€11,80 + IVA**;
- 1.300 paper labels: €9,90 VAT incl benchmark.

Cost/label:
- paper ~0,69 cent + VAT;
- PP ~1,18 cent + VAT.

Adhesive and condensation performance must be tested, not assumed.

## 8. Tray sealer

Public 2026 benchmarks:

SMA Group:
- manual SV300: €1.408 + IVA;
- manual SV400: €1.958 + IVA;
- semi-auto Packmatic 300: €2.988 + IVA;
- Packmatic 400: €3.958 + IVA.

Attrezzature Alimentari:
- manual TSM101: €1.729,75 + IVA;
- manual TSM102: €2.260 + IVA;
- semi-auto TSS101: €2.125 + IVA;
- semi-auto TSS102: €2.740 + IVA.

Dies are additional unless explicitly included.

## 9. Leafy washing/drying — optional

### Low-cost/pilot

GGM:
- manual 20 L: €117,99 net;
- inox 35 L, 70 kg/h: €572,99 net;
- inox 70 L, 140 kg/h: €714,99 net.

### Higher grade

Ristoattrezzature:
- washer+spinner 1,5–4 kg: €1.996,99 + IVA;
- spinner 6 kg/cycle: €2.011,49 + IVA;
- spinner 12 kg/cycle: €2.841,49 + IVA.

**Not baseline CAPEX** until F3-B ready-to-eat decision.

## 10. Hygiene / FCM

All crates, trays, films, bags and food-contact machine surfaces require applicable food-contact conformity.

Relevant baseline:
- Reg. EC 1935/2004;
- Reg. EC 2023/2006 GMP;
- plastics-specific declarations where applicable.

Do not accept "food safe" marketing text without supplier declaration/documentation.

## 11. Wash-water rule

EFSA 2025:
- poor process-water management can spread microbiological contamination;
- disinfection + replenishment can help maintain microbiological quality.

Therefore any F3-B wet line requires:
- water specification;
- refresh rate;
- treatment/disinfection if needed;
- monitoring;
- final-rinse requirement;
- drain/greywater plan;
- validation records.

## 12. Label data

Fresh produce labels/master data must support:
- product;
- origin;
- lot;
- packer;
- harvest/pack date internally;
- category/variety/calibre when required by marketing standard;
- net quantity where applicable;
- storage/use information where applicable.

Reg. delegated EU 2023/2429 governs current fruit/vegetable marketing information chain; prepacked-food rules may add requirements depending on SKU.

## 13. CAPEX working lower bound

Core tools only, excluding crate fleet and consumables:

- 8 low dollies + 2 raised: ~€810,50 + IVA;
- 3 tables: ~€654–687 net;
- scales: ~€1.538,47 + IVA;
- ZD421 TT Ethernet: €499,88 + IVA;
- manual tray sealer: ~€1.408–2.260 + IVA if adopted;
- manual spinner: €117,99 net.

Core without tray sealer: approximately **€3,6k + IVA-equivalent order of magnitude** before sinks, scanners, electrical, install and crate fleet.

Core with manual tray sealer: roughly **€5,0–5,9k + IVA-equivalent** before the same exclusions.

These are catalog lower bounds, not project CAPEX.

## 14. Gate

Final quantities/prices require:
- peak kg/h and kg/day;
- crate payload;
- sales channels;
- packaging SKUs;
- washed/unwashed decision;
- label legal review;
- wet-process decision;
- labor time study;
- RFQ on 100/250/500 crates;
- installed workstation quote;
- packaging MOQ and lead time;
- shelf-life and drop tests.
