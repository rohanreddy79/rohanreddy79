# Rohan Reddy Jakkam

**Software engineer building AI systems and the infrastructure underneath them.**
Software Engineer at UF Health · M.S. Computer Science, University of Florida · Y Combinator Startup School 2026

**Website: [rohanreddy79.github.io](https://rohanreddy79.github.io/)** · [LinkedIn](https://www.linkedin.com/in/jakkam-rohan-reddy-069a2a193/) · [jakkamrohan79@gmail.com](mailto:jakkamrohan79@gmail.com)

I work at the layer where machine learning meets systems engineering: training loops, retrieval
pipelines, agent runtimes, inference servers, and the consensus, indexing and gateway code that
production platforms depend on. In industry I have shipped an IRB-regulated healthcare data platform
used by 100+ NIH-funded researchers, a zero-to-one serverless video-analysis engine, and ad-platform
features for enterprise customers. The repositories below are written from scratch, tested in CI,
benchmarked with reproducible commands, and documented with honest roadmaps.

## AI engineering

| Project | What it is | Highlights |
|---|---|---|
| [tinygpt](https://github.com/rohanreddy79/tinygpt) | A GPT trained from scratch in PyTorch: byte-level BPE tokenizer, decoder-only transformer, KV-cache generation | 870K-parameter model trained on a laptop CPU in 147 s to 2.86 val loss; KV cache decodes 2.8× faster than recompute; 64 tests |
| [ragkit](https://github.com/rohanreddy79/ragkit) | Hybrid retrieval-augmented generation: BM25 + dense embeddings fused with reciprocal rank fusion, reranking, citations, CLI and HTTP API | recall@3 0.98 and MRR 0.94 on a 45-question eval corpus; BM25, dense and hybrid compared against a measured noise floor; 55 tests |
| [agentloop](https://github.com/rohanreddy79/agentloop) | A minimal agent runtime: typed tools with generated JSON schemas, budgets, parallel tool calls, structured outputs, JSONL tracing, Claude provider | Anthropic provider tested against a mocked SDK client; 8 parallel tools finish in 51 ms vs 413 ms serial; 153 offline tests |
| [evalkit](https://github.com/rohanreddy79/evalkit) | An evaluation harness for LLM apps: declarative tasks, deterministic metrics and LLM-as-judge, response cache, bootstrap confidence intervals, paired run comparison | paired bootstrap and sign test detect a +6.5-point change (95% CI +1.0 to +12.0) that overlapping intervals would hide; 63 tests |
| [batchserve](https://github.com/rohanreddy79/batchserve) | An inference server with dynamic batching, bounded queues with backpressure, Prometheus metrics and a Docker image | 17× throughput from batching (94 → 1,641 RPS, p50 648 → 36 ms); classifier at 96.7% on held-out templates; Docker image; 51 tests |
| [nanograd](https://github.com/rohanreddy79/nanograd) | A tensor autograd engine and neural-network library on NumPy, every gradient verified numerically; trains an MLP and a CNN | 30 differentiable ops, 75 finite-difference gradient checks; CNN reaches 98.3% on 8×8 digits in 1.7 s of CPU training; 156 tests |

## Systems engineering

| Project | What it is | Highlights |
|---|---|---|
| [raftkv](https://github.com/rohanreddy79/raftkv) | Raft consensus and a replicated key-value store in Go, with linearizable reads and a deterministic simulated network for partition and crash tests | Figure 2 Raft with ReadIndex reads and exactly-once client sessions; 20 seeded partition schedules under the race detector; ~300 ms failover |
| [hnswgo](https://github.com/rohanreddy79/hnswgo) | An HNSW approximate nearest-neighbour index from scratch in Go: persistence, deletes, concurrent search, HTTP service, recall/QPS benchmark | recall@10 of 0.999 at 35k queries/s single-threaded (12× brute force) on 20k×64 vectors; one allocation per query; CRC-checked persistence |
| [llm-gateway](https://github.com/rohanreddy79/llm-gateway) | An OpenAI-compatible LLM gateway in Go: virtual keys, rate limits, retries, provider fallback, circuit breakers, response cache, streaming translation, cost accounting | 65k requests/s at p99 1.7 ms through the full middleware chain; a 10%-failing upstream served 3,000 requests with zero client-visible errors; 87 race-clean tests |
| [mcp-toolbox](https://github.com/rohanreddy79/mcp-toolbox) | A sandboxed Model Context Protocol server in TypeScript: read-only SQLite, allow-listed filesystem and HTTP tools, with tests that prove each boundary | 8 tools over stdio and Streamable HTTP; 18 sandbox checks each mapped to a test; zero native dependencies via node:sqlite; 100 tests |

## Earlier projects

Coursework and smaller projects from 2022–2025, each brought up to the same standard in October 2026:
a real README, MIT license, pinned dependencies, the known bugs fixed, and a CI workflow that builds or
tests it on every push.

| Project | What it is | Language |
|---|---|---|
| [distributed-computing-model](https://github.com/rohanreddy79/distributed-computing-model) | Gossip and push-sum convergence simulated over line, full, 2D and imperfect-3D actor topologies with Akka.NET | F# |
| [chord-dht](https://github.com/rohanreddy79/chord-dht) | Chord peer-to-peer lookup: 160-bit SHA-1 ring, finger tables, stabilisation; measures about ½·log₂N hops per lookup after the routing fix | F# |
| [concurrent-client-server](https://github.com/rohanreddy79/concurrent-client-server) | Concurrent TCP calculator server and client with a small error-code protocol | F# |
| [GatorLibrary](https://github.com/rohanreddy79/GatorLibrary) | Library simulator on a hand-written red-black tree with min-heap reservation queues; golden-output test | Python |
| [Simple-File-Transfer-Chat](https://github.com/rohanreddy79/Simple-File-Transfer-Chat) | Peer-to-peer terminal chat with inline file transfer over raw TCP sockets | Python |
| [password-cracking-attacks](https://github.com/rohanreddy79/password-cracking-attacks) | Security coursework: brute-force, dictionary, rainbow-table and divide-and-conquer attacks on toy hashes | Python |
| [log-report-fixed](https://github.com/rohanreddy79/log-report-fixed) | A Terminal-Bench 2 task with its oracle and verifier, checked end to end in Docker | Python |
| [Django-deploy](https://github.com/rohanreddy79/Django-deploy) | Django + DRF polling app with a JSON vote API, fixed and covered by tests | Python |
| [streamlit-nyc-collisions](https://github.com/rohanreddy79/streamlit-nyc-collisions) | Streamlit dashboard over NYC motor-vehicle collision data: maps, hourly hexagons, top streets | Python |
| [Data-Science-and-analytics-Projects](https://github.com/rohanreddy79/Data-Science-and-analytics-Projects) | Seven notebooks: regression, k-means, retail and IPL EDA, decision trees, ARIMA on SENSEX, COVID maps | Jupyter |
| [Wetland-Detection-ML](https://github.com/rohanreddy79/Wetland-Detection-ML) | Wetland vs dry-land classification from spectral bands: trees, logistic regression, SVM, bagging, random forest | Jupyter |
| [sklearn-clustering-lab](https://github.com/rohanreddy79/sklearn-clustering-lab) | K-means, agglomerative and DBSCAN compared on synthetic blobs (re-executed on current scikit-learn) | Jupyter |
| [Random-Clusters](https://github.com/rohanreddy79/Random-Clusters) | The same clustering lab with the written analysis | Jupyter |
| [TASK-Check](https://github.com/rohanreddy79/TASK-Check) | Task dashboard and CLI with a Node test suite | JavaScript |
| [assessment](https://github.com/rohanreddy79/assessment) | Package-sorting exercise with 14 unit tests | Python |
| [spidr-airfryer-form](https://github.com/rohanreddy79/spidr-airfryer-form) | A small React form built for a take-home exercise | JavaScript |
| [Portfolio](https://github.com/rohanreddy79/Portfolio) | Previous portfolio site (React, Vite, Tailwind); superseded by [rohanreddy79.github.io](https://rohanreddy79.github.io/) | JavaScript |

## How I work

- Every repository has a test suite and a CI workflow; nothing is merged red.
- Every number in a README comes from a run on a stated machine, with the command to reproduce it.
- Hosted models are optional: tests and demos run offline with deterministic fakes.
- Each README explains the design decisions and the trade-offs, not only the usage.

## Experience

- **UF Health** · Software Engineer · Jan 2026–present · Scoped and shipped an IRB-regulated full-stack data platform (TypeScript, React, Python, AWS) for 100+ NIH-funded researchers: 99.9% uptime, interactive visualisation over 10M+ rows of healthcare data, 40% less manual retrieval and analysis time, demoed to NIAAA program leadership.
- **FilmTrends** · Founding Engineer · Oct 2025–Jan 2026 · Built the product from zero: a serverless video-processing engine on AWS Lambda analysing 10,000+ social accounts in parallel (latency 5 min → 30 s), an ML viral-prediction model over 50+ video features at 78% accuracy, infrastructure as code with Terraform and CloudFormation.
- **Koddi** · Software Engineer · Jun–Oct 2025 · Client-facing ad-platform features (React, TypeScript, GraphQL, Go) for Booking.com, Kroger and Grubhub; Go REST APIs and real-time pacing dashboards that cut customer-visible data discrepancies 45%.
- **University of Florida** · Software Engineer · Jan 2023–May 2025 · High-availability admin dashboard (Java, Spring Boot, React) consolidating 8 workflows at 99.9% uptime; Jenkins and Docker CI/CD that tripled release frequency.

## Side projects

- **Vera** · Voice AI agent platform for regulated industries. Agents whose actions are verifiable by design: a compliance finite-state machine constrains behaviour in real time, and a cryptographic audit ledger makes every action tamper-evident.
- **Layman** · AI news summariser live on the App Store. Cross-platform MVP shipped in 48 hours; production RAG backend (pgvector, Prisma) on an AWS Bedrock/SageMaker pipeline turning jargon into plain-language summaries.
- [AppleTune](https://github.com/rohanreddy79/AppleTune) · macOS menu-bar app in Swift for per-app volume, multi-device output, audio routing and a 10-band EQ.

## Skills

Every line names the repositories where the skill is demonstrated in working, tested code.

| Area | Skills | Proven in |
|---|---|---|
| Machine learning | PyTorch, NumPy, transformer architecture, BPE tokenisation, KV-cache inference, autograd and backpropagation, CNNs, optimisers and learning-rate schedules, numerical gradient checking, scikit-learn | [tinygpt](https://github.com/rohanreddy79/tinygpt), [nanograd](https://github.com/rohanreddy79/nanograd), [Wetland-Detection-ML](https://github.com/rohanreddy79/Wetland-Detection-ML), [sklearn-clustering-lab](https://github.com/rohanreddy79/sklearn-clustering-lab) |
| LLM engineering | Retrieval-augmented generation (BM25, hybrid retrieval, reciprocal rank fusion, reranking, cited answers), embeddings and vector search, agents and tool use, structured outputs, LLM evaluation and LLM-as-judge with confidence intervals, Anthropic and OpenAI APIs, Model Context Protocol, LangChain, guardrails | [ragkit](https://github.com/rohanreddy79/ragkit), [agentloop](https://github.com/rohanreddy79/agentloop), [evalkit](https://github.com/rohanreddy79/evalkit), [mcp-toolbox](https://github.com/rohanreddy79/mcp-toolbox), [llm-gateway](https://github.com/rohanreddy79/llm-gateway) |
| Systems and distributed | Raft consensus, linearizability, fault-injection simulation testing, HNSW approximate nearest-neighbour search, API gateways, token-bucket rate limiting, circuit breakers, retries with backoff, response caching, SSE streaming, dynamic batching and backpressure, actor model (Akka.NET), TCP socket programming | [raftkv](https://github.com/rohanreddy79/raftkv), [hnswgo](https://github.com/rohanreddy79/hnswgo), [llm-gateway](https://github.com/rohanreddy79/llm-gateway), [batchserve](https://github.com/rohanreddy79/batchserve), [chord-dht](https://github.com/rohanreddy79/chord-dht), [distributed-computing-model](https://github.com/rohanreddy79/distributed-computing-model), [concurrent-client-server](https://github.com/rohanreddy79/concurrent-client-server) |
| Languages | Python, Go, TypeScript, JavaScript, Java, SQL, Swift, C++, F# | all of the above, [AppleTune](https://github.com/rohanreddy79/AppleTune) |
| Backend and APIs | FastAPI, Django and Django REST Framework, Node.js, Flask, GraphQL, REST design, OAuth2 / JWT, Supabase Edge Functions (Deno), Streamlit, Prometheus metrics | [ragkit](https://github.com/rohanreddy79/ragkit), [batchserve](https://github.com/rohanreddy79/batchserve), [Django-deploy](https://github.com/rohanreddy79/Django-deploy), [streamlit-nyc-collisions](https://github.com/rohanreddy79/streamlit-nyc-collisions), visitlog (private: self-hosted site analytics) |
| Frontend | React, Next.js, React Native, hand-written HTML/CSS/JS, accessibility, performance and SEO | [rohanreddy79.github.io](https://github.com/rohanreddy79/rohanreddy79.github.io), [Portfolio](https://github.com/rohanreddy79/Portfolio), [spidr-airfryer-form](https://github.com/rohanreddy79/spidr-airfryer-form) |
| Data | PostgreSQL with row-level security, SQLite, Redis, Kafka, Spark, Airflow, Snowflake, ETL pipelines, pandas, Jupyter | [ragkit](https://github.com/rohanreddy79/ragkit), [mcp-toolbox](https://github.com/rohanreddy79/mcp-toolbox), [Data-Science-and-analytics-Projects](https://github.com/rohanreddy79/Data-Science-and-analytics-Projects) |
| Security | Sandboxing (path containment, SQL gating, host allow-lists), CSRF and auth hardening, applied cryptography coursework, CompTIA Security+ | [mcp-toolbox](https://github.com/rohanreddy79/mcp-toolbox), [Django-deploy](https://github.com/rohanreddy79/Django-deploy), [password-cracking-attacks](https://github.com/rohanreddy79/password-cracking-attacks) |
| Cloud, DevOps and quality | AWS, GCP, Supabase, Docker, Kubernetes, Terraform / CloudFormation, GitHub Actions CI, Jenkins, load testing and benchmarking, pytest, Go race detector, vitest, Django test client, uv and ruff, reproducible benchmarks with stated hardware | [batchserve](https://github.com/rohanreddy79/batchserve), [llm-gateway](https://github.com/rohanreddy79/llm-gateway), CI on all 28 repositories |

## Education

- **University of Florida** · M.S. Computer Science · Dec 2024
- **Manipal University** · B.Tech Computer Science · May 2023
- **Y Combinator Startup School** · 2026 cohort

## Contact

[LinkedIn](https://www.linkedin.com/in/jakkam-rohan-reddy-069a2a193/) · [jakkamrohan79@gmail.com](mailto:jakkamrohan79@gmail.com)
