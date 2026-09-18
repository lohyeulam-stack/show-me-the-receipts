<p align="center"><img src="./logo.png" alt="Show Me The Receipts — belegbasierte AI-Ausgabe Skill" width="140" /></p>

<h1 align="center">Show Me The Receipts</h1>

<p align="center"><strong>Belege, bitte. Damit Ihr KI-Agent die Antwort nicht unter schönen Worten begräbt.</strong></p>

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
  <a href="README.ja-JP.md" title="日本語" aria-label="日本語">🇯🇵 日本語</a> ·
  <a href="README.ko-KR.md" title="한국어" aria-label="한국어">🇰🇷 한국어</a> ·
  <a href="README.es-ES.md" title="Español" aria-label="Español">🇪🇸 Español</a> ·
  <a href="README.pt-BR.md" title="Português (Brasil)" aria-label="Português (Brasil)">🇧🇷 Português (Brasil)</a> ·
  <a href="README.fr-FR.md" title="Français" aria-label="Français">🇫🇷 Français</a> ·
  <strong title="Deutsch" aria-label="Deutsch">🇩🇪 Deutsch</strong> ·
  <a href="README.ru-RU.md" title="Русский" aria-label="Русский">🇷🇺 Русский</a> ·
  <a href="README.vi-VN.md" title="Tiếng Việt" aria-label="Tiếng Việt">🇻🇳 Tiếng Việt</a>
</p>

**Show Me The Receipts** ist ein Open-Source-Agent-Skill (MIT), der KI-Ausgaben in Berichten, Retrospektiven, Code-Reviews und Status-Updates zu belegbasierter Disziplin zwingt: Schlussfolgerung in der ersten Zeile, Fakten getrennt von Urteilen und Unbekanntem, jede Aktion mit Verantwortlichem · Frist · prüfbarem Ergebnis — AI-Buzzwords entfernt, ADHS-freundliches Formatting standardmäßig aktiv.

## Installation

```bash
claude plugin marketplace add lohyeulam-stack/show-me-the-receipts
claude plugin install show-me-the-receipts@show-me-the-receipts
```

Neustart, dann `/show-me-the-receipts`. Codex / Cursor / OpenCode / Web-LLM: [INSTALL.md](INSTALL.md).

## Warum

Berichte sterben an hohlen Floskeln: *"stetige Verbesserung", "das Dev-Team ist dran", "ASAP erledigt"* — nach dem Lesen weiß niemand, was passierte, wo es klemmt, wen man fragen muss. LLMs beherrschen genau dieses Fehlermuster.

Dieser Skill steht auf den Schultern zweier großartiger Projekte, denen wir danken: [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh) liefert die Checkliste chinesischer KI-Schreibmuster für unsere Anti-Slop-Regeln; [ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd) liefert ADHS-Formatting und Plugin-Architektur. Darauf baut dieser Repo eine neue Schicht: Evidenzstufen, Aktions-Trias, Dokumenten-Disziplin und Retro-Diagnose.

## Before / After

**😵 Before**
> Gute Frage! Dieses Quartal zeigte stetige Fortschritte. Die Integration wird bald gelöst. Die Zukunft ist rosig!

**🧾 After**
> Campaign Update schlägt bei `budget_mode`-Validierung fehl: Error Code 30100, 4 Kampagnen ungespeichert (Stand 17.09. 16:00).
> - **Target** 10 · **Actual** 7 · **Gap** −3, 70 %
> - **Cause** 2 blockiert durch TikTok-API-Validierung, 1 wartet auf Echtzugriff
> - **Nächster Schritt** — Verantwortlicher: Backend A · Frist: 18.09. 18:00 · Ergebnis: Logs erfolgreicher/fehlgeschlagener Requests mit Error Codes
> - „Verbesserungspotenzial": keine Daten → **unbekannt**

## Die 10 Regeln

1. Erste Zeile = Schlussfolgerung oder nächste Aktion. Kein Vorspann, kein „Hoffentlich hilft's!".
2. Vier Evidenzstufen: verifizierte Tatsache / nachvollziehbare Erfahrung / markierte Inferenz / Meinung.
3. Unbekannt wird als „unbekannt" geschrieben. Erfinden von Zahlen, Daten, Verantwortlichen, Kausalität verboten.
4. Aktions-Trias: Verantwortlicher · Frist · Ergebnis.
5. Fünf Konkretisierungen: Subjekt, Zeit, Ergebnis, Problem, Plan.
6. Fortschritt als Target / Actual / Gap / Cause.
7. Dokumenten-Disziplin: keine Meta-Kommentare, Einleitungsabsatz unter jedem Titel, Null-Info-Wörter verboten.
8. Retro-Diagnose: Urteil nur mit Beleg, Originalzitate bleiben, Kausalkette je Problem, Kritik präzise.
9. Anti-Slop: Füll-Opener, Hype, vage Quellen, falsche Bereiche streichen.
10. ADHS-freundlich: nummerierte Schritte, Status je Turn, konkrete Zeitschätzungen, Listen ≤ 5.

Volltext: [SKILL.md](./skills/show-me-the-receipts/SKILL.md)

## Dauerhaft aktiv

```bash
touch ~/.claude/.show-me-the-receipts-always
```

## FAQ

**Verhältnis zu i-have-adhd und Humanizer-zh?**
Vor allem Dankbarkeit: ADHS-Formatierung und Repo-Struktur stammen von i-have-adhd, das chinesische Anti-Slop-Vokabular von Humanizer-zh. Geben Sie beiden auch einen Stern.

**Funktioniert auf Englisch?**
Evidenzstufen, Aktions-Trias und Gap-Reporting sind sprachunabhängig. Die Slop-Vokabelliste ist chinesisch-zentriert; PRs für englische Marker willkommen.

## Credits

- [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh) — Checkliste chinesischer KI-Schreibmuster. Danke 🙏
- [ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd) — ADHS-Ausgabe und Multi-Runtime-Packaging. Danke 🙏

## Lizenz

[MIT](LICENSE)

---

<p align="center">Bring Belege. ⭐ wenn es Ihnen ein „Gute Frage!" erspart hat.</p>
