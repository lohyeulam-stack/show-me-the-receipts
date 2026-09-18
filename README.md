<p align="center"><img src="./logo.png" alt="show-me-the-receipts" width="140" /></p>

<h1 align="center">Show Me The Receipts</h1>

<p align="center"><strong>拿证据来。你的 AI 助手不再把答案埋进漂亮话里。</strong></p>

<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/github/license/lohyeulam-stack/show-me-the-receipts?style=flat" alt="License"></a>
  <a href="#安装"><img src="https://img.shields.io/badge/Claude%20Code-plugin-blue?style=flat" alt="Claude Code"></a>
  <a href="README.en.md"><img src="https://img.shields.io/badge/README-English-lightgrey?style=flat" alt="English"></a>
  <img src="https://img.shields.io/badge/PRs-welcome-brightgreen?style=flat" alt="PRs welcome">
</p>

<p align="center">
  <strong title="简体中文" aria-label="简体中文">🇨🇳</strong> ·
  <a href="README.en.md" title="English" aria-label="English">🇬🇧</a>
</p>

分析报告、复盘、周报最常见的病：*"稳中有升""开发那边在跟进""尽快处理""形成闭环抓手"* —— 读完仍然不知道发生了什么、卡在哪、下一步找谁。

这个 Skill 把 AI 输出强制转换为**可验证、可执行、可验收**的形式：

- 第一行就是结论或下一步，禁止开场白和"希望有帮助"；
- 事实 / 判断 / 推测 / 未知强制分层，禁止把推断写成事实；
- 每个行动落到 **负责人 · 完成时间 · 交付物**，未知写"待确定"，禁止编造；
- 进度先摆 Target / Actual / Gap / Cause，没有目标值不许虚构差距；
- 正式文档纪律：无元话语、标题后必有帽段、零信息量词汇禁用、英文缩写展开全称；
- 复盘诊断标准：抽象判断必须跟证据、保留关键原话、每条问题有因果链；
- 去 AI 味清单 + ADHD 友好排版。

完整规则见 [SKILL.md](./skills/show-me-the-receipts/SKILL.md)。

## 安装

复制粘贴到你的 CLI 对话框：

```text
Install the show-me-the-receipts skill/plugin from https://github.com/lohyeulam-stack/show-me-the-receipts, refer to the repo's AGENTS.md for instructions.
```

或手动安装（Claude Code / Codex / Cursor / OpenCode / 网页版通用）：👉 [INSTALL.md](INSTALL.md)

```bash
claude plugin marketplace add lohyeulam-stack/show-me-the-receipts
claude plugin install show-me-the-receipts@show-me-the-receipts
```

重启后输入 `/show-me-the-receipts` 激活。

## Before / After

<table>
<tr>
<td width="50%">

### Before 😵

> 本季度整体表现稳中有升，各条线持续推进优化。广告接入方面开发那边还在跟进，预计后续会尽快解决。专家认为链路稳定性仍有提升空间，希望以此次复盘为契机，进一步打通投放闭环、形成抓手。总之未来一片光明！

</td>
<td width="50%">

### After 🧾

> Campaign Update 联调未通过：`budget_mode` 参数校验返回 error code 30100，4 个 Campaign 无法保存（截至 9 月 17 日 16:00）。
>
> - Target：本周 10 项；Actual：7 项；Gap：少 3 项，完成率 70%。
> - Cause：2 项卡在 TikTok API 参数校验，1 项等待真实账户权限。
> - 下一步——负责人：后端 A；完成时间：9 月 18 日 18:00 前；交付物：真实账户联调的成功/失败请求与 error code 记录。
> - "链路稳定性"无对应数据，标记为**未知**。

</td>
</tr>
</table>

## 核心规则速览

1. 结论先行：第一行是答案或下一步动作。
2. 证据四级：一手证据 / 可追溯经验 / 标注过的推断 / 主观意见，后两级不得伪装成第一级。
3. 未知就写未知，禁止补全不存在的信息。
4. 行动三要素：负责人、完成时间、交付物。
5. 五类具体化：主体、时间、结果、问题、方案——全部到"能定位、能验证、能行动"为止。
6. 差距暴露：Target / Actual / Gap / Cause。
7. 正式文档格式纪律（帽段、列表、无元话语）。
8. 正式文档语言纪律（禁零信息量词、缩写展开、字段名规范）。
9. 复盘诊断纪律（证据跟判断、原话保留、因果链、批评落点具体）。
10. 去 AI 痕迹 + ADHD 友好输出协议。

## 长期开启（可选）

```bash
touch ~/.claude/.show-me-the-receipts-always
```

SessionStart hook 会在每次会话自动注入完整规则集；删除该文件即关闭。

## 常见问题

**和 i-have-adhd 什么关系？**
[i-have-adhd](https://github.com/ayghri/i-have-adhd) 解决"让 ADHD 读者能行动"的排版问题；本仓库在此之上解决"内容本身不可验证"的问题——证据分级、行动三要素、正式文档纪律、复盘诊断标准。ADHD 友好排版作为默认层保留。

**只适用于中文吗？**
规则文本以中文写作场景为主（"赋能 / 闭环 / 有所提升"等中文 AI 高频词），但证据分级与行动三要素对任何语言有效。英文禁用词表欢迎 PR。

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

## Credits

- 去 AI 痕迹规则（SKILL.md 第 9 节）参考 [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh)，中文语境下的 AI 写作痕迹清单以它为基准。
- 仓库结构、hooks 与多运行时插件方案参考 [ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd)。
- 证据分级、行动三要素、正式文档与诊断纪律为本仓库原创。

## License

[MIT](LICENSE)。

用完了记得贴 receipts。⭐ 如果它帮你躲过了一句"希望有帮助"。
