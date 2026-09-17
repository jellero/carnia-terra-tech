# Carnia TerraTech — Serra

**Aggiornato:** 17 settembre 2026  
**Stato:** `RAFFINATO COME ARCHITETTURA / DA DIMENSIONARE SUL LOTTO REALE / DA PREVENTIVARE`.

## 1. Obiettivo

La serra deve essere un'infrastruttura produttiva modulare, riparabile, sicura e piacevole da usare. Non viene trattata come un semplice involucro: deve integrare struttura, clima, colture, logistica, manutenzione, automazione e crescita futura.

## 2. Geometria di lavoro

Rimane come riferimento:

- circa **4.200 m² produttivi**;
- **6 comparti da circa 700 m²**;
- working geometry circa **20 × 35 m per comparto**;
- corridoio tecnico centrale circa 4 m;
- accessi compatibili con AMR, carrelli, transpallet e manutenzione;
- fascia esterna tecnica libera almeno 3–4 m, maggiore dove serve transito mezzi.

Queste dimensioni sono requisiti di concept, non quote esecutive. Geometria campate, passo colonne, altezza gronda/colmo, porte e fondazioni si chiudono solo con lotto, colture, macchine e calcolo strutturale reali.

## 3. Principi

- ogni comparto deve avere indipendenza funzionale per clima, irrigazione, schermi, aperture, sensori e allarmi;
- nessuna modifica agronomica deve richiedere di rifare la struttura principale;
- i carichi di fili coltura, schermi, canaline, tubazioni, ventilatori, sensori e manutenzione devono essere considerati nel progetto strutturale;
- i sistemi mobili devono avere modalità locale, finecorsa/protezioni e fallback coerente;
- la manutenzione futura deve essere possibile senza soluzioni improvvisate;
- struttura, involucro e impianti devono essere documentati as-built.

## 4. Regola economica

Non si stima il costo della serra moltiplicando un prezzo retail €/m² per 4.200 m². I benchmark servono solo per controllo di plausibilità.

Il costo definitivo deve derivare da preventivo riga per riga comprendente almeno:

- struttura portante;
- fondazioni/ancoraggi;
- zincatura/protezioni;
- copertura;
- profili e fissaggi copertura;
- testate;
- porte;
- gronde e pluviali;
- compartimentazioni;
- aperture;
- reti anti-insetto;
- schermi e motorizzazioni;
- accessori e bulloneria;
- trasporto;
- scarico;
- montaggio;
- mezzi di sollevamento;
- documentazione/calcoli;
- commissioning.

## 5. Documenti del blocco

- `STRUCTURE_FOUNDATIONS.md` — struttura, carichi, fondazioni e durabilità;
- `ENVELOPE_COVERING.md` — coperture, fissaggi, condensa e sostituzione;
- `OPENINGS_COMPARTMENTS.md` — ventilazione passiva, reti, porte e compartimentazione;
- `SCREENS_SHADING.md` — schermi termici/ombreggianti e motorizzazioni;
- `FOGGING_HUMIDITY.md` — fogging e integrazione con VPD/UR;
- `CROP_SUPPORTS_LOGISTICS.md` — carichi coltura, corsie, AMR e interfacce;
- `MAINTENANCE_SAFETY.md` — ispezioni, accessi, sicurezza e ricambi;
- `RFQ_GREENHOUSE_STRUCTURE.md` — capitolato minimo da inviare ai fornitori;
- `BOM_REGISTER.md` — registro costi e stato delle singole voci;
- `OFFICIAL_SOURCES.md` — norme e fonti da ricontrollare.

## 6. Collegamento con BOM già esistente

La ventilazione HAF è già trattata in:

`19_BOM_PRODOTTI_FORNITORI/SERRA_HAF_VENTILATION.md`

Il dimensionamento finale dei 24 HAF resta subordinato al layout reale, alle altezze e alla verifica del movimento d'aria.

## 7. Gate di chiusura

Il punto 03 potrà diventare `VALIDATO` solo quando esistono:

- lotto reale;
- dati neve/vento/sisma e geotecnica;
- layout esecutivo;
- calcolo strutturale;
- almeno preventivi confrontabili per struttura e principali sistemi;
- BOM completa;
- piano montaggio;
- piano manutenzione;
- verifica integrazione con agronomia, acqua, termico, elettrico e logistica.
