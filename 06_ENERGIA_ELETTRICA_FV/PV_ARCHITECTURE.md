# Architettura fotovoltaica — 120 kWp iniziali

**Aggiornato:** 17 settembre 2026  
**Stato:** `WORKING ARCHITECTURE / LOTTO E CONNESSIONE BLOCCANTI`.

## 1. Funzione nel sistema Carnia TerraTech

Il FV deve ridurre il costo elettrico e alimentare carichi flessibili senza diventare un vincolo per la coltivazione. La priorità energetica resta:

`carichi vitali/control plane -> celle e cold-chain -> pompe/fertirrigazione -> processi -> carichi differibili -> BESS 30 kW / EMS -> rete`.

Il BESS è il backup condiviso del sito, non una UPS locale. La potenza nota è **30 kW**; energia utile in kWh, autonomia, picco, transfer time, islanding e SOC reserve restano `DA CHIUDERE`. Il server centrale usa questi stati per load shedding e scheduling dei carichi differibili.

L'EMS sposta carichi quando conviene, ma PLC e protezioni restano autonomi.

## 2. Target e crescita

- fase 1: ~120 kWp DC;
- fase 2: 150–180 kWp DC se profilo carichi/connessione lo giustifica;
- nessuna copertura opaca dei 4.200 m² coltivati come soluzione base;
- predisporre canalizzazioni, quadro AC, rete dati e spazio inverter per espansione.

## 3. Moduli

Candidato 2026: Trina Vertex S+ TSM-470NEG9R.28.

Working: 256 moduli = 120,32 kWp. La scelta finale deve includere:

- garanzia prodotto/potenza;
- certificazioni IEC;
- resistenza neve/vento coerente con sito;
- carichi ammessi nei punti di clamp;
- disponibilità di moduli sostitutivi;
- compatibilità con inverter e connettori;
- PID/LID/LeTID e coefficiente temperatura;
- bancabilità e rete assistenza.

Tenere 1–2% moduli spare è da valutare su prezzo/lead time, non obbligatorio per default.

## 4. String design

Formula minima:

`Voc_cold = Voc_STC × [1 + |βVoc| × (25 - Tmin_cella)]`

La tensione della stringa a freddo, inclusa tolleranza, deve rimanere sotto il limite inverter.

Esempio non d'ordine con Trina 470 W e -20 °C: Voc sale a circa 60,5 V/modulo. Su inverter 1.100 V, 18 moduli sono circa 1.089 V prima di ulteriori margini; su inverter 1.000 V, 17 moduli superano circa 1.028 V. Quindi il numero moduli/stringa cambia realmente fra famiglie inverter.

Verificare anche Vmp caldo, corrente MPPT, Isc, numero ingressi e fusibili stringa.

## 5. Inverter

### Sungrow SG50CX-P2

- 50 kVA;
- 1.100 Vdc max;
- IP66/C5;
- DC SPD tipo I+II, AC tipo II secondo pagina prodotto;
- AFCI supportato;
- prezzo pubblico UE osservato da ~€1.899.

### Huawei SUN2000-50KTL-M3

- 50 kW nominali / 55 kW max cosφ=1;
- 4 MPPT / 8 ingressi;
- 1.100 Vdc max;
- 30 A max/MPPT, 20 A max/input;
- IP66;
- SPD DC/AC tipo II, AFCI, RS485;
- datasheet riporta CEI 0-16 e CEI 0-21 tra gli standard di connessione;
- prezzo pubblico UE osservato ~€2.379–2.399.

### SMA Sunny Tripower X 50/60

- famiglia 50/60 kW;
- 5 MPPT × 2 stringhe;
- 40 A utilizzabili/MPPT, 22 A/stringa;
- max PV 75 kWp per X50 / 90 kWp per X60;
- max 1.000 Vdc;
- System Manager integrato;
- ArcFix e gestione energia;
- X60 disponibile in Italia dal lancio 2025;
- benchmark pubblico UE: X50 ~€2.695, X60 ~€2.865.

CORE1 resta benchmark storico ma SMA lo dichiara non più commercializzato; non usarlo come baseline nuova.

## 6. BOS DC

Per ogni stringa/MPPT:

- cavi PV1-F;
- connettori originali/compatibili documentati;
- etichette permanenti;
- canaline/passaggi UV e roditori;
- eventuali combiner/fusibili solo se schema lo richiede;
- sezionamento DC;
- SPD secondo progetto fulmini;
- misura isolamento e test curve/stringhe al commissioning.

## 7. BOS AC

- interruttore per inverter;
- quadro raccolta AC;
- SPD;
- misura produzione;
- DDI/SPI/protezioni richieste dal DSO;
- cavi e caduta tensione;
- eventuale trasformatore/cabina MT solo se preventivo DSO lo richiede;
- predisposizione terzo inverter nello scenario I1.

## 8. Strutture

Tre famiglie:

- roof-mount Tech Barn;
- carport/coperture servizi;
- ground mount fixed tilt.

Nessuna struttura viene scelta senza neve/vento, geotecnica o verifica copertura. Un benchmark retail K2 per lamiera grecata è nell'ordine di ~€29/modulo ex VAT in piccoli kit, mentre benchmark factory per ground-mount steel possono essere molto inferiori: nessuno dei due rappresenta il costo installato Carnia.

Il vecchio input `moduli + struttura ~€200/kWp` non è un budget robusto: con moduli 470 W oggi il solo modulo sta circa ~€147–211/kWp nei benchmark osservati, lasciando poco margine alla struttura nei casi più costosi.

## 9. O&M e failure modes

Failure modes:

- inverter fuori servizio;
- stringa aperta/corto/isolamento basso;
- connettore caldo;
- SPD esaurito;
- ombreggiamento/sporcizia;
- rottura modulo;
- infiltrazione roof-mount;
- corrosione struttura;
- perdita comunicazione;
- limitazione DSO/rete assente.

Fallback: produzione parziale sugli inverter/stringhe sani; rete pubblica per i carichi; nessun carico vitale deve dipendere dalla produzione FV istantanea.

Ricambi/TCO: connettori, fusibili se usati, SPD/PCB sostituibili, 1–2 moduli compatibili o SLA di fornitura, ventole inverter se previste, documentazione string map e IV baseline.

## 10. Misure e KPI

- kWh DC/AC per inverter;
- kWh autoconsumati / immessi / prelevati;
- clipping;
- availability inverter;
- performance ratio;
- kWh/kWp;
- temperatura inverter/moduli dove utile;
- allarmi isolamento/SPD/AFCI;
- quota FV assorbita da PDC e carichi flessibili;
- costo energia evitato.
