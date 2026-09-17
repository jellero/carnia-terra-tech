# BOM-014 — Filtrazione acqua irrigua

**Aggiornato:** 17 settembre 2026  
**Ambito:** fonte/accumulo -> pretrattamento -> filtrazione 120 mesh/130 µm -> pompe/fertirrigazione.  
**Stato:** `CANDIDATI REALI / ARCHITETTURA FINALE BLOCCATA DA ANALISI ACQUA E PORTATA`.

## 1. Distinta principale

| Codice | Voce | Quantità working | Stato | Benchmark / nota |
|---|---|---:|---|---|
| FIL-ANA-001 | analisi acqua completa | 1+ campagne | OBBLIGATORIO | campionare anche periodo peggiore |
| FIL-HCY-001 | idrociclone 2" | 0–1 | CONDIZIONALE | Netafim-Arkal 15–25 m³/h, €363 + IVA |
| FIL-HCY-002 | scarico sabbia | 1 per idrociclone | REQUISITO SE PRESENTE | manuale/automatico da TCO |
| FIL-MAN-001 | filtro dischi manuale 2" Leader 120 mesh | 0–2 | CANDIDATO | €182 + IVA |
| FIL-MAN-002 | filtro dischi manuale 2" Dual 120 mesh | 0–2 | CANDIDATO | €241 + IVA; 25 m³/h max |
| FIL-AUT-001 | Spin-Klin 2" singolo automatico | 0–1 | CANDIDATO | €2.574 + IVA; 20 m³/h nominali / 15 media qualità |
| FIL-AUT-002 | Spin-Klin 2" doppio automatico | 0–1 | CANDIDATO | €4.321 + IVA; 40 nominali / 30 media qualità |
| FIL-SCR-001 | ScreenGuard automatico verticale 2" | 0–1 | ALTERNATIVA | da €2.988 + IVA; 25 m³/h max |
| FIL-SEC-001 | filtro sicurezza secondario 120 mesh | 1 | PREFERENZA | manuale dischi/rete, dimensionato modalità degradata |
| FIL-MED-001 | media/graniglia | 0–1 package | CONDIZIONALE | acqua superficiale/organico difficile, DA RFQ |
| FIL-HDR-001 | collettore ingresso | 1 | DA CALCOLO | DN portata max |
| FIL-HDR-002 | collettore uscita | 1 | DA CALCOLO | predisporre isolamento rami |
| FIL-BYP-001 | bypass manutenzione | 1 | REQUISITO | normalmente chiuso/piombabile o monitorato |
| FIL-ISO-001 | valvole isolamento | per ramo | REQUISITO | full bore/serviceable |
| FIL-NRV-001 | non ritorno | da P&ID | CANDIDATO | evitare inversioni durante lavaggi |
| FIL-PRS-001 | manometro monte | 1+ | REQUISITO | lettura locale |
| FIL-PRS-002 | manometro valle | 1+ | REQUISITO | lettura locale |
| FIL-DP-001 | trasmettitore Δp | 1 per stadio critico | PREFERENZA | analogico/Modbus da standardizzare |
| FIL-FLW-001 | misura portata | coordinata BOM-013/015 | REQUISITO | Q processo + Q lavaggio |
| FIL-BW-001 | valvole controlavaggio | da modello | INCLUSE/DA RFQ | separare ricambi |
| FIL-BW-002 | controller controlavaggio | 1 | DA RFQ | Δp + timer, locale |
| FIL-BW-003 | scarico controlavaggio | 1 rete | DA PROGETTO | non allagare tech barn/terreno |
| FIL-BW-004 | contatore acqua lavaggio | 0–1 | CANDIDATO | utile per TCO/diagnostica |
| FIL-SUP-001 | skid/supporti | 1 | DA RFQ | accesso smontaggio elementi |
| FIL-ELC-001 | alimentazione/cablaggio | 1 package | DA RFQ | valvole/controller/sensori |
| FIL-CTL-001 | integrazione PLC | 1 package | REQUISITO | allarmi/local fallback |
| FIL-SP-001 | pacco dischi 120 mesh automatico | 1–2 | RICAMBIO | €98 + IVA/cad |
| FIL-SP-002 | membrana valvola Spin-Klin | 1–2 | RICAMBIO | €29 + IVA/cad |
| FIL-SP-003 | elemento rete ScreenGuard Mini | 0–1 | RICAMBIO SE USATO | €29 + IVA |
| FIL-SP-004 | guarnizioni/O-ring | 1 lotto | RICAMBIO | da distinta modello |
| FIL-COM-001 | prova idraulica | 1 lotto | OBBLIGATORIO | Q/P/Δp |
| FIL-COM-002 | test controlavaggio | 1 lotto | OBBLIGATORIO | volume, tempo, pressione residua |
| FIL-COM-003 | test modalità degradata | 1 lotto | OBBLIGATORIO | ramo fuori servizio/bypass |
| FIL-DOC-001 | P&ID/as-built/manuali | 1 lotto | OBBLIGATORIO | base manutenzione |

## 2. Requisito di filtrazione

BOM-013 / PCJ impone come riferimento **120 mesh / circa 130 µm**.

Non basta indicare `120 mesh`: il filtro deve essere dimensionato per:

- portata reale;
- qualità acqua;
- perdita di carico accettabile;
- frequenza e disponibilità del controlavaggio;
- tipo di contaminante.

## 3. Candidati manuali

### Netafim-Arkal 2" Leader

- 120 mesh disponibile;
- **€182 + IVA**;
- filtro principale su piccoli impianti o secondario su impianti maggiori;
- stato: `PREZZO TROVATO`.

### Netafim-Arkal 2" Dual

- 2" filettato maschio;
- 25 m³/h max;
- 10 bar max;
- 120 mesh;
- superficie filtrante 953 cm²;
- **€241 + IVA**;
- stato: `PREZZO TROVATO`.

Due unità manuali in parallelo possono essere economicamente interessanti per ridondanza, ma richiedono più manodopera e non risolvono acqua molto sporca.

## 4. Candidati automatici

### Spin-Klin 2" singolo

- 20 m³/h nominali;
- 15 m³/h con acqua media qualità;
- 120 mesh / 130 µm;
- 10 bar standard / 6 bar low pressure;
- min controlavaggio 2,8 bar standard / 1,5 bar low pressure;
- **€2.574 + IVA**.

### Spin-Klin 2" doppio

- 3" DN80;
- 40 m³/h nominali;
- 30 m³/h con acqua media qualità;
- 120 mesh / 130 µm;
- 10 bar standard / 6 bar low pressure;
- min controlavaggio 2,8 bar standard / 1,5 bar low pressure;
- **€4.321 + IVA**.

### ScreenGuard automatico 2"

- 25 m³/h max;
- 10 bar max;
- min controlavaggio 2 bar;
- rete inox 316;
- pulizia automatica su tempo o Δp;
- **da €2.988 + IVA**.

Scelta automatica da fare sul contaminante reale, non sul prezzo isolato.

## 5. Idrociclone

Netafim-Arkal plastica 2":

- 15–25 m³/h;
- 10 bar;
- separazione sabbia dichiarata >90% nelle condizioni previste dal prodotto;
- **€363 + IVA**.

Netafim raccomanda idrociclone a monte quando la sabbia è significativa; il blog tecnico italiano cita come soglia indicativa concentrazioni >2 ppm.

## 6. Costi hardware di scenario — solo benchmark

### M1 — manuale minimale

- 1× Dual 2": €241 + IVA;
- manometri/valvole/raccordi non inclusi.

### M2 — manuale ridondato

- 2× Dual 2": **€482 + IVA** di soli filtri;
- permette manutenzione su un ramo ma la capacità degradata dipende dal Q reale.

### A1 — automatico singolo + sicurezza manuale

- Spin-Klin singolo €2.574 + Dual €241 = **€2.815 + IVA** di soli filtri.

### A2 — automatico doppio + sicurezza manuale

- Spin-Klin doppio €4.321 + Dual €241 = **€4.562 + IVA** di soli filtri.

### A3 — ScreenGuard automatico + sicurezza manuale

- ScreenGuard da €2.988 + Dual €241 = **da €3.229 + IVA** di soli filtri.

Se serve idrociclone aggiungere **€363 + IVA** di solo corpo, oltre a scarico e raccordi.

Questi scenari non comprendono skid, valvole, sensori, controller, tubi, posa e scarichi.

## 7. Controlavaggio

Il controlavaggio è un carico progettuale:

- Spin-Klin: verificare pressione minima 2,8 bar o 1,5 bar per variante low-pressure;
- ScreenGuard 2": minimo dichiarato 2 bar e almeno 12 m³/h durante il lavaggio;
- verificare se la pompa principale può sostenere simultaneamente irrigazione + lavaggio;
- misurare acqua persa per ciclo e frequenza.

## 8. Cosa la filtrazione non fa

I filtri standard non rimuovono:

- sali disciolti;
- durezza;
- EC elevata;
- carbonati disciolti;
- ferro/manganese non precipitati;
- contaminazione microbiologica in senso di disinfezione.

Questi problemi richiedono un package di trattamento separato.

## 9. Manutenzione

Registrare:

- Δp pulito baseline;
- Δp prima/dopo lavaggio;
- numero lavaggi;
- m³ acqua lavaggio;
- ore manutenzione;
- sabbia raccolta;
- stato dischi/rete;
- sostituzioni membrane/guarnizioni;
- deviazioni portata.

## 10. Gate

1. analisi acqua;
2. fonte e stagionalità;
3. Q processo reale;
4. P disponibile;
5. Q/P controlavaggio;
6. sabbia sì/no;
7. organico/alga e necessità media filtration;
8. automatico vs manuale;
9. ridondanza;
10. scarico controlavaggio;
11. eventuale trattamento chimico/RO separato;
12. RFQ comparabili.