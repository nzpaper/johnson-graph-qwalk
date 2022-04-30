# Quantum Random Walk on a Johnson graph
Circuital implementation of a Quantum Random Walk on a Johnson graph J(n,k) using qiskit. More specifically, the solution we have designed is based on Lackadaisical Quantum Walks, by Thomas Wong(http://www.thomaswong.net/). Parts of the code are still relative to the J(4,2) example, a full parametrization is still a WIP.

The oracles used for the search problem are relative to the collision-finding subprocedure of the Finiasz-Sendrier ISD attack.

This is work is based on the Master thesis titled "Design of a Quantum Circuit for Quantum Random Walks on Johnson graphs, Solving the ISD problem for code-based Post-quantum Cryptosystems" by Giacomo Lancellotti (https://github.com/GiacomoLancellotti) and Matteo Lodi (https://github.com/nzpaper), Politecnico di Milano.

Regarding performance, the circuit needs:
- `n` qubits for the state register
- `ceil(log_2(binom(n,2)))` qubits for the coin register

The adapted solution for the shift phase renders the walk too slow when n and k are too large. This is due to the fact that the self-loop weight value of any given vertex in the graph grows quickly and the probability of staying put during the exploration increases too much. We are studying a better solution involving the following paper https://arxiv.org/abs/1912.07353
