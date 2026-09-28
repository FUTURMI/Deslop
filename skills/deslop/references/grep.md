# Grep patterns

Case-insensitive, ripgrep syntax. For pasted text with no file, check each
line of the table by reading instead.
`\|` in the tables is an escaped pipe for markdown; use a plain `|` in the regex.

## Prose (md, txt, html, jsx/tsx copy)

| category | pattern |
|---|---|
| vocab | `\b(delv(e\|es\|ed\|ing)\|showcas(e\|es\|ed\|ing)\|underscor(e\|es\|ed\|ing)\|tapestry\|testament\|pivotal\|intricate\|intricacies\|meticulous(ly)?\|commendable\|realm\|boasts?\|bolster(s\|ed)?\|garner(s\|ed)?\|interplay\|vibrant\|foster(s\|ed\|ing)?\|crucial\|enduring\|multifaceted\|holistic\|seamless(ly)?\|leverag(e\|es\|ed\|ing)\|utiliz(e\|es\|ed\|ing)\|elevat(e\|es\|ing)\|unleash\|embark\|game-changer\|cutting-edge\|ever-evolving\|nestled\|renowned\|groundbreaking\|additionally\|notably\|landscape)\b` |
| significance | `(stands?\|serves?) as an? (testament\|reminder\|beacon)\|plays? an? (pivotal\|crucial\|vital\|key\|significant) role\|indelible mark\|evolving landscape\|setting the stage for\|marks? a (shift\|turning point)\|reflects? broader\|enduring legacy` |
| copula-avoid | `\b(serves\|stands\|functions\|operates) as\b` |
| neg-parallel | `not (just\|only\|merely) [^.;!?]{1,60}?,? but\|it'?s not [^.;!?]{1,50}?[,;—–-]+ ?it'?s\|this isn'?t [^.;!?]{1,50}?[,;—–-]+ ?it'?s` |
| ing-tail | `, (highlighting\|underscoring\|emphasizing\|showcasing\|reflecting\|symbolizing\|ensuring\|fostering\|contributing to\|cementing)\b` |
| vague-attrib | `experts (argue\|say\|note\|agree)\|industry reports\|observers (have )?(noted\|cited)\|some critics argue\|studies (show\|suggest)` |
| filler | `it'?s (important\|worth) (to note\|noting\|mentioning)\|in today'?s (fast-paced\|digital\|modern\|ever-changing)\|in the (realm\|world) of\|when it comes to\|at the end of the day\|let'?s dive in\|without further ado\|in conclusion\|in summary\|the future is bright\|the possibilities are endless` |
| chat-residue | `certainly!\|absolutely!\|great question\|i hope this helps\|let me know if you\|as an ai\|as of my (last\|latest) (update\|knowledge)\|knowledge cutoff` |
| placeholder | `\[(your\|insert\|company\|name\|placeholder)[^\]]{0,30}\]\|lorem ipsum` |
| citation-debris | `oaicite\|oai_citation\|contentReference\|turn\d+search\d+\|attributableIndex\|utm_source=chatgpt\.com\|\[cite: ?\d+\]\|grok_card\|ppl-ai-file-upload\|【` |
| fiction | `\b(elara\|kael)\b\|heart hammer(ed\|ing)\|voice (trembling\|barely above a whisper\|devoid of)\|a profound sense of\|unsettlingly\|shimmered` |
| em-dash | `—` (count, then divide by word count) |

## UI (html, css, jsx/tsx, vue, svelte)

| category | pattern |
|---|---|
| purple-gradient | `\b(from\|via\|to)-(indigo\|purple\|violet\|fuchsia)-\d{2,3}\b\|linear-gradient\([^)]*(#6366f1\|#8b5cf6\|#7c3aed\|#a855f7\|#4f46e5\|indigo\|purple\|violet)` |
| default-indigo | `\b(bg\|text\|border\|ring)-indigo-(500\|600)\b` |
| default-font | `font-family:\s*['"]?(Inter\|Roboto\|Open Sans\|Lato)\b\|\b(Inter\|Roboto)\(\{\|family=(Inter\|Roboto)\b\|\b(Fraunces\|Instrument[_ ]Serif)\b` |
| three-cards | `\b(md\|lg):grid-cols-3\b` (then check: equal icon+title+text cards?) |
| sparkles-icon | `\bSparkles\b\|✨` |
| generic-shadow | `\bshadow-(md\|lg\|xl)\b\|box-shadow:[^;]*rgba\(0,\s*0,\s*0` |
| glass | `backdrop-blur\|backdrop-filter:\s*blur` |
| empty-copy | `build faster\|ship (faster\|smarter)\|scale without limits\|all-in-one platform\|supercharge your\|elevate your\|unlock the power\|next-gen\|seamless(ly)? integrat` |
| fake-data | `\b(john\|jane) (doe\|smith)\b\|\bacme\b\|99\.99%\|lorem ipsum` |
| a11y | `alt=['"](\|image\|img\|photo\|picture)['"]\|>\s*click here\s*<\|window\.alert\(\|\balert\(['"]` |
| a11y-structure | files with no `<main` / `role="main"`; `<div onClick` without `role=`/`tabIndex`; `<input` without a matching `<label`/`aria-label` |
| perf | `addEventListener\(\s*['"]scroll['"]\|\bh-screen\b\|z-\[9{3,}\]\|z-index:\s*9{3,}` |
| step-labels | `\b(Step\|Stage\|Phase) 0?[1-3]\b` |

Skip `node_modules`, `dist`, `build`, `.next`, `vendor`.
