# BOM-027 — Fattoria didattica

**Aggiornato:** 18 settembre 2026  
**Ambito:** visitor route + sicurezza + accessibilità + didattica + riconoscimento ERSA.  
**Stato:** `ARCHITETTURA STRUTTURATA / QUANTITÀ DA MASTERPLAN E CAPIENZA / ERSA E RFQ BLOCCANTI / BENCHMARK UNITARI DISPONIBILI`.

## 1. Regola di lettura

Questa BOM non assegna una capienza fittizia e non duplica infrastrutture già previste.

Stati quantità:

- `DA MASTERPLAN` — deriva dal tracciato reale;
- `DA CAPIENZA` — deriva dal numero visitatori ammesso;
- `DA RISCHIO` — deriva dalla valutazione rischio;
- `INTERFACE` — costo già in altro package, qui solo integrazione;
- `RFQ` — prezzo non affidabile senza progetto.

Prezzi osservati il 18 settembre 2026 salvo diversa indicazione.

## 2. Distinta pezzo per pezzo

| Codice | Voce | Q.tà | UM | Stato | Benchmark unitario |
|---|---|---:|---|---|---:|
| FD-COURSE | percorso formativo operatore fattoria didattica | 1 referente min. | percorso | OBBLIGATORIO | corso base 2026 osservato gratuito per aventi diritto; percorso completo da confermare ERSA |
| FD-ERSA | domanda/sopralluogo/riconoscimento ERSA | 1 | pratica | OBBLIGATORIO | costo amministrativo DA VERIFICARE |
| FD-RC | RC attività didattica | 1 | anno | OBBLIGATORIO | RFQ assicurazione |
| FD-PROJ-DID | progetto didattico | 1 | lotto | OBBLIGATORIO | interno/consulenza |
| FD-MAP | planimetria quotata + zoning + percorsi | 1 | lotto | OBBLIGATORIO | tecnico/RFQ |
| FD-RISK | visitor risk assessment / procedure | 1 | lotto | BASELINE | interno/consulenza |
| FD-PARK | parcheggio/drop-off mezzo accompagnatore | DA MASTERPLAN | lotto/m² | OBBLIGATORIO | RFQ |
| FD-PATH | percorso pedonale drenante | DA MASTERPLAN | m² | BASELINE | FVG 2026 €37,05–39,76/m² per voce 5 cm pedonale, secondo posa |
| FD-PATH-BASE | sottofondo percorso ove richiesto | DA PROGETTO | m³ | CONDITIONAL | FVG 2026 fondazione granulare ~€44,80/m³ |
| FD-RAMP | raccordi/rampe accessibilità | DA MASTERPLAN | lotto | CONDITIONAL | RFQ/progetto |
| FD-REST | area di sosta percorso | DA MASTERPLAN | cad | BASELINE | arredo/RFQ |
| FD-BARRIER | barriera visitatori Z1/Z3 | DA MASTERPLAN | m | BASELINE | RFQ |
| FD-GATE-PED | gate pedonale visitatori | DA MASTERPLAN | cad | BASELINE | RFQ |
| FD-GATE-TECH | gate separazione tecnica | DA MASTERPLAN | cad | CONDITIONAL | RFQ |
| FD-OBS-GH | observation point serra | 1 o più DA MASTERPLAN | set | CANDIDATO | RFQ |
| FD-OBS-WATER | observation point acqua | DA PROGETTO | set | CANDIDATO | RFQ |
| FD-OBS-ENERGY | observation point energia/FV | DA PROGETTO | set | CANDIDATO | RFQ |
| FD-OBS-ANIMAL | punto osservazione area animali | 1 | set | SOLO SE ANIMALI | costo marginale + RFQ |
| FD-WC-ACC | servizio igienico accessibile completo | 1 o DA CAPIENZA | set | OBBLIGATORIO | RFQ, classe prezzario FVG 74.3 |
| FD-WC-SIGN | segnaletica WC/accessibilità | DA LAYOUT | cad | BASELINE | FVG safety signage class ~€34,63–43,46/cad per pannelli PVC benchmark |
| FD-HAND-PERM | lavamani permanente | DA LAYOUT | set | BASELINE | RFQ impiantistico |
| FD-HAND-PORT | lavamani autonomo inox backup/pilot | 0–1 | cad | FALLBACK | €242,10 retail benchmark |
| FD-SOAP | dispenser sapone | DA LAYOUT | cad | BASELINE | RFQ |
| FD-TOWEL | dispenser asciugatura | DA LAYOUT | cad | BASELINE | RFQ |
| FD-BIN | cestino lavamani/WC | DA LAYOUT | cad | BASELINE | RFQ |
| FD-FIRSTAID | cassetta/valigetta primo soccorso | 1 + DA RISCHIO | cad | OBBLIGATORIO | €75,90 + IVA valigetta All.1 / €117,90 + IVA armadietto maggiorato benchmark |
| FD-FIRST-REFILL | reintegro primo soccorso | OPEX | kit | BASELINE | ~€65,25 benchmark reintegro |
| FD-FIRST-SIGN | cartello primo soccorso | 1 | cad | BASELINE | FVG signage reference |
| FD-WATER-POT | punto acqua potabile vicino primo soccorso | 1 | set | OBBLIGATORIO | RFQ / existing interface |
| FD-MUSTER | punto raccolta emergenza | 1 | set | BASELINE | segnale + area |
| FD-EMAP | planimetria emergenza/visitor map | DA ACCESSI | cad | BASELINE | grafica + pannello |
| FD-SAFE-SIGN | cartello safety standard | DA RISCHIO | cad | BASELINE | FVG 2026 €34,63–43,46/cad PVC benchmark |
| FD-STICKER | cartello safety autoadesivo | DA RISCHIO | cad | CONDITIONAL | FVG 2026 ~€5,57–8,12/cad benchmark |
| FD-WAYFIND | wayfinding/frecce | DA MASTERPLAN | cad | BASELINE | RFQ |
| FD-DID-PANEL | pannello didattico Dibond 70×100 stampato | DA MODULI | cad | CANDIDATO | €90/cad benchmark |
| FD-DID-PANEL3 | 3 pannelli Dibond 70×100 stesso soggetto | DA MODULI | set | BENCHMARK | €169/set benchmark |
| FD-QR | QR/link + asset digitale | DA MODULI | cad | BASELINE | costo grafica/software interno |
| FD-COVER | spazio coperto | 1 | area | OBBLIGATORIO | INTERFACE BOM-026 o futura aula |
| FD-TABLE-ACC | tavolo picnic accessibile | DA CAPIENZA | cad | CANDIDATO | €439,79 retail benchmark |
| FD-TABLE | tavoli gruppo | DA CAPIENZA | cad | BASELINE | interface BOM-026 / RFQ |
| FD-SEAT | sedute | DA CAPIENZA | cad | BASELINE | interface BOM-026 / RFQ |
| FD-WHITEBOARD | lavagna magnetica 120×90 | 1 | cad | CANDIDATO | €85,73 benchmark parete |
| FD-STORAGE | armadio didattico chiudibile | 1+ | cad | BASELINE | RFQ |
| FD-DEMO-WATER | kit dimostrativo acqua | 1 | kit | CANDIDATO | interno/RFQ |
| FD-DEMO-ENERGY | kit dimostrativo energia | 1 | kit | CANDIDATO | interno/RFQ |
| FD-DEMO-SENSOR | sensori demo | 1 | kit | CANDIDATO | interface automazione/RFQ |
| FD-TABLET | tablet didattico | 0–1+ | cad | OPTIONAL | existing/IT RFQ |
| FD-DISPLAY | display dashboard | 0–1 | cad | OPTIONAL | RFQ |
| FD-WIFI | copertura guest Wi-Fi | 1 | area | BASELINE | INTERFACE BOM-026 U7 Outdoor €185 if not already counted |
| FD-NET-SEG | guest VLAN/firewall policy | 1 | config | BASELINE | interno/IT |
| FD-ANIMAL-BARR | barriera area animali | 1 | set | SOLO SE ANIMALI | interfaccia area animali + RFQ |
| FD-ANIMAL-SIGN | igiene/comportamento animali | 1+ | cad | BASELINE IF ANIMALS | pannello/RFQ |
| FD-VIS-VEST | gilet hi-vis per visite tecniche fuori percorso | DA RISCHIO | cad | OPTIONAL | ~€4,13/cad benchmark set 4 / €10,41 pro benchmark |
| FD-CLEAN | kit pulizia area visitatori | 1 | set | BASELINE | RFQ |
| FD-CONS | sapone/carta/sacchi/materiali didattici | OPEX | anno/visita | BASELINE | da utilizzo |
| FD-REGISTER | registro visite | 1 | sistema | OBBLIGATORIO | digitale/cartaceo |
| FD-PILOT | visita pilota/commissioning | 1+ | evento | OBBLIGATORIO | costo interno |
| FD-ASBUILT | as-built visitor route | 1 | lotto | BASELINE | tecnico/RFQ |

## 3. Formazione e riconoscimento

La pagina ERSA corrente per la domanda indica che gli imprenditori agricoli in possesso dell'attestato del relativo corso possono chiedere il sopralluogo ai fini dell'iscrizione nell'Elenco regionale.

Il catalogo formativo FVG 2026 osservato riporta:

- **Fattoria didattica e sociale (Base) — aspetti sanitari, sicurezza e adempimenti normativi**;
- durata pubblicata: **12 ore**;
- partecipazione pubblicata: **gratuita** per i soggetti ammessi;
- il corso base è indicato come **parte 1 di 2**;
- il catalogo include anche **Fattoria didattica (specialistico) — normativa, progettazione e requisiti per il riconoscimento**, durata indicata **24 ore**.

**Procurement rule:** prima di pianificare calendario/costo, confermare con ERSA il percorso formativo corrente effettivamente richiesto al referente e la disponibilità delle edizioni.

## 4. Assicurazione

Non viene stimato un premio generico.

RFQ deve esplicitare:

- minori;
- gruppi scolastici;
- animali;
- attività pratiche;
- percorsi esterni;
- eventuali laboratori;
- frequenza;
- massimale;
- franchigie;
- esclusioni.

Costo = `DA RFQ ASSICURATIVO`.

## 5. Percorsi

Prezzario FVG 2026, pavimentazione drenante eco-compatibile spessore 5 cm per percorsi pedonali/ciclabili senza transito veicolare:

- posa con finitrice: **€37,05/m²**;
- posa a mano: **€39,76/m²**.

Questi valori non definiscono il pacchetto completo del percorso.

Da aggiungere se necessari:

- scavo;
- sottofondo;
- cordoli;
- drenaggio;
- raccordi;
- rampe;
- segnaletica;
- protezioni;
- attraversamenti.

Fondazione stradale granulare FVG 2026:
- riferimento 95% AASHTO: **€44,80/m³**.

La superficie finale viene scelta da accessibilità, gelo, drenaggio e manutenzione.

## 6. Servizio igienico accessibile

È un requisito strutturale del package ma il costo viene lasciato a RFQ.

Motivo:

`WC completo = locale + accessibilità + sanitari + maniglioni + porta + acqua + scarico + ventilazione + elettrico + finiture + posa`.

Il Prezzario FVG contiene una classe dedicata a apparecchi sanitari e attrezzature per disabili; usare l'edizione vigente al momento del computo.

Non riportare il prezzo del solo vaso/lavabo come costo del servizio completo.

## 7. Lavaggio mani

Benchmark portatile:

Lioninox XS-E:
- inox AISI 304;
- comando a pedale;
- autonomo;
- prezzo osservato **€242,10**.

Uso previsto:
- pilot;
- backup;
- stazione temporanea.

Per apertura stabile, preferenza a stazione permanente con acqua/scarico dove tecnicamente realizzabile.

## 8. Primo soccorso

Benchmark CFS osservati:

- valigetta MEDIC 4 Allegato 1 DM 388: **€75,90 + IVA**;
- armadietto metallico Allegato 1 maggiorato: **€117,90 + IVA**;
- reintegro Allegato 1 maggiorato con sfigmomanometro: **€65,25 + IVA**.

Il contenuto effettivo deve essere coerente con la classificazione/primo soccorso aziendale applicabile.

ERSA richiede la presenza di materiale di primo soccorso vicino a una fonte d'acqua potabile.

## 9. Safety signage

Prezzario FVG 2026, cartelli safety PVC con posa:

- quadrato monofacciale, percezione 6 m: **€34,63/cad**;
- quadrato monofacciale, percezione 10 m: **€41,97/cad**;
- rettangolare e altre varianti: ordine di grandezza **€34–43/cad** nelle voci consultate.

Autoadesivi:
- circa **€5,57–8,12/cad** nelle voci consultate.

Usare cartelli normati per safety; i pannelli didattici non li sostituiscono.

## 10. Pannelli didattici

Benchmark stampa diretta outdoor:

- Dibond 70×100, 1 pannello: **€90** osservato;
- 3 pannelli 70×100 stesso soggetto: **€169** osservato.

Altro benchmark:
- Dibond stampato 70×100: **€132** presso altro fornitore.

Separare:

- grafica;
- traduzioni;
- stampa;
- supporti/pali;
- installazione;
- QR;
- manutenzione.

Non usare un unico pannello sovraccarico per tutto il percorso.

## 11. Tavolo accessibile

Benchmark retail:

- tavolo picnic accessibile per carrozzina, configurazione osservata: **€439,79**.

Altro prezzo dello stesso/analogo prodotto osservato:
- **€408,38**.

Il prodotto è solo benchmark arredo. Spazi di manovra, fondo e layout devono essere verificati nel progetto di accessibilità.

## 12. Lavagna

Benchmark Nobo 120×90:
- **€85,73** osservato per lavagna magnetica da parete.

Versioni mobili 120×90:
- circa **€195–275** nei benchmark osservati.

Baseline preferita: parete/struttura stabile se lo spazio coperto lo consente.

## 13. Rete e dashboard

BOM-026 contiene già il working candidate outdoor:

- Ubiquiti U7 Outdoor: **€185**;
- Ethernet Surge Protector: **€12**.

BOM-027 non li riconta se già installati.

Costo marginale fattoria didattica:

- guest SSID/VLAN;
- ACL/firewall;
- captive portal solo se realmente necessario;
- QR/content server;
- dashboard read-only.

**No route da guest network a PLC/OT.**

## 14. Visitor vest

Non baseline per i normali gruppi se il percorso è correttamente segregato.

Benchmark:

- set 4 gilet hi-vis: **€16,50**;
- prodotto professionale benchmark: **€10,41/cad**.

Uso:
- tecnici/adulti in visite speciali;
- emergenze/identificazione accompagnatori;
- non come sostituto di barriere o segregazione.

## 15. Pergolato BOM-026

Se BOM-026 soddisfa spazio coperto e capienza:

- non duplicare struttura;
- non duplicare luci;
- non duplicare prese;
- non duplicare Wi-Fi;
- contabilizzare soltanto costo marginale didattico.

Possibili extra BOM-027:

- tavolo accessibile;
- lavagna;
- armadio;
- pannelli;
- kit;
- eventuale protezione meteo laterale solo se strutturalmente ammessa.

## 16. Area animali futura

Non duplicare:

- recinto animali;
- dirty dock;
- gate logistici;

Aggiungere solo:

- visitor barrier;
- observation point;
- pannello;
- handwash/wayfinding;
- procedura visita;
- lockout dinamico macchine.

## 17. CAPEX formula

`CAPEX_027 = progettazione + percorso + separazioni + WC + igiene + first aid + segnaletica + observation points + arredi marginali + didattica + IT marginale + commissioning`.

Sottrarre/deduplicare:

`asset condivisi = BOM-026 + eventuale area animali + viabilità/parcheggi masterplan + IT/elettrico esistente`.

Non viene calcolato un totale finché mancano:

- m² percorso;
- m barriere;
- capienza;
- soluzione WC;
- numero stazioni didattiche;
- opere civili.

## 18. OPEX

Da quotare/misurare:

| Voce | Driver |
|---|---|
| RC | anno / attività |
| referente visite | ore/visita |
| preparazione | ore/visita |
| pulizia | visite/capienza |
| sapone/carta | visitatori |
| ristampa pannelli | degrado/contenuti |
| materiali didattici | visite |
| manutenzione percorso | m² |
| manutenzione barriere | m |
| manutenzione WC | uso |
| reintegro first aid | scadenze/uso |
| formazione | requisiti/turnover |
| IT/content | apparati/contenuti |

## 19. Contributi

Esiste una pagina regionale recente dedicata a un contributo straordinario per imprese agricole con fattorie didattiche/sociali relativo a aule polifunzionali e laboratori.

**Regola:** nessun contributo viene inserito nel business case come certo.

Verificare al momento della domanda:

- apertura effettiva;
- scadenza;
- requisiti;
- iscrizione all'elenco ERSA;
- spese ammissibili;
- cumulabilità;
- regime aiuto.

## 20. Gate d'acquisto

### Prima di opere civili

- masterplan;
- planimetria ERSA;
- accessibilità;
- capienza;
- WC;
- parcheggio;
- rischio;
- permessi.

### Prima di segnaletica/pannelli

- percorso definitivo;
- naming stazioni;
- safety review;
- progetto didattico.

### Prima di IT

- guest architecture;
- contenuti;
- separazione OT;
- offline fallback.

### Prima dell'apertura

- corso/referente;
- RC;
- sopralluogo/riconoscimento;
- procedure;
- registro visite;
- visita pilota.
