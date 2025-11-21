# Supervised_Regression_Models_for_Predicting_Log_Fold_Change_-logFC-_from_DGE_Statistics
Supervised_Regression_Models_for_Predicting_Log_Fold_Change_(logFC)_from_Differential_Gene_Expression_Statistics
# 📉 Comparative Regression Modeling of Differential Gene Expression (DGE) Statistics

This repository hosts a Jupyter Notebook (`Supervised_Regression_Models_for_Predicting_Log_Fold_Change_(logFC)_from_Differential_Gene_Expression_Statistics.ipynb`) that systematically builds and evaluates multiple regression models to **predict the Log Fold Change (`logFC`)** of genes using related statistical metrics.

The goal is to determine the most effective machine learning approach for quantitative gene expression prediction based on differential expression analysis outputs.

---

## 💡 Key Findings and Conclusion

### Top-Performing Model
**Linear Regression** emerged as the top performer, achieving the **highest R² score (0.8230)** and the lowest MSE (0.1380).

### Key Takeaway
The strong performance of the simple **Linear Regression** model suggests a clear, largely linear relationship between the input statistical features (`AveExpr`, `t`, `P.Value`, `adj.P.Val`) and the target variable (`logFC`). The Linear Regression model demonstrated superior explanatory power and predictive accuracy compared to more complex non-linear models like Random Forest and Decision Tree.

| Model | R² Score | MSE | Rank |
| :--- | :--- | :--- | :--- |
| **Linear Regression** | **0.8230** | **0.1380** | **1** |
| Support Vector Regressor (SVR) | 0.7852 | 0.1675 | 2 |
| Random Forest Regressor | 0.7373 | 0.2048 | 3 |
| KNN Regressor | 0.7061 | 0.2292 | 4 |
| Gradient Boosting Regressor | 0.6618 | 0.2636 | 5 |
| Decision Tree Regressor | 0.5836 | 0.3246 | 6 |

---

## 🛠️ Analysis Workflow

### Prerequisites
* Python 3.x
* Jupyter environment (VS Code, JupyterLab, or Google Colab)

### Installation
Install the necessary Python libraries:

```bash
!pip install pandas scikit-learn numpy matplotlib plotly
Data and Features

    Data Source: The analysis uses data loaded from a CSV file (e.g., DEG_GEO ids.csv), representing outputs from a differential gene expression (DGE) analysis.

    Target (y): logFC (Log Fold Change).

    Features (X): AveExpr, t (t-statistic), P.Value, adj.P.Val (adjusted P-Value).

Modeling Steps

    Data Preparation: The dataset is split into 70% training and 30% testing sets (test_size=0.3).

    Initial Benchmark: RandomForestRegressor and LinearRegression are trained and evaluated first.

    Comprehensive Benchmarking: Six different regression algorithms are trained and evaluated on the test data:

        Linear Regression

        Random Forest Regressor

        Decision Tree Regressor

        Gradient Boosting Regressor

        Support Vector Regressor (SVR)

        KNN Regressor

    Evaluation: Performance is measured using Mean Squared Error (MSE) and the R² Score (Coefficient of Determination).

    Visualization:

        A Matplotlib scatter plot compares the True Values vs. Predicted Values for the top two initial models (Linear Regression visually appears superior).

        An interactive Plotly horizontal bar chart is generated to visually rank all six models based on their R² scores, providing precise, hoverable metrics.
