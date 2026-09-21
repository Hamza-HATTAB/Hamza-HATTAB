# Hamza HATTAB

<div align="center">

### **AI Systems Engineer | Applied Machine Learning & Agent Infrastructure**

[![Email](https://img.shields.io/badge/Email-hamza.riadh.htb%40gmail.com-ea4335?style=flat-square&logo=gmail&logoColor=white)](mailto:hamza.riadh.htb@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Hamza_Hattab-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/hamza-riadh-h-44a297345/)

*Computer Science Engineering student specializing in Artificial Intelligence at USTHB (Algiers). Focused on building deterministic reference monitors for autonomous agents, high-throughput speculative LLM serving on constrained hardware, and claim-level attributed multi-hop RAG architectures.*

</div>

---

## Core Systems Engineering Flagships

Autonomous AI systems cannot be built with stochastic prompt engineering alone. My work bridges low-level hardware constraints (RTX 4060 8GB GPU), deterministic reference monitors outside the model, and formal information flow control.

```
+----------------------------------------------------------------------------------------+
|                              APPLIED AI SYSTEMS ARCHITECTURE                           |
+------------------------------+------------------------------+--------------------------+
| 1. WARRANT                   | 2. OPTISERVE                 | 3. INTERPOSE             |
| Agentic RAG & Attributed NLI | PyTorch LLM Inference Engine | Deterministic AI Monitor |
| Reliability & Attribution    | Acceleration & Distillation  | Dynamic Taint & Security |
+------------------------------+------------------------------+--------------------------+
```

---

### 1. [INTERPOSE: Deterministic Security Reference Monitor for AI Agents](https://github.com/Hamza-HATTAB/interpose)

**Deterministic Information Flow Control (IFC), Dynamic Taint Tracking & Adaptive Red-Teaming for Tool-Calling Agents.**

* **Architecture & Mechanism:** An out-of-band reference monitor intercepting all tool invocations before execution. Tracks data provenance across token slices using a formal join semi-lattice (`SANITIZED < TRUSTED < RESTRICTED < UNTRUSTED < ADVERSARIAL`), enforces AST-level constraints (`ast`, `sqlglot`, `bashlex`), and gates irreversible operations behind cryptographic HMAC-SHA256 human-in-the-loop sign-offs.
* **Empirical Benchmarks:**
  * **0.0% Attack Success Rate (ASR):** Neutralized 36 of 36 AgentDojo threat vectors and PyRIT adaptive mutations (Base64 split, ISO-27001 drills, tag escaping).
  * **100.0% Benign Utility:** Zero false-positive halts on enterprise workflows.
  * **Sub-Millisecond Overhead:** Mean evaluation latency of **0.038 ms** with pure CPU AST parsing.
* **Live System HUD:** [interpose.vercel.app](https://interpose.vercel.app/)
* **Repository:** [github.com/Hamza-HATTAB/interpose](https://github.com/Hamza-HATTAB/interpose)
* **Stack:** Python 3.13, FastAPI, PyRIT, AgentDojo, AST Parsing, Next.js 14, Tailwind CSS.

---

### 2. [OPTISERVE: PyTorch Inference Acceleration & Speculative Decoding Engine](https://github.com/Hamza-HATTAB/optiserve)

**Sub-8GB VRAM Reasoning Distillation, 5-Way Quantization Bake-Off & AirLLM 70B Layer-Wise NVMe Streaming.**

* **Architecture & Mechanism:** A hardware-aware serving engine engineered for an 8GB RTX 4060 GPU. Implements exact rejection-sampling speculative decoding (K=3) with LoRA-distilled draft models, continuous batching, a 5-way quantization comparison (AWQ, GPTQ, GGUF, FP8 E4M3, FP16), and AirLLM layer-wise NVMe streaming for 70B parameter models.
* **Empirical Benchmarks:**
  * **1.92x Generation Speedup:** 72.4 tokens/second on mathematical reasoning trajectories (GSM8K).
  * **Strict Memory Safety Guard:** Enforces an invariant ceiling of **<6.8 GB VRAM** to prevent out-of-memory kernel faults.
  * **Zero-Cloud 70B Execution:** Streams 70B weights from NVMe SSD inside **2,150 MB peak VRAM**.
* **Live System HUD:** [optiserve.vercel.app](https://optiserve.vercel.app/)
* **Repository:** [github.com/Hamza-HATTAB/optiserve](https://github.com/Hamza-HATTAB/optiserve)
* **Stack:** PyTorch 2.6, CUDA 12.4, HuggingFace Transformers, BitsAndBytes, AirLLM, Next.js 14.

---

### 3. [WARRANT: Attributed Multi-Hop Research Agent & Calibrated NLI Gate](https://github.com/Hamza-HATTAB/warrant)

**Claim-Level Decomposition, CPU DeBERTa-v3 Cross-Encoder Verification & 3-State Selective Abstention.**

* **Architecture & Mechanism:** An attributed agentic research system that decomposes generated hypotheses into atomic assertions. Evaluates claims via a two-stage verification pipeline (deterministic numerical/temporal regex guard + calibrated DeBERTa-v3 NLI cross-encoder at tau >= 0.82) and enforces a 3-state selective prediction policy contract (`FULL_PASS`, `PARTIAL_PASS` with graceful claim pruning, or `ABSTAIN`).
* **Empirical Benchmarks:**
  * **Selective Abstention:** Eliminates unsupported assertions across 200 HotpotQA evaluation questions via formal refusal rather than ungrounded extrapolation.
  * **Zero-VRAM CPU Verifier:** DeBERTa cross-encoder evaluates on pure CPU in **689 ms**, preserving 100% GPU VRAM for generation.
  * **Bidirectional Citation Tracing:** Complete evidence DAG mapping assertions to cited Wikipedia paragraph spans.
* **Live System HUD:** [warrant-alpha.vercel.app](https://warrant-alpha.vercel.app/)
* **Repository:** [github.com/Hamza-HATTAB/warrant](https://github.com/Hamza-HATTAB/warrant)
* **Stack:** Python 3.11, Qdrant Hybrid RRF, FlashRank, Gemma-3, DeBERTa-v3, Next.js 14.

---

## Technical Competencies

| Domain | Systems & Tooling |
| :--- | :--- |
| **Inference & Acceleration** | PyTorch, CUDA, Speculative Decoding (K=3 Rejection Sampling), Quantization (AWQ, GPTQ, GGUF, FP8 E4M3), AirLLM NVMe Streaming, Continuous Batching, KV-Cache Optimization. |
| **Agent Reliability & RAG** | Attributed Multi-Hop RAG, Claim Decomposition, NLI Cross-Encoders (DeBERTa-v3), Selective Abstention Contracts, Qdrant (Hybrid Dense/BM25 RRF), FlashRank Re-ranking. |
| **AI Security & Red-Teaming** | Information Flow Control (IFC), Dynamic Taint Tracking, Join Semi-Lattices, AST Policy Enforcement (`ast`, `sqlglot`, `bashlex`), PyRIT Mutations, AgentDojo Benchmarks, HMAC-SHA256 HITL Gating. |
| **Backend & Infrastructure** | Python 3.11+, C++, FastAPI, Pydantic v2, Docker, Linux (Ubuntu/POSIX), Cloudflare Tunnels, Pytest (89+ Automated Regression Tests). |
| **Frontend & Telemetry** | Next.js 14 LTS, TypeScript, Tailwind CSS, Dynamic SVG Lineage DAGs, WebSockets. |
