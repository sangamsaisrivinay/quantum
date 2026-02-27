# Multi-Qubit States

## Tensor Product (Kronecker Product)

### Definition

The tensor product ⊗ of two vectors creates a larger vector by multiplying each element of the first vector by the entire second vector.

For vectors **a** = [a₁, a₂] and **b** = [b₁, b₂]:

```
a ⊗ b = [a₁]  ⊗  [b₁]  =  [a₁ × b₁]
        [a₂]     [b₂]     [a₁ × b₂]
                          [a₂ × b₁]
                          [a₂ × b₂]
```

### Step-by-Step Example

Let's compute |0⟩ ⊗ |1⟩ in detail:

**Step 1:** Write out the vectors
```
|0⟩ = [1]    |1⟩ = [0]
      [0]          [1]
```

**Step 2:** Multiply first element of |0⟩ by entire |1⟩
```
1 × [0]  =  [1×0]  =  [0]
    [1]     [1×1]     [1]
```

**Step 3:** Multiply second element of |0⟩ by entire |1⟩
```
0 × [0]  =  [0×0]  =  [0]
    [1]     [0×1]     [0]
```

**Step 4:** Stack the results
```
|0⟩ ⊗ |1⟩ = [0]  ← from step 2
            [1]  ← from step 2
            [0]  ← from step 3
            [0]  ← from step 3
```

---

## Two-Qubit System

A system with two qubits has **4 basis states**, formed by the tensor product of single-qubit states.

### Computational Basis States

#### |00⟩ = |0⟩ ⊗ |0⟩

```
[1]  ⊗  [1]  =  [1×1]  =  [1]
[0]     [0]     [1×0]     [0]
                [0×1]     [0]
                [0×0]     [0]
```

#### |01⟩ = |0⟩ ⊗ |1⟩

```
[1]  ⊗  [0]  =  [1×0]  =  [0]
[0]     [1]     [1×1]     [1]
                [0×0]     [0]
                [0×1]     [0]
```

#### |10⟩ = |1⟩ ⊗ |0⟩

```
[0]  ⊗  [1]  =  [0×1]  =  [0]
[1]     [0]     [0×0]     [0]
                [1×1]     [1]
                [1×0]     [0]
```

#### |11⟩ = |1⟩ ⊗ |1⟩

```
[0]  ⊗  [0]  =  [0×0]  =  [0]
[1]     [1]     [0×1]     [0]
                [1×0]     [0]
                [1×1]     [1]
```

### Summary Table

| State | Ket Notation | Tensor Product | Result Vector |
|-------|--------------|----------------|---------------|
| \|00⟩ | \|0⟩ ⊗ \|0⟩  | [1,0] ⊗ [1,0]  | [1,0,0,0]ᵀ    |
| \|01⟩ | \|0⟩ ⊗ \|1⟩  | [1,0] ⊗ [0,1]  | [0,1,0,0]ᵀ    |
| \|10⟩ | \|1⟩ ⊗ \|0⟩  | [0,1] ⊗ [1,0]  | [0,0,1,0]ᵀ    |
| \|11⟩ | \|1⟩ ⊗ \|1⟩  | [0,1] ⊗ [0,1]  | [0,0,0,1]ᵀ    |

---

## Understanding Probabilities in Two-Qubit States

### How Vector Components Map to Measurement Outcomes

Each component of the state vector corresponds to a specific measurement outcome:

```
|ψ⟩ = [a₀]  ← Probability amplitude for measuring |00⟩
      [a₁]  ← Probability amplitude for measuring |01⟩
      [a₂]  ← Probability amplitude for measuring |10⟩
      [a₃]  ← Probability amplitude for measuring |11⟩
```

The **probability** of measuring a particular state is the **squared magnitude** of its amplitude:
- P(|00⟩) = |a₀|²
- P(|01⟩) = |a₁|²
- P(|10⟩) = |a₂|²
- P(|11⟩) = |a₃|²

### Example: State |10⟩

For the state |10⟩ = [0, 0, 1, 0]ᵀ:

```
|ψ⟩ = [0]  ← a₀ = 0, so P(|00⟩) = |0|² = 0
      [0]  ← a₁ = 0, so P(|01⟩) = |0|² = 0
      [1]  ← a₂ = 1, so P(|10⟩) = |1|² = 1  ✓
      [0]  ← a₃ = 0, so P(|11⟩) = |0|² = 0
```

**Interpretation:**
- The third component is 1, all others are 0
- This means 100% probability of measuring |10⟩
- 0% probability of measuring any other state (|00⟩, |01⟩, or |11⟩)

### Example: Superposition State

For a superposition state |ψ⟩ = 1/√2 (|00⟩ + |10⟩):

```
|ψ⟩ = [1/√2]  ← a₀ = 1/√2, so P(|00⟩) = |1/√2|² = 1/2 = 50%
      [0]     ← a₁ = 0,    so P(|01⟩) = |0|²    = 0   = 0%
      [1/√2]  ← a₂ = 1/√2, so P(|10⟩) = |1/√2|² = 1/2 = 50%
      [0]     ← a₃ = 0,    so P(|11⟩) = |0|²    = 0   = 0%
```

**Interpretation:**
- 50% chance of measuring |00⟩ (first qubit = 0, second qubit = 0)
- 50% chance of measuring |10⟩ (first qubit = 1, second qubit = 0)
- The system is in a superposition of these two states

### Verification: Normalization

The sum of all probabilities must equal 1:

```
P(|00⟩) + P(|01⟩) + P(|10⟩) + P(|11⟩) = 1
```

For |10⟩: 0 + 0 + 1 + 0 = 1 ✓
For superposition: 1/2 + 0 + 1/2 + 0 = 1 ✓

### General Two-Qubit State

A general two-qubit state can be written as:

```
|ψ⟩ = α|00⟩ + β|01⟩ + γ|10⟩ + δ|11⟩
```

Where:
- α, β, γ, δ are complex probability amplitudes
- Normalization: |α|² + |β|² + |γ|² + |δ|² = 1

**Matrix representation:**
```
|ψ⟩ = [α]
      [β]
      [γ]
      [δ]
```

---

## N-Qubit Systems

### General Properties

For a system with **n qubits**:

- **Number of basis states**: 2ⁿ
- **Dimension of state vector**: 2ⁿ
- **Number of complex amplitudes**: 2ⁿ

### Examples

| Qubits | Basis States | Vector Dimension |
|--------|--------------|------------------|
| 1      | 2            | 2                |
| 2      | 4            | 4                |
| 3      | 8            | 8                |
| 4      | 16           | 16               |
| n      | 2ⁿ           | 2ⁿ               |

### Three-Qubit Example

A three-qubit system has 8 basis states:

```
|000⟩, |001⟩, |010⟩, |011⟩, |100⟩, |101⟩, |110⟩, |111⟩
```

General state:
```
|ψ⟩ = α₀|000⟩ + α₁|001⟩ + α₂|010⟩ + α₃|011⟩ 
    + α₄|100⟩ + α₅|101⟩ + α₆|110⟩ + α₇|111⟩
```

With normalization: Σᵢ |αᵢ|² = 1

---

## Separable vs Entangled States

### Separable State

A multi-qubit state is **separable** if it can be written as a tensor product:

```
|ψ⟩ = |ψ₁⟩ ⊗ |ψ₂⟩ ⊗ ... ⊗ |ψₙ⟩
```

**Example:**
```
|ψ⟩ = (1/√2 |0⟩ + 1/√2 |1⟩) ⊗ |0⟩ = 1/√2 |00⟩ + 1/√2 |10⟩
```

### Entangled State

A state is **entangled** if it cannot be factored into a tensor product.

**Example:**
```
|ψ⟩ = 1/√2 (|00⟩ + |11⟩)  ← Cannot be factored!
```

This is fundamentally different from any separable state and exhibits quantum correlations.