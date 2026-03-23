---
name: gencat-design-system
description: "Aplica el Sistema de Disseny oficial de la Generalitat de Catalunya quan desenvolupes aplicacions web, components o interfícies d'usuari per a serveis digitals de la Generalitat. Utilitza aquesta skill quan es mencioni Gencat, Generalitat de Catalunya, aplicació gencat, sistema de disseny, o quan es demani construir, estilitzar o revisar qualsevol interfície digital del govern català. Garanteix l'alineació amb la marca oficial, l'accessibilitat i els estàndards de components."
---

# Sistema de Disseny de la Generalitat de Catalunya

Quan desenvolupis aplicacions per a la Generalitat de Catalunya, **sempre** has de seguir el Sistema de Disseny oficial. Documenta't en:
- Documentació principal: https://sistemadedisseny.gencat.cat
- Storybook de components: https://664dd24b10b47825ed57745e-tpikyjfnns.chromatic.com

## Principis fonamentals

1. **Accessibilitat primer** — compliment WCAG. Tots els components han de ser accessibles.
2. **Comunicació clara** — missatges directes, simples i comprensibles.
3. **Consistència** — usa sempre els components del sistema, mai en crees de nous si ja existeix un equivalent.
4. **Català com a llengua principal** — tota la UI ha d'estar en català per defecte.

## Referència ràpida de Fonaments

Llegeix `references/foundations.md` per a:
- Colors (paleta completa amb tokens)
- Tipografia (Open Sans, escala de mides)
- Espaiat i grid
- Elevació i ombres
- Arrodoniment (border-radius)

## Catàleg de components

Llegeix `references/components.md` per a la llista completa de components disponibles amb els seus noms oficials en català.

## Patrons d'ús

Per a casos d'ús habituals (formularis, àrea privada, cercadors, gestió interna), consulta `references/patterns.md`.

## Regles d'implementació

### Nomenclatura oficial

Usa **sempre** els noms en català dels components tal com apareixen al sistema de disseny:
- Botó → `Botons`
- Input → `Camp d'entrada`
- Modal → `Modals`
- Breadcrumb → `Fils d'Ariadna`
- Toast → `Notificació emergent`
- Checkbox → `Casella de selecció`
- Radio → `Botó d'opció`
- Toggle → `Commutador`
- Tabs → `Pestanyes` / `Barra de pestanyes`
- Accordion → `Acordió`
- Badge → `Insígnia`
- Chip → `Xips`
- Dropdown → `Desplegable`
- Skeleton → `Esquelet`
- Empty state → `Estat buit`
- Stepper → `Pas a pas`
- Tooltip → `Descripció emergent`
- Popover → `Descripció emergent`
- Side panel → `Panell emergent`
- Progress bar → `Barra de progrés`
- Loading → `Indicador de càrrega`

### Font

```css
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,300..800;1,300..800&display=swap');

:root {
  font-family: 'Open Sans', sans-serif;
  font-size: 16px; /* base rem */
}
```

### Colors principals

```css
:root {
  /* Brand */
  --color-brand-primary: #C00000;      /* Vermell Gencat - acció, links */

  /* Text */
  --color-text-primary:   #333333;
  --color-text-secondary: #5C5C5C;

  /* Background */
  --color-bg-default: rgb(250, 250, 250);
  --color-bg-white:   #FFFFFF;
}
```

### Accessibilitat obligatòria

- Tots els `<img>` han de tenir `alt`
- Tots els inputs han de tenir `<label>` associat
- Contrast mínim 4.5:1 per a text normal
- Contrast mínim 3:1 per a text gran (>18px o bold >14px)
- Suport de navegació per teclat en tots els components interactius
- `aria-label` / `aria-describedby` quan calgui

## Workflow per a noves funcionalitats

1. **Identifica el component** al catàleg de components (`references/components.md`)
2. **Consulta el disseny** a https://sistemadedisseny.gencat.cat
3. **Usa el component existent** si n'hi ha; si no, segueix les guies de foundations
4. **Verifica accessibilitat** (contrast, navegació per teclat, ARIA)
5. **Usa català** com a llengua de la UI

## Quan NO existeix un component oficial

Si necessites un component que no està al catàleg:
1. Segueix els `foundations` (colors, tipografia, espaiat, arrodoniment)
2. Mantén l'estètica consistent amb els components existents
3. Proposa-ho per sol·licitud a: https://sistemadedisseny.gencat.cat/p/sol·licituds
