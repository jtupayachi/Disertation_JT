# AI/ML-Enabled Microstructure Analysis for APT and ToF-SIMS

LaTeX source and project outline for the PhD dissertation proposal on a shared, multimodal machine learning framework designed to automate analysis for Atom Probe Tomography (APT) and Time-of-Flight Secondary Ion Mass Spectrometry (ToF-SIMS).


---

## Overview

This dissertation develops and validates a unified AI/ML framework to eliminate manual bottlenecks in nanoscale characterization. The system automates peak ranging, reconstruction disambiguation, pole-line indexing, and scientific reporting across both APT and ToF-SIMS data formats.

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


### Compilation Command

```bash
pdflatex proposal_one_pager.tex
```

Or using `latexmk`:

```bash
latexmk -pdf proposal_one_pager.tex
```