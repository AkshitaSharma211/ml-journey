# Decision Tree

## What is a Decision Tree?
A decision tree is a flowchart-like model that makes decisions by splitting data based on feature values. Like a game of 20 questions — at each step it asks a yes/no question and splits accordingly.

Is worst area > 800?
├── Yes → Is worst concave points > 0.14?
│         ├── Yes → Malignant
│         └── No  → Benign
└── No  → Benign

## How it works
- Starts at root node with all data
- Splits data based on best feature at each step
- Best split = one that reduces impurity the most
- Continues until leaf nodes (final predictions)

## Key concepts

| Term | Meaning |
|---|---|
| Root node | First split, entire dataset |
| Leaf node | Final prediction, no more splits |
| Depth | How many levels the tree has |
| Gini impurity | How mixed the classes are at a node |
| Information gain | How much a split reduces impurity |
| Pruning | Cutting the tree to prevent overfitting |

## Overfitting problem

No depth limit → tree memorizes training data
Train R² = 1.0, Test R² = 0.65 → classic overfitting

## Solution — Post Pruning with max_depth
```python
# try different depths
for depth in [2, 3, 4, 5, 6, 7, 8, 10]:
    model = DecisionTreeRegressor(max_depth=depth)
    # find depth where test score is highest
```

## Results on California Housing Dataset
| Model | R² Score | RMSE |
|---|---|---|
| Base DT (no limit) | ~0.65 | high |
| Pruned DT (best depth) | ~0.72 | lower |

## Key parameters
| Parameter | Effect |
|---|---|
| max_depth | controls tree size, prevents overfitting |
| min_samples_split | min samples needed to split a node |
| min_samples_leaf | min samples needed at leaf node |
| max_features | number of features to consider at each split |
| criterion | gini or entropy for classification |

## When to use Decision Trees
- Need interpretable/explainable model
- Mix of numerical and categorical features
- Quick baseline before trying complex models
- When you need to visualize the decision process

## Limitations
- Overfits easily without pruning
- Small data changes can completely change the tree
- Not great for regression compared to classification
- Solved by → Random Forest (many trees together)

## What I learned
- Always check train vs test score to detect overfitting
- max_depth is the most important parameter to tune
- Visualizing the tree helps understand what model learned
- Decision Trees are the foundation for Random Forest
- Feature importance shows which features matter most

## Files
- `decision_tree.ipynb` → classification + regression + pruning implementation