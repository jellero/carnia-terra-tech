# Smart crate + smart cart — architettura frictionless retail

**Aggiornato:** 18 settembre 2026  
**Ambito:** sottoarchitettura BOM-028 spaccio automatico self-service 24/7.  
**Stato:** `R&D CANDIDATO PRIORITARIO / PROTOTIPO E METROLOGIA LEGALE BLOCCANTI`.

## 1. Obiettivo

Eliminare il collo di bottiglia della cassa.

Il cliente deve poter:

1. prendere un carrello/cestino intelligente;
2. prelevare il prodotto;
3. vedere immediatamente sul display cosa ha preso, peso e prezzo;
4. rimettere il prodotto e vedere il carrello aggiornarsi;
5. pagare senza scaricare/scansionare la merce;
6. uscire soltanto quando la sessione è in stato `PAID`.

La "cassa" diventa quindi un **evento software**, non un punto fisico di scansione.

## 2. Architetture considerate

### A — rullo + pesa + camera

Flusso:

`cliente -> rullo -> camera -> bilancia -> riconoscimento -> prezzo -> pagamento`

Pro:
- riconoscimento semplice;
- una sola stazione metrologica;
- manutenzione concentrata;
- facile da validare;
- costo hardware contenuto.

Contro:
- ricrea una coda;
- richiede manipolazione extra;
- cliente deve scaricare il carrello;
- throughput limitato dalla stazione;
- guasto stazione = blocco vendite.

**Uso consigliato:** fallback/manual recovery e laboratorio di training AI, non baseline frictionless.

### B — smart crate / smart shelf

Ogni cassetta o posizione conosce già lo SKU.

Sensori:
- peso;
- apertura/movimento opzionale;
- camera area;
- presenza/prossimità.

Evento base:

`crate_A mass 12.42 kg -> 11.61 kg = -0.81 kg`

Il sistema sa che la cassetta A contiene pomodoro SKU X.

Pro:
- identificazione prodotto quasi gratuita perché deriva dalla posizione;
- nessun riconoscimento CV complesso per SKU normali;
- rileva pick e return;
- inventario reale continuo;
- refill automatico;
- ottimo per forecasting.

Contro:
- associare il prelievo al cliente corretto in presenza di più persone;
- vibrazioni/urti;
- cassette spostate;
- tara;
- metrologia legale se il peso determina direttamente il prezzo.

### C — smart cart

Il carrello integra:

- display;
- compute;
- camera;
- sensore massa del cestello;
- localizzazione;
- session ID;
- eventuale payment reader;
- battery/charging.

Pro:
- UI personale senza telefono;
- vede immediatamente carrello/prezzo;
- il peso del carrello può confermare l'evento di prelievo;
- removal dal carrello rilevabile;
- pagamento sul carrello possibile;
- antifurto/cart tracking;
- canale diretto per ricette, info lotto, offerte e assistenza.

Contro:
- costo per carrello;
- batteria/ricarica;
- urti/acqua;
- manutenzione display;
- la pesa mobile è più difficile da usare come misura commerciale certificata;
- camera sul carrello non vede sempre la provenienza del prodotto.

## 3. Baseline proposta — sensor fusion smart crate + smart cart

Per Carnia TerraTech la baseline R&D è:

`smart crate + cart scale + camera + location + event correlation`

Non affidarsi a un solo sensore.

### Pick

1. cliente/carrello entra nella zona della cassetta;
2. smart crate misura `-Δm`;
3. carrello misura quasi simultaneamente `+Δm`;
4. camera rileva hand/product transfer;
5. server correla:
   - time;
   - location;
   - SKU crate;
   - Δm crate;
   - Δm cart;
   - customer/cart session;
6. evento diventa `ITEM_ADDED`;
7. display carrello mostra:
   - prodotto;
   - peso;
   - €/kg;
   - prezzo riga;
   - totale.

### Return

1. cart mass `-Δm`;
2. crate mass `+Δm`;
3. posizione e camera confermano;
4. evento `ITEM_REMOVED`;
5. totale aggiornato.

## 4. Perché questa architettura è robusta

La crate conosce **cosa**.

Il carrello sa **chi** e verifica **quanto è entrato**.

La camera verifica **che l'evento fisico sia plausibile**.

Il server decide soltanto quando i segnali sono coerenti.

Confidence score esempio:

`confidence = crate_match + cart_mass_match + proximity + vision_event + temporal_match`

Stati:

- `CONFIRMED`;
- `PROVISIONAL`;
- `NEEDS_CUSTOMER_CONFIRMATION`;
- `STAFF_REVIEW`.

Mai addebitare silenziosamente un evento a bassa confidenza.

## 5. Metrologia legale

Le celle di carico economiche possono essere usate liberamente come:

- presence sensor;
- inventory sensor;
- anomaly sensor;
- cross-check.

Se il prezzo pagato viene determinato dal peso, la misura commerciale deve provenire da una catena metrologica idonea alla funzione di misura legale applicabile.

La Direttiva 2014/31/UE include esplicitamente:

- determinazione della massa per transazioni commerciali;
- determinazione del prezzo in funzione della massa per vendita diretta al pubblico.

Per prodotti sfusi venduti a peso, la prassi metrologica italiana richiede strumenti idonei/omologati e peso netto visibile al cliente.

**Regola di progetto:**
- cheap load cell != automaticamente bilancia legale.

Tre opzioni da prototipare:

### M1 — modulo di pesatura certificato per smart crate

Ogni stazione peso che determina il prezzo usa componenti e terminale conformi.

Pro:
- peso associato direttamente allo SKU;
- ottima precisione.

Contro:
- costo e verifiche moltiplicati per molte cassette.

### M2 — modulo certificato integrato nel carrello

Ogni carrello determina il Δpeso aggiunto.

Pro:
- una bilancia per carrello anziché per SKU.

Contro:
- superficie mobile/non livellata;
- urti;
- comportamento dinamico;
- certificazione più difficile.

### M3 — smart sensing + stazione legal-for-trade di conferma

Smart crate/cart costruiscono il carrello virtuale; prima del pagamento, una singola pesa certificata esegue un check/confirm automatico del totale o dei prodotti a peso.

Pro:
- basso numero di strumenti legali;
- ottimo fallback.

Contro:
- piccola interazione finale;
- il check massa totale non separa sempre gli SKU.

**Working recommendation:** prototipare M1 e M3; non assumere M2 come conforme finché non viene validato da specialista metrologico.

## 6. Display: niente "1000 schermi"

Non serve un display per prodotto.

### Shelf edge / cassetta

Un piccolo e-paper/ESL per **cassetta o posizione SKU** mostra:

- nome;
- €/kg o €/pz;
- origine;
- lotto/raccolto oggi;
- promo;
- QR;
- eventuale stock/LED solo lato operatore.

Le ESL moderne sono pensate per aggiornamento centralizzato, BLE e impieghi retail; esistono anche versioni waterproof/IP68 per reparti freschi.

Il numero di display è quindi:

`numero posizioni SKU`

non:

`numero prodotti fisici`.

Con 30 SKU:
- ~30 ESL.

Con 100 SKU:
- ~100 ESL.

Non 1000 salvo un negozio di scala molto diversa.

### Carrello

Sul carrello serve invece un display dinamico LCD/OLED, non e-paper:

- basket live;
- peso/prezzo;
- totale;
- warning;
- prodotto restituito;
- payment state;
- ricette;
- provenienza;
- assistenza.

E-paper sul carrello è troppo lento per una UI transazionale.

## 7. Smart cart hardware working

Ogni carrello/cestino smart:

- display 7–10";
- SBC/edge computer;
- Wi-Fi;
- BLE;
- UWB opzionale;
- IMU;
- 1–2 camera wide-angle;
- load platform/celle per cross-check;
- battery;
- dock contacts;
- buzzer/LED;
- cart ID;
- electronic wheel lock opzionale;
- emergency/manual release.

Lo schermo non contiene business logic critica.

Il server centrale resta master.

## 8. Localizzazione

Per correlare un pick:

### L1 — BLE proximity
Economica, precisione metri.

### L2 — UWB
Precisione molto migliore per associare carrello/area/cassetta.

### L3 — camera tracking
Ottima per conferma evento, più delicata lato privacy/occlusioni.

Working:
- UWB/BLE sul carrello;
- zone note delle smart crates;
- camera per conferma, non facial recognition.

Non serve identificare biometricamente il cliente.

## 9. Vision

La CV non deve necessariamente classificare ogni pomodoro.

Se la cassetta A = SKU A, la camera deve soprattutto capire:

- mano entra/esce;
- oggetto trasferito;
- direzione pick/return;
- numero oggetti;
- anomalia;
- cliente/carrello coinvolto.

Questo riduce drasticamente la complessità del modello.

Per una stazione AI scale fallback, esistono già bilance commerciali con camera per riconoscimento automatico ortofrutta, ad esempio DIGI SM-6000 AI e Tiliter AI Scale.

Queste sono benchmark di fattibilità, non baseline di acquisto.

## 10. Pagamento senza cassa

Tre modalità.

### P1 — pagamento al carrello

Reader Stripe integrato nel carrello.

Pro:
- esperienza perfetta.

Contro:
- reader per ogni cart;
- alimentazione;
- urti/weather;
- costo e service.

### P2 — pagamento al gate di uscita

Il carrello arriva al gate con totale già pronto.

Cliente:
- controlla totale sul display;
- tap card/phone sul UX700 fisso;
- pagamento;
- gate apre.

Tempo al gate: solo pagamento, nessuna scansione/pesatura.

Pro:
- un reader serve molti carrelli;
- reader fisso e protetto;
- minore CAPEX/manutenzione.

Contro:
- micro-collo di bottiglia se arriva molta gente insieme.

### P3 — payment method associato all'ingresso

Il cliente associa carta/wallet alla sessione e il server finalizza il totale in uscita secondo il flusso autorizzato.

Stripe Terminal supporta raccolta/salvataggio di metodi di pagamento e PaymentIntent con capture manuale; l'uso concreto per questa esperienza richiede consenso, SCA/network rules e pilot.

**Working recommendation:** P2 baseline; P1 future premium; P3 R&D per clienti registrati.

## 11. Exit gate

Il gate non è una cassa.

Input:
- cart ID;
- session status;
- payment status;
- anomaly state.

Apertura:

`PAID && CART_RECONCILED && NO_BLOCKING_ANOMALY`

Vincoli safety:
- uscita persone sempre possibile;
- nessun intrappolamento;
- emergency release;
- fire/evacuation override;
- nessun blocco che impedisca l'esodo.

Il carrello può avere wheel lock/geofence antifurto, ma non deve essere il mezzo primario per trattenere una persona.

## 12. Cart return

### Opzione R1 — nested return/charging

Baseline.

Il cliente restituisce il carrello in una baia annidata vicino ingresso/uscita.

Pro:
- semplice;
- ricarica automatica;
- zero autonomia veicolare.

Il mercato dimostra già smart cart con nested charging e geofencing/wheel lock.

### Opzione R2 — recovery rover

Usare un rover/AMR outdoor esistente o dedicato per recuperare una fila di carrelli.

Pro:
- non motorizza ogni cart;
- un solo robot;
- riuso tecnologie aziendali.

Contro:
- hitch automatico;
- pedestrian safety;
- percorso;
- docking;
- meteo.

### Opzione R3 — ogni carrello autonomo

Non baseline.

Contro:
- motori;
- sterzo;
- battery;
- safety;
- certificazione;
- costo;
- manutenzione × N carts.

**Raccomandazione:** R1 subito; R2 solo se il parcheggio/volume lo giustificano.

## 13. Inventario reale

Smart crates diventano anche sistema inventario.

Per ogni crate:

- tare;
- gross mass;
- estimated net stock;
- SKU;
- lot;
- shelf life;
- temperature class;
- last refill;
- expected depletion;
- anomaly.

Il server sa in tempo reale:

`stock CR-A -> transfer -> crate -> customer cart -> paid sale`

Questo chiude la tracciabilità fisica del prodotto.

## 14. Servizi possibili sul display carrello

### Customer UX
- totale live;
- kg e prezzo;
- rimozione immediata;
- ricevuta;
- lingua;
- accessibilità;
- help.

### Provenienza
- serra/comparto;
- data raccolta;
- lotto;
- varietà;
- metodo;
- distanza "0 km".

### Ricette
- suggerimenti basati sul basket;
- sostituzioni;
- quantità mancanti.

### Domanda/offerta
- promo su prodotto abbondante;
- markdown vicino fine shelf-life;
- bundle;
- suggerimenti senza profilazione invasiva.

### Fattoria didattica
- "questo pomodoro è stato raccolto oggi nel comparto C1";
- consumo acqua/energia del lotto come contenuto opzionale.

## 15. Servizi lato operatore

- stock live;
- refill prediction;
- pick-to-light sull'ESL;
- route di rifornimento;
- anomaly;
- crate displaced;
- tare drift;
- sensor health;
- low battery cart;
- cart missing;
- payment/vend mismatch;
- shrink suspicion;
- cleaning task.

## 16. Forecasting

I dati sono molto migliori del semplice POS.

Il server osserva:

- pick;
- return;
- dwell time;
- stockout;
- vendita;
- quantità/prezzo;
- promo;
- posizione;
- ora;
- meteo.

Questo permette di distinguere:

- domanda reale;
- curiosità;
- prodotto preso e rimesso;
- mancata vendita per stockout.

Forecast output:

- refill next 30/60/120 min;
- harvest tomorrow;
- pack quantity;
- expected waste;
- dynamic promotion candidate.

## 17. Dynamic pricing

Tecnologicamente semplice con ESL + server.

Regola:
- prezzo mostrato sulla cassetta deve essere coerente con quello applicato;
- snapshot del prezzo al momento dell'evento;
- ogni cambio prezzo auditato;
- il cliente vede il prezzo nel carrello immediatamente.

Niente prezzi personalizzati individualmente nella baseline.

Preferire:
- markdown trasparenti per shelf-life;
- surplus;
- fascia oraria;
- bundle.

## 18. Privacy

Vision serve a correlare eventi, non identità.

Baseline:
- no face recognition;
- no biometric profile;
- no audio;
- tracking per cart/session ID;
- elaborazione edge dove possibile;
- retention minima;
- blur/masking dove utile;
- log evento conservato più del video solo quando possibile.

## 19. Shrink / antifrode

Sensor fusion segnala:

- crate -800 g senza cart +800 g;
- cart +800 g senza crate event;
- prodotto spostato fra cassette;
- cart exit con reconciliation mismatch;
- occlusione camera;
- peso cart incoerente col basket virtuale.

Azioni:
- chiedi conferma sul display;
- reweigh;
- blocca soltanto il checkout del cart, non la persona;
- staff review;
- audit.

## 20. Failure modes

| Failure | Fallback |
|---|---|
| smart crate scale down | crate in MANUAL/NO-WEIGHT |
| camera down | crate+cart fusion senza CV se confidence sufficiente |
| cart scale down | crate event + customer confirm |
| UWB down | BLE/camera/proximity |
| cart display down | cart out of service |
| ESL down | prezzo master server + cart display; sostituire ESL |
| server down | no nuove sessioni frictionless; fallback vending/AI scale |
| network down | edge buffer; bloccare payment se non riconciliabile |
| event ambiguous | customer confirmation |
| return ambiguous | reweigh/confirmation |
| metrology fault | prodotti a peso non vendibili in modalità frictionless |
| payment fault | session pending/retry/refund |

## 21. Phasing

### F0 — digital store
- central server;
- Stripe;
- e-paper labels;
- normal vending/locker.

### F1 — smart crate pilot
- 3 SKU;
- cheap load cells;
- overhead camera;
- no commercial price from experimental scale;
- inventory/event detection.

### F2 — smart cart pilot
- 1 cart;
- display;
- scale cross-check;
- UWB/BLE;
- 10 SKU;
- real-time basket.

### F3 — metrology pilot
- legal-for-trade partner;
- compare M1/M3;
- calibrations;
- tare;
- direct-sale display requirements.

### F4 — frictionless live pilot
- 20–30 SKU;
- 2 carts;
- Stripe exit gate;
- 500+ transactions.

### F5 — scale
- more carts;
- more crates;
- predictive refill;
- dynamic markdown;
- recovery rover only if justified.

## 22. Acceptance KPI

- product association >=99.5% after customer confirmations;
- mass reconciliation within legal/engineering tolerance defined by metrology design;
- unhandled pick <0.5%;
- unhandled return <0.5%;
- inventory variance <1%;
- no double charge;
- no charge without reconciled basket;
- payment-to-exit median <10 s;
- cart battery >= full operating day;
- refill task generated before critical stockout;
- zero biometric identification.

## 23. Decision

**Candidato prioritario:** smart crate + smart cart sensor fusion.

**Non prioritario:** rullo come checkout principale.

**Fallback:** AI scale / certified weighing station.

**Display strategy:** e-paper per crate/SKU, LCD sul carrello.

**Payment baseline:** Stripe UX700 fisso all'uscita; reader su cart solo fase successiva.

**Cart return baseline:** nested dock/charging; autonomous recovery rover solo se economicamente giustificato.

## 24. Fonti di fattibilità

- Caper Cart: cart con computer vision, weight scale, product add/remove recognition, pagamento sul cart, nested charging, GPS/geofence e wheel lock;
- Cust2Mate: cart retrofit con display, scanner/CV/AI/weight/RFID e on-cart scale;
- Shekel Smart Bay: smart shelf basato su sensori peso per grab-and-go;
- DIGI SM-6000 AI: bilancia AI con camera per riconoscimento automatico ortofrutta;
- Tiliter AI Scale: recognition + scale per fresh produce;
- Vusion ESL: electronic shelf labels BLE, anche waterproof per fresh area;
- Direttiva 2014/31/UE e metrologia legale italiana per vendita a peso.

