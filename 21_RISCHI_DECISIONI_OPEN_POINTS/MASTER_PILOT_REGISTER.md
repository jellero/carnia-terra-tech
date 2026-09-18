# Master pilot register — Carnia TerraTech

**Aggiornato:** 18 settembre 2026  
**Stato:** `PILOT GOVERNANCE / ESECUZIONE BLOCCATA DOVE SERVONO LOTTO, IMPIANTO O SKU REALI`

## 1. Scopo

Unificare i pilot obbligatori prima di acquisto, scaling o apertura al pubblico.

Regola:

`pilot -> dati -> acceptance -> decisione -> RFQ/ordine/scaling`

Non:

`benchmark -> acquisto -> sperare che funzioni`.

Ogni pilot deve produrre:
- configurazione testata;
- ambiente e condizioni;
- raw data;
- anomalie;
- manutenzione/interventi;
- costo pilota;
- KPI;
- esito PASS / PASS WITH ACTIONS / FAIL;
- decisione economica;
- owner;
- data e firma.

## 2. Stati

| Stato | Significato |
|---|---|
| P0 | pilot definito ma non avviabile senza dati/sito |
| P1 | pilot organizzabile con vendor/demo equivalente |
| P2 | pilot su sito reale richiesto |
| P3 | pilot in corso |
| P4 | pilot completato, decisione aperta |
| P5 | accepted / scaled |
| PX | rejected / no-go |

## 3. Registro master

| ID | Package | Stato | Ambiente minimo | Durata / campione | KPI principali | Exit gate |
|---|---|---|---|---|---|---|
| PIL-AMR | BOM-020 AMR serra | P1/P2 | corsia ~1,20 m, porte, persone, carrello, area umida, dock, offline | almeno 8 h demo + 100 missioni acceptance | mission success, docking, no-contact, recovery, API, log | >=100 missioni consecutive secondo KPI concordati; docking >=99%; nessun contatto non previsto |
| PIL-MOW | BOM-022 robot tagliaerba | P0/P2 | prato reale, pendenze, ombra GNSS, no-go, dock | >=20 cicli dock-return + fault tests | dock success, area completion, RTK loss, obstacle/fail-safe, hens lockout | nessun ingresso aree interdette; recovery documentata; log disponibili |
| PIL-RETAIL | BOM-028 spaccio 24/7 | P1/P2 | macchina candidata + pack/SKU reali + pagamento/fiscalità test | >=100 erogazioni per SKU critico | jam, pack damage, product damage, temp, vend/payment reconciliation | zero jam/pack break nel test target; danno entro soglia; inventario/pagamento riconciliati |
| PIL-REUSE | BOM-033 drenaggio/riuso | P0/P2 | 1 comparto C1 o C2, drain segregato, HOLD, lab | 30–60 giorni | m³ drain, reuse ratio, EC/pH, Na/Cl, patogeni, €/m³, fertilizzante recuperato | trattamento validato + crop sign-off + legal discharge route + mass balance chiuso |
| PIL-DID | BOM-027 fattoria didattica | P0/P2 | visitor route reale, barriere, WC, lavamani, emergency, visit mode | almeno 1 visita pilota + emergenza + wet-weather | percorso, accessibilità, headcount, segregazione mezzi/AMR, WC/lavamani, emergency time | nessun critical finding; route/accessibility/ERSA pre-check chiusi |
| PIL-BESS | BOM-034 BESS / critical bus | P0/P2 | sistema installato, P0 production-like load | blackout SAT + black-start + 72 h log | no reboot, V/f waveform, shed/restart, black-start, grid return | P0 no-reboot + tutti i safety/protection test PASS |
| PIL-COLD | BOM-024 celle / post-harvest | P0/P2 | cella installata, prodotto reale, batch rappresentativo | pull-down + door cycles + mapping | pull-down time, product core T, RH, kWh/kg, door recovery | tempi/temperature/qualità conformi alla crop card |
| PIL-PACK | BOM-025 packaging | P1/P2 | SKU/pack reali, etichetta/lotto | >=100 pack per SKU critico o lotto concordato | jam, seal, damage, throughput, labour, label read | zero critical defect e throughput/labour entro target |
| PIL-LIFT | BOM-021 mezzo multifunzione | P1/P2 | pallet, big bag, materiale sfuso, area humus, pendenza reale | >=4 h duty + missioni rappresentative | stabilità, manovra, benna, ricarica, ergonomia | tutte le missioni core completate senza workaround insicuri |
| PIL-HGT | accesso in quota H1 | P1/P2 | punti alti reali/rappresentativi, piattaforma OEM o PLE | prova punti critici + emergency recovery | reach, setup, stabilità, emergenza | 100% punti manutentivi critici raggiungibili in sicurezza |

## 4. PIL-AMR — BOM-020

Fonte:
- `08_MACCHINE_E_LOGISTICA/RFQ_AMR.md`

### Setup minimo
- corsia ~1,20 m;
- porte/gate;
- carrello/cassette;
- persone;
- superficie e umidità rappresentative;
- docking;
- missione indoor/outdoor se prevista;
- rete locale;
- Internet disabilitato per test fault.

### Acceptance
- 100 missioni consecutive;
- nessun contatto non previsto;
- docking >=99% nel test;
- recovery obstacle/network fault;
- API integration;
- stop/restart;
- carico massimo di progetto;
- test porte;
- export log;
- backup configurazione/manuali.

### Costi pilot da separare
- demo/noleggio;
- trasporto;
- tecnico vendor;
- mapping;
- top module;
- carrelli;
- dock temporaneo;
- integrazione API;
- ore interne;
- assicurazione/safety review.

## 5. PIL-MOW — BOM-022

Fonte:
- `08_MACCHINE_E_LOGISTICA/RFQ_LAWN_MOWER.md`

Acceptance minima:
1. mappa/no-go;
2. >=20 dock-return;
3. ombra GNSS;
4. Internet/4G/Wi-Fi loss;
5. ostacoli rappresentativi;
6. lift/tilt/manual stop;
7. animal/visitor no-go e lockout se applicabili;
8. modifica no-go;
9. log;
10. recovery/operator training.

Non comprare prima di conoscere superficie netta, pendenza e aree condivise.

## 6. PIL-LIFT / PIL-HGT — mezzo e manutenzione in quota

Fonti:
- `08_MACCHINE_E_LOGISTICA/RFQ_LIFTING_MULTIFUNCTION.md`;
- `08_MACCHINE_E_LOGISTICA/RFQ_ACCESSO_IN_QUOTA_RAGNO.md`.

### PIL-LIFT
Testare:
- pallet;
- big bag;
- benna con materiale rappresentativo;
- area humus;
- pendenza;
- frenata;
- ricarica;
- 4 h duty.

### PIL-HGT
Testare tutti i punti manutentivi critici:
- gronde;
- aperture;
- colmo/falde accessibili;
- sensori/ventilatori;
- emergenza/discesa;
- stabilizzazione.

Il test può usare piattaforma OEM, PLE ragno o soluzione noleggiata.

## 7. PIL-RETAIL — BOM-028

Fonti:
- `10_BENESSERE_FATTORIA_E_SERVIZI/SPACCIO_AUTOMATICO_24_7_ARCHITECTURE.md`

Per ogni SKU critico:
- >=100 erogazioni;
- zero inceppamento target;
- zero rottura pack target;
- danno prodotto entro soglia predefinita;
- lettura lotto;
- recovery fault;
- temperatura;
- pagamento;
- vend_ack;
- refund/reconciliation.

Testare almeno:
- fogliare refrigerato;
- pack fragile premium;
- SKU chilling-sensitive se incluso;
- click&collect/locker se previsto.

Non congelare macchina prima di SKU + pack reali.

## 8. PIL-REUSE — BOM-033

Fonti:
- `04_ACQUA_E_FERTIRRIGAZIONE/DRAINAGE_REUSE_ARCHITECTURE.md`
- `04_ACQUA_E_FERTIRRIGAZIONE/RFQ_DRAINAGE_REUSE.md`

Pilot su un comparto C1 o C2:
- 30–60 giorni;
- feed/drain misurati;
- EC/pH/T;
- Na/Cl;
- nutrient panel;
- pathogen strategy;
- treatment test;
- limited blend;
- crop response.

Output:
- drain m³/day;
- reuse achievable;
- bleed cause;
- €/m³ reused;
- nutrient recovery;
- labour;
- maintenance;
- agronomic sign-off.

No automatic full reuse before PASS.

## 9. PIL-DID — BOM-027

Fonti:
- `10_BENESSERE_FATTORIA_E_SERVIZI/FATTORIA_DIDATTICA_ARCHITECTURE.md`
- `10_BENESSERE_FATTORIA_E_SERVIZI/RFQ_FATTORIA_DIDATTICA.md`

Prima apertura:
- visitor route completa;
- accessibilità;
- gate/barriere;
- separazione mezzi;
- WC;
- lavamani;
- acqua potabile;
- primo soccorso;
- headcount;
- punto raccolta;
- `VISIT MODE`;
- lockout AMR/mower;
- rete guest isolata;
- modulo galline;
- variante wet-weather.

Eseguire:
1. visita pilota realistica;
2. simulazione emergenza;
3. visita/accessibility walkthrough;
4. debrief;
5. corrective action closure.

## 10. PIL-BESS — BOM-034

Questo pilot è tecnicamente un SAT/commissioning ma viene registrato qui perché decide se la baseline no-UPS è accettabile.

Minimo:
- P0 production-like;
- grid loss;
- waveform;
- no reboot NODE-A/B/QNODE/network/PLC;
- black-start;
- motor/compressor pickup;
- shed P3/P2;
- low SOC;
- server/internet/comms loss;
- grid return;
- 72 h logging.

Fallimento no-reboot = architettura da correggere prima del go-live.

## 11. PIL-COLD

Prima di accettare la capacità frigorifera:
- batch rappresentativo;
- product core temperature;
- room mapping;
- pull-down;
- door openings;
- summer/representative load;
- defrost;
- alarm;
- energy.

KPI:
- kg/batch;
- kWh/kg;
- min to target core T;
- RH;
- product loss/quality;
- recovery after door event.

## 12. PIL-PACK

Prima di ordine/scaling di packaging automatico:
- SKU reale;
- pack reale;
- label/lot;
- condensation;
- throughput;
- operator intervention.

Misurare:
- pack/h;
- operator min/100 pack;
- reject %;
- seal/closure defect;
- damage;
- label read;
- consumable cost/pack.

## 13. Formato economico pilot

Ogni pilot deve riportare:

`PILOT_COST = vendor_demo + rental + freight + temporary_install + integration + consumables + lab + internal_labour + safety + travel + restoration`

Separare:
- costo pilot non recuperabile;
- eventuale fee scalabile sull'ordine;
- deposito;
- danni/assicurazione;
- costo campioni/prodotto;
- costo fermo impianto.

## 14. Decisione economica post-pilot

Non basta PASS tecnico.

Per ogni candidato calcolare:

`TCO = installed_CAPEX + 5/8/10y_OPEX + consumables + service + replacements + internal_labour + downtime`

e, quando applicabile:

`benefit = labour_saved + loss_avoided + water_saved + fertilizer_saved + revenue_enabled + safety/risk_value`.

Esito:
- SCALE;
- SCALE WITH CHANGES;
- RETEST;
- HOLD;
- REJECT.

## 15. Evidenze obbligatorie

Repository per ogni pilot:
- test plan;
- vendor/config;
- photos/video reference;
- raw CSV/log;
- incident/near-miss;
- maintenance interventions;
- cost sheet;
- acceptance sheet;
- corrective actions;
- decision record.

Nessun risultato viene riassunto solo in una frase senza raw evidence.

## 16. Sequenza consigliata

Prima del lotto:
1. AMR vendor demo in ambiente equivalente;
2. packaging/vendor bench test con sample pack;
3. smart-retail vend test su campioni se vendor accetta;
4. BESS/PCS factory/demo evidence richiesta via RFQ.

Dopo lotto/layout:
5. mezzo multifunzione su layout reale;
6. accesso in quota;
7. mower se realmente previsto;
8. didattica route;
9. AMR site pilot.

Dopo primo ciclo produttivo:
10. drainage/reuse 30–60 giorni;
11. cold-room pull-down;
12. packaging production pilot;
13. retail SKU pilot.

Dopo installazione elettrica:
14. BESS blackout SAT.

## 17. Gate closure punto 6

Il punto 6 può passare a `STRUCTURED -> EXECUTED` quando:
1. tutti i Q3 hanno pilot plan;
2. ogni pilot ha owner e budget;
3. i criteri PASS/FAIL sono scritti prima del test;
4. nessun pilot modifica i KPI a posteriori senza change log;
5. raw evidence è archiviata;
6. decision record è firmato;
7. procurement register viene aggiornato da Q3 a Q1/Q2/Q5 oppure PX.
