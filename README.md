
# Robust Multi-Site ADHD Classification via GraphSAGE-Based Functional Connectivity Modeling from rs-fMRI

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.0%2B-orange.svg)](https://pytorch.org/)

## Title
**Robust Multi-Site ADHD Classification via GraphSAGE-Based Functional Connectivity Modeling from rs-fMRI**

### Authors
- **Rabab BOUSMAHA**¹* (✉)  
- Khouloud MERIBAI¹  
- Nardjes BOUCHEMAL²,³  
- Naila BOUCHEMAL⁴  
- Galina IVANOVA⁵  

---

### Affiliations
¹ LabRi Laboratory, Ecole Supérieure en Informatique, Sidi Bel Abbes 22000, Algeria  
² LIRE Laboratory, Abdelhamid Mehri Constantine 2 University, Constantine 25000, Algeria  
³ LISI Laboratory of Intelligent Systems and Informatics, Mila 43000, Algeria  
⁴ LyRIDS ECE Ecole d’Ingénieurs de Paris, 75015 Paris, France  
⁵ Faculty of Electrical Engineering, Electronics and Automation, University of Ruse “Angel Kanchev”, 7017 Ruse, Bulgaria  

**Corresponding Author:** Rabab BOUSMAHA — r.bousmaha@esi-sba.dz

## Abstract

Attention Deficit Hyperactivity Disorder (ADHD) is a heterogeneous neurodevelopmental disorder whose diagnosis is mainly based on behavioral assessment and is often delayed due to clinical complexity and limited availability of specialists. Resting-state functional magnetic resonance imaging (rs-fMRI) provides a valuable source of information for supporting automated and objective diagnosis.

This work proposes a **graph-based deep learning framework** for ADHD classification from rs-fMRI that combines **Phase-Locking Value (PLV)** functional connectivity estimation with **GraphSAGE** representation learning. The model effectively captures both regional brain activity and inter-regional interactions while remaining robust to noise and inter-site variability.

The proposed framework was evaluated on the publicly available **ADHD-200** dataset across multiple acquisition sites as well as on a combined multi-site dataset. The model achieved **Accuracy = 0.89**, **AUC = 0.96**, and **Specificity = 0.96** on the combined dataset, outperforming several existing methods.

---

## Key Features

- Phase-Locking Value (PLV) based functional connectivity
- 3-layer GraphSAGE with LayerNorm and Dropout
- Data augmentation (Gaussian noise + time shift) applied **only on training subjects**
- Stratified Cross-Validation (5 outer folds)
- Early Stopping + Learning Rate Scheduler
- Optimized decision threshold with minimum recall constraint
- Fully reproducible code

---

## Dataset

- **ADHD-200** Multi-site rs-fMRI dataset: The data used in this study are publicly available from the ADHD-200    Preprocessed initiative (Athena pipeline): http://preprocessed-connectomes-project.org/adhd200/

- Due to size constraints, the dataset files (.npy) 
  are hosted on Google Drive and can be accessed here : 
  [Download Dataset](https://drive.google.com/drive/folders/1ycOw3TS5qSSJPrFZuF3S4J2oUKSzKGO5?usp=sharing)

- You only need to change the paths of the `.npy` files in the notebook

---
## Prerequisites & Packages

### Required Python Version
- **Python ≥ 3.8**

### Main Packages

| Package                  | Version Recommendation |
|-------------------------|------------------------|
| torch                   | ≥ 2.0                  |
| torch-geometric         | Latest                 |
| numpy                   | ≥ 1.21                 |
| pandas                  | ≥ 1.5                  |
| scikit-learn            | ≥ 1.2                  |
| scipy                   | ≥ 1.10                 |
| networkx                | ≥ 3.0                  |
| pywavelets (pywt)       | ≥ 1.4                  |
| tqdm                    | Latest                 |
| matplotlib & seaborn    | Latest                 |
| joblib                  | Latest                 |

---
## How to Run

1. Clone or download the repository
2. Open the Jupyter notebook:
   ```bash
   jupyter notebook ADHD_PLV_GraphSAGE.ipynb
3. Update the dataset paths in the notebook:Python

TS_NPY  = "path/to/timeseries_NeuroIMAGE2.npy"
LAB_NPY = "path/to/labels_NeuroIMAGE2.npy"

4. Run all cells

Results, best model, and plots will be automatically saved in the Results/ folder.

## 📁 Project Structure

├── ADHD_PLV_GraphSAGE.ipynb       # Main notebook
├── README.md                       # Project documentation
└── Results/                        # Generated automatically after running
    ├── best_model_weights.pt        # Best model weights
    ├── scaler.pkl                   # Fitted scaler
    ├── confusion_matrix_global.png  # Confusion matrix plot
    ├── roc_curve_global.png         # ROC curve plot
    ├── precision_recall_curve.png   # Precision-Recall curve plot
    └── final_results_metadata.json  # Final results & metrics

## 📄 Citation

> This paper is currently **under review** at *MDPI Bioengineering* (Manuscript ID: `bioengineering-4271001`).  
> A full citation will be provided upon publication.
