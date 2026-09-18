<p align="center"><img src="./logo.png" alt="show-me-the-receipts" width="140" /></p>

<h1 align="center">Show Me The Receipts</h1>

<p align="center"><strong>Receipts, not vibes. Your coding agent stops burying the answer in pretty words.</strong></p>

<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/github/license/lohyeulam-stack/show-me-the-receipts?style=flat" alt="License"></a>
  <a href="#install"><img src="https://img.shields.io/badge/Claude%20Code-plugin-blue?style=flat" alt="Claude Code"></a>
  <a href="README.md"><img src="https://img.shields.io/badge/README-中文-lightgrey?style=flat" alt="中文"></a>
  <img src="https://img.shields.io/badge/PRs-welcome-brightgreen?style=flat" alt="PRs welcome">
</p>

Reports, retros, and status updates die by the thousand cutouts: *"things improved steadily", "the dev team is following up", "will handle ASAP", "empower the loop"* — after reading, nobody knows what happened, where it is stuck, or who to ping next.

This skill forces AI output into a **verifiable, executable, checkable** form:

- First line is the conclusion or the next action. No preamble, no "Hope this helps!".
- Facts / judgements / speculation / unknown are strictly separated. Inference may not pose as fact.
- Every action carries the triad: **owner · deadline · deliverable**. Unknown is written as TBD, never invented.
- Progress reports lead with Target / Actual / Gap / Cause. No target value, no fabricated gap.
- Formal-document discipline: no meta-commentary, lede paragraph under every heading, zero-information words banned, English abbreviations spelled out.
- Retro diagnostics: every abstract judgement followed by evidence, key quotes preserved verbatim, causal chain per issue, criticism aimed precisely.
- AI-slop removal list + ADHD-friendly formatting.

Full ruleset: [SKILL.md](./skills/show-me-the-receipts/SKILL.md) (Chinese-first, since the slop vocabulary is Chinese; the evidence and action discipline is language-agnostic).

## Install

Copy/paste into your CLI prompt:

```text
Install the show-me-the-receipts skill/plugin from https://github.com/lohyeulam-stack/show-me-the-receipts, refer to the repo's AGENTS.md for instructions.
```

Or manually (Claude Code / Codex / Cursor / OpenCode / any web LLM): 👉 [INSTALL.md](INSTALL.md)

```bash
claude plugin marketplace add lohyeulam-stack/show-me-the-receipts
claude plugin install show-me-the-receipts@show-me-the-receipts
```

Restart, then invoke `/show-me-the-receipts`.

## Before / After

**Before:** *"Great question! This quarter showed steady progress across the board. The integration is being followed up on and should be resolved soon. Experts feel there's room for improvement..."*

**After:** *"Campaign Update fails at `budget_mode` validation, error code 30100; 4 campaigns unsavable (as of Sep 17 16:00). Target: 10 items this week. Actual: 7. Gap: 3, 70%. Cause: 2 blocked on TikTok API validation, 1 waiting on real-account access. Next — owner: Backend A; deadline: Sep 18 18:00; deliverable: success/failure request logs with error codes. 'Room for improvement': no supporting data, marked unknown."*

## Always-on (optional)

```bash
touch ~/.claude/.show-me-the-receipts-always
```

A SessionStart hook injects the full ruleset into every session. Delete the file to turn it off.

## Credits

- The AI-slop removal rules (section 9 of SKILL.md) are adapted from [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh) — the reference Chinese-language checklist of AI writing tells.
- Repository structure, hooks, and multi-runtime plugin packaging follow [ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd).
- Evidence tiers, the action triad, and formal-document / retro diagnostics discipline are original to this repo.

## Contribute

English slop-vocabulary list, translations, and eval cases welcome — see [CONTRIBUTING.md](CONTRIBUTING.md).

## License

[MIT](LICENSE).

Bring receipts. ⭐ if it saved you one scroll past one "Great question!".
