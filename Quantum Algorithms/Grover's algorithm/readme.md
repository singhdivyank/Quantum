# Grover's algorithm / Quantum search algorithm

An algorithm for [unstructured search](https://youtu.be/hK6BBluTGhU) that finds with the highest probability the unique input to a black box function that produces a particular output value in O(√N) evaluations of the function  

## Amplitude amplifiction trick

This algorithm can speed up an unstructured search problem quadratically, it can serve as a general trick to obtain quadratic runtime improvements for a variety of other algorithms

# Oracle

Grover's algorithm solves Oracles that add a negative phase to solution states i.e. 

for any state |x⟩ in the computational basis: U<sub>w</sub>|x⟩ = {|x⟩, if x≠ω; -|x⟩ if x=ω}

## Circuit representation

![](https://qiskit.org/textbook/ch-algorithms/images/grover_phase_oracle.svg)

# Amplitude amplification

Step1 - start out in the uniform superposition |s⟩, which is easily constructed from |s⟩ = H<sup>⊗n</sup>|0⟩<sup>n</sup>

![](https://qiskit.org/textbook/ch-algorithms/images/grover_step1.jpg)

Step2 - apply Oracle reflection U<sub>f</sub> to |s⟩ this means applitude in front of |w⟩ state becomes negative

![](https://qiskit.org/textbook/ch-algorithms/images/grover_step2.jpg)

Step3 - now apply an additional reflection about the state |s⟩: U<sub>s</sub> = 2|s⟩⟨s|−1 this transformation maps to U<sub>s</sub>U<sub>f</sub>|s⟩ and completes the transformation

![](https://qiskit.org/textbook/ch-algorithms/images/grover_step3.jpg)

This rotates |s⟩ closer to |w⟩. Since the average amplitude has been lowered by the first reflection this transformation boosts the negative amplitude of |w⟩ and decreases the other amplitudes.

After t steps: |ψ<sub>t</sub>⟩=(U<sub>s</sub>U<sub>f</sub>)<sup>t</sup>|s⟩

Roughly √N rotations are needed and for M solutions, √N/M rotations suffice

## Circuit diagram

![](https://qiskit.org/textbook/ch-algorithms/images/grover_circuit_high_level.png)

# For 2 qubit system

In a 2 qubit system, **N = 4** requires only **one rotation** to rotate |s⟩ to |w⟩

## Finding θ

(U<sub>s</sub>U<sub>ω</sub>)<sup>t</sup>|s⟩ = sinθ<sub>t</sub>|ω⟩ + cosθ<sub>t</sub>|s′⟩ where θ<sub>t</sub> = (2t+1)θ

This gives θ<sub>t</sub>=π/2 => θ=π/6

## Choosing the Oracle

Oracle for |w⟩ = 11. The Oracle Uw in this case is: U<sub>w</sub>|s⟩ = U<sub>w</sub>1/2(|00⟩ + |01⟩ + |10⟩ + |11⟩) = 1/2(|00⟩ + |01⟩ + |10⟩ − |11⟩)

Oracle can be represented as a matrix:

|1|0|0|0|
|-|-|-|-|
|0|1|0|0|
|0|0|1|0|
|0|0|0|-1|

this is a representation of the controlled Z gate, that means the **oracle** in this case **is** nothing but **controlled Z gate**

![](https://qiskit.org/textbook/ch-algorithms/images/grover_circuit_2qbuits_oracle_11.svg)

## Reflection

To complete the circuit an additional reflection is to be performed U<sub>s</sub>=2|s⟩⟨s|−1. There is a need to apply a negative phase to every state orthogonal to |s⟩

Steps to add a negative phase:
* H<sup>⊗n</sup>|s⟩ = |0⟩
* Now apply a circuit that adds a negative phase to states Orthogonal to |0⟩: U<sub>0</sub>1/2(|00⟩+|01⟩+|10⟩+|11⟩) = 1/2(|00⟩ −|01⟩ − |10⟩ − |11⟩)
* Apply H gate once again, this transforms the state |0⟩ to |s⟩

### Circuit diagram

![](https://qiskit.org/textbook/ch-algorithms/images/grover_circuit_2qbuits_reflection.svg)

## Overall circuit diagram

![](https://qiskit.org/textbook/ch-algorithms/images/grover_circuit_2qubits_full_11.svg)

# For 3 qubit system

For solving a 3 qubit system using Grover algorithm two marked states will be used - i) |101⟩ and ii) |110⟩

## Circuit diagram

![](https://qiskit.org/textbook/ch-algorithms/images/grover_circuit_3qubits.png)

## Steps to be performed:

1. Apply Hadamrd gate to 3 qubits initialized to |000⟩ to create a uniform superposition: |ψ<sub>1</sub>⟩=1/√8(|000⟩+|001⟩+|010⟩+|011⟩+|100⟩+|101⟩+|110⟩+|111⟩)
2. Mark states |101⟩ and |110⟩ using a phase oracle:|ψ<sub>2</sub>⟩=1/√8(|000⟩+|001⟩+|010⟩+|011⟩+|100⟩−|101⟩−|110⟩+|111⟩)
3. Perform reflection:
    * Apply Hadamard gate to qubits- |ψ<sub>3a</sub>⟩=1/2(|000⟩+|011⟩+|100⟩−|111⟩)
    * Apply X gate to qubits- |ψ<sub>3b</sub>⟩=1/2(−|000⟩+|011⟩+|100⟩+|111⟩)
    * Apply a doubly controlled Z gate between the 1, 2 (controls) and 3 (target) qubits: |ψ<sub>3c</sub>⟩=1/2(−|000⟩+|011⟩+|100⟩−|111⟩)
    * Apply X gates to qubits: |ψ<sub>3d</sub>⟩=1/2(−|000⟩+|011⟩+|100⟩−|111⟩)
    * Apply Hadamard gates to qubits: |ψ<sub>3e</sub>⟩=1/√2(−|101⟩−|110⟩)
4. Measure the three qubits to get receive states |101⟩ and |110⟩
