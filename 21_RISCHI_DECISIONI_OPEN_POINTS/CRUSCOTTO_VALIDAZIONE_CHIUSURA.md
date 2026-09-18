# Cruscotto di validazione e chiusura — Carnia TerraTech

**Aggiornato:** 18 settembre 2026  
**Stato:** `STATO GENERALE / DOCUMENTAZIONE STRUTTURATA / ESECUZIONE REALE ANCORA DA DATI-SITO-RFQ-PROVE-SAT`

## 1. Scopo

Questo file è il punto unico per capire:
- cosa è già strutturato;
- cosa è realmente chiuso;
- cosa resta bloccato;
- quale evidenza sblocca il passo successivo.

Non sostituisce i documenti tecnici: li coordina.

## 2. Stato della chiusura 1–8

| # | Blocco | Stato | Evidenza già pronta | Blocco reale |
|---:|---|---|---|---|
| 1 | lotto/piano generale/geotecnica/disposizione | STRUTTURATO / ESECUZIONE BLOCCATA | `20_CANTIERE_E_CRONOPROGRAMMA/PIANO_OPERATIVO_AVVIO/01_TERRENO_E_MASTERPLAN.md` + criteri punti 01/03 | lotto reale, titolo, rilievo, geotecnica, accessi, utenze |
| 2 | schede colturali + carichi reali acqua/termico/elettrico | STRUTTURATO / ESECUZIONE BLOCCATA | `20_CANTIERE_E_CRONOPROGRAMMA/PIANO_OPERATIVO_AVVIO/02_AGRONOMIA_P1.md` + metodi/BOM di dominio | schede colturali finali, stagione, meteo sito, analisi acqua, disposizione, misure reali |
| 3 | registro generale dei carichi 1–15 min + P0/P1 | STRUTTURATO | `MASTER_LOAD_REGISTER`, piano di misura, quadro dati fornitori, CSV di raccolta dati | misure P0/P1 e transitori + dati costruttore/RFQ mancanti |
| 4 | DSO/TICA BT/MT prelievo/immissione/protezioni | STRUTTURATO | preparazione DSO, richiesta dati, matrice BT/MT, RFQ connessione rete, scenari di costo | lotto, DSO, POD, potenze finali, preventivo reale |
| 5 | preventivi installati / approvvigionamenti | STRUTTURATO | `PROCUREMENT_CLOSURE_REGISTER` + classi Q1–Q5 | RFQ reali comparabili, disposizione/carichi dove necessari |
| 6 | prove pilota obbligatorie | STRUTTURATO | `MASTER_PILOT_REGISTER`, modello risultati/costi, verbale decisionale | dimostrazione fornitore, sito reale, prodotti/colture/impianto reale |
| 7 | messa in servizio / SAT integrato | STRUTTURATO | `COLLAUDO_MASTER_ACCETTAZIONE` + lista di controllo | impianto installato e condizioni stagionali |
| 8 | CAPEX/OPEX/flusso di cassa/rischi/passaggi decisionali | STRUTTURATO | `FINANCIAL_CLOSURE_CONTROL` + DG0–DG8 | preventivi installati, contratti, dati effettivi, concessioni/finanziamenti reali |

## 3. Ciò che è chiuso documentalmente

Sono già disponibili:
- BOM principali 001–034;
- fonti e riferimenti di confronto per i principali pacchetti;
- modelli RFQ per i pacchetti tecnici;
- registro generale dei carichi;
- piano di misura dei carichi;
- quadro dati fornitori;
- pacchetto preliminare DSO/TICA;
- registro approvvigionamenti;
- governo delle prove pilota;
- messa in servizio/SAT;
- controllo di chiusura finanziaria;
- passaggi decisionali generali.

Quindi il problema non è più “manca un documento”.

Il problema è sostituire progressivamente:
- `E0/E1` -> `E2/E3/E4/E5`;
- riferimento di confronto -> RFQ;
- RFQ -> contratto;
- ipotesi -> misura;
- piano prova pilota -> evidenza prova pilota;
- piano SAT -> SAT superato.

## 4. Analisi problematiche e rischi

Riferimenti:
- `ANALISI_PROBLEMATICHE_RISCHI.md`;
- `ANALISI_PROBLEMATICHE_RISCHI.csv`.

La lettura trasversale distingue **problematiche già presenti** da **rischi futuri**. Le problematiche oggi più bloccanti sono:
- chiusura finanziaria non ancora perfezionata;
- lotto non validato;
- schede colturali P1 non finalizzate;
- CAPEX principale ancora prevalentemente E0/E1;
- profilo P0/P1 non misurato;
- DSO/POD/BT-MT non determinati;
- prove pilota e SAT non eseguiti;
- OPEX non misurato;
- domanda P1 ancora da validare.

Le concentrazioni di rischio principali sono:
- finanza -> lotto -> RFQ;
- lotto -> geotecnica/DSO/disposizione;
- schede colturali -> acqua/termico/freddo/confezionamento;
- registro dei carichi -> BESS/DSO;
- mercato -> P2;
- integrazione -> avvio operativo.

Condizioni di escalation immediata:
- pacchetto principale >20% sopra il budget di riferimento;
- previsione di CAPEX installato >€950k;
- uso della riserva operativa per CAPEX;
- criticità urbanistica/geotecnica/idraulica del lotto;
- DSO con MT/opere inattese;
- carico P0/P1 oltre il dimensionamento di riferimento BESS;
- prova pilota critica FALLITA;
- riavvio P0 durante blackout;
- guasto critico su sicurezza alimentare/catena del freddo/acqua;
- scarico/riuso non autorizzato;
- modifica sostanziale della configurazione proposta dal fornitore;
- competenza P0 dipendente da una sola persona.

La severità indica la **conseguenza potenziale**; la probabilità resta `DA DETERMINARE` finché non esistono dati di sito, misure, evidenze dei fornitori o dati effettivi.

## 5. Piano operativo P1 già collegato

Il piano operativo generale corrente è:
- `20_CANTIERE_E_CRONOPROGRAMMA/PIANO_OPERATIVO_AVVIO/README.md`;
- `00_FINANZA_E_CASSA.md`;
- `01_TERRENO_E_MASTERPLAN.md`;
- `02_AGRONOMIA_P1.md`.

Questi documenti rendono eseguibili F0/F1 e preparano P1, ma non sostituiscono concessioni, lotto o schede colturali finali.

## 6. Prossime azioni possibili prima del lotto

### A. RFQ preliminari
Aprire:
1. BOM-034 BESS/PCS + commutazione rapida / alternative accoppiate in AC;
2. RFQ preliminare per progettazione connessione elettrica;
3. BOM-019 inverter/FV;
4. BOM-011 PDC;
5. BOM-030 server;
6. BOM-015 pompe/VFD;
7. BOM-025 prova banco/RFQ confezionamento;
8. BOM-024 dimensionamento preliminare celle frigorifere;
9. BOM-012 DryGair/sistema di supporto;
10. BOM-021 telescopico/dimostrazione.

Stato offerta:
`PRELIMINARE / NON VALIDO PER ORDINE`.

### B. Dimostrazioni fornitori
Possibili senza sito definitivo o con ambiente equivalente:
- PIL-AMR;
- PIL-PACK;
- PIL-RETAIL;
- evidenze/dimostrazione dell'architettura di commutazione BESS.

### C. Finanza
Chiudere evidenze di:
- concessione;
- anticipo;
- garanzia;
- finanziamento;
- linea IVA;
- finanziamento ponte;
- riserva operativa.

## 7. Azioni immediatamente dopo l'identificazione del lotto

Attivare in parallelo:

### Lotto
- verifica preliminare;
- rilievo;
- geotecnica;
- piano generale;
- accessi;
- drenaggi;
- acqua;
- utenze;
- neve/vento/meteo.

### Energia
- DSO/POD;
- TICA;
- BT/MT;
- Ik;
- prelievo/immissione;
- disposizione FV/BESS.

### Serra
- struttura/fondazioni;
- disposizione comparti;
- porte/corridoi;
- HAF/fogging;
- drenaggi.

### Visitatori/logistica
- percorso AMR;
- area robot tagliaerba;
- zonizzazione didattica;
- parcheggio/punto di discesa;
- accesso tecnico.

## 8. Azioni dopo schede colturali / processo reale

- portate irrigazione;
- ricette fertirrigazione;
- obiettivo drenaggi;
- carico termico;
- clima/VPD;
- bilancio umidità;
- picco raccolta kg/giorno;
- raffreddamento rapido celle;
- prodotti/confezioni;
- prodotti/temperature vendita;
- modello lavoro/attività.

Questi dati sostituiscono le classi di riferimento con dimensionamenti reali.

## 9. Dipendenze critiche

### Lotto sblocca
- geotecnica;
- serra;
- drenaggi;
- DSO;
- FV;
- posizione BESS;
- disposizione visitatori;
- percorsi macchine.

### Schede colturali sbloccano
- acqua;
- fertirrigazione;
- termico;
- deumidificazione;
- post-raccolta;
- confezionamento;
- OPEX.

### Registro reale dei carichi sblocca
- PCS;
- kWh BESS;
- bus dei carichi critici;
- potenza di prelievo DSO;
- gruppi di riavvio;
- CAPEX elettrico.

### Preventivi installati sbloccano
- CAPEX validato;
- calendario finanziario;
- assegnazione contratto;
- autorizzazione all'ordine.

### Prova pilota superata sblocca
- AMR;
- automazione vendita;
- espansione riuso drenaggi;
- robot tagliaerba;
- pulizia area galline;
- automazione confezionamento.

### SAT superato sblocca
- avvio operativo;
- pagamento di accettazione;
- decorrenza garanzia;
- passaggio alle operazioni.

## 10. Condizioni di blocco

Non procedere a un ordine irreversibile se:
- DG0 chiusura finanziaria non SUPERATO;
- specifica tecnica non chiusa;
- Q3 senza prova pilota SUPERATA;
- prezzo ancora solo di riferimento su un pacchetto principale;
- perimetro installato non separa posa/messa in servizio;
- blocco di sicurezza o normativo aperto;
- riserva operativa usata per coprire CAPEX;
- configurazione offerta materialmente diversa dal progetto approvato.

## 11. Scala di maturità

Per ogni pacchetto principale:

1. `PROGETTO`
2. `RIFERIMENTO`
3. `RFQ PRELIMINARE`
4. `RFQ INSTALLATO`
5. `PROVA PILOTA SUPERATA` se richiesta
6. `ORDINE AUTORIZZATO`
7. `INSTALLATO`
8. `SAT SUPERATO`
9. `COSTO/OPEX EFFETTIVO`
10. `REVISIONE A 90 GIORNI`

## 12. Documenti principali

Energia:
- `06_ENERGIA_ELETTRICA_FV/MASTER_LOAD_REGISTER.md`
- `06_ENERGIA_ELETTRICA_FV/LOAD_MEASUREMENT_AND_RFQ_PLAN.md`
- `06_ENERGIA_ELETTRICA_FV/DSO_TICA_CONNECTION_READINESS.md`

Chiusura:
- `21_RISCHI_DECISIONI_OPEN_POINTS/PROCUREMENT_CLOSURE_REGISTER.md`
- `21_RISCHI_DECISIONI_OPEN_POINTS/MASTER_PILOT_REGISTER.md`
- `21_RISCHI_DECISIONI_OPEN_POINTS/COLLAUDO_MASTER_ACCETTAZIONE.md`
- `21_RISCHI_DECISIONI_OPEN_POINTS/MASTER_DECISION_GATE_REGISTER.md`
- `21_RISCHI_DECISIONI_OPEN_POINTS/ANALISI_PROBLEMATICHE_RISCHI.md`

Finanza:
- `18_CAPEX_OPEX_CASHFLOW/BUDGET_AVVIO_IDEALE.md`
- `18_CAPEX_OPEX_CASHFLOW/FINANCIAL_CLOSURE_CONTROL.md`
- `18_CAPEX_OPEX_CASHFLOW/AVVIO_CASSA_E_RAMPA_PRODUTTIVA.md`

## 13. Stato sintetico corrente

La progettazione documentale non è più il collo di bottiglia principale.

I blocchi reali sono ora:
1. esecuzione F0 finanza reale;
2. lotto reale;
3. dati colturali e di processo;
4. misure;
5. preventivi installati;
6. prove pilota;
7. messa in servizio.

Nessuno di questi deve essere sostituito con numeri inventati.
