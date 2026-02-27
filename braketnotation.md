# Bra-Ket (Dirac) Notation

## Introduction

Bra-ket notation is a standard notation for describing quantum states, invented by physicist Paul Dirac.

### Basic Structure

```
⟨a|e⟩ = ⟨a| × |e⟩
```

Where:
- **|e⟩** = **ket** (represents the state of a qubit)
- **⟨a|** = **bra** (represents some angle of spin)
- **⟨a|e⟩** = **inner product** (bra-ket)

---

## Ket Notation

A **ket** represents the state of a qubit.

### Spin-Up Qubit

```
|1⟩ = [0]
      [1]
```

Read as: "ket 1"

### Spin-Down Qubit

```
|0⟩ = [1]
      [0]
```

Read as: "ket 0"

---

## Bra Notation

A **bra** represents some angle of spin and is the conjugate transpose of a ket.

### Converting Ket to Bra

Given a ket |a⟩:

**Step 1:** Take the transpose (aᵀ)
```
|a⟩ = [a₁]  →  aᵀ = [a₁  a₂]
      [a₂]
```

**Step 2:** Take the complex conjugate (a*)
```
⟨a| = (aᵀ)* = [a₁*  a₂*]
```

Where a* denotes the complex conjugate.

---

## Calculating Probability

To find the probability given ⟨a|e⟩:

```
Probability = |⟨a|e⟩|²
```

Where:
- ⟨a|e⟩ = a⁺ · e
- a⁺ = adjoint (conjugate transpose) of a

---

## Example Calculation

### Given States

```
a = |1⟩ = [0]
          [1]

e = |1⟩ = [0]
          [1]
```

### Step 1: Find the Transpose

```
aᵀ = [0  1]
```

### Step 2: Find the Complex Conjugate

Since there are no imaginary parts:

```
a⁺ = (aᵀ)* = [0  1]
```

### Step 3: Calculate Inner Product

```
⟨a|e⟩ = a⁺ · e = [0  1] · [0]
                          [1]

      = (0 × 0) + (1 × 1)
      = 0 + 1
      = 1
```

### Step 4: Calculate Probability

```
Probability = |⟨a|e⟩|² = |1|² = 1
```

**Result:** 100% probability (the states are identical)

---

## Superposition in Ket Notation

In most cases, we use ket notation to express quantum states.

### Example: Equal Superposition

```
|ψ⟩ = [1/√2]
      [1/√2]
```

This can be decomposed as:

```
|ψ⟩ = [1/√2] · [1] + [1/√2] · [0]
              [0]             [1]

    = (1/√2)|0⟩ + (1/√2)|1⟩

    = 1/√2 (|0⟩ + |1⟩)
```

**Interpretation:**
- The state is a linear combination of |0⟩ and |1⟩
- Equal probability (50%) of measuring either state
- This is the standard way to express superposition states

---

## Key Properties

### Normalization

For any valid quantum state |ψ⟩:

```
⟨ψ|ψ⟩ = 1
```

This ensures the total probability equals 1.

### Orthogonality

The basis states |0⟩ and |1⟩ are orthogonal:

```
⟨0|1⟩ = 0
⟨1|0⟩ = 0
```

### Identity

```
⟨0|0⟩ = 1
⟨1|1⟩ = 1
```

---

## Summary

| Notation | Name | Represents | Example |
|----------|------|------------|---------|
| \|ψ⟩     | Ket  | Quantum state (column vector) | \|0⟩ = [1, 0]ᵀ |
| ⟨ψ\|     | Bra  | Conjugate transpose (row vector) | ⟨0\| = [1, 0] |
| ⟨φ\|ψ⟩   | Bra-ket | Inner product (probability amplitude) | ⟨0\|0⟩ = 1 |

**Note:** In most quantum computing applications, we primarily use ket notation to describe states, and bra-ket notation to calculate probabilities and inner products.