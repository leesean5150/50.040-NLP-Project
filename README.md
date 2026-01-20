# Sparse Upcycling: GPT-2 to Mixture-of-Experts (MoE)

**Project for 50.040 Natural Language Processing (SUTD)**

## Overview
This repository implements the **upcycling of a dense GPT-2 model into a sparse Mixture-of-Experts (MoE) architecture**. By leveraging **Top-1 routing** and **Drop-Upcycling** methodologies, the model achieves performance parity with the dense baseline on cross-lingual transfer tasks (XNLI-MT) while utilizing only **~4% of the original pre-training data**.

## Project Structure
This module consisted of 3 phases. This repository focuses on the **Extended Task (Phase 3)**:
1.  **Rebuilding GPT-2:** Implementation of the standard transformer architecture.
2.  **Cross-Lingual Transfer:** Zero-shot, one-shot, and few-shot evaluation.
3.  **MoE Upcycling (Current):** Modifying the dense architecture into a sparse MoE model with 8 experts.

## Technical Highlights
* **Architecture:** Converted dense feed-forward networks into sparse MoE layers.
* **Optimization:** Implemented **auxiliary loss** and **router jitter** to prevent expert collapse and ensure load balancing.
* **Analysis:** Investigated expert routing patterns, identifying distinct syntactic specializations for English and French tokens.

## Documentation
* **[View Technical Report (PDF)](./NLP_Report.pdf):** Full detailed analysis of the architecture, experiments, and results.
* **[View Code (Jupyter Notebook)](./moe_upcycling.ipynb):** Complete implementation and training loop.
    * *Note: If the notebook fails to load on GitHub, please use [google collab](https://colab.research.google.com/github/leesean5150/50.040-NLP-Project/blob/main/moe_upcycling.ipynb) instead.