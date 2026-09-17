# BOM-014 — Filtrazione acqua irrigua

**Aggiornato:** 17 settembre 2026  
**Ambito:** fonte/accumulo -> eventuale separazione sabbia -> **stadio fine pressurizzato** 120 mesh/130 µm -> fertirrigazione. Con tank atmosferico le pompe principali BOM-015 sono normalmente a monte della filtrazione fine automatica.  
**Stato:** `CANDIDATI REALI / ARCHITETTURA FINALE BLOCCATA DA ANALISI ACQUA, FONTE, PORTATA E PRESSIONE`.

## 1. Nota di sequenza idraulica

Il package filtrazione non impone più la sequenza `filtro fine -> pompe`.

Con serbatoio atmosferico e filtri automatici che richiedono pressione di controlavaggio, la baseline diventa:

`tank -> protezione aspirazione grossolana -> BOM-015 pompe 1+1 -> eventuale idrociclone -> filtro principale 120 mesh -> filtro sicurezza -> fertirrigazione`.

Se la fonte è già pressurizzata (pozzo con propria pompa/rete), la sequenza può cambiare. Il P&ID finale deve mostrare chiaramente quale pompa fornisce Q/P al controlavaggio.

## 2. Distinta principale

| Codice | Voce | Quantità working | Stato | Benchmark / nota |
|---|---|---:|---|---|
| FIL-ANA-001 | analisi acqua completa | 1+ campagne | OBBLIGATORIO | campionare anche periodo peggiore |
| FIL-HCY-001 | idrociclone 2" | 0–1 | CONDIZIONALE | Netafim-Arkal 15–25 m³/h, €363 + IVA |
| FIL-HCY-002 | scarico sabbia | 1 per idrociclone | REQUISITO SE PRESENTE | manuale/automatico da TCO |
| FIL-MAN-001 | filtro dischi manuale 2" Leader 120 mesh | 0–2 | CANDIDATO | €182 + IVA |
| FIL-MAN-002 | filtro dischi manuale 2" Dual 120 mesh | 0–2 | CANDIDATO | €241 + IVA; 25 m³/h max |
| FIL-AUT-001 | Spin-Klin 2" singolo automatico | 0–1 | CANDIDATO | €2.574 + IVA; 20 nominali / 15 media qualità |
| FIL-AUT-002 | Spin-Klin 2" doppio automatico | 0–1 | CANDIDATO | €4.321 + IVA; 40 nominali / 30 media qualità |
| FIL-SCR-001 | ScreenGuard automatico verticale 2" | 0–1 | ALTERNATIVA | da €2.988 + IVA; 25 m³/h max |
| FIL-SEC-001 | filtro sicurezza secondario 120 mesh | 1 | PREFERENZA | manuale dischi/rete, modalità degradata |
| FIL-MED-001 | media/graniglia | 0–1 package | CONDIZIONALE | acqua superficiale/organico difficile |
| FIL-HDR-001 | collettore ingresso | 1 | DA CALCOLO | DN Q max |
| FIL-HDR-002 | collettore uscita | 1 | DA CALCOLO | rami isolabili |
| FIL-BYP-001 | bypass manutenzione | 1 | REQUISITO | normalmente chiuso/monitorato |
| FIL-ISO-001 | valvole isolamento | per ramo | REQUISITO | full bore |
| FIL-NRV-001 | non ritorno | da P&ID | CANDIDATO | controlavaggio |
| FIL-PRS-001 | manometro monte | 1+ | REQUISITO | locale |
| FIL-PRS-002 | manometro valle | 1+ | REQUISITO | locale |
| FIL-DP-001 | trasmettitore Δp | 1 per stadio critico | PREFERENZA | PLC |
| FIL-FLW-001 | misura portata | coord. BOM-013/015 | REQUISITO | processo + lavaggio |
| FIL-BW-001 | valvole controlavaggio | da modello | INCLUSE/DA RFQ | ricambi separati |
| FIL-BW-002 | controller controlavaggio | 1 | DA RFQ | Δp + timer, locale |
| FIL-BW-003 | scarico controlavaggio | 1 rete | DA PROGETTO | no allagamenti/erosione |
| FIL-BW-004 | contatore acqua lavaggio | 0–1 | CANDIDATO | TCO |
| FIL-SUP-001 | skid/supporti | 1 | DA RFQ | manutenzione |
| FIL-ELC-001 | alimentazione/cablaggio | 1 package | DA RFQ | controller/sensori |
| FIL-CTL-001 | integrazione PLC | 1 package | REQUISITO | fallback locale |
| FIL-SP-001 | pacco dischi 120 mesh | 1–2 | RICAMBIO | €98 + IVA |
| FIL-SP-002 | membrana valvola Spin-Klin | 1–2 | RICAMBIO | €29 + IVA |
| FIL-SP-003 | elemento rete | 0–1 | RICAMBIO SE USATO | €29 + IVA benchmark |
| FIL-SP-004 | guarnizioni/O-ring | 1 lotto | RICAMBIO | da modello |
| FIL-COM-001 | prova Q/P/Δp | 1 | OBBLIGATORIO | baseline |
| FIL-COM-002 | test controlavaggio | 1 | OBBLIGATORIO | Q/P/volume |
| FIL-COM-003 | test modalità degradata | 1 | OBBLIGATORIO | ramo escluso |
| FIL-DOC-001 | P&ID/as-built/manuali | 1 | OBBLIGATORIO | manutenzione |

## 3. Requisito di filtrazione

BOM-013/PCJ: riferimento **120 mesh / circa 130 µm**.

Dimensionare per Q reale, contaminante, perdita di carico, frequenza di lavaggio e pressione disponibile.

## 4. Candidati

### Manuali

- Arkal Leader 2": 120 mesh, **€182 + IVA**;
- Arkal Dual 2": 25 m³/h max, 10 bar, 120 mesh, **€241 + IVA**.

### Automatici

- Spin-Klin 2" singolo: 20 m³/h nominali / 15 media qualità; 120 mesh; min backwash 2,8 bar standard / 1,5 bar LP; **€2.574 + IVA**;
- Spin-Klin doppio DN80: 40 / 30 m³/h; min backwash 2,8 / 1,5 bar; **€4.321 + IVA**;
- ScreenGuard 2": 25 m³/h max; min backwash 2 bar; rete inox 316; **da €2.988 + IVA**.

### Idrociclone

Arkal plastica 2": 15–25 m³/h, 10 bar, **€363 + IVA**; condizionale a sabbia significativa.

## 5. Scenari hardware — benchmark

- 2× Dual manuali: **€482 + IVA**;
- Spin-Klin singolo + Dual: **€2.815 + IVA**;
- Spin-Klin doppio + Dual: **€4.562 + IVA**;
- ScreenGuard + Dual: **da €3.229 + IVA**;
- idrociclone se necessario: +€363 + IVA.

Non includono skid, valvole, sensori, tubi, scarichi, posa e PLC.

## 6. Controlavaggio

Il controlavaggio entra nel duty point BOM-015.

Richiedere:

- Q lavaggio;
- P minima;
- durata/volume;
- frequenza;
- possibilità di irrigazione simultanea;
- pressione residua ai settori;
- scarico.

ScreenGuard 2" dichiara almeno ~12 m³/h durante il lavaggio; Spin-Klin richiede la pressione minima specifica della versione.

## 7. Cosa non rimuove

La filtrazione meccanica non risolve automaticamente sali, EC, durezza, carbonati, Fe/Mn disciolti o disinfezione microbiologica. Questi richiedono trattamento separato.

## 8. Manutenzione

Trend: Δp pulito/sporco, lavaggi, m³ lavaggio, sabbia, ore manutenzione, stato dischi/rete, membrane/guarnizioni e deviazione Q.

## 9. Gate

1. analisi acqua;
2. fonte/stagionalità;
3. sequenza idraulica fonte-pompe-filtri;
4. Q processo;
5. Q/P controlavaggio;
6. sabbia/organico;
7. automatico vs manuale;
8. ridondanza;
9. scarico;
10. trattamento separato se necessario;
11. duty point BOM-015;
12. RFQ comparabili.