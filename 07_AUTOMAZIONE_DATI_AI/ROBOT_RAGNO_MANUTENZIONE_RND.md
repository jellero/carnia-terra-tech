# Robot "ragno" per ispezione e manutenzione in quota — R&S

**Aggiornato:** 18 settembre 2026  
**Stato:** `R&S PRIORITARIA / NON SOSTITUISCE ACCESSO UMANO CERTIFICATO`

## 1. Obiettivo

Ridurre esposizione delle persone al lavoro in quota e rendere più frequenti ispezione e manutenzione preventiva delle parti alte della serra.

Il "ragno" è distinto dalla PLE cingolata detta commercialmente "ragno".

- **PLE/piattaforma:** capacità umana certificata, parte del core operativo.
- **robot ragno:** sistema autonomo/semi-autonomo di ispezione/manutenzione, R&S prioritaria.

Il progetto non dipende dal successo del robot.

## 2. Evidenza tecnologica

Nel 2026 sono stati pubblicati lavori su robot autonomi dedicati alla pulizia di coperture di serre multispan, con prototipi e valutazioni sperimentali.

Questo dimostra che:
- locomozione e pulizia automatizzata su coperture di serra sono un campo tecnico reale;
- esistono architetture leggere dedicate;
- pulizia e monitoraggio della trasmittanza possono essere automatizzati.

Non dimostra:
- compatibilità con la struttura Carnia TerraTech;
- compatibilità con il film scelto;
- sicurezza su neve/vento/pioggia locali;
- possibilità di eseguire riparazioni generiche;
- maturità commerciale sufficiente per un acquisto P1.

Fonti:
- Scientific Reports 2026, robot autonomo per pulizia tetto serra;
- Smart Agricultural Technology 2026, robot fotovoltaico per tetti multispan;
- Journal of Field Robotics, review su robot di pulizia coperture serre.

Riferimenti completi:
`../22_FONTI_NORME_PREVENTIVI/ROBOT_RAGNO_MANUTENZIONE_SOURCES.md`.

## 3. Principio architetturale

Non progettare un robot che "si arrangia" su una struttura non pensata per lui.

Ordine preferito:

1. **interfaccia di manutenzione progettata nella serra**;
2. robot leggero e recuperabile;
3. navigazione confinata;
4. utensili semplici;
5. autonomia crescente solo dopo prove.

Possibili interfacce da valutare col costruttore strutturale:
- binario dedicato;
- guida lungo gronda/elemento strutturale;
- punti di ancoraggio/recovery;
- cavo di sicurezza;
- docking laterale;
- passaggi predisposti.

**Nessuna guida o carico aggiuntivo viene inserito sulla serra senza verifica strutturale.**

## 4. Divieto fondamentale

Il robot non deve assumere che il film di copertura sia una superficie portante.

Se una soluzione commerciale/scientifica si muove direttamente sulla copertura:
- carico di contatto;
- deformazione;
- abrasione;
- perforazione;
- compatibilità chimica;
- temperatura;
- vento;
- acqua;

devono essere esplicitamente validati sul sistema di copertura scelto.

Preferenza Carnia:
**scaricare i carichi sugli elementi strutturali progettati, non sul film, quando tecnicamente possibile.**

## 5. Roadmap R0–R4

### R0 — predisposizione
Durante progettazione serra:
- mappa punti alti;
- punti non raggiungibili da terra;
- possibili guide/ancoraggi;
- corridoi di recupero;
- alimentazione/dati eventuali;
- docking;
- interfaccia con PLE.

Costo basso e infrastruttura passiva, solo se approvata strutturalmente.

### R1 — ispezione
Primo robot utile:
- RGB;
- zoom;
- termica dove utile;
- profondità/distanza;
- illuminazione;
- posizione;
- immagini ripetibili.

Use case:
- film/fissaggi;
- gronde;
- aperture;
- attuatori;
- reti;
- schermi visibili;
- ventilatori;
- cablaggi;
- infiltrazioni;
- accumuli/sporco.

Obiettivo:
**trovare il problema prima che richieda emergenza in quota.**

### R2 — pulizia semplice
Solo dopo R1:
- pulizia copertura dove compatibile;
- pulizia gronde;
- rimozione sporco leggero;
- pulizia sensori/ottiche accessibili.

Acqua/brush/wiper solo con verifica copertura e drenaggio.

### R3 — manutenzione assistita
Utensili semplici e confinati:
- ispezione ravvicinata;
- pulizia;
- piccole operazioni ripetibili;
- eventuale lubrificazione solo dove ammessa dal costruttore;
- azionamento di punti predisposti.

### R4 — manipolazione avanzata
Solo R&S successiva:
- sostituzione piccoli componenti;
- interventi su attuatori;
- manipolatore.

Nessun intervento autonomo su elemento strutturale safety-critical senza procedura e supervisione adeguate.

## 6. Sicurezza

Guasti critici:
- caduta robot/pezzo;
- perdita aderenza;
- blocco in quota;
- batteria esaurita;
- perdita rete;
- vento;
- pioggia/condensa;
- urto copertura;
- danneggiamento film;
- caduta utensile;
- avvio con persone sotto.

Mitigazioni:
- massa minima;
- ritenuta/recovery indipendente dove possibile;
- geofencing fisico/logico;
- no-go meteo;
- area sottostante segregata;
- stop locale;
- nessuna dipendenza cloud;
- ritorno/docking degradato;
- procedura recupero con PLE.

## 7. Recovery

Un robot in quota che non può essere recuperato senza intervento improvvisato è un rischio aggiunto.

Prima del pilot deve esistere:
- punto di recupero;
- metodo manuale;
- accesso PLE;
- isolamento elettrico;
- possibilità di traino/rientro;
- procedura per robot bloccato;
- limite massimo di vento/meteo per recovery.

## 8. KPI

### R1 ispezione
- % area critica osservabile;
- difetti rilevati;
- falsi positivi;
- qualità immagine;
- tempo giro;
- interventi umani;
- ore in quota evitate;
- recovery events.

### R2 pulizia
- m²/h;
- L/m²;
- Wh/m²;
- variazione trasmittanza;
- usura film;
- qualità pulizia;
- ore uomo evitate.

### R3 manutenzione
- % attività completate;
- tempo/attività;
- errore;
- interventi umani;
- utensili persi: 0;
- eventi safety: 0.

## 9. Gate R&S

### RG0
Costruttore serra conferma geometria e carichi disponibili.

### RG1
Mock-up a terra della sezione strutturale.

### RG2
Robot tethered/confinato su mock-up inclinato.

### RG3
Pilot su una campata non produttiva o zona segregata.

### RG4
Ispezione estesa.

### RG5
Solo dopo dati: utensile/pulizia/manutenzione.

## 10. Relazione con CAPEX core

Core P1 finanzia:
- accessibilità;
- eventuali predisposizioni passive a basso costo;
- piattaforma/PLE necessaria;
- recovery.

Il robot ragno:
- non è incluso automaticamente nel budget core €950k;
- può usare fondi R&S dedicati;
- può entrare nel CAPEX futuro solo dopo pilot e business case.

## 11. Decisione attuale

**R&S prioritaria: SÌ.**

Ordine:
1. progettare la serra perché sia manutenibile;
2. garantire accesso umano certificato;
3. predisporre interfacce compatibili col robot se convenienti;
4. sviluppare/validare R1 ispezione;
5. solo dopo, pulizia/manutenzione attiva.

Questa R&S ha priorità superiore ai robot di servizio non essenziali perché agisce direttamente su rischio, manutenzione e qualità della vita.
