# BOM-031 — Sostenibilità personale e modello operativo

**Aggiornato:** 18 settembre 2026  
**Stato:** `WORKING OPERATING MODEL / ORGANICO DA VALIDARE SU VOLUMI REALI / TURNI E COSTO PERSONALE DA CPL UDINE E CONSULENTE PAGHE`.

## 1. Principio

Carnia TerraTech è progettata per essere altamente automatizzata, ma l'automazione deve ridurre il carico umano, non creare una reperibilità permanente.

Regole:

- 24/7 impianto != 24/7 presenza umana;
- notte/festivi vengono assorbiti da PLC, edge, server, BESS e fail-safe locali;
- la persona interviene solo su eventi classificati;
- nessuna funzione critica deve dipendere da una sola persona;
- nessuna persona deve essere permanentemente "on call";
- il fondatore/programmatore non viene conteggiato come manodopera gratuita;
- attività specialistiche rare vengono esternalizzate quando il costo di internalizzazione non è giustificato.

## 2. Obiettivo umano

L'azienda deve poter operare con:

- giornate normali prevedibili;
- picchi raccolta gestibili;
- ferie reali;
- malattia di una persona senza fermo azienda;
- weekend coperti a rotazione;
- reperibilità limitata;
- procedure chiare;
- poche chiamate notturne;
- manutenzione programmata;
- escalation vendor.

KPI umano:

- ore lavorate/FTE;
- overtime;
- chiamate fuori orario;
- P1 notturni;
- ferie utilizzate;
- task arretrati;
- incidenti/near-miss;
- turnover;
- ore manuali per kg;
- ore manutenzione correttiva;
- lavoro ripetitivo eliminato dall'automazione.

## 3. Organico working — scenario L1 lean

### R0 — owner / operations-tech lead

Compiti:

- piattaforma software;
- automazione;
- dati;
- fornitori tecnici;
- investimenti;
- KPI;
- incident review;
- finance/business integration.

Non deve diventare:

- unico reperibile;
- unico che sa riavviare il sistema;
- unico che conosce Stripe/server;
- raccoglitore/packager strutturale quotidiano.

Nel costing il tempo R0 viene registrato.

### R1 — crop & production lead

1 FTE working.

Competenze:

- agronomia serra;
- crop steering;
- fertirrigazione operativa;
- scouting;
- raccolta;
- quality;
- pianificazione settimanale;
- formazione operatori.

Backup:
- almeno un farm operator formato sulle procedure giornaliere;
- agronomo/consulente esterno per escalation.

### R2/R3 — farm operations polyvalent

**2 FTE working target** a regime L1.

Attività:

- raccolta;
- packaging;
- logistica;
- refill;
- pulizie operative;
- ispezioni;
- manutenzione L1;
- task agricoli;
- supporto visitatori/spaccio se pianificato.

Il valore è la polivalenza, non la specializzazione stretta.

### R4 — seasonal / peak pool

**0–3 OTD equivalenti**, attivati dal forecast.

Driver:

- harvest peak;
- trapianti;
- pulizia fine ciclo;
- packaging campaigns;
- eventi/visite;
- eventuale centro trasformazione futuro.

Non usare stagionali come copertura strutturale di una funzione safety-critical.

## 4. Scenario L0 — pre-ramp

Possibile durante commissioning:

- owner/tech lead;
- crop lead;
- 1 farm operator;
- stagionale/fornitore on-demand.

Durata:
- solo ramp-up;
- non sostenibile se l'azienda richiede attività contemporanee su raccolta, pack, manutenzione e visite.

Gate per uscire da L0:
- routine misurate;
- workload < capacità;
- secondo backup operativo formato.

## 5. Scenario L2 — scale

Trigger possibili:

- >80% saturazione stabile di R2/R3;
- overtime ripetuto;
- ferie difficili da concedere;
- packaging/raccolta simultanei;
- fattoria didattica frequente;
- spaccio/refill in crescita;
- manutenzione preventiva arretrata.

Azione:
- aggiungere 1 FTE polyvalent o specialista, non compensare con overtime permanente.

Working:
- crop lead 1;
- farm ops 3;
- owner/tech;
- OTD peaks.

## 6. BOM-029 transformation staffing

Il centro trasformazione non viene assorbito gratuitamente dall'organico L1.

Quando attivo:

- 2 operatori minimi nei process days;
- 3 nei picchi/pack;
- ruolo QC/HACCP;
- cleaning/CIP;
- ricezione clienti.

Opzioni:

- personale dedicato stagionale;
- turni pianificati di farm ops solo se workload agricolo lo consente;
- operatore food dedicato quando la frequenza supera il threshold economico.

Il server deve impedire double-booking di una persona su serra e process line.

## 7. Orario di lavoro

Il CCNL operai agricoli/florovivaisti usa come riferimento ordinario **39 ore settimanali**.

Il calendario reale deve essere costruito con:

- CCNL 2026–2029;
- CPL provincia competente;
- riposi;
- ferie;
- lavoro domenicale/festivo;
- straordinari;
- eventuali flessibilità territoriali.

Working preferred:

- settimana 5 giorni per core staff quando compatibile;
- weekend duty ruotata;
- nessun "sempre raggiungibile".

Il sistema produce il piano, ma payroll/consulente del lavoro valida il turno contrattuale.

## 8. Copertura 7/7

La serra richiede sorveglianza 7/7, non necessariamente un turno pieno 7/7.

Weekend baseline:

- remote health check automatizzato;
- physical round breve pianificato se agronomicamente richiesto;
- raccolta solo se crop plan lo richiede;
- alert-driven intervention;
- operator duty ruotato.

Il weekend non deve trasformarsi in un secondo turno quotidiano non contabilizzato.

## 9. Reperibilità

### P1 — emergenza reale

Esempi:

- perdita acqua importante;
- gelo/clima fuori fail-safe;
- cold-chain critica;
- electrical/BESS fault rilevante;
- safety/security;
- failure con rischio coltura immediato.

Richiede:
- ack remoto rapido;
- escalation automatica;
- eventuale intervento onsite.

### P2 — operativo urgente

Esempi:

- pompa secondaria;
- AMR down con fallback manuale;
- vending issue;
- sensore critico degradato ma ridondato.

Gestibile:
- orario esteso;
- next operational window.

### P3 — non urgente

Esempi:

- dashboard;
- report;
- forecast;
- camera non critica;
- analytics.

Solo orario lavorativo.

## 10. Rotazione reperibilità

Target sostenibile:

- almeno 3 persone/risorse in rotazione per P1 dove realisticamente possibile;
- oppure 2 interni + vendor contrattualizzato.

Evitare:
- 1 persona 365 giorni/anno;
- owner sempre L3+L2+L1;
- reperibilità informale senza confini.

Working:
- 1 settimana duty;
- almeno 2 settimane senza duty se il team lo consente.

Durante L0:
- rotazione 1-in-2 solo temporanea;
- vendor backup obbligatorio.

## 11. Escalation chain

Pattern:

`automation -> duty operator -> second internal -> specialist/vendor -> owner/decision authority`

Non:

`automation -> owner for everything`.

Ogni alert ha:

- severity;
- owner role;
- runbook;
- maximum retry;
- vendor;
- fallback;
- escalation timer.

## 12. Skill redundancy

Ogni funzione critica deve avere:

- primary;
- internal backup;
- external backup o documented fallback.

Critiche:

- fertigation;
- greenhouse climate;
- water pumps;
- cold rooms;
- BESS/electrical reset permitted;
- server restart/recovery;
- Stripe/store closure;
- fire/first aid;
- AMR safe stop;
- animal care;
- food hold/release if BOM-029 active.

## 13. Cosa internalizzare

### L1 internal

- visual inspection;
- filters;
- cleaning;
- hose/connector replacement;
- sensor swap;
- basic calibration checks;
- backup/restore routine;
- restart documented;
- belts/blades/basic consumables;
- lubrication;
- inventory/spares.

### L2 hybrid

- pump seals;
- dosing pumps;
- refrigeration diagnostics;
- PLC I/O replacement;
- network hardware;
- drives;
- advanced calibration.

### L3 external

- refrigerant circuit;
- HV/electrical work requiring qualification;
- inverter/BESS internal service;
- structural;
- certified metrology;
- statutory inspections;
- specialist safety;
- medical surveillance;
- complex machinery warranty work.

## 14. External contracts baseline

Request annual agreements / response pricing for:

- refrigeration;
- electrician;
- pumps/fertigation;
- greenhouse/climate;
- BESS/inverter;
- AMR/robotics;
- lifting equipment;
- metrology;
- occupational safety/RSPP support if external;
- occupational physician where required;
- payroll/labour consultant;
- food/HACCP specialist when BOM-029 active.

No generic "call someone when it breaks".

## 15. Vacation resilience

Gate:

A role is not sustainable until the primary can take **10 consecutive working days away** without unsafe or chaotic operation.

Before vacation:

- handover;
- current exceptions;
- scheduled jobs;
- vendor contacts;
- pending alarms;
- forecast;
- credentials available to authorized backup.

No password or operational knowledge may exist only in one person's head.

## 16. Sick-day resilience

Test:

At 06:00 one core operator is unavailable for 5 days.

System must:

1. replan;
2. defer P3 work;
3. preserve crop/animal/food-critical work;
4. activate seasonal/backup if threshold exceeded;
5. not force remaining people into indefinite overtime.

## 17. Training baseline

Training includes:

- safety according current D.Lgs. 81/2008 / Agreement State-Regions 2025;
- role-specific equipment;
- SOP;
- digital system;
- hygiene;
- first aid/fire roles;
- manual fallback;
- incident reporting.

The 2025 agreement establishes risk-class training durations and specific preposto requirements.

Training is a scheduled task, not "shadow someone until you know it".

## 18. Safety training planning

Worker training:
- general + specific according actual risk assessment.

Current Agreement 2025:
- low risk total 8 h;
- medium 12 h;
- high 16 h.

Agricultural/production role must be classified using the actual ATECO/risk and DVR; do not assume low-risk office training.

Preposto:
- separate training;
- current rules restrict e-learning for the preposto course/updates; use permitted delivery modes.

Add equipment-specific training when required.

## 19. Heat/weather

Greenhouse/outdoor schedules need:

- heat exposure procedure;
- hydration;
- breaks;
- task rescheduling;
- alerts;
- summer early-shift option;
- stop-work threshold from DVR/protocol.

Server scheduler must treat severe heat/weather as a hard constraint where required, not a productivity suggestion.

## 20. Hiring strategy

Labour market FVG is not assumed abundant.

Excelsior 2026 shows:

- regional difficulty of recruitment around half of planned entries in several monthly surveys;
- specialized food-processing workers particularly difficult in May 2026;
- agricultural/manual roles also show nontrivial recruitment difficulty.

Strategy:

- hire core roles early;
- cross-train;
- maintain seasonal pool;
- use referrals/agricultural schools;
- publish predictable schedules;
- invest in tools/automation;
- avoid "hero culture".

## 21. Compensation rule

Do not budget from national minimum alone.

Actual payroll basis:

`CCNL + CPL Udine/province applicable + level/profile + fixed elements + 13th + 14th + contributions + TFR + bilateral + overtime/festive + welfare + PPE/training/medical`.

The provincial contract is economically decisive.

EBAF Udine states that farms with labour in the province applying the national contract are also required to apply the provincial contract and bilateral contributions.

## 22. 2026 wage floor reference

Current national minimum area from 1 June 2026:

- Area 1: €1.532,999/month;
- Area 2: €1.398,093/month;
- Area 3: €1.042,434/month.

These are **national minimums**, not Carnia TerraTech salary offers.

The 2026 renewal increased provincial contractual salaries by 3.4% from 1 June 2026; another 1.7% applies from 1 January 2027.

## 23. Employer contributions

INPS 2026 for general agricultural employers reports, in the detailed OTI table, total employer contributions of **33,953%**; agricultural undertakings with industrial-type production processes show **35,753%**.

Worker pension share is separately shown as 8,84%.

Use actual classification/payroll calculation.

Do not apply one percentage blindly to owner, employees, food-processing staff or different contractual categories.

## 24. Cost-floor illustration

Using national minimum only, 14 monthly payments, 33,953% employer contribution and a simple TFR accrual approximation:

- Area 1: ~€30,3k/year employer floor;
- Area 2: ~€27,7k/year;
- Area 3: ~€20,6k/year.

**These are not budget salaries.**

Excluded:
- provincial contractual wage above national minimum;
- EBAF/bilateral;
- overtime/festive;
- leave replacement;
- welfare;
- payroll service;
- PPE;
- medical surveillance;
- training;
- bonuses;
- travel;
- meal/accommodation;
- recruitment.

Use only as a sanity-check lower bound.

## 25. Staffing trigger metrics

Add headcount when for 8 rolling weeks one or more occur:

- planned utilization >85%;
- overtime >5–8% of scheduled hours;
- PM completion <95%;
- holidays repeatedly deferred;
- >2 P1 calls/person/month;
- harvest/pack lateness;
- cleaning backlog;
- quality escape related to workload;
- owner manual ops > agreed ceiling.

Exact thresholds can be tuned after 90 days.

## 26. Automation trigger

Automate a task when:

`annual manual hours × loaded hourly cost + ergonomic/risk cost > automation TCO`

and automation does not create disproportionate maintenance complexity.

High-value candidates:

- data entry;
- scheduling;
- stock counting;
- refill prediction;
- repetitive transport;
- irrigation;
- monitoring;
- alerts;
- traceability.

Low-value automation:
- rare tasks already done in 5 minutes/month.

## 27. Meeting cadence

### Daily
10-minute operations review:
- exceptions;
- weather;
- harvest;
- maintenance;
- visitors;
- staffing.

### Weekly
45–60 min:
- crop;
- orders;
- forecast;
- maintenance;
- next week workload.

### Monthly
- KPI;
- P1 incidents;
- overtime;
- holidays;
- training;
- automation opportunities.

### Quarterly
- role/load review;
- vendor SLA;
- compensation/retention;
- DR/emergency exercise.

## 28. SOP hierarchy

P0 SOP:
- emergency;
- fire;
- injury;
- power/BESS;
- flood/leak;
- cold-chain;
- greenhouse climate failure.

P1:
- irrigation/fertigation;
- harvest/pack;
- animal care;
- store close;
- server failover.

P2:
- routine maintenance;
- cleaning;
- inventory;
- refill;
- visitor setup.

Each SOP:

- owner;
- backup;
- trigger;
- steps;
- stop conditions;
- escalation;
- evidence/log.

## 29. Human override

Automation can recommend and execute within guardrails.

Humans can override with:

- identity;
- reason;
- expiry;
- audit.

No permanent undocumented override.

## 30. Burnout guardrails

- no permanent 24/7 owner duty;
- no regular double shift;
- no repeated cancelled holiday because "only X knows it";
- no overnight P2/P3 alerts;
- alarm deduplication;
- alert budget;
- scheduled maintenance windows;
- maximum planned workload below 100%;
- capacity reserve for failures.

## 31. Success criterion

The farm is operationally sustainable when:

1. two-week owner absence is possible;
2. one operator sick for a week is manageable;
3. one compute node can fail;
4. one major machine can fail with documented fallback;
5. night P1 frequency is low and measured;
6. holidays are taken;
7. PM is completed;
8. overtime is episodic, not structural;
9. critical skills have backup;
10. process knowledge is documented.

## 32. Linked documents

- `14_ORGANIZZAZIONE_DEL_LAVORO/WORKFORCE_SKILL_MATRIX.md`;
- `17_SOSTENIBILITA_PERSONALE_E_LANCIO/LAUNCH_RAMP_UP_30_60_90_180.md`;
- `17_SOSTENIBILITA_PERSONALE_E_LANCIO/RFQ_SERVIZI_OPERATIVI_MANUTENZIONE.md`;
- `19_BOM_PRODOTTI_FORNITORI/ORGANIZZAZIONE_PERSONALE_LANCIO.md`;
- `22_FONTI_NORME_PREVENTIVI/ORGANIZZAZIONE_PERSONALE_LANCIO_SOURCES.md`.
