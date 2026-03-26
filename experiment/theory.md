<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>

#### 1. What is Quantum Computing?

Quantum computing is a field of computing that uses principles of quantum mechanics to perform calculations. Unlike classical computers, which use bits as the smallest unit of information (0 or 1), quantum computers use **qubits**, which can exist in a combination (superposition) of both 0 and 1.

Quantum computing is powerful because:

- Qubits can exist in superpositions
- Multiple qubits can be **entangled**, sharing information instantly
- It enables new algorithms that are faster than classical ones for certain problems (for example, Shor’s algorithm and Grover’s algorithm)

This experiment focuses on the basic concept of measuring a qubit and understanding what the outcome means through the **expectation value**.

#### 2. What is a Qubit?

A qubit is the fundamental unit of quantum information. It is a two-level quantum system that can be in state |0⟩, |1⟩, or any linear combination of the two.

Mathematically, a qubit can be written as:

$$|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$$

Where:

- α and β are complex numbers
- Normalization condition:

$$|\alpha|^2 + |\beta|^2 = 1$$

In matrix form:

$$|0\rangle = \begin{bmatrix} 1 \\ 0 \end{bmatrix}$$

$$|1\rangle = \begin{bmatrix} 0 \\ 1 \end{bmatrix}$$

This superposition is a key difference from classical bits, which are either 0 or 1 but never both at the same time.

#### 3. Qubit on the Bloch Sphere

Every pure qubit state can be represented on the surface of a sphere called the **Bloch Sphere**.

The general representation using spherical coordinates is:

$$|\psi\rangle = \cos(\theta/2)|0\rangle + e^{i\phi} \sin(\theta/2)|1\rangle$$

Where:

- $\theta$ represents the angle from the Z-axis
- $\phi$ represents the angle in the X–Y plane

This representation helps visualize quantum states as points on a three-dimensional sphere.

#### 4. Measurement in Quantum Computing

Quantum measurement collapses the qubit to one of the basis states.

If we measure in the computational basis:

- The outcome will be either $|0\rangle$ or $|1\rangle$
- Probability of measuring $|0\rangle$:

$$P(0) = |\alpha|^2$$

- Probability of measuring $|1\rangle$:

$$P(1) = |\beta|^2$$

In quantum mechanics, measurements are represented using **observable operators**, which are matrices acting on quantum states.

#### 5. Observable Operators (Measurement Basis)

In quantum mechanics, every measurable physical quantity (like position, momentum, or spin) is represented by an **observable**—a mathematical operator that acts on quantum states.

Observables represent measurable quantities in a quantum system. They are represented mathematically using **Hermitian matrices**, which have the special property that:

- All eigenvalues are **real numbers** (required since measurement outcomes must be physically real)
- Eigenvectors form a **complete orthonormal basis** (allowing any quantum state to be expressed as a superposition of eigenstates)

##### Why Hermitian Matrices?

Observable operators must be **Hermitian** (self-adjoint) for two fundamental reasons:

1. **Real Eigenvalues**: Physical measurement outcomes are always real numbers. Hermitian matrices guarantee that their eigenvalues are real, ensuring that quantum measurements always produce real, physical results.

2. **Orthogonal Eigenvectors**: A Hermitian matrix has a complete set of orthogonal eigenvectors. This orthogonal basis is essential because it allows any quantum state to be decomposed into eigenstates, making the eigenvalue structure central to understanding measurement outcomes.

##### Eigenvalues and Eigenstates

When an observable $A$ acts on a quantum state, the measurement outcome corresponds to one of its eigenvalues:

$$A|\psi\rangle = \lambda|\psi\rangle$$

Where:

- $A$ is the observable operator (a Hermitian matrix)
- $|\psi\rangle$ is the eigenstate of $A$
- $\lambda$ is the eigenvalue (the measurement outcome)

**Physical Interpretation:**

- If the system is in an eigenstate

$$|\psi\rangle$$

of observable $A$, measuring $A$ will always yield the eigenvalue $\lambda$ with **100% certainty** (deterministic result).

- If the system is in a **superposition** (not an eigenstate), the measurement outcome is probabilistic. The result will be one of the eigenvalues, with probability determined by the overlap of the state with each eigenstate.
- For a general state, the expected measurement outcome is the **expectation value** of the observable, which is a weighted average of all eigenvalues based on the state composition.

##### Pauli-Z Operator

The Pauli-Z operator measures the qubit along the Z-axis.

Matrix representation:

$$Z = \begin{bmatrix} 1 & 0 \\ 0 & -1 \end{bmatrix}$$

Measurement outcomes:

- $|0\rangle$ → +1
- $|1\rangle$ → −1

For a superposition state, the measurement produces an expectation value between −1 and +1.

##### Pauli-X Operator

The Pauli-X operator flips the state of a qubit and is often called the **quantum NOT gate**.

Matrix representation:

$$X = \begin{bmatrix} 0 & 1 \\ 1 & 0 \end{bmatrix}$$

Eigenstates:

$$|+\rangle = \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle)$$ → eigenvalue +1
$$|-\rangle = \frac{1}{\sqrt{2}}(|0\rangle - |1\rangle)$$ → eigenvalue −1

##### Pauli-Y Operator

The Pauli-Y operator introduces a phase difference and measures along the Y-axis.

Matrix representation:

$$Y = \begin{bmatrix} 0 & -i \\ i & 0 \end{bmatrix}$$

Eigenstates:

$$\frac{1}{\sqrt{2}}(|0\rangle + i|1\rangle)$$ → eigenvalue +1
$$\frac{1}{\sqrt{2}}(|0\rangle - i|1\rangle)$$ → eigenvalue −1
| -------- | --------------------------------------- | ---------------- |
| Pauli-Z | $\begin{bmatrix}1&0\\0&-1\end{bmatrix}$ | Z-axis |
| Pauli-X | $\begin{bmatrix}0&1\\1&0\end{bmatrix}$ | X-axis |
| Pauli-Y | $\begin{bmatrix}0&-i\\i&0\end{bmatrix}$ | Y-axis |

#### 6. Expectation Value

The expectation value of an observable $A$ for a quantum state:

$$|\psi\rangle$$

is the **statistical average** of measurement outcomes obtained from many repeated measurements on identically prepared quantum systems.

$$\langle A \rangle = \langle\psi|A|\psi\rangle$$

**Connection to Eigenvalues:**
The expectation value can be understood as a weighted average of the observable's eigenvalues:

$$\langle A \rangle = \sum_i P_i \lambda_i$$

Where:

- $\lambda_i$ are the eigenvalues of observable $A$
- $P_i$ is the probability of measuring eigenvalue $\lambda_i$
- The probabilities $P_i$ are determined by the overlap: $P_i = |\langle \psi_i | \psi \rangle|^2$, where $|\psi_i\rangle$ is the eigenstate corresponding to eigenvalue $\lambda_i$
- The sum of all probabilities equals 1: $\sum_i P_i = 1$

**Key Points:**

- For **eigenstates**: If $|\psi\rangle$ is an eigenstate of $A$ with eigenvalue $\lambda$, then $\langle A \rangle = \lambda$ (deterministic result)
- For **superpositions**: $\langle A \rangle$ lies between the smallest and largest eigenvalues of $A$
- For Pauli operators (with eigenvalues ±1), the expectation value always satisfies: $-1 \leq \langle A \rangle \leq +1$

#### 7. Example Calculation

Consider the qubit state:

$$|\psi\rangle = \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle)$$

Vector representation:

$$|\psi\rangle = \begin{bmatrix} 1/\sqrt{2} \\ 1/\sqrt{2} \end{bmatrix}$$

Observable:

$$Z = \begin{bmatrix}1&0\\0&-1\end{bmatrix}$$

Expectation value:

$$\langle Z \rangle = \begin{bmatrix} 1/\sqrt{2} & 1/\sqrt{2} \end{bmatrix} \begin{bmatrix}1&0\\0&-1\end{bmatrix} \begin{bmatrix} 1/\sqrt{2} \\ 1/\sqrt{2} \end{bmatrix}$$

Result:

$$\langle Z \rangle = 0$$

#### 8. Interpretation of Expectation Value

The expectation value is fundamentally a measure of how much the quantum state aligns with the eigenstates of the observable being measured.

**For the Pauli-Z operator:**
The expectation value $\langle Z \rangle$ describes the balance between the probabilities of measuring the two eigenvalues (+1 and −1):

When $\langle Z \rangle = +1$: The state is eigenstate $|0\rangle$ (100% probability of outcome +1)

When $\langle Z \rangle = -1$: The state is eigenstate $|1\rangle$ (100% probability of outcome −1)

When $\langle Z \rangle = 0$: Equal superposition (50% chance of +1, 50% chance of −1)

**Geometric Interpretation (Bloch Sphere):**
On the Bloch sphere, the expectation value equals the **z-component of the qubit state's position**. This is because:

- The Bloch sphere's surface represents all possible quantum states
- Each measurement axis (X, Y, or Z) defines a direction in 3D space
- The expectation value of a Pauli operator equals the projection of the state onto that measurement axis
- This projection directly gives the weighted average of the eigenvalue outcomes

This geometric picture provides intuition: a state pointing "up" (toward +Z) will have $\langle Z \rangle \approx +1$, while a state pointing "down" (toward -Z) will have $\langle Z \rangle \approx -1$.
