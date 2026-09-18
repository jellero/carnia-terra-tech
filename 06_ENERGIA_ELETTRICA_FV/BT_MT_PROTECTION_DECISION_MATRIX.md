# BT / MT / protection decision matrix — BOM-034

**Aggiornato:** 18 settembre 2026  
**Stato:** `PRE-DSO DECISION MATRIX`

| Tema | BT | MT | Decisione Carnia |
|---|---|---|---|
| Norma | CEI 0-21:2026-07 | CEI 0-16:2026-07 | da preventivo DSO |
| FV AC working | 100/120 kW | 100/120 kW | confrontare entrambi |
| Cabina MT | no, salvo opere DSO esterne | normalmente sì lato utente/connessione | RFQ solo se MT |
| Trasformatore | no dedicato utente salvo progetto | sì secondo STMG/progetto | DA DSO/RFQ |
| SPI/DDI | secondo CEI 0-21/DSO | secondo CEI 0-16/DSO | DA PROGETTO |
| CCI/PF2 >=100 kW | non assumere CCI MT | gate materiale se FV/eolico >=100 kW e applicabile | quotare opzione MT |
| SLI export limit | possibile secondo CEI/DSO | possibile secondo CEI/DSO | solo se cap richiesto/scelto |
| PCC meter | sì | sì | baseline |
| Ik max/min | DSO | DSO | obbligatorio |
| Selectivity | grid + island | grid + island | obbligatorio |
| BESS island | separazione DSO | separazione DSO | obbligatorio |
| Custom EMS | non protezione | non CCI/protezione | supervisory only |
| CAPEX rete | potenzialmente inferiore | cabina/protezioni/studi maggiori | non stimare prima STMG |
| Espansione 150–180 kWp | verificare margine | verificare STMG/cabina | chiedere envelope futuro |

## Decision tree

1. Il DSO concede BT alla potenza richiesta?
   - sì -> progettare CEI 0-21 e confrontare G100/G120;
   - no -> MT.

2. Il preventivo impone limite export?
   - no -> evitare SLI non necessario;
   - sì -> progettare SLI certificato aggregate PV+BESS.

3. Connessione MT + FV/eolico >=100 kW nel campo applicabile?
   - sì -> CCI/PF2 + comunicazioni + documentazione;
   - no -> motivare e registrare.

4. BESS opera in island?
   - sì -> separazione rete, grid-forming, protezioni island, reconnection e blackout SAT;
   - no -> nessun claim backup.

5. Espansione 150–180 kWp è credibile?
   - sì -> chiedere al DSO/progettista se dimensionare subito cabina/quadri/cavi/meters;
   - no -> non pagare sovradimensionamento senza business case.

## Dati che impediscono la selezione oggi

- lotto;
- DSO;
- POD/tensione se esistente;
- potenza disponibile prelievo;
- potenza richiesta prelievo;
- STMG/preventivo;
- Ik;
- import/export limit;
- 100 vs 120 kW AC;
- espansione reale 150–180 kWp.
