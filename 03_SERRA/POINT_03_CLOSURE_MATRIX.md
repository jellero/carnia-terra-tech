# Punto 03 — Matrice di chiusura Serra

**Aggiornato:** 17 settembre 2026  
**Scopo:** distinguere ciò che è progettualmente strutturato da ciò che resta bloccato da sito, crop card, calcoli o preventivi.

## 1. Stato generale

Il punto 03 è `RAFFINATO COME ARCHITETTURA / DA VALIDARE CON DATI REALI`.

Non è considerato esecutivo finché non sono chiusi terreno, carichi, geotecnica, layout, crop card, analisi acqua, dimensionamenti climatici/idraulici, mezzi e preventivi confrontabili.

## 2. Matrice

| Blocco | Stato | Cosa è chiuso | Cosa manca per validare |
|---|---|---|---|
| struttura portante | DA RFQ | requisiti, voci costo, carichi da dichiarare | lotto, neve/vento, geotecnica, shop drawing, peso acciaio, preventivi |
| fondazioni | BLOCCATO DAL LOTTO | famiglie alternative e voci costo | geotecnica, soluzione strutturale, quantità scavi/cls/armatura |
| copertura | CANDIDATI REALI | classe film, fissaggi, manutenzione, RFQ | geometria sviluppata, piano taglio, compatibilità sistema, offerta |
| schermi | CANDIDATI REALI | scenari energy/shade/doppio | fabbisogno climatico, shop drawing, meccanica, preventivo |
| aperture/reti | CANDIDATI REALI | attuatori, reti, logica controllo | area apribile, coppie, mesh per comparto, calcolo ventilazione |
| HAF | CANDIDATO | 24 working, modelli/prezzi, manutenzione | conferma layout/flussi, installazione elettrica/meccanica |
| fogging | DA CALCOLO | architetture, pompe/ugelli/prezzi, RFQ | analisi acqua, carico evaporativo, ugelli, metri linea, trattamento |
| supporti C1/C2 | DA CROP CARD | hook/spago/clip/canaline, formule e RFQ | steli/m², file, carichi high-wire, slab, pendenze |
| drenaggio fuori suolo | DA LAYOUT | sottobom e failure modes | geometria, portata, collettori, misura/gestione drenaggio |
| porte/comparti | DA LAYOUT/RFQ | scenari, hardware, sensori, RFQ | porte reali, AMR/mezzi, superfici divisori, dettagli passaparete |
| gronde/pluviali | DA CALCOLO IDRAULICO | sottobom, troppo-pieno fail-safe, RFQ | RainMap/site, area, intensità, diametri, scarico emergenza |
| cantiere/attrezzature | DA CRONOPROGRAMMA | buy-vs-rent, strumenti, DPI, prezzi benchmark, RFQ | metodo montaggio, giorni PLE, pesi colli, quantità consumabili, ore macchina |
| manutenzione | REQUISITO DEFINITO | principi e ricambi per sottosistema | frequenze finali da manuali/modelli scelti |
| sicurezza | REQUISITO DEFINITO | failure mode e fallback integrati | progetto sicurezza definitivo, procedure e formazione |

## 3. Cose che non devono essere riaperte senza motivo

Sono principi consolidati:

- 6 comparti ~700 m² come baseline;
- progettazione fail-safe locale;
- no cloud dependency per funzioni vitali;
- preventivi scomposti, niente forfait opachi;
- costo reale separato da costo eleggibile/contributo;
- manutenzione e ricambi come parte della scelta;
- niente dimensionamenti strutturali/idraulici inventati prima del lotto;
- niente acquisti grant-sensitive prima dei gate corretti;
- montaggio proprio valorizzato economicamente, non considerato gratuito.

## 4. Dipendenze che sbloccano più voci insieme

### Lotto reale
Sblocca: neve/vento locale, fondazioni, drenaggi, gronde/pluviali, accessi cantiere, spazio mezzi, rete/energia, acqua.

### Crop card C1/C2
Sblocca: steli, high-wire, hook/clip/spago, gutter, drenaggio, carichi sospesi e parte della manodopera.

### Layout esecutivo serra
Sblocca: porte, divisori, aperture, metri cavi/tubi, posizioni HAF, schermi, fogging, percorsi AMR.

### Analisi acqua
Sblocca: fogging e in seguito filtrazione/fertirrigazione.

### Preventivi struttura
Sblocca: peso acciaio, dettaglio fondazioni, cronoprogramma montaggio, attrezzature/PLE, trasporti e realistica stima ore uomo.

## 5. Condizione di chiusura del punto 03

Il punto 03 potrà passare a `VALIDATO / PRE-ORDINABILE` solo quando:

1. il lotto supera il punto 01;
2. esiste rilievo e layout esecutivo;
3. carichi e geotecnica sono disponibili;
4. struttura/fondazioni sono calcolate;
5. C1/C2 hanno crop card sufficientemente chiuse;
6. analisi acqua è disponibile;
7. ventilazione/schermi/fogging sono dimensionati;
8. porte/gronde/pluviali sono dimensionati;
9. BOM-001…008 hanno quantità reali o formule risolte;
10. almeno offerte comparabili sostituiscono i principali benchmark;
11. cronoprogramma e piano cantiere sono coerenti;
12. CAPEX serra è ricostruito bottom-up con contingenza esplicita.

Fino ad allora il punto 03 è una base di progettazione completa, non un progetto esecutivo.