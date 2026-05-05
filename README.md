# NetSieveX.io — ML Models

Machine learning pipeline for IoT network intrusion detection. 
Trains and evaluates classification models on the RT-IoT2022 dataset 
to detect four types of network traffic: Normal, NMAP, ARP Poisoning, 
and DOS SYN Hping.

## Related Repositories

- **Frontend:** [WebSait](https://github.com/ingenriquecardosoalfonso/WebSait)
- **Backend API:** [NetSieveXAPI](https://github.com/ingenriquecardosoalfonso/NetSieveXAPI)

## Dataset

**RT-IoT2022** — UCI Machine Learning Repository  
- Original: 123,117 rows x 85 features  
- After preprocessing: 37,264 rows x 17 features  
- Source: https://doi.org/10.24432/C5P338

## Traffic Classes

| Class | Risk Level |
|---|---|
| Normal | LOW |
| NMAP | MEDIUM |
| ARP_poisoning | HIGH |
| DOS_SYN_Hping | CRITICAL |

## Pipeline
Feature Selection
Variance Threshold → Pearson Correlation → Mutual Information
→ 17 final features selected from 85
Train/Test Split
Stratified 80/20 split (random_state=42)
Models Trained
Logistic Regression, Decision Tree, Random Forest, KNN, SVM

## Results

| Model | Accuracy | ROC-AUC | Hamming Loss |
|---|---|---|---|
| Random Forest | 99.37% | 0.9999 | 0.0063 |
| Decision Tree | 99.19% | 0.9945 | 0.0081 |
| KNN | 98.91% | 0.9984 | 0.0109 |
| SVM | 97.99% | 0.9955 | 0.0201 |
| Logistic Regression | 97.11% | 0.9920 | 0.0288 |

## Explainability

SHAP (SHapley Additive exPlanations) values are computed for all 
three selected models to provide feature-level explanations for 
each prediction.

## Getting Started

```bash
pip install -r requirements.txt
jupyter notebook
```

Open the notebook and run all cells to reproduce the full pipeline.

## References

- Lundberg, S. M., & Lee, S. I. (2017). A unified approach to 
  interpreting model predictions. NeurIPS, 30.
- Sharmila, B. S., & Nagapadma, R. (2023). RT-IoT2022 [Dataset]. 
  UCI Machine Learning Repository. https://doi.org/10.24432/C5P338

## Team

- Barbara Alfaro
- Ludwig Cardoso
- Nehal Gadhavi

SAIT — Integrated Artificial Intelligence Post-Diploma Certificate, 2026
