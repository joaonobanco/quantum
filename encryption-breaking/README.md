# Encryption Breaking

## Motivation
This work implements [Shor's algorithm](https://en.wikipedia.org/wiki/Shor%27s_algorithm) to factor semi-primes using quantum circuits implemented in IBM's [Qiskit](https://qiskit.org/). It manages to successfully break the modulus cryptoanalysis of RSA-7 security.


This research is motivated by the rapid advancements observed in quantum computing technology[^4] capable of harnessing existing quantum algorithms (e.g., Shor[^5]), with the potential in the future[^6] to compromise current asymmetric[^7] cryptography systems (e.g., RSA[^8], ECC[^9]). Although this quantum risk may take time to materialize in practice, the quantum threat looms large - malicious entities can store encrypted communication today for future decryption, taking advantage of the information's extended shelf life (which can span several years in sectors such as banking) and the added time and effort required for security protocol migration.

The current embryonic state of quantum hardware precludes a realistic simulation of attacks on RSA cipher keys. Therefore, in this investigation, an attack is conducted on a simplified version[^10]. As the cipher's security hinges on the difficulty of factoring a number N associated with its keys, the factorization time by varying N is calculated. 

The Shor's algorithm transforms the original problem of factoring a number N into a problem of finding periods[^11]. This algorithm leverages the peculiar way[^12] a quantum computer performs calculations to accelerate the solution's discovery.


[^4]: The metric employed to assess the capability of a quantum computer is Quantum Volume, which has been exponentially increasing each year.

[^5]: Published in 1994, it is an algorithm developed for quantum computers, addressing the factorization problem essential to RSA security.

[^6]: According to the Quantum Threat Timeline Report as of December 14, 2022, over 50% of interviewed experts concur that within 15 years, a quantum computer may feasibly factorize a 2048-bit number in less than 24 hours.

[^7]: The security of symmetric cryptography, due to its more indefinite encryption structure, exhibits greater resistance to Shor's algorithm.

[^8]: Announced in 1977, it boasts a long history of resilience. Since 2015, the NIST has recommended a 2048-bit security public key size for RSA.

[^9]: Proposed in 1985, it offers greater efficiency than RSA while employing smaller keys but exhibits lower compatibility with established infrastructure.

[^10]: Using shorter keys diminishes security.

[^11]: Shor's algorithm transforms a problem of successive attempts into a well-defined structured puzzle, which a quantum computer can globally eliminate incorrect answers.

[^12]: Quantum Computers' advantage in problem solving really shows in problems with a lot of "structure". The quantum calculations are good at finding optimizations in global structure problems.

## Files Description
`EB-brute-shor.ipynb` provides code to compile Shor for circuits of modulus N=15,21,33,35,39,51,55,57,65,69,77,85 and to run in several QC providers from Azure.

`EB-rsa.ipynb` implements an adaptable RSA-like encryption and decryption mechanism for a message of any lenght.

`EB-shor-quantum-check.ipynb` evaluates the intermidiate calculations and outputs necessary for understanding the process of the Shor's algorithm for period finding.

`EB-shor-quantum-test.ipynb` runs a simulator with expected simulation cost.

`EB-shor-quantum-ready.ipynb` is focused on executing the circuit in quantum hardware.

`EB-times.output` is the output of the times taken by a Quantum Computer (QC-Aria 16 qubit) for executing the encryption breaking of RSA-1 to RSA-7 security message.
