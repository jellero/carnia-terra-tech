# Carnia TerraTech — Punto 05: Termico e clima

**Aggiornato:** 17 settembre 2026  
**Stato:** `ARCHITETTURA DI BASE DEFINITA / DISTRIBUZIONE IDRONICA IN SVILUPPO / CARICHI TERMICI DA CALCOLO`.

## 1. Obiettivo

Il sistema termico deve proteggere produzione e impianti senza trasformare la serra in un edificio da mantenere sempre alla stessa temperatura.

Priorità:

- protezione gelo e danni critici;
- supporto fisiologico alle colture;
- gestione condensa/umidità quando il calore è utile allo scopo;
- riscaldamento vicino coltura/radice a bassa temperatura;
- modularità e priorità per comparto;
- utilizzo dell'accumulo termico per spostare energia nel tempo;
- funzionamento locale e degradato anche senza server/cloud;
- misurabilità di energia, temperature, portate e ore pompa.

## 2. Architettura working

Generazione e accumulo restano moduli separati dalla distribuzione:

`PDC -> primario protetto -> eventuale scambiatore -> accumulo termico -> collettore secondario -> 6 circuiti indipendenti -> terminali near-crop / eventuali boost`.

Working concept già consolidato:

- 3 × PDC Kensol KHP-R290-22-3 = 66 kW nominali iniziali;
- predisposizione quarta unità -> 88 kW nominali;
- accumulo 30 m³ iniziale, predisposizione 40–50 m³;
- 6 circuiti secondari indipendenti;
- pompa, miscelazione, misura T mandata/ritorno e portata per comparto;
- terminali near-crop a bassa temperatura;
- piccoli aerotermi idronici solo dove giustificati come boost/emergenza/deumidificazione.

Questi numeri non sostituiscono il calcolo del fabbisogno termico sul lotto reale.

## 3. Modalità operative

### Produzione

Setpoint e priorità coerenti con coltura e fase produttiva.

### Economia

Riduzione setpoint, priorità ai comparti più sensibili, carica accumulo nelle finestre energeticamente convenienti.

### Sopravvivenza

Obiettivo primario: evitare gelo/danno irreversibile a colture e impianti, anche sacrificando piena produttività temporanea.

## 4. Regole di progetto

- nessuna potenza PDC viene considerata sufficiente finché non esiste il calcolo di carico;
- nessuna pompa viene scelta solo dalla sigla commerciale;
- terminali radianti e dorsali sono due funzioni diverse e possono richiedere materiali diversi;
- i tratti che devono emettere calore non vanno coibentati; le dorsali che devono solo trasportarlo sì, quando tecnicamente opportuno;
- evitare glicole sull'intero accumulo se la protezione può essere confinata al primario esterno;
- ogni comparto deve poter essere isolato e mantenuto senza fermare gli altri;
- prevedere ricambi critici e modalità manuali;
- contabilizzare energia elettrica e termica per ricavare COP reale e costo per coltura.

## 5. Package in sviluppo

- `THERMAL_LOAD_METHOD.md` — metodo per il carico termico;
- `HYDRONIC_DISTRIBUTION.md` — architettura idraulica secondaria;
- `RFQ_HYDRONIC_DISTRIBUTION.md` — richiesta offerte scomposta;
- `19_BOM_PRODOTTI_FORNITORI/TERMICO_DISTRIBUZIONE_IDRONICA.md` — BOM-009;
- `22_FONTI_NORME_PREVENTIVI/TERMICO_DISTRIBUZIONE_SOURCES.md` — fonti e prezzi.

## 6. Gate

Il punto 05 non diventa `VALIDATO` finché non sono disponibili almeno:

- lotto e dati meteo di progetto;
- geometria esecutiva della serra;
- proprietà reali della copertura e degli schermi;
- ricette climatiche per C1–C6;
- calcolo carico per comparto e scenari produzione/economia/sopravvivenza;
- schema idraulico e perdite di carico;
- scelta terminale near-crop con compatibilità ambientale;
- dimensionamento PDC e accumulo;
- preventivi confrontabili;
- strategia elettrica/FV/backup coerente.
