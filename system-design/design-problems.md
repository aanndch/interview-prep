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
- Requests per second (QPS)
- Data storage requirements
- Bandwidth estimates

Back-of-envelope calculations:
- 1 million DAU = ~10-15 QPS
- 1 billion users = ~10K-15K QPS
- 1 KB per request, 1M requests = ~1 GB storage

Step 3: HIGH-LEVEL DESIGN (10-15 minutes)
------------------------------------------
- Draw main components
- Define APIs (REST endpoints)
- Data models (schema)
- Basic architecture diagram

Components to include:
- Client (Web/Mobile)
- Load Balancer
- API Gateway
- Application Servers
- Database(s)
- Cache
- Message Queue (if needed)

Step 4: DEEP DIVES (15-20 minutes)
-----------------------------------
- Identify bottlenecks
- Discuss scaling strategies
- Address non-functional requirements
- Trade-off discussions

Step 5: WRAP UP (2-3 minutes)
-------------------------------
- Summarize design
- Discuss alternatives
- Mention monitoring/observability

===============================================================================
2. COMMON INTERVIEW QUESTIONS
===============================================================================

CLASSIC PROBLEMS:
- Design URL Shortener (Bitly)
- Design Chat System (WhatsApp)
- Design News Feed (Facebook)
- Design Notification System
- Design Rate Limiter
- Design Search Autocomplete
- Design Web Crawler
- Design Payment System
- Design Ride Sharing (Uber)
- Design Video Streaming (YouTube)

INFRASTRUCTURE PROBLEMS:
- Design Distributed Cache
- Design Key-Value Store
- Design Job Scheduler
- Design Metrics Monitoring System
- Design Ad Click Aggregator

DATA-INTENSIVE PROBLEMS:
- Design Top K System
- Design News Aggregator
- Design E-commerce Platform
- Design Hotel Booking System

===============================================================================
3. QUESTION-SPECIFIC NOTES
===============================================================================

(To be filled in as you practice each problem)

===============================================================================
RESOURCES
===============================================================================

1. System Design Handbook: https://www.systemdesignhandbook.com/guides/system-design-fundamentals/
2. Roadmap.sh: https://roadmap.sh/system-design
3. Hello Interview: https://www.hellointerview.com/learn/system-design/in-a-hurry/introduction

===============================================================================
                               GOOD LUCK WITH YOUR INTERVIEW!
===============================================================================
