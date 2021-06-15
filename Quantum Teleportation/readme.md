Quantum teleportation is a process by which the **state of qubit (|ψ⟩) can be transmitted from one location to another**, using **two bits of classical communication and a Bell pair**. In other words, we can say it is a protocol that destroys the quantum state of a qubit in one location and recreates it on a qubit at a distant location, with the help of shared entanglement

In other words, **transport one qubit using two classical bits**

# No cloning theorem

One cannot simply make an exact copy of an unknown quantum state

# Overview

Alice wants to send quantum information, |ψ⟩ = α|0⟩+β|1⟩ to Bob. This entails passing on information about α and β to Bob, because of no cloning theorem Alice cannot simply generate a copy of |ψ⟩ and give it to Bob. 

Only classical states can be copied not superposition. However, by taking advantage of two classical bits and an entangled qubit pair, Alice can transfer her state |ψ⟩ to Bob. We call this teleportation because, Bob will have |ψ⟩ and Alice would not.

# Quantum Teleportation Protocol

* To transfer a quantum bit, Alice and Bob must use a third party (Telamon) to send them an entangled qubit pair
* Alice then performs some operations on her qubit, sends the results to Bob over a classical communication channel
* Bob performs some operations on his end to receive Alice’s qubit

![](https://qiskit.org/textbook/ch-algorithms/images/tele1.jpg)

**The teleportation protocol can be thought of as a flipped version of the superdense coding protocol, in the sense that Alice and Bob merely “swap their equipment”**

## Steps

### Step1

Telamon prepares a pair of entangled qubits (Bell pair) for Alice and Bob. The entangled qubits could be written in Dirac Notation as: **|e⟩ = 1/√2 (|00⟩ + |11⟩)**

Alice and Bob each possess one qubit of the entangled pair (denoted as A and B respectively), |e⟩ = 1/√2 (|0⟩A|0⟩B + |1⟩A|1⟩B)
 
This creates a three qubit quantum system where Alice has the first two qubits and Bob the last one,

|ψ⟩⊗|e⟩ = 1/√2 (α|0⟩ ⊗ (|00⟩ + |11⟩) + β|1⟩ ⊗ (|00⟩ + |11⟩)) = 1/√2 (α|000⟩ + α|011⟩ + β|100⟩ + β|111⟩)

#### Creation of bell pair

Transfer one of the qubits to the X-basis (|+⟩ and |−⟩) using a Hadamard gate and then to apply a CNOT gate onto the other qubit controlled by the one in the X-basis

### Step2

Alice applies CNOT gate on her two qubits followed by Hadamard gate on the first qubit. This results in the state: 

(H⊗I⊗I)(CNOT⊗I)(|ψ⟩⊗|e⟩)=(H⊗I⊗I)(CNOT⊗I)1/√2(α|000⟩+α|011⟩+β|100⟩+β|111⟩)=1/2(α(|000⟩+|011⟩+|100⟩+|111⟩)+β(|010⟩+|001⟩−|110⟩−|101⟩)) = **1/2(|00⟩(α|0⟩+β|1⟩)+|01⟩(α|1⟩+β|0⟩)+|10⟩(α|0⟩−β|1⟩)+|11⟩(α|1⟩−β|0⟩))**

### Step3

Alice measures the first two qubit (which she owns) and sends them as two classical bits to Bob. The result she obtains is always one of the four standard basis states |00⟩,|01⟩,|10⟩ and |11⟩ with equal probability. projection of Bob's states

| State | Projection|
| ----- | --------- |
| 00 | α0 + β1 |
| 01 | α1 + β0 |
| 10 | α0 - β1 |
| 11 | α1 - β0 |

### Step4

Bob applies gates on the projections to obtain |ψ⟩

|  Projection | Gate applied |
| ----------- | ------------ |
| α0 + β1 | I |
| α1 + β0 | X |
| α0 - β1 | Z |
| α1 - β0 | ZX |
