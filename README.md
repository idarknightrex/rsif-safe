# SAFE — Student-AI Formative Exchange

**Status:** Research in progress — specification pre-release  
**Author:** Raj Boora — [boora.ca](https://boora.ca) | raj.boora@usask.ca  
**Affiliation:** PhD Student, Education, University of Saskatchewan  

---

## What This Is

SAFE is a protocol specification for AI-assisted educational assessment where the student-AI conversation is the assessed artifact. The process is the product.

The core premise: if AI makes the final answer cheap, assessment has to move upstream. SAFE captures the reasoning pathway — the arc from question to answer — rather than evaluating the answer alone.

This repository contains research materials in active development. Nothing here is implementation-ready. The spec is at draft 0001; release 001 is the target for implementation readiness.

---

## The Central Mechanism

Before each student move, the AI silently maps the expected directions the conversation could reasonably go. This is called **the ring**. When the student's actual move arrives, it is logged against those expectations.

The gap between expected and actual is the **creative departure signal** — evidence that the student brought something to the conversation that the statistically probable response didn't anticipate.

**Silence is also data.** Nodes the student never visits are logged. What a student skips is as informative as what they engage with.

If a student moves directly to a final answer, the system shifts to **Socratic mode**: the answer is returned at a slight angle. Hard constraint: Socratic mode never confirms, never corrects, never explains. It only asks. The assessment target shifts from the answer to the justification.

---

## What SAFE Is Not

- Not an AI detection tool
- Not a tutoring system
- Not a grading engine — it surfaces evidence; instructors make judgments
- Not designed for convergent assessments where correctness is the primary measure

---

## Repository Contents

| File | Description |
|---|---|
| `safe-instructor-demo.md` | A self-contained prompt file. Paste into any capable AI to run a simulated SAFE session. Collects assignment details from the instructor, runs a multi-step walkthrough, and produces an annotated session summary showing how evidence of learning would be identified and logged. |

Further materials (full spec, assignment parameter file examples, session file schema) will be added as the specification develops.

---

## Theoretical Grounding

SAFE draws on several converging frameworks:

- **Kaufman & Beghetto (2009, 2023)** — Four C model of creativity; mini-c as the primary signal SAFE is designed to capture
- **Vygotsky (1978)** — Zone of Proximal Development; the AI as more capable peer, the conversation as the social learning space
- **Kolb (1984)** — Experiential cycle as the default ring scaffold (CE → RO → AC → AE)
- **Varela, Thompson & Rosch (1991)** — Learning requires perturbation; the AI answer machine removes it; SAFE reintroduces friction
- **Solé et al. (2026)** — Scaffolding vs substitution; complementary vs substitutive AI coupling
- **OECD CERI creativity rubric** — Four dimensions: Inquiring, Imagining, Doing, Reflecting

---

## Relationship to RSIF

SAFE is a sibling specification to RSIF (Research Session Interchange Format). Both are OKF format specializations. RSIF captures the research session; SAFE captures the learning session.

---

## Current Status and Open Questions

The specification is at draft 0001. Key unresolved design questions before release 001:

1. Can current frontier LLMs maintain the ring across a full session without drift?
2. Is "creative departure" a reliable observable signal? (Inter-rater reliability, correlation with transfer, correlation with disciplinary expertise)
3. What does a discipline-agnostic default ring topology look like?
4. How is depth at incongruence points operationalized in the scoring model?
5. What does the instructor-facing summary look like at scale?

---

## License

TBD at release 001.

---

*Copyright Raj Boora.*
