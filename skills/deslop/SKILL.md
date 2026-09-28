---
name: deslop
description: >
  Find and remove AI-slop patterns from prose and from UI/frontend code.
  Use when the user asks to deslop, de-AI, humanize, or clean up a draft;
  asks whether text or a page "looks AI-generated"; or wants a landing page,
  component, or site to stop looking vibe-coded (purple gradients, Inter,
  three-card rows, missing states, accessibility gaps). Two modes: scan
  (report only) and fix (rewrite/edit). Also triggers on /deslop.
---

# Deslop

Remove the patterns that make text and interfaces read as machine defaults.
The goal is better work, not detector evasion. No pattern proves AI
authorship; only clusters of them matter, and humans use every one of these
sometimes. Never promise that output will "pass" an AI detector.

## Mode

- **scan**: user asks "is this AI?", "check", "audit", "scan". Report only.
- **fix**: user asks to rewrite, clean, deslop, humanize, redesign. Edit.
- Unclear: scan, then offer to fix.

## Step 1: collect hits

Use your built-in search/grep tool (no scripts, no installs) with the
patterns in `references/grep.md` on the target files or pasted text.
Record `location: [category] match`. Grep only finds words and phrases;
structure, tone, and design choices come from Step 2.

For prose, also estimate em dashes per 1k words (human baseline ~3.2).

## Step 2: read against the reference

- Prose: read `references/text.md`
- UI, HTML, CSS, JSX/TSX, Tailwind: read `references/ui.md`
- Both kinds of content: read both

Load only what applies.

## Step 3a: scan report

Group findings by category. Most severe first. One line each:
`location: pattern -> why it reads as default -> suggested replacement`.
End with a verdict of one or two sentences: how many categories were hit, and
which three fixes would change the most. Rank by density, not by single hits.

## Step 3b: fix

**Prose rules**
1. Keep the author's voice, claims, facts, and structure. Change nothing the
   author meant. If a sentence is empty, cut it rather than rephrase it.
2. Replace inflated verbs with plain ones: "serves as" -> "is",
   "boasts" -> "has", "leverage" -> "use".
3. Replace vague significance claims with the specific fact, or delete them.
   Never invent a fact, number, source, or anecdote to fill the gap. If
   specifics are missing, leave a `[TODO: specific example]` marker and say so.
4. Break the rhythm: vary sentence length, and drop reflexive triplets where
   there aren't really three things.
5. Em dashes: keep one only where nothing else works. Use a period, comma,
   colon, or parentheses instead.
6. Remove chat residue, citation debris, and placeholder text entirely.
7. Formatting: turn bullet-lists-of-thoughts back into prose where the ideas
   connect. Drop bold on every lead-in. Use sentence-case headings.
8. Don't overcorrect into a new tell: no forced typos, no slang the author
   wouldn't use, no swapping "delve" for another fancy synonym.

**UI rules**
1. Ask for or infer one concrete direction from the brief (audience, brand,
   content). A banned-list alone just moves the average, so replace defaults
   with *chosen* ones and say why.
2. Fix accessibility first: landmarks, one `<main>`, contrast AA, labeled
   form controls, meaningful alt and link text. This is the best-measured
   failure and matters more than looks.
3. Add the missing states: empty, loading (skeleton where layout is known),
   error (inline, never `alert()`), focus, hover, active, disabled.
4. Then visuals: type, color, layout rhythm, icons, motion, copy.
5. Keep the stack. Don't add a dependency to fix a look. Don't change routes,
   IDs, analytics hooks, or information architecture unless asked.

After fixing, rerun Step 1 and report before/after hit counts in one line.
