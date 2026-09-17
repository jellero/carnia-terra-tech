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
| GH-VENT-001 | Aperture laterali | 6 zone | `REQUISITO` | **BOM-003** prossima |
| GH-VENT-002 | Aperture zenitali | DA VALUTARE | `CANDIDATO` | dipende da ventilazione/prezzo |
| GH-NET-001 | Rete anti-insetto | DA DIMENSIONARE | `REQUISITO` | selezione su parassita + airflow |
| GH-SCR-001 | Schermi C1/C2/C6 | ~2.100 m² nominali + geometria reale | `CANDIDATI REALI / DA PREVENTIVARE` | vedi BOM-002 |
| GH-SCR-002 | Predisposizione schermi C3-C5 | 3 comparti | `REQUISITO` | integrare nella struttura |
| GH-SCR-003 | Energy screen FR | 1 livello alternativo S1 | `CANDIDATO` | RES 10+ FR / LUXOUS 1147 FR, prezzo su richiesta |
| GH-SCR-004 | Shade/diffusion screen FR | 1 livello alternativo S2 | `CANDIDATO` | RLD 45 FR O / HARMONY 5220 O FR, prezzo su richiesta |
| GH-SCR-005 | Doppio schermo | alternativa S3 | `DA PREVENTIVARE` | doppia meccanica/carichi da quotare |
| GH-SCR-006 | Motoriduttori schermo | working 1/comparto/livello | `CANDIDATO` | famiglia Ridder RW45; benchmark variante retail £598 |
| GH-SCR-007 | Finecorsa/feedback | 1 set/motore | `CANDIDATO` | benchmark limit set RW45 £70; compatibilità da verificare |
| GH-SCR-008 | Meccanica screen | da shop drawing | `DA PREVENTIVARE` | fili, profili, alberi, cremagliere/push-pull, supporti |
| GH-SCR-009 | Quadro/cablaggio screen | per motore/zona | `DA PREVENTIVARE` | protezioni, sezionatori, cavi, I/O |
| GH-SCR-010 | Posa/commissioning/ricambi | 1 lotto | `DA PREVENTIVARE` | separare posa, taratura e stock ricambi |
| GH-HAF-001 | Ventilatori HAF | 24 working + scorta | `CANDIDATO` | vedi BOM-001 esistente |
| GH-FOG-001 | Fogging C1/C2/C6 | 3 zone | `REQUISITO` | dopo analisi acqua/clima |
| GH-CROP-001 | Fili/supporti pomodoro/peperone | DA LAYOUT | `REQUISITO` | carico al progettista |
| GH-CROP-002 | Canaline drenaggio fuori suolo | DA LAYOUT | `REQUISITO` | collegamento punto 04 |
| GH-ELEC-001 | Passerelle/canaline elettriche | DA LAYOUT | `REQUISITO` | collegamento punto 06/07 |
| GH-SAFE-001 | Accessi/manutenzione/anticaduta | DA PROGETTO | `REQUISITO` | da normativa/procedure |
| GH-SP-001 | Bulloneria/minuteria scorta | DA DISTINTA | `REQUISITO` | non assorbire in forfait |
| GH-LAB-001 | Montaggio struttura | ~960 h-persona benchmark storico | `DA PREVENTIVARE` | 4 persone × 8 h × 30 gg working benchmark |
| GH-TOOLS-001 | Attrezzatura cantiere | 1 lotto | `DA BOM` | vecchio working budget €18–30k da ricostruire |

## 2. BOM sviluppate

### BOM-001 — HAF

File: `19_BOM_PRODOTTI_FORNITORI/SERRA_HAF_VENTILATION.md`.

Stato: candidati e benchmark prezzi trovati; quantità finale da validare con geometria/velocità aria.

### BOM-002 — schermi

File: `19_BOM_PRODOTTI_FORNITORI/SERRA_SCHERMI_TERMICI_OMBREGGIANTI.md`.

Stato: candidati reali identificati e sistema scomposto fino a meccanica, elettrico, posa e ricambi. Prezzo completo non inventato perché tessuti professionali e sistemi completi sono quotati su richiesta e dipendono dalla geometria.

Alternative da RFQ:

- S1 energy-first;
- S2 shade/diffusion-first;
- S3 doppio schermo.

## 3. Benchmark struttura esistente

Nel lavoro precedente è stato registrato un benchmark pubblico:

- serra professionale 8 × 40 m = 320 m²;
- **€6.832 IVA inclusa**;
- circa **€21,35/m²**;
- struttura metallica;
- coperture escluse;
- montaggio escluso.

**Classificazione:** `BENCHMARK STORICO / URL DA RECUPERARE / NON SCALARE LINEARMENTE`.

Non usare `€21,35 × 4.200` come costo di progetto: una multicampata professionale con carichi locali, gronde, comparti, aperture e accessori ha architettura diversa.

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

1. **BOM-003 aperture/motorizzazioni/reti**;
2. BOM-004 copertura + profili + fissaggi;
3. RFQ struttura/fondazioni;
4. BOM-005 fogging;
5. supporti coltura/canaline;
6. porte/compartimenti/gronde;
7. attrezzatura e consumabili di montaggio.

La numerazione generale delle BOM può essere riallineata nel registro centrale senza perdere riferimenti.
