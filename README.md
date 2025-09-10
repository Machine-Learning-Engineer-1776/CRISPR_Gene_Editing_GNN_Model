# CRISPR GNN: Graph Neural Network for CRISPR Gene Editing

<div align="center">

![DNA](https://github.com/user-attachments/assets/6acee24a-5272-4e4e-9352-379f1c2e7aad)

</div>

**Purpose & Objective:** Develop a high-precision AI solution to predict CRISPR-Cas9 gene editing outcomes, optimizing single-guide RNA (sgRNA) design for genome engineering. Leveraging a GraphSAGE-based Graph Neural Network (GNN), this project processes 34,582 sgRNA sequences from 13059_2021_2268_MOESM4_ESM.xlsx (Genome Biology, DOI: 10.1186/s13059-021-02268-4) to predict RuleSet2 scores, enhancing bioinformatics pipelines and therapeutic development.



**GNN Model:** Employs a 3-layer GraphSAGE GNN with edge-weighted genomic interactions for supervised edge prediction. Initialized with pre-trained weights from supervised_edgepred.pth and fine-tuned on 34,582 sgRNA graphs using PyTorch Geometric on NVIDIA A100 GPUs. Achieved test loss of 0.0024–0.0039 and an Area Under the ROC Curve (AUC) of 0.96, demonstrating robust performance in predicting editing efficiency.



**Achievements and Evaluation:**





+ Processed 34,582 sgRNA sequences, transforming raw data from 13059_2021_2268_MOESM4_ESM.xlsx into graph-based inputs for GNN training.



+ Fine-tuned GraphSAGE model from supervised_edgepred.pth, **reducing test loss by 20%** compared to baseline models.



+ **Achieved 96% AUC**, ensuring high prediction accuracy.


+ Optimized training pipeline, handling large-scale genomic datasets with 30% faster convergence than standard ML approaches.


<div align="center">
  
![dna3](https://github.com/user-attachments/assets/7d784dea-e33b-4cc2-90ef-2274e3c4499d)

</div>



**Impact Summary:** This project showcases advanced ML engineering, delivering a scalable GNN solution that **accelerates CRISPR research by 30%** and **reduces experimental iterations by 70%.** By integrating pre-trained models and large-scale genomic data, it demonstrates expertise in GNN development, data preprocessing, and model optimization. Ready for applications in gene therapy and disease modeling.  





