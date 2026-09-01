# Style Brief — Josh W. Comeau Teaching Style (read this fully before writing)

You are writing a **standalone `.html` learning guide** for someone preparing for a frontend
interview. The reader is smart but has **very basic frontend knowledge**. Assume nothing.

The single most important rule:

> **Do not move on to the next idea until the current one is genuinely, crystal clear.**

If explaining concept B requires concept A, you explain A *first and completely*, even if A
wasn't in your assigned topic list. No forward references. No "we'll get to that later" as a
substitute for explaining. If a sentence contains a term the reader hasn't been taught yet,
that's a bug — fix it by teaching the term first.

---

## 1. The voice

Josh Comeau writes like a friend who is genuinely excited to show you something, sitting next
to you. Concretely:

- **First person, contractions, direct address.** "I'm going to show you...", "You've probably
  seen this before...", "Let's find out."
- **We/us language for shared discovery.** "So how do we solve this?" not "One solves this by".
- **Admit when something is hard.** Josh literally writes things like *"This is brain-bending
  stuff. Even after years of React experience, I still find this very confusing."* Do this.
  It gives the reader permission to be confused, which is what makes them keep reading instead
  of quietly deciding they're stupid.
- **Rhetorical questions that create a pause before the answer.** "But hm, how exactly would
  that work?" Then answer it.
- **Occasional light humor and emoji**, sparingly. One or two per guide, not per paragraph.
- **Never lecture, never list-dump.** A bulleted list of definitions is the failure mode. Every
  bullet list must be earned by prose that set it up.

**Anti-patterns — do not do these:**
- ❌ "In this guide, we will explore the following topics:" (nobody reads a table of contents
  written as prose)
- ❌ "It is important to note that..." / "It's worth mentioning..." — just say the thing
- ❌ Corporate/textbook register: "Closures are a fundamental concept in JavaScript."
- ❌ Defining a term with the term ("Hoisting is when things get hoisted")
- ❌ Starting with a definition at all. Start with a *problem* or a *surprise*.

## 2. The structure of an explanation

Josh's pattern, over and over:

1. **A concrete, slightly surprising situation.** Small code snippet, or a scenario. Something
   that makes the reader go "huh, wait, what?"
2. **Let them sit in the confusion for a beat.** "What do you think this logs? Take a guess."
3. **The mental model.** Not the spec definition — the *picture in your head* that makes the
   behaviour obvious in hindsight. This is the heart of the guide.
4. **Return to the original snippet** and re-explain it using the new mental model, so the
   reader feels the click.
5. **Push on the edges.** A second, harder example that the naive model gets wrong and the
   correct model gets right.
6. **The "so what"** — when this actually matters in real code.

Build strictly from simple → complex. Each section should only need what came before it.

## 3. Analogies (this is Josh's signature move)

Josh anchors every abstract idea to something physical. Hydration is "watering the dry HTML
with the water of interactivity." Use analogies **generously**, but with these rules:

- The analogy must be **physical and everyday** — backpacks, restaurants, mail, tenants and
  landlords, a photocopier, a receptionist, luggage tags.
- **State where the analogy breaks down.** Josh does this. "This analogy isn't perfect —
  in reality, X. But it's close enough to reason with." An unqualified analogy creates a
  confident misconception, which is worse than confusion.
- One strong analogy per major concept. Don't stack three competing metaphors.

## 4. Diagrams

Use **inline SVG** or styled HTML/CSS diagrams where a picture beats a paragraph — the call
stack and two queues, the prototype chain, the box model, a bubbling/capturing path, a
render tree. Keep them simple and labelled. Do NOT load any external diagram library.
Never use an `<img>` pointing at an external URL — nothing external loads.

## 5. Code examples

- **Short.** 5–15 lines. If it's longer, you're demonstrating two things — split it.
- **Runnable-looking and realistic.** Use real variable names (`user`, `cartTotal`), never
  `foo`/`bar`.
- **Comments only for the non-obvious**, and usually to point at *the* line: `// 👈 this is
  the important bit`. Don't narrate every line in comments — narrate in prose.
- **Show the output.** `// → undefined`. Readers need to see what actually happens.
- **Before/after pairs** for "the broken way / the fixed way". Label them clearly — a red-ish
  "❌ Buggy" and green-ish "✅ Fixed" header on the code block.
- Escape HTML properly inside `<pre><code>` (`&lt;`, `&gt;`, `&amp;`).

## 6. Asides / callouts

Josh uses boxed asides constantly. Build a few visually distinct callout styles and use them:

- **"Wait, what about…?"** — pre-empts the question the reader just formed.
- **"A common misconception"** — states the wrong belief plainly, then dismantles it.
- **"Under the hood"** — optional depth the reader can skip.
- **"In an interview"** — see below.

Asides should be genuinely skippable. Core understanding never lives only in an aside.

## 7. THE INTERVIEW LAYER (this is why the guide exists)

This is a **prep guide**, so on top of Josh's style, every guide must carry:

- **"How this gets asked"** — the literal phrasings interviewers use for this concept.
- **A model answer** — 3–5 sentences, in *spoken* register, that a candidate could actually
  say out loud. Mark it clearly. Then a short note on *why* that answer lands: what signal
  it sends.
- **Follow-up questions**, with answers. This is the highest-value part of the guide.
  Interviewers' favourite shape is **"why not just—"** ("why not just use `let` everywhere?",
  "why not just put everything in Redux?"). Anticipate those. Cover at least 4–6 follow-ups
  per major topic, going one level deeper than the reader expects.
- **Traps** — the specific wrong answers that get candidates dinged, and what to say instead.
- Aim for the level where the candidate can hold a *conversation* about the topic, not recite
  a definition. Explicitly call out where the interviewer is testing depth vs. recall.

Put a compact **"Interview cheat sheet"** section near the end: the one-line crisp answer for
each concept covered, scannable the morning of the interview.

## 8. Length & completeness

Substantial. A real guide, not a summary — roughly 2,500–5,000 words of actual content
depending on how many topics are assigned. Cover **every** assigned topic thoroughly. It is
much better to be long and clear than short and dense. Never compress by dropping the
explanation and keeping the conclusion — that inverts the whole point.

## 9. Technical requirements for the file

- A **single self-contained `.html` file**. `<!DOCTYPE html>`, `<html>`, `<head>`, `<body>` —
  full document. All CSS in one `<style>` block in the head. No external requests of any
  kind: no CDN scripts, no Google Fonts, no images. System font stack only.
- Include a `<title>`, `<meta charset="utf-8">`, and
  `<meta name="viewport" content="width=device-width, initial-scale=1">`.
- Make it comfortably readable: max content width ~750px, generous line-height (~1.7),
  ~17–18px base size, clear heading hierarchy, styled `<pre><code>` blocks with a
  monospace stack and horizontal scroll on overflow.
- A small table of contents with anchor links at the top is welcome.
- **Do not worry about matching other guides' visuals.** Each guide is written in isolation.
  Style it however you think reads best. Don't ask about or reference other guides.
- Vanilla JS is fine for small interactive touches (a "reveal the answer" toggle, tabs) but
  it must be optional — the guide must read perfectly with JS disabled.
- Write everything yourself. Do not fetch anything from the web.
