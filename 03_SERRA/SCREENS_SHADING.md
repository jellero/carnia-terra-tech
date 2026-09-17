# Carnia TerraTech — Thermal & Shading Screens

**Aggiornato:** 17 settembre 2026  
**Stato:** `REQUISITO DEFINITO / CANDIDATI REALI IDENTIFICATI / SISTEMA COMPLETO DA PREVENTIVARE`.

BOM economica collegata: `19_BOM_PRODOTTI_FORNITORI/SERRA_SCHERMI_TERMICI_OMBREGGIANTI.md`.

## 1. Obiettivo

Gli schermi devono ridurre dispersioni termiche quando utile, limitare eccesso di radiazione e permettere una gestione climatica differenziata senza togliere luce inutilmente alle colture.

## 2. Strategia attuale

Priorità iniziale:

- C1 pomodoro;
- C2 peperone;
- C6 basilico/vivaio/jolly.

Area nominale iniziale: **~2.100 m² a terra**. La superficie tessuto reale dipende da geometria, campate, pieghe, sovrapposizioni e overhang e viene calcolata da shop drawing.

La struttura deve essere predisposta, se economicamente ragionevole, per estensione futura agli altri comparti e deve essere verificata anche per l'eventuale secondo livello di schermo.

## 3. Risultato della ricerca di mercato 17/09/2026

Sono state identificate due famiglie funzionali distinte.

### Energy screen trasparente

Candidati:

- **Ridder RES 10+ FR (5 mm)** — 49% energy saving dichiarato, 11% shade diretto, flame retardant;
- **Svensson LUXOUS 1147 FR** — 47% energy saving dichiarato, 11% shade diretto con metodo Svensson / 15% NEN 2675, flame retardant.

Questa famiglia privilegia isolamento e trasmissione della luce; non è uno schermo estivo forte.

### Shade/diffusion screen aperto

Candidati:

- **Ridder RLD 45 FR O** — 46% shade diretto, 50% diffuso, 18% energy saving, struttura aperta, flame retardant;
- **Svensson HARMONY 5220 O FR** — 52% shade diretto con metodo Svensson / 59% NEN 2675, 20% energy saving, struttura aperta, flame retardant.

Questa famiglia privilegia controllo radiazione, diffusione e ventilazione attraverso lo schermo.

## 4. Architetture da confrontare

Non viene scelta oggi una soluzione unica. L'RFQ deve quotare tre scenari:

1. **S1 energy-first** — un livello trasparente FR su C1/C2/C6;
2. **S2 shade-first** — un livello aperto diffondente/ombreggiante FR su C1/C2/C6;
3. **S3 doppio schermo** — energy screen + shade/diffusion indipendenti.

La scelta finale dipende da clima reale, copertura, ventilazione, carico termico, colture e CAPEX/OPEX.

## 5. Dati da richiedere per ogni telo

- trasmissione luminosa diretta/diffusa;
- percentuale ombreggiamento con metodo dichiarato;
- risparmio energetico dichiarato e metodo;
- comportamento all'umidità/condensa;
- permeabilità all'aria;
- peso;
- reazione al fuoco e certificazioni applicabili;
- durata attesa;
- garanzia;
- metodo di pulizia;
- compatibilità con struttura e sistema di traino;
- larghezze/rotoli disponibili;
- cuciture e finiture;
- prezzo €/m² e sfrido;
- lead time.

## 6. Meccanica

La BOM non contiene solo il telo. Separare:

- telo/screen;
- overhang/pelmet per tenuta laterale;
- fili/monofilamenti di supporto;
- fili guida;
- profili;
- clips/ganci;
- barre di trazione;
- tubi/alberi di comando;
- riduttori/motoriduttori;
- cremagliere/pignoni/push-pull;
- cuscinetti/supporti;
- finecorsa;
- feedback posizione;
- staffe;
- bulloneria;
- tensionatori;
- quadro/protezioni;
- sezionatori locali;
- cablaggio;
- posa;
- commissioning;
- ricambi.

## 7. Motorizzazione candidata

La famiglia **Ridder RW45** è un candidato tecnico da dimensionare. Ridder dichiara versioni fino a 120 Nm, motori IP55, finecorsa integrati e varianti mono/trifase.

Un benchmark retail corrente trovato per una variante RW45 230 V single-drum, 0,09 kW, 120 Nm, SKU 531110 è **£598**. È solo un riferimento di prezzo per il motoriduttore: la configurazione single-drum non viene assunta come corretta per Carnia TerraTech.

È stato trovato anche un limit switch set RW45 4 A SKU 501105 a **£70**. Compatibilità da verificare con la variante finale.

## 8. Controllo

Per ogni comparto/livello:

- comando locale;
- comando PLC;
- posizione reale o feedback equivalente;
- finecorsa indipendenti;
- protezione sovraccarico;
- strategie giorno/notte;
- logiche su temperatura, radiazione e umidità;
- fallback in caso di perdita comunicazione;
- allarme inceppamento/mancato movimento;
- comportamento definito in blackout.

Il server/cloud non è necessario per l'azione locale di sicurezza.

## 9. Manutenzione

Prevedere già a progetto:

- accesso ai motori;
- sostituzione cavi/fili;
- retensionamento;
- pulizia;
- sostituzione del telo senza smontare impianti permanenti;
- ispezione dei supporti;
- prova periodica finecorsa;
- controllo allineamento trasmissione;
- storico ore/cicli;
- ricambi critici in funzione del lead time.

## 10. Gate successivo

Il sottosistema passa da `CANDIDATO` a `DA PREVENTIVARE` pieno quando sono disponibili:

- geometria esecutiva delle campate;
- punti di supporto e carichi ammessi;
- schema di apertura/ventilazione;
- decisione se predisporre uno o due livelli;
- specifica delle tre alternative S1/S2/S3.

Il prezzo completo deve essere confrontato come sistema installato, mai come solo tessuto.
