# AI/ML-Enabled Microstructure Analysis for APT and ToF-SIMS

LaTeX source and project outline for the PhD dissertation proposal on a shared, multimodal machine learning framework designed to automate analysis for Atom Probe Tomography (APT) and Time-of-Flight Secondary Ion Mass Spectrometry (ToF-SIMS).


---

## Overview

This dissertation develops and validates a unified AI/ML framework—combining spectral encoders, spatial encoders, cross-attention fusion, and a domain-specific LLM layer—to eliminate manual bottlenecks in nanoscale characterization. The system automates peak ranging, reconstruction disambiguation, pole-line indexing, and scientific reporting across both APT and ToF-SIMS data formats.

```
       +-------------------+       +-------------------+
       |  APT (POS/RRNG)   |       | ToF-SIMS (pySPM)  |
       +---------+---------+       +---------+---------+
                 |                           |
                 +-------------+-------------+
                               |
                   [FAIR Transcoding Layer]
                               |
            +------------------+------------------+
            |                                     |
    [Spectral Encoder]                    [Spatial Encoder]
     (1D CNN/Transformer)                    (CNN / GNN)
            |                                     |
            +------------------+------------------+
                               |
                    [Cross-Attention Fusion]
                               |
            +------------------+------------------+
            |                                     |
    [Automated Ranging &]                 [LLM Reporting Layer]
    [Pole Disambiguation]                 (vLLM + Literature RAG)
```

---

## Research Plan (Three-Paper Structure)

### Paper 1 (Basis for Fall Proposal Defense)
* **Title:** *A Shared AI/ML Framework for Automated Ranging and Microstructure Screening in APT and ToF-SIMS*
* **Scope & Objectives:**
  * Establishes the common two-modality representation and staged framework shared by APT and ToF-SIMS.
  * Documents the manual baseline and its failure modes on real LAMDA APT data (reconstruction ambiguity, molecular-ion overlap).
  * Defines the FAIR transcoding layer for vendor formats (`POS`/`RNG`/`RRNG` for APT; `ITA`/`ITM`/`ITS` via `pySPM` for ToF-SIMS).

### Paper 2 (Year 2)
* **Title:** *Automated Multimodal Ranging and Reconstruction via ML-ToF/Bayesian Peak Assignment and Learned Pole Indexing*
* **Scope & Objectives:**
  * Implements 1D CNN/Transformer spectral encoders for ranging and CNN/GNN spatial encoders for cluster and phase detection.
  * Resolves BCC-vs-FCC pole-indexing ambiguity and molecular-ion overlap identified in Paper 1.

### Paper 3 (Year 3)
* **Title:** *LLM-Driven Reporting and Literature-Grounded Interpretation for Correlative APT–ToF-SIMS Characterization*
* **Scope & Objectives:**
  * Integrates fused spectral/spatial embeddings into an LLM + literature Retrieval-Augmented Generation (RAG) reporting layer.
  * Validates automated reports against expert-authored reports and benchmarks the deployed `vLLM` pipeline (`ornl-qwen3-8-27b`).

### Compilation Command

```bash
pdflatex proposal_one_pager.tex
```

Or using `latexmk`:

```bash
latexmk -pdf proposal_one_pager.tex
```