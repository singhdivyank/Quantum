Quantum Finite Automata or Quantum State Machine provide a mathematical abstraction of real world quantum computers they are special cases of [geometric finite automata](https://en.wikipedia.org/wiki/Quantum_finite_automaton#Geometric_generalizations) or [topological finite automata](https://link.springer.com/chapter/10.1007/978-3-540-31856-9_32).

The automata work by receiving finite-length string of letters from a finite alphabet and assigning to each such string a probability indicating the probability of automation being in an accept state i.e. indicating whether the automation accepted or rejected the string

# Types of automata

## Measure-once

* The quantum automation is considered to have N possible internal states, represented by an N-state qubits
* The accept state is given by an NXN projection matrix

Given below is an example of such a system represented by a classical finite automation and state transition table

* Transition table
* State diagram

## Measure-all

The general framework resembles that of measure-once automata except that instead of one projection at the end there is a projection (measurement) performed after each letter is read
