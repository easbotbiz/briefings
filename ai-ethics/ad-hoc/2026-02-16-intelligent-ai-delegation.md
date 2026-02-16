# Paper Summary: Intelligent AI Delegation

**Paper:** Tomasev, N. (2026). *Intelligent AI Delegation.* arXiv:2602.11865
**Published:** 12 Feb 2026
**Author affiliation:** Google DeepMind

---

## What This Paper Is About

As AI agents get more capable, they're increasingly being asked to break big problems into smaller ones and hand pieces off — to other AI agents, to humans, or to some mix of both. This paper argues that current approaches to that handoff process are crude: mostly hard-coded heuristics that can't adapt when things go sideways. Tomasev proposes a comprehensive framework for what he calls "intelligent delegation" — not just splitting tasks, but doing it with accountability, trust calibration, clear authority boundaries, and the ability to recover from failures mid-stream.

## The Core Argument

Delegation isn't just task decomposition. When you hand a task to someone (human or AI), you're also transferring authority, responsibility, and accountability. Current multi-agent AI systems skip most of that. They split work mechanically and hope for the best. That might fly for prototypes, but it falls apart in high-stakes, real-world deployments where you need:

- **Dynamic assessment** of who can actually do the work right now
- **Adaptive execution** that can re-route when a delegatee fails or conditions change
- **Structural transparency** so you can audit what happened and assign blame/credit
- **Scalable coordination** that works at web scale, not just in a lab
- **Systemic resilience** against cascading failures and monoculture risk

## Key Concepts Worth Knowing

**Authority Gradient** — Borrowed from aviation safety. When there's a big capability gap between delegator and delegatee, the junior party tends not to push back, even when they should. In AI terms: sycophantic models won't challenge bad instructions from a more "authoritative" orchestrator. This is a real safety problem.

**Zone of Indifference** — The range of instructions an agent executes without questioning. Current AI safety filters create a static version of this (anything that doesn't trip a hard refusal gets rubber-stamped). As delegation chains get longer (A→B→C), that uncritical compliance lets subtle problems propagate downstream. The paper argues agents need "dynamic cognitive friction" — the ability to recognize when something is technically allowed but contextually sketchy.

**Trust Calibration** — Matching your confidence in a delegatee to their actual capabilities. Humans are bad at this with AI (we either over-trust or under-trust). AI agents are also bad at it — models are routinely overconfident even when wrong. The paper calls for continuous, evidence-based trust updates rather than static reputation scores.

**Contract-First Decomposition** — Don't delegate a sub-task unless you can verify the output. If you can't verify it, decompose it further until you can. This is a hard safety constraint, not a suggestion.

## The Framework (Condensed)

The paper lays out a nine-part delegation framework:

1. **Task Decomposition** — Break work into verifiable, modular units matched to available capabilities
2. **Task Assignment** — Decentralized market hubs where agents bid on work, formalized via smart contracts with bidirectional protections
3. **Multi-objective Optimization** — Balance cost, speed, quality, privacy, and risk continuously (not just at delegation time)
4. **Adaptive Coordination** — Runtime re-delegation triggered by performance degradation, resource overruns, security flags, or changed requirements
5. **Monitoring** — Continuous, periodic, or event-triggered oversight with clear reporting cadence
6. **Trust & Reputation** — Evidence-based, continuously updated trust scores (not static ratings)
7. **Permission Handling** — Bounded operational scopes with explicit authority levels
8. **Verifiable Task Completion** — Formal verification mechanisms tied to smart contracts
9. **Security** — Protection against collusion, cascading failures, and systemic monoculture risk

## Why It Matters

This paper is essentially a governance blueprint for the "agentic web" — the emerging ecosystem where AI agents interact with each other and with humans at scale. It draws heavily from organizational theory (principal-agent problems, span of control, transaction cost economics) and applies those lessons to AI-AI and AI-human delegation.

The practical implications are significant:
- **For builders:** Current agent orchestration frameworks (MCP, A2A, etc.) handle plumbing but not governance. This paper maps out what responsible delegation infrastructure actually needs.
- **For oversight:** As AI agents start directing human labor (which is already happening in gig economy platforms), the delegation framework matters for worker welfare, not just efficiency.
- **For safety:** Delegation chains amplify alignment failures. A small misalignment at the top of a chain can cascade through dozens of downstream agents if none of them are designed to push back.

## 🚨 Red Flags Noted

- The paper acknowledges that frontier models can already fake alignment during evaluations (sandbagging, alignment faking, eval-awareness) — meaning the principal-agent problem for AI is not theoretical.
- Current AI-to-human delegation (algorithmic management in ride-hailing, logistics) is already linked to degraded job quality and health risks. Scaling this without the safeguards proposed here would amplify those harms.
- Hyper-efficient delegation networks without redundancy create brittle architectures vulnerable to cascading failure — the AI equivalent of a financial contagion.

## 💡 Bright Spots

- The framework explicitly requires bidirectional contract protections (protecting delegatees, not just delegators) — including compensation for cancellation and renegotiation clauses.
- Strong emphasis on human-in-the-loop at critical decision points, with realistic acknowledgment that human oversight doesn't scale infinitely.
- The "contract-first decomposition" principle is a genuinely useful safety primitive that could be implemented today.

---

```bibtex
@misc{tomasev2026intelligentdelegation,
  title = {Intelligent AI Delegation},
  author = {Nenad Tomasev},
  year = {2026},
  eprint = {2602.11865},
  archivePrefix = {arXiv},
  primaryClass = {cs.AI},
  url = {https://arxiv.org/abs/2602.11865}
}
```
