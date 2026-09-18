<p align="center"><img src="./logo.png" alt="Show Me The Receipts — 根拠を示せ。AI 出力スキル" width="140" /></p>

<h1 align="center">Show Me The Receipts</h1>

<p align="center"><strong>根拠を示せ。AI が美しい言葉で答えを埋めるのをやめる。</strong></p>

<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="MIT License"></a>
  <a href="https://github.com/lohyeulam-stack/show-me-the-receipts/releases"><img src="https://img.shields.io/badge/release-v0.1.0-informational" alt="Release"></a>
  <a href="#-install"><img src="https://img.shields.io/badge/Claude%20Code-plugin-blue?style=flat" alt="Claude Code plugin"></a>
  <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg" alt="PRs welcome">
</p>

<p align="center">
  <a href="README.md" title="English" aria-label="English">🇬🇧 English</a> ·
  <a href="README.zh-CN.md" title="简体中文" aria-label="简体中文">🇨🇳 简体中文</a> ·
  <a href="README.zh-TW.md" title="繁體中文" aria-label="繁體中文">🇹🇼 繁體中文</a> ·
  <strong title="日本語" aria-label="日本語">🇯🇵 日本語</strong> ·
  <a href="README.ko-KR.md" title="한국어" aria-label="한국어">🇰🇷 한국어</a> ·
  <a href="README.es-ES.md" title="Español" aria-label="Español">🇪🇸 Español</a> ·
  <a href="README.pt-BR.md" title="Português (Brasil)" aria-label="Português (Brasil)">🇧🇷 Português (Brasil)</a> ·
  <a href="README.fr-FR.md" title="Français" aria-label="Français">🇫🇷 Français</a> ·
  <a href="README.de-DE.md" title="Deutsch" aria-label="Deutsch">🇩🇪 Deutsch</a> ·
  <a href="README.ru-RU.md" title="Русский" aria-label="Русский">🇷🇺 Русский</a> ·
  <a href="README.vi-VN.md" title="Tiếng Việt" aria-label="Tiếng Việt">🇻🇳 Tiếng Việt</a>
</p>

**Show Me The Receipts（根拠を示せ）** は MIT オープンソースのエージェントスキル：レポート・振り返り・コードレビュー・週次報告で、結論を最初に書く／事実・判断・不明を分層する／すべてのアクションに「担当者・期限・検収可能な成果物」を強制し、AI 臭い文章を除去し、ADHD 配慮フォーマットをデフォルトで適用する。

## インストール

```bash
claude plugin marketplace add lohyeulam-stack/show-me-the-receipts
claude plugin install show-me-the-receipts@show-me-the-receipts
```

再起動後 `/show-me-the-receipts` で有効化。Codex / Cursor / OpenCode / Web LLM 向けは [INSTALL.md](INSTALL.md) 参照。

## なぜ必要か

報告書のよくある病：「順調に改善」「開発側が追跡中」「至急対応」「クローズドループを構築」— 読んでも何が起きたか、どこで詰まっているか、次に誰に聞くかが分からない。LLM はまさにこの失敗パターンが得意だ。

本スキルは 2 つの優れたプロジェクトの肩に乗っており、感謝します：[op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh)（中国語 AI 文章痕跡チェックリスト）、[ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd)（ADHD 配慮出力とプラグイン構造）。その上に本リポジトリは新層を追加：証拠の階層化、アクション三要素、正式文書規律、振り返り診断基準。

## Before / After

**😵 Before**
> 今四半期は全体として安定した向上が見られ、広告連携は開発側が追跡中で、近日中に解決見込みです。今後の光明を期待します！

**🧾 After**
> Campaign Update 統合テスト失敗：`budget_mode` バリデーションで error code 30100、4 件の Campaign が保存不可（9/17 16:00 時点）。
> - Target：週 10 件 / Actual：7 件 / Gap：−3 件、達成率 70%
> - Cause：2 件は TikTok API バリデーションでブロック、1 件は実アカウント権限待ち
> - 次アクション — 担当者：バックエンド A / 期限：9/18 18:00 / 成果物：成功・失敗リクエストと error code の記録
> - 「改善の余地」：データなし → **不明** と明記

## コアルール（10 条）

1. 1 行目は結論または次のアクション。前置き・「役に立てば」禁止。
2. 証拠 4 階層：一次事実／追跡可能な経験／明示した推論／主観意見。
3. 不明は不明と書く。数字・時間・担当者・因果の捏造禁止。
4. アクション三要素：担当者・期限・成果物。
5. 5 類型の具体化：主体・時間・結果・問題・方案。
6. 進捗は Target / Actual / Gap / Cause を先に。
7. 正式文書規律：メタ発話禁止、見出し後に導入文、ゼロ情報語禁止。
8. 振り返り診断：判断に証拠、原文引用保持、因果連鎖、批判の的を特定。
9. AI 臭除去：「エンパワー／ループ／〜ではなく、むしろ〜」の硬直パターン削除。
10. ADHD 配慮：番号付きステップ、ターン毎の状況再提示、具体的な時間見積、リストは 5 項目まで。

全文：[SKILL.md](./skills/show-me-the-receipts/SKILL.md)

## 常時有効化

```bash
touch ~/.claude/.show-me-the-receipts-always
```

## FAQ

**i-have-adhd や Humanizer-zh との関係は？**
感謝が主です。ADHD 配慮フォーマット層とリポジトリ構造は i-have-adhd に、中国語 AI 臭語彙表は Humanizer-zh に由来します。両方ともスターしてください。

**英語でも使える？**
証拠階層・アクション三要素・ギャップ報告は言語非依存。AI 臭語彙表は中国語中心で、英語リストは PR 歓迎。

## クレジット

- [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh) — 中国語 AI 文章痕跡チェックリスト。感謝 🙏
- [ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd) — ADHD 出力層とプラグイン構造。感謝 🙏

## License

[MIT](LICENSE)

---

<p align="center">使ったらレシートを貼ること。⭐「Great question!」を 1 回スキップできたら。</p>
