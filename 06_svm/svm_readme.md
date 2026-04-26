# Support Vector Machine (SVM)

This file contains the implementation of Support Vector Machines for both classification and regression as part of the ML journey.

## Classification (Iris Dataset)

- Dataset loaded using `load_iris`
- Features and target separated into X and y
- Data split into training and testing sets
- Feature scaling applied using `StandardScaler`
- Model trained using `SVC` with RBF kernel
- Predictions made on test data

### Evaluation
- Accuracy score
- Classification report (precision, recall, F1-score)
- Confusion matrix
- Cross-validation (5-fold)

## Regression (Diabetes Dataset)

- Dataset loaded using `load_diabetes`
- Data split into training and testing sets
- Feature scaling applied
- Model trained using `SVR` with RBF kernel

### Evaluation
- R² score
- Root Mean Squared Error (RMSE)

## Kernel Comparison

- Compared SVM performance using:
  - Linear kernel
  - RBF kernel
  - Polynomial kernel
- Accuracy calculated for each kernel
- Results stored and visualized

## Hyperparameter Tuning

- Used `GridSearchCV` to find best parameters
- Parameters tuned:
  - C (regularization)
  - gamma (kernel coefficient)
  - kernel type
- Best model selected and evaluated

## Key Points

- Feature scaling is important for SVM
- RBF kernel works well for non-linear data
- Cross-validation improves reliability
- GridSearch helps in optimizing performance