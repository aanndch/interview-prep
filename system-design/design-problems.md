===============================================================================
                     SYSTEM DESIGN INTERVIEW PREPARATION
                        Design Problems & Framework
                           Fullstack Role - 5 Years Experience
                               Japan Market Focus
===============================================================================

===============================================================================
1. INTERVIEW FRAMEWORK (DELIVERY)
===============================================================================

Step 1: CLARIFY REQUIREMENTS (2-3 minutes)
-------------------------------------------
- Functional: What does the system do?
- Non-functional: Latency, throughput, availability targets
- Constraints: Users, scale, timeline

Questions to ask:
- What's the expected user base?
- What's the read/write ratio?
- What are the latency requirements?
- Is this global or regional?

Step 2: ESTIMATE SCALE (2-3 minutes)
-------------------------------------
- Daily Active Users (DAU)
- Requests per second (QPS): Average QPS and Peak QPS (typically 2x to 5x average)
- Data storage requirements (Writes/day * average size * retention window)
- Bandwidth estimates (Upload/download speeds)

Back-of-envelope calculations (Rule of Thumb):
- 1 Million DAU:
  - If average 100 actions/user/day = 100,000,000 requests/day.
  - Average QPS = 100,000,000 / 86,400s ≈ 1,160 QPS.
  - Peak QPS = Average QPS * 2 ≈ 2,320 QPS.
- 10 Million DAU:
  - Average QPS ≈ 11,600 QPS.
  - Peak QPS ≈ 23,200 QPS.
- Data Storage:
  - 100 Million daily uploads * 500 bytes per metadata record ≈ 50 GB/day.
  - 10M daily photo uploads * 200 KB average file size ≈ 2 TB/day.

Step 3: HIGH-LEVEL DESIGN (10-15 minutes)
------------------------------------------
- Draw main components
- Define APIs (REST endpoints/GraphQL schemas)
- Data models (SQL table structure vs NoSQL document collections)
- Basic architecture diagram

Components to include:
- Client (Web/Mobile)
- Load Balancer (Nginx/ALB - L4/L7)
- API Gateway (Auth, rate limit, path routing)
- Application Servers (Stateless services)
- Cache (Redis/Memcached cluster)
- Message Queue (Kafka/RabbitMQ logs)
- Database(s) (Primary SQL + Read Replicas, or NoSQL ring)

Step 4: DEEP DIVES (15-20 minutes)
-----------------------------------
- Identify bottlenecks (single points of failure, network latency bounds)
- Discuss scaling strategies (consistent hashing, database sharding)
- Address non-functional requirements (Availability vs Consistency)
- Trade-off discussions (OCC vs Pessimistic Locking, WAL buffers)

Step 5: JAPAN MARKET FOCUS (Specialized delivery notes)
-------------------------------------------------------
For Japan tech giants (LINE, Rakuten, Mercari, Yahoo Japan), structure your design around these local constraints:
- **Disaster Recovery (DR) Active-Active**: Due to earthquake risks, do not design for a single region. Propose multi-region active-active deployments between Tokyo (ap-northeast-1) and Osaka (ap-northeast-3). Discuss database replication lag and how to handle conflict resolution (Vector Clocks or CRDTs).
- **Commuter Traffic Concentration**: Tokyo trains experience massive QPS spikes at 8:00-9:00 and 18:00-19:00. Emphasize queue-buffering (Kafka) on ingestion and aggressive edge CDN caching (CloudFront) to prevent backend application thread pools from saturating.
- **Local Payment APIs Integration**: Integrating PayPay, LinePay, or Suica requires strict ledger schemas. Explain how you use the Transactional Outbox Pattern to guarantee that internal order records and third-party payment requests stay consistent without blocking database connections.

Step 6: WRAP UP (2-3 minutes)
-------------------------------
- Summarize design
- Discuss alternatives
- Mention monitoring/observability (RED metrics, distributed tracing spans)

===============================================================================
2. MASTER INTERVIEW ARCHETYPES (JUST ENOUGH PREP)
===============================================================================

Instead of memorizing 20+ niche system designs, master these 4 core archetypes that cover 90% of all fullstack system design questions:

1. Read-Heavy Key Lookup: URL Shortener (Bitly)
   - Core Concepts: Base62 hashing, unique ID generation (Snowflake), Cache-Aside scaling, Bloom filters, storage size rules.
   - Maps to: Distributed Cache, Search Autocomplete, News Aggregator, Pastebin.

2. Stateful WebSocket Event Flow: Chat System (LINE / WhatsApp)
   - Core Concepts: WebSocket gateway connection limits, user presence state, Cassandra LSM timeline log appending, offline notifications push sync.
   - Maps to: Notification Systems, Ride Sharing (Uber location updates), Video Streaming Metadata.

3. Write Protection & Rate Limiting: API Rate Limiter
   - Core Concepts: Token Bucket vs. Sliding Window Log, atomic Redis Lua scripts, Redis Hash memory layouts, API Gateway caching limits.
   - Maps to: Distributed Job Schedulers, DDOS prevention filters, API Gateways.

4. Transactional Booking & Ledgers: Hotel Booking / Payments System
   - Core Concepts: Double-booking prevention, Optimistic Concurrency Control (OCC) vs. Pessimistic Locking, distributed locks (Redlock), Transactional Outbox Pattern, idempotency keys.
   - Maps to: Payment Gateways, E-commerce Platforms, Ticket Reservation Systems.


===============================================================================
RESOURCES
===============================================================================

1. System Design Handbook: https://www.systemdesignhandbook.com/guides/system-design-fundamentals/
2. Roadmap.sh: https://roadmap.sh/system-design
3. Hello Interview: https://www.hellointerview.com/learn/system-design/in-a-hurry/introduction

===============================================================================
                               GOOD LUCK WITH YOUR INTERVIEW!
===============================================================================
