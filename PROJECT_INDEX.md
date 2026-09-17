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
- `03_SERRA/` — struttura, comparti, coperture, aperture, schermi, HAF, fogging, supporti coltura, drenaggi, porte, recupero pioggia e cantiere;
- `04_ACQUA_E_FERTIRRIGAZIONE/` — fonte, accumulo, filtri, pompe, dosaggio, drenaggio;
- `05_TERMICO_E_CLIMA/` — carico termico, PDC, accumulo, distribuzione, deumidificazione, emergenza;
- `06_ENERGIA_ELETTRICA_FV/` — FV, inverter, rete, UPS, generatore, EMS;
- `07_AUTOMAZIONE_DATI_AI/` — PLC, I/O, sensori, rete, edge, vision, cybersecurity e R&D robotica/laser;
- `08_MACCHINE_E_LOGISTICA/` — AMR, sollevatore, piattaforme, raccolta, carrelli;
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

**Stato: RAFFINATO / BASE DI GOVERNO DEL PROGETTO.**

Documenti: `PROJECT_CHARTER.md`, `KPI_GUARDRAILS.md`, `DECISION_GATES.md` in `00_VISIONE_E_PRINCIPI/`.

## 4. Stato punto 01 — Terreno e masterplan

**Stato: RAFFINATO / IN ATTESA DI LOTTO REALE.**

Il metodo è chiuso; diventa `VALIDATO` solo con lotto reale che supera due diligence, masterplan test e costo totale del sito.

## 5. Stato punto 02 — Agronomia

**Stato: RAFFINATO / PORTAFOGLIO E METODO DEFINITI / DATI COLTURALI DA VALIDARE.**

Portafoglio working: C1 pomodoro premium; C2 peperone; C3 lattuga; C4 lattuga/leaf flessibile; C5 baby leaf/rucola/spinacio; C6 basilico + vivaio + prove.

Il punto diventa `VALIDATO` coltura per coltura con sito, sistema, cultivar, resa vendibile, ore uomo, mercato, prezzo e marginalità.

## 6. Stato punto 03 — Serra

**Stato: RAFFINATO COME ARCHITETTURA / BOM-001…008 STRUTTURATE / VALIDAZIONE BLOCCATA DA DATI REALI.**

Package/BOM sviluppati:

- BOM-001 HAF;
- BOM-002 schermi climatici;
- BOM-003 aperture/attuatori/reti;
- BOM-004 copertura/film/fissaggi;
- package struttura/fondazioni;
- BOM-005 fogging;
- BOM-006 supporti coltura + drenaggio;
- BOM-007 porte, compartimentazioni, gronde e pluviali;
- BOM-008 attrezzatura e consumabili montaggio.

Matrice di chiusura: `03_SERRA/POINT_03_CLOSURE_MATRIX.md`.

Il punto 03 è sufficientemente coperto per proseguire, ma non è progetto esecutivo. Restano dipendenze da lotto, geotecnica, crop card, layout, analisi acqua, calcoli e preventivi.

## 7. Stato punto 05 — Termico e clima

**Stato: ARCHITETTURA DI BASE DEFINITA / BOM-009 E BOM-010 SVILUPPATE / CARICHI E PDC A FREDDO DA VALIDARE.**

Documenti principali:

- `05_TERMICO_E_CLIMA/README.md`;
- `05_TERMICO_E_CLIMA/THERMAL_LOAD_METHOD.md`;
- `05_TERMICO_E_CLIMA/HYDRONIC_DISTRIBUTION.md`;
- `05_TERMICO_E_CLIMA/RFQ_HYDRONIC_DISTRIBUTION.md`;
- `05_TERMICO_E_CLIMA/THERMAL_STORAGE_PRIMARY.md`;
- `05_TERMICO_E_CLIMA/RFQ_THERMAL_STORAGE_PRIMARY.md`;
- `19_BOM_PRODOTTI_FORNITORI/TERMICO_DISTRIBUZIONE_IDRONICA.md`;
- `19_BOM_PRODOTTI_FORNITORI/TERMICO_ACCUMULO_PRIMARIO.md`;
- `22_FONTI_NORME_PREVENTIVI/TERMICO_DISTRIBUZIONE_SOURCES.md`;
- `22_FONTI_NORME_PREVENTIVI/TERMICO_ACCUMULO_PRIMARIO_SOURCES.md`.

### BOM-009 — distribuzione idronica

Architettura: accumulo -> collettore secondario -> 6 circuiti indipendenti -> terminali near-crop.

Per zona: isolamento, pompa modulante, eventuale miscelazione, T mandata/ritorno, misura/bilanciamento portata, scarico/sfiato e fallback locale.

Candidati/benchmark registrati:

- Elydan TUBSER Ø25 e Palaplast GEOPAL Ø25/28 come tubi greenhouse, `DA PREVENTIVO`;
- IVAR FF-Therm PE-Xa Ø25×2,3 EVOH: €5,81/m listino, ~€4,23/m benchmark retail UE, idoneità alla posa esposta da confermare;
- Grundfos ALPHA2 25-60 da €249 IVA incl. e MAGNA1 25-60 €426,63 IVA incl. come classi da verificare sulla curva reale;
- ESBE VRG131 DN25 ~€64,15 + ARA661 ~€148,35 IVA incl.;
- Caleffi 132602 1", 10–40 l/min ~€102,28 IVA incl.

Il working 2.700–3.000 m di terminali non è quantità d'ordine. Con il solo PE-Xa benchmark equivale a circa €11.421–17.430 di solo tubo.

### BOM-010 — accumulo + primario + scambiatore

Working architecture:

`3×22 kW PDC -> primario corto protetto -> HX -> 30 m³ acqua tecnica -> BOM-009`, con predisposizione quarta PDC e 40–50 m³.

Energia teorica acqua:

- 30 m³: ~349 kWh/10 K; ~698 kWh/20 K; ~1.047 kWh/30 K;
- 40 m³: ~465 / 930 / 1.395 kWh;
- 50 m³: ~581 / 1.163 / 1.744 kWh.

Scenari serbatoi da RFQ:

- T1 6×5 m³ professionali;
- T2 3×10 m³ custom/industriali;
- T3 1×30 m³ custom, solo se TCO/affidabilità giustificano il single point of failure.

Candidato professionale pubblico: Cordivari PUFFER COMPACT 5000, ~5.042 l, Pmax 3 bar, Tmax 99 °C, prezzo da preventivo.

Benchmark da non confondere con puffer: serbatoi PE acqua ALTA 10/15/20 m³ a €1.840/2.940/4.740 + IVA in promo settembre 2026; non sono automaticamente idonei a pressione, temperatura, isolamento e stratificazione termica.

Scambiatori benchmark Sunerg listino 2025/2: 60 kW saldobrasato €932; 100 kW €1.252; 100 kW inox a piastre €3.013. Quotare 1×100 kW e 2×100 kW isolabili, oltre a eventuale ridondanza parziale.

Glicole propilenico confinato al primario: benchmark 25 kg ~€122–185. Il vaso espansione viene calcolato; Caleffi 556500 500 l (~€1.165,20) è solo un riferimento di classe, non una taglia scelta.

Open point critico: verificare circolatore integrato e prevalenza residua della Kensol KHP-R290-22-3 prima di aggiungere pompe primarie esterne.

### Dipendenze punto 05

Servono ancora:

- carico termico C1–C6 e scenari produzione/economia/sopravvivenza;
- temperature acqua;
- prestazioni PDC a freddo e alle temperature di mandata reali;
- perdite di carico/P&ID;
- materiale near-crop definitivo;
- volume accumulo 30/40/50 m³ e architettura T1/T2/T3;
- numero/taglia HX;
- concentrazione glicole;
- espansione/sicurezze;
- boost/deumidificazione/emergenza;
- preventivi professionali.

## 8. R&D trasversale — laser, vision e manutenzione robotica

Documento: `07_AUTOMAZIONE_DATI_AI/LASER_ROBOTICS_RND.md`.

Stato: `R&D CANDIDATO / NON BASELINE CAPEX`.

Linee correnti: potatura robotica con visione e microforbice/cutter come baseline R&D; laser solo confinato; controllo insetti laser solo con classificazione `TARGET / UTILE-PROTETTO / INCERTO` e nessuna attivazione su incerto.

## 9. Modulo futuro — centro trasformazione conto terzi

Documento: `09_TECH_BARN_E_POST_RACCOLTA/CENTRO_TRASFORMAZIONE_CONTO_TERZI.md`.

Stato: `MODULO FUTURO AD ALTO POTENZIALE / DA BUSINESS CASE / NON ANCORA NEL CAPEX BASE`.

Perimetro: mele, pere, piccoli frutti, succhi, puree, confetture/composte; lavoro proprio e conto terzi; tariffa, compensazione in prodotto, acquisto materia prima o modello ibrido. Il masterplan deve predisporre spazio e utilities senza obbligare l'acquisto iniziale.

## 10. Metodo BOM obbligatorio

Per ogni oggetto o sottosistema si analizzano funzione, requisiti, quantità, alternative, prezzo, IVA/trasporto, installazione, consumi, manutenzione, ricambi, vita utile, sicurezza, failure mode, fallback, contributi, dipendenze, espansione e stato decisionale.

## 11. Stato attuale dei grandi blocchi

I file in `docs/` restano sorgenti durante la migrazione. Sono nel perimetro robot tagliaerba, automazione area galline, fattoria didattica, spaccio 24/7, pergolati/vite/verde/relax, sostenibilità personale, R&D robotica/laser e centro trasformazione conto terzi.

## 12. Sequenza BOM

### Già strutturate

- Serra BOM-001…008;
- BOM-009 distribuzione termica idronica;
- **BOM-010 accumulo termico + primario/scambiatore**.

### Prossimo package

**PDC modulari 3+1 e prestazioni a freddo:** curva capacità/COP a temperature esterne reali, W35/W45, portata minima, circolatore integrato, sbrinamento, potenza elettrica, acustica, distanze/installazione, garanzia e ridondanza.

### Coda successiva

1. PDC modulari 3+1 e prestazioni a freddo;
2. boost/deumidificazione/emergenza;
3. gocciolatori e linee irrigue;
4. filtrazione acqua;
5. pompe principali irrigazione;
6. pompe dosatrici;
7. serbatoi fertilizzanti;
8. accumulo acqua 300 m³;
9. moduli FV e inverter;
10. AMR;
11. sollevatore/mezzo multifunzione;
12. robot tagliaerba;
13. sistema pulizia area galline;
14. celle frigorifere;
15. attrezzatura raccolta e packaging;
16. pergolato/vite/area relax;
17. fattoria didattica;
18. spaccio automatico 24/7;
19. centro trasformazione conto terzi: capacity model + BOM succo/confetture + CAPEX/OPEX + domanda locale.

La sequenza può cambiare quando una dipendenza tecnica rende necessario anticipare un blocco.
