# Carnia TerraTech — Punto 04: Acqua e fertirrigazione

**Aggiornato:** 17 settembre 2026  
**Stato:** `ARCHITETTURA IN SVILUPPO / BOM-013 DISTRIBUZIONE E BOM-014 FILTRAZIONE SVILUPPATE / POMPE E DOSAGGIO DA SVILUPPARE`.

## 1. Obiettivo

Il sistema deve distribuire acqua e soluzione nutritiva in modo misurabile, uniforme, manutenibile e indipendente per comparto/settore.

Principi:

- 6 comparti indipendenti;
- working 4 settori per comparto = 24 settori, da confermare con layout e crop card;
- ogni settore isolabile e comandabile localmente;
- nessuna portata fissata senza numero reale di emettitori/linee;
- niente riuso automatico del drenaggio prima di validazione tecnica, sanitaria e normativa;
- logica vitale in PLC locale;
- misure di pressione, portata e volume per diagnosticare intasamenti, perdite e mancata erogazione;
- filtrazione scelta sulla qualità reale dell'acqua e non soltanto sulla mesh.

## 2. Architettura working

`fonte/accumulo -> eventuale separatore sabbia -> filtrazione primaria -> filtrazione fine/sicurezza -> pompe principali 1+1 -> fertirrigazione -> collettore principale -> 6 collettori comparto -> working 24 settori -> linee PE/dripline -> emettitori`

BOM-013 copre la distribuzione post-fertirrigazione fino alla pianta. BOM-014 copre pretrattamento e filtrazione meccanica. Pompe, dosaggio e serbatoi fertilizzanti sono package successivi.

## 3. Distribuzione irrigua — BOM-013

### C1/C2/C6

Candidato preferenziale:

- gocciolatore on-line autocompensante;
- variante anti-drenaggio LCNL/HCNL per irrigazione pulsata;
- microtubo 3/5 mm;
- punto goccia/picchetto;
- linea PE cieca dimensionata.

Candidato reale: Netafim PCJ / PCJ PRO. 2 l/h è riferimento iniziale, non selezione definitiva.

### C3–C5 leafy

Confrontare dripline autocompensante permanente, ala leggera/monostagionale e altre configurazioni coerenti con letto, ciclo e futura meccanizzazione.

### Settori

Working: **24 settori**, 4 per comparto. Per ciascuno: isolamento manuale, elettrovalvola NC, eventuale regolazione pressione, misura/presa pressione, flush e integrazione PLC.

Formula base:

`Qsettore = numero emettitori × portata emettitore + eventuali linee aggiuntive`

## 4. Filtrazione — BOM-014

Requisito emettitori working: **120 mesh / circa 130 µm**.

La filtrazione finale dipende da:

- fonte acqua;
- SST/turbidità;
- sabbia;
- limo/argilla;
- organico/alghe;
- Fe/Mn;
- pH/EC/durezza/alcalinità;
- portata e pressione di processo;
- portata/pressione disponibile per controlavaggio.

### Scenari

- acqua buona: filtro manuale/automatico 120 mesh + sicurezza dove utile;
- pozzo con sabbia: idrociclone + filtro principale + sicurezza;
- acqua superficiale/organico: dischi automatici o media filtration + filtro secondario;
- sali/durezza/ferro disciolto: trattamento separato; la filtrazione meccanica non li rimuove.

### Candidati/prezzi correnti

- Netafim-Arkal 2" Leader manuale: **€182 + IVA**;
- Netafim-Arkal 2" Dual manuale: **€241 + IVA**, fino a 25 m³/h;
- Spin-Klin 2" singolo automatico: **€2.574 + IVA**, 20 m³/h nominali / 15 con acqua media qualità;
- Spin-Klin doppio DN80: **€4.321 + IVA**, 40 nominali / 30 media qualità;
- ScreenGuard automatico 2": **da €2.988 + IVA**, 25 m³/h max;
- idrociclone Arkal 2": **€363 + IVA**, range 15–25 m³/h.

Questi sono costi hardware, non impianto installato.

## 5. Ridondanza filtrazione

Confrontare:

- R0: singolo filtro + bypass;
- R1: due rami manuali isolabili;
- R2: automatico + filtro manuale di sicurezza/modalità degradata.

Preferenza progettuale verso R1/R2 se il TCO è ragionevole: la filtrazione non deve diventare single point of failure.

## 6. Controlavaggio

Il controlavaggio è un carico idraulico vero. Devono essere noti:

- portata;
- pressione minima;
- durata;
- volume/ciclo;
- frequenza;
- scarico;
- capacità residua per irrigazione.

Non assumere che la futura pompa principale possa sostenerlo senza calcolo.

## 7. Misure minime

- portata totale;
- pressione monte/valle filtrazione;
- Δp filtro;
- portata per comparto preferenziale;
- pressione comparti/settori critici;
- stato controlavaggio;
- allarme `valvola comandata + portata assente`;
- allarme `valvola chiusa + portata presente`;
- trend Δp/portata per manutenzione predittiva.

## 8. Flush e igiene

Ogni linea deve poter essere lavata, drenata, campionata, isolata e identificata. Gli scarichi di flush/controlavaggio devono essere accessibili e non generare allagamenti o erosioni.

## 9. Failure modes principali

- emettitore ostruito;
- capillare piegato/staccato;
- PE danneggiato;
- elettrovalvola bloccata;
- regolatore fuori taratura;
- filtro intasato o rotto;
- bypass aperto accidentalmente;
- controlavaggio fallito;
- idrociclone fuori range;
- biofilm/precipitati non risolti dalla sola filtrazione;
- sensore portata/pressione/Δp guasto;
- perdita PLC/bus.

Fallback: isolamento manuale di ramo/settore, modalità degradata filtrata, irrigazione temporanea manuale dove possibile e ricambi standardizzati.

## 10. Package sviluppati

- `IRRIGATION_DISTRIBUTION.md`;
- `RFQ_IRRIGATION_DISTRIBUTION.md`;
- `FILTRATION_ARCHITECTURE.md`;
- `RFQ_FILTRATION.md`;
- `19_BOM_PRODOTTI_FORNITORI/ACQUA_IRRIGAZIONE_DISTRIBUZIONE.md` — BOM-013;
- `19_BOM_PRODOTTI_FORNITORI/ACQUA_FILTRAZIONE.md` — BOM-014;
- `22_FONTI_NORME_PREVENTIVI/ACQUA_IRRIGAZIONE_SOURCES.md`;
- `22_FONTI_NORME_PREVENTIVI/ACQUA_FILTRAZIONE_SOURCES.md`.

## 11. Gate punto 04

Restano necessari:

- layout C1–C6;
- numero emettitori/portate;
- analisi acqua e fonte reale;
- pressione/portata disponibili;
- filtrazione/idrociclone/media filtration finali;
- requisiti controlavaggio;
- pompe principali 1+1;
- pompe dosatrici e miscelazione A/B/acido;
- serbatoi fertilizzanti;
- disinfezione/trattamento se necessario;
- drenaggio/riuso;
- accumulo acqua 300 m³;
- RFQ comparabili e commissioning.