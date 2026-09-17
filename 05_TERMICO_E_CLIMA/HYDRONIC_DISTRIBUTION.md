# Distribuzione idronica secondaria

**Aggiornato:** 17 settembre 2026  
**Stato:** `ARCHITETTURA DEFINITA / DIAMETRI, PORTATE E PREVALENZE DA CALCOLO`.

## 1. Architettura

Dall'accumulo termico si alimenta un collettore di mandata/ritorno con **6 circuiti indipendenti**, uno per comparto.

Schema funzionale per comparto:

`collettore mandata -> isolamento -> filtro/strainer se richiesto -> pompa zona -> miscelazione -> misura T mandata -> circuito terminali -> misura T ritorno -> misura/bilanciamento portata -> isolamento -> collettore ritorno`.

L'ordine reale dei componenti sarà definito nel P&ID esecutivo.

## 2. Requisiti per ogni zona

- isolamento manuale mandata e ritorno;
- pompa modulante dimensionata su portata/prevalenza;
- valvola miscelatrice motorizzata se richiesta dalla strategia di temperatura;
- T mandata e ritorno;
- misura portata o dispositivo di bilanciamento leggibile;
- punti di riempimento/svuotamento e sfiato dove necessari;
- valvole di non ritorno se richieste dallo schema;
- prese pressione o misura Δp dove utile;
- comando locale/manuale degradato;
- stato pompa e allarme;
- accessibilità senza entrare nella coltura quando possibile;
- componenti sostituibili senza svuotare l'intero impianto.

## 3. Terminali near-crop

Working estimate storico: 2.700–3.000 m totali.

C1/C2:

- working: 2 tubi per fila;
- ~720 m per comparto nel layout storico;
- totale working C1+C2 ~1.440 m.

C3–C6:

- working ~300–360 m per comparto;
- totale working ~1.200–1.440 m.

Queste quantità dipendono dal layout reale e dalle crop card.

## 4. Famiglie di tubo da confrontare

### T1 — tubo specifico greenhouse PEHD/PE100

Preferenza da RFQ quando disponibile perché progettato per esposizione in serra e uso come superficie emittente.

Candidati tecnici:

- **Elydan TUBSER**: PEHD Ø25 mm, specifico per riscaldamento a bassa temperatura delle serre, resistenza UV dichiarata;
- **Palaplast GEOPAL PE100**: Ø25/28 mm, specifico greenhouse heating, 100 m/rotolo; documentazione pubblica indica max 70 °C e pressione di esercizio dipendente dalla variante.

Prezzo: `DA PREVENTIVO`.

### T2 — PE-Xa con barriera EVOH

Benchmark IVAR FF-Therm PE-Xa Ø25×2,3:

- barriera EVOH;
- confezione 200/450 m;
- listino pubblico IVAR: €5,81/m;
- prezzo retail UE osservato: ~€4,23/m.

È idraulicamente interessante ma **non viene approvato per posa near-crop esposta** senza conferma del produttore su UV, ambiente serra, agenti chimici, fissaggi e dilatazione.

### T3 — altri PE tecnici/agricoli

Tubi PE irrigazione UV-resistant non sono automaticamente equivalenti a un tubo per acqua calda. Pressione nominale a 20 °C non dimostra idoneità a temperatura di esercizio termica.

## 5. Benchmark costo tubo

Solo per capire il peso economico, se i 2.700–3.000 m fossero tutti IVAR PE-Xa Ø25×2,3:

- al prezzo retail osservato ~€4,23/m: **~€11.421–12.690**;
- al listino IVAR €5,81/m: **~€15.687–17.430**.

Sono benchmark di solo tubo, esclusi raccordi, supporti, collettori, posa, sfridi e ricambi. Non costituiscono scelta materiale.

## 6. Pompe zona — candidati benchmark

### P1 — Grundfos ALPHA2 25-60 180

Dati pubblici osservati:

- DN25 / G 1½;
- prevalenza max ~6 m;
- portata indicata ~2,7 m³/h;
- assorbimento ~3–34 W;
- prezzo osservato da **€249 IVA inclusa**.

Uso: candidato per zone solo se curva pompa e punto di lavoro reale lo confermano.

### P2 — Grundfos MAGNA1 25-60

- classe più robusta per circuiti di riscaldamento/condizionamento;
- max 10 bar;
- prevalenza max ~6 m;
- prezzo osservato **€426,63 IVA inclusa**.

Uso: benchmark alternativo; portata/prevalenza reale da verificare sul punto di lavoro.

## 7. Miscelazione

Benchmark:

- **ESBE VRG131 DN25 Kvs 10**: circa **€64,15** prezzo osservato;
- **ESBE ARA661 230 V, 3 punti, 6 Nm, 120 s**: circa **€148,35 IVA inclusa** presso Fausto Ricambi.

La coppia valvola+attuatore è un candidato semplice e manutenzionabile, ma Kvs e diametro devono derivare dalla portata reale.

Per controllo PLC valutare 3-punti o segnale modulante secondo precisione e standardizzazione dell'impianto.

## 8. Bilanciamento / misura portata

Candidato benchmark:

- **Caleffi 132602**, attacco 1", campo 10–40 l/min, lettura diretta, Pmax 10 bar, -10…110 °C;
- prezzo osservato **~€102,28 IVA inclusa**.

Alternativa: valvola Venturi Caleffi serie 130 + misura differenziale, utile quando il campo di portata richiede soluzione diversa.

Il range 10–40 l/min equivale a 0,6–2,4 m³/h: potrebbe non essere adatto a tutte le zone/scenari. Il modello definitivo va scelto sulla portata calcolata.

## 9. Benchmark hardware testa-zona

Esempio puramente economico per 6 zone, usando una pompa ALPHA2 + VRG131 + ARA661 + Caleffi 132602 per zona:

- ~€563,78/comparto;
- ~€3.382,68 per 6 comparti.

Con MAGNA1 al posto di ALPHA2:

- ~€741,41/comparto;
- ~€4.448,46 per 6 comparti.

**Esclusi:** collettori, valvole isolamento, raccordi, filtri, sensori, cavi, quadro, supporti, tubo near-crop, dorsali, coibentazione, posa e commissioning.

Questi totali non sono CAPEX di zona e non provano il dimensionamento.

## 10. Collettori e dorsali

Da progettare dopo il calcolo portate:

- collettore mandata;
- collettore ritorno;
- diametri;
- materiale;
- isolamento termico;
- sfiati;
- scarichi;
- valvole di sezionamento;
- sensori pressione/temperatura;
- predisposizione settima linea/espansione se economicamente sensata.

Preferenza per collettore accessibile in locale tecnico, con etichettatura C1–C6 e spazio per sostituzione pompe/attuatori.

## 11. Coibentazione

Distinguere:

- **dorsali di trasporto:** coibentare per ridurre dispersioni non volute;
- **tubi near-crop:** non coibentare perché sono terminali emittenti;
- **tratti esterni/primario PDC:** protezione gelo e isolamento specifici, trattati nel package generazione/primario.

## 12. Automazione e misura

Per comparto almeno:

- T mandata;
- T ritorno;
- stato/comando pompa;
- comando valvola miscelatrice;
- portata;
- allarme assenza portata;
- opzionale Δp/pressione;
- contabilizzazione termica dove economicamente utile.

La logica vitale resta nel PLC locale.

## 13. Failure modes

- pompa zona guasta;
- valvola miscelatrice bloccata;
- attuatore guasto;
- sensore T errato;
- flussometro ostruito;
- aria nel circuito;
- perdita tubo/raccordo;
- congelamento tratto esposto;
- tubo near-crop degradato da UV/chimica;
- collettore o filtro ostruito;
- perdita alimentazione elettrica.

Fallback:

- isolamento singola zona;
- ricambio pompa compatibile a stock;
- possibilità di posizionamento manuale valvola;
- modalità sopravvivenza sugli altri comparti;
- bypass/procedura temporanea solo se progettata e documentata.

## 14. Ricambi minimi candidati

- 1 pompa zona compatibile;
- 1 attuatore miscelatrice;
- kit valvola/tenute se previsto;
- sensori T;
- flussimetro o componente di misura;
- raccordi principali;
- tratto tubo terminale;
- supporti/fascette specifiche;
- valvole manuali critiche.

## 15. Gate di validazione

Serve chiudere:

1. carico kW per C1–C6;
2. ΔT di progetto;
3. portata per zona;
4. perdite di carico dei circuiti;
5. materiale terminale compatibile greenhouse;
6. lunghezze e diametri reali;
7. schema collettori;
8. interfaccia con accumulo/PDC;
9. antigelo;
10. P&ID;
11. offerte professionali;
12. commissioning e bilanciamento.