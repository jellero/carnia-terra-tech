# 13 — Manutenzione e ricambi

**Aggiornato:** 18 settembre 2026  
**Stato:** `CORE RISK-FIRST / ASSET REGISTER DA POPOLARE CON RFQ E SERIALI`

## 1. Scopo

Un asset non è realmente acquistato quando arriva.

È operativo quando è:
- identificato;
- documentato;
- manutenibile;
- dotato di ricambi/strategia ricambi;
- inserito nel piano PM;
- associato a owner e vendor;
- testato per recovery.

## 2. Principi

- preferire componenti riparabili;
- evitare lock-in non necessario;
- conoscere lead time ricambi;
- tenere onsite ciò che ferma P0/P1 e costa poco rispetto al downtime;
- non accumulare ricambi costosi senza analisi;
- registrare firmware/configuration backup per asset digitali;
- misurare ore manutenzione e downtime.

## 3. Documenti

- [ASSET_REGISTER_E_RICAMBI.md](ASSET_REGISTER_E_RICAMBI.md)
- [ASSET_REGISTER_TEMPLATE.csv](ASSET_REGISTER_TEMPLATE.csv)
- [PIANO_MANUTENZIONE_TEMPLATE.csv](PIANO_MANUTENZIONE_TEMPLATE.csv)

## 4. Interfacce

- sicurezza/continuità: `../12_SICUREZZA_E_CONTINUITA/`;
- commissioning: `../21_RISCHI_DECISIONI_OPEN_POINTS/`;
- BOM: `../19_BOM_PRODOTTI_FORNITORI/`;
- personale/skill: `../14_ORGANIZZAZIONE_DEL_LAVORO/`.

## 5. KPI

- PM compliance;
- corrective hours;
- downtime;
- MTTR;
- failure count;
- spare stockouts;
- costo ricambi;
- lead time;
- % interventi eseguibili internamente;
- asset con manuale/config backup;
- asset senza fallback.

## 6. Guardrail

A commissioning:
- 0 asset critici senza procedura guasto;
- 0 asset critici senza strategia ricambio/fallback;
- 0 configurazioni critiche senza backup;
- 0 seriali/garanzie mancanti sugli asset principali.
