# I hate AI writing

A writing skill for AI assistants. It holds the rules that keep generated prose from reading like a language model wrote it, and it tells the assistant what to write instead.

**[Overview](#overview)** · **[Rules](#rules)** · **[Banned vocabulary](#banned-vocabulary)** · **[Usage](#usage)** · **[Roadmap](#roadmap)**

---

## Overview

Language models leave recognisable marks in prose. They inflate the importance of ordinary facts, pile on promotional adjectives, end sections with a tidy summary, write triads where two items would do, and frame points as "not X, but Y". Readers notice these marks quickly, and once they notice, they stop trusting the text.

This skill is a set of avoidance rules. Each rule names a pattern and says what to write in its place. The fix in every case is the same: say the concrete thing and drop the framing around it. If a claim has nothing specific behind it, the rule asks for a fact or for the sentence to be cut. Rewording the sentence to dodge the rule does not count.

The rules are distilled from Wikipedia's [Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) field guide (WP:AISIGNS), checked against its 28 September 2026 revision. The skill covers the chat answers, reports, change logs, emails and other text an assistant writes for someone to read or reuse.

## Rules

| Section | What it covers |
|---|---|
| Content rules | No significance inflation, no tacked-on analysis clauses, no promotional register, no weasel attribution, no formula conclusions, no speculation about what a source "likely" says |
| Banned vocabulary | A measured list of words that mark generated text, and plain swaps for each |
| Sentence construction | Plain copulas, no negative parallelisms, no rule-of-three padding, vary sentence length |
| Formatting | Sentence-case headings, prose over bullet lists, restrained bold, rare em dashes, straight quotes |
| Change logs and reports | Say what changed in content terms; no compliance assurances or stacked "improvements" |
| Chat and correspondence | No stock openers or closers, no self-narration, start emails with the reason for writing |
| What not to overcorrect | Simple constructions, plain verbs and honest hedges are fine |
| Final pass | Four checks to run before delivering any text |

## Banned vocabulary

These words are the measured markers of generated prose. One occurrence is a coincidence; several together are a pattern. The list covers words such as *delve*, *crucial*, *pivotal*, *testament*, *tapestry*, *landscape*, *interplay*, *robust*, *vibrant*, *foster*, *showcase*, *underscore*, *enhance*, *leverage* (as a verb), *seamless*, *holistic*, *unlock*, *journey* (abstract) and sentence-initial *Additionally*. The rule is to cut the word, not to swap in a cousin.

Plain swaps: *use* instead of *utilize*; *has* instead of *features*, *offers* or *boasts*; *is* instead of *serves as*, *stands as* or *represents*; *shows* instead of *showcases* or *underscores*; *improve* instead of *enhance*.

## Usage

Claude Code loads skills from a `.claude/skills/` folder, one folder per skill, with a `SKILL.md` file inside. To install this one in a project:

```bash
mkdir -p .claude/skills/human-voice
cp SKILL.md .claude/skills/human-voice/SKILL.md
```

The skill's `description` field tells the assistant when to load it. The file is plain Markdown, so it can also be pasted into any other assistant's instructions.

## Roadmap

- Re-check the rules against Wikipedia's guide when its revision changes.
