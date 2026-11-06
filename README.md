# Week 4: Predictive Modeling and Optimization in Logistics Systems

Yuva Intern data science task. A model predicts shipment delivery time, and the predictions are then used to optimise transport mode choice and carrier allocation.

## Files
| File | Description |
|------|-------------|
| `Week4_Predictive_Modeling_Optimization_Report.docx` | Full report |
| `predictive_optimization.py` | Python script: data, models, evaluation, optimization |
| `logistics_week4_dataset.csv` | Hypothetical dataset (6,000 shipments) |
| `results.json` | Metrics produced by the script |
| `charts/` | The 6 charts used in the report |

## Approach
1. **Problem:** regression, predict `delivery_days`
2. **Preparation:** train/test split (80/20), one-hot encoding, scikit-learn pipelines
3. **Model selection:** Linear Regression, Decision Tree, Random Forest, Gradient Boosting compared with 5-fold cross-validation
4. **Tuning:** RandomizedSearchCV on Gradient Boosting
5. **Evaluation:** MAE, RMSE and R-squared on the test set
6. **Optimization A:** switch air shipments to cheaper modes when predicted time stays inside the promise (cost minimization)
7. **Optimization B:** carrier allocation with linear programming (max 45% per carrier)

## Key results (hypothetical data)
- Tuned Gradient Boosting: MAE 0.70 days, RMSE 0.93 days, R-squared 0.49 (naive baseline MAE 1.01 days)
- Mode optimization: about 34% lower predicted cost, on-time rate unchanged
- Carrier allocation: average delivery time 3.33 to 3.18 days

## Run
```bash
pip install pandas numpy scikit-learn scipy matplotlib seaborn
python predictive_optimization.py
```

Note: data is hypothetical and generated for learning purposes.
