# [cite_start]🕵️‍♂️ Fraud Detection Machine Learning Model [cite: 27]

## 📌 Project Overview
[cite_start]Fraudulent transactions represent a significant challenge in the financial sector, costing billions of dollars annually[cite: 27]. [cite_start]The primary challenge in building a fraud detection model is the extreme class imbalance (i.e., legitimate transactions overwhelmingly outnumber fraudulent ones)[cite: 28]. [cite_start]This project builds a robust, tree-based machine learning pipeline to accurately identify fraudulent transactions while minimizing false negatives[cite: 29].

## 🎯 Key Highlights & Methodology
[cite_start]This project adheres to industry best practices for highly imbalanced datasets[cite: 30]:
* [cite_start]**Handling Class Imbalance (SMOTE)**: Utilized the Synthetic Minority Over-sampling Technique (SMOTE) to generate synthetic fraudulent examples, allowing the model to learn the minority class effectively[cite: 30].
* [cite_start]**Strict Prevention of Data Leakage**: Ensured that SMOTE was applied only to the training dataset after the train-test split, preserving the integrity of the test set (X_test_orig) for real-world evaluation[cite: 31].
* [cite_start]**Business-Centric Evaluation Metrics**: Accuracy is a misleading metric in fraud detection[cite: 32]. [cite_start]This project evaluates model performance using Recall , F1-Score , and ROC-AUC , prioritizing the capture of actual fraud cases[cite: 33].
* [cite_start]**Advanced Ensemble Modeling**: Leveraged state-of-the-art gradient boosting frameworks, including XGBoost and LightGBM , optimized for tabular data[cite: 34].

## [cite_start]🛠️ Tech Stack [cite: 35]
* **Language**: Python
* **Data Processing**: pandas, numpy
* **Machine Learning**: scikit-learn, xgboost, lightgbm, imblearn (SMOTE), torch
* **Data Visualization**: matplotlib, seaborn

## 📊 Exploratory Data Analysis (EDA)
[cite_start]Comprehensive EDA was conducted before modeling to understand feature distributions and relationships[cite: 35]:
* [cite_start]**count_comparison_of_fraud_nonfraud.png**: Visualizes the severe class imbalance in the raw dataset[cite: 35].
* [cite_start]**heatmap.png**: Correlation matrix to identify multicollinearity and the most predictive features[cite: 36].
* [cite_start]**spread_of_datapoints.png**: Scatter distribution showing how fraudulent transactions deviate from the normal transaction cluster[cite: 37].
* [cite_start]**ROC_Curves.png**: Compares the True Positive Rate vs. False Positive Rate across different models[cite: 38].

## 🚀 Installation & Usage
1. [cite_start]Clone the repository[cite: 39].
2. Install dependencies. [cite_start]It is recommended to use a virtual environment[cite: 39, 49].
3. [cite_start]Run the Jupyter Notebook[cite: 40, 50].

## [cite_start]📁 Repository Structure [cite: 40, 50]

## 📈 Results & Conclusion
[cite_start]*(Note: You can update these bullet points with your actual final scores from the notebook)* [cite: 40, 50]
* [cite_start]LightGBM / XGBoost demonstrated the strongest performance on the test set[cite: 40, 50].
* Achieved an impressive Recall Score of 0.XX, ensuring the vast majority of fraudulent transactions are caught[cite: 41, 51].
* [cite_start]Maintained a strong ROC-AUC Score of 0.XX, proving the model's ability to distinguish between normal and fraudulent behavior effectively[cite: 42, 52].

## 🤝 Contributing
Contributions, issues, and feature requests are welcome! [cite_start]Feel free to check the issues page[cite: 43, 53]. [cite_start]If you find this repository helpful, please consider giving it a ⭐![cite: 44, 54].
