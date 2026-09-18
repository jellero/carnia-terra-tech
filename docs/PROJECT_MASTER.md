# Carnia TerraTech — Project Master

**Aggiornato:** 18 settembre 2026  
**Stato:** `SINTESI DERIVATA / NON SOSTITUISCE I DOCUMENTI CANONICI`

## 0. Fonti autorevoli del progetto

La fonte di verità è costituita da:

1. `README.md`;
2. `PROJECT_INDEX.md`;
3. directory numerate `00_...`–`22_...`;
4. registri di rischio, procurement, pilot e commissioning in `21_RISCHI_DECISIONI_OPEN_POINTS/`.

Questo file serve solo come vista sintetica. In caso di conflitto prevale il documento di dominio più recente.

## 1. Scopo

Carnia TerraTech è un'azienda agricola ad alta automazione progettata per:

- essere economicamente sostenibile;
- ridurre lavoro pesante, sporco, ripetitivo e rischioso;
- mitigare i rischi prima di aumentare complessità;
- funzionare localmente anche senza cloud/Internet per le funzioni vitali;
- essere manutenibile e ripristinabile;
- crescere per fasi senza rifare infrastrutture permanenti;
- proteggere qualità della vita e continuità operativa.

Principio guida:

`ridurre incertezza -> mitigare rischio -> costruire capacità -> misurare -> automatizzare ciò che conviene`

## 2. Configurazione generale

### Finale

- serra produttiva: ~4.200 m²;
- 6 comparti × ~700 m²;
- FV iniziale: ~120 kWp;
- predisposizione FV: 150–180 kWp;
- accumulo acqua: ~300 m³;
- accumulo termico: ~30 m³ iniziale, predisposizione 40–50 m³;
- Tech Barn;
- post-raccolta e freddo;
- humus/vermicompost e cicli materia;
- mezzo multifunzione core;
- automazione locale PLC/edge/server;
- spaccio/vendita diretta.

### P1

- 3 comparti;
- ~2.100 m² produttivi;
- infrastrutture permanenti dimensionate per il progetto finale dove il retrofit sarebbe oneroso;
- robotica non essenziale rinviata.

## 3. Terreno

Target acquisto:
- <= €50.000, salvo revisione esplicita.

Superficie preferita:
- **10.000–12.000 m² realmente utilizzabili**;
- 9.000–10.000 m² solo con geometria molto efficiente, pochi vincoli e drenaggio favorevole;
- <9.000 m² = eccezione da dimostrare con masterplan completo.

Prima dell'acquisto:

1. pre-screening urbanistico/vincoli/accessi;
2. rilievo;
3. griglia campionamento su tutta la superficie utile;
4. intensificazione nelle anomalie;
5. prove infiltrazione/drenaggio;
6. mappa quote/ristagni;
7. storico e anomalie ambientali;
8. geotecnica professionale coerente con le opere;
9. masterplan di prova;
10. stima costi mitigazione.

Riferimento:
`../01_MASTERPLAN_E_TERRENO/PIANO_CAMPIONAMENTO_TERRENO_E_DRENAGGIO.md`.

## 4. Gerarchia delle priorità

### Core P1

- sito e drenaggi;
- struttura serra;
- acqua/fertirrigazione;
- termico/clima;
- elettrico/continuità;
- Tech Barn/freddo/packaging;
- PLC/edge/rete/server minimo;
- mezzo multifunzione;
- forche + benna;
- humus/cicli materia iniziali;
- accesso umano certificato in quota;
- vendita/spaccio semplice;
- personale e commissioning.

### Dopo dati P1

- AMR;
- tagliaerba robotico;
- automazioni commerciali avanzate;
- smart crate/cart;
- attrezzature industriali humus;
- capacità energetiche extra.

### Fuori dal core

- rover dedicato pulizia galline: **ARCHIVIATO**;
- centro trasformazione conto terzi fino a domanda validata;
- agriturismo evolutivo;
- R&S UE.

## 5. Mezzi e manutenzione

### Telescopico / mezzo multifunzione

È un asset core per:
- pallet;
- big bag;
- substrati;
- compost/humus;
- materiali sfusi;
- cantiere;
- manutenzione;
- logistica esterna.

Il pacchetto minimo include:
- forche;
- benna general purpose;
- caricatore;
- ricambi iniziali.

Riferimento:
`../08_MACCHINE_E_LOGISTICA/LIFTING_MULTIFUNCTION_ARCHITECTURE.md`.

### Accesso in quota

Ogni punto alto manutentivo deve essere raggiungibile in sicurezza.

Soluzioni:
1. piattaforma OEM sul mezzo, se sufficiente;
2. PLE cingolata compatta "ragno";
3. noleggio/servizio con SLA compatibile.

La funzione è obbligatoria; il possesso della PLE non lo è.

### Robot ragno

R&S prioritaria distinta dalla PLE.

Obiettivo progressivo:
- R1 ispezione;
- R2 pulizia semplice;
- R3 manutenzione assistita;
- R4 manipolazione avanzata.

Il robot non sostituisce l'accesso umano certificato.

Riferimento:
`../07_AUTOMAZIONE_DATI_AI/ROBOT_RAGNO_MANUTENZIONE_RND.md`.

## 6. Humus e cicli materia

Carnia TerraTech produce internamente humus/vermicompost e rilavora materie quando:
- legalmente ammissibili;
- tracciabili;
- compatibili con biosecurity;
- tecnicamente utili;
- economicamente sensate.

Flusso:
`ricezione -> controllo -> stoccaggio -> miscelazione/pretrattamento -> vermicompost -> vaglio -> maturazione -> utilizzo`.

Nessun materiale di terzi classificabile come rifiuto entra senza corretto perimetro autorizzativo.

Riferimento:
`../11_VERMICOMPOST_E_CICLI_MATERIA/`.

## 7. Agronomia

Portafoglio finale di lavoro:
- C1 pomodoro premium;
- C2 peperone;
- C3 lattuga;
- C4 lattuga/leaf flessibile;
- C5 baby leaf/rucola/spinacio;
- C6 basilico + vivaio + prove.

Le crop card devono chiudere:
- resa vendibile;
- prezzo reale per canale;
- scarto;
- ore uomo;
- acqua;
- energia;
- packaging;
- margine/m²;
- margine/ora.

Nessuna coltura viene mantenuta solo perché tecnicamente interessante.

## 8. Automazione

Architettura:

### L0 — safety e controllo locale
PLC, interblocchi, protezioni, fallback.

### L1 — edge
buffer, acquisizione, adattatori, inferenza locale dove utile.

### L2 — orchestrazione
dati, scheduler, inventario, manutenzione, logistica, analytics.

Regola:
`server non disponibile != impianto non sicuro`.

Maturità:
`osservare -> registrare -> allarmare -> comandare -> pianificare -> ottimizzare`.

### AMR

Non blocca P1.

Viene riaperto solo dopo dati reali su:
- ore trasporto;
- distanze;
- cassette/kg;
- congestione;
- costo lavoro;
- beneficio atteso.

## 9. Energia e continuità

Working baseline:
- FV ~120 kWp;
- predisposizione 150–180 kWp;
- PDC modulari;
- accumulo termico ~30 m³;
- EMS;
- BESS dimensionato sui carichi critici reali;
- P0/P1/P2/P3 come classi di carico.

Il dimensionamento definitivo richiede:
- profilo 1–15 min;
- transitori;
- DSO/POD;
- short-circuit/selectivity;
- test blackout e recovery.

## 10. Acqua

Working baseline:
- ~300 m³;
- 2 × ~150 m³ come configurazione di riferimento;
- 24 settori irrigui di lavoro;
- pompe principali duty/standby;
- filtrazione;
- fertirrigazione A/B/acido;
- trattamento per classi acqua;
- drenaggio segregato;
- riuso solo dopo pilot.

## 11. Post-raccolta

- due classi temperatura separate;
- dimensionamento su kg/giorno e pull-down;
- packaging minimo;
- tracciabilità lotto;
- niente linea food ready-to-eat non necessaria al core.

## 12. Finanza

Control budget corrente:
- **CAPEX netto: €950.000**;
- **riserva operativa protetta: €120.000**;
- **linea IVA/ponte target: €140.000–170.000**;
- fascia pre-RFQ: €850.000–1.050.000.

Target commerciale P1:
- **~€280.000/anno ricorrenti da validare**.

Non è una previsione.

Riferimenti:
- `../18_CAPEX_OPEX_CASHFLOW/BUDGET_AVVIO_IDEALE.md`;
- `../16_SOCIETA_FINANZA_E_CONTRIBUTI/BUSINESS_PLAN_MASTER.md`.

## 13. Sequenza di avvio

1. DG0 — finanza e cassa;
2. individuazione lotto;
3. campagna sito;
4. masterplan;
5. crop card e mercato;
6. RFQ/installato;
7. opere permanenti;
8. allestimento P1;
9. commissioning;
10. avvio colture;
11. vendite;
12. misura actual;
13. solo dopo: automazioni e P2.

## 14. Cosa non deve accadere

- comprare il terreno prima di misurarlo;
- spendere la riserva operativa in CAPEX;
- comprare robot perché agevolati;
- progettare attorno a prodotti non validati;
- creare punti manutentivi non raggiungibili;
- dipendere dal promotore per ogni recovery;
- assumere resa/prezzo senza validazione;
- usare R&S per coprire funzioni vitali.

## 15. Documenti da aprire per primi

1. `../PROJECT_INDEX.md`;
2. `../00_VISIONE_E_PRINCIPI/PROJECT_CHARTER.md`;
3. `../01_MASTERPLAN_E_TERRENO/README.md`;
4. `../18_CAPEX_OPEX_CASHFLOW/BUDGET_AVVIO_IDEALE.md`;
5. `../20_CANTIERE_E_CRONOPROGRAMMA/PIANO_OPERATIVO_AVVIO/README.md`;
6. `../21_RISCHI_DECISIONI_OPEN_POINTS/CRUSCOTTO_VALIDAZIONE_CHIUSURA.md`.
