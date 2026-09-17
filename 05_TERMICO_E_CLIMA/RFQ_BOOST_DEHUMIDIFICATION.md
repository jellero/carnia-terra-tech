# RFQ — Boost termico, deumidificazione ed emergenza

**Ambito:** serra Carnia TerraTech ~4.200 m², 6 comparti, sistema PDC + accumulo a bassa temperatura.

## 1. Regola dell'offerta

Non accettare un forfait unico `aerotermi/deumidificazione`.

Separare:

- aerotermi;
- staffe/supporti;
- valvole/attuatori;
- flessibili/raccordi;
- filtri/strainer;
- sensori;
- elettrico;
- controllo;
- eventuale ventilazione meccanica/recupero;
- eventuale deumidificazione refrigerata;
- scarichi condensa;
- posa;
- commissioning;
- ricambi;
- manutenzione.

## 2. Aerotermi — dati obbligatori

Quotare almeno una soluzione specifica per serre/ambienti agricoli corrosivi e dichiarare:

- marca/modello;
- IP;
- materiale housing;
- trattamento anticorrosione coil;
- portata aria e modulazione;
- assorbimento ventilatore;
- rumore;
- lancio aria;
- attacchi;
- Pmax/Tmax;
- peso;
- pulibilità;
- resistenza a umidità, detergenti e prodotti fitosanitari applicabili.

Fornire tabella resa termica e idraulica almeno per:

- acqua 35/30 °C;
- 40/30 °C;
- 45/35 °C;
- 50/40 °C;
- aria ingresso 5/10/15/20 °C.

Per ogni punto indicare:

- kW;
- m³/h acqua;
- Δp coil;
- T aria uscita;
- velocità ventola;
- W elettrici.

Non usare 90/70 °C come unico dato commerciale.

## 3. Scenari aerotermi

Quotare:

- B1: 3 unità per C1/C2/C6;
- B2: 6 unità, una per comparto;
- B3: soluzione alternativa motivata.

Queste quantità servono solo a confrontare CAPEX e non costituiscono ordine.

## 4. Valvole e idraulica

Per unità separare:

- valvola 2 vie o 3 vie;
- attuatore;
- isolamento mandata/ritorno;
- eventuale bilanciamento;
- flessibili;
- filtro;
- sfiato/scarico;
- T mandata/ritorno;
- raccordi;
- coibentazione delle sole linee di trasporto.

Indicare perdita di carico totale del ramo.

## 5. Controllo aerotermo

Richiedere:

- comando ON/OFF e modulante disponibile;
- 0–10 V / Modbus / contatti / altro;
- feedback ventola/guasto;
- velocità reale se disponibile;
- interblocco con portata acqua;
- gestione freeze protection;
- manual override locale.

## 6. D1 — heat + vent

Il system integrator deve proporre logica basata su:

- T/RH interno ed esterno;
- dew point;
- humidity ratio;
- VPD;
- vento/pioggia;
- stato schermi;
- energia termica disponibile.

Dichiarare:

- minima apertura richiesta;
- stima ricambio aria;
- perdita termica;
- tempo stimato per rimuovere un carico di umidità specificato;
- uniformità prevista;
- failure mode con apertura bloccata.

## 7. D2 — ventilazione meccanica con recupero

Quotare opzionalmente unità/sistema tipo AIRGAIA EXT'air o equivalente.

Dati obbligatori:

- portata aria nominale/min/max;
- prevalenza disponibile;
- potenza ventilatori;
- efficienza di recupero sensibile alle condizioni di progetto;
- eventuale recupero latente;
- curva prestazioni con -10/-5/0/+5 °C esterni;
- gestione gelo/defrost;
- condensa e drenaggio;
- filtrazione;
- rete anti-insetto e relativa Δp;
- distribuzione aria;
- rumorosità;
- manutenzione filtri/scambiatore;
- controllo PLC/BMS;
- costo unità, canali, posa e commissioning.

## 8. D3 — deumidificazione refrigerata

Quotare DryGair DG-3 / DG-12 o equivalenti horticulture.

Richiedere mappe di prestazione, non un solo punto:

- 10/12/15/18/20/25 °C;
- 70/75/80/85/90% RH;
- l/h acqua;
- kW elettrici;
- l/kWh;
- portata aria;
- calore sensibile restituito all'ambiente;
- eventuale defrost;
- campo operativo;
- refrigerante e GWP;
- carica;
- manutenzione frigorifera;
- rivestimenti anticorrosione;
- compatibilità zolfo/fitosanitari;
- scarico condensato;
- protocollo BMS/PLC;
- garanzia, assistenza e ricambi Italia.

## 9. Condensato

Per D2/D3 fornire:

- diametro scarico;
- portata massima;
- sifone;
- protezione gelo;
- sensore overflow;
- possibilità di misurare il condensato;
- destinazione e requisiti qualità se si intende recuperarlo.

Nessun riuso viene assunto senza verifica qualità.

## 10. Emergenza

Il fornitore/integratore deve descrivere il comportamento con:

- una PDC guasta;
- due PDC guaste;
- HX centrale guasto;
- accumulo scarico;
- blackout 30 min / 2 h / 12 h;
- pompa zona guasta;
- ventilatore aerotermo guasto;
- PLC centrale/server non disponibile;
- sensore T/RH guasto.

Separare energia richiesta per:

- controllo;
- pompe;
- aerotermi;
- D2;
- D3.

Indicare quali carichi devono essere su UPS e quali su generatore/backup di potenza.

## 11. Commissioning

Misurare e verbalizzare:

- portata acqua per aerotermo;
- ΔT acqua;
- potenza termica stimata/misurata;
- portata aria;
- uniformità T/RH;
- kg/h o l/h di umidità rimossa;
- kWh elettrici;
- l/kWh;
- risposta agli allarmi;
- fallback locale;
- modalità sopravvivenza.

## 12. Prezzi

Per ogni riga dichiarare:

- prezzo netto;
- IVA;
- trasporto;
- accessori obbligatori;
- posa;
- avviamento;
- garanzia;
- lead time;
- ricambi consigliati;
- costo manutenzione annuale indicativo.
