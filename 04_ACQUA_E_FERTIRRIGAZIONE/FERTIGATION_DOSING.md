# Fertirrigazione A/B/acido — architettura e criteri

**Aggiornato:** 17 settembre 2026  
**Stato:** `ARCHITETTURA DEFINITA / CANDIDATI REALI / PORTATE E CHIMICA DA CROP RECIPE E ANALISI ACQUA`.

## 1. Obiettivo

Preparare la soluzione nutritiva in modo misurabile, ripetibile e manutenibile, senza dipendere da un fertirrigatore proprietario chiuso.

Baseline:

`acqua filtrata e pressurizzata -> misura portata -> iniezione A -> miscelazione -> iniezione B -> miscelazione -> eventuale acido in punto dedicato -> miscelazione -> cella misura pH/EC/T -> collettore irrigazione`

L'ordine esatto di A/B/acido resta da validare con la chimica delle ricette e l'alcalinità dell'acqua. Regola obbligatoria: **i concentrati non devono incontrarsi tra loro prima di essere sufficientemente diluiti nell'acqua di processo**.

## 2. Canali iniziali

Tre canali indipendenti:

- **A** — concentrato fertilizzante A;
- **B** — concentrato fertilizzante B;
- **ACID** — correzione pH/alcalinità.

Predisporre almeno un quarto attacco fisico/cablaggio futuro per additivo o trattamento, ma non includere automaticamente disinfettante nella stessa logica di fertirrigazione.

Ogni canale deve avere:

- serbatoio dedicato (BOM-017);
- lancia/valvola di fondo e filtro se richiesto;
- sensore livello minimo;
- pompa dosatrice dedicata;
- tubo aspirazione dedicato;
- tubo mandata dedicato;
- valvola di contropressione se richiesta dalla pompa;
- valvola di sicurezza/relief se richiesta;
- valvola d'iniezione/non ritorno;
- valvole di isolamento;
- colonna/cilindro di calibrazione o metodo gravimetrico tracciabile;
- contenimento secondario e gestione perdite;
- identificazione chimica permanente.

## 3. Controllo

Il PLC locale comanda i canali con setpoint/ricette e applica limiti hard.

Ingressi minimi:

- portata acqua reale;
- pressione processo;
- pH;
- EC;
- temperatura soluzione;
- livelli A/B/acido;
- stato/allarme pompe;
- eventuale flow verification del dosaggio.

Interlock minimi:

- **no flow = no dose**;
- livello chimico basso = blocco del relativo canale;
- sensore pH/EC invalido o fuori plausibilità = stop dosaggio automatico e modalità sicura;
- EC alta = stop A/B;
- pH oltre limite hard = stop acido e allarme;
- perdita/sversamento rilevato = stop canale interessato;
- pompa o valvola non confermata = stop/alarme;
- watchdog PLC locale indipendente da cloud/server.

Imporre anche:

- dose massima per ciclo;
- dose massima per ora;
- tempo minimo di miscelazione/trasporto prima di correggere nuovamente;
- anti-windup del controllo pH/EC;
- rate limit dei comandi.

## 4. Dimensionamento pompe dosatrici

Non scegliere la pompa dal solo numero di litri/ora nominale.

Per ogni canale:

`q_dose,max = Q_acqua,max × ricetta_concentrato,max`

La ricetta concentrato deve essere espressa in L di stock per m³ di acqua o unità equivalente tracciabile.

Verificare:

- q minimo stabile e ripetibile;
- q massimo con margine;
- pressione di iniezione reale;
- turndown utile, non solo dichiarato;
- viscosità/densità;
- degasaggio;
- compatibilità PVDF/PTFE/ceramica/elastomeri;
- accuratezza con contropressione variabile;
- capacità di funzionare con segnale 4–20 mA o impulsi;
- diagnostica sotto/sovraccarico;
- parti di ricambio.

Se il canale richiede stabilmente portate oltre la classe ~20–45 l/h, valutare pompe a membrana motorizzate/peristaltiche industriali invece di sommare molte piccole pompe elettromagnetiche.

## 5. Candidati pompe

### Etatron eOne MF — candidato prioritario di piattaforma

Punti verificati dal costruttore:

- controllo 4–20 mA;
- ingresso flow sensor;
- allarmi underload/overload;
- membrana PTFE;
- corpo PP rinforzato;
- testa PP o PVDF;
- valvole a sfera ceramiche;
- tenute FPM o TFE/P;
- 100–250 Vac;
- fino a 300 impulsi/min;
- più modalità proporzionali.

Prezzi pubblici osservati, IVA esclusa:

- 6 l/h @ 7 bar: **€492**;
- 10 l/h @ 12 bar: **€593**;
- 15 l/h @ 5 bar: **€509**;
- 20 l/h @ 7 bar: **€626**;
- 30 l/h @ 5 bar: **€701**.

Working scenario solo per confronto:

- A: eOne MF 20/7;
- B: eOne MF 20/7;
- ACID: eOne MF 6/7;
- sole pompe: **€1.744 + IVA**.

Scenario A/B 30/5 + acido 6/7: **€1.894 + IVA**.

Queste taglie non sono ancora selezionate.

### SEKO Tekna EVO APG — alternativa economica

APG supporta dosaggio proporzionale da segnale analogico 4–20 mA/digitale, corpo pompa PVDF, membrana PTFE, IP65, 230 V.

APG 603 PVDF-T osservata a **€329 IVA inclusa**; altri retailer mostrano ~€288–390 a seconda di kit/mercato.

La classe 603 è utile come benchmark per piccoli canali, ma può essere insufficiente per A/B a portata massima: verificare curva esatta della variante ordinata.

### ProMinent gamma/X — alternativa premium/RFQ

Gamma/X copre circa **1 ml/h–45 l/h** e 25–2 bar, con diagnostica di pressione/dosaggio e materiali PP/PVDF/PTFE/inox a seconda della configurazione.

Prezzo: `PREZZO DA PREVENTIVO`.

## 6. Misura pH/EC

Preferenza: sensori di processo separabili e sostituibili, segnale standard verso PLC.

Candidato combinato economico/industriale:

**Hanna HI98143-22**

- pH 0–14;
- EC 0–10 mS/cm;
- uscite isolate 4–20 mA;
- 12–24 Vdc;
- IP54;
- prezzo pubblico osservato **€615 + IVA**, sonde escluse.

Il costruttore indica elettrodi pH industriali BNC e sonda EC HI3001 per installazione in linea. Verificare disponibilità/ricambi prima dell'ordine.

Alternativa separata:

- pH transmitter Hanna HI8614LN: **€670 + IVA** benchmark UE;
- EC transmitter Hanna HI8936: da **€327 + IVA**, versione LCD ~€505 + IVA;
- sonda EC 4 anelli HI7638: ~**€420–441 + IVA** a seconda del mercato;
- pH process probe PVDF classe HI1006: ~**€400 + IVA** benchmark.

Strumento portatile indipendente per verifica/calibrazione: Hanna HI9814 pH/EC/TDS/T, **€315 + IVA** in Italia.

## 7. Cella di misura

Non mettere pH/EC in un punto idraulicamente morto.

Prevedere:

- bypass/cella campione con portata nota;
- valvole isolamento;
- presa campione manuale;
- sensore T;
- possibilità di rimuovere/calibrare le sonde senza fermo prolungato;
- drenaggio controllato;
- tempo di trasporto noto tra iniezione e misura.

La posizione deve evitare che il sensore legga una vena di concentrato non ancora miscelata.

## 8. Miscelazione

Confrontare:

- tratto di tubo dimensionato come volume di miscelazione;
- static mixer;
- piccolo loop/mixing vessel solo se tecnicamente necessario.

Scelta su Reynolds, portata minima/massima, perdita di carico, tempi di risposta e pulibilità.

## 9. Calibrazione e verifica

### Pompe

Misurare volume reale dosato a più punti di comando e alla contropressione reale. Salvare curva `comando -> l/h` per ogni pompa.

### pH

Calibrazione a 2 punti con buffer certificati; definire frequenza da deriva reale. Benchmark buffer Hanna pH 4.01 e 7.01: ~€36 + IVA ciascuno nel formato osservato.

### EC

Verifica con standard coerente col range operativo; benchmark soluzione 5.000 µS/cm o 1.413 µS/cm ~€20 + IVA / 500 ml.

Confronto periodico con misuratore portatile indipendente.

## 10. Sicurezza chimica

- SDS disponibile per ogni prodotto;
- compatibilità materiali verificata sul prodotto reale e concentrazione reale;
- A/B/acido fisicamente identificati e non intercambiabili senza procedura;
- bacino/vasca di contenimento dimensionata nel BOM-017;
- ventilazione e accesso manutenzione;
- doccia/lavaocchi e DPI secondo valutazione rischio;
- nessun dosaggio automatico durante manutenzione aperta;
- riempimenti con procedura e tracciamento lotto.

## 11. Failure modes

- pompa bloccata/non dosa;
- sifonamento;
- valvola iniezione bloccata;
- tubo aspirazione pesca aria;
- concentrato finito;
- sensore pH deriva;
- sensore EC sporco/deriva;
- miscelazione insufficiente;
- ricetta errata;
- A/B scambiati;
- acido iniettato senza flusso;
- comando 4–20 mA interrotto;
- PLC o I/O guasto;
- perdita/sversamento.

Fallback: stop automatico dosaggio, acqua sola o ricetta degradata solo se agronomicamente ammessa, misura manuale pH/EC, isolamento del canale guasto.

## 12. Gate

BOM-016 diventa ordinabile con:

1. analisi acqua inclusa alcalinità;
2. crop recipes C1–C6;
3. concentrazione reale stock A/B;
4. acido reale e concentrazione di esercizio;
5. Q acqua min/max;
6. q dose min/max per canale;
7. pressione punto iniezione;
8. materiali compatibili confermati dal produttore;
9. posizione/miscelazione/cella pH-EC;
10. logica PLC/interlock approvata;
11. BOM-017 serbatoi/contenimento;
12. RFQ comparabili e commissioning.