# Linear Regression Notes
- 

## What I learned
- Linear regression finds best line by minimizing MSE
- R² tells how much of the pattern model explains
- RMSE tells average prediction error in original units
- Always split train/test before scaling
- fit_transform on train, only transform on test
- Cross validation gives honest performance estimate

## Results on Diabetes Dataset
- Linear Regression  R² = 0.477
- Ridge Regression   R² = 0.477  (no overfitting to fix)
- Lasso Regression   R² = 0.478  (slight improvement)
- Ceiling for linear models on this dataset = ~0.48
- Need tree based models to go higher

## Key mistakes I made 
- Passed feature names list instead of actual dataframe
- Was confused between dataset object and dataframe