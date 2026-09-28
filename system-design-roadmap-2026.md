# System Design Roadmap: Zero to Interview-Ready (2026 Edition)

A complete A-to-Z plan to learn system design from scratch and clear high-level design (HLD), low-level design (LLD) / machine-coding, and AI-era design rounds, using **free resources only**.

> **Version 3** (28 September 2026): coverage audit, plus [The Straight Path](#the-straight-path-every-link-in-order) — every resource as one ordered, linked sequence. See [Version History](#version-history). Every resource link was checked against live sources during research.
>
> **"Free"** means the linked material costs nothing. Some sites also sell premium tiers; those are marked.
>
> **Time needed:** 16 weeks at ~10–12 hours/week (core track), plus one buffer week. Fast (8-week) and deep (24-week) variants are included.

---

## Start Here: The Short Version

- **This week:** take the [placement test](#placement-test-what-can-you-skip) (10 minutes), then start Phase 0 or Phase 1. Read Hello Interview's free [System Design in a Hurry](https://www.hellointerview.com/learn/system-design/in-a-hurry/introduction) introduction alongside it.
- **Don't want to plan anything?** Open [The Straight Path](#the-straight-path-every-link-in-order) and work down it from step 1. Every resource, in order, with links.
- **Want to build, not just read?** [hands-on-projects-roadmap.md](hands-on-projects-roadmap.md) is a 12-lab build track timed to these same 16 weeks, where every lab produces a number you can quote in an interview.
- **Every topic:** learn it → see it in a real system → use it in a problem → explain it out loud in 2 minutes.
- **Core resources:** Hello Interview, System Design Primer, ByteByteGo, Jordan has no life and Kleppmann's lectures, plus free peer mocks on Aced.
- **Milestones:** first practice problem in week 4 · baseline mock in week 8 · all 27 core problems by week 15 · 11 mocks by week 16.
- **The 2026 difference:** cover failure modes, monitoring, rollback and cost in every design, and be able to design a RAG system and an LLM gateway.
- **Calendar:** ~10–12 hours a week. Starting Monday 28 September 2026, week 16 ends on 17 January 2027 (24 January with the buffer week).

---

## Table of Contents

1. [How to Use This Roadmap](#how-to-use-this-roadmap)
2. [The 2026 Interview Landscape](#the-2026-interview-landscape)
3. [Your Core Free Resource Stack](#your-core-free-resource-stack)
4. [Roadmap at a Glance](#roadmap-at-a-glance)
5. [**The Straight Path: Every Link in Order**](#the-straight-path-every-link-in-order)
6. [Phase 0: Prerequisites](#phase-0-prerequisites)
7. [Phase 1: Core Building Blocks](#phase-1-core-building-blocks)
8. [Phase 2: Data and Storage Deep Dive](#phase-2-data-and-storage-deep-dive)
9. [Phase 3: Distributed Systems Core](#phase-3-distributed-systems-core)
10. [Phase 4: APIs, Communication and Architecture Patterns](#phase-4-apis-communication-and-architecture-patterns)
11. [Phase 5: Reliability, Observability, Security and Cost](#phase-5-reliability-observability-security-and-cost)
12. [Phase 6: Back-of-the-Envelope Estimation](#phase-6-back-of-the-envelope-estimation)
13. [Phase 7: The Interview Framework](#phase-7-the-interview-framework)
14. [Phase 8: Practice Problems (The Curated 40)](#phase-8-practice-problems-the-curated-40)
15. [Phase 9: Low-Level Design and Machine Coding](#phase-9-low-level-design-and-machine-coding)
16. [Phase 10: AI, ML and GenAI System Design](#phase-10-ai-ml-and-genai-system-design)
17. [Phase 11: Advanced and Senior+ Topics](#phase-11-advanced-and-senior-topics)
18. [Phase 12: Mock Interviews and Final Prep](#phase-12-mock-interviews-and-final-prep)
19. [The 16-Week Schedule](#the-16-week-schedule)
20. [Progress Tracker](#progress-tracker)
21. [Cheat Sheets](#cheat-sheets)
22. [Complete Free Resource Index](#complete-free-resource-index)
23. [Optional Paid Resources](#optional-paid-resources)
24. [Final Interview-Readiness Checklist](#final-interview-readiness-checklist)
25. [Version History](#version-history)
26. [Sources](#sources)

---

## How to Use This Roadmap

### Who this is for

| You are | Start at | Go light on | Go deep on |
|---|---|---|---|
| Student / fresher (0–1 yr) | Phase 0 | Phase 11 | Phases 1, 7, 8 (Tiers 1–2), 9 |
| SDE-1 moving to SDE-2 (1–4 yrs) | Phase 1 | Phase 0 | Phases 2, 3, 7, 8, 9 |
| SDE-2 moving to Senior/Staff (4+ yrs) | Phase 1 (fast review) | Phases 0, 9 | Phases 3, 5, 8 (Tiers 3–4), 10, 11 |

### Placement test: what can you skip?

Answer out loud, without notes. Count only answers you could defend under follow-up questions.

**Set A: can you skip Phase 0?**
1. What happens, step by step, when you type a URL and press Enter?
2. TCP vs UDP: when would you choose UDP?
3. What problem does HTTP/2 multiplexing solve compared with HTTP/1.1?
4. How is a DNS name resolved, and what does the TTL control?
5. Process vs thread: what is a race condition?
6. Why does an index speed up reads but slow down writes?
7. What does each letter of ACID mean, with an example?
8. Forward proxy vs reverse proxy: what's the difference?

**7–8 solid answers:** skip Phase 0 (still build the Phase 0 project if you've never built a backend). **Fewer:** start at Phase 0.

**Set B: can you fast-review Phase 1?**
1. Cache-aside vs write-through: when would you use each?
2. How would you shard a users table, and what goes wrong with a bad shard key?
3. What is replication lag, and what user-visible bug can it cause?
4. Give two differences between a queue (SQS) and a log-based stream (Kafka).
5. How do you make message processing idempotent?
6. L4 vs L7 load balancing: what's the difference?
7. When would you use SSE instead of WebSockets?
8. What is consistent hashing, and why add virtual nodes?

**7–8 solid answers:** treat Phase 1 as a one-week review and start practice problems immediately. **Fewer:** follow Phase 1 in full.

### Three tracks

| Track | Duration | Hours/week | Choose it when |
|---|---|---|---|
| Fast | 8 weeks | 12–15 | An interview is already scheduled |
| **Core (default)** | 16 weeks | 10–12 | You want to be solid and interview-ready |
| Deep | 24 weeks | 10–12 | You want real distributed-systems depth (senior, infra or platform roles) |

### Weekly time budget

| Activity | Hours per week | Notes |
|---|---|---|
| Theory (weekdays) | 2–5 | One primary resource; take notes as you go |
| New practice problems (weekends) | 3–4.5 | The 90-minute loop; smaller problems take ~60 minutes |
| Speed re-solve | 0.5 | One earlier problem each week from week 6 |
| LLD / machine coding | 1.5–2 | Weeks 3–13 |
| Estimation drills | 0.5 | Two 15-minute drills |
| Mock interviews | ~1.5 per mock | From week 8: about 1 hour of session plus 30 minutes of notes |
| **Total** | **~10–12** | Every week in [the schedule](#the-16-week-schedule) was sized to fit this budget |

Every track assumes **one buffer week** you can insert anywhere (festivals, travel, a work crunch). If you don't need it, spend it on stretch problems and extra mocks.

### Why the roadmap is ordered this way

1. **Fundamentals before components.** You can't reason about a load balancer or a cache without knowing how a request travels over the network and hits a database.
2. **Components before distributed theory.** Consistency, quorums and consensus only make sense once you've seen replicated databases and caches.
3. **Practice starts in week 4, not at the end.** Problems reveal which theory matters; theory then makes the next problem easier.
4. **LLD runs in parallel.** It uses different muscles (code structure, patterns) and is its own round at many companies, especially in India.
5. **AI design comes after the core.** RAG, LLM gateways and recommendation systems are built from the same parts: caches, queues, search indexes, rate limiters.

### The learning loop (use it for every topic)

1. **Learn** the concept from one primary resource.
2. **See it in production:** read one engineering blog or case study that uses it.
3. **Apply** it in a practice problem within the same week.
4. **Explain** it out loud in 2 minutes: what it is, why it exists, when *not* to use it, and how it fails.

### Five rules that save months

1. **One primary resource per topic.** Everything marked *supplement* or *optional* is exactly that. Tutorial-hopping is the biggest time sink in system design prep.
2. **Start practice problems in week 4**, not after "finishing theory".
3. **Keep a trade-off journal.** For every decision in practice, write: options → choice → why → when you would switch.
4. **Practice out loud on a whiteboard tool** ([Excalidraw](https://excalidraw.com/) is free). System design is a communication interview.
5. **Revisit problems.** Re-solving a problem after 1–2 weeks teaches more than solving a new one. The schedule builds this in with a weekly speed re-solve.

### If you fall behind

1. **Protect practice problems and mocks.** Cut supplements and optional depth first.
2. **Stretch problems are always optional.** Core problems are not.
3. **Use the buffer week** instead of squeezing two weeks into one.
4. **More than two weeks behind?** Switch to the [fast track](#fast-track-8-weeks-interview-already-scheduled) table for the weeks you have left.
5. **Never skip a checkpoint.** It's how you know you actually learned the week, not just watched it.

### Using AI tools while you prepare

- **Good uses:** have an AI assistant play the interviewer ("Ask me to design X. Ask one question at a time, push back on my choices, and don't give me the answer."), critique your finished design against the [mock scorecard](#mock-scorecard-score-each-dimension-14), generate estimation drills, or quiz you on flashcards.
- **Watch out:** AI explanations can be confidently wrong on details, so check them against the primary resources, and never let a tool do the thinking during your 45-minute solve.
- **Never during a real interview** unless the company explicitly allows it. Some companies have moved rounds back in person partly to counter AI-assisted cheating.

---

## The 2026 Interview Landscape

### What the round looks like

- **45–60 minutes**, one open-ended prompt ("Design X"), collaborative, on a whiteboard tool, a Google Doc or a physical whiteboard.
- **Four common flavors:** product design ("Design Uber's backend"), infrastructure design ("Design a rate limiter"), object-oriented / low-level design ("Design a parking lot") and frontend design ("Design a spreadsheet app").
- **There is no single correct answer.** You are graded on how you reason, not on matching a reference diagram.

### What changed by 2026 (and why older prep guides fall short)

The format looks much like it did a few years ago, but the bar moved. Across 2026 guides from interviewers and prep platforms, the same shifts come up repeatedly:

| Shift | What it means for you |
|---|---|
| **AI-aware design is expected** | Know where LLMs, embeddings, vector stores and RAG fit, even in a general SWE loop. Classic prompts now get AI twists (for example, a feed plus a recommendation pipeline or an AI-generated summary), and new prompts such as "Design a RAG pipeline" or "Design an LLM gateway" appear. |
| **Cost is graded** (especially senior) | Reason about cost per request and right-sizing. Proposing multi-region active-active for a small app now reads as poor judgment, not ambition. |
| **Operations are graded** | Observability, deployment and rollback, failure modes and on-call burden are expected, not bonus points. |
| **Memorized answers fail** | Interviewers probe, push back and change requirements mid-interview. You need reasoning that survives follow-up questions. |
| **Earlier and more varied** | Design questions now reach mid-level and even junior loops (with calibrated expectations). At Google the round is light at L3/L4 (often folded into coding) and becomes a dedicated round from L5. Some companies have moved onsites back in person; some run multi-part timed designs or verbal-only design discussions. |

### What interviewers actually grade

| Dimension | What "good" looks like | Red flags |
|---|---|---|
| Problem navigation | Clarifies scope, picks the top 3 features, states non-functional requirements with numbers | Starts drawing immediately; tries to design everything |
| High-level design | A simple end-to-end design that satisfies every functional requirement; walks a request through it | Boxes with no data flow; buzzword soup |
| Technical depth | Goes deep on 2–3 real bottlenecks with concrete mechanisms (keys, indexes, algorithms, failure handling) | "We'll just use Kafka/Redis" with no *why* |
| Trade-offs | Compares options, commits to one, says when they would switch | "It depends" with no decision |
| Operations and cost | Mentions monitoring, failure modes, rollout and rough cost drivers | Ignores failures; gold-plates everything |
| Communication | Drives the conversation, checks in, keeps a clean diagram, manages time | Long monologues, long silences, runs out of time before deep dives |

### What is expected at each level

| Level | Expectation |
|---|---|
| New grad / SDE-1 | Solid fundamentals. A working high-level design with some guidance. Can explain load balancers, caches, databases and queues. Many companies test LLD/OOD more than HLD at this level. |
| Mid-level (SDE-2 / L4) | Drives most of the interview. A correct high-level design plus 1–2 meaningful deep dives with reasonable trade-offs. |
| Senior (L5) | Drives completely. Proactively finds bottlenecks, goes deep on 2–3 areas, and covers failures, operations and cost. |
| Staff+ (L6+) | Frames and challenges the problem, compares multiple viable architectures, and discusses evolution over time, migrations and organizational/operational impact. |

### India-specific note: machine coding and LLD rounds

Many Indian product companies run a **machine-coding round**: build a working, runnable, well-structured application in roughly **90–120 minutes**, then demo it and discuss extensibility. Flipkart is the best-known example; Uber, Swiggy and others use similar formats. Expect HLD rounds from SDE-2 upward, often with India-scale scenarios such as flash sales, inventory consistency and UPI-style payments. [Phase 9](#phase-9-low-level-design-and-machine-coding) covers this track, and it runs in parallel with the HLD phases.

---

## Your Core Free Resource Stack

If you only use a handful of resources, use these. Everything else in this file is a supplement.

| # | Resource | Format | Use it for |
|---|---|---|---|
| 1 | [Hello Interview: System Design in a Hurry](https://www.hellointerview.com/learn/system-design/in-a-hurry/introduction) | Written guide | The backbone: delivery framework, core concepts, key technologies, common patterns and problem breakdowns (most free, some premium) |
| 2 | [Hello Interview on YouTube](https://www.youtube.com/@hello_interview) | Video | Former FAANG interviewers walking through popular problems end to end, plus anonymized real mock interviews |
| 3 | [System Design Primer](https://github.com/donnemartin/system-design-primer) | GitHub | Breadth reference, solved examples and Anki flashcards for spaced repetition |
| 4 | [ByteByteGo on YouTube](https://www.youtube.com/@ByteByteGo) + [System Design 101](https://github.com/ByteByteGoHq/system-design-101) | Visual | Short, visual explanations of protocols, components and real-world case studies |
| 5 | [Jordan has no life](https://www.youtube.com/@jordanhasnolife5163) | Video | Deep concept series (close to book-level depth) plus a large set of problem walkthroughs |
| 6 | [Martin Kleppmann: Distributed Systems lectures](https://www.youtube.com/playlist?list=PLeKd45zvjcDFUEv_ohr_HdUFe97RItdiB) + [lecture notes (PDF)](https://www.cl.cam.ac.uk/teaching/2122/ConcDisSys/dist-sys-notes.pdf) | University course | The theory: time, replication, consensus and consistency (8 lectures split into 23 short videos, Cambridge) |
| 7 | [Arpit Bhayani (Asli Engineering)](https://youtube.com/c/ArpitBhayani) | Video | Database internals, outage dissections and dozens of engineering-blog breakdowns |
| 8 | [Amazon Builders' Library](https://aws.amazon.com/builders-library/) + [Google SRE books](https://sre.google/books/) | Articles and books | How large companies actually handle retries, overload, SLOs and failures |
| 9 | [Aced (formerly Exponent) peer mocks](https://www.tryexponent.com/practice) | Practice | Free live peer mock interviews within monthly credits (this is where Pramp's peer mocks moved) |

> **The one book worth buying (optional):** *Designing Data-Intensive Applications*, 2nd edition (Kleppmann and Riccomini, O'Reilly, 2026). An Indian reprint (Shroff/O'Reilly) is available. Everything in this roadmap works without it; the free Kleppmann lectures cover much of the same theory.

### How the free options compare (analysis)

My assessment of where each resource shines, so you know what to use it for and what not to expect from it:

| Resource | Interview focus | Conceptual depth | Time cost | Best phases | Weakness |
|---|---|---|---|---|---|
| Hello Interview | Very high | Medium | Low–medium | 1, 7, 8 | Some breakdowns are premium; less theory |
| System Design Primer | High | Medium | Medium | 1–4 (reference) | Some examples are dated; text-heavy |
| ByteByteGo | High | Low–medium | Low | Any (quick visuals) | Breadth over depth |
| Jordan has no life | High | High | High | 2, 3, 8 | Long videos; fast pace |
| Kleppmann lectures | Low | Very high | Medium | 3 | Theory only; no interview framing |
| Arpit Bhayani | Medium | High | Medium | 2, 11 | Not organized as an interview course |
| Builders' Library + SRE books | Medium | High | Medium | 4, 5, 11 | Long reads; pick chapters |
| MIT 6.5840 | Very low | Very high | Very high | Deep track only | Graduate-level; overkill for most interviews |

**Bottom line:** Hello Interview + System Design Primer give you the interview skeleton; Jordan and Kleppmann give you depth; ByteByteGo gives you fast visuals; Arpit, the Builders' Library and SRE books give you production judgment, which is exactly what 2026 rubrics reward.

---

## Roadmap at a Glance

```text
                 SYSTEM DESIGN ROADMAP (Core track: 16 weeks + 1 buffer week)

 SEQUENTIAL THEORY (do these in this order)
 Weeks 1-2    Phase 0   Prerequisites: networking, OS, DB basics, build a CRUD app
 Weeks 3-6    Phase 1   Core building blocks: LB, cache, CDN, DBs, queues, blobs, search
 Week  7      Phase 2A  Data core: storage engines, transactions, modeling, serialization
 Weeks 8-9    Phase 3   Distributed systems: consistency, clocks, replication, consensus
 Week  10     Phase 4   APIs, auth, cloud primitives, resilience patterns
 Week  11     Phase 5   Reliability, observability, security, cost
 Week  13     Phase 10  AI, ML and GenAI system design
 Weeks 15+    Phase 11  Advanced: papers, real architectures, senior+ skills

 JUST-IN-TIME MODULES (slotted right before the problems that need them)
 Weeks 11-15  Phase 2B  geo (11) · vectors (13) · streams and CDC (14) · time-series (15)

 PARALLEL TRACKS (running alongside the theory every week)
 Weeks 3-16   Phase 6   Estimation drills (15 minutes, twice a week)
 Week  4+     Phase 7   Interview framework (learn once, use in every problem)
 Weeks 4-16   Phase 8   Practice: 40 problems in 4 tiers + a speed re-solve each week
 Weeks 3-13   Phase 9   LLD and machine coding
 Weeks 8-16   Phase 12  Mock interviews (baseline in week 8), final prep
```

**Want the links instead of the phases?** [The Straight Path](#the-straight-path-every-link-in-order) lists every resource as one numbered sequence you can follow top to bottom.

---

## The Straight Path: Every Link in Order

The phases below explain *what* to learn and *why*. This section is the **flattened version**: one numbered list of links, in the order you open them, from step 1 to step 105. If you don't want to make decisions, work down this list.

**How to read a row:** **Read** / **Watch** = theory · **Build** = write code · **Solve** = a timed practice problem ([the 90-minute loop](#the-90-minute-practice-loop)) · **Drill** = 15-minute estimation ([method](#the-method)) · **LLD** = the [parallel design track](#phase-9-low-level-design-and-machine-coding) · **Say** = the week's checkpoint, out loud, no notes · **Mock** = a [scored interview](#mock-scorecard-score-each-dimension-14).

**Rules:** do the steps in order within a week; the week order is fixed, the order inside a day is yours. Anything marked *(optional)* is droppable when you fall behind. Where a row names a channel rather than a single video, search that channel for the listed topics — playlists get reorganized, channels don't.

### Weeks 1–2 · Phase 0: prerequisites (≈10 hours each)

| # | Type | Resource | What to cover | ~Time |
|---|---|---|---|---|
| 1 | Read | [Hello Interview: In a Hurry — Introduction](https://www.hellointerview.com/learn/system-design/in-a-hurry/introduction) | Orient yourself: what the round is and how it's graded | 20 m |
| 2 | Read | [What happens when you type a URL](https://github.com/alex/what-happens-when) | The whole walkthrough, slowly, looking up what you don't know | 2 h |
| 3 | Read | [Cloudflare Learning Center](https://www.cloudflare.com/learning/) | The DNS, CDN, TLS/SSL and DDoS article sets | 2 h |
| 4 | Watch | [Hussein Nasser](https://www.youtube.com/@hnasr) | Search: TCP vs UDP · HTTP/1.1 vs HTTP/2 vs HTTP/3 · TLS handshake · forward vs reverse proxy · connection pooling | 2.5 h |
| 5 | Watch | [ByteByteGo](https://www.youtube.com/@ByteByteGo) | Short videos on DNS, HTTP versions, TLS | 1 h |
| 6 | Read | [Hello Interview: Core Concepts](https://www.hellointerview.com/learn/system-design/in-a-hurry/core-concepts) | Networking and API sections | 1 h |
| 7 | Say | — | **Checkpoint:** 5 minutes on what happens when you type a URL | 30 m |
| 8 | Watch | [Hussein Nasser](https://www.youtube.com/@hnasr) | Search: database indexing · B-tree · ACID · isolation levels · threads vs processes · blocking vs non-blocking I/O | 2 h |
| 9 | Read | [System Design Primer](https://github.com/donnemartin/system-design-primer) | The *Relational databases*, *NoSQL* and *Caching* sections only | 1.5 h |
| 10 | Build | Postgres + Redis + Docker Compose + [k6](https://k6.io/) | The [Phase 0 hands-on](#hands-on-do-not-skip) app. Load test it, then delete the cache and watch p99 move | 5 h |
| 11 | Read | [CMU 15-445](https://15445.courses.cs.cmu.edu/) *(optional)* | Lectures 1–3 only, if you want database depth early | 2 h |
| 12 | Say | — | **Checkpoint:** why an index speeds up reads and slows down writes | 20 m |

### Week 3 · Scalability, load balancers, estimation, LLD starts (≈8.5 h)

| # | Type | Resource | What to cover | ~Time |
|---|---|---|---|---|
| 13 | Read | [Hello Interview: Key Technologies](https://www.hellointerview.com/learn/system-design/in-a-hurry/key-technologies) | Skim all of it once, then the load balancer and API gateway parts closely | 1.5 h |
| 14 | Read | [System Design Primer](https://github.com/donnemartin/system-design-primer) | *Performance vs scalability*, *Latency vs throughput*, *Availability vs consistency*, *Load balancer*, *Reverse proxy* | 1.5 h |
| 15 | Watch | [ByteByteGo](https://www.youtube.com/@ByteByteGo) | L4 vs L7 load balancing; algorithms; API gateway | 45 m |
| 16 | Read | [Back-of-the-envelope guide](https://systemdesign.one/back-of-the-envelope/) + [latency numbers](https://gist.github.com/jboner/2841832) + [Modern Hardware Numbers](https://hellointerview.substack.com/p/modern-hardware-numbers-for-system) | Learn the [7-step method](#the-method); memorize the ratios, not the digits | 1.5 h |
| 17 | Drill | [Interactive latency numbers](https://colin-scott.github.io/personal_website/research/interactive_latency.html) | Drills 1–2: X/Twitter timeline QPS · WhatsApp messages/sec | 30 m |
| 18 | LLD | [awesome-low-level-design](https://github.com/ashishps1/awesome-low-level-design) | The OOP and SOLID sections | 2 h |
| 19 | Say | — | **Checkpoint:** why p99 matters more than the average; where you'd terminate TLS | 20 m |

### Week 4 · Caching, CDNs, the framework, first problem (≈9 h)

| # | Type | Resource | What to cover | ~Time |
|---|---|---|---|---|
| 20 | Read | [Hello Interview: Delivery Framework](https://www.hellointerview.com/learn/system-design/in-a-hurry/delivery) | **The single most important read in this roadmap.** Learn the [45-minute flow](#the-45-minute-flow) | 1 h |
| 21 | Read | [interviewing.io: Senior Engineer's Guide](https://interviewing.io/guides/system-design-interview) | All four parts; note every green and red flag | 1.5 h |
| 22 | Read | [Hello Interview: Key Technologies](https://www.hellointerview.com/learn/system-design/in-a-hurry/key-technologies) + [Primer](https://github.com/donnemartin/system-design-primer) | Redis and CDN sections; Primer's *Cache* and *CDN* | 1.5 h |
| 23 | Watch | [Jordan has no life](https://www.youtube.com/@jordanhasnolife5163) | The caching concept videos: strategies, invalidation, stampede | 1 h |
| 24 | Solve | **#1 URL shortener** → compare with [Primer's solution](https://github.com/donnemartin/system-design-primer) and the [Hello Interview breakdown](https://www.hellointerview.com/learn/system-design/problem-breakdowns/overview) | Your first timed solve, on [Excalidraw](https://excalidraw.com/), out loud | 1.5 h |
| 25 | LLD | [Refactoring.Guru](https://refactoring.guru/design-patterns) | Strategy, Factory Method, Observer — read and code each once | 2 h |
| 26 | Drill | — | Drills 3–4: YouTube storage per day · Instagram photo storage per year | 30 m |

### Week 5 · Databases, replication, sharding (≈10 h)

| # | Type | Resource | What to cover | ~Time |
|---|---|---|---|---|
| 27 | Read | [Primer](https://github.com/donnemartin/system-design-primer) | *Database* in full: replication, federation, sharding, denormalization, SQL tuning | 2 h |
| 28 | Watch | [Jordan has no life](https://www.youtube.com/@jordanhasnolife5163) | Partitioning and replication concept videos | 1.5 h |
| 29 | Watch | [Arpit Bhayani](https://youtube.com/c/ArpitBhayani) + [knowledge base](https://github.com/arpitbbhayani/knowledge-base) | Consistent hashing; indexing internals; hot partitions | 1.5 h |
| 30 | Read | [System Design 101](https://github.com/ByteByteGoHq/system-design-101) | The database and SQL-vs-NoSQL sections, for the diagrams | 45 m |
| 31 | Solve | **#2 Pastebin** (60 min) · **#3 Distributed rate limiter** (90 min) | Rate limiter: get the Redis atomicity right | 2.5 h |
| 32 | LLD | [awesome-low-level-design](https://github.com/ashishps1/awesome-low-level-design) | **Parking lot**, timed, then read the reference solution | 2 h |
| 33 | Say | — | **Checkpoint:** how you'd serve "all posts from the last hour" when sharded by `user_id` | 20 m |

### Week 6 · Queues, streams, blobs, search, real-time (≈11 h)

| # | Type | Resource | What to cover | ~Time |
|---|---|---|---|---|
| 34 | Read | [Hello Interview: Key Technologies](https://www.hellointerview.com/learn/system-design/in-a-hurry/key-technologies) + [Patterns](https://www.hellointerview.com/learn/system-design/in-a-hurry/patterns) | Kafka, queues, Elasticsearch, blob storage; then every pattern | 2 h |
| 35 | Watch | [Jordan has no life](https://www.youtube.com/@jordanhasnolife5163) | Kafka internals; delivery semantics; idempotency | 1.5 h |
| 36 | Read | [Kafka documentation](https://kafka.apache.org/documentation/) | The **Design** section only (the log, partitions, consumer groups, offsets) | 1 h |
| 37 | Watch | [ByteByteGo](https://www.youtube.com/@ByteByteGo) | Polling vs SSE vs WebSockets; scaling WebSockets | 45 m |
| 38 | Solve | **#4 Unique ID** (60 m) · **#5 Notification system** (90 m) · **#6 Distributed counter** (90 m) | — | 3.5 h |
| 39 | Solve | **Re-solve #1** (25-minute speed run) | Requirements → API → design → 3 deep dives. Diff against your old notes | 30 m |
| 40 | LLD | [awesome-low-level-design](https://github.com/ashishps1/awesome-low-level-design) | **Thread-safe LRU cache**, timed | 1.5 h |

### Week 7 · Phase 2A: storage engines, transactions, serialization (≈10 h)

| # | Type | Resource | What to cover | ~Time |
|---|---|---|---|---|
| 41 | Watch | [Jordan has no life](https://www.youtube.com/@jordanhasnolife5163) | B-trees vs LSM-trees; WAL; compaction; transactions and isolation | 2 h |
| 42 | Read | [Hermitage](https://github.com/ept/hermitage) *(optional)* | What real databases actually do at each isolation level | 45 m |
| 43 | Read | [Protocol Buffers language guide](https://protobuf.dev/programming-guides/proto3/) | *Updating a message type*: why field numbers are forever | 45 m |
| 44 | Read | [Confluent: schema evolution and compatibility](https://docs.confluent.io/platform/current/schema-registry/fundamentals/schema-evolution.html) | Backward vs forward compatibility; what a schema registry buys you | 45 m |
| 45 | Solve | **#7 Typeahead** (90 m) · **#8 Leaderboard** (60 m) · **#9 Distributed cache** (90 m) | #9 is deliberately early — you revisit it in week 9 | 4 h |
| 46 | Solve | **Re-solve #3** (speed run) | — | 30 m |
| 47 | LLD | [awesome-low-level-design](https://github.com/ashishps1/awesome-low-level-design) | **Splitwise**, timed | 1.5 h |
| 48 | Say | — | **Checkpoint:** write skew with a concrete example; pick a database for 5 workloads | 30 m |

### Weeks 8–9 · Phase 3: distributed systems (≈11 h and ≈10 h)

| # | Type | Resource | What to cover | ~Time |
|---|---|---|---|---|
| 49 | Watch | [Kleppmann: Distributed Systems](https://www.youtube.com/playlist?list=PLeKd45zvjcDFUEv_ohr_HdUFe97RItdiB) + [notes PDF](https://www.cl.cam.ac.uk/teaching/2122/ConcDisSys/dist-sys-notes.pdf) | **Lectures 1–5:** intro, system models, time and clocks, broadcast, replication | 3 h |
| 50 | Read | [Jepsen: consistency models](https://jepsen.io/consistency) | The map; be able to place linearizable, causal, read-your-writes, eventual | 45 m |
| 51 | Solve | **#10 News feed** (90 m) · **#11 Instagram** (60 m) · **re-solve #5** | Fan-out on write vs read; the celebrity problem | 3 h |
| 52 | Mock | [Aced peer mocks](https://www.tryexponent.com/practice) or [HI Guided Practice](https://www.hellointerview.com/practice/overview) | **Mock #1 (baseline).** Use a problem you've already solved | 1.5 h |
| 53 | LLD | [awesome-low-level-design](https://github.com/ashishps1/awesome-low-level-design) | **Elevator system**, timed | 1.5 h |
| 54 | Watch | [Kleppmann playlist](https://www.youtube.com/playlist?list=PLeKd45zvjcDFUEv_ohr_HdUFe97RItdiB) | **Lectures 6–8:** consensus, replica consistency, case studies (CRDTs, Spanner) | 2.5 h |
| 55 | Watch | [Raft visualization](https://thesecretlivesofdata.com/raft/) → [raft.github.io](https://raft.github.io/) | Visualization first, then the paper's figures 2 and 3 | 1.5 h |
| 56 | Read | [Kleppmann: How to do distributed locking](https://martin.kleppmann.com/2016/02/08/how-to-do-distributed-locking.html) | Why a lock needs a fencing token | 45 m |
| 57 | Read | [Transactional outbox](https://microservices.io/patterns/data/transactional-outbox.html) + [Saga](https://microservices.io/patterns/data/saga.html) | Both patterns; orchestration vs choreography | 45 m |
| 58 | Read | [Distributed Systems for Fun and Profit](https://book.mixu.net/distsys/) *(optional)* | Chapters 2–4 | 1.5 h |
| 59 | Solve | **#12 Chat** (90 m) · **#13 YouTube** (90 m) · **re-solve #9** using quorums | — | 3.5 h |
| 60 | LLD | [awesome-low-level-design](https://github.com/ashishps1/awesome-low-level-design) | **BookMyShow**, timed | 1.5 h |
| 61 | Say | — | **Checkpoint:** why timeouts alone can't make a safe lock; Raft leader crash; exactly-once *delivery* vs *processing* | 30 m |

### Week 10 · Phase 4: APIs, auth, cloud, resilience (≈11.5 h)

| # | Type | Resource | What to cover | ~Time |
|---|---|---|---|---|
| 62 | Read | [Timeouts, retries and backoff with jitter](https://aws.amazon.com/builders-library/timeouts-retries-and-backoff-with-jitter/) | Required reading. Retry budgets and why jitter matters | 1 h |
| 63 | Read | [Making retries safe with idempotent APIs](https://aws.amazon.com/builders-library/making-retries-safe-with-idempotent-APIs/) | How to design an idempotency key | 1 h |
| 64 | Read | [Avoiding fallback in distributed systems](https://aws.amazon.com/builders-library/avoiding-fallback-in-distributed-systems/) *(optional)* | Senior-level, counter-intuitive | 45 m |
| 65 | Watch | [ByteByteGo](https://www.youtube.com/@ByteByteGo) | REST vs gRPC vs GraphQL; OAuth 2.0 and OIDC; JWT | 1 h |
| 66 | Read | [microservices.io patterns](https://microservices.io/patterns/) | Circuit breaker, bulkhead, service discovery, CQRS, event sourcing | 45 m |
| 67 | Read | [Kubernetes Basics](https://kubernetes.io/docs/tutorials/kubernetes-basics/) + [Overview](https://kubernetes.io/docs/concepts/overview/) | Enough to say "pod, service, deployment, HPA" and mean it | 45 m |
| 68 | Solve | **#14 Dropbox** (90 m) · **#15 Ticketmaster** (90 m) · **re-solve #10** | Ticketmaster: seat contention and reservation TTLs | 3.5 h |
| 69 | Mock | [Aced](https://www.tryexponent.com/practice) | **Mock #2** | 1.5 h |
| 70 | LLD | [workat.tech machine coding](https://workat.tech/machine-coding/) | Read the format guide, then **Snake and Ladder** timed | 1.5 h |
| 71 | Say | — | **Checkpoint:** a retry-safe "place order" API; three ways to stop a retry storm | 30 m |

### Week 11 · Phase 5 + geo module (≈13.5 h — the heaviest week)

| # | Type | Resource | What to cover | ~Time |
|---|---|---|---|---|
| 72 | Read | [SRE ch. 4: Service Level Objectives](https://sre.google/sre-book/service-level-objectives/) + [ch. 6: Monitoring](https://sre.google/sre-book/monitoring-distributed-systems/) | SLI vs SLO vs SLA, error budgets; the four golden signals; symptom-based alerting | 1.5 h |
| 73 | Read | [SRE ch. 21: Handling Overload](https://sre.google/sre-book/handling-overload/) + [ch. 22: Cascading Failures](https://sre.google/sre-book/addressing-cascading-failures/) | Load shedding, criticality, client throttling, cold caches | 1.5 h |
| 74 | Read | [Workload isolation using shuffle sharding](https://aws.amazon.com/builders-library/workload-isolation-using-shuffle-sharding/) + [load shedding](https://aws.amazon.com/builders-library/using-load-shedding-to-avoid-overload/) *(second one optional)* | Blast radius, cells, shuffle sharding | 1.25 h |
| 75 | Read | [The Tail at Scale](https://research.google/pubs/the-tail-at-scale/) | Hedged and tied requests; why p99 gets worse as you add fan-out | 45 m |
| 76 | Read | [Cost anchors](#k-cost-anchors-what-actually-drives-the-bill) + [OWASP Top 10](https://owasp.org/www-project-top-ten/) (skim) | The top two cost drivers and a lever for each design you've done | 45 m |
| 77 | Read | [Uber H3](https://h3geo.org/) | Geohash vs quadtree vs S2 vs H3; pick one and know it properly | 45 m |
| 78 | Solve | **#16 Uber** (90 m) · **#17 Yelp** (60 m) · **#18 Web crawler** (90 m) · **re-solve #12** | — | 4.5 h |
| 79 | LLD | [awesome-low-level-design](https://github.com/ashishps1/awesome-low-level-design) | **Thread-safe rate limiter**, timed | 1.5 h |
| 80 | Mock | [Aced](https://www.tryexponent.com/practice) | **Mock #3** | 1.5 h |
| 81 | Say | — | **Checkpoint:** 99.9% in minutes/month; three ways to cut video-streaming cost by 30%; the fan-out p99 question | 30 m |

> **Week 11 is over budget and you should plan for it.** As scheduled it holds all of Phase 5, the geo module, three new problems, a re-solve, an LLD problem and a mock — about 13.5 hours against a 12-hour target. Pick one before the week starts: spend your [buffer week](#weekly-time-budget) here, push **#18 Web crawler** to week 15, or drop the optional reading in steps 74 and 76. Don't drop the mock.

### Week 12 · Money, contention, consistency under load (≈11 h)

| # | Type | Resource | What to cover | ~Time |
|---|---|---|---|---|
| 82 | Watch | [Arpit Bhayani](https://youtube.com/c/ArpitBhayani) | Payment systems, idempotency, double-entry ledgers, inventory consistency | 1.5 h |
| 83 | Read | Your [trade-off journal](#five-rules-that-save-months) | Review every entry so far; you should have 25+ | 45 m |
| 84 | Solve | **#19 Payments** (90 m) · **#20 Flash sale** (90 m) · **#21 Food delivery** (90 m) · **re-solve #15** | — | 5 h |
| 85 | Mock | [Aced](https://www.tryexponent.com/practice) | **Mock #4** | 1.5 h |
| 86 | LLD | [awesome-low-level-design](https://github.com/ashishps1/awesome-low-level-design) | **Food ordering**, timed | 1.5 h |

### Week 13 · Phase 10: AI, ML and GenAI (≈12 h)

| # | Type | Resource | What to cover | ~Time |
|---|---|---|---|---|
| 87 | Read | [Building A Generative AI Platform (Chip Huyen)](https://huyenchip.com/2024/07/25/genai-platform.html) | **Read this one twice.** It is the reference architecture for #36 | 1.5 h |
| 88 | Read | [Patterns for Building LLM-based Systems (Eugene Yan)](https://eugeneyan.com/writing/llm-patterns/), then [Start Here](https://eugeneyan.com/start-here/) and [Applied LLMs](https://applied-llms.org/) *(both optional)* | Evals, RAG, caching, guardrails, defensive UX; then two-stage retrieval and ranking | 1.5 h |
| 89 | Read | [Building effective agents (Anthropic)](https://www.anthropic.com/research/building-effective-agents) | Workflows vs agents; the five patterns | 45 m |
| 90 | Read | [Evidently AI: ML and LLM case studies](https://www.evidentlyai.com/ml-system-design) | Filter to RAG and recommendations; read three real write-ups | 1 h |
| 91 | LLD | [awesome-low-level-design](https://github.com/ashishps1/awesome-low-level-design) | **In-memory key-value store with transactions**, timed | 1.5 h |
| 92 | Solve | **#35 RAG system** (90 m) · **#36 LLM gateway** (90 m) · **re-solve #16** | Access control at retrieval time; token accounting | 3.5 h |
| 93 | Mock | [Aced](https://www.tryexponent.com/practice) | **Mock #5** — ask for one AI-flavored prompt | 1.5 h |
| 94 | Say | — | **Checkpoint:** where the 3-second p95 goes in a RAG design; how you'd find a doubled LLM bill | 30 m |

### Week 14 · Streams, CDC and infrastructure problems (≈11.5 h)

| # | Type | Resource | What to cover | ~Time |
|---|---|---|---|---|
| 95 | Watch | [Jordan has no life](https://www.youtube.com/@jordanhasnolife5163) | Stream processing: windows, event vs processing time, watermarks, Lambda vs Kappa | 2 h |
| 96 | Read | [System Design 101](https://github.com/ByteByteGoHq/system-design-101) | CDC, the outbox, batch vs stream, OLTP vs OLAP sections | 1 h |
| 97 | Solve | **#25 Message queue** (90 m) · **#27 Top-K** (90 m) · **#28 Ad click aggregator** (90 m) · **re-solve #19** | — | 5 h |
| 98 | Mock | [Aced](https://www.tryexponent.com/practice) + peer group | **Mocks #6–7** | 3 h |

### Weeks 15–16 · Papers, real architectures, final prep (≈12 h and ≈11.5 h)

| # | Type | Resource | What to cover | ~Time |
|---|---|---|---|---|
| 99 | Read | [The 10-paper reading list](#the-10-paper-reading-list) | Abstract, intro, design, conclusion only. Two or three papers, not ten | 3 h |
| 100 | Read | [High Scalability](https://highscalability.com/) · [awesome-scalability](https://github.com/binhnguyennus/awesome-scalability) · [engineering blogs](https://github.com/kilimchoi/engineering-blogs) | One architecture a week, summarized in five lines | 1.5 h |
| 101 | Solve | **#26 Job scheduler** + full 60-minute re-solves of your 5 weakest | — | 4 h |
| 102 | Mock | [Aced](https://www.tryexponent.com/practice) + peer group | **Mocks #8–9** | 3 h |
| 103 | Read | [Stretch problems for your role](#which-stretch-problems-to-add) + company engineering blogs | Their products, their blog, recent interview reports | 2 h |
| 104 | Solve | Full re-solves of 5 more; rehearse your [project deep dive](#prepare-your-project-deep-dive) out loud | — | 4 h |
| 105 | Mock | [Aced](https://www.tryexponent.com/practice) + peer group | **Mocks #10–11**, then the [readiness checklist](#final-interview-readiness-checklist) | 3 h |

### The short list, if you only open five things

1. [Hello Interview: System Design in a Hurry](https://www.hellointerview.com/learn/system-design/in-a-hurry/introduction) — the framework and the components
2. [System Design Primer](https://github.com/donnemartin/system-design-primer) — the reference and the flashcards
3. [Kleppmann's lectures](https://www.youtube.com/playlist?list=PLeKd45zvjcDFUEv_ohr_HdUFe97RItdiB) — the theory
4. [Amazon Builders' Library](https://aws.amazon.com/builders-library/) + [Google SRE book](https://sre.google/books/) — production judgment
5. [Aced peer mocks](https://www.tryexponent.com/practice) — someone to practice against

---

## Phase 0: Prerequisites

**Duration:** Weeks 1–2 (skip if you already build backend services)
**Goal:** Understand how a request travels from a browser to a database and back.

### Topics checklist

**Networking**
- [ ] TCP/IP vs OSI model: what actually matters is L4 (transport) vs L7 (application)
- [ ] TCP vs UDP; the 3-way handshake; why new TCP connections are expensive
- [ ] HTTP/1.1 vs HTTP/2 (multiplexing) vs HTTP/3 (QUIC over UDP); keep-alive
- [ ] HTTPS and TLS at a high level: handshake, certificates, why TLS is often terminated at the load balancer
- [ ] DNS resolution end to end: recursive resolver, root, TLD, authoritative servers, TTLs and caching
- [ ] IP addresses, ports, NAT; forward vs reverse proxies

**Operating systems**
- [ ] Processes vs threads; context switching; concurrency vs parallelism
- [ ] Locks, deadlocks, race conditions
- [ ] Memory hierarchy: CPU cache → RAM → SSD → HDD → network (the orders of magnitude matter)
- [ ] Blocking vs non-blocking I/O; event loops (why Nginx and Node.js handle many connections)

**Databases 101**
- [ ] Relational model, SQL, joins, primary and foreign keys
- [ ] Indexes (B-trees): why lookups drop from O(n) to O(log n), and what they cost on writes
- [ ] Transactions and ACID
- [ ] Normalization vs denormalization

**Web fundamentals**
- [ ] Client-server model; the request/response lifecycle
- [ ] Cookies, sessions and tokens
- [ ] REST basics: resources, HTTP verbs, status codes

### Resources

| Priority | Resource | Notes |
|---|---|---|
| Primary | [Hello Interview: Core Concepts](https://www.hellointerview.com/learn/system-design/in-a-hurry/core-concepts) | Networking essentials, API design and data modeling, framed for interviews |
| Primary | [What happens when you type a URL (GitHub)](https://github.com/alex/what-happens-when) | The classic end-to-end walkthrough |
| Supplement | [Hussein Nasser (YouTube)](https://www.youtube.com/@hnasr) | Backend fundamentals: TCP, HTTP/2 and HTTP/3, proxies, connection pooling, database internals |
| Supplement | [ByteByteGo (YouTube)](https://www.youtube.com/@ByteByteGo) | Short visual videos on HTTP versions, DNS and TLS |
| Optional depth | [CMU 15-445 Database Systems](https://15445.courses.cs.cmu.edu/) | Free university database course (lectures on YouTube) |

### Hands-on (do not skip)

Build a small REST API (a to-do app or a mini URL shortener) in your main language with **PostgreSQL**, add **Redis** caching on one read path, run it with **Docker Compose**, and load test it with a free tool such as **k6**. Watch what happens to p99 latency when you remove the cache. This one exercise makes every later concept concrete.

> **Want it spelled out step by step?** This is [Lab 0 in the hands-on projects roadmap](hands-on-projects-roadmap.md#lab-0-the-baseline-service-weeks-12), which gives you the schema, the seed data, the four experiments to run and the numbers you should expect. That companion file runs a build track alongside all 16 weeks.

### Checkpoint

- Explain, in 5 minutes, everything that happens when you type a URL and press Enter.
- Explain why adding an index speeds up reads but slows down writes.

---

## Phase 1: Core Building Blocks

**Duration:** Weeks 3–6
**Goal:** Know every standard component well enough to explain what it does, when to use it, when *not* to use it, and how it fails.

> **Primary resources for this whole phase:** [Hello Interview: Key Technologies](https://www.hellointerview.com/learn/system-design/in-a-hurry/key-technologies) and [Common Patterns](https://www.hellointerview.com/learn/system-design/in-a-hurry/patterns), with the [System Design Primer](https://github.com/donnemartin/system-design-primer) as the reference for each topic. Use ByteByteGo videos whenever you want a visual explanation.

### 1.1 Scalability fundamentals

- [ ] Vertical vs horizontal scaling; why stateless services scale horizontally
- [ ] Latency vs throughput vs bandwidth; percentiles (p50, p95, p99) and why averages lie
- [ ] Availability vs reliability vs durability; single points of failure (SPOF); redundancy
- [ ] Read-heavy vs write-heavy systems (this one fact shapes most designs)

**Must answer:** *Why is p99 latency usually more important than average latency?*

### 1.2 Load balancers, reverse proxies and API gateways

- [ ] L4 vs L7 load balancing
- [ ] Algorithms: round robin, weighted, least connections, IP hash, consistent hashing
- [ ] Health checks, connection draining, sticky sessions (and why to avoid them)
- [ ] Global load balancing: GeoDNS and anycast
- [ ] Reverse proxy vs load balancer vs API gateway (auth, rate limiting, routing, TLS termination)

**Must answer:** *Where would you terminate TLS, and why?*

### 1.3 Caching

- [ ] Cache layers: browser/client → CDN → API gateway → application → distributed cache → database buffer pool
- [ ] Strategies: cache-aside (lazy loading), read-through, write-through, write-behind, write-around
- [ ] Eviction policies: LRU, LFU, FIFO, TTL
- [ ] Invalidation, the hard part: TTLs, explicit deletes, versioned keys, event-driven invalidation
- [ ] Failure modes: cache stampede (thundering herd), hot keys, cache penetration (lookups for keys that don't exist; fix with negative caching or Bloom filters), cold starts
- [ ] Redis vs Memcached: data structures, persistence, replication

**Must answer:** *With cache-aside, what happens if you update the database and the cache delete then fails?*

### 1.4 Content delivery networks (CDNs)

- [ ] Pull vs push CDNs; cache keys and TTLs; cache hit ratio
- [ ] Serving static assets, images and video segments from the edge
- [ ] Signed URLs for private content; edge compute basics

**Extra resource:** [Cloudflare Learning Center](https://www.cloudflare.com/learning/): clear free articles on CDNs, DNS and DDoS.

### 1.5 Databases

- [ ] SQL vs NoSQL: decide by access patterns, consistency needs and scale, not hype
- [ ] NoSQL families: key-value, document, wide-column, graph, time-series, search engines, vector databases
- [ ] Indexing: primary, secondary, composite and covering indexes; selectivity
- [ ] Replication: leader-follower, multi-leader, leaderless; synchronous vs asynchronous; replication lag and read-your-writes problems
- [ ] Partitioning and sharding: range vs hash vs directory-based; choosing a shard key; hot partitions; resharding
- [ ] Consistent hashing with virtual nodes
- [ ] Denormalization and read models
- [ ] Connection pooling and read replicas, and when to add each

**Must answer:** *You shard posts by `user_id`. How do you serve "all posts from the last hour"?*

**Extra resources:** Arpit Bhayani's database videos and his [knowledge base](https://github.com/arpitbbhayani/knowledge-base); Jordan has no life's concept playlists.

### 1.6 Asynchronous processing: queues and streams

- [ ] Why async: decoupling, absorbing traffic spikes, retries, long-running work
- [ ] Message queues (SQS, RabbitMQ) vs log-based streams (Kafka, Kinesis) vs pub/sub
- [ ] Delivery semantics: at-most-once, at-least-once and "exactly-once" (in practice: at-least-once plus idempotency)
- [ ] Ordering and partitions; consumer groups; offsets
- [ ] Dead-letter queues, retries with backoff, poison messages
- [ ] Backpressure

**Must answer:** *How do you make sure a payment is not charged twice if the consumer crashes after charging but before acknowledging the message?*

### 1.7 Blob and object storage

- [ ] When data belongs in S3-style object storage vs a database
- [ ] Pre-signed URLs for direct client upload and download
- [ ] Multipart and resumable uploads; chunking; content hashing for deduplication

### 1.8 Search

- [ ] Inverted indexes, tokenization and relevance basics
- [ ] When to add Elasticsearch/OpenSearch, and how to keep it in sync with the source of truth (change data capture)

### 1.9 Real-time communication

- [ ] Short polling vs long polling vs Server-Sent Events (SSE) vs WebSockets vs WebRTC
- [ ] Scaling WebSocket servers: connection registries, pub/sub fan-out between servers, heartbeats
- [ ] Start simple (polling) and upgrade only when latency requirements demand it

### Checkpoint

For each component above, give a 2-minute explanation covering **what, why, when not to use it and how it fails.** Record yourself once; it is uncomfortable and very effective.

---

## Phase 2: Data and Storage Deep Dive

**Duration:** The core module (2A) in week 7, plus short just-in-time modules (2B) in weeks 11, 13 and 14.
**Goal:** Go from "use a NoSQL database" to explaining *which* database, *which* keys and *which* consistency guarantees. This is where many candidates separate.
**Why it's split:** Covering everything in one week overloads it, and topics like stream processing stick far better when you learn them right before the problems that need them.

### 2A: Core module (week 7)

**Storage engines**
- [ ] B-trees vs LSM-trees: memtable, SSTables, compaction, write and read amplification
- [ ] Write-ahead logs (WAL) and crash recovery
- [ ] Why Cassandra- and RocksDB-style stores are write-friendly while classic B-tree stores favor reads

**Transactions and isolation**
- [ ] Isolation levels: read committed, repeatable read, snapshot isolation, serializable
- [ ] Anomalies: dirty reads, non-repeatable reads, phantoms, lost updates, write skew
- [ ] MVCC; pessimistic locking (`SELECT ... FOR UPDATE`) vs optimistic concurrency (version columns, compare-and-set)

**Data modeling for access patterns**
- [ ] Start from queries, not entities (especially with NoSQL)
- [ ] Partition key + sort/clustering key design (DynamoDB, Cassandra)
- [ ] Global vs local secondary indexes; hot keys and write sharding
- [ ] Modeling time-ordered data: feeds, chats, events

**Serialization and schema evolution**
- [ ] JSON vs Protobuf/Avro/Thrift: size, speed, schema enforcement, human readability
- [ ] Backward compatibility (new code reads old data) vs forward compatibility (old code reads new data), and why you need both during a rolling deploy
- [ ] Why Protobuf field numbers are permanent, and what breaks when you reuse one
- [ ] Schema registries in streaming pipelines; who validates a producer's schema
- [ ] Compression (gzip, Snappy, zstd) and where it pays for itself

**Why this matters in interviews:** every design with a queue, a stream or a versioned API has an implicit schema-evolution question in it. "How do you deploy a new field without breaking consumers?" is a very common follow-up, and it is also the honest answer to "how do you do a zero-downtime migration?"

### 2B: Just-in-time modules

| Module | When | Right before | Topics |
|---|---|---|---|
| Geospatial indexing | Week 11 | #16 Uber, #17 Yelp | Geohash, quadtrees, Google S2, [Uber H3](https://h3geo.org/); high-frequency location writes |
| Data lifecycle and privacy | Week 12 | #19 Payments, #20 Flash sale | Hot/warm/cold tiers, archival, retention and deletion (privacy laws such as GDPR or India's DPDP Act) |
| Vectors and embeddings | Week 13 (with [Phase 10](#phase-10-ai-ml-and-genai-system-design)) | #35 RAG | Embeddings, approximate nearest-neighbor search (HNSW), hybrid search |
| Stream processing and CDC | Week 14 | #27 Top-K, #28 Ad click aggregator | Batch (MapReduce, Spark) vs streams (Flink, Kafka Streams); tumbling, sliding and session windows; event vs processing time; watermarks and late data; Lambda vs Kappa; change data capture and the transactional outbox |
| OLTP vs OLAP | Week 14 (with the stream module) | #28 Ad click aggregator, #29 Metrics | Row vs columnar storage; why analytics doesn't belong on your production database; warehouses and lakehouses (BigQuery, Snowflake, ClickHouse); ETL vs ELT; the serving layer that dashboards actually read |
| Time-series and graph data | Week 15 (stretch) | #29 Metrics, social-graph questions | Downsampling, rollups, retention; adjacency lists in SQL vs graph databases |

### Resources

| Priority | Resource | Notes |
|---|---|---|
| Primary | [Jordan has no life](https://www.youtube.com/@jordanhasnolife5163): concept playlists | Storage engines, replication, partitioning, transactions and stream processing in depth |
| Primary | Hello Interview technology deep dives (linked from [Key Technologies](https://www.hellointerview.com/learn/system-design/in-a-hurry/key-technologies)) | Databases, caches, queues and search engines, framed for interviews |
| Supplement | [Arpit Bhayani](https://youtube.com/c/ArpitBhayani) | Database internals and real-world engineering-blog dissections |
| Supplement | [Transactional outbox](https://microservices.io/patterns/data/transactional-outbox.html) and [Saga](https://microservices.io/patterns/data/saga.html) (microservices.io) | Short, precise pattern write-ups |
| Optional depth | [Hermitage](https://github.com/ept/hermitage) | Kleppmann's tests of how real databases implement isolation levels |
| Optional depth | [CMU 15-445](https://15445.courses.cs.cmu.edu/) | Storage, indexing and concurrency-control lectures |

### Checkpoint

- Pick a database for a banking ledger, a chat history store, a product catalog, a metrics system and a social graph. Justify each choice in two sentences.
- Explain write skew with a concrete example (for instance, two on-call doctors who both go off call at the same time).

---

## Phase 3: Distributed Systems Core

**Duration:** Weeks 8–9
**Goal:** Understand *why* distributed systems are hard (partial failures, unreliable clocks, network partitions) and the standard tools for dealing with them.

### Topics checklist

**Foundations**
- [ ] The fallacies of distributed computing; partial failures; why a timeout can't tell "slow" from "dead"
- [ ] CAP theorem (what it really says: during a network partition, choose consistency or availability) and PACELC (otherwise, choose latency or consistency)
- [ ] Consistency models: linearizability, causal consistency, read-your-writes, monotonic reads, eventual consistency

**Time and ordering**
- [ ] Physical clocks, NTP and clock skew: why "last write wins" by timestamp can silently lose data
- [ ] Lamport clocks, vector clocks, hybrid logical clocks
- [ ] How Google Spanner uses bounded clock uncertainty (TrueTime)

**Replication and quorums**
- [ ] Quorums: N, R, W and the R + W > N rule
- [ ] Sloppy quorums, hinted handoff, read repair, anti-entropy with Merkle trees
- [ ] Conflict resolution: last-write-wins, version vectors, CRDTs

**Consensus and coordination**
- [ ] Raft: leader election, log replication and safety (know it at whiteboard level)
- [ ] Paxos (conceptually); ZooKeeper and etcd as coordination services
- [ ] Leader election, leases, distributed locks and **fencing tokens**
- [ ] Failure detection: heartbeats, gossip protocols, phi-accrual detectors

**Distributed transactions**
- [ ] Two-phase commit, and why a coordinator failure blocks it
- [ ] Sagas: orchestration vs choreography; compensating actions
- [ ] Idempotency keys, deduplication and the outbox pattern

### The algorithm toolbox (these show up in designs constantly)

| Tool | What it solves | Classic problem where it appears |
|---|---|---|
| Consistent hashing | Spreading keys across nodes with minimal reshuffling | Distributed cache, key-value store |
| Bloom filter | "Definitely not present" checks with tiny memory | Web crawler dedupe, cache penetration |
| Count-Min Sketch | Approximate frequency counts in a stream | Top-K / trending |
| HyperLogLog | Approximate unique counts (cardinality) | Unique visitors, distinct viewers |
| Token bucket, leaky bucket, sliding window | Rate limiting | API rate limiter |
| Geohash, quadtree, H3 | Proximity queries | Yelp, Uber, food delivery |
| Trie | Prefix lookups | Typeahead / autocomplete |
| Skip list / sorted set | Ordered ranking with fast updates | Leaderboard (Redis sorted sets) |
| Merkle tree | Efficient comparison of replicas | Anti-entropy in Dynamo-style stores |
| Snowflake-style IDs | Unique, roughly time-ordered IDs without per-ID coordination (each generator only needs a unique worker ID) | ID generator, URL shortener |

### Resources

| Priority | Resource | Notes |
|---|---|---|
| Primary | [Kleppmann: Distributed Systems lectures](https://www.youtube.com/playlist?list=PLeKd45zvjcDFUEv_ohr_HdUFe97RItdiB) + [notes](https://www.cl.cam.ac.uk/teaching/2122/ConcDisSys/dist-sys-notes.pdf) | Week 8: lectures 1–5 (introduction, system models, time, broadcast, replication). Week 9: lectures 6–8 (consensus, replica consistency, case studies including CRDTs and Spanner) |
| Primary | [Raft site](https://raft.github.io/) + [Raft visualization](https://thesecretlivesofdata.com/raft/) | Watch the visualization before reading the paper |
| Supplement | [Jepsen consistency models map](https://jepsen.io/consistency) | The clearest map of consistency guarantees |
| Supplement | [How to do distributed locking (Kleppmann)](https://martin.kleppmann.com/2016/02/08/how-to-do-distributed-locking.html) | Why locks need fencing tokens |
| Supplement | [Distributed Systems for Fun and Profit](https://book.mixu.net/distsys/) | A short free book |
| Optional depth | [MIT 6.5840 Distributed Systems (Spring 2026)](https://pdos.csail.mit.edu/6.824/) | Papers, lecture notes and Go labs (MapReduce, Raft, a fault-tolerant sharded key-value store) |

### Checkpoint

- Explain why you can't build a safe distributed lock with timeouts alone.
- Walk through what happens in Raft when the leader crashes mid-replication.
- Explain the difference between "exactly-once delivery" and "exactly-once processing".

---

## Phase 4: APIs, Communication and Architecture Patterns

**Duration:** Week 10
**Goal:** Design clean interfaces between clients and services, and make services resilient to each other's failures.

### Topics checklist

**API design**
- [ ] REST (the default for public APIs), gRPC (fast internal service-to-service calls), GraphQL (flexible, client-driven reads), and when each fits
- [ ] Resource naming, status codes, error formats
- [ ] Pagination: offset vs cursor-based (cursors for feeds and fast-changing data)
- [ ] Versioning and backward compatibility
- [ ] Idempotency keys for unsafe operations (payments, orders)
- [ ] Webhooks (with signatures and retries); rate-limit headers

**Authentication and authorization**
- [ ] Sessions vs tokens; JWTs and their revocation problem
- [ ] OAuth 2.0 and OpenID Connect flows at a high level
- [ ] API keys; service-to-service authentication (mTLS)
- [ ] RBAC vs ABAC

**Architecture styles**
- [ ] Monolith vs modular monolith vs microservices: start simple, split for team or scaling reasons
- [ ] Service discovery; API gateway and Backend-for-Frontend (BFF)
- [ ] Service mesh and sidecars (what problem they solve)
- [ ] Event-driven architecture, CQRS, event sourcing (and their costs)
- [ ] Serverless: where it fits and where it doesn't (cold starts, long-running work, cost at high steady load)

**Cloud and infrastructure primitives**
- [ ] VMs vs containers vs serverless functions; what Docker packages and what Kubernetes orchestrates (pods, services, deployments, autoscaling)
- [ ] Managed building blocks you can name in a design: object storage, managed queues, managed databases, CDNs, load balancers
- [ ] Regions and availability zones, and what "multi-AZ" actually protects you from
- [ ] Infrastructure as code and immutable deployments (concept level)

**Resilience patterns**
- [ ] Timeouts on every network call
- [ ] Retries with exponential backoff **and jitter**; retry budgets
- [ ] Idempotent APIs, so retries are safe
- [ ] Circuit breakers, bulkheads, load shedding, backpressure
- [ ] Graceful degradation, and why Amazon prefers to avoid fallback paths

### Resources

| Priority | Resource | Notes |
|---|---|---|
| Primary | [Timeouts, retries and backoff with jitter](https://aws.amazon.com/builders-library/timeouts-retries-and-backoff-with-jitter/) (Amazon Builders' Library) | Required reading |
| Primary | [Making retries safe with idempotent APIs](https://aws.amazon.com/builders-library/making-retries-safe-with-idempotent-APIs/) | How AWS designs for idempotency |
| Primary | [Hello Interview: Core Concepts (API design)](https://www.hellointerview.com/learn/system-design/in-a-hurry/core-concepts) | Interview defaults for REST, gRPC, pagination and auth |
| Supplement | [Avoiding fallback in distributed systems](https://aws.amazon.com/builders-library/avoiding-fallback-in-distributed-systems/) | Counter-intuitive, senior-level thinking |
| Supplement | [microservices.io patterns](https://microservices.io/patterns/) | A catalogue of microservice patterns |
| Supplement | [ByteByteGo (YouTube)](https://www.youtube.com/@ByteByteGo) | REST vs gRPC vs GraphQL, API gateways and OAuth explained visually |
| Supplement | [Kubernetes: Overview](https://kubernetes.io/docs/concepts/overview/) and [Learn Kubernetes Basics](https://kubernetes.io/docs/tutorials/kubernetes-basics/) | Official docs; enough to explain pods, services and autoscaling |
| Supplement | [System Design 101](https://github.com/ByteByteGoHq/system-design-101) | Its Docker vs Kubernetes and cloud-services cheat sheet sections |

### Checkpoint

- Design the API for a "place order" endpoint that is safe to retry.
- Explain how a retry storm can take down a system that was only briefly slow, and three ways to prevent it.

---

## Phase 5: Reliability, Observability, Security and Cost

**Duration:** Week 11
**Goal:** Cover the "operational maturity" and "cost reasoning" dimensions that 2026 senior loops grade explicitly.

### Topics checklist

**Reliability**
- [ ] SLIs, SLOs, SLAs and error budgets
- [ ] Availability math: components in series multiply (99.9% × 99.9% ≈ 99.8%); redundant components in parallel improve it
- [ ] Redundancy and failover: active-passive vs active-active; multi-AZ vs multi-region
- [ ] Disaster recovery: backups, RPO (how much data you can afford to lose) and RTO (how fast you must recover)
- [ ] Handling overload and cascading failures: load shedding, admission control

**Tail latency and blast radius**
- [ ] Why p99 gets *worse* as you fan out: a request touching 100 servers is only as fast as its slowest one
- [ ] Tail-tolerant techniques: hedged requests, tied requests, micro-partitioning, "constant work" designs
- [ ] Blast radius: cell-based architecture, shuffle sharding, and why one bad tenant shouldn't take down everyone
- [ ] Bulkheads and per-tenant quotas as isolation, not just as rate limiting

**Testing for failure**
- [ ] Load testing to failure, not to target — you need to know where the cliff is
- [ ] Chaos engineering: hypothesis, blast-radius limits, running in production, game days
- [ ] Fault injection, dependency failure drills, and failover rehearsals (an untested failover is a hope, not a plan)

**Observability**
- [ ] Logs, metrics and traces, and what each one is for
- [ ] RED (rate, errors, duration) for services; USE (utilization, saturation, errors) for resources
- [ ] Alert on user-facing symptoms, not every underlying cause
- [ ] Distributed tracing and correlation IDs (OpenTelemetry)

**Deployment and change management**
- [ ] Blue-green, canary and rolling deployments; feature flags; fast rollback
- [ ] Zero-downtime schema changes (expand → migrate → contract)
- [ ] Backfills and dual writes during migrations

**Security essentials**
- [ ] TLS in transit, encryption at rest, key and secret management
- [ ] Least privilege; tenant isolation in multi-tenant systems
- [ ] Input validation, rate limiting, WAF and DDoS protection
- [ ] PII handling, audit logs, data residency

**Cost reasoning (a newer rubric item)**
- [ ] The main cost drivers: compute, storage, network egress, managed-service premiums, GPUs for AI workloads
- [ ] The levers: caching, storage tiering, compression, batching, autoscaling, right-sizing, spot capacity
- [ ] Rough cost per request or per user, and the question "do we need this complexity at this scale?"

### Resources

| Priority | Resource | Notes |
|---|---|---|
| Primary | Google SRE book, chapters [4 (Service Level Objectives)](https://sre.google/sre-book/service-level-objectives/), [6 (Monitoring Distributed Systems)](https://sre.google/sre-book/monitoring-distributed-systems/), [21 (Handling Overload)](https://sre.google/sre-book/handling-overload/) and [22 (Addressing Cascading Failures)](https://sre.google/sre-book/addressing-cascading-failures/) | The four chapters that carry most of the operational rubric. [All three books](https://sre.google/books/) are free |
| Primary | [Using load shedding to avoid overload](https://aws.amazon.com/builders-library/using-load-shedding-to-avoid-overload/) (Builders' Library) | What to do when you're already over capacity |
| Primary | [Workload isolation using shuffle sharding](https://aws.amazon.com/builders-library/workload-isolation-using-shuffle-sharding/) | The clearest explanation of blast-radius reduction anywhere |
| Primary | [The Tail at Scale](https://research.google/pubs/the-tail-at-scale/) (Dean and Barroso) | Where tail latency comes from and how to fight it |
| Supplement | [Reliability, constant work, and a good cup of coffee](https://aws.amazon.com/builders-library/reliability-and-constant-work/) | Designs that behave identically under load and under failure |
| Supplement | [Principles of Chaos Engineering](https://principlesofchaos.org/) | Short; the method, not the tooling |
| Supplement | [OWASP Top 10](https://owasp.org/www-project-top-ten/) | Skim the ten risks so your security answers name real ones |
| Supplement | [Amazon Builders' Library](https://aws.amazon.com/builders-library/) | Queue backlogs, safe deployments, health checks |
| Supplement | *Building Secure and Reliable Systems* (free on the same [SRE books page](https://sre.google/books/)) | Security and reliability together |

> **Note on Builders' Library links:** these now redirect to `builder.aws.com`. The `aws.amazon.com/builders-library/...` links still work and land in the right place.

### Checkpoint

- Your service has a 99.9% SLO. How much downtime per month is that, and what happens when the error budget runs out?
- Name three ways to cut the cost of a video-streaming design by 30% without hurting user experience.
- A request fans out to 50 shards and each shard has a 1-in-100 chance of taking 1 second. What is your p99, and what would you do about it?

---

## Phase 6: Back-of-the-Envelope Estimation

**When:** Start in week 3; do a 15-minute drill twice a week until the end.
**Goal:** Produce rough numbers in under 3 minutes, and only where the numbers change a design decision (for example, "does this fit in memory?" or "do we need to shard?").

### The method

1. **Users → requests:** DAU × actions per user per day = requests per day.
2. **Requests per day → QPS:** divide by ~100,000 (a day has 86,400 seconds), then multiply by 2–10× for peak.
3. **Read:write ratio:** decides whether you need caching and replicas (read-heavy) or sharding and queues (write-heavy).
4. **Storage:** objects per day × size × retention (days) × replication factor.
5. **Bandwidth:** QPS × payload size.
6. **Cache memory:** size of the hot set (often estimated with an 80/20 rule).
7. **Servers:** peak QPS ÷ realistic per-server capacity (state your assumption out loud; see the [capacity rules of thumb](#j-capacity-rules-of-thumb-modern-hardware)).

**Remember that modern hardware is big.** A single well-tuned database or cache node goes much further than most candidates assume, so shard for a stated reason (data size, write throughput, isolation, operations), not by reflex.

### Handy conversions

| Per day | Per second (average) |
|---|---|
| 1 million | ≈ 12 |
| 10 million | ≈ 116 |
| 100 million | ≈ 1,160 |
| 1 billion | ≈ 11,600 |

### Worked example: URL shortener

Assumptions: 100M new URLs per day, a 100:1 read:write ratio, 500 bytes per record, 5-year retention, 3× replication.

| Quantity | Calculation | Result |
|---|---|---|
| Write QPS | 100M ÷ 86,400 | ≈ 1,160/s (peak ≈ 3,500/s at 3×) |
| Read QPS | 1,160 × 100 | ≈ 116,000/s (peak ≈ 350,000/s) |
| Storage per day | 100M × 500 B | 50 GB/day |
| Storage over 5 years | 50 GB × 365 × 5 | ≈ 91 TB (≈ 274 TB with 3× replication) |
| Read bandwidth | 116,000/s × 500 B | ≈ 58 MB/s |
| Short-code length | 5-year total ≈ 182.5B URLs; 62⁶ ≈ 56.8B (too small); 62⁷ ≈ 3.5 trillion | **7 base-62 characters** (lasts ~96 years at this rate) |
| Cache size (upper bound) | 20% of daily reads × 500 B | ≤ 1 TB (much less in practice, because hot URLs repeat) |

**Decisions these numbers drive:** reads dominate, so cache aggressively (and consider serving redirects at the edge); ~90 TB of data must be partitioned; 350K peak reads per second means many stateless app servers behind load balancers; 7-character codes suggest base-62 encoding of a unique ID.

### Practice prompts (one per drill)

X/Twitter timeline reads per second · WhatsApp messages per second · YouTube storage added per day · Uber location updates per second · Instagram photo storage per year · data points per second for a metrics system · tokens per second and GPU count for an LLM chat service ([Phase 10](#phase-10-ai-ml-and-genai-system-design))

**Resources:** [Back-of-the-envelope guide (systemdesign.one)](https://systemdesign.one/back-of-the-envelope/), [Latency numbers every programmer should know](https://gist.github.com/jboner/2841832), and the [Cheat Sheets](#cheat-sheets) below.

---

## Phase 7: The Interview Framework

**When:** Learn it in week 4 and use it for every practice problem afterwards.
**Why:** Many failed interviews fail on *structure* (running out of time, never reaching deep dives), not knowledge. The flow below follows the delivery framework popularized by Hello Interview, with the 2026 additions (operations and cost) built in.

### The 45-minute flow

| Step | Time | What you do | What ends up on the board |
|---|---|---|---|
| 1. Requirements | ~5 min | Ask clarifying questions. List the **top 3 functional requirements** ("users should be able to..."). State **non-functional requirements** with numbers: scale, latency, availability vs consistency, durability. Say what is **out of scope**. | Two short lists |
| 2. Core entities | ~2 min | Name the main nouns (User, Post, Follow...). | Entity list |
| 3. API / interface | ~5 min | Define the main endpoints or function signatures. | 3–5 endpoints |
| 4. Estimation (only if it matters) | ~2 min | Do the math that changes a decision (sharding? fits in memory?). | 3–4 numbers |
| 5. High-level design | ~10–15 min | Draw the simplest design that satisfies **every functional requirement**. Walk one request through it end to end. | Boxes and arrows with data flow |
| 6. Deep dives | ~10–15 min | Revisit the non-functional requirements: bottlenecks, scaling, consistency, failure handling. For each: options → trade-offs → decision. | Updated diagram |
| 7. Wrap-up | ~2 min | Summarize; mention monitoring, failure modes, cost drivers and what you would build next. | — |

In a 60-minute slot, spend the extra time on deep dives.

### Requirements question bank

- Who are the users, and how many (DAU/MAU)? Where are they (one region or global)?
- Which features matter most? Which can we skip?
- Is it read-heavy or write-heavy? What read:write ratio should we expect?
- What latency do the key flows need?
- Is slightly stale data acceptable (eventual consistency), or must it be correct immediately?
- Durability: can we ever lose data?
- Any special constraints: cost, compliance, mobile clients on poor networks?

### The deep-dive menu (pick based on the problem)

| If the problem is... | Likely deep dives |
|---|---|
| Read-heavy (feeds, profiles, URLs) | Caching strategy, CDN, read replicas, denormalized read models |
| Write-heavy (logs, metrics, likes, locations) | Sharding, write-optimized stores (LSM), batching, queues, approximate counting |
| Real-time (chat, live comments, tracking) | WebSockets or SSE, connection management, pub/sub fan-out, presence |
| High contention (tickets, auctions, inventory) | Locking vs optimistic concurrency, reservations with TTLs, virtual waiting queues |
| Money (payments, wallets) | Idempotency, double-entry ledger, exactly-once processing, reconciliation |
| Large files (video, Drive) | Chunking, pre-signed URLs, resumable uploads, transcoding pipelines, CDN |
| Location-based (Uber, Yelp) | Geo-indexing (geohash, quadtree, H3), high-frequency location updates |
| Search and ranking | Inverted indexes, Top-K, pre-computation, ranking pipelines |
| Global scale | Multi-region replication, data locality, conflict resolution, failover |
| AI features | RAG, model routing, caching, streaming, evals, guardrails, cost per request |

### Trade-off phrasing that works

> "We could do **A**, which gives us **X** but costs **Y**, or **B**, which gives us **Y** but costs **X**. Because our requirement is **Z**, I'll go with **A**. If **Z** changed (for example, if we needed strong consistency), I'd switch to **B**."

### Communication habits

- Think out loud, and check in every few minutes ("Does this level of detail work, or should I go deeper on storage?").
- State assumptions explicitly and write them down.
- Name components by what they do ("Feed Service", "Fan-out Workers"), not "Service A".
- Treat pushback as a hint, not an attack. Re-evaluate out loud.
- If you're stuck, go back to the requirements, then walk a single request through the system.

### Common mistakes (and fixes)

| Mistake | Fix |
|---|---|
| Designing before clarifying | Spend the first ~5 minutes on requirements, every time |
| Over-engineering from the start (Kafka + microservices + multi-region for 1,000 users) | Start simple; scale when a requirement demands it |
| Running out of time before deep dives | Timebox the high-level design and keep it simple |
| Only naming technologies | Explain the mechanism: keys, indexes, algorithms, failure behavior |
| Ignoring failures | For each component, ask "what if this dies or slows down?" |
| Never deciding | Commit to a choice and state the condition that would change it |
| Drawing in silence | Narrate as you draw |

### Round variations you may meet

| Variation | What changes | How to adapt |
|---|---|---|
| Product vs infrastructure design | Product rounds (Meta's product architecture round is a well-known example) weigh APIs, data models and user-facing flows; infrastructure rounds weigh scale, storage and distributed internals | Ask which flavor it is. Product: spend longer on the API and data model. Infrastructure: on partitioning, replication and failure handling. |
| Multi-part progressive prompts | Requirements arrive in stages under a time limit (reported at Stripe) | Keep version 1 minimal and extensible; finish each part before polishing |
| Verbal-only design | No whiteboard (reported for some Amazon GenAI roles) | Announce your structure ("three components; here's the request flow") and summarize often |
| API design or data modeling round | Deep focus on endpoints, schemas, versioning, pagination and idempotency | Use the Phase 4 checklist; give concrete request and response examples |
| Critique or evolve a design | You're handed an architecture to improve or debug | Find bottlenecks and single points of failure first; propose incremental changes |
| Frontend system design | Components, state, rendering, performance, offline behavior | See the next section |

### Frontend and mobile system design (if that's your track)

- **Topics:** component architecture and state management; rendering strategies (client-side, server-side, static generation, streaming); client-server API contracts (pagination, caching, optimistic updates); performance (bundle size, lazy loading, list virtualization, images); offline support and sync; real-time updates; accessibility and internationalization.
- **Mobile adds:** battery and flaky-network constraints, background sync, push notifications, and old app versions you can't force to update (so version your APIs).
- **Resources:** [Front End Interview Handbook: System Design](https://www.frontendinterviewhandbook.com/front-end-system-design) (free) and [GreatFrontEnd's Front End System Design Playbook](https://www.greatfrontend.com/front-end-system-design-playbook) (some content is premium).

### Resources

- [Hello Interview: Delivery Framework](https://www.hellointerview.com/learn/system-design/in-a-hurry/delivery)
- [Hello Interview: What is expected at each level](https://www.hellointerview.com/blog/the-system-design-interview-what-is-expected-at-each-level)
- [interviewing.io: A Senior Engineer's Guide to the System Design Interview](https://interviewing.io/guides/system-design-interview) (free, four parts; strong on what interviewers look for, with green and red flags)

---

## Phase 8: Practice Problems (The Curated 40)

**When:** Weeks 4–16, alongside theory.
**Goal:** Solve all **27 core problems** (marked **C**), re-solve at least 10 of them, and add **stretch problems** (marked **S**) for your target role.

### The 90-minute practice loop

1. **45 min: solve it cold.** Timer on, Excalidraw open, talking out loud (record yourself now and then). Follow the Phase 7 flow.
2. **20 min: compare.** Read or watch a reference walkthrough (sources below).
3. **15 min: diff.** Write down what you missed: a requirement, a component, a deep dive, a trade-off.
4. **10 min: capture.** Add new patterns to your notes and flashcards.
5. **Re-solve without looking.** From week 6, the schedule gives you one **25-minute speed re-solve** a week: requirements, API, high-level design, and the three deep dives you'd pick. Then compare with your old notes. Weeks 15–16 add full 60-minute re-solves of your weakest problems.

**Smaller problems** (#2 Pastebin, #4 Unique ID, #8 Leaderboard, #11 Instagram, #17 Yelp) reuse ideas from problems you've already done, so give them ~60 minutes: a 40-minute solve and a 20-minute diff.

### Where to find free walkthroughs

- [Hello Interview problem breakdowns](https://www.hellointerview.com/learn/system-design/problem-breakdowns/overview) (many free, some premium) and their [YouTube channel](https://www.youtube.com/@hello_interview)
- [System Design Primer](https://github.com/donnemartin/system-design-primer) solved examples: Pastebin/URL shortener, Twitter timeline and search, web crawler, key-value cache, sales ranking, scaling to millions of users on AWS
- [Jordan has no life](https://www.youtube.com/@jordanhasnolife5163) problem videos
- [ByteByteGo](https://www.youtube.com/@ByteByteGo) videos and the [System Design 101](https://github.com/ByteByteGoHq/system-design-101) real-world case studies
- [awesome-system-design-resources](https://github.com/ashishps1/awesome-system-design-resources): a problem list sorted into easy, medium and hard, with links

### Tier 1: Foundations (9 problems, weeks 4–7)

| # | Problem | Type | Key concepts tested |
|---|---|---|---|
| 1 | URL shortener (TinyURL, Bitly) | C | ID generation, base-62, key-value store, caching, 301 vs 302 redirects, analytics |
| 2 | Pastebin | C | Blob storage vs database, expiry and TTLs, CDN |
| 3 | Distributed rate limiter | C | Token bucket vs sliding window, atomic operations in Redis, placement (gateway vs service) |
| 4 | Unique ID generator (Snowflake) | C | Coordination-free IDs, clock skew, ordering |
| 5 | Notification system | C | Fan-out, queues, retries, user preferences, providers (push, SMS, email), idempotency |
| 6 | Distributed counter (likes, views) | C | Write hot spots, sharded counters, batching, approximate counts |
| 7 | Typeahead / autocomplete | C | Tries, top-K per prefix, offline aggregation, caching |
| 8 | Leaderboard | C | Redis sorted sets, sharding by score, real-time vs periodic updates |
| 9 | Distributed cache / key-value store | C | Consistent hashing, replication, quorums, eviction, hot keys |

### Tier 2: Core product designs (15 problems, weeks 8–12)

| # | Problem | Type | Key concepts tested |
|---|---|---|---|
| 10 | News feed (Facebook, X timeline) | C | Fan-out on write vs read, the celebrity problem, ranking, caching |
| 11 | Instagram / photo sharing | C | Media upload pipeline, CDN, feed generation |
| 12 | Chat (WhatsApp, Messenger) | C | WebSockets, presence, delivery receipts, ordering, offline messages, group chat |
| 13 | YouTube / Netflix | C | Chunked uploads, transcoding pipeline, adaptive bitrate streaming, CDN |
| 14 | Dropbox / Google Drive | C | Chunking, deduplication, sync and conflicts, pre-signed URLs, metadata database |
| 15 | Ticketmaster / BookMyShow | C | Seat contention, reservations with TTLs, virtual waiting room, idempotent payments |
| 16 | Ride-hailing (Uber, Ola) | C | High-frequency location updates, geo-indexing, matching, consistent driver assignment |
| 17 | Proximity search (Yelp) | C | Geohash or quadtree, read-heavy caching |
| 18 | Web crawler | C | URL frontier, politeness, dedupe with Bloom filters, distributed workers |
| 19 | Payment system (Stripe, UPI-style) | C | Idempotency, double-entry ledger, payment-provider integration, reconciliation, exactly-once processing |
| 20 | Flash sale / e-commerce checkout (Big Billion Days-style) | C | Inventory consistency, preventing overselling, queueing, catalog caching |
| 21 | Food delivery (Swiggy, Zomato) | C | Order state machine, dispatch and matching, ETAs, geo |
| 22 | Google Docs (collaborative editing) | S | OT vs CRDTs, WebSockets, versioning |
| 23 | Online auction (eBay-style bidding) | S | Contention, real-time bid updates, consistency, deadlines |
| 24 | LeetCode / online judge | S | Sandboxed code execution, job queues, contest-scale traffic, leaderboards |

### Tier 3: Infrastructure and data-intensive (10 problems, weeks 14–15)

| # | Problem | Type | Key concepts tested |
|---|---|---|---|
| 25 | Distributed message queue (Kafka-like) | C | Partitioned log, replication, consumer groups, retention, ordering |
| 26 | Distributed job scheduler | C | Leases, at-least-once execution, priorities, retries, cron at scale |
| 27 | Top-K / trending (hashtags, videos) | C | Count-Min Sketch, stream windows, approximate vs exact counts |
| 28 | Ad click aggregator | C | Stream processing, windowing, exactly-once processing, reconciliation, Lambda vs Kappa |
| 29 | Metrics and monitoring (Datadog-like) | S | Time-series storage, downsampling, alerting pipeline |
| 30 | Search engine (post or tweet search) | S | Inverted index, sharding by document vs by term, ranking, freshness |
| 31 | S3-like object storage | S | Separate metadata and data planes, erasure coding, durability |
| 32 | Stock exchange / order matching | S | Order book, sequencer, determinism, very low latency |
| 33 | Hotel / Airbnb reservations | S | Double-booking prevention, date-range inventory, optimistic concurrency |
| 34 | Live comments and reactions (Facebook Live, Hotstar-style) | S | Massive pub/sub fan-out, SSE, hot partitions |

### Tier 4: AI-era designs (6 problems, week 13)

| # | Problem | Type | Key concepts tested |
|---|---|---|---|
| 35 | RAG system for enterprise document search | C | Ingestion, chunking, embeddings, hybrid (vector + keyword) search, re-ranking, access control, citations, evals |
| 36 | LLM gateway | C | Model routing, per-tenant rate limits, token accounting and cost allocation, exact and semantic caching, fallbacks, observability |
| 37 | ChatGPT-style chat service | S | Token streaming (SSE), conversation storage, GPU serving (batching, KV cache), rate limits, safety filters |
| 38 | Recommendation system (feed or video recommendations) | S | Candidate generation and ranking, feature store, embeddings, online vs offline, A/B testing |
| 39 | AI customer-support agent | S | Workflows vs agents, tool calling, guardrails, human handoff, evals, cost controls |
| 40 | Content moderation pipeline | S | ML classifiers + LLM review + human queue, precision/recall trade-offs, appeals, latency tiers |

### Which stretch problems to add

| Target role | Add these |
|---|---|
| Product / backend SWE | 22, 23, 24, 34 |
| Infrastructure / platform | 29, 30, 31, 32 |
| Fintech (payments, broking, wallets) | 23, 32, 33 |
| AI / ML engineer | 37, 38, 39, 40 |

Fit stretch problems into weeks 15–16, the buffer week, or the weeks after your core plan ends.

### Bonus problems (only if you have time)

Video calling like Zoom (WebRTC, media servers) · maps and ETAs (routing, live traffic data) · an email service like Gmail (storage, search, spam filtering) · a dating app like Tinder (geo, swipes, matching) · fitness tracking like Strava (GPS ingestion, segment leaderboards) · distributed logging (ingestion, indexing, retention) · a CI/CD or code deployment system (build queues, artifacts, rollouts) · a price tracker (scheduled crawling, alerts)

---

## Phase 9: Low-Level Design and Machine Coding

**When:** A parallel track in weeks 3–13 (one problem or topic a week; keep going in week 14 only if your target companies run machine-coding rounds). Essential for SDE-1/SDE-2 roles in India; lighter for senior FAANG loops.

### Round formats you may face

| Format | What happens | Where it's common |
|---|---|---|
| Object-oriented design (whiteboard) | Classes, relationships and key methods; you talk through the design | Amazon-style and many global loops |
| Machine coding | Build a working, runnable, extensible app in ~90–120 minutes, then demo and discuss it | Indian product companies (Flipkart, Uber, Swiggy and others) |
| Concurrency round | Thread-safe components (bounded queue, rate limiter, cache) | Some companies (Uber is a known example) |

### Topics checklist

- [ ] OOP pillars: encapsulation, abstraction, inheritance, polymorphism; composition over inheritance
- [ ] SOLID principles, DRY, KISS, YAGNI
- [ ] UML basics: class and sequence diagrams (quick sketches, not formal UML)
- [ ] Design patterns, learned in this order: Strategy, Factory, Builder, Singleton (and its downsides), Observer, Decorator, Adapter, State, Command, Chain of Responsibility, Template Method, Facade
- [ ] Concurrency: threads, locks, concurrent collections, producer-consumer, read-write locks, deadlock avoidance
- [ ] Clean code: meaningful names, small classes, interfaces at extension points, in-memory repositories, custom exceptions, unit tests

### Machine-coding game plan (90 minutes)

| Time | Step |
|---|---|
| 0–10 min | Clarify requirements; list entities and the must-have flows |
| 10–20 min | Sketch classes, interfaces and relationships; identify extension points (strategies) |
| 20–70 min | Implement the core flows end to end first, with a runnable driver or CLI; keep it modular |
| 70–80 min | Handle edge cases, validation and errors; add a couple of tests |
| 80–90 min | Demo, and explain how you'd extend it (a new pricing strategy, persistence, concurrency) |

**Graders look for:** working code first, then modularity, extensibility, readability, sensible use of patterns (not pattern-stuffing) and edge-case handling.

**Language tip:** use the language you're fastest in. Most free material is in Java, but the designs translate directly to Python, C++, Go or TypeScript. Before your first timed round, build a reusable skeleton in your language: a package layout (models, services, repositories, strategies), an in-memory repository, a driver or CLI, and one example test. It saves 10–15 minutes in every round.

### Problem list (practice these timed)

| Level | Problems |
|---|---|
| Warm-up | Tic-tac-toe, Snake and Ladder, Vending machine, Logger framework, LRU cache |
| Core | Parking lot, Elevator system, Splitwise, BookMyShow (movie booking), Library management, ATM |
| Advanced | Ride-hailing (mini Uber), Food ordering, In-memory pub/sub, Thread-safe rate limiter, Task scheduler, In-memory key-value store with transactions, Stock broker / portfolio, Hotel management, Digital wallet, Chess |

### Resources

| Priority | Resource | Notes |
|---|---|---|
| Primary | [awesome-low-level-design](https://github.com/ashishps1/awesome-low-level-design) | OOP, patterns, UML, concurrency and interview problems with solutions |
| Primary | [Refactoring.Guru: Design Patterns](https://refactoring.guru/design-patterns) | Clear, free explanations of every classic pattern |
| Primary (video) | Concept && Coding: [LLD playlist](https://www.youtube.com/playlist?list=PL6W8uoQQ2c61X_9e6Net0WdYZidm7zooW) and [HLD playlist](https://www.youtube.com/playlist?list=PL6W8uoQQ2c63W58rpNFDwdrBnq5G3EfT7) | Popular with Indian candidates; the core playlists are free, while some newer content is members-only |
| Practice | [workat.tech machine coding](https://workat.tech/machine-coding/) | Articles and practice problems in the machine-coding format |
| Practice | [Hello Interview Guided Practice](https://www.hellointerview.com/practice/overview) | Free to start; includes LLD tracks with AI feedback |

---

## Phase 10: AI, ML and GenAI System Design

**When:** Week 13 (earlier if you're targeting AI roles).
**Why:** In 2026, interviewers expect you to know where AI components fit in a system, even in general SWE loops, and AI-specific prompts ("Design a RAG pipeline", "Design an LLM gateway") are now common.

### Topics checklist

**ML system basics**
- [ ] Framing: what to predict, success metrics (offline vs online), baselines, and whether you need ML at all
- [ ] Data pipelines, labeling and feature stores; training vs serving; batch vs online inference
- [ ] Model registry, A/B tests and shadow deployments; monitoring data and model drift; feedback loops
- [ ] Recommendations and search: the two-stage architecture (candidate retrieval → ranking → re-ranking), embeddings, approximate nearest-neighbor (ANN) search

**LLM application architecture**
- [ ] The request path: client → gateway (auth, rate limits, routing) → context building (RAG, tools, memory) → model → output guardrails → streamed response
- [ ] Model routing and fallbacks across providers and model sizes (quality vs latency vs cost)
- [ ] Caching: exact-match and semantic caching; prompt/prefix caching
- [ ] Streaming tokens to clients (SSE); long-running generations and cancellation
- [ ] Observability: tokens in and out, time-to-first-token (TTFT), latency, cost per request, error and refusal rates
- [ ] Prompt and model versioning; evaluation sets; offline and online evals

**RAG deep dive**
- [ ] Ingestion: parsing, chunking strategies, embeddings, metadata, re-indexing when documents change
- [ ] Retrieval: vector search (for example, HNSW indexes), keyword search (BM25), hybrid search, re-ranking
- [ ] Access control: filter by permissions at retrieval time (never leak another user's or tenant's documents)
- [ ] Grounding and citations; what to do when no good context is found
- [ ] Evaluation: retrieval quality (did we fetch the right chunks?) and answer quality (faithfulness, relevance)

**LLM serving (for infra-leaning roles)**
- [ ] GPU memory limits, batching (continuous batching), the KV cache, quantization
- [ ] Throughput vs latency; autoscaling GPU pools; cost per 1K tokens

**Agents**
- [ ] Workflows (predefined code paths) vs agents (the model directs its own steps); prefer the simplest option that works
- [ ] Patterns: prompt chaining, routing, parallelization, orchestrator-workers, evaluator-optimizer
- [ ] Tool calling, memory, stopping conditions, human-in-the-loop, sandboxing
- [ ] Compounding errors, runaway costs and guardrails

**Safety and governance**
- [ ] Prompt-injection defenses, PII redaction, content filtering, tenant isolation, audit logs

### Resources (all free)

| Priority | Resource | Notes |
|---|---|---|
| Primary | [Building A Generative AI Platform (Chip Huyen)](https://huyenchip.com/2024/07/25/genai-platform.html) | Builds a GenAI platform step by step: context, guardrails, router and gateway, caching, agent logic |
| Primary | [Patterns for Building LLM-based Systems and Products (Eugene Yan)](https://eugeneyan.com/writing/llm-patterns/) | Evals, RAG, fine-tuning, caching, guardrails, defensive UX, user feedback |
| Primary | [Building effective agents (Anthropic)](https://www.anthropic.com/research/building-effective-agents) | Workflows vs agents, and the core agentic patterns |
| Supplement | [ML and LLM system design: 800 case studies (Evidently AI)](https://www.evidentlyai.com/ml-system-design) | Real systems from 150+ companies, filterable by use case (recommendations, search, fraud, RAG, agents) |
| Supplement | [Eugene Yan: Start Here](https://eugeneyan.com/start-here/) | Links to his system design writing on recommendations and search |
| Supplement | [What We've Learned From A Year of Building with LLMs](https://applied-llms.org/) | Practitioner lessons |
| Supplement | [Generative AI System Design Interview (IGotAnOffer)](https://igotanoffer.com/en/advice/generative-ai-system-design-interview) | Example questions and an answer framework |

### Checkpoint

- Design a RAG assistant over 10 million internal documents with per-user permissions and p95 latency under 3 seconds. Where does the latency go?
- Your LLM bill doubled last month. Walk through how your design would find the cause and cut the cost.

---

## Phase 11: Advanced and Senior+ Topics

**When:** Week 15 onward (start earlier if you're targeting senior or staff roles).
**Goal:** Build the judgment that comes from seeing how real systems evolved.

### Read real architectures

- Pick one engineering blog post a week and summarize it in five lines: problem → constraints → design → trade-offs → what you'd reuse.
- Good starting points: [Arpit Bhayani's engineering-blog dissections](https://youtube.com/c/ArpitBhayani), [ByteByteGo's real-world case studies](https://github.com/ByteByteGoHq/system-design-101), [High Scalability](https://highscalability.com/), [awesome-scalability](https://github.com/binhnguyennus/awesome-scalability) and the [engineering blogs list](https://github.com/kilimchoi/engineering-blogs).
- Company blogs worth following: Netflix, Uber, Meta, Discord, Cloudflare, Stripe, Slack, Airbnb and LinkedIn, plus Indian engineering teams such as Flipkart, Swiggy, Zomato, Razorpay and Hotstar.

### The 10-paper reading list

Read each paper's abstract, introduction, design section and conclusion; skip the proofs. The [MIT 6.5840 schedule](https://pdos.csail.mit.edu/6.824/schedule.html) links many of these with guiding questions.

1. **[GFS](https://pdos.csail.mit.edu/6.824/papers/gfs.pdf)** (Google File System): distributed storage for large files
2. **[MapReduce](https://pdos.csail.mit.edu/6.824/papers/mapreduce.pdf)**: batch processing at scale
3. **[Bigtable](https://static.googleusercontent.com/media/research.google.com/en//archive/bigtable-osdi06.pdf)**: wide-column storage
4. **[Dynamo](https://www.allthingsdistributed.com/files/amazon-dynamo-sosp2007.pdf)**: leaderless replication, consistent hashing, quorums, vector clocks
5. **[Chubby](https://static.googleusercontent.com/media/research.google.com/en//archive/chubby-osdi06.pdf)**: a lock service for coarse-grained coordination
6. **[ZooKeeper](https://pdos.csail.mit.edu/6.824/papers/zookeeper.pdf)**: a coordination service
7. **[Raft](https://pdos.csail.mit.edu/6.824/papers/raft-extended.pdf)** (extended version; start with the [visualization](https://thesecretlivesofdata.com/raft/)): understandable consensus
8. **[Spanner](https://pdos.csail.mit.edu/6.824/papers/spanner.pdf)**: globally distributed transactions with TrueTime
9. **Kafka**: the distributed log — read the [official Design section](https://kafka.apache.org/documentation/) rather than the 2011 paper; it is clearer and current
10. **[Scaling Memcache at Facebook](https://pdos.csail.mit.edu/6.824/papers/memcache-fb.pdf)**: caching at massive scale ([USENIX page](https://www.usenix.org/conference/nsdi13/technical-sessions/presentation/nishtala))

**Two worth adding if you have time:** **[The Tail at Scale](https://research.google/pubs/the-tail-at-scale/)** (why large fan-out systems have terrible tails, and what to do about it — the most *immediately* useful paper on this list for interviews) and **[Paxos Made Simple](https://pdos.csail.mit.edu/6.824/papers/paxos-simple.pdf)** (only if Raft already makes sense to you).

### Senior and staff skills to practice

- [ ] Multi-region design: data locality, replication lag, conflict resolution, regional failover
- [ ] Migrations: the strangler-fig pattern, dual writes, backfills, shadow traffic, safe cutovers
- [ ] Capacity planning and cost modeling
- [ ] Multi-tenancy: noisy neighbors, isolation, per-tenant quotas
- [ ] Build vs buy; managed services vs self-hosted
- [ ] Evolution: "What does v1 look like for 10K users, and how does it evolve to 100M?"
- [ ] Explaining a system **you** built: scale, key decisions, what went wrong, what you'd change

### Build to learn (pick 2–3)

| Project | What it teaches | Detailed version |
|---|---|---|
| URL shortener with Postgres + Redis + a rate limiter, load-tested with k6 | Caching, indexing, rate limiting, measuring p99 | [Lab 1](hands-on-projects-roadmap.md#lab-1-url-shortener-under-load-weeks-34) |
| Chat server with WebSockets + Redis pub/sub across 2+ instances | Real-time fan-out, connection state | — |
| Order service using the transactional outbox + a Kafka consumer | Reliable events, idempotent consumers | [Labs 3](hands-on-projects-roadmap.md#lab-3-the-async-pipeline-week-6) and [8](hands-on-projects-roadmap.md#lab-8-money--ledger-and-inventory-week-12) |
| Key-value store with consistent hashing and replication (or the MIT 6.5840 Raft labs) | Partitioning, replication, consensus | [Lab 5](hands-on-projects-roadmap.md#lab-5-distributed-key-value-store-weeks-89) |
| Small RAG app with a vector database and an eval set | Chunking, retrieval quality, evals, cost | [Lab 9](hands-on-projects-roadmap.md#lab-9-rag-and-an-llm-gateway-week-13) |

> **The full build track:** [hands-on-projects-roadmap.md](hands-on-projects-roadmap.md) expands these into 12 labs timed to the same 16 weeks, each with a measurable experiment. It adds roughly 4–5 hours a week at its recommended intensity — read its [hour cost](hands-on-projects-roadmap.md#pick-your-intensity-and-the-honest-hour-cost) before committing, and never trade a mock for a lab.

---

## Phase 12: Mock Interviews and Final Prep

**When:** A baseline mock in week 8 (use a Tier 1 problem you've already solved, so the feedback targets your communication), then one a week from week 10 and two a week in weeks 14–16: 11 mocks in total.

### Free ways to get mock interviews

| Option | How it works |
|---|---|
| [Aced (formerly Exponent) peer mocks](https://www.tryexponent.com/practice) | The free Basic plan includes a limited number of live 1:1 peer mocks each month (5 at the time of writing); you and a peer interview each other. Pramp's peer mocks moved here. |
| [Hello Interview Guided Practice](https://www.hellointerview.com/practice/overview) | Free to start; step-by-step AI feedback on system design and LLD problems |
| Peer group | Find 2–3 people preparing at the same time (college groups, LinkedIn, Discord communities) and rotate interviewer and candidate |
| Self-mock | Record yourself solving a problem in 45 minutes, then review it against the scorecard below |
| Watch real mocks | Hello Interview's YouTube mocks and interviewing.io's replays show what strong and weak answers look like |

Playing the **interviewer** in peer mocks is surprisingly valuable: you quickly learn what separates clear candidates from confusing ones.

**Plan for the credit limit:** free Aced credits cover about five peer mocks a month, and two mocks a week in weeks 14–16 can exceed that. Fill the gap with your peer group and recorded self-mocks.

### Mock scorecard (score each dimension 1–4)

| Dimension | 1 (weak) | 4 (strong) |
|---|---|---|
| Requirements | Jumped in without clarifying | Prioritized features, quantified non-functional requirements, set scope |
| API and data model | Missing or vague | Clean entities and endpoints that match the requirements |
| High-level design | Incomplete; unclear data flow | Meets every functional requirement; clear request flow |
| Deep dives | Shallow; name-dropping | 2–3 real bottlenecks solved with concrete mechanisms |
| Trade-offs | No decisions | Options compared, decision made, switch conditions stated |
| Operations and cost | Not mentioned | Failure modes, monitoring, rollout and cost drivers covered |
| Communication and time | Rambling; ran out of time | Structured and interactive; finished with a wrap-up |

Adding up the seven dimensions gives a score out of 28, which you can log in the [Progress Tracker](#progress-tracker).

### Prepare your project deep dive

Senior loops often include "walk me through a system you built", and real experience also strengthens your answers in design rounds. Write your story down once, using this outline:

1. **Context:** what the system does and who uses it
2. **Scale:** users, requests per second, data size (real numbers)
3. **Architecture:** a five-box diagram you can draw in 2 minutes
4. **One hard decision:** the options you considered, the trade-off, and why you chose what you did
5. **One failure:** an incident or bottleneck, how you found it and how you fixed it
6. **Impact:** a metric that moved (latency, cost, reliability, revenue)
7. **Hindsight:** what you'd change today

If you're a fresher, use your strongest project or internship, and be honest about its scale.

### The final 14 days

| Days before interview | Focus |
|---|---|
| 14–11 | Re-solve your 6 weakest core problems; 2 mocks |
| 10–8 | Company research: their products, engineering blog and recent interview reports; practice their likely prompts; rehearse your project deep dive out loud |
| 7–5 | 3 mocks; review cheat sheets and flashcards daily (30 minutes) |
| 4–2 | Light review: trade-off journal, framework, estimation drills; 1 mock |
| 1 | Rest. Skim your one-page notes. Set up your whiteboard tool if the interview is remote. |

### Interview-day checklist

- Test your drawing tool and camera; keep a blank template ready (requirements, entities, API, diagram, deep dives).
- Keep a clock visible and timebox each step.
- Write the requirements down before drawing anything.
- After the high-level design, ask: "Which part would you like me to go deeper on?"
- Finish with a one-minute summary: the design, key trade-offs, what you'd monitor and what comes next.

---

## The 16-Week Schedule

**Time budget:** ~1–1.5 hours on weekdays plus ~3 hours on each weekend day ≈ 10–12 hours a week (see the [weekly time budget](#weekly-time-budget)).
**Weekly rhythm:** weekdays for theory and LLD; weekends for practice problems, the speed re-solve and mocks. Estimation drills run twice a week from week 3.
**Dates** assume you start on Monday 28 September 2026; shift them if you start later, and insert your buffer week wherever you need it.

| Week (starts) | Theory | New problems · speed re-solve | LLD · mocks | ≈ Hours |
|---|---|---|---|---|
| 1 (28 Sep) | Phase 0: networking, HTTP, DNS, TLS | — | — | 10 |
| 2 (5 Oct) | Phase 0: OS and database basics; build the CRUD app | — | — | 10 |
| 3 (12 Oct) | 1.1–1.2: scalability, load balancers, gateways; first estimation drill | — | LLD: OOP + SOLID | 8.5 |
| 4 (19 Oct) | 1.3–1.4: caching, CDNs; read the Phase 7 framework | #1 URL shortener | LLD: Strategy, Factory, Observer | 9 |
| 5 (26 Oct) | 1.5: databases, replication, sharding, consistent hashing | #2 Pastebin, #3 Rate limiter | LLD: Parking lot | 10 |
| 6 (2 Nov) | 1.6–1.9: queues, streams, blob storage, search, real-time | #4 Unique ID, #5 Notifications, #6 Distributed counter · re-solve #1 | LLD: LRU cache (thread-safe) | 11 |
| 7 (9 Nov) | 2A: storage engines, isolation, data modeling | #7 Typeahead, #8 Leaderboard, #9 Distributed cache · re-solve #3 | LLD: Splitwise | 10 |
| 8 (16 Nov) | Phase 3, part 1 (Kleppmann lectures 1–5) | #10 News feed, #11 Instagram · re-solve #5 | LLD: Elevator · **Mock #1 (baseline)** | 11 |
| 9 (23 Nov) | Phase 3, part 2 (lectures 6–8, Raft, sagas, algorithm toolbox) | #12 Chat, #13 YouTube · re-solve #9 using quorums and replication | LLD: BookMyShow | 10 |
| 10 (30 Nov) | Phase 4: APIs, auth, cloud primitives, resilience | #14 Dropbox, #15 Ticketmaster/BookMyShow · re-solve #10 | LLD: Snake and Ladder (timed) · **Mock #2** | 11.5 |
| 11 (7 Dec) | Phase 5 + 2B geo module | #16 Uber, #17 Yelp, #18 Web crawler · re-solve #12 | LLD: thread-safe rate limiter · **Mock #3** | 13 ⚠ |
| 12 (14 Dec) | Idempotency and double-entry ledgers (for #19); 2B data-lifecycle module; review your trade-off journal | #19 Payments, #20 Flash sale, #21 Food delivery · re-solve #15 | LLD: Food ordering (timed) · **Mock #4** | 11.5 |
| 13 (21 Dec) | Phase 10 + 2B vector module | #35 RAG, #36 LLM gateway · re-solve #16 | LLD: key-value store with transactions (timed) · **Mock #5** (include one AI prompt) | 12 |
| 14 (28 Dec) | 2B stream-processing module; Kafka internals | #25 Message queue, #27 Top-K, #28 Ad click aggregator · re-solve #19 | LLD only if your targets need it · **Mocks #6–7** | 11.5 |
| 15 (4 Jan) | Phase 11: papers and real architectures | #26 Job scheduler; full re-solves of your 5 weakest | **Mocks #8–9** | 12 |
| 16 (11 Jan) | Phase 12: final prep; company-specific prompts | Full re-solves of 5 more | **Mocks #10–11**; readiness checklist | 11.5 |

End each week with the checkpoint from that week's phase. Stretch problems go in weeks 15–16, the buffer week, or after week 16.

> **⚠ Week 11 runs about 13 hours, not 12.** It carries the whole of Phase 5 plus the geo module plus three problems plus a mock. This is the one week where the plan does not fit its own budget, so decide in advance: use your buffer week here, or move **#18 Web crawler** to week 15. See the week 11 block in [The Straight Path](#the-straight-path-every-link-in-order).

### Fast track (8 weeks, interview already scheduled)

| Week | Focus |
|---|---|
| 1 | Phase 1.1–1.5 (compressed) + the Phase 7 framework; #1 URL shortener, #3 Rate limiter |
| 2 | Phase 1.6–1.9 + estimation; #5 Notifications, #9 Distributed cache, #7 Typeahead |
| 3 | Phase 2A + Phase 3 essentials (CAP, consistency, quorums, idempotency); #10 News feed, #12 Chat |
| 4 | Phase 4–5 essentials; #13 YouTube, #14 Dropbox, #15 Ticketmaster; Mock #1 |
| 5 | The 2B geo module; #16 Uber, #17 Yelp, #18 Web crawler, #19 Payments; Mock #2 |
| 6 | Phase 10 essentials + the 2B vector and stream modules; #35 RAG, #36 LLM gateway, #27 Top-K, #26 Job scheduler; Mocks #3–4 |
| 7 | Stretch problems for your role; re-solve your 4 weakest; Mocks #5–6 |
| 8 | The final-14-days plan, compressed into 7 days |

**LLD-heavy loops (India, SDE-1/SDE-2):** add 3 timed machine-coding problems a week, and drop Tier 3 and Phase 11.

### Deep track (24 weeks)

Follow the 16-week plan, then add:

- **Weeks 17–20:** MIT 6.5840 labs (MapReduce, Raft) and the 10-paper reading list
- **Weeks 21–22:** all remaining stretch problems, plus one real-architecture write-up a week
- **Weeks 23–24:** two build-to-learn projects and weekly mocks

---

## Progress Tracker

Copy this table into a spreadsheet or notes app. Score each attempt out of 28 with the [mock scorecard](#mock-scorecard-score-each-dimension-14) (seven dimensions × 4 points). Aim for 21+ on re-solves.

| # | Core problem | 1st attempt (date, /28) | Biggest miss | Re-solve (date, /28) |
|---|---|---|---|---|
| 1 | URL shortener | | | |
| 2 | Pastebin | | | |
| 3 | Distributed rate limiter | | | |
| 4 | Unique ID generator | | | |
| 5 | Notification system | | | |
| 6 | Distributed counter | | | |
| 7 | Typeahead / autocomplete | | | |
| 8 | Leaderboard | | | |
| 9 | Distributed cache / key-value store | | | |
| 10 | News feed | | | |
| 11 | Instagram / photo sharing | | | |
| 12 | Chat (WhatsApp) | | | |
| 13 | YouTube / Netflix | | | |
| 14 | Dropbox / Google Drive | | | |
| 15 | Ticketmaster / BookMyShow | | | |
| 16 | Ride-hailing (Uber, Ola) | | | |
| 17 | Proximity search (Yelp) | | | |
| 18 | Web crawler | | | |
| 19 | Payment system | | | |
| 20 | Flash sale / checkout | | | |
| 21 | Food delivery | | | |
| 25 | Distributed message queue | | | |
| 26 | Distributed job scheduler | | | |
| 27 | Top-K / trending | | | |
| 28 | Ad click aggregator | | | |
| 35 | RAG system | | | |
| 36 | LLM gateway | | | |

---

## Cheat Sheets

### A. Latency numbers (orders of magnitude)

These are the classic (circa 2012) figures. Modern hardware is faster in places, but the **ratios** are what matter in interviews.

| Operation | Approx. time |
|---|---|
| L1 cache reference | 0.5 ns |
| Main memory reference | 100 ns |
| Send 1 KB over a 1 Gbps network | 10 µs |
| Random 4 KB read from SSD | 150 µs |
| Read 1 MB sequentially from memory | 250 µs |
| Round trip within the same datacenter | 0.5 ms |
| Read 1 MB sequentially from SSD | 1 ms |
| Disk (HDD) seek | 10 ms |
| Read 1 MB sequentially from HDD | 20 ms |
| Packet round trip California → Netherlands → California | 150 ms |

**Rules of thumb:** a random SSD read is over 1,000× slower than a memory reference; for sequential 1 MB reads, memory is ~4× faster than SSD and ~80× faster than HDD; a same-datacenter hop costs ~0.5 ms, while cross-continent round trips cost 100+ ms, so avoid chatty cross-region calls.

Sources: [latency numbers gist](https://gist.github.com/jboner/2841832) and an [interactive version that shows how the numbers changed by year](https://colin-scott.github.io/personal_website/research/interactive_latency.html).

### B. Availability ("the nines")

| Availability | Downtime per year | Downtime per 30-day month | Downtime per day |
|---|---|---|---|
| 99% | 3.65 days | 7.2 hours | 14.4 minutes |
| 99.9% | 8.76 hours | 43.2 minutes | 1.44 minutes |
| 99.95% | 4.38 hours | 21.6 minutes | 43.2 seconds |
| 99.99% | 52.6 minutes | 4.32 minutes | 8.6 seconds |
| 99.999% | 5.26 minutes | 25.9 seconds | 0.86 seconds |

**Combining components:** in series, multiply availabilities (two 99.9% services ≈ 99.8%). In parallel (redundant), availability = 1 − (1 − A)(1 − B), so two independent 99% replicas ≈ 99.99%.

### C. Powers of two and typical sizes

| Power | Exact value | Approximately | Unit |
|---|---|---|---|
| 2¹⁰ | 1,024 | 1 thousand | 1 KB |
| 2²⁰ | 1,048,576 | 1 million | 1 MB |
| 2³⁰ | 1,073,741,824 | 1 billion | 1 GB |
| 2⁴⁰ | ≈ 1.1 × 10¹² | 1 trillion | 1 TB |
| 2⁵⁰ | ≈ 1.13 × 10¹⁵ | 1 quadrillion | 1 PB |

| Item | Typical size (state it as an assumption) |
|---|---|
| A character (English text, UTF-8) | 1 byte |
| An int64 or a timestamp | 8 bytes |
| A UUID | 16 bytes binary (36 characters as text) |
| A short text post with metadata | ~0.5–1 KB |
| A compressed photo | ~200 KB–2 MB |
| One minute of 1080p video at streaming bitrates (~5–8 Mbps) | ~35–60 MB |

### D. Database selection guide

| Need | Good default | Examples | Why |
|---|---|---|---|
| Transactions, relations, flexible queries | Relational (SQL) | PostgreSQL, MySQL | ACID, joins, mature tooling; with indexes and replicas it scales further than most people expect |
| Massive key-based reads and writes, simple access patterns | Key-value / wide-column | DynamoDB, Cassandra, ScyllaDB | Horizontal scale, predictable latency via partition-key access |
| Flexible, nested documents | Document | MongoDB | Schema flexibility, document-level access |
| Caching, counters, leaderboards, sessions | In-memory key-value | Redis, Memcached | Sub-millisecond latency; rich data structures (Redis) |
| Full-text search, filtering, relevance | Search engine | Elasticsearch, OpenSearch | Inverted indexes |
| Metrics, IoT, events over time | Time-series | Prometheus, InfluxDB, TimescaleDB | Compression, rollups, retention policies |
| Relationships and multi-hop traversals | Graph | Neo4j (or adjacency lists in SQL) | Efficient traversals |
| Large files (images, video, backups) | Object storage | S3, GCS, Azure Blob Storage | Cheap, durable, CDN-friendly |
| Semantic similarity | Vector index | pgvector, Pinecone, Milvus, FAISS | ANN search over embeddings |
| Analytics over huge datasets | Columnar warehouse | BigQuery, Snowflake, ClickHouse | Fast column scans and aggregations |

### E. Caching strategies

| Strategy | How it works | Best for | Watch out for |
|---|---|---|---|
| Cache-aside | The app reads the cache; on a miss it reads the DB and fills the cache | General read-heavy workloads (the default) | Stale data; stampedes on popular misses |
| Read-through | The cache itself loads from the DB on a miss | Simpler application code | The cache becomes a critical dependency |
| Write-through | Writes go to the cache and the DB synchronously | Read-after-write consistency | Higher write latency |
| Write-behind (write-back) | Writes go to the cache and are flushed to the DB asynchronously | Write-heavy, loss-tolerant data (counters) | Data loss if the cache fails before flushing |
| Write-around | Writes go only to the DB; the cache fills on reads | Data rarely read soon after it's written | The first read is always a miss |

### F. Message queue vs log-based stream

| | Message queue (SQS, RabbitMQ) | Log-based stream (Kafka, Kinesis) |
|---|---|---|
| Model | Messages are removed once acknowledged | An append-only log; consumers track their own offsets |
| Replay | No | Yes, within the retention period |
| Ordering | Limited (FIFO queues exist) | Guaranteed within a partition |
| Consumers | Competing workers share the load | Many independent consumer groups read the same data |
| Best for | Task distribution, background jobs | Event streaming, analytics, CDC, feeding many downstream systems |

### G. Real-time communication options

| Technique | Direction | Use when |
|---|---|---|
| Short polling | Client pulls on an interval | Updates are infrequent and simplicity matters |
| Long polling | Client pulls; the server holds the request until data arrives | Moderate real-time needs over plain HTTP |
| Server-Sent Events (SSE) | Server → client, one way | Live feeds, notifications, streaming LLM tokens |
| WebSockets | Bidirectional | Chat, multiplayer games, collaborative editing |
| WebRTC | Peer-to-peer media and data | Voice and video calls |

### H. Consistency models (simplified)

| Model | Guarantee | Example use |
|---|---|---|
| Linearizable (strong) | Every read sees the latest write, as if there were one copy | Leader election, locks, account balances |
| Causal | Causally related operations are seen in order by everyone | Comment replies, chat threads |
| Read-your-writes | You always see your own updates | Editing your profile |
| Monotonic reads | You never see data go "back in time" | Feeds, timelines |
| Eventual | Replicas converge once writes stop | Like counts, view counts, DNS |

### I. The 20 trade-offs you must be able to articulate

1. SQL vs NoSQL
2. Strong vs eventual consistency
3. Latency vs consistency (PACELC)
4. Push (fan-out on write) vs pull (fan-out on read)
5. Synchronous vs asynchronous processing
6. Normalization vs denormalization
7. Cache-aside vs write-through
8. Pessimistic vs optimistic locking
9. Monolith vs microservices
10. Batch vs stream processing
11. REST vs gRPC vs GraphQL
12. Polling vs SSE vs WebSockets
13. Vertical vs horizontal scaling
14. Stateful vs stateless services
15. Single-leader vs multi-leader vs leaderless replication
16. Exact vs approximate answers (HyperLogLog, Count-Min Sketch)
17. At-least-once + idempotency vs exactly-once semantics
18. Precompute vs compute on demand
19. Build vs buy (managed services)
20. Cost vs performance vs reliability

**AI-era bonus:** RAG vs fine-tuning vs a bigger model; routing between small and large models; workflow vs agent.

### J. Capacity rules of thumb (modern hardware)

Order-of-magnitude starting points for estimation, summarized from Hello Interview's free [Modern Hardware Numbers for System Design Interviews (2025)](https://hellointerview.substack.com/p/modern-hardware-numbers-for-system). Real numbers vary with workload and instance size, so state them as assumptions.

| Component | Rule of thumb |
|---|---|
| In-memory cache (Redis) | 100K+ operations/second per instance; single-digit-millisecond latency within a region; up to ~1 TB of memory |
| Relational database (PostgreSQL, MySQL) | ~10–20K transactions/second on a well-tuned instance; up to ~64 TiB of storage per instance |
| Application server | 100K+ concurrent connections; 8–64 cores; 64–512 GB of RAM |
| Message broker (Kafka) | Up to ~1M messages/second per broker; 1–5 ms end to end within a region; up to ~50 TB of storage |

**The takeaway:** most applications can run on a single well-tuned database; sharding is usually driven by operational needs (data size, maintenance, isolation) rather than raw throughput. Say which reason applies before you shard.

### K. Cost anchors: what actually drives the bill

Cost is now graded, but nobody expects you to quote a price list. What they want is the ability to say **which line item dominates** and **which lever moves it**. Learn the shape of the table, not the digits.

| Cost driver | Rough shape (US regions, on-demand) | The lever that moves it |
|---|---|---|
| Object storage | Cents per GB-month; archive tiers are ~20× cheaper | Lifecycle policies, tiering, compression, deduplication |
| **Network egress to the internet** | ~10–100× the monthly cost of *storing* the same GB. Usually the surprise on the bill | CDN offload (cache hit ratio is a cost metric), compression, keeping traffic in-region |
| Cross-AZ / cross-region traffic | Charged per GB in both directions; chatty services multiply it | Co-locate callers and callees; batch; avoid chatty cross-region calls |
| Compute (CPU) | Per instance-hour; reserved and spot are far cheaper than on-demand | Right-sizing, autoscaling, spot for batch, higher utilization |
| **GPU compute** | 10–100× a comparable CPU instance-hour. Dominates any AI design | Batching, smaller models, caching, routing cheap requests to cheap models |
| Managed-service premium | A multiple of self-hosting the same thing | Usually worth paying — say so explicitly, and say why |
| LLM tokens | Per million tokens, output priced above input | Prompt/prefix caching, semantic caching, shorter contexts, model routing |
| Observability | Log *volume* is often a top-five line item | Sampling, log levels, metric cardinality limits, retention |

**How to use this in an interview:** name the top two drivers for *your* design, give a lever for each, then state the complexity you are declining to buy. "Reads dominate, so egress is the bill — I'd push redirects to the CDN and expect a 95% hit ratio. I'm not doing multi-region active-active; at 10K DAU it doubles cost to solve a problem we don't have."

**Live numbers** (check before quoting any figure): [AWS S3 pricing](https://aws.amazon.com/s3/pricing/) · [EC2 instance pricing comparison](https://instances.vantage.sh/) · [AWS Pricing Calculator](https://calculator.aws/).

---

## Complete Free Resource Index

### Guides and courses

| Resource | Best for |
|---|---|
| [Hello Interview: System Design in a Hurry](https://www.hellointerview.com/learn/system-design/in-a-hurry/introduction) | Framework, concepts, technologies, patterns and problem breakdowns |
| [System Design Primer](https://github.com/donnemartin/system-design-primer) | Breadth, solved examples and Anki flashcards |
| [System Design 101 (ByteByteGo)](https://github.com/ByteByteGoHq/system-design-101) | Visual explanations and real-world case studies |
| [Karan Pratap Singh: System Design course](https://github.com/karanpratapsingh/system-design) | A structured text course from basics to interview problems, free to read on GitHub (an ebook version is sold separately) |
| [awesome-system-design-resources](https://github.com/ashishps1/awesome-system-design-resources) | Curated free articles by topic, plus a problem list |
| [interviewing.io: A Senior Engineer's Guide to the System Design Interview](https://interviewing.io/guides/system-design-interview) | What interviewers look for; green and red flags; worked examples |
| [Kleppmann: Distributed Systems lectures](https://www.youtube.com/playlist?list=PLeKd45zvjcDFUEv_ohr_HdUFe97RItdiB) + [notes](https://www.cl.cam.ac.uk/teaching/2122/ConcDisSys/dist-sys-notes.pdf) | University-level distributed systems theory |
| [MIT 6.5840 Distributed Systems](https://pdos.csail.mit.edu/6.824/) | A graduate course with papers and labs |
| [CMU 15-445 Database Systems](https://15445.courses.cs.cmu.edu/) | Database internals |
| [Distributed Systems for Fun and Profit](https://book.mixu.net/distsys/) | A short, free book |
| [Google SRE books](https://sre.google/books/) | Reliability, SLOs and operations (three free books) |
| [Front End Interview Handbook: System Design](https://www.frontendinterviewhandbook.com/front-end-system-design) | Frontend system design rounds (free) |
| [GreatFrontEnd: Front End System Design Playbook](https://www.greatfrontend.com/front-end-system-design-playbook) | Frontend system design in depth (some content is premium) |
| [Kubernetes: Overview](https://kubernetes.io/docs/concepts/overview/) + [Kubernetes Basics tutorial](https://kubernetes.io/docs/tutorials/kubernetes-basics/) | Container orchestration basics |

### YouTube channels

| Channel | Best for |
|---|---|
| [Hello Interview](https://www.youtube.com/@hello_interview) | Interview walkthroughs and real anonymized mocks |
| [ByteByteGo](https://www.youtube.com/@ByteByteGo) | Short visual concept videos |
| [Jordan has no life](https://www.youtube.com/@jordanhasnolife5163) | Deep concept series plus many problems |
| [Gaurav Sen](https://www.youtube.com/@gkcs) | Intuitive concept explanations and classic problem videos |
| [Arpit Bhayani (Asli Engineering)](https://youtube.com/c/ArpitBhayani) | Database internals, outage and engineering-blog dissections |
| [Hussein Nasser](https://www.youtube.com/@hnasr) | Networking, protocols, backend and database internals |
| [System Design Interview (Mikhail Smarshchok)](https://www.youtube.com/@SystemDesignInterview) | Long, deep problem videos (older, still excellent) |
| [Martin Kleppmann](https://www.youtube.com/@kleppmann) | Distributed systems lectures and talks |
| [Concept && Coding](https://www.youtube.com/@ConceptAndCodingByShrayansh) | LLD and HLD playlists with an Indian-interview focus |

### Articles, blogs and newsletters

| Resource | Best for |
|---|---|
| [Amazon Builders' Library](https://aws.amazon.com/builders-library/) | Production lessons from AWS engineers |
| [ByteByteGo blog and newsletter](https://blog.bytebytego.com/) | Weekly visual explainers (free issues plus paid deep dives) |
| [systemdesign.one](https://systemdesign.one/) | Free concept articles (the newsletter mixes free and paid posts) |
| [High Scalability](https://highscalability.com/) | An archive of architecture case studies |
| [awesome-scalability](https://github.com/binhnguyennus/awesome-scalability) | Real-world scalability articles, organized by topic |
| [Engineering blogs list](https://github.com/kilimchoi/engineering-blogs) | A directory of company engineering blogs |
| [Martin Kleppmann's blog](https://martin.kleppmann.com/) | Deep essays on distributed systems |
| [Cloudflare Learning Center](https://www.cloudflare.com/learning/) | Networking, CDN, DNS and security basics |
| [microservices.io patterns](https://microservices.io/patterns/) | Microservice patterns |
| [Modern Hardware Numbers for System Design Interviews (Hello Interview)](https://hellointerview.substack.com/p/modern-hardware-numbers-for-system) | Up-to-date capacity numbers for estimation |
| [Workload isolation using shuffle sharding](https://aws.amazon.com/builders-library/workload-isolation-using-shuffle-sharding/) | Blast radius and cell-based thinking |
| [Using load shedding to avoid overload](https://aws.amazon.com/builders-library/using-load-shedding-to-avoid-overload/) | What to do past capacity |
| [Reliability, constant work, and a good cup of coffee](https://aws.amazon.com/builders-library/reliability-and-constant-work/) | Designs that don't change behavior under stress |
| [Principles of Chaos Engineering](https://principlesofchaos.org/) | Resilience testing, the method |
| [OWASP Top 10](https://owasp.org/www-project-top-ten/) | The security risks worth naming |
| [Protocol Buffers language guide](https://protobuf.dev/programming-guides/proto3/) | Serialization and safe message evolution |
| [Confluent: schema evolution and compatibility](https://docs.confluent.io/platform/current/schema-registry/fundamentals/schema-evolution.html) | Backward vs forward compatibility in pipelines |
| [Kafka documentation: Design](https://kafka.apache.org/documentation/) | The log, partitions, replication and offsets, from the source |
| [EC2 instance pricing comparison](https://instances.vantage.sh/) + [AWS Pricing Calculator](https://calculator.aws/) | Cost reasoning with real numbers |

### Papers and visual tools

| Resource | Best for |
|---|---|
| [Raft](https://raft.github.io/) + [visualization](https://thesecretlivesofdata.com/raft/) + [extended paper](https://pdos.csail.mit.edu/6.824/papers/raft-extended.pdf) | Understanding consensus visually |
| [Jepsen consistency models](https://jepsen.io/consistency) | A map of consistency guarantees |
| [Dynamo paper](https://www.allthingsdistributed.com/files/amazon-dynamo-sosp2007.pdf) | The classic leaderless, highly available store |
| [Scaling Memcache at Facebook](https://pdos.csail.mit.edu/6.824/papers/memcache-fb.pdf) | Caching at massive scale |
| [The Tail at Scale](https://research.google/pubs/the-tail-at-scale/) | Why fan-out ruins p99, and the fixes |
| [GFS](https://pdos.csail.mit.edu/6.824/papers/gfs.pdf) · [MapReduce](https://pdos.csail.mit.edu/6.824/papers/mapreduce.pdf) · [Bigtable](https://static.googleusercontent.com/media/research.google.com/en//archive/bigtable-osdi06.pdf) · [Chubby](https://static.googleusercontent.com/media/research.google.com/en//archive/chubby-osdi06.pdf) · [ZooKeeper](https://pdos.csail.mit.edu/6.824/papers/zookeeper.pdf) · [Spanner](https://pdos.csail.mit.edu/6.824/papers/spanner.pdf) | The rest of [the 10-paper list](#the-10-paper-reading-list), all free PDFs |
| [Latency numbers](https://gist.github.com/jboner/2841832) + [interactive version](https://colin-scott.github.io/personal_website/research/interactive_latency.html) | Estimation |
| [Excalidraw](https://excalidraw.com/) | A free whiteboard for practice and remote interviews |

### Low-level design

| Resource | Best for |
|---|---|
| [awesome-low-level-design](https://github.com/ashishps1/awesome-low-level-design) | OOP, patterns, concurrency and LLD problems with solutions |
| [Refactoring.Guru](https://refactoring.guru/design-patterns) | Design patterns |
| [Concept && Coding LLD playlist](https://www.youtube.com/playlist?list=PL6W8uoQQ2c61X_9e6Net0WdYZidm7zooW) | Video walkthroughs of LLD concepts and problems |
| [workat.tech machine coding](https://workat.tech/machine-coding/) | Machine-coding format and practice problems |

### AI, ML and GenAI

| Resource | Best for |
|---|---|
| [Building A Generative AI Platform (Chip Huyen)](https://huyenchip.com/2024/07/25/genai-platform.html) | GenAI platform architecture |
| [Patterns for Building LLM-based Systems (Eugene Yan)](https://eugeneyan.com/writing/llm-patterns/) | LLM system patterns |
| [Building effective agents (Anthropic)](https://www.anthropic.com/research/building-effective-agents) | Agent and workflow design |
| [Evidently AI: 800 ML and LLM case studies](https://www.evidentlyai.com/ml-system-design) | Real-world ML and LLM systems |
| [Applied LLMs](https://applied-llms.org/) | Practitioner lessons from building with LLMs |
| [IGotAnOffer: GenAI System Design Interview](https://igotanoffer.com/en/advice/generative-ai-system-design-interview) | Example GenAI interview questions |

### Practice and mock interviews

| Resource | Best for |
|---|---|
| [Aced (formerly Exponent) practice](https://www.tryexponent.com/practice) | Free live peer mocks within monthly credits |
| [Hello Interview Guided Practice](https://www.hellointerview.com/practice/overview) | Free-to-start guided practice with AI feedback (system design and LLD) |
| [interviewing.io guide](https://interviewing.io/guides/system-design-interview) | Interviewer expectations, plus links to mock replays |

---

## Optional Paid Resources

Only if your budget allows. None of these are required.

| Resource | Why it's worth it |
|---|---|
| *Designing Data-Intensive Applications*, 2nd edition (Kleppmann and Riccomini, O'Reilly, 2026) | The best single book on data systems; the new edition covers newer tools and trends. An Indian reprint (Shroff/O'Reilly) is available. |
| *System Design Interview*, Vol. 1 and 2 (Alex Xu, ByteByteGo) | Clean worked solutions to classic interview problems |
| Hello Interview Premium | Premium problem breakdowns, more AI practice, and paid mocks with FAANG interviewers |
| Paid 1:1 mocks (Aced, interviewing.io, Hello Interview) | Most valuable in the final 2–3 weeks if free mocks aren't enough |

**Tip:** check your college or company library, and your employer's learning budget, before buying anything.

---

## Final Interview-Readiness Checklist

**Concepts**
- [ ] I can explain every Phase 1 component in 2 minutes: what, why, when not to use it, how it fails
- [ ] I can pick and justify a database, a caching strategy, and a queue vs a stream for any scenario
- [ ] I can explain CAP/PACELC, quorums, Raft, idempotency and sagas without notes
- [ ] I can finish a full estimation in under 3 minutes

**Practice**
- [ ] I've solved all 27 core problems and re-solved at least 10
- [ ] I've solved the stretch problems for my target role
- [ ] I finish the high-level design by about minute 25 and still have time for deep dives
- [ ] My trade-off journal has 40+ entries

**Mocks**
- [ ] I've done at least 8 mock interviews, scoring 3+ on every scorecard dimension in my last 3

**2026-specific**
- [ ] I bring up monitoring, failure modes and rollback in every design without being asked
- [ ] I can reason about cost and right-size a design
- [ ] I can design a RAG system and an LLM gateway at a high level

**LLD (if applicable)**
- [ ] I've completed 8+ timed machine-coding problems with runnable code
- [ ] I apply Strategy, Factory, Observer and State naturally, not forcibly

**Your own experience**
- [ ] I can walk through one system I built: its scale, architecture, key decisions, failures and what I'd change
- [ ] I've written that story using the [project deep-dive outline](#prepare-your-project-deep-dive) and rehearsed it out loud

---

## Version History

**v3 (28 September 2026): coverage audit and the ordered path.**

Added [The Straight Path](#the-straight-path-every-link-in-order): all 105 steps of the core track as one numbered sequence of links, so the roadmap can be followed without planning anything.

Coverage gaps found and closed:

- **Serialization and schema evolution was missing entirely.** Protobuf/Avro, backward vs forward compatibility and schema registries are now in [Phase 2A](#2a-core-module-week-7). Every design with a queue or a versioned API has this question hiding in it.
- **Tail latency had no treatment** beyond "p99 matters". [Phase 5](#phase-5-reliability-observability-security-and-cost) now covers fan-out tail amplification and hedged requests, with *The Tail at Scale* added to the reading.
- **Blast radius was missing.** Cell-based architecture and shuffle sharding are now covered.
- **No resilience *testing*.** Chaos engineering, load testing to failure and failover rehearsals added.
- **Cost was graded but had no reference.** New [cost anchors cheat sheet](#k-cost-anchors-what-actually-drives-the-bill) covering which line item dominates and which lever moves it.
- **OLTP vs OLAP was implicit.** Now a [just-in-time module](#2b-just-in-time-modules) before the analytics-flavored problems.
- **Six of the ten papers had no link.** All ten now link to free PDFs, plus SRE chapters deep-linked to the exact chapter.
- **Ordering bug:** the at-a-glance diagram listed Phase 2B before Phase 3, out of week order, and omitted the week-15 module.

Schedule bugs found by laying the weeks out step by step:

- **Week 11 doesn't fit its own budget.** It holds all of Phase 5, the geo module, three problems, an LLD problem and a mock — about 13 hours against a 12-hour target. Now labelled honestly, with the data-lifecycle module moved to week 12 and a named deferral (#18 Web crawler) instead of a silent overrun.
- **Two scheduled LLD problems had nowhere to sit:** the thread-safe rate limiter (week 11) and the key-value store with transactions (week 13) were in the schedule table but fell out of the weekly breakdown. Both now have slots.
- **A re-solve went missing:** week 8's re-solve of #5 was in the schedule but not in the week's work.

**v2 (28 September 2026): second-pass review.** Problems found in v1 and fixed:

- **Overloaded weeks.** v1's weeks 14–16 added up to roughly 13–15 hours against a stated 10–12. Every week is now rebalanced, and the schedule shows estimated hours.
- **Re-solves promised but not scheduled.** v1 said to re-solve problems after 1–2 weeks but only scheduled re-solves in weeks 15–16. There's now a 25-minute speed re-solve every week from week 6.
- **Week 7 was crammed.** Phase 2 is now a core module in week 7 plus just-in-time modules (geo, vectors, stream processing) right before the problems that need them.
- **The key-value store problem came before quorums.** It now gets a second pass in week 9, after replication and quorums are covered.
- **Mocks started late.** A low-stakes baseline mock now happens in week 8, and the plan accounts for the free mock-credit limit.
- **LLD ran into the busiest weeks.** Structured LLD now ends in week 13 unless your target companies run machine-coding rounds.

Added in v2: the Start Here summary, a placement test, a weekly time budget, fall-behind rules and a buffer week; round variations and frontend/mobile pointers; cloud and Kubernetes basics; capacity rules of thumb for modern hardware; bonus problems; an LLD language tip; guidance on using AI while preparing; a project deep-dive outline; a progress tracker; and calendar dates for a 28 September 2026 start.

**v1 (28 September 2026):** first version.

---

## Sources

Research for this roadmap (checked 28 September 2026):

**How interviews changed in 2026**
- DesignGurus: [System Design Interviews Changed in 2026](https://designgurus.substack.com/p/system-design-interviews-changed) and [8 Ways System Design Interviews Changed](https://designgurus.substack.com/p/what-changed-in-system-design-interviews)
- DesignGurus: [The Complete System Design Interview Guide (2026)](https://www.designgurus.io/system-design-interview)
- Aced (formerly Exponent): [System Design Interview Prep and Questions (2026 Guide)](https://www.tryexponent.com/blog/system-design-interview-guide) and [What to Expect in Google's System Design Interview (2026)](https://www.tryexponent.com/blog/google-system-design-interview)
- [The 2026 System Design Prep Playbook (Medium)](https://medium.com/@shivali0087/how-to-prepare-system-design-interviews-2026-b3068bd2e67e)

**Interview framework and expectations**
- Hello Interview: [Delivery Framework](https://www.hellointerview.com/learn/system-design/in-a-hurry/delivery), [Core Concepts](https://www.hellointerview.com/learn/system-design/in-a-hurry/core-concepts), [Key Technologies](https://www.hellointerview.com/learn/system-design/in-a-hurry/key-technologies), [Patterns](https://www.hellointerview.com/learn/system-design/in-a-hurry/patterns), [How I'd Prepare](https://www.hellointerview.com/blog/how-id-prepare) and [Expectations by Level](https://www.hellointerview.com/blog/the-system-design-interview-what-is-expected-at-each-level)
- [interviewing.io: A Senior Engineer's Guide to the System Design Interview](https://interviewing.io/guides/system-design-interview)

**Mock interviews**
- [Aced (formerly Exponent) practice page](https://www.tryexponent.com/practice) and [IGotAnOffer's review of Aced/Exponent](https://igotanoffer.com/en/advice/tryexponent-alternatives)

**India: machine coding**
- [Flipkart LLD questions from recent machine-coding rounds (Medium, 2026)](https://medium.com/@prashant558908/flipkart-low-level-design-interview-questions-from-recent-machine-coding-rounds-976f106f6368)
- [AlgoMaster: Types of LLD interviews](https://algomaster.io/learn/lld/lld-interview-types)
- [workat.tech: What is a machine coding round?](https://workat.tech/machine-coding/article/what-is-a-machine-coding-round-omfn1w54ojlg)

**Books, courses and theory**
- [O'Reilly: Designing Data-Intensive Applications, 2nd Edition](https://www.oreilly.com/library/view/-/9781098119058/) and the [Indian reprint listing](https://www.amazon.in/Designing-Data-Intensive-Applications-Maintainable-Greyscale/dp/9368089043)
- [Martin Kleppmann's website](https://martin.kleppmann.com/)
- [MIT 6.5840 (Spring 2026)](https://pdos.csail.mit.edu/6.824/)

**AI and ML system design**
- [Evidently AI: ML and LLM system design case studies](https://www.evidentlyai.com/ml-system-design)
- [IGotAnOffer: Generative AI System Design Interview](https://igotanoffer.com/en/advice/generative-ai-system-design-interview)

**Added in v2**
- [Modern Hardware Numbers for System Design Interviews (Hello Interview, 2025)](https://hellointerview.substack.com/p/modern-hardware-numbers-for-system)
- [Hello Interview's Ticketmaster walkthrough](https://www.youtube.com/watch?v=fhdPyoO6aXI) (notes that the question is common in Meta's product architecture and system design rounds)
- [Front End Interview Handbook: System Design](https://www.frontendinterviewhandbook.com/front-end-system-design)
- [Kubernetes: Overview](https://kubernetes.io/docs/concepts/overview/)

*All YouTube channels, repositories, articles and courses linked in the phases above were also verified during research.*

