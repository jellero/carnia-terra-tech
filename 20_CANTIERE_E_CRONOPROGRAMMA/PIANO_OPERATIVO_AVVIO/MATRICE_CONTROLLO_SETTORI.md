# Matrice di controllo del piano operativo

**Aggiornato:** 18 settembre 2026

| Settore | Envelope | Fase iniziale | Dipendenza primaria | Verifica di uscita | Stato iniziale |
|---|---:|---|---|---|---|
| Finanza/cassa | governa €950k | F0 | concessioni/banca | 70% liquidità strutturata + riserve/ponte | DA CHIUDERE |
| Terreno | €60k | F1 | finanza | due diligence + masterplan | LOTTO DA TROVARE |
| Agronomia P1 | OPEX | F1–F5 | lotto/stagione/mercato | crop card + calendario | DA VALIDARE |
| Serra | €350k | F2–F4 | lotto/geotecnica | involucro + 3 comparti operativi | RFQ BLOCCATO DA LOTTO |
| Acqua | €55k | F2–F4 | fonte/crop card | portata/pressione/qualità testate | DATI REALI MANCANTI |
| Termico | €65k | F2–F4 | meteo/carichi | P1 in sicurezza + fallback | CARICO DA CHIUDERE |
| Energia | €130k | F2–F4 | load register/DSO | blackout/EMS/BESS SAT | DSO/RFQ DA CHIUDERE |
| Tech Barn | €95k | F2–F4 | kg/day/SKU | freddo + lotto + pack | DIMENSIONAMENTO DA P1 |
| Automazione | €25k | F3–F4 | impianti | locale/offline/restore | ARCHITETTURA PRONTA |
| Spaccio | €20k | F4–F6 | SKU/SUAP | ordine→ritiro/vendita completo | RFQ/SUAP |
| Macchine/cicli materia/quota | €90k | F1–F4 | layout/flussi/TCO | mezzo + humus + accesso sicuro | RFQ BLOCCATO DA LOTTO |
| Personale | €120k riserva condivisa | F0–F7 | cronoprogramma | team formato senza burn eccessivo | COSTI REALI DA PAGHE |

## Regole colore

- **VERDE:** ordinabile/eseguibile;
- **GIALLO:** progetto pronto ma manca un dato reale;
- **ROSSO:** spesa vietata finché non chiude il requisito;
- **BLU:** predisposizione oggi / acquisto dopo.

## Limiti di governo

### Scostamento ≤5%
Gestibile all'interno del settore se non tocca riserva.

### Scostamento 5–10%
Revisione budget e compensazione esplicita con altra voce CAPEX non critica.

### Scostamento >10%
Stop ordine e revisione del piano master.

### Totale >€1,05M
Revisione completa della Fase P1 e della copertura finanziaria.

## Verifica mensile

Ogni mese aggiornare:
- budget approvato;
- impegnato;
- pagato;
- contributo maturato;
- anticipo/acconto incassato;
- IVA anticipata;
- riserva residua;
- forecast 90 giorni;
- milestone D1/D2/D3/D4;
- rischio più alto per settore.

## Verifica per l'espansione P2

Tutti:
1. P1 tecnicamente stabile;
2. domanda sufficiente;
3. margine per comparto positivo e misurato;
4. riserva non in erosione strutturale;
5. personale non oltre soglia;
6. debito sostenibile;
7. nessuna criticità P0;
8. CAPEX P2 coperto senza dipendere da ricavi ipotetici.
