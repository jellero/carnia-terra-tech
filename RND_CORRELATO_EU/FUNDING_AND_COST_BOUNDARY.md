# Confine economico R&S e canali UE candidati

**Stato:** `PRE-SCREENING / NESSUN CONTRIBUTO ASSUNTO COME CERTO`  
**Aggiornato:** 18 settembre 2026.

Link operativi e fonti ufficiali: [`LINKS_UE_RND.md`](LINKS_UE_RND.md).

## 1. Regola principale

Il progetto R&S correlato ha contabilità e perimetro separati dal progetto agricolo.

Una spesa non diventa R&S perché installata in Carnia TerraTech.

Per essere trattata come costo di un progetto europeo deve essere:

- necessaria alle attività approvate;
- coerente con il topic/call;
- ammissibile secondo Grant Agreement e regole applicabili;
- documentata e allocata correttamente;
- sostenuta nel periodo e nelle modalità previste.

La verifica definitiva si fa solo sulla call specifica.

## 2. Classificazione costi

### A. Core agricolo — fuori R&S salvo eccezioni esplicite

- terreno;
- opere civili ordinarie;
- serra produttiva standard;
- accumuli e reti dimensionati per normale produzione;
- FV/BESS acquistati per fabbisogno ordinario;
- celle, packaging e mezzi di produzione ordinari;
- costi societari;
- capitale circolante;
- costi commerciali non legati alla R&S.

Stato: `CORE-NON-RND`.

### B. Interfacce condivise — da allocare con cautela

Esempi:

- rete dati;
- edge computer;
- sensori;
- robot commerciali usati come piattaforme di test;
- server;
- camere;
- storage;
- strumenti di misura.

Possono essere necessari al progetto R&S ma non sono automaticamente finanziabili integralmente. Il trattamento dipende dalle regole della call e dall'uso documentato.

Stato iniziale: `RND-NOT-ELIGIBILITY-ASSESSMENT`.

### C. Attività R&S candidate

- personale di ricerca e sviluppo;
- progettazione architetturale sperimentale;
- software/prototipi;
- dataset e pipeline sperimentali;
- adapters e middleware non disponibili commercialmente;
- prototipazione robotica;
- test bench;
- validazione;
- prove comparative;
- cybersecurity R&D;
- measurement/benchmarking;
- attività di integrazione che contengono reale incertezza tecnica.

Stato: `RND-RESEARCH` o `RND-PROTOTYPE` dopo verifica.

## 3. Horizon Europe — candidato primario

Le Research and Innovation Actions (RIA) possono arrivare al **100%** dei costi eleggibili; le Innovation Actions (IA) normalmente al **70%** per le imprese for-profit, salvo condizioni specifiche del topic.

Per CTT-AFP i cluster da monitorare sono:

- **Cluster 4 — Digital, Industry and Space:** AI, robotics, advanced computing, data e tecnologie digitali;
- **Cluster 6 — Food, Bioeconomy, Natural Resources, Agriculture and Environment:** agricoltura, food systems e digitalizzazione collegata.

Il Work Programme Horizon Europe 2026–2027 è adottato. La selezione deve essere fatta topic per topic: non si presume che una call generica finanzi il progetto.

Fonti ufficiali:

- Horizon Europe — how to apply: https://rea.ec.europa.eu/horizon-europe-how-apply_en
- Cluster 4: https://research-and-innovation.ec.europa.eu/funding/funding-opportunities/funding-programmes-and-open-calls/horizon-europe/cluster-4-digital-industry-and-space_en
- Cluster 6: https://research-and-innovation.ec.europa.eu/funding/funding-opportunities/funding-programmes-and-open-calls/horizon-europe/cluster-6-food-bioeconomy-natural-resources-agriculture-and-environment_en
- Work Programmes 2026–2027: https://research-and-innovation.ec.europa.eu/funding/funding-opportunities/funding-programmes-and-open-calls/horizon-europe/horizon-europe-work-programmes_en

## 4. EIC Accelerator — percorso successivo, non baseline iniziale

EIC Accelerator è orientato a startup/PMI con innovazioni ad alto rischio e potenziale di mercato, per attività tipicamente **TRL 6–8**.

Nel Work Programme 2026:

- grant component inferiore a **€2,5 milioni**;
- attività di innovazione TRL 6–8;
- possibile investment component separata secondo le condizioni EIC.

Per CTT-AFP ha senso solo quando esiste già una tecnologia sufficientemente matura, differenziata e scalabile oltre il singolo living lab.

Fonte ufficiale:
https://eic.ec.europa.eu/eic-funding-opportunities/eic-accelerator_en

Stato: `FUTURE SCALE-UP CANDIDATE`.

## 5. Nessuna doppia contabilizzazione

La stessa spesa non deve essere caricata contemporaneamente come:

- CAPEX del progetto agricolo;
- costo di un altro incentivo;
- costo Horizon/EIC;

salvo combinazioni espressamente consentite dalle regole applicabili e senza doppio finanziamento dello stesso costo.

La matrice finanziaria definitiva deve quindi riportare almeno:

| Voce | Core | R&S | Programma | Quota/criterio | Evidenza | Stato |
|---|---|---|---|---|---|---|
| esempio server test | sì, in parte | possibile | DA CALL | DA REGOLA | log uso/config | DA VERIFICARE |
| sviluppo scheduler | no | sì | candidato Horizon | DA CALL | timesheet/deliverable | DA VERIFICARE |
| serra produttiva | sì | no baseline | — | — | CAPEX core | CORE-NON-RND |

## 6. Gate economico

Prima di usare un bando nel cashflow:

1. topic identificato;
2. soggetto beneficiario eleggibile;
3. ruolo nel consorzio definito;
4. cost category verificata;
5. funding rate verificato;
6. cofinanziamento disponibile;
7. timing di anticipi/pagamenti compatibile;
8. assenza di doppio finanziamento;
9. trattamento IVA verificato;
10. nessun costo core reso dipendente dall'esito della call.

Fino a quel momento: **contributo = €0 nelle fonti certe del progetto principale**.
