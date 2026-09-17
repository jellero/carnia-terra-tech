# Metodo di calcolo del carico termico serra

**Aggiornato:** 17 settembre 2026  
**Stato:** `METODO DEFINITO / DATI REALI MANCANTI`.

## 1. Perché serve

La potenza termica non viene derivata da un W/m² generico. Il calcolo deve distinguere i sei comparti e almeno tre modalità operative: produzione, economia e sopravvivenza.

## 2. Input obbligatori

Per ogni comparto:

- geometria reale e volume;
- superficie e trasmittanza della copertura;
- effetto reale degli schermi chiusi;
- infiltrazioni/ventilazione minima;
- temperatura esterna di progetto e scenari meteo;
- temperatura interna target per coltura/fase;
- irraggiamento e guadagni solari quando pertinenti;
- inerzia di struttura, substrati, acqua e suolo;
- umidità/condensa e eventuale ventilazione/deumidificazione;
- potenza interna di pompe, luci, persone e altre sorgenti quando significativa;
- strategia di priorità e tempi di recupero.

## 3. Componenti del bilancio

Il modello deve tenere separati almeno:

- dispersione per trasmissione involucro;
- dispersione per infiltrazione/ricambio aria;
- ponti e discontinuità rilevanti;
- guadagni solari;
- guadagni interni;
- energia necessaria per rialzo temperatura dopo setback;
- eventuale carico per gestione umidità/condensa;
- margine progettuale esplicito, non nascosto.

## 4. Scenari da calcolare

### S1 — produzione

Setpoint coltura e continuità produttiva.

### S2 — economia

Setpoint ridotti e priorità termica a C1/C2/C6 o secondo piano agronomico reale.

### S3 — sopravvivenza

Temperatura minima per evitare gelo/danno irreversibile e mantenere operativi i sistemi critici.

### S4 — guasto parziale

Una PDC indisponibile e/o comparto escluso; verificare se accumulo e unità residue permettono la modalità sopravvivenza.

## 5. Output obbligatori

Per ogni comparto e scenario:

- kW di picco;
- kWh per notte/giorno tipo di progetto;
- temperatura di mandata/ritorno prevista;
- ΔT idronico di progetto;
- portata m³/h;
- ore di autonomia accumulo;
- priorità/load shedding;
- quota coperta con N, N-1 PDC;
- energia elettrica stimata con COP coerente con condizioni esterne e temperatura acqua.

## 6. Portata idronica

Per acqua, come relazione pratica:

`portata [m³/h] ≈ P[kW] / (1,163 × ΔT[K])`

Esempi aritmetici, non dimensionamento:

| Potenza zona | ΔT 5 K | ΔT 10 K |
|---:|---:|---:|
| 10 kW | ~1,72 m³/h | ~0,86 m³/h |
| 15 kW | ~2,58 m³/h | ~1,29 m³/h |
| 20 kW | ~3,44 m³/h | ~1,72 m³/h |

Questo dimostra perché la pompa va scelta dopo potenza, ΔT e perdite di carico.

## 7. Criterio accumulo

Energia teorica utile dell'acqua:

`E[kWh] ≈ volume[m³] × 1,163 × ΔT utile[K]`

Il ΔT utile non coincide automaticamente con la differenza tra temperatura massima e minima del serbatoio: dipende dalla temperatura minima richiesta dai terminali, stratificazione, scambiatore, PDC e logica di controllo.

## 8. Dati che NON sono ancora fatti

Restano working e da validare:

- 66 kW iniziali / 88 kW con quarta PDC;
- accumulo 30 m³ iniziale / 40–50 m³ futuro;
- 2.700–3.000 m di terminali near-crop;
- 2 tubi per fila C1/C2;
- setpoint e temperature acqua.

Nessuno di questi valori viene usato come dimensionamento definitivo prima del calcolo.