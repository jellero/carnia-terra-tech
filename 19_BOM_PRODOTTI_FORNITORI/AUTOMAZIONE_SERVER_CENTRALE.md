# BOM-030 — Server centrale di orchestrazione

**Aggiornato:** 18 settembre 2026  
**Ambito:** compute, storage, backup, edge, networking, virtualizzazione, DB, event bus, identity, observability, HA, DR.  
**Stato:** `ARCHITETTURA STRUTTURATA / HARDWARE TARGET DA RFQ / SOFTWARE STACK DEFINITO / ACCEPTANCE BLOCCANTE`.

## 1. Regola di lettura

Stati:

- `BASELINE`;
- `WORKING`;
- `OPTIONAL`;
- `FUTURE`;
- `INTERFACE`;
- `INTERNAL`;
- `RFQ`.

Prezzi pubblici osservati il 18/09/2026 sono benchmark, non configurazioni finali installate.

## 2. Distinta hardware/software

| Codice | Voce | Q.tà | Stato | Benchmark |
|---|---|---:|---|---:|
| SV-COMPUTE-A | server compute NODE-A | 1 | BASELINE | Dell T160 class, target config RFQ |
| SV-COMPUTE-B | server compute NODE-B | 1 | BASELINE | Dell T160 class, target config RFQ |
| SV-DELL-T160 | Dell PowerEdge T160 Smart Selection base reference | ref | BENCHMARK | €4.793,77 + IVA current listing |
| SV-DELL-R260 | Dell PowerEdge R260 Smart Selection rack reference | ref | ALT | ~€4.086–6.649 + IVA observed config-dependent |
| SV-HPE-MS | HPE ProLiant MicroServer Gen11 | ref | ALT | RFQ |
| SV-RAM-64 | ECC RAM 64 GB/node | 2 sets | MINIMUM | RFQ |
| SV-RAM-128 | ECC RAM 128 GB/node | 2 sets | WORKING TARGET | RFQ |
| SV-NVME-1920 | enterprise NVMe 1,92 TB PLP | 4 | BASELINE | 2/node mirror, RFQ |
| SV-NVME-3840 | enterprise NVMe 3,84 TB PLP | 0–4 | OPTIONAL | RFQ |
| SV-BOOT | boot SSD mirror/OEM boot module | 2 sets | BASELINE | RFQ |
| SV-NIC10 | dual-port 10GbE NIC | 2 | BASELINE | RFQ |
| SV-TPM | TPM 2.0 | 2 | BASELINE | OEM included/preferred |
| SV-BMC | iDRAC/iLO class remote management | 2 | BASELINE | OEM config |
| SV-QNODE | witness/edge node 16–32 GB | 1 | BASELINE | industrial/compact x86 RFQ |
| SV-QNODE-SSD | mirrored SSD/NVMe qnode | 2 | BASELINE | RFQ |
| SV-NAS | 8-bay backup NAS/server | 1 | BASELINE | Synology DS1825+ class, RFQ |
| SV-HDD12 | 12 TB NAS/enterprise HDD | 4–6 | BASELINE | RFQ |
| SV-HDD16 | 16 TB NAS/enterprise HDD | 0–6 | ALT | RFQ |
| SV-NAS-10G | 10GbE NIC for backup target | 1 | CANDIDATE | RFQ |
| SV-OFFSITE | encrypted offsite backup | 1 | BASELINE | €/TB/month RFQ |
| SV-RACK | 12U/18U/24U rack | 1 | BASELINE | RFQ |
| SV-PDU-A | rack PDU A | 1 | BASELINE | BESS-backed, RFQ |
| SV-PDU-B | rack PDU B | 1 | BASELINE | BESS-backed, RFQ |
| SV-RACK-TEMP | rack temp/environment sensor | 1–2 | BASELINE | RFQ |
| SV-PATCH | patch panel/cable management | 1 lot | BASELINE | RFQ |
| SV-SW-24 | UniFi Pro Max 24 | 0–1 | NETWORK BENCHMARK | €405 |
| SV-SW-XG10 | UniFi Pro XG 10 PoE | 0–1 | 10G CANDIDATE | €629 |
| SV-DAC10 | 10G DAC | 2–6 | BASELINE | from €12 |
| SV-SFP-MM | 10G multimode module | DA LAYOUT | OPTIONAL | from €18 |
| SV-EDGE | industrial edge gateway | 2 initial | BASELINE | RFQ |
| SV-EDGE-SPARE | edge gateway spare | 1 | SPARE | RFQ |
| SV-BESS | BESS 30 kW integration | 1 | INTERFACE | existing energy architecture |
| SV-UPS | local UPS | 0 | EXCLUDED | none |
| SV-PVE | Proxmox VE 9.2 | 2 nodes | BASELINE | open source |
| SV-PVE-COM | PVE Community subscription | 2 sockets/y | OPTIONAL | €240/y total |
| SV-PVE-BASIC | PVE Basic subscription | 2 sockets/y | WORKING SUPPORT | €740/y total |
| SV-PVE-STD | PVE Standard subscription | 2 sockets/y | ALT SUPPORT | €1.100/y total |
| SV-PBS | Proxmox Backup Server 4.2 | 1 | BASELINE | open source |
| SV-PBS-COM | PBS Community subscription | 1/y | OPTIONAL | €560/y |
| SV-PBS-BASIC | PBS Basic subscription | 1/y | ALT | €1.120/y |
| SV-DEBIAN | Debian 13 stable guests/qnode | all | BASELINE | €0 license |
| SV-PG | PostgreSQL 18 supported release | 2 | BASELINE | €0 license |
| SV-PG-HA | PG streaming replication | 1 | BASELINE | INTERNAL |
| SV-PATRONI | Patroni/DCS auto-failover | 0–1 | CANDIDATE | INTERNAL |
| SV-PGBACKREST | pgBackRest backup/WAL | 1 | BASELINE | €0 license |
| SV-NATS | NATS server | 3 | BASELINE | €0 license |
| SV-JS | JetStream R3 critical streams | 1 cluster | BASELINE | INTERNAL |
| SV-MQTT | MQTT broker/bridge | edge | BASELINE | Mosquitto/equivalent €0 |
| SV-KEYCLOAK | Keycloak/OIDC | 1 logical service | BASELINE | €0 license |
| SV-REVERSE | reverse proxy/HAProxy/Caddy class | 1 logical | BASELINE | €0 license |
| SV-PROM | Prometheus | 1 logical | BASELINE | €0 license |
| SV-GRAFANA | Grafana OSS | 1 logical | BASELINE | €0 license |
| SV-LOKI | Loki | 1 logical | BASELINE | €0 license |
| SV-ALLOY | Grafana Alloy/OTel collectors | multiple | BASELINE | €0 license |
| SV-GITOPS | Git/CI deployment pipeline | 1 | BASELINE | INTERNAL |
| SV-SECRETS | SOPS/age or secret manager | 1 | BASELINE | INTERNAL/€0 |
| SV-SCHED | operational scheduler service | 1 | BASELINE | INTERNAL DEVELOPMENT |
| SV-DISPATCH | dispatcher/reconciler | 1 | BASELINE | INTERNAL DEVELOPMENT |
| SV-DIGITAL | digital twin/state model | 1 | BASELINE | INTERNAL DEVELOPMENT |
| SV-FORECAST-D | demand forecast service | 1 | BASELINE | INTERNAL DEVELOPMENT |
| SV-FORECAST-S | supply forecast service | 1 | BASELINE | INTERNAL DEVELOPMENT |
| SV-STRIPE | Stripe backend integration | 1 | BASELINE | INTERNAL; transaction fees BOM-028 |
| SV-API | REST/OpenAPI layer | 1 | BASELINE | INTERNAL |
| SV-EVENTSCHEMA | AsyncAPI/event schemas | 1 | BASELINE | INTERNAL |
| SV-DEVICE | device registry | 1 | BASELINE | INTERNAL |
| SV-SIM | simulator/staging environment | 1 | BASELINE | INTERNAL |
| SV-OFFSITE-TEST | annual offsite restore drill | 1/y | BASELINE | internal/ops |
| SV-SPARE-NVME | enterprise NVMe spare | 1 | SPARE | RFQ |
| SV-SPARE-NIC | 10GbE NIC/transceiver spare | 1 lot | SPARE | RFQ |
| SV-SPARE-HDD | backup HDD spare | 1 | SPARE | RFQ |
| SV-COMMISSION | infra commissioning | 1 | OBBLIGATORIO | internal/integrator |
| SV-DRILL | DR/failover acceptance | 1 | OBBLIGATORIO | internal/integrator |

## 3. Hardware working baseline

### Compute

2 identical nodes:

- 8–16 server cores class;
- 128 GB ECC target;
- 2×1,92 TB enterprise NVMe mirror;
- 10GbE;
- BMC;
- TPM;
- 3–5 year support.

### Why 128 GB target

Not because current load needs it.

Headroom covers:
- PostgreSQL cache;
- observability;
- staging;
- rolling upgrades;
- forecasting;
- temporary failover when one node carries most services.

64 GB remains technically viable for initial deployment.

## 4. Dell T160 benchmark

Dell Italia current listing observed:
- PowerEdge T160 Smart Selection;
- Xeon 6315P class in listed config;
- 16 GB;
- 2 TB SATA;
- 3-year Basic NBD;
- **€4.793,77 + IVA**.

This is only the base price reference.

Target BOM requires:
- 64/128 GB ECC;
- enterprise NVMe mirror;
- 10GbE;
- suitable remote management/support.

Therefore:
- `SV-COMPUTE-A/B = RFQ`.

## 5. Rack alternative

PowerEdge R260 current official listings observed in a broad range depending on configuration, including:
- Smart Selection around €4.086 + IVA in one listing;
- other current configurations around €6.649 + IVA or higher.

R260 is preferred only if:
- rack density;
- datacenter-style service;
- airflow/noise;
- remote support;

justify the premium.

For near-edge farm installation, T160/compact server remains working candidate.

## 6. HPE alternative

HPE ProLiant MicroServer Gen11:
- current platform supports Xeon 6300/E-2400 class;
- 4 DDR5 DIMM slots;
- iLO;
- compact edge/on-prem form factor.

Use as:
- compute alternative;
- qnode/backup-server class.

Price:
- RFQ.

## 7. Backup target

Synology DS1825+ class:
- AMD Ryzen V1500B;
- 8 GB DDR4;
- 8× SATA bays;
- 2× M.2;
- 2×2,5GbE.

Use:
- backup/snapshot repository;
- non-primary DB.

Capacity examples before filesystem/RAID overhead:

- 4×12 TB = 48 TB raw;
- 6×12 TB = 72 TB raw;
- 4×16 TB = 64 TB raw.

Select layout from:
- retention;
- camera/image volume;
- DB backup;
- VM backup;
- rebuild risk.

## 8. Network benchmark

### Pro Max 24

Official EU:
- €405;
- Layer 3;
- 2.5GbE class.

### Pro XG 10 PoE

Official EU:
- €629;
- 10×10GbE;
- 2×10G SFP+;
- 400 W PoE.

### Accessories

- 10G DAC from €12;
- multimode SFP+ from €18.

Decision:
- use existing/shared network if already sufficient;
- do not duplicate switch cost into BOM-030 if purchased under site network BOM.

## 9. Proxmox

Current production reference:
- Proxmox VE 9.2.

Official subscriptions:
- Community €120/year/socket;
- Basic €370;
- Standard €550;
- Premium €1.100.

Working:
- Basic on 2 single-socket compute nodes:
  - **€740/year**.

User-developed stack makes Premium unnecessary baseline.

## 10. Proxmox Backup Server

Current reference:
- PBS 4.2.

Subscription:
- Community €560/year/server;
- Basic €1.120/year.

Working:
- run open source initially;
- add Community/Basic if enterprise repository/support is valuable.

## 11. OS/database

Debian stable on 18/09/2026:
- Debian 13.7 Trixie.

PostgreSQL:
- 18 current major;
- 18.6 published 13/08/2026.

License cost:
- €0.

Upgrade policy:
- patch regularly;
- major version upgrade tested in staging;
- never auto-upgrade production major.

## 12. Time-series decision

No separate commercial TSDB baseline.

Use PostgreSQL:
- partitioning;
- aggregates;
- retention;
- archive.

Prometheus is for:
- operational metrics/monitoring.

Add TimescaleDB only if benchmark proves:
- storage reduction;
- query benefit;
- maintenance benefit.

Avoid complexity by default.

## 13. Event bus sizing

NATS JetStream critical R3:
- three nodes;
- modest event payloads;
- bounded retention.

Business events persist long-term in PostgreSQL.

JetStream is:
- transport/durable coordination;
- not the only permanent ledger.

High-frequency raw telemetry:
- aggregate/filter at edge;
- batch DB;
- do not stream every raw sample forever without value.

## 14. Storage sizing

Initial local mirrored 1,92 TB/node is sufficient for:
- DB;
- event bus;
- application;
- observability active window.

Large blobs:
- images;
- vision;
- video;
- model artifacts;

go to backup/object/file tier.

Never store CCTV archive in PostgreSQL.

## 15. Backup retention working

VM:
- 7 daily;
- 4 weekly;
- 6 monthly.

Database:
- continuous WAL;
- daily base;
- monthly archive.

Config:
- Git history;
- encrypted credential recovery material.

Offsite:
- daily/weekly according bandwidth.

Final policy after measured daily data growth.

## 16. Data growth meter

Server must expose:
- DB GB/day;
- telemetry GB/day;
- logs GB/day;
- images GB/day;
- backup growth;
- compression;
- retention forecast.

Forecast storage 12/36/60 months.

Do not buy 100 TB because it feels safer.

## 17. Energy

Meter separately:
- compute A;
- compute B;
- QNODE;
- backup;
- network.

Server scheduler can:
- suspend forecast training;
- defer backup compaction;
- reduce noncritical analytics;

when BESS is low.

Do not suspend:
- DB;
- network;
- event ingress;
- critical logging.

## 18. No UPS

`SV-UPS = 0`.

All core IT is on BESS-backed circuits.

Acceptance requires:
- grid-loss test;
- inverter/BESS transition;
- no unexpected reboot if the BESS transfer characteristic supports it.

If actual transfer time proves incompatible with server PSU ride-through:
- solve at BESS/inverter/distribution architecture first;
- local UPS only becomes exception after measured evidence.

## 19. Development cost

Software is internally developed.

Do not assign fake market SaaS cost.

Track actual:
- development hours;
- maintenance hours;
- incident hours;
- cloud/API fees;
- support.

This enables true TCO without pretending internal engineering is free.

## 20. Five-year TCO

`TCO5 = compute + qnode + backup + network_incremental + support + offsite + disk_replacement + energy + maintenance + internal_engineering`.

Keep separate:
- existing/shared BESS;
- existing site network;
- Stripe transaction fees;
- domain-specific edge/cameras already in other BOMs.

## 21. Purchase gate

No order before:

1. server-room/rack location;
2. temperature/dust;
3. BESS transfer test;
4. kWh/autonomy;
5. retention model;
6. image/video storage policy;
7. 3 quotes for compute;
8. SSD endurance;
9. network topology;
10. backup/offsite;
11. acceptance plan.
