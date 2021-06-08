A **deterministic**(given a prticular input will always give a particular output) quantum algorithm which was the first example of a quantum algorithm that outperforms the best classical algorithm

# Problem statement

Given a black box quantum computer ([Oracle](https://en.wikipedia.org/wiki/Oracle_machine)) that implements some Boolean function f, which takes as input a string of bits and returns either 0 or 1. The task is to determine if f is constant(**evaluates to 1**) or balanced(**evaluates to 0**) by using the Oracle

# Classical solution

* Total number of possible inputs, 2<sup>n</sup>
* Number of trial inputs, 2<sup>n-1</sup> + 1 to determine if f is constant in the worst case

**P<sub>constant</sub>(k) = 2<sup>1-k</sup>**

# Quantum solution

Using a quantum computer, we can solve the problem with 100% confidence after only one call to the function f(x), provided we have the function f implemented as a quantum Oracle

## Quantum circuit

![](https://qiskit.org/textbook/ch-algorithms/images/deutsch_steps.png)

## Steps

1. Prepare two quantum registers- **first** is a **n qubit register initialised to |0⟩** and the **second** is a **one-qubit register initialised to |1⟩**
2. Apply a Hadmard gate to each qubit
    * Input register is an equal superpoition of all the states in the computational basis
3. Apply the quantum Oracle
4. Apply Hadamard gate to each qubit in the first register
5. Measure the first register

# Effect of constant Oracle

* A constant Oracle has no effect on the input qubits and the quantum states before and after querying the Oracle are same
* Since H gate is its own inverse we obtain initial quantum state of |00...0⟩ in the first register

# Effect of balanced Oracle

* When the Oracle is balanced phase kickback adds a negative phase to exactly half of the input states
* The quantum state after querying the Oracle is orthogonal to the quantum state before querying the Oracle.
