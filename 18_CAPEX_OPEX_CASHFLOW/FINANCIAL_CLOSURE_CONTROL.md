# Financial closure control — CAPEX / OPEX / cashflow

**Aggiornato:** 18 settembre 2026  
**Stato:** `CONTROL FRAMEWORK / BUDGET ENVELOPE €850k / COSTI FINALI DA RFQ-CONTRATTI-ATTUALI`

## 1. Scopo

Collegare il budget di avvio alle evidenze tecniche reali.

Il target corrente è:

- CAPEX netto ammissibile di pianificazione: **€850.000**;
- range di controllo pre-RFQ: **€750.000–950.000**;
- riserva operativa separata: **€120.000**;
- linea IVA/ponte target: **€120.000–150.000**;
- ponte CAPEX stimato prima del saldo contributo: **~€102.000**, salvo calendario fornitori diverso;
- P1: primi **3 comparti / ~2.100 m²**;
- target commerciale P1 da validare: **€250.000/anno ricorrenti**.

Questi valori restano pianificazione, non previsione certa.

## 2. Livelli di maturità costo

| Livello | Evidenza |
|---|---|
| E0 | envelope/assunzione interna |
| E1 | benchmark pubblico / listino / prezzo osservato |
| E2 | budgetary RFQ comparabile |
| E3 | installed RFQ comparabile |
| E4 | offerta accettata / contratto |
| E5 | costo impegnato/fatturato/actual |

Regola:
- nessun E0/E1 viene trattato come "costo finale";
- il gate investimento richiede E3/E4 sulle voci materiali principali;
- E5 alimenta il cashflow actual.

## 3. CAPEX control baseline

| Blocco | Envelope netto | Maturità corrente | Evidenze già presenti | Gap per chiusura |
|---|---:|---|---|---|
| Terreno + atti/verifiche | €50.000 | E0 | regole due diligence | lotto reale, prezzo, atti, verifiche |
| Serra 4.200 m² | €350.000 | E1 | benchmark unitari/BOM-001…008 | lotto, neve/vento, geotecnica, layout, 3 installed RFQ |
| Acqua/fertirrigazione/drenaggio iniziale | €55.000 | E1 | benchmark componenti, pompe, tank | crop card, fonte/analisi, layout, installed RFQ |
| Termico/clima | €65.000 | E1/E2 parziale | PDC/dehumidifier benchmark e package RFQ | carico reale, meteo, P&ID, installed RFQ |
| Energia FV + grid + EMS/BESS minimo | €130.000 | E1/E2 parziale | moduli/meters/inverter/BESS vendor data, DSO RFQ template | lotto/DSO/POD, load profile, installed RFQ, fire design |
| Tech Barn minimo + celle + packaging | €95.000 | E1 | shell/cold unit/packaging benchmark | layout, kg/day, pull-down, SKU, installed RFQ |
| Automazione/PLC/edge/rete/server | €30.000 | E1/E2 parziale | server/network benchmark, RFQ BOM-030 | 3 comparable quotes + acceptance scope |
| Spaccio semplice/semi-auto | €20.000 | E1 | vending/payment/retail benchmark | SKU/temp/SUAP/fiscalità/pilot + installed RFQ |
| Progettazione/direzione/collaudi/commissioning/contingenza | €55.000 | E0/E1 | RFQ professionali e SAT scope strutturati | fee professionali reali, opere escluse, contingency model |
| **Totale** | **€850.000** | **planning** | | |

## 4. Regola di ricalcolo

Ogni volta che una voce passa:
- E0 -> E1;
- E1 -> E2;
- E2 -> E3;
- E3 -> E4;
- E4 -> E5;

aggiornare:
1. base cost;
2. IVA;
3. freight;
4. installazione;
5. commissioning;
6. service;
7. ricambi;
8. lead time;
9. eleggibilità;
10. cash timing.

Non sovrascrivere il dato precedente: mantenere revision history.

## 5. CAPEX committed vs paid

Separare sempre:

- `CAPEX_budget`;
- `CAPEX_quote`;
- `CAPEX_committed`;
- `CAPEX_paid`;
- `CAPEX_eligible`;
- `CAPEX_grant_base`;
- `CAPEX_noneligible`.

Formule di controllo:

`variance_quote = CAPEX_quote - CAPEX_budget`

`variance_committed = CAPEX_committed - CAPEX_budget`

`cash_gap = payments_due - cash_available_for_CAPEX`

## 6. Waterfall finanziario corrente

Su €850.000 di spesa ammissibile, nello scenario di lavoro:

- SRD01 60% = **€510.000**;
- anticipo massimo 50% del sostegno = **€255.000**;
- finanziamento di lavoro 40% = **€340.000**;
- liquidità iniziale investimento = **€595.000**.

Dopo almeno il 50% della spesa sostenuta:
- sostegno cumulativamente liquidabile fino all'80% = **€408.000**;
- ulteriore acconto teorico dopo anticipo = **€153.000**;
- liquidità cumulata investimento = **€748.000**.

Saldo residuo:
- **€102.000**.

Guardrail:
- queste cifre valgono solo se concessione, garanzia, acconto e finanziamento sono realmente perfezionati;
- non sommare automaticamente strumenti sulle stesse spese;
- verificare cumulo/intensità/doppio finanziamento voce per voce.

## 7. Cassa separata

Contenitori minimi:

| Contenitore | Uso | Non può coprire |
|---|---|---|
| C1 | terreno/atti | working capital |
| C2 | costruzione/infrastrutture | stipendi |
| C3 | allestimento produttivo | extra non approvati |
| C4 | persone/OPEX/circolante | sfori cantiere |
| C5 | vendita/spaccio/logistica | opere core non previste |
| VAT | IVA/ponte | OPEX ordinario |
| BRIDGE | ponte CAPEX fino al saldo | optional |

La riserva operativa **€120k** è protetta.

## 8. OPEX master structure

Non consolidare un solo OPEX "medio" finché mancano actuals.

Categorie obbligatorie:

- personale;
- energia importata;
- acqua;
- fertilizzanti/substrati;
- packaging;
- consegne/logistica;
- manutenzione;
- ricambi;
- service contracts;
- software/subscription;
- telecom;
- assicurazioni;
- laboratorio/analisi;
- pulizia/HACCP;
- smaltimenti/scarichi;
- interessi/debito;
- amministrazione;
- marketing/commerciale;
- pilot/R&D non capitalizzato;
- downtime/losses.

Per ogni categoria registrare:
- fixed/variable;
- €/month;
- €/kg;
- €/m²;
- €/order;
- €/m³;
- €/kWh;
- owner;
- fonte.

## 9. OPEX misurato dal go-live

Primi 90 giorni:

- kWh e € per subsystem;
- m³ acqua;
- fertilizzante;
- packaging;
- waste/scarto;
- ore uomo;
- manutenzione;
- service;
- ricambi;
- consegne/km;
- downtime;
- resi/rimborsi.

A day 30 e day 90 confrontare:
- design;
- budget;
- actual.

## 10. Ricavi e margine

Target P1:
- **€250k/anno ricorrenti** da validare, non forecast.

Controllo mensile:
- revenue;
- gross margin;
- contribution margin;
- €/m²;
- €/kg;
- €/order;
- delivery cost/order;
- spoilage;
- return/refund;
- channel mix.

Break-even illustrativo corrente:
- fixed/semi-fixed ~€150–170k/y;
- contribution margin 60–70%;
- break-even revenue ~€229–267k/y.

## 11. Gate di revisione CAPEX

### G-CAPEX-GREEN
Condizioni:
- total installed forecast <=€950k;
- riserva €120k intatta;
- IVA line chiusa;
- bridge chiuso;
- P1 productive scope completo;
- critical systems non tagliati.

### G-CAPEX-AMBER
Una o più:
- installed forecast €950k–€1,05M;
- contingency assorbita >50%;
- un major package >20% sopra envelope;
- lead time forza anticipo cassa;
- eleggibilità incerta.

Azione:
- design-to-value;
- scope review;
- payment schedule negotiation;
- no optional order.

### G-CAPEX-RED
Una o più:
- fondo operativo viene usato per CAPEX;
- IVA senza linea dedicata;
- bridge non coperto;
- safety/cold/water/first-production scope incompleto;
- total installed forecast >€1,05M senza nuova copertura;
- contributo/finanziamento non perfezionati.

Azione:
- stop nuovi impegni irreversibili.

Le soglie amber/red sono governance interna e vanno riesaminate dopo i primi installed RFQ.

## 12. Collegamento procurement/pilot/SAT

Un package può essere finanziariamente "ready" solo se:

- procurement class compatibile;
- pilot richiesto = PASS;
- installed RFQ disponibile;
- SAT/commissioning scope contrattualizzato;
- owner e maintenance definiti;
- funding/eleggibilità definiti.

Nessuna voce Q3 passa direttamente da benchmark a ordine.

## 13. Reporting mensile

Dashboard minima:
- CAPEX budget;
- committed;
- paid;
- eligible;
- grant approved;
- grant received;
- debt drawn;
- cash;
- operational reserve;
- VAT bridge usage;
- procurement maturity;
- pilot status;
- SAT status;
- revenue;
- contribution margin;
- 90-day OPEX;
- forecast D3/D4.

## 14. Decisione

Il target €850k resta il **control budget**.

Non viene "protetto" tagliando:
- safety;
- acqua essenziale;
- cold-chain;
- commissioning;
- load measurement;
- operator training;
- working capital.

Se gli RFQ reali non rientrano, si modifica il perimetro P1 o il finanziamento prima di impegnare la cassa.
