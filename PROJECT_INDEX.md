# Carnia TerraTech — Project Index

**Ruolo:** indice operativo e mappa di copertura del progetto.  
**Aggiornato:** 18 settembre 2026.

## 1. Scopo

Il repository deve permettere di progettare l'azienda senza lasciare aree scoperte. Ogni decisione deve essere collegata a costi, manutenzione, sicurezza, dipendenze, crescita e qualità della vita.

## 2. Struttura target

- `00_VISIONE_E_PRINCIPI/` — missione, KPI, guardrail e verifiche decisionali;
- `01_MASTERPLAN_E_TERRENO/` — lotto, vincoli, accessi, drenaggi, espansioni;
- `02_AGRONOMIA/` — colture, calendari, rese, vite, luppolo, siepi, esterno;
- `03_SERRA/` — struttura, comparti, coperture, aperture, schermi, HAF, fogging, supporti coltura, drenaggi, porte, recupero pioggia e cantiere;
- `04_ACQUA_E_FERTIRRIGAZIONE/` — fonte, accumulo, filtri, pompe, dosaggio, distribuzione, drenaggio;
- `05_TERMICO_E_CLIMA/` — carico termico, PDC, accumulo, distribuzione, boost, deumidificazione, emergenza;
- `06_ENERGIA_ELETTRICA_FV/` — FV, inverter, rete, BESS/backup, EMS;
- `07_AUTOMAZIONE_DATI_AI/` — server centrale di orchestrazione, pianificatore, dati/AI, PLC, I/O, sensori, rete, edge, vision, cybersecurity e R&S robotica/laser;
- `08_MACCHINE_E_LOGISTICA/` — AMR, sollevatore, piattaforme, raccolta, carrelli e robot verde;
- `09_TECH_BARN_E_POST_RACCOLTA/` — celle, confezionamento, officina, magazzini e centro trasformazione conto terzi;
- `10_BENESSERE_FATTORIA_E_SERVIZI/` — pergolato, verde, fattoria didattica, servizi futuri, spaccio 24/7;
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

**Fuori dalla numerazione e dal progetto agricolo principale:**

- `RND_CORRELATO_EU/` — progetto R&S tecnologico correlato; usa Carnia TerraTech come laboratorio operativo reale/dimostratore ma mantiene budget, TRL, deliverable, rischi e finanziamenti separati dal progetto principale. Non entra nella sequenza BOM 001… e non è requisito per l'operatività agricola.
- `EXTRA_AGRITURISMO_EVOLUTIVO/` — piano extra di diversificazione agrituristica con budget e fondi propri; E1 spuntini non cucinati, poi esperienze, cucina e ospitalità solo per verifica bloccante successivi. Non modifica la configurazione base agricola né la sequenza BOM.

## 3. Stato punto 00 — Visione e principi

**RAFFINATO / BASE DI GOVERNO DEL PROGETTO.**

## 4. Stato punto 01 — Terreno e masterplan

**RAFFINATO / IN ATTESA DI LOTTO REALE.**

## 5. Stato punto 02 — Agronomia

**RAFFINATO / PORTAFOGLIO E METODO DEFINITI / DATI COLTURALI DA VALIDARE.**

Di lavoro portfolio: C1 pomodoro premium; C2 peperone; C3 lattuga; C4 lattuga/leaf flessibile; C5 baby leaf/rucola/spinacio; C6 basilico + vivaio + prove.

## 6. Stato punto 03 — Serra

**RAFFINATO COME ARCHITETTURA / BOM-001…008 STRUTTURATE / VALIDAZIONE BLOCCATA DA DATI REALI.**

Matrice: `03_SERRA/POINT_03_CLOSURE_MATRIX.md`.

## 7. Stato punto 04 — Acqua e fertirrigazione

**ARCHITETTURA STRUTTURATA / BOM-013…018 + BOM-032 TRATTAMENTO-DISINFEZIONE + BOM-033 DRENAGGIO-RIUSO SVILUPPATE / RIUSO R1 BLOCCATO DA PILOT, Na-Cl, FITOPATOGENI E CLASSIFICAZIONE SCARICHI.**

Documenti principali: `04_ACQUA_E_FERTIRRIGAZIONE/README.md`, package distribuzione/filtrazione/pompe/fertirrigazione/tank chimici/accumulo e relativi RFQ; BOM-013…018 e fonti dedicate.

Dati guida:

- BOM-013: 24 settori di lavoro; 1.000 punti goccia ~€470–515 + IVA prima di dorsali/valvole/posa;
- BOM-014: filtrazione di lavoro 120 mesh/~130 µm;
- BOM-015: pompe 1+1, Grundfos CR10-6 riferimento di confronto €1.946,78 IVA incl./cad;
- BOM-016: A/B/acido; sole pompe scenario ~€1.744–1.894 + IVA;
- BOM-017: scenario tank A/B/acido 500/500/200 L; soli contenitori ~€509,40 + IVA;
- BOM-018: 2×150 m³ di lavoro, espansione 400–500 m³; 300 m³ = 8,6–10 giorni teorici a 30–35 m³/giorno;
- BOM-032: W0/W1/W2/W3/W4 water classes; UV after filtration as working microbial barrier when required; UV sizing from Q + worst-case UVT + validated dose; no blind bypass; chemical sanitation conditional; W3 potable/food kept separate;
- BOM-033: D0–D6 separated water streams; R0 collect/measure/HOLD baseline; C1/C2 measured separately; R1 treatment + clean tank + partial reuse only after 30–60 day pilot; Na/Cl + pathogen guardrails; bleed metered with lawful destination; no default discharge to soil.

Verifica bloccante: lotto, source/seasonal water analyses, UVT254, microbiology, crop card, bilancio idrico, geotecnica/RainMap, RFQ, BOM-032 validation, BOM-033 pilot/mass balance + discharge classification, commissioning.

## 8. Stato punto 05 — Termico e clima

**ARCHITETTURA STRUTTURATA / BOM-009…012 SVILUPPATE / VALIDAZIONE BLOCCATA DA LOTTO, CARICHI E RFQ.**

Matrice: `05_TERMICO_E_CLIMA/POINT_05_CLOSURE_MATRIX.md`.

## 9. Stato punto 06 — Energia elettrica e FV

**BOM-019 FV + BOM-034 EMS/BESS/CONNESSIONE SVILUPPATE / BESS 30 kW POWER BASELINE / kWh, BT-MT, FIRE DESIGN, LOAD PROFILE E RFQ BLOCCANTI / NESSUNA UPS LOCALE.**

Documenti: `06_ENERGIA_ELETTRICA_FV/README.md`, `PV_ARCHITECTURE.md`, `RFQ_PV_INVERTERS.md`, `EMS_BESS_GRID_ARCHITECTURE.md`, `LOAD_PRIORITY_MATRIX.md`, `RFQ_EMS_BESS_GRID.md`, BOM-019, BOM-034 e fonti dedicate.

### BOM-019 — FV e inverter

Di lavoro candidate Trina Vertex S+ TSM-470NEG9R.28:

- 256×470 W = **120,32 kWp**;
- ~511,5 m² di sola superficie moduli;
- ~5,38 t;
- soli moduli ~€17,6–25,3k riferimento di confronto UE;
- inverter 2×50 kW o 2×60 kW da confrontare;
- niente FV opaco sopra colture principali;
- CEI 0-21:2026 / CEI 0-16:2026;
- BT/MT e protezioni da preventivo DSO/TICA;
- predisposizione 150–180 kWp.

### BOM-034 — EMS, BESS e connessione elettrica

**SVILUPPATA / 30 kW POWER BASELINE / ENERGIA UTILE, DSO, FIRE DESIGN E RFQ BLOCCANTI.**

Working architecture:
- BESS C&I AC-coupled, LFP candidate chemistry;
- PCS 30 kW continuous island class;
- scenari **60 / 90 / 120 kWh utili**;
- P0/P1 critical bus, P2 condizionale, P3 shed;
- nessuna UPS locale;
- controller locale grid-forming/load-shed; server centrale solo supervisory/economic layer;
- black-start richiesto e PV-in-island separato come opzione da validare.

Autonomia aritmetica, prima di reserve/losses/auxiliaries/EOL:
- 60 kWh: 2 h @30 kW / 3 h @20 / 4 h @15 / 6 h @10;
- 90 kWh: 3 h @30 / 4,5 h @20 / 6 h @15 / 9 h @10;
- 120 kWh: 4 h @30 / 6 h @20 / 8 h @15 / 12 h @10.

Hard continuity:
- grid loss must not reboot server/network/PLC P0;
- acceptance = blackout reale, non transfer-time marketing;
- soluzione con commutazione nell'ordine dei secondi non è sufficiente da sola per P0 senza ulteriore architettura no-break.

Load anchors già noti:
- irrigazione ~2,2 kW duty pump candidate;
- PDC fino a 9 kW/cad dichiarati; 3 unità fino a 27 kW;
- cold-room compressor references ~1,48–2,25 kW + auxiliaries;
- dehumidification 2,3 / 9,55 kW.
Quindi 30 kW non è "whole farm full-power backup".

Candidate/benchmark:
- TESLA Group STILLA 30 kW / 61 kWh LFP class: RFQ, Italy/island/transfer/fire/service gates open;
- Fronius Verto Plus 30 kW class: manuale OEM corrente con Rapid switch <20 ms + Backup Controller 63A; candidato RFQ prioritario, topology Italia/CEI-DSO e blackout SAT da validare;
- Schneider PM5110 €700 list; PM5340 €1.469; PM5341 MID €1.694.

Grid:
- CEI 0-21:2026-07 se BT;
- CEI 0-16:2026-07 se MT;
- TICA/DSO decide BT/MT e limiti import/export;
- se MT e classe applicabile >=100 kW: CCI/PF2 gate;
- SLI/export limitation dove richiesta;
- custom farm server non assunto come dispositivo CEI/DSO compliant.

Fire:
- BESS esterno dedicato preferito;
- specifica valutazione incendio/esplosione;
- misure finali da sistema selezionato + professionista antincendio.

Documenti:
- `06_ENERGIA_ELETTRICA_FV/EMS_BESS_GRID_ARCHITECTURE.md`;
- `06_ENERGIA_ELETTRICA_FV/LOAD_PRIORITY_MATRIX.md`;
- `06_ENERGIA_ELETTRICA_FV/RFQ_EMS_BESS_GRID.md`;
- `06_ENERGIA_ELETTRICA_FV/DSO_TICA_CONNECTION_READINESS.md`;
- `06_ENERGIA_ELETTRICA_FV/DSO_TICA_DATA_REQUEST.csv`;
- `06_ENERGIA_ELETTRICA_FV/BT_MT_PROTECTION_DECISION_MATRIX.md`;
- `06_ENERGIA_ELETTRICA_FV/RFQ_DSO_GRID_CONNECTION_ENGINEERING.md`;
- `06_ENERGIA_ELETTRICA_FV/GRID_CONNECTION_COST_COMPARISON.csv`;
- `19_BOM_PRODOTTI_FORNITORI/ENERGIA_EMS_BESS_CONNESSIONE.md`;
- `22_FONTI_NORME_PREVENTIVI/ENERGIA_EMS_BESS_CONNESSIONE_SOURCES.md`.

### BOM-030 — server centrale di orchestrazione

**SVILUPPATA / HARDWARE DA RFQ / ACCEPTANCE, BESS E DR BLOCCANTI.**

Di lavoro architecture:
- 2 compute node server-grade;
- 1 QNODE/edge witness;
- 1 backup target separato;
- 10GbE server interconnect;
- BESS 30 kW shared backup;
- nessuna UPS locale.

Compute target:
- 64 GB ECC minimo;
- 128 GB ECC di lavoro;
- 2×1,92 TB enterprise NVMe mirror/node;
- TPM;
- BMC;
- 10GbE.

Software configurazione base:
- Proxmox VE 9.2;
- Debian 13;
- PostgreSQL 18;
- NATS JetStream R3 sui critical stream;
- MQTT edge ingress;
- Keycloak/OIDC;
- Prometheus/Grafana/Loki/Alloy;
- custom pianificatore + dispatcher + reconciler;
- previsione domanda/offerta;
- digital twin/state model;
- Stripe server-side.

Explicitly non-configurazione base:
- Kubernetes;
- Ceph/SAN;
- GPU nel control plane;
- cloud-only database;
- proprietary ERP master;
- UPS locale.

Current public riferimento di confrontos:
- Dell T160 Smart Selection base ~€4.793,77 + IVA; target config RFQ;
- UniFi Pro Max 24 €405;
- Pro XG 10 PoE €629;
- Proxmox Basic su 2 single-socket compute = €740/year;
- PBS Community optional €560/year.

Resilience:
- PostgreSQL primary/replica + WAL/PITR;
- NATS R3 A/B/QNODE;
- edge buffering;
- 3-2-1 backup;
- offsite encrypted copy;
- prove di guasto NODE-A/B/QNODE;
- prova reale del trasferimento BESS;
- prova webhook Stripe ritardato/riconciliazione.

Principio invariato:
- server centrale = sistema autorevole dei dati + pianificatore;
- PLC/edge mantengono sicurezza e cicli di controllo in tempo reale;
- `server non disponibile != impianto non sicuro`.

Documenti:
- `07_AUTOMAZIONE_DATI_AI/README.md`;
- `07_AUTOMAZIONE_DATI_AI/CENTRAL_ORCHESTRATION_SERVER.md`;
- `07_AUTOMAZIONE_DATI_AI/RFQ_CENTRAL_ORCHESTRATION_SERVER.md`;
- `07_AUTOMAZIONE_DATI_AI/EVENT_API_CONTRACTS.md`;
- `07_AUTOMAZIONE_DATI_AI/SERVER_ACCEPTANCE_DR_RUNBOOK.md`;
- `19_BOM_PRODOTTI_FORNITORI/AUTOMAZIONE_SERVER_CENTRALE.md`;
- `22_FONTI_NORME_PREVENTIVI/AUTOMAZIONE_SERVER_CENTRALE_SOURCES.md`.

## 10. Stato punto 08 — Macchine e logistica

**RISK-FIRST / BOM-021 MEZZO CORE / AMR SECONDARIO / ACCESSO IN QUOTA CORE.**

Ordine di priorità:
1. telescopico elettrico compatto con forche + benna;
2. accesso sicuro alle parti alte tramite piattaforma OEM o PLE cingolata "ragno";
3. stoccatore Tech Barn;
4. AMR solo dopo pilot e dati ore/uomo;
5. tagliaerba solo dopo masterplan.

BOM-021 serve a:
- pallet e big bag;
- humus/compost/substrati;
- materiali sfusi;
- cantiere;
- manutenzione;
- logistica esterna.

Documenti:
- `08_MACCHINE_E_LOGISTICA/LIFTING_MULTIFUNCTION_ARCHITECTURE.md`;
- `08_MACCHINE_E_LOGISTICA/ACCESSO_IN_QUOTA_RAGNO_ARCHITETTURA.md`;
- `08_MACCHINE_E_LOGISTICA/RFQ_ACCESSO_IN_QUOTA_RAGNO.md`;
- `19_BOM_PRODOTTI_FORNITORI/MACCHINE_SOLLEVATORE_MULTIFUNZIONE.md`.

## 11. Stato punto 10 — Benessere, fattoria e servizi

**MODULI FUTURI / ROBOTICA GALLINE RIMOSSA DAL CORE.**

- BOM-023 rover pulizia galline: **ARCHIVIATA / NON ORDINABILE**;
- eventuale modulo galline futuro: layout semplice, superfici pulibili, nastro/raschiatore se utile;
- BOM-026 pergolato/vite/relax: futuro;
- BOM-027 fattoria didattica: futuro;
- BOM-028 spaccio: parte commerciale rilevante, prima versione semplice/semi-automatica.

Principio: nessun robot dedicato marginale precede acqua, manutenzione, mezzi, humus o produzione.

## 12. Stato punto 11 — Humus, vermicompost e cicli materia

**CORE STRUTTURATO / QUANTITÀ DA DATI REALI.**

Obiettivo:
- produrre humus/vermicompost internamente;
- valorizzare residui propri;
- acquistare e rilavorare materie con stato giuridico chiaro quando conveniente;
- ridurre dipendenza da prodotti finiti;
- usare il telescopico come mezzo centrale di movimentazione.

Documenti:
- `11_VERMICOMPOST_E_CICLI_MATERIA/README.md`;
- `11_VERMICOMPOST_E_CICLI_MATERIA/HUMUS_E_CICLI_MATERIA_ARCHITETTURA.md`.

Guardrail:
- nessun rifiuto di terzi senza corretta classificazione/autorizzazione;
- biosecurity;
- tracciabilità lotti;
- area separata dal food.

## 13. R&S trasversale — laser, vision e manutenzione robotica

Documento: `07_AUTOMAZIONE_DATI_AI/LASER_ROBOTICS_RND.md`. Stato: `R&S CANDIDATO / NON INCLUSO NEL CAPEX BASE`.

## 14. Stato punto 09 — Tech Barn e post-raccolta

**BOM-024 CELLE FRIGORIFERE + BOM-025 RACCOLTA/PACKAGING + BOM-029 CENTRO TRASFORMAZIONE CONTO TERZI SVILUPPATE / DOMANDA LOCALE, CARICHI, SKU, LAYOUT FOOD E RFQ BLOCCANTI.**

Configurazione base:
- CR-A COLD-LEAF ~1–3 °C, lattuga/baby leaf/spinacio;
- CR-B COOL-SENSITIVE ~10–12 °C, pomodoro/peperone/basilico con crop-card e short dwell;
- ~25 m²/cella di lavoro, totale freddo ~50 m² più zona servizio;
- forced-air precooling predisposto per CR-A;
- due sistemi frigoriferi indipendenti;
- confronto 1×100% vs circuiti modulari sulla cella critica;
- refrigerante naturale o GWP <150;
- monitoraggio locale + logger indipendente;
- pavimento strutturale verificato per BOM-021.

Riferimento di confronto:
- shell 4,74×4,74×2,54 m senza gruppo: €6.775,99 + IVA;
- R290 KDC800N: €5.399,99 net, max 50 m³ dichiarati, solo riferimento di confronto;
- R290 KDC600N: €4.899,99 net, max 35,1 m³ @32 °C / 21 m³ @43 °C;
- Testo 160 TH: €180 + IVA/cella.

Regola: dimensionamento da kg prodotto / temperatura ingresso / pull-down time, non da m³ stanza.

### BOM-025 — raccolta e packaging

Configurazione base:
- cassette 600×400 food-contact, quantità da `peak kg in loop / kg per crate × 1,3–1,5`;
- 6–12 low dollies + 2–4 raised come di lavoro range;
- 3 tavoli inox 1800×700 di lavoro;
- 2×30 kg + 1×300 kg scales;
- Zebra ZD421 TT Ethernet;
- tray sealer manuale opzionale;
- wash/spin leafy non configurazione base finché non viene scelta una linea ready-to-eat;
- label/traceability locale.

Riferimento di confronto progetto principale:
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

## 15. BOM-029 — centro trasformazione conto terzi

**SVILUPPATO COME UNITÀ OPERATIVA FUTURA / NON ANCORA NEL CAPEX DEL PROGETTO PRINCIPALE.**

Candidato di lavoro:
- scenario S2: 600–700 kg/h frutta in ingresso;
- succo ~420–525 L/h teorici secondo resa;
- 100P2/EBP500 classe;
- trattamento termico 500–750 L/h;
- bag-in-box configurazione base;
- jam/compote 100–200 L/batch classe;
- semi-CIP minimo;
- dirty -> process -> high-hygiene fill -> finished-goods zoning;
- batch genealogy e cost accounting sul server centrale.

Demand verifica bloccante:
- 30–50 interviste;
- >=3 anchor customers;
- >=150 t/year credible volume per S2 oppure right-size a S0/S1;
- price acceptance;
- minimum lot/setup fee;
- 3 RFQ comparabili.

Scale check:
- ERSA 2024: 68.735 t mele FVG;
- 150–300 t/year S2 = circa 0,22–0,44% del raccolto regionale; proxy di scala, NON prova della domanda Carnia.

Riferimento di confronto:
- BIB 3 L 100 pcs ~€114,75;
- BIB 5 L 100 pcs ~€127,05;
- jars 212 mL ~€688,52/1.728 pcs;
- jars 314 mL ~€696,72/1.344 pcs;
- ETI 10H ~€3.754,10;
- main process line equipment = RFQ OEM.

Contributi:
- SRD13 è pertinente come famiglia d'intervento;
- graduatoria FVG pubblicata 15/09/2026;
- nessun contributo inserito come certo.

Documenti:
- `09_TECH_BARN_E_POST_RACCOLTA/CENTRO_TRASFORMAZIONE_CONTO_TERZI.md`;
- `09_TECH_BARN_E_POST_RACCOLTA/RFQ_CENTRO_TRASFORMAZIONE_CONTO_TERZI.md`;
- `19_BOM_PRODOTTI_FORNITORI/TECH_BARN_TRASFORMAZIONE_CONTO_TERZI.md`;
- `22_FONTI_NORME_PREVENTIVI/TECH_BARN_TRASFORMAZIONE_CONTO_TERZI_SOURCES.md`;
- `15_MERCATO_E_VENDITE/DOMANDA_LOCALE_CENTRO_TRASFORMAZIONE.md`.

## 16. BOM-031 — sostenibilità personale e lancio operativo

**SVILUPPATA / ORGANICO E COSTO DA VALIDARE CON CPL UDINE, VOLUMI REALI E 90 GIORNI DI DATI.**

Di lavoro operating model:
- impianto 24/7 senza presenza umana 24/7;
- owner/operations-tech non come manodopera gratuita né reperibile permanente;
- 1 crop & production lead;
- 2 farm operations polyvalent come target L1;
- 0–3 OTD equivalenti per picchi;
- BOM-029 separa 2–3 operatori/process day quando attiva;
- ogni skill critica ha primary + backup + escalation esterna;
- ferie testate con almeno 10 giorni lavorativi consecutivi di assenza del primary;
- sick-day drill e owner-absence drill;
- P1/P2/P3 alerting per evitare rumore notturno;
- manutenzione L1 interna, L2 ibrida, L3 esterna;
- server centrale pianifica workload e non consente double-booking delle persone;
- ramp-up D-90 / 0–30 / 31–60 / 61–90 / 91–180 giorni;
- add-headcount trigger da workload, overtime, PM backlog, ferie e qualità, non da impressione.

Costo lavoro:
- minimi nazionali dal 01/06/2026: Area 1 €1.532,999/mese; Area 2 €1.398,093; Area 3 €1.042,434;
- aumento rinnovo: +3,4% dal 01/06/2026 e +1,7% dal 01/01/2027;
- INPS OTI generalità aziende agricole 2026: contributi a carico azienda 33,953% nella tabella ufficiale;
- floor illustrativo con 14 mensilità + contributi + TFR semplice: ~€30,3k Area 1, ~€27,7k Area 2, ~€20,6k Area 3;
- questi valori NON sono budget: il costo reale richiede CPL Udine/provincia, inquadramento, bilateralità, overtime/festivi, DPI, formazione, medical, payroll e altri elementi.

Labour-market guardrail:
- Excelsior FVG 2026 mostra difficoltà di reperimento elevate in diversi profili;
- hiring progetto principale anticipato e seasonal pool prequalificato;
- nessuna dipendenza da assunzioni last-minute.

Documenti:
- `17_SOSTENIBILITA_PERSONALE_E_LANCIO/README.md`;
- `14_ORGANIZZAZIONE_DEL_LAVORO/WORKFORCE_SKILL_MATRIX.md`;
- `17_SOSTENIBILITA_PERSONALE_E_LANCIO/LAUNCH_RAMP_UP_30_60_90_180.md`;
- `17_SOSTENIBILITA_PERSONALE_E_LANCIO/RFQ_SERVIZI_OPERATIVI_MANUTENZIONE.md`;
- `19_BOM_PRODOTTI_FORNITORI/ORGANIZZAZIONE_PERSONALE_LANCIO.md`;
- `22_FONTI_NORME_PREVENTIVI/ORGANIZZAZIONE_PERSONALE_LANCIO_SOURCES.md`.

## 17. Rischi, validazione e collaudo master — STRUTTURATO

Directory: `21_RISCHI_DECISIONI_OPEN_POINTS/`.

Punto unico di controllo:
- `README.md` — indice closure;
- `ANALISI_PROBLEMATICHE_RISCHI.md/.csv` — registro rischi e problematiche;
- `CRUSCOTTO_VALIDAZIONE_CHIUSURA.md/.csv` — stato delle chiusure;
- `COLLAUDO_MASTER_ACCETTAZIONE.md/.csv` — SAT integrato e messa in servizio;
- registri pilot, procurement e verifiche decisionali già presenti nella directory.

Regola:
`ipotesi -> dato reale -> RFQ -> contratto -> installazione -> prova -> PASS`.

## 18. Società, business plan e governance — STRUTTURATO

Directory: `16_SOCIETA_FINANZA_E_CONTRIBUTI/`.

Pacchetto:
- `BUSINESS_PLAN_MASTER.md` — business plan unico banca/bandi;
- `PIANO_AZIENDALE_BANDI.md` — base SRE01/SRD01;
- `SCELTA_FORMA_SOCIETARIA.md`;
- `STATUTO_TIPO_SOCIETA_AGRICOLA_SRL.md` — specifica da validare col notaio;
- `PATTI_SOCI_BOZZA.md`;
- `GOVERNANCE_E_DELEGHE.md`;
- `CHECKLIST_COSTITUZIONE_E_DATA_ROOM.md`;
- piano contributi/cassa iniziale.

Preferenza societaria di lavoro: **S.r.l. società agricola**, non ancora decisione notarile/fiscale definitiva.

Principio:
- un solo set di numeri per business plan, banca e bandi;
- lavoro dei soci valorizzato;
- oggetto societario agricolo da mantenere coerente;
- IAP, fiscalità, previdenza, quote e garanzie da chiudere prima dell'atto.

Fonti:
`22_FONTI_NORME_PREVENTIVI/SOCIETA_IAP_COSTITUZIONE_SOURCES.md`.

## 19. Avvio economico e messa a reddito — PRIORITÀ MASSIMA

L'avvio è ora trattato come sottoprogetto trasversale fra finanza, cantiere, persone, agronomia e mercato.

Assunzione di lavoro:
- il progetto parte solo dopo approvazione formale del pacchetto finanziario;
- SRD01 giovane: 60% di sostegno; anticipo massimo pari al 50% del sostegno = fino al 30% della spesa ammessa, soggetto a garanzia;
- quota di finanziamento di lavoro: circa 40% della spesa, da deliberare con Fondo/banca;
- obiettivo: circa 70% di liquidità iniziale sull'investimento quando entrambi gli strumenti sono perfezionati;
- SRE01 €70.000 separato: €49.000 acconto + €21.000 saldo se concesso e coerente con il PA di produzione primaria;
- il finanziamento fornisce liquidità ma resta debito;
- quota residua, IVA, costi non ammissibili e circolante vengono coperti separatamente;
- prima del CAPEX viene isolato un fondo operativo non utilizzabile dal cantiere;
- il 60% oggi può giustificare l'anticipo di infrastrutture certe e durevoli, non l'acquisto indiscriminato di tecnologia futura.

Sequenza:
`chiusura finanziaria -> terreno -> struttura serra -> primi comparti allestiti -> coltivazione -> commerciale -> primo raccolto/incasso -> spaccio -> comparti restanti -> regime`.

Strategia di accelerazione:
- struttura/involucro completi quando economicamente conveniente;
- allestimento produttivo per ondate;
- primi 2–3 comparti messi a reddito prima del completamento di tutto il progetto;
- commerciale pronto prima del primo raccolto;
- spaccio inizialmente semplice/semi-automatico se accelera i ricavi;
- automazioni non indispensabili non ritardano il primo incasso.

Quattro date obbligatorie:
- D1 prima spesa irreversibile;
- D2 primo comparto in produzione;
- D3 primo incasso;
- D4 pareggio di cassa operativo mensile.

Documenti:
- `16_SOCIETA_FINANZA_E_CONTRIBUTI/REGOLA_FINANZIARIA_AVVIO.md`;
- `16_SOCIETA_FINANZA_E_CONTRIBUTI/PIANO_AVVIO_SICURO_CONTRIBUTI.md`;
- `16_SOCIETA_FINANZA_E_CONTRIBUTI/MAPPA_CONTRIBUTI_E_CASSA_INIZIALE.md`;
- `18_CAPEX_OPEX_CASHFLOW/AVVIO_CASSA_E_RAMPA_PRODUTTIVA.md`;
- `18_CAPEX_OPEX_CASHFLOW/MATRICE_INVESTIRE_ORA_O_DOPO.md`;
- `18_CAPEX_OPEX_CASHFLOW/BUDGET_AVVIO_IDEALE.md` — target €950k CAPEX netto + €120k riserva operativa + linea IVA;
- `20_CANTIERE_E_CRONOPROGRAMMA/SEQUENZA_AVVIO_E_MESSA_A_REDDITO.md`;
- `20_CANTIERE_E_CRONOPROGRAMMA/PIANO_OPERATIVO_AVVIO/README.md` — piano master per settore, €950k CAPEX, P1 su 3 comparti, cronoprogramma 0–15 mesi e verifiche di uscita;
- `15_MERCATO_E_VENDITE/VENDITA_DIRETTA_E_CONSEGNE_PROGRAMMATE.md`.

## 20. Metodo BOM obbligatorio

Per ogni oggetto/sottosistema: funzione, requisiti, quantità, alternative, prezzo, IVA/trasporto, installazione, consumi, manutenzione, ricambi, vita utile, sicurezza, modalità di guasto, ripiego, contributi, dipendenze, espansione e stato decisionale.

## 21. Stato attuale dei grandi blocchi

La sequenza BOM core 001–034 è ora strutturata. Restano R&S robotica/laser separata e soprattutto le validazioni reali: lotto, crop card, profili di carico, DSO/RFQ, pilot e commissioning.

## 22. Sequenza BOM

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
- BOM-023 rover galline ARCHIVIATO;
- BOM-024 celle frigorifere;
- BOM-025 raccolta e packaging;
- BOM-026 pergolato, vite e area relax;
- BOM-027 fattoria didattica;
- BOM-028 spaccio automatico self-service 24/7;
- BOM-029 centro trasformazione conto terzi;
- BOM-030 server centrale di orchestrazione;
- BOM-031 sostenibilità personale e lancio operativo;
- BOM-032 trattamento e disinfezione acqua;
- BOM-033 drenaggio, raccolta e riuso acqua;
- **BOM-034 EMS, BESS e connessione elettrica**.

Artefatti closure avviati:
- `06_ENERGIA_ELETTRICA_FV/MASTER_LOAD_REGISTER.md`;
- `06_ENERGIA_ELETTRICA_FV/MASTER_LOAD_REGISTER.csv`;
- `06_ENERGIA_ELETTRICA_FV/LOAD_MEASUREMENT_AND_RFQ_PLAN.md`;
- `06_ENERGIA_ELETTRICA_FV/LOAD_DATA_CAPTURE_TEMPLATE.csv`.
- `21_RISCHI_DECISIONI_OPEN_POINTS/PROCUREMENT_CLOSURE_REGISTER.md`;
- `21_RISCHI_DECISIONI_OPEN_POINTS/PROCUREMENT_CLOSURE_REGISTER.csv`.
- `21_RISCHI_DECISIONI_OPEN_POINTS/MASTER_PILOT_REGISTER.md`;
- `21_RISCHI_DECISIONI_OPEN_POINTS/MASTER_PILOT_REGISTER.csv`;
- `21_RISCHI_DECISIONI_OPEN_POINTS/PILOT_RESULT_CAPTURE_TEMPLATE.csv`;
- `21_RISCHI_DECISIONI_OPEN_POINTS/PILOT_DECISION_RECORD_TEMPLATE.md`.
- `21_RISCHI_DECISIONI_OPEN_POINTS/MASTER_COMMISSIONING_ACCEPTANCE.md`;
- `21_RISCHI_DECISIONI_OPEN_POINTS/MASTER_COMMISSIONING_ACCEPTANCE.csv`.
- `18_CAPEX_OPEX_CASHFLOW/FINANCIAL_CLOSURE_CONTROL.md`;
- `18_CAPEX_OPEX_CASHFLOW/FINANCIAL_CLOSURE_CONTROL.csv`;
- `21_RISCHI_DECISIONI_OPEN_POINTS/MASTER_DECISION_GATE_REGISTER.md`;
- `21_RISCHI_DECISIONI_OPEN_POINTS/MASTER_DECISION_GATE_REGISTER.csv`.
- `21_RISCHI_DECISIONI_OPEN_POINTS/VALIDATION_CLOSURE_DASHBOARD.md`;
- `21_RISCHI_DECISIONI_OPEN_POINTS/VALIDATION_CLOSURE_DASHBOARD.csv`.
- `21_RISCHI_DECISIONI_OPEN_POINTS/ANALISI_PROBLEMATICHE_RISCHI.md`;
- `21_RISCHI_DECISIONI_OPEN_POINTS/ANALISI_PROBLEMATICHE_RISCHI.csv`.

### Prossima fase — validation / closure sprint

Master status: `21_RISCHI_DECISIONI_OPEN_POINTS/VALIDATION_CLOSURE_DASHBOARD.md`.

Non viene aperta una BOM-035 finché non emerge un sottosistema fisico realmente scoperto.

Priorità di chiusura:

1. lotto/masterplan/geotecnica e layout definitivo;
2. crop card e carichi termici/idrici/elettrici reali;
3. master load register + profilo 1–15 min e P0/P1 — **v0.1 strutturato + piano misure/RFQ e template dati pronti il 18/09/2026; resta raccolta dati reali**;
4. preventivo DSO/TICA, BT/MT, limiti import/export e protezioni — **pre-application package strutturato il 18/09/2026; pratica reale bloccata da lotto/DSO/POD e potenze finali**;
5. RFQ installati per i package ancora a prezzo `RFQ` — **registro procurement/closure strutturato il 18/09/2026; separati Q1–Q5, priorità e blocker per dominio**;
6. pilot obbligatori: AMR/robotica, smart retail, fattoria didattica, drenaggio-riuso e altri package marcati PILOT — **master pilot register + result/cost template + decision record strutturati il 18/09/2026; esecuzione fisica ancora da sito/vendor/produzione reale**;
7. commissioning e acceptance end-to-end — **master SAT, failure/degraded tests, 72 h endurance, punch-list e seasonal acceptance strutturati il 18/09/2026; esecuzione fisica da impianto reale**;
8. consolidamento CAPEX/OPEX/cashflow, rischi e decision gate — **financial closure control E0–E5 + master decision gates DG0–DG8 + analisi trasversale problematiche/rischi strutturati il 18/09/2026; actuals/RFQ/contratti/evidenze ancora da popolare**.

La numerazione riprende solo se la closure matrix evidenzia un nuovo package fisico/operativo non coperto.

## 23. Progetto R&S correlato UE — SEPARATO DAL PROGETTO PRINCIPALE

Directory: `RND_CORRELATO_EU/`.

**Stato:** `CORRELATO / SEPARATO DAL PROGETTO PRINCIPALE / PRE-CANDIDATURA R&S`.

Il progetto di lavoro **CTT-PAA — Piattaforma di Automazione Agricola Carnia TerraTech** sviluppa tecnologie potenzialmente replicabili per orchestrazione agricola, edge/PLC, robotica, visione artificiale, fusione sensoriale e pianificazione.

Regole di separazione:

- non sostituisce nessun blocco 00–22;
- non modifica la configurazione base CAPEX/OPEX agricola;
- nessun contributo R&S viene contato come fonte certa del progetto principale;
- Carnia TerraTech è laboratorio operativo reale, non il prodotto R&S;
- i sistemi vitali del progetto principale mantengono controllo locale e ripiego indipendenti;
- fallimento o ritardo di un dimostratore non deve bloccare produzione o safety;
- costi condivisi devono essere allocati e verificati sulla call specifica;
- IP, partner, TRL, deliverable e budget R&S vengono governati separatamente.

Documenti:

- `RND_CORRELATO_EU/README.md`;
- `RND_CORRELATO_EU/PIATTAFORMA_AUTOMAZIONE_AGRICOLA.md`;
- `RND_CORRELATO_EU/FINANZIAMENTI_E_CONFINI_DI_COSTO.md`.

Canali UE candidati da verificare topic per topic: Horizon Europe Cluster 4/6; EIC Accelerator solo in una fase successiva se tecnologia, TRL e scalabilità lo giustificano.

## 24. Piano extra agriturismo evolutivo — SEPARATO DAL PROGETTO PRINCIPALE

Directory: `EXTRA_AGRITURISMO_EVOLUTIVO/`.

**Stato:** `EXTRA / FONDI DEDICATI / NON BLOCCANTE`.

Sequenza:
- E0 predisposizioni minime di layout/utilities;
- E1 ristoro light a spuntini non cucinati;
- E2 esperienze/degustazioni/visite;
- E3 cucina agrituristica solo dopo analisi economica;
- E4 ospitalità solo dopo analisi economica.

Regole:
- budget e contributi separati dal progetto principale;
- nessun costo spostato artificialmente fra progetto principale ed extra;
- nessun doppio finanziamento;
- BOM-026/027/028 restano autonome e possono solo fornire interfacce condivise quando autorizzate;
- se il piano extra non parte, Carnia TerraTech resta invariata.

Fondo primario da monitorare: SRD03 FVG agriturismo. Altri canali: finanza regionale per multifunzionalità/diversificazione e GAL Open Leader per turismo esperienziale/ospitalità; misure ricettive solo nelle fasi future e se il beneficiario è ammissibile.

Documenti:
- `EXTRA_AGRITURISMO_EVOLUTIVO/README.md`;
- `EXTRA_AGRITURISMO_EVOLUTIVO/ARCHITETTURA_EVOLUTIVA.md`;
- `EXTRA_AGRITURISMO_EVOLUTIVO/PIANO_FINANZIAMENTI.md`;
- `EXTRA_AGRITURISMO_EVOLUTIVO/CAPEX_E_CONFINI.md`;
- `EXTRA_AGRITURISMO_EVOLUTIVO/VINCOLI_LEGALI_E_ALIMENTARI.md`.
