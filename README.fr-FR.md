<p align="center"><img src="./logo.png" alt="Show Me The Receipts — skill de sortie fondée sur les preuves" width="140" /></p>

<h1 align="center">Show Me The Receipts</h1>

<p align="center"><strong>Montre-moi les preuves. Empêche votre agent IA d'enfouir la réponse sous de belles phrases.</strong></p>

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
  <strong title="Français" aria-label="Français">🇫🇷 Français</strong> ·
  <a href="README.de-DE.md" title="Deutsch" aria-label="Deutsch">🇩🇪 Deutsch</a> ·
  <a href="README.ru-RU.md" title="Русский" aria-label="Русский">🇷🇺 Русский</a> ·
  <a href="README.vi-VN.md" title="Tiếng Việt" aria-label="Tiếng Việt">🇻🇳 Tiếng Việt</a>
</p>

**Show Me The Receipts** est un skill open-source (MIT) pour agents IA qui impose une sortie fondée sur les preuves dans les rapports, rétrospectives, revues de code et points de statut : conclusion en première ligne, faits séparés des jugements et de l'inconnu, chaque action avec responsable, échéance et livrable vérifiable — vocabulaire IA superflu supprimé, mise en page adaptée TDAH par défaut.

## Installation

```bash
claude plugin marketplace add lohyeulam-stack/show-me-the-receipts
claude plugin install show-me-the-receipts@show-me-the-receipts
```

Redémarrez puis lancez `/show-me-the-receipts`. Codex / Cursor / OpenCode / LLM web : [INSTALL.md](INSTALL.md).

## Pourquoi

Les rapports meurent de mille phrases creuses : *« amélioration constante », « l'équipe dev suit le sujet », « traité au plus vite »* — après lecture, personne ne sait ce qui s'est passé, où ça bloque, ni à qui demander. Les LLM excellent dans ce mode d'échec.

Ce skill s'appuie sur deux excellents projets auxquels nous sommes reconnaissants : [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh), dont la liste des tics d'écriture IA en chinois nourrit nos règles anti-slop, et [ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd), dont nous suivons le formatage TDAH et l'architecture de plugins. Par-dessus leur base, ce dépôt ajoute : niveaux de preuve, triade d'action et discipline des documents formels et rétrospectives.

## Before / After

**😵 Before**
> Bonne question ! Ce trimestre montre des progrès réguliers. L'intégration sera résolue bientôt. L'avenir est prometteur !

**🧾 After**
> Campaign Update échoue à la validation `budget_mode` : error code 30100, 4 campaigns non sauvegardés (au 17/09 16:00).
> - **Target** 10 · **Actual** 7 · **Gap** −3, 70 %
> - **Cause** 2 bloqués sur la validation de l'API TikTok, 1 en attente d'accès compte réel
> - **Prochaine étape** — responsable : Backend A · échéance : 18/09 18:00 · livrable : journaux de requêtes OK/échouées avec error codes
> - « Marge de progression » : aucune donnée → **inconnu**

## Les 10 règles

1. Première ligne = conclusion ou prochaine action. Ni préambule ni « J'espère que ça aide ! ».
2. Quatre niveaux de preuve : fait vérifié / expérience traçable / inférence étiquetée / opinion.
3. L'inconnu s'écrit « inconnu ». Interdit d'inventer chiffres, dates, responsables ou causalité.
4. Triade d'action : responsable · échéance · livrable.
5. Cinq concrétisations : sujet, temps, résultat, problème, plan.
6. Progrès en Target / Actual / Gap / Cause.
7. Discipline documentaire : pas de méta-commentaires, paragraphe d'introduction sous chaque titre, zéro mot creux.
8. Diagnostic de rétrospective : preuve après chaque jugement, citations verbatim, chaîne causale, critique précise.
9. Anti-slop : supprimer ouvertures de remplissage, hype, attributions vagues, fausses plages.
10. Adapté TDAH : étapes numérotées, état rappelé à chaque tour, estimations concrètes, listes ≤ 5.

Texte complet : [SKILL.md](./skills/show-me-the-receipts/SKILL.md)

## Mode permanent

```bash
touch ~/.claude/.show-me-the-receipts-always
```

## FAQ

**Quel lien avec i-have-adhd et Humanizer-zh ?**
De la gratitude, surtout : le formatage TDAH et la structure du dépôt viennent de i-have-adhd ; le vocabulaire anti-slop chinois, de Humanizer-zh. Allez aussi leur mettre une étoile.

**Fonctionne en anglais ?**
Niveaux de preuve, triade d'action et reporting d'écarts sont indépendants de la langue. La liste anti-slop est centrée sur le chinois ; les PR pour l'anglais sont bienvenues.

## Crédits

- [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh) — liste de tics d'écriture IA en chinois. Merci 🙏
- [ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd) — formatage TDAH et packaging multi-runtime. Merci 🙏

## Licence

[MIT](LICENSE)

---

<p align="center">Apportez les preuves. ⭐ si ça vous a évité un « Bonne question ! ».</p>
