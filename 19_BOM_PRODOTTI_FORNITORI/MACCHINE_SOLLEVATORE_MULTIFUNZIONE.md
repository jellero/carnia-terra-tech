# BOM-021 — Sollevatore / mezzo multifunzione

**Aggiornato:** 18 settembre 2026  
**Ambito:** movimentazione pesante, forche, accessori e lavoro in quota certificato.  
**Stato:** `FUNZIONE CORE / TELESCOPICO DA DEMO-RFQ / BENNA OBBLIGATORIA / ACCESSO IN QUOTA DA CHIUDERE`.

## 1. Distinta principale

| Codice | Voce | Quantità working | Stato | Benchmark / nota |
|---|---|---:|---|---|
| LFT-MAIN-001 | telescopico elettrico compatto | 1 | DA DEMO/RFQ | Merlo EW25.5-90 candidato prioritario |
| LFT-ALT-001 | Manitou MLT 625 e | benchmark | DA RFQ | 2,5 t / 5,9 m / 1,81 m |
| LFT-ALT-002 | JCB 525-60E | benchmark | DA RFQ | 2,5 t / 6 m / 1,84 m |
| LFT-FORK-001 | portaforche + forche 1.2 m | 1 | BASELINE | OEM |
| LFT-SHIFT-001 | traslatore/posizionatore forche | 0–1 | DA TCO | riduce manovre |
| LFT-BKT-001 | benna general purpose | 1 | REQUISITO CORE | humus/compost/substrati/materiali |
| LFT-JIB-001 | gancio/jib carichi sospesi | 0–1 | CONDIZIONALE | solo OEM e formazione specifica |
| LFT-AWP-001 | piattaforma persone OEM | 0–1 | DA CONFRONTO H1 | se copre realmente i punti manutentivi |
| LFT-AWP-PREP | predisposizione macchina navicella | 0–1 | OBBLIGATORIA SE AWP | OEM |
| LFT-REMOTE | radiocomando OEM | 0–1 | CONDIZIONALE | solo configurazione autorizzata |
| LFT-TIRE-001 | pneumatici set | 1 | DA SCELTA | agricolo/industriale |
| LFT-CHG-001 | caricatore/wallbox | 1 | OBBLIGATORIO | 230/400 V da versione |
| LFT-CHG-002 | fast charger/opzione | 0–1 | DA DUTY | costo separato |
| LFT-BAT-SP | batteria trazione ricambio | 0–1 | DA TCO | lead time/garanzia |
| LFT-LIGHT | luci lavoro/beacon | 1 package | REQUISITO | OEM |
| LFT-CAM | camera posteriore/360 | 0–1 package | PREFERENZA | persone/angoli ciechi |
| LFT-REC | kit recovery/traino | 1 | OBBLIGATORIO | secondo manuale |
| LFT-TELEM | telematica | 0–1 | CONDIZIONALE | cloud non vitale |
| LFT-L2-001 | stoccatore elettrico compatto | 1 | CANDIDATO | EP EST122 o classe equivalente |
| LFT-H1-001 | PLE cingolata compatta tipo ragno | 0–1 | FUNZIONE CORE / ACQUISTO CONDIZIONALE | confronto con piattaforma OEM/noleggio |
| LFT-L2-BAT | batteria stoccatore | 1 | inclusa/ricambio | AGM/Li-ion da TCO |
| LFT-L2-CHG | caricatore stoccatore | 1 | incluso | 230 V preferito |
| LFT-SP-001 | filtri/olio/guarnizioni | 1 lotto | RICAMBIO | primo anno |
| LFT-SP-002 | tubo idraulico critico | 1 lotto | DA OEM | standardizzare dove possibile |
| LFT-SP-003 | sensore/interlock accessorio | 0–1 | DA SLA | lead time |
| LFT-SP-004 | pneumatico/ruota | 0–1 | DA TCO | spazio/lead time |
| LFT-COM-001 | commissioning macchina | 1 | OBBLIGATORIO | controlli/accessori |
| LFT-COM-002 | acceptance con carichi reali | 1 | OBBLIGATORIO | pallet/bin/porte/pendenze |
| LFT-TRN-001 | formazione telescopico | operatori | OBBLIGATORIO | Accordo vigente |
| LFT-TRN-002 | modulo persone/carichi sospesi | operatori | CONDIZIONALE | se funzioni usate |
| LFT-VER-001 | verifiche periodiche | annuale | OPEX | regime applicabile |
| LFT-DOC | DoC/manuali/diagrammi/as-built | 1 lotto | OBBLIGATORIO | consegna proprietario |

## 2. Merlo EW25.5-90 — candidato prioritario

Dati pubblici correnti/di gamma:

- portata massima **2.500 kg**;
- altezza massima ~**4,8–5,0 m**;
- sbraccio ~**2,6 m**;
- larghezza **1.540 mm**;
- altezza ~**1.975 mm**;
- massa ~**4.950–5.120 kg** secondo configurazione;
- 4WD versione 90;
- elettrico, batteria 48 V 960 Ah nelle schede eWorker archiviate;
- autonomia ideale dichiarata fino a ~8 h, dipendente dal duty cycle;
- attacco rapido e utenze idrauliche;
- piattaforma persone disponibile nella gamma.

### Prezzi trovati

Benchmark dimostrativo 2023 con ~50 h, Francia:

- forche: **€69.000 + IVA**;
- forche + piattaforma con radiocomando: **€75.000 + IVA**.

`BENCHMARK USATO/DEMO, NON BASELINE DI ACQUISTO NUOVO`.

Usato 2022 osservato:

- ~€53.500–63.500 a seconda di annuncio/configurazione.

Questi prezzi servono per TCO e valore residuo, non per definire il CAPEX agevolabile: l'acquisto di progetto resta nuovo salvo decisione esplicita.

### Piattaforma persone

Merlo documenta l'abbinamento eWorker + piattaforma come sistema conforme EN 280 nella configurazione autorizzata; una piattaforma compatta riportata nella documentazione Merlo porta 2 persone / 200 kg e richiede predisposizione specifica.

Regola Carnia: **l'abbinamento deve essere espressamente autorizzato da Merlo per la macchina/seriale acquistato**.

## 3. Manitou MLT 625 e — alternativa agricola

- 2.500 kg;
- 5,90 m;
- 3,30 m sbraccio;
- 1,81 m larghezza;
- 2,00 m altezza;
- raggio esterno 3,31 m;
- 4.762 kg con forche;
- 34,8 kWh Li-ion;
- caricatore 9 kW;
- 4WD / 4WS / crab;
- 20 km/h;
- 84 l/min @ 235 bar.

Produttore lo propone esplicitamente anche per uso in serre/stalle.

**Prezzo:** `PREZZO DA PREVENTIVO`.

## 4. JCB 525-60E — alternativa

- 2.500 kg;
- 6,0 m;
- portata 2.000 kg a quota massima;
- sbraccio max 3,5 m, 720 kg a max sbraccio;
- 1,84 m larghezza;
- 1,89 m altezza;
- raggio esterno 3,7 m;
- massa ~5.145 kg;
- batteria Li-ion 24 kWh;
- 4WD / 3 modalità sterzo;
- manutenzione dichiarata ogni 500 h.

**Prezzo elettrico:** `PREZZO DA PREVENTIVO`.

Non usare come benchmark il prezzo del 525-60 diesel.

## 5. Stoccatore L2 — EP EST122 benchmark

Dati:

- 1.200 kg;
- larghezza **792 mm**;
- lunghezza 1.715 mm;
- raggio di sterzata ~1.464 mm;
- sollevamento ~2,93–3,01 m;
- 24 V / 85 Ah AGM;
- ~590 kg;
- consumo dichiarato ~0,62 kWh/h secondo DIN EN 16796;
- corridoio di stivaggio europallet ~2,23 m.

Prezzo pubblico Italia: **da €2.900**, regime IVA da pagina commerciale.

Alternative economiche 1.200 kg / 3 m osservate ~€1.899–1.900 + IVA; classe professionale al litio da ~€4.490–7.990 + IVA.

Il L2 è complemento del telescopico, non sostituto.

## 6. Compatibilità con layout Carnia

### Corsie coltura ~1,20 m

- Merlo 1,54 m: **NO**;
- Manitou 1,81 m: **NO**;
- JCB 1,84 m: **NO**;
- EP EST122 0,792 m: passa fisicamente, ma il pallet e la manovra richiedono spazio molto maggiore; non assumere uso normale nelle file coltura.

### Corridoio tecnico ~4 m

Compatibile da validare con turning envelope, carico e protezioni laterali.

### Tech Barn

Stoccatore L2 prioritario per pallet ordinari; telescopico entra solo se porte, soletta e raggi lo consentono.

## 7. CAPEX working

Nessun totale definitivo.

Ordine di grandezza documentato:

- telescopico Merlo eWorker classe 2,5 t: **€69–75k + IVA** su demo quasi nuove con forche / forche+navicella;
- nuovo 2026: `DA PREVENTIVO`;
- stoccatore L2: ~**€2–8k + IVA** a seconda della classe;
- accessori, formazione, verifiche, caricatore, trasporto e manutenzione separati.

Non sommare automaticamente €6k come prezzo della piattaforma: la differenza fra i due annunci è solo un benchmark di configurazione.

## 8. OPEX e manutenzione

Registrare:

- kWh/ora e kWh/missione;
- ore macchina;
- cicli batteria;
- pneumatici;
- grassaggio;
- olio/idraulica;
- verifiche giornaliere;
- manutenzione programmata;
- verifiche periodiche obbligatorie;
- formazione/aggiornamenti;
- assicurazione;
- fermo macchina e noleggio sostitutivo.

## 9. Safety gate

- diagramma carico per ogni attrezzatura;
- blocco meccanico/idraulico accessori;
- load management;
- ROPS/FOPS;
- procedure pedoni/mezzi;
- test frenata e pendenza;
- piattaforma solo OEM/autorizzata;
- modulo formazione funzione persone/carichi sospesi se applicabile;
- verifiche periodiche annuali del telescopico secondo regime vigente;
- nessuna modifica a radiocomando/interlock fuori OEM.

## 9A. Ruolo nei cicli materia

Il mezzo L1 serve a:
- alimentare baie e letti humus;
- movimentare big bag;
- muovere substrati;
- caricare vaglio/miscelatore futuri;
- movimentare prodotto finito;
- gestire materiali di cantiere e manutenzione.

Questo utilizzo rende il mezzo core anche senza AMR.

## 10. Decisione working

**Direzione preferita da validare:**

1. Merlo EW25.5-90 nuovo con forche come L1;
2. predisposizione + piattaforma OEM da quotare contestualmente, se il TCO sostituisce realmente PLE/noleggi;
3. benna general purpose inclusa nel pacchetto iniziale;
4. stoccatore elettrico L2 da ~1,2 t per Tech Barn;
5. AMR BOM-020 per trasporto ripetitivo delle cassette;
6. capacità accesso in quota obbligatoria: piattaforma OEM se sufficiente, altrimenti PLE ragno o noleggio con SLA;
7. noleggio per attrezzature eccezionali che non meritano CAPEX.