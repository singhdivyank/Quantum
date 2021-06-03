# Shor's factoring algorithm

It factors integers in polynomial time and is primarily used for solving problems of the type: **given an integer n find its prime factors**

# Period finding

Since a factoring problem can be turned into a period finding problem in polynomial time, an efficient period finding algorithm can be used to factor integers efficiently too. Finding the period of **a<sup>x</sup> mod N** efficiently means we can efficiently factor.

This algorithm uses [quantum phase estimation](https://qiskit.org/textbook/ch-algorithms/quantum-phase-estimation.html) on unary operator to approach the problem in O(n<sup>2</sup> logn loglogn)

## Parts of the algorithm

1. A **reduction that can be done on a classical computer**, of the factoring problem to the problem of order-finding

* Pick a random number 1<a<N
* Using [Euclidean algorithm](https://en.wikipedia.org/wiki/Euclidean_algorithm) compute gcd(a, N)
    * if(gcd!=1) factor is non-trivial and we are done

* Use ![period finding subroutine](https://upload.wikimedia.org/wikipedia/commons/thumb/6/6b/Shor%27s_algorithm.svg/450px-Shor%27s_algorithm.svg.png) to find r, the period
    * if(r is odd) back to step 1
    * if(a<sup>r/2</sup> = -1(mod N)) back to step 1
        * Otherwise both gcd(a<sup>r/2</sup> + 1, N) and gcd(a<sup>r/2</sup> - 1, N) are non-trivial factors of N and we are done
                             
2. A **quantum algorithm to solve order-finding problem**

# Circuit diagram

![](https://qiskit.org/textbook/ch-algorithms/images/shor_circuit_1.svg)
