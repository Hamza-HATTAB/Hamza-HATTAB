<div align="center">

# Hamza Riadh HATTAB

### AI Systems & Machine Learning Engineer
**Agentic Reliability · Multimodal Perception & Grounding · Autonomous Agent Security**

[![WARRANT Demo](https://img.shields.io/badge/Live_Demo-WARRANT_RAG-10b981?style=flat-square&logo=vercel&logoColor=white)](https://warrant-hamza-riadh-s-projects.vercel.app/)
[![INTERPOSE Demo](https://img.shields.io/badge/Live_Demo-INTERPOSE_Security-6366f1?style=flat-square&logo=vercel&logoColor=white)](https://interpose.vercel.app/)
[![Research Poster](https://img.shields.io/badge/Research_Poster-MuJoCo_RL-e11d48?style=flat-square&logo=adobeacrobatreader&logoColor=white)](https://github.com/Hamza-HATTAB/llm-guided-reward-rl/blob/main/docs/poster.pdf)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Hamza_Riadh_Hattab-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/hamza-riadh-h-44a297345/)
[![Email](https://img.shields.io/badge/Email-hamza.riadh.htb%40gmail.com-ea4335?style=flat-square&logo=gmail&logoColor=white)](mailto:hamza.riadh.htb@gmail.com)
[![Location](https://img.shields.io/badge/Location-Algiers%20(UTC%2B1)-1f2937?style=flat-square)](https://time.is/Algiers)

</div>

---

## Systems Engineering Focus

> Autonomous AI systems cannot be built with stochastic prompt engineering alone. Production reliability requires deterministic out-of-band verification, real-time multimodal perception grounding, and non-bypassable security reference monitors outside the model weights.

My work bridges foundation model capabilities and production engineering constraints across three core areas:
1. **Attributed Agentic RAG & Fact Verification:** Eliminating multi-hop hallucination loops via fine-grained atomic claim decomposition, calibrated DeBERTa-v3 cross-encoders ($\tau \ge 0.82$), and formal 3-state selective abstention.
2. **High-Throughput PyTorch Inference Acceleration:** Accelerating autoregressive token generation via rejection-sampling speculative decoding (1.92x speedup) and single-GPU 70B parameter layer streaming.
3. **Autonomous Agent Security & Deterministic Reference Monitors:** Gating multi-agent tool execution loops with out-of-band AST taint tracking and join semi-lattice information flow control (0.0% ASR on AgentDojo).

```
+-------------------------------------------------------------------------------------------------------+
|                                   APPLIED AI SYSTEMS ARCHITECTURES                                    |
+-----------------------------------+-----------------------------------+-------------------------------+
| 1. WARRANT                        | 2. OPTISERVE                      | 3. INTERPOSE                  |
| Attributed Agentic RAG Engine     | High-Throughput Inference Engine  | Deterministic Security Monitor|
| Claim Decomp & DeBERTa-v3 NLI     | Speculative Decoding & AirLLM 70B | Dynamic AST Taint Tracking    |
| [100% Precision / 89 Tests]       | [1.92x Speedup / 5-Way Quant]     | [0.0% ASR / 0.038ms Latency]  |
+-----------------------------------+-----------------------------------+-------------------------------+
```

---

## Core Systems & Architectures

### 1. [WARRANT: Attributed Agentic RAG & Calibrated Fact Verification Engine](https://github.com/Hamza-HATTAB/warrant)

<div align="left">

[![Live Demo](https://img.shields.io/badge/Live_System-warrant--alpha.vercel.app-10b981?style=flat-square&logo=vercel)](https://warrant-hamza-riadh-s-projects.vercel.app/)
[![Repository](https://img.shields.io/badge/Repository-Hamza--HATTAB%2Fwarrant-181717?style=flat-square&logo=github)](https://github.com/Hamza-HATTAB/warrant)
[![Regression Tests](https://img.shields.io/badge/Automated_Tests-89_Passing-brightgreen?style=flat-square&logo=pytest)](https://github.com/Hamza-HATTAB/warrant)
[![NLI Verifier](https://img.shields.io/badge/Verifier-DeBERTa--v3--large_NLI-blue?style=flat-square)](https://huggingface.co/cross-encoder/nli-deberta-v3-large)
[![Vector Engine](https://img.shields.io/badge/Vector_DB-Qdrant_Hybrid_RRF-red?style=flat-square&logo=qdrant)](https://qdrant.tech/)

</div>

* **The Problem:** Standard RAG pipelines suffer from silent multi-hop hallucinations when questions require complex cross-document reasoning or when retrieved context is incomplete or adversarial.
* **Systems Architecture:**
  * **Atomic Claim Decomposition:** Parses complex model outputs into discrete, verifiable factual propositions.
  * **Deterministic Regex Guard:** Fast-path pre-validation of numerical, temporal, and entity constraints before neural evaluation.
  * **Calibrated DeBERTa-v3 Cross-Encoder:** NLI cross-encoder scoring claim entailment against retrieved context at an empirically calibrated threshold ($\tau \ge 0.82$).
  * **Cyclic LangGraph State Machine:** Enforces a 3-state selective prediction contract (`FULL_PASS`, `PARTIAL_PASS` with claim pruning, or `ABSTAIN`), formally refusing ungrounded extrapolation.
  * **Hybrid Dense/Sparse Retrieval:** Qdrant vector indexing combining dense semantic embeddings with sparse BM25 Reciprocal Rank Fusion (RRF) and sub-token citation DAGs.
* **Empirical Benchmarks:**
  * **Zero Hallucination Extrapolations:** Enforces formal abstention across 200 HotpotQA evaluation questions rather than emitting unsupported claims.
  * **Zero-VRAM CPU Verifier:** DeBERTa cross-encoder evaluates on pure CPU in **689 ms**, preserving GPU memory entirely for high-throughput generation.
  * **Automated Reliability:** Backed by an **89-test automated regression suite** covering edge-case token splits, contradiction pruning, and cyclical graph states.
* **Tech Stack:** Python 3.11, PyTorch, Hugging Face Transformers, DeBERTa-v3-large, Qdrant, LangGraph, FlashRank, FastAPI, Next.js 14, Docker.

---

### 2. [OPTISERVE: High-Throughput PyTorch Speculative Decoding Engine](https://github.com/Hamza-HATTAB/optiserve)

<div align="left">

[![Live Demo](https://img.shields.io/badge/Live_System-optiserve.vercel.app-6366f1?style=flat-square&logo=vercel)](https://optiserve.vercel.app/)
[![Repository](https://img.shields.io/badge/Repository-Hamza--HATTAB%2Foptiserve-181717?style=flat-square&logo=github)](https://github.com/Hamza-HATTAB/optiserve)
[![Speedup](https://img.shields.io/badge/Speedup-1.92x_Wall--Clock-brightgreen?style=flat-square)]()
[![Quantization](https://img.shields.io/badge/Quantization_Bake--Off-5--Way_Empirical-blue?style=flat-square)](https://github.com/Hamza-HATTAB/optiserve)
[![Framework](https://img.shields.io/badge/Framework-PyTorch_%2B_CUDA-ee4c2c?style=flat-square&logo=pytorch)](https://pytorch.org/)

</div>

* **The Problem:** Memory bandwidth bottlenecks and autoregressive token-by-token generation cap inference throughput on edge and cloud hardware, while large 70B parameter models exceed standard consumer VRAM capacities.
* **Systems Architecture:**
  * **Speculative Decoding Engine:** Pairs a compact draft model (Llama-3.2-1B) with a high-capacity target model (Llama-3.1-8B), using Leviathan modified rejection sampling to guarantee 100% mathematical output distribution equivalence.
  * **KV-Cache Optimization:** Verifies multi-token draft speculative trees in a single forward pass, reducing memory bandwidth pressure and latency.
  * **Blockwise Layer-Streaming (AirLLM):** Streams transformer weights layer-by-layer across NVMe-to-PCIe-to-VRAM, enabling local inference of 70B parameter models on a single consumer GPU (RTX 4060, 8GB VRAM).
  * **Production Telemetry & API:** High-concurrency FastAPI microservice with Server-Sent Events (SSE) streaming and Prometheus latency metrics (P95 TTFT, ITL).
* **Empirical Benchmarks:**
  * **1.92× Wall-Clock Speedup:** Realized sustained acceleration over autoregressive baselines on consumer hardware.
  * **5-Way Quantization Bake-Off:** Comprehensive benchmarking matrix across FP16, AWQ (4-bit), GPTQ (4-bit), GGUF (Q4_K_M), and FP8 (E4M3) on RTX 4060.
* **Tech Stack:** Python 3.11, PyTorch, CUDA, Hugging Face Transformers, AirLLM, FastAPI, Next.js 14, Tailwind CSS, Docker.

---

### 3. [INTERPOSE: Autonomous Agent Security & Deterministic Reference Monitor](https://github.com/Hamza-HATTAB/interpose)

<div align="left">

[![Live Demo](https://img.shields.io/badge/Live_System-interpose.vercel.app-6366f1?style=flat-square&logo=vercel)](https://interpose.vercel.app/)
[![Repository](https://img.shields.io/badge/Repository-Hamza--HATTAB%2Finterpose-181717?style=flat-square&logo=github)](https://github.com/Hamza-HATTAB/interpose)
[![Attack Success Rate](https://img.shields.io/badge/Attack_Success_Rate-0.0%25-success?style=flat-square)]()
[![Benchmark](https://img.shields.io/badge/Benchmark-AgentDojo_36%2F36-purple?style=flat-square)](https://github.com/Hamza-HATTAB/interpose)
[![Overhead](https://img.shields.io/badge/Overhead-0.038ms-yellow?style=flat-square)]()

</div>

* **The Problem:** Stochastic in-model guardrails inevitably fail against indirect prompt injection, tool jailbreaks, and data poisoning attacks. Autonomous agents require non-bypassable, deterministic reference monitors outside the model.
* **Systems Architecture:**
  * **Out-of-Band Execution Interceptor:** Sits directly between the LLM agent reasoning loop and system tool invocation APIs, validating every call before execution.
  * **Dynamic AST Taint Tracking:** Tracks data provenance across token slices using a formal join semi-lattice (`SANITIZED < TRUSTED < RESTRICTED < UNTRUSTED < ADVERSARIAL`).
  * **Deterministic AST Policy Enforcement:** Syntactically inspects payloads using Python `ast`, `sqlglot`, and `bashlex` to block unauthorized file writes, shell escapes, and SQL injection vectors.
  * **Cryptographic Human-in-the-Loop Gating:** Irreversible system operations (e.g., database deletions, balance transfers) trigger HMAC-SHA256 authenticated human sign-offs.
* **Empirical Benchmarks:**
  * **0.0% Attack Success Rate (ASR):** Neutralized 36 of 36 AgentDojo threat vectors and adaptive PyRIT mutations (Base64 splitting, ISO-27001 drills, markdown tag escaping).
  * **100.0% Benign Utility:** Zero false-positive halts on production enterprise workflows.
  * **Sub-Millisecond Overhead:** Mean evaluation latency of **0.038 ms** with pure CPU AST parsing.
* **Tech Stack:** Python 3.13, FastAPI, PyRIT, AgentDojo, AST Parsing, SQLGlot, Next.js 14, Tailwind CSS, Docker.

---

## Applied AI Research & Engineering Experience

### **Open-Source ML Systems Contributor** | [Awras AI](https://awras.site/en)
*Low-Resource Language Model Pretraining & SFT Infrastructure (2025 -- Present)*
* Engineered distributed data cleaning, deduplication, and quality filters for 100K+ token Algerian Darija and dialectal Arabic datasets, eliminating token fragmentation and dialect representation bias.
* Built end-to-end data processing pipelines and supervised fine-tuning (SFT) workflows on Transformer architectures, standardizing semantic consistency and factual accuracy evaluation benchmarks.

### **AI Research Fellow** | [School of AI Algiers](https://github.com/SchoolofAI-Algiers)
*LLM-Guided Reinforcement Learning for MuJoCo Humanoid-v4 (2023 -- Present)*
* Developed an LLM-assisted RL framework coupling a foundation model with Soft Actor-Critic (SAC) to automate iterative reward-function synthesis and refinement for obstacle navigation in MuJoCo Humanoid-v4.
* Achieved a **32% increase in episodic return** (3,290 to 4,350), boosted obstacle avoidance success from **38% to 69%**, and reduced collision rates from **51% to 24%** across 3 random seeds compared to hand-tuned baselines.
* **Research Paper Poster:** [Download Poster (PDF)](https://github.com/Hamza-HATTAB/llm-guided-reward-rl/blob/main/docs/poster.pdf)

### **Machine Learning Systems Intern** | Ericsson Algeria
*Industrial Telecommunications Applied AI (Jul 2025 -- Aug 2025 · Algiers, Algeria)*
* Engineered machine learning and computer vision pipelines for industrial telecom infrastructure datasets, executing automated feature extraction, data preprocessing, and model validation.
* Conducted comparative performance benchmarks across statistical ML and deep neural network baselines to evaluate operational classification accuracy and inference efficiency.

---

## Professional Certifications

* **[Deep Learning Specialization](https://www.coursera.org/specializations/deep-learning)** — DeepLearning.AI & Andrew Ng
  * *Focus:* Deep Neural Networks, Convolutional Neural Networks (CNNs), Sequence Models & Attention Mechanisms, Hyperparameter Tuning & Optimization.
* **[Machine Learning Specialization](https://www.coursera.org/specializations/machine-learning-introduction)** — Stanford Online & DeepLearning.AI
  * *Focus:* Supervised Learning, Advanced Learning Algorithms, Unsupervised Learning, Recommender Systems, Reinforcement Learning.

---

## Technical Arsenal & Production Stack

| Engineering Domain | Production Technologies & Tooling |
| :--- | :--- |
| **Deep Learning & Vision** | **PyTorch**, **Hugging Face Transformers**, **SAM 2 (Segment Anything)**, **Swin-T**, **Whisper STT**, OpenCV, Torchvision, Scikit-Learn |
| **Agentic Systems & NLP** | **Attributed RAG**, **DeBERTa-v3 NLI**, **LangGraph (Cyclic State Machines)**, **Qdrant (Hybrid Dense/BM25 RRF)**, FlashRank Re-ranking, SpaCy |
| **AI Security & Guardrails** | **AgentDojo Benchmark**, **Dynamic AST Taint Tracking (`ast`, `sqlglot`)**, Join Semi-Lattices, HMAC-SHA256 HITL Gating, PyRIT |
| **Backend & Distributed Systems** | **Python 3.11+**, **C++**, **FastAPI**, **Pydantic v2**, PostgreSQL, Redis, Docker, Linux (Ubuntu/POSIX), Git/GitHub CI/CD |
| **Reliability & Testing** | **Pytest (89+ Automated Regression Test Suites)**, HotpotQA Multi-Hop Evaluation, Semantic Abstention Contracts |
| **Frontend & Telemetry** | **Next.js 14**, TypeScript, Tailwind CSS, Dynamic Lineage DAGs, WebSockets, Vercel |

---

## Education & Technical Community

* **University of Science and Technology Houari Boumediene (USTHB)** | *Bab Ezzouar, Algiers*
  * **State Engineering Degree (Diplôme d'Ingénieur d'État) in Computer Science** — *Artificial Intelligence Specialization*
  * *Coursework:* Deep Learning, Machine Learning, Computer Vision, Natural Language Processing, Distributed Systems, High-Performance Computing, Advanced Algorithms.
* **Micro Club USTHB** (2024 -- Present): Member & AI Workshop Contributor — Leading technical sessions on open-source machine learning pipelines, algorithmic problem solving, and student hackathons.
* **Google Developer Groups (GDG) Algiers** (2024 -- Present): Active member & technical contributor in AI meetups and DevFests.

---

## Contact & Collaboration

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Hamza_Riadh_Hattab-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/hamza-riadh-h-44a297345/)
[![Email](https://img.shields.io/badge/Email-hamza.riadh.htb%40gmail.com-ea4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:hamza.riadh.htb@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-Hamza--HATTAB-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Hamza-HATTAB)

*Open to technical deep-dives, research collaborations, and production AI systems engineering challenges.*

</div>
