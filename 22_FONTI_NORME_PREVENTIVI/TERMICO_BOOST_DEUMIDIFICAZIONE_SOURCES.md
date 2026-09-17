# Fonti — Boost, deumidificazione ed emergenza

**Aggiornato:** 17 settembre 2026.  
**Regola:** prezzi e prestazioni vanno riconfermati prima di RFQ/ordine; distinguere dati produttore, retail e letteratura.

## Aerotermi agricoli

- Reventon FARMER Series: https://reventongroup.eu/en/lphw-unit-heaters/farmer-series/ — serre incluse tra le applicazioni, coil GOLD epoxy, HCF IP54/IP66, OpenAir IP66.
- Reventon FARMER HCF: https://reventongroup.eu/en/lphw-unit-heaters/farmer-series/lphw-unit-heater-farmer-hcf/ — 3,87–66,2 kW range pubblicato, max 5.000 m³/h, dati motori/IP.
- TDS FARMER HCF con tabelle 80/60, 70/50, 50/40, 40/30: https://www.vpsindustrialheating.co.uk/wp-content/uploads/2025/11/farmerhcf.pdf — riferimento principale per resa a bassa temperatura.
- Reventon Italia OpenAir: https://reventongroup.it/prodotto/aerotermo-ad-acqua-della-serie-farmer-openair/ — contatto/documentazione Italia.

## Prezzi aerotermi — benchmark retail

- Profi-Bau-Shop, HCF IP54-EC HCFE-50EC-2534: https://www.profi-bau-shop.de/heizen-und-lueften/shop/heizen-und-lueften/heizung/warmwasser-luftheizer/wasser-lufterhitzer-farmer-hcf-ip54-ec-detail — €901 IVA 19% inclusa osservati 17/09/2026; `PREZZO TROVATO / RETAIL DE`.
- Wolf Online Shop, HCF IP66 WHHCF53-1527: https://www.wolf-online-shop.de/Reventon-Farmer-HCF-IP66-Wasser-Lufterhitzer-50-2kW-230V%3A%3A335928.html — circa €822,17 IVA 19% incl. osservati; `PREZZO TROVATO / RETAIL DE`.
- Climatik, collezione Reventon: https://climatik.pro/collections/reventon — Farmer HCF IP66 circa €943 TTC osservati; `PREZZO TROVATO / RETAIL FR`.
- Kältetechnikshop HCF IP66: https://www.kaeltetechnikshop.com/reventon-wasser-lufterhitzer-serie-farmer-230v-ac-farmer-hcf-ip66-50-2kw-heizleistung-90-700c-wassertemperatur-00c-raumtemperatur — accessori pubblici: flessibili 3/4" ~€88,71 incl.; HMI SINGLE BMS ~€137,64; relay RM-16A ~€73,98; `BENCHMARK ACCESSORI`.

## Deumidificazione greenhouse — letteratura

- Wageningen, Dehumidification of greenhouses: https://research.wur.nl/en/publications/dehumidification-of-greenhouses/ — confronto economico/pratico/energetico; ventilazione meccanica con recupero indicata come soluzione efficace/competitiva nel contesto studiato.
- Wageningen, Dehumidification of Greenhouses at Northern Latitudes: https://research.wur.nl/en/publications/dehumidification-of-greenhouses-at-northern-latitudes/ — confronto ventilazione, superficie fredda, recupero, sistemi igroscopici.
- Wageningen, Energy conserving dehumidification: https://research.wur.nl/en/publications/energy-conserving-dehumidification-of-greenhouses/ — recupero del calore sensibile/latente e trade-off energetici.
- Wageningen, finned pipes condensation: https://research.wur.nl/en/publications/dehumidification-in-greenhouses-by-condensation-on-finned-pipes/ — riferimento sperimentale storico sulla condensazione interna.

## Ventilazione meccanica con recupero

- AIRGAIA EXT'air / SIVAL 2025: https://www.sival-innovation.com/en/extair/ — sistema dual-flow greenhouse con recupero; claim produttore/innovazione da verificare in RFQ alle condizioni reali; `PREZZO DA PREVENTIVO`.

## Deumidificatori horticulture

- DryGair DG-3 50 Hz: https://drygair.com/dehumidifiers/dg-3-50hz/ — 11 l/h @18°C 80% RH, ~4.500 m³/h, 2,3 kW, 10–35°C, ~300 kg, R513A; `PREZZO DA PREVENTIVO`.
- DryGair DG-12 50 Hz: https://drygair.com/dehumidifiers/dg-12-50hz-standard/ — 43 l/h @18°C 80% RH, ~20.000 m³/h, 9,55 kW, 10–35°C, ~770 kg; `PREZZO DA PREVENTIVO`.
- DryGair DG-6 Heating & Cooling: https://drygair.com/dehumidifiers/dg-6-eu-heating-cooling/ — 25 l/h @18°C 80% RH, 6,5 kW, hot-water integration; riferimento se si valuta una macchina combinata.
- Hortispares dehumidifier parts: https://www.hortispares.com/product-category/climate-control/air-treatment/dehumidifier/ — disponibilità ricambi DryGair e prezzi pubblici di vari componenti; utile per TCO/manutenzione.

## Nota prezzo storico DryGair

- CORDIS progetto Drygair20: https://cordis.europa.eu/project/id/729874 — indicava nel 2016 un prezzo finale target ~€22.000. È `BENCHMARK STORICO 2016 / NON PREZZO ATTUALE` e non va usato nel CAPEX 2026.

## Regola tecnica

Un aerotermo che alza la temperatura abbassa l'UR ma non rimuove massa d'acqua. La deumidificazione va contabilizzata in kg/h o l/h di acqua rimossa e kWh consumati, usando condizioni T/RH reali.
