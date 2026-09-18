<p align="center"><img src="./logo.png" alt="Show Me The Receipts — skill de salida basada en evidencia" width="140" /></p>

<h1 align="center">Show Me The Receipts</h1>

<p align="center"><strong>Demuestra con evidencia. Evita que tu agente de IA entierre la respuesta bajo palabras bonitas.</strong></p>

<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="MIT License"></a>
  <a href="https://github.com/lohyeulam-stack/show-me-the-receipts/releases"><img src="https://img.shields.io/badge/release-v0.1.0-informational" alt="Release"></a>
  <a href="#-install"><img src="https://img.shields.io/badge/Claude%20Code-plugin-blue?style=flat" alt="Claude Code plugin"></a>
  <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg" alt="PRs welcome">
</p>

<p align="center">
  <a href="README.md" title="English" aria-label="English">🇬🇧 English</a> ·
  <a href="README.zh-CN.md" title="简体中文" aria-label="简体中文">🇨🇳 简体中文</a> ·
  <a href="README.zh-TW.md" title="繁體中文" aria-label="繁體中文">🇨🇳 繁體中文</a> ·
  <a href="README.ja-JP.md" title="日本語" aria-label="日本語">🇯🇵 日本語</a> ·
  <a href="README.ko-KR.md" title="한국어" aria-label="한국어">🇰🇷 한국어</a> ·
  <strong title="Español" aria-label="Español">🇪🇸 Español</strong> ·
  <a href="README.pt-BR.md" title="Português (Brasil)" aria-label="Português (Brasil)">🇧🇷 Português (Brasil)</a> ·
  <a href="README.fr-FR.md" title="Français" aria-label="Français">🇫🇷 Français</a> ·
  <a href="README.de-DE.md" title="Deutsch" aria-label="Deutsch">🇩🇪 Deutsch</a> ·
  <a href="README.ru-RU.md" title="Русский" aria-label="Русский">🇷🇺 Русский</a> ·
  <a href="README.vi-VN.md" title="Tiếng Việt" aria-label="Tiếng Việt">🇻🇳 Tiếng Việt</a>
</p>

**Show Me The Receipts** es un skill open-source (MIT) para agentes de IA que impone salida basada en evidencia en informes, retrospectivas, code reviews y reportes de estado: conclusión en la primera línea, hechos separados de juicios y desconocidos, cada acción con responsable, fecha límite y entregable verificable — con vocabulario de relleno de IA eliminado y formato apto para TDAH por defecto.

## Instalación

```bash
claude plugin marketplace add lohyeulam-stack/show-me-the-receipts
claude plugin install show-me-the-receipts@show-me-the-receipts
```

Reinicia y ejecuta `/show-me-the-receipts`. Para Codex / Cursor / OpenCode / LLM web: [INSTALL.md](INSTALL.md).

## Por qué

Los informes mueren de mil frases huecas: *"se mejoró de forma estable", "el equipo de dev lo está siguiendo", "se resolverá ASAP"* — tras leerlos nadie sabe qué pasó, dónde está el bloqueo ni a quién preguntar. Los LLM dominan exactamente ese modo de fallo.

Este skill se apoya en dos proyectos excelentes a los que agradecemos: [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh), cuya lista de señales de escritura de IA en chino alimenta nuestras reglas anti-slop, y [ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd), del que seguimos el formato apto para TDAH y la arquitectura de plugins. Sobre su base añadimos: niveles de evidencia, tríada de acción y disciplina de documentos formales y retrospectivas.

## Before / After

**😵 Before**
> ¡Buena pregunta! Este trimestre mostró progreso estable en general. La integración se resolverá pronto. ¡El futuro es brillante!

**🧾 After**
> Campaign Update falla en la validación de `budget_mode`: error code 30100, 4 campaigns sin guardar (al 17 sep 16:00).
> - **Target** 10 · **Actual** 7 · **Gap** −3, 70%
> - **Cause** 2 bloqueados por validación de la API de TikTok, 1 esperando acceso a cuenta real
> - **Siguiente** — responsable: Backend A · fecha: 18 sep 18:00 · entregable: logs de peticiones OK/fallidas con error codes
> - "Margen de mejora": sin datos → **desconocido**

## Las 10 reglas

1. Primera línea = conclusión o próxima acción. Sin preámbulos ni "¡Espero que ayude!".
2. Cuatro niveles de evidencia: hecho verificado / experiencia trazable / inferencia etiquetada / opinión.
3. Lo desconocido se escribe "desconocido". Prohibido inventar números, fechas, responsables o causalidad.
4. Tríada de acción: responsable · fecha límite · entregable.
5. Cinco concreciones: sujeto, tiempo, resultado, problema, plan.
6. Reporte de progreso con Target / Actual / Gap / Cause.
7. Disciplina de documento formal: sin meta-comentarios, párrafo introductorio bajo cada título, cero palabras vacías.
8. Diagnóstico en retrospectivas: evidencia tras cada juicio, citas textuales, cadena causal, crítica precisa.
9. Anti-slop: elimina aperturas de relleno, hype, atribuciones vagas, rangos falsos.
10. Aptos para TDAH: pasos numerados, estado reiterado por turno, estimaciones concretas, listas ≤ 5.

Texto completo: [SKILL.md](./skills/show-me-the-receipts/SKILL.md)

## Modo siempre activo

```bash
touch ~/.claude/.show-me-the-receipts-always
```

## FAQ

**¿Qué relación con i-have-adhd y Humanizer-zh?**
Sobre todo gratitud: el formato TDAH y la estructura del repo vienen de i-have-adhd; el vocabulario anti-slop en chino, de Humanizer-zh. Ve a darles estrella también.

**¿Funciona en inglés?**
Niveles de evidencia, tríada de acción y reporte de gaps son independientes del idioma. La lista de vocabulario slop es chino-first; PRs con señales en inglés bienvenidas.

## Créditos

- [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh) — lista de señales de escritura IA en chino. Gracias 🙏
- [ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd) — formato TDAH y empaquetado multi-runtime. Gracias 🙏

## Licencia

[MIT](LICENSE)

---

<p align="center">Trae siempre los tickets. ⭐ si te ahorró un "¡Buena pregunta!".</p>
