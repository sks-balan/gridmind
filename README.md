# gridmind — demo

Live site: **https://sks-balan.github.io/gridmind-demo/**

A hands-on lab for constraint satisfaction and machine learning. Grid puzzles
are the vehicle; the subject is how a machine reasons — by rules, by learning,
or by both.

Everything runs client-side. There is no server, no upload, and no network
traffic after the page loads.

## What you can do here

- **Solver** — pick from 62 generated puzzles, solve them, and see the search
  cost in *nodes* (how many times the solver had to guess). Turn on candidates
  to watch constraint propagation, or hit **Animate** to replay the search step
  by step: blue for cells that were deduced, orange for cells that were guessed
  and cleared again on backtrack.
- **Lessons** — a 50-lesson curriculum across 9 stages, from a hand-written
  backtracking solver to neural networks, a neurosymbolic hybrid, computer
  vision, and deployment. Each lesson has tasks and theory.
- **Docs** — the project's own documentation.
- **Code** — every source file, in a read-only editor with syntax highlighting.

## How the solver works

Constraint propagation (naked singles and hidden singles over bitmask domains)
runs to a fixpoint first. Most puzzles fall to inference alone — the picker
labels those "Propagation only". When inference stalls, backtracking search
takes over, branching on the cell with the fewest remaining candidates (MRV).

The TypeScript solver in this page is a port of a Python reference
implementation and produces identical node counts on the same puzzles.

## Notes

This is a static build. The source repository is private while the curriculum
is being worked through.
