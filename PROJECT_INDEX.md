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

**Stato: ARCHITETTURA DI BASE DEFINITA / BOM-009 DISTRIBUZIONE SVILUPPATA / CARICHI E GENERAZIONE DA VALIDARE.**

Nuovi documenti:

- `05_TERMICO_E_CLIMA/README.md`;
- `05_TERMICO_E_CLIMA/THERMAL_LOAD_METHOD.md`;
- `05_TERMICO_E_CLIMA/HYDRONIC_DISTRIBUTION.md`;
- `05_TERMICO_E_CLIMA/RFQ_HYDRONIC_DISTRIBUTION.md`;
- `19_BOM_PRODOTTI_FORNITORI/TERMICO_DISTRIBUZIONE_IDRONICA.md`;
- `22_FONTI_NORME_PREVENTIVI/TERMICO_DISTRIBUZIONE_SOURCES.md`.

### BOM-009 — distribuzione idronica

Architettura: accumulo -> collettore secondario -> 6 circuiti indipendenti -> terminali near-crop.

Per zona sono previsti come requisiti:

- isolamento manuale;
- pompa modulante;
- miscelazione motorizzata dove richiesta;
- T mandata/ritorno;
- misura/bilanciamento portata;
- scarico/sfiato/manutenzione;
- comando e fallback locale.

Candidati/benchmark registrati:

- Elydan TUBSER Ø25 e Palaplast GEOPAL Ø25/28 come tubi specifici greenhouse, `DA PREVENTIVO`;
- IVAR FF-Therm PE-Xa Ø25×2,3 EVOH: €5,81/m listino, ~€4,23/m benchmark retail UE, idoneità alla posa esposta da confermare;
- Grundfos ALPHA2 25-60 da €249 IVA incl. e MAGNA1 25-60 €426,63 IVA incl. come classi di pompa da verificare sulla curva reale;
- ESBE VRG131 DN25 ~€64,15 + ARA661 ~€148,35 IVA incl. come benchmark miscelazione;
- Caleffi 132602 1", 10–40 l/min ~€102,28 IVA incl. come benchmark bilanciamento/lettura portata.

Il working storico 2.700–3.000 m di terminali non è una quantità d'ordine. Con il solo PE-Xa benchmark equivale a circa €11.421–17.430 di solo tubo, a seconda del prezzo utilizzato.

Pompe e diametri saranno dimensionati da potenza, ΔT e perdite di carico; la relazione operativa registrata è `Q[m³/h] ≈ P[kW]/(1,163×ΔT[K])`.

### Dipendenze punto 05

Servono ancora:

- carico termico per C1–C6 e scenari produzione/economia/sopravvivenza;
- temperature di progetto acqua;
- perdite di carico e P&ID;
- materiale near-crop definitivo;
- accumulo termico e primario/scambiatore;
- verifica PDC alle condizioni fredde reali;
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
- **BOM-009 distribuzione termica idronica**.

### Prossimo package

**BOM-010 — accumulo termico + primario PDC + scambiatore:** serbatoi 30 m³ con espansione 40–50 m³, stratificazione, scambiatore a piastre, pompe primarie, glicole confinato, valvole, sicurezza, isolamento, sensori, manutenzione e costi.

### Coda successiva

1. BOM-010 accumulo termico + primario/scambiatore;
2. PDC modulari 3+1 e prestazioni a freddo;
3. boost/deumidificazione/emergenza;
4. gocciolatori e linee irrigue;
5. filtrazione acqua;
6. pompe principali irrigazione;
7. pompe dosatrici;
8. serbatoi fertilizzanti;
9. accumulo acqua 300 m³;
10. moduli FV e inverter;
11. AMR;
12. sollevatore/mezzo multifunzione;
13. robot tagliaerba;
14. sistema pulizia area galline;
15. celle frigorifere;
16. attrezzatura raccolta e packaging;
17. pergolato/vite/area relax;
18. fattoria didattica;
19. spaccio automatico 24/7;
20. centro trasformazione conto terzi: capacity model + BOM succo/confetture + CAPEX/OPEX + domanda locale.

La sequenza può cambiare quando una dipendenza tecnica rende necessario anticipare un blocco.
