# BOM-017 — Serbatoi fertilizzanti e contenimento

**Aggiornato:** 17 settembre 2026  
**Ambito:** stock A/B/acido, contenimento secondario, livelli, agitazione, travaso e sicurezza locale.  
**Stato:** `ARCHITETTURA DEFINITA / CANDIDATI E PREZZI REALI / VOLUMI DA RICETTE E SDS`.

## 1. Distinta principale

| Codice | Voce | Quantità working | Stato | Benchmark / nota |
|---|---|---:|---|---|
| TANK-A-001 | serbatoio stock A | 1 | DA DIMENSIONARE | scenario confronto 500 L |
| TANK-B-001 | serbatoio stock B | 1 | DA DIMENSIONARE | scenario confronto 500 L |
| TANK-AC-001 | serbatoio acido | 1 | DA DIMENSIONARE | scenario confronto 200 L |
| TANK-FUT-001 | predisposizione quarto serbatoio | 1 | PREDISPOSIZIONE | spazio/attacchi/I-O |
| TANK-CAN-500 | Pack Services PFF-CH0500 PE chimici | candidato | PREZZO TROVATO | €188,73 + IVA; 500 L |
| TANK-CAN-200 | Pack Services PFF-CH0200 PE chimici | candidato | PREZZO TROVATO | €131,94 + IVA; 200 L |
| TANK-ELBI-500 | ELBI CHL-500 | alternativa | PREZZO TROVATO | €219 IVA incl.; tabella resistenza chimica obbligatoria |
| TANK-DOSE-200 | stazione dosaggio PE 200 L con vasca | alternativa acido | PREZZO TROVATO | €202,77 + IVA |
| BUND-A-001 | bacino contenimento A | 1 | REQUISITO | capacità da calcolo/rischio |
| BUND-B-001 | bacino contenimento B | 1 | REQUISITO | o comune A+B se compatibili |
| BUND-AC-001 | bacino acido dedicato | 1 | BASELINE | non comune senza verifica |
| BUND-CAN-600 | DENIOS PE 600 L | benchmark | PREZZO TROVATO | €560 + IVA |
| BUND-CAN-500 | vasca PE 500 L con griglia | benchmark | PREZZO TROVATO | €641,72 IVA incl. Gaesco |
| LVL-A-001 | livello continuo A | 1 | REQUISITO | 4–20 mA/Modbus |
| LVL-B-001 | livello continuo B | 1 | REQUISITO | 4–20 mA/Modbus |
| LVL-AC-001 | livello continuo acido | 1 | REQUISITO | preferenza non-contatto |
| LVL-CAN-LAS | Novus TL400 | benchmark | PREZZO TROVATO | da €130 pubblicati; IVA da confermare |
| LVL-CAN-RAD | WIKA ILT-C01 radar | benchmark | PREZZO TROVATO | €390,09 + IVA |
| LLS-A-001 | low-low indipendente A | 1 | OBBLIGATORIO | blocco dosaggio |
| LLS-B-001 | low-low indipendente B | 1 | OBBLIGATORIO | blocco dosaggio |
| LLS-AC-001 | low-low indipendente acido | 1 | OBBLIGATORIO | blocco dosaggio |
| HLS-001 | high/high-high | 3 | REQUISITO | anti-trabocco/travaso |
| LLS-CAN | Elesa HFLT-E/HFL-E | benchmark | PREZZO TROVATO | da €39,18/€60,41 + IVA; compatibilità da verificare |
| AG-A-001 | agitatore o ricircolo A | 0–1 | CONDIZIONALE | dipende da solubilità/stabilità |
| AG-B-001 | agitatore o ricircolo B | 0–1 | CONDIZIONALE | dipende da solubilità/stabilità |
| AG-AC-001 | agitatore acido | 0 | NON BASELINE | solo se processo lo richiede |
| AG-CAN-500 | agitatore AISI316 0,37 kW per 500 L | benchmark alto | PREZZO TROVATO | €1.835 + IVA |
| FILL-A-001 | punto riempimento A | 1 | REQUISITO | dedicato/identificato |
| FILL-B-001 | punto riempimento B | 1 | REQUISITO | dedicato/identificato |
| FILL-AC-001 | punto riempimento acido | 1 | REQUISITO | attacco dedicato, procedura controllata |
| TRF-PMP-001 | pompa travaso | 0–1/famiglia | DA LOGISTICA | da contenitore fornitore/IBC |
| TRF-HOSE-001 | tubo travaso | per chimico | REQUISITO | materiale dedicato |
| TRF-DRIP-001 | vaschetta antigoccia | 3 | REQUISITO | punto connessione |
| VENT-A-001 | sfiato A | 1 | REQUISITO | dimensionato riempimento/prelievo |
| VENT-B-001 | sfiato B | 1 | REQUISITO | dimensionato riempimento/prelievo |
| VENT-AC-001 | sfiato acido | 1 | DA SDS | eventualmente convogliato/scrubber |
| VAL-OUT-001 | valvola fondo/uscita | 3 | REQUISITO | compatibilità chimica |
| BHD-001 | passaparete/bocchelli | da distinta | REQUISITO | compatibilità + tenuta |
| SAMPLE-001 | punto campione | 3 | PREFERENZA | sicuro e contenuto |
| LEAK-001 | sensore perdita bacino | 1 per zona | REQUISITO | interlock BOM-016 |
| FLOOR-001 | pavimento/rivestimento resistente | 1 area | DA PROGETTO | chimica reale |
| DRAIN-001 | drenaggio controllato bacino | per bacino | REQUISITO | normalmente chiuso |
| SIGN-001 | etichette e identificazione | 1 lotto | OBBLIGATORIO | A/B/acido, CLP dove applicabile |
| SPILL-001 | spill kit compatibile | 1+ | REQUISITO | materiale da SDS |
| PPE-001 | DPI specifici | 1 lotto | DA DVR/SDS | non forfait generico |
| EYE-001 | lavaocchi/doccia | 0–1 package | DA VALUTAZIONE RISCHIO | coordinare punto 12 |
| SP-001 | guarnizioni/passaparete | 1 lotto | RICAMBIO | materiali compatibili |
| SP-002 | valvole | 1 per standard usato | RICAMBIO | standardizzare |
| SP-003 | livellostato low-low | 1 | PREFERENZA | lead time basso |
| SP-004 | sensore continuo | 0–1 | DA SLA/TCO | dipende da lead time |
| COM-001 | leak test serbatoi/raccordi | 1 lotto | OBBLIGATORIO | con acqua/fluido sicuro dove possibile |
| COM-002 | test livelli/interlock | 1 lotto | OBBLIGATORIO | low-low/high-high |
| COM-003 | test contenimento | 1 lotto | OBBLIGATORIO | simulazione controllata |
| COM-004 | test travaso | 3 canali | OBBLIGATORIO | arresto high-level e procedura |
| DOC-001 | SDS/manuali/as-built | 1 lotto | OBBLIGATORIO | manutenzione e sicurezza |

## 2. Benchmark serbatoi

### Pack Services PFF-CH0500

- PE per chimici/alimenti;
- 500 L;
- circa Ø1000 × 705 mm;
- monolitico;
- stabilizzato UV;
- campo dichiarato -30…+50 °C;
- **€188,73 + IVA**;
- `PREZZO TROVATO`.

### Pack Services PFF-CH0200

- PE per chimici/alimenti;
- 200 L;
- circa Ø770 × 565 mm;
- **€131,94 + IVA**;
- `PREZZO TROVATO`.

### ELBI CHL-500

- 500 L PE;
- **€219 IVA inclusa**;
- il venditore richiede verifica della tabella di resistenza chimica ELBI;
- `PREZZO TROVATO`.

### Stazione dosaggio 200 L con vasca

Pack Services AGI/VA-200:

- 200 L;
- PE;
- supporto superiore per dosaggio/agitatore;
- vasca di contenimento integrata;
- **€202,77 + IVA**;
- `PREZZO TROVATO / ALTERNATIVA INTERESSANTE PER CANALE PICCOLO`.

## 3. Scenario hardware serbatoi — solo confronto

Scenario 500 L A + 500 L B + 200 L acido con PFF-CH:

- 2 × €188,73 = €377,46;
- 1 × €131,94 = €131,94;
- totale soli serbatoi = **€509,40 + IVA**.

Questo numero dimostra che **il costo del contenitore è una parte minoritaria del package**. Non include bacini, valvole, livelli, agitatori, travaso, pavimento, sicurezza, posa o commissioning.

## 4. Contenimento

Benchmark professionali:

### DENIOS PE 600 L

- capacità raccolta 600 L;
- per chimici non infiammabili compatibili, incluse soluzioni acide/alcaline secondo prodotto;
- **€560 + IVA**;
- `PREZZO TROVATO`.

### Gaesco PE 500 L con griglia

- capacità 500 L;
- **€641,72 IVA inclusa**;
- `PREZZO TROVATO`.

Per lo scenario 500/500/200, tre contenimenti singoli professionali possono costare più dei tre serbatoi stessi: è normale e va modellato nel CAPEX.

## 5. Livelli

### Novus TL400

- misura laser non a contatto;
- 4–20 mA;
- precisione dichiarata ±3 mm;
- **da €130** pubblicati;
- IVA da confermare;
- `PREZZO TROVATO / CANDIDATO ECONOMICO`.

### WIKA ILT-C01

- radar non a contatto;
- 4–20 mA;
- IP67;
- -40…100 °C processo dichiarato nella configurazione osservata;
- **€390,09 + IVA**;
- `PREZZO TROVATO / CANDIDATO ROBUSTO`.

### Low-low indipendente

Elesa HFLT-E / HFL-E:

- tecnopolimero;
- da **€39,18 / €60,41 + IVA**;
- versioni/materiali speciali su richiesta;
- `PREZZO TROVATO / COMPATIBILITÀ DA CONFERMARE`.

## 6. Agitazione

Benchmark professionale di classe alta:

- agitatore verticale AISI 316;
- fino a 500 L;
- 0,37 kW;
- 750 rpm nella configurazione osservata;
- **€1.835 + IVA**;
- packaging €80 + IVA;
- `PREZZO TROVATO / NON BASELINE`.

Il costo conferma che prima di comprare un agitatore conviene verificare se A/B richiedano davvero agitazione continua o se sia sufficiente ricircolo/preparazione batch.

## 7. Dimensionamento volume

Per ogni stock:

`Vop = L/giorno massimo × giorni autonomia`

Il volume nominale deve lasciare margine per:

- freeboard;
- fondo non pescabile;
- agitazione;
- densità/espansione;
- lotto di rifornimento.

Non fissare 500/500/200 L finché BOM-016 non ha ricette e consumi reali.

## 8. Contenimento — criterio di progetto

Baseline ingegneristica iniziale:

- bacino singolo >= volume nominale del serbatoio;
- acido in bacino separato;
- bacino comune A+B solo con compatibilità confermata.

Le regole italiane per rifiuti liquidi pericolosi usano in diversi casi criteri come 30%/1/3 del volume totale e comunque almeno il serbatoio maggiore, talvolta maggiorato del 10%. **Non vengono trattate come prescrizione automatica per i fertilizzanti:** il requisito applicabile va verificato con SDS, classificazione e autorità/tecnico competente.

## 9. Sicurezza e failure mode

Interlock minimi:

- low-low -> stop pompa dosatrice relativa;
- leak nel bacino -> stop canale e allarme;
- high-high durante travaso -> stop travaso;
- sensor fault -> blocco riempimento automatico/semiautomatico;
- agitatore -> inhibit sotto livello minimo;
- acido -> interlock dedicati e procedura doppio controllo.

Failure modes principali:

- fessura serbatoio;
- passaparete perde;
- bacino insufficiente/pieno;
- sensore livello guasto;
- travaso nel tank sbagliato;
- contaminazione A/B;
- acido su materiale incompatibile;
- precipitazione stock;
- sfiato ostruito;
- agitatore guasto;
- drenaggio bacino lasciato aperto.

## 10. Gate

1. consumo massimo A/B/acido;
2. autonomia target;
3. concentrazioni stock;
4. SDS;
5. densità e temperatura;
6. compatibilità completa;
7. volumi nominali;
8. agitazione/ricircolo;
9. layout e sfiati;
10. contenimento applicabile;
11. strategia travaso;
12. livelli e interlock;
13. RFQ;
14. commissioning.
