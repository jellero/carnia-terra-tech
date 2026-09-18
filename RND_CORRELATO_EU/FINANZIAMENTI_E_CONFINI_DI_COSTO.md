# Finanziamenti R&S e confini di costo

**Stato:** `PRE-VALUTAZIONE / NESSUN CONTRIBUTO ASSUNTO COME CERTO`  
**Aggiornato:** 18 settembre 2026.

Collegamenti operativi e fonti ufficiali: [`COLLEGAMENTI_UE_RND.md`](COLLEGAMENTI_UE_RND.md).

## 1. Regola principale

Il progetto R&S correlato ha contabilità e perimetro separati dal progetto agricolo.

Una spesa non diventa R&S perché installata in Carnia TerraTech.

Per essere trattata come costo di un progetto europeo deve essere:

- necessaria alle attività approvate;
- coerente con il tema e il bando;
- ammissibile secondo l'accordo di sovvenzione e le regole applicabili;
- documentata e allocata correttamente;
- sostenuta nel periodo e nelle modalità previste.

La verifica definitiva si fa solo sul bando specifico.

## 2. Classificazione costi

### A. Progetto agricolo principale — fuori R&S salvo eccezioni esplicite

- terreno;
- opere civili ordinarie;
- serra produttiva standard;
- accumuli e reti dimensionati per normale produzione;
- FV/BESS acquistati per fabbisogno ordinario;
- celle, confezionamento e mezzi di produzione ordinari;
- costi societari;
- capitale circolante;
- costi commerciali non legati alla R&S.

Stato: `PRINCIPALE-NON-RND`.

### B. Interfacce condivise — da allocare con cautela

Esempi:

- rete dati;
- computer edge;
- sensori;
- robot commerciali usati come piattaforme di prova;
- server;
- telecamere;
- archiviazione;
- strumenti di misura.

Possono essere necessari al progetto R&S ma non sono automaticamente finanziabili integralmente. Il trattamento dipende dalle regole del bando e dall'uso documentato.

Stato iniziale: `RND-AMMISSIBILITA-DA-VERIFICARE`.

### C. Attività R&S candidate

- personale di ricerca e sviluppo;
- progettazione architetturale sperimentale;
- software/prototipi;
- dataset e catene di elaborazione sperimentali;
- adattatori e middleware non disponibili commercialmente;
- prototipazione robotica;
- banchi prova;
- validazione;
- prove comparative;
- R&S di cybersicurezza;
- misura e confronto prestazionale;
- attività di integrazione con reale incertezza tecnica.

Stato: `RND-RICERCA` o `RND-PROTOTIPO` dopo verifica.

## 3. Horizon Europe — candidato primario

Le azioni di ricerca e innovazione (RIA) possono arrivare al **100%** dei costi eleggibili; le azioni di innovazione (IA) normalmente al **70%** per le imprese a scopo di lucro, salvo condizioni specifiche del tema.

Per CTT-PAA i raggruppamenti da monitorare sono:

- **Cluster 4 — Digitale, industria e spazio:** AI, robotica, calcolo avanzato, dati e tecnologie digitali;
- **Cluster 6 — Alimentazione, bioeconomia, risorse naturali, agricoltura e ambiente:** agricoltura, sistemi alimentari e digitalizzazione collegata.

Il programma di lavoro Horizon Europe 2026–2027 è adottato. La selezione deve essere fatta tema per tema: non si presume che un bando generico finanzi il progetto.

Fonti ufficiali:

- Horizon Europe — come candidarsi: https://rea.ec.europa.eu/horizon-europe-how-apply_en
- Cluster 4: https://research-and-innovation.ec.europa.eu/funding/funding-opportunities/funding-programmes-and-open-calls/horizon-europe/cluster-4-digital-industry-and-space_en
- Cluster 6: https://research-and-innovation.ec.europa.eu/funding/funding-opportunities/funding-programmes-and-open-calls/horizon-europe/cluster-6-food-bioeconomy-natural-resources-agriculture-and-environment_en
- Programmi di lavoro 2026–2027: https://research-and-innovation.ec.europa.eu/funding/funding-opportunities/funding-programmes-and-open-calls/horizon-europe/horizon-europe-work-programmes_en

## 4. EIC Accelerator — percorso successivo, non configurazione iniziale

EIC Accelerator è orientato a startup/PMI con innovazioni ad alto rischio e potenziale di mercato, per attività tipicamente **TRL 6–8**.

Nel programma di lavoro 2026:

- componente di sovvenzione inferiore a **€2,5 milioni**;
- attività di innovazione TRL 6–8;
- possibile componente di investimento separata secondo le condizioni EIC.

Per CTT-PAA ha senso solo quando esiste già una tecnologia sufficientemente matura, differenziata e scalabile oltre il singolo sito operativo.

Fonte ufficiale:
https://eic.ec.europa.eu/eic-funding-opportunities/eic-accelerator_en

Stato: `CANDIDATO-FUTURO-PER-CRESCITA`.

## 5. Nessuna doppia contabilizzazione

La stessa spesa non deve essere caricata contemporaneamente come:

- CAPEX del progetto agricolo;
- costo di un altro incentivo;
- costo Horizon/EIC;

salvo combinazioni espressamente consentite dalle regole applicabili e senza doppio finanziamento dello stesso costo.

La matrice finanziaria definitiva deve riportare almeno:

| Voce | Progetto principale | R&S | Programma | Quota/criterio | Evidenza | Stato |
|---|---|---|---|---|---|---|
| server di prova | sì, in parte | possibile | DA BANDO | DA REGOLA | registro uso/configurazione | DA VERIFICARE |
| sviluppo pianificatore | no | sì | candidato Horizon | DA BANDO | ore/risultati | DA VERIFICARE |
| serra produttiva | sì | no | — | — | CAPEX principale | PRINCIPALE-NON-RND |

## 6. Verifica economica

Prima di usare un bando nel flusso di cassa:

1. tema identificato;
2. soggetto beneficiario eleggibile;
3. ruolo nel consorzio definito;
4. categoria di costo verificata;
5. percentuale di finanziamento verificata;
6. cofinanziamento disponibile;
7. tempi di anticipi/pagamenti compatibili;
8. assenza di doppio finanziamento;
9. trattamento IVA verificato;
10. nessun costo principale reso dipendente dall'esito del bando.

Fino a quel momento: **contributo = €0 nelle fonti certe del progetto principale**.
