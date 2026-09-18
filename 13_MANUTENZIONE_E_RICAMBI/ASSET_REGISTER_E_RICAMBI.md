# Asset register, ricambi e manutenzione

**Aggiornato:** 18 settembre 2026

## 1. Campi obbligatori

Per ogni asset:

### Identità
- asset ID;
- sistema;
- funzione;
- criticità P0/P1/P2/P3;
- marca;
- modello;
- seriale;
- revisione;
- ubicazione.

### Acquisto
- fornitore;
- ordine;
- data;
- costo;
- garanzia;
- eleggibilità/contributo dove rilevante.

### Tecnica
- alimentazione;
- capacità;
- interfacce;
- firmware/software;
- configurazione;
- dipendenze;
- manuale;
- as-built.

### Manutenzione
- PM;
- frequenza;
- consumabili;
- utensili;
- ore;
- competenza;
- contractor.

### Ricambi
- ricambio critico;
- quantità onsite;
- lead time;
- shelf life;
- alternativa compatibile;
- punto di riordino.

### Failure/recovery
- failure mode;
- allarme;
- fallback;
- recovery;
- RTO;
- escalation.

## 2. Classi ricambio

### S0 — consumabile
Basso costo, uso frequente.

### S1 — ricambio critico rapido
Un guasto può fermare P0/P1 e il componente ha costo ragionevole.

### S2 — ricambio critico costoso
Non necessariamente onsite; serve SLA/fornitore/strategia alternativa.

### S3 — non critico
Acquisto a guasto accettabile.

## 3. Esempi da valutare S1

Non sono quantità definitive:
- sensori critici;
- alimentatori 24 V;
- relè/contattori;
- valvole/attuatori standard;
- seal/filter kit;
- pompa dosatrice o kit compatibile;
- switch/rete essenziale;
- dischi/SSD enterprise secondo architettura;
- fusibili/SPD;
- consumabili packaging essenziali.

Per pompe, PDC, inverter, PCS, compressor e altri asset costosi:
- modularità;
- unità standby;
- SLA;
- stock vendor;
- interchangeability.

## 4. Mezzo multifunzione

Registrare:
- batteria;
- caricatore;
- forche;
- benna;
- pneumatici;
- filtri/oli se applicabili;
- parti usura;
- diagnostica;
- assistenza;
- mezzo sostitutivo/noleggio.

## 5. PLE/accesso in quota

Registrare:
- verifiche periodiche;
- batteria;
- cingoli;
- tubi;
- sensori;
- emergency lowering;
- DPI;
- formazione;
- rescue plan.

## 6. Robot ragno R&S

Anche un prototipo deve avere:
- asset ID;
- battery state;
- tether/recovery gear;
- firmware;
- config backup;
- spares;
- failure log.

R&S non significa manutenzione informale.

## 7. Configurazioni digitali

Backup obbligatorio per:
- PLC;
- VFD;
- EMS;
- BESS settings esportabili;
- switch/firewall;
- server;
- database;
- camera/vision configs dove materiale.

Il backup deve essere testato, non solo esistente.

## 8. Review

- prima dell'ordine: maintainability review;
- commissioning: popolamento asset register;
- 30 giorni: correggere PM;
- 90 giorni: ricambi e failure reali;
- annuale: obsolescenza/TCO.
