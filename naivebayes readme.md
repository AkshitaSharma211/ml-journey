# Naive Bayes

## What is Naive Bayes?
A probability based algorithm that predicts based on how likely 
something is given past data. Based on Bayes theorem.

P(A|B) = P(B|A) × P(A) / P(B)
In simple words:
P(malignant | features) = how likely is malignant given these measurements

## Why "Naive"?
Assumes all features are independent of each other.
In reality they aren't — but it still works surprisingly well.


Naive assumption:
worst area and worst radius are independent → not true in reality
But model still gives 92.9% accuracy → naive assumption works!

## Types of Naive Bayes

| Type | Use case |
|---|---|
| Gaussian NB | continuous features (most common) |
| Bernoulli NB | binary features (0 or 1) |
| Multinomial NB | count data (text classification) |

## How it works


Calculate probability of each class
For each feature, calculate probability given each class
Multiply all probabilities together
Pick class with highest probability


## Results on Breast Cancer Dataset
Gaussian NB   → Accuracy=92.9%  CV=93.1%
Bernoulli NB  → Accuracy=92.9%  CV=93.1%
Random Forest → Accuracy=95.6%  CV=95.3%
Naive Bayes only 2.7% behind Random Forest
but trains in milliseconds vs seconds

## Key parameters
| Parameter | Effect |
|---|---|
| var_smoothing | stability when probability is 0 (Gaussian) |
| alpha | smoothing for zero probabilities (Bernoulli) |
| binarize | threshold for converting to binary (Bernoulli) |

## When to use Naive Bayes
- Text classification (spam detection)
- When speed matters more than accuracy
- Small datasets
- Real time predictions
- Good baseline model always

## Limitations
- Naive assumption rarely true in real world
- Not great with correlated features
- Can't capture complex relationships
- Improved by → Random Forest, SVM

## Naive Bayes vs Random Forest
Naive Bayes    → fast, simple, 92.9% accuracy
Random Forest  → slower, complex, 95.6% accuracy
Use Naive Bayes when → speed critical, text data, baseline
Use Random Forest when → accuracy critical, tabular data

## What I learned
- Probability based models can be very powerful
- Naive assumption works despite being wrong
- Gaussian NB and Bernoulli NB gave same results here
- Speed vs accuracy tradeoff is real
- Always compare with stronger models like Random Forest
- Good baseline before trying complex models

## Files
- `naive_bayes.ipynb` → Gaussian NB, Bernoulli NB, comparison with Random Forest
