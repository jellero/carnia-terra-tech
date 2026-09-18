# Architettura evolutiva — Agriturismo extra

**Stato:** `ARCHITETTURA DI LAVORO / EXTRA`  
**Aggiornato:** 18 settembre 2026.

## 1. Obiettivo tecnico

Costruire il minimo necessario per iniziare con spuntini non cucinati, lasciando però percorsi tecnici, spazio e utilities che evitino rifacimenti se in futuro si passa a cucina o ospitalità.

Il principio è:

`predisporre != installare`

## 2. E0 — predisposizioni

E0 non deve generare un secondo cantiere invasivo nel progetto principale.

### Masterplan
Riservare:
- area per micro-locale food;
- relazione diretta con pergolato/area consumo;
- percorso cliente separato da logistica agricola;
- accesso rifornimento separabile;
- possibile espansione laterale del locale;
- possibile futuro percorso per espulsione cucina;
- area tecnica per freddo/impianti;
- collegamento a WC accessibile.

### Utilities
Prevedere possibilità di espansione per:
- acqua potabile;
- acqua calda;
- scarico;
- potenza elettrica;
- dati;
- drenaggio;
- eventuale futuro scarico/ventilazione di cucina.

Non installare cappe, linea calda o impianti sovradimensionati senza analisi economica.

### Edile
Dove economicamente razionale:
- cavedi accessibili;
- manicotti/passaggi;
- spazio quadro;
- pareti e superfici facilmente convertibili a standard food;
- geometria che consenta futura separazione dirty/clean.

## 3. E1 — ristoro light

### Funzione
Servizio presidiato in finestre definite, indipendente dallo spaccio 24/7.

Flusso:

`stock approvato -> frigo ristoro -> preparazione non cotta -> servizio -> pergolato/tavoli`

### Dotazione funzionale minima da RFQ
- piano lavoro lavabile/disinfettabile;
- lavaggio mani;
- lavaggio utensili secondo layout sanitario;
- frigorifero dedicato con monitoraggio;
- piccolo stock ambient protetto;
- banco servizio;
- protezione alimenti;
- contenitori ingredienti identificati;
- utensili dedicati;
- gestione allergeni;
- rifiuti;
- cleaning storage separato;
- protezione infestanti;
- illuminazione adeguata;
- POS/fiscalità da definire;
- tracciabilità lotti;
- HACCP/autocontrollo.

### Esclusioni E1
- cottura;
- friggitrici;
- piastre;
- forno produttivo;
- cucina cook-chill;
- catering strutturato;
- banqueting;
- linea lavaggio stoviglie industriale sovradimensionata;
- cappa di cucina installata "in previsione".

## 4. E1 — rapporto con BOM-028

Modalità distinte:

### M0
Spaccio automatico 24/7, unattended.

### M1
Ristoro agrituristico presidiato a spuntini.

M1 può utilizzare:
- stessa area generale clienti;
- signage coordinato;
- eventuale account inventario comune;
- eventuale infrastruttura pagamento/server.

Ma:
- autorizzazioni;
- flussi alimentari;
- stock;
- pulizia;
- personale;
- contabilità analitica

restano distinti.

Alla chiusura di M1, M0 continua.

## 5. E1 — rapporto con BOM-026

Il pergolato è il candidato per il consumo/sosta se:
- capienza;
- destinazione;
- accessibilità;
- servizi;
- meteo;
- sicurezza;
- requisiti sanitari

sono compatibili.

Non trasformare il pergolato in sala ristorante chiusa senza progetto dedicato.

## 6. E1 — rapporto con BOM-027

Obiettivo di progetto:
**un unico blocco servizi ben posizionato**, potenzialmente condiviso tra fattoria didattica e ristoro, se autorizzato.

La condivisione deve essere verificata su:
- capienza;
- accessibilità;
- antibagno;
- percorsi;
- pulizia;
- orari;
- requisiti SUAP/sanitari.

## 7. Menu architecture

Non congelare ricette prima del verifica sanitario.

Famiglie candidate E1:
- prodotti orticoli aziendali;
- frutta;
- panini/spuntini non cucinati compatibili;
- taglieri;
- degustazioni;
- bevande;
- box picnic;
- prodotti regionali complementari ammessi.

Ogni SKU/menu item avrà:
- provenienza;
- lotto;
- allergeni;
- temperatura;
- shelf-life;
- preparazione;
- utensili;
- rischio cross-contamination;
- modalità servizio;
- classificazione `SPUNTINO-SI / DA-VERIFICARE / NO`.

## 8. E2 — esperienze

E2 non richiede automaticamente cucina.

Possibili servizi:
- degustazioni guidate;
- visite serra/automazione;
- picnic box;
- laboratori;
- eventi agricoli stagionali;
- esperienze con raccolta/colture dove autorizzate;
- pacchetti con fattoria didattica;
- percorsi territorio/bici.

E2 deve usare slot prenotabili per proteggere lavoro agricolo e qualità della vita.

## 9. E3 — cucina

Attivare solo quando:
- E1 ha domanda misurata;
- margine giustifica ore uomo;
- esiste copertura finanziaria separata;
- layout e autorizzazioni sono chiusi.

Nuovi sottosistemi probabili:
- cucina/laboratorio;
- zona cottura;
- aspirazione/espulsione;
- lavaggio;
- maggior freddo;
- spogliatoio/servizi personale;
- maggiore potenza;
- maggiore scarico;
- stoccaggio;
- HACCP più articolato.

E3 deve avere RFQ e analisi economica propri.

## 10. E4 — ospitalità

E4 è separata dal ristoro.

Possibili direzioni:
- strutture ecocompatibili rimovibili;
- unità leggere;
- glamping/campeggio agrituristico;
- camere/locali aziendali se compatibili.

Nessun alloggio entra in E1.

## 11. KPI di verifica

E1 deve misurare almeno:
- clienti/giorno apertura;
- ticket medio;
- costo materia prima;
- waste;
- minuti lavoro/cliente;
- ore settimanali totali;
- margine lordo per ora uomo;
- utilizzo posti;
- % clienti spaccio che usano ristoro;
- conversione visita -> acquisto;
- reclami;
- scarti;
- stagionalità.

E3 non parte senza dati reali E1/E2.

## 12. Regola in caso di insuccesso

Se il piano extra non funziona:
- progetto principale agricolo continua;
- spaccio continua;
- pergolato resta utilizzabile;
- fattoria didattica resta utilizzabile;
- nessun impianto vitale dipende dal ristoro.

L'investimento E1 deve poter essere riconvertito a:
- tasting room;
- area didattica food;
- punto confezionamento non produttivo;
- servizio eventi leggero;
- spazio visitatori.
