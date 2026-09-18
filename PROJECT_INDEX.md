# Carnia TerraTech — Project Index

**Ruolo:** indice operativo e mappa di copertura del progetto.  
**Aggiornato:** 18 settembre 2026.

## 1. Scopo

Il repository deve permettere di progettare l'azienda senza lasciare aree scoperte. Ogni decisione deve essere collegata a costi, manutenzione, sicurezza, dipendenze, crescita e qualità della vita.

## 2. Struttura target

- `00_VISIONE_E_PRINCIPI/` — missione, KPI, guardrail e decision gates;
- `01_MASTERPLAN_E_TERRENO/` — lotto, vincoli, accessi, drenaggi, espansioni;
- `02_AGRONOMIA/` — colture, calendari, rese, vite, luppolo, siepi, outdoor;
- `03_SERRA/` — struttura, comparti, coperture, aperture, schermi, HAF, fogging, supporti coltura, drenaggi, porte, recupero pioggia e cantiere;
- `04_ACQUA_E_FERTIRRIGAZIONE/` — fonte, accumulo, filtri, pompe, dosaggio, distribuzione, drenaggio;
- `05_TERMICO_E_CLIMA/` — carico termico, PDC, accumulo, distribuzione, boost, deumidificazione, emergenza;
- `06_ENERGIA_ELETTRICA_FV/` — FV, inverter, rete, UPS, generatore, EMS;
- `07_AUTOMAZIONE_DATI_AI/` — PLC, I/O, sensori, rete, edge, vision, cybersecurity e R&D robotica/laser;
- `08_MACCHINE_E_LOGISTICA/` — AMR, sollevatore, piattaforme, raccolta, carrelli e robot verde;
- `09_TECH_BARN_E_POST_RACCOLTA/` — celle, confezionamento, officina, magazzini e centro trasformazione conto terzi;
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

**RAFFINATO / BASE DI GOVERNO DEL PROGETTO.**

## 4. Stato punto 01 — Terreno e masterplan

**RAFFINATO / IN ATTESA DI LOTTO REALE.**

## 5. Stato punto 02 — Agronomia

**RAFFINATO / PORTAFOGLIO E METODO DEFINITI / DATI COLTURALI DA VALIDARE.**

Working portfolio: C1 pomodoro premium; C2 peperone; C3 lattuga; C4 lattuga/leaf flessibile; C5 baby leaf/rucola/spinacio; C6 basilico + vivaio + prove.

## 6. Stato punto 03 — Serra

**RAFFINATO COME ARCHITETTURA / BOM-001…008 STRUTTURATE / VALIDAZIONE BLOCCATA DA DATI REALI.**

Matrice: `03_SERRA/POINT_03_CLOSURE_MATRIX.md`.

## 7. Stato punto 04 — Acqua e fertirrigazione

**ARCHITETTURA STRUTTURATA / BOM-013…018 SVILUPPATE / TRATTAMENTO-DISINFEZIONE E DRENAGGIO-RIUSO DA SVILUPPARE / VALIDAZIONE BLOCCATA DA LOTTO, ACQUA E CROP CARD.**

Documenti principali: `04_ACQUA_E_FERTIRRIGAZIONE/README.md`, package distribuzione/filtrazione/pompe/fertirrigazione/tank chimici/accumulo e relativi RFQ; BOM-013…018 e fonti dedicate.

Dati guida:

- BOM-013: 24 settori working; 1.000 punti goccia ~€470–515 + IVA prima di dorsali/valvole/posa;
- BOM-014: filtrazione working 120 mesh/~130 µm;
- BOM-015: pompe 1+1, Grundfos CR10-6 benchmark €1.946,78 IVA incl./cad;
- BOM-016: A/B/acido; sole pompe scenario ~€1.744–1.894 + IVA;
- BOM-017: scenario tank A/B/acido 500/500/200 L; soli contenitori ~€509,40 + IVA;
- BOM-018: 2×150 m³ working, espansione 400–500 m³; 300 m³ = 8,6–10 giorni teorici a 30–35 m³/giorno.

Gate: lotto, analisi acqua, crop card, bilancio idrico, geotecnica/RainMap, RFQ, trattamento/disinfezione, drenaggio/riuso e commissioning.

## 8. Stato punto 05 — Termico e clima

**ARCHITETTURA STRUTTURATA / BOM-009…012 SVILUPPATE / VALIDAZIONE BLOCCATA DA LOTTO, CARICHI E RFQ.**

Matrice: `05_TERMICO_E_CLIMA/POINT_05_CLOSURE_MATRIX.md`.

## 9. Stato punto 06 — Energia elettrica e FV

**ARCHITETTURA FV IN SVILUPPO / BOM-019 MODULI+INVERTER SVILUPPATA / CONNESSIONE, UPS, GENERATORE ED EMS DA SVILUPPARE.**

Documenti: `06_ENERGIA_ELETTRICA_FV/README.md`, `PV_ARCHITECTURE.md`, `RFQ_PV_INVERTERS.md`, BOM-019 e fonti.

### BOM-019 — FV e inverter

Working candidate Trina Vertex S+ TSM-470NEG9R.28:

- 256×470 W = **120,32 kWp**;
- ~511,5 m² di sola superficie moduli;
- ~5,38 t;
- soli moduli ~€17,6–25,3k benchmark UE;
- inverter 2×50 kW o 2×60 kW da confrontare;
- niente FV opaco sopra colture principali;
- CEI 0-21:2026 / CEI 0-16:2026;
- BT/MT e protezioni da preventivo DSO/TICA;
- predisposizione 150–180 kWp.

## 10. Stato punto 08 — Macchine e logistica

**ARCHITETTURA IN SVILUPPO / BOM-020 AMR + BOM-021 SOLLEVAMENTO + BOM-022 TAGLIAERBA SVILUPPATE / MASTERPLAN, PILOT E RFQ BLOCCANTI.**

Documenti: `08_MACCHINE_E_LOGISTICA/README.md` più package dedicati AMR, lifting e lawn mower; BOM-020…022 in `19_BOM_PRODOTTI_FORNITORI/`; fonti dedicate in `22_FONTI_NORME_PREVENTIVI/`.

### BOM-020 — AMR serra

Missioni: trasporto, traino, ritorno vuoti, scouting/imaging, inventario e docking.

- Burro Verde prioritario da pilot: 68,5 cm, payload 227 kg, towing 908 kg, IP65, prezzo UE/Italia da preventivo;
- MiR250 benchmark industriale ma non baseline serra finché resta indoor-only/IP21/non-condensing;
- AgileX Bunker per R&D/scouting, non AMR collaborativo baseline;
- scouting vendor-independent OAK-D + Jetson opzionale.

Gate: demo realistica, CE/DoC, IP/condensa, offline/API, dock, canoni/TCO, ricambi Italia e acceptance >=100 missioni.

### BOM-021 — sollevatore / mezzo multifunzione

Architettura a due livelli:

- L1 telescopico elettrico: **Merlo EW25.5-90** candidato prioritario; 2.500 kg, ~4,8–5 m, ~1,54 m larghezza; benchmark demo ~€69k + IVA con forche / ~€75k + IVA con navicella e radiocomando; nuovo `DA PREVENTIVO`;
- alternative Manitou MLT 625 e e JCB 525-60E;
- L2 stoccatore: EP EST122 benchmark 1.200 kg, 792 mm, ~3 m, da ~€2.900.

Nessun telescopico entra nelle corsie coltura ~1,20 m. Piattaforma persone solo OEM e abbinamento autorizzato.

### BOM-022 — robot tagliaerba

La taglia dipende dalla **superficie netta di prato robotizzabile**, da derivare dal masterplan.

Scenari:

- <=1.500 m²: Kress KR171E, €1.699 IVA incl.;
- 1.500–5.000 m² regolare: **Kress KR174E**, €2.999 IVA incl., candidato working;
- <=5.000 m² difficile/pendente: Mammotion LUBA 2 AWD 5000X €2.499 promo / €2.999 listino, oppure Kress 4×4 KR285E €4.499;
- >5.000 fino a ~12.000 m²/professionale: Husqvarna 560 EPOS €6.994 + RS5 €1.019 = **€8.013 IVA incl.** hardware base.

Guardrail:

- no mowing at night;
- area didattica/relax occupata = stop/no-go;
- prato condiviso con galline = lockout dinamico; rasaerba solo con hens-clear/gate chiuso;
- buffer da vasche, fossi, viabilità e drop-off;
- obstacle detection non sostituisce segregazione;
- perdita cloud/RTK -> safe stop/park.

Ricambi benchmark: Kress KA0002 6 lame €22,90; Husqvarna Endurance HSS 6 pz €31; Mammotion lame €55.

Gate: mappa prato, pendenze, GNSS/RTK/network coverage, pilot, offline behavior, assistenza/ricambi, TCO 5–8 anni e commissioning zone/no-go.

## 11. Stato punto 10 — Benessere, fattoria e servizi

**BOM-023 PULIZIA GALLINE FREE-RANGE + BOM-026 PERGOLATO/VITE/AREA RELAX + BOM-027 FATTORIA DIDATTICA + BOM-028 SPACCIO AUTOMATICO 24/7 SVILUPPATE / LAYOUT, SITO, ERSA, SUAP, PILOT/RFQ BLOCCANTI.**

Vincolo consolidato: galline libere nel dominio dedicato composto da ricovero, portico, parcheggi/superfici dure e prato.

BOM-023:
- manure belt/scraper sotto posatoi;
- rover sanitario dedicato su tutto il dominio galline;
- hard-floor spot pickup su portico/parcheggi;
- grass spot-pickup vision R&D, senza aspirazione continua;
- dirty dock per svuotamento, ricarica e wash;
- gate automatici per separazione temporale galline/veicoli;
- nessun ingresso del rover sanitario in aree food.

Candidati/benchmark: Burro Verde base agricola all-area; AgileX Bunker Pro 2.0 ~€22,1k ex VAT R&D; Gausium Beetle 2.0 ~€20k + IVA hard-floor; Big Dutchman SIMBA manure-belt; ChickenGuard/Omlet porte automatiche piccole.

La letteratura dimostra fattibilità su superfici avicole progettate, ma non esiste ancora un COTS provato per gallina + prato + parcheggio: pilot mixed-surface obbligatorio.

Documenti:
- 10_BENESSERE_FATTORIA_E_SERVIZI/CHICKEN_FREE_RANGE_CLEANING_ARCHITECTURE.md;
- 10_BENESSERE_FATTORIA_E_SERVIZI/RFQ_CHICKEN_FREE_RANGE_CLEANING.md;
- 19_BOM_PRODOTTI_FORNITORI/BENESSERE_GALLINE_PULIZIA_AUTONOMA.md;
- 22_FONTI_NORME_PREVENTIVI/BENESSERE_GALLINE_PULIZIA_SOURCES.md.

Correzione BOM-022: il prato condiviso con le galline è lockout dinamico, non no-go permanente; rasaerba solo con hens-clear/gate chiuso.


### BOM-026 — pergolato, vite e area relax

Architettura:
- pergolato aperto; legno lamellare candidato working, acciaio zincato alternativa;
- sezioni, controventi, fondazioni e ancoraggi `DA CALCOLO`;
- neve/vento da sito reale e NTC; nessun carico catalogo assunto come progetto;
- telo ombreggiante removibile opzionale, non caricato da neve salvo verifica esplicita;
- vite/rampicanti su griglia indipendente e manutenibile;
- varietà vite da microclima/uso frutto; barbatelle resistenti solo benchmark di acquisto;
- zona irrigua dedicata, svuotabile in inverno;
- superficie permeabile + drenaggio;
- arredi modulari;
- illuminazione/prese/rete outdoor con manual override;
- manutenzione strutturale, agronomica, drenaggi, irrigazione ed elettrico.

Benchmark unitari già tracciati:
- GL24h retail €39,90–118,50/cad secondo formato osservato;
- calcestruzzo fondazioni FVG 2026 €237,52/m³ nella voce consultata, escluso plinto completo;
- vite resistente da tavola €5,95/cad;
- kit goccia 100 m² €54,90;
- griglia permeabile €17,71/m²;
- tavolo outdoor ~8 posti €310;
- LED IP65 10 W €62,66 IVA incl.;
- FG16OR16 3×2,5 €3,10/m;
- cavidotto Ø40 FVG 2026 €1,83/m;
- Ubiquiti U7 Outdoor €185 + Ethernet surge protector €12.

Regola: nessun CAPEX totale prima di layout, carichi, geotecnica e RFQ; distinta a quantità `DA LAYOUT / DA CALCOLO` con costo pezzo per pezzo.

Documenti:
- `10_BENESSERE_FATTORIA_E_SERVIZI/PERGOLATO_VITE_AREA_RELAX_ARCHITECTURE.md`;
- `10_BENESSERE_FATTORIA_E_SERVIZI/RFQ_PERGOLATO_VITE_AREA_RELAX.md`;
- `19_BOM_PRODOTTI_FORNITORI/BENESSERE_PERGOLATO_VITE_AREA_RELAX.md`;
- `22_FONTI_NORME_PREVENTIVI/BENESSERE_PERGOLATO_VITE_AREA_RELAX_SOURCES.md`.


### BOM-027 — fattoria didattica

Baseline:
- zoning visitatori Z0–Z3 con separazione fisica da produzione e aree tecniche;
- planimetria ERSA integrata nel masterplan;
- referente formato + RC visite;
- primo soccorso vicino ad acqua potabile;
- parcheggio/drop-off mezzo accompagnatore;
- servizi igienici adeguati/accessibili;
- percorso accessibile a primo soccorso, WC, spazio coperto e parte del percorso;
- spazio coperto con BOM-026 come candidato da verificare;
- observation point per serra/acqua/energia/automazione/animali;
- modulo galline integrato con BOM-023, macchine in lockout/segregazione durante la visita;
- safety signage separata dalla didattica;
- pannelli/QR e dashboard read-only su guest network separata dall'OT;
- food tasting/somministrazione non baseline;
- registro visite, meteo/emergenza e visita pilota.

Benchmark:
- percorso drenante FVG 2026 €37,05–39,76/m² nella voce consultata;
- fondazione granulare €44,80/m³;
- safety signage PVC ~€34,63–43,46/cad;
- lavamani autonomo backup €242,10;
- first aid Allegato 1 €75,90 + IVA valigetta / €117,90 + IVA armadietto maggiorato;
- reintegro €65,25 + IVA;
- Dibond didattico 70×100 €90/cad;
- tavolo picnic accessibile €439,79;
- lavagna 120×90 €85,73.

Formazione:
- corso base 2026 osservato 12 h e gratuito per categorie ammesse, indicato come parte 1 di 2;
- catalogo include specialistico fattoria didattica 24 h;
- requisito e sequenza correnti da confermare con ERSA.

Documenti:
- `10_BENESSERE_FATTORIA_E_SERVIZI/FATTORIA_DIDATTICA_ARCHITECTURE.md`;
- `10_BENESSERE_FATTORIA_E_SERVIZI/RFQ_FATTORIA_DIDATTICA.md`;
- `19_BOM_PRODOTTI_FORNITORI/BENESSERE_FATTORIA_DIDATTICA.md`;
- `22_FONTI_NORME_PREVENTIVI/BENESSERE_FATTORIA_DIDATTICA_SOURCES.md`.


### BOM-028 — spaccio automatico self-service 24/7

Baseline:
- doppio gate normativo: vendita diretta agricola ex D.Lgs. 228/2001 vs vending retail generico;
- preferenza a R1 agricolo se prodotti propri/prevalenza restano nel perimetro;
- kiosk/locale protetto baseline; outdoor solo con macchina specificamente progettata/garantita;
- matrice SKU/temperatura collegata a BOM-024;
- nessun 0–4 °C automatico per pomodoro/peperone/basilico;
- Gusto 8 multi-temperature candidato;
- Gusto 8 Lift prioritario per prodotti fragili;
- Drum/FAS Easy Food alternative;
- cashless baseline con telemetria;
- fiscalizzazione da validare su macchina/payment reali;
- logger indipendente, temp alarm e stop-vend;
- CCTV privacy-aware, no audio/face recognition;
- rete vending/CCTV separata dall'OT;
- UPS solo IT/elettronica, refrigerazione su continuità generale;
- 100 cicli/SKU critico + 500 vendite miste prima del go-live.

Benchmark:
- Necta Gusto 8 ~€5.900 EU seller benchmark;
- Gusto 8 Lift ~€7.200;
- Gusto Drum ~€10.600–13.199;
- FAS Pro 900 €8.840 net benchmark listing incl. Nayax;
- Nayax VPOS Touch €430;
- Nayax service €15,75/mese + fee 1,45–3,5% benchmark;
- Testo 160 T €124 net / €151,28 IVA incl.;
- Ubiquiti G5 Turret Ultra €80/cad;
- NIA/VIA sanitaria €20 reference.

Documenti:
- `10_BENESSERE_FATTORIA_E_SERVIZI/SPACCIO_AUTOMATICO_24_7_ARCHITECTURE.md`;
- `10_BENESSERE_FATTORIA_E_SERVIZI/RFQ_SPACCIO_AUTOMATICO_24_7.md`;
- `19_BOM_PRODOTTI_FORNITORI/BENESSERE_SPACCIO_AUTOMATICO_24_7.md`;
- `22_FONTI_NORME_PREVENTIVI/BENESSERE_SPACCIO_AUTOMATICO_24_7_SOURCES.md`.

## 12. R&D trasversale — laser, vision e manutenzione robotica

Documento: `07_AUTOMAZIONE_DATI_AI/LASER_ROBOTICS_RND.md`. Stato: `R&D CANDIDATO / NON BASELINE CAPEX`.

## 13. Stato punto 09 — Tech Barn e post-raccolta

**BOM-024 CELLE FRIGORIFERE + BOM-025 RACCOLTA/PACKAGING SVILUPPATE / CARICHI, SKU E RFQ BLOCCANTI.**

Baseline:
- CR-A COLD-LEAF ~1–3 °C, lattuga/baby leaf/spinacio;
- CR-B COOL-SENSITIVE ~10–12 °C, pomodoro/peperone/basilico con crop-card e short dwell;
- ~25 m²/cella working, totale freddo ~50 m² più zona servizio;
- forced-air precooling predisposto per CR-A;
- due sistemi frigoriferi indipendenti;
- confronto 1×100% vs circuiti modulari sulla cella critica;
- refrigerante naturale o GWP <150;
- monitoraggio locale + logger indipendente;
- pavimento strutturale verificato per BOM-021.

Benchmark:
- shell 4,74×4,74×2,54 m senza gruppo: €6.775,99 + IVA;
- R290 KDC800N: €5.399,99 net, max 50 m³ dichiarati, solo benchmark;
- R290 KDC600N: €4.899,99 net, max 35,1 m³ @32 °C / 21 m³ @43 °C;
- Testo 160 TH: €180 + IVA/cella.

Regola: dimensionamento da kg prodotto / temperatura ingresso / pull-down time, non da m³ stanza.

### BOM-025 — raccolta e packaging

Baseline:
- cassette 600×400 food-contact, quantità da `peak kg in loop / kg per crate × 1,3–1,5`;
- 6–12 low dollies + 2–4 raised come working range;
- 3 tavoli inox 1800×700 working;
- 2×30 kg + 1×300 kg scales;
- Zebra ZD421 TT Ethernet;
- tray sealer manuale opzionale;
- wash/spin leafy non baseline finché non viene scelta una linea ready-to-eat;
- label/traceability locale.

Benchmark core:
- dolly 600×400 300 kg €45,50 + IVA;
- raised trolley €223,25 + IVA;
- inox table €217,99–228,99 net;
- 30 kg scale €413,99 + IVA;
- 300 kg scale €710,49 + IVA;
- ZD421 TT Ethernet €499,88 + IVA;
- manual tray sealers ~€1.408–2.260 + IVA;
- powered spinner 35 L / 70 kg/h €572,99 net.

Guardrail: washing is a process-risk decision; EFSA 2025 notes cross-contamination risk from poorly managed process water.

Documenti:
- 09_TECH_BARN_E_POST_RACCOLTA/README.md;
- 09_TECH_BARN_E_POST_RACCOLTA/COLD_ROOMS_ARCHITECTURE.md;
- 09_TECH_BARN_E_POST_RACCOLTA/RFQ_COLD_ROOMS.md;
- 09_TECH_BARN_E_POST_RACCOLTA/HARVEST_PACKAGING_ARCHITECTURE.md;
- 09_TECH_BARN_E_POST_RACCOLTA/RFQ_HARVEST_PACKAGING.md;
- 19_BOM_PRODOTTI_FORNITORI/TECH_BARN_CELLE_FRIGORIFERE.md;
- 19_BOM_PRODOTTI_FORNITORI/TECH_BARN_RACCOLTA_PACKAGING.md;
- fonti dedicate in 22_FONTI_NORME_PREVENTIVI/.

## 14. Modulo futuro — centro trasformazione conto terzi

Documento: `09_TECH_BARN_E_POST_RACCOLTA/CENTRO_TRASFORMAZIONE_CONTO_TERZI.md`. Stato: `MODULO FUTURO AD ALTO POTENZIALE / DA BUSINESS CASE / NON ANCORA NEL CAPEX BASE`.

## 15. Metodo BOM obbligatorio

Per ogni oggetto/sottosistema: funzione, requisiti, quantità, alternative, prezzo, IVA/trasporto, installazione, consumi, manutenzione, ricambi, vita utile, sicurezza, failure mode, fallback, contributi, dipendenze, espansione e stato decisionale.

## 16. Stato attuale dei grandi blocchi

Restano nel perimetro sostenibilità personale, R&D robotica/laser e centro trasformazione conto terzi.

## 17. Sequenza BOM

### Già strutturate

- Serra BOM-001…008;
- BOM-009 distribuzione termica;
- BOM-010 accumulo/primario/HX;
- BOM-011 PDC 3+1;
- BOM-012 boost/deumidificazione/emergenza;
- BOM-013 distribuzione irrigua;
- BOM-014 filtrazione acqua;
- BOM-015 pompe principali irrigazione 1+1;
- BOM-016 fertirrigazione A/B/acido;
- BOM-017 serbatoi fertilizzanti e contenimento;
- BOM-018 accumulo acqua 300 m³;
- BOM-019 FV e inverter;
- BOM-020 AMR serra;
- BOM-021 sollevatore / mezzo multifunzione;
- BOM-022 robot tagliaerba;
- BOM-023 pulizia galline free-range;
- BOM-024 celle frigorifere;
- BOM-025 raccolta e packaging;
- BOM-026 pergolato, vite e area relax;
- BOM-027 fattoria didattica;
- **BOM-028 spaccio automatico self-service 24/7**.

### Prossimo package

**BOM-029 — centro trasformazione conto terzi:** capacity model, famiglie processo succo/confetture/trasformati, zoning food, lavaggio/preparazione, cottura/pastorizzazione, riempimento, CIP/pulizia, utilities, laboratorio/QC, packaging, HACCP, CAPEX/OPEX e domanda locale.

### Coda successiva

1. centro trasformazione conto terzi: capacity model + BOM succo/confetture + CAPEX/OPEX + domanda locale.

La sequenza può cambiare quando una dipendenza tecnica rende necessario anticipare un blocco.