# BOM-013 — Distribuzione irrigua, gocciolatori e settori

**Aggiornato:** 17 settembre 2026  
**Ambito:** uscita fertirrigazione -> 6 comparti -> working 24 settori -> emettitori.  
**Stato:** `CANDIDATI REALI / QUANTITÀ BLOCCATE DA CROP CARD E CALCOLO IDRAULICO`.

## 1. Distinta principale

| Codice | Voce | Quantità working | Stato | Prezzo / nota |
|---|---|---:|---|---|
| IRR-HDR-001 | collettore principale | 1 | DA CALCOLO/RFQ | DN da portata simultanea |
| IRR-HDR-002 | collettori comparto | 6 | REQUISITO | isolabili |
| IRR-SEC-001 | settori irrigui | 24 working | DA VALIDARE | 4×6, non quantità immutabile |
| IRR-ISO-001 | valvola manuale settore | 24 working | DA RFQ | full bore/serviceable |
| IRR-SOL-001 | elettrovalvola 24 VAC NC | 24 working | CANDIDATI | Bermad 1" ~€23,15–28,53 IVA incl. benchmark |
| IRR-PRS-001 | regolatore pressione settore/comparto | 6–24 | DA CALCOLO | Netafim 3/4" €9,89–18 + IVA benchmark |
| IRR-PRS-002 | regolatore 1,5" | da portata | BENCHMARK | Netafim €41 + IVA |
| IRR-PRS-003 | regolatore 2" | da portata | BENCHMARK | Netafim €139 + IVA |
| IRR-DRP-001 | Netafim PCJ standard 2 l/h | da piante | PREZZO TROVATO | €261 + IVA / 1.000 pz = €0,261/pz |
| IRR-DRP-002 | PCJ LCNL/HCNL 2 l/h | da piante | CANDIDATO PRIORITARIO | prezzo configurazione da confermare/RFQ |
| IRR-MIC-001 | microtubo PE 5 mm OD | da layout | PREZZO TROVATO | €38 + IVA / 200 m = €0,19/m |
| IRR-STK-001 | punto goccia 14 cm 3/5 mm | da punti | PREZZO TROVATO | €95 + IVA / 1.000 = €0,095/pz |
| IRR-STK-002 | asta guidata 3/5 mm | da punti | PREZZO TROVATO | €140 + IVA / 1.000 per variante osservata |
| IRR-MUL-001 | gruppo 2/4 punti preassemblato | da progetto | PREZZO TROVATO | da €0,83 + IVA/gruppo; 60 cm microtubo |
| IRR-PE25-001 | PE BD PN4 Ø25 100 m | m da layout | BENCHMARK | €40 IVA incl. / 100 m |
| IRR-PE32-001 | PE BD PN4 Ø32 100 m | m da layout | BENCHMARK | €55 IVA incl. / 100 m |
| IRR-MAIN-001 | PE100/PN adeguato dorsali | m/DN da layout | DA RFQ | non sostituire automaticamente con PN4 |
| IRR-FIT-001 | tee/gomiti/riduzioni/unioni | da layout | DA DISTINTA | niente forfait |
| IRR-PUNCH-001 | pinza/punch inserimento dripper | 2+ | PREZZO TROVATO | Netafim da €28 + IVA |
| IRR-REP-001 | tappi riparazione foro PE | lotto | DA RFQ | manutenzione |
| IRR-FLS-001 | valvole flush fine linea | per linea/collettore | CANDIDATO | Netafim valvola fine linea €5,50 + IVA benchmark |
| IRR-FLS-002 | collettore scarico flush | da layout | DA PROGETTO | gestione acqua lavaggio |
| IRR-FLW-001 | flow meter centrale | 1 | REQUISITO | package pompe/filtri da coordinare |
| IRR-FLW-002 | flow meter comparto | 6 | PREFERENZA | scenario M1 |
| IRR-FLW-003 | flow meter settore | 24 | OPZIONE M2 | decidere su TCO/diagnostica |
| IRR-PRE-001 | sensore pressione comparto | 6 | PREFERENZA | analogico/Modbus da standardizzare |
| IRR-PRE-002 | prese/manometri settore | 24 | CANDIDATO | basso costo, commissioning |
| IRR-ELC-001 | cablaggio elettrovalvole | 24 zone | DA RFQ | morsetti, scatole, cavi |
| IRR-CTL-001 | I/O PLC | 24 zone | REQUISITO | comando/feedback/allarmi |
| IRR-SP-001 | elettrovalvole scorta | 1–2 | CANDIDATO | standardizzare taglie se possibile |
| IRR-SP-002 | solenoidi scorta | 2+ | CANDIDATO | compatibilità modello |
| IRR-SP-003 | emettitori/capillari/punti goccia | 1–5% | DA TCO | definire dopo quantità |
| IRR-COM-001 | flushing iniziale | 1 lotto | OBBLIGATORIO | prima emettitori/commissioning |
| IRR-COM-002 | test uniformità | 24 settori o architettura finale | OBBLIGATORIO | portata/pressione campionata |
| IRR-DOC-001 | P&ID/as-built | 1 lotto | OBBLIGATORIO | layout, codici, ricambi |

## 2. PCJ candidato

Netafim PCJ standard/LCNL:

- 2 l/h disponibile;
- autocompensante;
- autopulente;
- LCNL anti-drenaggio;
- standard PC range tipico 0,5–4 bar; LCNL 0,7–4 bar;
- LCNL shut-off ~0,12 bar;
- filtrazione raccomandata 120 mesh / 130 μm;
- PE cieco richiesto 0,9–1,2 mm per inserimento secondo scheda Netafim.

**Decisione:** per C1/C2/C6 confrontare PCJ LCNL/HCNL 1,2–4 l/h. 2 l/h non è ancora congelato.

## 3. Benchmark costo per 1.000 punti singoli

Configurazione puramente economica con prezzi pubblici standard:

- 1.000 PCJ standard 2 l/h: €261 + IVA;
- 600 m microtubo PE 5 mm: 3 bobine × €38 = €114 + IVA;
- 1.000 punti goccia 14 cm: €95 + IVA.

Totale: **~€470 + IVA per 1.000 punti**, esclusi PE principale, raccordi, punch, valvole, posa, ricambi e variante LCNL.

Con asta guidata da €140/1.000 al posto del punto goccia €95/1.000: **~€515 + IVA/1.000 punti**.

È un benchmark, non un ordine.

## 4. Benchmark 24 elettrovalvole

Bermad IR-21T 1" 24 VAC ~€23,15 IVA incl.:

- 24 pz = ~€555,60 IVA incl.

Bermad 100DTV 1" ~€28,53 IVA incl.:

- 24 pz = ~€684,72 IVA incl.

Questi totali non includono valvole manuali, regolatori, raccordi, pozzetti/scatole, cablaggio, I/O o installazione. Il diametro 1" non è selezionato finché non conosciamo Q settore.

## 5. Linee PE

Benchmark agricoli:

- Ø25 PN4: €40/100 m IVA incl. = €0,40/m;
- Ø32 PN4: €55/100 m IVA incl. = €0,55/m.

Usarli solo dove pressione, posa e durata sono coerenti. Dorsali principali e tratti sempre in pressione vanno confrontati con PE100/PN superiore.

## 6. Settori e portata

Formula:

`Qsettore [m³/h] = Σ portate emettitori [l/h] / 1000`.

Esempio matematico:

- 500 × 2 l/h = 1,0 m³/h;
- 1.000 × 2 l/h = 2,0 m³/h;
- 1.500 × 2 l/h = 3,0 m³/h.

Valvola e DN devono essere verificati sul Q reale e sulla perdita accettabile.

## 7. Filtrazione — interfaccia col prossimo package

Il candidato PCJ richiede 120 mesh / 130 μm. Netafim raccomanda pretrattamento addizionale in presenza di sabbia significativa; l'analisi acqua decide idrociclone, dischi/rete, automazione controlavaggio e ridondanza.

La BOM-013 non compra ancora i filtri: definisce il requisito che BOM-014 dovrà soddisfare.

## 8. Manutenzione

Registrare:

- pressione e portata baseline settore;
- deviazione rispetto baseline;
- ore/cicli elettrovalvole;
- flush effettuati;
- sostituzioni dripper/capillari;
- perdite/riparazioni PE;
- calibrazione sensori;
- uniformità stagionale.

## 9. Gate

1. piante/steli e layout C1/C2;
2. geometria letti C3–C5;
3. configurazione C6;
4. q nominale emettitore;
5. lunghezza capillare;
6. 24 settori confermati/modificati;
7. pressione post-fertirrigazione;
8. analisi acqua/filtrazione;
9. perdite di carico;
10. M1 vs M2 per flow meter;
11. uniformità target;
12. RFQ comparabili.
