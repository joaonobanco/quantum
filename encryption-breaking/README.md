# Encryption Breaking
This work implements [Shor's algorithm](https://en.wikipedia.org/wiki/Shor%27s_algorithm) to factor semi-primes using quantum circuits implemented in IBM's [Qiskit](https://qiskit.org/). It manages to successfully break the modulus cryptoanalysis of RSA-7 security.

EB-brute-shor.ipynb provides code to compile Shor for circuits of modulus N=15,21,33,35,39,51,55,57,65,69,77,85 and to run in several QC providers from Azure.

EB-rsa.ipynb implements an adaptable RSA-like encryption and decryption mechanism for a message of any lenght.

EB-shor-quantum-check.ipynb evaluates the intermidiate calculations and outputs necessary for understanding the process of the Shor's algorithm for period finding.

EB-shor-quantum-test.ipynb runs a simulator with expected simulation cost.

EB-shor-quantum-ready.ipynb is focused on executing the circuit in quantum hardware.

EB-times.output is the output of the times taken by a Quantum Computer (QC-Aria 16 qubit) for executing the encryption breaking of RSA-1 to RSA-7 security message.
