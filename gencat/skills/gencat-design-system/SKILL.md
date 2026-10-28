---
name: gencat-design-system
description: "Aplica el Sistema de Disseny oficial de la Generalitat de Catalunya quan construeixis, estilitzis o revisis interfícies web per a serveis digitals Gencat. Conté la documentació completa del sistema (fonaments, tokens, 78 components amb la seva API de web component (91 tags), patrons, guies de desenvolupament Vue/React/Angular i historial de versions). Activa-la quan es mencioni Gencat, sistema de disseny, components UI, tokens, colors, tipografia corporativa, web components gencat-core o gencat-conversational, o patrons com formularis, xat o notificacions per a la Generalitat de Catalunya."
license: CC0-1.0
metadata:
  author: Generalitat de Catalunya
  version: "2.0"
---

# Sistema de Disseny de la Generalitat de Catalunya

Quan desenvolupis interfícies per a la Generalitat de Catalunya, **sempre** has de seguir el Sistema de Disseny oficial (SDGC). Aquesta skill en conté la documentació completa extreta del lloc oficial, de manera que **no cal tornar a consultar el web** per treballar-hi. Font oficial i punt de contacte: https://sistemadedisseny.gencat.cat

## Versió i data d'actualització

| | |
|---|---|
| **Última actualització de la skill** | **2026-10-28** (extracció completa del lloc) |
| Llibreria de components (Figma) | v12.6.0 — publicada el 22/10/2026 |
| Fonaments (Figma) | v6.2.1 — 02/10/2026 |
| Components conversacionals (Figma) | v5.1.0 — 19/06/2026 |
| Exemples d'ús (Figma) | v4.0.0 |
| Codi (llibreria de web components) | v12.1.2 — 05/10/2026 (paquets `@ctti-dev/gencat-core` i `@ctti-dev/gencat-conversational`) |
| Documentació d'API usada | `documentation-v12.0.0` (generada el 13/07/2026) |

Cada fitxer de `references/` indica a la capçalera la pàgina d'origen, el seu identificador al lloc i la **data de l'última modificació de la font**. Per saber si la skill és desactualitzada, compara aquestes dades amb `references/versions-actualitzacions.md` i amb la pàgina "Actualitzacions" del lloc (vegeu "Com actualitzar aquesta skill").

> Si treballes amb una versió de la llibreria diferent de la 12.x, comprova primer els canvis a `references/versions-actualitzacions.md`: l'API dels components i els noms dels tokens poden variar entre versions majors.

## Abast de la skill

### Què cobreix
- Fonaments visuals: colors (primitives i tokens), tipografia, espaiat, quadrícules i punts de tall, arrodoniment, elevacions, iconografia, marca, imatge, il·lustracions i visualització de dades.
- Catàleg complet de components (core i conversacionals): quan usar-los, anatomia, variants, estats, mides, bones pràctiques, accessibilitat, tokens, API del web component i historial de versions.
- Patrons d'interfície i exemples d'ús (formularis, cercador, àrea privada, gestió interna, xat, notificacions, errors…).
- Desenvolupament: instal·lació i configuració per a Vue, React i Angular, temes per marca, personalització de textos, idioma i referència de claus.
- Organització de les biblioteques de Figma, accessos, suport i historial de versions.

### Què NO cobreix
- Redacció detallada de literals i microcopy (delegar a `gencat-comunicacio-clara`)
- Auditories d'accessibilitat completes o informes de compliment normatiu (delegar a `gencat-accessibilitat`)
- Redacció específica de fitxes de tràmit (delegar a `gencat-tramits`)
- Materials no web o peces institucionals de marca (delegar a `gencat-identitat-corporativa`)

### Skills complementàries
- `gencat-accessibilitat` per validar WCAG en components i fluxos
- `gencat-comunicacio-clara` per literals de UI, missatges i contingut textual
- `gencat-identitat-corporativa` quan hi ha materials no web o peces institucionals de marca

Si una skill complementària no està instal·lada, continua amb el que diu aquesta skill: cada fitxer de component ja inclou les seves pautes d'accessibilitat i de contingut.

## Principis fonamentals

1. **Accessibilitat primer** — compliment WCAG 2.2 (UNE-EN 301549:2022). Tots els components han de ser accessibles.
2. **Comunicació clara** — missatges directes, simples i comprensibles.
3. **Consistència** — usa sempre els components del sistema; no en creïs de nous si ja n'hi ha un d'equivalent.
4. **Català com a llengua principal** — tota la UI en català per defecte.
5. **Dos entorns** — web ciutadà (públic) i aplicacions de gestió interna (back-office); molts components i quadrícules tenen comportament diferent en cadascun.

## Mapa de referències (`references/`)

Obre només el fitxer que necessitis. Tots els enllaços són relatius a `references/`.

| Necessites… | Fitxer |
|---|---|
| Valors de colors, tipografia, espaiat, radis, ombres, quadrícules i el bloc CSS de tokens (**font canònica**) | `references/foundations.md` |
| Guia d'ús del color i tots els tokens semàntics | `references/fonaments-guia-de-colors.md` |
| Resta de fonaments (tipografia, espaiat, arrodoniment, elevacions, punts de tall, iconografia, marca, variables/temes, imatge, il·lustracions, gràfics i mapes, conversacional, comunicació clara) | `references/fonaments-*.md` |
| Trobar un component pel seu nom o necessitat | `references/components.md` (índex) |
| Documentació d'un component | `references/component-<nom>.md` |
| Trobar un patró o un exemple de pàgina | `references/patterns.md` (índex), `references/patro-*.md`, `references/exemple-*.md` |
| Instal·lar i configurar la llibreria (Vue, React, Angular), temes, textos i idioma | `references/dev-*.md` |
| Inventari dels 91 web components (tag → fitxer) | `references/dev-visio-general-paquets-web-components.md` |
| Claus de text (i18n) de tots els components | `references/dev-referencia-de-claus-disponibles.md` |
| Biblioteques de Figma i organització dels arxius | `references/figma-*.md` |
| Context, principis, preguntes freqüents, accessibilitat del sistema, onboarding | `references/sobre-*.md` |
| Accessos, suport, sol·licitud de components o de suport, incidències | `references/suport-*.md` |
| Historial de versions i estat de fonaments i components | `references/versions-actualitzacions.md` |

### Estructura dels fitxers de component

Tots segueixen el mateix ordre (omet les seccions sense contingut): què és i quan usar-lo · quan NO usar-lo · anatomia · variants, tipus i estats · mides i espaiats · comportament · contingut i microcopy · bones pràctiques (FER / NO FER) · accessibilitat · tokens · **Implementació (component web)** amb propietats, esdeveniments, mètodes i exemples de codi · historial de versions · vegeu també.

Les marques `[discrepància]` i `[a verificar]` dins dels fitxers assenyalen punts on el lloc oficial es contradiu o és ambigu (per exemple, un nom d'atribut diferent entre la pàgina i la documentació generada del codi). En cas de discrepància, **l'exemple de codi de la secció "Implementació" és el que s'executa**; verifica'l amb el component real.

## Regles d'implementació

### Com treballar amb un component (workflow)

1. **Identifica el component** a `references/components.md` (cerca pel nom català o per l'equivalent anglès). Si és un cas d'ús complet (formulari, xat, errors, notificacions), mira abans `references/patterns.md`.
2. **Llegeix el fitxer del component** sencer: l'ús correcte, les variants i les bones pràctiques FER/NO FER pesen tant com l'API.
3. **Implementa'l amb el web component oficial** (secció "Implementació") i no amb HTML/CSS propi; configura el projecte seguint `references/dev-projectes-*.md`.
4. **Estils i colors**: només amb els tokens de `references/foundations.md` (vegeu més avall); mai amb valors literals copiats.
5. **Verifica accessibilitat** (secció "Accessibilitat" del component, contrast, teclat, ARIA) i redacta els textos amb les pautes de "Contingut i microcopy".
6. **Comprova que el resultat es comporta bé en ambdós entorns** (ciutadà / gestió interna) i en tots els punts de tall (vegeu `references/foundations.md`).

### Nomenclatura oficial

Usa **sempre** els noms oficials en català. Equivalències habituals (les correccions respecte de terminologies antigues estan en negreta):

| Anglès / ús comú | Nom oficial | Fitxer |
|---|---|---|
| Button | Botons | `component-botons.md` |
| Input / text field | Camp d'entrada | `component-camp-d-entrada.md` |
| Textarea | Àrea de text | `component-area-de-text.md` |
| Checkbox | Casella de selecció | `component-casella-de-seleccio.md` |
| Radio | Botó d'opció | `component-boto-d-opcio.md` |
| Toggle / switch | Commutador | `component-commutador.md` |
| Select / dropdown | Desplegable | `component-desplegable.md` |
| Slider | Control de rang | `component-control-de-rang.md` |
| Date picker | Selector de data | `component-selector-de-data.md` |
| Modal | Modals | `component-modals.md` |
| Breadcrumb | Fils d'Ariadna | `component-fils-d-ariadna.md` |
| Tabs | Pestanyes / Barra de pestanyes | `component-pestanyes.md`, `component-barra-de-pestanyes.md` |
| Accordion | Acordió | `component-acordio.md` |
| Badge | Insígnia | `component-insignia.md` |
| Chip | Xips | `component-xips.md` |
| Tag | Etiquetes | `component-etiquetes.md` |
| Alert / callout | Avisos | `component-avisos.md` |
| Toast | Notificació emergent | `component-notificacio-emergent.md` |
| **Tooltip** | **Indicador de funció** | `component-indicador-de-funcio.md` |
| **Popover** | **Descripció emergent** | `component-descripcio-emergent.md` |
| Side panel / drawer / sheet | Panell emergent | `component-panell-emergent.md` |
| Skeleton | Esquelet | `component-esquelet.md` |
| Spinner / loading | Indicador de càrrega | `component-indicador-de-carrega.md` |
| Progress bar | Barra de progrés | `component-barra-de-progres.md` |
| Stepper | Pas a pas | `component-pas-a-pas.md` |
| Empty state | Estat buit | `component-estat-buit.md` |
| Card | Targetes | `component-targetes.md` |
| Data table | Taules dinàmiques | `component-taules-dinamiques.md` |
| Footer | Peu de pàgina | `component-peu-de-pagina.md` |

La llista sencera (78 components) amb equivalent anglès i tag del web component és a `references/components.md`.

### Tokens i estils

- Els tokens estan en **dues capes**: les primitives (`--color-brand-primary-500`, `--spacing-8`, `--size-m`…), que són les variables base i **no s'han d'utilitzar ni modificar directament**, i els tokens de color per ús (fons `--background-*`, contingut `--content-*` i vora `--border-*`), alguns dels quals són específics d'un component (p. ex. `--background-buttons-primary-default`). Usa els tokens, no les primitives.
- Totes les primitives, el bloc CSS `:root` i els valors d'espaiat, radis, ombres, tipografia i quadrícules són a `references/foundations.md`: copia'n el bloc, no redefineixis valors.
- La tipografia és **Open Sans** (FS Pimlico només per a Loteries de Catalunya).
- Hi ha **un mode per marca** (`gencat` per defecte, `atc`, `gaip`, `loteries`, `infraestructures`) que s'activa amb `data-theme` a `<html>` (vegeu `references/fonaments-variables.md`).
- El vermell de marca i el d'error **són colors diferents** (primitiva d'error pròpia). La nomenclatura simplificada que usava la versió anterior d'aquesta skill (`--color-brand-primary`, `--color-text-primary`, `--space-*`…) **no és oficial**; si la trobes en codi existent, migra-la als tokens reals.

### Accessibilitat obligatòria

Mínims en escriure qualsevol component (cobertura completa a la skill `gencat-accessibilitat` i a cada fitxer de component):
- Tots els inputs amb etiqueta associada i totes les imatges amb text alternatiu
- Contrast mínim 4.5:1 (text normal) i 3:1 (text gran i components UI)
- Navegació completa per teclat amb focus visible
- Respectar les especificacions WCAG 2.2 citades a la secció "Accessibilitat" de cada component

## Quan NO existeix un component oficial

1. Comprova que no hi ha un component o patró equivalent: cerca per equivalent anglès a `references/components.md` i `references/patterns.md`.
2. Segueix els fonaments (colors, tipografia, espaiat, arrodoniment) de `references/foundations.md`.
3. Mantén l'estètica consistent amb els components existents.
4. Proposa'l a l'equip del Sistema de Disseny pel canal de sol·licituds (vegeu `references/suport-sollicita-components.md` i `references/suport-suport-i-contacte.md`).

## Com actualitzar aquesta skill

1. Obre la pàgina "Actualitzacions" del lloc (https://sistemadedisseny.gencat.cat) i compara-la amb `references/versions-actualitzacions.md`: versions de llibreria, taula d'estat i historial.
2. Per a cada component, fonament o patró nou o modificat, refés el seu fitxer a partir de la pàgina del lloc (el seu identificador i la data de modificació són a la capçalera del fitxer) i de la documentació d'API generada del codi.
3. Mantén la plantilla de seccions i les convencions del repo (català, agnòstic d'agent, el color de marca només a `foundations.md`).
4. Actualitza: la taula "Versió i data d'actualització" d'aquest fitxer, `references/components.md` i `references/patterns.md` si hi ha fitxers nous, la data a `README.md` i a `gencat/README.md`, i `metadata.version`.
