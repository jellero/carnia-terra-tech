# Accumulo acqua 300 m³ — architettura e criteri

**Aggiornato:** 17 settembre 2026  
**Stato:** `ARCHITETTURA DEFINITA / 2×150 m³ BASELINE DA VALIDARE / VOLUME FINALE BLOCCATO DA BILANCIO IDRICO E LOTTO`.

## 1. Obiettivo

Accumulo atmosferico per acqua irrigua e piovana, indipendente dal cloud, manutenibile senza fermare completamente l'azienda e predisposto all'espansione.

Baseline di confronto:

- **300 m³ nominali totali**;
- preferenza iniziale **2 × 150 m³** indipendenti;
- predisposizione fisica/idraulica a **400–500 m³** se il bilancio idrico lo richiede.

Prima dell'ordine distinguere esplicitamente `volume nominale` da `volume utile`. Se l'obiettivo diventa 300 m³ realmente prelevabili, il volume geometrico installato deve compensare freeboard, fondo non aspirabile e volume morto.

## 2. Bilancio idrico

Working peak storico del progetto: **30–35 m³/giorno**, ancora da validare agronomicamente.

Autonomia teorica a 300 m³ pieni:

- 30 m³/giorno -> **10,0 giorni**;
- 35 m³/giorno -> **8,6 giorni**.

Volumi teorici per sola autonomia, prima di margini e reintegro:

- 10 giorni -> 300–350 m³;
- 14 giorni -> 420–490 m³;
- 15 giorni -> 450–525 m³;
- 21 giorni -> 630–735 m³.

Quindi 300 m³ è un buon **primo stadio**, non una prova di autosufficienza.

## 3. Captazione pioggia

Con circa 4.200 m² nominali di copertura serra:

`V [m³] = pioggia [mm] × area [m²] / 1000 × coefficiente di resa`

Ordine di grandezza:

- 1 mm -> 4,2 m³ teorici;
- 300 m³ -> 71,4 mm a resa 100%;
- 300 m³ -> ~84 mm a resa 85%.

La portata di troppo-pieno non si dimensiona sui 300 m³, ma sulla pioggia di progetto del lotto e sulla superficie realmente captata:

`Qroof [m³/h] = i [mm/h] × A [m²] / 1000 × C`.

RainMap FVG/BOM-007 fornisce l'intensità di progetto quando avremo coordinate e tempo di ritorno.

## 4. Architettura baseline S1 — 2×150 m³ rigidi con liner

Preferenza progettuale iniziale:

- due tank atmosferici indipendenti;
- struttura zincata/verniciata o soluzione equivalente professionale;
- liner sostituibile e compatibile con acqua irrigua;
- copertura opaca anti-alga/insetti;
- ingressi, uscite, overflow e scarichi indipendenti;
- collettore comune con valvole di isolamento;
- possibilità di funzionare con un solo tank durante manutenzione dell'altro;
- predisposizione terzo tank o espansione volume.

Non tenere i due serbatoi permanentemente equalizzati senza possibilità di isolamento: una perdita o contaminazione non deve svuotare/contaminare entrambi.

## 5. Alternative da RFQ

### S2 — 3×100 m³

Vantaggi: maggiore granularità e manutenzione. Svantaggi: più valvole, collegamenti, fondazioni, footprint e punti di perdita.

### S3 — 1×300 m³

Potenzialmente minor costo specifico e meno accessori, ma **single point of failure**; pulizia/ispezione richiedono fermo o accumulo alternativo. Non baseline.

### S4 — 2×150 m³ bladder flessibili

Vantaggi: CAPEX basso, chiuse, montaggio rapido. Svantaggi: footprint elevato, protezione meccanica, accesso/diagnostica più difficili, rischio puntura/abrasione, gestione base e riparazione.

### S5 — GRP/modulare

Interessante se layout edilizio o forma rettangolare sono decisivi. Prezzo europeo per 150 m³ generalmente da RFQ; non assumere equivalenza economica con tank agricoli a liner.

## 6. Benchmark di mercato

### Bladder 150 m³ — Labaronne Citaf

Annuncio 2026:

- 150.000 L;
- nuovo;
- **€4.270 + IVA**;
- consegna indicata **€1.000 + IVA** nell'annuncio, da confermare per destinazione e quantità;
- disponibilità ricambi dichiarata 10 anni.

Due unità: **€8.540 + IVA di solo hardware**, prima di base, collegamenti, protezioni e installazione.

### Steel tank — benchmark europeo

Agroinform, aggiornato luglio 2026:

- 81 m³: €3.910 + IVA;
- 200 m³: **€6.630 + IVA**;
- 356 m³: €9.280 + IVA;
- 473 m³: €11.300 + IVA;
- trasporto e installazione esclusi.

ABEKO 200 m³ utili:

- tank zincato + liner PVC 0,75 mm + floor mat;
- volume utile pubblicato 200 m³;
- **€7.807 + IVA**;
- copertura telo +€725 + IVA;
- trasporto/installazione da verificare.

**Nota critica:** un prodotto ABEKO denominato commercialmente “150 m³” pubblica volume utile di soli **112 m³**. Nel progetto si usa sempre il **volume utile dichiarato**, non il nome commerciale.

### Steel 150.000 L — benchmark UK

Tanks Direct pubblica 150.000 L, Ø ~9,14 m, h ~2,29 m, **£4.650 ex VAT**. È benchmark estero in GBP, non prezzo di budget italiano.

### Inox 150 m³

Usato AISI 304 osservato a **€32.300 + IVA**: utile solo per dimostrare l'ordine di grandezza di una soluzione sovraqualificata; non baseline per acqua irrigua.

## 7. Footprint e fondazione

Un tank cilindrico Ø9,14 m occupa ~65,6 m². Con 150 m³ d'acqua il solo carico idrostatico medio sul footprint è circa **2,29 t/m² / 22,4 kPa**, prima del peso del tank e degli effetti locali.

Una bladder 14,0×8,88 m occupa ~124,3 m² e porta mediamente ~1,21 t/m², ma richiede superficie molto più ampia e perfettamente protetta.

Fondazione/base da progettare con:

- geotecnica del lotto;
- tolleranza planarità del costruttore;
- drenaggio perimetrale;
- gelo/erosione;
- carichi locali del bordo e degli ancoraggi;
- eventuale sisma/vento per struttura e copertura;
- accesso per montaggio e sostituzione liner.

Non fissare platea o spessore prima del manuale OEM e della geotecnica.

## 8. Idraulica di ogni tank

Ogni serbatoio deve avere almeno:

- ingresso pioggia/fonte isolabile;
- ingresso con diffusione/calming per non risospendere sedimenti;
- overflow passivo a quota sicura;
- protezione insetti/fauna dove compatibile con la sezione richiesta;
- presa di processo sopra il fondo;
- scarico di fondo dedicato;
- valvola isolamento;
- punto campionamento;
- possibilità di drenaggio completo controllato;
- sfiato adeguato;
- accesso/ispezione secondo OEM.

Il troppo-pieno deve funzionare con blackout, PLC guasto e serbatoio pieno.

## 9. Qualità acqua

Baseline:

- first flush/pre-screen coordinati con BOM-007;
- copertura opaca per limitare luce/alghe;
- nessun dosaggio chimico permanente nel tank come default;
- campionamento periodico;
- sedimenti rimossi con procedura;
- trattamento fine resta BOM-014/BOM-016;
- nessuna connessione che possa contaminare la rete potabile.

Riferimento normativo di progetto per uso pioggia non potabile: **UNI EN 16941-1:2024**, in vigore dal 18 aprile 2024, oltre a obblighi locali/nazionali applicabili.

## 10. Livelli e automazione

Per tank:

- misura continua non-contact preferenziale;
- low-low indipendente per protezione pompe;
- high-high indipendente per blocco riempimento controllato;
- allarme rate-of-level-change anomalo per perdita;
- trend volume stimato;
- PLC locale.

Il low-low vitale non deve dipendere dal solo radar né dal cloud.

## 11. Interfaccia BOM-015

Preferenza: aspirazione allagata dalle due vasche verso collettore pompe.

Requisiti:

- ogni tank isolabile senza fermare l'altro;
- aspirazioni dimensionate su NPSH e velocità;
- presa sufficientemente alta da evitare sedimento;
- valvole full-bore;
- protezione vortice se necessaria;
- possibilità di lavare una linea aspirazione;
- livello minimo reale usato nel calcolo NPSHa.

## 12. Failure modes

- liner perforato;
- corrosione/cedimento pannello;
- fondazione cede o va fuori piano;
- overflow insufficiente/ostruito;
- ingresso rompe il liner o risospende sedimenti;
- copertura strappata;
- crescita algale;
- sedimenti elevati;
- radar guasto;
- low-low guasto;
- valvola cross-connect lasciata aperta;
- contaminazione di un tank che passa all'altro;
- scarico fondo aperto;
- gelo su raccordi/linee esterne;
- pompa aspira aria/cavita.

Fallback: isolamento tank guasto, esercizio su unità superstite, integrazione da fonte esterna autorizzata, modalità irrigazione prioritaria e riparazione liner/accessori.

## 13. Manutenzione

Registrare:

- volume utile calibrato;
- livelli min/max;
- sedimento;
- qualità acqua;
- integrità liner/copertura;
- bulloneria/struttura;
- overflow e reti;
- valvole e passaparete;
- prove low-low/high-high;
- perdite stimate;
- lavaggi/pulizie;
- ore uomo.

## 14. Gate

BOM-018 diventa ordinabile con:

1. lotto e area disponibile;
2. geotecnica/base;
3. bilancio idrico mensile e picco;
4. fonte primaria/secondaria e portata di reintegro;
5. RainMap e superficie captata reale;
6. decisione 300 m³ nominali vs utili;
7. autonomia target;
8. S1/S2/S3/S4/S5 comparati;
9. materiali/liner/copertura;
10. DN ingressi/overflow/aspirazioni/scarichi;
11. RFQ trasporto + montaggio + fondazioni;
12. piano espansione 400–500 m³;
13. commissioning e prova overflow.
