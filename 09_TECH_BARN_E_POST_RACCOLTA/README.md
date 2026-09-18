# Carnia TerraTech — Punto 09: Tech Barn e post-raccolta

**Aggiornato:** 18 settembre 2026  
**Stato:** ARCHITETTURA CELLE + PACKAGING + BOM-029 TRASFORMAZIONE CONTO TERZI STRUTTURATE / BOM-024…025 + BOM-029 SVILUPPATE / DOMANDA LOCALE, CARICHI, SKU E RFQ BLOCCANTI.

## 1. Ruolo del blocco

Il Tech Barn deve ricevere, raffreddare, conservare, preparare e spedire il prodotto senza creare un collo di bottiglia fra serra e vendita.

Working allocation già usata nel progetto: circa 450 m² complessivi, con circa 50–60 m² destinati alla refrigerazione.

## 2. Due celle, non una

La baseline è composta da due ambienti indipendenti:

- **CR-A COLD-LEAF:** working 1–3 °C, regolabile circa 0–5 °C; lattuga, baby leaf, spinacio e prodotti compatibili; RH elevata, target da crop card;
- **CR-B COOL-SENSITIVE:** working 10–12 °C, regolabile circa 7–15 °C; pomodoro, peperone e basilico con tempi di permanenza specifici.

Una sola temperatura non è tecnicamente corretta per il portafoglio Carnia. Basilico è chilling-sensitive sotto 10 °C; lattuga richiede vicino a 0 °C; peperone ha optimum intorno a 7,5 °C; pomodoro maturo lavora tipicamente nell'ordine di 10–12,5 °C.

Le crop card finali stabiliranno setpoint e durata massima per prodotto. CR-B è un compromesso operativo per short dwell e direct sales, non un'ipotetica temperatura universale.

## 3. Working geometry

Scenario di confronto, non ordine:

- circa 25 m² netti/cella;
- altezza interna circa 2,5–2,7 m;
- circa 60–70 m³/cella;
- zona filtro/servizio davanti alle porte;
- porte utili da pallet/cassette e mezzi reali;
- nessuna rampa interna se il pavimento può essere integrato nella soletta del Tech Barn.

La dimensione finale segue kg/giorno, numero cassette/pallet, giorni massimi di permanenza, corridoi e airflow clearances.

## 4. Regola di dimensionamento frigorifero

Non dimensionare il gruppo sui soli m³ di cella.

Carico:

Qtot = trasmissioni + infiltrazioni + product pull-down + respirazione + persone/luci/fan + sbrinamento + margine.

Esempio puramente ingegneristico: 1.000 kg di prodotto con cp ~3,8 kJ/kgK raffreddati da 25 a 2 °C in 6 h richiedono circa **4,0 kW di solo carico sensibile prodotto**, prima delle dispersioni e della respirazione.

Per 500 kg, stesso profilo, circa 2,0 kW.

Questo è il motivo per cui un monoblocco dichiarato "per 50 m³" non viene automaticamente accettato.

## 5. Pre-raffreddamento

Per C3–C5 il room cooling può essere troppo lento. Il progetto prevede quindi:

- predisposizione a **forced-air precooling**;
- parete/tunnel mobile o posizione pallet/cassette compatibile;
- ventilatori EC;
- controllo Δp/airflow;
- nessuna aspirazione che disidrati inutilmente il prodotto;
- hydrocooling/vacuum cooling solo dopo business case, igiene acqua e volumi reali.

Il precooler è opzionale BOM-024, ma la sua predisposizione fisica è baseline.

## 6. Involucro

Working:

- pannello PIR/PUR 100 mm come classe di confronto;
- giunti igienici, sigillati e lavabili;
- soffitto coibentato;
- pavimento coibentato strutturale flush, preferibilmente integrato nel cantiere;
- finitura antiscivolo e lavabile;
- sgusce/coving;
- porta isolata con apertura interna di emergenza;
- door contact;
- protezioni antiurto.

Se entra lo stoccatore BOM-021, il pavimento deve essere verificato su carichi ruota reali. Non assumere che il pavimento modulare standard di una cella commerciale sopporti il carrello.

## 7. Refrigerazione

Scenari RFQ:

### R1 — singolo sistema indipendente per cella

Remote/split o monoblocco professionale dimensionato sul carico reale. CAPEX minore, ma nessuna ridondanza interna.

### R2 — due circuiti modulari per CR-A

2× unità parzializzate per la cella più critica. Obiettivo: mantenimento degradato dopo guasto di un circuito, non doppia capacità non controllata.

### R3 — due circuiti modulari su entrambe le celle

Massima continuità, più CAPEX e manutenzione. Da TCO.

Refrigerante: preferenza R290/naturale oppure soluzione A2L/naturale con GWP <150 già compatibile con il quadro F-gas futuro.

## 8. Umidità e airflow

- evaporatori selezionati a basso TD dove necessario;
- ventilatori EC/modulabili;
- evitare getti diretti sul prodotto;
- RH misurata indipendentemente;
- eventuale umidificazione soltanto dopo verifica acqua/HACCP/condensa;
- niente fogging improvvisato nelle celle;
- controllare dew point, condensa e muffe.

## 9. Monitoraggio

Per ogni cella:

- controller frigorifero locale;
- almeno 2–3 punti temperatura aria in commissioning;
- sonda evaporatore;
- door contact;
- RH;
- logger indipendente;
- allarme high/low temperature;
- allarme porta aperta;
- fault compressore/fan/defrost;
- energy meter;
- storico locale + supervisione edge;
- continuità controller/logger/rete dal BESS aziendale 30 kW; nessuna UPS locale baseline.

Il frigorifero continua a funzionare senza cloud.

## 10. Emergenza

Il backup elettrico dei compressori e dei controlli è a carico del BESS/EMS aziendale; nessuna UPS locale baseline.

Procedure:

- allarme immediato;
- verifica tempo residuo termico;
- CR-B meccanicamente capace di scendere temporaneamente più in basso se configurazione e prodotto lo permettono;
- trasferimento prodotto secondo priorità;
- disponibilità di servizio frigorista e ricambi critici;
- piano B con cella/container refrigerato a noleggio;
- registrazione dell'escursione di temperatura e decisione HACCP.

## 11. Raccolta e packaging — BOM-025

Architettura:

- standard logistico 600×400;
- cassette food-contact dimensionate da peak product in loop, non da numero fisso;
- 3 tavoli inox working;
- 2× bilancia 30 kg + 1× bilico 300 kg working;
- Zebra ZD421 TT Ethernet class;
- termosigillatrice manuale solo se richiesta dagli SKU retail;
- washed/ready-to-eat leafy come modulo futuro, non baseline;
- traceability harvest -> cold room -> pack -> shipment;
- label media testate anche con condensa CR-A.

Documenti:
- `HARVEST_PACKAGING_ARCHITECTURE.md`;
- `RFQ_HARVEST_PACKAGING.md`;
- `19_BOM_PRODOTTI_FORNITORI/TECH_BARN_RACCOLTA_PACKAGING.md` — BOM-025;
- `22_FONTI_NORME_PREVENTIVI/TECH_BARN_RACCOLTA_PACKAGING_SOURCES.md`.

## 12. Centro trasformazione conto terzi — BOM-029

**Sviluppato come business unit futura, non ancora CAPEX core.**

Working candidate:
- S2: 600–700 kg/h raw fruit;
- juice ~420–525 L/h teorici secondo resa;
- press 100P2/EBP500 class;
- thermal 500–750 L/h;
- bag-in-box baseline;
- jam/compote 100–200 L/batch class;
- semi-CIP minimo;
- tracciabilità sul server centrale;
- building/utility layout dirty -> process -> high-hygiene fill -> finished goods.

Demand gate:
- 30–50 interviste;
- >=3 anchor customers;
- >=150 t/year credible aggregate volume per S2;
- willingness-to-pay validata;
- 3 RFQ comparabili.

Benchmark:
- FVG apples 2024 ~68.735 t regional proxy, non domanda Carnia;
- BIB 3 L 100 pcs ~€114,75;
- BIB 5 L 100 pcs ~€127,05;
- ETI 10H labeler ~€3.754,10;
- high-Brix refractometer ~€21,31;
- main process equipment = RFQ OEM.

Documenti:
- `CENTRO_TRASFORMAZIONE_CONTO_TERZI.md`;
- `RFQ_CENTRO_TRASFORMAZIONE_CONTO_TERZI.md`;
- `19_BOM_PRODOTTI_FORNITORI/TECH_BARN_TRASFORMAZIONE_CONTO_TERZI.md`;
- `22_FONTI_NORME_PREVENTIVI/TECH_BARN_TRASFORMAZIONE_CONTO_TERZI_SOURCES.md`;
- `15_MERCATO_E_VENDITE/DOMANDA_LOCALE_CENTRO_TRASFORMAZIONE.md`.

## 13. Package

- COLD_ROOMS_ARCHITECTURE.md;
- RFQ_COLD_ROOMS.md;
- HARVEST_PACKAGING_ARCHITECTURE.md;
- RFQ_HARVEST_PACKAGING.md;
- CENTRO_TRASFORMAZIONE_CONTO_TERZI.md;
- RFQ_CENTRO_TRASFORMAZIONE_CONTO_TERZI.md;
- BOM-024, BOM-025 e BOM-029 in `19_BOM_PRODOTTI_FORNITORI/`;
- fonti dedicate in `22_FONTI_NORME_PREVENTIVI/`.
