# Activation Functions

Activation functions introduce non-linearity into neural networks, enabling them to learn complex patterns.

## 1. ReLU (Rectified Linear Unit)

### Formula
```
f(x) = max(0, x)
```

### Properties
- **Range:** [0, ∞)
- **Derivative:** 1 if x > 0, else 0
- **Pros:** Fast computation, reduces vanishing gradient
- **Cons:** Dead neurons (outputs 0 for negative inputs)

---

## 2. Leaky ReLU

### Formula
```
f(x) = max(αx, x)  where α ≈ 0.01
```

### Properties
- **Range:** (-∞, ∞)
- **Derivative:** 1 if x > 0, else α
- **Pros:** Prevents dead neurons
- **Cons:** Inconsistent predictions for negative values

---

## 3. Sigmoid

### Formula
```
f(x) = 1 / (1 + e^(-x))
```

### Properties
- **Range:** (0, 1)
- **Derivative:** f(x) * (1 - f(x))
- **Pros:** Smooth gradient, outputs probabilities
- **Cons:** Vanishing gradient, not zero-centered

---

## 4. Tanh (Hyperbolic Tangent)

### Formula
```
f(x) = (e^x - e^(-x)) / (e^x + e^(-x))
```

### Properties
- **Range:** (-1, 1)
- **Derivative:** 1 - f(x)²
- **Pros:** Zero-centered, stronger gradients than sigmoid
- **Cons:** Still suffers from vanishing gradient

---

## 5. Softmax

### Formula
```
f(x_i) = e^(x_i) / Σ(e^(x_j))
```

### Properties
- **Range:** (0, 1), outputs sum to 1
- **Use Case:** Multi-class classification (output layer)
- **Pros:** Converts logits to probability distribution
- **Cons:** Computationally expensive

---

## 6. GELU (Gaussian Error Linear Unit)

### Formula
```
f(x) = x * Φ(x)  where Φ is the CDF of standard normal distribution
```

### Properties
- **Range:** (-∞, ∞)
- **Pros:** Smooth, used in transformers (BERT, GPT)
- **Cons:** More computationally expensive than ReLU

---

## 7. Swish / SiLU

### Formula
```
f(x) = x * sigmoid(x)
```

### Properties
- **Range:** (-∞, ∞)
- **Pros:** Self-gated, smooth, non-monotonic
- **Cons:** More expensive than ReLU

---

## Summary Table

| Activation | Range      | Zero-Centered | Vanishing Gradient | Common Use        |
| ---------- | ---------- | ------------- | ------------------ | ----------------- |
| ReLU       | [0, ∞)     | No            | No                 | Hidden layers     |
| Leaky ReLU | (-∞, ∞)    | No            | No                 | Hidden layers     |
| Sigmoid    | (0, 1)     | No            | Yes                | Binary output     |
| Tanh       | (-1, 1)    | Yes           | Yes                | Hidden layers     |
| Softmax    | (0, 1)     | No            | No                 | Multi-class output|
| GELU       | (-∞, ∞)    | No            | No                 | Transformers      |
| Swish/SiLU | (-∞, ∞)    | No            | No                 | Modern CNNs       |
