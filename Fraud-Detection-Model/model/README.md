# Credit Card Fraud Detection

## Introduction
This project aims to build a robust and accurate system for detecting fraudulent credit card transactions. By analyzing historical transaction data, we can identify patterns and anomalies that indicate fraudulent activity, helping to minimize financial losses for both individuals and institutions.

## Data
The dataset used in this project is the "Credit Card Fraud Detection" dataset obtained from Kaggle. It contains anonymized credit card transactions, with features V1-V28 being the result of a PCA transformation. The dataset also includes 'Time', 'Amount', and the 'Class' variable indicating whether the transaction is fraudulent (1) or not (0). The data has been loaded into a pandas DataFrame named `df`.

## Methodology
The methodology involves data cleaning, exploratory data analysis, handling of imbalanced data, dimensionality reduction, and training various classifiers.

### Data Cleaning and Preprocessing
The initial data cleaning involved checking for missing values, and it was found that there were no null values in the dataset.
To handle the varying scales of the 'Amount' and 'Time' features compared to the PCA-transformed features (V1-V28), RobustScaler was applied to standardize these columns. After scaling, the original 'Time' and 'Amount' columns were dropped from the dataset.

### Handling Imbalanced Data
The dataset is highly imbalanced, with a significantly smaller number of fraudulent transactions (minority class) compared to non-fraudulent transactions (majority class). To address this, two techniques were employed:

1.  **Random Under-Sampling:** This technique balances the dataset by randomly removing instances from the majority class. A balanced dataset (`balanced_df`) was created using this method, resulting in an equal number of fraudulent and non-fraudulent transactions.

2.  **SMOTE (Synthetic Minority Over-sampling Technique):** SMOTE is an over-sampling technique that generates synthetic instances for the minority class. This was applied to the original training data (`X_train_orig`, `y_train_orig`) to create a balanced training set (`X_train_smote`, `y_train_smote`) without removing data from the majority class.

The rationale behind using these techniques is to prevent machine learning models from being biased towards the majority class, which can lead to poor performance in detecting the rare, but critical, fraudulent transactions. By balancing the dataset, we aim to improve the models' ability to learn the patterns associated with the minority class.

### Exploratory Data Analysis (EDA)
Exploratory Data Analysis was conducted to understand the characteristics of the dataset. This included:
- Checking the distribution of the 'Class' variable, which clearly showed the severe imbalance between non-fraudulent and fraudulent transactions.
- Visualizing the correlation matrix of the features using heatmaps. This helped to identify potential relationships between features and the target variable, both in the original and the under-sampled datasets.

### Model Training and Evaluation
Several classifiers were trained and evaluated for this fraud detection task, including Logistic Regression, K-Nearest Neighbors, Random Forest, Support Vector Classifier, Decision Tree, Gaussian Naive Bayes, and XGBoost.

Initially, these classifiers were trained on the balanced dataset created using Random Under-Sampling. Cross-validation was performed to assess their initial performance and identify potential overfitting.

Subsequently, the training data was resampled using SMOTE, and a subset of classifiers (Logistic Regression, K-Nearest Neighbors, Random Forest, and XGBoost) were trained on this SMOTE-resampled data. Cross-validation was also performed on the SMOTE-resampled training data.

## Results
The models trained on the SMOTE-resampled data were evaluated on the original, unseen test set to assess their performance on imbalanced data. The following metrics were obtained:

| Classifier            | Precision | Recall  | F1-Score | ROC AUC |
|-----------------------|-----------|---------|----------|---------|
| Logistic Regression   | 0.06      | 0.93    | 0.11     | 0.98    |
| KNearest              | 0.48      | 0.88    | 0.62     | 0.94    |
| RandomForest          | 0.91      | 0.84    | 0.87     | 0.99    |
| XGBoost               | 0.78      | 0.85    | 0.81     | 0.99    |

**Interpretation of Results:**

*   **Logistic Regression:** While achieving high recall (identifying most fraud cases), its very low precision indicates a high rate of false positives, making it less practical for this application.
*   **KNearest:** Shows a better balance than Logistic Regression, with decent recall and improved precision.
*   **RandomForest:** Demonstrates a strong performance with a high precision and good recall, resulting in a high F1-score. This suggests it effectively identifies fraud cases while keeping false positives relatively low.
*   **XGBoost:** Also performs well, with a good balance between precision and recall, and a high F1-score.

Based on these evaluations, **RandomForest** and **XGBoost** appear to be the most effective models for this credit card fraud detection task, offering the best trade-off between identifying fraudulent transactions and minimizing false alarms on unseen, imbalanced data.

## Conclusion
This project demonstrated an end-to-end approach to credit card fraud detection on an imbalanced dataset. Key takeaways include:

*   The importance of handling imbalanced data using techniques like Random Under-Sampling and SMOTE to prevent model bias and improve the detection of the minority class (fraud).
*   The effectiveness of SMOTE in generating synthetic samples to balance the training data.
*   The need to evaluate model performance on the original, imbalanced test set to get a realistic assessment of how well the models generalize to unseen data.
*   Among the evaluated classifiers, **RandomForest** and **XGBoost** showed the most promising results in terms of balancing precision and recall, making them suitable choices for this fraud detection task. Further tuning and exploration of these models could potentially lead to even better performance.
