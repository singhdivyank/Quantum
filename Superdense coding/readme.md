A quantum communication protocol to **transmit two classical bits** of information from a sender(Alice) to a receiver(Bob) **by sending only one qubit** from Alice to Bob under the assumption of **Alice and Bob pre-sharing an entangled state**

It is the underlying principle of secure quantum secret coding

# The process

![](https://qiskit.org/textbook/ch-algorithms/images/superdense.jpg)

1. **Alice** can prearrange the measurement Bob makes by performing one of the **four quantum gate operations on the entagled qubit** she posses
2. **Bob** receives the qubits, operates on both of them and measures them thus having **two classical bits of information**

## Importance of entanglement

If Alice and Bob do not share entanglement before the protocol begins then it is impossible then it is impossible to send two classical bits using a single qubit

## Importance of two qubits

Having two qubits to decode the information being sent eliminates the risk of eavesdroppers intercepting messages

# Steps involved

## Step1: Preparation
Charlie(third party) prepares a [bell pair](https://github.com/singhdivyank/Quantum/tree/main/Entanglement)

## Step2: Sharing

Charlie shares the first qubit with Alice and second qubit with Bob

## Step3: Encoding

The goal of this protocol is for Alice to send two classical bits to Bob using a qubit inorder to do so she has to apply a set of quantum gates depending on the bits she wants to send

This process **transforms the entangled** state but does not break it

| Intended message | Applied gate | Resulting state |
| ---------------- | ------------ | --------------- |
| 00 | I | 00 + 11 |
| 10 | X | 01 + 10 |
| 01 | Z | 00 - 11 |
| 11 | ZX | -01 + 10 |

## Step4: Sending

Alice sends her entangled qubit to Bob through a [quantum network](https://en.wikipedia.org/wiki/Quantum_network)

## Step5: Decoding

Bob uses his qubit to receive Alice's qubit and applies CNOT gate using rightmost qubit as control and leftmost as target. After that he applies a Hadamard gate and measures both the qubits to extract Alice's message

**There is no need to have knowledge of the state to decode it. Just simply use the restoration operation**

| Bob receives | After CNOT | After Hadamard |
| ------------ | ---------- | -------------- |
| 00 + 11 | 00 + 01 | 00 |
| 01 + 10 | 11 + 10 | 10 |
| 00 - 11 | 00 - 01 | 01 |
| -01 + 10 | -11 + 10 | -11 |
