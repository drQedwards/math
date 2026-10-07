# 2-SAT is decidable in linear time

## Statement

Let a 2-CNF on n variables be a conjunction of m clauses, each a disjunction of two literals. There is a deterministic procedure that decides satisfiability, and returns a satisfying assignment when one exists, using a number of steps bounded by a constant times n + m.

## Procedure

A clause (a ∨ b) is equivalent to the two implications (¬a → b) and (¬b → a). Build the implication graph on 2n vertices, one for each literal. Compute the strongly connected components (Kosaraju). The formula is unsatisfiable if and only if some variable x and its negation lie in the same component. Otherwise set x true exactly when the component index of x is strictly greater than the component index of ¬x, under the numbering produced by processing vertices in reverse finish order on the transpose graph.

Each vertex and each edge is visited a constant number of times. The edge count is 2m. The bound is O(n + m).

## What was checked

For n from 1 through 10, planted and uniform random formulas were compared with enumeration of all 2^n assignments. Status and, when satisfiable, the returned assignment matched. The four clauses (x ∨ y), (x ∨ ¬y), (¬x ∨ y), (¬x ∨ ¬y) are reported unsatisfiable, with the conflict on x.

A separate run at n = 300, three clauses per variable, planted, returned a satisfying assignment. The operation count divided by n + m stayed a small constant. That measurement is consistency with the linear bound. It is not a proof that every implementation is linear, and the proof of linearity is the graph argument above, not the timing.

## What this does not decide

A clause of three literals does not split into two implications. 3-SAT is NP-complete (Cook, Levin, 1971). The procedure in this note does not accept a 3-CNF. Karp’s reductions put vertex cover in the same completeness class. No step here shows that every problem in NP has a polynomial algorithm, and none shows that one does not.

The three standard barriers still apply to any claimed resolution of P versus NP: relativization (Baker, Gill, Solovay, 1975), natural proofs (Razborov, Rudich, 1997), and algebrization (Aaronson, Wigderson, 2008).

## Reference

Bengt Aspvall, Michael F. Plass, Robert Endre Tarjan. A linear-time algorithm for testing the truth of certain quantified boolean formulas. Information Processing Letters, 8(3), 1979.
