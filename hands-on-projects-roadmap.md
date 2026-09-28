# Hands-On Projects Roadmap: Build the System Design Roadmap (2026)

A parallel **build track** for [system-design-roadmap-2026.md](system-design-roadmap-2026.md). Twelve labs, in order, each one building the thing you learned that week and **measuring it**, so your design answers come from experience instead of from videos.

> **Everything runs locally in Docker. No cloud account, no bill, no free-tier surprises.** The only optional exception is Lab 9, where an LLM API key costs a few dollars — a local model works too.

---

## Why This Exists

The main roadmap teaches you to *say* "we'd add a cache here." This track is how you earn the right to say the next sentence: **"and when I did that, p99 went from 180 ms to 12 ms, until the cache expired all at once and I learned about stampedes."**

That second sentence is what separates a mid-level answer from a senior one, and it cannot be obtained by watching anything.

### The one rule: every lab produces a number

If a lab ends without a number in your [results log](#the-results-log), you did the lab wrong. You are not building products here. You are running **experiments** where the system is the subject. Every lab below has an **Experiment** section and an **Expected result**, so you know whether what you saw was real.

---

## Table of Contents

1. [How This Maps to the Main Roadmap](#how-this-maps-to-the-main-roadmap)
2. [Pick Your Intensity (and the Honest Hour Cost)](#pick-your-intensity-and-the-honest-hour-cost)
3. [How to Fit It Into 16 Weeks](#how-to-fit-it-into-16-weeks)
4. [Setup: Do This Once](#setup-do-this-once)
5. [The Lab Index](#the-lab-index)
6. [Lab 0: The Baseline Service](#lab-0-the-baseline-service-weeks-12)
7. [Lab 1: URL Shortener Under Load](#lab-1-url-shortener-under-load-weeks-34)
8. [Lab 2: Replication and Sharding](#lab-2-replication-and-sharding-week-5)
9. [Lab 3: The Async Pipeline](#lab-3-the-async-pipeline-week-6)
10. [Lab 4: The Transactions Lab](#lab-4-the-transactions-lab-week-7)
11. [Lab 5: Distributed Key-Value Store](#lab-5-distributed-key-value-store-weeks-89)
12. [Lab 6: The Resilience Lab](#lab-6-the-resilience-lab-week-10)
13. [Lab 7: Observability, SLOs and Geo](#lab-7-observability-slos-and-geo-week-11)
14. [Lab 8: Money — Ledger and Inventory](#lab-8-money--ledger-and-inventory-week-12)
15. [Lab 9: RAG and an LLM Gateway](#lab-9-rag-and-an-llm-gateway-week-13)
16. [Lab 10: Streams, CDC and Top-K](#lab-10-streams-cdc-and-top-k-week-14)
17. [Lab 11: The Capstone](#lab-11-the-capstone-weeks-1516)
18. [The Parallel LLD Skeleton](#the-parallel-lld-skeleton-weeks-313)
19. [The Results Log](#the-results-log)
20. [The Lab README Template](#the-lab-readme-template)
21. [What Not to Build](#what-not-to-build)
22. [Turning This Into Your "System I Built" Story](#turning-this-into-your-system-i-built-story)
23. [Definition of Done](#definition-of-done)

---

## How This Maps to the Main Roadmap

Each lab is timed to land in the same week as the theory that explains it and **immediately before** the practice problems that need it. The order is fixed for the same reason the main roadmap's order is fixed: you cannot build a quorum before you have seen a replica.

| Lab | Week | Follows theory | Feeds practice problems |
|---|---|---|---|
| [0 Baseline service](#lab-0-the-baseline-service-weeks-12) | 1–2 | Phase 0 | Everything after it |
| [1 URL shortener under load](#lab-1-url-shortener-under-load-weeks-34) | 3–4 | 1.1–1.4 scaling, LB, caching, CDN | #1 URL shortener, #3 Rate limiter |
| [2 Replication and sharding](#lab-2-replication-and-sharding-week-5) | 5 | 1.5 databases | #2, #9, and every sharding deep dive |
| [3 The async pipeline](#lab-3-the-async-pipeline-week-6) | 6 | 1.6 queues and streams | #5 Notifications, #6 Counter |
| [4 The transactions lab](#lab-4-the-transactions-lab-week-7) | 7 | 2A transactions and isolation | #15 Ticketmaster, #19 Payments, #20 Flash sale |
| [5 Distributed key-value store](#lab-5-distributed-key-value-store-weeks-89) | 8–9 | Phase 3 replication, quorums, consensus | #9 Distributed cache, #25 Message queue |
| [6 The resilience lab](#lab-6-the-resilience-lab-week-10) | 10 | Phase 4 resilience patterns | Every "what if this dies" follow-up |
| [7 Observability, SLOs and geo](#lab-7-observability-slos-and-geo-week-11) | 11 | Phase 5 + 2B geo | #16 Uber, #17 Yelp |
| [8 Money: ledger and inventory](#lab-8-money--ledger-and-inventory-week-12) | 12 | Idempotency and ledgers | #19 Payments, #20 Flash sale, #15 Ticketmaster |
| [9 RAG and an LLM gateway](#lab-9-rag-and-an-llm-gateway-week-13) | 13 | Phase 10 + 2B vectors | #35 RAG, #36 LLM gateway |
| [10 Streams, CDC and Top-K](#lab-10-streams-cdc-and-top-k-week-14) | 14 | 2B stream processing and CDC | #27 Top-K, #28 Ad click aggregator |
| [11 Capstone](#lab-11-the-capstone-weeks-1516) | 15–16 | Phase 11 | Your project deep dive |

This track **replaces** the main roadmap's two build sections rather than adding to them: the [Phase 0 hands-on](system-design-roadmap-2026.md#hands-on-do-not-skip) app is Lab 0, and [Phase 11's "build to learn"](system-design-roadmap-2026.md#build-to-learn-pick-23) list is expanded into Labs 1, 3, 5 and 9.

---

## Pick Your Intensity (and the Honest Hour Cost)

**Read this before you commit.** The main roadmap is already a full 10–12 hours a week, and every hour in it is allocated. Building is not free, and a track that pretends otherwise will collapse in week 4.

| Intensity | Labs | Extra hours/week | Combined load | Choose it when |
|---|---|---|---|---|
| **Lean** | 0, 1, 3, 6, 9 + a small capstone | +2 | 12–14 h | An interview is scheduled, or you already build backends for a living |
| **Core (recommended)** | All 12, skipping every stretch | +4–5 | 15–17 h | You have the time and want the depth to actually show |
| **Full** | All 12 plus stretches | +7–8 | 18–20 h | You're targeting infra/platform roles, or you're between jobs |

**Total build hours:** Lean ≈ 30 h · Core ≈ 72 h · Full ≈ 110 h.

**My recommendation:** start at **Core** and drop to **Lean** the first week you miss a mock. Mocks and practice problems always win; a half-built lab still taught you something, a skipped mock taught you nothing.

**If you can only ever do two labs,** do [Lab 0](#lab-0-the-baseline-service-weeks-12) and [Lab 6](#lab-6-the-resilience-lab-week-10). Lab 0 makes every component concrete; Lab 6 is where the operations and failure-mode answers that 2026 rubrics grade actually come from.

---

## How to Fit It Into 16 Weeks

Building is a *substitute* for some watching, not an addition to it. Three hours of building the async pipeline will teach you more about delivery semantics than three hours of video. Use these swaps against [The Straight Path](system-design-roadmap-2026.md#the-straight-path-every-link-in-order):

| Week | Swap out (Straight Path step) | Swap in | Net |
|---|---|---|---|
| 4 | Step 23, Jordan on caching (1 h) | Lab 1's stampede experiment | −1 h |
| 5 | Step 28, Jordan on partitioning (1.5 h) | Lab 2 (watch it *after* you break it) | −1.5 h |
| 6 | Step 35, Jordan on Kafka internals (1.5 h) | Lab 3 | −1.5 h |
| 7 | Step 42, Hermitage *(already optional)* | Lab 4 — Hermitage's point, run by you | −0.75 h |
| 10 | Nothing. Keep all the reading | Lab 6 | +5 h |
| 14 | Step 95, Jordan on stream processing (2 h) | Lab 10 | −2 h |

**Rules for the combined track:**

1. **Theory first, build second, problem third.** Within a week: read/watch it, build it, then solve the problem that uses it. The build is the bridge.
2. **Timebox hard.** Every lab below has a time budget. When it runs out, write down where you got to and move on. An unfinished lab with a recorded result beats a perfect lab that ate your mock.
3. **Never trade away a mock or a practice problem.** Those are the interview. This track is the evidence.
4. **Skip Lab 5 and Lab 10 first** if you fall behind — they are the two most expensive and the most substitutable by reading.
5. **Use your buffer week on a lab, not on catching up theory.** Theory catches up by itself during problems; builds don't.

---

## Setup: Do This Once

### Tooling

| Tool | Why | Install |
|---|---|---|
| Docker + Docker Compose | Every lab runs in containers | [docs.docker.com/get-started](https://docs.docker.com/get-started/) |
| A language you're fast in | Go, Python, TypeScript, Java, C++ — it genuinely does not matter | — |
| [k6](https://k6.io/) | Load testing with thresholds. Every measurement comes from here | `docker run` works; native binary is nicer |
| [Excalidraw](https://excalidraw.com/) | The architecture diagram in each lab README | Browser |
| `psql`, `redis-cli` | You will live in these | Ship with the containers |

### Repo layout

One repo, one directory per lab, one shared infrastructure file. This becomes a portfolio artifact, so treat the READMEs as part of the work.

```text
system-design-labs/
  docker-compose.yml        # all infrastructure, profiles per lab
  README.md                 # the results log + links to each lab
  load/                     # k6 scripts, shared
    smoke.js
    baseline.js
  lab00-baseline/
    README.md               # architecture, decisions, measurements, what broke
    src/
  lab01-shortener/
  lab02-replication/
  ...
  lab11-capstone/
```

### The shared `docker-compose.yml`

Use Compose **profiles** so each lab starts only what it needs (`docker compose --profile lab03 up -d`). This is the single most useful setup decision in the whole track — without it you will be running fourteen containers by week 10 and blaming your laptop.

```yaml
services:
  postgres:
    image: postgres:16
    profiles: ["core", "lab00", "lab01", "lab04", "lab08", "lab10"]
    environment:
      POSTGRES_USER: app
      POSTGRES_PASSWORD: apppass
      POSTGRES_DB: labs
    ports: ["5432:5432"]
    # Lab 10 needs logical decoding; harmless everywhere else.
    command: ["postgres", "-c", "wal_level=logical"]

  redis:
    # redis-stack adds Bloom filters and Count-Min Sketch (Labs 1, 10).
    image: redis/redis-stack:latest
    profiles: ["core", "lab01", "lab03", "lab07", "lab10"]
    ports: ["6379:6379", "8001:8001"]   # 8001 = RedisInsight UI

  # --- Lab 2: streaming replication, primary + replica (official images) ---
  # The replica's data directory is seeded once with pg_basebackup;
  # see Lab 2's build steps. Using official images keeps this independent
  # of third-party image repackaging.
  pg-primary:
    image: postgres:16
    profiles: ["lab02"]
    environment:
      POSTGRES_USER: app
      POSTGRES_PASSWORD: apppass
      POSTGRES_DB: labs
    command:
      - postgres
      - -c
      - wal_level=replica
      - -c
      - max_wal_senders=4
      - -c
      - hot_standby=on
    volumes: ["pgprimary:/var/lib/postgresql/data"]
    ports: ["5433:5432"]

  pg-replica:
    image: postgres:16
    profiles: ["lab02"]
    depends_on: [pg-primary]
    environment:
      POSTGRES_USER: app
      POSTGRES_PASSWORD: apppass
    volumes: ["pgreplica:/var/lib/postgresql/data"]
    ports: ["5434:5432"]

  # --- Lab 3, 10: Kafka API without the weight of Kafka ---
  redpanda:
    image: redpandadata/redpanda:latest
    profiles: ["lab03", "lab10"]
    # Flags use = so each list item is a single argv element.
    command:
      - redpanda
      - start
      - --mode=dev-container
      - --smp=1
      - --kafka-addr=PLAINTEXT://0.0.0.0:9092
      - --advertise-kafka-addr=PLAINTEXT://redpanda:9092
    ports: ["9092:9092"]

volumes:
  pgprimary:
  pgreplica:

  # --- Lab 6: fault injection ---
  toxiproxy:
    image: ghcr.io/shopify/toxiproxy
    profiles: ["lab06"]
    ports: ["8474:8474", "15432:15432", "16379:16379"]

  # --- Lab 7: observability ---
  prometheus:
    image: prom/prometheus
    profiles: ["lab07"]
    volumes: ["./lab07-observability/prometheus.yml:/etc/prometheus/prometheus.yml"]
    ports: ["9090:9090"]

  grafana:
    image: grafana/grafana
    profiles: ["lab07"]
    environment:
      GF_AUTH_ANONYMOUS_ENABLED: "true"
      GF_AUTH_ANONYMOUS_ORG_ROLE: Admin
    ports: ["3000:3000"]

  jaeger:
    image: jaegertracing/all-in-one
    profiles: ["lab07"]
    environment:
      COLLECTOR_OTLP_ENABLED: "true"
    ports: ["16686:16686", "4317:4317", "4318:4318"]
```

### The k6 template you'll reuse everywhere

Thresholds are the point. A load test without a threshold is a number you'll rationalize; a threshold either passes or fails.

```js
// load/baseline.js
import http from 'k6/http';
import { check } from 'k6';

export const options = {
  stages: [
    { duration: '30s', target: 50 },   // ramp
    { duration: '2m',  target: 50 },   // steady — read your numbers HERE
    { duration: '30s', target: 0 },
  ],
  thresholds: {
    http_req_failed:   ['rate<0.01'],           // <1% errors
    http_req_duration: ['p(95)<150', 'p(99)<400'],
  },
};

export default function () {
  const res = http.get(`${__ENV.BASE_URL}/api/items/42`);
  check(res, { 'status 200': (r) => r.status === 200 });
}
```

Run it: `k6 run -e BASE_URL=http://localhost:8080 load/baseline.js`

**Read the steady-state window, not the ramp.** And record `p(95)`, `p(99)`, throughput and error rate every single time — those four numbers are your evidence.

---

## The Lab Index

| # | Lab | Time | The claim it earns you |
|---|---|---|---|
| 0 | [Baseline service](#lab-0-the-baseline-service-weeks-12) | 5 h | "I've measured what a cache actually does to p99" |
| 1 | [URL shortener under load](#lab-1-url-shortener-under-load-weeks-34) | 6 h | "I've caused a cache stampede and fixed it two ways" |
| 2 | [Replication and sharding](#lab-2-replication-and-sharding-week-5) | 4 h | "I've watched replication lag serve a user their own stale write" |
| 3 | [The async pipeline](#lab-3-the-async-pipeline-week-6) | 5 h | "I've double-charged a customer with at-least-once delivery, then made it idempotent" |
| 4 | [The transactions lab](#lab-4-the-transactions-lab-week-7) | 3 h | "I've reproduced write skew and lost updates, and I know which isolation level stops each" |
| 5 | [Distributed key-value store](#lab-5-distributed-key-value-store-weeks-89) | 8 h | "I've implemented consistent hashing and R+W>N quorums" |
| 6 | [The resilience lab](#lab-6-the-resilience-lab-week-10) | 5 h | "I've triggered a retry storm and stopped it with jitter and a circuit breaker" |
| 7 | [Observability, SLOs and geo](#lab-7-observability-slos-and-geo-week-11) | 6 h | "I've defined an SLO, burned its error budget, and traced a slow request across services" |
| 8 | [Money: ledger and inventory](#lab-8-money--ledger-and-inventory-week-12) | 6 h | "I've oversold inventory under concurrency and fixed it without a global lock" |
| 9 | [RAG and an LLM gateway](#lab-9-rag-and-an-llm-gateway-week-13) | 8 h | "I've measured retrieval quality and cut LLM cost with semantic caching" |
| 10 | [Streams, CDC and Top-K](#lab-10-streams-cdc-and-top-k-week-14) | 6 h | "I've read the WAL directly and computed Top-K with a sketch" |
| 11 | [Capstone](#lab-11-the-capstone-weeks-1516) | 10 h | Your project deep dive, with real numbers |

---

## Lab 0: The Baseline Service (Weeks 1–2)

**Maps to:** Phase 0 · Straight Path step 10 · replaces [the Phase 0 hands-on](system-design-roadmap-2026.md#hands-on-do-not-skip)
**Time:** 5 h · **Profile:** `--profile lab00`

**Why this one is non-negotiable:** every abstraction in the next 15 weeks — connection pools, p99, cache hit ratio, index cost — becomes a thing you have *seen* rather than a thing you've read. Do not skip it even if you build backends daily; the measurement discipline is the point, not the CRUD.

### Build

1. **A REST API with four endpoints** over one table (`items`): `POST /api/items`, `GET /api/items/:id`, `GET /api/items?cursor=&limit=`, `DELETE /api/items/:id`.
2. **Postgres**, with a schema you wrote by hand. No ORM auto-migration for this one — you want to see the DDL.
3. **Seed 1,000,000 rows.** This matters. At 1,000 rows every query is fast and you learn nothing.
   ```sql
   INSERT INTO items (name, payload, created_at)
   SELECT 'item-' || g, repeat('x', 200), now() - (g || ' seconds')::interval
   FROM generate_series(1, 1000000) g;
   ```
4. **Connection pooling** with a pool size you chose deliberately (start at 10) and can defend.
5. **Redis cache-aside on `GET /api/items/:id`** with a 60-second TTL, plus a `/metrics`-style counter for hits and misses so you can compute hit ratio.
6. **A `GET /api/slow` endpoint** that runs an unindexed query — you'll need something genuinely slow later.

### Experiment

Run the k6 template four times, changing exactly one thing each time. **One variable per run** or the numbers mean nothing.

| Run | Configuration | Record |
|---|---|---|
| A | Cache on | p95, p99, throughput, hit ratio |
| B | Cache off (bypass Redis in code) | p95, p99, throughput |
| C | Cache off, and drop the index on the queried column (`DROP INDEX`) | p99, and the query plan |
| D | Cache on, pool size 2 instead of 10 | p99, error rate |

For run C, get the plan before and after:
```sql
EXPLAIN (ANALYZE, BUFFERS) SELECT * FROM items WHERE id = 500000;
```

### Expected result

- **A vs B:** a large p99 drop with the cache on — commonly an order of magnitude on a warm cache, since you're comparing a Redis round trip against a Postgres round trip plus query execution.
- **C:** the plan changes from an index scan to a sequential scan over a million rows, and p99 degrades dramatically. This is the "index speeds up reads" checkpoint, felt rather than recited.
- **D:** p99 rises sharply and you may start seeing timeouts or pool-exhaustion errors, while *throughput barely changes*. This is your first encounter with queueing: the bottleneck moved out of the database and into waiting for a connection.

### Done when

- [ ] Four runs recorded in the [results log](#the-results-log) with all four numbers each
- [ ] You can explain run D's shape — why latency exploded but throughput didn't
- [ ] Your README has a five-box architecture diagram
- [ ] `docker compose --profile lab00 up -d` and a seed command is all a stranger needs

### Journal entry

Write the answer to: *what did the cache cost me?* (Staleness window, an extra dependency, invalidation complexity.) You just bought a 10× latency win for a 60-second consistency compromise. That trade is the shape of half of system design.

### Stretch

Add a second app instance and put Nginx in front. Measure whether p99 improves (it probably won't much — you're database-bound, not app-bound). Learning that horizontal scaling doesn't help a database bottleneck is worth an hour.

---

## Lab 1: URL Shortener Under Load (Weeks 3–4)

**Maps to:** Phases 1.1–1.4 · problems #1, #3 · Straight Path steps 20–26
**Time:** 6 h (3 h per week) · **Profile:** `--profile lab01`

### Build

**Week 3 — the service and the load balancer:**

1. `POST /shorten` → base-62 encode a unique ID. Use a **Snowflake-style ID**: `timestamp | worker_id | sequence`. Do not use a random string with a uniqueness retry loop; you want to feel why coordination-free IDs exist.
2. `GET /:code` → **302** redirect. Write a comment in the code justifying 302 over 301: a 301 is cached by browsers forever, which kills your analytics and makes the mapping unchangeable.
3. Cache-aside on the redirect path, TTL 300 s.
4. **Two app instances behind Nginx**, round robin. Make both stateless — verify by killing one mid-test and confirming the test keeps passing.

**Week 4 — the rate limiter:**

5. A **token bucket in Redis, atomic via Lua.** The non-atomic version is the whole lesson — build it wrong first:
   ```
   -- WRONG: read-modify-write, two round trips, races under concurrency
   GET  bucket:{user}
   SET  bucket:{user} <new>
   ```
   Then fix it with a single `EVAL` script that reads tokens and last-refill, computes the refill, decrements and writes — all inside one Redis execution.
6. Return `429` with `Retry-After` and `X-RateLimit-Remaining` headers.

### Experiment

**E1 — Cache stampede.** Set the TTL to 60 s, drive 200 concurrent virtual users at **one single hot code**, and watch the database at the expiry boundary:
```sql
SELECT count(*) FROM pg_stat_activity WHERE state = 'active';
```
Then fix it twice and re-measure:
- **Per-key lock:** `SET lock:{code} 1 NX EX 5` — one request refills, the rest briefly serve stale or wait.
- **Jittered TTL:** `TTL = 300 + rand(0..60)` so a million keys don't expire in the same second.

**E2 — Rate limiter correctness.** Set a limit of 10 requests/second for one user, then fire 100 concurrent requests. Count how many got `200`.

**E3 — Hit ratio vs latency.** Run with Zipf-ish traffic (80% of requests to 20% of codes), then uniform traffic. Record hit ratio and p99 for each.

### Expected result

- **E1:** with the naive version you see a spike of concurrent database queries at the TTL boundary — every in-flight request missing at once. Both fixes flatten it; the lock flattens it harder, the jitter scales better across many keys.
- **E2:** the **non-atomic limiter lets through noticeably more than 10** — that gap is the race, and it's the exact reason interviewers ask "how do you make that atomic?". The Lua version lets through exactly 10 (plus the bucket's burst allowance, if you implemented one).
- **E3:** skewed traffic gives a much higher hit ratio and much better p99 than uniform traffic at the same cache size. This is why "what's the access distribution?" is a real requirements question.

### Done when

- [ ] E2 shows a concrete number for the broken limiter (e.g. "34 of 100 passed when 10 should have") — this is one of the best stories in the whole track
- [ ] Stampede spike measured before and after, both fixes
- [ ] You can state your short-code length and justify it with the [estimation math](system-design-roadmap-2026.md#worked-example-url-shortener)
- [ ] One instance killed mid-load-test without failing the k6 thresholds

### Journal entry

Where does the rate limiter belong — gateway or service? You just built it in the service. Write down what changes if it moves to the gateway (shared state across services, one more hop, harder per-endpoint rules).

### Stretch

Add negative caching for codes that don't exist, then a Bloom filter (`BF.ADD` / `BF.EXISTS` in redis-stack) in front of it. Measure how many pointless database lookups the filter saves under a load of random 404s — this is cache penetration, defeated.

---

## Lab 2: Replication and Sharding (Week 5)

**Maps to:** Phase 1.5 · every sharding deep dive
**Time:** 4 h · **Profile:** `--profile lab02`

### Build

1. **Bring up the primary, then seed the replica from it.** Streaming replication is a physical copy, so the replica's data directory starts as a base backup of the primary — this three-step bootstrap is the part most tutorials hide behind a magic image, and it's worth doing once by hand.

   ```bash
   docker compose --profile lab02 up -d pg-primary

   # 1. a replication role on the primary
   docker compose exec pg-primary psql -U app -d labs -c \
     "CREATE ROLE repl WITH REPLICATION LOGIN PASSWORD 'replpass';"

   # 2. allow it to connect (official image's pg_hba needs one line)
   docker compose exec pg-primary bash -c \
     "echo 'host replication repl all md5' >> /var/lib/postgresql/data/pg_hba.conf"
   docker compose exec pg-primary psql -U app -d labs -c "SELECT pg_reload_conf();"

   # 3. base backup into the replica's empty volume.
   #    -R writes standby.signal + primary_conninfo for you.
   docker compose run --rm --entrypoint bash pg-replica -c \
     "rm -rf /var/lib/postgresql/data/* && \
      PGPASSWORD=replpass pg_basebackup -h pg-primary -U repl \
        -D /var/lib/postgresql/data -Fp -Xs -R -P"

   docker compose --profile lab02 up -d pg-replica
   ```

   Verify it took: `docker compose exec pg-replica psql -U app -d labs -c "SELECT pg_is_in_recovery();"` must return `t`. A write attempted on the replica must fail with *cannot execute INSERT in a read-only transaction* — try it, so you know what a reader hitting a replica by mistake looks like.

2. Point your Lab 0 service's **writes at the primary (port 5433) and reads at the replica (5434)**.
3. Add `GET /api/items/:id?consistency=strong` that routes to the primary, so you have both behaviors available.
4. **Application-level sharding:** two separate Postgres databases, route by `hash(user_id) % 2`. Write a `shard_for(user_id)` function and a query that has to hit both shards.

### Experiment

**E1 — Read-your-writes violation.** Write a row to the primary, then immediately read it from the replica in a tight loop. Under write load, you will read stale data or nothing at all.

Watch the lag from both sides:
```sql
-- On the primary: how far behind is each replica?
SELECT client_addr, state, sent_lsn, replay_lsn, replay_lag
FROM pg_stat_replication;

-- On the replica: how old is the newest data I have?
SELECT now() - pg_last_xact_replay_timestamp() AS replication_delay;
```

**E2 — Make lag visible.** Hammer the primary with writes (k6 against `POST`) while running E1. Record peak `replay_lag`.

**E3 — The scatter-gather cost.** With your two shards, run "give me the 20 most recent items across all users" and compare it to the same query on one shard. You have to query both, merge and re-sort in the application.

**E4 — The hot shard.** Route 90% of your load to user IDs that hash to shard 0. Measure both shards' CPU.

### Expected result

- **E1/E2:** under sustained writes, lag becomes clearly measurable — and your own read-after-write breaks. **This is the single most useful thing in this lab**, because "how do you handle read-your-writes?" is asked constantly and you'll have an answer with a number in it.
- **E3:** the cross-shard query is dramatically more expensive and more code, and `LIMIT 20` has to become "fetch 20 from *each* shard, merge, take 20." This is exactly the main roadmap's checkpoint question — *you shard posts by `user_id`, how do you serve "all posts from the last hour"?* — and now you've felt why the answer is usually "a separate read model."
- **E4:** one shard saturates while the other idles. A bad shard key doesn't degrade gracefully, it just moves your bottleneck.

### Done when

- [ ] Peak replication lag recorded under write load
- [ ] Three fixes for read-your-writes written down: read from primary after write, sticky routing for N seconds, or wait-for-LSN
- [ ] Cross-shard query implemented and its cost recorded
- [ ] Hot-shard CPU asymmetry recorded

### Journal entry

You now have direct evidence for the most common sharding mistake: choosing the key that's convenient for writes and discovering it's wrong for reads. Write down your resharding plan — how would you go from 2 shards to 4 without downtime? (Consistent hashing, or double-write plus backfill plus cutover.)

### Stretch

Implement **consistent hashing with virtual nodes** for shard routing instead of modulo, then add a third shard. Count how many keys move under each scheme. Modulo moves roughly everything; consistent hashing moves roughly 1/N. That number is a great interview answer.

---

## Lab 3: The Async Pipeline (Week 6)

**Maps to:** Phase 1.6 · problems #5, #6
**Time:** 5 h · **Profile:** `--profile lab03`

Build this **twice** — once on Redis Streams, once on the Kafka API via Redpanda. The comparison is the lesson, and it maps directly to [cheat sheet F](system-design-roadmap-2026.md#f-message-queue-vs-log-based-stream).

### Build

**Part A — Redis Streams (2 h).** A notification pipeline: `POST /notify` enqueues, a worker consumes and "sends" (log it), with a consumer group.
```
XADD    notifications * user_id 42 channel email body "hello"
XREADGROUP GROUP senders worker-1 COUNT 10 BLOCK 5000 STREAMS notifications >
XACK    notifications senders <id>
XPENDING notifications senders          # what's in flight or stuck
XAUTOCLAIM notifications senders worker-2 60000 0   # steal from a dead worker
```

**Part B — Kafka API via Redpanda (2 h).** The same pipeline on a partitioned log. Use 3 partitions, key by `user_id`, and run 2 then 3 then 4 consumers in one group.

**Part C — Make it correct (1 h).**
1. A worker that **crashes after doing the work but before acknowledging** (`process(); crash(); ack()` — literally `os.Exit(1)`).
2. Then make it idempotent: a `processed_messages` table with the message ID as the **primary key**, inserted in the same transaction as the side effect. A duplicate hits a unique-violation and is safely skipped.
3. A **dead-letter queue**: after 3 failed attempts, move the message aside with its error and attempt count.
4. A **poison message**: one that always throws. Confirm it lands in the DLQ instead of blocking the partition forever.

### Experiment

**E1 — At-least-once, felt.** Run the crashing worker. Count how many times the notification was "sent" for a single message.

**E2 — Idempotency.** Same test with the dedupe table. Count again.

**E3 — Consumer group rebalancing.** With 3 partitions, run 2 consumers, then 3, then 4. Record which partitions each consumer owns, and the throughput each time.

**E4 — Ordering.** Publish messages for the same `user_id` and confirm they're processed in order. Then publish across different keys and confirm that ordering is *not* guaranteed globally.

### Expected result

- **E1:** the message is delivered more than once — usually repeatedly, since it's redelivered after every crash. This is "exactly-once delivery doesn't exist," demonstrated in about four lines of code.
- **E2:** the side effect happens exactly once no matter how many times it's delivered. You've just built the answer to the main roadmap's payment question — *how do you avoid double-charging if the consumer crashes after charging but before acknowledging?*
- **E3:** the **4th consumer sits completely idle**. Partitions cap consumer parallelism, which is why partition count is a capacity decision you make up front.
- **E4:** per-key ordering holds, global ordering does not.

### Done when

- [ ] Both implementations work, and you can name three concrete differences from having built them
- [ ] Duplicate delivery count recorded before and after the dedupe table
- [ ] The idle 4th consumer observed
- [ ] A poison message sitting in your DLQ with its error and attempt count

### Journal entry

Queue or log — which would you pick for notifications, and why? (Probably a queue: you don't need replay, you do need competing workers.) And for an audit trail? (A log: you need replay and multiple independent consumers.) You've now earned both answers.

### Stretch

Add **backpressure**: when the queue depth exceeds N, have `POST /notify` return `429`. Then measure what happens without it — let the queue grow unboundedly under load and watch memory. Unbounded queues are a latency bug disguised as a reliability feature.

---

## Lab 4: The Transactions Lab (Week 7)

**Maps to:** Phase 2A · problems #15, #19, #20
**Time:** 3 h · **Profile:** `--profile lab00` (just Postgres)

The cheapest lab here and one of the highest value. No application code at all — **two `psql` sessions side by side.** Open two terminals now.

### Part 1: Lost update (Read Committed)

```sql
-- setup
CREATE TABLE counters (id int PRIMARY KEY, n int);
INSERT INTO counters VALUES (1, 0);
```

| Session A | Session B |
|---|---|
| `BEGIN;` | |
| `SELECT n FROM counters WHERE id=1;` → 0 | |
| | `BEGIN;` |
| | `SELECT n FROM counters WHERE id=1;` → 0 |
| `UPDATE counters SET n=1 WHERE id=1;` | |
| `COMMIT;` | |
| | `UPDATE counters SET n=1 WHERE id=1;` |
| | `COMMIT;` |

`SELECT n FROM counters;` → **1, not 2.** Two increments, one survived. That's a lost update, and it's how like-counters silently under-count.

**Now fix it three ways** and note what each costs:
1. **Atomic write:** `UPDATE counters SET n = n + 1 WHERE id = 1;` — no read-modify-write, no race. Cheapest, but only works when the new value is a pure function of the old.
2. **Pessimistic:** `SELECT n FROM counters WHERE id=1 FOR UPDATE;` — B blocks until A commits. Correct, but serializes and can deadlock.
3. **Optimistic:** add a `version` column, then `UPDATE ... WHERE id=1 AND version=<read version>`; if zero rows updated, retry. No blocking, but you must handle the retry.

### Part 2: Write skew (Repeatable Read)

Postgres's `REPEATABLE READ` is snapshot isolation, which does **not** prevent write skew. The classic on-call example:

```sql
CREATE TABLE doctors (id int PRIMARY KEY, name text, on_call boolean);
INSERT INTO doctors VALUES (1,'Alice',true), (2,'Bob',true);
```

| Session A | Session B |
|---|---|
| `BEGIN ISOLATION LEVEL REPEATABLE READ;` | `BEGIN ISOLATION LEVEL REPEATABLE READ;` |
| `SELECT count(*) FROM doctors WHERE on_call;` → 2 | `SELECT count(*) FROM doctors WHERE on_call;` → 2 |
| *"2 on call, safe for me to leave"* | *"2 on call, safe for me to leave"* |
| `UPDATE doctors SET on_call=false WHERE id=1;` | `UPDATE doctors SET on_call=false WHERE id=2;` |
| `COMMIT;` | `COMMIT;` |

`SELECT count(*) FROM doctors WHERE on_call;` → **0.** Both transactions committed, each was individually correct, and the invariant "at least one doctor on call" is broken. They never touched the same row, so row locks would not have helped.

**Now re-run the whole thing with `BEGIN ISOLATION LEVEL SERIALIZABLE;`.** One transaction fails with `could not serialize access due to read/write dependencies among transactions`. That error message is the price of serializability: **your application must be prepared to retry.**

### Part 3: Phantoms and the shape of the fix

Repeat with a range query (`SELECT count(*) FROM bookings WHERE room=1 AND date BETWEEN ...`) and two inserts — the double-booking bug. Note that the fix is either `SERIALIZABLE`, or a constraint the database can enforce for you (an exclusion constraint on a range).

### Expected result

Exactly as written above: `1` instead of `2`, and `0` doctors on call. These are deterministic — if you don't see them, your isolation level isn't what you think it is. Check with `SHOW transaction_isolation;`.

### Done when

- [ ] Lost update reproduced, then fixed three ways, with the cost of each written down
- [ ] Write skew reproduced under `REPEATABLE READ` and prevented under `SERIALIZABLE`
- [ ] You've seen and can quote the serialization-failure error
- [ ] You can explain why row-level locking doesn't fix write skew

### Journal entry

This lab is the foundation of Labs 8's inventory problem and of problems #15, #19 and #20. Write down your default: **which isolation level do you reach for, and when do you escalate?** A good answer: Read Committed plus atomic writes and explicit locks where invariants matter; Serializable for the few flows where an invariant spans rows, with retry logic.

### Stretch

Run [Hermitage](https://github.com/ept/hermitage)'s test suite against Postgres and MySQL and compare. Isolation-level *names* mean different things in different databases — that's a genuinely senior observation.

---

## Lab 5: Distributed Key-Value Store (Weeks 8–9)

**Maps to:** Phase 3 · problems #9, #25
**Time:** 8 h (4 h per week) · **The most expensive lab. Drop this one first if you're behind.**

Three processes on your laptop, talking over HTTP. No frameworks.

### Build

**Week 8 — partitioning and replication (4 h):**

1. **A node**: an in-memory map behind `GET /kv/:key`, `PUT /kv/:key`, plus `GET /internal/kv/:key` for peer reads.
2. **A consistent hash ring** with **150 virtual nodes per physical node**. `ring.nodes_for(key, n=3)` returns the 3 replicas.
3. **A coordinator**: any node can take a request, hash the key, and fan out to the replica set.
4. **Quorum reads and writes** with configurable N, R, W. Write succeeds at W acks; read returns once R respond, with the highest-version value winning.
5. **Versioning:** store `(value, version, node_id)`. Start with last-write-wins by version counter.

**Week 9 — failure and coordination (4 h):**

6. **Kill a node** and verify reads still succeed when R is satisfiable.
7. **Hinted handoff**: when a replica is down, a healthy node stores the write with a hint and replays it on recovery.
8. **Read repair**: when a read finds replicas disagreeing, write the winner back to the stale ones.
9. **Heartbeats** with a failure detector, and a membership list.

### Experiment

**E1 — The R+W>N rule, tested.** For N=3, run these and record whether you can read your own write:

| N | R | W | Read-your-write? | Tolerates node loss? |
|---|---|---|---|---|
| 3 | 1 | 1 | | |
| 3 | 2 | 2 | | |
| 3 | 1 | 3 | | |
| 3 | 3 | 1 | | |

**E2 — Key movement.** With 3 nodes and 10,000 keys, add a 4th node. Count keys that move. Then repeat with `hash(key) % N` instead of the ring.

**E3 — Latency vs durability.** Measure write p99 at W=1, W=2, W=3.

**E4 — Conflict.** Partition two nodes (block them in code), write a different value to the same key on each, then heal. What does a read return, and what got lost?

### Expected result

- **E1:** `R=1,W=1` is fast and reads stale data. `R=2,W=2` satisfies R+W>N and gives read-your-writes, at the cost of needing 2 of 3 nodes up for both operations. `W=3` means any single node failure blocks all writes.
- **E2:** the ring moves roughly **1/4 of keys** (≈2,500); modulo moves **nearly all** of them. This is the number that makes consistent hashing obvious.
- **E3:** p99 rises with W, because you wait for the slowest of W replicas — your first direct encounter with [tail latency amplification](system-design-roadmap-2026.md#phase-5-reliability-observability-security-and-cost).
- **E4:** last-write-wins **silently discards one write.** This is the motivation for version vectors and CRDTs, and it's much more convincing after you've watched your own data vanish.

### Done when

- [ ] The E1 table filled in from actual runs, not reasoning
- [ ] Key-movement counts for ring vs modulo
- [ ] A node killed mid-load-test with reads still succeeding
- [ ] Read repair demonstrably converging two disagreeing replicas
- [ ] You can explain why LWW lost data in E4

### Journal entry

You've now built Dynamo's core. Read the [Dynamo paper](https://www.allthingsdistributed.com/files/amazon-dynamo-sosp2007.pdf) *after* this lab, not before — it reads completely differently once these are your own bugs.

### Stretch (pick one, they're both big)

- **The MIT 6.5840 Raft labs** ([course](https://pdos.csail.mit.edu/6.824/)). The best distributed systems exercise that exists, in Go, with a test suite that is merciless. Budget 15+ hours; it is worth a week of your buffer if you want infra roles.
- **Replace LWW with version vectors** and expose conflicts to the client as siblings, the way Dynamo does.

---

## Lab 6: The Resilience Lab (Week 10)

**Maps to:** Phase 4 resilience patterns · every failure-mode follow-up
**Time:** 5 h · **Profile:** `--profile lab06`
**If you do only two labs, this is the second one.** It produces more usable interview material per hour than anything else here.

### Build

Two services: **Frontend** (`GET /checkout`) calls **Inventory** (`GET /stock/:id`). Route the call through **toxiproxy** so you can break the network without touching code.

```bash
# proxy the inventory service through toxiproxy
curl -X POST http://localhost:8474/proxies -d '{
  "name":"inventory","listen":"0.0.0.0:16379","upstream":"inventory:8081"
}'

# add 2 seconds of latency
curl -X POST http://localhost:8474/proxies/inventory/toxics -d '{
  "type":"latency","attributes":{"latency":2000,"jitter":500}
}'

# or black-hole it entirely
curl -X POST http://localhost:8474/proxies/inventory/toxics -d '{
  "type":"timeout","attributes":{"timeout":0}
}'
```

Then build these **in order, measuring after each**:

1. **No protection.** Frontend calls Inventory with no timeout. (Yes, really — you need the baseline.)
2. **A timeout** (200 ms), chosen from the p99 you measured, not from a round number you liked.
3. **Naive retries:** 3 immediate retries.
4. **Exponential backoff with jitter:** `sleep = rand(0, min(cap, base * 2^attempt))`.
5. **A retry budget:** retries capped at 10% of total requests, tracked in a sliding window.
6. **A circuit breaker:** closed → open after 50% failures in a 10-request window → half-open probe after 5 s.
7. **Graceful degradation:** on an open circuit, return the page with "stock unknown" instead of a 500.

### Experiment

**E1 — No timeout.** Add 2 s of latency. Watch Frontend's threads/connections pile up. Record p99 and error rate. Now black-hole the connection and see how long a request hangs.

**E2 — Retry storm.** With naive retries, make Inventory slow but not dead (500 ms) and drive steady load. Record the **request rate arriving at Inventory** versus the rate leaving Frontend.

**E3 — Backoff with jitter.** Same test, with backoff. Record the amplification factor again.

**E4 — Circuit breaker.** Black-hole Inventory completely. Record Frontend's p99 and error rate before and after the breaker opens.

**E5 — Thundering herd on recovery.** Fix Inventory while the breaker is open. Do all clients hit it simultaneously the moment it recovers?

### Expected result

- **E1:** with no timeout, **one slow dependency takes down a healthy service.** Every worker ends up parked waiting, and the failure is total, not partial. This is the most important 15 minutes in this track.
- **E2:** the load arriving at the struggling service is **multiplied** — roughly 4× with 3 retries, plus synchronization as retries align into waves. You've made a slow service into a dead one.
- **E3:** amplification drops and the waves flatten. Jitter is doing the flattening; write down why.
- **E4:** once the breaker opens, p99 **collapses to fast failures** instead of slow timeouts, and with degradation the user gets a usable page. "Fail fast" becomes a number.
- **E5:** without half-open probing and jittered recovery, yes — you get a herd, and you can knock the service back over just as it comes up.

### Done when

- [ ] Amplification factor recorded for naive retries vs jittered backoff
- [ ] The no-timeout cascade reproduced and explained
- [ ] Breaker state transitions observable in logs
- [ ] A degraded response that's actually useful to a user
- [ ] You can answer the main roadmap's checkpoint — *how does a retry storm take down a system that was only briefly slow, and three ways to prevent it?* — from your own data

### Journal entry

Read [Timeouts, retries and backoff with jitter](https://aws.amazon.com/builders-library/timeouts-retries-and-backoff-with-jitter/) again after this lab. Then write down how you chose your timeout value, because "what timeout would you set, and how did you pick it?" is a question that separates people who have run systems from people who have read about them.

### Stretch

Add **load shedding**: when concurrent in-flight requests exceed a threshold, return `503` immediately rather than queueing. Measure goodput (successful requests/second) with and without it under 5× overload. Shedding *increases* successful throughput under overload, which is counter-intuitive until you've measured it.

---

## Lab 7: Observability, SLOs and Geo (Week 11)

**Maps to:** Phase 5 + 2B geo · problems #16, #17
**Time:** 6 h · **Profile:** `--profile lab07`
**Week 11 is the [tightest week in the plan](system-design-roadmap-2026.md#the-16-week-schedule).** Do part A; part B is genuinely optional.

### Part A — Observability and SLOs (4 h)

1. **OpenTelemetry instrumentation** across Frontend and Inventory from Lab 6, exporting traces to Jaeger via OTLP.
2. **A correlation ID** generated at the edge, propagated through every call, and logged in structured JSON on every log line.
3. **RED metrics** (rate, errors, duration) as Prometheus histograms, and a Grafana dashboard with those three panels.
4. **An SLO:** 99% of `/checkout` requests under 300 ms over a rolling window. Compute the **error budget** and display remaining budget as a single number.
5. **One symptom-based alert** — "error budget burn rate > 2×" — not "CPU > 80%".

### Part A experiment

- **E1:** use Lab 6's toxiproxy to inject 2 s of latency into Inventory, then find the slow span in Jaeger **without reading the code**. Time yourself. This is what on-call is.
- **E2:** burn the error budget deliberately. Record how long 5× normal error rate takes to exhaust a month's budget. (For a 99% SLO, this is alarmingly fast — that's the point of burn-rate alerts.)
- **E3:** add a high-cardinality label (like `user_id`) to a Prometheus metric, generate traffic, and watch memory. Then remove it. Cardinality is a cost and an outage risk.

### Part B — Geo indexing (2 h, optional)

6. Load ~10,000 random points around a city into Postgres.
7. Implement proximity search three ways and time each at radius 1 km, 5 km and 20 km:
   - **Naive:** compute distance to every row.
   - **Bounding box:** `WHERE lat BETWEEN ... AND lng BETWEEN ...` with a composite index, then filter exactly.
   - **H3 cells:** store `h3_cell` at resolution 9, query with `gridDisk(center, k)` and filter exactly.
     ```python
     # h3-py v4 names (v3 used geo_to_h3 / k_ring)
     cell  = h3.latlng_to_cell(lat, lng, 9)
     cells = h3.grid_disk(cell, 2)
     ```
8. Simulate **high-frequency location updates**: 1,000 drivers posting every 5 seconds. Compare writing every update to Postgres versus keeping current position in Redis and only persisting periodically.

### Part B expected result

Naive scales linearly with table size and collapses. Bounding box is dramatically faster but returns a *rectangle*, so you must filter exactly afterward. H3 gives near-constant lookup cost via cell-set membership, and the trade-off moves to picking the resolution — too coarse means too many candidates, too fine means too many cells to query. The location-update test should show clearly why hot, ephemeral position data doesn't belong in your primary database.

### Done when

- [ ] One trace showing the full request path with the slow span identified
- [ ] Time-to-diagnosis recorded for E1
- [ ] Error budget as a live number on a dashboard
- [ ] The cardinality mistake made and measured
- [ ] (Part B) Query times for all three approaches at three radii

### Journal entry

Write your three golden dashboards: what would you put on a dashboard you'd look at during an incident? If your answer includes CPU before it includes user-facing error rate, redo it.

---

## Lab 8: Money — Ledger and Inventory (Week 12)

**Maps to:** week 12 theory · problems #15, #19, #20
**Time:** 6 h · **Profile:** `--profile lab08`

This lab is where Lab 4's isolation knowledge pays off. Correctness matters absolutely here — you cannot cache your way out of a wrong balance.

### Build

**Part A — A double-entry ledger (3 h):**

1. **Schema:** `accounts(id, name)` and `entries(id, txn_id, account_id, amount_minor, created_at)`. **Amounts are integers in minor units** (paise, cents). Never floats — write yourself a comment explaining why (`0.1 + 0.2 != 0.3`).
2. **The invariant:** every transaction's entries sum to zero. Enforce it, and write a checker that scans for violations.
3. **Balance** = `SELECT sum(amount_minor) FROM entries WHERE account_id = ?`. Never a mutable `balance` column you update — the entries *are* the truth.
4. **Transfers with idempotency keys:** `POST /transfers` with an `Idempotency-Key` header, stored with a unique index. A replay returns the original result and creates nothing.
5. **The outbox pattern:** insert a `payment.completed` row into an `outbox` table in the **same transaction** as the entries, with a poller that publishes and marks it sent.
6. **A reconciliation job** that recomputes every balance from entries and reports drift.

**Part B — Flash sale inventory (3 h):**

7. `POST /reserve` for a product with 100 units, under 1,000 concurrent buyers.
8. **Build it wrong first:** `SELECT stock` → check `> 0` → `UPDATE stock = stock - 1`. Run it concurrently.
9. Then fix it **three ways** and measure each:
   - **Atomic conditional update:** `UPDATE products SET stock = stock - 1 WHERE id=? AND stock > 0` and check rows affected.
   - **Reservations with TTL:** create a `reservations` row with an expiry, and a sweeper that releases expired ones. This is Ticketmaster's model.
   - **Redis counter as the gate:** `DECR` as admission control, with the database as the durable record.

### Experiment

**E1 — Overselling.** Run the naive version with 1,000 concurrent requests for 100 units. **Count how many succeeded.**

**E2 — The fixes.** Same test for each of the three fixes. Record units sold and p99 for each.

**E3 — Idempotency under retry.** Fire the same transfer 50 times concurrently with the same idempotency key. Count ledger entries created.

**E4 — Crash mid-transfer.** Kill the process between the entry insert and the outbox publish. Confirm that after restart, either both happened or neither did — and that the event still eventually publishes.

**E5 — Reconciliation.** Corrupt one balance by hand. Confirm the job finds it.

### Expected result

- **E1:** you sell **more than 100 units.** This is not a subtle bug; it's the default behavior of read-check-write under concurrency, and it's exactly why #20 Flash sale is a real interview question.
- **E2:** all three fixes hold the line at exactly 100, with different costs. The atomic update is simplest and fastest. Reservations add complexity but support a checkout flow where the user needs time. The Redis gate is fastest under extreme load but introduces a consistency boundary between two systems — say so out loud.
- **E3:** exactly one set of entries, 50 identical responses.
- **E4:** the outbox is the whole point — because the event and the data commit atomically, there's no window where money moved but the event vanished.

### Done when

- [ ] An oversell number recorded from the naive version ("sold 143 of 100 units")
- [ ] Three fixes measured with their trade-offs written down
- [ ] Idempotency verified under concurrent replay
- [ ] Crash test passing, with the event still published after recovery
- [ ] Reconciliation catching injected drift

### Journal entry

Why is a mutable `balance` column a bug waiting to happen, and when would you add one anyway? (As a cached projection, rebuilt from entries and reconciled — never as the source of truth.) This question comes up in every fintech interview.

### Stretch

Add a **saga**: a transfer that spans two services (debit and credit), with compensating actions if the second fails. Then deliberately fail the compensation and see what manual intervention you need. Sagas don't remove failure, they relocate it — usually into someone's on-call queue.

---

## Lab 9: RAG and an LLM Gateway (Week 13)

**Maps to:** Phase 10 + 2B vectors · problems #35, #36
**Time:** 8 h · **Profile:** `--profile lab00` + pgvector

Use **Postgres with pgvector** rather than a dedicated vector database — one less container, and "we used pgvector because we already had Postgres and 10M vectors fits fine" is a better interview answer than naming a vendor.

> **Cost note:** a hosted LLM API for this lab costs a few dollars at most. A local model via Ollama works and costs nothing, but is slower. Embeddings can be generated locally with a small sentence-transformer model for free.

### Part A — RAG with evaluation (5 h)

1. **A corpus:** 200–1,000 documents you actually know something about — your own notes, a project's docs, downloaded engineering blog posts. You must be able to judge whether an answer is right.
2. **Ingestion pipeline:** parse → chunk → embed → store, with `document_id`, `chunk_index`, `text`, `embedding` and **`tenant_id`** (permissions from day one, not bolted on).
3. **Three chunking strategies:** fixed 500 characters · 500 with 50 overlap · paragraph/heading-aware. Keep all three; you're going to compare them.
4. **Retrieval, three ways:**
   - Vector similarity (pgvector `<=>` cosine distance, with an HNSW index)
   - Keyword search (Postgres full-text `tsvector`, which is BM25-ish)
   - **Hybrid**, fusing both rankings
5. **An eval set: 30 questions with known correct source chunks.** This is the part everyone skips and the part that makes the lab worth doing.
6. **Measure retrieval quality** — recall@5 and MRR — for each chunking strategy × retrieval method.
7. **Generation with citations**, and an explicit "I don't have enough context" path when top scores fall below a threshold.
8. **Access control at retrieval time**: filter by `tenant_id` in the query itself. Then write a test that proves tenant A can never retrieve tenant B's chunk.

### Part B — The LLM gateway (3 h)

9. `POST /v1/chat` in front of your model with:
   - **Per-tenant rate limiting** (reuse Lab 1's token bucket)
   - **Token accounting**: log input tokens, output tokens and computed cost per request, per tenant
   - **An exact-match cache** keyed on a hash of the normalized prompt
   - **A semantic cache**: embed the prompt, and serve a cached answer if cosine similarity to a previous prompt exceeds a threshold
   - **Model routing**: cheap model by default, expensive model on a complexity signal or explicit override
   - **A fallback** when the primary model errors or times out
   - **SSE token streaming** to the client, plus cancellation when the client disconnects
   - **Metrics:** TTFT, total latency, tokens/second, cost per request, cache hit rate

### Experiment

**E1 — Chunking matters.** Fill in recall@5 for all nine combinations:

| | Fixed 500 | 500 + overlap | Structure-aware |
|---|---|---|---|
| Vector only | | | |
| Keyword only | | | |
| Hybrid | | | |

**E2 — Semantic cache economics.** Send 100 questions where 30 are paraphrases of others. Record cache hit rate, cost saved, and — critically — **how many cache hits returned a subtly wrong answer** because the threshold was too loose.

**E3 — Latency budget.** Break a p95 RAG request into: embed → retrieve → re-rank → generate. Which dominates?

**E4 — Access control.** Attempt cross-tenant retrieval. Must return nothing.

**E5 — Routing savings.** Route 80% of requests to the cheap model. Record cost delta and any quality loss.

### Expected result

- **E1:** hybrid beats either method alone on most question types, and overlap helps when answers straddle chunk boundaries. Structure-aware chunking usually wins on documents with real headings. **Your numbers are what matter** — being able to say "overlap improved recall@5 from 0.71 to 0.83 on my set" is worth more than any general claim.
- **E2:** the semantic cache saves real money *and* introduces a correctness risk. Finding your own false-positive rate teaches the trade-off properly.
- **E3:** generation normally dominates, which is why streaming matters — TTFT is the number users feel, not total latency.
- **E5:** most requests don't need the expensive model, which is the entire business case for a gateway.

### Done when

- [ ] The 3×3 retrieval quality table filled in from your eval set
- [ ] A latency breakdown per pipeline stage
- [ ] A cross-tenant leak test that passes
- [ ] Cost per request tracked and a measured saving from caching plus routing
- [ ] Streaming works, and cancelling the client actually stops the generation

### Journal entry

Answer the main roadmap's checkpoint from your own data: *your LLM bill doubled — how does your design find the cause?* You built the token accounting, so you know exactly which dimensions you'd group by.

---

## Lab 10: Streams, CDC and Top-K (Week 14)

**Maps to:** 2B stream processing and CDC · problems #27, #28
**Time:** 6 h · **Profile:** `--profile lab10`

### Part A — CDC from the WAL, with no extra tooling (2 h)

Read Postgres's write-ahead log directly. No Debezium, no Kafka Connect, no containers — this is the clearest possible demonstration of what CDC *is*.

```sql
-- requires wal_level=logical (already set in the compose file above)
SELECT * FROM pg_create_logical_replication_slot('lab_slot', 'test_decoding');

-- now, in another session:
INSERT INTO items (name) VALUES ('hello');
UPDATE items SET name = 'goodbye' WHERE name = 'hello';
DELETE FROM items WHERE name = 'goodbye';

-- and read the change stream:
SELECT * FROM pg_logical_slot_get_changes('lab_slot', NULL, NULL);
```

You'll see BEGIN / INSERT / UPDATE / DELETE / COMMIT records with old and new values. **Then do the two things that matter:**

1. **Don't consume the slot for a while, then check disk.** An unconsumed replication slot pins WAL forever and will fill your disk. `SELECT slot_name, pg_size_pretty(pg_wal_lsn_diff(pg_current_wal_lsn(), restart_lsn)) FROM pg_replication_slots;` — this is a real production outage in a bottle.
2. **Compare it with the outbox pattern** from Lab 8. CDC needs no application change but couples you to the schema; the outbox needs application discipline but gives you clean domain events.

Clean up: `SELECT pg_drop_replication_slot('lab_slot');`

### Part B — Windowed aggregation (2 h)

3. Produce a synthetic click stream to Redpanda: `(ad_id, user_id, event_time)` at a few thousand events/second, and **deliberately include events that arrive late** (event_time several minutes in the past).
4. **Tumbling 1-minute windows** counting clicks per ad, keyed by **event time**, not processing time.
5. **A watermark**: close a window when you've seen event times past `window_end + 30 s`. Route later arrivals to a late-data path.
6. **Exactly-once-ish aggregation:** store `(window, ad_id) → count` with the consumer offset committed in the *same* transaction as the count update, so a crash can't double-count.
7. **Kill the consumer mid-window and restart it.** Counts must be correct.

### Part C — Approximate structures (2 h)

8. **Count-Min Sketch for Top-K** using redis-stack:
   ```
   CMS.INITBYDIM clicks 2000 10
   CMS.INCRBY clicks ad_42 1
   CMS.QUERY clicks ad_42
   TOPK.RESERVE trending 10 2000 10 0.9      # TopK is also in redis-stack
   TOPK.ADD trending ad_42
   TOPK.LIST trending
   ```
9. **HyperLogLog for unique viewers:** `PFADD viewers:ad_42 user_1 ...` then `PFCOUNT`.
10. **Compare against exact counts** kept in a hash/set: measure memory used and error rate for both.

### Experiment

**E1 — CDC lag and WAL growth.** Record WAL retained by an unconsumed slot over 10 minutes of writes.
**E2 — Late data.** Record how many events arrive after their window closed, and what your pipeline does with them.
**E3 — Crash correctness.** Counts before the crash vs after recovery. Any drift?
**E4 — Sketch accuracy.** For 1M events across 10,000 ads: exact memory vs CMS memory, and the error on the top 10.
**E5 — HLL accuracy.** Exact unique count vs `PFCOUNT`, and memory for each.

### Expected result

- **E1:** WAL grows without bound. Unconsumed slots are one of the most common self-inflicted Postgres outages.
- **E2:** late events exist and are not rare. Event-time processing with watermarks is the only honest way to handle them; processing-time windows silently produce wrong answers.
- **E4/E5:** the sketches use **dramatically less memory** — orders of magnitude — with small, bounded error. HLL typically lands within a couple of percent of exact. This is the concrete basis for "exact vs approximate" in [trade-off 16](system-design-roadmap-2026.md#i-the-20-trade-offs-you-must-be-able-to-articulate), and "we don't need exact unique counts for a trending list" becomes a decision you can defend with numbers.

### Done when

- [ ] You've read your own database's WAL and can describe a CDC event's contents
- [ ] WAL growth from an unconsumed slot measured
- [ ] Late-data path working with a watermark
- [ ] Crash test with no double-counting
- [ ] Memory and error numbers for CMS and HLL vs exact

### Journal entry

Write the Lambda vs Kappa decision for this pipeline: you have a streaming path that's fast and approximate, and a batch recompute that's slow and exact. Do you run both? For ad *billing*, the answer is usually yes — and now you know why.

---

## Lab 11: The Capstone (Weeks 15–16)

**Maps to:** Phase 11 · [your project deep dive](system-design-roadmap-2026.md#prepare-your-project-deep-dive)
**Time:** 10 h

Don't start something new. **Take one earlier lab and make it something you'd defend in a senior interview.** Pick the one whose story you most want to tell — usually Lab 6, 8 or 9.

### The capstone checklist

1. **A written design doc** (2 h) — 2 pages, in the repo:
   - Requirements, functional and non-functional, with numbers
   - The design, with a diagram
   - Three decisions, each as options → choice → why → when you'd switch
   - What you'd do differently at 100× the scale
2. **A zero-downtime migration** (3 h) — change something structural with live traffic running: add a NOT NULL column, split a table, or change a shard key. Use expand → migrate → contract:
   - Expand: add the new structure, write to both
   - Migrate: backfill in batches, with progress tracking and a kill switch
   - Contract: cut reads over, verify, remove the old path
   - **Run k6 throughout and prove zero failed requests.** That's the deliverable.
3. **A cost model** (1 h) — using [cheat sheet K](system-design-roadmap-2026.md#k-cost-anchors-what-actually-drives-the-bill), estimate monthly cost at 10K, 1M and 100M users. Name the dominant line item at each scale; it changes, and noticing that is the senior insight.
4. **A runbook** (1 h) — the three most likely failures, how you'd detect each (the specific alert), and the first three steps to mitigate.
5. **A load test as a regression gate** (1 h) — k6 with thresholds that fail the build. Then make a change that breaks a threshold and watch it fail.
6. **A game day** (2 h) — write a hypothesis ("if Redis dies, checkout degrades but stays up"), kill the dependency, record what *actually* happened, and fix the gap. That gap is your best interview story, because it's the one you didn't predict.

### Done when

- [ ] The design doc could be handed to another engineer
- [ ] A migration completed under live load with zero failed requests
- [ ] Cost at three scales, with the dominant driver named at each
- [ ] A game day where reality diverged from your hypothesis, documented
- [ ] Your [project deep dive](system-design-roadmap-2026.md#prepare-your-project-deep-dive) written out and rehearsed out loud

---

## The Parallel LLD Skeleton (Weeks 3–13)

The main roadmap's [Phase 9](system-design-roadmap-2026.md#phase-9-low-level-design-and-machine-coding) already schedules one LLD problem a week. One piece of build work makes every one of them faster, and it belongs here.

**In week 3, build a reusable machine-coding skeleton in your language** (1.5 h, once):

```text
lld-skeleton/
  models/          # plain data classes, no logic
  repositories/    # interfaces + in-memory implementations
  services/        # business logic, depends on interfaces
  strategies/      # the extension points (pricing, allocation, matching)
  exceptions/      # custom exceptions with useful messages
  cli.py           # or Main.java — a runnable driver that demos every flow
  tests/           # one example test that actually runs
```

Then in weeks 4–13, each LLD problem starts by copying this directory. **It saves 10–15 minutes in every timed round**, which is the difference between demoing a working app and apologizing for an unfinished one.

**The discipline that scores in a machine-coding round**, in priority order:

1. **Working code first.** A complete simple solution beats an elegant half-finished one, every time.
2. **A runnable driver from minute 20.** If it doesn't run, it doesn't count.
3. **Interfaces exactly at the extension points** the interviewer will poke at — pricing, matching, notification channels. They will ask "now add X."
4. **In-memory repositories behind an interface**, so "how would you add persistence?" is a one-sentence answer.
5. **Two or three tests**, not twenty.
6. **No pattern-stuffing.** A Singleton you can't justify is worse than no pattern.

---

## The Results Log

Put this table in your repo's root `README.md` and fill it in as you go. **It is the most valuable output of this entire track** — it converts 70 hours of building into a page of quotable evidence.

| Lab | Experiment | Metric | Before | After | What it taught me |
|---|---|---|---|---|---|
| 0 | Cache on vs off | p99 | | | |
| 0 | Index dropped | p99 + plan | | | |
| 0 | Pool size 10 → 2 | p99 / throughput | | | |
| 1 | Non-atomic rate limiter | requests allowed vs limit | | | |
| 1 | Cache stampede | peak concurrent DB queries | | | |
| 2 | Replication lag under writes | peak lag (ms) | | | |
| 2 | Add a shard: modulo vs ring | keys moved | | | |
| 3 | Crash before ack | duplicate deliveries | | | |
| 3 | 4 consumers, 3 partitions | throughput per consumer | | | |
| 4 | Lost update | final counter value | | | |
| 4 | Write skew | doctors on call | | | |
| 5 | R=1,W=1 vs R=2,W=2 | stale reads observed | | | |
| 5 | Write p99 at W=1/2/3 | p99 | | | |
| 6 | No timeout, slow dependency | p99 / error rate | | | |
| 6 | Retry storm | load amplification factor | | | |
| 6 | Circuit breaker open | p99 | | | |
| 7 | Time to find a slow span | minutes | | | |
| 7 | High-cardinality label | Prometheus memory | | | |
| 8 | Naive reserve, 1000 buyers | units oversold | | | |
| 8 | Three fixes | units sold / p99 | | | |
| 9 | Chunking × retrieval | recall@5, MRR | | | |
| 9 | Semantic cache | hit rate / cost saved / false positives | | | |
| 10 | Unconsumed slot | WAL retained | | | |
| 10 | CMS and HLL vs exact | memory / error | | | |
| 11 | Migration under load | failed requests | | | |
| 11 | Game day | hypothesis vs reality | | | |

**How to use it in an interview:** when you propose a component, attach a number. "I'd cache the redirect path — when I built this, that took p99 from *X* to *Y*, and the failure mode I hit was a stampede at TTL expiry, so I'd jitter the TTLs." No interviewer hears that sentence and wonders whether you've done the work.

---

## The Lab README Template

Every lab directory gets this. Fifteen minutes each, and by week 16 you have a portfolio.

```markdown
# Lab N: <name>

## What this demonstrates
One paragraph. The interview claim it earns.

## Architecture
<Excalidraw PNG — five boxes maximum>

## Run it
    docker compose --profile labNN up -d
    <seed command>
    <run command>
    k6 run -e BASE_URL=http://localhost:8080 ../load/baseline.js

## Decisions
| Decision | Options considered | Chose | Why | Would switch if |
|---|---|---|---|---|

## Measurements
| Experiment | Metric | Result |
|---|---|---|

## What broke
The bug you didn't expect, how you found it, what you changed.
This section is the most valuable one. Never leave it empty.

## What I'd do differently at 100x
```

---

## What Not to Build

Time sinks that feel like progress. Every hour here is an hour stolen from a mock.

| Don't | Why | Instead |
|---|---|---|
| A frontend | Zero interview value for a backend design round | `curl`, or a 20-line CLI |
| Auth and user management | Solved, boring, and nobody will ask | Hardcode a `tenant_id` header |
| Kubernetes for the labs | A week of YAML to learn what Compose taught you | Docker Compose; read the [k8s basics](https://kubernetes.io/docs/tutorials/kubernetes-basics/) for vocabulary only |
| Deploying to a cloud provider | Real money, real time, no extra learning | Localhost. Reason about cloud cost with [cheat sheet K](system-design-roadmap-2026.md#k-cost-anchors-what-actually-drives-the-bill) |
| Framework or library shopping | Infinite, and it isn't the lesson | The boring default in your language |
| Perfect test coverage | These are experiments, not products | Tests that verify the *experiment* is valid |
| Refactoring a finished lab | It already taught you what it had to | Start the next lab |
| Your own Raft from scratch (unless infra-bound) | 15+ hours for one interview talking point | Read the paper; use etcd; do the MIT labs only if you have the time |

**The strongest signal that you're off track:** you're writing code and not generating numbers. Stop and go back to the experiment.

---

## Turning This Into Your "System I Built" Story

Senior loops ask "walk me through a system you built." These labs qualify — **as long as you're honest that they're labs.** Scale is not the point; judgment is, and "I built this to find out where it breaks, and here's what I found" is a genuinely strong answer.

Map your capstone onto the main roadmap's [seven-point outline](system-design-roadmap-2026.md#prepare-your-project-deep-dive):

| Outline point | Where it comes from |
|---|---|
| Context | The lab's README opening paragraph |
| Scale | Your k6 numbers, stated as what you tested, not what you'd claim in production |
| Architecture | The five-box diagram you can draw in two minutes |
| One hard decision | A row from your Decisions table, including the switch condition |
| One failure | The "What broke" section, or your game-day surprise |
| Impact | A before/after from the results log |
| Hindsight | "What I'd do differently at 100×" |

**Be straight about it.** "This was a lab I built to understand quorums, not a production system — at 1,000 keys the numbers are directional" earns more credit than an inflated claim that collapses under one follow-up question.

---

## Definition of Done

**Per lab:** an experiment run, numbers recorded, a README with a diagram and a populated "What broke" section, and one sentence you'd say in an interview.

**For the whole track:**

- [ ] The [results log](#the-results-log) has a real number in every row you attempted
- [ ] For every component in [Phase 1](system-design-roadmap-2026.md#phase-1-core-building-blocks), you've either built it or broken it on purpose
- [ ] You've caused, and then fixed: a lost update, an oversell, a duplicate charge, a retry storm, a cache stampede and a stale read
- [ ] You can name a failure mode you did not predict, and what it changed in your thinking
- [ ] Your capstone survived a migration under live load
- [ ] Your project deep dive is written down and rehearsed out loud
- [ ] Your repo is something you'd send a hiring manager without editing it first

---

*Companion to [system-design-roadmap-2026.md](system-design-roadmap-2026.md). Same principle: free tools only, everything local, and every claim backed by a number you measured yourself.*
