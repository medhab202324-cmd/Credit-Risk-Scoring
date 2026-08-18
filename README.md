# Credit Risk Scoring & Probability of Default Prediction

A machine learning based credit risk scoring system designed to estimate the probability of loan default and transform model predictions into an interpretable credit scorecard.

## Project Overview

This project develops an end-to-end credit risk modelling pipeline using historical loan data.

The system combines feature engineering, Information Value (IV), Weight of Evidence (WoE), Logistic Regression and scorecard methodology to predict borrower default risk and generate interpretable credit scores.

## Objectives

- Predict the Probability of Default (PD)
- Identify important borrower and loan risk factors
- Build an interpretable credit risk scorecard
- Optimize the classification threshold for default detection
- Segment borrowers into different risk bands
- Evaluate model stability using Population Stability Index (PSI)

## Methodology

The project follows the following pipeline:

1. Data Understanding & Quality Assessment
2. Feature Engineering
3. Exploratory Data Analysis
4. Data Preprocessing
5. Logistic Regression PD Modelling
6. Information Value (IV) Feature Selection
7. Weight of Evidence (WoE) Transformation
8. Credit Scorecard Development
9. Population Stability & Model Monitoring
10. Credit Score Generation & Risk Segmentation

## Feature Engineering

50 engineered features were created covering:

- Loan-to-income relationships
- Debt burden
- Installment affordability
- Credit utilization
- Delinquency behaviour
- Credit history
- Account activity
- Income and employment stability
- Loan vintage and issue-date features
- Risk interaction features

## Feature Selection

Information Value (IV) was used to identify predictive variables.

An IV threshold of 0.02 resulted in:

**59 selected features**

These features were subsequently transformed using Weight of Evidence (WoE) for scorecard modelling.

## Model

A Logistic Regression model was trained using WoE-transformed features to estimate Probability of Default.

The model was evaluated using:

- ROC-AUC
- Gini coefficient
- Kolmogorov-Smirnov (KS) statistic
- Brier Score
- Precision
- Recall
- F1 Score

## Model Performance

| Metric | Test Result |
|---|---:|
| ROC-AUC | 0.6916 |
| Gini | 0.3832 |
| KS Statistic | 0.2796 |
| Brier Score | 0.1544 |

## Threshold Optimization

The default classification threshold was optimized using the validation set.

**Optimal threshold: 0.174**

At this threshold, the model achieved:

- Recall: 66.10%
- Precision: 31.52%
- F1 Score: 42.68%

The lower threshold prioritizes identifying potential defaulters, which is important in credit risk applications.

## Credit Scorecard

The predicted Probability of Default was converted into an interpretable credit score.

Test score range:

**455 – 610**

Mean test score:

**536.2**

Higher scores represent lower estimated credit risk.

## Risk Segmentation

Borrowers were divided into four risk bands:

| Risk Band | Actual Default Rate |
|---|---:|
| Very High Risk | 44.88% |
| High Risk | 24.01% |
| Moderate Risk | 8.62% |
| Low Risk | 3.92% |

The observed default rate decreases as the credit score increases, demonstrating that the scorecard provides meaningful risk separation.

## Model Stability

Population Stability Index (PSI) was used to evaluate stability between training and test populations.

**PD PSI: 0.0059**

This indicates a stable overall population distribution.

Feature-level stability analysis identified one feature requiring monitoring:

`combined_utilization_stress`

PSI:

**0.2109**

This feature should therefore be monitored for future population shifts.

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- Jupyter Notebook

## Repository Contents

- `loan.ipynb` — Complete project notebook containing the modelling pipeline and analysis
- `README.md` — Project documentation
- `.gitignore` — Git ignored files configuration

## Dataset

The project uses historical loan-level credit data.

The raw dataset is not included in this repository due to its large size.

## Disclaimer

This project is developed for educational and portfolio purposes and should not be used as a standalone system for real-world lending decisions.

## Author

**Medha Bhandari**
