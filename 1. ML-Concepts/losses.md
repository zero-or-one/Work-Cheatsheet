# Loss Functions

Loss functions measure the difference between predicted and actual values, guiding model optimization during training.

## 1. Mean Squared Error (MSE)

### Formula
```
L = (1/n) * Σ(y_i - ŷ_i)²
```

### Properties
- **Use Case:** Regression
- **Range:** [0, ∞)
- **Pros:** Penalizes large errors heavily, differentiable
- **Cons:** Sensitive to outliers

---

## 2. Mean Absolute Error (MAE)

### Formula
```
L = (1/n) * Σ|y_i - ŷ_i|
```

### Properties
- **Use Case:** Regression
- **Range:** [0, ∞)
- **Pros:** Robust to outliers
- **Cons:** Not differentiable at zero, slower convergence

---

## 3. Huber Loss

### Formula
```
L = { ½(y - ŷ)²           if |y - ŷ| ≤ δ
    { δ|y - ŷ| - ½δ²      otherwise
```

### Properties
- **Use Case:** Regression
- **Pros:** Combines MSE and MAE benefits, robust to outliers
- **Cons:** Requires tuning δ parameter

---

## 4. Binary Cross-Entropy (BCE)

### Formula
```
L = -(1/n) * Σ[y_i * log(ŷ_i) + (1 - y_i) * log(1 - ŷ_i)]
```

### Properties
- **Use Case:** Binary classification
- **Range:** [0, ∞)
- **Pros:** Probabilistic interpretation, smooth gradients
- **Cons:** Requires sigmoid activation

---

## 5. Categorical Cross-Entropy (CCE)

### Formula
```
L = -(1/n) * Σ Σ y_ij * log(ŷ_ij)
```

### Properties
- **Use Case:** Multi-class classification (one-hot labels)
- **Range:** [0, ∞)
- **Pros:** Works with softmax, penalizes confident wrong predictions
- **Cons:** Requires one-hot encoding

---

## 6. Sparse Categorical Cross-Entropy

### Formula
```
L = -(1/n) * Σ log(ŷ_i[c_i])  where c_i is the true class index
```

### Properties
- **Use Case:** Multi-class classification (integer labels)
- **Range:** [0, ∞)
- **Pros:** Memory efficient, no one-hot encoding needed
- **Cons:** Same as CCE

---

## 7. Focal Loss

### Formula
```
L = -(1/n) * Σ α(1 - ŷ_i)^γ * log(ŷ_i)
```

### Properties
- **Use Case:** Imbalanced classification
- **Pros:** Focuses on hard examples, reduces easy example weight
- **Cons:** Requires tuning α and γ hyperparameters

---

## 8. Hinge Loss

### Formula
```
L = (1/n) * Σ max(0, 1 - y_i * ŷ_i)  where y ∈ {-1, 1}
```

### Properties
- **Use Case:** SVM, binary classification
- **Range:** [0, ∞)
- **Pros:** Margin-based, robust
- **Cons:** Not differentiable at margin boundary

---

## 9. KL Divergence (Kullback-Leibler)

### Formula
```
L = Σ P(x) * log(P(x) / Q(x))
```

### Properties
- **Use Case:** Probability distribution comparison, VAEs
- **Range:** [0, ∞)
- **Pros:** Measures distribution similarity
- **Cons:** Not symmetric, undefined when Q(x) = 0

---

## 10. Contrastive Loss

### Formula
```
L = (1/2n) * Σ[y * d² + (1 - y) * max(0, m - d)²]
```

### Properties
- **Use Case:** Siamese networks, metric learning
- **Pros:** Learns embeddings, pulls similar pairs together
- **Cons:** Requires paired data, margin m tuning

---

## Summary Table

| Loss Function          | Task Type           | Robust to Outliers | Key Feature              |
| ---------------------- | ------------------- | ------------------ | ------------------------ |
| MSE                    | Regression          | No                 | Penalizes large errors   |
| MAE                    | Regression          | Yes                | Linear penalty           |
| Huber                  | Regression          | Yes                | Hybrid MSE/MAE           |
| Binary Cross-Entropy   | Binary Class        | No                 | Probabilistic            |
| Categorical Cross-Ent. | Multi-class         | No                 | One-hot labels           |
| Sparse Cat. Cross-Ent. | Multi-class         | No                 | Integer labels           |
| Focal Loss             | Imbalanced Class    | No                 | Focuses on hard examples |
| Hinge Loss             | Binary Class (SVM)  | Yes                | Margin-based             |
| KL Divergence          | Distribution Match  | No                 | Asymmetric divergence    |
| Contrastive Loss       | Metric Learning     | No                 | Similarity learning      |
