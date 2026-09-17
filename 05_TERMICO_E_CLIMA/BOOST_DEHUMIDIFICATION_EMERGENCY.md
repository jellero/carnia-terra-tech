# Boost termico, deumidificazione ed emergenza

**Aggiornato:** 17 settembre 2026  
**Stato:** `ARCHITETTURA DEFINITA / CANDIDATI REALI / QUANTITÀ DA CARICO TERMICO E BILANCIO UMIDITÀ`.

## 1. Tre funzioni diverse

Questo package separa funzioni che non devono essere confuse:

1. **boost termico** — aumentare rapidamente la potenza sensibile in un comparto usando acqua calda disponibile;
2. **deumidificazione** — rimuovere realmente vapore acqueo dall'aria;
3. **emergenza** — mantenere condizioni di sopravvivenza quando una parte della generazione o dell'alimentazione è indisponibile.

Un aerotermo idronico da solo **non deumidifica**: aumenta la temperatura dell'aria e quindi abbassa l'UR relativa, ma la massa d'acqua nell'aria resta. La rimozione di umidità richiede ricambio con aria esterna più secca, condensazione su superficie fredda/refrigerata oppure adsorbimento/assorbimento.

## 2. Architettura working

### B1 — boost idronico

`accumulo -> circuito comparto -> valvola/isolamento -> aerotermo agricolo -> ritorno`

Working quantity: **0–1 aerotermo per comparto**, con priorità di studio C1, C2 e C6. Non è quantità d'ordine.

Funzioni:

- recupero rapido dopo aperture/ventilazione;
- supporto anticondensa quando combinato con ricambio d'aria;
- protezione locale di vivaio/area sensibile;
- distribuzione rapida del calore già disponibile nell'accumulo;
- eventuale supporto estivo con acqua fredda solo se in futuro esiste una sorgente frigorifera e gestione condensa.

### D1 — heat + vent controllato

Baseline a CAPEX basso:

- HAF mantiene l'aria omogenea;
- il PLC valuta T/RH/dew point o humidity ratio interno/esterno;
- si introduce aria esterna solo quando ha minore contenuto assoluto di umidità e le condizioni meteo lo consentono;
- il boost termico compensa la perdita sensibile e limita i gradienti freddi;
- aperture e schermi vengono coordinati.

È semplice ma disperde energia e dipende dalle condizioni esterne.

### D2 — ventilazione meccanica con recupero

Scenario da predisporre/quotare se l'umidità invernale diventa un costo rilevante:

`presa aria esterna filtrata -> recuperatore -> distribuzione uniforme -> serra -> estrazione -> recuperatore -> espulsione`

Richiede ventilatori modulanti, filtrazione/insect protection, scarico condensa, anti-gelo, distribuzione aria e integrazione PLC. Riduce la perdita sensibile rispetto all'apertura delle finestre.

### D3 — deumidificazione interna a condensazione

Macchina refrigerata dedicata horticulture che condensa acqua senza ricambio d'aria. Vantaggi: controllo indipendente dall'umidità esterna e recupero della parte sensibile/latente come calore nell'ambiente; svantaggi: CAPEX, assorbimento elettrico, refrigerante, manutenzione frigorifera e calore aggiunto quando non desiderato.

Da valutare soprattutto per C1/C2/C6 dopo misura/forecast del carico di umidità.

## 3. Aerotermi candidati — Reventon FARMER

La serie FARMER è progettata per serre e ambienti agricoli umidi/corrosivi, con scambiatore protetto GOLD epoxy.

### FARMER HCF IP54-EC

- codice HCFE-50EC-2534;
- portata massima ~4.800 m³/h;
- motore EC 430 W;
- IP54;
- campo potenza pubblicato ~6,9–63,9 kW a seconda di acqua/aria;
- 3/4";
- max 120 °C / 1,6 MPa;
- benchmark retail Germania 17/09/2026: **€901 IVA 19% inclusa**;
- stato: `PREZZO TROVATO / CANDIDATO PER MODULAZIONE`.

Vantaggio: EC/modulazione. Limite: grado IP inferiore alla variante IP66; verificare regime di lavaggio e aggressività ambiente.

### FARMER HCF IP66

- codice WHHCF53-1527;
- 5.000 m³/h;
- motore 560 W, 230 V;
- IP66;
- rumore dichiarato 63 dB a 5 m;
- attacchi 3/4";
- scambiatore 1,95 l;
- max 120 °C / 1,6 MPa;
- benchmark retail UE osservati: circa **€822–943 IVA locale inclusa**, trasporto escluso;
- stato: `PREZZO TROVATO / CANDIDATO ROBUSTO`.

### Prestazioni utili con acqua a bassa temperatura

Per HCF IP66 a 5.000 m³/h:

| Acqua | aria ingresso | potenza | portata acqua | Δp coil |
|---|---:|---:|---:|---:|
| 50/40 °C | 15 °C | 17,1 kW | 1,49 m³/h | 11 kPa |
| 50/40 °C | 20 °C | 13,7 kW | 1,19 m³/h | 7 kPa |
| 40/30 °C | 15 °C | 10,3 kW | 0,89 m³/h | 4 kPa |
| 40/30 °C | 20 °C | 7,0 kW | 0,61 m³/h | 2 kPa |

**Regola:** non usare il valore commerciale 50,2 kW per dimensionare un impianto a PDC. L'RFQ deve fornire tabelle a 35/30, 40/30, 45/35 e 50/40 °C per aria 5/10/15/20 °C.

## 4. Deumidificatori horticulture candidati

### DryGair DG-3 50 Hz

Dati pubblici @18 °C / 80% RH:

- estrazione acqua: **11 l/h**;
- portata aria: ~4.500 m³/h;
- assorbimento: **2,3 kW**;
- efficienza dichiarata: 4,8 l/kWh;
- 400 V 3~;
- max operativo 14 A;
- temperatura operativa 10–35 °C;
- peso ~300 kg;
- refrigerante R513A;
- prezzo: `PREZZO DA PREVENTIVO`.

È un candidato interessante per comparti da ~700 m², ma 11 l/h non viene assunto sufficiente senza bilancio reale di traspirazione/infiltrazioni.

### DryGair DG-12 50 Hz

Dati pubblici @18 °C / 80% RH:

- estrazione acqua: **43 l/h**;
- portata aria: ~20.000 m³/h;
- assorbimento: **9,55 kW**;
- efficienza dichiarata: 4,5 l/kWh;
- 400 V 3~;
- max operativo 30 A;
- temperatura 10–35 °C;
- peso ~770 kg;
- prezzo: `PREZZO DA PREVENTIVO`.

Disponibile opzione defrost dichiarata per estendere il funzionamento fino a circa 6 °C. Verificare resa reale a bassa T e RH inferiori all'80%.

## 5. Ventilazione con recupero

La letteratura Wageningen identifica la ventilazione meccanica con recupero di calore come soluzione energeticamente interessante per il controllo dell'umidità in climi freddi, perché consente di rimuovere vapore riducendo la perdita di calore sensibile.

Candidato di mercato/innovazione da RFQ: **AIRGAIA EXT'air**, sistema dual-flow per serre con recupero. La comunicazione SIVAL 2025 dichiara, nel proprio esempio di progetto, aria esterna 0 °C/80% RH riscaldata fino a circa 18 °C con serra 20 °C/80% RH e un recupero vicino al 90%. Questi sono dati del produttore/contesto dimostrativo e vanno verificati alle nostre portate e condizioni.

Prezzo: `PREZZO DA PREVENTIVO`.

## 6. Controllo dell'umidità

Non comandare la deumidificazione solo su UR.

Il PLC deve calcolare almeno:

- temperatura interna/esterna;
- UR interna/esterna;
- dew point;
- umidità assoluta o humidity ratio;
- VPD coltura;
- stato schermo;
- posizione aperture;
- temperatura acqua disponibile;
- energia termica residua nell'accumulo.

Regola D1 semplificata:

`deumidifica con aria esterna solo se x_out < x_in - margine` e se vento/pioggia/T esterna e rischio gelo consentono la manovra.

Su `x_out >= x_in` aprire le finestre può raffreddare senza rimuovere abbastanza umidità: la logica deve impedirlo salvo esigenze di temperatura/sicurezza.

## 7. Emergenza — cosa può e non può fare il boost

L'aerotermo **non è una sorgente di energia**. Funziona solo se esiste acqua calda e circolazione.

Scenari:

- **E1 — una PDC guasta:** altre PDC + accumulo + aerotermi possono concentrare potenza sui comparti prioritari;
- **E2 — tutte PDC ferme ma accumulo caldo:** aerotermi permettono scarica rapida/localizzata finché c'è energia nel tank;
- **E3 — blackout rete:** servono alimentazione di emergenza per pompe, ventilatori, valvole e controllo; UPS del PLC da solo non alimenta la potenza termica;
- **E4 — blackout lungo / accumulo scarico / PDC indisponibili:** serve una vera sorgente termica alternativa o generazione elettrica di backup, da dimensionare nel punto 12/06.

Quindi BOM-012 copre la **distribuzione di emergenza**, non sostituisce il futuro dimensionamento del generatore/backup energetico.

## 8. Logica operativa

### Boost

- richiesta alta potenza comparto;
- verifica energia termica disponibile;
- avvio pompa/valvola;
- conferma portata;
- avvio ventola;
- controllo T aria/mandata/ritorno;
- stop con post-ventilazione se richiesta dal costruttore.

### Deumidificazione D1

- HAF ON;
- confronto humidity ratio interno/esterno;
- apertura minima controllata;
- boost termico se necessario;
- chiusura quando target dew point/VPD raggiunto.

### Deumidificazione D2/D3

- comando modulante;
- misura l/h condensata o portata aria;
- kWh elettrici;
- integrazione con schermi e HAF;
- blocco/allarme condensa/scarico.

## 9. Failure modes

- ventola aerotermo guasta;
- valvola bloccata;
- coil ostruito/sporco;
- perdita acqua;
- corrosione coil;
- scarico condensa bloccato;
- deumidificatore in high-pressure/low-pressure fault;
- filtro aria intasato;
- recuperatore ghiacciato;
- sensore T/RH fuori calibrazione;
- errato confronto umidità interna/esterna;
- apertura non confermata;
- perdita alimentazione;
- PLC/server offline.

Il controllo vitale resta locale. Un guasto su D2/D3 non deve fermare il riscaldamento di sopravvivenza.

## 10. Manutenzione e ricambi

Aerotermi:

- pulizia coil;
- controllo rivestimento anticorrosione;
- ventola/motore;
- cuscinetti se applicabili;
- valvole/attuatori;
- flessibili e guarnizioni;
- serraggi/supporti;
- filtro/defangatore circuito.

Deumidificatori/HRV:

- filtri aria;
- batterie/scambiatori;
- vasca e scarico condensa;
- sensori T/RH;
- pressostati;
- ventilatori;
- circuito frigorifero da tecnico abilitato;
- pulizia/disinfezione;
- verifica efficienza reale l/kWh.

## 11. Gate

BOM-012 diventa dimensionabile quando sono noti:

1. carico termico per comparto;
2. temperatura acqua reale disponibile nei diversi scenari;
3. profilo notturno di traspirazione/umidità C1–C6;
4. meteo e umidità assoluta del sito;
5. strategia schermi e ventilazione;
6. target VPD/dew point;
7. capacità elettrica e FV/backup;
8. costo energia e valore del calore recuperato;
9. RFQ Reventon/DryGair/HRV;
10. costo del rischio Botrytis/condensa e perdite produttive.
