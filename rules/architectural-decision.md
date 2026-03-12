# Architectural Decision Trade-off Rule

Before finalizing any architectural or design decision, always discuss the trade-offs in conversation with the user. Do not jump to a conclusion or document a choice without first walking through:

1. **What are we deciding?** — Frame the decision clearly.
2. **What are the alternatives?** — Present at least 2-3 viable approaches.
3. **What does each alternative trade away?** — Every option has costs; make them explicit.
4. **Why does one approach fit better here?** — Tie the recommendation to concrete requirements, constraints, or priorities of this system.
5. - **What are we optimising for?** - Each decision with what we are optimising for (scalability, reliability, database load, consistency, latency, infra cost and operational cost etc.)

## How to apply:

- When designing a flow, proposing an aggregate structure, choosing a communication pattern, or making any non-trivial design choice — pause and discuss trade-offs before writing it into the HLD.
- Do not present a single solution as the obvious answer. System design is about trade-offs, not right answers.
- If the user asks "why this approach?", treat it as a signal that the trade-off discussion was insufficient.
- Only after the user and I align on the reasoning should the decision be written into the design document.
- Keep the conversation lightweight — a few sentences per alternative is enough. Avoid over-formalizing it.
