<p align="center"><img src="./logo.png" alt="Show Me The Receipts — receipts-first AI output skill" width="140" /></p>

<h1 align="center">Show Me The Receipts</h1>

<p align="center"><strong>Receipts, not vibes. A skill that stops your AI agent from burying the answer in pretty words.</strong></p>

<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="MIT License"></a>
  <a href="https://github.com/lohyeulam-stack/show-me-the-receipts/releases"><img src="https://img.shields.io/badge/release-v0.1.0-informational" alt="Release"></a>
  <a href="#-install"><img src="https://img.shields.io/badge/Claude%20Code-plugin-blue?style=flat" alt="Claude Code plugin"></a>
  <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg" alt="PRs welcome">
</p>

<p align="center">
  <strong title="English" aria-label="English">🇬🇧 English</strong> ·
  <a href="README.zh-CN.md" title="简体中文" aria-label="简体中文">🇨🇳 简体中文</a> ·
  <a href="README.zh-TW.md" title="繁體中文" aria-label="繁體中文">🇹🇼 繁體中文</a> ·
  <a href="README.ja-JP.md" title="日本語" aria-label="日本語">🇯🇵 日本語</a> ·
  <a href="README.ko-KR.md" title="한국어" aria-label="한국어">🇰🇷 한국어</a> ·
  <a href="README.es-ES.md" title="Español" aria-label="Español">🇪🇸 Español</a> ·
  <a href="README.pt-BR.md" title="Português (Brasil)" aria-label="Português (Brasil)">🇧🇷 Português (Brasil)</a> ·
  <a href="README.fr-FR.md" title="Français" aria-label="Français">🇫🇷 Français</a> ·
  <a href="README.de-DE.md" title="Deutsch" aria-label="Deutsch">🇩🇪 Deutsch</a> ·
  <a href="README.ru-RU.md" title="Русский" aria-label="Русский">🇷🇺 Русский</a> ·
  <a href="README.vi-VN.md" title="Tiếng Việt" aria-label="Tiếng Việt">🇻🇳 Tiếng Việt</a>
</p>

**Show Me The Receipts** is an open-source agent skill (MIT licensed) that enforces evidence-first output in AI-generated reports, retrospectives, code reviews, and status updates: conclusion on the first line, facts separated from judgements and unknowns, every action assigned an owner, a deadline, and a verifiable deliverable — with AI-slop vocabulary removed and ADHD-friendly formatting on by default.

## 📦 Install

Copy/paste this into your coding agent's prompt:

```text
Install the show-me-the-receipts skill/plugin from https://github.com/lohyeulam-stack/show-me-the-receipts, refer to the repo's AGENTS.md for instructions.
```

Or install the Claude Code plugin directly:

```bash
claude plugin marketplace add lohyeulam-stack/show-me-the-receipts
claude plugin install show-me-the-receipts@show-me-the-receipts
```

Restart, then run `/show-me-the-receipts`. Full instructions for Codex, Cursor, OpenCode, Qoder, and plain web LLMs: [INSTALL.md](INSTALL.md) · [llms.txt](llms.txt) for AI readers.

##  Why

Reports die by a thousand cutouts: *"things improved steadily", "the dev team is following up", "will resolve ASAP", "empower the loop, form a closed circuit"* — after reading, nobody knows what happened, where it is stuck, or who to ping next.

LLMs are fluent at exactly this failure mode: confident prose, unverifiable claims, invented owners and dates, sycophantic openers and closers.

This skill stands on the shoulders of two projects it is deeply grateful to: [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh), whose Chinese AI-writing-tell checklist powers the de-AI-ification rules, and [ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd), whose ADHD-friendly output shaping and plugin architecture this repo follows. On top of their foundations, it adds the layer they leave open: evidence tiers, the action triad (owner · deadline · deliverable), and formal-document / retro diagnostics discipline.

## 📋 Table of contents

- [What changes: Before / After](#-before--after)
- [The rules](#-the-rules)
- [Supported runtimes](#-supported-runtimes)
- [Always-on mode](#-always-on-mode)
- [FAQ](#-faq)
- [Tune it (fork guide)](#-tune-it-fork-guide)
- [Contributing](#-contributing)
- [Credits](#-credits)
- [License](#-license)

## 🔄 Before / After

<table>
<tr>
<td width="50%">

### 😵 Before

> Great question! This quarter showed steady progress across the board. The ad integration is being followed up by the dev side and should be resolved soon. Experts feel there's room for improvement in link stability. Let's take this retro as an opportunity to empower the delivery loop and form real grip. The future is bright!

</td>
<td width="50%">

### 🧾 After

> Campaign Update fails at `budget_mode` validation: error code 30100, 4 campaigns unsavable (as of Sep 17 16:00).
>
> - **Target** 10 items this week · **Actual** 7 · **Gap** −3, 70% done
> - **Cause** 2 blocked on TikTok API validation, 1 waiting on real-account access
> - **Next** — owner: Backend A · deadline: Sep 18 18:00 · deliverable: success/failure request logs with error codes
> - "Room for improvement": no supporting data → marked **unknown**

</td>
</tr>
</table>

## 📏 The rules

Ten rules, full text in [SKILL.md](./skills/show-me-the-receipts/SKILL.md):

1. **First line is the conclusion or next action.** No preamble, no recap, no "Hope this helps!".
2. **Four evidence tiers** — verified fact / traceable experience / labelled inference / opinion. Lower tiers may never pose as the top tier.
3. **Unknown is written "unknown".** Fabricating numbers, owners, dates, or causality is prohibited.
4. **Action triad:** owner · deadline · deliverable. Unknown → TBD.
5. **Five concretisation checks:** subject, time, result, problem, and plan must each be locatable, verifiable, actionable.
6. **Gap-first reporting:** Target / Actual / Gap / Cause. No target value → no fabricated gap.
7. **Formal-document discipline:** no meta-commentary, a lede paragraph under every heading, lists over comma-piles, zero-information words banned ("steadily improved", "整体向好"), English abbreviations spelled out.
8. **Retro diagnostics:** abstract judgements must carry evidence, key quotes stay verbatim, every issue has a causal chain, criticism lands precisely and stays unemotional.
9. **De-AI-ify:** strip filler openers, hype vocabulary, vague attribution, negation antithesis ("not just X, but Y"), forced triads, false ranges.
10. **ADHD-friendly output:** numbered steps, state restated every turn, concrete time estimates, visible wins, lists capped at 5 items.

## 🖥 Supported runtimes

| Runtime | Entry point |
| --- | --- |
| Claude Code | `.claude-plugin/` + `hooks/` (plugin, `/show-me-the-receipts`) |
| Codex / Grok / Antigravity | `plugin.json` + `skills/show-me-the-receipts/SKILL.md` |
| Cursor | `.cursor/skills/show-me-the-receipts/SKILL.md` |
| OpenCode / Qoder / Pi | `skills/` directory copy — see [INSTALL.md](INSTALL.md) |
| Any web LLM | Paste the SKILL.md body into your system prompt |

## 🔁 Always-on mode

```bash
touch ~/.claude/.show-me-the-receipts-always
```

A `SessionStart` hook injects the full ruleset into every session on startup, resume, clear, or compact. Delete the flag file to turn it off.

## ❓ FAQ

**What does "show me the receipts" mean?**
Demand proof for every claim. Here it is a ruleset that makes an AI agent attach evidence — or admit the answer is unknown — before it dares to write a summary.

**What is the relationship with i-have-adhd and Humanizer-zh?**
Gratitude, mostly. This skill borrows its ADHD-friendly formatting layer and repo structure from [i-have-adhd](https://github.com/ayghri/i-have-adhd), and its Chinese de-AI-ification vocabulary from [Humanizer-zh](https://github.com/op7418/Humanizer-zh). Both are credited in [SKILL.md §9](./skills/show-me-the-receipts/SKILL.md) and below; go star them too.

**Does it work in English?**
The evidence tiers, action triad, gap reporting, and diagnostics rules are language-agnostic. The slop-vocabulary list (rule 9) is Chinese-first; English tells are tracked in [CONTRIBUTING.md](CONTRIBUTING.md).

**How is this different from a style guide in AGENTS.md?**
It is opt-in per session (`/show-me-the-receipts`), shippable as a plugin, and ends with a 13-point pre-output self-check instead of loose advice.

**Does it slow the model down?**
Slightly more thinking, dramatically fewer rounds of "make this less vague" follow-ups.

**Who is it for?**
Engineering managers writing weekly reports, anyone running retros, reviewers of PRDs and data reviews, and any reader with ADHD who needs the first line to be the answer.

## 🛠 Tune it (fork guide)

Edit `skills/show-me-the-receipts/SKILL.md`, then swap in your copy:

```bash
claude plugin uninstall show-me-the-receipts
claude plugin marketplace remove show-me-the-receipts
claude plugin marketplace add <your-username>/show-me-the-receipts
claude plugin install show-me-the-receipts@show-me-the-receipts
```

## 🤝 Contributing

English slop vocabulary, translations, eval cases, and new runtime adapters welcome. Start with [CONTRIBUTING.md](CONTRIBUTING.md) and [AGENTS.md](AGENTS.md).

## 🙏 Credits

- De-AI-ification rules (SKILL.md §9) adapted from [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh) — the reference Chinese-language checklist of AI writing tells.
- Repo structure, hooks, and multi-runtime plugin packaging follow [ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd).
- Evidence tiers, action triad, formal-document and retro diagnostics discipline are original to this repo.

## 📄 License

[MIT](LICENSE) — same license used by React, VS Code, and LangChain. Free to use, modify, and redistribute with attribution preserved.

---

<p align="center">Bring receipts. ⭐ if it saved you one scroll past one "Great question!".</p>
