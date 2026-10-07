# math

Notes and checked procedures from Dr. Q. This repository is not a claim on the Clay Millennium problems.

The first family is a decision procedure for 2-SAT. It always answers, and the number of steps is linear in the number of variables plus the number of clauses. That is a polynomial of degree 1. Width-three SAT is a different problem, and this procedure does not solve it.

## Catalogue

| Family | Subject | Status |
| --- | --- | --- |
| 001 | 2-SAT is decidable in linear time | Checked against brute force for n ≤ 10 |
| 002 | 3-SAT is decided exactly, not in polynomial time | Checked against brute force for n ≤ 10 |

Start with [CONTENTS.md](CONTENTS.md). Family 001 is [preprints/2-sat-linear](preprints/2-sat-linear/paper.md) and [src/two_sat.py](src/two_sat.py). Family 002 is [preprints/3-sat-exact](preprints/3-sat-exact/paper.md) and [src/three_sat.py](src/three_sat.py).

```bash
python tests/test_two_sat.py
```

## What this is not

P versus NP is open. A polynomial algorithm for 2-SAT has been known since Aspvall, Plass, and Tarjan (1979). Publishing another implementation does not move the Millennium problem. The OpenAI catalogue at [github.com/openai/math](https://github.com/openai/math) is a separate collection; family 102 there is an approximation-hardness claim for Max-Cut, not a separation or a collapse of P and NP.

License: MIT.
