# Hamza HATTAB

<div align="center">

### **AI Systems & Security Engineer | Applied Machine Learning & Agent Infrastructure**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Hamza_Hattab-0077b5?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/hamza-riadh-h-44a297345/)
[![GitHub](https://img.shields.io/badge/GitHub-Hamza--HATTAB-181717?style=flat-square&logo=github)](https://github.com/Hamza-HATTAB)
[![Email](https://img.shields.io/badge/Email-hhamzariadh@gmail.com-ea4335?style=flat-square&logo=gmail)](mailto:hhamzariadh@gmail.com)
[![Timezone](https://img.shields.io/badge/Timezone-UTC%2B1%20(4h%20EST%20Overlap)-emerald?style=flat-square)](https://time.is/EST)
[![Target](https://img.shields.io/badge/Target-Canadian%20AI%20Startups%20%26%20Scale--Ups-purple?style=flat-square)](#why-canadian-ai-scale-ups)

*Computer Science Engineering student specializing in Artificial Intelligence at USTHB (Algiers). Focused on building deterministic reference monitors for autonomous agents, high-throughput speculative LLM serving on constrained hardware, and claim-level attributed multi-hop RAG architectures.*

</div>

---

## ⚡ The Flagship Systems Trilogy

I believe production-grade AI systems cannot be built with stochastic prompt hacks alone. My work bridges low-level hardware constraints (RTX 4060 8GB GPU), deterministic reference monitors outside the model, and formal information flow control.

```
┌────────────────────────────────────────────────────────────────────────────────────────┐
│                          THE APPLIED AI SYSTEMS TRILOGY                                │
├──────────────────────────────┬──────────────────────────────┬──────────────────────────┤
│ 1. WARRANT                   │ 2. OPTISERVE                 │ 3. INTERPOSE             │
│ Agentic RAG & Attributed NLI │ PyTorch LLM Inference Engine │ Deterministic AI Monitor │
│ "Build it reliably"          │ "Make it fast & cheap"       │ "Break it on purpose"    │
└──────────────────────────────┴──────────────────────────────┴──────────────────────────┘
```

---

### 🛡️ 1. [INTERPOSE // Deterministic Security Reference Monitor for AI Agents](https://github.com/Hamza-HATTAB/interpose)
> **Deterministic Information Flow Control (IFC), Dynamic Taint Tracking & Adaptive Red-Teaming for Tool-Calling Agents.**

* **The Problem:** In-model prompt guardrails inevitably fail against indirect prompt injections and data poisoning attacks. Autonomous agents need deterministic, provably non-bypassable security barriers.
* **The Solution:** An out-of-band reference monitor intercepting all tool invocations, tracking data provenance across token slices with a mathematical join semi-lattice (`SANITIZED < TRUSTED < RESTRICTED < UNTRUSTED < ADVERSARIAL`), enforcing AST-level constraints (`ast`, `sqlglot`, `bashlex`), and gating irreversible actions behind cryptographic HMAC-SHA256 human sign-offs.
* **Empirical Benchmarks:** 
  * **0.0% Attack Success Rate (ASR):** 36 of 36 AgentDojo & PyRIT mutation attacks neutralized.
  * **100.0% Benign Task Utility:** Zero false-positive halts on enterprise workflows.
  * **Sub-Millisecond Overhead:** Mean latency **<0.038 ms** with pure CPU AST parsing.
* **Live System HUD:** 🌐 **[interpose.vercel.app](https://interpose.vercel.app/)**
* **Core Stack:** Python 3.13, FastAPI, PyRIT, AgentDojo, AST Parsing, Next.js 14, Tailwind CSS.

---

### ⚡ 2. [OPTISERVE // PyTorch Inference Acceleration & Speculative Decoding Engine](https://github.com/Hamza-HATTAB/optiserve)
> **Sub-8GB VRAM Reasoning Distillation, 5-Way Quantization Bake-Off & AirLLM 70B Layer-Wise NVMe Streaming.**

* **The Problem:** Serving frontier reasoning models (DeepSeek-R1 / Qwen2.5) locally requires expensive enterprise clusters (A100/H100), exceeding the budgets of edge deployments and lean startups.
* **The Solution:** A hardware-aware serving engine engineered for an 8GB RTX 4060 GPU. Combines exact rejection-sampling speculative decoding ($K=3$), LoRA-distilled draft models, a 5-way quantization bake-off (AWQ, GPTQ, GGUF, FP8 E4M3, FP16), and AirLLM layer-wise NVMe streaming for 70B parameter models.
* **Empirical Benchmarks:** 
  * **1.92× Generation Speedup:** 72.4 tokens/second on mathematical reasoning (GSM8K).
  * **Strict Memory Safety Guard:** Never violates the **<6.8 GB VRAM safety ceiling** on an 8GB host.
  * **Zero-Cloud 70B Execution:** Streams 70B weights from NVMe SSD inside **2,150 MB peak VRAM**.
* **Live System HUD:** 🌐 **[optiserve.vercel.app](https://optiserve.vercel.app/)**
* **Core Stack:** PyTorch 2.6, CUDA 12.4, HuggingFace Transformers, BitsAndBytes, AirLLM, Next.js 14.

---

### 🔍 3. [WARRANT // Attributed Multi-Hop Research Agent & Calibrated NLI Gate](https://github.com/Hamza-HATTAB/warrant)
> **Claim-Level Decomposition, CPU DeBERTa-v3 Cross-Encoder Verification & 3-State Selective Abstention.**

* **The Problem:** Standard RAG pipelines suffer from silent multi-hop hallucinations and confabulations when questions require cross-document reasoning or when evidence is missing.
* **The Solution:** An attributed agentic research system that decomposes generated hypotheses into fine-grained atomic assertions, evaluates them via a dual-stage pipeline (deterministic numerical/temporal guard + calibrated DeBERTa-v3 NLI cross-encoder at $\tau \ge 0.82$), and enforces a 3-state policy contract (`FULL_PASS`, `PARTIAL_PASS` with graceful pruning, or `ABSTAIN`).
* **Empirical Benchmarks:** 
  * **Zero Unsupported Assertions:** Calibrated selective prediction contract eliminates unsupported assertions across 200 HotpotQA evaluation sweeps.
  * **Zero-VRAM CPU Verifier:** DeBERTa cross-encoder runs on pure CPU in **689 ms**, preserving 100% GPU VRAM for the primary synthesis model.
  * **Ground-Truth Traceability:** Interactive DAG with sentence-level bidirectional citation mapping.
* **Live System HUD:** 🌐 **[warrant-alpha.vercel.app](https://warrant-alpha.vercel.app/)**
* **Core Stack:** Python 3.11, Qdrant Hybrid RRF, FlashRank, Gemma-3, DeBERTa-v3, Next.js 14.

---

## 🛠️ Technical Systems Competencies

| Domain | Production Tooling & Methodologies |
| :--- | :--- |
| **Inference & Acceleration** | PyTorch, CUDA, Speculative Decoding ($K=3$ Rejection Sampling), Quantization (AWQ, GPTQ, GGUF, FP8 E4M3), AirLLM NVMe Streaming, Continuous Batching, KV-Cache Optimization. |
| **Agent Reliability & RAG** | Attributed Multi-Hop RAG, Claim Decomposition, NLI Cross-Encoders (DeBERTa-v3), Selective Abstention Contracts, Qdrant (Hybrid Dense/BM25 RRF), FlashRank Re-ranking. |
| **AI Security & Red-Teaming** | Information Flow Control (IFC), Dynamic Taint Tracking, Join Semi-Lattices, AST Policy Enforcement (`ast`, `sqlglot`, `bashlex`), PyRIT Mutations, AgentDojo Benchmarks, HMAC-SHA256 HITL Gating. |
| **Backend & Infrastructure** | Python 3.11+, C++, FastAPI, Pydantic v2, Docker, Linux (Ubuntu/POSIX), Cloudflare Zero-Trust Tunnels, Pytest (89+ Automated Regression Tests). |
| **Frontend & Telemetry** | Next.js 14 LTS, TypeScript, Tailwind CSS, Dynamic SVG Lineage DAGs, WebSockets, Lucide Icons. |

---

## 🇨🇦 Why Canadian AI Scale-Ups? (The Remote Value Proposition)

I am specifically seeking **Remote AI Systems Engineer, LLMOps Infrastructure, or Applied ML Internships / B2B Contractor roles** with high-growth Canadian AI startups (Toronto, Montreal, Waterloo, Vancouver):

1. **4-Hour Daily Synchronous Overlap with EST:** Based in Algiers (`UTC+1`), my core working hours provide **4 full synchronous hours with Toronto/Montreal (8:00 AM – 12:00 PM EST)**, paired with uninterrupted afternoon blocks for deep systems development.
2. **Empirical Engineering vs. Toy Wrappers:** I do not build generic API-wrapper chatbots. Every project in my portfolio is an engineered engine backed by passing automated test suites, mathematical formalisms, and live interactive production deployments.
3. **Lean Resource Efficiency:** Proven track record of squeezing maximum throughput, zero-trust security, and attribution accuracy out of consumer hardware (RTX 4060 8GB) without requiring $50k/month cloud GPU clusters.

---

## 📬 Get In Touch

* **Email:** [hhamzariadh@gmail.com](mailto:hhamzariadh@gmail.com)
* **LinkedIn:** [linkedin.com/in/hamza-riadh-h-44a297345](https://www.linkedin.com/in/hamza-riadh-h-44a297345/)
* **GitHub:** [github.com/Hamza-HATTAB](https://github.com/Hamza-HATTAB)
* **Location:** Algiers, Algeria (Open to Remote Worldwide · Direct EST Collaboration)

---
<div align="center">
<sub>Built with precision. Engineered outside the model.</sub>
</div>
