#  ToxiFusion: Hybrid Framework for Toxic Peptide Prediction

##  Overview

ToxiFusion is a computational biology framework for toxic peptide prediction proposed in the accompanying manuscript:

“ToxiFusion: A Hybrid Framework for Toxic Peptide Prediction Using ProtBERT, AAC/DPC, and Tuned XGBoost”  
(Bioinformatics, Oxford University Press)

The method integrates:
- Protein Language Model embeddings (ProtBERT)
- Handcrafted compositional descriptors (AAC, DPC)
- Gradient boosting classifier (XGBoost)
- Sensitivity-constrained threshold optimization

---

##  Key Contributions

- Fusion of ProtBERT + AAC + DPC features
- PCA compression of embeddings (1024 → 256)
- Sensitivity-driven threshold optimization (OOF-based)
- Evaluation on ToxTeller, ToxIBTL, ToxinPred
- SHAP-based interpretability

---

## Model Pipeline

1. Input peptide sequence S  
2. Feature extraction:
   - ProtBERT embeddings + PCA
   - AAC (20D)
   - DPC (400D)
3. Feature fusion:
   x(S) = [BERT_PCA; AAC; DPC]
4. XGBoost classifier
5. Threshold optimization (Sn ≥ 0.88 constraint)

---

##  Datasets

- ToxTeller (fixed benchmark with independent test set)
- ToxIBTL (deep learning benchmark dataset)
- ToxinPred (classical toxicity dataset)

---

## Installation

git clone https://github.com/ameneayyoubi-hub/ToxFusion.git
cd ToxFusion
pip install -r requirements.txt

---

##  Usage

jupyter notebook

---

## Results Summary

- ToxTeller: Sn=0.80, Sp=0.92, MCC=0.73  
- ToxIBTL: Sn=0.88, Sp=0.96, MCC=0.75  
- ToxinPred: Sn=0.84, Sp=0.97, MCC=0.78  

---

##  Citation

@article{toxfusion2026,
  title={ToxiFusion: A Hybrid Framework for Toxic Peptide Prediction},
  author={Ayyoubi, Amene et al.},
  journal={Bioinformatics},
  year={2026}
}
