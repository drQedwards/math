# 3-SAT is decided exactly, not in polynomial time

## Decision

3-SAT does not inherit the linear algorithm from family 001.

A width-2 clause `(a ∨ b)` is the implication pair `(¬a → b)`, `(¬b → a)`. A width-3 clause `(a ∨ b ∨ c)` is not a pair of implications on the same graph. Routing a ternary clause through that construction either drops a literal or answers the wrong language. The implication-graph procedure is therefore not a 3-SAT decider.

What does decide 3-SAT, on every finite instance, is depth-first search with unit propagation (DPLL). The procedure in `src/three_sat.py` returns a satisfying assignment or, after the binary search tree is exhausted, unsatisfiable. On the instances checked here the answer matches enumeration of all `2^n` assignments.

## Bound

Unit propagation removes forced literals. It does not give a proven polynomial bound. The search tree is still exponential in the worst case. No degree is claimed, because none is known.

3-SAT is NP-complete (Cook, Levin, 1971; the width-3 restriction is Karp, 1972). A polynomial-time decision procedure for it, with a proof, would be a proof that P = NP. This note contains no such proof. A proof that some 3-CNF family requires superpolynomial time on every algorithm would be a proof that P ≠ NP. This note contains no such proof either.

## What was checked

For n from 1 through 10, planted and uniform random 3-CNFs were compared with enumeration. Status matched. Every reported witness satisfied its formula. The eight clauses on three variables that include every possible sign pattern are reported unsatisfiable, and enumeration agrees. The empty formula on four variables is reported satisfiable.

## What stays open

P versus NP. The same three barriers named in family 001 still apply to any claimed resolution: relativization, natural proofs, and algebrization.

## Reference

Martin Davis, Hilary Putnam, A Computing Procedure for Quantification Theory, 1960. The form used here is the later DPLL search with unit clauses propagated before a branch.
