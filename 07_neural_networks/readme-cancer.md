# Neural Networks - Breast Cancer Classification

## What is a Neural Network?
Layers of neurons that learn patterns from data.
Each neuron takes inputs, multiplies by weights, 
passes through activation function, sends to next layer.

Input (30 features)
↓
Layer 1 (32 neurons) → ReLU
↓
Layer 2 (16 neurons) → ReLU
↓
Output (1 neuron)    → Sigmoid → 0 or 1

## Key Concepts

| Term | Meaning |
|---|---|
| Neuron | takes input, does calculation, sends output |
| ReLU | if negative → 0, if positive → keep |
| Sigmoid | converts output to 0-1 (probability) |
| Forward pass | data moves input → output |
| Backward pass | error moves output → input (backprop) |
| Loss | how wrong the model is |
| Optimizer | adjusts weights to reduce loss |

## Architecture

Input layer  → 30 features (cancer measurements)
Hidden layer 1 → 32 neurons, ReLU
Hidden layer 2 → 16 neurons, ReLU
Output layer → 1 neuron, Sigmoid

## Training

Epochs    → 100
Optimizer → Adam (lr=0.001)
Loss      → BCELoss (Binary Cross Entropy)

## Results

Dataset  → Breast Cancer (569 samples)
Train    → 455 samples
Test     → 114 samples
Accuracy → ?  (fill yours)

## What I learned
- Neural networks learn by adjusting weights
- ReLU used in hidden layers
- Sigmoid used in output for binary classification
- Loss should decrease over epochs
- Adam optimizer adjusts learning rate automatically
- PyTorch needs data as tensors not numpy arrays

## Files
- `neural_network.ipynb` → full implementation