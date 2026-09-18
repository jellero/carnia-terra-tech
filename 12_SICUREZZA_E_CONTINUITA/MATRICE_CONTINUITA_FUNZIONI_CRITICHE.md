# Matrice continuità funzioni critiche

**Aggiornato:** 18 settembre 2026  
**Stato:** `BASELINE / RTO E AUTONOMIE DA DATI REALI`

## 1. Regola

Non assegnare un tempo di ripristino arbitrario.

Per ogni funzione si definiscono:
- classe;
- trigger di danno;
- RTO massimo accettabile;
- autonomia necessaria;
- fallback;
- test.

I valori finali derivano da crop card, processo, condizioni meteo e dati del sito.

## 2. Matrice iniziale

| Funzione | Classe | Guasto principale | Fallback | Evidenza di chiusura |
|---|---|---|---|---|
| PLC/interblocchi safety | P0 | perdita alimentazione/control | alimentazione P0 + logica locale fail-safe | blackout SAT |
| rete OT core | P0 | switch/gateway down | ridondanza/fallback locale PLC | loss-network test |
| server orchestration | P1/P2 | node/server down | PLC/edge autonomi + replica/restore | node-loss + DR test |
| irrigazione controllo | P0/P1 | PLC/valvola/control down | manuale locale + ricambi | irrigation fault SAT |
| pompa irrigazione | P1 | duty pump fail | standby 100% | duty-to-standby test |
| disponibilità acqua | P1 | source loss | storage + gestione consumi | autonomy calculation |
| fertirrigazione | P1/P2 | dosing failure | irrigazione acqua / ricetta degradata secondo crop | recipe fallback test |
| termico minimo | P1 | PDC/circuito fail | modularità + accumulo + modalità survival | cold-condition SAT |
| ventilazione/aperture | P1 | actuator/control fail | manual/local safe position | actuator fault test |
| cella freddo critica | P1 | compressor/controller fail | alarm + second strategy/service | loaded pull-down/fault test |
| BESS/critical bus | P0/P1 | grid loss / PCS fail | rete se disponibile + architecture A/B/C | blackout/no-reboot SAT |
| fire/security/access | P0 | controller/power fail | local safe state/manual procedure | safety SAT |
| drenaggio | P1/P2 | blockage/pump fail | HOLD/overflow safe route | wet test |
| telescopico | P2 | machine unavailable | noleggio/service/manual safe workaround | SLA/TCO plan |
| accesso in quota | P1/P2 | PLE unavailable | OEM platform/noleggio alternative | reach/recovery test |
| humus/cicli materia | P2/P3 | equipment unavailable | stock buffer/manual simple process | process fallback |
| spaccio | P2/P3 | kiosk/payment fail | ritiro/manual sale | sales fallback |
| Internet/cloud | P3 per vitali | WAN loss | local operation | WAN-loss test |

## 3. Dipendenze nascoste da evitare

Una funzione apparentemente ridondata non lo è se entrambi i rami dipendono da:

- stesso quadro;
- stesso switch;
- stessa tubazione;
- stessa valvola;
- stesso trasformatore;
- stessa credenziale/cloud;
- stessa persona;
- stesso ricambio raro;
- stesso punto fisico esposto a incendio/allagamento.

Il review deve cercare **common-cause failure**.

## 4. P0 elettrico

La continuità P0 non è legata a una tecnologia unica.

Confrontare:
- BESS/PCS no-break;
- BESS + ride-through professionale dedicato;
- DC buffer industriale;
- architettura equivalente.

Non usare UPS consumer sparse come soluzione implicita.

Criterio:
**P0 non si riavvia nel blackout SAT oppure il progetto viene corretto.**

## 5. Persone

Per ogni skill critica:
- primary;
- backup interno;
- supporto esterno;
- procedura;
- contatti;
- accesso alle credenziali/documenti.

Test:
- assenza primary;
- assenza promotore;
- ferie >=10 giorni lavorativi quando il team è a regime.

## 6. Aggiornamento

La matrice viene aggiornata:
- dopo lotto;
- dopo RFQ;
- dopo commissioning;
- a 30/90 giorni;
- dopo ogni incidente/near miss significativo.
