# BOM-030 — Event & API contracts

**Aggiornato:** 18 settembre 2026  
**Stato:** `CONTRACT BASELINE / SCHEMI APPLICATIVI DA IMPLEMENTARE E TESTARE`.

## 1. Obiettivo

Definire un contratto stabile fra:

- server centrale;
- edge gateway;
- PLC/controller;
- AMR/robot;
- Tech Barn;
- celle;
- vending/smart retail;
- Stripe;
- BESS/EMS;
- dashboard;
- scheduler;
- forecasting.

Principio:

- **command** = richiesta di fare qualcosa;
- **event** = fatto già accaduto;
- **query** = lettura dello stato.

Non mescolare i tre.

## 2. Event envelope

Ogni evento business usa almeno:

```json
{
  "event_id": "019...",
  "event_type": "inventory.lot.moved.v1",
  "occurred_at": "2026-09-18T10:00:00.123+02:00",
  "recorded_at": "2026-09-18T10:00:00.245+02:00",
  "source": "edge.techbarn.01",
  "actor": {
    "type": "device",
    "id": "scanner.pack.02"
  },
  "correlation_id": "019...",
  "causation_id": "019...",
  "schema_version": 1,
  "payload": {}
}
```

## 3. IDs

Use:

- UUIDv7 for server-generated event/entity IDs where practical;
- vendor/device serial only as external reference;
- never use mutable names as primary IDs.

Required IDs:

- asset_id;
- device_id;
- lot_id;
- container_id;
- task_id;
- mission_id;
- order_id;
- payment_id;
- customer_session_id;
- cart_id;
- batch_id;
- maintenance_work_order_id.

## 4. Time

Every device event carries:

- device timestamp;
- server receive timestamp;
- monotonic/source sequence when available;
- clock quality.

Fields:

```json
{
  "occurred_at": "...",
  "source_sequence": 145998,
  "clock_status": "SYNCED",
  "clock_offset_ms": 4.3
}
```

If clock invalid:
- event accepted with flag;
- no strict temporal correlation where unsafe;
- alert if source participates in smart-retail sensor fusion.

## 5. Event naming

Pattern:

`domain.entity.action.vN`

Examples:

- `crop.harvest.created.v1`;
- `inventory.lot.moved.v1`;
- `coldroom.temperature.excursion_started.v1`;
- `irrigation.zone.completed.v1`;
- `machine.mission.completed.v1`;
- `retail.cart.item_added.v1`;
- `payment.stripe.authorized.v1`;
- `energy.bess.mode_changed.v1`.

## 6. Commands

Pattern:

`domain.entity.command.vN`

Command envelope:

```json
{
  "command_id": "019...",
  "command_type": "irrigation.zone.start.v1",
  "requested_at": "...",
  "requested_by": "scheduler",
  "target_asset_id": "irrigation.zone.12",
  "expires_at": "...",
  "idempotency_key": "...",
  "preconditions": {},
  "payload": {}
}
```

Lifecycle:

`REQUESTED -> ACCEPTED/REJECTED -> STARTED -> COMPLETED/FAILED/EXPIRED`

## 7. Command safety

A local controller may reject a valid server command.

Example reasons:

- local interlock;
- E-stop;
- door open;
- pressure low;
- tank empty;
- maintenance mode;
- visitor lockout;
- animal zone occupied.

Server records rejection; it must not bypass safety locally.

## 8. Idempotency

All external side effects require idempotency.

Examples:
- Stripe PaymentIntent;
- refund;
- vending dispense;
- AMR mission create;
- irrigation batch;
- label print;
- customer order creation.

Rule:

same `idempotency_key` + same command = same logical operation.

## 9. NATS subjects

Working hierarchy:

- `evt.<domain>.<entity>.<action>.v1`;
- `cmd.<domain>.<entity>.<action>.v1`;
- `reply.<service>.<id>`;
- `telemetry.<domain>.<asset>.<metric>`.

Critical event streams:
- ORDER;
- PAYMENT;
- INVENTORY;
- LOT;
- TASK;
- COMMAND;
- AUDIT.

Telemetry high-rate streams may have lower retention/replication.

## 10. PostgreSQL business ledger

NATS is transport/persistence.

PostgreSQL stores the durable business ledger.

Minimum event table:

- event_id;
- event_type;
- occurred_at;
- recorded_at;
- source;
- actor_type;
- actor_id;
- correlation_id;
- causation_id;
- schema_version;
- payload_json;
- hash/checksum optional;
- ingest_status.

Append-only application policy.

Corrections create new events.

## 11. Master state vs events

Current state can be materialized.

Example:

- `asset_state_current`;
- `inventory_current`;
- `cart_current`;
- `task_current`.

Never mutate historical event rows to make current state look cleaner.

## 12. Device telemetry schema

Minimum:

```json
{
  "device_id": "sensor.greenhouse.c3.temp.01",
  "asset_id": "greenhouse.c3",
  "metric": "air_temperature",
  "value": 24.18,
  "unit": "degC",
  "quality": "GOOD",
  "occurred_at": "...",
  "source_sequence": 92201
}
```

Allowed quality:
- GOOD;
- SUSPECT;
- BAD;
- STALE;
- ESTIMATED.

## 13. Units

Store canonical SI/defined units.

Examples:
- °C;
- Pa/bar;
- L/min;
- m3;
- kg;
- kWh;
- W;
- %RH.

Never infer unit from device model.

Gateway normalizes vendor units.

## 14. Asset registry API

Endpoints working:

- `GET /api/v1/assets`;
- `GET /api/v1/assets/{id}`;
- `GET /api/v1/assets/{id}/state`;
- `GET /api/v1/assets/{id}/events`;
- `POST /api/v1/assets/{id}/commands`.

Writes require:
- RBAC;
- idempotency;
- audit.

## 15. Task API

Task object:

- task_id;
- type;
- location;
- skill;
- priority;
- earliest_start;
- deadline;
- estimated_duration;
- dependencies;
- assigned_to;
- status;
- actual start/end;
- reason code.

State:

`PLANNED -> READY -> ASSIGNED -> ACCEPTED -> IN_PROGRESS -> DONE/FAILED/CANCELLED`.

## 16. Scheduler contract

Input snapshots:
- demand forecast;
- supply forecast;
- workers;
- machines;
- assets;
- maintenance;
- energy;
- water;
- orders;
- weather;
- constraints.

Output:
- plan_id;
- plan_version;
- tasks;
- missions;
- reservations;
- reasons.

Every replan records:
- trigger;
- previous plan;
- new plan;
- delta.

## 17. AMR mission

Command:

```json
{
  "mission_id": "...",
  "origin": "greenhouse.c3.pickup",
  "destination": "techbarn.pack.in",
  "payload": {
    "container_ids": ["crate-001"]
  },
  "priority": 70,
  "deadline": "..."
}
```

Events:
- mission.accepted;
- mission.started;
- mission.arrived;
- mission.payload_confirmed;
- mission.completed;
- mission.failed.

## 18. Inventory movement

Every movement contains:

- lot_id;
- container_id;
- quantity;
- unit;
- from_location;
- to_location;
- reason;
- operator/device;
- timestamp.

Mass balance errors generate anomaly events.

## 19. Harvest lot

Created with:

- crop;
- variety;
- compartment;
- harvest time;
- gross/net weight;
- operator;
- quality grade;
- container IDs.

Links:
- packing batch;
- cold-room entry;
- retail lot;
- transformation batch.

## 20. Cold-chain events

Examples:

- temperature.sample;
- door.opened;
- excursion_started;
- excursion_ended;
- compressor_fault;
- product_hold_created;
- product_released;
- product_discarded.

Excursion event stores:
- threshold;
- duration;
- max/min;
- affected lots.

## 21. Smart crate event

Raw sensing event:

```json
{
  "crate_id": "crate.tomato.03",
  "sku_id": "tomato-premium",
  "lot_id": "lot-...",
  "mass_before_g": 10480,
  "mass_after_g": 9730,
  "delta_g": -750,
  "legal_for_trade": false,
  "quality": "GOOD"
}
```

This does not charge the customer by itself.

## 22. Smart cart event

```json
{
  "cart_id": "cart-02",
  "session_id": "...",
  "mass_before_g": 3520,
  "mass_after_g": 4268,
  "delta_g": 748,
  "zone": "retail.tomato",
  "quality": "GOOD"
}
```

Correlation engine uses crate/cart/time/location/vision.

## 23. Retail correlation result

```json
{
  "correlation_id": "...",
  "session_id": "...",
  "sku_id": "tomato-premium",
  "quantity_kg": 0.750,
  "confidence": 0.997,
  "measurement_source": "scale-LFT-03",
  "legal_for_trade": true,
  "unit_price": 4.90,
  "line_total": 3.68,
  "price_snapshot_id": "..."
}
```

If:
- confidence low;
- legal measurement missing for weight-priced SKU;

state = customer confirmation / blocking.

## 24. Cart state machine

`OPEN`
→ `SHOPPING`
→ `RECONCILING`
→ `READY_TO_PAY`
→ `PAYMENT_PENDING`
→ `PAID`
→ `EXIT_AUTHORIZED`
→ `CLOSED`.

Invalid transition attempts generate audit event.

## 25. Stripe event boundary

Server stores:
- Stripe PaymentIntent ID;
- amount;
- currency;
- local order ID;
- state;
- event/webhook ID;
- reconciliation state.

Never store raw card data.

Webhook handling:
- verify signature;
- deduplicate event ID;
- transactional state update;
- publish internal event after DB commit.

## 26. Payment/vend invariant

Invariant:

`order PAID != product delivered`.

For vending:
- payment confirmed;
- vend command;
- vend ack;
- close.

If vend fails:
- recovery/refund.

For smart retail:
- basket reconciled;
- payment;
- paid state;
- exit authorization.

## 27. BESS events

Telemetry:
- SOC;
- grid_available;
- battery_power;
- load_power;
- available_power;
- estimated_runtime.

Events:
- backup_mode_entered;
- low_soc;
- island_mode_entered;
- grid_restored.

Commands from scheduler can request:
- defer workload;
- stop noncritical compute jobs.

No server command may disable BESS safety protections.

## 28. Personnel

Do not publish sensitive HR detail broadly on event bus.

Task events contain only necessary:
- worker ID;
- task;
- status;
- timing.

Role/authorization data remain restricted.

## 29. Maintenance

Events:
- maintenance.due;
- work_order.created;
- work_order.started;
- part.consumed;
- work_order.completed;
- asset.returned_to_service.

Every spare consumption updates inventory.

## 30. Audit

Audit subject:
- permission change;
- login;
- admin action;
- manual override;
- price change;
- recipe change;
- release/hold;
- delete/export;
- security configuration.

Audit record stores:
- actor;
- IP/device;
- action;
- target;
- before/after references;
- result.

## 31. Versioning

Breaking schema change:
- new major event version.

Non-breaking:
- optional fields allowed;
- consumers must ignore unknown optional fields.

Do not silently change semantics of `v1`.

## 32. Schema repository

Repository path future:

`07_AUTOMAZIONE_DATI_AI/contracts/`

Contains:
- OpenAPI;
- AsyncAPI;
- JSON Schema/Protobuf;
- examples;
- test fixtures.

CI validates schemas and compatibility.

## 33. Consumer rule

Consumers must handle:
- duplicate message;
- out-of-order event where possible;
- retry;
- poison message;
- schema version mismatch.

Dead-letter/error channel records failure without silently dropping business event.

## 34. Privacy

Event payload minimizes:
- names;
- contact data;
- visitor data.

Use IDs and resolve personal data only in authorized service.

No facial recognition identity in retail event schemas.

## 35. Acceptance

Before production:

1. publish duplicate order event;
2. delayed message;
3. reordered telemetry;
4. invalid schema;
5. old schema consumer;
6. device clock drift;
7. Stripe duplicate webhook;
8. AMR retry;
9. smart-cart ambiguous event;
10. DB transaction rollback before event publish;
11. NATS replay;
12. edge offline buffer replay.

Target:
- no double charge;
- no double mission;
- no double inventory movement;
- no silently lost critical event.
