A linear transformation on qubits. Quantum Fourier Transform can be performed efficiently on a quantum computer with a particular decomposition into a product of simpler unitary matrices. [Fourier transforms](https://www.youtube.com/watch?v=spUNpyF58BY) can be implemented as a Quantum circuit consisting of only Hadamard gate and controlled phase shift gates.

Quantum Fourier Transform is a function that transforms between two bases, computational basis and [Fourier basis](https://matthew-brett.github.io/teaching/fourier_basis.html)

|State in Computational Basis⟩ −−− QFT−−−→ |State in Fourier Basis⟩

QFT|x⟩ = |x˜⟩

**Quantum Fourier Transform acts on quantum state and Fourier transformer acts on vectors**

# Difference in counting in Fourier transform

* In computational basis, numbers are stored in binary using the states |0⟩ and |1⟩
![](https://qiskit.org/textbook/ch-algorithms/images/zbasis-counting.gif)

* In Fourier basis, numbers are stored using different rotations around Z axis. The number we want to store dictates the angle at which each qubit is rotated about Z axis

![](https://qiskit.org/textbook/ch-algorithms/images/fourierbasis-counting.gif)

**Leftmost qubit has lowest frequency and rightmost has the highest**

In the state |0˜⟩ all qubits are in the state |+⟩. To encode the state |5˜⟩ on 4 qubits, rotate the left most qubit by 5/16 full turns i.e. 5/16 X 2π radians

# Circuit implementing QFT

The circuit comprises two gates:

1. Hadamard gate
2. CROT gate

![](https://qiskit.org/textbook/ch-algorithms/images/qft.png)
