# BOM-005 — Fogging alta pressione serra

**Aggiornato:** 17 settembre 2026  
**Ambito:** C1 pomodoro, C2 peperone, C6 basilico/vivaio/jolly; predisposizione futura C3–C5.  
**Stato:** `CANDIDATI REALI E PREZZI TROVATI / PORTATA, UGELLI E TRATTAMENTO ACQUA DA DIMENSIONARE`.

## 1. Funzione

Il fogging deve controllare raffrescamento evaporativo e umidità/VPD senza trasformarsi in irrigazione fogliare o creare bagnatura persistente.

È un sottosistema climatico separato dall'irrigazione/fertirrigazione. Un guasto del fogging non deve impedire irrigazione, aperture o HAF.

## 2. Requisiti di progetto

- alta pressione professionale, working range indicativo 70 bar;
- tre zone indipendenti C1/C2/C6;
- attivazione da PLC su T/UR/VPD e stato climatico;
- anti-drip sugli ugelli o soluzione equivalente;
- drenaggio/depressurizzazione controllati;
- filtrazione coerente con foro ugelli;
- trattamento acqua deciso dopo analisi;
- protezione marcia a secco;
- misura pressione e preferibilmente portata;
- valvola di sicurezza/bypass secondo pompa;
- isolamento manuale delle zone;
- manutenzione senza fermare irrigazione;
- possibilità di svuotamento e protezione gelo.

## 3. Architetture da confrontare

### F1 — pompa centrale singola + 3 zone

Una pompa alimenta C1/C2/C6 tramite elettrovalvole HP indipendenti.

Vantaggi:
- CAPEX più basso;
- una sola stazione filtri/pompa;
- manutenzione centralizzata.

Svantaggi:
- pompa = single point of failure del fogging;
- pressione/portata devono restare stabili con combinazioni diverse di zone;
- richiede bypass/inverter o logica idraulica appropriata.

Il fogging non è servizio vitale come irrigazione, quindi il single point of failure può essere tecnicamente tollerabile solo se aperture/HAF garantiscono un fallback climatico accettabile.

### F2 — centrale N+1

Due pompe, ciascuna dimensionata per il carico di progetto richiesto, con duty/standby o parallelo controllato.

Vantaggi:
- ridondanza reale;
- manutenzione senza perdita completa del fogging;
- migliore coerenza con filosofia Carnia TerraTech.

Svantaggi:
- costo iniziale maggiore;
- più valvole, logica, spazio e manutenzione.

### F3 — tre pompe indipendenti

Una pompa dedicata per C1, una C2, una C6.

Vantaggi:
- failure domain minimo;
- controllo semplice per comparto;
- espansione/manutenzione modulari.

Svantaggi:
- tre pompe da mantenere;
- più quadri/filtri/connessioni;
- CAPEX potenzialmente superiore.

**Nessuna architettura è ancora selezionata.** La scelta finale usa portata evaporativa, pressione al punto sfavorito, contemporaneità, TCO e costo della ridondanza.

## 4. Pompe — benchmark reali

I seguenti prodotti forniscono benchmark di mercato e capacità. Alcuni sono commercializzati per zootecnia/general misting: prima della scelta finale servono RFQ e verifica specifica greenhouse.

### P1 — LUBING 70 bar, 5,5 L/min

- portata: 5,5 L/min;
- pressione: 70 bar;
- dichiarata per 60 ugelli da 0,2 mm;
- alimentazione trifase;
- prezzo osservato: **€2.830,43**;
- disponibilità indicata: 14 giorni.

Fonte: https://en.fermo.pl/pump-for-fogging-system-lubing-70-bar-55lmin.html

Classificazione: `PREZZO TROVATO / BENCHMARK PROFESSIONALE`.

Tre unità: **€8.491,29** di sole pompe.

### P2 — LUBING 70 bar, 20 L/min

- portata: 20 L/min;
- pressione: 70 bar;
- dichiarata per 240 ugelli da 0,2 mm;
- alimentazione trifase;
- prezzo osservato: **€3.747,49**.

Fonte: https://en.fermo.pl/pump-for-fogging-system-lubing-70-bar-20lmin.html

Classificazione: `PREZZO TROVATO / BENCHMARK CENTRALE`.

Due unità N+1: **€7.494,98** di sole pompe.

### P3 — FERMO 50–100 bar, 8 L/min

- portata: 8 L/min;
- pressione regolabile 50–100 bar;
- controllo manuale/automatico/esterno;
- corpo inox;
- prezzo osservato sulla pagina prodotto: **€2.138,83**.

Fonte: https://en.fermo.pl/pump-for-fogging-system-fermo-50-100-bar-8-lmin.html

Classificazione: `PREZZO TROVATO / BENCHMARK`.

Tre unità: **€6.416,49** di sole pompe.

### P4 — FERMO 50–100 bar, 21 L/min

- portata: 21 L/min;
- fino a 194 ugelli dichiarati dal venditore;
- controllo da climate computer possibile;
- prezzo osservato: **€3.335,28**.

Fonte: https://en.fermo.pl/pump-for-fogging-system-fermo-50-100-bar-21-lmin.html

Classificazione: `PREZZO TROVATO / BENCHMARK CENTRALE`.

Due unità N+1: **€6.670,56** di sole pompe.

### Fornitori greenhouse-specific da quotare

- LUBING GreenTec greenhouse fogging: https://horticulture.lubingusa.com/horticulture/fogging-system/
- Natural Misting Italia: https://naturalmisting.com/en/departments/nurseries-and-greenhouses/
- FOG System: https://www.fog-system.com/
- Tecnocooling: https://tecnocooling-en.es/en/

Questi diventano RFQ prioritari; i prezzi retail sopra servono a controllare le offerte.

## 5. Ugelli — costo pezzo

### N1 — LUBING inox 0,2 mm

- materiale inox;
- foro 0,2 mm;
- portata dichiarata ~5 L/h a 70 bar;
- prezzo osservato: **€8,98/cad**.

Fonte: https://en.fermo.pl/nozzle-for-sprinkler-system-lubing-stainless-steel-02-mm.html

Formula costo: `numero ugelli × €8,98`.

Esempi puramente aritmetici, **non dimensionamento**:
- 100 pz = €898;
- 180 pz = €1.616,40;
- 240 pz = €2.155,20.

### N2 — Tecnocooling inox 0,20 mm con anti-drip + filtro

- inox;
- 0,20 mm;
- 70 bar nominali, 150 bar max dichiarati;
- anti-drip;
- filtro integrato;
- prezzo osservato: **€15,70/cad**.

Fonte: https://tecnocooling-en.es/en/nozzle-1024-stainless-steel-020-mm/

Esempi aritmetici:
- 100 pz = €1.570;
- 180 pz = €2.826;
- 240 pz = €3.768.

### N3 — Tecnocooling 0,15 mm anti-drip + filtro

- 0,15 mm;
- 70 bar;
- anti-drip e filtrazione integrata;
- prezzo osservato: **€10,77/cad**.

Fonte: https://tecnocooling-en.es/en/nozzle-1024-015-mm/

Il diametro finale non viene scelto sul prezzo: dipende da portata, distribuzione, dimensione goccia, rischio bagnatura, qualità acqua e pressione reale.

## 6. Tubazioni HP

### T1 — inox 12 mm, barra 6 m

Benchmark FERMO:

- tubo inox 12 mm;
- lunghezza 6 m;
- prezzo osservato **€21,55/barra**;
- equivalente ~**€3,59/m** di solo tubo.

Fonte categoria: https://en.fermo.pl/livestock-buildings-equipment/presure-cooling-systems.html

### T2 — PA12PHL 3/8, bobina 25 m

Tecnocooling:

- nylon PA12;
- 3/8";
- pressione dichiarata 70–150 bar;
- 25 m;
- prezzo osservato versione bianca **€114,81**;
- equivalente ~**€4,59/m**.

Fonte: https://tecnocooling-en.es/en/pa12phl-38-nylon-pipe-25-m-white/

Scelta inox/PA12 da fare su durata, montaggio, espansioni termiche, pulizia, raccordi, UV, sostituzione e garanzia.

## 7. Raccordi e supporti — benchmark

FERMO 12 mm inox:

- raccordo diritto: **€14,81**;
- gomito: **€24,82**;
- tee: ~**€59**;
- staffa tubo con gomma: **€0,65**.

Fonti:
- https://en.fermo.pl/livestock-buildings-equipment/presure-cooling-systems.html
- https://en.fermo.pl/tee-for-stainless-steel-tube-12-mm-screwed-to-sprinkler-system.html

Queste voci dimostrano perché i raccordi non possono essere assorbiti in un forfait per metro.

## 8. Elettrovalvole e zone

Tecnocooling NC-100 PRO:

- 3/8";
- 24 VAC;
- alta pressione;
- prezzo osservato **€217,07/cad**.

Fonte: https://tecnocooling-en.es/valvula-solenoide-ap-38-24-v-ca-nc-100-pro/

Per 3 zone: **€651,21** di sole elettrovalvole, esclusi isolamento manuale, raccordi, cablaggio e ricambi.

Ogni zona deve avere almeno:

- valvola manuale isolamento;
- elettrovalvola HP;
- possibilità di drenaggio/depressurizzazione;
- pressione misurabile;
- identificazione fisica e nel PLC.

## 9. Filtrazione e acqua

### Filtrazione meccanica

Tecnocooling mostra:

- cartuccia 1 micron 20": **€13,45**;
- set filtrazione con manometro 3 × 9", stadi 5 + 1 + 0,005 micron: **€259,23**.

Fonti:
- https://tecnocooling-en.es/en/water-treatment/
- https://tecnocooling-en.es/en/filter-set-with-pressure-gauge-3934-510005-microns/

La sequenza finale segue le prescrizioni del sistema selezionato. La documentazione Tecnocooling mostra configurazioni di filtrazione differenti a seconda dell'impianto; il progetto non congela quindi una sequenza universale prima della selezione pompa/ugello.

### Analisi acqua obbligatoria

Prima di decidere il trattamento servono almeno:

- pH;
- EC/TDS;
- durezza;
- alcalinità/bicarbonati;
- Fe/Mn;
- silice se rilevante;
- torbidità/solidi;
- cloruri/sali;
- qualità microbiologica quando richiesta dal rischio d'uso.

### Osmosi inversa

**Stato: `CONDIZIONALE / PREZZO DA PREVENTIVO`.**

Non viene installata automaticamente. MicroCool e operatori greenhouse come Natural Misting indicano RO/softening come strumenti per limitare sali, scaling e intasamento quando la qualità dell'acqua lo richiede.

Fonti:
- https://microcool.com/greenhouse/how-to-ensure-optimal-water-quality-for-high-pressure-fog-systems-in-horticulture/
- https://naturalmisting.com/en/departments/nurseries-and-greenhouses/

Dimensionamento e costo dipendono da analisi acqua, portata, recupero e qualità permeato.

## 10. Sensori e controllo

Riutilizzare dove possibile la sensoristica già prevista nel progetto, senza duplicare hardware inutilmente.

Input minimi:

- T/UR per comparto;
- VPD calcolato;
- leaf wetness come veto/feedback dove sensato;
- stato aperture;
- HAF;
- pressione HP;
- bassa pressione ingresso/acqua presente;
- fault pompa;
- eventuale portata fogging.

Output:

- enable pompa;
- selezione pompa duty/standby se F2;
- 3 elettrovalvole zone;
- drenaggio/depressurizzazione;
- allarmi.

Principio di sicurezza:

`richiesta fog → verifica prerequisiti → apertura zona → pressione valida → ciclo fog → verifica UR/VPD/bagnatura → stop → depressurizzazione`.

## 11. Integrazione con HAF e aperture

Non prevedere subito ventilatori nebulizzatori dedicati.

Prima opzione:

- utilizzare i 4 HAF/comparto già previsti per uniformare il microclima;
- posizionare ugelli e linee affinché la nebbia evapori prima della coltura e non investa direttamente motori/elettrico;
- verificare con smoke/fog test e commissioning reale.

Se l'uniformità non è sufficiente, il ventilatore dedicato diventa una voce successiva, non un acquisto automatico.

## 12. BOM minima

| Codice | Voce | Quantità | Stato |
|---|---|---:|---|
| FOG-PMP | pompa/e HP | da scenario F1/F2/F3 | CANDIDATI REALI |
| FOG-FIL | prefiltri/cartuccia | da portata | DA DIMENSIONARE |
| FOG-RO | RO/softening | se analisi lo richiede | CONDIZIONALE |
| FOG-TNK | break tank/vaso tecnico | se richiesto | DA PROGETTO |
| FOG-LP | sensore bassa pressione/dry-run | per stazione | REQUISITO |
| FOG-HP | manometro + trasduttore HP | per stazione | REQUISITO |
| FOG-FLO | flussimetro | 1 totale o per zona | DA VALUTARE |
| FOG-SAFE | relief/bypass | per stazione | REQUISITO |
| FOG-MAIN | collettore HP | da P&ID | DA PREVENTIVO |
| FOG-PIPE | linee HP | m da layout | DA GEOMETRIA |
| FOG-FIT | raccordi | da distinta | DA GEOMETRIA |
| FOG-BRK | staffe/supporti | da layout | DA GEOMETRIA |
| FOG-ZV | elettrovalvola HP | 3 + eventuale scorta | CANDIDATO |
| FOG-IV | valvole isolamento | almeno 3 + stazione | REQUISITO |
| FOG-DRN | drenaggi/depressurizzazione | per zona/stazione | REQUISITO |
| FOG-NOZ | ugelli | da calcolo | CANDIDATI REALI |
| FOG-NF | microfiltri/tenute/molle ugelli | stock | REQUISITO |
| FOG-EL | quadro/protezioni | per architettura | DA PREVENTIVO |
| FOG-CAB | cavi/passerelle | m da layout | DA PREVENTIVO |
| FOG-PLC | I/O e logica PLC | 1 package | DA INTEGRARE |
| FOG-COM | commissioning | 1 lotto | DA PREVENTIVO |
| FOG-SP | ricambi | 1 lotto | DA DEFINIRE |

## 13. Ricambi minimi da quotare

- ugelli completi;
- teste/orifizi;
- filtri ugello;
- molle anti-drip;
- O-ring/tenute;
- cartucce filtri;
- elettrovalvola/coil;
- kit tenute pompa;
- olio prescritto;
- pressostato/trasduttore critico;
- raccordi e tratto tubo HP;
- eventuale pompa completa se architettura senza ridondanza e lead time elevato.

## 14. Manutenzione

Manuale Tecnocooling verificato:

- controllo frequente stato filtri;
- ugelli con spruzzo degradato vanno rimossi/serviti o sostituiti con tappo durante manutenzione;
- per il modello/manuale esaminato, cambio olio pompa indicato ogni **800–1000 h**;
- per fermo invernale: drenare pompa e linee, spurgare, rimuovere/proteggere gli ugelli secondo procedura del costruttore.

Fonte manuale: https://tecnocooling-en.es/instructions/en/Operating%20instructions%20for%20the%20fogging%20system.pdf

L'intervallo definitivo sarà quello del modello acquistato.

## 15. Failure modes da collaudare

- pompa non parte;
- dry-run;
- pressione troppo bassa/alta;
- elettrovalvola bloccata aperta;
- elettrovalvola bloccata chiusa;
- ugello ostruito;
- ugello gocciolante;
- rottura tubo/raccordo HP;
- filtro intasato;
- qualità acqua fuori specifica;
- sensore UR errato;
- apertura serra incompatibile con strategia fog;
- HAF fermo;
- perdita comunicazione PLC;
- blackout;
- gelo.

## 16. Sicurezza

Una linea a ~70 bar non è una normale linea irrigua.

Prevedere:

- componenti con pressione nominale adeguata e margine dichiarato;
- protezione meccanica delle linee nei passaggi;
- lockout/depressurizzazione prima di manutenzione;
- nessun serraggio/smontaggio in pressione;
- cartellinatura punti di isolamento;
- valvola di sicurezza;
- procedure specifiche per perdite HP;
- protezione elettrica coerente con ambiente umido.

## 17. Gate per `VALIDATO`

BOM-005 non passa a `VALIDATO` finché non sono chiusi:

1. analisi acqua;
2. carico di raffrescamento/umidificazione per C1/C2/C6;
3. portata evaporabile senza bagnatura;
4. numero/foro/layout ugelli;
5. pressione al punto idraulicamente sfavorito;
6. architettura F1/F2/F3;
7. trattamento acqua;
8. P&ID;
9. schema elettrico/PLC;
10. preventivo completo almeno da 2 fornitori greenhouse-specific;
11. piano manutenzione/ricambi;
12. commissioning con verifica uniformità e assenza di bagnatura indesiderata.
