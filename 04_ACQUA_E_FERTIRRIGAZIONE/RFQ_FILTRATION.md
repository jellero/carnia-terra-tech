# RFQ — Filtrazione acqua irrigua

**Ambito:** Carnia TerraTech, serra ~4.200 m², distribuzione working 6 comparti / 24 settori, gocciolatori target 120 mesh / 130 µm.

## 1. Regola offerta

Non accettare una voce unica `sistema filtrazione`.

Separare almeno:

- separatore sabbia/idrociclone;
- filtro/i principali;
- filtro di sicurezza secondario;
- collettori e bypass;
- valvole manuali;
- valvole automatiche/controlavaggio;
- controller;
- manometri/trasmettitori pressione;
- misura Δp;
- tubazioni/raccordi;
- scarico controlavaggio;
- supporti;
- quadro/cablaggio;
- posa;
- commissioning;
- ricambi;
- documentazione.

Ogni riga: quantità, marca/modello, filtrazione µm/mesh, portata, Δp pulito/sporco, Pmax, prezzo unitario/totale, IVA, trasporto, posa, garanzia, lead time.

## 2. Dati che forniremo al fornitore

- analisi acqua completa;
- origine acqua e stagionalità;
- SST/turbidità;
- sabbia e granulometria;
- organico/alghe;
- Fe/Mn;
- pH/EC/durezza/alcalinità;
- portate min/max;
- pressione disponibile;
- schema pompe/fertirrigazione;
- requisito emettitori 120 mesh / 130 µm.

Se questi dati non sono ancora disponibili, l'offerta deve dichiarare esplicitamente le assunzioni.

## 3. Scenari obbligatori

Quotare almeno, se tecnicamente coerenti:

### S1 — acqua buona

- filtro manuale 120 mesh;
- misura Δp;
- bypass manutenzione;
- filtro secondario/sicurezza opzionale.

### S2 — automatico

- filtro automatico 120 mesh;
- controlavaggio automatico su Δp + tempo;
- filtro manuale di sicurezza/bypass;
- strumentazione completa.

### S3 — acqua con sabbia

- idrociclone;
- filtro automatico 120 mesh;
- sicurezza secondaria;
- scarico sabbia/controlavaggio.

### S4 — acqua superficiale difficile

- proporre dischi automatici o media filtration/graniglia;
- filtro secondario 120 mesh;
- indicare frequenza/volume controlavaggio e OPEX.

## 4. Ridondanza

Quotare separatamente:

- un solo filtro principale;
- due rami isolabili;
- automatico + manuale di sicurezza dimensionato per modalità degradata.

Dichiarare quale portata resta disponibile con un ramo fuori servizio.

## 5. Prestazioni idrauliche

Per ogni filtro dichiarare:

- portata nominale;
- portata raccomandata con qualità acqua fornita;
- Δp filtro pulito alla portata di progetto;
- soglia Δp lavaggio;
- Δp massimo ammesso;
- curva perdita di carico;
- pressione minima/massima;
- portata e pressione di controlavaggio;
- volume acqua per ciclo;
- durata ciclo;
- capacità filtrante/superficie.

## 6. Idrociclone

Se proposto:

- range portata efficace;
- dimensione minima particelle separabili;
- efficienza attesa sulla nostra granulometria;
- volume camera sabbia;
- modalità spurgo manuale/automatico;
- perdita di carico;
- materiale/corrosione;
- manutenzione.

Non proporre idrociclone fuori dal proprio range Q.

## 7. Automazione

Richiedere segnali locali/PLC per:

- pressione monte;
- pressione valle;
- Δp;
- stato controlavaggio;
- allarme lavaggio fallito;
- pressione insufficiente;
- eventuale stato valvole;
- contatore acqua di lavaggio se economicamente sensato.

Il sistema deve continuare a proteggere l'irrigazione senza cloud.

## 8. Controlavaggio

Il fornitore deve dichiarare:

- se avviene durante irrigazione o con pausa;
- portata richiesta;
- pressione minima;
- volume/ciclo;
- scarico necessario;
- qualità/pressione acqua di lavaggio;
- perdita di produzione/portata durante il ciclo;
- logica di fallback se Δp resta alto dopo il lavaggio.

## 9. Chimica acqua

Dichiarare cosa il filtro **non** risolve.

In presenza di ferro, manganese, carbonati, sali o biofilm, indicare eventuali pretrattamenti necessari separatamente. Non presentare 120 mesh come soluzione a contaminanti disciolti.

## 10. Materiali e fertilizzanti

Dichiarare compatibilità con:

- pH di esercizio previsto;
- fertilizzanti A/B;
- acido usato per correzione pH/pulizia;
- disinfettanti eventualmente ammessi;
- UV/ambiente tecnico;
- temperatura acqua.

## 11. Manutenzione e ricambi

Quotare separatamente:

- pacco dischi/rete;
- guarnizioni;
- membrane valvole;
- solenoidi;
- controller;
- sensori Δp/pressione;
- kit pulizia;
- valvole critiche.

Indicare tempi manutenzione, intervalli e lead time ricambi.

## 12. Commissioning

Obbligatorio verbale con:

- Q reale;
- P monte/valle;
- Δp pulito;
- test soglia controlavaggio;
- volume e durata lavaggio;
- pressione residua a valle;
- verifica 120 mesh/130 µm installati;
- test bypass/ridondanza;
- baseline per manutenzione predittiva.

## 13. Criterio di confronto offerte

Confrontare su:

- protezione emettitori;
- portata utile;
- perdita di carico;
- affidabilità;
- capacità degradata;
- acqua/energia controlavaggio;
- ore manutenzione;
- ricambi;
- CAPEX;
- OPEX;
- compatibilità futura con fonte acqua alternativa.