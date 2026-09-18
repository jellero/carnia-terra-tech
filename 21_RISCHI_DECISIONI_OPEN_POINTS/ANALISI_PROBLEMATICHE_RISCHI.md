# Analisi problematiche, rischi e vulnerabilità trasversali — Carnia TerraTech

**Aggiornato:** 18 settembre 2026  
**Stato:** `ANALISI GENERALE DEI RISCHI / PROBABILITÀ DA POPOLARE CON DATI REALI`

## 1. Scopo

Questo documento raccoglie in un solo punto:

- problematiche già presenti;
- rischi futuri;
- vulnerabilità di progetto;
- condizioni di escalation;
- mitigazioni;
- responsabile;
- condizione di chiusura.

Distinzione fondamentale:

- **problematica** = condizione già esistente e verificata che blocca o limita una decisione;
- **rischio** = evento o condizione futura/incerta che può produrre un impatto negativo;
- **vulnerabilità** = caratteristica del progetto che aumenta l'impatto se il rischio si materializza.

Non vengono assegnate probabilità numeriche senza dati reali.

## 2. Classificazione impatto

La severità qui indica **conseguenza potenziale**, non probabilità.

| Classe | Significato |
|---|---|
| I4 — CRITICO | può bloccare finanziamento, acquisto, costruzione, avvio operativo, sicurezza, conformità o continuità P0 |
| I3 — ALTO | può modificare materialmente CAPEX, tempi, resa, OPEX o operatività |
| I2 — MEDIO | può degradare prestazioni o creare costi/ritardi recuperabili |
| I1 — LOCALE | impatto circoscritto, recuperabile senza revisione del progetto |

La probabilità resta:
- `DA DETERMINARE`;
- `MISURATA`;
- `EVIDENZA FORNITORE`;
- `EVIDENZA SITO`;

finché esistono evidenze sufficienti.

## 3. Problematiche già presenti

| ID | Problematica attuale | Impatto | Perché è reale | Azione di chiusura |
|---|---|---|---|---|
| P-01 | pacchetto finanziario non ancora perfezionato | I4 | contributi, anticipo, garanzia, finanziamento, linea IVA e finanziamento ponte non sono ancora effettivi/concessi nel registro | chiudere DG0/F0 con atti reali |
| P-02 | lotto reale non ancora acquisito/validato | I4 | blocca campionamento, drenaggio, geotecnica, layout, DSO, neve/vento, accessi e RFQ installati | campagna sito + due diligence + DG1 |
| P-03 | schede colturali P1 non finalizzate | I3 | blocca carichi idrici/termici, resa, raccolta, freddo e confezionamento | completare le schede colturali per i 3 comparti P1 |
| P-04 | CAPEX principale ancora prevalentemente E0/E1 | I4 | €950k è budget di controllo, non costo contrattuale | preventivi installati comparabili E3/E4 |
| P-05 | profilo elettrico P0/P1 reale non disponibile | I4 | BESS 30 kW e 60/90/120 kWh non possono essere chiusi | misure 1–15 min + transitori |
| P-06 | DSO/POD/BT-MT non determinati | I4 | non è noto il costo/assetto reale della connessione | lotto + DSO/TICA reale |
| P-07 | prove pilota Q3 non ancora eseguite | I3 | AMR, vendita automatizzata, tagliaerba, riuso, mezzo e accesso in quota richiedono evidenze reali dove previsto | eseguire registro generale delle prove pilota |
| P-08 | SAT/messa in servizio ancora solo pianificati | I4 | continuità, commutazione di emergenza e prestazioni non sono ancora provate | eseguire piano generale SAT |
| P-09 | OPEX reale non misurato | I3 | energia, lavoro, manutenzione, confezionamento e logistica sono ancora di pianificazione | revisione dei dati effettivi a 30/90 giorni |
| P-10 | domanda P1 da validare commercialmente | I4 | €280k/y è obiettivo da validare, non vendite acquisite | pre-vendita, clienti, ordini e validazione dei canali di vendita |

## 4. Rischi finanziari e di cassa

### R-FIN-01 — ritardo o riduzione del sostegno
**Impatto:** I4.

Evento:
- concessione inferiore al previsto;
- anticipo non ottenibile nei tempi;
- garanzia insufficiente;
- SAL/saldo più lento del previsto.

Conseguenza:
- cantiere avviato senza copertura;
- necessità di finanziamento ponte più elevato;
- erosione della riserva operativa;
- stop lavori.

Mitigazione:
- DG0 prima di ogni spesa irreversibile;
- flusso di cassa mensile;
- calendario pagamenti fornitori;
- finanziamento ponte dedicato;
- nessuna contabilizzazione di contributi come incassati prima dell'accredito.

Condizioni di escalation:
- finanziamento o contributo inferiore al modello;
- slittamento >1 ciclo di pagamento;
- richiesta di anticipare CAPEX con C4.

### R-FIN-02 — uso della riserva operativa per coprire CAPEX
**Impatto:** I4.

È uno dei principali modalità di guasto economiche del progetto.

Conseguenza:
- impianto costruito ma mancanza di liquidità per personale, input, raccolta, confezionamento e vendita.

Mitigazione:
- €120k segregati;
- contenitori di cassa;
- stop automatico nuovi ordini se C4 scende sotto soglia approvata.

### R-FIN-03 — CAPEX reale sopra il budget di riferimento
**Impatto:** I4.

Fattori principali:
- neve/vento;
- fondazioni;
- opere DSO;
- cabina MT;
- BESS;
- area tecnica/post-raccolta;
- opere civili;
- messa in servizio;
- trasporti;
- esclusioni non viste.

Mitigazione:
- E3 preventivi installati;
- ottimizzazione tecnica rispetto al costo;
- contingenza separata;
- revisione perimetro P1;
- nessun taglio a sicurezza, freddo, acqua, messa in servizio o capitale circolante.

### R-FIN-04 — IVA e tempistica fiscale
**Impatto:** I3/I4.

Mitigazione:
- linea IVA €120–150k;
- calendario fatture;
- verifica commercialista;
- nessun uso del fondo stipendi per IVA.

## 5. Rischi lotto, strutture e opere civili

### R-SITE-01 — lotto tecnicamente incompatibile o costoso
**Impatto:** I4.

Possibili cause:
- accesso inadeguato;
- vincoli;
- drenaggio;
- ombreggiamento;
- scarsa espandibilità;
- allacci lontani;
- rischio idraulico;
- geologia sfavorevole.

Mitigazione:
- verifica preliminare pre-acquisto;
- piano generale P1 + finale;
- stima allacci;
- geotecnica preliminare;
- scartare il lotto se incompatibile.

### R-SITE-02 — fondazioni/struttura più onerose del previsto
**Impatto:** I3/I4.

Condizioni di escalation:
- carichi neve/vento;
- terreno debole;
- falda;
- scavi;
- drenaggi;
- fondazioni speciali.

Mitigazione:
- non congelare costo serra prima di geotecnica;
- 3 RFQ comparabili;
- computo quantità;
- controllo €/m² e peso acciaio.

### R-SITE-03 — piano generale troppo denso
**Impatto:** I3.

Conseguenza:
- percorsi mezzi insufficienti;
- manutenzione difficile;
- AMR incompatibile;
- BESS/serbatoi senza buffer;
- espansione P2 compromessa.

Mitigazione:
- acquistare un lotto che ospita il progetto finale, non solo P1;
- spazi minimi per manutenzione e accessi obbligatori.

## 6. Rischi acqua, fertirrigazione e ambiente

### R-WAT-01 — fonte acqua insufficiente o qualità non idonea
**Impatto:** I4.

Variabili:
- disponibilità stagionale;
- alcalinità;
- EC;
- Na/Cl;
- microbiologia;
- UVT;
- Fe/Mn;
- torbidità.

Mitigazione:
- analisi stagionali;
- bilancio idrico;
- trattamento dimensionato su dati reali;
- accumulo e fonte alternativa legale.

### R-WAT-02 — dimensionamento errato pompe/filtri/fertirrigazione
**Impatto:** I3.

Mitigazione:
- Q/H/NPSH reali;
- curve pompe;
- simultaneità settori;
- controlavaggio;
- messa in servizio idraulica.

### R-WAT-03 — riuso drenaggi diffonde fitopatogeni
**Impatto:** I4.

Mitigazione:
- R0 raccolta/misura/BLOCCO;
- segregazione C1/C2;
- trattamento validato;
- monitoraggio dei patogeni;
- prova pilota di 30–60 giorni;
- nessun riuso automatico prima dell'esito positivo.

### R-WAT-04 — accumulo Na/Cl nel circuito chiuso
**Impatto:** I3/I4.

Mitigazione:
- pannello analitico ionico di laboratorio;
- rapporto di riuso dinamico;
- spurgo controllato;
- soglie specifiche per coltura.

### R-WAT-05 — scarico non autorizzato o classificazione errata
**Impatto:** I4.

Mitigazione:
- classificazione reale;
- percorso autorizzativo;
- AUA/SUAP dove applicabile;
- misuratore di portata e punto di campionamento;
- nessuno scarico al suolo come configurazione di base.

## 7. Rischi agronomici e produttivi

### R-AGR-01 — resa inferiore alla scheda colturale
**Impatto:** I4.

Conseguenza:
- mancato raggiungimento del obiettivo commerciale;
- costo unitario maggiore;
- sovradimensionamento infrastrutture rispetto ai ricavi.

Mitigazione:
- resa prudente;
- P1 su 3 comparti;
- misure kg/m², €/m², scarto;
- P2 solo dopo dati P1.

### R-AGR-02 — mix P1 non coerente con stagione e mercato
**Impatto:** I3/I4.

Mitigazione:
- scheda colturale prima degli ordini interni;
- pre-validazione commerciale;
- flessibilità C3–C6;
- almeno una coltura rapida e una ad alto valore.

### R-AGR-03 — pressione fitosanitaria / evento fitosanitario
**Impatto:** I4.

Vulnerabilità:
- sistemi fuori suolo e riuso possono amplificare eventi se non segregati.

Mitigazione:
- compartimentazione;
- tracciabilità genealogica;
- isolamento;
- flussi pulito/sporco;
- procedure operative fitosanitarie;
- nessun ritorno comune non trattato.

## 8. Rischi termici e climatici

### R-TH-01 — PDC sottodimensionate in condizioni reali sottozero
**Impatto:** I4.

Problema:
- dati A7/A2 non bastano per Carnia.

Mitigazione:
- A-7/A-10/A-15;
- W45;
- sbrinamento netto;
- meteo sito;
- accumulo termico;
- SAT stagionale.

### R-TH-02 — deumidificazione sottostimata
**Impatto:** I3/I4.

Conseguenza:
- malattie;
- condensa;
- qualità;
- energia eccessiva.

Mitigazione:
- kg/h vapore;
- rapporto di umidità;
- D1/D2/D3 modello comparativo;
- misura reale.

### R-TH-03 — strategia di emergenza termica dipendente troppo dall'elettrico
**Impatto:** I4.

Mitigazione:
- accumulo termico;
- distacco selettivo dei carichi;
- strategia di temperatura di sopravvivenza;
- BESS solo per carichi essenziali.

## 9. Rischi elettrici, rete e BESS

### R-EL-01 — connessione DSO più costosa/complessa
**Impatto:** I4.

Possibili cause:
- MT;
- cabina;
- opere di rete;
- limite di immissione;
- CCI/PF2;
- SLI.

Mitigazione:
- scenari G100/G120/G120-CAP100;
- pacchetto preliminare alla domanda;
- non scegliere limite di immissione solo sul corrispettivo della domanda.

### R-EL-02 — BESS 30 kW non sostiene i carichi reali
**Impatto:** I4.

Mitigazione:
- registro dei carichi misurato;
- P0/P1;
- gruppi di riavvio;
- resilienza termica;
- nessuna assunzione di backup a piena potenza dell'intera azienda.

### R-EL-03 — commutazione non realmente senza interruzione
**Impatto:** I4.

Mitigazione:
- SAT in blackout;
- criterio finale = nessun riavvio P0;
- non fare affidamento sul solo dato commerciale <20 ms.

### R-EL-04 — avviamento da rete assente / ritorno rete non affidabili
**Impatto:** I4.

Mitigazione:
- sequenza testata;
- protezioni rete/isola;
- riavvio ritardato;
- avvio dei motori;
- separazione fisica dalla rete DSO.

### R-EL-05 — incendio/esplosione BESS
**Impatto:** I4.

Mitigazione:
- installazione esterna dedicata preferita;
- valutazione del rischio incendio;
- protezioni del costruttore;
- accesso e isolamento di emergenza;
- no acquisto prima del progetto antincendio.

## 10. Rischi catena del freddo, confezionamento e sicurezza alimentare

### R-FOOD-01 — celle sottodimensionate sul raffreddamento rapido
**Impatto:** I4.

Mitigazione:
- kg/lotto;
- Tin;
- target temperatura al cuore;
- cicli di apertura porta;
- messa in servizio a carico.

### R-FOOD-02 — temperatura impostata non coerente fra SKU
**Impatto:** I3/I4.

Mitigazione:
- CR-A/CR-B;
- scheda colturale post-raccolta;
- niente 0–4 °C automatico per SKU sensibili al freddo.

### R-FOOD-03 — confezionamento danneggia prodotto o rallenta troppo
**Impatto:** I3.

Mitigazione:
- PIL-PACK;
- 100 confezioni per prodotto critico;
- produttività, danni, scarti, lavoro.

### R-FOOD-04 — vendita automatizzata vende prodotto fuori specifica
**Impatto:** I4.

Mitigazione:
- registratore indipendente;
- blocco della vendita;
- tracciabilità dell'inventario;
- riconciliazione vendita/pagamento;
- chiusura HACCP/fiscale/SUAP.

## 11. Rischi automazione, dati e sicurezza informatica

### R-IT-01 — server centrale diventa punto singolo di guasto operativo
**Impatto:** I4.

Mitigazione:
- PLC/edge locali;
- nessuna dipendenza dal cloud per la sicurezza;
- commutazione di emergenza;
- ripristino di emergenza;
- SAT di perdita server.

### R-IT-02 — perdita/corruzione dati
**Impatto:** I3/I4.

Mitigazione:
- PostgreSQL replica;
- WAL/PITR;
- PBS/copia fuori sede;
- prova di ripristino;
- riproduzione degli eventi.

### R-IT-03 — sicurezza informatica / compromissione accessi
**Impatto:** I4.

Mitigazione:
- VLAN;
- RBAC;
- MFA/gestione identità;
- accesso remoto fornitore limitato nel tempo;
- registri;
- backup;
- procedura di gestione incidente.

### R-IT-04 — automazione ottimizza su dati errati
**Impatto:** I3/I4.

Mitigazione:
- controlli di plausibilità;
- taratura sensori;
- limiti rigidi locali;
- il modello non può superare i limiti di sicurezza/HACCP;
- segnalazioni di anomalia.

### R-IT-05 — integrazioni fornitore/API instabili
**Impatto:** I3.

Mitigazione:
- API locale preferita;
- documentazione dei protocolli;
- modalità fuori rete;
- inventario versioni;
- test di accettazione dell'integrazione.

## 12. Rischi robotica e mezzi

### R-ROB-01 — AMR non compatibile con serra reale
**Impatto:** I3.

Possibili cause:
- condensa;
- corridoi;
- porte;
- vegetazione;
- riflessi;
- rete;
- aggancio alla stazione.

Mitigazione:
- prova pilota di 8 h + 100 missioni;
- nessun ordine su scala completa prima del SUPERATO.

### R-ROB-02 — robot tagliaerba non sicuro nelle aree condivise
**Impatto:** I4.

Mitigazione:
- area libera da galline;
- blocco durante presenza visitatori;
- nessuna operatività notturna;
- GNSS e prove fuori rete;
- area fisica interdetta.

### R-MNT-04 — accesso in quota insufficiente
**Impatto:** I4.

Problema:
una parte alta non raggiungibile in sicurezza trasforma manutenzione ordinaria in rischio, fermo o dipendenza esterna.

Mitigazione:
- mappa punti alti;
- piattaforma OEM/PLE ragno;
- demo sui punti reali;
- emergency recovery;
- corridoi e piazzole nel masterplan.

Chiusura:
PIL-HGT PASS e 100% punti critici raggiungibili.

### R-ROB-04 — mezzo multifunzione non compatibile con flussi reali
**Impatto:** I2/I3.

Mitigazione:
- dimostrazione;
- analisi dei compiti;
- acquisto rispetto a noleggio;
- stoccatore L2 per evitare uso improprio.

## 13. Rischi approvvigionamenti e catena di fornitura

### R-SUP-01 — preventivi non comparabili
**Impatto:** I3.

Mitigazione:
- separare hardware, posa, messa in servizio, assistenza, IVA, trasporto;
- PROCUREMENT_CLOSURE_REGISTER.

### R-SUP-02 — dipendenza vincolante da un fornitore
**Impatto:** I3.

Mitigazione:
- protocolli aperti;
- esportazione sorgenti/configurazioni;
- ricambi;
- seconda fonte di fornitura dove possibile;
- separare supervisione personalizzata separata dalle funzioni di sicurezza del costruttore.

### R-SUP-03 — tempo di consegna e ricambi Italia
**Impatto:** I3/I4.

Mitigazione:
- tempo di consegna in RFQ;
- elenco ricambi critici;
- assistenza SLA;
- assistenza locale;
- approvvigionamento dei componenti a lunga consegna dopo passaggio decisionale.

### R-SUP-04 — revisione/modello diverso tra benchmark e offerta
**Impatto:** I3.

Mitigazione:
- modello/revisione esatti;
- scheda tecnica;
- firmware;
- conformità;
- controllo delle modifiche prima dell'ordine.

## 14. Rischi personale e organizzazione

### R-HR-01 — difficoltà di reperimento competenze
**Impatto:** I3/I4.

Mitigazione:
- assunzione anticipata;
- matrice delle competenze;
- bacino di lavoratori stagionali;
- supporto esterno.

### R-HR-02 — dipendenza eccessiva dal promotore
**Impatto:** I4.

Mitigazione:
- responsabile primario + sostituto;
- procedura operativa;
- prova di assenza del responsabile;
- ferie testate;
- nessuna assunzione del promotore come manodopera gratuita.

### R-HR-03 — carico operativo superiore alle stime
**Impatto:** I3/I4.

Mitigazione:
- ore/kg;
- registri delle attività;
- straordinari;
- arretrato della manutenzione preventiva;
- condizioni per aumento dell'organico.

## 15. Rischi mercato e ricavi

### R-MKT-01 — domanda inferiore al obiettivo P1
**Impatto:** I4.

Mitigazione:
- pre-vendita;
- famiglie ricorrenti;
- ristorazione selettiva;
- canali multipli;
- P2 subordinata a domanda/margine.

### R-MKT-02 — eccessiva concentrazione su pochi clienti/canali
**Impatto:** I3.

Mitigazione:
- mix dei canali;
- limite concentrazione da definire sui dati;
- spaccio/ritiro/consegna/B2B.

### R-MKT-03 — prezzo accettato insufficiente
**Impatto:** I4.

Mitigazione:
- test prezzo prima del piena espansione;
- margine per coltura/canale;
- non inseguire volume negativo.

## 16. Rischi normativi e autorizzativi

### R-REG-01 — requisiti edilizi/urbanistici incompatibili
**Impatto:** I4.

Chiusura:
- lotto + tecnico + titoli.

### R-REG-02 — contributi: eleggibilità/cumulo/doppio finanziamento
**Impatto:** I4.

Mitigazione:
- matrice spesa→bando;
- documentazione;
- no assunzione automatica 60%.

### R-REG-03 — vendita/spaccio regime errato
**Impatto:** I4.

Mitigazione:
- SUAP/commercialista;
- distinzione vendita agricola vs distributore automatico;
- fiscalità prima dell'avvio operativo.

### R-REG-04 — fattoria didattica non conforme ai requisiti reali
**Impatto:** I3/I4.

Mitigazione:
- ERSA;
- zonizzazione visitatori;
- accessibilità;
- RC;
- visita pilota.

## 17. Rischi sicurezza e continuità

### R-SAFE-01 — interazione persone/macchine
**Impatto:** I4.

Aree:
- AMR;
- telescopico;
- robot tagliaerba;
- percorso visitatori.

Mitigazione:
- zonizzazione;
- interblocco;
- procedure;
- nessun affidamento esclusivo su visione/IA.

### R-SAFE-02 — guasti simultanei o a cascata
**Impatto:** I4.

Esempi:
- blackout + freddo;
- server + rete;
- pompa + livello basso;
- trattamento + livello serbatoio altissimo.

Mitigazione:
- piano generale SAT;
- prove delle modalità di guasto;
- prova di durata di 72 h;
- escalation.

### R-SAFE-03 — allarme eccessivo / affaticamento da allarmi
**Impatto:** I3.

Mitigazione:
- razionalizzazione degli allarmi;
- P0/P1/P2/P3;
- nessuna chiamata notturna per allarmi P3;
- responsabile e ripristino per ogni allarme.

## 18. Rischi programma e controllo delle modifiche

### R-PM-01 — troppe attività parallele prima dei dati reali
**Impatto:** I3/I4.

Conseguenza:
- rilavorazioni;
- RFQ scaduti;
- incompatibilità tra pacchetti.

Mitigazione:
- DG0–DG8;
- congelamento P1;
- programma basato sulle dipendenze.

### R-PM-02 — espansione incontrollata del perimetro
**Impatto:** I4.

Aree più esposte:
- robotica;
- visitor;
- vendita automatizzata;
- agriturismo;
- R&S;
- trasformazione.

Mitigazione:
- progetto principale ed extra separati;
- BOM-029/extra fuori dal CAPEX principale;
- richiesta di modifica con costo/cassa.

### R-PM-03 — espansione P2 compromessa da scelte P1
**Impatto:** I3/I4.

Mitigazione:
- dimensionare dorsali e spazi permanenti sul progetto finale quando conveniente;
- non sovradimensionare elettronica obsolescente.

## 19. Rischi manutenzione e ciclo di vita

### R-MNT-01 — progetto acquistabile ma non manutenibile
**Impatto:** I3/I4.

Mitigazione:
- elenco ricambi;
- manuali;
- piano di manutenzione preventiva;
- assistenza;
- formazione;
- backup sorgenti/configurazioni.

### R-MNT-02 — ricambi critici con tempo di consegna lungo
**Impatto:** I3.

Mitigazione:
- scorta in sito;
- seconda fonte di fornitura;
- SLA;
- strategia ricambi.

### R-MNT-03 — costo ciclo di vita sottostimato
**Impatto:** I3/I4.

Mitigazione:
- TCO 5/8/10 anni;
- consumabili;
- batterie;
- assistenza;
- sostituzioni;
- fermo impianto.

## 20. Concentrazioni principali di rischio

Le concentrazioni di rischio più rilevanti non sono singoli componenti, ma dipendenze:

### A. Finanza -> lotto -> RFQ
Se DG0/F0 non è chiuso, tutto il percorso resta teorico.

### B. Lotto -> DSO/geotecnica/layout
Un lotto errato può rendere inutili molte ottimizzazioni già fatte.

### C. Scheda colturale -> acqua/termico/freddo/confezionamento
Specifiche premature su questi pacchetti aumentano il rischio di sovra/sottodimensionamento.

### D. Registro dei carichi -> BESS/DSO
Il 30 kW potenza di riferimento non chiude i kWh né l'import/export.

### E. Mercato -> P2
L'espansione dei 6 comparti non deve precedere dati P1 sufficienti.

### F. Integrazione -> avvio operativo
Ogni singolo sottosistema può funzionare e l'impianto integrato può comunque fallire: per questo SAT integrato è passaggio decisionale obbligatorio.

## 21. Trigger di escalation immediata

Aprire/reaprire un passaggio decisionale se si verifica uno dei seguenti:

- CAPEX major pacchetti >20% sopra il budget di riferimento;
- previsione CAPEX installato >€1,05M;
- richiesta di usare riserva operativa per CAPEX;
- contributo/finanziamento ridotto o ritardato materialmente;
- lotto con criticità geotecnica/idraulica/urbanistica;
- DSO impone MT/opere inattese;
- carico P0/P1 > envelope BESS;
- resa/prezzo delle colture significativamente sotto obiettivo P1;
- prova pilota critica FALLITA;
- riavvio P0 durante blackout;
- failure food/cold/water sicurezza;
- scarico/riuso non autorizzato;
- il fornitore cambia modello/configurazione;
- ricambio critico/assistenza non disponibile;
- dipendenza da una sola persona per competenza P0.

## 22. Chiusura di un rischio

Un rischio non viene marcato `CHIUSO` perché esiste una mitigazione scritta.

Stati:
- `APERTO`;
- `MITIGAZIONE PROGETTATA`;
- `EVIDENZA IN ATTESA`;
- `SOTTO CONTROLLO`;
- `ACCETTATO`;
- `CHIUSO`;
- `MATERIALIZZATO`.

Per passare a `SOTTO CONTROLLO` servono:
- responsabile;
- controllo implementato;
- evidenza;
- test quando applicabile;
- rischio residuo registrato.

## 23. Governance

Il registro rischi va rivisto obbligatoriamente:

- prima di DG0;
- prima di acquisto lotto;
- al congelamento del progetto P1;
- prima degli ordini principali;
- dopo ogni prova pilota FALLITA;
- prima della messa in servizio;
- prima dell'avvio operativo;
- a 30 e 90 giorni dall'avvio operativo;
- prima di P2.

## 24. Collegamenti

- `VALIDATION_CLOSURE_DASHBOARD.md`;
- `MASTER_DECISION_GATE_REGISTER.md`;
- `PROCUREMENT_CLOSURE_REGISTER.md`;
- `MASTER_PILOT_REGISTER.md`;
- `MASTER_COMMISSIONING_ACCEPTANCE.md`;
- `../18_CAPEX_OPEX_CASHFLOW/FINANCIAL_CLOSURE_CONTROL.md`;
- `../20_CANTIERE_E_CRONOPROGRAMMA/PIANO_OPERATIVO_AVVIO/README.md`.
