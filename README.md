# Häggkvist–Janssen list edge colouring of complete graphs

Lean formalization of the classical bound **χ′ₗ(Kₙ) ≤ n**. Every finite list
assignment on the edges of a complete graph, with at least n colours in each
list, admits a proper edge colouring choosing from those lists. The conclusion
uses Mathlib's actual edge type and line-graph colouring; the colour type is
arbitrary and orders zero and one are included.

Main theorem:
`LeanPool.ListEdgeColoringComplete.exists_listEdgeColoring_complete`.

## Proof and attribution

The theorem is due to Roland Häggkvist and Jeannette C. M. Janssen,
*The list chromatic index of K_n and K_{n,n}*, Combinatorics, Probability and
Computing 6 (1997), 295–313, [doi:10.1017/S0963548397002927](https://doi.org/10.1017/S0963548397002927).
This repository covers the complete-graph case, not the bipartite theorem
or the general list-edge-colouring conjecture.

The proof is an alternative presentation, not a literal translation of the
article's argument: a direct local-rank construction and uniqueness induction
provide a nonzero extended-star polynomial coefficient, followed by Mathlib's
combinatorial Nullstellensatz and a native graph-colouring adapter. The
classical theorem is not claimed as new mathematics.

The Lean proofs were produced with Aristotle and local AI-assisted development
and review, under Juan Pablo Traverso Gianini's direction. Aristotle project:
`36dbf0e5-9462-4621-9741-2f865d35bbbf`.

## Build

Pinned Lean: `v4.35.0-rc3`.
Pinned Mathlib commit: `c55e6e786f49471c72fbddbec5415808896aec1e`.

```sh
lake exe cache get
lake build LeanPool.ListEdgeColoringComplete.Imports
```

The contribution passed a targeted local build without warnings, the Lean Pool
declaration linter, and axiom and environment audits. The theorem's axiom
footprint is `[propext, Classical.choice, Quot.sound]`; no project axiom or
unproved certificate is assumed. These are local checks, not independent
peer review or a clean-room recompilation of Mathlib.

## Files and license

`Basic` supplies numerical data, `Certificate` proves the combinatorial
certificate, `Polynomial` develops the coefficient argument, and `Main` proves
the list-colouring theorem. `Imports` is the complete import-only index.

All contributed Lean code is licensed under Apache-2.0; see [LICENSE](LICENSE).
The original article and its PDF are not redistributed here.
