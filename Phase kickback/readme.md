The phenomenon where the **phase of target qubit** is **kicked up to the control qubit** via a controlled operation is called phase kickback and is used in almost every quantum algorithm. For example, performing **X gate on |−⟩ qubit**: X|−⟩ = −|−⟩

The identity below is an example of kickback mechanism. Wrapping the CNOT in H-gates transforms the qubits from the computational basis to the  (|+⟩, |−⟩) basis

![](https://qiskit.org/textbook/ch-gates/images/identities_1.svg)

**Control qubit is in either |0⟩ or |1⟩**:

This phase affects the whole state, however it is a global state and has no observable effects
* CNOT|−0⟩ = |−⟩⊗|0⟩ = |−0⟩
* CNOT|−1⟩ = X|−⟩⊗|1⟩ = −|−⟩⊗|1⟩ = −|−1⟩

**Control qubit is in superposition**:

The component of the control qubit that lies in the direction of |1⟩ applies this phase factor to the target qubit which in turn kicks back a relative phase to control qubit
* CNOT|−+⟩ = 1/√2 (CNOT|−0⟩+CNOT|−1⟩) = 1/√2 (|−0⟩+X|−1⟩) = 1/√2 (|−0⟩−|−1⟩)

which can be written as two seperate qubits , CNOT|−+⟩ = |−⟩⊗1/√2 (|0⟩−|1⟩) = |−−⟩
