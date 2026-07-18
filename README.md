# 🕵️‍♂️ Fraud Detection Machine Learning Model

## 📌 Project Overview

Fraudulent transactions represent a significant challenge in the financial sector, costing billions of dollars annually. The primary challenge in building a fraud detection model is the extreme class imbalance, where legitimate transactions overwhelmingly outnumber fraudulent ones.

This project builds a robust tree-based machine learning pipeline to accurately identify fraudulent transactions while minimizing false negatives.

---

## 🎯 Key Highlights & Methodology

This project follows industry best practices for handling highly imbalanced datasets.

- ✅ **Handling Class Imbalance (SMOTE)**
  - Used the Synthetic Minority Over-sampling Technique (SMOTE) to generate synthetic fraudulent samples, enabling the model to learn the minority class effectively.

- ✅ **Prevention of Data Leakage**
  - Applied SMOTE **only on the training dataset** after the train-test split to ensure unbiased evaluation on the original test set.

- ✅ **Business-Centric Evaluation Metrics**
  - Accuracy alone is misleading for fraud detection.
  - Evaluated models using:
    - Recall Score
    - Precision
    - F1-Score
    - ROC-AUC Score

- ✅ **Advanced Ensemble Models**
  - Trained multiple machine learning models including:
    - XGBoost
    - LightGBM
    - Random Forest
    - Decision Tree

---

## 🛠️ Tech Stack

| Category | Technologies |
|----------|--------------|
| Language | Python |
| Data Processing | Pandas, NumPy |
| Machine Learning | Scikit-learn, XGBoost, LightGBM, Imbalanced-Learn (SMOTE), PyTorch |
| Visualization | Matplotlib, Seaborn |
| Development | Jupyter Notebook |

---

## 📊 Exploratory Data Analysis (EDA)

Comprehensive exploratory data analysis was performed before model training.

| Visualization | Description |
|--------------|-------------|
| `count_comparison_of_fraud_nonfraud.png` | Shows the severe class imbalance in the dataset |
| `heatmap.png` | Displays feature correlation matrix |
| `spread_of_datapoints.png` | Visualizes the distribution of fraudulent and legitimate transactions |
| `ROC_Curves.png` | Compares ROC curves of different machine learning models |

---

## 🚀 Installation & Usage

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/rajsinghal830/Fraud-Detection-Model.git
cd Fraud-Detection-Model
```

---

### 2️⃣ Install Dependencies

It is recommended to create a virtual environment before installing packages.

```bash
pip install -r requirements.txt
```

---

### 3️⃣ Launch Jupyter Notebook

```bash
jupyter notebook fraud_detection.ipynb
```

---

## 📁 Repository Structure

```text
Fraud-Detection-Model/
│
├── dataset/
│   └── dataset.csv
│
├── images/
│   ├── count_comparison_of_fraud_nonfraud.png
│   ├── heatmap.png
│   ├── ROC_Curves.png
│   └── spread_of_datapoints.png
│
├── model/
│   ├── fraud_detection.ipynb
│   └── trained_model.pkl
│
├── requirements.txt
└── README.md
```

---

## 🤖 Machine Learning Workflow

1. Data Collection
2. Data Cleaning
3. Exploratory Data Analysis (EDA)
4. Feature Engineering
5. Train-Test Split
6. SMOTE Oversampling
7. Model Training
8. Hyperparameter Tuning
9. Model Evaluation
10. Fraud Prediction

---

## 📈 Model Evaluation Metrics

The models were evaluated using:

- 📌 Accuracy
- 📌 Precision
- 📌 Recall
- 📌 F1-Score
- 📌 ROC-AUC Score
- 📌 Confusion Matrix

---

### Best Performing Model

🏆 **LightGBM / XGBoost** achieved the highest overall performance.

- High Recall Score for detecting fraudulent transactions.
- Strong ROC-AUC demonstrating excellent classification capability.
- Low False Negative Rate, making the model suitable for real-world fraud detection.

---

## 💡 Future Improvements

- Deep Learning-based Fraud Detection
- Real-Time Fraud Detection API
- Explainable AI using SHAP/LIME
- Hyperparameter Optimization using Optuna
- Deployment with FastAPI & Docker
- Streamlit Dashboard for Live Predictions

---

## 👨‍💻 Author

**Raj Singhal**

- 🎓 B.Tech CSE, IIIT Kota
- 💼 Machine Learning & Full Stack Developer
- 🔗 GitHub: https://github.com/rajsinghal830

---

## ⭐ Support

If you found this project useful, please consider giving it a ⭐ on GitHub!
