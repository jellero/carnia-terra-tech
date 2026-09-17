# BOM-002 — Schermi termici / ombreggianti serra

**Aggiornato:** 17 settembre 2026  
**Ambito iniziale:** C1 pomodoro, C2 peperone, C6 basilico/vivaio/jolly = **~2.100 m² nominali di area a terra**.  
**Stato:** `CANDIDATI REALI / SISTEMA COMPLETO DA PREVENTIVARE`.

> Nota quantità: i 2.100 m² sono area nominale dei tre comparti. La superficie di telo da ordinare NON coincide automaticamente con l'area a terra: dipende da campate, geometria, sovrapposizioni, pieghe, overhang/pelmet e sistema di trazione. Quantità definitiva solo da shop drawing del fornitore.

## 1. Funzioni richieste

Il sistema deve poter contribuire a:

- riduzione delle perdite radiative e convettive notturne;
- riduzione del volume termicamente attivo quando previsto dalla strategia climatica;
- protezione da eccesso di radiazione;
- diffusione della luce quando utile;
- gestione dell'umidità senza creare condensa incontrollata;
- riduzione del carico termico estivo;
- gestione indipendente almeno dei comparti C1, C2 e C6;
- integrazione con PLC locale e logiche fail-safe.

## 2. Regola di progetto

Non viene scelto un unico telo prima di avere:

- clima del lotto reale;
- copertura serra definitiva;
- aperture laterali/zenitali;
- strategia termica;
- cultivar e calendari;
- verifica del rischio surriscaldamento/umidità;
- costo installato comparabile.

La scelta sarà tra uno o due livelli di schermo. Un singolo telo trasparente massimizza il risparmio energetico ma offre poca ombreggiatura; un telo aperto diffondente/ombreggiante offre raffrescamento e passaggio aria ma meno isolamento. Un doppio sistema aumenta prestazioni e flessibilità ma anche CAPEX, manutenzione e carico strutturale.

## 3. Candidati tessuto — energia trasparente

### A — Ridder RES 10+ FR (5 mm)

**Classificazione:** `CANDIDATO / PREZZO DA PREVENTIVO`.

- uso: interno;
- funzione principale: energy saving;
- flame retardant: sì;
- ombreggiamento luce diretta: 11%;
- ombreggiamento luce diffusa: 20%;
- energy saving dichiarato: 49%;
- struttura traspirante per trasporto umidità;
- adatto a colture rampicanti e climi freddi secondo produttore.

Fonte: https://ridder.com/res-10-fr-5mm

**Prezzo:** non pubblicato dal produttore; richiedere prezzo €/m², taglio/cucitura, sfrido, trasporto e posa.

### B — Svensson LUXOUS 1147 FR

**Classificazione:** `CANDIDATO / PREZZO DA PREVENTIVO`.

- uso: interno;
- sistema: hanging/sliding;
- flame retardant: sì;
- ombreggiamento diretto: 15% NEN 2675 / 11% metodo Svensson;
- ombreggiamento diffuso: 25% NEN 2675 / 19% metodo Svensson;
- energy saving dichiarato: 47%;
- peso dichiarato: 57 g/m²;
- garanzia dichiarata: 5 anni.

Fonte: https://www.ludvigsvensson.com/en-us/climate-technologies/product/luxous-1147-2675

Il webshop Huisman elenca diversi tessuti Svensson con prezzo **on request**, confermando che per questa classe di prodotto il costo corrente va chiesto a preventivo:
https://webshop.huismanscreensystems.com/en/producten-schermdoek/

## 4. Candidati tessuto — ombreggiamento/diffusione aperto

### C — Ridder RLD 45 FR O

**Classificazione:** `CANDIDATO / PREZZO DA PREVENTIVO`.

- uso: interno;
- struttura aperta;
- flame retardant: sì;
- ombreggiamento diretto: 46% metodo Ridder;
- ombreggiamento diffuso: 50% metodo Ridder;
- energy saving: 18%;
- compatibile con ventilazione zenitale secondo produttore;
- alto livello di diffusione della luce.

Fonte: https://ridder.com/rld-45-fr-o

### D — Svensson HARMONY 5220 O FR

**Classificazione:** `CANDIDATO / PREZZO DA PREVENTIVO`.

- uso: interno;
- struttura aperta;
- flame retardant: sì;
- ombreggiamento diretto: 59% NEN 2675 / 52% metodo Svensson;
- ombreggiamento diffuso: 63% NEN 2675 / 56% metodo Svensson;
- energy saving: 20%;
- peso: 60 g/m²;
- garanzia dichiarata: 5 anni.

Fonte: https://www.ludvigsvensson.com/en-us/climate-screens/product/harmony-5220-o-fr

Prezzo: `PREZZO DA PREVENTIVO`; Huisman lo elenca come "Price: On request".

## 5. Scenari da quotare

Per evitare di scegliere il sistema prima dei dati climatici, l'RFQ dovrà chiedere almeno tre scenari confrontabili.

### Scenario S1 — energy-first

Un solo livello trasparente FR nei tre comparti C1/C2/C6, con candidato RES 10+ FR o LUXOUS 1147 FR.

Obiettivo: massimizzare risparmio energetico e trasmissione della luce.

### Scenario S2 — climate/shade-first

Un solo livello aperto diffondente/ombreggiante FR nei tre comparti, con candidato RLD 45 FR O o HARMONY 5220 O FR.

Obiettivo: ridurre picchi radiativi mantenendo ventilazione attraverso lo schermo.

### Scenario S3 — doppio schermo

Un livello energy screen + un livello shade/diffusion screen, indipendenti.

Obiettivo: massima flessibilità stagionale e climatica. Deve essere quotato separatamente perché richiede doppia meccanica/guide o architettura compatibile e aumenta i carichi sospesi.

## 6. Motorizzazione e trasmissione

### Ridder RW45 — famiglia candidata

Ridder dichiara per la famiglia RW45:

- coppie fino a 120 Nm;
- 1–5 rpm a 50 Hz secondo variante;
- trasmissione a vite senza fine autobloccante;
- finecorsa lineare integrato;
- motori IP55;
- versioni 230 V monofase e 400 V trifase;
- opzione feedback posizione RPU.

Fonte tecnica: catalogo Ridder Drive Systems.

**Benchmark retail trovato:** Ridder RW45 230 V single-drum drive, SKU 531110, 0,09 kW, 120 Nm — **£598,00**, 2 pezzi indicati disponibili al momento della verifica. Il prezzo non specifica chiaramente nel risultato indicizzato il regime IVA e la configurazione single-drum non è automaticamente quella corretta per il nostro screen system.

Fonte prezzo: https://saltelectricalshop.co.uk/product/ridder-rw45-230v-ac-single-drum-drive/

**Classificazione:** `PREZZO TROVATO — SOLO BENCHMARK MOTORE / CONFIGURAZIONE DA VALIDARE`.

Working quantity se un motore indipendente per comparto risultasse sufficiente dal calcolo:

- 3 motori operativi;
- possibile 1 unità di scorta solo se stessa variante su tutti i comparti e lead time lo giustifica;
- benchmark 3 pezzi: £1.794;
- benchmark 4 pezzi: £2.392;
- trasporto, IVA/dazi, staffe, trasmissione e controllo esclusi.

### Finecorsa/ricambio RW45

Salt Electrical elenca anche un limit switch set Ridder RW45 4 A, SKU 501105, **£70,00**, con disponibilità indicata 10 pezzi alla verifica.

Fonte: https://saltelectricalshop.co.uk/product/ridder-rw45-drive-limit-set-4-amp/

**Classificazione:** `PREZZO TROVATO — RICAMBIO CANDIDATO / COMPATIBILITÀ DA VERIFICARE`.

## 7. Meccanica da quotare separatamente

Per ogni livello di schermo e comparto il preventivo deve separare almeno:

| Codice | Voce | Quantità | Stato costo |
|---|---|---:|---|
| SCR-TEX | telo climatico | da shop drawing | PREZZO DA PREVENTIVO |
| SCR-OVH | overhang/pelmet per tenuta perimetrale | da geometria | PREZZO DA PREVENTIVO |
| SCR-SUP | fili/monofilamenti di supporto | da campate/passo | PREZZO DA PREVENTIVO |
| SCR-GUI | fili/cavi guida inferiori/superiori | da sistema | PREZZO DA PREVENTIVO |
| SCR-LEAD | profilo/barra bordo mobile | 1 set per sezione | PREZZO DA PREVENTIVO |
| SCR-SHAFT | albero/tubo di trasmissione | da layout | PREZZO DA PREVENTIVO |
| SCR-RACK | cremagliere/pignoni o push-pull | da layout | PREZZO DA PREVENTIVO |
| SCR-BRG | cuscinetti/supporti albero | da passo | PREZZO DA PREVENTIVO |
| SCR-MOT | motoriduttore | working 1/comparto/livello | PREZZO DA PREVENTIVO |
| SCR-LIM | finecorsa/posizione | 1 set/motore | PREZZO DA PREVENTIVO |
| SCR-BRK | staffe e piastre | da layout | PREZZO DA PREVENTIVO |
| SCR-TEN | tensionatori/molle | da sistema | PREZZO DA PREVENTIVO |
| SCR-CLP | clips/ganci/occhielli | da sistema | PREZZO DA PREVENTIVO |
| SCR-HDW | bulloneria/minuteria | distinta completa | PREZZO DA PREVENTIVO |
| SCR-ISO | sezionatore locale | 1/motore | PREZZO DA PREVENTIVO |
| SCR-PROT | protezione motore/contattori | 1/motore | PREZZO DA PREVENTIVO |
| SCR-CAB | cavi potenza/segnale | metri da layout | PREZZO DA PREVENTIVO |
| SCR-PLC | I/O/interfaccia PLC | per zona | verificare riuso I/O previsti |
| SCR-LAB | posa e tensionamento | ore/forfait separato | PREZZO DA PREVENTIVO |
| SCR-COM | commissioning | 1 lotto | PREZZO DA PREVENTIVO |
| SCR-SP | ricambi iniziali | 1 lotto | PREZZO DA PREVENTIVO |

## 8. Controllo e sicurezza

Ogni zona deve prevedere:

- comando automatico PLC;
- comando locale manutenzione;
- finecorsa indipendenti;
- protezione sovraccarico;
- feedback posizione, preferibile reale e non solo temporizzato;
- allarme mancato movimento;
- procedura manuale di apertura/chiusura in guasto quando tecnicamente possibile;
- interblocco con altre apparecchiature se necessario;
- comportamento definito in blackout;
- posizione di sicurezza definita per stagione/evento.

Il server/cloud non è nel loop vitale.

## 9. Carichi strutturali e interfacce

Prima dell'ordine il progettista della serra deve ricevere:

- peso telo per m²;
- peso fili/profili/alberi/motori;
- carichi dinamici del sistema di trazione;
- punti di reazione/ancoraggio;
- eventuale secondo livello futuro;
- carichi manutentivi.

La predisposizione C3–C5 deve essere valutata subito perché aggiungere in seguito punti strutturali, alberi o spazi può essere molto più costoso.

## 10. Manutenzione e ricambi

Piano minimo:

- ispezione tensione fili/cavi;
- controllo clips e profili;
- controllo allineamento cremagliere/push-pull;
- prova finecorsa;
- prova sovraccarico;
- pulizia telo secondo produttore;
- verifica strappi/usura;
- verifica cuscinetti/supporti;
- prova manual override;
- storico ore/cicli motore.

Ricambi candidati a stock:

- limit switch compatibile;
- clips/ganci;
- tensionatori/molle;
- tratto di telo o kit riparazione compatibile;
- bulloneria specifica;
- eventualmente un motoriduttore comune se lead time e standardizzazione lo giustificano.

## 11. Stato economico attuale

Oggi non esiste un **totale affidabile** della BOM-002 perché i componenti economicamente dominanti — tessuto, meccanica completa e posa — sono a preventivo e la quantità reale dipende dalla geometria della serra.

Questo non è un buco da coprire con una stima arbitraria: il sistema è ora sufficientemente specificato per chiedere offerte confrontabili.

Prima di promuovere la BOM a `VALIDATO` servono almeno:

1. shop drawing serra;
2. carichi ammessi e punti di supporto;
3. simulazione/strategia clima per C1/C2/C6;
4. 2–3 offerte complete;
5. confronto S1/S2/S3;
6. CAPEX installato;
7. consumo elettrico/cicli;
8. manutenzione e ricambi;
9. verifica incendio e conformità del sistema completo;
10. compatibilità contributi.
