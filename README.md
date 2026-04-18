# Global Inflation Rate Prediction
A ML project that predicts country-level inflation rates from the post-covid period.

## Feature Engineering
- Parsed date into year and cyclical month features (month_sin, month_cos) using sine/cosine encoding to capture seasonality.

## Preprocessor
Used ColumnTransformer to handle:
- categorical features: One-Hot Encoding
- numerical features + date features: Standard Scaling

## EDA
- correlation heatmap for all numeric features
- USA yearly average inflation rate plotted over time

## Models 
**Linear Regression:**
- random 80/20 split
- Evaluated with RMSE, MAE, and R^2

**XGBoost Regressor**
- Chronological 80/20 split
- Hyperparameter tuning using RandomizedSearchCV with TimeSeriesSplit (5 folds)
- Tuned parameters: n_estimators, max_depth, learning_rate
- Evaluated with RMSE, MAE, and R^2

## Results
| Metric | Linear Regression | XGBoost |
|---|---|---|
| RMSE | 1.1105 | 0.5010 |
| MAE | 0.8776 | 0.4004 |
| R² | 0.4189 | 0.8816 |

XGBoost outperforms Linear Regression by a huge margin, having a smaller error and explaining 88% of the variance in inflation rates compared to 42% for LR.

  
