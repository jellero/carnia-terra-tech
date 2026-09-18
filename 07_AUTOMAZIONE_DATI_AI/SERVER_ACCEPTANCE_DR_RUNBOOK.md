# BOM-030 — Server acceptance, failover e disaster recovery runbook

**Aggiornato:** 18 settembre 2026  
**Stato:** `RUNBOOK BASELINE / DA ESEGUIRE IN COMMISSIONING E POI PERIODICAMENTE`.

## 1. Obiettivo

Dimostrare che:

- un guasto server non rende unsafe gli impianti;
- ordini/pagamenti non vengono duplicati;
- gli eventi non vengono persi silenziosamente;
- i dati possono essere ripristinati;
- il BESS sostiene realmente il control plane;
- il personale sa cosa fare durante un incidente.

## 2. Priorità servizi

### P0 — safety/control visibility
- network core;
- edge ingress;
- asset health;
- identity admin path;
- DB/event core.

### P1 — business critical
- inventory;
- lots;
- orders;
- Stripe/payment;
- retail exit;
- cold-chain event logging.

### P2 — operations
- scheduler;
- task dispatch;
- maintenance;
- dashboards.

### P3 — deferrable
- forecast training;
- analytics;
- bulk reports;
- historical reprocessing.

## 3. SLO working

| Servizio | Availability | RPO | RTO |
|---|---:|---:|---:|
| payment/order | 99.9% | 0–5 s | <2–5 min |
| lot/inventory | 99.9% | <30 s | <5 min |
| scheduler | 99.5% | <1 min | <5 min |
| edge ingress | 99.5% | local buffer | <10 min |
| dashboards | 99% | n/a | <15 min |
| forecast/analytics | 95% | <24 h | <4 h |

## 4. Backup classes

### B1 — PostgreSQL
- replica;
- daily base backup;
- continuous WAL;
- retention;
- offsite.

### B2 — VM/LXC
- Proxmox Backup Server;
- daily/weekly/monthly.

### B3 — files/images
- snapshot;
- checksum;
- offsite encrypted copy.

### B4 — configuration
- Git;
- encrypted secrets recovery;
- device config export.

## 5. Minimum retention working

VM:
- 7 daily;
- 4 weekly;
- 6 monthly.

DB:
- WAL sufficient for PITR across retention;
- daily base;
- monthly archive.

Critical config:
- indefinite Git history where reasonable.

Adjust after real data growth.

## 6. Daily checks

Automated:

- NODE-A/B health;
- QNODE health;
- PostgreSQL replica lag;
- WAL archive age;
- NATS cluster;
- disk SMART;
- ZFS/RAID status;
- backup success;
- backup verification;
- offsite copy age;
- certificate expiry;
- BESS power status;
- clock offset;
- Internet/cloud integration.

Any failed backup older than one planned interval = alert.

## 7. Weekly checks

- restore one small file;
- verify backup datastore;
- check storage growth;
- review failed jobs;
- check NATS under-replicated streams;
- review admin audit;
- review pending updates;
- verify qdevice/quorum.

## 8. Monthly checks

- restore one VM to isolated network;
- PostgreSQL test restore;
- rotate/test selected secret;
- edge buffer test;
- verify offsite object readability;
- review firewall/VLAN changes;
- update asset inventory.

## 9. Quarterly drill

Execute one scenario:

- compute node loss;
- DB primary loss;
- Internet loss;
- backup failure;
- Stripe outage simulation;
- edge gateway isolation.

Record:
- actual RTO;
- actual RPO;
- operator actions;
- unexpected dependencies;
- corrective work order.

## 10. Annual full DR drill

Assume both compute nodes unavailable.

Required:
1. replacement/temporary compute;
2. install hypervisor;
3. restore network configs;
4. restore identity;
5. restore PostgreSQL;
6. restore NATS/app;
7. reconnect edges;
8. reconcile buffered events;
9. resume scheduler;
10. validate Stripe;
11. validate lots/inventory;
12. sign off.

Measure total time.

## 11. NODE-A failure

Expected:

- NODE-B available;
- QNODE preserves quorum;
- critical services fail over/promote according deployment;
- PLC/edge unaffected.

Steps:

1. alert received;
2. verify power/network vs hardware failure;
3. verify PostgreSQL primary;
4. verify NATS R3;
5. verify payment/order API;
6. verify scheduler;
7. mark NODE-A out of service;
8. repair without risking healthy node.

Acceptance:
- no duplicate command;
- no order lost beyond RPO;
- no manual safety intervention required solely due server loss.

## 12. NODE-B failure

Same as NODE-A.

Do not immediately perform risky maintenance on NODE-A while redundancy is lost.

## 13. QNODE failure

Expected:
- compute workloads remain;
- event bus may remain operational depending current quorum;
- cluster redundancy degraded.

Actions:
- alert;
- avoid second-node maintenance;
- restore QNODE promptly.

Acceptance:
- no production stop unless quorum design requires protective mode.

## 14. Both compute nodes unavailable

Expected:
- PLC/local controllers enter autonomous safe mode;
- edge buffers events;
- new Stripe/store operations unavailable unless separately proven;
- no new central missions.

Actions:
1. declare control-plane incident;
2. stop operations that require central authorization;
3. preserve food/cold-chain via local controls;
4. inspect BESS/network;
5. restore best compute node or DR host;
6. restore DB;
7. restore event/app stack;
8. reconcile.

## 15. PostgreSQL primary failure

If automatic failover enabled:

1. DCS confirms quorum;
2. replica promoted;
3. application connection pool reconnects;
4. old primary fenced from writes.

If manual:
1. confirm primary truly unavailable;
2. inspect replica lag;
3. promote;
4. redirect;
5. fence old primary before return.

Never allow split brain.

## 16. PostgreSQL corruption

1. stop application writes;
2. snapshot evidence/logs;
3. determine logical vs physical corruption;
4. choose clean replica or PITR;
5. restore isolated;
6. validate row counts/checks;
7. switch traffic;
8. preserve corrupted copy until root cause known.

## 17. Point-in-time recovery test

Quarterly or before risky migration:

1. create known test transaction T0;
2. create T1;
3. record target timestamp between;
4. restore base backup;
5. replay WAL to target;
6. verify T0 exists;
7. verify T1 absent;
8. document restore duration.

## 18. NATS node failure

Kill one server.

Expected:
- R3 critical streams continue;
- majority remains;
- consumers continue.

Check:
- stream replica state;
- publish;
- consume;
- ack;
- replay.

Restore node and verify catch-up.

## 19. NATS double failure

With only one of three:
- critical R3 writes should stop rather than accept non-majority state.

Expected application:
- queue locally where safe;
- stop commands requiring durable coordination;
- alert.

## 20. Edge disconnection

Simulate 30–120 min offline.

Edge:
- local safety remains;
- buffers defined events;
- rejects commands requiring live authorization;
- timestamps events.

Reconnect:
- ordered/bounded replay;
- duplicate handling;
- reconciliation.

## 21. Internet loss

Expected:
- greenhouse/irrigation/local production continue;
- database/event bus local;
- Stripe/cloud/vendor services unavailable/degraded;
- store policy follows tested Stripe offline capability only.

Do not invent offline payment behavior not validated with UX700/Stripe.

## 22. Stripe outage

State:
- no new payment authorization;
- carts/orders cannot be marked PAID from assumptions;
- pending payments remain pending/reconciling.

When restored:
- fetch/reconcile PaymentIntent;
- process verified webhook/API state;
- never double capture.

## 23. Delayed Stripe webhook

Test:
- payment succeeds;
- webhook delayed.

Application must:
- remain PAYMENT_PENDING or reconcile by API;
- not issue duplicate PaymentIntent;
- not double charge;
- authorize exit only after confirmed payment state.

## 24. BESS transfer test

**Nessuna UPS consumer/distribuita. BOM-034 governa BESS, critical bus e l'eventuale ride-through P0 professionale dedicato.**

Test with electrician/energy engineer:

1. servers/network under normal load;
2. cut grid input according safe procedure;
3. record transfer;
4. verify no reboot;
5. verify DB/event continuity;
6. verify BESS telemetry;
7. run 30+ min;
8. restore grid;
9. verify transition;
10. verify P0 compute/network/PLC have no reboot or brownout-induced fault.

If reboot occurs:
- test fails;
- measure interruption;
- investigate PCS/grid-forming/transfer/distribution/PSU ride-through;
- redesign BOM-034 transfer path before production acceptance.

Non mascherare il problema con UPS desktop casuali. Se serve ride-through, deve diventare un sottosistema P0 esplicito, monitorato, manutenibile e sottoposto a SAT.

## 25. LOW_SOC

Force/simulate.

Scheduler should:
1. pause forecast training;
2. defer bulk analytics;
3. defer optional device charging;
4. keep DB/NATS/network;
5. protect cold-chain control visibility.

Verify load shedding commands never disable safety.

## 26. Rack/network switch failure

If single switch:
- acknowledged infrastructure SPOF.

For final production choose:
- spare switch with documented replacement;
- or dual-switch topology if uptime case justifies.

Test config restore to spare hardware.

## 27. Backup target failure

Production must continue.

Actions:
- alert;
- stop risky migrations/upgrades;
- replace/repair;
- restore backup schedule.

If no valid offsite backup exists:
- incident severity increases.

## 28. Offsite loss

Local backup remains.

Recreate offsite only after verifying local backup integrity.

## 29. Ransomware/admin compromise

1. isolate management plane;
2. disable compromised accounts/tokens;
3. revoke certificates;
4. preserve logs;
5. block remote access;
6. determine blast radius;
7. verify immutable/offsite backup;
8. rebuild clean management plane;
9. restore data;
10. rotate all relevant secrets.

Do not trust a compromised host merely after antivirus scan.

## 30. Keycloak/identity outage

Existing service sessions may continue until token expiry according design.

Admin/UI new logins unavailable.

Critical machine-to-machine flows should use independent service credentials/certs, not human IdP session.

Restore identity from backup.

## 31. Certificate expiry

Monitoring alerts at:
- 30 days;
- 14 days;
- 7 days;
- 1 day.

Test one non-production certificate expiry.

Automatic renewal must not silently fail.

## 32. Clock drift

Thresholds:

- warning according sensor correlation need;
- blocking for transaction correlation if drift materially affects correctness.

Actions:
- verify chrony/NTP;
- QNODE reference;
- network;
- RTC.

Events remain marked SUSPECT until corrected.

## 33. Disk failure

Mirror should remain available.

Actions:
- identify exact failed device;
- verify healthy mirror;
- replace;
- rebuild;
- monitor errors.

Do not replace two drives simultaneously unless procedure requires.

## 34. NVMe exhaustion

Alert at:
- endurance percentage;
- media errors;
- spare capacity;
- latency.

Enterprise NVMe spare on site preferred.

## 35. DB disk full

Prevent with thresholds.

At emergency:
- stop noncritical ingest;
- increase retention cleanup;
- never manually delete WAL required for backup/replica;
- expand storage or archive correctly.

## 36. Log explosion

Loki/application logging:
- rate limit;
- retention;
- cardinality controls.

Audit events preserved separately.

## 37. Scheduler failure

Fallback:
- existing tasks continue where locally safe;
- no new optimized plan;
- manual operations dashboard;
- fixed baseline rules.

Forecast service can fail without stopping scheduler.

## 38. Forecast bad model

Detect:
- bias;
- WAPE drift;
- implausible outputs.

Fallback:
- seasonal/simple baseline;
- manual override.

Model never overrides safety or HACCP rule.

## 39. Recovery order

When rebuilding control plane:

1. network;
2. DNS/time;
3. storage;
4. PostgreSQL;
5. NATS;
6. identity;
7. core API;
8. device ingress;
9. scheduler;
10. Stripe/retail;
11. observability;
12. forecast/analytics.

## 40. Incident log

Every incident records:

- start/end;
- severity;
- detected by;
- affected services;
- user/production impact;
- RPO/RTO;
- root cause;
- actions;
- data loss;
- recurrence prevention;
- linked work orders.

## 41. Commissioning acceptance gate

BOM-030 cannot be considered closed until:

- full DB restore demonstrated;
- one compute failover demonstrated;
- NATS R3 single-node loss demonstrated;
- edge replay demonstrated;
- BESS transition demonstrated;
- Stripe delayed webhook demonstrated;
- RBAC denied-action demonstrated;
- offsite restore demonstrated.

Evidence:
- screenshots/log IDs;
- timestamps;
- operator;
- result;
- corrective action if fail.
