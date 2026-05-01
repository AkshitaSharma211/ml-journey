# Random Forest

## What is Random Forest?
Multiple decision trees working together to give better predictions.
One tree can be wrong — 100 trees voting together are much harder to fool.

Tree 1 → Malignant
Tree 2 → Malignant
Tree 3 → Benign
Tree 4 → Malignant
Tree 5 → Malignant
→ Final vote: Malignant (4/5)

## How it works
Take random samples of data (bagging)
Build many decision trees on each sample
Each tree also picks random features at each split
All trees vote → majority wins (classification)
→ average (regression)

## Why better than single Decision Tree?
Single Decision Tree → overfits, memorizes training data
Random Forest        → many trees, each sees different data
mistakes cancel out → better generalization

## Key concepts

| Term | Meaning |
|---|---|
| Bagging | each tree trains on random sample of data |
| Random features | each split considers random subset of features |
| Ensemble | combining many models for better performance |
| n_estimators | number of trees in the forest |
| Feature importance | how much each feature contributes to predictions |
| OOB score | out of bag score, built in cross validation |

## Key parameters
| Parameter | Effect |
|---|---|
| n_estimators | more trees = better but slower (start with 100) |
| max_depth | controls each tree depth, None = fully grown |
| min_samples_split | min samples to split a node |
| max_features | features considered at each split (sqrt is default) |
| n_jobs=-1 | use all CPU cores, runs faster |
| random_state | reproducibility |

## Results on Breast Cancer Dataset
| Model | Accuracy | CV Mean |
|---|---|---|
| Base Random Forest | 95.6% | 95.3% |
| Tuned Random Forest | 95.6% | 96.0% |

## Feature Importance findings
worst area           → 14.0%  (tumor size at worst point)
worst concave points → 12.9%  (shape irregularity)
worst radius         → 9.7%   (size measurement)

Key insight: "worst" features matter more than "mean" features
Cancer identified by worst characteristics, not average

## GridSearchCV results
Best params:
n_estimators     = 200
max_depth        = None
min_samples_split= 2
max_features     = sqrt
Tried 72 combinations × 5 folds = 360 fits
CV improved from 95.3% to 96.0%

## When to use Random Forest
- Classification and regression both
- When single decision tree overfits
- Need feature importance
- Large datasets with many features
- When you need reliable, production ready model

## Limitations
- Slower than single decision tree
- Less interpretable than single tree
- High memory usage with many trees
- Improved by → XGBoost, Gradient Boosting

## What I learned
- More trees = more stable predictions
- CV score more important than just accuracy
- Feature importance reveals real world insights
- GridSearchCV automates finding best parameters
- stratify=y important for imbalanced datasets
- Tuning improved CV from 95.3% to 96%

## Files
- `random_forest.ipynb` → full implementation on breast cancer dataset