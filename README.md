# deslop

A skill for Claude Code and Codex that finds and removes AI-slop patterns
in text, design and code. Each pattern notes where the evidence comes from: a
measured study, Wikipedia's AI-cleanup editors, or practitioner opinion.

## Install

Claude Code:

```sh
claude plugin marketplace add FUTURMI/deslop
claude plugin install deslop@deslop
```

Codex:

```sh
codex plugin marketplace add FUTURMI/deslop
codex plugin add deslop@deslop
```

## Usage

Run `/deslop` in Claude Code or `@deslop` in Codex. You can also just ask,
e.g. "deslop this draft" or "does this page look AI-made?"

It works in two modes. Scan reports what it finds and changes nothing. Fix
rewrites the text or edits the code.

## What's inside

| File | Contents |
| --- | --- |
| [`skills/deslop/SKILL.md`](skills/deslop/SKILL.md) | The workflow (scan or fix) |
| [`skills/deslop/references/text.md`](skills/deslop/references/text.md) | Prose patterns, with sources |
| [`skills/deslop/references/ui.md`](skills/deslop/references/ui.md) | UI patterns, with sources |
| [`skills/deslop/references/grep.md`](skills/deslop/references/grep.md) | Regexes the agent runs with its built-in search |

## License

[MIT](LICENSE)
