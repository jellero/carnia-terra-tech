# Carnia TerraTech — Punto 07: Automazione, dati e AI

**Aggiornato:** 18 settembre 2026  
**Stato:** BOM-030 SERVER CENTRALE SVILUPPATA / HARDWARE DA RFQ / ACCEPTANCE E DR BLOCCANTI.

## 1. Principio

Carnia TerraTech usa un server centrale come:

- system of record;
- scheduler operativo;
- event ledger;
- inventory/lot master;
- payment/retail coordinator;
- maintenance planner;
- energy-aware planner;
- demand/supply forecasting layer.

Il server non sostituisce:
- safety PLC;
- E-stop;
- interblocchi;
- protezioni locali;
- motion safety;
- BESS protection.

Regola:

`server down != impianto unsafe`.

## 2. BOM-030 deployment

Working:

- 2 compute node server-grade;
- 1 qnode/edge witness;
- 1 backup target separato;
- 10GbE server interconnect;
- BESS 30 kW come backup condiviso;
- nessuna UPS locale.

Compute target:
- 64 GB ECC minimo;
- 128 GB ECC working;
- enterprise NVMe mirror;
- remote management;
- TPM;
- 10GbE.

## 3. Software stack

Baseline:

- Proxmox VE;
- Debian;
- PostgreSQL;
- NATS JetStream;
- MQTT edge ingress;
- Keycloak/OIDC;
- Prometheus;
- Grafana;
- Loki;
- Alloy/OpenTelemetry;
- Git/CI;
- custom scheduler/forecast services.

Explicitly non-baseline:
- Kubernetes;
- Ceph;
- SAN;
- cloud-only DB;
- proprietary ERP master;
- GPU nel control plane.

## 4. Database

PostgreSQL è la base unica per:

- master data;
- ordini;
- inventory;
- lotti;
- task;
- manutenzione;
- stato macchina;
- audit;
- business event ledger.

Telemetry:
- partitioned tables;
- retention;
- aggregate;
- cold archive.

TSDB addizionale solo dopo benchmark.

## 5. Event bus

NATS JetStream:

- NODE-A;
- NODE-B;
- QNODE.

Critical streams:
- R3.

Examples:
- order;
- payment;
- inventory;
- lot;
- command;
- task;
- audit.

## 6. Contracts

Documento:
- `EVENT_API_CONTRACTS.md`.

Principi:
- command != event != query;
- idempotency;
- correlation/causation IDs;
- schema versioning;
- UUIDv7;
- state machines;
- no silent side effects.

## 7. Scheduler

Custom scheduler:

- planner;
- dispatcher;
- reconciler;
- replanner.

Inputs:
- demand;
- supply;
- staff;
- machines;
- energy;
- water;
- maintenance;
- weather;
- orders.

Outputs:
- tasks;
- robot missions;
- harvest windows;
- packaging;
- refill;
- maintenance;
- irrigation;
- deferrable loads.

## 8. Forecasting

Demand:
- SKU/day/hour;
- stockout-aware;
- weather/season/events;
- uncertainty interval.

Supply:
- crop;
- planting;
- climate;
- harvest;
- quality;
- vision.

Models:
- simple baseline first;
- ML only if it improves measured error.

## 9. Smart retail

BOM-028 integration:

- smart crate;
- smart cart;
- sensor fusion;
- Stripe;
- paid-exit;
- inventory reconciliation.

Payment confirmation and physical sale are distinct states.

## 10. Edge

Edge gateway responsibilities:

- local protocol adapters;
- MQTT;
- OPC UA;
- Modbus;
- buffering;
- local timestamps;
- health;
- safe degradation.

No field device writes directly to central DB.

## 11. Security

- VLAN segmentation;
- RBAC;
- MFA;
- OIDC;
- service accounts;
- TLS/mTLS;
- secrets outside Git;
- no direct OT Internet;
- VPN admin;
- audit.

## 12. Backup/DR

Document:
- `SERVER_ACCEPTANCE_DR_RUNBOOK.md`.

Required:
- DB PITR;
- VM restore;
- offsite;
- NODE-A fail;
- NODE-B fail;
- QNODE fail;
- NATS R3 fail;
- edge replay;
- BESS transfer;
- Stripe delayed webhook.

## 13. Hardware benchmarks

Current public references:

- Dell PowerEdge T160 Smart Selection ~€4.793,77 + IVA base config;
- Pro Max 24 €405;
- Pro XG 10 PoE €629;
- Proxmox Basic 2 compute sockets €740/year;
- PBS Community €560/year if chosen.

Target server config remains RFQ.

## 14. Package

- `CENTRAL_ORCHESTRATION_SERVER.md`;
- `RFQ_CENTRAL_ORCHESTRATION_SERVER.md`;
- `EVENT_API_CONTRACTS.md`;
- `SERVER_ACCEPTANCE_DR_RUNBOOK.md`;
- `19_BOM_PRODOTTI_FORNITORI/AUTOMAZIONE_SERVER_CENTRALE.md`;
- `22_FONTI_NORME_PREVENTIVI/AUTOMAZIONE_SERVER_CENTRALE_SOURCES.md`.

## 15. Gate

Before purchase:

1. rack environment;
2. BESS transfer/autonomy;
3. compute sizing;
4. NVMe endurance;
5. backup retention;
6. offsite;
7. 10GbE topology;
8. RFQ;
9. restore test;
10. acceptance plan.