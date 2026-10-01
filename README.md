<div align="center">

# Hamza Riadh HATTAB

### AI Systems & Machine Learning Engineer
**Attributed Agentic RAG · Low-Resource NLP · Multimodal Grounding**

[![WARRANT Demo](https://img.shields.io/badge/Live_Demo-WARRANT_RAG-10b981?style=flat-square&logo=vercel&logoColor=white)](https://warrant-hamza-riadh-s-projects.vercel.app/)
[![Research Poster](https://img.shields.io/badge/Research_Poster-MuJoCo_RL-e11d48?style=flat-square&logo=adobeacrobatreader&logoColor=white)](https://github.com/Hamza-HATTAB/llm-guided-reward-rl/blob/main/docs/poster.pdf)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Hamza_Riadh_Hattab-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/hamza-riadh-h-44a297345/)
[![Email](https://img.shields.io/badge/Email-hamza.riadh.htb%40gmail.com-ea4335?style=flat-square&logo=gmail&logoColor=white)](mailto:hamza.riadh.htb@gmail.com)
[![Location](https://img.shields.io/badge/Location-Algiers%20(UTC%2B1)-1f2937?style=flat-square)](https://time.is/Algiers)

</div>

---

## Systems Engineering Focus

> Production AI reliability requires deterministic out-of-band verification, fine-grained atomic claim decomposition, and real-time multimodal perception grounding.

My work bridges foundation model capabilities and production engineering constraints across two core areas:
1. **Attributed Agentic RAG & Fact Verification:** Eliminating multi-hop hallucination loops via fine-grained atomic claim decomposition, calibrated DeBERTa-v3 cross-encoders ($\tau \ge 0.82$), and formal 3-state selective abstention.
2. **High-Throughput PyTorch Inference Acceleration:** Accelerating autoregressive token generation via rejection-sampling speculative decoding (1.92x speedup) and single-GPU 70B parameter layer streaming.
3. **Autonomous Agent Security & Deterministic Reference Monitors:** Gating multi-agent tool execution loops with out-of-band AST taint tracking and join semi-lattice information flow control (0.0% ASR on AgentDojo).

```
+-------------------------------------------------------------------------------------------------------+
|                                   APPLIED AI SYSTEMS ARCHITECTURES                                    |
+---------------------------------------------------+---------------------------------------------------+
| 1. WARRANT                                        | 2. STARK VISION                                   |
| Attributed Agentic RAG Engine                     | Real-Time Multimodal Grounding Engine             |
| Atomic Claim Decomp & DeBERTa-v3 NLI Verification | Continuous Whisper STT + Swin-T + SAM 2 Memory    |
| [Zero Hallucination / 89 Automated Tests]         | [30 FPS Mask Propagation / Consumer Edge GPU]     |
+---------------------------------------------------+---------------------------------------------------+
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

### 2. [STARK VISION: Real-Time Multimodal Speech-to-Mask Grounding Engine](https://github.com/Hamza-HATTAB)

<div align="left">

[![Status](https://img.shields.io/badge/Status-In_Active_Development-orange?style=flat-square)]()
[![Affiliation](https://img.shields.io/badge/Research-School_of_AI_Algiers-blueviolet?style=flat-square)](https://github.com/SchoolofAI-Algiers)
[![Perception](https://img.shields.io/badge/Vision_Backbone-SAM_2_%2B_Swin--T-blue?style=flat-square)](https://github.com/facebookresearch/segment-anything-2)
[![Speech](https://img.shields.io/badge/Speech_Recognition-Streaming_Whisper-brightgreen?style=flat-square)](https://github.com/openai/whisper)
[![Framework](https://img.shields.io/badge/Framework-PyTorch_%2B_OpenCV-ee4c2c?style=flat-square&logo=pytorch)](https://pytorch.org/)

</div>

* **The Problem:** Existing referring video object segmentation models struggle with latency and temporal drift when operators use continuous, real-time vocal commands rather than static text queries.
* **Systems Architecture:**
  * **Decoupled Multimodal Pipeline:** Streams continuous natural vocal instructions through OpenAI Whisper, extracting acoustic tokens with minimal audio chunk latency.
  * **Cross-Modal Attention Grounder:** Fuses visual feature pyramids (Swin-Transformer backbone) with linguistic token projections via multi-scale cross-attention to predict geometric bounding box prompts.
  * **SAM 2 Temporal Memory Propagation:** Injects predicted bounding boxes as spatial prompts into Meta's Segment Anything Model 2 (SAM 2) memory-attention mechanism, maintaining pixel-accurate object masks across camera occlusions and continuous 30 FPS video feeds.
* **Engineering Highlights:**
  * Modular design decoupling speech recognition, vision-language grounding, and temporal mask propagation to enable independent model upgrades without full pipeline retraining.
  * Optimized for edge inference on consumer GPU hardware with low-latency OpenCV video streaming.
* **Tech Stack:** PyTorch, Whisper STT, SAM 2 (Segment Anything), Swin-T, Hugging Face Transformers, OpenCV, FastAPI, Python 3.11.

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
