# BOM-015 — Pompe principali irrigazione 1+1

**Aggiornato:** 17 settembre 2026  
**Ambito:** accumulo/fonte -> stazione pompe 1+1 -> filtrazione fine pressurizzata -> fertirrigazione.  
**Stato:** `ARCHITETTURA E CANDIDATI REALI / TAGLIA FINALE DA Q-H, NPSH E RFQ`.

## 1. Distinta principale

| Codice | Voce | Quantità working | Stato | Benchmark / nota |
|---|---|---:|---|---|
| PMP-001 | pompa principale duty | 1 | DA CALCOLO/RFQ | 100% duty point |
| PMP-002 | pompa standby | 1 | DA CALCOLO/RFQ | identica dove possibile |
| PMP-CAN-001 | Grundfos CR 10-6 2,2 kW | candidato | PREZZO TROVATO | 10 m³/h nominali, 48,3 m, €1.946,78 IVA incl. |
| PMP-CAN-002 | Grundfos CR 5-8 | alternativa minore | BENCHMARK | ~€1.291 retail UE per versione trifase osservata |
| PMP-CAN-003 | Hydro Multi-E 2 CRE 10-3 | alternativa integrata | LISTINO 2026 | €12.185 listino, condizioni/IVA da confermare |
| PMP-VFD-001 | VFD pompa 1 | 1 | REQUISITO | dedicato |
| PMP-VFD-002 | VFD pompa 2 | 1 | REQUISITO | dedicato |
| PMP-VFD-CAN | Danfoss FC-51 2,2 kW 380–480 V | benchmark | PREZZO TROVATO | €895,30 + IVA/cad RS Italia |
| PMP-SUC-001 | collettore aspirazione | 1 | DA CALCOLO | DN/NPSH |
| PMP-SUC-002 | valvole isolamento aspirazione | 2 | REQUISITO | full bore |
| PMP-SUC-003 | riduzioni eccentriche | 2 | DA DISTINTA | evitare sacche aria |
| PMP-SUC-004 | strainer/griglia grossolana | 0–1 | CONDIZIONALE | non filtro fine in aspirazione |
| PMP-DIS-001 | collettore mandata | 1 | DA CALCOLO | Q max/transitori |
| PMP-NRV-001 | non ritorno ramo | 2 | REQUISITO | prevenire backspin/ricircolo |
| PMP-DIS-002 | valvole isolamento mandata | 2 | REQUISITO | manutenzione indipendente |
| PMP-FIT-001 | unioni/giunti/raccordi | 1 lotto | DA DISTINTA | niente forfait |
| PMP-PRS-001 | trasmettitore pressione principale | 1 | REQUISITO | 4–20 mA |
| PMP-PRS-002 | sensore pressione ridondante/pressostato | 1 | REQUISITO | plausibilità/safety |
| PMP-PRS-CAN | WIKA A-10 0–10 bar | benchmark | PREZZO TROVATO | da €133,95 + IVA; RS ~€151,36 + IVA |
| PMP-MAN-001 | manometro mandata | 1 | REQUISITO | locale |
| PMP-VAC-001 | vacuometro aspirazione | 0–1 | CANDIDATO | utile diagnosi NPSH/ostruzione |
| PMP-LVL-001 | livello minimo tank | 1 + ridondanza logica | OBBLIGATORIO | dry-run interlock locale |
| PMP-FLW-001 | flow meter centrale | 1 | COORD. BOM-013 | processo/controlavaggio |
| PMP-ENE-001 | misura energia pompa 1 | 1 | PREFERENZA | kWh/OPEX |
| PMP-ENE-002 | misura energia pompa 2 | 1 | PREFERENZA | kWh/OPEX |
| PMP-VES-001 | vaso autoclave 50–100 l | 0–1 | CONDIZIONALE | stabilità PID/transitori |
| PMP-VES-CAN | Zilmet Ultra-Pro 100 l | benchmark | BENCHMARK | ~€475 listino 2026 osservato, IVA da verificare |
| PMP-REL-001 | relief/sicurezza pressione | 0–1 | DA CALCOLO | dipende da shut-off/Pmax |
| PMP-SKD-001 | skid/supporti | 1 | DA RFQ | drenabile/accessibile |
| PMP-DRN-001 | drenaggio skid/locale | 1 | REQUISITO | leak management |
| PMP-ELC-001 | quadro MCC/protezioni | 1 | DA RFQ | 400 V 3~ working |
| PMP-CTL-001 | logica lead/standby | 1 | REQUISITO | locale |
| PMP-CTL-002 | selettori AUTO/OFF/MAN | 2 | REQUISITO | manutenzione |
| PMP-COM-001 | test duty point | 1 lotto | OBBLIGATORIO | Q/H/kW |
| PMP-COM-002 | failover P1->P2 | 1 test | OBBLIGATORIO | reale |
| PMP-COM-003 | failover P2->P1 | 1 test | OBBLIGATORIO | reale |
| PMP-COM-004 | test low-level/dry-run | 1 | OBBLIGATORIO | interlock |
| PMP-COM-005 | test backwash | 1 | OBBLIGATORIO | con BOM-014 |
| PMP-SP-001 | tenuta meccanica | 1 kit | DA SLA | ricambio |
| PMP-SP-002 | trasmettitore pressione | 1 | PREFERENZA | standardizzare |
| PMP-SP-003 | VFD completo | 0–1 | DA SLA/TCO | lead time |
| PMP-SP-004 | kit non ritorno/guarnizioni | 1 lotto | PREFERENZA | manutenzione |
| PMP-DOC-001 | P&ID/as-built/curve/parametri | 1 lotto | OBBLIGATORIO | gestione futura |

## 2. Punto di lavoro

Nessuna pompa è selezionata finché non è definito:

`Qdesign = max(Q irrigazione simultanea, Q flush, Q irrigazione + Q backwash se simultanei)`

`Hdesign = Hstatica + ΔH aspirazione + ΔH filtro + ΔH fertirrigazione + ΔH rete + P residua richiesta`

Verificare almeno modalità normale, backwash, flush e degradata.

## 3. Vero 1+1

Baseline:

- P1 = 100% Q/H;
- P2 = 100% Q/H;
- una sola normalmente in servizio;
- alternanza automatica;
- standby testata periodicamente;
- entrambe isolabili idraulicamente/elettricamente.

Se il progetto futuro sceglie due pompe che insieme raggiungono il duty point, riclassificare correttamente l'architettura come parallelo `2×50%` o altra ripartizione.

## 4. Benchmark Grundfos CR 10-6

Prodotto osservato 17/09/2026:

- Grundfos 96500984 CR 10-6 A-A-A-E-HQQE;
- Q nominale 10 m³/h;
- H nominale 48,3 m;
- Hmax 61,2 m;
- 2,2 kW;
- trifase;
- Pmax 16 bar;
- idraulica inox EN 1.4301/AISI 304 con testa/base ghisa;
- prezzo retail Italia: **€1.946,78 IVA 22% inclusa/cad**.

Due pompe: **€3.893,56 IVA incl.**, solo pompe.

Non implica che 10 m³/h @48,3 m sia il duty corretto Carnia TerraTech.

## 5. Benchmark inverter

Danfoss VLT Micro Drive FC-51 2,2 kW, 380–480 V 3~:

- RS Italia: **€895,30 + IVA/cad**;
- 2 unità: **€1.790,60 + IVA**.

Benchmark alternativo distributori UE inferiore, ma non usato per il budget prudente.

## 6. Benchmark soluzione OEM integrata

Listino Grundfos gennaio 2026:

- Hydro Multi-E 2 CRE 10-3 U2: **€12.185**;
- Hydro Multi-E 2 CRE 10-5 U2: **€13.323**.

Stato: `LISTINO 2026 / IVA E SCONTO REALE DA CONFERMARE`.

Serve come confronto TCO contro `2 pompe + 2 VFD + quadro/skid custom`.

## 7. Sensori pressione

Candidati reali:

- WIKA A-10: da **€133,95 + IVA**, configurabile 4–20 mA;
- WIKA A-10 0–10 bar RS: ~**€151,36 + IVA**;
- Danfoss MBS 3000 0–10 bar, 4–20 mA, IP65: ~**€195,44 + IVA**.

Preferenza: due segnali indipendenti o un trasmettitore + pressostato, così la perdita del singolo sensore non porta a sovrapressione o fermo cieco.

## 8. Aspirazione e NPSH

Con tank atmosferico preferire aspirazione allagata.

Calcolare NPSHa sul livello minimo, non sul livello medio. Il dato deve includere quota, perdite aspirazione, temperatura e pressione atmosferica sito.

Gate: `NPSHa > NPSHr + margine di progetto` definito dal progettista/OEM.

Segnali di rischio: rumore, vibrazione, calo portata, pitting giranti, assorbimento instabile.

## 9. Filtrazione: sequenza corretta

BOM-014 automatico necessita pressione di backwash. Con tank atmosferico non assumere:

`tank -> filtro automatico -> pompa`

La baseline diventa:

`tank -> protezione aspirazione grossolana -> pompe -> idrociclone/filtro automatico -> sicurezza -> fertirrigazione`

La sequenza cambia se la fonte arriva già pressurizzata.

## 10. Controllo

Lead/standby:

- duty alternata per ore/cicli;
- pressione controllata via PID;
- setpoint modificabile solo entro limiti;
- low tank = stop pompe;
- pressione alta = trip;
- comando ON senza portata/pressione = fault;
- fault VFD = avvio standby;
- server/cloud offline non modifica la capacità di irrigare.

## 11. Vaso autoclave

Opzionale, non accumulo di processo.

Benchmark Zilmet Ultra-Pro 100 l, 10 bar, membrana intercambiabile: prezzo/listino corrente osservato ~€475; alternative retail possono essere inferiori. Dimensionare su anti-cycling/transienti, non “più grande è meglio”.

## 12. Failure modes

- pompa duty guasta;
- entrambe pompe indisponibili;
- VFD guasto;
- sensore pressione deriva/guasto;
- tank basso;
- cavitazione;
- strainer aspirazione ostruito;
- non ritorno bloccato;
- perdita tenuta meccanica;
- mandata chiusa/dead-head;
- sovrapressione;
- blackout;
- PLC/bus indisponibile.

Fallback: standby automatica; manual override locale; irrigazione prioritaria/degradata; ricambi critici.

## 13. OPEX

Misurare kWh per m³ pompato e per coltura/periodo.

`energia specifica = kWh pompe / m³ erogati`

Il VFD deve ridurre pressione/energia a domanda parziale evitando di strozzare inutilmente con valvole.

## 14. Gate

1. Q simultanea reale;
2. Q/P controlavaggio;
3. H statica;
4. pressione richiesta post-fertirrigazione;
5. perdite BOM-014/linee/valvole;
6. livello minimo tank;
7. NPSH;
8. vero 1+1 vs capacità degradata;
9. curve pump candidate;
10. controllo/VFD;
11. materiali acqua;
12. backup elettrico;
13. RFQ comparabili;
14. commissioning/failover.