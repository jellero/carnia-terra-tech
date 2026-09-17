# Architettura pulizia galline free-range — BOM-023

**Aggiornato:** 17 settembre 2026
**Stato:** WORKING ARCHITECTURE / ROVER ALL-AREA / TESTATA PRATO R&D / LAYOUT E PILOT BLOCCANTI.

## 1. Vincolo di progetto

Le galline devono poter essere libere, in condizioni ordinarie, nell'intero dominio galline: ricovero, portico, parcheggi/superfici dure rese accessibili, prato/verde e percorsi fra queste aree.

Il sistema di pulizia deve percorrere tutto il dominio accessibile. Il robot sanitario è dedicato a questo dominio e non entra nella serra, nel Tech Barn pulito, nelle celle o nelle aree di confezionamento.

## 2. Perché una sola testata non basta

Le deiezioni cambiano comportamento con superficie e freschezza. Su cemento/asfalto possono essere fresche, aderenti o secche; sul prato sono immerse fra fili d'erba e terreno; su lettiera si mescolano con materiale organico; sotto i posatoi si concentrano in modo ripetitivo.

Una spazzola continua può spalmare una deiezione fresca. Un aspiratore continuo sul prato aspirerebbe anche terra, foglie, insetti e materiale vegetale. La baseline è quindi un solo rover con modalità/testate specifiche.

## 3. Architettura

### CHK-1 — raccolta concentrata nel ricovero

Sotto posatoi e aree di riposo: piano fessurato o piattaforma progettata; nastro deiezioni/scraper coperto; scarico in contenitore chiuso; sensori fine corsa/coppia/inceppamento; accesso manutenzione da zona segregabile.

Big Dutchman SIMBA è un riferimento reale per il principio slat + manure belt, non una selezione già fatta. La letteratura 2026 su pannelli scanalati e robot di rimozione ha misurato circa 88% di rimozione in ambiente sperimentale: utile come prova di fattibilità, non trasferibile automaticamente al prato.

### CHK-2 — rover sanitario all-area

Percorso: ricovero -> portico -> parcheggi/superfici dure -> prato -> dirty dock.

Requisiti: outdoor reale; pioggia/umidità/fango entro specifica; pendenza e soglie; basso rischio di impigliamento; trasmissioni completamente protette; E-stop, bumper e percezione 360°; local compute; mappa/no-go locali; funzionamento degradato senza cloud; teleoperazione/recovery.

### CHK-3 — testata hard-surface

Sequenza: vision rileva deposito -> posizionamento -> squeegee/pickup roller confinato -> aspirazione in hopper sigillato -> eventuale micro-risciacquo a bassa pressione -> immediata estrazione del liquido sporco.

Niente idropulizia aperta con galline presenti e niente aerosolizzazione intenzionale.

### CHK-4 — testata prato

Sul prato niente aspirazione continua. Working R&D: RGB/depth; pickup frontale a pettine morbido/scoop flessibile; aspirazione localizzata; pressione al suolo ridotta; nessun taglio/scavo del cotico; discriminazione di sassi, fauna, foglie e piume; contenitore sigillato.

PetBotics PoopBot è un technology analog pre-commerciale per spot-pickup su prato, ma è pensato per deiezioni canine e non è una soluzione avicola pronta.

### CHK-5 — dirty dock

Dock separato da alimenti e logistica pulita: ricarica, svuotamento hopper, lavaggio ruote/sottoscocca, vasca di raccolta, separazione solidi, wash testata, asciugatura, rifornimento acqua pulita se previsto e gestione greywater.

## 4. Piattaforme candidate

### A — Burro Verde dedicato + testata custom

685 mm, 227 kg payload, indoor/outdoor agricolo, IP65, LiDAR/camere/GPS e navigazione GPS-denied. Prezzo Europa/Italia da preventivo. È il candidato funzionale prioritario perché nasce in ambiente agricolo, ma la macchina integrata richiede validazione completa. Unità dedicata alle galline, mai AMR logistico condiviso.

### B — AgileX Bunker Pro 2.0 + testata custom

Benchmark R&D rugged: 785 mm, 120 kg payload, IP67, 225 kg, LiFePO4 72 V / 50 Ah, circa €22,1k ex VAT benchmark UE. I cingoli e la massa possono danneggiare il prato e aumentare il rischio vicino agli animali: ammissibile solo dopo pilot.

### C — Gausium Beetle 2.0 come benchmark superfici dure

Outdoor/indoor, classe 750 mm, 45 L, 4–8 h, 3D LiDAR, spot cleaning, Full-Scenario Edition IP54; prezzi pubblici circa €15–20k + IVA secondo versione/canale. È forte su portico/parcheggi, ma non è documentato per prato né per manure fresco.

## 5. Sicurezza animale

Requisiti non negoziabili: velocità animal-zone validata; nessun rullo/catena/cingolo/puleggia/punto di schiacciamento esposto; carter inferiori lisci; protezione anti-intrappolamento zampe; pickup head disabilitato se un animale entra nella safety zone; E-stop; soft bumper; nessuna retromarcia cieca; arresto sicuro su perdita percezione.

Uno studio su robot autonomi in pollai ha osservato spostamento degli animali e contatti/spinte leggere. Welfare e habituation vanno quindi provati.

## 6. Free-range, parcheggio e traffico

Le galline sono libere per default, ma durante manovre veicoli si usa separazione temporale:

- FREE_RANGE: accesso aperto;
- VEHICLE_WINDOW: gate chiude temporaneamente il parcheggio alle galline;
- CLEAN_WINDOW: rover pulisce dopo il passaggio dei mezzi;
- REOPEN: area riaperta.

ChickenGuard/Omlet sono benchmark piccoli da circa €110–170; il gate aziendale parcheggio richiede progetto robusto dedicato.

## 7. Interlock con BOM-022 tagliaerba

Il prato è condiviso. Con galline libere il rover sanitario è ammesso e il rasaerba è bloccato. Con galline temporaneamente nel ricovero/settore sicuro il rasaerba può operare se le altre condizioni safety sono soddisfatte. L'obstacle detection non è barriera unica.

## 8. Biosicurezza

Hopper chiuso e lavabile; percorsi sporco/pulito separati; DPI e wash-down per manutenzione; niente rover in aree food; registrazione massa/volume raccolto; manure verso precompost/compost/vermicompost solo dopo validazione agronomica, igienica e normativa; niente scarico greywater incontrollato.

## 9. Failure modes e fallback

Failure: missed detection, false positive, smear, intasamento, hopper full, ruota contaminata, gallina in safety zone, perdita localizzazione, dock irraggiungibile, gate guasto, belt bloccato, perdita greywater, batteria bassa.

Fallback: stop sicuro, head-up, teleoperazione, pulizia manuale spot, isolamento zona, nastro ricovero indipendente dal rover, override manuale gate.

## 10. Pilot obbligatorio

Testare prato, cemento/asfalto, portico e ricovero; depositi freschi/semi-secchi/secchi; galline presenti; vehicle-window; pioggia/umidità compatibile; dock/wash; hopper full; perdita rete/localizzazione; danno prato; stress/contatti animali; almeno 100 missioni autonome senza evento safety non gestito.

KPI: detection rate, pickup primo/secondo passaggio, smear residuo, kg/L raccolti, m²/h, Wh/m², interventi umani/100 missioni, near-miss animali, danno cotico, tempo wash e OPEX consumabili.

## 11. Gate

Prima ordine: numero galline; geometria; superfici; pendenze; quantità manure misurata; quota concentrata sotto posatoi; gate parcheggio; base rover; testata prato; testata hard floor; dirty dock; safety/welfare; manure/greywater destination; CAPEX/OPEX/TCO; conformità macchina integrata.
