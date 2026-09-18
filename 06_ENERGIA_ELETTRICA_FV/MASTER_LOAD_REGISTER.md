# Master Load Register — validation/closure sprint BOM-034

**Aggiornato:** 18 settembre 2026  
**Stato:** `V0.1 / STRUTTURA CARICHI CONSOLIDATA / P0-P1 DA MISURA-RFQ`  
**Ambito:** inventario elettrico, priorità P0/P1/P2/P3, profilo 1–15 min, spunti, restart e verifica del vincolo BESS 30 kW.

## 1. Scopo

Questo documento trasforma la `LOAD_PRIORITY_MATRIX.md` in un registro chiudibile con dati misurati o da RFQ.

Non decide ancora:

- capacità BESS 60/90/120 kWh;
- adeguatezza finale dei 30 kW;
- margine di potenza definitivo;
- tempi di trasferimento/islanding;
- BT/MT e limiti DSO.

Queste decisioni restano bloccate finché P0/P1 e i transitori non sono misurati o garantiti da fornitore.

## 2. Legenda stato dato

| Stato | Significato |
|---|---|
| `KNOWN-REF` | valore già presente nel repository come riferimento/candidato |
| `OEM-RFQ` | da ottenere come dato garantito dal fornitore |
| `MEASURE` | da misurare sul sistema reale |
| `DESIGN` | dipende dal progetto elettrico/layout |
| `FUTURE` | fuori dalla configurazione iniziale o non attivo al day-1 |

Un valore `KNOWN-REF` non è automaticamente un valore di progetto finale.


## 2A. Struttura costi, fonti e link

Il master load register **non duplica i prezzi** già governati dalle BOM di dominio. Ogni costo deve avere un solo source-of-truth; qui viene mantenuto il collegamento tecnico/economico.

Regola:

- `power/load data` -> questo registro;
- `quantità + prezzo + IVA + installazione + ricambi + vita utile` -> BOM di dominio;
- `norme + datasheet + pagine OEM + benchmark prezzo` -> file fonti;
- `prezzo finale installato` -> RFQ comparabile e poi CAPEX consolidato;
- nessun prezzo osservato online viene promosso a budget senza RFQ/validazione.

Link principali:

- [BOM-034 — EMS, BESS e connessione](../19_BOM_PRODOTTI_FORNITORI/ENERGIA_EMS_BESS_CONNESSIONE.md)
- [Fonti BOM-034 — norme, OEM, benchmark e link esterni](../22_FONTI_NORME_PREVENTIVI/ENERGIA_EMS_BESS_CONNESSIONE_SOURCES.md)
- [Architettura EMS/BESS/grid](EMS_BESS_GRID_ARCHITECTURE.md)
- [Load priority matrix](LOAD_PRIORITY_MATRIX.md)
- [Server centrale P0](../07_AUTOMAZIONE_DATI_AI/CENTRAL_ORCHESTRATION_SERVER.md)
- [Acqua e fertirrigazione](../04_ACQUA_E_FERTIRRIGAZIONE/README.md)
- [Termico e clima](../05_TERMICO_E_CLIMA/README.md)
- [Celle frigorifere](../09_TECH_BARN_E_POST_RACCOLTA/COLD_ROOMS_ARCHITECTURE.md)
- [Spaccio automatico 24/7](../10_BENESSERE_FATTORIA_E_SERVIZI/SPACCIO_AUTOMATICO_24_7_ARCHITECTURE.md)
- [Vendor data snapshot 18/09/2026](LOAD_VENDOR_DATA_SNAPSHOT_2026-09-18.md) — dati OEM/retailer verificati, prezzi benchmark e open RFQ

Benchmark economici già presenti nel package BOM-034:

| Voce | Benchmark già tracciato | Stato |
|---|---:|---|
| Schneider PM5110 | €700 listino osservato | riferimento, non installato |
| Schneider PM5340 | €1.469 listino osservato | riferimento, non installato |
| Schneider PM5341 MID | €1.694 listino osservato | riferimento, non installato |
| BESS/PCS 30 kW | RFQ | costo finale aperto |
| 60/90/120 kWh useful | RFQ | costo finale aperto |
| critical bus / switchgear | RFQ | costo finale aperto |
| fire package / fire engineering | RFQ | costo finale aperto |
| DSO / CCI / SLI / eventuale MT | DSO/RFQ | dipende dal punto di connessione |
| commissioning + blackout SAT | RFQ | obbligatorio |

La struttura economica di BOM-034 resta:

`CAPEX034 = BESS + PCS + fire + civil + critical bus + switchgear + meters + protection + DSO/CCI-SLI + engineering + commissioning`

`OPEX034 = aux_energy + losses + service + inspections + software_if_any + degradation + meter/calibration + fire maintenance`

Nel CSV sono aggiunti i campi `capex_status`, `cost_source` e `technical_source` per mantenere la tracciabilità macchina-per-macchina.

## 3. Registro carichi v0.1

| ID | Funzione | Classe | Potenza working | Stato | Island baseline | Dato da chiudere |
|---|---|---|---:|---|---|---|
| EL-PLC | PLC safety/control | P0 | DA QUADRO | DESIGN + MEASURE | sì | W reali, alimentatori, ridondanza, spunto |
| EL-EDGE | edge gateway OT | P0 | DA MISURA | MEASURE | sì | W idle/max |
| EL-NET | network core | P0 | DA MISURA | MEASURE | sì | switch/router/PoE normal/max |
| EL-SRV | NODE-A/B/QNODE + storage minimo | P0 | DA MISURA | MEASURE + OEM-RFQ | sì | W idle, 95p, max, restart |
| EL-BESS-AUX | BMS/PCS/fire/HVAC/control | P0 | OEM AUX | OEM-RFQ | sì | ausiliari normal/max/winter |
| EL-SAFETY | fire/security/access essenziale | P0 | DA PROGETTO | DESIGN + MEASURE | sì | lista circuiti e W |
| EL-CR-CTRL | controlli/logger celle | P0 | piccolo / DA MISURA | MEASURE | sì | W continui |
| EL-IRR-CTRL | controlli irrigazione/valvole | P0 | piccolo / DA MISURA | MEASURE | sì | W continui + attuazioni |
| EL-IRR-P1 | pompa irrigazione duty | P1 | **2,2 kW** candidate | KNOWN-REF + OEM-RFQ | quando richiesta | kW reali, PF, inrush, VFD |
| EL-IRR-P2 | pompa irrigazione standby | P2 | **2,2 kW** candidate | KNOWN-REF + OEM-RFQ | normalmente no | idem; interlock 1-at-a-time |
| EL-FERT | dosaggio fertirrigazione | P1 | sub-kW/low-kW | OEM-RFQ | quando irrigazione critica | W max, duty |
| EL-UV-W1 | UV trattamento W1 | P1 | **~0,1–0,3 kW** class | KNOWN-REF + OEM-RFQ | quando richiesto | potenza esatta + lamp state |
| EL-CR-A | cella CR-A holding | P1 | **~2,25 kW compressore + aux** | KNOWN-REF + OEM-RFQ | sì | kW, aux, LRA/inrush, defrost |
| EL-CR-B | cella CR-B holding | P1/P2 | **~1,48–2,25 kW compressore + aux** | KNOWN-REF + OEM-RFQ | condizionale | kW, aux, LRA/inrush, defrost |
| EL-GH-ACT | aperture/attuatori serra survival | P1 | DA RFQ | OEM-RFQ | sì | W per gruppo + simultaneità |
| EL-HAF | subset HAF essenziale | P1 | DA BOM/RFQ | OEM-RFQ | condizionale | W unitario, n attivi, VFD |
| EL-ANIMAL | welfare animali essenziale | P1 | DA BOM | DESIGN + OEM-RFQ | se necessario | circuiti e W |
| EL-LIGHT | illuminazione sicurezza minima | P1 | DA LAYOUT | DESIGN | limitata | W circuito |
| EL-PDC-1 | PDC modulo #1 | P2 / P1 emergenza | **fino a 9 kW** dichiarati | KNOWN-REF + OEM-RFQ | solo regola emergenza | input reale vs condizioni |
| EL-PDC-2 | PDC modulo #2 | P3 | **fino a 9 kW** | KNOWN-REF + OEM-RFQ | no baseline | input reale |
| EL-PDC-3 | PDC modulo #3 | P3 | **fino a 9 kW** | KNOWN-REF + OEM-RFQ | no baseline | input reale |
| EL-PDC-4 | PDC futuro | P3 | **fino a 9 kW** | FUTURE | no | input reale |
| EL-DH-3 | deumidificatore DG-3 | P2/P3 | **2,3 kW** | KNOWN-REF + OEM-RFQ | condizionale | spunto/duty |
| EL-DH-12 | deumidificatore DG-12 | P3 | **9,55 kW** | KNOWN-REF + OEM-RFQ | no baseline | spunto/duty |
| EL-RETAIL-REF | refrigerazione spaccio | P1/P2 | DA RFQ | OEM-RFQ | temperatura-driven | W normal/max/start |
| EL-RETAIL-PAY | payment/controller/exit | P1 | basso / DA MISURA | MEASURE | sessione attiva | W + rete |
| EL-AMR-CHG | ricarica AMR | P3 | DA RFQ | OEM-RFQ | no | kW charger + simultaneità |
| EL-MOWER-CHG | ricarica rasaerba | P3 | DA BOM | OEM-RFQ | no | W charger |
| EL-WORKSHOP | officina | P3 | DA QUADRO | DESIGN | no | circuiti e picco |
| EL-VISITOR | servizi visitatori/relax | P3 | DA LAYOUT | DESIGN | no | circuiti |
| EL-BOM029 | linea trasformazione | P3 | futuro | FUTURE | no baseline | package separato |

## 4. Subtotali numerici già dimostrabili

Questi subtotali sono **solo aritmetica sui riferimenti già presenti nel repository** e non includono P0, ausiliari, HAF, attuatori, fertirrigazione, luci o altri carichi ancora aperti.

### P1 numerico di riferimento

Assumendo contemporaneamente:

- pompa irrigazione duty: 2,20 kW;
- UV W1: 0,10–0,30 kW;
- CR-A compressore: 2,25 kW;
- CR-B compressore: 1,48–2,25 kW;

si ottiene:

**6,03–7,00 kW** prima di ausiliari e prima di tutto il P0.

Se CR-B viene sheddata/declassata a P2:

**4,55–4,75 kW** prima di ausiliari e P0.

### Incrementi utili per le prove

- + DG-3: **+2,30 kW**;
- + una PDC: **+9,00 kW max dichiarato**;
- P1 numerico + DG-3 + una PDC: **17,33–18,30 kW**, ancora prima di P0 e ausiliari.

Questa è la ragione per cui il vincolo 30 kW non può essere validato senza misurare il bus P0 e gli spunti.

## 5. Budget di potenza per simulazione

Per un PCS nominale da 30 kW:

| Headroom simulato | Budget steady-state |
|---:|---:|
| 20% | 24,0 kW |
| 25% | 22,5 kW |
| 30% | 21,0 kW |

Formula:

`P_allowed = 30 kW × (1 - headroom)`

Il confronto con i carichi va fatto su:

1. potenza continua;
2. spunto/startup;
3. kVA/PF;
4. derating temperatura;
5. fase peggiore;
6. ausiliari BESS;
7. restart simultaneo.

## 6. Campagna dati obbligatoria

### A. Prima del detailed design

Per ogni carico >1 kW o P0:

- marca/modello;
- tensione/fasi;
- P nominale e P max input;
- corrente nominale;
- PF/cosφ;
- corrente/spunto o overload;
- durata startup;
- VFD/inverter sì/no;
- restart delay;
- duty cycle;
- stato in island;
- comportamento dopo power loss;
- protocollo/contatto per load shed.

### B. Metering di progetto

Minimo punti misura:

- PCC;
- PV;
- BESS;
- P0 critical bus;
- PDC aggregate + preferibilmente per modulo;
- CR-A;
- CR-B;
- irrigazione;
- Tech Barn;
- retail;
- IT;
- charging mobile.

### C. Acquisizione

- 1 s o 10 s durante start/transitori significativi;
- 1 min profilo operativo;
- 15 min domanda;
- energia giornaliera;
- timestamp max demand;
- stato `grid/island`;
- stato asset e priorità.

## 7. Data model minimo

Campi:

`timestamp, asset_id, state, priority, grid_island, kW, kvar, kVA, PF, V_L1_L2_L3, A_L1_L2_L3, Hz, phase_imbalance, start_event, shed_permission`

Per ogni asset devono inoltre esistere:

- owner del dato;
- fonte `MEASURE/OEM/DESIGN`;
- revisione;
- data di validazione;
- incertezza/note.

## 8. Restart groups da rendere quantitativi

| Gruppo | Asset | Gate prima della chiusura |
|---|---|---|
| RG0 | switchgear, BESS, PLC, network, server | kW/kVA P0 e no-reboot misurati |
| RG1 | water control, cold-room control, safety | W/max e interlock |
| RG2 | compressori celle + pompa irrigazione | start current + delay sequenziale |
| RG3 | HAF/attuatori + PDC condizionale | max simultaneous kW |
| RG4 | produzione/logistica | controlled restart |
| RG5 | charging/deferred | enable solo con headroom |

Ogni gruppo deve avere:

- delay;
- max kW;
- max kVA;
- condizioni di consenso;
- timeout;
- fallback;
- allarme.

## 9. Closure criteria del master load register

Il gate è chiuso soltanto quando:

1. nessun asset P0 ha potenza `DA MISURA/DA PROGETTO`;
2. ogni carico >1 kW ha kW, kVA/PF e startup definiti;
3. P0 normal/max e P1 normal/max sono calcolati;
4. simultaneità e duty cycle sono documentati;
5. RG0–RG5 hanno limiti numerici;
6. sono simulati headroom 20/25/30%;
7. sono simulati scenari 60/90/120 kWh a EOL;
8. si verifica il caso peggiore di restart dopo ritorno rete;
9. il BESS selezionato supera test di blackout reale senza reboot P0;
10. il risultato alimenta RFQ, SLD, short-circuit/selectivity e CAPEX/OPEX.

## 10. Decisioni bloccate fino alla closure

Restano `OPEN`:

- scelta definitiva 60/90/120 kWh;
- conferma 30 kW PCS;
- architettura no-break/rapid-transfer;
- eventuale PV-in-island;
- riserva SOC;
- power headroom finale;
- dimensionamento quadri critical bus;
- sequenza restart definitiva.

## 11. Interfacce

- `LOAD_PRIORITY_MATRIX.md` — classificazione funzionale e logica di shed;
- `EMS_BESS_GRID_ARCHITECTURE.md` — architettura e vincoli PCS/BESS;
- `RFQ_EMS_BESS_GRID.md` — richieste al fornitore;
- `19_BOM_PRODOTTI_FORNITORI/ENERGIA_EMS_BESS_CONNESSIONE.md` — BOM-034;
- `07_AUTOMAZIONE_DATI_AI/CENTRAL_ORCHESTRATION_SERVER.md` — carico P0 IT;
- BOM-015/024/028 e package termico — fonti dei carichi di dominio.
