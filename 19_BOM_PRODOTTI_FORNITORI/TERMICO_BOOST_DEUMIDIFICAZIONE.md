# BOM-012 — Boost termico, deumidificazione ed emergenza

**Aggiornato:** 17 settembre 2026  
**Ambito:** 6 comparti serra, con priorità C1/C2/C6.  
**Stato:** `CANDIDATI REALI / QUANTITÀ DA CALCOLO TERMICO E BILANCIO UMIDITÀ`.

## 1. Distinta

| Codice | Voce | Quantità working | Stato | Prezzo / nota |
|---|---|---:|---|---|
| TH-BST-001 | Aerotermo idronico per comparto | 0–1/comparto | DA CALCOLO | priorità studio C1/C2/C6, non quantità d'ordine |
| TH-BST-002 | Reventon FARMER HCF IP54-EC | candidato | PREZZO TROVATO | €901 IVA 19% incl. retail DE; ~4.800 m³/h, 430 W, IP54 |
| TH-BST-003 | Reventon FARMER HCF IP66 | candidato | PREZZO TROVATO | benchmark retail UE ~€822–943 IVA locale incl.; 5.000 m³/h, 560 W, IP66 |
| TH-BST-004 | Valvola 2/3 vie + attuatore | per unità | DA RFQ | modulazione/isolamento |
| TH-BST-005 | Valvole isolamento | 2/unità | REQUISITO | manutenzione senza fermare zona |
| TH-BST-006 | Flessibili/giunti | per unità | CANDIDATO | benchmark Reventon set 3/4" €88,71 incl. DE |
| TH-BST-007 | Filtro/strainer locale | da P&ID | DA PROGETTO | protezione coil |
| TH-BST-008 | Scarico/sfiato | per unità | REQUISITO | manutenzione e gelo |
| TH-BST-009 | Vaschetta/scarico condensa | se cooling/condensa | CONDIZIONALE | obbligatoria se uso freddo |
| TH-BST-010 | Supporto sospensione/parete | per unità | DA RFQ | carico struttura e accessibilità |
| TH-BST-011 | Alimentazione 230 V | per unità | DA PROGETTO | protezione dedicata |
| TH-BST-012 | Controllo fan/EC | per unità | DA RFQ | preferenza modulante |
| TH-BST-013 | T mandata/ritorno | per unità/zona | REQUISITO | diagnosi resa |
| TH-BST-014 | Stato ventola/guasto | per unità | REQUISITO | feedback reale |
| TH-BST-015 | Ricambi boost | 1 lotto | DA SLA | motore/fan/attuatori/sensori |
| TH-DEH-001 | D1 heat + vent con aperture esistenti | 6 zone logiche | BASELINE | CAPEX incrementale basso, OPEX termico da simulare |
| TH-DEH-002 | Sensori T/RH interni | già previsti + ridondanza | REQUISITO | calibrazione e dew point |
| TH-DEH-003 | Sensore T/RH esterno | 1+ ridondanza | REQUISITO | humidity ratio esterna |
| TH-DEH-004 | Algoritmo humidity ratio/VPD | 6 zone | REQUISITO | no controllo su sola UR |
| TH-DEH-005 | Ventilazione meccanica con recupero | da studio | CANDIDATO D2 | AIRGAIA EXT'air o equivalente, prezzo da preventivo |
| TH-DEH-006 | Filtri/insect protection D2 | da portata | REQUISITO | perdita di carico e ricambi |
| TH-DEH-007 | Canali/distribuzione aria D2 | da layout | DA RFQ | evitare correnti fredde locali |
| TH-DEH-008 | Scarico condensa D2 | da unità | REQUISITO | antigelo/ispezione |
| TH-DEH-009 | DryGair DG-3 50 Hz | da bilancio | CANDIDATO D3 | 11 l/h @18°C 80%RH, 2,3 kW, prezzo da preventivo |
| TH-DEH-010 | DryGair DG-12 50 Hz | da bilancio | CANDIDATO D3 | 43 l/h @18°C 80%RH, 9,55 kW, prezzo da preventivo |
| TH-DEH-011 | Scarico condensato D3 | per macchina | OBBLIGATORIO | misura volume utile |
| TH-DEH-012 | Contatore energia D3 | per macchina | OBBLIGATORIO | l/kWh reale |
| TH-DEH-013 | Interfaccia PLC/BMS D3 | per macchina | DA CONFERMA | comandi, stati, allarmi |
| TH-DEH-014 | Trattamento anticorrosione D3 | se necessario | CONDIZIONALE | zolfo/fitosanitari/umidità |
| TH-EMG-001 | Priorità comparti emergenza | 1 logica | REQUISITO | C1/C2/C6 da confermare con crop card |
| TH-EMG-002 | Alimentazione pompe/valvole/fan critica | da load list | COLLEGAMENTO P06/P12 | UPS solo controlli, potenza da backup dedicato |
| TH-EMG-003 | Fonte termica alternativa | da rischio | OPEN POINT | non sostituita dagli aerotermi |
| TH-EMG-004 | Test modalità sopravvivenza | 1 lotto | OBBLIGATORIO | perdita PDC/HX/rete/sensori |
| TH-COM-001 | Commissioning aerotermi | 1 lotto | OBBLIGATORIO | portata acqua/aria, ΔT, resa |
| TH-COM-002 | Commissioning deumidificazione | 1 lotto | OBBLIGATORIO | kg/h acqua, kWh, uniformità |
| TH-DOC-001 | As-built/P&ID/parametri | 1 lotto | OBBLIGATORIO | manutenzione e tuning |

## 2. Benchmark potenza Reventon HCF IP66 a bassa T

Dati pubblicati dal costruttore/technical data:

| T acqua | T aria ingresso | Potenza | Portata acqua | Δp coil |
|---|---:|---:|---:|---:|
| 50/40 °C | 15 °C | 17,1 kW | 1,49 m³/h | 11 kPa |
| 50/40 °C | 20 °C | 13,7 kW | 1,19 m³/h | 7 kPa |
| 40/30 °C | 15 °C | 10,3 kW | 0,89 m³/h | 4 kPa |
| 40/30 °C | 20 °C | 7,0 kW | 0,61 m³/h | 2 kPa |

La potenza commerciale 50,2 kW è riferita a condizioni acqua/aria molto più calde. **Dimensionamento obbligatorio con temperature reali PDC/accumulo.**

## 3. Benchmark hardware boost

### HCF IP54-EC

- €901 IVA 19% inclusa osservati in Germania;
- `PREZZO TROVATO`;
- trasporto/accessori esclusi;
- 4.800 m³/h max, motore EC 430 W, IP54.

### HCF IP66

Prezzi retail osservati in UE:

- ~€822 IVA 19% inclusa presso Wolf Online;
- ~€943 TTC presso Climatik;
- `PREZZO TROVATO / VARIA PER MERCATO`.

Per 3 unità il solo hardware sarebbe indicativamente ~€2,5–2,8k IVA locale inclusa usando questi benchmark; per 6 ~€4,9–5,7k. **Non è preventivo impianto** e non giustifica la quantità.

## 4. Benchmark deumidificazione attiva

### DG-3 50 Hz

- 11 l/h @18°C / 80% RH;
- 2,3 kW elettrici;
- ~4.500 m³/h;
- 4,8 l/kWh dichiarati;
- 10–35 °C;
- ~300 kg;
- 400 V 3~ / max 14 A;
- prezzo `DA PREVENTIVO`.

### DG-12 50 Hz

- 43 l/h @18°C / 80% RH;
- 9,55 kW;
- ~20.000 m³/h;
- 4,5 l/kWh dichiarati;
- 10–35 °C;
- ~770 kg;
- 400 V 3~ / max 30 A;
- prezzo `DA PREVENTIVO`.

Non scalare linearmente i l/h: servono curve su T/RH e carico reale di traspirazione.

## 5. Bilancio umidità richiesto

Per ogni comparto calcolare almeno:

`vapore prodotto da coltura + evaporazione superfici - condensazione passiva - ricambio naturale - deumidificazione attiva = accumulo di vapore`

Input:

- LAI/fase colturale;
- irrigazione e drenaggio;
- T/RH/VPD;
- schermo aperto/chiuso;
- infiltrazioni;
- ventilazione;
- temperatura superfici/copertura;
- condensa osservata;
- setpoint notte/giorno.

## 6. Deumidificazione con aria esterna

La decisione deve usare umidità assoluta/humidity ratio, non soltanto RH.

Condizione minima per D1/D2:

`x_out < x_in - margine`

poi verificare:

- T esterna;
- vento/pioggia;
- rischio gelo;
- costo termico;
- posizione schermo;
- capacità boost disponibile.

## 7. Emergenza

Gli aerotermi sono terminali, non generatori.

- PDC singola guasta: redistribuire carico e usare accumulo;
- tutte PDC ferme: usare accumulo finché disponibile;
- blackout: alimentazione critica da punto 06/12;
- blackout lungo o accumulo esaurito: serve fonte termica/elettrica alternativa dedicata.

## 8. Open points

1. carico termico per zona;
2. profilo umidità C1–C6;
3. acqua 35/30, 40/30, 45/35 o 50/40 disponibile nei diversi scenari;
4. quantità aerotermi;
5. IP54-EC vs IP66;
6. ventilazione naturale D1 sufficiente o no;
7. necessità D2 con recupero;
8. necessità/capacità DG-3/DG-12;
9. potenza elettrica disponibile;
10. backup reale per blackout;
11. costo energia e TCO;
12. manutenzione/ricambi locali.
