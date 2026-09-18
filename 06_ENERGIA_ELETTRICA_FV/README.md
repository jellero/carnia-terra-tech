# Carnia TerraTech — Punto 06: Energia elettrica e fotovoltaico

**Aggiornato:** 17 settembre 2026  
**Stato:** `ARCHITETTURA FV IN SVILUPPO / BOM-019 MODULI+INVERTER SVILUPPATA / BESS BACKUP 30 kW CONSOLIDATO / kWh, AUTONOMIA, ISLANDING, CONNESSIONE ED EMS DA SVILUPPARE / NESSUNA UPS LOCALE BASELINE`.

## 1. Obiettivo

Produrre energia elettrica con priorità all'autoconsumo delle utenze agricole, senza sottrarre luce alle colture principali e mantenendo controllo locale, manutenibilità e possibilità di espansione.

Baseline working:

- **120 kWp DC iniziali**;
- predisposizione **150–180 kWp**;
- niente moduli opachi sopra le aree produttive principali della serra come baseline;
- integrazione con PDC/accumulo termico, pompe, celle fredde, automazione e futuri carichi flessibili;
- backup elettrico centralizzato tramite BESS da **30 kW di potenza**; capacità utile in kWh, autonomia, potenza di picco, tempo di trasferimento e islanding da chiudere; nessuna UPS locale baseline;
- EMS locale, cloud non vitale.

## 2. Candidato moduli 2026

Working candidate: **Trina Solar Vertex S+ TSM-470NEG9R.28**.

Dati:

- 470 Wp;
- N-type i-TOPCon, doppio vetro;
- 23,5% efficienza;
- 1762 × 1134 × 30 mm;
- 21 kg;
- Vmp 46,1 V, Imp 10,20 A;
- Voc 54,6 V, Isc 10,89 A;
- coefficiente Voc -0,24%/°C;
- 1500 Vdc max modulo;
- 25 anni garanzia prodotto / 30 anni potenza nella documentazione 2026.

Working layout elettrico nominale:

- **256 moduli × 470 W = 120,32 kWp**;
- sola area moduli ~**511,5 m²**;
- massa soli moduli ~**5,38 t**;
- area lorda impianto da masterplan maggiore: spazi, inclinazione, ombre, camminamenti e struttura da layout reale.

Non congelare numero moduli/stringa finché non sono noti temperatura minima di progetto, inverter, orientamenti e ombre.

## 3. Architetture inverter da confrontare

### I1 — 2 × 50 kW AC

- 100 kW AC totali;
- 120,32 kWp DC => DC/AC ~1,20;
- buona modularità e produzione degradata al 50% circa con un inverter fuori servizio;
- espansione 150–180 kWp da verificare: oversizing ammesso dal modello reale oppure terzo inverter/predisposizione.

Candidati: Sungrow SG50CX-P2, Huawei SUN2000-50KTL-M3, SMA Sunny Tripower X 50.

### I2 — 2 × 60 kW AC

- 120 kW AC totali;
- DC/AC iniziale ~1,00;
- candidato SMA Sunny Tripower X 60;
- il produttore dichiara fino a 90 kWp DC per unità e rapporto DC/AC fino al 150%, quindi la famiglia consente teoricamente 180 kWp DC con 2×60 kW; stringhe, correnti e connessione devono comunque essere verificate.

### I3 — terzo inverter predisposto

Spazio, AC board, rete dati e canalizzazioni predisposti per un terzo inverter se la soluzione 2×50 kW viene espansa.

## 4. Layout fisico

Priorità da confrontare:

1. tetto Tech Barn/edifici tecnici, dopo verifica strutturale e antincendio;
2. carport/parcheggi e coperture di servizio;
3. campo a terra in area non produttiva, se urbanisticamente e agronomicamente accettabile;
4. future strutture dual-use solo se non danneggiano colture, accessi o paesaggio.

La superficie del Tech Barn (~450 m² di footprint working) non va assunta sufficiente: 120,32 kWp con il candidato 470 W richiedono già ~511,5 m² di sola superficie modulo.

## 5. Connessione e norme

Il livello BT/MT non viene deciso dalla potenza FV a tavolino: dipende dal preventivo e dalle prescrizioni del DSO.

Riferimenti correnti:

- CEI 0-21:2026-07 per connessioni BT;
- CEI 0-16:2026-07 per connessioni MT/AT;
- TICA ARERA per la connessione degli impianti di produzione;
- se installato su attività soggetta a prevenzione incendi, Linee Guida VVF fotovoltaico aggiornate con Nota 01/09/2025 n. 14030 e chiarimenti successivi.

Per impianti FV/eolici >=100 kW connessi in MT verificare anche gli obblighi correnti derivanti dall'Allegato A.72/CEI 0-16 e controllori richiesti dal DSO.

## 6. Principi elettrici

- string sizing con Voc a temperatura minima reale + tolleranze;
- nessun mix di connettori DC di famiglie non espressamente compatibili;
- cavo PV1-F dimensionato per corrente, caduta, temperatura e posa;
- SPD DC/AC coerenti con LPS e valutazione fulminazione;
- sezionamento accessibile e identificato;
- equipotenzialità/messa a terra;
- protezioni di interfaccia secondo DSO/CEI;
- misura energia produzione/scambio;
- Modbus/Ethernet o altro protocollo documentato verso EMS locale;
- fail-safe: perdita cloud non deve fermare la produzione locale.

## 7. Package sviluppati

- `PV_ARCHITECTURE.md`;
- `RFQ_PV_INVERTERS.md`;
- `19_BOM_PRODOTTI_FORNITORI/ENERGIA_FV_MODULI_INVERTER.md` — BOM-019;
- `22_FONTI_NORME_PREVENTIVI/ENERGIA_FV_SOURCES.md`.

## 8. Gate BOM-019

1. lotto e masterplan reale;
2. superfici disponibili e ombre;
3. geotecnica/strutture se ground/carport;
4. carichi elettrici annuali e profilo 15 min;
5. producibilità PVGIS;
6. preventivo connessione DSO e BT/MT;
7. scelta 100 vs 120 kW AC e strategia espansione;
8. string design completo;
9. protezioni/quadri e selettività;
10. verifica antincendio dove applicabile;
11. RFQ moduli/strutture/inverter/BOSe;
12. CAPEX installato e commissioning.
