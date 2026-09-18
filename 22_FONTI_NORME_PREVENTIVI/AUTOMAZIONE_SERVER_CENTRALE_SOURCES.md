# Fonti — BOM-030 Server centrale di orchestrazione

**Aggiornato:** 18 settembre 2026

## 1. Regola fonti

Priorità:

1. vendor hardware ufficiale;
2. progetto software ufficiale;
3. documentazione tecnica ufficiale;
4. prezzi vendor/store ufficiali;
5. RFQ installatore/integratore per configurazione reale.

Il costo di una configurazione base online non viene usato come prezzo finale del nodo target.

## 2. Dell PowerEdge T160

Dell Italia:

https://www.dell.com/it-it/shop/dell-emc-poweredge-tower-servers/sr/servers?showSRMessage=1

Pagina prodotto:

https://www.dell.com/it-it/shop/ipovw/poweredge-t160

Dati osservati:
- server near-edge/tower 3U;
- single socket;
- Smart Selection corrente in catalogo;
- configurazione vista con Xeon 6315P, 16 GB, 2 TB SATA, 3-year Basic NBD;
- prezzo osservato **€4.793,77 + IVA**.

Altre pagine/configurazioni Dell mostrano prezzi differenti.

Regola:
- benchmark soltanto;
- BOM-030 richiede 64/128 GB ECC, enterprise NVMe mirror e 10GbE, quindi prezzo = RFQ.

## 3. Dell PowerEdge R260

https://www.dell.com/it-it/shop/server-storage-e-connettivit%C3%A0/poweredge-r260/spd/poweredge-r260/emea_r260

Smart Selection:

https://www.dell.com/it-it/shop/enterprise-products/server-rack-poweredge-r260/spd/poweredge-r260/emea_per2601a?view=configurations

Dati osservati:
- rack 1U;
- near-edge;
- single socket;
- prezzi online fortemente configuration-dependent;
- Smart Selection osservato circa €4.086 + IVA in una pagina;
- altra configurazione corrente osservata circa €6.649 + IVA.

Regola:
- usare RFQ identica configurazione per confronto T160/R260.

## 4. HPE ProLiant MicroServer Gen11

HPE Italia:

https://www.hpe.com/it/it/products/compute/proliant/microserver-gen11.html

Dati:
- compact/edge server;
- Intel Xeon 6300 / E-2400 / Pentium options;
- 4 DDR5 DIMM slots;
- PCIe;
- HPE iLO;
- posizione flessibile.

Uso BOM:
- alternativa compute;
- qnode;
- backup server class.

Prezzo:
- RFQ.

## 5. Synology DS1825+

Product manual:

https://kb.synology.com/en-global/HIGs/DS1825p_HIG/1

Dati:
- AMD Ryzen V1500B;
- DDR4 8 GB;
- 8× 3.5/2.5 SATA bays;
- 2× M.2 NVMe;
- 2×2.5GbE;
- 0–40 °C operating range.

Uso:
- benchmark backup/NAS;
- non primary PostgreSQL storage.

Prezzo:
- RFQ/reseller.

## 6. Ubiquiti Pro Max 24

Official EU Store:

https://eu.store.ui.com/eu/en/products/usw-pro-max-24

Dati osservati:
- €405;
- 24-port Layer 3;
- 2.5GbE class;
- 10G uplink accessories.

## 7. Ubiquiti Pro XG 10 PoE

Official EU Store:

https://eu.store.ui.com/eu/en/products/usw-pro-xg-10-poe

Dati:
- €629;
- 10×10GbE;
- 2×10G SFP+;
- 400 W PoE.

Accessori osservati:
- 10G DAC from €12;
- 10G multimode optical module from €18.

Uso:
- benchmark server/edge switching;
- la topologia finale può usare altro vendor.

## 8. Proxmox VE 9.2

Release:

https://www.proxmox.com/en/about/company-details/press-releases/proxmox-virtual-environment-9-2

Rilasciato:
- 21 maggio 2026.

Dati:
- Debian 13.5 base;
- KVM;
- LXC;
- ZFS;
- HA;
- SDN;
- Dynamic Load Balancer;
- QEMU 11;
- LXC 7;
- ZFS 2.4.

Uso:
- working virtualization baseline.

## 9. Proxmox VE subscription

https://www.proxmox.com/en/products/proxmox-virtual-environment/pricing

Prezzi netti osservati:
- Community: **€120/year/CPU socket**;
- Basic: **€370/year/socket**;
- Standard: **€550/year/socket**;
- Premium: **€1.100/year/socket**.

Per 2 single-socket compute nodes:
- Community €240/year;
- Basic €740/year;
- Standard €1.100/year;
- Premium €2.200/year.

Subscription non necessaria per feature unlock; serve repository/support secondo piano.

## 10. Proxmox Backup Server 4.2

Release index:

https://www.proxmox.com/en/about/company-details/press-releases

Release:
- 29 aprile 2026.

Documentation:
https://pbs.proxmox.com/docs/

Support/pricing:
https://www.proxmox.com/en/products/proxmox-backup-server/pricing

Prezzi osservati:
- Community €560/year/server;
- Basic €1.120/year;
- Standard €2.240/year;
- Premium €4.480/year.

Software open source.

## 11. Debian 13

Current release page:

https://www.debian.org/releases/trixie/

Al 18/09/2026:
- Debian stable = 13 Trixie;
- latest point release = **13.7**, 12 settembre 2026;
- full Debian support fino agosto 2028;
- LTS fino giugno 2030.

Uso:
- qnode;
- guest OS;
- infrastructure services.

## 12. PostgreSQL 18

Release notes:

https://www.postgresql.org/docs/release/

Press kit:

https://www.postgresql.org/about/press/presskit18/

Al 18/09/2026:
- current major = PostgreSQL 18;
- 18.6 released 13 agosto 2026.

Features relevant:
- asynchronous I/O;
- uuidv7();
- improved upgrades;
- OAuth 2.0 authentication support.

Uso:
- central relational database;
- append-only business event ledger;
- partitioned telemetry tables.

## 13. NATS JetStream

JetStream:

https://docs.nats.io/concepts/jetstream

Key properties:
- persistence;
- replay;
- server-side streams;
- durable consumers;
- acknowledgements;
- at-least-once delivery.

Cluster:

https://docs.nats.io/learn/topologies/jetstream-in-a-cluster

Important architecture points:
- cluster coordination uses majority;
- odd number of servers preferred;
- 3 servers tolerate loss of one;
- R3 is production floor for replicated streams described in official docs;
- R1 stream on a cluster is still single-copy.

BOM rule:
- critical streams R3 on NODE-A, NODE-B, QNODE.

## 14. Keycloak

HA overview:

https://www.keycloak.org/high-availability/introduction

Main site/docs:

https://www.keycloak.org/documentation

Use:
- OIDC;
- user identity;
- role-based access;
- admin MFA integration.

BOM does not require multi-region Keycloak HA; local redundant service is sufficient.

## 15. Prometheus

Download/releases:

https://prometheus.io/download/

Release cycle/LTS:

https://prometheus.io/docs/introduction/release-cycle/

Observed 18/09/2026:
- current release: Prometheus 3.14.0, 17/08/2026;
- Prometheus 3.13 is LTS;
- 3.13 support through 31/07/2027.

Working:
- prefer supported/LTS line for production if stability is more valuable than latest features.

## 16. Grafana Alloy

Docs:

https://grafana.com/docs/alloy/latest/

Why Alloy:

https://grafana.com/docs/alloy/latest/introduction/why-alloy/

Alloy supports:
- Prometheus metrics;
- OpenTelemetry;
- logs;
- traces;
- edge/gateway deployment;
- multiple destinations.

Use:
- common observability collector.

## 17. Grafana Loki

Docs:

https://grafana.com/docs/loki/latest/

Data source docs:

https://grafana.com/docs/grafana/latest/datasources/loki/

Use:
- application/infrastructure logs;
- labels rather than full-content index architecture.

Logs are not the immutable business audit ledger.

## 18. Grafana OSS

https://grafana.com/oss/grafana/

Use:
- infrastructure;
- operations;
- energy;
- device;
- scheduler dashboards.

No Grafana Cloud dependency baseline.

## 19. MQTT

Eclipse Mosquitto:

https://mosquitto.org/

Use:
- field/edge MQTT ingress;
- not central system of record.

Devices publish to edge broker/gateway; normalized events enter internal event bus/database.

## 20. Stripe

Terminal:
https://stripe.com/it/terminal

UX700:
https://stripe.com/terminal/ux700

Server-driven:
https://support.stripe.com/questions/terminal-server-driven-integration?locale=it-IT

Use:
- BOM-028 integration;
- secrets remain on central server;
- PaymentIntent/webhook/refund/reconciliation logic.

Transaction fees belong to BOM-028, not duplicated in BOM-030.

## 21. BESS dependency

BOM-030 uses the project constraint already consolidated:

- shared BESS backup power: **30 kW**;
- local UPS baseline: **0**.

Still required from energy package:
- usable kWh;
- continuous/peak power;
- transfer time;
- islanding;
- SOC reserve;
- black start if present.

Server acceptance must test actual BESS transition.

## 22. Software license principle

Baseline software components are open source:
- Debian;
- PostgreSQL;
- NATS;
- Keycloak;
- Prometheus;
- Grafana OSS;
- Loki;
- Alloy;
- Mosquitto;
- Proxmox VE/PBS.

This does not mean zero TCO.

Track:
- support;
- updates;
- operations;
- internal development;
- backup;
- offsite;
- energy;
- incident response.

## 23. Update rule

On final RFQ record:

1. vendor;
2. model;
3. CPU;
4. RAM;
5. NVMe vendor/endurance;
6. NIC;
7. management;
8. warranty;
9. support;
10. net price;
11. VAT;
12. delivery;
13. power;
14. heat;
15. lead time;
16. replacement;
17. firmware lifecycle;
18. installed total;
19. five-year TCO.
