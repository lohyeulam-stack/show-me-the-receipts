# Contributing

PRs welcome, especially for:

1. **English slop vocabulary** — extend section 9 of `skills/show-me-the-receipts/SKILL.md` with English AI-writing tells (a parallel ruleset may live in `skills/show-me-the-receipts/SKILL.en.md` once mature).
2. **Translations** of `README.md` / `INSTALL.md`.
3. **Runtime adapters** — new plugin manifests or hooks; follow the pattern in `AGENTS.md`.
4. **Eval cases** — before/after document pairs proving the ruleset improves verifiability.

## Rules of the house

- `skills/show-me-the-receipts/SKILL.md` is the source of truth. Keep `.cursor/skills/show-me-the-receipts/SKILL.md` byte-identical.
- Do not weaken hard constraints (evidence tiers, action triad, no-fabrication, pre-output checks) for style.
- Run the checks in `AGENTS.md` → Verification and report exact commands and results in the PR.

## Before opening a PR

```bash
diff skills/show-me-the-receipts/SKILL.md .cursor/skills/show-me-the-receipts/SKILL.md
node hooks/always-on.mjs   # must exit 0 silently without the flag file
git diff --check
```
