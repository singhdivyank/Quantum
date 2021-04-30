If two or more qubits are represented as a single quantum system this combined state is equal to tensor product of constituemt qubits. **An entangled state is a state that cannot be written as a tensor product of its constituent qubit states**.

# Bell pair

A bell state is a **maximally entangled quantum state of two qubits** thought to be spatially seperated but exhibit perfect correlation which cannot be explained without quantum mechanics

There are 4 bell states-

1. |Φ−⟩ = 1/√2 (|0⟩A ⊗ |0⟩B − |1⟩A ⊗ |1⟩B), **∣0⟩ and ∣1⟩ are computational basis**
2. |Φ+⟩ = 1/√2 (|0⟩A ⊗ |0⟩B + |1⟩A ⊗ |1⟩B)
3. |Ψ−⟩ = 1/√2 (|0⟩A ⊗ |1⟩B − |1⟩A ⊗ |0⟩B)
4. |Ψ+⟩ = 1/√2 (|0⟩A ⊗ |1⟩B + |1⟩A ⊗ |0⟩B)

One of them is achieved in the jupyter notebook-

![](https://upload.wikimedia.org/wikipedia/commons/thumb/f/fc/The_Hadamard-CNOT_transform_on_the_zero-state.png/400px-The_Hadamard-CNOT_transform_on_the_zero-state.png)

This means the **qubit held by "A" can be 0 as well as 1**. If A measured their qubit the **outcome would be perfectly random either possibility having probability 1/2** but if **"B" measured their qubit the outcome would be the same as the one A got**. So, **if B measured he/she would also get a random outcome on first sight**, but **if A and B communicated** they would find out that, although the outcomes seemed random, **they are correlated**. So far this is nothing special.

**Quantum mechanics allows qubits to be in quantum superposition** i.e. in 0 and 1 simultaneously, e.g. **in either of the states |+⟩ = 1/√2 (|0⟩+|1⟩) or |−⟩ = 1/√2 (|0⟩−|1⟩)**. If **A and B chose to measure** on this basis i.e. check **whether qubits were ∣+⟩ or ∣−⟩ they will find the same correlations as above**. That is because the Bell state can be formally rewritten as: 

|Φ+⟩ = 1/√2 (|+⟩A ⊗ |+⟩B + |−⟩A ⊗ |−⟩B) (**∣+⟩ and ∣-⟩ are hadamard basis**) 

which is still the same state

# Components in jupyter notebook

## Quantum circuit

A qunatum circuit object is used to store our circuits,  this is essentially a list of the quantum operations on our circuit and the qubits they are applied to. In a quantum circuit the qubit always start in the state |0⟩ using initialise() it can be transformed to any state

## Qiskit simulators

Used to view the resulting state of qubit

## Quantum register

A system comprising multiple qubits. The quantum computers perform calculations by manipulating qubits within a quantum register

## Classical register

An array of [flip-flops](https://en.wikipedia.org/wiki/Flip-flop_(electronics))

## Measurement

Takes a quantum state and projects it to one of the basis vectors with a likelihood equal to square of vector's depth along the [basis](https://www.quantum-inspire.com/kbase/qubit-basis-states/) vector. As it assigns the observed quantum state to a single value it is irreversible thus cannot be a quantum gate.

Measuring a single qubit, whose quantum state is represented by the vector ∣Y⟩ = a∣0⟩ + b∣1⟩ will result in ∣0⟩ with probability |a|^2 and ∣1⟩ with probability |b|^2

![](https://miro.medium.com/max/1200/1*wEVOl6Cqr7_JtyfXcQCezQ.png)

To measure ∣Y⟩ in ∣0⟩ and ∣1⟩:

P(0) = |<Y∣0⟩|^2 and P(1) = |<Y∣1⟩|^2 where <Y∣0⟩ and <Y∣1⟩ is [bra-ket notation](https://www.youtube.com/watch?v=ctXDXABJRtg)
