# Workforce skill matrix — BOM-031

**Aggiornato:** 18 settembre 2026  
**Stato:** `WORKING MATRIX / NOMINATIVI, LIVELLI E FORMAZIONE DA ASSEGNARE`.

## 1. Regola

Ogni competenza critica deve avere:

- P = primary;
- B = backup interno;
- E = escalation esterna;
- F = fallback documentato.

Nessuna riga critica può avere solo P.

## 2. Ruoli working

| Codice | Ruolo |
|---|---|
| R0 | owner / operations-tech lead |
| R1 | crop & production lead |
| R2 | farm operations polyvalent A |
| R3 | farm operations polyvalent B |
| R4 | seasonal/peak operator pool |
| EXT-A | agronomy specialist |
| EXT-E | electrician/BESS |
| EXT-R | refrigeration |
| EXT-W | water/fertigation |
| EXT-M | machinery/AMR/lifting |
| EXT-S | safety/RSPP/medical |
| EXT-F | food/HACCP/metrology |
| EXT-P | payroll/labour consultant |

## 3. Matrix

| Competenza | R0 | R1 | R2 | R3 | R4 | Esterno/Fallback |
|---|---|---|---|---|---|---|
| crop plan | B | P | B | B | - | EXT-A |
| scouting agronomico | B | P | B | B | - | EXT-A |
| irrigation daily ops | B | P | B | B | - | EXT-W |
| fertigation recipe execution | B | P | B | B | - | EXT-A/EXT-W |
| fertigation recipe design | B | P | - | - | - | EXT-A |
| greenhouse climate normal | B | P | B | B | - | vendor |
| greenhouse climate emergency | B | P | B | B | - | vendor |
| harvest | B | P | P | P | P | defer/replan |
| packaging | B | B | P | P | P | temporary labour |
| quality grading | B | P | P | B | B trained | customer/spec |
| lot/traceability | P | B | P | P | B | manual log fallback |
| cold-room normal ops | B | B | P | P | B | EXT-R |
| cold-room technical fault | B | - | B | B | - | EXT-R |
| smart retail refill | P | B | P | P | B | manual close/fallback |
| Stripe/order recovery | P | B trained | B trained | - | - | Stripe support/runbook |
| server service recovery | P | B trained | - | - | - | documented bare-metal/DR |
| server hardware swap | P | B trained | - | - | - | IT supplier |
| BESS status/operator checks | B | B | B | B | - | EXT-E |
| electrical fault diagnostics | - | - | visual only | visual only | - | EXT-E |
| pump/filter L1 maintenance | B | B | P | P | - | EXT-W |
| pump technical repair | - | B | B | B | - | EXT-W |
| AMR safe stop/restart | P | B | P | P | - | EXT-M |
| lifting equipment operator | B if trained | B if trained | P if trained | P if trained | only trained | EXT-M |
| chicken care | B | B | P | P | B trained | vet/service |
| visitor mode | P | P | B | B | - | close visit |
| first aid | trained backup | trained | trained | trained | optional | emergency service |
| fire/emergency | trained | trained | trained | trained | briefed | emergency service |
| HACCP release | B | B | trained if assigned | trained if assigned | - | EXT-F |
| BOM-029 line process | B | B | P if assigned | P if assigned | P trained | EXT-F/vendor |
| CIP | B | B | P | P | P trained | EXT-F/vendor |
| metrology legal | - | - | basic checks | basic checks | - | EXT-F |
| payroll/time approval | P | - | - | - | - | EXT-P |
| safety documentation | B | B/preposto if assigned | worker | worker | worker | EXT-S |

## 4. Critical minimum redundancy

Before full go-live:

### Must have 2 internal trained persons

- greenhouse emergency;
- irrigation/fertigation safe mode;
- cold-room hold procedure;
- lot traceability;
- BESS basic status;
- AMR safe stop;
- first-aid/fire roles according DVR;
- smart retail close/manual fallback.

### May be 1 internal + external SLA

- refrigeration repair;
- electrical repair;
- BESS internal service;
- advanced pump repair;
- structural/mechanical certified work;
- legal metrology;
- occupational medicine;
- advanced food validation.

### Must not depend only on R0

- server restart;
- retail close;
- Stripe incident recognition;
- access to emergency credentials;
- network recovery basic;
- alarm acknowledgement.

## 5. Training levels

### T0 — awareness
Can recognize hazard/state and call correct escalation.

### T1 — normal operator
Can execute standard SOP.

### T2 — advanced operator
Can troubleshoot within authorized boundaries.

### T3 — specialist
Requires professional qualification/vendor competence/certification.

Rule:
- do not turn a T1 into T3 by writing a longer SOP.

## 6. Authorization matrix

System permissions follow skill, not job title alone.

Examples:

### Fertigation
- R1: recipe edit + approve;
- R2/R3: execute approved recipe;
- R0: emergency administrative access but changes audited.

### Stripe
- R0: admin/reconciliation;
- R1 or trained backup: store close/refund limited;
- farm ops: customer support workflow without unrestricted financial permissions.

### BESS
- operators: view/ack;
- R0/R1: operational mode request within documented scope;
- vendor/electrician: protected technical service.

### Food release
- only assigned qualified/authorized role.

## 7. Password/credential resilience

No credential only known by one person.

Use:

- password manager/secrets system;
- break-glass account;
- dual-control recovery;
- documented access owner;
- quarterly access review.

No shared personal passwords.

## 8. Holiday coverage test

For each role ask:

> Can this person be absent for 10 working days?

If no:

- train backup;
- simplify system;
- outsource;
- defer noncritical service.

The answer "owner will cover it" does not close the gap if owner already covers multiple critical domains.

## 9. Seasonal pool profile

Seasonal operators should be pre-qualified before peak.

Maintain:

- contact;
- previous training;
- tasks permitted;
- PPE size;
- language;
- availability;
- performance notes;
- re-training expiry.

Priority seasonal tasks:

- harvest;
- pack;
- transplant;
- cleaning;
- handling.

Do not assign untrained seasonal staff to:

- chemicals;
- complex equipment;
- electrical;
- autonomous machinery service;
- food release.

## 10. Preposto

Where organization requires one or more preposti:

- identify by actual supervisory function;
- train under current rules;
- record appointment/role as applicable;
- ensure authority to stop unsafe work.

Do not nominate a preposto only on paper.

## 11. Owner absence drill

At least annually:

- R0 unavailable 5 working days in simulation;
- no privileged intervention except emergency;
- backups operate system;
- collect blocked actions;
- fix knowledge/authorization gaps.

Target:
- no P0/P1 process blocked because "only owner can do it".

## 12. Review cadence

Update matrix:

- new employee;
- new machine;
- software release changing permissions;
- incident;
- annual review;
- before planned long absence.

Version controlled in repository; personal/sensitive details kept in restricted HR system, not public Git.
