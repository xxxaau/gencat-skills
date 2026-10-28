# Taula de continguts (Table of contents)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/41fe25 · Web component: `<table-of-contents-component>` (paquet core) · Font actualitzada el 2026-10-26 · Extret el 2026-10-28

## Què és i quan usar-lo
Una taula de continguts és una llista estructurada d'àncores clicables que representen les diferents seccions d'una pàgina de continguts. Facilita l'accés ràpid i estructurat al contingut, cosa que permet als usuaris desplaçar-se directament a qualsevol apartat sense haver de fer-ho manualment.

Quan s'utilitza:
- Quan la pàgina té un contingut llarg i estructurat en diverses seccions.
- Quan el contingut està organitzat jeràrquicament i els usuaris poden necessitar accedir directament a una secció específica.
- Quan la pàgina és un article tècnic, un informe o una documentació extensa.

## Quan NO usar-lo / alternatives
- Quan la pàgina té poc contingut i es pot visualitzar fàcilment sense necessitat de navegació.
- Quan es vol que els usuaris llegeixin el contingut en un ordre específic.
- Quan la navegació requereix canviar de pàgina en lloc de desplaçar-se entre seccions dins d'una mateixa pàgina (en aquest cas, és més adequat utilitzar un menú de navegació).

## Anatomia
Figma: Anatomia (Taula de continguts/Components/Taula de continguts/DOC_TableofContents/Anatomia). La font no inclou llista numerada de parts.

## Variants, tipus i estats

### Taula de continguts

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Extra Large / Large - Small | Extra Large |
| Collapsed | True / False | True |
| Slot | Sections | Section |

Variants Figma: punt de tall — _Table of Contents dropdown [Collapsed = True]; Table of Contents [Breakpoint = Extra Large]. Col·lapsat — _Table of Contents dropdown [Collapsed = False | True].

### Secció

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Default / Hover / Focus / Selected / Selected-Hover / Selected-Focus | Default |
| Level | First Level / Second Level | First Level |
| Line top | True / False | True |
| Line down | True / False | True |

Variants Figma: _Section [State = Default, Level = First Level]; LineDown; LineTop.

## Mides i espaiats
- Punt de tall Extra Large: ubicada al lateral esquerre, alineada amb el títol de la pàgina, amb una amplada màxima de 262 píxels.
- Historial de disseny: espaiat entre l'àrea interactiva i el divisor de 8px (versió Github 3.0.0, 2 maig 2025).

## Comportament i interacció

### Visualització
- Punt de tall *Extra-Large:* la taula de continguts es manté *sticky* (fixa) al lateral esquerre quan l'usuari es desplaça per la pàgina i sempre està visible (no es pot replegar).
- Punts de tall *Large, Medium i Small:* la taula de continguts es replega i es col·loca dins del contingut de la pàgina; deixa de ser *sticky*.

### Ubicació a la pàgina
- Punt de tall *Extra-Large:* lateral esquerre, alineat amb el títol de la pàgina, amb una amplada màxima de 262 píxels.
- Punts de tall *Large, Medium i Small:* es disposa replegada dins del contingut, després del títol, subtítol i data (si és possible).
- Figma: extraLarge, Medium, Large, Small.

### Opció de replegar i desplegar
- Punt de tall *Extra-Large:* sempre visible, no es pot replegar.
- Punts de tall *Large, Medium i Small:* inicialment, la taula de continguts apareix replegada. Quan l'usuari la desplega, es manté oberta fins que l'usuari la tanqui manualment. Si l'usuari accedeix a una secció de la taula i després torna a dalt amb el botó *back to top*, la taula de continguts continua desplegada, excepte si l'usuari l'ha tancada abans.

### Ressaltat de la secció activa
- Punt de tall *Extra-Large:* es mostra un ressaltat visual per indicar la secció activa mitjançant un element gràfic animat. A mesura que l'usuari es desplaça per les diferents seccions de la pàgina, l'indicador s'actualitza i assenyala l'opció corresponent a la secció on es troba.
- Punts de tall *Large, Medium i Small:* no es mostra l'element de ressaltat, sinó que es mostra de la mateixa manera que l'opció per defecte.

### Interactivitat
- Només els enllaços de la taula de continguts són interactius.
- L'element gràfic que indica la secció activa és decoratiu i no té funcionalitat interactiva.

## Bones pràctiques

Salt de línia:
- **FER:** utilitzar salt de línia per garantir que el títol sigui llegible i que no sobrecarregui l'espai visual.
- **NO FER:** deixar títols massa llargs que ocupin més de dues línies.

Claredat:
- **FER:** crear títols clars, simples i directes que els usuaris puguin entendre ràpidament.
- **NO FER:** fer servir títols amb frases complicades o genèriques que requereixin una interpretació addicional i no donin context real del contingut de la secció.

Estil:
- **FER:** utilitzar el mateix estil i format per a tots els títols i seccions de la taula de continguts per aconseguir coherència visual.

Consistència:
- **FER:** fer coincidir exactament els títols de la taula de continguts amb els de les seccions de la pàgina per facilitar la navegació i garantir consistència.

Enllaç:
- **NO FER:** incloure enllaços externs que poden trencar la navegació interna i distreure l'usuari del contingut principal.

Visibilitat:
- **NO FER:** ometre titulars només perquè no es veuen en la càrrega inicial de la pàgina.

## Accessibilitat

### Pautes d'accessibilitat del contingut web (WCAG)
- **Orientació (AA) — 1.3.4:** el contingut s'adapta a les diferents orientacions de la pantalla, com ara vertical o horitzontal, cosa que permet visualitzar el contingut. [CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Contrast mínim (AA) — 1.4.3:** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA) — 1.4.4:** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA) — 1.4.11:** els elements gràfics presenten un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A) — 2.1.1:** tota la funcionalitat del contingut (navegar pels enllaços) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Focus visible (AA) — 2.4.7:** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

### Navegació per teclat

| Tecla | Acció |
|---|---|
| Tabulació | Navega al següent element interactiu de la pàgina |
| Shift + Tabulació | Navega a l'element interactiu anterior de la pàgina (la font diu "a l'element interactiu de la pàgina") |

## Implementació (component web)

Des de disseny està definit que aquest component tingui una posició fixa en punts de tall *Extra Large*, la qual cosa no està reflectida al CSS del codi. Per tant, quan s'utilitzi aquest component cal incloure'l en un contenidor al qual s'apliqui la posició fixa (`position: sticky`) al seu CSS, seguint les indicacions de disseny sobre la seva ubicació a la pàgina.

### `<table-of-contents-component>`
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat (lloc) |
|---|---|---|---|---|---|
| `idActive` | `id-active` | Identificador de l'enllaç actiu | `string` | `undefined` | Opcional |
| `linkListData` | `link-list-data` | Array amb les dades de cada enllaç. Accepta objecte o string JSON | `string` (array) | `undefined` | Obligatori |
| `textTooltipBackToTop` | `text-tooltip-back-to-top` | Text del tooltip del botó de tornar a dalt | `string` | `` (buit) | Obligatori |

**Propietats de l'array `linkListData`**

| Propietat | Descripció | Atribut | Obligatorietat | Tipus |
|---|---|---|---|---|
| `children` | Fills d'aquest enllaç. Té les mateixes propietats que `linkListData` | `children` | Opcional | Array |
| `text` | Text de l'enllaç | `idLink` (tal com apareix al lloc) | Obligatori | String |
| `idLink` | Identificador de l'enllaç actiu | `text` (tal com apareix al lloc) | Obligatori | String |

[discrepància: a la taula del lloc les columnes "Atribut" de `text` i `idLink` estan intercanviades (`text` → `idLink`, `idLink` → `text`); l'exemple de codi usa `text` per al text i `idLink` per a l'identificador. Als fills de l'exemple també apareix `href`.]

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `blurLink` | Es llança cada cop que es treu el focus d'un enllaç | - | `link-component` |
| `focusLink` | Es llança cada cop que es fa focus en un enllaç | - | `link-component` |
| `linkEmit` | Es llança cada cop que es fa clic en un enllaç | `id` | `link-component` |
| `clickLinkTableContents` | Es llança cada cop que es fa clic en un enllaç; com a paràmetre conté el seu ID (tipus PDF: `CustomEvent<any>`) | ID de l'enllaç | `table-of-contents-component` |

**Depèn de:** [`divider-component`](component-divisor.md), [`back-to-top-button-component`](component-boto-tornar-amunt.md), [`tooltip-component`](component-indicador-de-funcio.md), [`link-component`](component-enllacos.md).

**Exemple d'ús**

```html
<!-- /index.html -->
<table-of-contents-component
      id-active="id1"
      text-tooltip-back-to-top="Tornar amunt"
      link-list-data='[
        { "text": "Secció de la pàgina exemple", "idLink": "id1", "children": [{"idLink": "id-sub-1", "text": "Subsecció de la pàgina exemple","href": "#intro-sub-1"}]},
        { "text": "Secció de la pàgina exemple", "idLink": "id2" },
        { "text": "Secció de la pàgina exemple", "idLink": "id3" },
        { "text": "Secció de la pàgina exemple", "idLink": "id4" },
        { "text": "Secció de la pàgina exemple", "idLink": "id5" },
        { "text": "Secció de la pàgina exemple", "idLink": "id6" },
        { "text": "Secció de la pàgina exemple", "idLink": "id7" }
      ]'></table-of-contents-component>
```

Exemple d'instància (PDF):

```html
<table-of-contents-component
id-active="texto-ejemplo"
link-list-data="texto-ejemplo"
text-tooltip-back-to-top=''
></table-of-contents-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 11.0.0 | 9.2.0 | 8 maig, 2026 | Disseny: s'apliquen slots pel llistat d'elements. |
| 9.0.0 | 9.2.0 | 20 març, 2026 | Desenvolupament: eliminar truncats |
| 9.0.0 | 9.1.0 | 27 febrer, 2026 | Disseny: s'afegeix instància del bullet per poder adaptar les línies en funció de l'alçada; s'elimina l'opció de truncar text. |
| 8.1.0 | 9.1.0 | 6 febrer, 2026 | Desenvolupament: es fan adaptacions d'accessibilitat pel que fa a mides de font extra gran i augment de pantalla |
| 8.1.0 | 6.1.0 | 6 octubre, 2025 | Disseny: s'ajusta la posició del focus de l'asset Table dropdown a Left + Right; s'ajusta la posició del divisor de l'asset Table dropdown a Left + Right. |
| 4.0.0 | 6.1.0 | 12 setembre, 2025 | Desenvolupament: nova propietat afegida |
| 4.0.0 | 6.0.1 | 28 juliol, 2025 | Desenvolupament: resolució de problemes |
| 4.0.0 | 5.0.0 | 9 juny, 2025 | Desenvolupament: resolució de problemes |
| 4.0.0 | 4.0.1 | 19 maig, 2025 | Desenvolupament: resolució de problemes |
| 4.0.0 | 3.0.0 | 2 maig, 2025 | Disseny: s'augmenta l'espaiat entre l'àrea interactiva i el divisor a 8px. |
| 2.4.0 | 3.0.0 | 28 abril, 2025 | Desenvolupament del component |
| 2.4.0 | No aplica | 10 març, 2025 | Disseny del component. |

## Vegeu també
- [Enllaços](component-enllacos.md): per facilitar la navegació entre parts del contingut o funcionalitats.
- [Llista](component-llista.md): les llistes són agrupacions de contingut relacionat.
- [Botó Tornar amunt](component-boto-tornar-amunt.md)
- [Divisor](component-divisor.md)
- Suport: https://zeroheight.com/38669693e/p/57c57a-suport-i-contacte · https://zeroheight.com/38669693e/p/72240b-preguntes-frequents · https://zeroheight.com/38669693e/p/690b45 · https://zeroheight.com/38669693e/p/342611
