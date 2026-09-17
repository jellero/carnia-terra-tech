# Fonti — Accumulo termico, primario PDC e scambiatore

**Aggiornato:** 17 settembre 2026.  
**Regola:** prezzi e disponibilità vanno ricontrollati prima di RFQ/ordine; i dati di catalogo non sostituiscono il dimensionamento termico-idraulico.

## Puffer / accumuli professionali

- Cordivari PUFFER COMPACT, scheda tecnica: https://www.cordivari.it/wp-content/uploads/2023/10/IT-Cordivari_TEC-Scheda-PUFFER-COMPACT_06.2024.pdf — modelli fino a 8.000 l; 5.000 nominale 5.042 l, Pmax 3 bar, Tmax 99 °C; `FORNITORE DA RFQ`.
- Cordivari PUFFER standard: https://www.cordivari.it/wp-content/uploads/2023/10/IT-Cordivari_TEC-Scheda-PUFFER_06.2024.pdf — modello 5.000 l volume netto pubblicato ~4.985 l; `FORNITORE DA RFQ`.

## Serbatoi acqua PE — solo benchmark non equivalente

- ALTA AcquaTec serbatoi fuori terra: https://www.alta.it/promozioni/cisterne-e-serbatoi-in-polietilene/ — promo settembre 2026 IVA esclusa: verticale 10.000 l €1.840, 15.000 l €2.940, 20.000 l €4.740; campo dichiarato circa -40…+60 °C. `BENCHMARK / NON PUFFER`.
- ALTA serbatoi da interro: https://www.alta.it/promozioni/serbatoi-in-polietilene-da-interro/ — prezzi e campo termico della linea da interro; `BENCHMARK / NON PUFFER`.

## Scambiatori

- Sunerg catalogo 2025/2: https://www.sunergsolar.com/media/all_pagina/1_CAT%20ST%202025-2_SH-compressed.pdf — benchmark listino: saldobrasato 60 kW €932; saldobrasato 100 kW €1.252; inox a piastre 100 kW €3.013. `BENCHMARK LISTINO / RICHIEDERE OFFERTA 2026`.

## PDC Kensol

- Senetic DE, KHP-R290-22-3: https://www.senetic.de/product/KHP-R290-22-3 — prezzo osservato 17/09/2026 €3.616,74 + IVA; 22 kW nominali, trifase, R290; trasporto separato.
- Trovaprezzi Italia, ricerca 22 kW: https://www.trovaprezzi.it/prezzo_climatizzazione_pompa_di_calore_22_kw.aspx — Kensol KHP-R290-22-3 osservata ~€4.412,42 IVA inclusa + spedizione; `BENCHMARK RETAIL ITALIA`.

**Open point:** acquisire datasheet/manuale completo Kensol per circolatore integrato, portata minima/nominale, prevalenza residua, capacità e COP alle temperature fredde e W35/W45.

## Pompe primarie

- Idealo, pompe riscaldamento / Grundfos MAGNA3 32-80: https://www.idealo.it/cat/18430F107838763/pompe-per-riscaldamento.html — benchmark osservato da ~€1.149; portata indicata ~10 m³/h, prevalenza max 8 m. `BENCHMARK / DA CURVA Q-H`.

## Glicole propilenico

- Polsinelli, glicole propilenico 25 kg: https://www.polsinelli.it/glicole-anticongelante-atossico-biodegradabile-25-kg-P5387.htm — €122,13 osservati + spedizione; indicazioni diluizione pubblicate 20% ~-9 °C, 30% ~-14 °C. `PREZZO TROVATO / VERIFICARE IDONEITÀ HVAC SPECIFICA`.
- Leroy Merlin marketplace, Antigel atossico 25 kg: https://www.leroymerlin.it/prodotti/antigel-atossico-tanica-25-kg-per-impianto-riscaldamento-raffrescamento-98301148.html — €185,11 IVA inclusa osservati; glicole propilenico inibito per riscaldamento/raffrescamento. `PREZZO TROVATO`.
- GeneralGas catalogo HVACR 2025, Kryon ProGel: https://www.generalgas.it/storage/catalogo/GG-HVACR-Catalogo-2025-ITA.pdf?v=02-2025 — 25 kg listino €210 / promo 2025 €115,50; 200 kg listino €1.520 / promo €836. `BENCHMARK STORICO DI LISTINO`, richiedere prezzo 2026.

## Vasi espansione

- Caleffi 556 ufficiale: https://www.caleffi.com/it-it/vaso-di-espansione-saldato-per-impianti-di-riscaldamento-certificato-ce-556-caleffi-556300 — serie 300–600 l; modello 556500 500 l, Pmax 6 bar, sistema -10…120 °C, max glicole 50%, EN 13831.
- ManoMano, Caleffi 556500 500 l: https://www.manomano.it/p/556500-vaso-despansione-saldato-per-impianti-di-riscaldamento-500-l-caleffi-6302452 — €1.165,20 osservati. `PREZZO TROVATO / TAGLIA NON SELEZIONATA`.

## Regola di progetto

- serbatoio acqua economico ≠ accumulo termico professionale;
- dimensionare energia utile da volume × ΔT, non dal solo volume;
- non glicolare automaticamente l'accumulo completo;
- verificare circolatori integrati PDC prima di aggiungere pompe;
- HX e pompe vanno scelti su temperature, portate, perdite di carico e glicole reali;
- vaso espansione va calcolato, non scelto per analogia;
- richiedere dispersioni reali dell'accumulo e misura della stratificazione.
