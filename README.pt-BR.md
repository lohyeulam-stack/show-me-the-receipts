<p align="center"><img src="./logo.png" alt="Show Me The Receipts — skill de saída baseada em evidências" width="140" /></p>

<h1 align="center">Show Me The Receipts</h1>

<p align="center"><strong>Mostre os comprovantes. Impede que seu agente de IA enterre a resposta sob palavras bonitas.</strong></p>

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
  <strong title="Português (Brasil)" aria-label="Português (Brasil)">🇧🇷 Português (Brasil)</strong> ·
  <a href="README.fr-FR.md" title="Français" aria-label="Français">🇫🇷 Français</a> ·
  <a href="README.de-DE.md" title="Deutsch" aria-label="Deutsch">🇩🇪 Deutsch</a> ·
  <a href="README.ru-RU.md" title="Русский" aria-label="Русский">🇷🇺 Русский</a> ·
  <a href="README.vi-VN.md" title="Tiếng Việt" aria-label="Tiếng Việt">🇻🇳 Tiếng Việt</a>
</p>

**Show Me The Receipts** é um skill open-source (MIT) para agentes de IA que impõe saída baseada em evidências em relatórios, retrospectivas, code reviews e status updates: conclusão na primeira linha, fatos separados de julgamentos e desconhecidos, cada ação com dono, prazo e entregável verificável — com jargão de IA removido e formatação amigável a TDAH por padrão.

## Instalação

```bash
claude plugin marketplace add lohyeulam-stack/show-me-the-receipts
claude plugin install show-me-the-receipts@show-me-the-receipts
```

Reinicie e rode `/show-me-the-receipts`. Codex / Cursor / OpenCode / LLM web: [INSTALL.md](INSTALL.md).

## Por quê

Relatórios morrem de frases ocas: *"houve melhora consistente", "o time de dev está acompanhando", "resolvemos o quanto antes"* — depois de ler, ninguém sabe o que aconteceu, onde travou e com quem falar. LLMs dominam exatamente esse modo de falha.

Este skill se apoia em dois projetos excelentes, aos quais agradecemos: [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh), cuja lista de marcas de escrita de IA em chinês alimenta nossas regras anti-slop, e [ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd), de onde seguimos o formato TDAH e a arquitetura de plugins. Sobre a base deles adicionamos: níveis de evidência, tríade de ação e disciplina de documentos formais e retrospectivas.

## Before / After

**😵 Before**
> Ótima pergunta! Este trimestre mostrou progresso consistente. A integração será resolvida em breve. O futuro é brilhante!

**🧾 After**
> Campaign Update falha na validação de `budget_mode`: error code 30100, 4 campaigns não salvos (às 17/09 16:00).
> - **Target** 10 · **Actual** 7 · **Gap** −3, 70%
> - **Cause** 2 travados na validação da API do TikTok, 1 aguardando acesso à conta real
> - **Próximo** — dono: Backend A · prazo: 18/09 18:00 · entregável: logs de requisições ok/falhas com error codes
> - "Há margem de melhoria": sem dados → **desconhecido**

## As 10 regras

1. Primeira linha = conclusão ou próxima ação. Sem preâmbulo nem "Espero que ajude!".
2. Quatro níveis de evidência: fato verificado / experiência rastreável / inferência rotulada / opinião.
3. Desconhecido se escreve "desconhecido". Proibido inventar números, datas, donos ou causalidade.
4. Tríade de ação: dono · prazo · entregável.
5. Cinco concretizações: sujeito, tempo, resultado, problema, plano.
6. Progresso com Target / Actual / Gap / Cause.
7. Disciplina de documento formal: sem meta-comentários, parágrafo de abertura sob cada título, zero palavras vazias.
8. Diagnóstico em retrospectivas: evidência após cada julgamento, citações verbatim, cadeia causal, crítica precisa.
9. Anti-slop: remova aberturas de preenchimento, hype, atribuições vagas, falsos intervalos.
10. Amigável a TDAH: passos numerados, estado reafirmado por turno, estimativas concretas, listas ≤ 5.

Texto completo: [SKILL.md](./skills/show-me-the-receipts/SKILL.md)

## Modo sempre ativo

```bash
touch ~/.claude/.show-me-the-receipts-always
```

## FAQ

**Qual a relação com i-have-adhd e Humanizer-zh?**
Gratidão, sobretudo: o formato TDAH e a estrutura do repo vêm do i-have-adhd; o vocabulário anti-slop em chinês, do Humanizer-zh. Vá dar estrela neles também.

**Funciona em inglês?**
Níveis de evidência, tríade de ação e reporte de gaps são independentes de idioma. A lista de vocabulário slop é chino-first; PRs com marcas em inglês são bem-vindas.

## Créditos

- [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh) — lista de marcas de escrita de IA em chinês. Obrigado 🙏
- [ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd) — formato TDAH e empacotamento multi-runtime. Obrigado 🙏

## Licença

[MIT](LICENSE)

---

<p align="center">Traga os comprovantes. ⭐ se economizou um "Ótima pergunta!".</p>
