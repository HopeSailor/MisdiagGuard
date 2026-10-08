# MisdiagGuard

Research notebooks for clinical misdiagnosis risk prediction and feature identification.

**Research:** *Integrating Prior Knowledge with Multi-source Heterogeneous Data for Clinical Misdiagnosis Risk Prediction and Feature Identification*. [Related publication record](https://link.cnki.net/urlid/10.1478.g2.20260113.1308.002).

> **Reproducibility status:** This is a research notebook archive, not a turnkey clinical product. Several notebooks use hard-coded local Windows paths and private input datasets. The study cannot currently be reproduced from a clean checkout alone.

## Methods and notebook guide

| Notebook | Research step |
| --- | --- |
| [Preprocessing](code/Preprocessing.ipynb) | Aggregation of EMRs, screening repeated admissions and preparation for expert annotation |
| [Traditional machine learning](code/traditional_machine_learning.ipynb) | Logistic regression, SVM, decision trees, random forests, XGBoost, ROC/PR curves and SHAP |
| [ADASYN and violin plots](code/ADASYN_and_violin_plot.ipynb) | Imputation, class-balancing exploration and plots |
| [BERT pretrained](code/bert_pretrained.ipynb) | BERT-based clinical complaint classification |
| [Data augmentation](code/data_augumentation.ipynb) | Translation-based augmentation and BERT experiments |

Repeated admissions within 14 days and changes in diagnoses are used to help identify *potential* cases for further review; they are **not** automatically verified misdiagnoses. Oversampling must be performed only on training data to avoid leakage.

## Repository structure

- `code/`: original research notebooks
- `demo data/`: example Excel workbooks (provenance and de-identification have not been independently verified)
- `requirements-research.txt`: unpinned import inventory, **not** a validated lockfile

## Setup and limitations

1. Create an isolated Python environment and install the packages in `requirements-research.txt` plus Jupyter Notebook.
2. Open the corresponding notebook; replace local paths such as `G:/...` and `D:/...` with authorized local data paths.
3. Validate column names, label construction, split strategy and dependencies before running cells.
4. The translation experiments additionally require local pretrained MarianMT resources; the BERT notebooks may require downloaded model files.

**No clean-environment reproduction test has been completed.** Notebook inputs, original dependency versions and full dataset schema are not provided. Evaluation code includes ROC-AUC, PR-AUC and additional classification metrics; consult the paper for reported experimental findings.

## Data governance

Original clinical records are not distributed as a complete research dataset. The included example workbooks must **not** be assumed to have been approved for arbitrary redistribution or clinical use. Researchers must check provenance, institutional permissions and de-identification requirements. Never publish patient-identifying data.

## Citation and use

Please cite the paper through the authoritative [publication record](https://link.cnki.net/urlid/10.1478.g2.20260113.1308.002). This repository is **for research only** and is not a validated diagnostic tool.