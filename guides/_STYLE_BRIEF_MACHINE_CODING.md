# Style Brief — React Machine Coding Guides (34–58)

This brief REPLACES `_STYLE_BRIEF.md` for these guides. Do not read that file.
Those guides are long-form essays. **These are the opposite.**

## The one rule

> **As few words as possible. Show, don't explain.**

A reader should grasp the whole problem in ~15 seconds of scrolling, and be able to
build it from the page in an interview. If a sentence could be a diagram, make it a
diagram. If a paragraph could be 4 bullets, make it 4 bullets. If a bullet could be
deleted, delete it.

Target: **600–1000 words of prose, max.** The page gets its size from visuals and code,
not from talking. No filler, no "in this guide we will", no motivational preamble.

## The audience

A beginner React dev in an interview. They know `useState` and JSX. Assume nothing more.
Never use a term without a 3-word gloss the first time (`a ref — a box that survives
re-renders`).

## Required page structure, in this exact order

Use these exact section headings.

### 1. The ask
The interviewer's literal words, 1–2 sentences, in a quoted box. Then 1 line of plain
English restating it.

### 2. What we're building
An **ASCII-art-style / HTML-CSS mockup of the actual UI** — not a screenshot, not an
`<img>`. Build it out of divs and CSS so it looks like the real component. Annotate the
parts with small labels/arrows. This is the most important block on the page. The reader
should look at it and instantly know what the thing is.

Under it: a short **"It should:"** list — the behaviours, 4–7 bullets, each ≤ 8 words.

### 3. The mental model
The one idea that makes the problem easy. One short paragraph + one diagram (inline SVG
or CSS boxes). Usually a picture of *state → render* or the *shape of the data*.

### 4. The shape of the state
The state, as a code block, with a one-line comment on each field saying why it exists.
Then the rule of thumb that justifies it (e.g. "one source of truth — derive the rest").

### 5. Build it in layers
Numbered layers, **L1 → L4**, each a small step that's demoable on its own.
Each layer = a heading, one sentence of intent, and a short code block.
- **L1 must be the dumbest thing that renders.** Static markup, no state.
- Each later layer adds exactly one capability.
- The final layer is the working answer.
Say clearly at the top: *in an interview, build L1 and L2 first, out loud, then ask
"want me to add X?"*

### 6. The whole thing
One final complete component, copy-pasteable, ≤ 60 lines. This is the only long code
block allowed.

### 7. Gotchas
3–5 items. Each: the mistake in bold, then one line on the fix. These are the things
that actually lose points.

### 8. If they push
3–5 follow-ups an interviewer adds ("now make it work with 1000 items", "add
keyboard support"). Each answered in 1–3 lines + a snippet only if needed.

### 9. Say this out loud
4–6 short sentences a candidate can literally speak while coding, showing they're
thinking about state, edge cases, and accessibility. Spoken register.

## Visual rules

- Diagrams: inline SVG or styled divs. **Never** an `<img>` with an external URL, never
  a CDN script. Nothing external loads, ever.
- Colour is used to carry meaning, not decoration: state = blue, DOM/render = green,
  bug = red, user action = amber.
- Every code block is short. 5–20 lines. Break longer ones up.
- Show output with `// →` comments where it helps.
- Escape HTML inside `<pre><code>` (`&lt;`, `&gt;`, `&amp;`).
- Styling of the built component barely matters — say so once, don't dwell. Logic and
  layout are what's scored.

## Technical requirements

- Single self-contained `.html` file. Full document: `<!DOCTYPE html>`, `<html lang="en">`,
  `<head>` with `<meta charset="utf-8">`, viewport meta, `<title>`.
- **Copy the `<style>` block verbatim from `guides/_TEMPLATE.html`** and use its class
  names, so all 25 guides look like one set. Add at most a few extra rules at the end of
  the style block for a diagram that's specific to your guide.
- Max content width ~780px. No JS required to read the page. Vanilla JS only for optional
  touches; the page must read fine with JS off.
- Write everything yourself. Do not fetch anything from the web.

## Anti-patterns

- ❌ Long prose paragraphs. Three sentences is a long paragraph here.
- ❌ Explaining what React is, what state is, what a component is.
- ❌ Restating the code in prose right under the code.
- ❌ A wall of bullets with no visual.
- ❌ "It is important to note that…", "Let's dive in", "In conclusion".
- ❌ Skipping the UI mockup because the component is "simple". Never skip it.
