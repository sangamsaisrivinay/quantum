# Qubit States

## Basic Qubit States

A qubit has **2 fundamental states**: spin-up or spin-down.

### Spin-Up State (Classical Bit 1)

```
|↑⟩ = |1⟩ = [0]
            [1]
```

**Matrix representation:**
```
|1⟩ = [0]
      [1]
```

Represents classical bit **1**

### Spin-Down State (Classical Bit 0)

```
|↓⟩ = |0⟩ = [1]
            [0]
```

**Matrix representation:**
```
|0⟩ = [1]
      [0]
```

Represents classical bit **0**

---

## General Qubit State Vector

For a general qubit state vector:

```
|ψ⟩ = [p]
      [q]
```

Where:
- **p** = probability amplitude of spin-down state
- **q** = probability amplitude of spin-up state

### Complex Probability Amplitudes

Each amplitude can be a complex number:

```
p = a + ib
```

Where:
- `a` = real part
- `b` = imaginary part
- `i` = imaginary unit (√-1)

### Probability Calculation

The probability is calculated using the squared magnitude:

```
|p|² = a² + b²
```

### Normalization Condition

The sum of probabilities must equal 1:

```
|p|² + |q|² = 1
```

This ensures the qubit is in a valid quantum state.

---

## Example: Superposition State

A qubit in equal superposition:

**Ket notation:**
```
|ψ⟩ = 1/√2 |0⟩ + 1/√2 |1⟩
```

**Matrix representation:**
```
|ψ⟩ = [1/√2]
      [1/√2]
```

Or equivalently:
```
|ψ⟩ = 1/√2 [1] + 1/√2 [0] = [1/√2]
            [0]       [1]   [1/√2]
```

### Verification

```
p² + q² = (1/√2)² + (1/√2)²
        = 1/2 + 1/2
        = 1 ✓
```

This state represents a **50% probability** of measuring either spin-up or spin-down.