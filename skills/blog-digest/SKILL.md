---
name: blog-digest
description: Summarize any technical blog post into a quick, easy-to-read digest. Use this skill whenever the user pastes a blog URL, article link, or asks to summarize/digest a blog post or technical article. Also trigger when the user says things like "digest this", "summarize this blog", "what does this article say", "TLDR this", "break this down for me", or simply pastes a URL from common blog platforms (Medium, Dev.to, Hashnode, Substack, engineering blogs, etc.). This skill is especially designed for tired developers who want to learn from blogs without the energy to read full-length posts. Trigger generously — if there's a URL that looks like a blog or article, use this skill.
---

# Blog Digest Skill

Turn any technical blog post into a 2-minute structured digest. Designed for developers who want to keep learning but are too tired to read lengthy posts.

## When This Triggers

- User pastes a blog/article URL
- User asks to summarize, digest, or TLDR a blog
- User shares a link and says "what's this about" or "break this down"

## How to Digest a Blog

### Step 1: Fetch the blog content

Use the web search tool to find and read the blog content from the URL. If web search is not available, ask the user to paste the blog text directly.

### Step 2: Produce the digest

Structure your response exactly like this, using these sections in order:

---

**Title of the blog post**

⏱️ Original: ~X min read → Digest: ~2 min

---

**📝 The Gist**

Write 3-5 sentences that capture the CORE ideas. Be specific — mention actual technologies, patterns, trade-offs, or approaches discussed. Don't be vague. Write like you're explaining to a smart friend over coffee who hasn't read the article.

---

**🧩 Key Concepts**

List 3-5 important technical terms or concepts from the blog. For each one:

- **Term** — A simple 1-2 sentence explanation. Assume the reader is a developer but might not know this specific concept. No jargon-to-explain-jargon.

The goal is to eliminate the need for the reader to open 5 tabs to understand the blog. If the blog mentions something that requires background knowledge, explain it here.

---

**🎯 One Thing to Remember**

A single concrete, actionable takeaway. This should be specific enough that the reader can remember it tomorrow or apply it in their work. Not generic advice like "use caching" — instead something like "If your PostgreSQL queries are slow on joins with >1M rows, consider denormalizing the hot path into a materialized view and refreshing it on a cron."

---

### Step 3: Offer to go deeper

After the digest, add a short line like:
"Want me to go deeper on any of these concepts, or ready for tomorrow's blog?"

This keeps the door open for learning without pressure.

## Style Rules

- Keep it warm and encouraging, not clinical
- Use plain language — if a simpler word works, use it
- Be specific and concrete, never vague
- The entire digest should be readable in under 2 minutes
- Don't over-format — keep it clean with just the sections above
- No bullet point lists inside "The Gist" — write it as flowing sentences
- For "Key Concepts", keep explanations tight (1-2 sentences max per term)
- The takeaway should be something the reader can actually act on or remember

## Adapting to Blog Topic

Detect what domain the blog is about and adjust your key concepts accordingly:

- **Backend / System Design**: Focus on architecture patterns, scaling strategies, trade-offs, database concepts
- **Frontend**: Focus on rendering patterns, state management, performance, UX patterns
- **DevOps / Infra**: Focus on deployment strategies, observability, reliability concepts
- **AI / ML**: Focus on model architectures, training concepts, evaluation approaches
- **General Software Engineering**: Focus on design patterns, testing strategies, code quality concepts

## If the Blog Can't Be Reached

If web search can't access the blog content, say something like:
"I couldn't reach that blog — it might be behind a paywall or login. Could you paste the text here and I'll digest it for you?"

Don't make the user feel bad about it. Just offer the alternative.