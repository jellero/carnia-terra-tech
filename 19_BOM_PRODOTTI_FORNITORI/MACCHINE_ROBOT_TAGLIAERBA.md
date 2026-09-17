# BOM-022 — Robot tagliaerba autonomo

**Aggiornato:** 17 settembre 2026  
**Ambito:** manutenzione automatica del prato/verde non produttivo.  
**Stato:** `CANDIDATI REALI / SUPERFICIE PRATO E PILOT BLOCCANTI`.

## 1. Distinta principale

| Codice | Voce | Quantità working | Stato | Benchmark / nota |
|---|---|---:|---|---|
| MOW-BASE-001 | robot tagliaerba | 1 | DA MASTERPLAN/PILOT | classe da area netta prato |
| MOW-KR171 | Kress KR171E | benchmark M1 | PREZZO TROVATO | 1.500 m², €1.699 IVA incl. |
| MOW-KR174 | Kress KR174E | benchmark M2 | CANDIDATO | 5.000 m², €2.999 IVA incl. |
| MOW-LUBA | Mammotion LUBA 2 AWD 5000X | benchmark M3 | CANDIDATO TERRENO DIFFICILE | €2.499 promo / €2.999 listino, IVA incl. |
| MOW-KR285 | Kress EyePilot 4×4 KR285E | benchmark M3 | ALTERNATIVA AWD | 5.000 m², €4.499 IVA incl. |
| MOW-HQ560 | Husqvarna 560 EPOS | benchmark M4 | CANDIDATO PRO | 12.000 m², €6.994 IVA incl. |
| MOW-HQRS5 | Husqvarna EPOS RS5 | 1 se HQ | NECESSARIO HQ | €1.019 IVA incl. |
| MOW-DOCK | dock/charging station | 1 | REQUISITO | incluso o separato da modello |
| MOW-RTK | RTK/reference station | 0–1 | DA MODELLO | hardware/servizio da distinguere |
| MOW-MOUNT | palo/supporto RTK | 0–1 | DA MODELLO | visibilità cielo |
| MOW-PWR | alimentazione 230 V + protezioni | 1 package | REQUISITO | esterno, drenato, protetto |
| MOW-GAR | garage | 0–1 | OPZIONE | solo OEM/compatibile |
| MOW-VIS | Vision AI / OAS optional | 0–1 | DA MODELLO | non sostituisce regole safety |
| MOW-SIM | SIM / cloud / RTK service | annuale | DA RFQ | costo 5–8 anni |
| MOW-MAP | mapping e no-go commissioning | 1 | OBBLIGATORIO | as-built masterplan |
| MOW-SP-BLD | lame + viti | 2–4 set | RICAMBIO | Kress €22,90/6; HQ HSS €31/6 |
| MOW-SP-DISC | disco lama | 0–1 | DA SLA | lead time |
| MOW-SP-WHL | ruota/pneumatico | 0–1 set | DA TCO | terreno reale |
| MOW-SP-BAT | batteria | 0–1 | DA TCO | prezzo/lead time OEM |
| MOW-SP-PSU | alimentatore dock | 0–1 | PREFERENZA | ricambio critico economico |
| MOW-SP-SEN | sensore/bumper | 0–1 | DA SLA | modello-specifico |
| MOW-ANTI | antifurto/GPS/PIN | 1 | REQUISITO | nativo o servizio |
| MOW-SIGN | cartello area robotizzata | 1+ | DA SAFETY | area visitatori |
| MOW-COM-001 | prova docking | 20 cicli min | OBBLIGATORIO | senza interventi |
| MOW-COM-002 | prova no-go | 1 lotto | OBBLIGATORIO | acqua/pollaio/colture/pubblico |
| MOW-COM-003 | prova offline | 1 | OBBLIGATORIO | Internet/4G/Wi-Fi |
| MOW-COM-004 | prova safety | 1 lotto | OBBLIGATORIO | lift/tilt/stop/ostacoli |
| MOW-DOC | DoC/manuali/mappe/config | 1 lotto | OBBLIGATORIO | proprietario |

## 2. Scenari economici hardware

### M1 — <=1.500 m²

Kress KR171E: **€1.699 IVA inclusa**. Installazione, eventuali servizi e ricambi separati.

### M2 — <=5.000 m² regolare

Kress KR174E: **€2.999 IVA inclusa**.

Dati principali:

- 5.000 m²;
- 647×470×290 mm;
- 12,6 kg;
- pendenza 40%;
- IPX5;
- 4G/app/OTA;
- OAS;
- taglio sistematico.

### M3 — <=5.000 m² terreno difficile

Mammotion LUBA 2 AWD 5000X:

- **€2.499 IVA inclusa** in promozione osservata, listino €2.999;
- sito ufficiale indicava esaurito al 17/09/2026;
- AWD, pendenza fino a 80%;
- 400 mm di taglio;
- IPX6 macchina/dock;
- vision + RTK + radar ultrasonico + bumper.

Kress EyePilot 4×4 KR285E: **€4.499 IVA inclusa**, alternativa AWD da demo.

### M4 — <=12.000 m² professionale

Husqvarna Automower 560 EPOS:

- robot €6.994 IVA inclusa;
- RS5 €1.019 IVA inclusa;
- totale hardware base **€8.013 IVA inclusa**;
- Vision AI opzionale non incluso;
- installazione/mapping non incluso.

Prestazioni pubbliche:

- 12.000 m²;
- 50% pendenza;
- 17,3 kg, 780×590×310 mm;
- IPX5;
- 26 cm, 20–60 mm;
- 150 min lavoro / 55 min carica;
- 57 kWh/mese al massimo utilizzo;
- radar, GPS antifurto, Fleet Services.

Husqvarna 580 EPOS: 16.000 m², €9.054 IVA inclusa + RS5; benchmark, non baseline.

## 3. Ricambi e OPEX

Prezzi trovati:

- Kress KA0002 6 lame lunga durata: **€22,90 IVA inclusa**;
- Husqvarna Endurance HSS 6 pz: **€31 IVA inclusa**;
- Husqvarna Endurance HSS 45 pz: **€188 IVA inclusa** listino 2026;
- Mammotion lame ricambio: **€55 IVA inclusa** osservati.

Da preventivo:

- batteria;
- dock/alimentatore;
- RTK station;
- motori ruota/taglio;
- sensori;
- SIM/cloud/RTK correction;
- manutenzione annuale e winter service.

TCO:

`CAPEX + installazione + elettrico + servizi digitali + lame + batteria + ricambi + manutenzione + fermo macchina`.

Confrontare a 5 e 8 anni.

## 4. Guardrail safety

- **taglio solo diurno** come baseline;
- robot fermo quando area didattica/relax è occupata;
- pollaio/free-range = no-go;
- buffer fisico/virtuale da vasche, fossi, strade e drop-off;
- obstacle AI non sostituisce segregazione;
- mappa rivista dopo lavori o modifiche layout;
- manual stop sempre accessibile;
- prove lift/tilt/blade stop al commissioning.

Leibniz-IZW documenta il rischio di collisioni notturne con ricci e promuove night bans come misura di mitigazione.

## 5. Conformità

Richiedere dichiarazione UE di conformità e standard applicati. La famiglia tecnica di riferimento per robot rasaerba è IEC 60335-2-107:2017 + AMD1:2020 + AMD2:2021; in ambito europeo verificare la versione EN applicabile alla macchina offerta.

Il Regolamento (UE) 2023/1230 sulle macchine diventa applicabile obbligatoriamente dal 20 gennaio 2027; verificare il regime applicabile alla data di immissione sul mercato/messa in servizio.

## 6. Contributi

- acquisto nuovo come baseline;
- eleggibilità contributiva: `DA VERIFICARE PER BANDO`;
- separare sempre costo reale da costo eventualmente ammissibile;
- software/SIM/manutenzione potrebbero avere trattamento diverso dall'hardware: `DA VERIFICARE`.

## 7. Decisione working

Non congelare il modello prima del masterplan.

- se prato <=1.500 m²: classe KR171E;
- se 1.500–5.000 m² e fondo normale: **KR174E come candidato economico/prioritario**;
- se terreno difficile/forte pendenza: LUBA 2 AWD 5000X o Kress 4×4 da pilot;
- se >5.000 m² o richiesta professionale/assistenza fleet: Husqvarna 560 EPOS.

Il criterio finale è TCO + affidabilità sul sito + supporto, non la capacità massima dichiarata.