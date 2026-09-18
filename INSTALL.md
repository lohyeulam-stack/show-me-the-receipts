# How to install

<details>
<summary><strong>Claude Code（插件，推荐）</strong></summary>

```bash
claude plugin marketplace add lohyeulam-stack/show-me-the-receipts
claude plugin install show-me-the-receipts@show-me-the-receipts
```

重启后在会话里输入 `/show-me-the-receipts` 激活。

### Always-on（可选）

```bash
touch ~/.claude/.show-me-the-receipts-always
```

每次会话开始自动注入完整规则集。删除该文件关闭。

### Uninstall

```bash
claude plugin uninstall show-me-the-receipts
claude plugin marketplace remove show-me-the-receipts
```

</details>

<details>
<summary><strong>Codex / 通用 SKILL.md</strong></summary>

下载 [skills/show-me-the-receipts/SKILL.md](https://raw.githubusercontent.com/lohyeulam-stack/show-me-the-receipts/main/skills/show-me-the-receipts/SKILL.md)，放进你的 skills 目录（如 `~/.codex/skills/` 或项目内 `skills/`），按你运行时的 skill 发现机制启用。

</details>

<details>
<summary><strong>Cursor</strong></summary>

本仓库自带 `.cursor/skills/show-me-the-receipts/SKILL.md`。Clone 后 Cursor 会自动发现；或把该文件复制到你项目的 `.cursor/skills/` 下。

</details>

<details>
<summary><strong>Qoder</strong></summary>

```bash
git clone https://github.com/lohyeulam-stack/show-me-the-receipts
cp -r show-me-the-receipts/skills/show-me-the-receipts ~/.qoder/skills/
```

重启后输入 `/show-me-the-receipts` 调用。

</details>

<details>
<summary><strong>任何模型 / 网页版</strong></summary>

把 `SKILL.md` 正文（去掉顶部 `---` frontmatter）直接粘贴进对话开头，或放进系统提示词 / 自定义指令。规则本身不依赖任何工具。

</details>

## Verify

激活后随便丢一段 AI 味汇报让它改写。合格输出应满足：

1. 第一行是结论或下一步，不是"好的""这是非完整季度对比"之类的元话语；
2. 事实、判断、未知分开；
3. 每个行动有负责人 / 完成时间 / 交付物，未知写"待确定"；
4. 没有"赋能 / 闭环 / 有所提升"。
