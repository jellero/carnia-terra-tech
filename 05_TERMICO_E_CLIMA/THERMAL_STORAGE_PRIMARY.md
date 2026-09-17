# Accumulo termico e circuito primario PDC

**Aggiornato:** 17 settembre 2026  
**Stato:** `ARCHITETTURA E SCENARI DEFINITI / TAGLIA FINALE E P&ID DA CALCOLO`.

## 1. Obiettivo

Separare chiaramente quattro funzioni:

1. generazione con PDC modulari;
2. protezione antigelo del tratto esterno;
3. trasferimento di calore verso acqua tecnica pulita;
4. accumulo termico stratificato che alimenta il secondario a 6 zone.

Schema working:

`PDC esterne -> primario corto protetto -> scambiatore a piastre -> accumulo acqua tecnica -> distribuzione secondaria BOM-009`.

Il glicole va confinato al minimo volume tecnicamente necessario. Non glicolare automaticamente 30–50 m³ di accumulo.

## 2. Taglie working

- fase iniziale: **30 m³**;
- predisposizione: **40–50 m³**;
- generazione working: 3 × 22 kW = 66 kW nominali;
- predisposizione quarta PDC: 88 kW nominali.

Questi numeri restano working finché non sono chiusi carico termico, temperatura acqua, COP/capacità a freddo e strategia operativa.

## 3. Energia utile dell'accumulo

Per acqua:

`E[kWh] ≈ 1,163 × V[m³] × ΔT[K]`.

| Volume | ΔT 10 K | ΔT 20 K | ΔT 30 K |
|---:|---:|---:|---:|
| 30 m³ | ~349 kWh | ~698 kWh | ~1.047 kWh |
| 40 m³ | ~465 kWh | ~930 kWh | ~1.395 kWh |
| 50 m³ | ~581 kWh | ~1.163 kWh | ~1.744 kWh |

Sono energie teoriche dell'acqua, prima di perdite, volumi inutilizzabili, limiti di temperatura e stratificazione reale.

## 4. Tempo teorico di carica

Solo come controllo energetico, senza carichi contemporanei e usando potenza termica nominale:

- 30 m³ / ΔT 20 K: ~698 kWh -> ~10,6 h con 66 kW; ~7,9 h con 88 kW;
- 50 m³ / ΔT 20 K: ~1.163 kWh -> ~17,6 h con 66 kW; ~13,2 h con 88 kW.

Il calcolo reale deve usare la capacità PDC alle condizioni esterne e di mandata effettive, non il solo dato nominale 22 kW.

## 5. Architetture accumulo da quotare

### T1 — 6 × 5 m³ modulari

Vantaggi:

- componenti professionali commerciali;
- trasporto e movimentazione più semplici;
- possibilità di isolare un serbatoio;
- espansione futura per moduli;
- riduzione del single point of failure meccanico.

Svantaggi:

- più attacchi, valvole e sensori;
- maggiore superficie disperdente;
- più spazio e collegamenti;
- gestione della stratificazione più complessa.

Candidato tecnico: Cordivari PUFFER COMPACT 5000, volume nominale pubblicato 5.042 l, Pmax 3 bar, Tmax 99 °C. Prezzo: `DA PREVENTIVO`.

### T2 — 3 × 10 m³ custom/industriali

Vantaggi:

- buon compromesso tra modularità e numero connessioni;
- facile predisposizione 30 -> 40/50 m³ aggiungendo moduli compatibili.

Svantaggi:

- disponibilità/listini meno trasparenti;
- trasporto, altezza e accesso Tech Barn da verificare;
- engineering specifico di attacchi e isolamento.

Stato: `DA RFQ`.

### T3 — 1 × 30 m³ custom

Vantaggi:

- meno raccordi e valvole;
- potenzialmente minor costo per m³;
- stratificazione verticale più semplice se ben progettata.

Svantaggi:

- single point of failure;
- trasporto/installazione difficili;
- manutenzione interna/esterna più vincolante;
- crescita futura meno modulare;
- richiede spazio dedicato e accessi permanenti.

Stato: `DA RFQ / NON PREFERITO SENZA VANTAGGIO TCO EVIDENTE`.

## 6. Serbatoi acqua PE: confronto, non candidato base

Serbatoi PE da acqua possono costare molto meno dei puffer professionali. Esempio corrente ALTA AcquaTec: 10.000 l verticali €1.840 + IVA, 15.000 l €2.940 + IVA, 20.000 l €4.740 + IVA, con campo termico dichiarato fino a circa +60 °C per la serie da esterno.

Questi prezzi **non dimostrano idoneità come accumulo termico**: pressione, temperatura continuativa, diffusione ossigeno, attacchi, stratificazione, isolamento e vita utile sono diversi. Non usare normali serbatoi acqua per abbassare artificialmente il CAPEX senza validazione del costruttore.

## 7. Scambiatore a piastre

Funzione: tenere il circuito glicolato esterno separato dai 30–50 m³ di acqua tecnica.

Scenari da quotare:

- HX1: 1 × ~100 kW;
- HX2: 2 × ~100 kW in parallelo, ciascuno isolabile;
- HX3: 2 × ~50–60 kW, accettando capacità degradata in guasto.

Benchmark Sunerg listino 2025/2:

- saldobrasato 60 kW: €932;
- saldobrasato 100 kW: €1.252;
- a piastre inox 100 kW: €3.013.

Sono benchmark, non selezione. Il dimensionamento deve dichiarare:

- potenza reale alle temperature di progetto;
- percentuale glicole;
- approach temperature;
- portate lato primario/secondario;
- perdita di carico;
- materiale piastre/brasatura;
- fouling factor;
- possibilità di lavaggio/sostituzione.

Un solo HX centrale è un single point of failure; la scelta 1× vs 2× deve essere valutata sul costo di fermo e sulla modalità sopravvivenza.

## 8. Primario PDC

Per ogni PDC prevedere o verificare:

- valvole isolamento;
- non ritorno;
- filtro/defangatore;
- sfiato;
- scarico;
- T mandata/ritorno;
- pressione;
- portata o prova di portata;
- protezione gelo;
- compensatori/supporti dove necessari;
- possibilità di rimozione della singola unità senza fermare le altre.

**Open point critico:** verificare se KHP-R290-22-3 integra già un circolatore e quale prevalenza residua fornisce. Non aggiungere pompe esterne per duplicazione finché il datasheet completo non lo chiarisce.

## 9. Portata primaria

Relazione acqua indicativa:

`Q[m³/h] ≈ P[kW] / (1,163 × ΔT[K])`.

Per 66 kW:

- ΔT 5 K -> ~11,35 m³/h;
- ΔT 10 K -> ~5,68 m³/h.

Per 88 kW:

- ΔT 5 K -> ~15,13 m³/h;
- ΔT 10 K -> ~7,57 m³/h.

Benchmark pompa: Grundfos MAGNA3 32-80, circa 10 m³/h e 8 m di prevalenza, da ~€1.149. È solo un riferimento di classe: può essere insufficiente o sovradimensionata secondo ΔT, perdite HX e prevalenza residua PDC.

## 10. Glicole

Preferenza: propilenico inibito nel solo primario esterno, se necessario per la temperatura minima di progetto e lo scenario blackout.

Benchmark correnti:

- Antigel atossico 25 kg: ~€185,11 IVA inclusa;
- glicole propilenico 25 kg Polsinelli: €122,13 più spedizione osservata.

Il costo reale dipende dal volume primario e dalla concentrazione. Un produttore retail indica, come riferimento, ~20% per -9 °C e ~30% per -14 °C; la concentrazione definitiva deve derivare dalla temperatura minima di progetto più margine, dalle specifiche PDC e dal fluido selezionato.

Registrare anche l'effetto del glicole su:

- viscosità;
- portata;
- perdita di carico;
- scambio termico;
- potenza pompa;
- manutenzione e controllo concentrazione.

## 11. Espansione e sicurezza

L'accumulo e il primario devono avere calcolo di espansione separato.

Candidato di classe: Caleffi 556500, vaso 500 l, Pmax 6 bar, -10…120 °C, max 50% glicole, conforme EN 13831; benchmark retail €1.165,20.

**500 l non è automaticamente la taglia corretta.** Il volume necessario dipende da:

- volume totale acqua;
- Tmin/Tmax;
- pressione statica;
- precarica;
- pressione massima ammessa;
- valvola di sicurezza;
- eventuale separazione dei circuiti.

Prevedere inoltre:

- valvole di sicurezza;
- manometri/trasduttori;
- separatore aria/defangatore;
- riempimento e reintegro controllato;
- scarichi sicuri;
- protezione bassa pressione;
- eventuale vaso dedicato sul primario glicolato.

## 12. Stratificazione e misura energia

L'accumulo deve essere misurabile, non trattato come una singola temperatura.

Richiedere:

- sonde verticali su più quote;
- almeno top/bottom per ogni modulo se modulare;
- 4–6 livelli rappresentativi sull'insieme dell'accumulo;
- T mandata/ritorno primario;
- T mandata/ritorno secondario;
- misuratore energia termica con portata e ΔT;
- algoritmo software per stima kWh realmente disponibili.

La posizione degli attacchi deve favorire stratificazione e ridurre corto-circuiti idraulici.

## 13. Isolamento e dispersioni

Il preventivo deve dichiarare:

- materiale e spessore isolamento;
- rivestimento esterno;
- classe/reazione al fuoco applicabile;
- perdita termica o coefficiente dichiarato;
- ponti termici su bocchelli/supporti;
- possibilità di smontaggio per manutenzione;
- protezione da urti/umidità nel locale tecnico.

Non scegliere solo in base allo spessore nominale dell'isolante.

## 14. Failure modes e fallback

- una PDC guasta -> le altre restano isolate e operative;
- pompa primario guasta -> valutare N+1 o uso circolatori integrati;
- HX sporco/guasto -> bypass/manutenzione o secondo HX secondo architettura scelta;
- sensore stratificazione guasto -> fallback su sonde sane + allarme;
- vaso espansione guasto -> allarme pressione e procedura;
- gelo primario -> concentrazione, circolazione minima e logica antigelo locale;
- accumulo fuori servizio -> possibilità di operare temporaneamente in modalità ridotta da PDC a rete secondaria solo se il P&ID lo consente e viene validato.

## 15. Gate

BOM-010 passa a `VALIDATO` solo con:

1. carico termico e temperature acqua;
2. prestazioni PDC alle condizioni fredde reali;
3. scelta volume utile 30/40/50 m³;
4. scelta architettura T1/T2/T3;
5. P&ID primario/accumulo;
6. calcolo portate/perdite;
7. dimensionamento HX;
8. calcolo vaso espansione/sicurezze;
9. concentrazione glicole;
10. layout e accessibilità manutenzione;
11. dispersioni/isolamento quantificati;
12. preventivi comparabili e commissioning definito.
