# Launch ramp-up 30 / 60 / 90 / 180 giorni — BOM-031

**Aggiornato:** 18 settembre 2026  
**Stato:** `WORKING LAUNCH PLAN / DATE REALI DA MASTER CRONOPROGRAMMA`.

## 1. Regola

Il go-live non è un interruttore.

Ogni fase aumenta autonomia soltanto dopo evidenza:

- procedure;
- training;
- KPI;
- incidenti;
- backup;
- manutenzione;
- dati.

No scaling per calendario se i gate non sono passati.

## 2. D-90 → D-60 — preparazione persone

Obiettivi:

- nominare R0/R1;
- selezionare primo farm operator;
- mappare skill gap;
- identificare vendor critici;
- impostare consulente lavoro/paghe;
- definire CCNL/CPL/inquadramenti;
- DVR e piano formazione;
- creare SOP skeleton.

Deliverable:

- organigramma;
- skill matrix v0;
- vendor contact list;
- training plan;
- PPE plan;
- payroll setup;
- on-call concept;
- emergency contacts.

Gate:
- nessuna assunzione senza job scope;
- nessun ruolo critico senza backup plan.

## 3. D-60 → D-30 — training e shadow commissioning

Persone partecipano ai SAT/commissioning di:

- serra;
- irrigazione;
- clima;
- celle;
- BESS;
- server;
- AMR;
- packaging;
- spaccio.

Regola:
- chi opererà l'impianto deve vedere anche come fallisce.

Training:

- safety;
- normal ops;
- manual fallback;
- alarm;
- LOTO/authorized boundaries;
- first aid/fire roles;
- hygiene/traceability.

Output:
- sign-off per skill;
- open gaps;
- runbook corrections.

## 4. D-30 → D0 — simulation mode

Eseguire simulazioni senza produzione piena:

- pump fault;
- sensor fail;
- Internet down;
- server node down;
- BESS transition;
- cold-room alarm;
- AMR blocked;
- missing worker;
- store payment fault;
- traceability recall.

Operations team lavora già con:
- task system;
- shift handover;
- incident log;
- maintenance work order.

Go-live gate:
- P0 SOP complete;
- two-person redundancy on critical daily operations;
- external SLA contacts active;
- no unresolved critical safety issue.

## 5. Giorni 0–30 — manual visibility, low automation authority

Principio:

**automatizzare il monitoraggio prima della decisione automatica.**

Server:
- collects;
- alerts;
- suggests;
- logs.

Humans:
- approve major schedules;
- verify irrigation;
- verify harvest;
- verify stock;
- verify payment/retail;
- verify maintenance.

Automation:
- only mature control loops;
- no aggressive optimization.

Staffing:
- L0 allowed;
- owner/tech present more than future steady state;
- vendors close to commissioning.

KPI daily:
- alarm count;
- false alarm;
- task completion;
- manual hours;
- downtime;
- quality;
- water/energy;
- inventory error.

Gate day 30:
- no recurring critical unknown fault;
- top 20 manual routines documented;
- alarm noise reduced.

## 6. Giorni 31–60 — controlled automation

Enable:

- automatic task generation;
- refill prediction;
- maintenance reminders;
- schedule suggestions;
- standard AMR missions;
- automatic data reconciliation.

Still approval-required:
- high-impact fertigation changes;
- price changes;
- unusual load shedding;
- food hold/release;
- destructive maintenance.

People:
- R2/R3 operate more independently;
- R0 removes itself from routine physical tasks.

Measure:
- owner interventions/day;
- manual fallback;
- workload;
- overtime;
- P1/P2 alarms.

Gate day 60:
- owner routine ops declining;
- farm can run 2 consecutive days without owner onsite;
- first holiday-cover dry run.

## 7. Giorni 61–90 — stable lean operations

Goal:
- move from commissioning mentality to repeatable operations.

Enable:

- scheduler auto-dispatch within guardrails;
- demand forecast into refill;
- supply forecast into harvest plan;
- maintenance prioritization;
- BESS-aware deferment.

Run drills:
- R0 absent 3 days;
- R1 absent 2 days;
- R2/R3 one sick-day scenario.

Staff decision:
- compare real workload to L1 capacity.

Add FTE only if:
- workload is structurally high;
- not because of unresolved bad process.

Gate day 90:
- PM >=95%;
- holiday plan possible;
- overtime non-structural;
- task aging controlled;
- no single-person daily critical dependency.

## 8. Giorni 91–180 — optimization

Focus:

- remove repeated manual data entry;
- tune forecast;
- optimize harvest/pack;
- reduce walking/handling;
- improve refill;
- vendor SLA review;
- spare optimization.

Automation candidates scored by:

- hours saved;
- ergonomic risk;
- error reduction;
- maintenance burden;
- CAPEX/TCO.

People:
- cross-training complete;
- seasonal pool identified before next peak;
- rota sustainable.

## 9. Day 180 sustainability review

Questions:

### Human
- Are holidays actually being taken?
- Who was called at night?
- How often?
- Is founder still routine bottleneck?
- Is one role overloaded?

### Process
- What tasks exceed planned duration?
- What repeatedly fails?
- What can be standardized?

### Technology
- Which automation saves real time?
- Which automation generates support burden?
- Which alerts are useless?

### Economic
- loaded labor €/kg;
- overtime;
- vendor spend;
- maintenance;
- temporary labor.

Decision:
- stay L1;
- add FTE;
- outsource;
- automate;
- reduce service scope.

## 10. Ramp-up staffing working

### D-90 to D0
- R0;
- R1;
- R2;
- vendor engineers.

### Day 0–30
- R0 high presence;
- R1;
- R2;
- R3 onboard/training if not already;
- seasonal only if production requires.

### Day 31–90
- L1 target:
  - R1 1 FTE;
  - R2/R3 2 FTE;
  - R0 technical/operations lead, increasingly non-manual;
  - seasonal pool.

### Day 91–180
- decide L1 vs L2 from measured data.

## 11. Ramp-up rule for BOM-027 visitors

Do not open full educational-farm schedule during core commissioning.

Sequence:

1. internal tour;
2. invited small group;
3. one scheduled group;
4. only then recurring visits.

Visitor events must not hide production workload problems.

## 12. Ramp-up rule for BOM-028 store

Phases:

1. staff test;
2. invited customers;
3. limited hours;
4. unattended day;
5. unattended extended;
6. 24/7 only after payment/security/cold-chain incidents are understood.

Frictionless smart cart:
- later pilot;
- not required for basic shop go-live.

## 13. Ramp-up rule for BOM-029 transformation

BOM-029 remains future.

If activated:
- separate commissioning;
- separate workload capacity;
- no assumption that current farm team can absorb it.

## 14. Alarm budget

During commissioning it is normal to have noise.

By day 90:

- each P1 is truly actionable;
- no repeated false P1;
- P2 aggregated where possible;
- P3 silent outside work hours.

Target:
- P1 rare enough that duty rotation is sustainable.

## 15. Change freeze windows

No risky release:

- before major harvest;
- before holiday closure;
- before visitor event;
- before weekend unless rollback/support exists.

Infrastructure:
- maintenance windows planned;
- rollback tested.

## 16. Handover format

Every shift/day handover includes only exceptions:

- crop issue;
- alarm;
- machine out;
- lot hold;
- task overdue;
- visitor/event;
- vendor visit.

Do not require reading a narrative diary.

Server generates current state summary.

## 17. First 180-day KPI table

| KPI | Day 30 | Day 60 | Day 90 | Day 180 |
|---|---|---|---|---|
| PM completion | baseline | >90% | >=95% | >=95% |
| inventory accuracy | measure | improve | target | stable |
| owner routine interventions | measure | down | low | exception |
| overtime | measure | trend | episodic | episodic |
| P1 alarms | tune | down | low | low |
| task on-time | measure | improve | stable | stable |
| forecast error | baseline | baseline | usable | improving |
| holiday coverage | design | dry run | possible | demonstrated |
| sick-day resilience | design | test | pass | pass |

Numerical product KPI targets remain domain-specific.

## 18. Stop conditions

Pause scaling when:

- safety incident pattern;
- >2 weeks structural overtime;
- PM backlog;
- unresolved traceability;
- repeated P1 alarms;
- staff cannot take rest;
- quality worsening;
- owner remains single point of failure.

Fix process before adding complexity.
