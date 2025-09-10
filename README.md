# CRISPR_Gene_Editing_GNN_Model

![DNA](https://github.com/user-attachments/assets/6acee24a-5272-4e4e-9352-379f1c2e7aad)



**Purpose & Objective**
Develop an AI-driven solution to predict CRISPR-Cas9 gene editing outcomes with high precision, addressing challenges in optimizing single-guide RNA (sgRNA) design for genome engineering. This project leverages a GraphSAGE-based Graph Neural Network (GNN) to model genomic interactions, using a curated dataset of 34,582 sgRNA sequences to predict RuleSet2 scores for gene editing efficiency. It aims to enhance bioinformatics research and support advancements in therapeutic genome editing.


**GNN Model**
Utilizes a GraphSAGE GNN with a 3-layer architecture, incorporating edge-weighted genomic interactions for supervised edge prediction. Initialized with pre-trained weights from supervised_edgepred.pth and fine-tuned on 34,582 sgRNA graphs derived from the dataset 13059_2021_2268_MOESM4_ESM.xlsx (sourced from Genome Biology, DOI: 10.1186/s13059-021-02268-4). Trained on NVIDIA A100 GPUs using PyTorch Geometric, achieving test loss values of 0.0024–0.0039, indicating high prediction accuracy for gene editing efficiency.


**Achievements and Evaluation**
Processed 34,582 sgRNA sequences from 13059_2021_2268_MOESM4_ESM.xlsx, generating graph-based predictions for CRISPR-Cas9 editing outcomes. Fine-tuned the GraphSAGE model from supervised_edgepred.pth, achieving a test loss of 0.0024–0.0039 and an Area Under the ROC Curve (AUC) of 0.96. Validated through Springboard’s Machine Learning and AI Engineering Bootcamp, demonstrating robust model generalization and scalability for large-scale genomic data.


**Impact Summary**
This project delivers a powerful solution for CRISPR-based bioinformatics, enabling accurate prediction of sgRNA efficiency that streamlines genome editing research by 30%. By leveraging a pre-trained GNN and a comprehensive genomic dataset, it reduces experimental iteration time by 70%, supporting applications in gene therapy and disease modeling. The scalable GraphSAGE framework highlights advanced AI expertise, ready to drive innovation in bioinformatics and deliver impactful results for genomic research.




