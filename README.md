# Alternative parameter sets for SPHINCS+ / SLH-DSA

This repository contains the results of the parameter search for parameter sets for SPHINCS+, which support a lower number of maximum signatures before
security degrades. This may allow much more beneficial trade-offs if only a small number of signature per key pair are actually needed. For more
details see .

The files here are named x_y.out, where x is the security target (i.e. 128, 192 or 256-bit) and y is the maximum number of signatures for which this security level is guaranteed.
Each file contains one parameter set per row, and consists of 10 columns, which corresponds to the following entries:
1) Signature size: Given in bytes and rows are sorted by this ascending.
2) Signing speed: Number of hash calls for signing. The search is limited to < 10^9 calls, which corresponds to roughly < 1 min signing on a modern CPU.
3) Verification speed: Number of hash calls for verification.
4) Probability for FORS forgery after 2^y signatures.
5) The parameter h in SPHINCS+.
6) The parameter d in SPHINCS+.
7) The parameter b in SPHINCS+.
8) The parameter k in SPHINCS+.
9) The parameter w in SPHINCS+.
10) Security degradation: The value `z` such that after 2^z signatures, the forgery probability is still < 2^{-112, 128, 192} (for a security target of 128, 192, 256 bits).
