# Carnia TerraTech — Calendar & Capacity Planning

**Aggiornato:** 17 settembre 2026.

## 1. Obiettivo

Il calendario colturale deve coordinare agronomia, lavoro, clima, energia, raccolta, celle frigo e vendite. Non basta sapere se una coltura cresce: bisogna sapere quando occupa spazio e quando genera lavoro e prodotto.

## 2. Unità minima di pianificazione

La pianificazione operativa deve essere almeno settimanale. Per ogni lotto registrare:

- comparto e sottozona;
- specie/cultivar;
- superficie;
- data semina;
- data trapianto;
- periodo di attecchimento;
- fase vegetativa;
- finestra fioritura/allegagione quando applicabile;
- inizio raccolta;
- frequenza raccolta;
- fine raccolta;
- fine ciclo;
- pulizia/sanificazione;
- giorni di indisponibilità prima del lotto successivo.

## 3. Capacità reale dei comparti

La capacità annua non è `700 m² × 365 giorni`. Va corretta per:

- corridoi e aree non produttive;
- tempi di preparazione;
- sovrapposizioni di cicli;
- sanificazione;
- fallanze;
- prove;
- vivaio;
- manutenzione;
- eventuali periodi in cui produrre sarebbe tecnicamente possibile ma economicamente inefficiente.

Per ogni comparto calcolare:

- m²-giorno teorici;
- m²-giorno occupati;
- m²-giorno vendibili;
- m²-giorno non produttivi;
- motivo della mancata disponibilità.

## 4. Picchi di lavoro

Per ogni settimana sommare almeno:

- trapianti/semina;
- tutoraggio/potatura;
- scouting;
- raccolta;
- movimentazione;
- cernita/confezionamento;
- pulizia;
- manutenzione agronomica.

Il calendario non è accettabile se i picchi superano la capacità dei soci/personale senza un piano esplicito di automazione o manodopera aggiuntiva.

## 5. Picchi di prodotto

Registrare per settimana:

- kg previsti per coltura;
- kg vendibili;
- cassette;
- spazio cella necessario;
- ore di confezionamento;
- capacità di trasporto;
- ordini/clienti necessari.

Una produzione che supera la capacità di vendita o post-raccolta è un errore di pianificazione, non un successo agronomico.

## 6. Energia e clima

Il calendario deve essere incrociato con:

- temperature esterne;
- radiazione solare;
- rischio gelo;
- caldo estremo;
- umidità e precipitazioni;
- disponibilità FV;
- capacità PDC/accumulo.

Per il sito finale si useranno dati storici e correnti ARPA FVG–OSMER. La stazione di Gemona del Friuli dispone di serie storiche meteorologiche utili come riferimento territoriale, ma il dimensionamento finale userà il lotto reale.

## 7. Calendario commerciale

Per ogni coltura affiancare:

- finestra di domanda;
- prezzo storico/atteso con fonte;
- clienti;
- quantità richiesta;
- frequenza consegne;
- eventuali settimane di domanda debole.

Il calendario produttivo deve seguire il mercato quando tecnicamente ed economicamente sensato, non produrre automaticamente al massimo tutto l'anno.

## 8. Year 0 / commissioning agronomico

Prima della piena saturazione prevedere una fase di commissioning agronomico:

- test irrigazione;
- uniformità gocciolatori;
- calibrazione pH/EC;
- test sensori;
- prova drenaggio;
- prova climate control;
- lotti limitati;
- verifica logistica raccolta;
- verifica celle e packaging;
- raccolta dei primi tempi standard di lavoro.

## 9. Output futuro

Quando cultivar, clienti e sito saranno definiti, questo documento dovrà generare un calendario annuale con una riga per settimana e almeno:

`comparto | lotto | coltura | fase | m² | lavoro h | acqua | energia | kg attesi | kg vendibili | cella | cliente`.

Fino ad allora non vengono inventate date o rese definitive.