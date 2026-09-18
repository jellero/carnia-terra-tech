# RFQ — Server centrale di orchestrazione — BOM-030

**Progetto:** Carnia TerraTech  
**Aggiornato:** 18 settembre 2026  
**Stato:** `RFQ TEMPLATE / 2 COMPUTE + QNODE + BACKUP SEPARATO / NESSUNA UPS LOCALE`.

## 1. Oggetto

Richiesta di offerta separata e comparabile per:

- 2 nodi compute server-grade;
- 1 witness/edge node;
- storage NVMe enterprise;
- backup target separato;
- networking 10 GbE;
- rack/PDU;
- Proxmox VE;
- Proxmox Backup Server o equivalente;
- installazione;
- firmware/support;
- commissioning;
- spare strategy.

Lo stack applicativo principale è open-source e sviluppato/integrato internamente.

## 2. Vincoli architetturali

Non quotare come baseline:

- UPS locali;
- Kubernetes;
- SAN;
- Ceph;
- GPU nei nodi core;
- database cloud-only;
- ERP proprietario come system of record.

Il sito dispone di BESS condiviso da 30 kW; capacità utile in kWh/autonomia da definire nel package energia.

## 3. Lotto A — compute NODE-A / NODE-B

Quotare 2 nodi identici.

Reference class:
- Dell PowerEdge T160;
- Dell PowerEdge R260;
- HPE ProLiant MicroServer Gen11 / server equivalente;
- Lenovo ThinkSystem equivalente.

Requisiti minimi per nodo:

- CPU x86_64 server-grade;
- 8 core fisici utili minimo, 12–16 preferiti;
- ECC DDR5;
- 64 GB ECC minimo;
- 128 GB ECC target;
- espansione >=128 GB;
- 2×1,92 TB enterprise NVMe minimum;
- mirror software/ZFS supportato;
- endurance e DWPD dichiarati;
- 2×10GbE o NIC equivalente;
- 1× management/BMC;
- TPM 2.0;
- remote management;
- temperature/fan telemetry;
- secure boot;
- rack/tower installabile;
- 3–5 year support.

Quotare varianti:
- A1 64 GB;
- A2 128 GB;
- A3 256 GB.

## 4. Storage node locale

Per ciascun compute:

### OS
- 2× SSD enterprise mirror, oppure boot mirror OEM.

### Workload
- 2× enterprise NVMe 1,92 TB mirror;
- optional 3,84 TB.

Richiedere:
- vendor/model;
- interface;
- power-loss protection;
- endurance TBW/DWPD;
- warranty;
- SMART/health;
- hot-swap where possible.

Consumer NVMe without PLP is not preferred for PostgreSQL primary.

## 5. NIC/network

Per compute:

- dual 10GbE preferred;
- SFP+ or 10GBase-T;
- separate management port;
- VLAN support.

Quotare:
- NIC;
- DAC;
- optics;
- spare transceiver.

## 6. Lotto B — QNODE / edge witness

1 unit.

Target:

- x86_64;
- 16 GB RAM minimum, 32 GB preferred;
- ECC preferred;
- 2× SSD/NVMe mirrored preferred;
- 2×1/2.5GbE minimum;
- fanless/industrial or compact server;
- TPM;
- watchdog;
- remote reboot;
- BESS powered.

Loads:
- Proxmox qdevice/quorum;
- NATS third replica;
- coordination/DCS;
- chrony/NTP;
- MQTT bridge;
- edge health services.

No main PostgreSQL primary.

## 7. Lotto C — backup target

Quote:

### C1 8-bay NAS class

Reference:
- Synology DS1825+ class or equivalent.

Minimum:
- 8 bays;
- ECC if available;
- snapshots;
- 2.5GbE minimum;
- 10GbE upgrade preferable;
- SMART/scrub;
- encrypted backup;
- API/monitoring.

### C2 dedicated backup server

Alternative:
- x86 server;
- ZFS;
- Proxmox Backup Server;
- 32 GB ECC;
- 8 bays.

Quote both where practical.

## 8. Backup drives

Quote options:

- 4×12 TB enterprise/NAS HDD;
- 6×12 TB;
- 4×16 TB.

State:
- usable capacity by RAID/ZFS layout;
- rebuild time estimate;
- workload rating;
- warranty;
- AFR/URE specs.

Do not mix drive models in same vdev/RAID set baseline.

## 9. Offsite

Quote optionally:

- encrypted S3-compatible object storage;
- second-site NAS;
- removable encrypted media rotation.

Provide:
- €/TB/month;
- egress;
- minimum retention;
- API compatibility.

Offsite is required architecturally, vendor may be selected separately.

## 10. Lotto D — switching

Quote server interconnect and rack switching.

Working candidates:
- Ubiquiti Pro Max 24 class;
- Ubiquiti Pro XG 10 PoE class;
- enterprise equivalent from Aruba/Cisco/MikroTik where justified.

Requirements:
- VLAN;
- 10GbE server links;
- SFP+;
- LACP where used;
- SNMP/API;
- fan/PSU monitoring;
- spare config/export.

PoE is useful for edge/CCTV but not mandatory for the server interconnect itself.

## 11. Rack and power

Quote:

- 12U/18U/24U rack as appropriate;
- lockable;
- cable management;
- patch panel;
- 2 PDUs;
- temperature sensor;
- airflow clearance;
- shelves/rails;
- grounding.

Power:
- fed from BESS-backed distribution;
- no local UPS.

Require separate feed/branch circuit design from electrician.

## 12. Environment

Vendor to declare:

- operating temperature;
- humidity;
- dust requirements;
- acoustic level;
- airflow;
- heat output at idle/typical/max.

Server location must be dry, dust controlled and separate from food-process washdown.

## 13. Proxmox VE

Quote support options for 2 occupied CPU sockets:

- Community;
- Basic;
- Standard.

Do not bundle Premium unless explicitly justified.

Current official reference:
- Community €120/year/socket;
- Basic €370/year/socket;
- Standard €550/year/socket.

Installation:
- Proxmox VE 9.2 current baseline;
- cluster;
- qdevice;
- networking;
- storage;
- templates;
- RBAC;
- update policy.

## 14. Backup software

Quote:
- Proxmox Backup Server 4.2 installation;
- repository;
- retention;
- verification;
- prune;
- garbage collection;
- alerting.

Support optional:
- Community;
- Basic.

Also configure:
- PostgreSQL base backups;
- WAL archive;
- file/object backup.

## 15. PostgreSQL deployment

Implementation scope:

- PostgreSQL 18 supported release;
- primary/replica;
- TLS;
- role separation;
- pg_hba;
- monitoring;
- backup;
- WAL archive;
- failover runbook.

Automatic failover:
- quote as separate implementation option.

Candidate:
- Patroni + quorum/DCS.

Do not enable automatic failover without acceptance testing.

## 16. NATS JetStream

Deploy 3 servers:
- NODE-A;
- NODE-B;
- QNODE.

Critical streams:
- replicas=3.

Configure:
- TLS;
- accounts/users;
- limits;
- disk storage;
- monitoring;
- backup/config export.

Acceptance:
- kill one server;
- publish/read continues.

## 17. MQTT/edge ingress

Quote/configure:

- MQTT broker/bridge;
- TLS;
- client certs where possible;
- retained-message policy;
- bridge to event normalization layer.

Protocols:
- MQTT;
- OPC UA;
- Modbus gateway.

## 18. Identity

Deploy:
- Keycloak or equivalent OIDC provider;
- MFA;
- RBAC;
- admin roles;
- service account separation;
- backup.

External IdP integration optional.

## 19. Observability

Deploy/configure:

- Prometheus;
- Grafana;
- Loki;
- Grafana Alloy/OpenTelemetry.

Dashboards:
- host;
- storage;
- PostgreSQL;
- NATS;
- applications;
- network;
- backup;
- BESS integration;
- device health.

Alert routing:
- email/other channel defined by operator;
- no hidden vendor SaaS dependency required.

## 20. Security

Configuration includes:

- host firewall;
- VLAN rules;
- SSH keys;
- MFA;
- TLS;
- certificate renewal;
- BMC isolation;
- patch policy;
- vulnerability review;
- admin logging;
- encrypted backups;
- secure offsite.

No public exposure of:
- Proxmox;
- PostgreSQL;
- NATS admin;
- PLC interfaces.

## 21. Lotto E — edge gateways

Quote unit class for future scaling:

- 4-port industrial/edge x86;
- 8–16 GB RAM;
- 256–512 GB SSD;
- dual/quad NIC;
- 24 VDC option;
- TPM;
- fanless;
- DIN/industrial mounting where appropriate.

Initial quantity:
- 2 working;
- scalable to 4–8.

Use:
- greenhouse;
- Tech Barn;
- energy/water;
- retail.

## 22. API / integration scope

Vendor/integrator must not own business schema.

Deliverables:
- network endpoints;
- certificates;
- service discovery;
- monitoring endpoints;
- backups;
- deployment manifests;
- documented ports.

Application/API contracts remain in Carnia TerraTech repository.

## 23. Commissioning

Required:

1. firmware inventory;
2. BIOS baseline;
3. TPM/secure boot;
4. storage mirror test;
5. NIC fail test;
6. NODE-A power failure;
7. NODE-B failure;
8. QNODE failure;
9. Proxmox cluster quorum;
10. PostgreSQL promotion/restore;
11. NATS R3 failover;
12. NAS failure alert;
13. backup job;
14. VM restore;
15. DB PITR;
16. Internet loss;
17. BESS power mode;
18. network VLAN isolation;
19. MFA/RBAC;
20. certificate expiry simulation;
21. offsite restore sample.

## 24. Documentation required

- as-built rack;
- IP/VLAN plan;
- serial numbers;
- warranty;
- BIOS settings;
- firmware;
- Proxmox config;
- storage layout;
- backup policy;
- credentials handoff procedure;
- restore runbook;
- network diagram;
- support contacts.

No credentials in PDF/plain email deliverable.

## 25. Economic format

For each item:

| Campo | Richiesto |
|---|---|
| code | yes |
| make/model | yes |
| CPU | yes |
| RAM | yes |
| storage | yes |
| NIC | yes |
| qty | yes |
| net price | yes |
| VAT | separate |
| freight | separate |
| install | separate |
| support | €/year |
| power typical/max | W |
| warranty | years |
| lead time | yes |
| spare availability | yes |
| exclusions | yes |

## 26. Variants

Compare:

- 2× Dell T160 class + QNODE;
- 2× rack R260 class + QNODE;
- 2× HPE/Lenovo equivalent + QNODE;
- 64 vs 128 GB;
- 1.92 vs 3.84 TB NVMe mirror;
- NAS vs dedicated PBS server;
- Proxmox Basic vs Standard;
- 1G/2.5G general switching + 10G uplinks vs full 10G core.

## 27. TCO

5-year TCO:

`hardware + support + storage replacement + disks + electricity + offsite + licenses/subscriptions + maintenance + admin time`.

Separate:
- capital hardware;
- annual support;
- cloud/offsite;
- development labor;
- network already shared with other BOMs.
