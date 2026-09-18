# Procurement closure register — Carnia TerraTech

**Aggiornato:** 18 settembre 2026  
**Stato:** `WORKING REGISTER / RFQ INSTALLED ANCORA DA RACCOGLIERE`

## 1. Scopo

Unificare la fase 5 della closure:

`RFQ installati per i package ancora a prezzo RFQ`.

Il registro non sostituisce le BOM di dominio. Serve a evitare:
- richieste premature senza dati di progetto;
- preventivi non confrontabili;
- forfait senza separazione hardware/installazione/service;
- acquisti anticipati di tecnologia non validata;
- doppio conteggio CAPEX.

## 2. Classi procurement

| Classe | Significato |
|---|---|
| Q1 | RFQ tecnico/commerciale richiedibile già ora; alcuni dati sito possono restare come opzione |
| Q2 | RFQ utile solo dopo dati di lotto/layout/carico/crop card |
| Q3 | pilot/demo obbligatorio prima della scelta/acquisto |
| Q4 | futuro/separato dal CAPEX core |
| Q5 | servizio/professionista da quotare, non prodotto catalogo |

## 3. Registro

| Area | BOM | Package | Classe | Stato costo | Gate già documentati | Prossima evidenza procurement |
|---|---|---|---|---|---|---|
| Serra | 001–008 | struttura, coperture, comparti, aperture, HAF, fogging, supporti, drenaggi/porte | Q2 | benchmark + RFQ | lotto, masterplan, geotecnica, layout | 3 RFQ installati dopo sito definitivo |
| Termico | 009 | distribuzione idronica | Q2 | RFQ | carichi, P&ID, layout | RFQ installato con metri reali e perdite |
| Termico | 010 | accumulo/primario/HX | Q2 | benchmark + RFQ | carico termico, PDC, glicole, HX | RFQ scenari tank/HX installati |
| Termico | 011 | PDC 3+1 | Q1/Q2 | prezzo hardware trovato + RFQ installato | clima sito, A-7/A-10/A-15, defrost, carico | conferma OEM Italia + installed RFQ 3 unità |
| Termico | 012 | boost/deumidificazione/emergenza | Q1/Q2 | benchmark + RFQ | bilancio vapore, climate recipe | DryGair/Reventon + installazione separata |
| Acqua | 013 | distribuzione irrigua | Q2 | benchmark + RFQ | crop card, layout, Q simultanea | distinta linee/valvole e posa |
| Acqua | 014 | filtrazione | Q2 | benchmark + RFQ | fonte acqua, analisi, Q/backwash | RFQ skid installato |
| Acqua | 015 | pompe 1+1 | Q1/Q2 | hardware benchmark verificato | Q/H/NPSH | Grundfos/VFD + quadro/skid/installazione |
| Acqua | 016 | fertirrigazione | Q2 | benchmark + RFQ | crop card, portate, ricette | RFQ A/B/acido installato |
| Acqua | 017 | tank fertilizzanti | Q1/Q2 | benchmark + RFQ | layout/containment | RFQ contenimento + accessori |
| Acqua | 018 | accumulo 300 m³ | Q2 | RFQ | geotecnica, fonte, bilancio | RFQ 2×150 m³ / alternative |
| Energia | 019 | FV + inverter | Q1/Q2 | moduli/inverter benchmark + RFQ | layout, strutture, DSO | RFQ 100 vs 120 kW AC installato |
| Logistica | 020 | AMR serra | Q4/Q3 P2 | HOLD | ore/flussi P1 reali + pilot serra | aprire RFQ solo se business case positivo |
| Logistica | 021 | telescopico/mezzo multifunzione CORE | Q1/Q2/Q3 | benchmark + RFQ | accessi, portanza, area humus, duty | demo/RFQ macchina + forche + benna |
| Verde | 022 | robot tagliaerba | Q3 | prezzi benchmark | superficie netta, pendenze, GNSS/RTK | pilot zona reale |
| Benessere | 023 | rover pulizia galline | Q4 / ARCHIVIATO | storico | rimosso dal core | nessuna RFQ |
| Manutenzione | 021-H1 | PLE/piattaforma accesso in quota | Q2/Q3 | RFQ | layout, punti alti, portanza | demo punti critici + TCO acquisto/noleggio |
| Materia | 011-MAT | humus/vermicompost base | Q2 | budget | flussi t/anno, layout, stato materiali | RFQ baie/strumenti solo dopo layout |
| Post-raccolta | 024 | celle frigorifere | Q2 | benchmark hardware + RFQ | kg/day, batch, T ingresso, pull-down, layout | RFQ frigorista installato |
| Post-raccolta | 025 | raccolta/packaging | Q1/Q2 | molti benchmark unitari | volumi, SKU, packaging | RFQ lotto equipment + consumabili |
| Servizi | 026 | pergolato/vite/relax | Q2 | benchmark unitari + RFQ | layout, neve/vento, geotecnica | calcolo strutturale + RFQ installato |
| Servizi | 027 | fattoria didattica | Q2/Q3 | benchmark + RFQ | ERSA, layout, accessibilità, visita pilota | preventivi opere + servizi |
| Retail | 028 | spaccio 24/7 | Q3 | benchmark vending + RFQ | SUAP, SKU/temp, pilot erogazione, fiscalità | demo SKU + RFQ installato |
| Trasformazione | 029 | centro conto terzi | Q4 | RFQ OEM | domanda locale, anchor customers, volumi | non nel CAPEX core finché gate domanda aperto |
| Automazione | 030 | server centrale | Q1 | benchmark + RFQ | config target già definita; BESS/DR acceptance | 3 RFQ hardware/support |
| Personale | 031 | workforce/lancio | Q5 | costo lavoro floor, non budget | CPL Udine, inquadramenti, volumi | consulente lavoro/payroll/service RFQ |
| Acqua | 032 | trattamento/disinfezione | Q2 | RFQ | UVT, microbiologia, Q, water class | RFQ UV/treatment dopo analisi |
| Acqua | 033 | drenaggio/riuso | Q3 | RFQ | pilot 30–60 gg, Na/Cl, patogeni, scarichi | pilot + RFQ treatment/reuse |
| Energia | 034 | EMS/BESS/connessione | Q1/Q2/Q5 | vendor data + RFQ | load register, DSO, fire, site | BESS + grid engineering + installed RFQ |

## 4. RFQ da aprire già ora senza impegnare acquisto

Richiedibili come **budgetary / technical RFQ**:
- PDC Kensol o equivalente;
- pompe/VFD Grundfos-Danfoss o equivalente;
- deumidificazione DryGair;
- FV inverter/moduli;
- server BOM-030;
- BESS/PCS e rapid-switch architecture;
- metering;
- packaging equipment;
- telescopico/mezzo multifunzione;
- cold-room hardware come benchmark tecnico, dichiarando che load sizing finale resta aperto.

Questi RFQ devono riportare chiaramente:
- `BUDGETARY / NOT FOR ORDER`;
- assunzioni;
- esclusioni;
- validità;
- prezzo netto;
- IVA;
- trasporto;
- installazione;
- commissioning;
- ricambi;
- service;
- lead time;
- garanzia.

## 5. RFQ da non congelare prima dei dati reali

Non chiedere un "prezzo finale installato" senza:
- lotto/layout per serra/civili/FV/DSO;
- crop card per acqua/fertirrigazione;
- carico termico per distribuzione/accumulo;
- kg prodotto/pull-down per celle;
- superficie/pilot per robotica non core;
- layout/punti alti per accesso in quota;
- flussi reali per attrezzature humus;
- domanda per BOM-029.

Un prezzo senza questi input resta solo benchmark.

## 6. Priorità RFQ immediata

Ordine operativo risk-first:

1. **BOM-021 telescopico + forche + benna** — capacità fisica core per materiali, humus, cantiere e manutenzione;
2. **H1 accesso in quota** — RFQ/TCO piattaforma OEM vs PLE ragno vs noleggio;
3. **BOM-034 BESS/PCS + grid engineering**;
4. **BOM-019 FV/inverter**;
5. **BOM-011 PDC**;
6. **BOM-015 pompe/VFD**;
7. **BOM-024 celle** — budgetary con load sheet aperto;
8. **BOM-025 packaging**;
9. **BOM-030 server centrale minimo**;
10. **BOM-012 boost/deumidificazione**;
11. **BOM-031 servizi professionali/personale**.

L'ordine non autorizza l'acquisto: indica quali RFQ servono prima per chiudere rischio, CAPEX e layout.

## 7. Campi obbligatori per ogni offerta

- vendor;
- modello;
- revisione offerta;
- data;
- validità;
- quantità;
- prezzo unitario;
- sconto;
- netto;
- IVA;
- freight;
- installazione;
- commissioning;
- training;
- service annuo;
- subscription;
- ricambi;
- lead time;
- garanzia;
- vita utile/availability;
- consumi;
- esclusioni;
- dipendenze;
- link datasheet/manuale;
- stato: budgetary / firm / installed;
- file offerta.

## 8. Regola comparabilità

Nessun vendor viene dichiarato più economico se:
- uno include installazione e l'altro no;
- uno include commissioning e l'altro no;
- IVA/freight non sono separati;
- configurazioni tecniche non sono equivalenti;
- SLA/garanzia differiscono materialmente.

Confronto minimo:
`CAPEX installed + 5/10y service + energy + consumables + replacements + downtime risk`.

## 9. Collegamento strategia contributiva

La matrice `MATRICE_INVESTIRE_ORA_O_DOPO.md` governa quando acquistare.

RFQ != ordine.

Un RFQ anticipato serve a:
- quantificare candidatura/contributo;
- verificare lead time;
- bloccare specifiche;
- confrontare alternative.

L'ordine avviene soltanto quando:
- gate tecnico chiuso;
- copertura finanziaria chiusa;
- fondo operativo protetto;
- eleggibilità/cumulo confermati dove rilevante.


## 10. Pilot interface

Per tutte le righe `Q3` e per i package che richiedono acceptance fisica prima dell'ordine, il riferimento unico è:

- `MASTER_PILOT_REGISTER.md`;
- `MASTER_PILOT_REGISTER.csv`;
- `PILOT_RESULT_CAPTURE_TEMPLATE.csv`;
- `PILOT_DECISION_RECORD_TEMPLATE.md`.

Regola di transizione:

- `Q3 -> Q1/Q2` solo dopo pilot PASS / PASS WITH ACTIONS e corrective actions compatibili;
- `Q3 -> PX` se il pilot fallisce o il TCO non giustifica scaling;
- `Q3 -> Q3` se serve retest;
- nessun ordine full-scale prima del decision record.

Pilot principali attivi nel registro:
- PIL-AMR — solo P2 se giustificato dai dati;
- PIL-MOW;
- PIL-RETAIL;
- PIL-REUSE;
- PIL-DID;
- PIL-BESS;
- PIL-COLD;
- PIL-PACK;
- PIL-LIFT;
- PIL-HGT.
