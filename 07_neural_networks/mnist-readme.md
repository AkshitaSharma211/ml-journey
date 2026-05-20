# MNIST - Handwritten Digit Recognition

## What is MNIST?
28×28 pixel images of handwritten digits 0-9.
60,000 training + 10,000 test images.
Hello World of Deep Learning.

## How it works

Image (28×28)
→ Flatten to 784 numbers
→ Layer 1 (128 neurons) learns edges
→ Layer 2 (64 neurons) learns shapes
→ Output (10 neurons) predicts digit

## Key concepts

| Term | Meaning |
|---|---|
| Flatten | 28×28 image → 784 numbers |
| Epoch | one full pass through 60k images |
| Batch | 64 images processed together |
| CrossEntropyLoss | loss for 10 class problem |
| Softmax | converts output to probabilities |
| DataLoader | feeds data in batches automatically |

## Difference from previous models

| Topic | Breast Cancer | MNIST |
|---|---|---|
| Input | 30 numbers | 784 pixels |
| Output | 1 (yes/no) | 10 (digit 0-9) |
| Loss | BCELoss | CrossEntropyLoss |
| Last activation | Sigmoid | Softmax |
| Classes | 2 | 10 |

## What backpropagation does here

Epoch 1  → random weights → ~10% accuracy
Epoch 5  → adjusted weights → ~85% accuracy
Epoch 10 → good weights → ~97% accuracy
Each epoch backprop asks:
"Which weights caused wrong predictions?"
"How much should each weight change?"
Then adjusts all weights slightly

## Results

Dataset  → MNIST 70,000 images
Accuracy → ~97%
Epochs   → 10
Optimizer→ Adam

## What I learned
- Images are just numbers to a neural network
- More layers = learns more complex patterns
- Backprop adjusts weights after every batch
- CrossEntropyLoss for multi-class problems
- DataLoader handles batching automatically
- Can visualize what model predicted vs actual

## Files
- `mnist.ipynb` → full implementation