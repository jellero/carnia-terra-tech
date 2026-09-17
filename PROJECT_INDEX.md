# Carnia TerraTech — Project Index

**Ruolo:** indice operativo e mappa di copertura del progetto.  
**Aggiornato:** 17 settembre 2026.

## 1. Scopo

Il repository deve permettere di progettare l'azienda senza lasciare aree scoperte. Ogni decisione deve essere collegata a costi, manutenzione, sicurezza, dipendenze, crescita e qualità della vita.

## 2. Struttura target

- `00_VISIONE_E_PRINCIPI/` — missione, KPI, guardrail e decision gates;
- `01_MASTERPLAN_E_TERRENO/` — lotto, vincoli, accessi, drenaggi, espansioni;
- `02_AGRONOMIA/` — colture, calendari, rese, vite, luppolo, siepi, outdoor;
- `03_SERRA/` — struttura, comparti, coperture, aperture, schermi, HAF, fogging, supporti coltura, drenaggi, porte, recupero pioggia e cantiere;
- `04_ACQUA_E_FERTIRRIGAZIONE/` — fonte, accumulo, filtri, pompe, dosaggio, drenaggio;
- `05_TERMICO_E_CLIMA/` — carico termico, PDC, accumulo, distribuzione, boost, deumidificazione, emergenza;
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

## 4. Stato punto 01 — Terreno e masterplan

**Stato: RAFFINATO / IN ATTESA DI LOTTO REALE.**

Il metodo diventa `VALIDATO` solo con lotto reale che supera due diligence, masterplan test e costo totale del sito.

## 5. Stato punto 02 — Agronomia

**Stato: RAFFINATO / PORTAFOGLIO E METODO DEFINITI / DATI COLTURALI DA VALIDARE.**

Working portfolio: C1 pomodoro premium; C2 peperone; C3 lattuga; C4 lattuga/leaf flessibile; C5 baby leaf/rucola/spinacio; C6 basilico + vivaio + prove.

## 6. Stato punto 03 — Serra

**Stato: RAFFINATO COME ARCHITETTURA / BOM-001…008 STRUTTURATE / VALIDAZIONE BLOCCATA DA DATI REALI.**

Package sviluppati:

- BOM-001 HAF;
- BOM-002 schermi climatici;
- BOM-003 aperture/attuatori/reti;
- BOM-004 copertura/film/fissaggi;
- package struttura/fondazioni;
- BOM-005 fogging;
- BOM-006 supporti coltura + drenaggio;
- BOM-007 porte, compartimentazioni, gronde e pluviali;
- BOM-008 attrezzatura e consumabili montaggio.

Matrice: `03_SERRA/POINT_03_CLOSURE_MATRIX.md`.

## 7. Stato punto 05 — Termico e clima

**Stato: ARCHITETTURA STRUTTURATA / BOM-009…012 SVILUPPATE / VALIDAZIONE BLOCCATA DA LOTTO, CARICHI E RFQ.**

Documenti principali:

- `05_TERMICO_E_CLIMA/README.md`;
- `THERMAL_LOAD_METHOD.md`;
- `HYDRONIC_DISTRIBUTION.md` + RFQ;
- `THERMAL_STORAGE_PRIMARY.md` + RFQ;
- `HEAT_PUMP_CASCADE.md` + RFQ;
- `BOOST_DEHUMIDIFICATION_EMERGENCY.md` + RFQ;
- `POINT_05_CLOSURE_MATRIX.md`.

BOM:

- **BOM-009 — distribuzione idronica**: 6 zone indipendenti, near-crop, pompe/miscelazione/misure;
- **BOM-010 — accumulo/primario/HX**: 30 m³ working, predisposizione 40–50 m³, glicole confinato, HX e sicurezze;
- **BOM-011 — PDC modulari 3+1**: Kensol KHP-R290-22-3 candidato, A7/A2 verificati, sottozero/defrost da RFQ;
- **BOM-012 — boost/deumidificazione/emergenza**: aerotermi agricoli, D1 heat+vent, D2 recupero, D3 condensazione interna e failure modes.

### BOM-012 — elementi chiave

Aerotermo candidato Reventon FARMER HCF:

- IP54-EC ~4.800 m³/h, 430 W, benchmark €901 IVA 19% incl.;
- IP66 5.000 m³/h, 560 W, benchmark ~€822–943 IVA locale incl.;
- HCF IP66 a 50/40 °C e aria 20 °C: ~13,7 kW;
- HCF IP66 a 40/30 °C e aria 20 °C: ~7,0 kW.

Quindi la potenza nominale commerciale a 90/70 °C non viene usata per dimensionare il sistema a PDC.

Deumidificazione:

- D1 baseline: HAF + heat + vent su humidity ratio/dew point;
- D2: ventilazione meccanica con recupero, candidato AIRGAIA EXT'air/equivalente;
- D3: DryGair DG-3 (11 l/h, 2,3 kW) / DG-12 (43 l/h, 9,55 kW) come candidati da bilancio reale.

Gli aerotermi non sono una sorgente energetica di backup: servono accumulo caldo e circolazione. Backup lungo blackout resta collegato ai punti 06/12.

### Gate punto 05

Restano necessari:

- lotto/meteo/Tmin/umidità assoluta;
- carico termico C1–C6;
- climate recipes e VPD;
- prestazioni PDC A-7/A-10/A-15, W45 e defrost netto;
- P&ID/perdite di carico;
- terminali near-crop finali;
- volume tank/HX/glicole/espansione;
- quantità boost;
- bilancio kg/h di vapore e scelta D1/D2/D3;
- fonte di backup lunga durata;
- preventivi comparabili.

Matrice: `05_TERMICO_E_CLIMA/POINT_05_CLOSURE_MATRIX.md`.

## 8. R&D trasversale — laser, vision e manutenzione robotica

Documento: `07_AUTOMAZIONE_DATI_AI/LASER_ROBOTICS_RND.md`.

Stato: `R&D CANDIDATO / NON BASELINE CAPEX`.

Potatura robotica con vision + microforbice/cutter come baseline R&D; laser solo confinato; controllo insetti laser con classificazione `TARGET / UTILE-PROTETTO / INCERTO`, nessun tiro su incerto.

## 9. Modulo futuro — centro trasformazione conto terzi

Documento: `09_TECH_BARN_E_POST_RACCOLTA/CENTRO_TRASFORMAZIONE_CONTO_TERZI.md`.

Stato: `MODULO FUTURO AD ALTO POTENZIALE / DA BUSINESS CASE / NON ANCORA NEL CAPEX BASE`.

## 10. Metodo BOM obbligatorio

Per ogni oggetto/sottosistema: funzione, requisiti, quantità, alternative, prezzo, IVA/trasporto, installazione, consumi, manutenzione, ricambi, vita utile, sicurezza, failure mode, fallback, contributi, dipendenze, espansione e stato decisionale.

## 11. Stato attuale dei grandi blocchi

I file in `docs/` restano sorgenti durante la migrazione. Restano nel perimetro robot tagliaerba, automazione galline, fattoria didattica, spaccio 24/7, pergolati/vite/verde/relax, sostenibilità personale, R&D robotica/laser e centro trasformazione conto terzi.

## 12. Sequenza BOM

### Già strutturate

- Serra BOM-001…008;
- BOM-009 distribuzione termica;
- BOM-010 accumulo/primario/HX;
- BOM-011 PDC 3+1;
- **BOM-012 boost/deumidificazione/emergenza**.

### Prossimo package

**04_ACQUA_E_FERTIRRIGAZIONE — gocciolatori e linee irrigue:** ali gocciolanti/gocciolatori, capillari, picchetti, collettori, elettrovalvole, regolazione pressione, flush, settori, misure e ricambi.

### Coda successiva

1. gocciolatori e linee irrigue;
2. filtrazione acqua;
3. pompe principali irrigazione;
4. pompe dosatrici;
5. serbatoi fertilizzanti;
6. accumulo acqua 300 m³;
7. moduli FV e inverter;
8. AMR;
9. sollevatore/mezzo multifunzione;
10. robot tagliaerba;
11. sistema pulizia area galline;
12. celle frigorifere;
13. attrezzatura raccolta e packaging;
14. pergolato/vite/area relax;
15. fattoria didattica;
16. spaccio automatico 24/7;
17. centro trasformazione conto terzi: capacity model + BOM succo/confetture + CAPEX/OPEX + domanda locale.

La sequenza può cambiare quando una dipendenza tecnica rende necessario anticipare un blocco.
