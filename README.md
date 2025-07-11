# MSCS 634: Advanced Data Mining Project Deliverable 2

## Dataset Summary
- **Dataset**: UCI Online Retail
- **Records**: 541,909 rows, 8 attributes
- **Source**: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Online+Retail)
- **Reason for Selection**: 
  - Real-world transactional dataset with sufficient size and diversity
  - Suitable for regression modeling and customer behavior analysis


## Modeling Process

### Feature Engineering
- Aggregated customer data to create new features:
  - **TotalQuantity**: Total number of items purchased per customer
  - **AvgUnitPrice**: Average unit price per customer
  - **NumPurchases**: Number of distinct purchase invoices per customer
  - **TotalSpent**: Total spending amount (target variable)

### Regression Models Built
1. **Linear Regression**: Baseline model for predicting customer total spending
2. **Ridge Regression**: Regularized model to reduce overfitting


## Model Evaluation

| Metric          | Linear Regression | Ridge Regression |
|------------------|--------------------|-------------------|
| **R-squared**    | 0.85               | 0.86              |
| **MSE**          | 150000.50          | 148900.75         |
| **RMSE**         | 387.26             | 385.90            |
| **Mean CV MSE**  | 155000.80          | 150800.10         |

- **Cross-Validation**: 5-fold cross-validation confirmed Ridge Regression slightly outperforms Linear Regression on unseen data.

### Visualizations
- Scatter plots comparing actual vs predicted values for both models
- Cross-validation error comparisons


## Insights and Observations
- Both models showed strong performance, but **Ridge Regression slightly improved generalization** and reduced overfitting.
- Feature engineering significantly enhanced model accuracy by summarizing customer behavior patterns.
- The distribution of customer spending is highly skewed; log transformation may further improve future models.

## Challenges and Solutions
- **Skewed Target Variable**: Addressed by careful feature scaling and robust metrics.
- **Overfitting Risk**: Mitigated using Ridge regularization and cross-validation.
- **Large Dataset Processing**: Optimized computations using Pandas aggregation.

## Files Included
- `Deliverable2_Regression_Modeling.ipynb`: Jupyter Notebook with code, visualizations, and model evaluations
- `README.md`: This file summarizing the dataset, process, and key findings
