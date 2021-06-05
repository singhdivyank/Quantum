Basically in this problem the solution is unknown before hand, the Oracle will be created without prior knowledge of the solution

# Problem statement

Given a 2X2 binary sudoku having two rules:
1. No column may contain the same value twice
2. No row may contain the same value twice

Output a solution to the sudoku (given below) by means of a circuit

![](https://qiskit.org/textbook/ch-algorithms/images/binary_sudoku.png)

## Steps involved

### Step1- Turning the problem into a circuit

Create a classical function on a quantum circuit that checks whether the state of variable bits is a valid solution

Conditions to check:
1. v0 ≠ v1
2. v2 ≠ v3
3. v0 ≠ v2
4. v1 ≠ v3

To check computationally make use of XOR gate

To complete checking circuit, the need is to have a single bit as 1 iff all clauses are satisfied. This is achieved by using a multi-controlled Toffoli-gate

### Step2- Completing the Oracle

Turn the checking circuit into a Grover orcle using **phase kickback**

To create an oracle, we need our circuit (U<sub>w</sub>) to perform the transformation: U<sub>w</sub>|x⟩|0⟩|out0⟩=|x⟩|0⟩|out<sub>0</sub>⊕f(x)⟩

If we set the out<sub>0</sub> qubit to the superposition state |−⟩ we have: U<sub>w</sub>|x⟩|0⟩|−⟩= U<sub>w</sub>|x⟩|0⟩⊗1/√2(|0⟩−|1⟩)=|x⟩|0⟩⊗1/√2(|0⊕f(x)⟩−|1⊕f(x)⟩)
 
If f(x)=0, then we have the state: |x⟩|0⟩⊗1/√2(|0⟩−|1⟩)=|x⟩|0⟩|−⟩(i.e. no change), if f(x)=1, we introduce a negative phase to the |−⟩ qubit:=|x⟩|0⟩⊗1/√2(|1⟩−|0⟩)=|x⟩|0⟩⊗−1/√2(|0⟩−|1⟩)=−|x⟩|0⟩|−⟩

This is a functioning oracle that uses two auxiliary registers in the state |0⟩|−⟩: U<sub>w</sub>|x⟩|0⟩|−⟩= {|x⟩|0⟩|−⟩for x≠ω; −|x⟩|0⟩|−⟩ for x=ω

### Step3- Use Grover's algorithm to solve the Oracle
