# CRISPR-GNN Top-5  
**AI-Powered Alternate Cut Site Ranking for Precision Gene Editing**

<div align="center">
  <img width="420" src="https://github.com/user-attachments/assets/d29ae237-49fb-4320-b71c-a269fb3aca9a" alt="CRISPR Top-5 Visualization"/>
  <br><br>
</div>

---

## Executive Summary

**CRISPR-GNN Top-5** extends the original GraphSAGE model to predict **not just one**, but the **top-5 most likely CRISPR-Cas9 cut sites** per sgRNA sequence — each with **confidence score** and **off-target risk**.

This enables **safer backup site selection**, reducing reliance on primary sites and improving experimental success rates.

- **34,582 sgRNA sequences** processed into graph inputs  
- **6,917 validation sequences** analyzed in production pipeline  
- **Top-5 confidence + risk scoring** with professional visualization  
- **Full MLOps via MLflow**: metrics, artifacts, model tracking  
- **Production-ready**: 5-minute end-to-end execution in Colab

---

## Key Features

| Feature | Implementation |
|-------|----------------|
| **Top-5 Cut Site Prediction** | `torch.topk(k=5)` on softmax logits |
| **Confidence Scoring** | Per-position probability (0–1) |
| **Off-Target Risk** | `risk = 1 - confidence` |
| **Color-Coded Visualization** | Green (>0.8), Orange (0.6–0.8), Red (<0.6) |
| **Batch Inference** | 32 sequences per batch (GPU-optimized) |
| **MLflow Tracking** | Parameters, metrics, CSVs, PNGs, logs |
| **Auto-Downloadable Outputs** | CSV, PNGs, MD reports |

---

## Model Architecture

```python
GraphSAGE GNN
├── Input: 30bp DNA → 30 nodes (4-dim one-hot: A,T,C,G)
├── 2 × SAGEConv layers (200 hidden units)
├── Global mean pooling
├── MLP → 30 logits (one per cut position)
└── Softmax → Top-5 probabilities + indices

---

## Top 5 Results and Confidence Scores
