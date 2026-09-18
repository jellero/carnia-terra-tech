# 12 — Sicurezza e continuità

**Aggiornato:** 18 settembre 2026  
**Stato:** `CORE RISK-FIRST / CONSOLIDAMENTO TRASVERSALE`

## 1. Scopo

Questo blocco raccoglie ciò che non deve restare implicito nei singoli sottosistemi:

- funzioni critiche;
- modalità di guasto;
- dipendenze;
- fallback;
- continuità;
- recovery;
- test integrati;
- responsabilità.

Non sostituisce DVR, progettazione sicurezza, antincendio, CE o verifiche professionali.

## 2. Principio

Per ogni funzione critica bisogna sapere:

1. cosa la alimenta;
2. da cosa dipende;
3. cosa succede quando un componente fallisce;
4. quanto tempo può restare indisponibile;
5. qual è il fallback;
6. chi interviene;
7. quale ricambio/strumento serve;
8. come si prova il recovery.

Regola:

`guasto previsto -> comportamento noto -> allarme -> fallback -> recovery -> verifica`

## 3. Classi di priorità

- **P0 — safety/control:** non deve creare condizione insicura e deve mantenere il controllo minimo;
- **P1 — protezione biologica/prodotto:** perdita prolungata può danneggiare coltura/prodotto;
- **P2 — continuità produttiva:** fermo tollerabile per una finestra definita;
- **P3 — differibile:** può attendere senza danno materiale immediato.

La classe è della **funzione**, non del marchio.

## 4. Domini

Consolidare almeno:

- elettrico/BESS/P0 ride-through;
- acqua e irrigazione;
- fertirrigazione;
- termico/clima;
- celle e catena del freddo;
- PLC/rete/server;
- drenaggi;
- incendio/security/access;
- mezzo multifunzione;
- accesso in quota;
- humus/cicli materia;
- vendita/spaccio;
- persone/competenze.

## 5. Documenti

- [MATRICE_CONTINUITA_FUNZIONI_CRITICHE.md](MATRICE_CONTINUITA_FUNZIONI_CRITICHE.md)
- [CONTINUITA_FUNZIONI_CRITICHE.csv](CONTINUITA_FUNZIONI_CRITICHE.csv)
- [PIANO_SCENARI_GUASTO_E_RECOVERY.md](PIANO_SCENARI_GUASTO_E_RECOVERY.md)

## 6. Gate

Prima del go-live:

- 0 funzioni vitali cloud-only;
- 0 single point of failure non mitigati su funzioni vitali;
- fallback definito;
- owner definito;
- allarme verificato;
- recovery testato;
- ricambio/servizio critico definito;
- documentazione as-built disponibile.

Riferimenti:
- `../00_VISIONE_E_PRINCIPI/KPI_GUARDRAILS.md`;
- `../21_RISCHI_DECISIONI_OPEN_POINTS/COLLAUDO_MASTER_ACCETTAZIONE.md`.
