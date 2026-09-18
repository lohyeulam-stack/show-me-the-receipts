<p align="center"><img src="./logo.png" alt="Show Me The Receipts —— 拿证据来的 AI 输出纪律 Skill" width="140" /></p>

<h1 align="center">Show Me The Receipts</h1>

<p align="center"><strong>拿证据来。让 AI 不再把答案埋进漂亮话里。</strong></p>

<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="MIT License"></a>
  <a href="https://github.com/lohyeulam-stack/show-me-the-receipts/releases"><img src="https://img.shields.io/badge/release-v0.1.0-informational" alt="Release"></a>
  <a href="#安装"><img src="https://img.shields.io/badge/Claude%20Code-plugin-blue?style=flat" alt="Claude Code 插件"></a>
  <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg" alt="欢迎 PR">
</p>

<p align="center">
  <a href="README.md" title="English" aria-label="English">🇬🇧 English</a> ·
  <strong title="简体中文" aria-label="简体中文">🇨🇳 简体中文</strong> ·
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

**Show Me The Receipts（拿证据来）** 是一个 MIT 开源的 Agent Skill：强制 AI 在分析报告、复盘、代码评审、周报中做到结论先行、事实与判断和未知分层、每个行动落到负责人 + 完成时间 + 可验收交付物，同时去除 AI 写作痕迹、默认 ADHD 友好排版。

## 安装

复制粘贴到你的 CLI 对话框：

```text
Install the show-me-the-receipts skill/plugin from https://github.com/lohyeulam-stack/show-me-the-receipts, refer to the repo's AGENTS.md for instructions.
```

或直接安装 Claude Code 插件：

```bash
claude plugin marketplace add lohyeulam-stack/show-me-the-receipts
claude plugin install show-me-the-receipts@show-me-the-receipts
```

重启后输入 `/show-me-the-receipts` 激活。Codex / Cursor / OpenCode / Qoder / 网页版通用安装见 [INSTALL.md](INSTALL.md)。

## 为什么需要它

分析报告、复盘、周报最常见的病：*"稳中有升""开发那边在跟进""尽快处理""形成闭环抓手"* —— 读完仍然不知道发生了什么、卡在哪、下一步找谁。

LLM 恰好精通这种失败模式：自信的行文、无法验证的断言、编造的负责人和时间、谄媚的开头结尾。

本 Skill 站在两个优秀项目的肩膀上，并向它们致谢：[op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh) 提供了中文 AI 写作痕迹清单（SKILL.md 第 9 节的基础）；[ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd) 提供了 ADHD 友好输出层与本仓库的插件化结构。在它们的地基之上，本仓库补上了新的一层：证据分级、行动三要素、正式文档纪律、复盘诊断标准。

## 目录

- [Before / After](#before--after)
- [核心规则](#核心规则)
- [支持运行时](#支持运行时)
- [长期开启](#长期开启可选)
- [常见问题](#常见问题)
- [Fork 后怎么改](#fork-后怎么改)
- [致谢](#致谢)
- [License](#license)

## Before / After

<table>
<tr>
<td width="50%">

### 😵 Before

> 本季度整体表现稳中有升，各条线持续推进优化。广告接入方面开发那边还在跟进，预计后续会尽快解决。专家认为链路稳定性仍有提升空间，希望以此次复盘为契机，进一步打通投放闭环、形成抓手。总之未来一片光明！

</td>
<td width="50%">

### 🧾 After

> Campaign Update 联调未通过：`budget_mode` 参数校验返回 error code 30100，4 个 Campaign 无法保存（截至 9 月 17 日 16:00）。
>
> - Target：本周 10 项；Actual：7 项；Gap：少 3 项，完成率 70%。
> - Cause：2 项卡在 TikTok API 参数校验，1 项等待真实账户权限。
> - 下一步——负责人：后端 A；完成时间：9 月 18 日 18:00 前；交付物：真实账户联调的成功/失败请求与 error code 记录。
> - "链路稳定性"无对应数据，标记为**未知**。

</td>
</tr>
</table>

## 核心规则

10 条速览，完整规则见 [SKILL.md](./skills/show-me-the-receipts/SKILL.md)：

1. 第一行就是结论或下一步，禁止开场白和"希望有帮助"。
2. 证据四级：一手证据 / 可追溯经验 / 标注过的推断 / 主观意见，后两级不得伪装成第一级。
3. 未知就写未知，禁止编造数字、时间、负责人、因果。
4. 行动三要素：负责人、完成时间、交付物；未知写"待确定"。
5. 五类具体化：主体、时间、结果、问题、方案——全部到"能定位、能验证、能行动"为止。
6. 进度先摆 Target / Actual / Gap / Cause，没有目标值不许虚构差距。
7. 正式文档纪律：无元话语、标题后必有帽段、零信息量词汇禁用、英文缩写展开全称。
8. 复盘诊断纪律：抽象判断必须跟证据、保留关键原话、每条问题有因果链、批评落点具体不情绪化。
9. 去 AI 味：删"赋能 / 闭环 / 不仅仅是…而是… / 三段式硬凑 / 虚假范围"。
10. ADHD 友好：编号步骤、每轮重述状态、时间给具体单位、完成结果可见、列表不超 5 项。

## 支持运行时

| 运行时 | 入口 |
| --- | --- |
| Claude Code | `.claude-plugin/` + `hooks/`（插件，`/show-me-the-receipts`） |
| Codex / Grok / Antigravity | `plugin.json` + `skills/show-me-the-receipts/SKILL.md` |
| Cursor | `.cursor/skills/show-me-the-receipts/SKILL.md` |
| OpenCode / Qoder / Pi | 复制 `skills/` 目录，见 [INSTALL.md](INSTALL.md) |
| 任意网页 LLM | 把 SKILL.md 正文贴进系统提示词 |

## 长期开启（可选）

```bash
touch ~/.claude/.show-me-the-receipts-always
```

SessionStart hook 会在每次会话（startup / resume / clear / compact）自动注入完整规则集；删除该文件即关闭。

## 常见问题

**"Show me the receipts" 是什么意思？**
"拿证据来"。这里是让 AI 在写下任何结论之前先附上证据——或者承认不知道。

**和 i-have-adhd、Humanizer-zh 是什么关系？**
主要是感谢。本 Skill 的 ADHD 友好排版层和仓库结构来自 [i-have-adhd](https://github.com/ayghri/i-have-adhd)，中文去 AI 味词表来自 [Humanizer-zh](https://github.com/op7418/Humanizer-zh)。两处都已在 SKILL.md 和下方致谢，推荐大家去给它们点 star。

**只适用于中文吗？**
证据分级、行动三要素、差距报告、诊断纪律与语言无关；去 AI 味词表（第 9 条）以中文为主，英文词表欢迎 PR。

**和写在 AGENTS.md 里的风格指南有什么区别？**
按需激活（`/show-me-the-receipts`）、可打包分发、并且以 13 项输出前自检收尾，而不是一堆松散建议。

**怎么验证效果？**
丢一段 AI 味汇报让它改写。合格输出：第一行是结论、事实/未知分开、行动有负责人、没有"赋能/闭环/有所提升"。

## Fork 后怎么改

编辑 `skills/show-me-the-receipts/SKILL.md`，然后换成你自己的副本：

```bash
claude plugin uninstall show-me-the-receipts
claude plugin marketplace remove show-me-the-receipts
claude plugin marketplace add <your-username>/show-me-the-receipts
claude plugin install show-me-the-receipts@show-me-the-receipts
```

## 致谢

- [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh)：中文 AI 写作痕迹清单的基准，SKILL.md 第 9 节在其基础上整理。感谢 🙏
- [ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd)：ADHD 友好输出层与仓库结构、hooks、多运行时插件方案的参考。感谢 🙏
- 证据分级、行动三要素、正式文档与复盘诊断纪律为本仓库原创。

## License

[MIT](LICENSE)——与 React、VS Code、LangChain 相同的协议，可自由使用、修改、分发，保留版权声明即可。

---

<p align="center">用完了记得贴 receipts。⭐ 如果它帮你躲过了一句"希望有帮助"。</p>
