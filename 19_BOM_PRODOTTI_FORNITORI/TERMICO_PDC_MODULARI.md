# BOM-011 — PDC modulari 3+1

**Aggiornato:** 17 settembre 2026  
**Candidato:** Kensol KHP-R290-22-3, monoblocco R290, 3 fasi.  
**Stato:** `CANDIDATO REALE / PREZZO TROVATO / DATI A FREDDO INCOMPLETI`.

## 1. Distinta

| Codice | Voce | Quantità working | Stato | Prezzo / nota |
|---|---|---:|---|---|
| TH-HP-001 | KHP-R290-22-3 | 3 iniziali | CANDIDATO | €3.616,74 + IVA/cad Senetic DE |
| TH-HP-002 | quarta KHP-R290-22-3 | 0–1 | PREDISPOSIZIONE / OPZIONE RFQ | decisione dopo carico e A-7 |
| TH-HP-003 | basamenti | 3 + predisposizione 1 | DA RFQ | robusti, livellati, accessibili |
| TH-HP-004 | antivibranti | 4 punti/unità o OEM | DA RFQ | compatibilità peso 202 kg |
| TH-HP-005 | valvole isolamento idraulico | 2/unità + accessori | REQUISITO | rimozione singola PDC |
| TH-HP-006 | flessibili/giunti antivibranti | per unità | CANDIDATO | dimensionare perdita carico |
| TH-HP-007 | non ritorno | per ramo se richiesto | DA P&ID | prevenire ricircoli |
| TH-HP-008 | filtro/defangazione | da P&ID | REQUISITO | acqua tecnica conforme OEM |
| TH-HP-009 | scarico/sfiato | per ramo | REQUISITO | manutenzione e gelo |
| TH-HP-010 | drenaggio condensa | per unità | REQUISITO | gestire gelo e scarico sicuro |
| TH-HP-011 | coibentazione tubi esterni | per ramo | REQUISITO | meteo/UV |
| TH-HP-012 | glicole primario | da volume | BOM-010 | confinato al tratto necessario |
| TH-HP-013 | sezionatore locale | 1/unità | REQUISITO | accessibile manutenzione |
| TH-HP-014 | protezione elettrica dedicata | 1/unità | DA PROGETTO | scheda corrente raccomanda C16A |
| TH-HP-015 | cavo potenza | da layout | DA PROGETTO | verifica targa/manuale/norma IT |
| TH-HP-016 | contatore energia | 1/unità o ramo | REQUISITO | COP reale e manutenzione |
| TH-HP-017 | interfaccia dati | 1/unità | DA CONFERMA OEM | Modbus/RS485/altro |
| TH-HP-018 | controllore cascata | 1 | DA ARCHITETTURA | OEM o PLC, no cloud dependency |
| TH-HP-019 | sensori T ingresso/uscita | per unità | REQUISITO | se non esposti affidabilmente via bus |
| TH-HP-020 | stato defrost/allarmi | per unità | REQUISITO DATI | telemetria PLC |
| TH-HP-021 | spazio sicurezza/manutenzione | 4 piazzole | REQUISITO | manuale: 0,5/1,5/1,0/0,5 m minimi per unità |
| TH-HP-022 | protezione neve/ghiaccio | da sito | DA PROGETTARE | non ostacolare flusso aria |
| TH-HP-023 | commissioning OEM | 3–4 unità | OBBLIGATORIO | garanzia e curve reali |
| TH-HP-024 | ricambi critici | 1 lotto | DA SLA | decidere dopo lead time |
| TH-HP-025 | documentazione/as-built | 1 lotto | OBBLIGATORIO | matricole, firmware, parametri |

## 2. Prezzo hardware

Prezzo unitario osservato:

- €3.616,74 + IVA;
- ~€4.412,42 IVA 22% inclusa come benchmark italiano.

Totale sole PDC:

- 3 unità: €10.850,22 + IVA / ~€13.237,26 IVA incl.;
- 4 unità: €14.466,96 + IVA / ~€17.649,68 IVA incl.

Non include installazione né componenti BOM-010/011 accessori.

## 3. Prestazioni certificate/pubblicate del modello

### A7/W35

- 7,80–22,00 kW termici;
- 1,48–5,90 kW elettrici secondo datasheet corrente;
- COP 3,73–5,27.

### A2/W35

- 6,69–18,80 kW termici;
- 1,45–5,50 kW elettrici;
- COP 3,42–4,61.

### Stagionale

- SCOP W35: 5,13;
- SCOP W55: 3,84.

## 4. Idraulica integrata

Datasheet corrente:

- pompa integrata SHIMGE;
- portata nominale 2,9 m³/h;
- perdita interna max 65 kPa;
- prevalenza pompa a portata nominale 100 kPa;
- attacchi 1".

Manuale 6/26 riporta valori diversi (45 kPa / 6,9 m). Chiarimento OEM obbligatorio.

## 5. Elettrico

Per unità:

- 380–415 V 3N 50 Hz;
- max input dichiarato 9 kW;
- max corrente 15,8 A;
- protezione raccomandata datasheet C16A.

Aggregato teorico massimo dichiarato:

- 3 unità: 27 kW;
- 4 unità: 36 kW.

Il progetto elettrico deve considerare anche pompe, resistenze accessorie eventualmente presenti/abilitate, quadro, protezioni e contemporaneità reale.

## 6. Acustica e layout

Datasheet:

- pressione sonora 1 m: 47 dB(A);
- potenza sonora EN 12102: 62 dB(A).

Layout da validare con quattro piazzole e percorsi aria indipendenti. Evitare che lo scarico freddo di una unità venga aspirato da un'altra.

## 7. Failure modes

- compressore guasto;
- pompa integrata guasta;
- ventilatore guasto;
- scheda inverter/control guasta;
- sensore T/P/flow errato;
- ghiaccio/condensa che ostruisce scarico;
- perdita acqua/glicole;
- perdita R290;
- defrost ripetuti con forte perdita capacità;
- alimentazione assente su una fase/ramo;
- bus dati indisponibile;
- errore cascata che cicla le unità.

Fallback: unità guasta isolabile idraulicamente/elettricamente; altre unità continuano; accumulo fornisce inerzia; PLC passa in modalità economia/sopravvivenza se capacità residua insufficiente.

## 8. Ricambi

Non si compra automaticamente una PDC completa di scorta. Prima richiedere prezzi e lead time di:

- scheda principale/inverter;
- display/controller;
- pompa SHIMGE completa;
- motore/i ventilatore;
- sensori temperatura/pressione/flow;
- valvole/attuatori refrigerante se vendibili;
- kit guarnizioni/raccordi idraulici.

La quarta macchina installata può diventare la forma più efficace di ridondanza solo se il carico critico lo giustifica.

## 9. Open points

1. A-7/W35 e A-7/W45;
2. A-10/A-15 e capacità netta con defrost;
3. massima/minima temperatura acqua nelle condizioni reali;
4. curva pompa integrata e prevalenza residua;
5. revisione corretta dei dati 5,9/6,9 kW e 65/45 kPa;
6. funzione cascade OEM;
7. protocollo e registri PLC;
8. distanze R290 definitive per installazione plurima;
9. garanzia 5+2 in Italia;
10. rete assistenza/ricambi FVG;
11. carico termico reale e decisione 3 vs 4 unità installate.
