# Fonti — BOM-015 pompe principali irrigazione 1+1

**Aggiornato:** 17 settembre 2026.  
**Regola:** prezzi online = benchmark; selezione finale su curve certificate, duty point e RFQ.

## Grundfos — documentazione tecnica

- CR/CRI/CRN databooklet: https://api.grundfos.com/literature/Grundfosliterature-776430.pdf
- CR 10 databooklet: https://api.grundfos.com/literature/Grundfosliterature-776429.pdf
- Grundfos Product Center / guida documentazione: https://www.grundfos.com/it/support/how-to-guides/how-to-get-technical-product-information

Dati usati:

- famiglia CR 5/10 multistadio verticale;
- curve Q/H, potenza, NPSH e motori da verificare sul codice esatto offerto.

## Grundfos CR 10-6 — prezzo retail Italia

Tavolla, codice 96500984:

https://www.tavolla.com/grundfos-96500984-cr-10-6-a-a-a-e-hqqe-pompa-centrifuga-verticale-multistadio-con-porte-di-aspirazione-e-scarico-sullo-stesso-livello-6-giranti/

Osservato 17/09/2026:

- €1.946,78 IVA 22% inclusa;
- Q nominale 10 m³/h;
- H nominale 48,3 m;
- H max 61,2 m;
- motore 2,2 kW;
- Pmax 16 bar.

Stato: `PREZZO TROVATO / RETAIL ITALIA`.

## Grundfos CR 5 / CR 10 — benchmark UE

Hidraulicart:

- CR 5: https://www.hidraulicart.com/it/vertical/bomba-centrifuga-vertical-grundfos-cr-5/
- CR 10: https://www.hidraulicart.com/it/multicelular/pompa-centrifuga-verticale-grundfos-cr-10/

Benchmark osservati:

- CR 5-8 trifase ~€1.291;
- CR 10-4 ~€1.825;
- CR 10-5 ~€1.981;
- CR 10-6 ~€2.090.

IVA/trasporto/codice esatto da verificare.

## Grundfos Hydro Multi-E — listino 2026

Listino Grundfos gennaio 2026:

https://www.idroftp.net/FLIPBOOK/IDROSTILE/GRU/GRUNDFOS%20-%20LISTINO%202026/files/basic-html/page180.html

Righe usate come benchmark:

- Hydro Multi-E 2 CRE 10-3 U2: €12.185;
- Hydro Multi-E 2 CRE 10-5 U2: €13.323.

Stato: `LISTINO 2026 / IVA, SCONTO E CONFIGURAZIONE DA CONFERMARE`.

## Danfoss VLT Micro Drive FC-51

RS Italia, codice Danfoss 132F0022:

https://it.rs-online.com/web/p/inverter/8918827

Osservato:

- 2,2 kW;
- 3 fasi 380–480 V;
- 5,3 A;
- €895,30 + IVA / €1.092,27 IVA incl.

Benchmark distributore UE:

https://asb-drives.eu/equipment/price.php?section=238

- FC-51 2,2 kW T4: €519 indicati dal distributore.

Per budget prudente usare il prezzo Italia finché non esiste RFQ.

## WIKA A-10

Pagina ufficiale / shop:

- https://www.wika.com/it-it/a_10.WIKA
- https://shop.wika.com/it-it/a_10.WIKA

Prezzo ufficiale shop: da €133,95 + IVA/spedizione.

RS Italia 0–10 bar 4–20 mA:

https://it.rs-online.com/web/p/sensori-di-pressione/7255948

- €151,36 + IVA.

## Danfoss MBS 3000

Scheda tecnica:

https://assets.danfoss.com/documents/latest/156949/AI308930736185it-IT0201.pdf

TME Italia, 0–10 bar, 4–20 mA, IP65:

https://www.tme.eu/it/details/060g1125/trasduttori-di-pressione/danfoss/mbs-3000-2011-a1ab04-0/

- €195,44 + IVA per 1 pz osservato.

## Zilmet Ultra-Pro 100 l

Prodotto ufficiale:

https://www.zilmet.it/prodotto/100-litri-ultra-pro-100h/

Dati:

- 100 l;
- Pmax 10 bar;
- precarica 1,5 bar;
- raccordo 1" G;
- membrana intercambiabile.

Listino/catalogo 2026 osservato:

https://www.gaivi.it/listini/zilmet/impiantistica-06/5.html

- ~€474,69 per Ultra-Pro 100 H nella pagina osservata; IVA/condizioni da verificare.

## Interfaccia BOM-014

Per Spin-Klin/ScreenGuard e requisiti di controlavaggio vedere:

`22_FONTI_NORME_PREVENTIVI/ACQUA_FILTRAZIONE_SOURCES.md`.

Il requisito di pressione/portata del controlavaggio deve entrare nel duty point BOM-015.