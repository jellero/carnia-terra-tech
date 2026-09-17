# Carnia TerraTech — Punto 05: Termico e clima

**Aggiornato:** 17 settembre 2026  
**Stato:** `ARCHITETTURA DI BASE DEFINITA / BOM-009, 010 E 011 SVILUPPATE / CARICHI E PRESTAZIONI SOTTOZERO DA VALIDARE`.

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

`3× PDC iniziali (+ quarta predisposta) -> primario protetto -> scambiatore a piastre -> accumulo termico -> collettore secondario -> 6 circuiti indipendenti -> terminali near-crop / eventuali boost`.

Working concept:

- 3 × Kensol KHP-R290-22-3 iniziali;
- predisposizione quarta unità;
- accumulo 30 m³ iniziale, predisposizione 40–50 m³;
- 6 circuiti secondari indipendenti;
- pompa, miscelazione, T mandata/ritorno e portata per comparto;
- terminali near-crop a bassa temperatura;
- piccoli aerotermi idronici solo se giustificati per boost/emergenza/deumidificazione.

La dicitura 3+1 non significa N+1 finché la quarta unità non è realmente installata.

## 3. PDC Kensol — stato verificato

Modello working: KHP-R290-22-3, R290, 3 fasi.

Dati dal datasheet corrente:

- A7/W35: 7,80–22,00 kW, assorbimento 1,48–5,90 kW, COP 3,73–5,27;
- A2/W35: 6,69–18,80 kW, assorbimento 1,45–5,50 kW, COP 3,42–4,61;
- SCOP W35: 5,13;
- SCOP W55: 3,84;
- max input: 9 kW / 15,8 A;
- portata nominale: 2,9 m³/h;
- pompa SHIMGE integrata;
- R290 1,30 kg;
- campo ambiente dichiarato -25…43 °C;
- 47 dB(A) pressione sonora a 1 m / 62 dB(A) potenza sonora;
- peso 202 kg.

Potenza massima aggregata:

- 3 unità: 66 kW a A7/W35, ma 56,4 kW a A2/W35;
- 4 unità: 88 kW a A7/W35, ma 75,2 kW a A2/W35.

I dati A-7/W35, A-7/W45 e il derating netto da defrost non sono ancora disponibili nei documenti pubblici esaminati e sono gate obbligatori.

## 4. Idraulica PDC

La pompa integrata è confermata, ma la prevalenza residua resta da chiarire.

Datasheet corrente 22 kW:

- portata nominale 2,9 m³/h;
- perdita interna max 65 kPa;
- prevalenza pompa alla portata nominale 100 kPa.

Il manuale KHP-R290 codice 6/26 riporta invece perdita interna 45 kPa e prevalenza 6,9 m. Questa discrepanza deve essere chiusa da OEM/fornitore sulla revisione effettivamente offerta.

Non inserire una pompa primaria esterna solo per prudenza: prima acquisire curva Q/H integrata e perdita reale di HX, filtri, glicole, tubi e valvole.

## 5. Accumulo termico

Energia teorica acqua:

`E[kWh] ≈ 1,163 × V[m³] × ΔT[K]`.

Ordini di grandezza:

- 30 m³: ~349 kWh/10 K; ~698 kWh/20 K; ~1.047 kWh/30 K;
- 40 m³: ~465 / 930 / 1.395 kWh;
- 50 m³: ~581 / 1.163 / 1.744 kWh.

Per 30 m³ e ΔT 20 K, 66 kW nominali richiederebbero teoricamente ~10,6 h di carica, ma alle temperature fredde la potenza PDC reale cala e possono esserci carichi simultanei e defrost.

Scenari da RFQ:

- T1: 6 × 5 m³ professionali;
- T2: 3 × 10 m³ custom/industriali;
- T3: 1 × 30 m³ custom, solo con vantaggio TCO evidente.

I normali serbatoi PE per acqua non sono automaticamente equivalenti a puffer professionali.

## 6. Primario e glicole

Il glicole deve essere confinato al primario esterno quando tecnicamente possibile.

Ogni PDC deve essere isolabile senza fermare le altre.

Portata nominale aggregata dalle PDC:

- 3 unità: 8,7 m³/h;
- 4 unità: 11,6 m³/h.

Il dimensionamento reale deve considerare viscosità glicole, HX, filtri, valvole e curve pompe integrate.

## 7. Scambiatore

Confrontare almeno:

- 1 × ~100 kW;
- 2 × ~100 kW in parallelo e isolabili;
- ridondanza parziale con 2 × ~50–60 kW.

La scelta dipende da temperature, glicole, approach, portate, pressione differenziale, manutenzione e costo del fermo.

## 8. Installazione PDC

Il manuale della serie KHP-R290 richiede installazione esterna ventilata, base robusta/livellata, drenaggio condensa, assenza ostacoli e lontananza da fonti di ignizione.

Clearance minime indicate per la singola unità:

- ingresso aria A >500 mm;
- uscita aria B >1500 mm;
- lato servizio C >1000 mm;
- lato D >500 mm.

Per 3–4 unità affiancate il layout deve essere confermato dal fornitore per evitare ricircolo aria fredda, interferenze di sbrinamento, accumulo neve/ghiaccio e problemi R290.

## 9. Modalità operative

### Produzione

Setpoint e priorità coerenti con coltura e fase produttiva.

### Economia

Riduzione setpoint, priorità comparti sensibili, carica accumulo nelle finestre energeticamente convenienti.

### Sopravvivenza

Evitare gelo/danno irreversibile a colture e impianti, anche sacrificando temporaneamente la piena produttività.

La cascata deve poter ridurre automaticamente il carico serra quando una PDC è guasta o la capacità disponibile non copre la modalità richiesta.

## 10. Regole di progetto

- nessuna potenza PDC è sufficiente finché non esiste il calcolo di carico;
- `22 kW` non viene usato come potenza a -7 °C;
- nessuna pompa esterna viene scelta prima della curva della pompa integrata;
- terminali radianti e dorsali hanno funzioni diverse;
- i tratti emissivi non si coibentano; le dorsali di trasporto sì quando necessario;
- evitare glicole sull'intero accumulo se può essere confinato al primario;
- ogni comparto e ogni PDC devono essere isolabili;
- prevedere ricambi critici e manual override;
- contabilizzare energia elettrica e termica;
- misurare stratificazione e kWh termici realmente disponibili;
- dimensionare espansione e sicurezze con calcolo dedicato;
- il controllo vitale non dipende da cloud.

## 11. Package sviluppati

- `THERMAL_LOAD_METHOD.md` — metodo carico termico;
- `HYDRONIC_DISTRIBUTION.md` — distribuzione secondaria;
- `RFQ_HYDRONIC_DISTRIBUTION.md` — RFQ distribuzione;
- `THERMAL_STORAGE_PRIMARY.md` — accumulo/primario/scambiatore;
- `RFQ_THERMAL_STORAGE_PRIMARY.md` — RFQ BOM-010;
- `HEAT_PUMP_CASCADE.md` — architettura e dati PDC 3+1;
- `RFQ_HEAT_PUMPS.md` — RFQ BOM-011;
- `19_BOM_PRODOTTI_FORNITORI/TERMICO_DISTRIBUZIONE_IDRONICA.md` — BOM-009;
- `19_BOM_PRODOTTI_FORNITORI/TERMICO_ACCUMULO_PRIMARIO.md` — BOM-010;
- `19_BOM_PRODOTTI_FORNITORI/TERMICO_PDC_MODULARI.md` — BOM-011;
- `22_FONTI_NORME_PREVENTIVI/TERMICO_DISTRIBUZIONE_SOURCES.md`;
- `22_FONTI_NORME_PREVENTIVI/TERMICO_ACCUMULO_PRIMARIO_SOURCES.md`;
- `22_FONTI_NORME_PREVENTIVI/TERMICO_PDC_SOURCES.md`.

## 12. Gate

Il punto 05 non diventa `VALIDATO` finché non sono disponibili almeno:

- lotto e dati meteo di progetto;
- geometria esecutiva della serra;
- proprietà reali della copertura e degli schermi;
- ricette climatiche C1–C6;
- carico termico per comparto e scenari produzione/economia/sopravvivenza;
- prestazioni PDC a -7/-10/-15 °C e alle temperature acqua reali;
- capacità netta con defrost;
- chiarimento revisione/dati Kensol discordanti;
- protocollo/cascata e garanzia Italia;
- P&ID e perdite di carico;
- scelta terminale near-crop;
- volume/architettura accumulo;
- dimensionamento scambiatore, glicole, espansione e sicurezza;
- preventivi confrontabili;
- strategia elettrica/FV/backup coerente.
