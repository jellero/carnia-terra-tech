# BOM-009 — Distribuzione termica idronica

**Aggiornato:** 17 settembre 2026  
**Ambito:** accumulo -> collettore secondario -> 6 comparti -> terminali near-crop.  
**Stato:** `ARCHITETTURA E CANDIDATI REALI / QUANTITÀ E TAGLIE BLOCCATE DAL CALCOLO TERMICO-IDRAULICO`.

## 1. Distinta principale

| Codice | Voce | Quantità working | Stato | Benchmark / nota |
|---|---|---:|---|---|
| TH-HDR-001 | Collettore mandata principale | 1 | DA CALCOLO/RFQ | DN/materiale da portata totale |
| TH-HDR-002 | Collettore ritorno principale | 1 | DA CALCOLO/RFQ | accessibile e coibentato |
| TH-ZON-001 | Gruppi zona C1–C6 | 6 | REQUISITO | standardizzare dove possibile |
| TH-PMP-001 | Circolatore zona | 6 + 1 scorta candidata | CANDIDATI REALI | ALPHA2 25-60 da €249 incl.; MAGNA1 25-60 €426,63 incl. benchmark |
| TH-MIX-001 | Valvola miscelatrice | 6 | CANDIDATO | ESBE VRG131 DN25 Kvs10 ~€64,15 osservati |
| TH-MIX-002 | Attuatore miscelatrice | 6 + scorta | CANDIDATO | ESBE ARA661 230V ~€148,35 IVA incl. |
| TH-FLW-001 | Bilanciamento/misura portata | 6 | CANDIDATI | Caleffi 132602 1", 10–40 l/min ~€102,28 IVA incl. |
| TH-ISO-001 | Valvole isolamento mandata | 6 + centrali | DA DISTINTA | full bore/serviceable |
| TH-ISO-002 | Valvole isolamento ritorno | 6 + centrali | DA DISTINTA | idem |
| TH-NRV-001 | Valvole non ritorno | da P&ID | CONDIZIONALE | evitare circolazioni parassite |
| TH-STR-001 | Filtri/strainer | da P&ID | DA PROGETTARE | accesso pulizia |
| TH-AIR-001 | Sfiati/separazione aria | da P&ID | REQUISITO | posizione da schema |
| TH-DRN-001 | Scarichi/riempimento | da P&ID | REQUISITO | per manutenzione zona |
| TH-TMP-001 | Sensore T mandata | 6 | REQUISITO | PT1000/industriale da standardizzare |
| TH-TMP-002 | Sensore T ritorno | 6 | REQUISITO | idem |
| TH-PRS-001 | Pressione/Δp | centrale/zone critiche | CANDIDATO | valore da architettura |
| TH-EMT-001 | Tubo terminale near-crop | ~2.700–3.000 m working | DA VALIDARE | preferenza tubo greenhouse-specific |
| TH-EMT-002 | Raccordi terminale | da layout | DA DISTINTA | riparabilità in campo |
| TH-EMT-003 | Supporti/fissaggi terminale | da layout | DA DISTINTA | UV/corrosione/espansione |
| TH-MAIN-001 | Dorsale mandata | m/DN da layout | DA CALCOLO | trasporto, non emissione |
| TH-MAIN-002 | Dorsale ritorno | m/DN da layout | DA CALCOLO | idem |
| TH-INS-001 | Coibentazione dorsali | m da layout | DA CALCOLO/RFQ | protezione ambiente serra |
| TH-FIT-001 | Raccordi/tee/riduzioni/unioni | da P&ID | DA DISTINTA | evitare forfait |
| TH-SUP-001 | Staffe/supporti dorsali | da passo | DA DISTINTA | corrosione/condensa |
| TH-ELC-001 | Cablaggio pompe/attuatori/sensori | 6 zone + centrale | DA RFQ | collegamento PLC locale |
| TH-CTL-001 | I/O e logica PLC | 6 zone | REQUISITO | fallback locale |
| TH-SP-001 | Pompa zona scorta | 1 | CANDIDATO | se modello unico sulle 6 zone |
| TH-SP-002 | Attuatore miscelatrice scorta | 1 | CANDIDATO | standardizzare |
| TH-SP-003 | Sensori/raccordi/valvole critiche | 1 lotto | REQUISITO | quantità da piano ricambi |
| TH-COM-001 | Lavaggio/prova/bilanciamento | 1 lotto | OBBLIGATORIO | dati finali per zona |
| TH-COM-002 | As-built/P&ID/parametri | 1 lotto | OBBLIGATORIO | documentazione manutenzione |

## 2. Terminali — candidati

### E1 — Elydan TUBSER Ø25

- PEHD;
- uso dichiarato: riscaldamento basse temperature di serre agricole/maraîchères;
- resistenza UV dichiarata;
- bobina;
- prezzo `DA PREVENTIVO`.

**Stato:** `CANDIDATO GREENHOUSE-SPECIFIC`.

### E2 — Palaplast GEOPAL PE100 Ø25/28

- specifico per greenhouse heating;
- rotoli da 100 m;
- max temperatura pubblicata 70 °C;
- pressione di esercizio da scheda/variante;
- prezzo `DA PREVENTIVO`.

**Stato:** `CANDIDATO GREENHOUSE-SPECIFIC`.

### E3 — IVAR FF-Therm PE-Xa Ø25×2,3 EVOH

- listino IVAR: €5,81/m;
- benchmark retail UE: ~€4,23/m;
- PN6 a +90 °C / PN10 a +60 °C nel prodotto retail osservato;
- barriera ossigeno.

**Stato:** `CANDIDATO IDRAULICO / IDONEITÀ AMBIENTE SERRA DA CONFERMARE`.

## 3. Peso economico del solo terminale

Se, solo per benchmark, tutti i 2.700–3.000 m fossero IVAR Ø25×2,3:

| Lunghezza | €4,23/m | €5,81/m |
|---:|---:|---:|
| 2.700 m | €11.421 | €15.687 |
| 3.000 m | €12.690 | €17.430 |

Non include raccordi, supporti, sfrido, posa, test o ricambi.

## 4. Pompe — benchmark

### Grundfos ALPHA2 25-60 180

- prezzo osservato da €249 IVA incl.;
- portata pubblicata ~2,7 m³/h;
- prevalenza max ~6 m;
- 3–34 W.

Non selezionare senza curva Q/H e perdita circuito.

### Grundfos MAGNA1 25-60

- prezzo osservato €426,63 IVA incl.;
- 10 bar;
- prevalenza max ~6 m;
- classe industriale/impiantistica più robusta.

Non selezionare solo perché più grande/costosa.

## 5. Miscelazione — benchmark

- ESBE VRG131 DN25 Kvs10: ~€64,15;
- ESBE ARA661 230 V 3-punti, 6 Nm, 120 s: ~€148,35 IVA incl.

Hardware per sei zone, solo valvola+attuatore: ~€1.275 complessivi usando questi prezzi osservati.

## 6. Bilanciamento — benchmark

Caleffi 132602:

- 1";
- 10–40 l/min;
- lettura diretta;
- ~€102,28 IVA incl.;
- 6 pz ~€613,68.

Il campo 0,6–2,4 m³/h non copre automaticamente tutte le zone: scegliere modello/range dopo il calcolo.

## 7. Benchmark testa-zona incompleta

Per pura comparazione:

`pompa + VRG131 + ARA661 + 132602`

- ALPHA2: ~€563,78 per zona / ~€3.382,68 per 6;
- MAGNA1: ~€741,41 per zona / ~€4.448,46 per 6.

Sono esclusi tutti gli altri componenti e la posa. Non usare questi numeri come preventivo impianto.

## 8. Dimensionamento pompe

Relazione acqua:

`Q[m³/h] ≈ P[kW] / (1,163 × ΔT[K])`.

Esempio: 20 kW a ΔT 5 K -> ~3,44 m³/h. In quel caso un prodotto con portata indicativa 2,7 m³/h non sarebbe sufficiente a quel punto di lavoro, prima ancora di valutare la prevalenza.

## 9. Controllo e failure-safe

Ogni zona deve poter:

- essere isolata;
- fermare la propria pompa;
- essere messa in manuale;
- segnalare assenza portata;
- leggere T mandata/ritorno;
- evitare che il guasto di una zona fermi le altre.

Il guasto server/cloud non deve fermare la protezione termica minima.

## 10. Manutenzione

Registrare:

- ore pompa;
- ΔT anomalo;
- portata anomala;
- cicli valvola;
- perdite;
- spurghi;
- pulizia filtri;
- sostituzione attuatori/sensori;
- stato tubo/supporti.

## 11. Open points

1. carico termico per comparto;
2. temperature acqua;
3. ΔT idronico;
4. portate;
5. prevalenze;
6. tubo greenhouse specifico e potenza per metro;
7. lunghezze reali;
8. collettori/dorsali;
9. trattamento acqua tecnica;
10. antigelo;
11. misura energia termica;
12. P&ID e preventivi.
