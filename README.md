# Quantum Computing

## About this repositry

Contains codes as Jupyter notebooks tried on IBM Quiskit in different folders. Before looking at the notebooks lets first understand about Quantum computing. 

## What is Quantum computing

Quantum computing harnesses the phenomenon of Quantum mechanics to solve cmplex problems that powerful super computers cannot and will not solve. Supercomputers are unable to have working memory to hold the myriad combinations of real world problems, they analyze each combination one after the other which is time consuming. Such scenarios lead to the birth of Quantum computing. Real life applications of Quantum Computing- [Quantum battery in electric vehicles](https://www.ibm.com/case-studies/daimler/), [Searching for Higgs event and discovery of Universe](https://www.ibm.com/case-studies/cern/)

## Advantages of Quantum Computers

1. Fast speed

2. Minimize the need for optimizing space complexity

**Explained below are some terms used in the Jupyter notebooks**

## Quantum gates

Like digital computers have classical logic gates operating on bits similarly quantum computers have quantum gates operating on **[qubits](https://www.quantum-inspire.com/kbase/what-is-a-qubit/)**. Unlike logic gates **all quantum gates are reversible**. 

Reversibility means from any possible output it is possible to get unique input corresponding to output. Explained below are some quantum gates frequently used by-

### Single qubit gates
1. Hadamard gate

Rotates a qubit by 180 degrees in the XZ plane. It can be considered as a X gate followed by 90 degree rotation about Y axis

![](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSsJ2do2WiVrR9NKmYfED1TxNuJr1rCQeVjww&usqp=CAU)

This means a measurement will have equal probabilities to result in 0 or 1 i.e. creates superposition

**Circuit representation**:

![](https://upload.wikimedia.org/wikipedia/commons/thumb/1/1a/Hadamard_gate.svg/300px-Hadamard_gate.svg.png)

**Matrix representation**:

![](https://miro.medium.com/max/366/1*NsjB5wjw2Hbk9AKWObtFHA.png)

**Reversibility of Hadamard gate**:

![](https://miro.medium.com/max/780/1*IFAIKjWcInXkRQPn2wCgQg.png)

2.  X gate

A bit flip gate equivalent to NOT gate in classical computers i.e. it maps |0⟩ to |1⟩ and |1⟩ to |0⟩. It equates to a rotation around X axis by 180 degrees

![](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/95986i683E040D17666026?v=v2)

**Circuit representation**:

![](https://upload.wikimedia.org/wikipedia/commons/4/43/Qcircuit_X.svg)

**Matrix representation**:

![](https://desireevl.com/images/intro_unitary/X.png)

3. Z gate

**Circuit representation**

![](https://upload.wikimedia.org/wikipedia/commons/f/f7/Qcircuit_Z.svg)

4. Y gate

Equates to a rotation around Y axis by 180 degrees, maps |0⟩ to i|1⟩ and |1⟩ to -i|0⟩

**Circuit representation**:

![](https://upload.wikimedia.org/wikipedia/commons/7/79/Qcircuit_Y.svg)

**Matrix representation and relationship between X, Y and Z gate**:

![](https://desireevl.com/images/intro_unitary/Y.png)

Computation performed by Y gate-

![](https://desireevl.com/images/intro_unitary/Y0.png)

5. I gate

6. NOT gate

### Two qubit gates
1. CNOT gate

2. Controlled gate

3. Swap gate

![](https://static-01.hindawi.com/articles/physri/volume-2014/479320/figures/479320.fig.002.jpg)

### Three qubit gates
1. CCNOT gate

2. CSWAP gate

**3C NOT gate**

## Bloch sphere
