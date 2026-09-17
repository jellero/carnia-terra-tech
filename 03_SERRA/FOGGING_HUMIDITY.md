# Carnia TerraTech — Fogging & Humidity Management

**Stato:** `REQUISITO DEFINITO / DIMENSIONAMENTO DA FARE`.

## 1. Funzione

Il fogging non è un impianto da accendere genericamente quando fa caldo. Serve a gestire raffrescamento evaporativo, VPD/UR e specifiche fasi colturali, mantenendo controllo su bagnatura fogliare e rischio fitosanitario.

## 2. Compartimenti prioritari

Working priority:

- C1 pomodoro;
- C2 peperone;
- C6 basilico/vivaio/jolly.

Predisposizione futura sugli altri comparti solo se giustificata.

## 3. Dati necessari prima del dimensionamento

- analisi acqua;
- durezza/sali;
- temperatura e UR esterne di progetto;
- volume reale comparto;
- ricambi aria/ventilazione;
- coltura e VPD target;
- portata evaporabile senza bagnare la coltura;
- pressione richiesta dagli ugelli;
- qualità filtrazione.

## 4. Architettura da confrontare

Preferenza per sistema professionale ad alta pressione se giustificato da qualità acqua, prestazioni e manutenzione.

La BOM deve comprendere:

- pompa/gruppo pressione;
- prefiltro/filtrazione fine;
- eventuale trattamento acqua;
- accumulo/vaso tecnico se necessario;
- collettori;
- tubazioni alta pressione;
- raccordi;
- elettrovalvole per zona;
- ugelli;
- valvole scarico;
- manometri/trasduttori;
- protezione marcia a secco;
- quadro/protezioni;
- sensori T/RH/VPD;
- ricambi ugelli e tenute.

## 5. Logica di controllo

Il PLC deve considerare almeno:

- temperatura;
- UR/VPD;
- stato aperture;
- HAF;
- rischio condensa;
- bagnatura fogliare quando disponibile;
- orario/fase coltura;
- allarmi pressione/portata.

## 6. Failure mode

Prevedere:

- ugello ostruito;
- ugello che gocciola;
- perdita alta pressione;
- pompa guasta;
- sensore UR errato;
- qualità acqua fuori specifica;
- attivazione con ventilazione incompatibile.

Il guasto del fogging non deve compromettere irrigazione o altre funzioni vitali.

## 7. Manutenzione

Definire:

- controllo filtri;
- lavaggio linee;
- controllo ugelli;
- gestione calcare/minerali;
- sanificazione;
- manutenzione pompa;
- ricambi minimi;
- procedura di svuotamento/protezione gelo.
