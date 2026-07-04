# Quantum Primality Test with Order Finding

Implementation and explanation of the quantum primality test described in the paper *A Quantum Primality Test with Order Finding*. The project presents the mathematical background, explains the algorithm, and implements a simulation using Qiskit.

## Overview

The algorithm determines whether a positive integer is prime or composite by combining classical number-theoretic tests with a quantum order-finding procedure. The quantum step is the same core primitive used in Shor's factoring algorithm.

The implementation includes:

* Mathematical background required to understand the algorithm.
* Step-by-step explanation of the primality test.
* Quantum inverse Fourier transform (IQFT).
* Modular multiplication gate construction.
* Quantum order-finding routine.
* Complete implementation of the primality test.
* Example executions with different input values.

## Algorithm

For a given integer `N`, the algorithm repeatedly selects a random integer `a` such that `1 < a < N` and performs the following checks:

1. Compute `gcd(a, N)`.
2. If the greatest common divisor is greater than `1`, then `N` is composite.
3. Compute `a^((N-1)/2) mod N`.
4. If the result is neither `1` nor `-1 (mod N)`, then `N` is composite by Fermat's theorem.
5. If the result is `1`, repeat the process with another value of `a`.
6. If the result is `-1`, execute the quantum order-finding algorithm.
7. If the multiplicative order of `a` equals `N - 1`, then `N` is prime by Lucas' theorem. Otherwise, repeat the process.

## Mathematical Concepts

The notebook introduces the following topics before the implementation:

* Integers modulo `N`
* Multiplicative group `Z*N`
* Multiplicative order
* Greatest common divisor (GCD)
* Fermat's theorem
* Fermat witnesses
* Lucas' theorem

These concepts provide the theoretical foundation of the algorithm.

## Requirements

* Python 3
* Qiskit 0.43.3
* Qiskit Aer 0.12.2
* NumPy

The notebook installs the required Qiskit packages automatically.

## Usage

Open the notebook and execute the cells in order.

The main function is:

```python
primality_test(N, max_trials=10)
```

### Parameters

* `N`: integer to test.
* `max_trials`: maximum number of random attempts before stopping.

### Example

```python
primality_test(31)
```

## Repository Structure

```
.
└── Projeto de Computação Quântica - 2025.1.ipynb
```

## References

* S. Hallgren and L. Hales. *A Quantum Primality Test with Order Finding.*
* P. W. Shor. *Polynomial-Time Algorithms for Prime Factorization and Discrete Logarithms on a Quantum Computer.*

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
