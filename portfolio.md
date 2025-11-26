---
layout: page
title: "Portfolio"
permalink: /portfolio/
---

# **Medical Imaging & Image Quality Enhancement**

*Low-Dose CT Denoising & Perceptual Quality Modeling*

![Representative LDCT Denoising Results](/assets/images/portfolio-denoising.png)

**Context.** Multi-year research program focused on low-dose CT denoising and perceptual image quality assessment, integrating supervised, unsupervised, and no-reference IQA methodologies.

- **Problem.** Restore high-quality CT images from ultra low-dose acquisitions while preserving diagnostic structures and texture fidelity.  
- **Approach.** Designed a multi-frame deep learning framework, developed unsupervised training pipelines without clean references, and introduced a self-supervised NIQA metric for perceptual CT quality.  
- **Role.** Led model architecture design, training pipelines, evaluation on clinical datasets, and coordinated collaboration with radiologists and imaging physicists.  
- **Methods.** PyTorch, self-supervised learning, CT reconstruction theory, noise modeling, perceptual metric design.  
- **Outcomes.** Multiple peer-reviewed publications and a comprehensive systematic review defining perceptual-quality-driven evaluation standards for LDCT denoising.

**📄 Selected Publications**

- *A systematic review of deep learning-based denoising for low-dose computed tomography from a perceptual quality perspective* (2024) – **Biomedical Engineering Letters**
- *An unsupervised two-step training framework for low-dose computed tomography denoising* (2023) – **Medical Physics**

**🔒 Selected Patents**

- **A learning and restoration method for reducing image noise using a neural network**
- **Method for removing medical image artifacts using artificial intelligence**

**➡️ [Full publications & patents](https://www.wjkim.com/about/)**

---

# **Psychology RAG System 🧠 (Ongoing)**

AI-augmented analytical tool for synthesizing fragmented interdisciplinary knowledge into unified theoretical frameworks.

- **Problem.** Complex psychological phenomena (trauma responses, behavioral loops, emotional incongruence) are scattered across hundreds of documents. Traditional search cannot reveal subtle conceptual links or temporal dependencies—blocking coherent theory formation.  
- **Solution.** Developed a 3-tier Hierarchical RAG system functioning as an **expert reasoning partner** (human-in-the-loop), enabling contextual reframing and cross-domain synthesis.  
- **Stack.** Python, FastAPI, React/TypeScript, ChromaDB, OpenAI Embeddings, GPT-4/Claude.  
- **Results.**  
  - 9,610 indexed chunks from 330+ documents (sub-2s retrieval latency)  
  - In-progress methodology paper validating system as a next-generation AI Research Tool (arXiv target)  
- **Roadmap.**  
  - 🧠 Fully personalized psychological analysis engine  
  - 🗂️ Hierarchical knowledge graph with semantic cross-referencing  
  - 🎯 Adaptive retrieval strategies (dynamic weighting by file type + context)  
  - 🔀 Query orchestration pipeline: decomposition → parallel retrieval → aggregation  

[GitHub — Coming Soon] · [White Paper — Coming Soon]

---

# **Physics-Informed Neural Adaptive Optics for OCT 🔬 (Ongoing)**

Self-supervised deep learning framework for computational aberration correction in optical coherence tomography—eliminating the need for expensive hardware adaptive optics.

- **Problem.** Optical aberrations degrade OCT image quality, limiting achievable resolution. Hardware AO is expensive ($50K–200K+) and assumes phase stability that many systems lack.  
- **Solution.** Designing a **physics-informed neural field** approach that jointly learns tissue structure and optical aberrations from a single measurement volume—fully self-supervised, no ground-truth labels required.  
- **Core Innovations.**  
  - Neural implicit representation for complex-valued scattering fields  
  - Differentiable OCT forward model with coherent interference physics  
  - Joint optimization of structural MLP weights + Zernike-based aberrations  
- **Stack.** PyTorch, custom OCT physics simulator  
- **Current Progress.**  
  - Neural coordinate representations adapted to interferometric imaging  
  - Successful phantom/tissue validation with measurable resolution improvement  
  - Exploration of depth-dependent aberration modeling  
- **Roadmap.**  
  - 🔬 Phase-stable optimization and robust training under realistic noise  
  - 🧠 Real-time inference for clinical deployment  
  - 📊 Extensions to PS-OCT and OCTA  
  - 📄 Publication target: biomedical optics journal (2026)

> The model jointly estimates the underlying 3D scattering structure and depth-dependent optical aberrations using a differentiable forward model grounded in OCT interferometry.
This enables coherent reconstruction without hardware adaptive optics.

[Code — Available upon publication] · [Preprint — Coming Soon]
