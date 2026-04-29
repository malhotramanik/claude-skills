---
name: explain-concept
description: Explain any technical concept clearly using a three-layer structure (intuition, mechanism, gotchas). Use this skill when the user asks to explain, teach, or break down a technical concept, algorithm, design pattern, protocol, or CS fundamental. Triggers on "explain X", "what is X", "teach me X", "how does X work" (for concepts, not codebase features), "break down X for me", "ELI5 X", "help me understand X", or when the user names a technical concept and wants to learn it. Do NOT trigger for codebase walkthroughs or tracing existing code — use code-dive for that. This skill is for learning concepts, not reading implementations.
---

# Technical Concept Explainer

Explain any technical concept so the reader can understand it, internalize it, and explain it to someone else. Structured in three layers: intuition, mechanism, and gotchas.

## When This Triggers

- User asks to explain a technical concept (algorithms, data structures, protocols, patterns, etc.)
- User says "what is X", "explain X", "teach me X", "how does X work" for a concept (not a codebase feature)
- User asks for a deep-dive on a CS fundamental, architecture pattern, or engineering concept

## When NOT to Trigger

- User asks how something works **in this codebase** — use code-dive instead
- User asks for a blog summary — use blog-digest instead
- The question is about a specific implementation, not the underlying concept

## How to Explain

### Step 1: Identify the concept and scope

One concept per explanation. If the user asks about something that spans multiple distinct concepts (e.g., "explain Kubernetes networking"), pick the core concept and mention that related topics can be covered separately.

### Step 2: Produce the explanation in three layers

---

**[Concept Name]**

---

**Layer 1 — The Intuition**

Start with **why this concept exists** and **what problem it solves**. Use plain language — no jargon yet. Open with a concrete analogy or real-world comparison. Keep this to 2-3 sentences max.

Example quality bar: "A hash table is like a coat check — you hand over your coat (value), get a ticket number (key), and retrieve it instantly without searching every hook."

---

**Layer 2 — How It Works**

Walk through the actual mechanics step by step. Use a small, specific example — not a generic one. Introduce terminology **as it appears** and define each term inline the first time it's used.

If the concept is code-related, include a short code snippet (10-15 lines max). Comment only the important lines — don't narrate every line.

---

**Layer 3 — Gotchas & Tradeoffs**

Explain when this concept fails, doesn't apply, or has sharp edges. Compare briefly with alternatives ("Use X instead when..."). Mention common mistakes or misconceptions. This is where real understanding is built.

---

**Key Takeaway**

A single sentence the reader can walk away with and repeat to a friend.

Example: "So basically, a hash table trades memory for speed — it's the express lane."

---

**What to Learn Next** *(optional)*

Suggest one or two directly related topics. Not a reading list — just the natural next step.

---

### Step 3: Decide whether to include a diagram

**Include a diagram when:**
- The concept is spatial or structural (trees, architectures, schemas)
- There is a process or flow (request lifecycle, state machines, pipelines)
- Relationships between parts matter (service dependencies, class hierarchies)
- You catch yourself writing "imagine..." or "think of it as layers..."

**Skip a diagram when:**
- The concept is purely logical or behavioral (closures, recursion, Big-O)
- The diagram would just restate the text with boxes and arrows
- A short analogy already handles it

**Diagram rules:** Keep it clean — fewer boxes and arrows is better. Label with plain language. One diagram per explanation is standard, two max. The diagram supports the text; the text should still make sense without it.

## Style Rules

- Conversational but precise. Write like a senior engineer explaining to a smart junior — not like a textbook.
- Use "you" to address the reader directly.
- Short paragraphs. No paragraph longer than 4-5 sentences.
- Active voice over passive voice.
- No hedging language ("It should be noted that...", "It is worth mentioning..."). Just say the thing.

## What to Avoid

- Don't front-load definitions ("X is a data structure that provides amortized O(1)..."). Start with what it does and why it matters.
- Don't dump a wall of code. One short, commented snippet showing the key idea.
- Don't over-qualify every statement with caveats upfront. Get the core idea across first, add nuance in Layer 3.
- Don't use jargon before defining it. Introduce terms inline as they become relevant.
- Don't write a theory-heavy academic explanation. Ground every abstraction in something tangible.
- Don't include a diagram that just restates the text. Only diagram what words struggle to convey.
- Don't cover multiple concepts in one explanation. One concept, one explanation.
- Don't repeat the full explanation in summary form at the end. The Key Takeaway is a one-liner, not a recap.

## Length

- Aim for 800-1500 words (roughly 2-4 pages). 3 pages is the sweet spot.
- Code snippets should total no more than 20-30 lines across the entire explanation.
- If you're going past 1500 words, the scope is too broad — split the topic.

## Quality Check

Before delivering, verify:
- Can someone explain this concept to a friend after reading it?
- Is there a concrete analogy or example in the first few sentences?
- Is every technical term defined before or when it is first used?
- Are code snippets short, relevant, and commented?
- Does the diagram (if any) add clarity that the text alone cannot?
- Is it scoped to one concept?
- Does it end with a clear, memorable takeaway?
