# Punt de tall i quadrícules (Breakpoints & grids)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/805a0a · Font actualitzada el 2025-07-31 · Extret el 2026-10-28

## Introducció
***Breakpoints & grids***
Elements que ajuden a organitzar i alinear de manera coherent els elements visuals dins d'una interfície, garantint així una jerarquia clara i un disseny consistent en diferents dispositius.

## Ús genèric

### Descripció i ús
La quadrícula és la base estructural de tots els elements visuals, des de la tipografia fins a columnes, requadres, icones i il·lustracions. Proporciona estructura i orientació per a tota la presa de decisions creatives. També admet contingut i proporciona un marc coherent, repetible i sensible per al disseny.

### Quadrícules
Els dos entorns comparteixen quadrícula fins al punt de tall* (breakpoint) *de 1280 dp. Un cop arribat a aquest punt tenim dos comportaments diferents segons l’entorn:
**Web ciutadà:**
- 1280 ≤ amplada <1440: marge de 80 dp, espai entre columnes de 40 dp i amplada de columna variable (*Extra large column variable*).
- Amplada ≥1440: amplada de columna de 76 dp i espai entre columnes de 40 dp  fix i marges variables (*Extra large column fix*).
**Web de gestió interna:**
- Utilitzarà marge de 80 dp, espai entre columnes de 40 dp i amplada de columna variable per totes les amplades majors o iguals de 1280dp (*Extra large column variable*).

#### Web Ciutadà

| ***Grid style*** | ***Size*** | ***Nº columns*** | ***Column size*** | ***Content size*** | ***Gutter*** | ***Margin*** |
|---|---|---|---|---|---|---|
| *Small* | 0 - 479 dp | 2 | *Variable* | *Variable* | 16 dp | 12 dp |
| *Medium* | 480 - 959 dp | 4 | *Variable* | *Variable* | 24 dp | 32 dp |
| *Large* | 960 - 1279 dp | 8 | *Variable* | *Variable* | 32 dp | 40 dp |
| *Extra Large column variable* | 1280 - 1439 dp | 12 | *Variable* | *Variable* | 40 dp | 80 dp |
| *Extra Large column fixed* | ≥1440 dp | 12 | 76 dp | 1.352 | 32 dp | *Variable* |

#### Aplicacions de gestió interna (back-office)

| ***Grid style*** | ***Size*** | ***Nº Columns*** | ***Column size*** | ***Content size*** | ***Gutter*** | ***Margin*** |
|---|---|---|---|---|---|---|
| *Small* | 0 - 479 dp | 2 | *Variable* | *Variable* | 16 dp | 12 dp |
| *Medium* | 480 - 959 dp | 4 | *Variable* | *Variable* | 24 dp | 32 dp |
| *Large* | 960 - 1279 dp | 8 | *Variable* | *Variable* | 32 dp | 40 dp |
| *Extra Large column variable* | ≥1280 dp | 12 | *Variable* | *Variable* | 40 dp | 80 dp |

Figma: Grids  (🟢 05. Breakpoints i grids/DOC_Breakpoints&Grids/Grids)

## Versions

### Versions

| **Versió Figma** | **Versió Github** | **Data** | **Descripció** |
|---|---|---|---|
| 2.2.0 | No aplica | 20 de gener, 2025 | Sense canvis |
| 2.1.0 | No aplica | 04 desembre, 2024 | Sense canvis |
| 2.0.0 | No aplica | 02 desembre, 2024 | **Disseny**: Canvis en les quadrícules: - Medium / - Large / - Extra large |
| 1.1.0 | No aplica | 22 novembre, 2024 | Sense canvis |
| 1.0.0 | No aplica | 1 novembre, 2024 | **Disseny** i **documentació** del fonament |

## Pestanya legacy (plantilla genèrica): Spacing
- Do you have a common set of spacings?
- What are the best practices for applying these different levels of spacing?
- What is the corresponding spacing in code? For example:

| **Spacing** | **Sass variable** |
|---|---|
| 4px | `$spacing-xxs` |
| 8px | `$spacing-xs` |
| 16px | `$spacing-s` |
| 24px | `$spacing-m` |
| 48px | `$spacing-l` |
| 96px | `$spacing-xl` |


## Pestanya legacy (plantilla genèrica): Grid

#### Baseline
- Do you have a baseline grid? Why?
- Is it ever OK to place something off the grid?
- Does the baseline grid differ between content and typography?

#### Columns
- Do you use a column system or a horizontal grid?
- Are there any best practices around column widths?
- How do gutters work?

## Pestanya legacy (plantilla genèrica): Breakpoints
Do you have well-defined breakpoints? Documenting them here can help make it clear when and how to adjust content responsively, e.g.
[codev2] {"blockType": "live-code", "syntaxLanguage": "css", "code": "// Small devices (landscape phones, 576px and up)\n@media (min-width: 576px) { ... }\n\n// Medium devices (tablets, 768px and up)\n@media (

> Nota: la font acaba truncada dins l'exemple de breakpoints de la plantilla genèrica ("Small devices (landscape phones, 576px and up) `@media (min-width: 576px)`, Medium devices (tablets, 768px and up) …"). No és contingut específic del sistema de disseny. [a verificar]
> Nota: al text introductori, l'espai entre columnes d'"Extra large column fix" (≥1440 dp) és de 40 dp, mentre que la taula Web ciutadà indica 32 dp de gutter. [discrepància: text diu 40 dp; taula diu 32 dp]
