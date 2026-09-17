# Carnia TerraTech — Technical Architecture

**Aggiornato:** 17 settembre 2026

---

## 1. Architettura generale

Il progetto viene strutturato come un sistema agricolo modulare composto da:

1. serra a 6 comparti;
2. dorsale acqua/fertirrigazione;
3. dorsale termica con PDC + accumulo;
4. fotovoltaico e gestione energia;
5. PLC e I/O locali;
6. rete dati e server edge;
7. computer vision;
8. AMR e mezzo multifunzione;
9. Tech Barn e post-raccolta;
10. vermicompost;
11. fasce verdi produttive e outdoor.

Principio: **nessun servizio vitale deve dipendere da cloud o connettività Internet**.

---

## 2. Serra — 6 comparti

Working geometry:

- 6 × ~700 m²;
- circa 20 × 35 m per comparto;
- corridoio tecnico centrale ~4 m;
- testate e aree svolta compatibili con AMR;
- accessi 2,5–3 m dove necessario;
- fascia manutenzione esterna libera 3–4 m o più.

Ogni comparto deve essere indipendente per:

- irrigazione;
- ricetta fertirrigazione;
- riscaldamento;
- ventilazione;
- aperture;
- schermatura;
- sensoristica;
- allarmi.

---

## 3. Clima

### 3.1 Ventilazione passiva

- aperture laterali motorizzate;
- zenitali dove struttura e budget lo consentono;
- rete anti-insetto dimensionata per non penalizzare troppo la ventilazione;
- logica vento/pioggia/temperatura locale in PLC.

### 3.2 HAF

Working quantity:

- 4 ventilatori per comparto;
- totale 24;
- regolazione velocità preferibile;
- obiettivo: uniformare T, UR e CO₂, ridurre zone morte e condensa.

### 3.3 Schermo termico / ombreggiante

Priorità iniziale almeno per C1, C2 e C6, preferibilmente predisposizione su tutta la serra.

Funzioni:

- riduzione dispersioni notturne;
- riduzione volume termicamente attivo;
- ombreggiamento estivo controllato.

### 3.4 Fogging

Predisposizione nei comparti più sensibili:

- pomodoro;
- peperone;
- vivaio/jolly.

Da usare in funzione di VPD/UR e non come sistema indiscriminato.

---

## 4. Impianto termico

### 4.1 Generazione

Working concept:

- 3 × Kensol KHP-R290-22-3 iniziali;
- 66 kW nominali complessivi;
- predisposizione quarta unità → 88 kW;
- modularità e fault tolerance.

### 4.2 Batteria termica

- 30 m³ iniziali;
- predisposizione a 40–50 m³;
- preferenza per più serbatoi modulari;
- misura stratificazione verticale;
- calcolo software dell'energia utile disponibile.

### 4.3 Circuito primario

Architettura preferenziale da verificare:

PDC → circuito primario protetto dal gelo → eventuale scambiatore a piastre → accumulo termico.

Scopo: non glicolare inutilmente decine di m³ d'acqua se è sufficiente proteggere il tratto esterno.

### 4.4 Circuiti secondari

Accumulo → collettore → 6 circuiti indipendenti.

Per ogni comparto:

- pompa zona;
- valvola miscelatrice;
- T mandata;
- T ritorno;
- flussimetro;
- valvole isolamento;
- bilanciamento.

### 4.5 Terminali

Pomodoro/peperone:

- riscaldamento basso/radicale;
- working estimate 2 tubi per fila;
- ~720 m per comparto × 2 comparti = ~1.440 m.

Leafy/basilico:

- ~300–360 m per comparto;
- ~1.200–1.440 m complessivi.

Totale working estimate: **2.700–3.000 m**.

Piccoli aerotermi idronici solo come boost/deumidificazione/emergenza.

---

## 5. Strategia termica operativa

Il sistema non tenta necessariamente di mantenere tutta la serra a temperatura produttiva piena durante eventi estremi.

Modalità previste:

### Modalità produzione

- C1/C2 con setpoint più alto;
- C6 vivaio/basilico protetto;
- leafy con setpoint minore.

### Modalità economia

- riduzione setpoint;
- utilizzo priorità termica;
- carica accumulo nelle ore FV/temperatura esterna favorevole.

### Modalità sopravvivenza

- protezione gelo e danno critico;
- capacità termica concentrata sui comparti più sensibili.

---

## 6. Acqua

### 6.1 Accumulo

Working concept:

- 300 m³ totali;
- preferenza 2 × 150 m³ o serbatoio compartimentato;
- recupero pioggia dalle serre;
- fonte primaria da verificare sul sito.

### 6.2 Catena

Fonte/raccolta → pretrattamento → serbatoi → filtrazione → pompe 1+1 → fertirrigazione → collettore → 24 settori.

### 6.3 Ridondanza

- due pompe principali identiche;
- master/slave alternato periodicamente;
- standby automatico;
- allarme portata/pressione.

---

## 7. Fertirrigazione

### 7.1 Concentrati

- A: 500–1.000 L;
- B: 500–1.000 L;
- acido/pH: volume minore;
- additivo/disinfezione: opzionale.

### 7.2 Dosaggio

Pompe dosatrici controllate da PLC:

- A;
- B;
- pH;
- additivo;
- 1 unità universale di ricambio.

### 7.3 Misure

- pH online;
- EC online;
- temperatura acqua;
- portata;
- pressione;
- differenziale filtri;
- livello serbatoi fertilizzanti;
- preferenza per celle di carico o misura massa dove utile.

### 7.4 Zone

- 4 settori per comparto;
- totale 24;
- ricette diverse per coltura/comparto.

---

## 8. Drenaggio

Per comparti fuori suolo:

- canaline raccolta;
- pozzetto per comparto;
- misura volume;
- EC;
- pH;
- temperatura;
- eventuale pompa recupero 1+1 dove necessario.

Riuso solo dopo validazione tecnica, sanitaria e normativa.

---

## 9. Elettrico

### 9.1 Dorsale

Quadro generale → sottocampi/quadri locali:

- serra;
- PDC;
- pompe;
- Tech Barn;
- frigo;
- FV;
- robot/ricarica;
- servizi.

### 9.2 Contabilizzazione

Contatori Modbus su carichi principali per ricavare:

- kWh/kg;
- kWh per comparto;
- COP reale PDC;
- quota autoconsumo FV;
- costo energetico per coltura.

### 9.3 Backup

Da definire:

- UPS online per PLC, rete, server e attuatori critici;
- eventuale generatore per blackout prolungati;
- carichi prioritari e load shedding.

---

## 10. Fotovoltaico

### 10.1 Taglia

- 120 kWp iniziali;
- predisposizione 150–180 kWp.

### 10.2 Posizionamento

- Tech Barn;
- carport;
- vermicompost;
- pensiline logistiche;
- eventuale fase 2 su area servizi.

Evitare pannelli opachi sopra i comparti produttivi principali.

### 10.3 Logica EMS

Il controllore energia deve poter:

- leggere produzione FV;
- leggere import/export;
- leggere SOC eventuale batteria elettrica;
- stimare energia termica disponibile;
- decidere quando caricare accumulo termico;
- modulare PDC;
- spostare carichi flessibili.

---

## 11. PLC e I/O

### 11.1 Livello centrale

Working candidate:

- WAGO PFC200 750-8215.

### 11.2 Livello comparto

Working concept:

- 1 nodo I/O digitale;
- 1 nodo I/O analogico;
- 24 VDC locale;
- RS485 isolata;
- Ethernet/fibra;
- switch PoE dove necessario.

### 11.3 Failure domain

Un guasto su un bus di comparto non deve abbattere tutti i 6 comparti.

Preferenza:

- RS485 separata per comparto;
- backbone Ethernet/fibra;
- segmentazione rete;
- watchdog locali;
- fallback in PLC.

---

## 12. Sensoristica

### Per comparto

- 3 × T/RH aria;
- 4 × umidità radicale;
- 2 × temperatura radicale;
- 1–2 × EC substrato;
- 1 × PAR;
- 1 × bagnatura fogliare;
- 1 × CO₂;
- 1 × pressione irrigazione;
- 1 × portata irrigazione;
- 1 × T mandata;
- 1 × T ritorno.

### Centrale

- pH;
- EC;
- temperatura acqua;
- pressione pre/post filtri;
- portata totale;
- livello serbatoi;
- perdite/allagamento;
- meteo;
- energia elettrica;
- energia termica;
- sonde stratificazione batteria.

---

## 13. Video e AI

### Telecamere fisse

- 2 per comparto = 12;
- PoE;
- inquadratura stabile.

### Stazioni campione

- 1 per comparto;
- camera + illuminazione costante;
- riferimento dimensionale;
- stesso soggetto/area nel tempo.

### Trappole insetti

- 1–2 per comparto;
- camera macro;
- illuminazione controllata;
- conteggio e trend.

### Robot

- camera RGB frontale;
- camera laterale;
- depth/stereo;
- termica mobile opzionale;
- eventuale multispettrale in fase successiva.

---

## 14. Server edge

Funzioni:

- database time-series;
- MQTT;
- orchestrazione automazioni non critiche;
- dashboard;
- NVR/integrazione video;
- inferenza AI;
- analisi immagini;
- data lake aziendale;
- report e KPI.

Il server non è nel loop vitale dell'irrigazione di sicurezza.

---

## 15. Robot AMR

Primo rilascio:

- trasporto cassette;
- trasporto materiali;
- pattugliamento/scouting;
- imaging;
- docking automatico.

Il layout fisico della serra deve essere compatibile prima di comprare il robot.

---

## 16. Mezzo multifunzione

Da ricercare sul mercato:

- nuovo;
- forche;
- attacco rapido;
- possibile cestello/piattaforma certificata;
- compatibilità comando remoto OEM;
- eventuali cingoli solo se utili;
- ricambi e rete assistenza;
- idoneità a contributi se applicabile.

---

## 17. Post-raccolta

### Flusso

raccolta → AMR/carrello → Tech Barn → selezione → confezionamento → cella → spedizione.

### Celle

Due temperature indipendenti:

- foglie/lattuga;
- prodotto più sensibile al freddo e basilico/pomodoro/peperone.

### Fase iniziale

No linea IV gamma completa. Prima consolidare produzione, vendite e catena del freddo base.

---

## 18. Vermicompost

Flusso concettuale:

residui vegetali sani → precompostaggio → stabilizzazione → letti lombrichi → monitoraggio → vaglio → humus → autoconsumo / vendita futura.

Sensori minimi:

- temperatura;
- umidità;
- eventualmente peso/volume lotti;
- tracciamento origine materiale.

---

## 19. Sicurezza e manutenzione

Da incorporare nel progetto esecutivo:

- sezionamenti;
- E-stop;
- protezioni differenziali e sovracorrente;
- SPD;
- protezione fulmini ove necessaria;
- accessi manutenzione;
- bypass manuali;
- ricambi minimi a scaffale;
- una pompa zona di scorta;
- una dosatrice universale di scorta;
- sensori critici di ricambio;
- valvole manuali per isolamento.

---

## 20. KPI tecnici

Il sistema deve rendere disponibili almeno:

- kWh elettrici/giorno;
- kWh termici/giorno;
- COP PDC;
- energia termica accumulata;
- autoconsumo FV;
- acqua totale e per comparto;
- fertilizzante per comparto;
- drenaggio %;
- ore di pompa;
- ore HAF;
- ore aperture/schermi;
- allarmi e downtime;
- kg raccolti;
- kg/m²;
- kWh/kg;
- L acqua/kg;
- ore lavoro/kg.
