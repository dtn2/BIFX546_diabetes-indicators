# Diabetes Prediction Using Health Indicators

### BIFX-546: Machine Learning for Bioinformatics — Spring 2026

**Student:**  
Duong Nguyen (dtn2@hood.edu)

**Instructor:** 
Dr. Sarangan (Ravi) Ravichandran


---



---

# 🎯 Project Goal

The goal of this project is to develop interpretable machine learning models for predicting diabetes status using health indicator data from the CDC Behavioral Risk Factor Surveillance System (BRFSS). The project also aims to identify the strongest risk factors associated with diabetes and evaluate how different preprocessing and imbalance-handling techniques affect predictive performance.

---

# 📊 Dataset

| Field | Details |
|---|---|
| **Name** | Diabetes Health Indicators Dataset |
| **Source** | Kaggle / CDC BRFSS 2015 |
| **URL** | https://www.kaggle.com/datasets/alexteboul/diabetes-health-indicators-dataset |
| **Size** | 253,680 observations with 21 feature variables |
| **Target Variable** | `Diabetes_binary` (0 = No Diabetes, 1 = Diabetes/Prediabetes) |

The dataset contains demographic, lifestyle, and clinical health indicators related to diabetes risk.

---

# 🧠 Techniques Used

| Phase | Technique |
|---|---|
| EDA | Summary statistics and class distribution analysis |
| EDA | Histograms, boxplots, countplots, correlation heatmap |
| Data Cleaning | Duplicate removal |
| Data Cleaning | BMI outlier removal using IQR |
| Modeling | Logistic Regression |
| Modeling | Random Forest |
| Imbalance Handling | Class weighting |
| Imbalance Handling | SMOTE oversampling |
| Imbalance Handling | Random undersampling |
| Feature Selection | Reduced-feature logistic regression |
| Evaluation | Accuracy, Precision, Recall, F1-score |
| Evaluation | ROC-AUC, PR-AUC, Confusion Matrix |

---

# 📁 Repository Structure

```text
BIFX546_diabetes-indicators/
├── data/
│   ├── diabetes_012_health_indicators_BRFSS2015.csv
│   ├── diabetes_binary_5050split_health_indicators_BRFSS2015.csv
│   └── diabetes_binary_health_indicators_BRFSS2015.csv
├── notebooks/
│   └── EDA_diabetes_indicators.ipynb
├── src/
│   └── .gitkeep
├── EDA_diabetes_indicators_Final.ipynb
├── Project Proposal.docx
├── LICENSE
└── README.md
```

---

# ⚙️ How to Run

## Option 1 — Google Colab

1. Open Google Colab  
2. Upload or open the notebook from GitHub  
3. Install required packages:

```python
!pip install -r requirements.txt
```

4. Run all notebook cells

---

## Option 2 — Local Jupyter Notebook

```bash
# Clone repository
git clone https://github.com/dtn2/diabetes-prediction.git

cd diabetes-prediction

# Install dependencies
pip install -r requirements.txt

# Launch notebook
jupyter notebook
```

---

# 📈 Key Results

| Model | Accuracy | Diabetes Recall | ROC-AUC |
|---|---|---|---|
| Logistic Regression | 73% | 0.78 | 0.827 |
| Random Forest | 86% | 0.16 | 0.799 |
| Logistic Regression + SMOTE | 72% | 0.74 | 0.802 |
| Reduced Feature Logistic Regression | 72% | 0.76 | 0.813 |

### Main Findings

- General health, BMI, high blood pressure, age, and mobility issues showed the strongest associations with diabetes
- Logistic Regression outperformed Random Forest for detecting diabetes cases
- Random Forest achieved higher accuracy but missed many diabetes cases due to class imbalance
- Duplicate removal and BMI outlier removal had minimal impact on performance
- SMOTE and undersampling produced only small performance changes
- A reduced-feature model achieved similar performance using only 6 variables

---

# 📝 Conclusion

Logistic Regression provided the most effective and interpretable model for diabetes prediction in this imbalanced healthcare dataset. Although Random Forest achieved higher overall accuracy, Logistic Regression achieved substantially higher recall for diabetes cases, making it more clinically useful for screening purposes. The results also demonstrated that a simplified model using only a few key health indicators can still effectively predict diabetes risk.

---

# 📦 Dependencies

Core Python packages:

```text
pandas
numpy
matplotlib
seaborn
scikit-learn
imbalanced-learn
jupyter
```

---

# 📜 References

1. CDC Behavioral Risk Factor Surveillance System (BRFSS)  
   https://www.cdc.gov/brfss/

2. Kaggle Diabetes Health Indicators Dataset  
   https://www.kaggle.com/datasets/alexteboul/diabetes-health-indicators-dataset

---

*BIFX-546 · Hood College · Spring 2026*
