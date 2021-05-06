A secure communication method which implements a cryptographic protocol implementing a cryptographic protocol involving components of quantum mechanics. It enables two parties to produce a shared random secret key known to them which can then be used to encrypt and decrypt messages

It is used to produce and distribute a key, not to transmit any message data. This key can then be used with any chosen encryption algorithm to encrypt a message which can then be ttransmitted over a standard communication channel

# Importance

It allows two communicating users to detect the presence of any third party trying to gain knowledge of the key. A third party trtying to eavesdrop on the key must in some way measure it, thus introducing detectable anomalies

## Detecting eavesdropping

By using **entanglement** and **transmitting information in quantum states**, a communicating system (some type of fibre-optic cable) can be implemented to detect eavesdropping

## Protocol overview

The protocol makes use of the fact that measuring a qubit can change its state. If Alice sends Bob a qubit, and an eavesdropper (Eve) tries to measure it before Bob does, there is a chance that Eve’s measurement will change the state of the qubit and Bob will not receive the qubit state Alice sent

* If Alice prepares a qubit in the state |+⟩ and Bob measures it in the  X-basis, he is sure to measure 0
* If Eve eavesdrops and measures it in Z basis, the output changes to |0⟩ or |1⟩, Bob is no longer certain to measure 0
    * If Bob measures 1, he and Alice would be aware of some probelm in the channel

### Minimizing chance of eavesdropping

Repeating the said process an enough number of times. It can be illustrated as follows-

* Step1

Alice chooses a string of random bits (**1000101011010100**) and a random choice of basis (**ZZXZXXXZXZXXXXXX**) for each bit amd keeps the information private to herself

* Step2

Alice encodes a bit of each qubit using the basis she chose (**|1⟩|0⟩|+⟩|0⟩|−⟩|+⟩|−⟩|0⟩|−⟩|1⟩|+⟩|−⟩|+|−⟩|+⟩|+⟩**) and sends the message to Bob

* Step3

Bob measures each qubit using a basis (**XZZZXZXZXZXZZZXZ**) for each qubit and keeps the result private

* Step4

Bob and Alice then publicly share which basis they used for each qubit

If **Bob measured** a qubit **in the same basis Alice prepared it in**, they **use this to form part of their shared secret key**, otherwise they discard the information for that bit

* Step5

Finally, Bob and Alice share a random sample of their keys, and if the samples match, they can be sure (to a small margin of error) that their transmission is successful

# Qunatum Key exchange

Qunatum key distribution exploits certain properties of quantum states to ensure its security. There are several different approaches but they can be divided into two main categories - [Prepare and Measure protocols]() and [Entanglement based protocols]()

# Qiskit implementation

Implementing the protocol in IBM Qiskit (refer to attached Jupyter notebook) to determine whether Alice and Bob can tell if Eve has been trying to listen their quantum messages

* Step1: Alice determines her random bits
* Step2: Alice encodes these in the Z and X bases at random, and sends these to Bob through Eve's quantum channel where Eve intercepts it
* Step3: Eve sends the message to Bob who **measures in the same basis** as Alice
* Step4: Bob and Alice reveal their basis choice
* Step5: Alice and Bob compare their keys to see if they were intercepted
