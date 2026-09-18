# Mezzo multifunzione e sollevamento — architettura

**Aggiornato:** 18 settembre 2026  
**Stato:** `FUNZIONE CORE / TELESCOPICO MULTIFUNZIONE + STOCCATORE / PLE IN QUOTA DA TCO-RFQ`.

## 1. Obiettivo

Carnia TerraTech necessita di capacità di sollevamento e movimentazione per:

- pallet, cassette, fertilizzanti, ricambi, film, profili e materiali di cantiere;
- manutenzione in quota e montaggio serra;
- movimentazione fra piazzale, Tech Barn e corridoio tecnico;
- movimentazione di humus, compost, substrati e materie sfuse;
- carico/scarico dell'area cicli materia;
- movimentazione di materiali acquistati da rilavorare internamente;
- uso di forche, benna e altri accessori OEM dove utili;
- eventuale piattaforma persone esclusivamente nella configurazione prevista e autorizzata dal costruttore.

Non è realistico imporre a una sola macchina di entrare nelle corsie coltura da ~1,20 m e contemporaneamente sollevare 2,5 t a 5–6 m. L'architettura separa quindi due livelli.

## 2. Livello L1 — telescopico multifunzione

**Decisione di progetto:** la funzione è core. Il mezzo serve anche se AMR e robotica vengono rinviati.

Missioni:

- scarico camion e pallet pesanti;
- movimentazione materiali serra/Tech Barn;
- carico/scarico bins;
- montaggio e manutenzione struttura;
- accesso in quota con navicella OEM quando autorizzato;
- benna/materiali sfusi come requisito per humus/cicli materia;
- lavoro esterno e nel corridoio tecnico principale.

### Candidato prioritario: Merlo EW25.5-90 / eWorker

Motivi:

- elettrico;
- larghezza circa 1,54 m, inferiore ai concorrenti 1,81–1,84 m censiti;
- portata 2.500 kg;
- altezza massima ~4,8–5 m;
- sbraccio ~2,6 m;
- 4WD nella versione 90;
- attacco rapido e attrezzature intercambiabili;
- possibilità OEM di piattaforma aerea;
- produttore italiano e rete assistenza da verificare localmente.

La macchina NON entra nelle corsie coltura working da 1,20 m. È destinata a corridoio tecnico, piazzale, Tech Barn e aree di manovra dedicate.

### Piattaforma persone

La piattaforma deve essere:

- specifica per il modello;
- espressamente autorizzata dal costruttore;
- inclusa nella configurazione/documentazione della macchina;
- dotata dei comandi e interblocchi previsti dall'OEM;
- gestita con formazione e verifiche previste per il telescopico con funzione sollevamento persone.

Nessun retrofit artigianale e nessun radiocomando aggiunto fuori dalla configurazione certificata.

## 3. Alternative L1

### Manitou MLT 625 e

Candidato agricolo elettrico:

- 2.500 kg;
- 5,90 m;
- 1,81 m larghezza;
- 2,00 m altezza;
- raggio esterno 3,31 m;
- 34,8 kWh Li-ion;
- caricatore 9 kW;
- 4WD/4WS/crab;
- 20 km/h.

È esplicitamente proposto dal produttore anche per serre/stalle, ma è più largo del Merlo.

### JCB 525-60E

- 2.500 kg;
- 6,0 m;
- 1,84 m larghezza;
- 1,89 m altezza;
- raggio esterno 3,7 m;
- 24 kWh Li-ion;
- 4WD e tre modalità sterzo.

Ottimo riferimento, ma footprint maggiore.

## 4. Livello L2 — stoccatore elettrico compatto

Per Tech Barn e movimentazioni leggere si mantiene una macchina separata economica, ad esempio EP EST122 o equivalente:

- 1.200 kg;
- larghezza 792 mm;
- sollevamento ~3 m;
- raggio ~1.46 m;
- 24 V AGM;
- prezzo pubblico da ~€2.900 + IVA.

Questa macchina può gestire pallet nei locali tecnici e riduce l'uso del telescopico da ~5 t per missioni banali. Il corridoio minimo di stivaggio con pallet resta >2,2 m: la larghezza macchina da sola non rende automaticamente compatibile una corsia coltura da 1,20 m.

## 4A. Livello H1 — accesso in quota

La manutenzione delle parti alte è funzione core.

Tre soluzioni:
1. piattaforma persone OEM sul telescopico, se quota/sbraccio e geometria sono sufficienti;
2. PLE cingolata compatta "ragno" dedicata;
3. noleggio/servizio con SLA compatibile.

Riferimenti:
- `ACCESSO_IN_QUOTA_RAGNO_ARCHITETTURA.md`;
- `RFQ_ACCESSO_IN_QUOTA_RAGNO.md`.

La capacità di raggiungere ogni punto manutentivo critico deve essere dimostrata sul masterplan prima di chiudere il layout.

## 5. Geometria e masterplan

Requisiti da inserire nel masterplan:

- corridoio tecnico principale ~4 m compatibile telescopico;
- piazzole di inversione dimensionate sul modello scelto;
- pavimentazione con portanza per massa macchina ~5 t + carico;
- pendenze e drenaggi compatibili con stabilità e aderenza;
- altezza porte Tech Barn/serra da macchina reale + margine;
- area di ricarica ventilata/protetta e fuori dalle vie di fuga;
- separazione pedoni/mezzi nei punti ciechi;
- parcheggio accessori con appoggi che evitino instabilità;
- accesso e raggio di lavoro area humus/cicli materia;
- piazzole/stabilizzazione PLE per copertura, gronde e parti alte.

## 6. Energia e ricarica

Il caricatore e la chimica batteria dipendono dalla versione d'ordine.

Da RFQ:

- capacità batteria utile;
- autonomia sul duty cycle Carnia;
- potenza caricatore standard e rapido;
- curva e tempi 20→80% / 10→100%;
- vita ciclica e garanzia batteria;
- temperatura di carica;
- assorbimento di picco;
- possibilità di opportunity charging;
- costo batteria di ricambio.

L'EMS può differire la ricarica, ma non deve bloccare una missione critica.

## 7. Accessori baseline da quotare separatamente

- portaforche + forche standard;
- traslatore/posizionatore forche se disponibile e utile;
- benna general purpose;
- gancio/attrezzatura per carichi sospesi solo se business case;
- piattaforma persone OEM completa di predisposizione, comandi e documentazione;
- pneumatici agricoli/industriali da confrontare;
- protezioni e luci lavoro;
- caricatore/wallbox;
- eventuale batteria secondaria/rapida;
- kit recovery;
- telematica solo se non vitale per il funzionamento.

## 8. Safety e normativa operativa

Il telescopico è attrezzatura con obblighi specifici di uso, manutenzione, formazione e verifica periodica.

Principi di progetto:

- macchina base + accessorio = configurazione approvata dal costruttore;
- diagrammi di carico per ogni accessorio;
- nessuna persona sotto carichi sospesi;
- nessun trasporto persone sulle forche;
- stabilità verificata su pavimento/pendenza reale;
- zone pedonali, specchi/camere, beacon e procedure di precedenza;
- verifica annuale del carrello telescopico secondo regime applicabile;
- formazione operatori conforme all'Accordo Stato-Regioni vigente, incluso modulo funzione persone/carichi sospesi se utilizzata.

## 9. Failure modes e fallback

Failure modes:

- batteria scarica/guasta;
- caricatore guasto;
- pneumatico;
- tubo/valvola idraulica;
- sensore stabilità/load management;
- attacco accessorio non correttamente bloccato;
- guasto piattaforma/comandi;
- indisponibilità ricambio;
- pavimento/terreno non portante;
- urto struttura/coltura.

Fallback:

- stoccatore L2 per pallet leggeri;
- AMR/carrelli manuali per cassette;
- noleggio telescopico/PLE per guasti lunghi o picchi;
- manutenzione in quota sospesa se la configurazione certificata non è disponibile.

## 9A. Priorità economica

Ordine:
1. mezzo L1 con forche + benna;
2. stoccatore L2 se Tech Barn lo richiede;
3. capacità certificata di accesso in quota;
4. altri accessori solo da ore/anno reali.

AMR e robot di servizio non devono sottrarre CAPEX a queste funzioni.

## 10. Decision gate

1. definire pallet/bin/materiali massimi;
2. verificare corridoi, porte, raggi e portanza;
3. demo Merlo/Manitou/JCB sul sito o simulazione layout;
4. RFQ macchina + accessori separati;
5. confermare piattaforma OEM autorizzata e relativa configurazione;
6. formazione/verifiche/assicurazione;
7. costo energia, manutenzione e batteria su 8–10 anni;
8. confronto acquisto vs leasing/noleggio;
9. decisione su stoccatore L2;
10. acceptance test con carichi reali.