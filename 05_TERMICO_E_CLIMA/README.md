# Carnia TerraTech — Punto 05: Termico e clima

**Aggiornato:** 17 settembre 2026  
**Stato:** `ARCHITETTURA DI BASE DEFINITA / BOM-009 E BOM-010 SVILUPPATE / CARICHI E PDC A FREDDO DA VALIDARE`.

## 1. Obiettivo

Il sistema termico deve proteggere produzione e impianti senza trasformare la serra in un edificio da mantenere sempre alla stessa temperatura.

Priorità:

- protezione gelo e danni critici;
- supporto fisiologico alle colture;
- gestione condensa/umidità quando il calore è utile allo scopo;
- riscaldamento vicino coltura/radice a bassa temperatura;
- modularità e priorità per comparto;
- accumulo termico per spostare energia nel tempo;
- funzionamento locale e degradato anche senza server/cloud;
- misurabilità di energia, temperature, portate e ore pompa.

## 2. Architettura working

`PDC esterne -> primario protetto -> scambiatore a piastre -> accumulo termico -> collettore secondario -> 6 circuiti indipendenti -> terminali near-crop / eventuali boost`.

Working concept:

- 3 × Kensol KHP-R290-22-3 = 66 kW nominali iniziali;
- predisposizione quarta unità -> 88 kW nominali;
- accumulo 30 m³ iniziale, predisposizione 40–50 m³;
- 6 circuiti secondari indipendenti;
- pompa, miscelazione, T mandata/ritorno e portata per comparto;
- terminali near-crop a bassa temperatura;
- piccoli aerotermi idronici solo se giustificati per boost/emergenza/deumidificazione.

Questi numeri non sostituiscono il calcolo del fabbisogno termico sul lotto reale.

## 3. Accumulo termico

Energia teorica acqua:

`E[kWh] ≈ 1,163 × V[m³] × ΔT[K]`.

Ordini di grandezza:

- 30 m³: ~349 kWh/10 K; ~698 kWh/20 K; ~1.047 kWh/30 K;
- 40 m³: ~465 / 930 / 1.395 kWh;
- 50 m³: ~581 / 1.163 / 1.744 kWh.

Per 30 m³ e ΔT 20 K, 66 kW nominali richiedono teoricamente ~10,6 h di carica; 88 kW ~7,9 h. Il dato reale dipende da capacità PDC a freddo, carichi simultanei e dispersioni.

Scenari da RFQ:

- T1: 6 × 5 m³ professionali;
- T2: 3 × 10 m³ custom/industriali;
- T3: 1 × 30 m³ custom, da accettare solo con vantaggio TCO evidente.

I normali serbatoi PE per acqua non vengono considerati automaticamente equivalenti a puffer professionali.

## 4. Primario e glicole

Il glicole deve essere confinato al primario esterno quando tecnicamente possibile.

Prima di inserire pompe primarie aggiuntive si deve verificare:

- se le PDC integrano già il circolatore;
- portata minima/nominale;
- prevalenza residua;
- comportamento in parallelo;
- prescrizioni antigelo del costruttore.

Ogni PDC deve essere isolabile senza fermare le altre.

## 5. Scambiatore

Confrontare almeno:

- 1 × ~100 kW;
- 2 × ~100 kW in parallelo e isolabili;
- ridondanza parziale con 2 × ~50–60 kW.

La scelta dipende da temperature, glicole, approach, portate, pressione differenziale, manutenzione e costo del fermo.

## 6. Modalità operative

### Produzione

Setpoint e priorità coerenti con coltura e fase produttiva.

### Economia

Riduzione setpoint, priorità comparti sensibili, carica accumulo nelle finestre energeticamente convenienti.

### Sopravvivenza

Evitare gelo/danno irreversibile a colture e impianti, anche sacrificando temporaneamente la piena produttività.

## 7. Regole di progetto

- nessuna potenza PDC è sufficiente finché non esiste il calcolo di carico;
- nessuna pompa viene scelta solo dalla sigla commerciale;
- terminali radianti e dorsali hanno funzioni diverse;
- i tratti emissivi non si coibentano; le dorsali di trasporto sì quando necessario;
- evitare glicole sull'intero accumulo se può essere confinato al primario;
- ogni comparto e ogni PDC devono essere isolabili;
- prevedere ricambi critici e manual override;
- contabilizzare energia elettrica e termica;
- misurare stratificazione e kWh termici realmente disponibili;
- dimensionare espansione e sicurezze con calcolo dedicato.

## 8. Package sviluppati

- `THERMAL_LOAD_METHOD.md` — metodo carico termico;
- `HYDRONIC_DISTRIBUTION.md` — distribuzione secondaria;
- `RFQ_HYDRONIC_DISTRIBUTION.md` — RFQ distribuzione;
- `THERMAL_STORAGE_PRIMARY.md` — accumulo/primario/scambiatore;
- `RFQ_THERMAL_STORAGE_PRIMARY.md` — RFQ BOM-010;
- `19_BOM_PRODOTTI_FORNITORI/TERMICO_DISTRIBUZIONE_IDRONICA.md` — BOM-009;
- `19_BOM_PRODOTTI_FORNITORI/TERMICO_ACCUMULO_PRIMARIO.md` — BOM-010;
- `22_FONTI_NORME_PREVENTIVI/TERMICO_DISTRIBUZIONE_SOURCES.md`;
- `22_FONTI_NORME_PREVENTIVI/TERMICO_ACCUMULO_PRIMARIO_SOURCES.md`.

## 9. Gate

Il punto 05 non diventa `VALIDATO` finché non sono disponibili almeno:

- lotto e dati meteo di progetto;
- geometria esecutiva della serra;
- proprietà reali della copertura e degli schermi;
- ricette climatiche C1–C6;
- carico termico per comparto e scenari produzione/economia/sopravvivenza;
- prestazioni PDC alle condizioni fredde e alle temperature acqua reali;
- P&ID e perdite di carico;
- scelta terminale near-crop;
- volume/architettura accumulo;
- dimensionamento scambiatore, glicole, espansione e sicurezza;
- preventivi confrontabili;
- strategia elettrica/FV/backup coerente.
