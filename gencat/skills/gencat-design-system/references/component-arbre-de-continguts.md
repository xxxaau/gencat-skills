# Arbre de continguts (Content tree)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/775a73 · Web component: `<content-tree-component>` (paquet core) · Font actualitzada el 2026-07-14 · Extret el 2026-10-28

## Què és i quan usar-lo
Representa la informació de manera jeràrquica, com un esquema en forma d'arbre, creant una estructura que reflecteix la relació entre diferents nivells de contingut.

Cada element pot tenir subelements. Aquesta jerarquia comença amb un ítem principal, que representa el nivell més alt de l'estructura. A partir d'aquí, es despleguen branques que connecten amb altres ítems, subelements, els quals poden tenir més fills, formant una estructura en diversos nivells.

Quan s'utilitza:
- Quan la informació que vols mostrar té una estructura jeràrquica o necessita una navegació clara i escalable.
- Quan vols millorar la navegació amb moltes seccions o nivells, com ara molta informació.

## Quan NO usar-lo / alternatives
- Quan el contingut no té jerarquia, i és molt lineal o té poca informació.
- Quan l'usuari no necessita navegar per contingut en diferents nivells.
- Quan el contingut canvia constantment.

## Anatomia
Figma: Arbre contingut_anatomia.

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Level | 1 / 2 / 3 / 4 / 5 / 6 | - |
| Type | Link / Static text | Link |
| Size | Extra Large - Large / Medium - Small | Extra Large - Large |
| Show Tag | True / False | False |
| Tree parent line | - | - |
| Show line down | True / False | True |
| Tree toggle | - | - |
| Show line top | True / False | False |
| Collapsable button | True / False | True |
| Show line down (Collapsable button) | True / False | True |
| _Tree button | - | - |
| Collapsed | True / False | True |

### Estats
Figma: Arbre contingut_Estats.
- **Replegat:** per defecte es veurà replegat fins al segon nivell, per tal que es mostri la informació de primer i segon nivell de l'arbre de continguts.
- **Desplegat:** es mostra quan l'usuari fa clic a sobre el xebró de cada un dels nivells i subnivells del component, aconseguint que es vegi tota l'estructura de l'arbre de continguts.

## Mides i espaiats
### Adaptació responsiva
El component s'adapta tant a pantalles grans d'escriptori com a dispositius més petits, tauletes o mòbils. Té dos variants de mides:
- **Extra Large:** 640px x 74 px per línia d'arbre (horitzontal, mín. 540px - màx. 656 px).
- **Large - Small:** 296px (mín.) x 54px per línia d'arbre (horitzontal, mín. 296 px - màx. 588px).

## Bones pràctiques

**Claredat i brevetat**
- **FER:** Utilitza etiquetes curtes i concises.
- **NO FER:** No utilitzis etiquetes massa llargues o confuses.

**Construcció**
- **FER:** Quan l'arbre de continguts està tot obert s'ha de veure tot sencer.
- **NO FER:** No hi ha barra de desplaçament dins de l'arbre de continguts.

**Composició**
- **FER:** Fes servir els nivells de jerarquia correctament.

**Distintiu**
- **FER:** En els distintius, es recomana fer servir principalment colors com el blau, lila, etc. abans del verd o el vermell.
- **NO FER:** En els distintius, evita fer servir colors com el vermell, que té connotacions negatives, o el verd que té connotacions positives.
- **FER:** Quan un contingut tingui més d'un distintiu posa'ls de manera igual a cada línia.
- **NO FER:** Quan un contingut tingui més d'un distintiu no els posis diferents a cada línia.

## Accessibilitat

### Pautes d'accessibilitat del contingut web (WCAG)
- **Orientació (AA):** el contingut de l'àrea de text s'adapta a les diferents orientacions de la pantalla, vertical o horitzontal, cosa que permet visualitzar el contingut. [1.3.4 Orientació - CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Ús del color (A):** el color no es fa servir com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a diferenciar les diferents tipologies d'avisos, s'inclouen icones específiques per a cadascuna. [1.4.1 Ús del color - CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són excepció d'aquesta norma. [1.4.3 Contrast mínim - CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA):** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [1.4.4 Canvia la mida del text - CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Redistribució (AA):** el contingut es pot presentar sense pèrdua d'informació o funcionalitat, i sense necessitat de desplaçar-se en dues dimensions per: contingut de desplaçament vertical amb una amplada equivalent a 320 píxels CSS; contingut de desplaçament horitzontal amb una alçària equivalent a 256 píxels CSS. [1.4.10 Redistribució - CAT](https://www.w3.org/WAI/WCAG22/Understanding/reflow) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/reflow)
- **Contrast d'elements no textuals (AA):** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [1.4.11 Contrast d'elements no textuals - CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Espaiat del text (AA):** quan es desenvolupa contingut utilitzant llenguatges de marcatge que permeten aplicar les propietats d'estil de text, no es perd cap contingut ni funcionalitat si s'ajusten les propietats següents: alçada de línia (interlineat) de com a mínim 1,5 vegades la mida de la lletra; espaiat entre els paràgrafs de com a mínim dues vegades la mida de la lletra; espaiat entre lletres (tracking) de com a mínim 0,12 vegades la mida de la lletra; espaiat entre paraules de com a mínim 0,16 vegades la mida de la lletra. [1.4.12 Espaiat del text - CAT](https://www.w3.org/Translations/WCAG22-ca/#text-spacing) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/text-spacing)
- **Teclat (A):** tota la funcionalitat del contingut (navegar pels enllaços i botons) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [2.1.1 Teclat - CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Ordre del focus (A):** l'arbre presenta un ordre lògic del focus dels elements interns per facilitar la navegació per teclat o altres dispositius d'entrada. L'ordre ha de seguir el flux de la informació o les tasques que s'estan presentant. L'ordre ha de ser el següent: 1. Tab: es navega per tot el contingut endavant o, en el cas que ja no n'hi hagi endavant, salta a la següent línia. 2. Intro: obrir enllaç. 3. Shift Tab: es va enrere, el contrari de Tab. [2.4.3 Ordre del focus - CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-order) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-order)
- **Focus visible (AA):** la navegació pels diferents botons i enllaços mitjançant teclat és visible a través d'un rectangle. [2.4.7 Focus visible - CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

## Implementació (component web)

### `<content-tree-component>`

Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat (lloc) |
|---|---|---|---|---|---|
| `tree` | `tree` | Estructura d'arbre de navegació: array on cal afegir el contingut de l'arbre. Els fills de cada contingut aniran afegits de la mateixa manera, amb els mateixos atributs, dins del pare corresponent. Accepta array d'objectes o string JSON | string (Array) | `[]` | Obligatori |

**Props que accepten JSON.** Propietats de l'array `tree`:

| Propietat | Atribut | Descripció | Tipus | Obligatori |
|---|---|---|---|---|
| `label` | `label` | Text del contingut | String | Obligatori |
| `isLink` | `is-link` | Indica si és enllaç o no | Boolean | Opcional |
| `tags` | `tags` | Etiqueta del text | Array | Opcional |
| `children` | `children` | Fills del contingut. S'afegeixen a un array amb els mateixos atributs que `tree` | Array | Opcional |

Propietats de l'array `tags`:

| Propietat | Atribut | Descripció | Tipus | Obligatori |
|---|---|---|---|---|
| `text` | `text` | Text de l'etiqueta | String | Obligatori |
| `color` | `color` | Color de l'etiqueta | String | Obligatori |
| `textAlternative` | `text-alternative` | Text que llegirà el lector de pantalla | String | Obligatori |

**Variants**

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `color` | `color-blau`, `color-verd`, `color-taronja`, `color-vermell`, `color-lila`, `color-gris`, `color-neutre` | - |

**Esdeveniments (lloc)**

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `linkEmit` | Esdeveniment llançat en fer clic sobre l'enllaç | `id` | `link-component` |
| `focusLink` | Esdeveniment llançat en fer focus sobre l'enllaç | - | `link-component` |
| `blurLink` | Es llança cada cop que es treu el focus de l'enllaç | - | `link-component` |
| `handlerClick` | Esdeveniment llançat en fer clic sobre algun dels botons | `id` | `button-component` |
| `focusButton` | Esdeveniment llançat en fer focus sobre algun dels botons | - | `button-component` |
| `button-component` | Esdeveniment llançat en treure el focus d'algun dels botons | - | `button-component` |

[discrepància: el lloc llista aquests esdeveniments heretats dels components fills; el PDF diu «Sin eventos declarados» per a `content-tree-component`] [a verificar: l'última fila del lloc porta el nom `button-component` a la columna d'esdeveniment, que sembla un error d'origen]

**Depèn de:** `link-component` ([Enllaços](component-enllacos.md)), `button-component` ([Botons](component-botons.md)).

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<content-tree-component tree='[
      {
        "label": "Principal",
        "children": [
          {
            "label": "Blog",
            "tags": [
              { "text": "NW", "color": "color-lila", "textAlternative": "Notícia Web" }
            ],
            "children": [
              {
                "label": "2024",
                "children": [
                  {
                    "label": "Enero",
                    "isLink": true,
                    "tags": [
                      { "text": "OK", "color": "color-verd", "textAlternative": "Òptim Kriteri" }
                    ]
                  },
                  {
                    "label": "Febrero",
                    "isLink": true,
                    "tags": [
                      { "text": "RV", "color": "color-taronja", "textAlternative": "Revisar Vista" },
                      { "text": "DR", "color": "color-vermell", "textAlternative": "Dades Ràpides" }
                    ]
                  }
                ]
              },
              {
                "label": "2023",
                "tags": [
                  { "text": "HI", "color": "color-gris", "textAlternative": "Històric Important" }
                ],
                "children": [
                  {
                    "label": "Marzo",
                    "isLink": true
                  }
                ]
              }
            ]
          },
          {
            "label": "Prueba",
            "isLink": true
          },
          {
            "label": "Proyectos",
            "tags": [
              { "text": "AC", "color": "color-verd", "textAlternative": "Acceptat Correctament" }
            ],
            "children": [
              {
                "label": "Proyecto A",
                "isLink": true,
                "tags": [
                  { "text": "IN", "color": "color-blau", "textAlternative": "Iniciat Nou" }
                ]
              },
              {
                "label": "Proyecto B",
                "isLink": true,
                "tags": [
                  { "text": "UR", "color": "color-verd", "textAlternative": "Urgent Requereix" }
                ],
                "children": [
                  {
                    "label": "Subproyecto B1",
                    "isLink": true
                  },
                  {
                    "label": "Subproyecto B2",
                    "isLink": true,
                    "tags": [
                      { "text": "NW", "color": "color-gris", "textAlternative": "Notícia Web" },
                      { "text": "RV", "color": "color-neutre", "textAlternative": "Revisar Vista" }
                    ]
                  }
                ]
              }
            ]
          },
          {
            "label": "Contacto",
            "isLink": true,
            "tags": [
              { "text": "ON", "color": "color-blau", "textAlternative": "On Line" },
              { "text": "SP", "color": "color-verd", "textAlternative": "Suport Professional" }
            ]
          }
        ]
      }
    ]'></content-tree-component>
```

**Exemple d'instància (PDF)**

```html
<content-tree-component
tree='[]'
></content-tree-component>
```

## Claus de text (internacionalització)
Vegeu les [claus](dev-referencia-de-claus-disponibles.md) (`contentTree`).

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 4.2.0 | 10.1.0 | 29 maig, 2026 | Desenvolupament: es corregeix la representació de línies en nivells imbricats. |
| 4.2.0 | 8.5.0 | 5 desembre, 2025 | Desenvolupament: resolució de problemes menors. |
| 4.2.0 | 6.2.1 | 3 octubre, 2025 | Desenvolupament: nova propietat afegida o eliminada. |
| 4.2.0 | 6.0.1 | 28 juliol, 2025 | Desenvolupament: resolució de problemes. |
| 4.2.0 | 6.0.0 | 3 juliol, 2025 | Desenvolupament del component botó desplegable. |
| 4.2.0 | - | 05 juny, 2025 | Disseny i documentació del component. |

## Vegeu també
- [Etiquetes](component-etiquetes.md): per mostrar l'estat d'un element, les propietats clau o les categories.
- [Enllaços](component-enllacos.md): per connectar diferents pàgines web o recursos.
