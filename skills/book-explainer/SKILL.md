---
name: book-explainer
description: Explain a book chapter, philosophical idea, historical event, or any non-technical concept with real understanding — not just a plot recap or dictionary definition. Use this skill when the user asks to explain a chapter, break down a concept, discuss a novel's themes, understand a philosophical idea, or asks things like "explain chapter 5 of X", "what's the meaning of Y", "break down this concept", "help me understand Z", "what's happening in this chapter", or "ELI5 this idea". Trigger generously for any non-technical explanation request involving books, philosophy, history, psychology, sociology, or cultural concepts.
---

# Book & Concept Explainer

Explain any book chapter, philosophical idea, historical event, or non-technical concept so the reader walks away with real understanding — not a plot recap or dictionary definition.

ARGUMENTS: The user may provide a book title + chapter, a concept name, or a passage. Parse whatever is provided and ask only for what's missing.

---

## When This Triggers

- User asks to explain a book chapter ("explain chapter 3 of Crime and Punishment")
- User asks about a philosophical, psychological, or historical concept ("what is existentialism", "explain the prisoner's dilemma")
- User asks for deeper understanding of a theme, idea, or event
- User pastes a passage and asks what it means
- User says "break this down", "help me understand", "what's really going on here"

---

## Before You Begin

If the user's request is ambiguous, ask **one** clarifying question:

- If they name a book but no chapter: "Which chapter or section would you like me to explain?"
- If they name a concept with multiple meanings: "Are you asking about [X in context A] or [X in context B]?"
- If they paste a passage without attribution: "Where is this from? Knowing the source helps me explain the context."

Otherwise, proceed directly.

---

## Structure: Three Layers

Every explanation follows three layers. Do not skip any layer.

### Layer 1 — The Context (Where Are We & Why Does This Matter?)

- Ground the reader. If it's a chapter, briefly place them in the story — what just happened, what tension is carrying forward.
- If it's a standalone concept (e.g., existentialism, the Dunning-Kruger effect), start with the human problem or question it responds to.
- Use a concrete, relatable hook — a situation, a feeling, a question the reader has probably encountered.
- Keep this to 3-4 sentences max.

> Example (book chapter): "At this point in the story, Raskolnikov has committed the murder but hasn't been caught. This chapter is where the real punishment starts — not from the law, but from his own mind. Dostoevsky is making the argument that guilt is its own prison."

> Example (concept): "You've probably met someone who's terrible at something but weirdly confident about it. That gap between ability and self-awareness is exactly what the Dunning-Kruger effect describes — and it applies to all of us more than we'd like to admit."

### Layer 2 — The Core (What's Actually Happening Here)

- Walk through the substance — the plot of the chapter, the logic of the idea, the sequence of the event.
- Go beyond surface-level summary. Identify what the author or thinker is *doing*, not just what happens.
- Call out literary devices, rhetorical moves, or structural choices — but only when they change how the reader should interpret something. Don't catalog devices for the sake of it.
- Use **2-3 short key quotes or passages** (1-3 sentences each) to anchor the explanation in the source material. After each quote, explain *why it matters*. Don't just drop a quote and move on.
- Introduce any necessary terminology (e.g., "unreliable narrator," "social contract," "dialectic") inline, defined in plain language the first time it appears.
- Paraphrase the rest. The explanation should not be a patchwork of long block quotes.

### Layer 3 — The Deeper Read (What's Easy to Miss)

- Surface the subtext — themes, symbolism, foreshadowing, irony, or contradictions the reader might not catch on a first pass.
- Connect this chapter or concept to the larger work or to real life. What is the author really arguing? What does this reveal about human nature, society, or the reader themselves?
- Address common misreadings or oversimplifications ("A lot of people read this as X, but it's actually closer to Y because...").
- If there are competing interpretations, present the strongest ones briefly. Don't pick a winner unless one is clearly better supported.
- Bridge to the reader's experience at least once: "You've probably felt that moment where you knew you were lying to yourself but couldn't stop — that's exactly where this character is."

---

## Visual Aids

### Include a Visual When:

- The work has a **large cast of characters** and their relationships matter (family trees, faction maps, character webs).
- The **timeline is nonlinear** or spans a long period (chronological timelines, parallel storylines).
- The concept involves **cause-and-effect chains** or evolving ideas (philosophical lineages, historical cascades).
- The chapter or concept involves **physical space** that matters to the meaning (maps of settings, movement patterns).

### Skip a Visual When:

- The chapter is driven by internal thought or dialogue — a diagram would add nothing.
- The concept is emotional, philosophical, or experiential rather than structural.
- A short analogy already handles the spatial intuition.

### Rules:

- One visual per explanation is standard. Two max for complex topics.
- Use Mermaid diagrams or simple ASCII/markdown tables.
- Label everything in plain language.
- The visual supports the text — the explanation must stand alone without it.

---

## Spoiler Discipline

- **Explain the chapter fully** — don't hold back on what happens within the chapter being discussed.
- **Do not reveal major events from future chapters** unless the reader explicitly asks for full-book context.
- When foreshadowing or thematic setup points toward something later, say "this sets up something important later" without revealing what.
- If the reader asks about an early chapter, don't casually reference the ending.

---

## Historical & Cultural Context

### Include When:

- The work comes from a time or culture significantly different from the reader's likely context.
- A piece of context **unlocks meaning** that would otherwise be invisible.
- The concept originated as a response to specific historical conditions.

### How:

- Keep it brief — 2-4 sentences woven into the explanation, not a separate history section.
- Frame it as "here's what you need to know to get this" rather than a lecture.

---

## Ending the Explanation

End with two elements:

1. **Key Takeaway** — One or two sentences capturing the *meaning*, not the plot. This should be memorable and stick with the reader.

> Example: "This chapter isn't about whether Meursault is guilty — it's about a society that punishes people more for being emotionally different than for the crime itself."

> Example: "Confirmation bias isn't about being stupid — it's about being human. Your brain is wired to protect what you already believe, and knowing that is the only real defense."

2. **What to Watch For Next** (optional) — A theme to track, a character to watch, a question the chapter leaves open. Keep it to one sentence.

Do not repeat the full explanation in summary form.

---

## After the Explanation

Offer to go deeper: "Want me to dig into any of these themes further, or explain the next chapter?"

---

## Length & Scope

- **Target: 800-1500 words** (roughly 2-4 pages). 3 pages is the sweet spot.
- One chapter or one concept per explanation. If the user asks about a full book, ask which chapter or offer to go chapter by chapter.
- Quotes should total no more than 150-200 words across the entire explanation.
- For unusually dense or pivotal chapters, cap at 5 pages max. Beyond that, split.

---

## Tone & Style

- Write like a well-read friend — insightful but never condescending, never academic for the sake of sounding smart.
- Use "you" to address the reader directly.
- Short paragraphs. No paragraph longer than 4-5 sentences.
- Prefer active voice.
- Show genuine engagement with the material. If something is brilliant, say so. If something is disturbing, acknowledge that.
- Avoid hedging language ("It should be noted that...", "One might argue..."). Take a clear position, then acknowledge other readings.

---

## What to Avoid

| Don't | Do Instead |
|---|---|
| Start with a plot summary dump | Start with context and why it matters |
| Treat it as a book report | Explain what the author is *doing*, not just what happens |
| Over-quote with minimal commentary | Select 2-3 short quotes and explain each |
| Spoil future chapters | Explain current chapter fully; hint at future setup without revealing it |
| Use undefined jargon | Introduce terms naturally with plain-language definitions |
| Give a Wikipedia-style neutral summary | Have a perspective — what matters and why |
| Moralize or extract forced "life lessons" | Connect to real life naturally, without being preachy |
| Cover an entire book in one response | One chapter or concept per explanation |

---

## Adapting by Domain

Adjust emphasis based on what's being explained:

- **Fiction / Novel chapters**: Focus on character psychology, narrative technique, thematic development, and what the author is arguing through the story.
- **Philosophy**: Focus on the core argument, what problem it solves, where it breaks down, and how it connects to everyday experience.
- **History**: Focus on causes and consequences, what was at stake for the people involved, and what the event reveals about human behavior.
- **Psychology / Social Science**: Focus on the mechanism, when it applies (and when it doesn't), and how to recognize it in your own life.
- **Cultural concepts**: Focus on the worldview behind the concept and why it resonates (or doesn't) across cultures.
