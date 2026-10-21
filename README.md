# Rohan Reddy Jakkam

**Software engineer building AI systems and the infrastructure underneath them.**
Software Engineer at Koddi · M.S. Computer Science, University of Florida (2024)

I work at the layer where machine learning meets systems engineering: training loops, retrieval
pipelines, agent runtimes, inference servers, and the consensus, indexing and gateway code that
production platforms depend on. The repositories below are written from scratch, tested in CI,
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

## How I work

- Every repository has a test suite and a CI workflow; nothing is merged red.
- Every number in a README comes from a run on a stated machine, with the command to reproduce it.
- Hosted models are optional: tests and demos run offline with deterministic fakes.
- Each README explains the design decisions and the trade-offs, not only the usage.

## Background

- **Koddi** · Software Engineer · 2025–present · production features in React, TypeScript and GraphQL
- **University of Florida** · M.S. Computer Science · 2023–2024 · also a full-stack developer for the university
- Certifications: AWS Certified Solutions Architect – Associate, CompTIA Security+
- Languages and tools: Python, Go, TypeScript, Java, Swift, SQL · PyTorch, NumPy, FastAPI · Docker, Kubernetes, AWS, GCP

## Contact

[LinkedIn](https://www.linkedin.com/in/jakkam-rohan-reddy-069a2a193/) · [jakkamrohan79@gmail.com](mailto:jakkamrohan79@gmail.com)
