<p align="center"><img src="./logo.png" alt="Show Me The Receipts — скилл доказательного вывода ИИ" width="140" /></p>

<h1 align="center">Show Me The Receipts</h1>

<p align="center"><strong>Покажите чеки. ИИ-агент перестаёт закапывать ответ под красивые слова.</strong></p>

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
  <a href="README.de-DE.md" title="Deutsch" aria-label="Deutsch">🇩🇪 Deutsch</a> ·
  <strong title="Русский" aria-label="Русский">🇷🇺 Русский</strong> ·
  <a href="README.vi-VN.md" title="Tiếng Việt" aria-label="Tiếng Việt">🇻🇳 Tiếng Việt</a>
</p>

**Show Me The Receipts** — открытый скилл (MIT) для ИИ-агентов, принуждающий отчёты, ретроспективы, код-ревью и статус-апдейты к доказательной дисциплине: вывод в первой строке, факты отделены от суждений и неизвестного, у каждого действия есть ответственный, срок и проверяемый результат — с удалением ИИ-штампов и ADHD-дружественным форматированием по умолчанию.

## Установка

```bash
claude plugin marketplace add lohyeulam-stack/show-me-the-receipts
claude plugin install show-me-the-receipts@show-me-the-receipts
```

Перезапустите и выполните `/show-me-the-receipts`. Codex / Cursor / OpenCode / веб-LLM: [INSTALL.md](INSTALL.md).

## Зачем

Отчёты умирают от пустых фраз: *«стабильное улучшение», «команда разработки в курсе», «сделаем в ближайшее время»* — после прочтения никто не знает, что произошло, где блок и к кому идти. LLM именно в этом и сильны.

Скилл опирается на два прекрасных проекта, которым мы благодарны: [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh) — чек-лист ИИ-штампов в китайском тексте, лёгший в основу анти-слейп-правил, и [ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd) — ADHD-форматирование и архитектура плагинов. Поверх их фундамента этот репозиторий добавляет: уровни доказательств, триаду действия и дисциплину официальных документов и ретроспектив.

## Before / After

**😵 Before**
> Отличный вопрос! В этом квартале — стабильный прогресс. Интеграцию скоро решат. Будущее светлое!

**🧾 After**
> Campaign Update падает на валидации `budget_mode`: error code 30100, 4 кампании не сохранены (на 17.09 16:00).
> - **Target** 10 · **Actual** 7 · **Gap** −3, 70%
> - **Cause** 2 блокирует валидация TikTok API, 1 ждёт доступа к реальному аккаунту
> - **Дальше** — ответственный: Backend A · срок: 18.09 18:00 · результат: логи успешных/ошибочных запросов с error codes
> - «Есть потенциал улучшения»: данных нет → **неизвестно**

## 10 правил

1. Первая строка = вывод или следующее действие. Без вступлений и «Надеюсь, помогло!».
2. Четыре уровня доказательств: проверенный факт / прослеживаемый опыт / помеченное умозаключение / мнение.
3. Неизвестное пишется как «неизвестно». Запрещено выдумывать цифры, даты, ответственных, причинность.
4. Триада действия: ответственный · срок · результат.
5. Пять конкретизаций: субъект, время, результат, проблема, план.
6. Прогресс через Target / Actual / Gap / Cause.
7. Дисциплина документа: без метакомментариев, вводный абзац под каждый заголовок, ноль слов-пустышек.
8. Диагностика ретроспектив: за каждым суждением — доказательство, цитаты дословно, причинная цепочка, критика точна.
9. Анти-слейп: убрать мусорные вступления, хайп, размытые ссылки, ложные диапазоны.
10. ADHD-дружелюбие: нумерованные шаги, статус каждый ход, конкретные оценки времени, списки ≤ 5.

Полный текст: [SKILL.md](./skills/show-me-the-receipts/SKILL.md)

## Всегда включено

```bash
touch ~/.claude/.show-me-the-receipts-always
```

## FAQ

**Причём тут i-have-adhd и Humanizer-zh?**
Прежде всего благодарность: ADHD-форматирование и структура репо — от i-have-adhd, китайский анти-слейп-словарь — от Humanizer-zh. Поставьте и им звёзды.

**Работает с английским?**
Уровни доказательств, триада действия и отчёт о разрывах не зависят от языка. Словарь штампов заточен под китайский; PR с английским списком приветствуются.

## Credits

- [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh) — чек-лист ИИ-штампов (китайский). Спасибо 🙏
- [ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd) — ADHD-вывод и мультирантайм-упаковка. Спасибо 🙏

## Лицензия

[MIT](LICENSE)

---

<p align="center">Несите чеки. ⭐ если сэкономили вам одно «Отличный вопрос!».</p>
