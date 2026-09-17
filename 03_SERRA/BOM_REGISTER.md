# Carnia TerraTech — Greenhouse BOM Register

**Aggiornato:** 17 settembre 2026  
**Regola:** una riga resta aperta finché quantità, specifica, prezzo, posa, manutenzione e ricambio non sono chiusi.

## 1. Registro principale

| Codice | Voce | Quantità working | Stato | Prezzo / nota |
|---|---|---:|---|---|
| GH-STR-001 | Struttura portante 4.200 m² | 1 sistema | `DA PREVENTIVARE` | nessun prezzo definitivo |
| GH-FND-001 | Fondazioni/ancoraggi | DA CALCOLARE | `BLOCCATO DAL LOTTO` | dipende da geotecnica e struttura |
| GH-COV-001 | Film/copertura principale | DA CALCOLARE | `DA SPECIFICARE` | richiedere prezzo €/m² + posa |
| GH-COV-002 | Profili/fissaggi copertura | DA CALCOLARE | `DA SPECIFICARE` | voce separata |
| GH-COV-003 | Kit riparazione/scorta copertura | DA DEFINIRE | `REQUISITO` | stock iniziale |
| GH-END-001 | Testate | 6 comparti / layout | `DA PREVENTIVARE` | separare da struttura |
| GH-DR-001 | Porte persone | DA LAYOUT | `DA PREVENTIVARE` | sicurezza + biosicurezza |
| GH-DR-002 | Porte logistiche/AMR | DA LAYOUT | `DA PREVENTIVARE` | quota dopo scelta mezzi |
| GH-GUT-001 | Gronde | DA GEOMETRIA | `DA PREVENTIVARE` | integrate con recupero pioggia |
| GH-GUT-002 | Pluviali/collettori primari | DA GEOMETRIA | `DA PREVENTIVARE` | collegamento punto 04 |
| GH-CMP-001 | Divisori comparti | 5 separazioni + dettagli | `DA PREVENTIVARE` | materiale da definire |
| GH-VENT-001 | Aperture laterali | 6 zone | `REQUISITO` | BOM dedicata successiva |
| GH-VENT-002 | Aperture zenitali | DA VALUTARE | `CANDIDATO` | dipende da ventilazione/prezzo |
| GH-NET-001 | Rete anti-insetto | DA DIMENSIONARE | `REQUISITO` | selezione su parassita + airflow |
| GH-SCR-001 | Schermi C1/C2/C6 | ~2.100 m² + margini | `REQUISITO` | **BOM-002** da prezzare |
| GH-SCR-002 | Predisposizione schermi C3-C5 | 3 comparti | `REQUISITO` | da integrare in struttura |
| GH-HAF-001 | Ventilatori HAF | 24 working + scorta | `CANDIDATO` | vedi BOM-001 esistente |
| GH-FOG-001 | Fogging C1/C2/C6 | 3 zone | `REQUISITO` | dopo analisi acqua/clima |
| GH-CROP-001 | Fili/supporti pomodoro/peperone | DA LAYOUT | `REQUISITO` | carico al progettista |
| GH-CROP-002 | Canaline drenaggio fuori suolo | DA LAYOUT | `REQUISITO` | collegamento punto 04 |
| GH-ELEC-001 | Passerelle/canaline elettriche | DA LAYOUT | `REQUISITO` | collegamento punto 06/07 |
| GH-SAFE-001 | Accessi/manutenzione/anticaduta | DA PROGETTO | `REQUISITO` | da normativa/procedure |
| GH-SP-001 | Bulloneria/minuteria scorta | DA DISTINTA | `REQUISITO` | non assorbire in forfait |
| GH-LAB-001 | Montaggio struttura | ~960 h-persona benchmark storico | `DA PREVENTIVARE` | 4 persone × 8 h × 30 gg working benchmark |
| GH-TOOLS-001 | Attrezzatura cantiere | 1 lotto | `DA BOM` | vecchio working budget €18–30k da ricostruire |

## 2. Benchmark struttura esistente

Nel lavoro precedente è stato registrato un benchmark pubblico:

- serra professionale 8 × 40 m = 320 m²;
- **€6.832 IVA inclusa**;
- circa **€21,35/m²**;
- struttura metallica;
- coperture escluse;
- montaggio escluso.

**Classificazione:** `BENCHMARK STORICO / URL DA RECUPERARE / NON SCALARE LINEARMENTE`.

Non usare `€21,35 × 4.200` come costo di progetto: una multicampata professionale con carichi locali, gronde, comparti, aperture e accessori ha architettura diversa.

## 3. Benchmark retail secondario

Sono disponibili sul mercato italiano piccole serre professionali/modulari in acciaio zincato e policarbonato con prezzi pubblici; servono solo come confronto su materiali e ordine di grandezza, non come base dimensionale per Carnia TerraTech.

## 4. Costo completo

Per ogni macrovoce calcolare:

`materiale + accessori + minuteria + trasporto + scarico + posa + mezzi + progettazione + commissioning + ricambi iniziali`.

Poi separare:

- costo reale;
- IVA;
- costo eventualmente eleggibile;
- contributo potenziale;
- quota finanziata;
- quota cassa/equity.

## 5. Prossima sequenza economica serra

1. **BOM-002 schermi termici/ombreggianti**;
2. BOM-003 aperture/motorizzazioni/reti;
3. BOM-004 copertura + profili + fissaggi;
4. RFQ struttura/fondazioni;
5. BOM-005 fogging;
6. supporti coltura/canaline;
7. porte/compartimenti/gronde;
8. attrezzatura e consumabili di montaggio.

La numerazione generale delle BOM può essere riallineata nel registro centrale senza perdere riferimenti.
