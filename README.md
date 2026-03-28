# KG-EDAS: A Meta-Metric Framework for Evaluating Knowledge Graph Completion Models
## Abstract
KGs are often incomplete, missing entities and relations, an issue addressed by Knowledge Graph Completion (KGC) methods that predict missing elements. Mean Reciprocal Rank (MRR), Mean Rank (MR), and Hit@k (e.g., MRR) are commonly used to assess the performance of KGC models. A major challenge in evaluating KGC models however, lies in comparing their performance across multiple datasets and metrics. A model may outperform others on one dataset but underperform on another, making it difficult to determine overall superiority. Moreover, even within a single dataset, different metrics such as MRR and Hit@1 can yield conflicting rankings, where one model excels in MRR while another performs better in Hit@1, further complicating model selection for downstream tasks.  To address this fragmentation, we propose \textbf{KG-EDAS}, Inspired by Inspired by Multi-Criteria Decision-Making (MCDM), \textit{E}valuation based on \textit{D}istance from \textit{A}verage \textit{S}olution (EDAS), a robust meta-metric that synthesizes model performance across multiple datasets and diverse evaluation criteria into a single normalized score ($M_i \in [0,1]$). Experiments on five standard datasets show that KG-EDAS produces stable, interpretable rankings highly correlated with MRR ($\rho=0.93$) while resolving conflicts across metrics. In addition, it integrates multi-metric, multi-dataset performance into a unified ranking, offering a consistent, robust, and generalizable framework that resolves conflicting rankings and supports informed model selection in real-world KGC applications. We argue that KG-EDAS offers a principled foundation for standardized evaluation in KGC—enabling fair comparisons and supporting automated model selection.

### Knowledge Graph Embedding, Link Prediction, Evaluation Metrics, Multi-criteria Decision Making, Model Ranking, Performance Aggregation



[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

**KG-EDAS** is a Python implementation of the **Evaluation based on Distance from Average Solution (EDAS)** method, adapted as a robust **meta-metric** for ranking Knowledge Graph Completion (KGC) / Knowledge Graph Embedding (KGE) models.

This tool addresses the long-standing challenge in KGC evaluation: conflicting rankings across multiple datasets (e.g., FB15k-237, WN18RR) and metrics (MRR, Hit@1, Hit@3, Hit@10, MR). KG-EDAS synthesizes all performance signals into a single normalized score **M ∈ [0, 1]**, providing stable, interpretable, and generalizable model rankings.

---

##  Associated Research Paper

**Title**: KG-EDAS: A Meta-Metric Framework for Evaluating Knowledge Graph Completion Models  
**Authors**: Haji Gul¹, Abdul Ghani Naim¹, Ajaz Ahmad Bhat¹*  
**Affiliation**: School of Digital Science, Universiti Brunei Darussalam  

**Paper Link**: [IEEE Big Data 2025](https://www.computer.org/csdl/video-library/video/2dOy17xNjQQ)
**ORCIDs**:  
- Haji Gul: [0000-0002-2227-6564](https://orcid.org/0000-0002-2227-6564)  
- Abdul Ghani Naim: [0000-0002-7778-4961](https://orcid.org/0000-0002-7778-4961)  
- Ajaz Ahmad Bhat: [0000-0002-6992-8224](https://orcid.org/0000-0002-6992-8224)

**Abstract**:  
We propose **KG-EDAS**, a Multi-Criteria Decision-Making (MCDM) based meta-metric inspired by EDAS. It aggregates performance across multiple datasets and heterogeneous metrics (MR, MRR, Hits@k) into one unified score. Experiments on five standard benchmarks show high correlation with MRR (ρ = 0.93) while resolving metric conflicts and enabling fair cross-dataset comparisons.

---

## Key Features

- Automatic detection of models and criteria from CSV
- Support for **beneficial** (higher better: MRR, Hits@k) and **non-beneficial** (lower better: MR) criteria
- Two weight strategies: Equal weights or custom per metric type
- Full computation of PDA, NDA, WPDA, WNDA, and final **M** score
- Stable and interpretable rankings with linear time complexity **O(nm)**
- Saves all intermediate results (Average, PDA, NDA, WPDA, WNDA, final ranking)

---

#
KG-EDAS/
├── dataloader.py
├── edas.py
├── utils.py
├── main.py
├── tail_prediction_results.csv          # Example input (tail prediction)
├── requirements.txt
├── README.md
├── paper/
│   ├── IEEE_BigData__KG_EDAS_.pdf       # Full paper
│   └── Figure1.png                      # Figure 1: Correlation & Comparison Plots
└── outputs/                             # Generated results (gitignored)

---



## Figure 1 from the Paper

**Figure 1**: Comparison of mean MRR, mean Hit@1, and KG-EDAS **M** scores across multiple datasets.

![KG-EDAS Figure 1](FB237_MRR_Hit1_vs_EDAS.png)

![KG-EDAS Figure 1](Combined_MRR_Hit1_vs_EDAS.png)

*Left: Relation prediction (mean MRR vs EDAS M). Right: Mean Hit@1 vs EDAS M values.*





## Quick Start

### 1. Clone the Repository

```bash
git clone https://github.com/hajigul/KG-EDAS.git
cd KG-EDAS




