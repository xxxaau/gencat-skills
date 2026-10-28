# Enllaços (Links)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/92e152 · Web component: `<link-component>` i `<highlighted-link-component>` (paquet core) · Font actualitzada el 2026-10-22 · Extret el 2026-10-28

## Què és i quan usar-lo
Text que navega a una altra ubicació. Un enllaç és un text utilitzat per **connectar una part del contingut o funcionalitat amb una altra**, facilitant la navegació entre elles.

Els enllaços s'empren per a enllaçar o guiar l'usuari a altres continguts. Els principals casos són:
- Navegar a una altra **pàgina dins del lloc web**.
- Navegar a un **lloc web extern**.
- Enllaçar a **correus electrònics o números de telèfon** (pot iniciar una aplicació).
- Redirigir a **documents o arxius.**

### Enllaços externs
Els enllaços externs són aquells que redirigeixen a pàgines que presenten un **canvi en l'estructura de la navegació principal.**

### Enllaç destacat
Els enllaços destacats s'utilitzen per a enllaços que necessiten tenir una major jerarquia en la pàgina perquè tenen una **major rellevància.** Poden estar com una secció única o formar part d'una secció de la pàgina. L'enllaç destacat pot ser tant **intern com extern.**

### Enllaços versus botons

| Enllaços | Botons |
|---|---|
| Emprats per navegació | Emprats per accions que provoquen un canvi en el sistema |
| Estan escrits en una frase o part d'ella | Els botons han de ser concisos i clars utilitzant un màxim de quatre paraules |
| Poden redirigir a un lloc o document extern | Realitzen una acció com enviar un formulari, guardar o editar, entre d'altres |

## Anatomia
- **Enllaç** (Figma `Links`): Show Icon, First line, Second line, Third line, Size, Nº of Lines, State, Dark background, Visited.
- **Enllaç destacat** (Figma `Highlighted link`): Full width.

## Variants, tipus i estats

### Enllaç

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Type | Not visited / Visited | Not visited |
| State | Default / Hover / Focus / Active / Visited | Default |
| Number of lines | One / Two / Three | One |
| Size | Small / Medium / Large | Medium |
| External link Icon | With / without icon | Without icon |
| Show Icon | True / False | False |

Variants Figma (`Links`): Show Icon = True | False; First line = Enllaç 1ª linia; Second line = Enllaç 2ª linia; Third line = Enllaç 3ª linia; Size = Small | Medium | Large; Nº of Lines = One | Two | Three; State = Default | Hover | Focus | Active | Visited; Dark background = False | True; Visited = False | True.

### Enllaç destacat

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Full width | True / False | True |

Segons si és a amplada completa o no, presenta les propietats següents.

**Amplada completa** (`_Highlighted link_full width`)

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Extra Large Column Fixed / Extra Large Column Variable / Large / Medium / Small | Extra Large Column Fixed |
| Title | True / False | True |

**Amplada segons retícula** (`_Highlighted link`)

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Extra Large - Medium / Small | Extra Large - Medium |
| Title | True / False | True |

## Mides i espaiats
- Les mides dels enllaços s'hauran de seleccionar **en funció del text al qual acompanyen.** Si s'està usant un cos de text *Large* (20 px), la mida de l'enllaç haurà de ser la mateixa (*Large*).
- Per a enllaços que no estiguin dins d'un cos de text, s'utilitzarà la mida *Medium* per defecte, la *Large* per a casos on la jerarquia d'altres elements sigui de mides superiors, com un *Heading XL*, i la mida *Small* per a casos on es disposi de poc espai, com el cas del peu de pàgina.
- Els enllaços de mida *Small* tenen un *min-height* de 24 px.

## Comportament i interacció
**Obrir l'enllaç:** els enllaços s'obriran per defecte en la mateixa pestanya en la qual es troba l'usuari. Hi ha dues excepcions en les quals s'obriran en una pestanya nova:
- Si és un **enllaç extern**.
- Quan l'usuari està en un **procés de tramitació** o en un **procés en el qual pugui perdre informació.**

### Documents / fitxers descarregables
Els documents dins de la llista de resultats es presenten de manera clara i intuïtiva. La indicació del pes de l'arxiu es mostra segons aquests criteris:
- **Pes inferior a 1 MB:** no es mostrarà el pes del fitxer.
- **Pes igual o superior a 1 MB:** es mostrarà el pes del fitxer.
- Quan es mostri, el pes s'expressarà en **MB** i amb **1 decimal**.

Per consultar els criteris d'arrodoniment, separadors decimals i format numèric, consulta [Introducció de dades](patro-introduccio-de-dades.md).

Al costat del títol, entre parèntesis, es mostra el **format del fitxer i el seu pes**, oferint informació útil sense sobrecarregar la visualització.

**Comportament:** en fer clic sobre el títol del resultat s'obre una nova pestanya amb la previsualització del document. Aquesta vista permet revisar el contingut abans de descarregar-lo, amb un botó de descàrrega clarament visible dins de la previsualització. Aquesta interacció evita descàrregues accidentals i millora l'experiència de l'usuari, assegurant que el procés sigui segur i intuïtiu.

### Ubicació de l'enllaç destacat
L'enllaç destacat s'utilitza en amplada completa quan és una secció pròpia i, per tant, es col·locarà entre seccions diferenciades. Quan no va a amplada completa, es col·locarà dins d'una altra secció de contingut.

## Bones pràctiques

**Contextualització**
- **FER:** Utilitza'ls en una frase o part d'una frase sense ser excessivament llarga.
- **NO FER:** No els utilitzis en una frase excessivament llarga.
- **FER:** Contextualitza'ls perquè sigui més clara la navegació. Un enllaç ben redactat té sentit fora de context i normalment combina un tema (p. ex., seguretat, marca, màrqueting) amb el format (qüestionari, formulari de sol·licitud, etc.).
- **NO FER:** No facis servir enllaços no contextualitzats com "fes clic" o "aquest enllaç".
- **FER:** Es recomana que l'enllaç estigui relacionat amb el context del títol de la pàgina, secció, arxiu, etc. on navega.
- **NO FER:** No es recomana que l'enllaç no estigui relacionat amb el context del títol on navega.

**Documents o arxius**
- **FER:** En el cas de redirecció a documents o arxius es recomana indicar el tipus de format i el pes.

**Enllaços externs**
- **FER:** Acompanya els enllaços externs de la icona corresponent.

**Guia de comunicació clara**
- **FER:** Segueix la [guia de comunicació clara](fonaments-comunicacio-clara.md). No utilitzis l'imperatiu en català o l'infinitiu en castellà.

**URL**
- **NO FER:** No mostris els enllaços URL. Excepció: en casos legals on l'usuari necessiti imprimir l'enllaç per algun requisit específic.

**Imatges**
- **FER:** No utilitzis imatges com a enllaços. Inclou altres elements com enllaços.

**Destacats**
- **NO FER:** No utilitzis els destacats sense icona i/o sense fons.
- **NO FER:** No utilitzis el destacat dins del cos d'un text.

## Accessibilitat

### Pautes WCAG
- **Ús del color (A)**: el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a diferenciar els diferents estats es juga amb la presència de subratllats i el seu gruix. [1.4.1 Ús del color - CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA)**: els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. [1.4.3 Contrast mínim - CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA)**: excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [1.4.4 Canvia la mida del text - CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA)**: els elements gràfics presenten un contrast mínim de 3:1. [1.4.11 Contrast d'elements no textuals - CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A)**: tota la funcionalitat del contingut (navegar pels enllaços) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [2.1.1 Teclat - CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Focus visible (AA)**: la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [2.4.7 Focus visible - CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

## Implementació (component web)

### `<link-component>`

Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte |
|---|---|---|---|---|
| `ariaDescribedby` | `aria-describedby` | Atribut aria-describedby per a l'enllaç (ID de l'element que descriu aquest component). Opcional | string | `undefined` |
| `ariaLabelledby` | `aria-labelledby` | Atribut aria-labelledby per a l'enllaç. Opcional | string | `undefined` |
| `colorBackground` | `color-background` | Determina el color de fons de l'enllaç. Opcions: `dark-background`, `grey-background`. Opcional | string | `undefined` (PDF); `grey-background` (lloc, vegeu variants) |
| `customId` | `custom-id` | Identificador personalitzat (identificador HTML personalitzat de l'element). Opcional | string | `undefined` |
| `mode` | `mode` | Permet configurar si l'enllaç és extern o intern: si és extern, el target serà blank i apareixerà icona; si és intern, el target serà self i l'enllaç no tindrà icona. Opcions: `external`, `internal`. Opcional | string | `internal` |
| `size` | `size` | Mida de la font de l'enllaç. Opcions: `link-large`, `link-medium`, `link-small`. Opcional | string | `link-medium` |
| `text` | `text` | Text que es mostra dins de l'enllaç. **Obligatori** | string | `undefined` |

[discrepància: lloc diu que el valor predeterminat de `colorBackground` és `grey-background`; PDF diu `undefined`]

**Variants**

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `colorBackground` | `dark-background` `grey-background` | `grey-background` |
| `mode` | `external` `internal` | `internal` |
| `size` | `link-small` `link-medium` `link-large` | `link-medium` |

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `blurLink` | Es llança cada cop que es treu el focus en un enllaç (`CustomEvent<void>`) | - | `link-component` |
| `focusLink` | Es llança cada cop que es fa focus en un enllaç (`CustomEvent<HTMLElement>`) | - | `link-component` |
| `linkEmit` | Es llança cada cop que es fa clic en un enllaç (`CustomEvent<string>`) | `id` | `link-component` |

**Utilitzat per**: `callout-component` ([Avisos](component-avisos.md)), `card-navigation-component` ([Targetes](component-targetes.md)), `content-tree-component` ([Arbre de continguts](component-arbre-de-continguts.md)), `dynamic-table-component` ([Taules dinàmiques](component-taules-dinamiques.md)), `empty-state-component` ([Estat buit](component-estat-buit.md)), `file-uploader-component` ([Carregador d'arxius](component-carregador-d-arxius.md)), `footer-component` ([Peu de pàgina](component-peu-de-pagina.md)), `header-public-component` ([Capçalera web pública](component-capcalera-web-publica.md)), `highlighted-link-component` (vegeu avall), `horizontal-menu-component` ([Menú horitzontal](component-menu-horitzontal.md)), `link-list-component` ([Llista d'enllaços](component-llista-d-enllacos.md)), `list-component` ([Llista](component-llista.md)), `pagination-component` ([Paginació](component-paginacio.md)), `poi-component` ([Visor de mapa](component-visor-de-mapa.md)), `popover-component` ([Descripció emergent](component-descripcio-emergent.md)), `results-list-component` ([Llistat de resultats](component-llistat-de-resultats.md)), `status-tracker-component` ([Rastrejador d'estat](component-rastrejador-d-estat.md)), `summary-list-component` ([Dades estructurades](component-dades-estructurades.md)), `table-of-contents-component` ([Taula de continguts](component-taula-de-continguts.md); el lloc enllaça a la pàgina de Dades estructurades), `timeline-component` ([Línia de temps](component-linia-de-temps.md)), `toast-component` ([Notificació emergent](component-notificacio-emergent.md)).

**Exemple d'ús**

```html
<!-- /index.html -->
<link-component 
  text="Enllaç" 
  size="link-small"
  mode="external"
  color-background="grey-background"
  custom-id="custom-id"
>
</link-component>
```

**Exemple d'instància (PDF)**

```html
<link-component
aria-describedby="texto-ejemplo"
aria-labelledby="texto-ejemplo"
color-background="dark-background"
custom-id="texto-ejemplo"
mode='internal'
size='link-medium'
text="texto-ejemplo"
></link-component>
```

### `<highlighted-link-component>`

Paquet: core. Sense esdeveniments propis declarats (PDF); els del `link-component` (vegeu a sota).

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte |
|---|---|---|---|---|
| `description` | `description` | Descripció de l'enllaç. Opcional | string | `undefined` |
| `fullWidth` | `full-width` | Permet configurar si el component ocuparà l'amplada completa de la pàgina o no. Opcional | boolean | `true` |
| `linkProps` | `link-props` | Configuració de l'enllaç. Accepta array d'objectes o string JSON. **Obligatori** | string (JSON) | `undefined` |
| `titleHighlightedLink` | `title-highlighted-link` | Títol de l'enllaç destacat. Opcional | string | `undefined` |
| `visibilityTitle` | `visibility-title` | Visibilitat del títol. Opcional | boolean | `true` |

**Props que accepten JSON**

`linkProps`:

| Propietat | Atribut | Descripció | Obligatorietat | Tipus |
|---|---|---|---|---|
| `customId` | `custom-id` | Identificador personalitzat de l'enllaç | Opcional | string |
| `text` | `text` | Text de l'enllaç | Obligatori | string |
| `mode` | `mode` | Tipus d'enllaç: `internal` o `external` | Obligatori | string |

**Esdeveniments** (del `link-component` intern)

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `blurLink` | Es llança cada cop que es treu el focus en un enllaç | - | `link-component` |
| `focusLink` | Es llança cada cop que es fa focus en un enllaç | - | `link-component` |
| `linkEmit` | Es llança cada cop que es fa clic en un enllaç | `id` | `link-component` |

**Depèn de**: `link-component`.

**Exemple d'ús**

```html
<!-- /index.html -->
<highlighted-link-component 
  title-highlighted-link="Títol"
  description="Text descriptiu de l'enllaç"
  visibility-title="true"
  full-width="false" 
  link-props='{
  "text": "Enllaç 1ª linia",
  "mode": "internal"
}
'></highlighted-link-component>
```

**Exemple d'instància (PDF)**

```html
<highlighted-link-component
description="texto-ejemplo"
full-width=true
link-props="texto-ejemplo"
title-highlighted-link="texto-ejemplo"
visibility-title=true
></highlighted-link-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.5.0 | 9.2.0 | 02 octubre, 2026 | Disseny: s'ha afegit un min-height de 24 px als enllaços mida small |
| 12.3.0 | 9.2.0 | 31 juliol, 2026 | Disseny: s'apliquen les variables de color de nou dels estats pressed i hover |
| 12.0.0 | 9.2.0 | 10 juliol, 2026 | Desenvolupament: enllaços destacats: s'utilitza el token correcte per al color de text de la descripció de l'enllaç |
| 12.0.0 | 9.2.0 | 29 maig, 2026 | Disseny: s'aplica el token específic pel fons dels enllaços destacats |
| 9.0.0 | 9.2.0 | 20 febrer, 2026 | Disseny: s'han eliminat els truncats del títol |
| 8.2.0 | 9.2.0 | 27 febrer, 2026 | Desenvolupament: es crea la property customId per poder introduir id personalitzat |
| 8.2.0 | 6.2.1 | 27 octubre, 2025 | Disseny: revisió d'estils tipogràfics |
| 8.1.0 | 6.2.1 | 6 octubre, 2025 | Disseny: s'ajusta el comportament de la descripció dels enllaços destacats perquè el contenidor s'adapti a la llargada de la descripció; es canvia el color de la descripció per label-default. Desenvolupament: nova propietat afegida o eliminada |
| 8.0.0 | 6.0.1 | 12 setembre, 2025 | Disseny: es modifica la mida de l'enllaç a Medium i també la de la icona a Medium; també es modifiquen els espaiats |
| 5.0.0 | 6.0.1 | 28 juliol, 2025 | Desenvolupament: resolució de problemes |
| 5.0.0 | 6.0.0 | 3 juliol, 2025 | Desenvolupament: resolució de problemes |
| 5.0.0 | 5.0.0 | 10 juny, 2025 | Disseny: canvi de color del fons de l'enllaç destacat; s'elimina el subratllat de l'estat pressed |
| 4.0.0 | 5.0.0 | 9 juny, 2025 | Desenvolupament: resolució de problemes |
| 4.0.0 | 4.0.1 | 19 maig, 2025 | Desenvolupament: resolució de problemes |
| 3.0.0 | 2.0.0 | 31 març, 2025 | Disseny: disseny de l'enllaç destacat |
| 2.4.0 | 2.0.0 | 10 març, 2025 | Disseny: correcció de l'alineació de l'autolayout; passa de centrada a l'esquerra |
| 2.3.0 | 1.0.0 | 31 gener, 2025 | Sense canvis |
| 2.2.0 | 0.1.1 | 20 gener, 2025 | Disseny: adaptació dels enllaços a dues i tres línies |
| 2.1.0 | 0.1.1 | 04 desembre, 2024 | Disseny: correcció de l'alineació en els estats |
| 2.0.0 | 0.1.0 | 02 desembre, 2024 | Sense canvis |
| 1.1.0 | 0.1.0 | 22 novembre, 2024 | Sense canvis |
| 1.1.0 | 0.0.4 | 18 novembre, 2024 | Sense canvis |
| 1.0.0 | 0.0.3 | 1 novembre, 2024 | Disseny, desenvolupament i documentació del component |

## Vegeu també
- [Fils d'Ariadna](component-fils-d-ariadna.md): per proporcionar una trajectòria clara de les pàgines visitades.
- [Llista](component-llista.md): per a agrupacions de contingut relacionat.
- [Llista d'enllaços](component-llista-d-enllacos.md): per a agrupacions d'enllaços.
- [Botons](component-botons.md)
- [Llistat de resultats](component-llistat-de-resultats.md)
