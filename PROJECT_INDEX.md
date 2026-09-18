# Carnia TerraTech — Project Index

**Aggiornato:** 18 settembre 2026  
**Ruolo:** `INDICE CANONICO / MAPPA DI COPERTURA / STATO DEL PROGETTO`

## 1. Regola di autorità

Per leggere il progetto usare questo ordine:

1. `README.md`;
2. questo `PROJECT_INDEX.md`;
3. documento di dominio nella directory numerata;
4. BOM/RFQ/fonti;
5. registri di chiusura in `21_RISCHI_DECISIONI_OPEN_POINTS/`.

I file in `docs/` sono sintesi derivate o archivi benchmark e non prevalgono sui documenti numerati.

## 2. Obiettivo

Carnia TerraTech deve essere:

- redditizia;
- robusta;
- manutenibile;
- espandibile;
- misurabile;
- compatibile con una buona qualità della vita;
- poco dipendente da lavoro pesante/sporco/ripetitivo;
- capace di funzionare in modalità degradata.

Principio guida:

`mitigare il rischio -> costruire capacità -> misurare -> automatizzare ciò che conviene`

## 3. Baseline corrente

### Lotto
- area prioritaria: corridoio Venzone/Gemona;
- target acquisto: <= €50.000;
- superficie preferita: **10.000–12.000 m² realmente utilizzabili**;
- 9.000–10.000 m²: solo con forma/accessi/drenaggio molto favorevoli;
- <9.000 m²: eccezione da dimostrare.

### Produzione
- serra finale: ~4.200 m²;
- 6 comparti × ~700 m²;
- P1: 3 comparti / ~2.100 m².

### Infrastrutture
- FV iniziale: ~120 kWp;
- predisposizione FV: 150–180 kWp;
- accumulo termico: ~30 m³ iniziale, predisposizione 40–50 m³;
- accumulo acqua: ~300 m³;
- Tech Barn;
- due classi temperatura post-raccolta;
- mezzo multifunzione core;
- humus/vermicompost e cicli materia;
- accesso umano certificato in quota;
- PLC/edge/server locale.

### Finanza di lavoro
- control budget CAPEX: **€950.000 netti**;
- riserva operativa protetta: **€120.000**;
- linea IVA/ponte target: **€140.000–170.000**;
- target commerciale P1 da validare: **~€280.000/anno ricorrenti**.

Questi sono valori di pianificazione, non costi/ricavi contrattuali.

## 4. Gerarchia tecnologica

### Core P1
- terreno e drenaggi;
- serra;
- acqua;
- clima;
- energia/continuità;
- Tech Barn/freddo;
- PLC/edge/rete/server minimo;
- telescopico + forche + benna;
- humus/cicli materia base;
- accesso umano in quota;
- packaging minimo;
- vendita/spaccio semplice;
- personale, sicurezza, manutenzione e commissioning.

### P2 / dopo dati reali
- AMR;
- robot tagliaerba;
- capacità energetiche extra;
- attrezzature humus più industriali;
- automazione commerciale avanzata.

### R&S prioritaria ma non vitale
- robot ragno per ispezione/manutenzione parti alte;
- vision/robotica agronomica;
- laser/IPM confinato;
- orchestrazione avanzata CTT-PAA.

### Fuori core / futuro
- rover pulizia galline: **ARCHIVIATO / NON ORDINABILE**;
- fattoria didattica;
- pergolato/relax;
- agriturismo evolutivo;
- centro trasformazione conto terzi fino a domanda validata.

## 5. Terreno — gate obbligatorio

Sequenza:

`annuncio -> pre-screening -> campagna fisica -> analisi -> masterplan di prova -> decisione`

Prima dell'acquisto:

- griglia campionamento su tutta la superficie utile;
- intensificazione anomalie;
- prove infiltrazione/drenaggio;
- quote e ristagni;
- storico e anomalie ambientali;
- analisi acqua;
- geotecnica coerente con le opere;
- costi mitigazione;
- masterplan completo.

Riferimento:
`01_MASTERPLAN_E_TERRENO/PIANO_CAMPIONAMENTO_TERRENO_E_DRENAGGIO.md`.

## 6. Continuità elettrica P0

La continuità P0 non è legata a una sola tecnologia.

Confrontare:

- BESS/PCS con trasferimento no-break misurato;
- BESS + ride-through P0 professionale dedicato;
- DC buffer/architettura equivalente.

**Non sono baseline UPS consumer distribuite.**

Criterio:
P0 deve superare il blackout SAT senza reboot o fault non accettato.

## 7. Macchine e manutenzione

### BOM-021 — mezzo multifunzione
**CORE P1.**

Serve per:
- pallet;
- big bag;
- substrati;
- humus/compost;
- materiale sfuso;
- cantiere;
- manutenzione.

Baseline accessori:
- forche;
- benna;
- caricatore;
- ricambi iniziali.

### Accesso umano in quota
Funzione core.

Soluzioni:
1. piattaforma OEM sul telescopico;
2. PLE cingolata compatta "ragno";
3. noleggio con SLA.

### Robot ragno
R&S prioritaria distinta dalla PLE.

Roadmap:
`R0 predisposizioni -> R1 ispezione -> R2 pulizia -> R3 manutenzione assistita -> R4 manipolazione`.

Il robot non sostituisce recovery/accesso umano.

## 8. Humus e cicli materia

Obiettivo:
- valorizzare residui propri;
- produrre humus/vermicompost;
- acquistare materie a minor grado di lavorazione quando sensato;
- ridurre dipendenza da prodotti finiti.

Guardrail:
- classificazione legale;
- tracciabilità;
- biosecurity;
- separazione food/dirty;
- drenaggio/percolati;
- costo interno misurato.

Directory:
`11_VERMICOMPOST_E_CICLI_MATERIA/`.

## 9. Mappa directory 00–22

| Punto | Directory | Stato sintetico |
|---|---|---|
| 00 | `00_VISIONE_E_PRINCIPI` | **BASE DI GOVERNO** — charter, KPI, decision gates |
| 01 | `01_MASTERPLAN_E_TERRENO` | **STRUTTURATO / LOTTO REALE BLOCCANTE** |
| 02 | `02_AGRONOMIA` | **PORTAFOGLIO STRUTTURATO / CROP CARD DA VALIDARE** |
| 03 | `03_SERRA` | **BOM-001…008 STRUTTURATE / SITO-RFQ BLOCCANTI** |
| 04 | `04_ACQUA_E_FERTIRRIGAZIONE` | **BOM-013…018, 032, 033 STRUTTURATE / DATI REALI E PILOT RIUSO BLOCCANTI** |
| 05 | `05_TERMICO_E_CLIMA` | **BOM-009…012 STRUTTURATE / CARICHI-RFQ BLOCCANTI** |
| 06 | `06_ENERGIA_ELETTRICA_FV` | **BOM-019/034 STRUTTURATE / DSO-LOAD PROFILE-RFQ BLOCCANTI** |
| 07 | `07_AUTOMAZIONE_DATI_AI` | **ARCHITETTURA LOCALE + R&S ROBOT RAGNO/LASER** |
| 08 | `08_MACCHINE_E_LOGISTICA` | **BOM-021 CORE / AMR P2 / ACCESSO QUOTA CORE** |
| 09 | `09_TECH_BARN_E_POST_RACCOLTA` | **BOM-024/025 STRUTTURATE / BOM-029 FUTURA** |
| 10 | `10_BENESSERE_FATTORIA_E_SERVIZI` | **MODULI FUTURI / BOM-023 ARCHIVIATA** |
| 11 | `11_VERMICOMPOST_E_CICLI_MATERIA` | **CORE STRUTTURATO / FLUSSI REALI DA CHIUDERE** |
| 12 | `12_SICUREZZA_E_CONTINUITA` | **CORE STRUTTURATO / RTO-AUTONOMIE DA DATI REALI** |
| 13 | `13_MANUTENZIONE_E_RICAMBI` | **CORE STRUTTURATO / ASSET REGISTER DA POPOLARE** |
| 14 | `14_ORGANIZZAZIONE_DEL_LAVORO` | **SKILL MATRIX / ORE REALI DA VALIDARE** |
| 15 | `15_MERCATO_E_VENDITE` | **CANALI STRUTTURATI / DOMANDA P1 DA VALIDARE** |
| 16 | `16_SOCIETA_FINANZA_E_CONTRIBUTI` | **BUSINESS PLAN/GOVERNANCE STRUTTURATI / ATTI E BANDI REALI BLOCCANTI** |
| 17 | `17_SOSTENIBILITA_PERSONALE_E_LANCIO` | **RAMPA E PERSONALE STRUTTURATI / COSTI REALI DA PAGHE** |
| 18 | `18_CAPEX_OPEX_CASHFLOW` | **CONTROL BUDGET €950k / RFQ E ACTUAL DA POPOLARE** |
| 19 | `19_BOM_PRODOTTI_FORNITORI` | **BOM-001…034 STRUTTURATE** |
| 20 | `20_CANTIERE_E_CRONOPROGRAMMA` | **PIANO P1 STRUTTURATO / LOTTO E FINANZA BLOCCANTI** |
| 21 | `21_RISCHI_DECISIONI_OPEN_POINTS` | **REGISTRI MASTER STRUTTURATI / EVIDENZE REALI DA CHIUDERE** |
| 22 | `22_FONTI_NORME_PREVENTIVI` | **FONTI PER DOMINIO / DA RIVALIDARE ALLE DECISIONI** |

## 10. Sequenza BOM 001–034

### Serra
- BOM-001 struttura/fondazioni;
- BOM-002 copertura;
- BOM-003 aperture/reti anti-insetto;
- BOM-004 schermi;
- BOM-005 fogging;
- BOM-006 HAF;
- BOM-007 supporti coltura/drenaggio;
- BOM-008 porte/compartimenti/gronde.

### Termico
- BOM-009 distribuzione idronica;
- BOM-010 accumulo/primario/HX;
- BOM-011 PDC modulari;
- BOM-012 boost/deumidificazione.

### Acqua
- BOM-013 distribuzione irrigua;
- BOM-014 filtrazione;
- BOM-015 pompe principali;
- BOM-016 fertirrigazione;
- BOM-017 tank fertilizzanti/contenimento;
- BOM-018 accumulo acqua;
- BOM-032 trattamento/disinfezione;
- BOM-033 drenaggio/riuso.

### Energia
- BOM-019 FV/inverter;
- BOM-034 EMS/BESS/connessione.

### Macchine
- BOM-020 AMR — **P2/HOLD**;
- BOM-021 mezzo multifunzione — **CORE**;
- BOM-022 tagliaerba — **P2/FUTURO**.

### Benessere/servizi
- BOM-023 rover galline — **ARCHIVIATA**;
- BOM-026 pergolato/relax;
- BOM-027 fattoria didattica;
- BOM-028 spaccio automatico.

### Post-raccolta
- BOM-024 celle;
- BOM-025 raccolta/packaging;
- BOM-029 trasformazione conto terzi — **UNITÀ FUTURA**.

### Automazione/organizzazione
- BOM-030 server centrale;
- BOM-031 personale/lancio.

**Non aprire BOM-035** finché non emerge un sottosistema fisico realmente scoperto.

Humus, sicurezza, manutenzione e robot ragno sono per ora coperti come architetture/processi trasversali o R&S, senza forzare una nuova BOM.

## 11. Pilot

### Necessari prima di specifici acquisti/go-live
- PIL-LIFT — mezzo multifunzione;
- PIL-HGT — accesso in quota;
- PIL-PACK — packaging se automatizzato;
- PIL-COLD — celle;
- PIL-BESS — continuità elettrica;
- PIL-REUSE — solo prima del riuso drenaggio.

### Non bloccano P1
- PIL-AMR;
- mower;
- retail avanzato;
- didattica.

Il pilot segue:

`test plan -> dati grezzi -> KPI -> decision record -> procurement`.

## 12. Rischio e manutenzione

Riferimenti nuovi:

- `12_SICUREZZA_E_CONTINUITA/MATRICE_CONTINUITA_FUNZIONI_CRITICHE.md`;
- `12_SICUREZZA_E_CONTINUITA/PIANO_SCENARI_GUASTO_E_RECOVERY.md`;
- `13_MANUTENZIONE_E_RICAMBI/ASSET_REGISTER_E_RICAMBI.md`;
- `13_MANUTENZIONE_E_RICAMBI/ASSET_REGISTER_TEMPLATE.csv`.

A commissioning:
- nessun P0 senza test;
- nessun asset critico senza fallback;
- nessun asset critico senza strategia ricambi;
- nessuna configurazione critica senza backup.

## 13. Closure sprint corrente

Ordine:

1. individuare lotto;
2. campagna fisica terreno/drenaggio;
3. masterplan reale;
4. chiudere crop card P1;
5. validare domanda e prezzi;
6. chiudere load profile;
7. DSO/TICA;
8. RFQ installati;
9. chiudere mezzo, humus e accesso in quota;
10. consolidare CAPEX/OPEX/cashflow;
11. stress test;
12. freeze P1;
13. cantiere;
14. commissioning;
15. actual 30/90 giorni;
16. decidere P2/automazioni.

## 14. Progetti separati

### R&S UE
`RND_CORRELATO_EU/`

CTT-PAA usa Carnia TerraTech come dimostratore, ma:
- budget separato;
- TRL separato;
- nessuna dipendenza vitale.

### Agriturismo
`EXTRA_AGRITURISMO_EVOLUTIVO/`

- budget separato;
- fondi separati;
- non necessario all'avvio agricolo.

## 15. Punto di ingresso operativo

Per una nuova sessione:

1. leggere questo file;
2. aprire `21_RISCHI_DECISIONI_OPEN_POINTS/CRUSCOTTO_VALIDAZIONE_CHIUSURA.md`;
3. lavorare sul primo blocker reale;
4. non aggiungere tecnologia finché non chiude un rischio o un fabbisogno misurato.
