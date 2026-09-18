# Carnia TerraTech — Decision Gates

**Aggiornato:** 18 settembre 2026  
**Scopo:** impedire che idee interessanti diventino acquisti o lavori prima di essere tecnicamente, economicamente e operativamente mature.

## Stato standard di ogni elemento

Ogni oggetto, impianto o modulo deve avere uno dei seguenti stati:

- `IDEA` — esigenza o possibilità registrata;
- `REQUISITO` — funzione e vincoli definiti;
- `CANDIDATO` — esistono una o più soluzioni concrete;
- `DA PREVENTIVARE` — specifica sufficiente per chiedere prezzi reali;
- `VALIDATO` — soluzione tecnicamente ed economicamente verificata;
- `ORDINABILE` — può essere acquistata senza aprire questioni bloccanti;
- `ACQUISTATO` — ordine effettuato;
- `INSTALLATO` — installato ma non necessariamente collaudato;
- `COMMISSIONATO` — test funzionali e di sicurezza completati;
- `OPERATIVO` — inserito nella normale gestione e manutenzione.

## Gate G0 — ammissione nel progetto

Principio prioritario: una voce entra nel core se riduce un rischio materiale o abilita una funzione necessaria.

Per entrare nel perimetro deve essere chiaro almeno uno dei benefici:

- produzione/reddito;
- riduzione ore di lavoro;
- sicurezza;
- resilienza;
- manutenzione;
- qualità della vita;
- crescita futura;
- valore commerciale/didattico;
- natura/paesaggio coerente con il progetto.

Se non esiste un beneficio identificabile, la voce resta fuori dal core.

## Gate G1 — requisito definito

Per passare da `IDEA` a `REQUISITO` servono:

- funzione;
- utilizzatore;
- area del progetto coinvolta;
- prestazioni necessarie;
- vincoli di spazio/interfaccia;
- sicurezza essenziale;
- conseguenza dell'assenza della funzione;
- fase temporale prevista.

Non serve ancora scegliere una marca.

## Gate G1A — evidenza di sito

Per terreno, fondazioni, drenaggi, viabilità, acqua e layout non basta una compatibilità teorica.

Prima della progettazione esecutiva devono esistere, secondo il livello necessario:
- rilievo reale;
- campionamento distribuito del terreno;
- prove di drenaggio/infiltrazione;
- anomalie mappate;
- indagini geotecniche professionali per i parametri strutturali;
- analisi acqua;
- masterplan di prova sul lotto.

Riferimento: `../01_MASTERPLAN_E_TERRENO/PIANO_CAMPIONAMENTO_TERRENO_E_DRENAGGIO.md`.

## Gate G2 — candidato reale

Per passare a `CANDIDATO` servono:

- almeno una soluzione acquistabile o realizzabile concretamente;
- dati tecnici sufficienti;
- compatibilità preliminare con il progetto;
- fonte verificabile;
- prezzo trovato, prezzo da preventivo o stima chiaramente etichettata;
- disponibilità/mercato ricambi almeno preliminarmente verificati.

Quando il mercato lo consente si confrontano 2–3 alternative.

## Gate G3 — specifica da preventivo

Prima di chiedere offerte definitive devono essere chiusi:

- quantità;
- dimensioni;
- prestazioni;
- alimentazioni;
- accessori;
- interfacce;
- materiali;
- condizioni sito rilevanti;
- consegna/posa richiesta;
- esclusioni chiare.

Il preventivo deve essere confrontabile riga per riga, evitando forfait opachi dove tecnicamente evitabile.

## Gate G4 — validazione tecnica

Una soluzione diventa `VALIDATO` quando sono verificati:

- prestazioni nelle condizioni reali di Carnia TerraTech;
- compatibilità con sistemi a monte e valle;
- sicurezza;
- manutenzione;
- ricambi;
- failure mode;
- fallback;
- consumi;
- installabilità;
- espandibilità;
- documentazione tecnica sufficiente.

Per sensori o componenti low-cost può essere richiesto un lotto pilota prima della validazione.

## Gate G5 — validazione economica

Prima di diventare `ORDINABILE` devono essere noti:

- CAPEX completo;
- IVA;
- trasporto;
- posa/installazione;
- accessori/minuteria;
- OPEX atteso;
- manutenzione;
- ricambi;
- vita utile;
- impatto sulle ore uomo;
- costo totale di possesso quando significativo;
- eventuale costo ammissibile a contributo;
- fonte finanziaria prevista.

La soluzione deve essere compatibile con cashflow, capitale circolante e sostenibilità personale del lancio.

## Gate G6 — controllo qualità della vita

Ogni scelta importante deve rispondere a queste domande:

1. riduce o aumenta il lavoro indesiderato?
2. introduce nuove emergenze o dipendenze?
3. è semplice da capire e mantenere?
4. cosa succede quando si rompe di notte, in inverno o durante un'assenza?
5. richiede presenza continua?
6. crea rumore, sporco, fatica o disagio evitabili?
7. rende l'azienda più piacevole o più stressante da gestire?

Una soluzione tecnicamente eccellente può essere scartata se peggiora in modo significativo e non necessario la qualità della vita.

## Gate G7 — controllo crescita

Prima di costruire un'infrastruttura permanente bisogna verificare:

- capacità iniziale;
- espansione ragionevolmente prevedibile;
- spazio fisico futuro;
- predisposizioni convenienti da realizzare subito;
- elementi che diventerebbero colli di bottiglia;
- eventuali demolizioni necessarie in fase 2.

## Gate G8 — ordine

Un elemento può essere `ORDINABILE` solo se:

- non presenta open point bloccanti;
- il modello/preventivo è identificato;
- quantità e accessori sono definiti;
- la spesa non compromette contributi o ammissibilità;
- esiste copertura finanziaria;
- la sequenza lavori consente realmente l'acquisto;
- esiste un luogo/condizione corretta di stoccaggio se arriva prima della posa.

## Gate G9 — commissioning

Prima dello stato `OPERATIVO` devono essere completati:

- verifica installazione;
- test funzionale;
- test allarmi;
- test fallback;
- test guasto simulato dove sensato;
- documentazione as-built;
- seriali e garanzie;
- ricambi iniziali;
- piano manutenzione;
- formazione minima degli utilizzatori;
- integrazione nella dashboard/asset register quando prevista.

## Regola di blocco

Se emerge un rischio che può cambiare in modo sostanziale sicurezza, fattibilità, costo, manutenzione, continuità o compatibilità con contributi, lo stato non avanza finché il rischio non è chiuso o formalmente accettato.

Per il lotto, nessun rischio materiale di drenaggio/geotecnica/contaminazione viene accettato per sola convenienza di prezzo.

## Eccezioni

Le eccezioni devono essere esplicite e motivate nel documento interessato. Non esistono scorciatoie implicite dovute a fretta, sconto commerciale o disponibilità temporanea di un prodotto.
