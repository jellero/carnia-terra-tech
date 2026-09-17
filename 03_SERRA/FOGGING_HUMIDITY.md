# Carnia TerraTech — Fogging & Humidity Management

**Aggiornato:** 17 settembre 2026  
**Stato:** `BOM-005 SVILUPPATA / PORTATA E TRATTAMENTO BLOCCATI DA ANALISI ACQUA E CALCOLO CLIMATICO`.

## 1. Funzione

Il fogging è un sottosistema climatico per:

- raffrescamento evaporativo;
- controllo UR/VPD;
- supporto a fasi sensibili di coltura/propagazione.

Non è irrigazione e non deve creare bagnatura fogliare persistente.

## 2. Compartimenti prioritari

- C1 pomodoro;
- C2 peperone;
- C6 basilico/vivaio/jolly.

C3–C5: predisposizione solo se futura analisi clima/agronomia dimostra utilità.

## 3. Architetture aperte

La BOM-005 confronta:

- **F1:** una pompa centrale + tre zone;
- **F2:** centrale ridondata N+1;
- **F3:** una pompa indipendente per C1/C2/C6.

Il criterio non è solo CAPEX: confrontare failure domain, manutenzione, consumo, stabilità pressione a carico parziale e costo ricambi.

File completo: `19_BOM_PRODOTTI_FORNITORI/SERRA_FOGGING.md`.

RFQ: `03_SERRA/RFQ_FOGGING.md`.

## 4. Dati obbligatori prima del dimensionamento

- analisi acqua;
- temperatura/UR esterne di progetto;
- volume reale di ciascun comparto;
- ventilazione naturale/reti anti-insetto;
- HAF;
- coltura e VPD target;
- carico evaporativo;
- massima portata evaporabile senza bagnatura;
- pressione/nozzle curve;
- contemporaneità C1/C2/C6.

Nessun numero di ugelli viene definito solo da una regola empirica per m².

## 5. Acqua

Analizzare almeno:

- pH;
- EC/TDS;
- durezza;
- alcalinità/bicarbonati;
- Fe/Mn;
- silice quando rilevante;
- torbidità/solidi;
- cloruri/sali;
- requisiti microbiologici applicabili.

Filtrazione fine è obbligatoria; osmosi/softening sono condizionali alla qualità dell'acqua e alla specifica del costruttore.

Non comprare un impianto RO prima dell'analisi.

## 6. Catena funzionale

`fonte acqua → pretrattamento → eventuale trattamento → protezione low-pressure/dry-run → pompa HP → relief/bypass → collettore → 3 zone HP → linee → ugelli anti-drip → drenaggio/depressurizzazione`

Misure desiderate:

- pressione ingresso;
- pressione HP;
- portata totale o per zona;
- stato pompa;
- fault;
- stato filtri quando economicamente sensato.

## 7. Controllo PLC

Input climatici:

- T/UR;
- VPD calcolato;
- leaf wetness dove previsto;
- aperture;
- HAF;
- fase/orario coltura.

Sequenza minima:

`richiesta → verifica acqua/pressioni/interblocchi → attiva zona → attiva pompa → verifica pressione → ciclo fog → feedback clima → stop → depressurizzazione`.

Il server/cloud non entra nel loop vitale.

## 8. Integrazione con HAF

Prima opzione: usare gli HAF già previsti per uniformare la nebbia, evitando ventilatori nebulizzatori dedicati finché un test reale non dimostra la necessità.

Verificare:

- nessun getto diretto su motori/quadri;
- evaporazione prima della coltura;
- uniformità tra centro/bordi;
- comportamento con aperture e reti anti-insetto.

## 9. Failure modes

- pompa guasta;
- dry-run;
- filtro intasato;
- pressione anomala;
- elettrovalvola bloccata;
- ugello ostruito;
- ugello che gocciola;
- tubo/raccordo HP lesionato;
- sensore UR errato;
- qualità acqua fuori specifica;
- HAF fermo;
- apertura non nella posizione prevista;
- perdita comunicazione PLC;
- blackout;
- gelo.

Il fogging deve poter essere disabilitato senza perdere irrigazione o ventilazione naturale.

## 10. Manutenzione

Prevedere nel piano asset:

- ispezione/sostituzione cartucce;
- pulizia e test ugelli;
- verifica anti-drip;
- controllo perdite/raccordi;
- verifica pressione;
- test dry-run e relief;
- manutenzione pompa;
- scorta tenute e ugelli;
- drenaggio/protezione gelo.

Manuale Tecnocooling esaminato come benchmark:

- controllare filtri prima del funzionamento;
- ugelli degradati vanno serviti/sostituiti;
- cambio olio indicato ogni 800–1000 h per il sistema del manuale;
- invernaggio con drenaggio pompa/linee e spurgo.

L'intervallo definitivo sarà quello del modello acquistato.

## 11. Sicurezza

Una linea ~70 bar richiede:

- componenti con rating dichiarato;
- relief valve;
- depressurizzazione prima di interventi;
- lockout elettrico/idraulico;
- protezione delle linee da urti;
- procedure specifiche perdite HP;
- nessun serraggio/smontaggio sotto pressione.

## 12. Stato economico

Sono ora disponibili benchmark reali per:

- pompe 5,5–21 L/min;
- ugelli inox/anti-drip;
- tubo inox e PA12;
- raccordi;
- elettrovalvole HP;
- filtrazione.

Il totale resta `DA PREVENTIVO` perché numero ugelli, metri tubo, portata e trattamento acqua dipendono da calcolo climatico, layout e analisi acqua.
