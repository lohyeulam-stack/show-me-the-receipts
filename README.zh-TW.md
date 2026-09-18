<p align="center"><img src="./logo.png" alt="Show Me The Receipts —— 拿證據來的 AI 輸出紀律 Skill" width="140" /></p>

<h1 align="center">Show Me The Receipts</h1>

<p align="center"><strong>拿證據來。讓 AI 不再把答案埋進漂亮話裡。</strong></p>

<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="MIT License"></a>
  <a href="https://github.com/lohyeulam-stack/show-me-the-receipts/releases"><img src="https://img.shields.io/badge/release-v0.1.0-informational" alt="Release"></a>
  <a href="#-install"><img src="https://img.shields.io/badge/Claude%20Code-plugin-blue?style=flat" alt="Claude Code plugin"></a>
  <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg" alt="PRs welcome">
</p>

<p align="center">
  <a href="README.md" title="English" aria-label="English">🇬🇧 English</a> ·
  <a href="README.zh-CN.md" title="简体中文" aria-label="简体中文">🇨🇳 简体中文</a> ·
  <strong title="繁體中文" aria-label="繁體中文">🇹🇼 繁體中文</strong> ·
  <a href="README.ja-JP.md" title="日本語" aria-label="日本語">🇯🇵 日本語</a> ·
  <a href="README.ko-KR.md" title="한국어" aria-label="한국어">🇰🇷 한국어</a> ·
  <a href="README.es-ES.md" title="Español" aria-label="Español">🇪🇸 Español</a> ·
  <a href="README.pt-BR.md" title="Português (Brasil)" aria-label="Português (Brasil)">🇧🇷 Português (Brasil)</a> ·
  <a href="README.fr-FR.md" title="Français" aria-label="Français">🇫🇷 Français</a> ·
  <a href="README.de-DE.md" title="Deutsch" aria-label="Deutsch">🇩🇪 Deutsch</a> ·
  <a href="README.ru-RU.md" title="Русский" aria-label="Русский">🇷🇺 Русский</a> ·
  <a href="README.vi-VN.md" title="Tiếng Việt" aria-label="Tiếng Việt">🇻🇳 Tiếng Việt</a>
</p>

**Show Me The Receipts（拿證據來）** 是一個 MIT 開源的 Agent Skill：強制 AI 在分析報告、復盤、代碼評審、週報中做到結論先行、事實與判斷和未知分層、每個行動落到負責人 + 完成時間 + 可驗收交付物，同時去除 AI 寫作痕跡、預設 ADHD 友善排版。

## 安裝

```bash
claude plugin marketplace add lohyeulam-stack/show-me-the-receipts
claude plugin install show-me-the-receipts@show-me-the-receipts
```

重啟後輸入 `/show-me-the-receipts` 啟用。Codex / Cursor / OpenCode / 網頁版通用安裝見 [INSTALL.md](INSTALL.md)。

## 為什麼需要它

報告最常見的病：「穩中有升」「開發那邊在跟進」「盡快處理」「形成閉環抓手」—— 讀完仍然不知道發生了什麼、卡在哪、下一步找誰。LLM 恰好精通這種失敗模式。

本 Skill 站在兩個優秀專案的肩膀上，並向它們致謝：[op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh) 提供中文 AI 寫作痕跡清單；[ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd) 提供 ADHD 友善輸出層與外掛結構。在它們的地基之上，本倉庫補上新一層：證據分級、行動三要素、正式文件紀律、復盤診斷標準。

## Before / After

**😵 Before**

> 本季度整體表現穩中有升，廣告接入開發那邊還在跟進，預計後續會盡快解決。專家認為仍有提升空間，總之未來一片光明！

**🧾 After**

> Campaign Update 聯調未通過：`budget_mode` 參數校驗返回 error code 30100，4 個 Campaign 無法儲存（截至 9 月 17 日 16:00）。
>
> - Target：本週 10 項；Actual：7 項；Gap：少 3 項，完成率 70%。
> - Cause：2 項卡在 TikTok API 參數校驗，1 項等待真實帳戶權限。
> - 下一步——負責人：後端 A；完成時間：9 月 18 日 18:00 前；交付物：成功/失敗請求與 error code 記錄。
> - 「鏈路穩定性」無對應資料，標記為**未知**。

## 核心規則

1. 第一行就是結論或下一步，禁止開場白和「希望有幫助」。
2. 證據四級：一手證據 / 可追溯經驗 / 標註過的推斷 / 主觀意見。
3. 未知就寫未知，禁止編造數字、時間、負責人、因果。
4. 行動三要素：負責人、完成時間、交付物；未知寫「待確定」。
5. 五類具體化：主體、時間、結果、問題、方案。
6. 進度先擺 Target / Actual / Gap / Cause。
7. 正式文件紀律：無元話語、標題後必有帽段、零資訊量詞禁用。
8. 復盤診斷紀律：判斷跟證據、保留原話、因果鏈、批評落點具體。
9. 去 AI 味：刪「賦能 / 閉環 / 不僅是…而是… / 三段式硬湊」。
10. ADHD 友善：編號步驟、每輪重述狀態、時間給具體單位、列表不超 5 項。

完整規則見 [SKILL.md](./skills/show-me-the-receipts/SKILL.md)。

## 長期開啟

```bash
touch ~/.claude/.show-me-the-receipts-always
```

## 常見問題

**和 i-have-adhd、Humanizer-zh 是什麼關係？**
主要是感謝。ADHD 友善排版層與倉庫結構來自 i-have-adhd，中文去 AI 味詞表來自 Humanizer-zh，兩處均已致謝，推薦去給它們點 star。

**只適用於中文嗎？**
證據分級與行動三要素與語言無關；去 AI 味詞表以中文為主，英文詞表歡迎 PR。

## 致謝

- [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh)：中文 AI 寫作痕跡清單的基準。感謝 🙏
- [ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd)：ADHD 輸出層與外掛結構的參考。感謝 🙏

## License

[MIT](LICENSE)。

---

<p align="center">用完了記得貼 receipts。⭐ 如果它幫你躲過了一句「希望有幫助」。</p>
