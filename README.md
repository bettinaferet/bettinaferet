**Platform reliability engineer building queue-backed ingestion services and the boundaries around them.**

## @bettinaferet

I build ingestion services around Kafka, Postgres, and HTTP APIs, with workers that make retries and schema evolution explicit. I own failure modes across queues, caches, and RPC calls, and I keep operational cost visible before a service reaches production. I prefer boring reliability: bounded queues, idempotent writes, clear ownership, and migrations that can be rolled back. The trade-off is slower initial delivery when a durable contract is cheaper than a fast workaround.

### 🛠 Tech & Infrastructure

**Core:** TypeScript, Node.js, TypeScript
**Data:** Kafka, Postgres, Redis
**Infra:** Docker, Terraform
**Tooling:** Jest, OpenTelemetry

### ⚙️ Engineering Areas


- Backpressure and replayable Kafka partitions for high-volume event ingestion
- Postgres schemas, indexes, and idempotency constraints for exactly-once effects
- TypeScript RPCs with typed envelopes, deadlines, and structured error codes
- Redis caches with explicit invalidation and bounded worker concurrency

### 🔭 Current Focus


- Draining a stalled Kafka topic without duplicating writes to Postgres
- Reducing cache stampedes with single-flight requests and short TTLs
- Adding trace-based latency breakdowns across RPCs and worker queues
- Designing a backward-compatible schema migration with a rollback path

### 📌 Engineering Notes

- Tests should cover queue redelivery, partial failures, and out-of-order events, not only happy paths.
- Boundaries need explicit contracts for retries, deadlines, and error classification.
- Migrations should be reversible and tested against the data shape the service actually holds.
- Errors belong in traces and metrics with stable labels, never in raw user-facing payloads.

### 🧭 How I Work


- Choose the smallest durable boundary that makes the next failure understandable.
- Prefer additive changes, observable rollout, and a rollback over a clever emergency fix.

*Reliable systems are made from small, reviewable contracts.*

[Email](mailto:bettinaferet3039449@gmail.com)