# Credit_Card_Fraud_Detection
#Project Overview

This project focuses on identifying fraudulent credit card transactions using a dataset of European cardholders from September 2013. The primary challenge of this project is the extreme class imbalance: out of 284,807 transactions, only 492 are fraudulent (0.172%).

The goal was to build a robust predictive model that can accurately distinguish between legitimate and fraudulent activities, minimizing false negatives to ensure security while maintaining a high precision to avoid customer inconvenience.

 #Description of Dataset
The dataset contains transactions that occurred over two days. Due to confidentiality reasons, the original features were transformed using Principal Component Analysis (PCA).

Features V1-V28: Principal components obtained via PCA.

Time: Seconds elapsed between each transaction and the first transaction in the dataset.

Amount: Transaction amount, which could potentially be used for cost-sensitive learning.

Class: The target variable (1 for fraud, 0 for legitimate).

#Technical Workflow
The notebook follows a standard data science pipeline:

1. Data Exploration & Cleaning
Verified that the dataset contains no missing values.

Analyzed the distribution of transactions over time to identify patterns in legitimate vs. fraudulent activity.

Conducted a correlation analysis to understand the relationships between the PCA-transformed features and the target Class.

2. Handling Imbalance
Recognizing the 0.172% fraud rate, I evaluated models based on Area Under the ROC Curve (AUC) rather than simple accuracy, which would be misleading in such an unbalanced scenario.

3. Predictive Modeling
I implemented and compared several advanced ensemble methods:

Random Forest: Used as a baseline for robust classification.

AdaBoost & XGBoost: Implemented to leverage gradient boosting techniques.

LightGBM: Utilized for its efficiency and high performance with large datasets.

CatBoost: Tested to see how it handled the numerical features compared to LightGBM.

#Key Results
Random Forest: Achieved a best validation AUC score of 0.984 and a test AUC of 0.974.

LightGBM: Performance remained strong with a validation AUC of 0.974 and a test set score of 0.946.

Cross-Validation: Using 5-fold cross-validation, the model stability was confirmed with a test prediction AUC of 0.93.

#Conclusion
The experiments demonstrate that ensemble methods like Random Forest and LightGBM are highly effective at detecting fraud even in highly skewed datasets. While the models achieved high AUC scores, further tuning for precision-recall balance is recommended for actual production deployment to ensure a seamless user experience for cardholders.
