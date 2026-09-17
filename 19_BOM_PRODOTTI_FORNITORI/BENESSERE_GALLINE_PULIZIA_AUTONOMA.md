# BOM-023 — Pulizia automatizzata galline free-range

**Aggiornato:** 17 settembre 2026
**Ambito:** ricovero + portico + parcheggi + prato accessibili alle galline.
**Stato:** ARCHITETTURA DEFINITA / HARD-SURFACE COTS BENCHMARK / GRASS PICKUP R&D / PILOT BLOCCANTE.

## 1. Distinta

| Codice | Voce | Q.tà working | Stato | Benchmark / nota |
|---|---|---:|---|---|
| CHK-BASE-001 | rover sanitario dedicato | 1 | DA PILOT/RFQ | Burro Verde candidato |
| CHK-BASE-002 | AgileX Bunker Pro 2.0 | benchmark | R&D ALTERNATIVA | ~€22.138 ex VAT / ~€22.550 incl. IVA DE |
| CHK-COTS-HARD | Gausium Beetle 2.0 | benchmark | HARD FLOOR | ~€19.999 + IVA osservato |
| CHK-NAV | LiDAR/vision/GNSS/localization | 1 pkg | REQUISITO | nativo/integrato |
| CHK-SAFE | bumper/E-stop/animal-zone | 1 pkg | OBBLIGATORIO | no parti mobili esposte |
| CHK-HARD-HEAD | testata hard floor | 1 | CUSTOM/RFQ | scraper + pickup + vacuum |
| CHK-GRASS-HEAD | testata prato spot-pickup | 1 | R&D | vision + soft scoop/local vacuum |
| CHK-HOPPER | hopper sigillato 20–45 L class | 1 | DA TEST | lavabile, level sensor |
| CHK-CLEAN-W | clean-water tank | 0–1 | HARD FLOOR | volume da pilot |
| CHK-GREY-W | greywater tank | 0–1 | HARD FLOOR | separato dai solidi |
| CHK-FILTER | filtro/solids trap | 1 pkg | REQUISITO | serviceable |
| CHK-PUMP-VAC | vacuum/blower | 1 | DA HEAD | wet-compatible se necessario |
| CHK-PUMP-W | pompa risciacquo bassa pressione | 0–1 | CONDIZIONALE | no aerosol |
| CHK-CAM-RGBD | RGB/depth camera | 1–2 | R&D | OAK-D class |
| CHK-COMPUTE | edge inference | 1 | R&D | Jetson class |
| CHK-DCK-001 | dirty dock | 1 | CUSTOM/RFQ | charge + empty + wash |
| CHK-DCK-WASH | wheel/underbody wash | 1 | REQUISITO | contained |
| CHK-DCK-SOL | solids separator | 1 | REQUISITO | accessible |
| CHK-DCK-GW | greywater holding/drain | 1 | DA SITE | no uncontrolled discharge |
| CHK-COOP-SLAT | fessurato/piattaforma posatoi | da layout | CANDIDATO FORTE | concentra manure |
| CHK-COOP-BELT | manure belt/scraper | 1 system | DA RFQ | Big Dutchman SIMBA class |
| CHK-COOP-DRIVE | drive/tension/limits | 1 pkg | REQUISITO | guarded |
| CHK-GATE-COOP | porta automatica ricovero | 1+ | REQUISITO | benchmark €110–170 small-scale |
| CHK-GATE-PARK | gate parcheggio galline | 1+ | DA MASTERPLAN | commercial RFQ |
| CHK-GATE-IO | status/interlock I/O | per gate | REQUISITO | local |
| CHK-BIN-001 | bin manure chiuso | 1–2 | REQUISITO | washable |
| CHK-SP-BRUSH | scraper/brush spare | 1 set | RICAMBIO | quick change |
| CHK-SP-SEAL | hose/seal/filter spare | 1 lot | RICAMBIO | contamination-critical |
| CHK-SP-WHEEL | wheel/track spare | 0–1 | DA TCO | lead time |
| CHK-PPE | DPI sanitation service | 1 lot | OPEX | procedure-specific |
| CHK-COM-001 | mixed-surface pilot | 1 | OBBLIGATORIO | grass/hard/coop |
| CHK-COM-002 | animal welfare/safety test | 1 | OBBLIGATORIO | hens present |
| CHK-COM-003 | gate/vehicle interlock test | 1 | OBBLIGATORIO | parking |
| CHK-COM-004 | dirty dock validation | 1 | OBBLIGATORIO | wash/containment |
| CHK-DOC | DoC/risk assessment/as-built | 1 lot | OBBLIGATORIO | integrated machine |

## 2. Prezzi trovati

Gausium Beetle/2.0: official indoor/outdoor sweeper, 3D LiDAR, spot cleaning, 45 L, 4–8 h. Beetle 2.0 Full-Scenario annunciata 2026. Prezzo distributore osservato €19.999 + IVA; altri canali Beetle/Pro ~€14.500–15.999 + IVA. PREZZO TROVATO UE; non prova manure fresco né prato.

AgileX Bunker Pro 2.0: IP67, 120 kg payload, 785 mm, 225 kg, circa €22.138 ex VAT benchmark UE; altro listino circa €22.550 con IVA DE. PREZZO TROVATO / BASE R&D.

Burro Verde: 685 mm, 227 kg, indoor/outdoor farm, IP65. PREZZO DA PREVENTIVO; benchmark terzo già censito in BOM-020.

ChickenGuard 2026: Pro ~€111,56; Pro Door Kit ~€133,87; all-in-one ~€126–134; self-locking door ~€50–55. Benchmark piccoli, non gate parcheggio.

## 3. Componenti custom — stime di prefattibilità

Non esiste listino affidabile per una testata avicola grass+hard-floor all-area.

- hard-surface sanitary head: STIMA PREFATTIBILITÀ €6–12k;
- grass spot-pickup prototype/NRE: STIMA PREFATTIBILITÀ €8–20k;
- dirty dock wash/empty: STIMA PREFATTIBILITÀ €4–10k;
- perception/edge add-on: STIMA PREFATTIBILITÀ €1–3k;
- manure belt/scraper ricovero: PREZZO DA PREVENTIVO;
- gates commerciali: PREZZO DA PREVENTIVO.

Le stime sono primo-prototipo, non includono certificazione completa, ore interne, IVA, trasporto o industrializzazione.

## 4. Benchmark ricerca

Studio 2026 grooved-floor: rimozione fecale 88,24 ± 2,37% e volume 3D correlato al peso. Prototipo flat-coop: 95,38% cleanliness e ~178 m²/h. Studi robot-poultry mostrano movimento del gruppo e contatti/spinte leggere: welfare test obbligatorio. Sono BENCHMARK DI RICERCA, non prestazioni Carnia.

## 5. TCO

CAPEX rover + heads + coop belt + dock + gates + integration + certification + spares.

OPEX: energia + acqua + consumabili + wash + filtri + manutenzione + software + usura + ore manuali residue + downtime.

Contabilizzare anche ore di lavoro sporco eliminate, minore contatto operatore/manure, qualità portico/parcheggio e welfare.

## 6. Decisione working

Preferenza architetturale: rover agricolo dedicato tipo Burro Verde + testata hard-floor custom + testata prato R&D + manure belt/scraper sotto posatoi + dirty dock.

Gausium Beetle resta benchmark COTS per superfici dure. AgileX Bunker Pro resta base R&D alternativa.

Nessun ordine finché il grass spot-pickup non supera un pilot realistico senza danni al prato e senza rischio per gli animali.
