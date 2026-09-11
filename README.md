Backend engineer building ingestion and payments systems on TypeScript.
## @latinapalencia
I build APIs, queues, workers, and schema migrations for payment operations.
I own failure modes across RPC boundaries and make retries observable before they become user-visible.
I prioritize bounded queues, idempotent writes, and recovery paths that can be exercised under load.
I accept conservative dependency choices when they reduce operational ambiguity.
### 🛠 Tech & Infrastructure
- **Core:** TypeScript, Node.js, Express, gRPC
- **Data:** PostgreSQL, Redis, Kafka
- **Infra:** Docker, AWS ECS
- **Tooling:** ESLint, Vitest, pnpm
### ⚙️ Engineering Areas
- Payment APIs with idempotency keys and outbox patterns
- Kafka consumers with bounded concurrency and replay-safe checkpoints
- PostgreSQL schema migrations with compatibility windows
- Distributed tracing across RPCs, workers, and provider callbacks
### 🔭 Current Focus
- Reducing worker pile-ups by splitting backlog queues by payment provider.
- Reconciling outbox rows with idempotency records without increasing PostgreSQL locks.
- Replacing callback retries with a fixed-delay scheduler and bounded dead-letter retention.
- Mapping trace correlation across worker queues while keeping sampling costs predictable.
### 📌 Engineering Notes
- Tests should cover boundary failures, not just successful request paths.
- Schema additions should remain backward compatible until every reader catches up.
- Migrations need a rollback path, a lock budget, and an owner on call.
- Retries need deadlines, jitter, and a final record of why the operation stopped.
### 🧭 How I Work
- Keep ownership local: one component owns a state transition and its durable record.
- Prefer boring infrastructure with explicit failure modes over opaque abstractions.
- Document trade-offs next to the decision, not in a separate report.
*I keep systems recoverable, observable, and easy to reason about under failure.*
[Email](mailto:latinapalencia@gmail.com)