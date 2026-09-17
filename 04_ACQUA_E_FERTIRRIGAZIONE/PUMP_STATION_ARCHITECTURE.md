# Stazione pompe irrigazione 1+1 — architettura e criteri

**Aggiornato:** 17 settembre 2026  
**Stato:** `ARCHITETTURA DEFINITA / TAGLIA BLOCCATA DA Q-H, FONTE E CONTROLAVAGGIO`.

## 1. Funzione

La stazione deve fornire pressione e portata stabili a filtrazione fine, fertirrigazione e distribuzione, garantendo continuità con una pompa fuori servizio.

La definizione `1+1` significa **due pompe da 100% del duty point richiesto**, salvo decisione esplicita di accettare una modalità degradata. Due pompe che devono funzionare insieme per raggiungere il punto di progetto sono `2×50%`, non 1+1.

## 2. Sequenza idraulica

Con accumulo atmosferico la sequenza preferenziale da verificare è:

`tank 300 m³ -> presa aspirazione / griglia grossolana -> collettore aspirazione -> P1/P2 1+1 -> filtrazione fine pressurizzata -> fertirrigazione -> distribuzione`

L'idrociclone può stare sul lato pressurizzato quando richiesto. Se la fonte è un pozzo con propria pompa o rete già pressurizzata, la sequenza può cambiare.

**Correzione rispetto al working precedente:** un filtro automatico che richiede 1,5–2,8 bar per il controlavaggio non può essere assunto a monte delle pompe quando la fonte è un serbatoio atmosferico senza pressione sufficiente.

## 3. Duty point

Il punto di lavoro non è ancora fissato.

Per ogni scenario calcolare:

`Htot = Hstatica + Hfiltri + Hfertirrigazione + Htubi/valvole + Hsettore + margine controllo`

Scenari minimi:

- P1 — irrigazione normale al massimo numero di settori simultanei;
- P2 — irrigazione + controlavaggio filtro, se ammesso simultaneamente;
- P3 — flush linee/collettori;
- P4 — modalità degradata con un ramo filtro escluso;
- P5 — emergenza, sola irrigazione comparti prioritari.

La pressione all'emettitore più sfavorito deve restare nel range del gocciolatore scelto. Nessuna prevalenza si seleziona dalla sola pressione nominale del filtro.

## 4. Aspirazione e NPSH

Preferenza: **aspirazione allagata** dal serbatoio, con pompe poste sotto o vicino al livello minimo utile quando il masterplan lo consente.

Verificare:

- livello minimo e massimo tank;
- quota asse pompa;
- lunghezza/DN aspirazione;
- temperatura acqua;
- perdite valvole/raccordi/griglia;
- pressione atmosferica sito;
- NPSHr della pompa al Q reale;
- margine NPSH;
- vortici e ingresso aria nel tank.

Ogni pompa deve avere isolamento indipendente. Evitare filtri fini in aspirazione; solo griglia/strainer grossolano se necessario e dimensionato con Δp basso.

## 5. Architettura 1+1

Per ogni pompa:

`collettore aspirazione -> valvola isolamento -> pompa -> non ritorno -> valvola isolamento -> collettore mandata`

Requisiti:

- una pompa duty, una standby;
- alternanza automatica per ore/cicli;
- test periodico della standby;
- partenza automatica standby su guasto duty o pressione non raggiunta;
- possibilità di selezione manuale `AUTO / OFF / MANUALE`;
- nessuna dipendenza da cloud/server;
- ogni pompa e inverter isolabili senza fermare l'altra.

## 6. VFD

Preferenza: **1 VFD per pompa**.

Un unico inverter condiviso è un single point of failure e viene accettato solo se il TCO lo giustifica e il bypass elettrico è documentato.

Controllo pressione:

- trasmettitore principale 4–20 mA;
- secondo trasmettitore o pressostato indipendente per plausibilità/sicurezza;
- PID nel VFD o PLC locale;
- limite frequenza minima secondo pompa;
- anti-cycling;
- overpressure trip;
- low-pressure/no-flow alarm.

## 7. Candidati di classe

### Grundfos CR 10-6

Benchmark reale disponibile:

- Q nominale ~10 m³/h;
- H nominale ~48,3 m;
- H max ~61,2 m;
- motore 2,2 kW trifase;
- Pmax 16 bar;
- parti idrauliche inox AISI 304, testa/base in ghisa;
- prezzo retail IT osservato: **€1.946,78 IVA 22% inclusa/cad**;
- stato: `PREZZO TROVATO / CANDIDATO DI CLASSE, NON SELEZIONATO`.

Due corpi pompa: ~€3.893,56 IVA inclusa, prima di VFD, valvole, skid, collettori, sensori e quadro.

### Grundfos CR 5-8

Classe inferiore di portata, utile se il duty reale risultasse più basso:

- famiglia CR 5;
- motore tipico 2,2 kW per CR5-8 nella documentazione corrente;
- benchmark retail UE ~€1.291 per versione trifase osservata;
- da verificare codice esatto, curva e IVA/trasporto.

### Hydro Multi-E 2 CRE

Gruppo OEM integrato con due pompe elettroniche.

Listino Grundfos 2026 riporta, tra gli altri:

- Hydro Multi-E 2 CRE 10-3 U2: **€12.185 listino**;
- Hydro Multi-E 2 CRE 10-5 U2: **€13.323 listino**.

IVA/condizioni commerciali da confermare. È benchmark di soluzione integrata, non scelta.

## 8. VFD benchmark

Danfoss VLT Micro Drive FC-51 2,2 kW, 380–480 V 3~:

- RS Italia: **€895,30 + IVA/cad** per codice 132F0022;
- altri distributori UE mostrano prezzi inferiori, ma per budget usare un benchmark prudente finché non esiste RFQ;
- 2 unità RS: ~€1.790,60 + IVA.

Il VFD definitivo deve essere dimensionato sulla corrente di targa e sul regime del motore selezionato, non sui soli kW.

## 9. Strumentazione

Minimo:

- manometro aspirazione/vuoto dove utile;
- manometro mandata;
- trasmettitore pressione mandata principale;
- ridondanza sensore/pressostato;
- flow meter centrale coordinato BOM-013;
- livello minimo tank hardwired o safety PLC/local logic;
- stato VFD/pompa;
- energia elettrica per pompa/ramo;
- Δp filtrazione da BOM-014.

Benchmark sensori:

- WIKA A-10 0–10 bar, 4–20 mA: **da €133,95 + IVA** nello shop WIKA; retail RS ~€151,36 + IVA;
- Danfoss MBS 3000 0–10 bar, 4–20 mA, IP65: ~**€195,44 + IVA** presso TME.

## 10. Vaso autoclave / smorzamento

Non è automaticamente necessario un grande vaso con VFD. Valutare 50–100 l per:

- smorzare transitori;
- limitare micro-avviamenti a bassissima domanda;
- stabilizzare il PID;
- proteggere da piccoli colpi d'ariete.

Benchmark Zilmet Ultra-Pro 100 l, 10 bar: listino/retail corrente circa **€475** nella fonte 2026 osservata; prezzo e configurazione da RFQ. Non viene usato come accumulo d'acqua di processo.

## 11. Protezioni

Obbligatorie o da verificare:

- livello basso tank / marcia a secco;
- pressione alta mandata;
- pressione insufficiente;
- assenza portata con pompa comandata;
- sovracorrente/temperatura VFD;
- perdita fase/alimentazione;
- valvola mandata chiusa / dead-head;
- non ritorno guasto/backspin;
- allarme cavitazione da segnali indiretti e ispezione;
- perdita acqua/skid.

Valvola di sicurezza/relief solo se necessaria in base a shut-off head, Pmax componenti e possibili modalità di guasto.

## 12. Failover

Sequenza minima:

1. duty richiesta;
2. verifica livello e interlock;
3. avvio VFD e rampa;
4. verifica incremento pressione/portata;
5. se fault o target non raggiunto: arresto/isolamento logico duty;
6. avvio standby;
7. allarme manutenzione;
8. se entrambe indisponibili: priorità irrigazione manuale/emergenza e allarme critico.

L'alternanza deve impedire che la pompa standby resti ferma per mesi senza test.

## 13. Manutenzione e ricambi

Richiedere BOM ricambi e lead time di:

- tenuta meccanica;
- motore/cuscinetti se separabili;
- ventola VFD e componenti soggetti a usura;
- trasmettitore pressione;
- pressostato;
- valvola di ritegno/guarnizioni;
- kit tenute valvole;
- fusibili/protezioni;
- VFD completo come ricambio opzionale in funzione SLA.

Registrare ore pompa, avviamenti, kWh, pressione, portata, allarmi e vibrazioni/anomalie.

## 14. Gate

BOM-015 diventa ordinabile solo con:

1. portata simultanea reale da BOM-013;
2. Q/P controlavaggio BOM-014;
3. quota e geometria tank/tech barn;
4. fonte acqua e livello minimo;
5. P richiesta a valle fertirrigazione;
6. perdite filtri, dosaggio, tubi e valvole;
7. NPSHa/NPSHr;
8. decisione 100%+100% vs degradato;
9. selezione CR/Lowara/equivalenti con curve certificate;
10. scelta VFD/control architecture;
11. P&ID/elettrico;
12. RFQ almeno due fornitori;
13. commissioning con test failover reale.