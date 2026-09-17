# Carnia TerraTech — Punto 04: Acqua e fertirrigazione

**Aggiornato:** 17 settembre 2026  
**Stato:** `ARCHITETTURA DI BASE APERTA / BOM-013 DISTRIBUZIONE IRRIGUA SVILUPPATA / FILTRAZIONE, POMPE E DOSAGGIO DA SVILUPPARE`.

## 1. Obiettivo

Il sistema deve distribuire acqua e soluzione nutritiva in modo misurabile, uniforme, manutenibile e indipendente per comparto/settore.

Principi:

- 6 comparti indipendenti;
- working architecture 4 settori per comparto = 24 settori, da confermare con layout e crop card;
- ogni settore isolabile e comandabile localmente;
- nessuna portata viene fissata senza numero reale di emettitori/linee;
- niente riuso automatico del drenaggio prima di validazione tecnica, sanitaria e normativa;
- logica vitale in PLC locale, non dipendente dal cloud;
- misure di pressione, portata e volume per diagnosticare intasamenti, perdite e mancata erogazione.

## 2. Architettura working

`serbatoi/fonte -> filtrazione -> pompe principali 1+1 -> fertirrigazione -> collettore principale -> 6 collettori comparto -> 4 settori/comparto -> linee PE/dripline -> gocciolatori/capillari/punti goccia`

Il package BOM-013 copre dalla distribuzione post-fertirrigazione fino alla pianta. Filtrazione, pompe principali, dosaggio e serbatoi fertilizzanti sono package successivi.

## 3. Strategie per coltura

### C1 pomodoro / C2 peperone fuori suolo

Candidato preferenziale da RFQ:

- gocciolatore on-line autocompensante;
- variante anti-drenaggio LCNL/HCNL per irrigazione pulsata;
- microtubo 3/5 mm;
- punto goccia/picchetto nel substrato;
- linea PE cieca dimensionata per portata e perdite.

Candidato reale: Netafim PCJ / PCJ PRO. Portata 2 l/h è solo un riferimento iniziale, non una selezione definitiva.

### C3–C5 leafy

Non si forza lo stesso sistema del pomodoro. Confrontare:

- dripline autocompensante permanente;
- ala leggera/monostagionale se compatibile con il ciclo;
- linee riutilizzabili su letti/bench;
- eventuale subirrigazione o altra architettura solo se giustificata.

La scelta dipende da letto, densità, ciclo, meccanizzazione e igiene.

### C6 basilico / vivaio / prove

Richiede massima flessibilità. Predisporre collettori e attacchi che permettano sia gocciolatori singoli sia linee/dripline senza rifare il comparto.

## 4. Settori

Working architecture: **24 settori**, 4 per comparto.

Per ogni settore:

- valvola manuale di isolamento;
- elettrovalvola normalmente chiusa;
- regolazione pressione dove necessaria;
- punto misura pressione;
- flush di fine linea accessibile;
- feedback comando/stato dove economicamente sensato;
- capacità di funzionamento/manual override in emergenza.

La portata di settore si calcola da:

`Qsettore = numero emettitori × portata emettitore + eventuali linee aggiuntive`

Poi si dimensionano DN, elettrovalvola, regolatore e collettore con margine tecnico, non viceversa.

## 5. Misure minime

Preferenza progettuale:

- portata totale centrale;
- portata per comparto;
- pressione a monte distribuzione;
- pressione per comparto e/o settore critico;
- volume irrigato per settore derivato da contatore/tempo solo se l'accuratezza è validata;
- allarme `valvola comandata + portata assente`;
- allarme `valvola chiusa + portata presente`;
- trend pressione/portata per riconoscere filtro sporco, perdita o occlusione.

## 6. Flush e igiene

Ogni linea deve poter essere:

- lavata senza smontaggi distruttivi;
- drenata quando necessario;
- campionata;
- isolata in caso di contaminazione/guasto;
- identificata con comparto/settore.

Prevedere valvole di fine linea o collettori di flush accessibili. Evitare terminali nascosti sotto coltura senza accesso.

## 7. Pressione e filtrazione

Il PCJ candidato richiede filtrazione raccomandata 120 mesh / 130 micron e lavora, a seconda della variante, in un range tipico circa 0,7–4 bar. Questi dati guidano il package filtrazione successivo ma non sostituiscono l'analisi acqua.

Se sabbia, limo, ferro o materiale organico lo richiedono, il pretrattamento dovrà essere aggiunto a monte.

## 8. Materiali e tubazioni

Distinguere:

- PE di dorsale/collettore: più robusto, pressione nominale coerente con pompa e transitori;
- PE cieco su file con gocciolatori inseriti: spessore compatibile con il barb del gocciolatore;
- microtubo: solo collegamento finale, non dorsale;
- dripline: selezione separata per leafy.

Il PN4 agricolo è solo benchmark economico per linee a bassa pressione; non usarlo automaticamente come dorsale sempre in pressione.

## 9. Failure modes

- gocciolatore ostruito;
- capillare piegato/staccato;
- picchetto uscito dal substrato;
- linea PE forata/crepata;
- elettrovalvola bloccata aperta o chiusa;
- regolatore fuori taratura;
- flush dimenticato aperto;
- pressione insufficiente;
- colpo d'ariete;
- errore ricetta/settore;
- sensore portata/pressione guasto;
- perdita bus/PLC.

Fallback: isolamento manuale del settore, irrigazione manuale temporanea dove praticabile, ricambi standardizzati a scaffale.

## 10. Package sviluppati

- `IRRIGATION_DISTRIBUTION.md` — architettura e criteri;
- `RFQ_IRRIGATION_DISTRIBUTION.md` — richiesta offerte;
- `19_BOM_PRODOTTI_FORNITORI/ACQUA_IRRIGAZIONE_DISTRIBUZIONE.md` — BOM-013;
- `22_FONTI_NORME_PREVENTIVI/ACQUA_IRRIGAZIONE_SOURCES.md` — fonti/prezzi.

## 11. Gate

BOM-013 diventa ordinabile solo con:

- layout file/letti/bench C1–C6;
- numero piante/steli e punti acqua;
- portata target per punto;
- durata/frequenza impulsi;
- drenaggio target;
- analisi acqua e filtrazione;
- pressione disponibile a valle fertirrigazione;
- perdite di carico;
- scelta 24 settori confermata o modificata;
- preventivi comparabili e prova di uniformità.