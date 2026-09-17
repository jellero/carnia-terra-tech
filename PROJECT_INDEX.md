# Carnia TerraTech — Project Index

**Ruolo:** indice operativo e mappa di copertura del progetto.  
**Aggiornato:** 17 settembre 2026.

## 1. Scopo

Il repository deve permettere di progettare l'azienda senza lasciare aree scoperte. Ogni decisione deve essere collegata a costi, manutenzione, sicurezza, dipendenze, crescita e qualità della vita.

## 2. Struttura target

- `00_VISIONE_E_PRINCIPI/` — missione, KPI, guardrail e decision gates;
- `01_MASTERPLAN_E_TERRENO/` — lotto, vincoli, accessi, drenaggi, espansioni;
- `02_AGRONOMIA/` — colture, calendari, rese, vite, luppolo, siepi, outdoor;
- `03_SERRA/` — struttura, comparti, coperture, aperture, schermi, HAF, fogging, supporti coltura, drenaggi, porte, recupero pioggia e cantiere;
- `04_ACQUA_E_FERTIRRIGAZIONE/` — fonte, accumulo, filtri, pompe, dosaggio, distribuzione, drenaggio;
- `05_TERMICO_E_CLIMA/` — carico termico, PDC, accumulo, distribuzione, boost, deumidificazione, emergenza;
- `06_ENERGIA_ELETTRICA_FV/` — FV, inverter, rete, UPS, generatore, EMS;
- `07_AUTOMAZIONE_DATI_AI/` — PLC, I/O, sensori, rete, edge, vision, cybersecurity e R&D robotica/laser;
- `08_MACCHINE_E_LOGISTICA/` — AMR, sollevatore, piattaforme, raccolta, carrelli;
- `09_TECH_BARN_E_POST_RACCOLTA/` — celle, confezionamento, officina, magazzini e centro trasformazione conto terzi;
- `10_BENESSERE_FATTORIA_E_SERVIZI/` — pergolato, verde, fattoria didattica, robot di servizio, spaccio 24/7;
- `11_VERMICOMPOST_E_CICLI_MATERIA/`;
- `12_SICUREZZA_E_CONTINUITA/`;
- `13_MANUTENZIONE_E_RICAMBI/`;
- `14_ORGANIZZAZIONE_DEL_LAVORO/`;
- `15_MERCATO_E_VENDITE/`;
- `16_SOCIETA_FINANZA_E_CONTRIBUTI/`;
- `17_SOSTENIBILITA_PERSONALE_E_LANCIO/`;
- `18_CAPEX_OPEX_CASHFLOW/`;
- `19_BOM_PRODOTTI_FORNITORI/`;
- `20_CANTIERE_E_CRONOPROGRAMMA/`;
- `21_RISCHI_DECISIONI_OPEN_POINTS/`;
- `22_FONTI_NORME_PREVENTIVI/`.

## 3. Stato punto 00 — Visione e principi

**Stato: RAFFINATO / BASE DI GOVERNO DEL PROGETTO.**

## 4. Stato punto 01 — Terreno e masterplan

**Stato: RAFFINATO / IN ATTESA DI LOTTO REALE.**

Il metodo diventa `VALIDATO` solo con lotto reale che supera due diligence, masterplan test e costo totale del sito.

## 5. Stato punto 02 — Agronomia

**Stato: RAFFINATO / PORTAFOGLIO E METODO DEFINITI / DATI COLTURALI DA VALIDARE.**

Working portfolio: C1 pomodoro premium; C2 peperone; C3 lattuga; C4 lattuga/leaf flessibile; C5 baby leaf/rucola/spinacio; C6 basilico + vivaio + prove.

## 6. Stato punto 03 — Serra

**Stato: RAFFINATO COME ARCHITETTURA / BOM-001…008 STRUTTURATE / VALIDAZIONE BLOCCATA DA DATI REALI.**

Package sviluppati: BOM-001 HAF; BOM-002 schermi; BOM-003 aperture/reti; BOM-004 copertura; struttura/fondazioni; BOM-005 fogging; BOM-006 supporti+drenaggio; BOM-007 porte/comparti/gronde; BOM-008 attrezzatura cantiere.

Matrice: `03_SERRA/POINT_03_CLOSURE_MATRIX.md`.

## 7. Stato punto 04 — Acqua e fertirrigazione

**Stato: ARCHITETTURA APERTA / BOM-013 DISTRIBUZIONE IRRIGUA SVILUPPATA / FILTRAZIONE, POMPE E DOSAGGIO DA SVILUPPARE.**

Documenti:

- `04_ACQUA_E_FERTIRRIGAZIONE/README.md`;
- `04_ACQUA_E_FERTIRRIGAZIONE/IRRIGATION_DISTRIBUTION.md`;
- `04_ACQUA_E_FERTIRRIGAZIONE/RFQ_IRRIGATION_DISTRIBUTION.md`;
- `19_BOM_PRODOTTI_FORNITORI/ACQUA_IRRIGAZIONE_DISTRIBUZIONE.md` — BOM-013;
- `22_FONTI_NORME_PREVENTIVI/ACQUA_IRRIGAZIONE_SOURCES.md`.

### BOM-013 — distribuzione irrigua

Working architecture: 6 comparti × 4 settori = **24 settori**, da confermare con crop card/layout.

C1/C2/C6: candidato Netafim PCJ, con preferenza da RFQ per LCNL/HCNL anti-drenaggio nelle irrigazioni pulsate. Il 2 l/h è riferimento, non portata congelata.

Benchmark correnti:

- PCJ standard 2 l/h: €261 + IVA / 1.000 pz;
- microtubo PE 5 mm: €38 + IVA / 200 m;
- punto goccia 14 cm: €95 + IVA / 1.000;
- asta guidata 3/5: €140 + IVA / 1.000 nella configurazione osservata;
- benchmark 1.000 punti standard con 0,6 m microtubo: ~€470–515 + IVA prima di PE principale/valvole/posa;
- Bermad 1" 24 VAC: ~€23,15–28,53 IVA incl. benchmark;
- PE PN4 agricolo Ø25 ~€40/100 m e Ø32 ~€55/100 m IVA incl., solo benchmark per linee a bassa pressione;
- regolatori Netafim da €9,89–18 + IVA per 3/4", taglie maggiori da calcolo.

Per C3–C5 non si forza il punto goccia per pianta: confrontare dripline PC/pluristagionale e soluzione leggera compatibile con letti e meccanizzazione.

Gate principali:

- piante/steli/letto e numero punti acqua;
- q emettitore e impulsi;
- pressione post-fertirrigazione;
- analisi acqua/filtrazione;
- portate/perdite di carico;
- conferma numero settori;
- scelta misura per comparto vs per settore;
- prova di uniformità.

## 8. Stato punto 05 — Termico e clima

**Stato: ARCHITETTURA STRUTTURATA / BOM-009…012 SVILUPPATE / VALIDAZIONE BLOCCATA DA LOTTO, CARICHI E RFQ.**

Documenti principali in `05_TERMICO_E_CLIMA/`, inclusa `POINT_05_CLOSURE_MATRIX.md`.

BOM:

- BOM-009 distribuzione idronica;
- BOM-010 accumulo/primario/HX;
- BOM-011 PDC modulari 3+1;
- BOM-012 boost/deumidificazione/emergenza.

Gate: lotto/meteo, carico C1–C6, PDC sottozero/defrost, P&ID, terminali, tank/HX/glicole/espansione, umidità/deumidificazione, backup e RFQ.

## 9. R&D trasversale — laser, vision e manutenzione robotica

Documento: `07_AUTOMAZIONE_DATI_AI/LASER_ROBOTICS_RND.md`.

Stato: `R&D CANDIDATO / NON BASELINE CAPEX`.

Potatura robotica con vision + microforbice/cutter come baseline R&D; laser solo confinato; controllo insetti laser con classificazione `TARGET / UTILE-PROTETTO / INCERTO`, nessun tiro su incerto.

## 10. Modulo futuro — centro trasformazione conto terzi

Documento: `09_TECH_BARN_E_POST_RACCOLTA/CENTRO_TRASFORMAZIONE_CONTO_TERZI.md`.

Stato: `MODULO FUTURO AD ALTO POTENZIALE / DA BUSINESS CASE / NON ANCORA NEL CAPEX BASE`.

## 11. Metodo BOM obbligatorio

Per ogni oggetto/sottosistema: funzione, requisiti, quantità, alternative, prezzo, IVA/trasporto, installazione, consumi, manutenzione, ricambi, vita utile, sicurezza, failure mode, fallback, contributi, dipendenze, espansione e stato decisionale.

## 12. Stato attuale dei grandi blocchi

I file in `docs/` restano sorgenti durante la migrazione. Restano nel perimetro robot tagliaerba, automazione galline, fattoria didattica, spaccio 24/7, pergolati/vite/verde/relax, sostenibilità personale, R&D robotica/laser e centro trasformazione conto terzi.

## 13. Sequenza BOM

### Già strutturate

- Serra BOM-001…008;
- BOM-009 distribuzione termica;
- BOM-010 accumulo/primario/HX;
- BOM-011 PDC 3+1;
- BOM-012 boost/deumidificazione/emergenza;
- **BOM-013 distribuzione irrigua/gocciolatori/settori**.

### Prossimo package

**BOM-014 — filtrazione acqua:** analisi acqua, prefiltrazione, idrociclone condizionale, filtri dischi/rete, 1+1 o bypass, Δp, controlavaggio, valvole, scarichi, sensori, ricambi e costo.

### Coda successiva

1. filtrazione acqua;
2. pompe principali irrigazione;
3. pompe dosatrici;
4. serbatoi fertilizzanti;
5. accumulo acqua 300 m³;
6. moduli FV e inverter;
7. AMR;
8. sollevatore/mezzo multifunzione;
9. robot tagliaerba;
10. sistema pulizia area galline;
11. celle frigorifere;
12. attrezzatura raccolta e packaging;
13. pergolato/vite/area relax;
14. fattoria didattica;
15. spaccio automatico 24/7;
16. centro trasformazione conto terzi: capacity model + BOM succo/confetture + CAPEX/OPEX + domanda locale.

La sequenza può cambiare quando una dipendenza tecnica rende necessario anticipare un blocco.
