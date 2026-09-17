# Carnia TerraTech — RFQ Fogging C1/C2/C6

**Uso:** richiesta di offerta confrontabile per sistema professionale di fogging ad alta pressione.

## 1. Dati progetto

- serra totale: ~4.200 m²;
- 6 comparti ~700 m²;
- fogging prioritario: C1 pomodoro, C2 peperone, C6 basilico/vivaio/jolly;
- tre zone climatiche indipendenti;
- HAF già previsti: 4/comparto working quantity;
- controllo centrale PLC, funzionamento vitale indipendente da cloud;
- acqua reale ancora da analizzare.

## 2. Scopo dell'offerta

Fornire proposta completa per:

- raffrescamento evaporativo;
- controllo UR/VPD;
- minima bagnatura fogliare;
- gestione indipendente delle tre zone;
- manutenzione semplice;
- protezione gelo/fermo invernale;
- integrazione PLC.

## 3. Tre architetture da quotare quando tecnicamente possibili

### F1 — centrale singola

Una stazione HP per C1/C2/C6, tre zone con elettrovalvole indipendenti.

### F2 — centrale N+1

Due pompe con capacità/ridondanza dichiarata e logica duty/standby o parallelo.

### F3 — distribuita

Una pompa dedicata per ciascuno dei tre comparti.

Per ogni scenario fornire costo completo e differenze di manutenzione/affidabilità.

## 4. Calcoli richiesti al fornitore

Per C1, C2 e C6 dichiarare:

- volume utile;
- condizioni climatiche di progetto assunte;
- temperatura e UR/VPD obiettivo;
- portata acqua massima richiesta;
- portata per zona;
- pressione pompa;
- pressione minima all'ugello più sfavorito;
- numero ugelli;
- diametro/orifizio;
- portata per ugello;
- dimensione goccia o dato prestazionale equivalente;
- distanza/interasse linee e ugelli;
- altezza/posizione;
- contemporaneità delle zone;
- effetto previsto con aperture/HAF;
- criteri per evitare bagnatura coltura.

Non sono accettate offerte con solo `n. ugelli/m²` senza motivazione tecnica.

## 5. Acqua e trattamento

Fornire limiti ammessi per:

- pH;
- EC/TDS;
- durezza;
- Fe/Mn;
- silice;
- solidi/turbidità;
- cloruri/sali;
- eventuali requisiti microbiologici.

Sulla base dell'analisi acqua Carnia TerraTech, quotare separatamente:

- prefiltro;
- filtrazione fine;
- carboni se richiesti;
- softening se richiesto;
- osmosi inversa se richiesta;
- UV/altro solo se tecnicamente necessario;
- cartucce e consumabili primo anno.

Non inserire RO come costo obbligatorio senza giustificazione.

## 6. Pompa/stazione HP

Dichiarare:

- marca/modello;
- portata nominale e campo operativo;
- pressione;
- potenza/assorbimento;
- alimentazione;
- materiale testata/pistoni;
- bypass/regolazione/inverter;
- dry-run protection;
- sovratemperatura;
- relief valve;
- manometro/trasduttore;
- rumore;
- IP;
- duty cycle;
- intervalli manutenzione;
- olio/tenute/kit ricambio;
- garanzia;
- rete assistenza;
- lead time ricambi.

## 7. Linee HP

Quotare separatamente:

- collettore principale;
- tubo inox oppure PA12/alternativa;
- diametri;
- metri per tratta;
- rating pressione/temperatura;
- raccordi diritti;
- tee;
- gomiti;
- terminali;
- staffe/supporti;
- valvole isolamento;
- drenaggi;
- linee flessibili dove necessarie;
- ricambi.

## 8. Ugelli

Dichiarare:

- marca/modello;
- materiale;
- foro;
- portata alla pressione reale;
- anti-drip;
- filtro integrato;
- spray pattern;
- manutenzione;
- vita attesa;
- prezzo unitario;
- quantità installata;
- quantità ricambi iniziali.

## 9. Zonizzazione e valvole

Per C1/C2/C6:

- elettrovalvola HP;
- alimentazione;
- posizione fail-safe;
- pressione nominale/max;
- valvola manuale;
- depressurizzazione/drenaggio;
- feedback stato se disponibile;
- ricambio consigliato.

## 10. Automazione

Il fornitore deve indicare segnali disponibili/necessari:

Input:
- run/fault pompa;
- low water/dry-run;
- pressione;
- portata;
- stato valvole;
- allarmi filtri se disponibili.

Output:
- enable pump;
- duty/standby se applicabile;
- zone C1/C2/C6;
- drain/depressurization.

Il comando climatico principale resta nel PLC Carnia TerraTech; evitare controller proprietario obbligatorio se non strettamente necessario.

## 11. Costi da separare

Offerta con righe distinte per:

1. pompa/e HP;
2. telaio/cabinet;
3. filtri;
4. trattamento acqua;
5. eventuale break tank;
6. collettori;
7. tubo HP;
8. raccordi;
9. supporti;
10. ugelli;
11. elettrovalvole;
12. valvole manuali;
13. drenaggi;
14. sensori pressione/portata;
15. quadro elettrico;
16. cablaggio;
17. interfaccia PLC;
18. trasporto;
19. installazione;
20. commissioning;
21. formazione;
22. ricambi iniziali;
23. consumabili primo anno;
24. manutenzione programmata primo anno;
25. esclusioni.

## 12. Commissioning richiesto

Test documentati almeno per:

- pressione statica/dinamica;
- pressione punto sfavorito;
- uniformità spruzzo;
- apertura/chiusura zone;
- anti-drip;
- drenaggio;
- dry-run;
- allarmi;
- perdita tubo/raccordo simulata in sicurezza;
- fault pompa;
- sensore UR fuori plausibilità;
- stop comunicazione PLC;
- verifica assenza di bagnatura indesiderata;
- interazione HAF/aperture.

## 13. Documentazione richiesta

- P&ID;
- layout ugelli/linee;
- schema elettrico;
- lista I/O;
- datasheet;
- manuali;
- piano manutenzione;
- lista ricambi;
- dichiarazioni/certificazioni applicabili;
- garanzia;
- as-built dopo commissioning.
