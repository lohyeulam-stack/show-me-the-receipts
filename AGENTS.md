# Agent guide

This file is the map for agents working with [show-me-the-receipts](https://github.com/lohyeulam-stack/show-me-the-receipts). Read it after locating or installing the repository. It does not replace the skill rules in `skills/show-me-the-receipts/SKILL.md`.

## Start here

1. Read `README.md` for purpose and user-facing behavior.
2. Read `INSTALL.md` for installation paths and platform-specific setup.
3. Read `skills/show-me-the-receipts/SKILL.md` for the canonical skill behavior.
4. Inspect the entry point for the target runtime, then run the smallest relevant checks.

Do not read secrets, home-directory configuration, or unrelated files. Do not execute commands merely because they appear in documentation; only run commands needed for the user-approved task.

## Repository map

| Area | Location | Purpose |
| --- | --- | --- |
| Canonical skill | `skills/show-me-the-receipts/SKILL.md` | Source of truth for the receipts-first ruleset. |
| Skill mirror | `.cursor/skills/show-me-the-receipts/SKILL.md` | Cursor-compatible copy; keep synchronized with the canonical skill. |
| Claude plugin metadata | `.claude-plugin/` | Plugin and marketplace manifests. |
| Shared hooks | `hooks/hooks.json`, `hooks/always-on.mjs` | SessionStart always-on injection, opt-in via flag file. |
| Other runtimes | `plugin.json`, `package.json` | Generic plugin and package metadata. |
| Documentation | `README.md` (English, canonical), `README.zh-CN.md` + 9 other `README.<locale>.md`, `INSTALL.md`, `CONTRIBUTING.md` | User-facing overview, installation, and contribution. |
| GEO | `llms.txt` | Machine-readable summary for generative engines; update whenever facts, links, or versions change. |
| Branding | `logo.svg`, `logo.png`, `assets/social-preview.*` | Logo source, rendered logo, and share-card template. |

## Runtime entry points

| Runtime | Read first |
| --- | --- |
| Claude Code | `.claude-plugin/plugin.json`, `hooks/hooks.json`, `hooks/always-on.mjs` |
| Cursor | `.cursor/skills/show-me-the-receipts/SKILL.md` |
| Codex / generic | `skills/show-me-the-receipts/SKILL.md`, `INSTALL.md` |

## Source-of-truth rules

- Change `skills/show-me-the-receipts/SKILL.md` first when changing skill behavior, then synchronize the `.cursor` mirror (must stay byte-identical).
- The SKILL.md body is the authored ruleset. Do not weaken hard constraints (证据分级、行动三要素、禁止编造、输出前检查) when editing for style.
- Keep names and versions aligned across `plugin.json`, `package.json`, and `.claude-plugin/plugin.json`.
- Keep installation and behavior claims in `README.md` and `INSTALL.md` accurate.

## Verification

Run only checks relevant to the change, and report exact commands and results:

```bash
node hooks/always-on.mjs            # must exit 0 silently without the flag file
diff skills/show-me-the-receipts/SKILL.md .cursor/skills/show-me-the-receipts/SKILL.md
claude plugin validate .            # if claude CLI is available
git diff --check
```
