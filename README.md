# Show Me The Receipts

> 拿证据来。结论先行，事实 / 判断 / 未知分层，行动落到负责人 + 完成时间 + 交付物。不编造，不谄媚，不写 AI 味。

[![License](https://img.shields.io/github/license/lohyeulam-stack/show-me-the-receipts?style=flat)](LICENSE)

## Install

复制粘贴到你的 CLI 对话框：

```text
Install the show-me-the-receipts skill/plugin from https://github.com/lohyeulam-stack/show-me-the-receipts, refer to the repo's AGENTS.md for instructions.
```

或查看[完整安装说明](INSTALL.md)（Claude Code / Codex / Cursor / OpenCode / 通用 SKILL.md）。

## 它解决什么

分析报告、复盘、周报、方案评审里最常见的问题：漂亮话掩盖了无法验证的信息。"效果显著提升""开发那边还在跟进""尽快处理"——读者看完仍然不知道发生了什么、卡在哪、下一步找谁。

这个 skill 把输出强制转换为可验证、可执行、可验收的形式。

## Before / After

<table>
<tr>
<td width="50%">

### Before

> 这个季度整体表现稳中有升，各条线持续推进优化。广告接入方面开发那边还在跟进，预计后续会尽快解决。专家认为链路稳定性仍有提升空间，我们希望以此次复盘为契机，进一步打通投放闭环、形成抓手。总之未来一片光明！

</td>
<td width="50%">

### After

> Campaign Update 联调未通过：`budget_mode` 参数校验阶段返回 error code 30100，导致 4 个 Campaign 无法保存（截至 9 月 17 日 16:00）。
>
> - Target：本周完成 10 项接入；Actual：7 项；Gap：少 3 项，完成率 70%。
> - Cause：2 项卡在 TikTok API 参数校验，1 项等待真实账户权限。
> - 下一步——负责人：后端 A；完成时间：9 月 18 日 18:00 前；交付物：完成真实账户联调，提交成功请求、失败请求与 error code 记录。
> - "链路稳定性""闭环""抓手"为原文引用，原文未给对应数据，标记为未知。

</td>
</tr>
</table>

## 核心规则

完整版见 [SKILL.md](./skills/show-me-the-receipts/SKILL.md)。摘要：

1. 第一行就是结论或下一步，禁止开场白和结束客套。
2. 证据分四级：一手证据 / 可追溯经验 / 标注过的推断 / 主观意见，不准把后两级写成第一级。
3. 信息不足直接写"未知"，禁止编造数字、时间、负责人、因果。
4. 行动三要素：负责人、完成时间、交付物；未知写"待确定"。
5. 五类具体化：主体、时间、结果、问题、方案，全部到"能定位、能验证、能行动"为止。
6. 涉及进度先摆 Target / Actual / Gap / Cause，没有目标值不虚构 Gap。
7. 正式文档纪律：无元话语、标题后必有帽段、并列项成列表、零信息量词汇禁用、英文缩写展开为全称。
8. 复盘诊断：抽象判断跟证据、保留关键原话、每条问题有因果链、批评落点具体不情绪化。
9. 去 AI 痕迹：删"赋能 / 闭环 / 不仅仅是…而是… / 三段式硬凑 / 虚假范围"。
10. ADHD 友好：编号步骤、每轮重述状态、时间给具体单位、完成结果可见。

## 长期开启（可选）

安装为 Claude Code 插件后：

```bash
touch ~/.claude/.show-me-the-receipts-always
```

SessionStart hook 会在每次会话注入完整规则集。删除该文件即关闭。

## Fork 后怎么改

编辑 `skills/show-me-the-receipts/SKILL.md`，然后换成你自己的副本：

```bash
claude plugin uninstall show-me-the-receipts
claude plugin marketplace remove show-me-the-receipts
claude plugin marketplace add <your-username>/show-me-the-receipts
claude plugin install show-me-the-receipts@show-me-the-receipts
```

## Credits

仓库结构（README / hooks / 多运行时清单）参考 [ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd)。规则内容为原创。

## License

[MIT](LICENSE)。

用完了记得贴 receipts。⭐ 如果有帮你躲过一句"希望有帮助"。
