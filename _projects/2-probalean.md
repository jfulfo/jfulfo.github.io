---
title: "ProbaLean: A Probabilistic DSL in Lean 4"
excerpt: "A discrete probabilistic programming language in Lean 4 with denotational semantics over s-finite measures on Mathlib and a machine-checked soundness proof. Spring 2026.<br/>[Paper](/files/probalean.pdf) · [Code](https://github.com/trey3p/probalean)"
collection: projects
---

Joint work with Trey Plante and Zirui Zhou (equal contribution). Spring 2026.

ProbaLean is a discrete probabilistic programming language embedded in Lean 4.
It has two semantics: an executable operational semantics that runs programs as weighted lists of outcomes, and a denotational semantics that interprets programs as s-finite measures, built on Mathlib's measure theory library.
Programs are parameterized by their weight type, so the same program can be run with `Float` or exact rationals, or reasoned about in `ENNReal`.

Machine-checked results:

- **Monad morphism.** The interpretation into the Giry monad preserves the monad laws.
- **Commutativity of independent sampling.** Drawing from two independent programs in either order gives the same measure.
- **Soundness.** The denotational semantics agrees with the operational semantics. When the weights are non-negative rationals, the whole pipeline from execution to denotational correctness is proved without axioms.

[Paper (PDF)](/files/probalean.pdf) · [GitHub repository](https://github.com/trey3p/probalean)
