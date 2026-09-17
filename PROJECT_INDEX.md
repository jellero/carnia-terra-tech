# Carnia TerraTech — Project Index

**Ruolo:** indice operativo e mappa di copertura del progetto.  
**Aggiornato:** 17 settembre 2026.

## 1. Scopo

Il repository deve permettere di progettare l'azienda senza lasciare aree scoperte. Ogni decisione deve essere collegata a costi, manutenzione, sicurezza, dipendenze, crescita e qualità della vita.

## 2. Struttura target

La riorganizzazione procede senza cancellare i documenti storici finché il contenuto non è stato migrato e verificato.

- `00_VISIONE_E_PRINCIPI/` — missione, KPI, guardrail e decision gates;
- `01_MASTERPLAN_E_TERRENO/` — lotto, vincoli, accessi, drenaggi, espansioni;
- `02_AGRONOMIA/` — colture, calendari, rese, vite, luppolo, siepi, outdoor;
- `03_SERRA/` — struttura, comparti, coperture, aperture, schermi, HAF, fogging;
- `04_ACQUA_E_FERTIRRIGAZIONE/` — fonte, accumulo, filtri, pompe, dosaggio, drenaggio;
- `05_TERMICO_E_CLIMA/` — PDC, accumulo, distribuzione, deumidificazione, emergenza;
- `06_ENERGIA_ELETTRICA_FV/` — FV, inverter, rete, UPS, generatore, EMS;
- `07_AUTOMAZIONE_DATI_AI/` — PLC, I/O, sensori, rete, edge, vision, cybersecurity;
- `08_MACCHINE_E_LOGISTICA/` — AMR, sollevatore, piattaforme, raccolta, carrelli;
- `09_TECH_BARN_E_POST_RACCOLTA/` — celle, confezionamento, officina, magazzini;
- `10_BENESSERE_FATTORIA_E_SERVIZI/` — pergolato, verde, fattoria didattica, robot di servizio, spaccio 24/7;
- `11_VERMICOMPOST_E_CICLI_MATERIA/`;
- `12_SICUREZZA_E_CONTINUITA/`;
- `13_MANUTENZIONE_E_RICAMBI/`;
- `14_ORGANIZZAZIONE_DEL_LAVORO/`;
- `15_MERCATO_E_VENDITE/`;
- `16_SOCIETA_FINANZA_E_CONTRIBUTI/`;
- `17_SOSTENIBILITA_PERSONALE_E_LANCIO/`;
- `18_CAPEX_OPEX_CASHFLOW/`;
- `19_BOM_PRODOTTI_FORNITORI/`;
- `20_CANTIERE_E_CRONOPROGRAMMA/`;
- `21_RISCHI_DECISIONI_OPEN_POINTS/`;
- `22_FONTI_NORME_PREVENTIVI/`.

## 3. Stato punto 00 — Visione e principi

**Stato: RAFFINATO / BASE DI GOVERNO DEL PROGETTO.**

Documenti:

- `00_VISIONE_E_PRINCIPI/PROJECT_CHARTER.md` — missione, principi non negoziabili, definizione di progettato e regola anti-zona-scoperta;
- `00_VISIONE_E_PRINCIPI/KPI_GUARDRAILS.md` — indicatori di qualità della vita, finanza, resilienza, manutenzione, ergonomia, risorse e crescita;
- `00_VISIONE_E_PRINCIPI/DECISION_GATES.md` — stati standard da IDEA a OPERATIVO e condizioni per avanzare.

Il punto 00 non viene considerato “immutabile”: potrà essere aggiornato se emergono nuovi requisiti, ma è sufficientemente definito per governare i blocchi successivi.

## 4. Stato punto 01 — Terreno e masterplan

**Stato: RAFFINATO / IN ATTESA DI LOTTO REALE.**

Documenti:

- `01_MASTERPLAN_E_TERRENO/README.md` — processo e stati di avanzamento del terreno;
- `01_MASTERPLAN_E_TERRENO/SITE_REQUIREMENTS.md` — requisiti del lotto e hard blocker;
- `01_MASTERPLAN_E_TERRENO/DUE_DILIGENCE_GATE.md` — urbanistica, PPR, PAI/PGRA, Natura 2000, geologia, acqua, energia, accessi e verifiche amministrative;
- `01_MASTERPLAN_E_TERRENO/MASTERPLAN_REQUIREMENTS.md` — superfici, flussi, logistica, verde, crescita e moduli futuri;
- `01_MASTERPLAN_E_TERRENO/SITE_EVALUATION_TEMPLATE.md` — scheda standard da compilare per ogni candidato;
- `01_MASTERPLAN_E_TERRENO/LAND_COST_MODEL.md` — prezzo terreno + trasferimento + due diligence + opere abilitanti;
- `01_MASTERPLAN_E_TERRENO/OFFICIAL_SOURCES.md` — fonti ufficiali da ricontrollare sul lotto reale.

Il metodo del punto 01 è chiuso. Il punto diventa `VALIDATO` solo con un lotto reale che supera due diligence, masterplan test e costo totale del sito.

## 5. Metodo BOM obbligatorio

Per ogni oggetto o sottosistema si analizzano, in ordine:

1. funzione;
2. requisiti tecnici e operativi;
3. quantità;
4. alternative reali acquistabili;
5. prezzo trovato / prezzo da preventivo / stima;
6. IVA, trasporto e accessori esclusi/inclusi;
7. installazione e minuteria;
8. alimentazioni e consumi;
9. manutenzione ordinaria;
10. manutenzione straordinaria;
11. ricambi critici;
12. vita utile e sostituibilità;
13. sicurezza e certificazioni;
14. failure mode;
15. fallback manuale o ridondanza;
16. compatibilità con contributi;
17. dipendenze da altri sistemi;
18. predisposizione per espansione;
19. stato documentale secondo `DECISION_GATES.md`.

## 6. Stato attuale dei grandi blocchi

### Base tecnica già esistente

I file in `docs/` coprono già serra, termico, acqua, automazione, finanza, prodotti e open points. Sono documenti sorgente durante la migrazione.

### Nuovi requisiti incorporati

Sono parte esplicita del progetto:

- robot autonomo per manutenzione/taglio prato;
- soluzione automatizzata per pulizia delle deiezioni nell'area galline;
- area fattoria didattica;
- futuro spaccio aziendale self-service automatizzato 24/7;
- pergolati, vite, ombra, verde, aree relax e qualità estetica come infrastruttura di benessere;
- piano economico che consideri la sostenibilità personale durante il lancio.

## 7. Sequenza BOM

Si procede un sottosistema alla volta, chiudendo il più possibile prima di passare al successivo.

### In lavorazione

**BOM-001 — Ventilazione HAF serra**  
File: `19_BOM_PRODOTTI_FORNITORI/SERRA_HAF_VENTILATION.md`

### Coda immediata

1. schermi termici/ombreggianti e motorizzazioni;
2. aperture e attuatori;
3. tubi, collettori e pompe circuito termico;
4. gocciolatori e linee irrigue;
5. filtrazione acqua;
6. pompe principali irrigazione;
7. pompe dosatrici;
8. serbatoi fertilizzanti;
9. accumulo termico 30–50 m³;
10. accumulo acqua 300 m³;
11. moduli FV e inverter;
12. AMR;
13. sollevatore/mezzo multifunzione;
14. robot tagliaerba;
15. sistema pulizia area galline;
16. celle frigorifere;
17. attrezzatura raccolta e packaging;
18. pergolato/vite/area relax;
19. fattoria didattica;
20. spaccio automatico 24/7.

La sequenza può cambiare quando una dipendenza tecnica rende necessario anticipare un blocco.
