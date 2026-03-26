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
- $|\alpha|^2 + |\beta|^2 = 1$ to satisfy normalization

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
- Probability of measuring $|0\rangle$ = $|\alpha|^2$
- Probability of measuring $|1\rangle$ = $|\beta|^2$

In quantum mechanics, measurements are represented using **observable operators**, which are matrices acting on quantum states.

#### 5. Observable Operators (Measurement Basis)

Observables represent measurable quantities in a quantum system. They are represented mathematically using **Hermitian matrices**, which have real eigenvalues and orthogonal eigenvectors.

##### Eigenvalues and Eigenstates

When an observable A acts on a quantum state, the measurement outcome corresponds to one of its eigenvalues.

$$A|\psi\rangle = \lambda|\psi\rangle$$

Where:

- $A$ is the observable operator
- $|\psi\rangle$ is the eigenstate
- $\lambda$ is the eigenvalue (measurement result)

If the state is already an eigenstate of the observable, the measurement result is deterministic. Otherwise, the outcome is probabilistic.

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

This operator measures the qubit along the **X-axis** of the Bloch sphere.

##### Pauli-Y Operator

The Pauli-Y operator introduces a phase difference and measures along the Y-axis.

Matrix representation:

$$Y = \begin{bmatrix} 0 & -i \\ i & 0 \end{bmatrix}$$

Eigenstates:

$$\frac{1}{\sqrt{2}}(|0\rangle + i|1\rangle)$$ → eigenvalue +1  
$$\frac{1}{\sqrt{2}}(|0\rangle - i|1\rangle)$$ → eigenvalue −1

| Operator | Matrix                                  | Measurement Axis |
| -------- | --------------------------------------- | ---------------- |
| Pauli-Z  | $\begin{bmatrix}1&0\\0&-1\end{bmatrix}$ | Z-axis           |
| Pauli-X  | $\begin{bmatrix}0&1\\1&0\end{bmatrix}$  | X-axis           |
| Pauli-Y  | $\begin{bmatrix}0&-i\\i&0\end{bmatrix}$ | Y-axis           |

#### 6. Expectation Value

The expectation value of an observable A for a quantum state $|\psi\rangle$ is the average result obtained from many repeated measurements.

$$\langle A \rangle = \langle\psi|A|\psi\rangle$$

For Pauli operators acting on a single qubit, the expectation value lies between **−1 and +1**.

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

The expectation value describes the balance between the probabilities of $|0\rangle$ and $|1\rangle$.

- $\langle Z \rangle = 1$ → qubit is fully in $|0\rangle$
- $\langle Z \rangle = -1$ → qubit is fully in $|1\rangle$
- $\langle Z \rangle = 0$ → equal superposition of $|0\rangle$ and $|1\rangle$

On the Bloch sphere, this value corresponds to the **projection of the qubit state along the measurement axis**.
