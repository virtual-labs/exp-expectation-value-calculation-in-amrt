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

|ψ⟩ = α|0⟩ + β|1⟩

Where:

- α and β are complex numbers  
- |α|² + |β|² = 1 to satisfy normalization

In matrix form:

|0⟩ = [1, 0]ᵀ  
|1⟩ = [0, 1]ᵀ

This superposition is a key difference from classical bits, which are either 0 or 1 but never both at the same time.



#### 3. Qubit on the Bloch Sphere

Every pure qubit state can be represented on the surface of a sphere called the **Bloch Sphere**.

The general representation using spherical coordinates is:

|ψ⟩ = cos(θ/2)|0⟩ + e^(iφ) sin(θ/2)|1⟩

Where:

- θ represents the angle from the Z-axis  
- φ represents the angle in the X–Y plane  

This representation helps visualize quantum states as points on a three-dimensional sphere.



#### 4. Measurement in Quantum Computing

Quantum measurement collapses the qubit to one of the basis states.

If we measure in the computational basis:

- The outcome will be either |0⟩ or |1⟩  
- Probability of measuring |0⟩ = |α|²  
- Probability of measuring |1⟩ = |β|²  

In quantum mechanics, measurements are represented using **observable operators**, which are matrices acting on quantum states.



#### 5. Observable Operators (Measurement Basis)

Observables represent measurable quantities in a quantum system. They are represented mathematically using **Hermitian matrices**, which have real eigenvalues and orthogonal eigenvectors.



##### Eigenvalues and Eigenstates

When an observable A acts on a quantum state, the measurement outcome corresponds to one of its eigenvalues.

A|ψ⟩ = λ|ψ⟩

Where:

- A is the observable operator  
- |ψ⟩ is the eigenstate  
- λ is the eigenvalue (measurement result)

If the state is already an eigenstate of the observable, the measurement result is deterministic. Otherwise, the outcome is probabilistic.



##### Pauli-Z Operator

The Pauli-Z operator measures the qubit along the Z-axis.

Matrix representation:

Z = [[1, 0],  
     [0, -1]]

Measurement outcomes:

- |0⟩ → +1  
- |1⟩ → −1  

For a superposition state, the measurement produces an expectation value between −1 and +1.



##### Pauli-X Operator

The Pauli-X operator flips the state of a qubit and is often called the **quantum NOT gate**.

Matrix representation:

X = [[0, 1],  
     [1, 0]]

Eigenstates:

|+⟩ = (1/√2)(|0⟩ + |1⟩) → eigenvalue +1  
|−⟩ = (1/√2)(|0⟩ − |1⟩) → eigenvalue −1

This operator measures the qubit along the **X-axis** of the Bloch sphere.



##### Pauli-Y Operator

The Pauli-Y operator introduces a phase difference and measures along the Y-axis.

Matrix representation:

Y = [[0, -i],  
     [i, 0]]

Eigenstates:

(1/√2)(|0⟩ + i|1⟩) → eigenvalue +1  
(1/√2)(|0⟩ − i|1⟩) → eigenvalue −1



| Operator | Matrix | Measurement Axis |
|--------|--------|----------------|
| Pauli-Z | [[1,0],[0,-1]] | Z-axis |
| Pauli-X | [[0,1],[1,0]] | X-axis |
| Pauli-Y | [[0,-i],[i,0]] | Y-axis |



#### 6. Expectation Value

The expectation value of an observable A for a quantum state |ψ⟩ is the average result obtained from many repeated measurements.

⟨A⟩ = ⟨ψ|A|ψ⟩

For Pauli operators acting on a single qubit, the expectation value lies between **−1 and +1**.



#### 7. Example Calculation

Consider the qubit state:

|ψ⟩ = (1/√2)(|0⟩ + |1⟩)

Vector representation:

|ψ⟩ = [1/√2, 1/√2]ᵀ

Observable:

Z = [[1,0],[0,-1]]

Expectation value:

⟨Z⟩ = [1/√2, 1/√2] × [[1,0],[0,-1]] × [1/√2, 1/√2]ᵀ

Result:

⟨Z⟩ = 0



#### 8. Interpretation of Expectation Value

The expectation value describes the balance between the probabilities of |0⟩ and |1⟩.

- ⟨Z⟩ = 1 → qubit is fully in |0⟩  
- ⟨Z⟩ = −1 → qubit is fully in |1⟩  
- ⟨Z⟩ = 0 → equal superposition of |0⟩ and |1⟩  

On the Bloch sphere, this value corresponds to the **projection of the qubit state along the measurement axis**.