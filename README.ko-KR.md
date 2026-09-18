<p align="center"><img src="./logo.png" alt="Show Me The Receipts — 근거를 보여줘 AI 출력 스킬" width="140" /></p>

<h1 align="center">Show Me The Receipts</h1>

<p align="center"><strong>근거를 보여줘. AI가 그럴듯한 말 속에 정답을 묻는 것을 막아줍니다.</strong></p>

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
  <strong title="한국어" aria-label="한국어">🇰🇷 한국어</strong> ·
  <a href="README.es-ES.md" title="Español" aria-label="Español">🇪🇸 Español</a> ·
  <a href="README.pt-BR.md" title="Português (Brasil)" aria-label="Português (Brasil)">🇧🇷 Português (Brasil)</a> ·
  <a href="README.fr-FR.md" title="Français" aria-label="Français">🇫🇷 Français</a> ·
  <a href="README.de-DE.md" title="Deutsch" aria-label="Deutsch">🇩🇪 Deutsch</a> ·
  <a href="README.ru-RU.md" title="Русский" aria-label="Русский">🇷🇺 Русский</a> ·
  <a href="README.vi-VN.md" title="Tiếng Việt" aria-label="Tiếng Việt">🇻🇳 Tiếng Việt</a>
</p>

**Show Me The Receipts(근거를 보여줘)** 는 MIT 오픈소스 에이전트 스킬입니다: 리포트·회고·코드 리뷰·주간 보고에서 결론을 첫 줄에 쓰고, 사실·판단·미지의 것을 분리하며, 모든 액션에 담당자·기한·검수 가능한 산출물을 강제하고, AI 특유 문어를 제거하고, ADHD 친화 포맷을 기본 적용합니다.

## 설치

```bash
claude plugin marketplace add lohyeulam-stack/show-me-the-receipts
claude plugin install show-me-the-receipts@show-me-the-receipts
```

재시작 후 `/show-me-the-receipts`로 활성화. Codex / Cursor / OpenCode / 웹 LLM 설치는 [INSTALL.md](INSTALL.md) 참고.

## 왜 필요한가

리포트의 흔한 병: "안정적으로 개선 중", "개발 쪽에서 후속 조치 중", "빠른 시일 내 처리", "클로즈드 루프 구축" — 다 읽고도 무슨 일이 있었는지, 어디서 막혔는지, 누구에게 물어볼지 모른다. LLM은 정확히 이 실패 패턴에 능숙하다.

이 스킬은 두 훌륭한 프로젝트의 어깨 위에 서며 감사드립니다: [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh)(중국어 AI 문어 체크리스트), [ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd)(ADHD 친화 출력과 플러그인 구조). 그 위에 이 저장소가 새 층을 더합니다: 근거 등급화, 액션 3요소, 공식 문서 규율, 회고 진단 기준.

## Before / After

**😵 Before**
> 이번 분기는 전반적으로 안정적인 성장세를 보였고, 광고 연동은 개발 쪽에서 후속 조치 중이며 조만간 해결될 예정입니다. 미래가 밝습니다!

**🧾 After**
> Campaign Update 통합 테스트 실패: `budget_mode` 검증에서 error code 30100, Campaign 4건 저장 불가(9/17 16:00 기준).
> - Target 주간 10건 / Actual 7건 / Gap −3건, 달성률 70%
> - Cause 2건은 TikTok API 검증 블록, 1건은 실계정 권한 대기
> - 다음 — 담당: 백엔드 A / 기한: 9/18 18:00 / 산출물: 성공·실패 요청 및 error code 기록
> - "개선 여지": 데이터 없음 → **미지**로 표기

## 핵심 규칙 10

1. 첫 줄은 결론 또는 다음 액션. 인사말·"도움이 되길" 금지.
2. 근거 4단계: 1차 사실 / 추적 가능한 경험 / 표시한 추론 / 주관 의견.
3. 모르는 건 모른다고. 숫자·시간·담당자·인과 날조 금지.
4. 액션 3요소: 담당자·기한·산출물.
5. 5가지 구체화: 주체·시간·결과·문제·방안.
6. 진행 보고는 Target / Actual / Gap / Cause 먼저.
7. 공식 문서 규율: 메타 발화 금지, 제목 뒤 도입부, 무정보어 금지.
8. 회고 진단: 판단에 근거, 원문 인용 보존, 인과 사슬, 비판 대상 특정.
9. AI 문어 제거: "엔파워/클로즈드 루프/단순한 X가 아닌 Y" 패턴 삭제.
10. ADHD 친화: 번호 단계, 턴마다 상태 재정리, 구체적 시간 추정, 목록 5개 제한.

전문: [SKILL.md](./skills/show-me-the-receipts/SKILL.md)

## 상시 활성화

```bash
touch ~/.claude/.show-me-the-receipts-always
```

## FAQ

**i-have-adhd, Humanizer-zh와의 관계는?**
감사가 대부분입니다. ADHD 친화 포맷 층과 저장소 구조는 i-have-adhd에서, 중국어 AI 문어 어휘는 Humanizer-zh에서 왔습니다. 둘 다 star 부탁드려요.

**영어에서도 되나요?**
근거 등급·액션 3요소·Gap 보고는 언어 비의존. AI 문어 목록은 중국어 중심이며 영어 목록 PR 환영.

## 크레딧

- [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh) — 중국어 AI 문어 체크리스트 기준. 감사 🙏
- [ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd) — ADHD 출력 층과 플러그인 구조 참고. 감사 🙏

## License

[MIT](LICENSE)

---

<p align="center">다 썼으면 영수증을 붙이세요. ⭐ "Great question!" 한 번을 피했다면.</p>
