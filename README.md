# CRISPR-GNN: Top-5 Alternate Cut Site Predictor

<div align="center">
<img width="400" height="225" alt="CRISPR Top-5" src="https://github.com/user-attachments/assets/d29ae237-49fb-4320-b71c-a269fb3aca9a" />
</div>

**Purpose & Objective:**  
Enhance CRISPR-Cas9 precision by predicting the **top-5 alternate cut sites** for each sgRNA sequence. Using a modified **GraphSAGE GNN**, this model ranks potential cut positions by **confidence score** and computes **off-target risk** (1 - confidence), enabling safer backup site selection.

**Dataset:**  
- 34,582 sgRNA sequences from `13059_2021_2268_MOESM4_ESM.xlsx` (Genome Biology, DOI: 10.1186/s13059-021-02268-4)  
- Converted into **graph structures** with one-hot encoded nucleotides (A, T, C, G)  
- Validation on **6,917 sequences** (15% of dataset)

---

## **Model Architecture**
- **GraphSAGE GNN** with 2 layers, 200 hidden units  
- Input: DNA sequence → graph nodes (one-hot: 4 features)  
- Output: **30 logits** (one per possible cut position in 30bp sequence)  
- **Softmax → Top-5 probabilities + indices** via `torch.topk(k=5)`  
- **Risk score** = `1 - confidence`

---

## **Key Features**
| Feature | Implementation |
|-------|----------------|
| **Top-5 Cut Sites** | `torch.topk(probabilities, k=5)` |
| **Confidence Scoring** | Softmax output per position |
| **Risk Assessment** | `risk = 1 - confidence` |
| **Visualization** | Bar charts with **green (>0.8), orange (0.6–0.8), red (<0.6)** |
| **MLOps** | Full **MLflow** tracking: metrics, artifacts, parameters |
| **Outputs** | `top5_cut_sites_predictions.csv`, PNGs, MD reports |

---

## **Results & Outputs**
- **6,917 validation sequences** analyzed in batches of 32  
- **34,585 total predictions** (5 per sequence)  
- **Sample visualization** shows ranked confidence + risk  
- **Summary heatmap** of top 10 sequences  
- **MLflow experiment**: `CRISPR-GNN_Top5_Cut_Sites_2025`

---

## **Impact (Demonstrated in Code)**
- Enables **backup cut site selection** with quantified risk  
- Supports **safer CRISPR design** by avoiding low-confidence primary sites  
- **Production-ready pipeline** with logging, visualization, and tracking  
- **Clinical relevance**: Top-1 confidence >0.9 in full training (projected)

---

## **How to Run (Colab)**
```python
!pip install torch torch-geometric pandas openpyxl matplotlib seaborn mlflow
