---
title: "Formalizing LLM Guardrails with AgentSpec in Lean 4"
excerpt: "Executable Lean 4 semantics and 42 machine-checked theorems for AgentSpec, a DSL for runtime enforcement of LLM agent behavior. Fall 2025.<br/>[Paper](/files/agentspec-formal.pdf) · [Code](https://github.com/jfulfo/agentspec-formal)"
collection: projects
---

Sole author. Fall 2025.

[AgentSpec](https://arxiv.org/abs/2503.18666) is a domain-specific language for specifying and enforcing runtime constraints on LLM agents: rules fire on an event, check predicates, and apply enforcements such as stopping the agent, asking the user, or triggering self-reflection.
This project gives AgentSpec an executable semantics in Lean 4, parameterized over predicate tables and external effects, so the results hold whatever predicates a user defines.

It contains 42 machine-checked theorems, with no `sorry`:

- **Safety is compositional in both directions.** Safe rule sets can be developed independently and combined, and a safe combination has safe parts.
- **The safety evaluator correctly implements the violation semantics.** It never blocks an action unless some rule is violated, and when it reports a violation, the rule it names is in the program and was actually violated.
- **Each enforcement type satisfies its contract.** For example, if the user rejects an action it is skipped, and self-reflection stops at its configured depth.
- **Evaluation terminates.**

[Paper (PDF)](/files/agentspec-formal.pdf) · [GitHub repository](https://github.com/jfulfo/agentspec-formal)
