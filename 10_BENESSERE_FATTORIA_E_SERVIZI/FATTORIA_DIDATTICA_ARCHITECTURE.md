# Architettura fattoria didattica — BOM-027

**Aggiornato:** 18 settembre 2026  
**Stato:** `WORKING ARCHITECTURE / RICONOSCIMENTO ERSA, MASTERPLAN VISITATORI, CAPIENZA E RFQ BLOCCANTI / COSTI UNITARI DISPONIBILI`.

## 1. Obiettivo

Trasformare una parte dell'azienda in un percorso didattico reale, sicuro e accessibile che mostri il funzionamento di Carnia TerraTech senza contaminare o rallentare il core produttivo.

La fattoria didattica deve poter raccontare:

- coltivazione in serra;
- acqua, irrigazione e fertirrigazione;
- energia e fotovoltaico;
- automazione, sensori e robotica;
- post-raccolta e tracciabilità senza ingresso nelle aree food;
- suolo, compost e cicli di materia;
- biodiversità, verde, vite e pergolato;
- galline e benessere animale;
- manutenzione, sicurezza e resilienza dell'azienda.

La visita non deve trasformare le aree tecniche in spazi pubblici. Il principio base è **osservare il processo da un percorso protetto**, entrando nelle aree operative soltanto quando una specifica attività è stata progettata, segregata e supervisionata.

## 2. Requisiti regionali che guidano il progetto

Per il riconoscimento FVG, la documentazione ERSA corrente richiede che l'azienda abbia almeno:

- referente formato mediante percorso riconosciuto;
- assicurazione RC per i rischi connessi alle visite;
- materiale di primo soccorso vicino a una fonte di acqua potabile;
- attrezzature e sostanze pericolose rese inaccessibili;
- aree e attrezzature a rischio delimitate e segnalate;
- spazio per il parcheggio del mezzo che accompagna l'utenza, anche esterno all'azienda purché compatibile con le esigenze dei visitatori;
- servizi igienici adeguati e accessibili;
- accessibilità al luogo di primo soccorso e ad almeno parte dei percorsi didattici, compreso lo spazio coperto;
- spazio coperto per le scolaresche;
- progetto didattico con temi, obiettivi e conduzione pratica;
- domanda e sopralluogo ERSA prima dell'iscrizione nell'Elenco regionale.

La planimetria richiesta da ERSA deve inoltre localizzare:

- particelle interessate;
- parcheggio;
- aree didattiche;
- aree a rischio;
- servizi igienici;
- primo soccorso/acqua potabile;
- percorsi didattici esterni e interni;
- percorsi accessibili e misure adottate per eliminare le barriere.

**Regola di progetto:** queste voci non sono documentazione da preparare alla fine; diventano layer obbligatori del masterplan.

## 3. Dati che NON sono ancora congelati

Non si fissano capienza, numero di servizi o metri di percorso prima di conoscere:

1. lotto reale;
2. posizione accesso pubblico;
3. parcheggio/autobus;
4. spazio coperto effettivamente utilizzabile;
5. percorsi compatibili con logistica agricola;
6. bagni esistenti o da realizzare;
7. progetto didattico;
8. fasce di età e tipologia gruppi;
9. eventuale somministrazione/degustazione;
10. frequenza visite;
11. accessibilità del sito;
12. rischio incendio e affollamento delle aree coperte;
13. piano emergenza;
14. assicurazione;
15. sopralluogo e indicazioni ERSA.

Le quantità della BOM sono quindi `DA MASTERPLAN`, `DA CAPIENZA` o `DA RFQ`.

## 4. Zoning visitatori

Il dominio aziendale viene diviso in quattro classi.

### Z0 — pubblico / accoglienza

Comprende:

- punto di arrivo;
- briefing;
- servizi;
- primo soccorso;
- spazio coperto;
- area sosta;
- eventuale materiale didattico.

Accesso libero soltanto durante visite autorizzate.

### Z1 — percorso didattico protetto

Percorsi e punti di osservazione dove il gruppo può muoversi con supervisione senza interferire con macchine o processi.

Esempi:

- bordo esterno serra con observation point;
- area energia con vista protetta;
- percorso acqua;
- vite/pergolato;
- vermicompost;
- area galline vista da barriera;
- biodiversità.

### Z2 — accesso controllato per attività specifiche

Ingresso solo dopo messa in sicurezza e con referente.

Possibili esempi:

- modulo serra dimostrativo;
- orto didattico;
- attività con piante;
- contatto animale specificamente progettato;
- laboratorio sotto pergolato/aula.

### Z3 — no visitor

Baseline:

- locali tecnici;
- quadri elettrici;
- pompe e chimici;
- deposito fitofarmaci/fertilizzanti;
- officina;
- corsie mezzi;
- dock AMR;
- celle e packing operativo;
- tetti e FV;
- accumuli acqua;
- zone di carico/scarico;
- R&D laser;
- dirty dock galline;
- aree in manutenzione.

Il confine Z1/Z3 deve essere evidente fisicamente, non soltanto descritto verbalmente.

## 5. Percorso visitor-first, non production-first

Il percorso viene disegnato partendo dal visitatore:

`arrivo -> briefing/sicurezza -> agricoltura -> acqua -> energia -> automazione -> cicli materia/biodiversità -> animali -> lavaggio mani -> spazio coperto/debrief -> uscita`.

Non è obbligatorio mostrare ogni blocco a ogni visita.

Il percorso deve poter essere abbreviato o deviato in caso di:

- lavorazioni;
- mezzi;
- trattamenti;
- manutenzione;
- meteo;
- presenza di animali non gestibile;
- guasti;
- cantieri.

## 6. Interfaccia con la serra

Baseline: **observation point**, non visita libera nelle corsie.

Possibili soluzioni:

- tratto dedicato esterno con pannello e vista attraverso testata/fiancata;
- piccola zona interna segregabile;
- finestra/porta di osservazione;
- telecamera tecnica con feed locale per mostrare dettagli non raggiungibili.

Guardrail:

- AMR e visitatori non condividono la stessa mission area durante la visita;
- nessun accesso a dosaggio/fertirrigazione;
- nessun percorso vicino a parti in movimento;
- nessun ostacolo alle vie operative;
- niente raccolta/assaggio diretto senza procedura igienica e specifico progetto.

## 7. Acqua, energia e automazione come exhibit

L'esperienza didattica deve usare dati reali, non pannelli scollegati dall'azienda.

Display possibili:

- livello accumulo acqua;
- acqua piovana recuperata;
- portata irrigazione;
- energia FV istantanea/giornaliera;
- stato accumuli;
- temperatura/UR serra;
- grafico storico semplice;
- missioni AMR;
- immagini vision selezionate;
- ciclo compost.

Il display didattico legge **solo dati pubblicabili/read-only**.

Nessun controllo operativo deve essere esposto alla rete guest o al dispositivo visitatori.

## 8. Area galline

La didattica animale deve essere compatibile con BOM-023.

Baseline:

- osservazione da lato sicuro;
- barriera fisica;
- gate non accessibile ai bambini;
- nessun contatto non supervisionato;
- rover sanitario fermo o segregato durante l'attività didattica nelle aree condivise;
- rasaerba in lockout;
- lavaggio mani dopo la visita;
- niente cibo consumato nella zona animali;
- materiale educativo sul comportamento animale e biosicurezza.

ERSA richiede il controllo degli animali durante le visite e la gestione sicura delle lavorazioni concomitanti.

## 9. Spazio coperto

BOM-026 pergolato è il candidato naturale per coprire una parte della funzione, ma deve essere verificato rispetto a:

- capienza;
- accessibilità;
- sedute;
- meteo laterale;
- illuminazione;
- prese;
- sicurezza;
- uso durante temporali/vento;
- destinazione e autorizzazioni.

Il pergolato non sostituisce automaticamente un'aula chiusa.

Scenario evolutivo:

- **L1:** pergolato attrezzato per briefing e laboratori semplici;
- **L2:** aula/laboratorio chiuso se domanda, stagionalità e requisiti lo giustificano.

L2 resta `FUTURE / RFQ` fino a business case e verifica edilizia.

## 10. Servizi igienici

Requisito bloccante.

La soluzione deve essere:

- adeguata alla capienza;
- accessibile;
- raggiungibile dal percorso visitatori;
- lavabile;
- mantenibile;
- con acqua e scarico conformi al sito;
- segnalata;
- inclusa nel piano pulizia.

Non viene assunto che il bagno personale/aziendale esistente sia automaticamente sufficiente.

La BOM tratta il servizio accessibile come **lotto impiantistico/edile da RFQ**, perché il costo dipende da edificio, scarichi, approvvigionamento idrico e opere murarie.

## 11. Lavaggio mani e acqua potabile

Oltre al punto di primo soccorso vicino ad acqua potabile, il layout deve prevedere lavaggio mani in posizione utile soprattutto dopo il modulo animali.

Preferenza:

- lavabo allacciato a rete idrica/scarico;
- comando non manuale quando conveniente;
- sapone;
- asciugatura monouso;
- cestino;
- protezione gelo se esterno.

Lavamani autonomo portatile è un **fallback/pilot**, non la soluzione preferita permanente se l'area è stabilmente aperta.

## 12. Primo soccorso

Prevedere:

- kit conforme alla valutazione aziendale e ai requisiti applicabili;
- posizione segnalata;
- prossimità a fonte di acqua potabile come richiesto da ERSA;
- registro controllo scadenze;
- contatti emergenza;
- accesso mezzi di soccorso;
- referente formato secondo gli obblighi aziendali.

Un DAE può essere valutato separatamente da rischio, distanza dai soccorsi e politica aziendale; non viene dichiarato obbligatorio dalla BOM-027.

## 13. Accessibilità

Il requisito ERSA viene trasformato in un percorso accessibile verificabile.

Minimo:

- dal parcheggio/drop-off al punto di accoglienza;
- al primo soccorso;
- al servizio igienico accessibile;
- allo spazio coperto;
- a una parte significativa del percorso didattico.

Caratteristiche da verificare da tecnico:

- pendenze;
- larghezze;
- fondo stabile;
- drenaggio;
- soglie;
- raccordi;
- raggi di manovra;
- aree di sosta;
- assenza di ostacoli sporgenti.

Il Prezzario FVG 2026 fornisce benchmark per pavimentazioni drenanti pedonali; la scelta finale dipende dal terreno e dal progetto di accessibilità.

## 14. Parcheggio e drop-off

ERSA richiede uno spazio compatibile per il mezzo che accompagna l'utenza.

Il masterplan deve mostrare:

- punto discesa/salita;
- percorso pedonale protetto;
- area di manovra;
- separazione dalla logistica agricola;
- accesso emergenze;
- eventuale sosta autobus/van;
- parcheggio disabili se richiesto dal progetto/autorizzazioni.

Non si definiscono dimensioni senza lotto e mezzo target.

## 15. Separazioni e recinzioni

Tipologie distinte:

### B1 — barriera visitatori

Serve a impedire ingresso involontario nelle zone Z3.

Requisiti:

- niente filo spinato;
- niente punte accessibili;
- stabilità;
- visibilità;
- manutenzione semplice;
- gate chiudibile;
- nessun intrappolamento evidente.

### B2 — segregazione macchine

Dove il rischio è macchina/AMR/mezzo, la barriera deve derivare dalla valutazione del rischio, non dall'estetica.

### B3 — animal barrier

Separazione specifica, compatibile con welfare, pulizia e operazioni BOM-023.

## 16. Segnaletica

Tre livelli:

1. **wayfinding** — ingresso, percorso, servizi, uscita;
2. **safety** — vietato accesso, parti elettriche, mezzi, emergenza;
3. **didattica** — pannelli tema/QR.

La segnaletica safety non viene sostituita dai pannelli didattici.

I QR non devono essere l'unico mezzo per informazioni essenziali.

## 17. Didattica fisica e digitale

### Pannelli

Preferenza:

- pannello durevole da esterno;
- grafica sostituibile;
- icone leggibili;
- testo breve;
- QR per approfondimenti;
- codice pannello per manutenzione.

### Aula/pergolato

Attrezzatura minima:

- tavoli/sedute;
- almeno una postazione accessibile;
- lavagna;
- materiali dimostrativi;
- contenitori chiusi;
- prese/rete;
- kit pulizia.

### Digitale

Opzionale:

- tablet;
- display;
- dashboard locale;
- guest Wi-Fi;
- contenuti multilingua;
- quiz senza raccolta dati personali.

Il contenuto deve funzionare anche senza Internet quando possibile.

## 18. Progetto didattico

Documento obbligatorio da costruire prima del riconoscimento.

Per ogni modulo:

- titolo;
- fascia utenti;
- obiettivo;
- prerequisiti;
- durata;
- area;
- numero massimo ammesso dal progetto;
- materiali;
- rischi;
- DPI se realmente necessari;
- procedura;
- messaggio chiave;
- attività pratica;
- pulizia finale;
- variante meteo;
- accessibilità.

Working modules:

- D1 — come cresce una coltura protetta;
- D2 — viaggio dell'acqua;
- D3 — energia della fattoria;
- D4 — sensori e robot agricoli;
- D5 — compost e cicli di materia;
- D6 — vite, biodiversità e stagioni;
- D7 — galline, comportamento e welfare;
- D8 — dalla raccolta alla tracciabilità, senza ingresso nella packing room operativa.

## 19. Food/tasting: NON baseline

Assaggi, merende, somministrazione o preparazione alimenti non vengono inclusi automaticamente.

Se introdotti, richiedono verifica separata di:

- titolo/attività;
- igiene;
- HACCP;
- allergeni;
- acqua;
- superfici;
- conservazione;
- responsabilità;
- eventuali requisiti agrituristici/commerciali.

Baseline BOM-027: didattica senza processo food destinato al consumo.

## 20. Organizzazione visite

Flusso minimo:

### Prima

- prenotazione;
- età/tipologia gruppo;
- referente accompagnatore;
- esigenze accessibilità;
- allergie/intolleranze o problemi particolari comunicati dagli accompagnatori nella misura necessaria alla sicurezza;
- programma;
- meteo;
- conferma aree disponibili.

### Arrivo

- headcount a carico dell'accompagnatore;
- briefing;
- regole;
- aree vietate;
- emergenza;
- lavaggio mani quando previsto.

### Durante

- referente fattoria presente;
- gruppo mantenuto nel percorso;
- gate richiusi;
- stop attività se entra un mezzo o si perde segregazione.

### Uscita

- headcount;
- verifica area;
- pulizia;
- registrazione visita prevista da ERSA;
- segnalazione quasi incidenti/danni.

## 21. Registro visite e dati personali

ERSA richiede un registro visite.

Design privacy-aware:

- registrare solo i dati richiesti/necessari;
- evitare liste nominali di minori se non necessarie;
- nessun riconoscimento facciale;
- videosorveglianza separata dagli strumenti didattici;
- foto/video solo con base giuridica/consensi applicabili;
- guest Wi-Fi senza accesso ai sistemi OT.

## 22. Meteo

Procedure di stop/riduzione percorso per:

- temporali;
- vento forte;
- caldo;
- ghiaccio/neve;
- allagamento;
- scarsa visibilità;
- lavori in corso.

Il percorso deve avere una variante `WET WEATHER` che non richieda attraversare terreno fangoso o zone operative.

## 23. Failure modes e fallback

| Failure mode | Conseguenza | Fallback |
|---|---|---|
| percorso incrocia mezzo agricolo | collision risk | stop visitatori / gate / reroute |
| AMR attivo in area visitatori | interazione non prevista | mission lockout durante finestra visita |
| animale non controllabile | morso/fuga/stress | chiusura modulo animali |
| guasto lavamani | igiene insufficiente | stazione backup / chiusura attività animale |
| WC indisponibile | requisito ospitalità compromesso | sospendere visita se non esiste alternativa idonea |
| pioggia/allagamento percorso | caduta/accessibilità | percorso wet-weather |
| caldo/temporale | rischio persone | rientro nello spazio sicuro / cancellazione |
| segnale/cartello mancante | ingresso errato | barriera fisica + sostituzione immediata |
| tablet/Wi-Fi guasto | perdita contenuto | pannelli e materiale offline |
| primo soccorso incompleto/scaduto | risposta emergenza ridotta | visita non avviata finché ripristinato |
| referente assente | requisito operativo non rispettato | visita cancellata |
| area tecnica aperta | accesso pericoloso | stop visita e lock area |
| emergenza durante visita | evacuazione confusa | punto raccolta, route e headcount |
| trattamento/lavorazione imprevista | esposizione/interferenza | esclusione modulo / rinvio |

## 24. Automazione utile

Automazione ammessa:

- calendario visite collegato a finestre operative;
- stato `VISIT MODE`;
- lockout logico del robot tagliaerba nelle aree visitatori;
- mission hold AMR in specifiche crossing zone;
- dashboard read-only;
- notifiche al personale;
- illuminazione percorso.

**Guardrail:** la sicurezza non dipende da un singolo software. Barriere, procedure e controllo umano restano necessari.

## 25. Manutenzione

### Prima di ogni visita

- percorso libero;
- gate/barriere;
- bagni;
- acqua;
- sapone/asciugatura;
- kit primo soccorso;
- cartelli;
- area coperta;
- meteo;
- animali;
- lockout macchine previsto.

### Mensile/stagionale

- fondo percorso;
- drenaggi;
- arredi;
- fissaggi pannelli;
- leggibilità cartelli;
- recinzioni;
- luci;
- rete;
- materiali didattici;
- scadenze kit;
- procedure emergenza.

### Annuale

- RC;
- revisione progetto didattico;
- verifica requisiti ERSA;
- simulazione emergenza;
- revisione accessibilità;
- aggiornamento planimetria;
- formazione/aggiornamenti pertinenti.

## 26. Regola economica

Separare:

`CAPEX infrastructure`:
- percorso;
- separazioni;
- WC;
- lavamani;
- punto primo soccorso;
- pannelli;
- arredi;
- impianti.

`CAPEX didattico`:
- grafica;
- lavagna;
- kit dimostrativi;
- tablet/display opzionali.

`OPEX`:
- RC;
- pulizia;
- consumabili;
- rinnovo grafica;
- formazione;
- manutenzione;
- ore referente;
- eventuali verifiche.

Non conteggiare nuovamente ciò che è già incluso in BOM-026, BOM-023, rete o infrastrutture generali: riportare una dipendenza con costo marginale.

## 27. Gate BOM-027

1. completamento percorso formativo richiesto;
2. progetto didattico;
3. lotto/masterplan;
4. visitor zoning Z0-Z3;
5. planimetria conforme agli elementi richiesti da ERSA;
6. parcheggio/drop-off;
7. capienza;
8. WC accessibile;
9. spazio coperto;
10. primo soccorso + acqua potabile;
11. percorso accessibile;
12. segregazione mezzi/AMR;
13. modulo animali + igiene;
14. piano emergenza/meteo;
15. RC;
16. RFQ infrastrutture;
17. procedure visita;
18. registro visite;
19. sopralluogo ERSA;
20. commissioning con visita pilota prima dell'apertura.
