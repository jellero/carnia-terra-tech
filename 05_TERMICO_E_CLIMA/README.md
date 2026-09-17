# Carnia TerraTech — Punto 05: Termico e clima

**Aggiornato:** 17 settembre 2026  
**Stato:** `ARCHITETTURA STRUTTURATA / BOM-009…012 SVILUPPATE / VALIDAZIONE BLOCCATA DA LOTTO, CARICHI E RFQ`.

## 1. Obiettivo

Il sistema termico deve proteggere produzione e impianti senza trasformare la serra in un edificio da mantenere sempre alla stessa temperatura.

Priorità:

- protezione gelo e danni critici;
- supporto fisiologico alle colture;
- gestione condensa/umidità;
- riscaldamento vicino coltura/radice a bassa temperatura;
- modularità e priorità per comparto;
- accumulo termico per spostare energia nel tempo;
- funzionamento locale e degradato anche senza server/cloud;
- misurabilità di energia, temperature, portate, umidità rimossa e ore macchina.

## 2. Architettura working

`3× PDC iniziali (+ quarta predisposta) -> primario protetto -> HX -> accumulo 30 m³ -> collettore -> 6 circuiti -> near-crop + boost opzionale`.

Per il controllo umidità:

`HAF + sensori -> D1 heat+vent controllato -> opzionale D2 ventilazione meccanica con recupero -> opzionale D3 deumidificazione interna`.

Working concept:

- 3 × Kensol KHP-R290-22-3 iniziali;
- predisposizione quarta;
- accumulo 30 m³, predisposizione 40–50 m³;
- 6 circuiti secondari indipendenti;
- terminali near-crop come base;
- aerotermi agricoli solo come boost/emergenza/localizzazione;
- deumidificazione distinta dal semplice riscaldamento.

La dicitura 3+1 non significa N+1 finché la quarta PDC non è installata.

## 3. PDC Kensol — stato verificato

KHP-R290-22-3:

- A7/W35: 7,80–22,00 kW, assorbimento 1,48–5,90 kW, COP 3,73–5,27;
- A2/W35: 6,69–18,80 kW, assorbimento 1,45–5,50 kW, COP 3,42–4,61;
- SCOP W35 5,13; W55 3,84;
- max input 9 kW / 15,8 A;
- portata nominale 2,9 m³/h;
- pompa SHIMGE integrata;
- R290 1,30 kg;
- campo ambiente dichiarato -25…43 °C;
- 47 dB(A) pressione a 1 m / 62 dB(A) potenza sonora;
- peso 202 kg.

Aggregato massimo:

- 3 unità: 66 kW A7/W35, 56,4 kW A2/W35;
- 4 unità: 88 kW A7/W35, 75,2 kW A2/W35.

A-7/W35, A-7/W45, A-10/A-15 e defrost netto restano gate obbligatori.

## 4. Idraulica PDC

Pompa integrata confermata; prevalenza residua da chiarire.

Datasheet corrente 22 kW:

- 2,9 m³/h nominali;
- perdita interna max 65 kPa;
- prevalenza pompa 100 kPa a portata nominale.

Manuale KHP-R290 codice 6/26 riporta invece 45 kPa e 6,9 m. OEM/fornitore deve dichiarare revisione e curva valida della macchina offerta.

Pompa primaria esterna solo dopo calcolo di HX, filtri, glicole, tubi e valvole.

## 5. Accumulo termico

`E[kWh] ≈ 1,163 × V[m³] × ΔT[K]`.

- 30 m³: ~349 kWh/10 K; ~698 kWh/20 K; ~1.047 kWh/30 K;
- 40 m³: ~465 / 930 / 1.395 kWh;
- 50 m³: ~581 / 1.163 / 1.744 kWh.

Scenari RFQ:

- T1: 6 × 5 m³ professionali;
- T2: 3 × 10 m³ custom/industriali;
- T3: 1 × 30 m³ custom solo con TCO/affidabilità convincenti.

## 6. Primario, glicole e HX

Il glicole va confinato al primario esterno quando possibile. Ogni PDC deve essere isolabile.

Portata nominale aggregata PDC:

- 3 unità: 8,7 m³/h;
- 4 unità: 11,6 m³/h.

HX da confrontare:

- 1 × ~100 kW;
- 2 × ~100 kW isolabili;
- 2 × ~50–60 kW per ridondanza parziale.

## 7. Distribuzione secondaria

Accumulo -> collettore -> 6 circuiti indipendenti.

Per comparto:

- isolamento;
- pompa;
- eventuale miscelazione;
- T mandata/ritorno;
- misura/bilanciamento portata;
- scarico/sfiato;
- fallback locale.

Terminali near-crop working 2.700–3.000 m restano da crop card/layout. Preferenza RFQ per tubo specifico greenhouse.

## 8. BOM-012 — boost termico

Working quantity: **0–1 aerotermo per comparto**, con priorità di studio C1/C2/C6.

Candidati Reventon FARMER:

- HCF IP54-EC: ~4.800 m³/h, 430 W, IP54, prezzo retail benchmark €901 IVA 19% incl.;
- HCF IP66: 5.000 m³/h, 560 W, IP66, benchmark ~€822–943 IVA locale incl.

Dato critico per impianto PDC, HCF IP66:

- 50/40 °C acqua, 20 °C aria: ~13,7 kW;
- 40/30 °C acqua, 20 °C aria: ~7,0 kW;
- 50/40 °C acqua, 15 °C aria: ~17,1 kW;
- 40/30 °C acqua, 15 °C aria: ~10,3 kW.

Quindi il valore commerciale 50,2 kW non viene usato per il nostro dimensionamento a bassa temperatura.

## 9. Deumidificazione

### D1 — heat + vent

Baseline iniziale:

- HAF per uniformità;
- confronto humidity ratio/dew point interno-esterno;
- apertura controllata solo quando l'aria esterna è effettivamente più secca in termini assoluti;
- boost per compensare la perdita sensibile;
- coordinamento con schermi.

### D2 — ventilazione meccanica con recupero

Upgrade da valutare se il costo energetico della ventilazione invernale è rilevante. Candidato RFQ: AIRGAIA EXT'air o equivalente.

### D3 — condensazione interna dedicata

DryGair benchmark:

- DG-3: 11 l/h @18°C 80% RH, 2,3 kW, ~4.500 m³/h;
- DG-12: 43 l/h @18°C 80% RH, 9,55 kW, ~20.000 m³/h.

Prezzi: `DA PREVENTIVO`.

Nessuna capacità viene scelta senza bilancio di vapore per comparto.

## 10. Emergenza

Gli aerotermi **non sono una fonte termica alternativa**.

- una PDC guasta: capacità residua + accumulo + priorità comparti;
- tutte PDC ferme con tank caldo: scarica/localizzazione rapida con boost;
- blackout: UPS per controllo non equivale a backup di pompe/fan/PDC;
- blackout lungo/tank scarico: serve fonte di energia alternativa da punto 06/12.

La BOM-012 copre distribuzione e logica d'emergenza; la generazione di backup resta una decisione separata.

## 11. Modalità operative

### Produzione

Setpoint e priorità per coltura/fase.

### Economia

Setpoint ridotti, carica accumulo in finestre convenienti, deumidificazione con minimo costo termico/elettrico compatibile con il rischio coltura.

### Sopravvivenza

Load shedding, priorità comparti, protezione gelo/condensa critica e uso dell'energia residua senza dipendenza cloud.

## 12. Regole di progetto

- `22 kW PDC` non significa 22 kW sottozero;
- `50 kW aerotermo` non significa 50 kW con acqua 40/30;
- riscaldare non equivale a rimuovere umidità;
- controllo deumidificazione su humidity ratio/dew point/VPD, non sola UR;
- near-crop = base heating; aerotermo = boost;
- D2/D3 solo se TCO/rischio colturale li giustificano;
- glicole confinato al primario;
- ogni comparto/PDC deve essere isolabile;
- controllo vitale locale;
- misurare energia termica, elettrica e acqua condensata.

## 13. Package sviluppati

- `THERMAL_LOAD_METHOD.md`;
- `HYDRONIC_DISTRIBUTION.md`;
- `RFQ_HYDRONIC_DISTRIBUTION.md`;
- `THERMAL_STORAGE_PRIMARY.md`;
- `RFQ_THERMAL_STORAGE_PRIMARY.md`;
- `HEAT_PUMP_CASCADE.md`;
- `RFQ_HEAT_PUMPS.md`;
- `BOOST_DEHUMIDIFICATION_EMERGENCY.md`;
- `RFQ_BOOST_DEHUMIDIFICATION.md`;
- `POINT_05_CLOSURE_MATRIX.md`;
- `19_BOM_PRODOTTI_FORNITORI/TERMICO_DISTRIBUZIONE_IDRONICA.md` — BOM-009;
- `19_BOM_PRODOTTI_FORNITORI/TERMICO_ACCUMULO_PRIMARIO.md` — BOM-010;
- `19_BOM_PRODOTTI_FORNITORI/TERMICO_PDC_MODULARI.md` — BOM-011;
- `19_BOM_PRODOTTI_FORNITORI/TERMICO_BOOST_DEUMIDIFICAZIONE.md` — BOM-012;
- fonti dedicate in `22_FONTI_NORME_PREVENTIVI/`.

## 14. Gate

Il punto 05 non è esecutivo finché mancano:

- lotto/meteo;
- carico termico C1–C6;
- climate recipes/VPD;
- PDC sottozero e defrost netto;
- P&ID/perdite;
- terminale near-crop finale;
- volume tank/HX/glicole/espansione;
- quantità boost;
- bilancio umidità e scelta D1/D2/D3;
- backup energetico lungo termine;
- preventivi comparabili.

Dettaglio: `POINT_05_CLOSURE_MATRIX.md`.
