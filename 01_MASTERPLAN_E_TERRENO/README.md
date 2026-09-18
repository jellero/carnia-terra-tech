# Carnia TerraTech — Punto 01: Terreno e Masterplan

**Aggiornato:** 18 settembre 2026  
**Stato:** `RAFFINATO / IN ATTESA DI LOTTO REALE`

## Scopo

Il terreno non viene scelto perché “sembra bello” o perché costa poco. Deve supportare l'intero sistema Carnia TerraTech: produzione, logistica, energia, acqua, automazione, manutenzione, benessere, crescita futura e possibili attività didattiche/commerciali.

Il punto 01 definisce il metodo con cui un lotto passa da annuncio a possibile acquisto.

## Vincoli già consolidati

- area prioritaria: corridoio **Venzone / Gemona**;
- tetto obiettivo acquisto terreno: **€50.000**;
- superficie preferita: **10.000–12.000 m² realmente utilizzabili**;
- 9.000–10.000 m²: valutabili solo con forma molto efficiente e pochi vincoli;
- <9.000 m²: eccezione da dimostrare con masterplan completo, manutenzione, drenaggi e crescita;
- serra produttiva target: **4.200 m²**;
- nessun acquisto senza verifica urbanistica, idraulica/geologica, paesaggistica, accessi, acqua, elettricità e fattibilità del masterplan;
- nessun annuncio o informazione del venditore sostituisce documentazione ufficiale o verifica tecnica.

Un candidato discusso in passato era circa 8.500 m² a €32.000, ma non è mai stato validato e quindi non è un terreno scelto.

## Documenti del blocco

- `SITE_REQUIREMENTS.md` — requisiti minimi e preferenze del lotto;
- `DUE_DILIGENCE_GATE.md` — controlli obbligatori prima di proposta/acquisto;
- `MASTERPLAN_REQUIREMENTS.md` — funzioni che il lotto deve riuscire a ospitare;
- `SITE_EVALUATION_TEMPLATE.md` — scheda standard per confrontare terreni reali;
- `PIANO_CAMPIONAMENTO_TERRENO_E_DRENAGGIO.md` — campagna fisica obbligatoria sul lotto serio;
- `LAND_COST_MODEL.md` — tutti i costi da considerare oltre al prezzo di acquisto;
- `OFFICIAL_SOURCES.md` — fonti territoriali e amministrative da usare.

## Stati del terreno

Ogni lotto candidato assume uno stato:

1. `SEGNALATO` — annuncio o contatto ricevuto;
2. `PRE-SCREENING` — prezzo, superficie, posizione e forma compatibili in prima battuta;
3. `DOCUMENTI_RICHIESTI` — mappali, titoli e documentazione richiesti;
4. `DUE_DILIGENCE` — verifiche ufficiali e tecniche in corso;
5. `FIELD_TESTED` — campioni, drenaggio/infiltrazione, quote e anomalie misurate;
6. `MASTERPLAN_TEST` — layout Carnia TerraTech provato sul lotto reale;
6. `COSTO_TOTALE_STIMATO` — prezzo + imposte/oneri + abilitazioni + opere necessarie;
7. `VALIDATO` — nessuna criticità bloccante nota;
8. `NEGOZIABILE` — condizioni economiche e sospensive definite;
9. `ACQUISTABILE` — decision gate superato;
10. `ACQUISTATO`.

## Regola di blocco

Un lotto non può diventare `ACQUISTABILE` senza stato `FIELD_TESTED` e non può diventarlo se resta `UNKNOWN` su una questione che può impedire o alterare sostanzialmente:

- realizzazione della serra;
- accesso mezzi;
- disponibilità acqua;
- connessione elettrica;
- sicurezza idraulica/geologica;
- capacità di costruire Tech Barn e impianti tecnici;
- costi di preparazione del sito;
- futura crescita del progetto.

## Cosa significa “punto 01 finito”

Questo blocco progettuale è strutturato; diventerà operativo-finito solo dopo l'individuazione del lotto reale e il completamento della sua scheda di due diligence e masterplan.
