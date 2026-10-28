# Denis Priimenko

_Senior Golang Developer | FinTech & SaaS | High-Load & Distributed Systems | Go, gRPC, AWS, Kafka, PostgreSQL, Kubernetes_

Belgrade, Serbia, RS · priimedenis6@gmail.com · https://www.linkedin.com/in/denis-priimenko · [LinkedIn](https://www.linkedin.com/in/denis-priimenko) · [+381637595623](https://wa.me/381637595623) · [@prijmary](https://t.me/prijmary) · [GitHub](https://github.com/priimedenis)

## About me

Golang Developer with 7+ years of experience in banking services, enterprise analytics, and business process automation. I work with high-load systems where transaction correctness, data consistency, and the behavior of external integrations during failures are critical. I handle tasks from API contracts and storage schema design through event processing, release, and ongoing service maintenance. My engineering work focuses on separating transactional and analytical workloads, diagnosing issues in concurrent processing, and restoring data exchange after failures.

## Skills

- **Languages and Backend/API**: Go (Golang), PHP, REST API, gRPC, Protobuf, HTTP, OAuth 2.0, OpenID Connect (OIDC), JWT, RS256, JWKS, Python
- **Data and Message Brokers**: PostgreSQL, MySQL, Redis, ClickHouse, MongoDB, Kafka, RabbitMQ, SQL optimization, Caching, CDC, ETL, Data quality validation
- **Infrastructure and Observability**: AWS (EKS, RDS, S3, IAM, Secret Manager, Cognito), Docker, Kubernetes, Linux, Git, CI/CD, GitLab CI, Prometheus, Grafana, Grafana Tempo, Elasticsearch, pprof
- **Architecture and Engineering Practices**: Distributed systems, Microservices, Event-driven architecture, Extracting services from PHP codebases, Transactional Outbox, Message retries, DLQ, Provider isolation, SLO-based service operations, Incident analysis

## Experience

### [Sberbank](http://sberbank.ru/) — Senior Golang Developer (Aug 2024 – Present)

As a Senior Golang Developer at Sberbank, I build and optimize backend services and APIs for the customer banking portal. My work covers bank statements, transaction history, debit and credit notifications, bank details validation, and integrations with payment providers.

- Increased productivity by 30% across several teams working on Go projects: developed an MCP server and AI agents tailored to the bank's in-house LLM, providing it with project context and automating work from requirements to implementation. Other teams adopted the solution and tailored it to their own projects.
- Decoupled debit/credit push notifications via a Go Kafka consumer and latest transaction status in Redis. Payroll-day delays fell from minutes to seconds; sending notifications no longer blocks transaction processing.
- Isolated payment providers in goroutine pools with gRPC timeouts and Redis fallback. Provider degradation no longer ties up shared connections; other APIs meet SLOs with p95 <150 ms and error rates <0.3%.
- Built a real-time transaction activity data mart using Kafka, ClickHouse, SQL cohort/retention models and Grafana segment/type views, replacing reports assembled from manual exports over business days.
- Cut MTTR by at least 2x with Prometheus/Grafana SLO alerts, Elasticsearch and pprof. Found shared cache mutex contention during a payroll peak and introduced per-shard locks, restoring SLO latency and enabling metric/log-based incident analysis.
- Automated banking-system reconciliation using PostgreSQL CDC, Kafka and Grafana discrepancy alerts. Replaced manual Excel comparisons and initial Python scripts with a Go task run through CI/CD.

### [GoodData.AI](https://www.gooddata.ai) — Senior Golang Engineer (Dec 2022 – Jul 2024)

As a Senior Golang Engineer at GoodData, I developed and maintained backend services for a SaaS analytics platform in an AWS cloud environment. My work covered customer data ingestion, ETL pipelines, KPI models, and REST APIs for dashboards.

- Migrated PHP ingestion to Go on AWS, splitting the synchronous endpoint into intake and processing. Kafka carries validated events for PostgreSQL batch writes. Reduced errors and data loss at peak traffic, decoupled acknowledgments from database writes, and enabled intake releases independent of the monolith.
- Replaced OLTP dashboard queries with a ClickHouse data mart incrementally updated by a Go Kafka consumer. With over 120M records, refresh fell from up to 35 minutes to within 15 seconds, providing fresh data while offloading heavy aggregations from the transactional database.
- Built Go ETL to assemble a unified analytical model from PostgreSQL, MySQL, CSV, and partner APIs, normalizing and deduplicating data before snapshots. Automated consistent daily datasets, eliminating hours of manual source consolidation.
- Created an enterprise KPI/dashboard builder with an analytical model, industry report templates, widgets, and period/segment filters. Customers got their first view sooner after connecting sources, avoided report setup delays, and platform NPS increased.
- Added statistical validation before data mart loading to detect outliers, missing values, and drift, quarantine problematic records, and alert through Grafana. Reduced incorrect dashboard incidents and exposed source errors during ingestion instead of manual dataset checks.
- Correlated Elasticsearch logs and distributed traces with a shared ID, adding Kafka consumer lag metrics in Prometheus/Grafana. Accelerated failure detection and resolution by revealing event paths and lagging processors.

### [Kissflow](https://kissflow.com) — Go Developer (Apr 2019 – Nov 2022)

As a Go Developer at Kissflow, I developed backend services for enterprise request submission and approval workflows. My work covered request intake and routing, status transitions, notifications, integrations with accounting systems, and completion reporting.

- Extracted request intake from a PHP monolith into Go, linking PostgreSQL writes to an outbox and Kafka; moved email delivery to RabbitMQ with retries and DLQ. Reduced creation errors under morning load; requests are acknowledged in seconds even during email retries.
- Replaced synchronous REST/HTTP status transitions with a Go state machine using PostgreSQL transactions and Kafka events. Eliminated write races during parallel approvals; status updates are atomic, logged and no longer stall at intermediate stages.
- Cached active request lists in Redis with TTL and status-based invalidation, replacing JOINs across 4 tables. Reduced p95 read latency to 45 ms with a cache hit rate of at least 84%, freeing PostgreSQL from repeatedly rebuilding the hot dataset.
- Replaced accounting/ERP REST adapters with gRPC, Protobuf and Kafka processing. External slowdowns no longer block user requests; the platform stays operational and applies integration responses from the queue as they arrive.
- Moved monthly request SLA reports to ClickHouse. A Go consumer aggregates Kafka events for completion times, overdue requests and department breakdowns. Reports run in seconds, removing heavy OLTP scans and freeing the database for request creation and approval.
- Added end-to-end Go request tracing: correlation IDs travel through Kafka headers and gRPC metadata, with paths shown in Grafana Tempo. Engineers locate missing requests in seconds without manually linking stdout logs, accelerating incident response.

## Education

### Saint Petersburg State Electrotechnical University "LETI" — Master’s Degree in Information Systems and Technology (2023 – 2025)

### Saint Petersburg State Electrotechnical University "LETI" — Bachelor’s Degree in Information Systems and Technology (2019 – 2023)

###
