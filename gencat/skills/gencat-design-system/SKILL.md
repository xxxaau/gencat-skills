---
name: gencat-design-system
description: "Aplica el Sistema de Disseny oficial de la Generalitat de Catalunya quan construeixis, estilitzis o revisis interfícies web per a serveis digitals Gencat. Activa-la quan es mencioni Gencat, sistema de disseny, components UI, tokens, colors o tipografia corporativa en el desenvolupament web per a la Generalitat de Catalunya."
---

# Sistema de Disseny de la Generalitat de Catalunya

Quan desenvolupis aplicacions per a la Generalitat de Catalunya, **sempre** has de seguir el Sistema de Disseny oficial. Documenta't en:
- Documentació principal: https://sistemadedisseny.gencat.cat
- Storybook de components: https://664dd24b10b47825ed57745e-tpikyjfnns.chromatic.com (enllaç de build de Chromatic — si no respon, busca l'enllaç vigent a sistemadedisseny.gencat.cat)

## Abast de la skill

### Què cobreix
- Fonaments visuals (colors, tipografia, espaiat, tokens)
- Ús correcte del catàleg de components oficials
- Patrons d'interfície per a casos d'ús habituals de serveis digitals Gencat

### Què NO cobreix
- Redacció detallada de literals i microcopy (delegar a `gencat-comunicacio-clara`)
- Auditories d'accessibilitat completes o informes de compliment normatiu (delegar a `gencat-accessibilitat`)
- Redacció específica de fitxes de tràmit (delegar a `gencat-tramits`)

### Skills complementàries
- `gencat-accessibilitat` per validar WCAG en components i fluxos
- `gencat-comunicacio-clara` per literals de UI, missatges i contingut textual
- `gencat-identitat-corporativa` quan hi ha materials no web o peces institucionals de marca

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
- Tooltip → `Descripció emergent` (variant hover: informació breu, desapareix sola)
- Popover → `Descripció emergent` (variant click: contingut o accions, persisteix fins que es tanca)
- Side panel → `Panell emergent`
- Progress bar → `Barra de progrés`
- Loading → `Indicador de càrrega`

### Tokens i estils

Tots els tokens (colors, tipografia Open Sans, espaiat, arrodoniment, ombres) són a `references/foundations.md`: copia el bloc de variables CSS d'allà. No redefineixis valors a mà.

### Accessibilitat obligatòria

Mínims en escriure qualsevol component (cobertura completa a la skill `gencat-accessibilitat`):
- Tots els inputs amb `<label>` associat i tots els `<img>` amb `alt`
- Contrast mínim 4.5:1 (text normal) i 3:1 (text gran i components UI)
- Navegació completa per teclat amb focus visible

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
