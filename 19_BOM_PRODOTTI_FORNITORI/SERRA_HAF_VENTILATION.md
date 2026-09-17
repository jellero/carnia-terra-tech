# BOM-001 — Ventilazione HAF serra

**Aggiornato:** 17 settembre 2026.  
**Ambito:** 6 comparti × ~700 m².  
**Working quantity esistente:** 4 ventilatori per comparto = 24 unità.  
**Stato:** `CANDIDATO / DA VALIDARE CON LAYOUT E PREVENTIVO`.

## 1. Funzione

La ventilazione HAF (Horizontal Air Flow / ricircolo interno) serve a ridurre stratificazione di temperatura e umidità, zone d'aria stagnante e condensa e a rendere più uniforme il microclima della coltura.

Non sostituisce le aperture di ventilazione né viene trattata come ricambio d'aria esterno.

## 2. Requisiti di progetto

- uso professionale in serra umida;
- funzionamento prolungato;
- protezioni meccaniche sulle pale;
- resistenza alla corrosione;
- manutenzione semplice;
- ricambi disponibili in UE;
- possibilità di isolamento elettrico locale per manutenzione;
- comando almeno per comparto;
- nessun guasto di un singolo ventilatore deve fermare la ventilazione degli altri comparti;
- montaggio che non interferisca con colture, fili di sostegno, schermi e AMR.

La quantità 4/comparto rimane da validare dopo geometria definitiva, altezza utile, schermi e misura/CFD o verifica delle velocità d'aria reali.

---

## 3. Alternativa A — Biemmedue FJ 18 T

**Classificazione:** `PREZZO TROVATO` — candidato baseline.

- produttore: Biemmedue;
- modello: FJ 18 T;
- codice: 02FJ102;
- alimentazione: 400 V trifase, 50/60 Hz;
- portata: 4.750 m³/h;
- potenza dichiarata: 190/210 W;
- diametro ventola: 450 mm;
- struttura interna/esterna inox;
- motore IP44 con protezione termica;
- doppia rete di protezione;
- ganci di sospensione;
- raddrizzatori di flusso.

Fonte tecnica/prezzo:  
https://indors.eu/air-circulator/2649-biemmedue-fj-fan-for-agricultural-greenhouses.html

Scheda tecnica/codici:  
https://www.rea-cz.cz/user/related_files/1645793989_fj.pdf

### Prezzo osservato 17/09/2026

- €298,03 + IVA / **€363,60 IVA inclusa** per la variante mostrata con MPN 02FJ102;
- 24 unità: **€7.152,72 + IVA / €8.726,40 IVA inclusa**;
- eventuale 1 unità completa di scorta: +€298,03 + IVA / +€363,60 IVA inclusa;
- 25 unità inclusa scorta: **€7.450,75 + IVA / €9.090,00 IVA inclusa**.

### Numeri di sistema con 24 unità

- portata nominale sommata: **114.000 m³/h**;
- per comparto: 4 × 4.750 = **19.000 m³/h** di ricircolo nominale;
- potenza targhe complessiva: **4,56–5,04 kW** sulla base del dato 190/210 W;
- per comparto: **0,76–0,84 kW**.

La somma delle portate non equivale automaticamente alla portata utile uniforme nel volume: il posizionamento resta parte del dimensionamento.

---

## 4. Alternativa B — Priva EcoFan+ 4550

**Classificazione:** `PREZZO TROVATO` — candidato efficienza/premium.

- portata: 4.550 m³/h;
- gittata dichiarata: 40 m;
- alimentazione: 230 V, 50 Hz;
- potenza elettrica: 160 W;
- livello sonoro massimo dichiarato: 61,2 dB;
- progettato specificamente per ricircolo aria in serra;
- materiali dichiarati resistenti alla corrosione.

Fonte:  
https://www.hortispares.com/machines/priva-ecofan/

### Prezzo osservato 17/09/2026

- EcoFan+ 4550: **€339,00 + IVA**, esclusi griglia e cavo di alimentazione;
- cavo 5 m dedicato: **€23,50 + IVA**;
- 24 ventilatori: **€8.136,00 + IVA**;
- 24 cavi: **€564,00 + IVA**;
- subtotale noto: **€8.700,00 + IVA**, ancora **escluse le griglie**.

### Numeri di sistema

- 24 × 4.550 = **109.200 m³/h** nominali;
- 24 × 160 W = **3,84 kW**;
- 4 per comparto = **18.200 m³/h** e **640 W** per comparto.

Rispetto al Biemmedue FJ 18 T, il dato di targa indica una potenza complessiva inferiore di circa 0,72–1,20 kW a parità di 24 unità. Ogni 1.000 ore di funzionamento la differenza teorica è circa **720–1.200 kWh**, prima di considerare controllo, condizioni reali e rendimento effettivo.

---

## 5. Alternativa C — Ziehl-Abegg FN040-4EK.0F.V7P1

**Classificazione:** `PREZZO TROVATO / ALTERNATIVA INDUSTRIALE`, non specificamente selezionata come ventilatore serra.

- diametro: 400 mm;
- alimentazione: 230 V monofase;
- portata: 3.800 m³/h;
- potenza: 240 W;
- protezione: IP54;
- velocità: 1.340 rpm.

Fonte:  
https://kaelte4you.de/products/luftereinheit-fn040-4ek-0f-v7p1-ziehl-abegg

### Prezzo osservato 17/09/2026

- **€229,00 + IVA / €272,51 IVA inclusa**;
- 24 unità: **€5.496,00 + IVA / €6.540,24 IVA inclusa**.

### Numeri di sistema

- 24 × 3.800 = **91.200 m³/h**;
- 24 × 240 W = **5,76 kW**.

Costa meno come puro ventilatore, ma non include automaticamente i vantaggi costruttivi specifici per HAF serra del Biemmedue/Priva. Non va scelto solo sul prezzo.

---

## 6. Scelta di lavoro

### Baseline economica attuale

**Biemmedue FJ 18 T — 24 unità + valutazione di 1 unità di scorta.**

Motivi della baseline:

- prodotto esplicitamente destinato a serre;
- inox;
- doppia protezione;
- ganci e raddrizzatori di flusso integrati;
- prezzo retail verificabile;
- produttore italiano;
- costo attuale inferiore al subtotale Priva noto.

### Confronto obbligatorio prima dell'ordine

Il Priva EcoFan+ deve rimanere nel confronto finale perché la minore potenza elettrica di targa potrebbe compensare parte del maggior CAPEX durante molte ore di esercizio.

Nessun ordine finché non sono noti:

- ore HAF previste per coltura/stagione;
- prezzo reale energia del piano economico;
- costo delle griglie Priva;
- preventivo quantità 24/25 pezzi per entrambe le marche;
- trasporto;
- garanzia;
- ricambi e tempi di consegna;
- comportamento con regolazione di velocità se richiesta.

---

## 7. Sotto-BOM installazione — da chiudere prima di dichiarare il sistema `ORDINABILE`

| Voce | Quantità preliminare | Stato costo |
|---|---:|---|
| Ventilatori HAF | 24 | prezzo trovato |
| Ventilatore di scorta | 0–1 | prezzo trovato per baseline |
| punti di sospensione/supporti strutturali | 24 | DA DIMENSIONARE |
| sistemi anticaduta secondari dei ventilatori | 24 | DA SPECIFICARE |
| sezionatore locale bloccabile | 24 | DA QUOTARE |
| protezioni elettriche | per circuito/comparto | DA PROGETTARE |
| contattori/relè comando | per architettura scelta | DA PROGETTARE |
| cassette IP adeguato | da layout | DA QUOTARE |
| cavo potenza | metri da layout | DA MISURARE |
| passerella/canalina/fissaggi | metri da layout | DA MISURARE |
| morsetti, pressacavi, etichette | lotto | DA QUOTARE |
| comando PLC/I/O | 6 zone minimo | da coordinare con BOM automazione |
| manodopera installazione | ore da metodo di montaggio | DA STIMARE |
| collaudo portata/direzione | 6 comparti | DA DEFINIRE |

Non si assegna un forfait agli accessori: verranno quotati riga per riga dopo il layout elettrico e strutturale.

---

## 8. Architettura di controllo proposta

Working concept da validare elettricamente:

- 4 ventilatori per comparto;
- comando di gruppo per comparto dal PLC;
- isolamento locale di ogni singola macchina per manutenzione;
- feedback almeno dello stato del circuito; valutare misura corrente/energia per comparto;
- logica basata su temperatura, UR/VPD, condensa e modalità serra;
- nessuna dipendenza dal server edge per il funzionamento base.

Se si decide la modulazione continua, verificare esplicitamente compatibilità motore/regolatore del modello scelto prima dell'acquisto.

---

## 9. Manutenzione

Da inserire nel piano manutenzione definitivo:

- ispezione visiva protezioni e sospensioni;
- pulizia pale/griglie;
- controllo vibrazioni e rumori;
- serraggio collegamenti/supporti;
- controllo assorbimento elettrico;
- verifica cavi e pressacavi;
- sostituzione immediata di unità rumorose o con vibrazioni anomale;
- almeno una procedura per sostituzione rapida senza fermare il comparto.

Politica ricambi candidata: **1 ventilatore completo a scaffale** se il modello finale non è reperibile con consegna rapida garantita.

---

## 10. Decisioni ancora aperte

1. confermare 4 unità/comparto con geometria definitiva;
2. scegliere 230 V vs 400 V in coerenza con distribuzione elettrica;
3. definire se serve velocità variabile o solo comando on/off/stadi;
4. quotare accessori elettrici e sospensioni pezzo per pezzo;
5. ottenere offerta 24 + 1 unità da Biemmedue/Indors e Priva/Hortispares;
6. confrontare costo totale di possesso su ore annue realistiche;
7. definire posizione fisica rispetto a schermi, colture e corridoi.

## 11. Esito del blocco

La voce "HAF" non è più una cifra generica: esistono tre alternative reali con dati e prezzi verificabili. Il CAPEX del solo hardware ventilatori è oggi compreso tra circa **€6,54k IVA inclusa** per l'alternativa industriale Ziehl-Abegg e **€8,73k IVA inclusa** per 24 Biemmedue FJ 18 T; il Priva richiede ancora il costo delle griglie prima di un confronto completo.

Il prossimo passaggio di questa BOM è chiudere **installazione elettrica e meccanica**; il prossimo sottosistema di progetto in coda è **schermi termici/ombreggianti e relative motorizzazioni**.
