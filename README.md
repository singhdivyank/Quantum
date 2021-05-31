# Quantum Computing

## About this repository

Contains codes as Jupyter notebooks tried on IBM Quiskit in different folders. Before looking at the notebooks lets first understand about Quantum computing. 

## What is Quantum computing

Quantum computing harnesses the phenomenon of Quantum mechanics to solve complex problems that powerful super computers cannot and will not solve. Supercomputers are unable to have working memory to hold the myriad combinations of real world problems, they analyze each combination one after the other which is time consuming. Such scenarios lead to the birth of Quantum computing. Real life applications of Quantum Computing- [Quantum battery in electric vehicles](https://www.ibm.com/case-studies/daimler/), [Searching for Higgs event and discovery of Universe](https://www.ibm.com/case-studies/cern/)

## Advantages of Quantum Computers

1. Fast speed

2. Minimize the need for optimizing space complexity

**Explained below are some terms used in the Jupyter notebooks**

## Quantum gates

Like digital computers have classical logic gates operating on bits similarly quantum computers have quantum gates operating on **[qubits](https://www.quantum-inspire.com/kbase/what-is-a-qubit/)**. Unlike logic gates **all quantum gates are reversible**. 

Reversibility means from any possible output it is possible to get unique input corresponding to output. Explained below are some frequently used quantum gates-

### Single qubit gates
1. Hadamard gate

Rotates a qubit by 180 degrees in the XZ plane. It can be considered as a X gate followed by 90 degree rotation about Y axis

![](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSsJ2do2WiVrR9NKmYfED1TxNuJr1rCQeVjww&usqp=CAU)

This means a measurement will have equal probabilities to result in 0 or 1 i.e. creates superposition

**Circuit representation**:

![](https://upload.wikimedia.org/wikipedia/commons/thumb/1/1a/Hadamard_gate.svg/300px-Hadamard_gate.svg.png)

**Matrix representation**:

![](https://miro.medium.com/max/366/1*NsjB5wjw2Hbk9AKWObtFHA.png)

2.  X gate / **Pauli X gate**

A **bit flip gate** equivalent to NOT gate in classical computers i.e. it maps |0⟩ to |1⟩ and |1⟩ to |0⟩. It equates to a rotation around X axis by 180 degrees

![](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/95986i683E040D17666026?v=v2)

**Circuit representation**:

![](https://upload.wikimedia.org/wikipedia/commons/4/43/Qcircuit_X.svg)

**Matrix representation**:

![](https://desireevl.com/images/intro_unitary/X.png)

**Mapping |1⟩ to |0⟩**

![](https://desireevl.com/images/intro_unitary/X1.png)

3. Z gate / **Pauli Z gate**

A **phase shift gate** that maps |0⟩ to |0⟩ and |1⟩ to -|1⟩. It equates to a rotation around Z axis by 180 degrees

**Circuit representation**:

![](https://upload.wikimedia.org/wikipedia/commons/f/f7/Qcircuit_Z.svg)

**Matrix representation**:

![](https://phyworld.pk/wp-content/uploads/2020/12/Screenshot-79.png)

**Demonstrating phase shift**

![](https://desireevl.com/images/intro_unitary/Z0.png)

![](https://desireevl.com/images/intro_unitary/Z1.png)

4. Y gate / **Pauli Y gate**

Equates to a rotation around Y axis by 180 degrees, maps |0⟩ to i|1⟩ and |1⟩ to -i|0⟩

**Circuit representation**:

![](https://upload.wikimedia.org/wikipedia/commons/7/79/Qcircuit_Y.svg)

**Matrix representation and relationship between X, Y and Z gate**:

![](https://desireevl.com/images/intro_unitary/Y.png)

**Mapping |0⟩ to i|1⟩**

![](https://desireevl.com/images/intro_unitary/Y0.png)

5. I gate

| Input | Output |
| ----- | ------ |
| 0 | 0 |
| 1 | 1 |

6. √NOT gate

It maps the basis state |0⟩ to ((1 + i)|0⟩ + (1 - i)|1⟩)/2 and |1⟩ to ((1 - i)|0⟩ + (1 + i)|1⟩)/2

**Circuit representation**:

![](https://upload.wikimedia.org/wikipedia/commons/thumb/b/b1/Qcircuit_SqrtNot.svg/300px-Qcircuit_SqrtNot.svg.png)

**Matrix representation**:

![]()

### Two qubit gates
1. CNOT gate

The Controlled NOT gate can be used to entangle and disentangle bell states.

**Truth table**:

| a | b | Output |
| - | - | ------ |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

**Conclusion**:
* If control bit is 0, target bit is the output
* If control bit is 1, the output qubit will be obtained by flipping target bit

For **|01⟩, 0 is control bit and 1 is target bit**

![](https://www.researchgate.net/publication/334686887/figure/fig1/AS:784710536032256@1564100979347/Matrix-representation-and-quantum-circuit-of-CNOT-gate.png)

2. Controlled Z gate

* If control bit is 0 then no change
* If control bit is 1 then apply Z gate to target bit

**Truth table**:

| Input | Output |
| ----- | ------ |
| 00 | 00 |
| 01 | 01 |
| 10 | 10 |
| 11 | -11 |

![](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSQwNBaq5opSmtqOSuGh0SwhDMDN8RsXJCKnenUBYWnMuWTdAmcDpM2nj0_D8eKEuHPLZI&usqp=CAU)

3. Swap gate

Swaps the state of two qubits involved in operation

**Truth table**:

| Input | Output |
| ----- | ------ |
| 00 | 00 |
| 01 | 10 |
| 10 | 01 |
| 11 | 11 |

**Circuit representation**:

![](https://static-01.hindawi.com/articles/physri/volume-2014/479320/figures/479320.fig.002.jpg)

**Matrix representation**:

![](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT65UDk4od4hMSOb78eSgf9IYfyIIDtE2TYgQ&usqp=CAU)

4. CROT gate

Controlled rotation gate

![](https://image2.slideserve.com/4731414/crot-gate-a-two-qubit-gate-l.jpg)

### Three qubit gates
1. CCNOT gate / **Toffoli gate**

It is a universal gate only when combined with a Hadamard gate

**Truth table**:

| a | b | c | Output |
| - | - | - | ------ |
| 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 1 |
| 0 | 1 | 0 | 0 |
| 0 | 1 | 1 | 1 |
| 1 | 0 | 0 | 0 |
| 1 | 0 | 1 | 1 |
| 1 | 1 | 0 | **1** |
| 1 | 1 | 1 | **0** |

**If both the internal bit are |1⟩ state then flip the target bit**

![](https://www.researchgate.net/publication/282460904/figure/fig1/AS:651577236934659@1532359527889/Toffoli-CCNOT-gate-symbol-and-associated-matrix.png)

2. CSWAP gate / **Fredkin gate**

**Truth table**:

| a | b | c | Output |
| - | - | - | ------ |
| 0 | 0 | 0 | 000 |
| 0 | 0 | 1 | 001 |
| 0 | 1 | 0 | 010 |
| 0 | 1 | 1 | 011 |
| 1 | 0 | 0 | 100 |
| 1 | 0 | 1 | 110 |
| 1 | 1 | 0 | 101 |
| 1 | 1 | 1 | 111 |

**If control bit is 1 then swap the other two bits**

**Circuit representation**:

![](https://upload.wikimedia.org/wikipedia/commons/thumb/c/ca/Fredkin_gate.svg/1200px-Fredkin_gate.svg.png)

**Matrix representation**:

![](https://jeremykun.files.wordpress.com/2015/04/example-3swap2.png)

**3C NOT gate**

**Circuit representation**:

![](https://i.stack.imgur.com/ELZCQ.png)

Here the 5th qubit |0⟩ is called ancilla qubit it starts with |0⟩ and ends in |0⟩ when the circuit is applied. It is needed for calculation and does not actually take part in input-output

## Bloch sphere

A geometric representation (3 dimensional) of pure state space of a single qubit. The North pole is chosen for the basis vector |0⟩ (spin up) and South pole for basis vector |1⟩ (spin down). The points on the surface correspond to [pure states](https://en.wikipedia.org/wiki/Quantum_state#Superposition_of_pure_states) of the system whereas interior points correspond to [mixed states](https://en.wikipedia.org/wiki/Quantum_state#Mixed_states)

An advantage of Bloch sphere is that the evolution of the qubit is describable by rotations of Bloch sphere.

**Rotations of Bloch sphere about Cartesian axis in Bloch basis**:

![](http://einsteinrelativelyeasy.com/images/Quantum/hadamard_decomposition_1.gif)

**Rotations of qubit after logic gate operations**:

![](https://miro.medium.com/max/3184/1*qVOpHOnoxiNDK33znIXmjA.png)
