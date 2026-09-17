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

Package: BOM-001 HAF; BOM-002 schermi; BOM-003 aperture/reti; BOM-004 copertura; struttura/fondazioni; BOM-005 fogging; BOM-006 supporti+drenaggio; BOM-007 porte/comparti/gronde; BOM-008 attrezzatura cantiere.

Matrice: `03_SERRA/POINT_03_CLOSURE_MATRIX.md`.

## 7. Stato punto 04 — Acqua e fertirrigazione

**Stato: ARCHITETTURA IN SVILUPPO / BOM-013…015 SVILUPPATE / DOSAGGIO, SERBATOI E ACCUMULO DA SVILUPPARE.**

Documenti principali:

- `04_ACQUA_E_FERTIRRIGAZIONE/README.md`;
- `IRRIGATION_DISTRIBUTION.md` + RFQ;
- `FILTRATION_ARCHITECTURE.md` + RFQ;
- `PUMP_STATION_ARCHITECTURE.md` + `RFQ_MAIN_IRRIGATION_PUMPS.md`;
- BOM-013/014/015 in `19_BOM_PRODOTTI_FORNITORI/`;
- fonti dedicate in `22_FONTI_NORME_PREVENTIVI/`.

### BOM-013 — distribuzione irrigua

Working 6 comparti × 4 settori = 24 settori, da validare.

C1/C2/C6: Netafim PCJ/LCNL/HCNL candidato; 2 l/h non congelato. C3–C5: dripline/ala da selezionare per letto e meccanizzazione.

Benchmark: PCJ 1.000 pz €261 + IVA; microtubo €38/200 m + IVA; punti goccia €95/1.000 + IVA; 1.000 punti completi ~€470–515 + IVA prima di dorsali/valvole/posa.

### BOM-014 — filtrazione

Requisito working 120 mesh / ~130 µm.

Candidati:

- Arkal Leader €182 + IVA;
- Dual €241 + IVA;
- Spin-Klin singolo €2.574 + IVA;
- Spin-Klin doppio €4.321 + IVA;
- ScreenGuard da €2.988 + IVA;
- idrociclone 2" €363 + IVA.

Con tank atmosferico la filtrazione fine automatica va normalmente sul lato pressurizzato delle pompe, perché il controlavaggio richiede pressione. Griglia/strainer grossolano resta lato aspirazione se necessario.

### BOM-015 — pompe principali irrigazione 1+1

Baseline: **2×100% duty**, una pompa in servizio e una standby, un VFD per pompa, failover locale automatico.

Candidato di classe Grundfos CR 10-6:

- Q nominale 10 m³/h;
- H nominale 48,3 m, Hmax 61,2 m;
- 2,2 kW 3~;
- prezzo retail IT €1.946,78 IVA incl./cad;
- due pompe ~€3.893,56 IVA incl., solo pompe.

VFD benchmark Danfoss FC-51 2,2 kW: €895,30 + IVA/cad su RS Italia.

Sensori: WIKA A-10 da €133,95 + IVA; Danfoss MBS3000 0–10 bar ~€195,44 + IVA.

Alternativa OEM: Grundfos Hydro Multi-E 2 CRE 10-3 U2 €12.185 listino 2026; 10-5 U2 €13.323, condizioni/IVA da confermare.

Duty point e taglia restano bloccati da Q simultanea, controlavaggio, perdite, pressione richiesta e NPSH.

### Gate punto 04

Restano necessari:

- layout/portate C1–C6;
- fonte/analisi acqua;
- quote tank/tech barn e NPSH;
- filtrazione finale/controlavaggio;
- duty point pompe e RFQ;
- **pompe dosatrici e miscelazione A/B/acido**;
- serbatoi fertilizzanti;
- trattamento/disinfezione se necessario;
- drenaggio/riuso;
- accumulo acqua 300 m³;
- backup elettrico;
- commissioning.

## 8. Stato punto 05 — Termico e clima

**Stato: ARCHITETTURA STRUTTURATA / BOM-009…012 SVILUPPATE / VALIDAZIONE BLOCCATA DA LOTTO, CARICHI E RFQ.**

BOM: 009 distribuzione idronica; 010 accumulo/primario/HX; 011 PDC modulari 3+1; 012 boost/deumidificazione/emergenza.

Matrice: `05_TERMICO_E_CLIMA/POINT_05_CLOSURE_MATRIX.md`.

## 9. R&D trasversale — laser, vision e manutenzione robotica

Documento: `07_AUTOMAZIONE_DATI_AI/LASER_ROBOTICS_RND.md`.

Stato: `R&D CANDIDATO / NON BASELINE CAPEX`.

Potatura robotica vision + microforbice/cutter baseline R&D; laser confinato; controllo insetti con `TARGET / UTILE-PROTETTO / INCERTO`, nessun tiro su incerto.

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
- BOM-013 distribuzione irrigua;
- BOM-014 filtrazione acqua;
- **BOM-015 pompe principali irrigazione 1+1**.

### Prossimo package

**BOM-016 — pompe dosatrici / fertirrigazione A-B-acido:** pompe, portata/min-max turndown, materiali chimici, valvole iniezione, calibrazione, miscelazione, EC/pH, interlock, spill containment, ricambi e costi.

### Coda successiva

1. pompe dosatrici/fertirrigazione;
2. serbatoi fertilizzanti;
3. accumulo acqua 300 m³;
4. moduli FV e inverter;
5. AMR;
6. sollevatore/mezzo multifunzione;
7. robot tagliaerba;
8. sistema pulizia area galline;
9. celle frigorifere;
10. attrezzatura raccolta e packaging;
11. pergolato/vite/area relax;
12. fattoria didattica;
13. spaccio automatico 24/7;
14. centro trasformazione conto terzi: capacity model + BOM succo/confetture + CAPEX/OPEX + domanda locale.

La sequenza può cambiare quando una dipendenza tecnica rende necessario anticipare un blocco.