# Punto 05 — Matrice di chiusura Termico e clima

**Aggiornato:** 17 settembre 2026  
**Stato generale:** `ARCHITETTURA STRUTTURATA / VALIDAZIONE BLOCCATA DA LOTTO, CARICHI E PREVENTIVI`.

## 1. Matrice

| Blocco | Stato | Cosa è strutturato | Cosa manca |
|---|---|---|---|
| metodo carico termico | METODO DEFINITO | input/scenari produzione-economia-sopravvivenza | lotto, meteo, U reali, infiltrazioni, crop recipes |
| terminali near-crop | BOM-009 | candidati greenhouse, formule, failure mode | metri reali, resa/m, file, temperature acqua |
| 6 gruppi zona | BOM-009 | pompe/miscelazione/misure/isolamento | portate/prevalenze, DN, P&ID |
| accumulo 30→50 m³ | BOM-010 | scenari 6×5 / 3×10 / 1×30 m³ | autonomia richiesta, perdite, RFQ, layout |
| scambiatore | BOM-010 | 1×100 / 2×100 / ridondanza parziale | temperature/portate/glicole/Δp, RFQ |
| primario/glicole | BOM-010 | confinamento glicole, sicurezza, sensori | Tmin sito, volume, concentrazione, DN |
| PDC Kensol 3+1 | BOM-011 | modello/prezzo/A7/A2/idraulica/installazione | A-7/A-10/A-15, W45, defrost netto, revisione OEM |
| boost idronico | BOM-012 | candidati Reventon, rese 40/30 e 50/40, RFQ | quantità e potenza per comparto |
| deumidificazione D1 | BOM-012 | logica heat+vent su humidity ratio | carico vapore, meteo sito, tuning |
| deumidificazione D2 | CANDIDATO | ventilazione meccanica + recupero | portata, distribuzione, CAPEX/OPEX, RFQ |
| deumidificazione D3 | CANDIDATO | DryGair DG-3/DG-12 benchmark | kg/h richiesti, curve T/RH, CAPEX/OPEX |
| emergenza termica | ARCHITETTURA | priorità, uso accumulo, load shedding | fonte backup lunga durata, generatore, autonomia |
| controllo | REQUISITO DEFINITO | PLC locale, misure energia/T/RH/portate, fail-safe | I/O/protocolli finali, software commissioning |
| manutenzione/ricambi | REQUISITO DEFINITO | categorie, failure mode, stock critico | modelli finali, SLA, lead time Italia |

## 2. Dipendenze che sbloccano più voci

### Lotto reale

Sblocca:

- Tmin e profilo meteo;
- umidità assoluta esterna;
- vento/neve;
- condizioni PDC sottozero;
- strategia antigelo;
- D1/D2 deumidificazione;
- rumore/layout esterno PDC.

### Crop card + climate recipes C1–C6

Sblocca:

- setpoint T/RH/VPD;
- profilo traspirazione;
- priorità emergenza;
- potenza near-crop;
- boost;
- capacità deumidificazione.

### Layout esecutivo

Sblocca:

- metri tubi;
- DN;
- perdite di carico;
- posizione tank/HX/PDC;
- posizione aerotermi;
- eventuale distribuzione D2/D3.

### Preventivi/OEM

Sbloccano:

- prestazioni PDC sottozero;
- revisione reale Kensol;
- TCO accumulo;
- TCO D2/D3;
- ricambi/garanzie;
- lead time.

## 3. Principi da non riaprire senza motivo

- 6 circuiti termici indipendenti;
- terminali near-crop come riscaldamento base;
- aerotermi solo boost/rapida distribuzione, non base heating indiscriminato;
- glicole confinato al primario quando possibile;
- accumulo termico come batteria principale;
- PDC modulari e isolabili;
- controllo locale, non cloud-dependent;
- nessuna potenza commerciale usata senza condizioni di prova;
- deumidificazione misurata in massa d'acqua rimossa, non in calo di UR dovuto al solo riscaldamento;
- backup di distribuzione separato da backup di generazione.

## 4. Gate `VALIDATO / PRE-ORDINABILE`

Il punto 05 può diventare validato solo quando:

1. lotto e dati meteo sono reali;
2. carico termico è calcolato per i 6 comparti;
3. ricette climatiche e VPD sono definite;
4. PDC hanno curve sottozero e defrost verificati;
5. P&ID e perdite di carico sono chiusi;
6. terminale near-crop è scelto e quantificato;
7. accumulo/HX/glicole/espansione sono dimensionati;
8. boost è dimensionato;
9. carico umidità e strategia D1/D2/D3 sono calcolati;
10. backup energetico di lunga durata è definito;
11. offerte comparabili sostituiscono i benchmark principali;
12. CAPEX/OPEX e manutenzione sono ricostruiti bottom-up;
13. commissioning e test di failure sono pianificati.

Fino ad allora il punto 05 è una base di progettazione completa, non un esecutivo.
