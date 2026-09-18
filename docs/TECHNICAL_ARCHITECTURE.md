# Carnia TerraTech — Architettura tecnica

**Aggiornato:** 18 settembre 2026  
**Stato:** `SINTESI DERIVATA / FONTI CANONICHE NELLE DIRECTORY DI DOMINIO`

## 1. Principio

L'architettura è progettata per:

- fault tolerance ragionevole;
- fallback locale;
- manutenzione;
- modularità;
- misura;
- basso lock-in;
- sicurezza;
- mitigazione del rischio di sito e operativo.

La robotica non è l'architettura: è uno strato opzionale che viene aggiunto quando i flussi reali lo giustificano.

## 2. Blocchi

1. serra 6 comparti;
2. acqua/fertirrigazione;
3. termico/clima;
4. energia/FV/EMS/BESS;
5. PLC/edge/rete/server;
6. Tech Barn e post-raccolta;
7. mezzo multifunzione;
8. humus/cicli materia;
9. accesso/manutenzione in quota;
10. vendita/spaccio;
11. robotica P2/R&S.

## 3. Serra

- ~4.200 m²;
- 6 × ~700 m²;
- P1: 3 comparti;
- corridoio tecnico e viabilità da layout reale;
- fascia perimetrale sufficiente per manutenzione e mezzi;
- carichi neve/vento/geotecnica da lotto reale.

La geometria deve permettere:
- manutenzione PLE/piattaforma;
- accesso telescopico nelle aree previste;
- recovery del robot ragno;
- drenaggi;
- crescita.

## 4. Acqua

- accumulo ~300 m³ working;
- pompe 2 × 100% duty/standby;
- 6 comparti;
- 24 settori working;
- filtrazione;
- dosaggio A/B/acido;
- classi acqua separate;
- raccolta drenato segregata;
- riuso solo dopo pilot 30–60 giorni e verifica agronomica.

Riferimento:
`../04_ACQUA_E_FERTIRRIGAZIONE/`.

## 5. Termico/clima

Working:
- 3 PDC 22 kW-class iniziali;
- predisposizione quarta;
- accumulo termico 30 m³;
- predisposizione 40–50 m³;
- distribuzione zonale;
- HAF;
- boost/deumidificazione solo dopo bilancio.

La capacità reale viene chiusa con:
- meteo sito;
- crop card;
- U-value/involucro;
- setpoint;
- bilancio umidità.

## 6. Energia

- FV ~120 kWp;
- predisposizione 150–180 kWp;
- EMS locale;
- BESS C&I da chiudere su kW + kWh reali;
- critical bus P0/P1;
- load shedding;
- black-start/islanding solo se supportati e validati;
- DSO/TICA dopo lotto.

Il BESS non viene usato per sostenere indiscriminatamente tutti i carichi termici.

## 7. OT / IT

### PLC
Funzioni vitali e sequenze locali.

### Edge
Acquisizione, buffer, protocollo, inference non safety-critical.

### Server centrale
Orchestrazione, dati, ordini, manutenzione, inventario, reporting, scheduling.

### Rete
Segmentazione:
- OT;
- server;
- CCTV;
- retail;
- guest;
- management.

Guardrail:
- 0 funzioni vitali cloud-only.

## 8. Mezzo multifunzione

BOM-021 è core.

Funzioni:
- forche;
- benna;
- big bag;
- humus/compost;
- substrati;
- cantiere;
- movimentazione;
- manutenzione.

Il mezzo non entra nelle corsie coltura strette.

## 9. Accesso in quota

Capacità umana:
- piattaforma OEM;
- PLE ragno;
- noleggio con SLA.

Obiettivo:
100% dei punti manutentivi critici raggiungibili in sicurezza.

Il masterplan deve includere:
- portanza;
- piazzole;
- accessi;
- pendenze;
- recovery.

## 10. Robot ragno R&S

Sistema distinto dalla PLE.

Roadmap:
- R0 predisposizione;
- R1 ispezione;
- R2 pulizia;
- R3 manutenzione assistita;
- R4 manipolazione.

Preferenza:
- guida/binario/interfaccia strutturale;
- massa ridotta;
- recovery indipendente;
- nessuna assunzione che il film sia portante.

Riferimento:
`../07_AUTOMAZIONE_DATI_AI/ROBOT_RAGNO_MANUTENZIONE_RND.md`.

## 11. AMR

Stato:
`P2 / HOLD / NON BLOCCA P1`.

Condizione di riapertura:
- ore manuali misurate;
- flussi reali;
- business case;
- pilot.

Le predisposizioni geometriche possono essere conservate se non penalizzano il core.

## 12. Humus/cicli materia

Area iniziale:
~180–250 m² + spazio di manovra.

Funzioni:
- ricevimento;
- segregazione;
- miscelazione;
- pretrattamento;
- vermicompost;
- vagliatura;
- maturazione;
- stoccaggio;
- quarantena.

Riferimento:
`../11_VERMICOMPOST_E_CICLI_MATERIA/`.

## 13. Tech Barn

Funzioni minime:
- ricezione;
- selezione;
- packaging;
- celle;
- magazzino;
- area tecnica;
- officina/manutenzione;
- servizi.

Dimensionamento su flussi P1 reali, non su metri quadrati arbitrari.

## 14. Sicurezza e failure

Ogni sottosistema deve definire:
- failure mode;
- allarme;
- fallback;
- ricambio;
- recovery;
- procedura manuale;
- owner;
- test SAT.

Nessun asset critico viene considerato operativo solo perché installato.

## 15. Ordine di maturità

`requisito -> candidato -> RFQ -> pilot se necessario -> validato -> ordine -> installazione -> SAT -> actual -> ottimizzazione`.

## 16. Fonti tecniche

Per il dettaglio aprire:
- `../03_SERRA/`;
- `../04_ACQUA_E_FERTIRRIGAZIONE/`;
- `../05_TERMICO_E_CLIMA/`;
- `../06_ENERGIA_ELETTRICA_FV/`;
- `../07_AUTOMAZIONE_DATI_AI/`;
- `../08_MACCHINE_E_LOGISTICA/`;
- `../09_TECH_BARN_E_POST_RACCOLTA/`;
- `../11_VERMICOMPOST_E_CICLI_MATERIA/`.
