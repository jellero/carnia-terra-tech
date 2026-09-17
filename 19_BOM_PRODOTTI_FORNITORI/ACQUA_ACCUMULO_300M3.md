# BOM-018 — Accumulo acqua 300 m³

**Aggiornato:** 17 settembre 2026  
**Ambito:** captazione/fonte -> accumulo atmosferico -> aspirazione pompe BOM-015.  
**Stato:** `BASELINE 2×150 m³ / CANDIDATI REALI / VOLUME E TIPO DA BILANCIO IDRICO, LOTTO E RFQ`.

## 1. Distinta principale

| Codice | Voce | Quantità working | Stato | Benchmark / nota |
|---|---|---:|---|---|
| WST-TNK-001 | tank acqua 1 | 150 m³ working | DA RFQ | volume utile da dichiarare |
| WST-TNK-002 | tank acqua 2 | 150 m³ working | DA RFQ | indipendente/isolabile |
| WST-EXP-001 | predisposizione espansione | 1 | REQUISITO | 400–500 m³ futuri |
| WST-STEEL-150 | tank acciaio zincato 150.000 L | benchmark | PREZZO TROVATO | Tanks Direct £4.650 ex VAT, UK |
| WST-STEEL-200 | tank acciaio zincato 200 m³ | benchmark | PREZZO TROVATO | €6.630 + IVA, installazione/trasporto esclusi |
| WST-ABEKO-200 | ABEKO ~200 m³ utili | benchmark | PREZZO TROVATO | €7.807 + IVA + cover €725 |
| WST-BLD-150 | bladder Labaronne Citaf 150 m³ | alternativa | PREZZO TROVATO | €4.270 + IVA; delivery annuncio €1.000 + IVA da confermare |
| WST-BLD-150B | bladder RL Distrib 150 m³ | alternativa | PREZZO TROVATO | €3.799 + IVA benchmark |
| WST-GRP-150 | GRP/modulare ~150 m³ | alternativa | PREZZO DA PREVENTIVO | forma/layout flessibili |
| WST-LIN-001 | liner tank 1 | 1 | REQUISITO SE STEEL | materiale/spessore OEM |
| WST-LIN-002 | liner tank 2 | 1 | REQUISITO SE STEEL | ricambio/lead time |
| WST-COV-001 | copertura tank 1 | 1 | REQUISITO | opaca anti-alga |
| WST-COV-002 | copertura tank 2 | 1 | REQUISITO | opaca anti-alga |
| WST-IN-001 | ingresso pioggia tank 1 | 1 | DA CALCOLO | DN da BOM-007/RainMap |
| WST-IN-002 | ingresso pioggia tank 2 | 1 | DA CALCOLO | isolabile |
| WST-FILL-001 | ingresso fonte integrativa | 2 o collettore | DA PROGETTO | air-gap/backflow dove applicabile |
| WST-CALM-001 | calming inlet/diffusore | 2 | PREFERENZA | limitare sedimenti |
| WST-OVF-001 | overflow passivo tank 1 | 1 | OBBLIGATORIO | capacità pioggia di progetto |
| WST-OVF-002 | overflow passivo tank 2 | 1 | OBBLIGATORIO | indipendente da PLC |
| WST-OVF-SCR | protezione fauna/insetti overflow | 2 | DA CALCOLO | non strozzare portata |
| WST-SUC-001 | presa aspirazione processo | 2 | REQUISITO | sopra fondo/sedimento |
| WST-DRN-001 | scarico fondo | 2 | REQUISITO | drenaggio completo |
| WST-ISO-001 | valvole tank | 4+ | REQUISITO | full-bore |
| WST-XCON-001 | cross-connect tra tank | 1 | REQUISITO | normalmente isolabile |
| WST-SAMPLE | punti campione | 2 | REQUISITO | accessibili |
| WST-VENT | sfiati | 2 | REQUISITO | portata riempimento/svuotamento |
| WST-LVL-001 | radar livello tank 1 | 1 | PREFERENZA | 4–20 mA/Modbus |
| WST-LVL-002 | radar livello tank 2 | 1 | PREFERENZA | 4–20 mA/Modbus |
| WST-LL-001 | low-low tank 1 | 1 | OBBLIGATORIO | interlock pompe |
| WST-LL-002 | low-low tank 2 | 1 | OBBLIGATORIO | indipendente radar |
| WST-HH-001 | high-high tank 1 | 1 | REQUISITO | stop riempimento controllato |
| WST-HH-002 | high-high tank 2 | 1 | REQUISITO | overflow resta passivo |
| WST-TMP-001 | temperatura acqua | 1–2 | CANDIDATO | qualità/trend |
| WST-MAN-001 | accesso/manway | 2 | REQUISITO | OEM/sicurezza |
| WST-LAD-001 | scala/piattaforma | da modello | DA RFQ | lavoro in quota |
| WST-BASE-001 | fondazione/base tank 1 | 1 | DA GEOTECNICA/OEM | costo separato |
| WST-BASE-002 | fondazione/base tank 2 | 1 | DA GEOTECNICA/OEM | drenaggio perimetrale |
| WST-DRA-001 | drenaggio area | 1 package | REQUISITO | perdita/overflow sicuri |
| WST-FLS-001 | first flush/pre-screen | coord. BOM-007 | REQUISITO | upstream |
| WST-PLC-001 | integrazione PLC | 1 package | REQUISITO | livelli/allarmi/local |
| WST-SP-001 | kit riparazione liner | 1/tipo | PREFERENZA | intervento rapido |
| WST-SP-002 | guarnizioni/passaparete | 1 lotto | RICAMBIO | standardizzare |
| WST-SP-003 | livellostato low-low | 1 | PREFERENZA | spare |
| WST-COM-001 | prova tenuta | 2 tank | OBBLIGATORIO | prima servizio |
| WST-COM-002 | calibrazione volume/livello | 2 | OBBLIGATORIO | curva livello-volume |
| WST-COM-003 | test overflow | 2 | OBBLIGATORIO | senza PLC |
| WST-COM-004 | test isolamento/crossfeed | 1 | OBBLIGATORIO | modalità degradata |
| WST-DOC-001 | as-built/manuali/garanzie | 1 lotto | OBBLIGATORIO | manutenzione |

## 2. Autonomia

A 30–35 m³/giorno, 300 m³ teorici = **8,6–10 giorni**. Non includono volume morto, qualità acqua, riserva operativa o reintegro.

## 3. Benchmark economici

### Bladder 2×150 m³

Labaronne Citaf 150 m³:

- €4.270 + IVA/cad;
- 2 unità = **€8.540 + IVA** di solo hardware;
- consegna pubblicata €1.000 + IVA nell'annuncio, da verificare per consegna combinata in FVG;
- base, raccordi, protezioni, montaggio e commissioning esclusi.

RL Distrib 150 m³: **€3.799 + IVA/cad** come secondo benchmark.

### Steel

Prezzo pubblico 200 m³: **€6.630 + IVA** per tank, trasporto/installazione esclusi.

ABEKO ~200 m³ utili: **€7.807 + IVA**, cover telo +€725 + IVA.

Tanks Direct UK 150.000 L: **£4.650 ex VAT**, Ø ~9,14 m × h ~2,29 m. Non convertito in euro e non usato come prezzo Italia.

### Attenzione ai nomi commerciali

Un tank ABEKO commercializzato come “150 m³” riporta **112 m³ utili** nella scheda pubblica. Il volume utile deve essere sempre verificato prima dell'ordine.

## 4. Fondazioni

Per tank Ø9,14 m, footprint ~65,6 m². Con 150 m³ d'acqua il carico medio dell'acqua è ~22,4 kPa, esclusa struttura/carichi locali.

Costo fondazione: `DA CALCOLO`. Riutilizzare il benchmark FVG C25/30 soltanto dopo volume calcestruzzo e armatura reali; non costruire budget da una platea inventata.

## 5. Volume utile

Prima di ordine registrare:

`V_utile = V_nominale - freeboard - fondo non prelevabile - volume morto`.

Se il requisito è **300 m³ utili**, 2×150 nominali potrebbero non bastare.

## 6. Captazione

Con 4.200 m²:

- 1 mm = 4,2 m³ teorici;
- 300 m³ richiedono 71,4 mm teorici;
- con resa 85% servono ~84 mm.

Overflow dimensionato da `i × A × C`, con intensità RainMap FVG del lotto.

## 7. Ridondanza

La baseline 2×150 permette:

- pulizia di un tank con l'altro operativo;
- isolamento contaminazione/perdita;
- manutenzione liner/accessori;
- gestione differenziata fonte/pioggia se utile.

Un solo tank da 300 m³ resta alternativa CAPEX ma non soddisfa lo stesso livello di continuità.

## 8. Normativa/standard

UNI EN 16941-1:2024 è riferimento corrente per progettazione, dimensionamento, installazione, identificazione, commissioning e manutenzione di sistemi di utilizzo acqua piovana non potabile. Resta necessario verificare obblighi locali/nazionali e autorizzazioni della fonte.

## 9. Gate

1. 300 m³ nominali vs utili;
2. bilancio acqua mensile e picco;
3. autonomia target;
4. fonte e reintegro;
5. lotto/geotecnica;
6. RainMap/superficie captata;
7. scenario tank;
8. fondazioni/accessi;
9. overflow e scarico;
10. interfaccia pompe/NPSH;
11. piano espansione;
12. preventivo installato completo.
