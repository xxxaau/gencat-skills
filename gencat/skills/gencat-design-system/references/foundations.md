# Foundations — Sistema de Disseny Gencat

> Font canònica dels valors dels fonaments (colors, tipografia, espaiat, arrodoniment, elevacions, quadrícules). Extreta del Sistema de Disseny de la Generalitat de Catalunya (https://sistemadedisseny.gencat.cat): pàgines Guia de colors (actualitzada el 2026-07-20; versió Figma 6.0.1, Github 2.0.0), Tipografia (2026-08-24; Figma 5.0.0, Github 2.1.0), Espaiat (2025-10-28), Arrodoniment (2025-10-28), Elevacions (2026-01-20; Github 3.0.0), Punt de tall i quadrícules (2025-07-31), Iconografia (2026-09-09), Variables (2026-09-09) i Marca (2026-06-01). Extret el 2026-10-28. La transcripció pàgina a pàgina és a `fonaments-*.md` (per exemple [Guia de colors](fonaments-guia-de-colors.md), [Tipografia](fonaments-tipografia.md), [Variables](fonaments-variables.md)).

> **Nota sobre la nomenclatura:** els noms `--color-brand-primary`, `--color-text-primary`, `--color-bg-*`, `--space-*` i similars que apareixien a la versió anterior d'aquest fitxer eren una simplificació no oficial i no existeixen al sistema de disseny; també eren incorrectes alguns valors (colors de text, estats, escala tipogràfica i espaiat). Els noms oficials són els d'aquest document (per exemple `--color-brand-primary-500`, `--spacing-8`, `--size-m`, `--weight-bold`).
>
> **Nota sobre l'error i la marca:** el color d'error i el de marca ja no comparteixen valor. L'error té primitiva pròpia (`--color-error-300`, `--color-error-500`, `--color-error-700`) i tokens propis (`--border-error`, `--content-error`, `--background-error-*`). Per això ja no cal el "doble ús" del vermell que es descrivia abans; el color de marca és `--color-brand-primary-500` i només s'usa per a elements interactius i d'identitat.
>
> Les **primitives** no s'han d'utilitzar ni modificar directament als components (excepte les elevacions, que sí que es poden usar directament): cal usar els **tokens semàntics**. El color de marca de Gencat és `--color-brand-primary-500`; la identitat corporativa (Pantone 485) es descriu a la skill `gencat-identitat-corporativa`.

## Modes (marques)

El sistema té un mode per marca. El mode per defecte és **gencat**; la resta s'activen amb l'atribut `data-theme` a l'etiqueta `<html>`: `data-theme="atc"` (Agència Tributària de Catalunya), `data-theme="gaip"` (Comissió de Garantia del Dret d'Accés a la Informació Pública), `data-theme="loteries"` (Loteries de Catalunya) i `data-theme="infraestructures"` (Infraestructures). Els modes només canvien les primitives de marca (i, a Loteries, els neutres, la tipografia i alguns tokens; a Infraestructures, el neutre 400); les primitives informatives, positives, d'alerta, d'error, de focus i alternatives són les de Gencat.

## Colors — primitives

Format: hex i rgb tal com els dona la font. Les files marcades amb `*` tenen una discrepància a la font (vegeu "Discrepàncies de la font" al final); el hex mostrat és el que s'usa al bloc CSS.

### Gencat (mode per defecte)

#### Marca (brand)

| Primitiva | Hex | RGB |
|---|---|---|
| --color-brand-secondary-50 | #f9e5e5 | rgb(249, 229, 229) |
| --color-brand-secondary-100 | #f2cccc | rgb(242, 204, 204) |
| --color-brand-primary-300 | #d96666 | rgb(217, 102, 102) |
| --color-brand-primary-500 | #c00000 | rgb(192, 0, 0) |
| --color-brand-primary-600 | #900000 | rgb(144, 0, 0) |
| --color-brand-primary-700 | #660000 | rgb(102, 0, 0) |

#### Neutre (neutral)

| Primitiva | Hex | RGB |
|---|---|---|
| --color-neutral-100 | #f5f5f5 | rgb(245, 245, 245) |
| --color-neutral-200 | #f2f2f2 | rgb(242, 242, 242) |
| --color-neutral-300 | #dddddd | rgb(221, 221, 221) |
| --color-neutral-400 | #939393 | rgb(147, 147, 147) |
| --color-neutral-500 | #6e6e6e | rgb(110, 110, 110) |
| --color-neutral-700 | #333333 | rgb(51, 51, 51) |

#### Base

| Primitiva | Hex | RGB |
|---|---|---|
| --color-base-black | #000000 | rgb(0, 0, 0) |
| --color-base-white | #ffffff | rgb(255, 255, 255) |

#### Informatiu (informative)

| Primitiva | Hex | RGB |
|---|---|---|
| --color-informative-300 | #ecf9fb | rgb(236, 249, 251) |
| --color-informative-500 | #c8e5f8 | rgb(200, 229, 248) |
| --color-informative-700 | #006db5 | rgb(0, 109, 181) |

#### Positiu (positive)

| Primitiva | Hex | RGB |
|---|---|---|
| --color-positive-300 | #eaf9ea | rgb(234, 249, 234) |
| --color-positive-500 | #c4e4c4 | rgb(196, 228, 196) |
| --color-positive-700 | #3f7200 | rgb(63, 114, 0) |

#### Alerta (alert)

| Primitiva | Hex | RGB |
|---|---|---|
| --color-alert-300 | #fff5e1 | rgb(255, 245, 225) |
| --color-alert-500 | #fbe4bc | rgb(251, 228, 188) |
| --color-alert-700 | #bc5000 | rgb(188, 80, 0) |

#### Error

| Primitiva | Hex | RGB |
|---|---|---|
| --color-error-300 | #fbeeed | rgb(251, 238, 237) |
| --color-error-500 | #f5b4b4 | rgb(245, 180, 180) |
| --color-error-700 | #dd0404 | rgb(221, 4, 4) |

#### Focus

| Primitiva | Hex | RGB |
|---|---|---|
| --color-focus-500 | #2c93f2 | rgb(44, 147, 242) |

#### Alternatiu (alternative)

| Primitiva | Hex | RGB |
|---|---|---|
| --color-alternative-300 | #dcc0f8 | rgb(220, 192, 248) |
| --color-alternative-500 | #a36fb4 | rgb(163, 111, 180) |
| --color-alternative-700 | #7320c2 | rgb(115, 32, 194) |

### ATC
Només varien les primitives de marca; la resta com a Gencat.

| Primitiva | Hex | RGB |
|---|---|---|
| --color-brand-secondary-50 | #ebf6ff | rgb(235, 246, 255) |
| --color-brand-secondary-100 | #cce3f4 * | rgb(204, 227, 224) |
| --color-brand-secondary-300 | #76a8cc | rgb(118, 168, 204) |
| --color-brand-primary-500 | #a81a8d | rgb(168, 26, 141) |
| --color-brand-primary-600 | #80146c | rgb(128, 20, 108) |
| --color-brand-primary-700 | #550c47 | rgb(85, 12, 71) |

### GAIP
Només varien les primitives de marca; la resta com a Gencat.

| Primitiva | Hex | RGB |
|---|---|---|
| --color-brand-secondary-50 | #e5f1f3 | rgb(229, 241, 243) |
| --color-brand-secondary-100 | #a6ced6 | rgb(166, 206, 214) |
| --color-brand-secondary-300 | #4d9faf | rgb(77, 159, 175) |
| --color-brand-primary-500 | #00768c * | rgb(0, 118, 140) |
| --color-brand-primary-600 | #005665 | rgb(0, 86, 101) |
| --color-brand-primary-700 | #0d2326 | rgb(13, 35, 38) |

### Loteries de Catalunya
Varien les primitives de marca i els neutres; la resta com a Gencat. A nivell de tokens hi ha variacions per a components específics (vegeu més avall).

| Primitiva | Hex | RGB |
|---|---|---|
| --color-brand-secondary-50 | #deeafc * | rgb(222, 234, 252) |
| --color-brand-secondary-100 | #c6d9f5 * | rgb(196, 217, 245) |
| --color-brand-secondary-300 | #627fb9 | rgb(98, 127, 185) |
| --color-brand-primary-500 | #017939 | rgb(1, 121, 57) |
| --color-brand-primary-600 | #005c2b | rgb(0, 92, 43) |
| --color-brand-primary-700 | #003c1c | rgb(0, 60, 28) |
| --color-neutral-100 | #f7fafd * | rgb(247, 250, 253) |
| --color-neutral-200 | #eef5ff * | rgb(238, 245, 255) |
| --color-neutral-300 | #e4eefd | rgb(228, 238, 253) |
| --color-neutral-400 | #7994c9 | rgb(121, 148, 201) |
| --color-neutral-500 | #5a72a3 | rgb(90, 114, 163) |
| --color-neutral-700 | #173571 | rgb(23, 53, 113) |

### Infraestructures
Varien les primitives de marca i el neutral 400; la resta com a Gencat.

| Primitiva | Hex | RGB |
|---|---|---|
| --color-brand-secondary-50 | #ebf8e2 | rgb(235, 248, 226) |
| --color-brand-secondary-100 | #ceeeb8 | rgb(206, 238, 184) |
| --color-brand-secondary-300 | #5eac28 | rgb(94, 172, 40) |
| --color-brand-primary-500 | #48841e | rgb(72, 132, 30) |
| --color-brand-primary-600 | #2d5213 | rgb(45, 82, 19) |
| --color-brand-primary-700 | #1d350c | rgb(29, 53, 12) |
| --color-neutral-400 | #9a9a9a | rgb(154, 154, 154) |

### Opacitat (overlay)
Les modals i diàlegs emergents enfosqueixen el contingut subjacent amb color base `--color-neutral-700` (#333333) a opacitat 25% (token `--background-tertiary-opacity-25` → `--color-neutral-700-25`).

## Colors — tokens semàntics clau

Els tokens es classifiquen en **Fons** (`--background-*`), **Vora** (`--border-*`) i **Contingut** (`--content-*`, text i icones). Els tokens amb `darkbackground` són per a elements sobre fons fosc (per exemple enllaços al peu de pàgina). Taula de tokens clau (la llista completa, amb tots els tokens de botons, enllaços, camps, il·lustració, etc., és al bloc CSS d'aquest fitxer i a [Guia de colors](fonaments-guia-de-colors.md)):

| Token | Referència | Ús |
|---|---|---|
| --background-primary | --color-base-white | Fons de pàgina/contenidor base |
| --background-primary-hover | --color-neutral-100 | Fons en hover |
| --background-accent-default | --color-brand-primary-500 | Fons d'accent (botons primaris) |
| --background-accent-pressed | --color-brand-primary-700 | Fons d'accent pressed |
| --background-decorative | --color-neutral-200 | Fons decoratiu |
| --background-disabled | --color-neutral-100 | Fons deshabilitat |
| --background-error-primary | --color-error-300 | Fons error |
| --background-success-primary | --color-positive-300 | Fons èxit |
| --background-alert-primary | --color-alert-300 | Fons alerta |
| --background-information-primary | --color-informative-300 | Fons informatiu |
| --border-primary | --color-neutral-700 | Vora principal |
| --border-secondary | --color-neutral-400 | Vora secundària |
| --border-tertiary | --color-neutral-300 | Vora terciària |
| --border-accent-primary-default | --color-brand-primary-500 | Vora d'accent |
| --border-focus | --color-focus-500 | Vora de focus |
| --border-error | --color-error-700 | Vora error |
| --border-disabled | --color-neutral-400 | Vora deshabilitada |
| --content-primary-default | --color-neutral-700 | Text principal |
| --content-secondary-default | --color-neutral-500 | Text secundari |
| --content-disabled | --color-neutral-400 | Contingut deshabilitat |
| --content-accent-primary-default | --color-brand-primary-500 | Contingut d'accent (enllaços/accions) |
| --content-error | --color-error-700 | Contingut error |
| --content-succes | --color-positive-700 | Contingut èxit |
| --content-alert | --color-alert-700 | Contingut alerta |
| --content-informative | --color-informative-700 | Contingut informatiu |
| --content-visited | --color-alternative-700 | Contingut visitat |
| --content-primary-darkbackgroiund-default | --color-base-white | Contingut sobre fons fosc |

Ús dels nivells de cada color: marca 500 = color primari (botons per defecte, pestanyes seleccionades); 600 = hover; 700 = pressed; 50 = fons decoratius; 100 i 300 = elements decoratius/il·lustracions. Neutral 700 = cos de text i estat seleccionat de caselles i botons d'opció; 500 = text secundari; 400 = separadors i elements gràfics; 300/200 = fons hover i decoratiu sense requisit d'accessibilitat. Per a cada família (informative, positive, alert, error, alternative) 300 = fons, 500 = fons d'estat, 700 = elements gràfics/vores/contingut. Focus: `--color-focus-500` (vora de focus, `--border-focus`). Alternatiu 700 = enllaços visitats (`--border-visited`, `--content-visited`).

Contrast: text normal 4.5:1, text gran (≥ 24 px, o ≥ 18.66 px en negreta) 3:1 (WCAG 1.4.3 AA; UNE-EN 301549:2022 / WCAG 2.2). Vegeu l'accessibilitat a [Guia de colors](fonaments-guia-de-colors.md).

## Tipografia

Família corporativa: **Open Sans** (`--family-primary`), de Google Fonts: https://fonts.google.com/specimen/Open+Sans. Loteries de Catalunya usa **FS Pimlico** (només per a aquesta marca; `--family-primary` = FS Pimlico en mode Loteries).

### Primitives
Pesos: `--weight-bold` 700, `--weight-semibold` 600, `--weight-regular` 400.

| Primitiva | Gencat (Open Sans) | Loteries (FS Pimlico) |
|---|---|---|
| --size-xs | 12px | 14px |
| --size-s | 14px | 16px |
| --size-m | 16px | 18px |
| --size-l | 18px | 20px |
| --size-xl | 20px | 24px |
| --size-2xl | 24px | 28px |
| --size-3xl | 28px | 32px |
| --size-4xl | 32px | 36px |
| --size-5xl | 36px | 40px |
| --size-6xl | 40px | 48px |
| --size-7xl | 48px | 56px |
| --size-8xl | 56px | 60px |
| --size-9xl | 60px | 72px |
| --size-10xl | 72px | 80px |

### Estils (escriptori i mòbil)

Estils de Figma: Display (escriptori i mòbil: MD Regular); Heading (escriptori: XL, LG, MD, SM, XS Semibold; mòbil: XL, LG, MD, SM, XS Semibold); Body (LG, MD, SM en Regular, Semibold i Bold); Label (LG, MD, SM Regular i Semibold; XS Semibold). Mides resoltes a partir dels tokens de la font (vegeu les referències):

| Estil | Token de mida | Referència | Gencat | Loteries |
|---|---|---|---|---|
| Display MD escriptori | --display-desktop-m-size | --size-8xl | 56px | 60px |
| Display MD mòbil | --display-mobile-m-size | --size-7xl | 48px | 56px |
| Heading XL escriptori | --heading-desktop-xl-size | --size-7xl | 48px | 56px |
| Heading LG escriptori | --heading-desktop-l-size | --size-6xl | 40px | 48px |
| Heading MD escriptori | --heading-desktop-m-size | --size-4xl | 32px | 36px |
| Heading SM escriptori | --heading-desktop-s-size | --size-3xl | 28px | 32px |
| Heading XS escriptori | --heading-desktop-xs-size | --size-2xl | 24px | 28px |
| Heading XL mòbil | --heading-mobile-xl-size | --size-5xl | 36px | 40px |
| Heading LG mòbil | --heading-mobile-l-size | --size-4xl | 32px | 36px |
| Heading MD mòbil | --heading-mobile-m-size | --size-3xl | 28px | 32px |
| Heading SM mòbil | --heading-mobile-s-size | --size-2xl | 24px | 28px |
| Heading XS mòbil | --heading-mobile-xs-size | --size-xl | 20px | 24px |
| Body LG | --body-l-size | --size-xl | 20px | 24px |
| Body MD | --body-m-size | --size-m | 16px | 18px |
| Body SM | --body-s-size | --size-s | 14px | 16px |
| Label LG | --label-l-size | --size-l | 18px | 20px |
| Label MD | --label-m-size | --size-m | 16px | 18px |
| Label SM | --label-s-size | --size-s | 14px | 16px |
| Label XS | --label-xs-size | --size-xs | 12px | 14px |

- Interlineat: la font només especifica el 150% per a totes les variants de Body (corregit a la versió 1.1.1); no en dona per a la resta d'estils.
- Espaiat entre paràgrafs: Body L `--body-l-paragraph-spacing` → `--spacing-16`; Body M → `--spacing-12`; Body S → `--spacing-8`.
- Pesos: Display `--display-weight` → `--weight-regular`; Heading `--heading-weight` → `--weight-semibold`; Body i Label usen `--body-*-regular|semibold|bold-weight` i `--label-*-regular|semibold-weight`.
- Famílies: `--body-family`, `--display-family`, `--heading-family`, `--label-family` → `--family-primary`.
- Bones pràctiques: amplada de paràgraf entre 45 i 75 caràcters; prioritzar les minúscules; usar cada estil en el seu context.
- [discrepància: l'historial diu que el Heading XL (escriptori) passa de 48 a 40 px i el Heading L de 40 a 36 px des de la versió 2.0.0, però els tokens apunten a `--size-7xl` (48px) i `--size-6xl` (40px)] [a verificar].

## Espaiat

Escala basada en múltiples de 4 i 8 px. Primitives `--spacing-*` (valor en px; rem = valor/16): 0 (0), 2 (0,125), 4 (0,25), 8 (0,5), 12 (0,75), 16 (1), 20 (1,25), 24 (1,5), 32 (2), 40 (2,5), 48 (3), 56 (3,5), 64 (4), 72 (4,5), 80 (5), 88 (5,5), 96 (6), 128 (8).

Tokens de layout (`--layout-*`): none → 0, x0-175 → 2, x0-25 → 4, x0-5 → 8, x0-75 → 12, x1 → 16, x1-5 → 24, x2 → 32, x2-5 → 40, x3 → 48, x3-5 → 56, x4 → 64, x5 → 80, x8 → 128. Tokens de mida (`--size-x*`): x0-175 → 2, x0-25 → 4, x0-5 → 8, x0-75 → 12, x1 → 16, x1-25 → 20, x1-5 → 24, x2 → 32, x2-5 → 40, x3 → 48, x3-5 → 56, x4 → 64, x4-5 → 72, x5 → 80, x8 → 128. Les primitives 88 i 96 no tenen cap token de layout ni de mida (96 s'usa per a `--full` d'arrodoniment).

## Iconografia (mides)

Mides: Extra Small 20 px (`--size-icons-xs`), Small 24 px (`--size-icons-sm`), Medium 32 px (`--size-icons-md`), Large 48 px (`--size-icons-lg`), i `--size-icons-xxs` 16 px. Mida mínima recomanada: 24 px. Usos: accions i etiquetes 20 px i 24 px; suport visual 32 px i 48 px. Usar preferentment els tokens `--size-icons-*`; els `--size-x*` serveixen per definir mides que `--size-icons-*` no cobreix. Llibreria: Bootstrap Icons (https://icons.getbootstrap.com), icones sense farciment (la font la descriu amb unes 2.000 icones i llicència MIT).

## Marca (logotips)

Mida mínima del logotip de la Generalitat (amb text) a la capçalera web: no responsiva 119 x 32 px; responsiva escriptori i tauleta 104 x 28 px; responsiva mòbil 90 x 24 px. L'isotip (capçaleres d'aplicacions internes i dispositius de menys de 375 px) manté les alçades mínimes: 32 px, 28 px i 24 px respectivament. Capçalera de web pública: logotip en color; peu de pàgina: logotip en blanc amb fons transparent. Propietats (valor per defecte): Color Color / Black / White (Color); State Default / Focus (Default); el logotip de la Generalitat també té Disposition Left / Center (Left). Hi ha logotips propis per a ATC, GAIP i Loteries de Catalunya. Detall a [Marca](fonaments-marca.md).

## Arrodoniment (corner radius)

Valors mètrics: 12, 8, 4 i 2 (segons la mida del component). Variants: Cap 0 px; Petita 4 px (0,25 rem); Mitjana 8 px (0,5 rem); Llarga 12 px (0,75 rem); Extrallarga 16 px (1 rem); Ple 50%. Tokens: `--xs` → `--spacing-2` (2px), `--sm` → `--spacing-4` (4px), `--md` → `--spacing-8` (8px), `--lg` → `--spacing-12` (12px), `--xl` → `--spacing-16` (16px), `--full` → `--spacing-96` (96px; la font diu "Ple 50%" a la taula de variants).

## Elevacions (ombres)

Primitives (es poden usar directament):

| Primitiva | Valor |
|---|---|
| --elevations-level-1 | 0px 4px 30px 0px rgba(102, 102, 102, 0.1) |
| --elevations-level-2 | 0px 1px 4px 0px rgba(0, 0, 0, 0.15) |
| --elevations-level-3 | 0px 4px 16px 1px rgba(51, 51, 51, 0.2) |

L'historial menciona un nivell 4 (Figma 2.0.0, desembre 2025), del qual la font no dona cap valor [a verificar].

## Punts de tall i quadrícules

Els dos entorns comparteixen quadrícula fins als 1280 dp. Unitat: dp.

### Web ciutadà

| Grid style | Amplada | Columnes | Columna | Contingut | Gutter | Marge |
|---|---|---|---|---|---|---|
| Small | 0 - 479 dp | 2 | variable | variable | 16 dp | 12 dp |
| Medium | 480 - 959 dp | 4 | variable | variable | 24 dp | 32 dp |
| Large | 960 - 1279 dp | 8 | variable | variable | 32 dp | 40 dp |
| Extra Large column variable | 1280 - 1439 dp | 12 | variable | variable | 40 dp | 80 dp |
| Extra Large column fixed | ≥ 1440 dp | 12 | 76 dp | 1.352 | 32 dp (el text diu 40 dp) | variable |

### Aplicacions de gestió interna (back-office)

| Grid style | Amplada | Columnes | Columna | Contingut | Gutter | Marge |
|---|---|---|---|---|---|---|
| Small | 0 - 479 dp | 2 | variable | variable | 16 dp | 12 dp |
| Medium | 480 - 959 dp | 4 | variable | variable | 24 dp | 32 dp |
| Large | 960 - 1279 dp | 8 | variable | variable | 32 dp | 40 dp |
| Extra Large column variable | ≥ 1280 dp | 12 | variable | variable | 40 dp | 80 dp |

## Bloc CSS (tokens reals, noms verbatim)

El mode per defecte és a `:root`; els altres modes sobreescriuen les primitives que varien (i els tokens específics de Loteries) amb `[data-theme="..."]`. Els noms de tokens semàntics es reprodueixen tal com els escriu la font, incloent-hi errates (vegeu "Discrepàncies de la font"): una referència `var(--color-brand-priimary-700)` o `var(--content-primary-darkbackgroiund-default)` no resol si no es defineix aquest nom exacte.

```css
:root {
  /* Primitives de color — mode Gencat (per defecte) */
  --color-brand-secondary-50: #f9e5e5;
  --color-brand-secondary-100: #f2cccc;
  --color-brand-primary-300: #d96666;
  --color-brand-primary-500: #c00000;
  --color-brand-primary-600: #900000;
  --color-brand-primary-700: #660000;
  --color-neutral-100: #f5f5f5;
  --color-neutral-200: #f2f2f2;
  --color-neutral-300: #dddddd;
  --color-neutral-400: #939393;
  --color-neutral-500: #6e6e6e;
  --color-neutral-700: #333333;
  --color-base-black: #000000;
  --color-base-white: #ffffff;
  --color-informative-300: #ecf9fb;
  --color-informative-500: #c8e5f8;
  --color-informative-700: #006db5;
  --color-positive-300: #eaf9ea;
  --color-positive-500: #c4e4c4;
  --color-positive-700: #3f7200;
  --color-alert-300: #fff5e1;
  --color-alert-500: #fbe4bc;
  --color-alert-700: #bc5000;
  --color-error-300: #fbeeed;
  --color-error-500: #f5b4b4;
  --color-error-700: #dd0404;
  --color-focus-500: #2c93f2;
  --color-alternative-300: #dcc0f8;
  --color-alternative-500: #a36fb4;
  --color-alternative-700: #7320c2;
  --color-neutral-700-25: rgba(51, 51, 51, 0.25);  /* derivat: neutral-700 al 25% (secció Opacitat); la font només en dona el nom */

  /* Primitives d'espaiat */
  --spacing-0: 0px;
  --spacing-2: 2px;
  --spacing-4: 4px;
  --spacing-8: 8px;
  --spacing-12: 12px;
  --spacing-16: 16px;
  --spacing-20: 20px;
  --spacing-24: 24px;
  --spacing-32: 32px;
  --spacing-40: 40px;
  --spacing-48: 48px;
  --spacing-56: 56px;
  --spacing-64: 64px;
  --spacing-72: 72px;
  --spacing-80: 80px;
  --spacing-88: 88px;
  --spacing-96: 96px;
  --spacing-128: 128px;

  /* Primitives de tipografia */
  --weight-bold: 700;
  --weight-semibold: 600;
  --weight-regular: 400;
  --family-primary: "Open Sans";
  --size-xs: 12px;
  --size-s: 14px;
  --size-m: 16px;
  --size-l: 18px;
  --size-xl: 20px;
  --size-2xl: 24px;
  --size-3xl: 28px;
  --size-4xl: 32px;
  --size-5xl: 36px;
  --size-6xl: 40px;
  --size-7xl: 48px;
  --size-8xl: 56px;
  --size-9xl: 60px;
  --size-10xl: 72px;

  /* Tokens de layout (espaiat) */
  --layout-none: var(--spacing-0);
  --layout-x0-175: var(--spacing-2);
  --layout-x0-25: var(--spacing-4);
  --layout-x0-5: var(--spacing-8);
  --layout-x0-75: var(--spacing-12);
  --layout-x1: var(--spacing-16);
  --layout-x1-5: var(--spacing-24);
  --layout-x2: var(--spacing-32);
  --layout-x2-5: var(--spacing-40);
  --layout-x3: var(--spacing-48);
  --layout-x3-5: var(--spacing-56);
  --layout-x4: var(--spacing-64);
  --layout-x5: var(--spacing-80);
  --layout-x8: var(--spacing-128);

  /* Tokens de mida (--size-x*) i mides d'icones */
  --size-x0-175: var(--spacing-2);
  --size-x0-25: var(--spacing-4);
  --size-x0-5: var(--spacing-8);
  --size-x0-75: var(--spacing-12);
  --size-x1: var(--spacing-16);
  --size-x1-25: var(--spacing-20);
  --size-x1-5: var(--spacing-24);
  --size-x2: var(--spacing-32);
  --size-x2-5: var(--spacing-40);
  --size-x3: var(--spacing-48);
  --size-x3-5: var(--spacing-56);
  --size-x4: var(--spacing-64);
  --size-x4-5: var(--spacing-72);
  --size-x5: var(--spacing-80);
  --size-x8: var(--spacing-128);
  --size-icons-lg: var(--size-x3);
  --size-icons-md: var(--size-x2);
  --size-icons-sm: var(--size-x1-5);
  --size-icons-xs: var(--size-x1-25);
  --size-icons-xxs: var(--size-x1);

  /* Arrodoniment (corner radius) */
  --full: var(--spacing-96);
  --xl: var(--spacing-16);
  --lg: var(--spacing-12);
  --md: var(--spacing-8);
  --sm: var(--spacing-4);
  --xs: var(--spacing-2);

  /* Elevacions (primitives; es poden usar directament) */
  --elevations-level-1: 0px 4px 30px 0px rgba(102, 102, 102, 0.1);
  --elevations-level-2: 0px 1px 4px 0px rgba(0, 0, 0, 0.15);
  --elevations-level-3: 0px 4px 16px 1px rgba(51, 51, 51, 0.2);

  /* Tipografia — Body */
  --body-family: var(--family-primary);
  --body-l-bold-weight: var(--weight-bold);
  --body-l-paragraph-spacing: var(--spacing-16);
  --body-l-regular-weight: var(--weight-regular);
  --body-l-semibold-weight: var(--weight-semibold);
  --body-l-size: var(--size-xl);
  --body-m-bold-weight: var(--weight-bold);
  --body-m-paragraph-spacing: var(--spacing-12);
  --body-m-regular-weight: var(--weight-regular);
  --body-m-semibold-weight: var(--weight-semibold);
  --body-m-size: var(--size-m);
  --body-s-bold-weight: var(--weight-bold);
  --body-s-paragraph-spacing: var(--spacing-8);
  --body-s-regular-weight: var(--weight-regular);
  --body-s-semibold-weight: var(--weight-semibold);
  --body-s-size: var(--size-s);
  /* Tipografia — Display */
  --display-desktop-m-size: var(--size-8xl);
  --display-family: var(--family-primary);
  --display-mobile-m-size: var(--size-7xl);
  --display-weight: var(--weight-regular);
  /* Tipografia — Heading */
  --heading-family: var(--family-primary);
  --heading-weight: var(--weight-semibold);
  --heading-desktop-xl-size: var(--size-7xl);
  --heading-desktop-l-size: var(--size-6xl);
  --heading-desktop-m-size: var(--size-4xl);
  --heading-desktop-s-size: var(--size-3xl);
  --heading-desktop-xs-size: var(--size-2xl);
  --heading-mobile-xl-size: var(--size-5xl);
  --heading-mobile-l-size: var(--size-4xl);
  --heading-mobile-m-size: var(--size-3xl);
  --heading-mobile-s-size: var(--size-2xl);
  --heading-mobile-xs-size: var(--size-xl);
  /* Tipografia — Label */
  --label-family: var(--family-primary);
  --label-l-regular-weight: var(--weight-regular);
  --label-l-semibold-weight: var(--weight-semibold);
  --label-l-size: var(--size-l);
  --label-m-regular-weight: var(--weight-regular);
  --label-m-semibold-weight: var(--weight-semibold);
  --label-m-size: var(--size-m);
  --label-s-regular-weight: var(--weight-regular);
  --label-s-semibold-weight: var(--weight-semibold);
  --label-s-size: var(--size-s);
  --label-xs-semibold-weight: var(--weight-semibold);
  --label-xs-size: var(--size-xs);

  /* Semàntics — Fons (background) */
  --background-accent-darkbackground-default: var(--color-brand-secondary-50);
  --background-accent-default: var(--color-brand-primary-500);
  --background-accent-pressed: var(--color-brand-primary-700);
  --background-alert-primary: var(--color-alert-300);
  --background-alert-secondary: var(--color-alert-500);
  --background-alert-tertiary: var(--color-alert-700);
  --background-alternative-primary: var(--color-alternative-300);
  --background-alternative-tertiary: var(--color-alternative-500);
  --background-alternative-secondary: var(--color-alternative-700);
  --background-baner-primary: var(--color-brand-secondary-50);
  --background-buttons-primary-colorbackground-default: var(--background-tertiary);
  --background-buttons-primary-colorbackground-hover: var(--background-secondary-hover);
  --background-buttons-primary-darkbackground-default: var(--background-primary);
  --background-buttons-primary-darkbackground-hover: var(--background-secondary-hover);
  --background-buttons-primary-darkbackground-pressed: var(--background-secondary-darkbackground);
  --background-buttons-primary-default: var(--background-accent-default);
  --background-buttons-primary-hover: var(--background-tertiary);
  --background-buttons-primary-pressed: var(--background-accent-pressed);
  --background-buttons-tertiary-darkbackground-hover: var(--background-secondary-hover);
  --background-buttons-tertiary-hover: var(--background-primary-hover);
  --background-decorative: var(--color-neutral-200);
  --background-disabled: var(--color-neutral-100);
  --background-error-primary: var(--color-error-300);
  --background-error-secondary: var(--color-error-500);
  --background-error-tertiary: var(--color-error-700);
  --background-herobanner-primary: var(--color-brand-secondary-50);
  --background-highlitedlink-primary: var(--color-brand-secondary-50);
  --background-information-primary: var(--color-informative-300);
  --background-information-secondary: var(--color-informative-500);
  --background-information-tertiary: var(--color-informative-700);
  --background-inputs-default: var(--background-primary);
  --background-inputs-disabled: var(--background-disabled);
  --background-inputs-selected: var(--background-tertiary);
  --background-inputs-selected-hover: var(--background-tertiary);
  --background-neutral: var(--color-neutral-300);
  --background-primary: var(--color-base-white);
  --background-primary-hover: var(--color-neutral-100);
  --background-secondary: var(--color-neutral-400);
  --background-secondary-darkbackground: var(--color-neutral-500);
  --background-secondary-hover: var(--color-neutral-300);
  --background-subheader-primary: var(--background-decorative);
  --background-success-primary: var(--color-positive-300);
  --background-success-secondary: var(--color-positive-500);
  --background-success-tertiary: var(--color-positive-700);
  --background-tertiary: var(--color-neutral-700);
  --background-tertiary-opacity-25: var(--color-neutral-700-25);

  /* Semàntics — Vora (border) */
  --border-accent-primary-default: var(--color-brand-primary-500);
  --border-accent-primary-pressed: var(--color-brand-priimary-700);
  --border-accent-secondary: var(--color-brand-primary-600);
  --border-alert: var(--color-alert-700);
  --border-buttons-secondary-colobackground: var(--border-primary);
  --border-buttons-secondary-darkbackground-default: var(--border-primary-darkbackground-default);
  --border-buttons-secondary-default: var(--border-accent-primary-default);
  --border-buttons-secondary-hover: var(--border-primary);
  --border-buttons-secondary-pressed: var(--border-accent-primary-pressed);
  --border-disabled: var(--color-neutral-400);
  --border-disabled-on-content: var(--color-base-white);
  --border-dividers-primary: var(--border-tertiary);
  --border-dividers-secondary: var(--border-secondary);
  --border-error: var(--color-error-700);
  --border-focus: var(--color-focus-500);
  --border-informative: var(--color-informative-700);
  --border-inputs-primary-default: var(--border-secondary);
  --border-inputs-primary-disabled: var(--border-tertiary);
  --border-inputs-primary-hover: var(--border-primary);
  --border-inputs-primary-pressed: var(--border-accent-primary-pressed);
  --border-inputs-primary-selected: var(--border-primary);
  --border-links-primary-darkbackground-default: var(--border-primary-darkbackground-default);
  --border-links-primary-default: var(--border-primary);
  --border-links-primary-hover: var(--border-accent-secondary);
  --border-links-primary-pressed: var(--border-accent-primary-pressed);
  --border-links-primary-visited: var(--border-visited);
  --border-not-available: var(--color-neutral-500);
  --border-primary: var(--color-neutral-700);
  --border-primary-darkbackground-default: var(--color-base-white);
  --border-secondary: var(--color-neutral-400);
  --border-succes: var(--color-positive-700);
  --border-tertiary: var(--color-neutral-300);
  --border-visited: var(--color-alternative-700);

  /* Semàntics — Contingut (content) */
  --content-accent-primary-default: var(--color-brand-primary-500);
  --content-accent-primary-pressed: var(--color-brand-primary-700);
  --content-accent-secondary: var(--color-brand-primary-600);
  --content-alert: var(--color-alert-700);
  --content-buttons-primary-darkbackground-default: var(--content-primary-default);
  --content-buttons-primary-default: var(--content-tertiary-default);
  --content-buttons-secondary-darkbackground-default: var(--content-primary-darkbackgroiund-default);
  --content-buttons-secondary-default: var(--content-accent-primary-default);
  --content-buttons-secondary-hover: var(--content-primary-default);
  --content-buttons-secondary-pressed: var(--content-accent-primary-pressed);
  --content-disabled: var(--color-neutral-400);
  --content-error: var(--color-error-700);
  --content-hover: var(--color-neutral-700);
  --content-illustration-decorative-primary: var(--color-neutral-200);
  --content-illustration-decorative-secondary: var(--color-neutral-300);
  --content-illustration-primary: var(--color-brand-secondary-300);
  --content-illustration-secondary: var(--color-brand-secondary-100);
  --content-illustration-tertiary: var(--color-brand-secondary-50);
  --content-illustration-white: var(--color-base-white);
  --content-informative: var(--color-informative-700);
  --content-links-primary-darkbackground-default: var(--content-primary-darkbackgroiund-default);
  --content-links-primary-default: var(--content-primary-default);
  --content-links-primary-hover: var(--content-accent-secondary);
  --content-links-primary-pressed: var(--content-links-primary-pressed);
  --content-links-primary-visited: var(--content-visited);
  --content-primary-darkbackgroiund-default: var(--color-base-white);
  --content-primary-default: var(--color-neutral-700);
  --content-secondary-darkbackground-default: var(--color-neutral-400);
  --content-secondary-default: var(--color-neutral-500);
  --content-succes: var(--color-positive-700);
  --content-tertiary-darkbackground-default: var(--color-neutral-300);
  --content-tertiary-default: var(--color-base-white);
  --content-texts-body: var(--content-primary-default);
  --content-texts-label-darkbackground-primary-default: var(--content-links-primary-darkbackground-default);
  --content-texts-label-primary-defualt: var(--content-primary-default);
  --content-texts-label-secondary-default: var(--content-secondary-default);
  --content-texts-title: var(--content-primary-default);
  --content-visited: var(--color-alternative-700);
}

[data-theme="atc"] {
  --color-brand-secondary-50: #ebf6ff;
  --color-brand-secondary-100: #cce3f4;  /* hex de la font #cce3f4 no coincideix amb el rgb rgb(204, 227, 224); es conserva el hex */
  --color-brand-secondary-300: #76a8cc;
  --color-brand-primary-500: #a81a8d;
  --color-brand-primary-600: #80146c;
  --color-brand-primary-700: #550c47;
}

[data-theme="gaip"] {
  --color-brand-secondary-50: #e5f1f3;
  --color-brand-secondary-100: #a6ced6;
  --color-brand-secondary-300: #4d9faf;
  --color-brand-primary-500: #00768c;  /* la font escriu #c00000 amb rgb rgb(0, 118, 140); s'usa el valor del rgb, coherent amb la resta de la paleta GAIP */
  --color-brand-primary-600: #005665;
  --color-brand-primary-700: #0d2326;
}

[data-theme="loteries"] {
  --color-brand-secondary-50: #deeafc;  /* hex de la font malformat (#deafc); s'usa el derivat del rgb */
  --color-brand-secondary-100: #c6d9f5;  /* hex de la font #c6d9f5 no coincideix amb el rgb rgb(196, 217, 245); es conserva el hex */
  --color-brand-secondary-300: #627fb9;
  --color-brand-primary-500: #017939;
  --color-brand-primary-600: #005c2b;
  --color-brand-primary-700: #003c1c;
  --color-neutral-100: #f7fafd;  /* la font escriu #f5f5f5 amb rgb rgb(247, 250, 253); s'usa el valor del rgb, coherent amb la resta de neutres de Loteries */
  --color-neutral-200: #eef5ff;  /* la font escriu #f2f2f2 amb rgb rgb(238, 245, 255); s'usa el valor del rgb, coherent amb la resta de neutres de Loteries */
  --color-neutral-300: #e4eefd;
  --color-neutral-400: #7994c9;
  --color-neutral-500: #5a72a3;
  --color-neutral-700: #173571;
  --family-primary: "FS Pimlico";
  --size-xs: 14px;
  --size-s: 16px;
  --size-m: 18px;
  --size-l: 20px;
  --size-xl: 24px;
  --size-2xl: 28px;
  --size-3xl: 32px;
  --size-4xl: 36px;
  --size-5xl: 40px;
  --size-6xl: 48px;
  --size-7xl: 56px;
  --size-8xl: 60px;
  --size-9xl: 72px;
  --size-10xl: 80px;
  /* Tokens específics de Loteries */
  --background-banner-primary: var(--color-neutral-200);
  --background-herobanner-primary: var(--color-neutral-200);
  --background-highlitedlink-primary: var(--color-neutral-200);
  --background-subheader-primary: var(--color-neutral-200);
  --border-links-primary: var(--border-accent-primary-default);  /* la font escriu un sol guió: -border-accent-primary-default */
  --content-links-primary: var(--content-accent-primary-default);  /* la font escriu un sol guió: -content-accent-primary-default */
}

[data-theme="infraestructures"] {
  --color-brand-secondary-50: #ebf8e2;
  --color-brand-secondary-100: #ceeeb8;
  --color-brand-secondary-300: #5eac28;
  --color-brand-primary-500: #48841e;
  --color-brand-primary-600: #2d5213;
  --color-brand-primary-700: #1d350c;
  --color-neutral-400: #9a9a9a;
}
```

## Discrepàncies de la font

- `--color-brand-secondary-100` (ATC): hex de la font #cce3f4 no coincideix amb el rgb rgb(204, 227, 224); es conserva el hex.
- `--color-brand-primary-500` (GAIP): la font escriu #c00000 amb rgb rgb(0, 118, 140); s'usa el valor del rgb, coherent amb la resta de la paleta GAIP.
- `--color-brand-secondary-50` (Loteries): hex de la font malformat (#deafc); s'usa el derivat del rgb.
- `--color-brand-secondary-100` (Loteries): hex de la font #c6d9f5 no coincideix amb el rgb rgb(196, 217, 245); es conserva el hex.
- `--color-neutral-100` (Loteries): la font escriu #f5f5f5 amb rgb rgb(247, 250, 253); s'usa el valor del rgb, coherent amb la resta de neutres de Loteries.
- `--color-neutral-200` (Loteries): la font escriu #f2f2f2 amb rgb rgb(238, 245, 255); s'usa el valor del rgb, coherent amb la resta de neutres de Loteries.
- Primitives Gencat: hi ha `--color-brand-primary-300`, però no `--color-brand-secondary-300` (que sí que existeix a ATC, GAIP, Loteries i Infraestructures i que referencia `--content-illustration-primary`) [a verificar].
- `--color-neutral-700-25` (`--background-tertiary-opacity-25`) no figura a cap taula de primitives; el valor `rgba(51, 51, 51, 0.25)` es deriva de la secció Opacitat.
- Espaiat: la taula "Valors d'espaiat" no marca cap token de mida per a 2 px, 72 px ni 128 px (ni de layout per a 2 px), però les llistes de tokens d'Espaiat i d'Iconografia defineixen `--layout-x0-175`, `--size-x0-175`, `--size-x4-5`, `--size-x8` i `--layout-x8`; el CSS segueix les llistes de tokens.
- Variables: la pestanya Disseny (Figma) només cita els modes gencat, ATC i GAIP; la pestanya Desenvolupament en llista cinc (afegeix Loteries i Infraestructures). Els exemples de la font apliquen el mode amb `<html dir="ltr" lang="en" data-theme="atc">` (igual per a `gaip`, `loteries` i `infraestructures`).
- Errates de nom de token a la font (conservades verbatim al CSS): `--color-brand-priimary-700` (referència de `--border-accent-primary-pressed`), `--content-primary-darkbackgroiund-default`, `--border-buttons-secondary-colobackground`, `--content-texts-label-primary-defualt`, `--border-succes`, `--content-succes`, `--background-baner-primary` (general) vs `--background-banner-primary` (Loteries); a Loteries `--border-links-primary` i `--content-links-primary` referencien `-border-accent-primary-default` / `-content-accent-primary-default` (un sol guió). `--content-links-primary-pressed` apunta a ella mateixa. [a verificar]
