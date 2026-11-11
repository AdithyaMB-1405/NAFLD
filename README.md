# NAFLD Prediction Using Machine Learning

## Overview

This project explores the use of machine learning techniques to predict Non-Alcoholic Fatty Liver Disease (NAFLD) using clinical and biochemical data.

Multiple classification algorithms are evaluated and compared. Feature selection and threshold tuning are then applied to selected models to study their predictive performance.

## Project Workflow

1. **Data preprocessing** – Filter the dataset based on alcohol consumption criteria and handle missing values in essential clinical variables.
2. **Feature engineering** – Generate additional metabolic indicators, including TyG, TG/HDL, TyG-BMI, TyG-WC, and METS-IR.
3. **Model development** – Train and evaluate multiple machine learning classification algorithms.
4. **Model comparison** – Compare models using metrics such as precision, recall, F1-score, F2-score, ROC-AUC, and PR-AUC.
5. **Class imbalance handling** – Apply SMOTE-NC to the training data.
6. **Feature selection** – Use SHAP-based feature importance to identify relevant features for selected models.
7. **Threshold tuning** – Evaluate classification thresholds to study the precision-recall trade-off.

## Models Evaluated

The project evaluates the following classification algorithms:

- Logistic Regression
- Support Vector Machine (SVM)
- Random Forest
- Gradient Boosting
- XGBoost
- LightGBM
- CatBoost
- AdaBoost
- K-Nearest Neighbors (KNN)
- Multi-Layer Perceptron (MLP)
- TabNet
- Naive Bayes
- Decision Tree
- Bagging Classifier

## Final Model Results

The following results are from the current notebook run after feature selection and threshold tuning.

| Metric            | Gradient Boosting | LightGBM |
| ----------------- | ----------------: | -------: |
| Accuracy          |            86.73% |   86.83% |
| Precision         |            60.88% |   61.13% |
| Recall            |            68.53% |   68.92% |
| F1-score          |            0.6448 |   0.6479 |
| F2-score          |            0.6685 |   0.6721 |
| ROC-AUC           |            0.9048 |   0.9081 |
| PR-AUC            |            0.6934 |   0.7034 |
| Selected features |                 9 |       12 |

LightGBM achieved slightly higher scores across the reported metrics, while Gradient Boosting used fewer features.

## Project Structure

```text
NAFLD-project/
├── data/
│   └── Data+set+Int+J+Obesity.xlsx
├── notebooks/
│   └── NAFLDcode (1).ipynb
├── outputs/
│   ├── Trained models
│   ├── Evaluation results
│   └── Visualizations
├── .gitignore
└── README.md
```

The `data/` and `outputs/` directories are excluded from Git tracking.

## Getting Started

1. Clone this repository.
2. Install the required Python libraries.
3. Place the dataset inside the `data/` directory.
4. Open the notebook in Jupyter Notebook or VS Code.
5. Select a Python environment with the required dependencies installed.
6. Execute the notebook cells in order.

## Evaluation Note

Threshold tuning and model evaluation should be interpreted with care. The current notebook uses the test set during threshold selection, which can introduce test-set leakage and make the reported performance optimistic. Independent validation is needed for a more reliable estimate of generalization performance.

## Disclaimer

This project is an academic machine learning research project. It is intended for educational and experimental purposes only and is not a clinically validated diagnostic tool. It should not be used to diagnose or make medical decisions.
