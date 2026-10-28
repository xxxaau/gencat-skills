# Barra de pestanyes (Tab bar)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/5986b7 · Web component: `<tab-bar-horizontal-component>` i `<tab-bar-vertical-component>` (paquet core) · Font actualitzada el 2026-10-07 · Extret el 2026-10-28

## Què és i quan usar-lo
La barra de pestanyes permet navegar entre diferents seccions d'una pàgina de manera fluida, sense recarregar la pàgina ni afectar altres elements que no formin part del cos del contingut.

És un component d'interfície d'usuari que permet navegar entre diferents seccions d'una pàgina de manera dinàmica, sense necessitat de recarregar la pàgina ni afectar altres elements externs al cos del contingut, com els fils d'Ariadna.

Existeixen dos tipus principals de barres de pestanyes:
- **Horitzontal**: agrupació de diferents pestanyes disposades en línia horitzontal. Se situen a dins del cos del contingut i permeten canviar de secció de manera fluida sense alterar altres elements de la pàgina o del mateix cos del contingut.
- **Vertical**: columna lateral amb diferents pestanyes apilades, que ofereix una experiència de navegació estructurada dins d'una mateixa pàgina. Ideal per organitzar pàgines senceres dins de seccions diferenciades sense modificar-ne l'estructura general ni carregar-la de nou, ja que només afecta la informació mostrada dins de la seva àrea de contingut.

### Quan s'utilitza
- Quan és necessari proporcionar una navegació entre seccions sense recarregar tota la pàgina.
- Quan el contingut de cada pestanya està relacionat amb una mateixa àrea temàtica o funcionalitat.
- Quan es vol oferir una navegació ràpida sense interferir amb altres components de la pàgina.

Tant la barra de pestanyes horitzontal com la vertical poden conviure dins d'una mateixa interfície, sempre que les barres horitzontals formin part del contingut i no actuïn com un segon nivell dins de les verticals.

**Barra de pestanyes vertical** (recomanada quan):
- Hi ha **moltes opcions** i/o **textos llargs**.
- Es necessiten **dos nivells de navegació**.
- Es vol **englobar tot el contingut d'una secció** dins d'una mateixa estructura.

**Barra de pestanyes horitzontal** (recomanada quan):
- Hi ha **poques opcions** amb **textos curts**.
- Es vol **mostrar dins del cos del contingut** sense afectar altres elements de la pàgina.

## Quan NO usar-lo / alternatives
- **Navegació principal:** les pestanyes no s'utilitzen per a la navegació principal d'una web, especialment si aquesta és complexa i compta amb diferents nivells de contingut. En aquests casos es considerarà l'ús de menús de navegació horitzontals o verticals, juntament amb els fils d'Ariadna.
- **Continguts no relacionats:** en casos en què els continguts no tinguin cap relació entre ells, es recomana l'ús d'altres elements com botons o enllaços.

Més informació sobre quan no fer ús de les pestanyes a [Pestanyes](component-pestanyes.md).

## Anatomia

### Barra de pestanyes horitzontal

Punt de tall Extra Large - Medium:
1. **Etiqueta:** el text visible que es mostra a la pestanya, indicant el seu contingut o funció.
2. **Indicador de tabulació:** el senyal visual (subratllat) que ressalta la pestanya seleccionada.

Punt de tall Small:
1. **Etiqueta:** el text visible que es mostra a la pestanya, indicant el seu contingut o funció.
2. **Indicador de tabulació:** el senyal visual (línia vertical) que ressalta la pestanya seleccionada.
3. **Desplegable:** el llistat de pestanyes disponibles.

### Barra de pestanyes vertical

Punt de tall Extra-Large:
1. **Etiqueta:** el text visible que es mostra a la pestanya, indicant el seu contingut o funció.
2. **Indicador de tabulació:** el senyal visual (línia vertical) que ressalta la pestanya seleccionada.

Punts de tall Large-Small:
1. **Etiqueta:** indica la pestanya seleccionada en el llistat de pestanyes inferior.
2. **Indicador de tabulació:** el senyal visual (línia vertical) que ressalta la pestanya seleccionada.
3. **Desplegable:** el llistat de pestanyes disponibles.
4. **Xebró**
5. **Scroll** (barra de desplaçament)

## Variants, tipus i estats

### Horitzontals

Punts de tall Extra Large - Medium:

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Show chevron right | True/False | False |
| Show chevron left | True/False | False |

Variants Figma: chevronLeft, chevronRight (components de comportament). Horizontal tab bar [Show Right Icon = False, Show Left Icon = False, Breakpoint = Extra Large - Medium].

Punt de tall Small:

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Collapsed | True / False | True |
| States | Default/Pressed/Focus | Default |

Desplegable: _Horizontal Tabs bar dropdown interaction [Collapsed = True]. Estats: _Horizontal Tabs bar dropdown states [Collapsed = True, State = Default].

### Verticals

Punt de tall Extra Large:

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Container | Slot | Vertical_Tabs |

Variant Figma: Vertical tab bar [Breakpoint = Extra Large].

Punts de tall Large-Small:

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Sticky | True/False | False |
| Collapsed | True/False | False |
| Show Scroll | True/False | False |
| States | Default/Hover/Focus | Default |
| Container | Slot | Vertical_tabs |

Comportament sticky (fix): _Vertical Tabs bar dropdown interaction [Show Scroll = False, Sticky = False, Collapsed = True]. Estats: _Vertical Tabs bar dropdown states [States = Default, _Collapsed = True].

## Comportament i interacció

### General
- Quan l'usuari selecciona una pestanya, el contingut de la pàgina canvia dinàmicament, sense necessitat de recarregar la pàgina ni afectar altres components de la pàgina, com els fils d'Ariadna o la capçalera.
- L'URL de la pàgina s'actualitza automàticament per reflectir la nova secció seleccionada, mantenint una navegació fluida sense interrupcions.

Més informació sobre el comportament de les pestanyes a [Pestanyes](component-pestanyes.md).

### Barra de pestanyes vertical

**Ubicació i comportament.** La barra de pestanyes vertical es manté sticky (fix) a la pantalla mentre l'usuari desplaça el contingut.
- **Extra Large:** la barra es posiciona al lateral esquerre del contingut.
- **Large-Small:** la barra se situa sobre el contingut i n'ocupa exactament la mateixa amplada, ajustant-se al mateix espai o nombre de columnes. Es pot desplegar o replegar segons la interacció de l'usuari.
- Per a construir la versió small cal introduir la variant small del component dins el component [panell emergent (sheet)](component-panell-emergent.md).
- Quan la barra de pestanyes vertical convisqui amb el botó de sortida ràpida, deixarà de tenir comportament fix (sticky) i es desplaçarà amb la resta del contingut.

**Interacció.** En dispositius Large-Small, quan se selecciona una pestanya, la barra es tanca automàticament per permetre més espai al contingut, millorant l'experiència d'usuari en pantalles petites.

**Navegació.** Quan la barra de pestanyes verticals té més de **7 pestanyes (primer o segon nivell)** en punts de tall Large-Small, apareix una barra de desplaçament (scroll) per poder veure totes les opcions disponibles.

### Barra de pestanyes horitzontal
- Per als punts de tall **Medium a Extra-Large**, apareixerà per defecte la barra de pestanyes horitzontal no col·lapsada.
- Si, a mesura que es redueix l'amplada de pantalla, les pestanyes queden tallades, es mostraran uns **xebrons** que permetran la **navegació horitzontal** per la barra i l'accés a totes les pestanyes.
- Per a pantalles de **menys de 480 px d'amplada**, el menú de pestanyes horitzontal es transformarà en un menú desplegable, de manera que només quedarà visible a primer nivell la pestanya seleccionada. Per accedir a la resta de seccions, l'usuari haurà de clicar a la fletxa del desplegable per visualitzar el llistat amb totes les pestanyes disponibles. Aquest llistat apareixerà en format bottom sheet.
- Aquesta barra no té un comportament sticky (fix).
- Per a construir la versió small cal introduir la variant small del component dins el component [panell emergent (sheet)](component-panell-emergent.md).

## Bones pràctiques
- **NO FER:** No afegeixis insígnies a les pestanyes de la barra de pestanyes.

Per a més bones pràctiques relacionades amb l'ús de pestanyes, consulta [Pestanyes](component-pestanyes.md).

## Accessibilitat

### Pautes d'accessibilitat del contingut web (WCAG)
- **Orientació (AA):** el contingut de la pestanya s'adapta a les diferents orientacions de la pantalla, com ara vertical o horitzontal, cosa que permet visualitzar el contingut. [1.3.4 Orientació - CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. [1.4.3 Contrast mínim - CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA):** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [1.4.4 Canvia la mida del text - CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA):** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [1.4.11 Contrast d'elements no textuals - CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A):** tota la funcionalitat del contingut (navegar per les diferents pestanyes) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [2.1.1 Teclat - CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Focus visible (AA):** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [2.4.7 Focus visible - CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- **Gestos d'apuntament (A):** totes les funcionalitats que requereixen gestos de contacte múltiple o amb desplaçament es poden activar amb un apuntament únic i sense gestos amb desplaçament, tret que els gestos de contacte múltiple o amb desplaçament siguin essencials. La versió per mòbil està dissenyada en format desplegable per facilitar aquesta interacció. [2.5.1 Gestos d'apuntament - CAT](https://www.w3.org/Translations/WCAG22-ca/#pointer-gestures) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/pointer-gestures)

### Navegació per teclat

| Tecla | Acció |
|---|---|
| Tabulació | Navega al següent element interactiu de la pàgina |
| Shift+Tabulació | Navega a l'anterior element interactiu de la pàgina |
| Fletxes dreta i esquerra | Navega per la barra de pestanyes horitzontals |
| Fletxes amunt i avall | Navega per la barra de pestanyes verticals |
| Enter | Selecciona un element o desplegar un element |
| Esc | Replega l'element |

En seleccionar un dels nivells amb desplegable el focus es trasllada al primer subnivell.

## Implementació (component web)

### `<tab-bar-horizontal-component>`

Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat (lloc) |
|---|---|---|---|---|---|
| `showContentTab` | `show-content-tab` | Mostra o oculta el contingut de les pestanyes | boolean | `true` | Opcional |
| `tabs` | `tabs` | Definició de les pestanyes del component (array amb el nom de la pestanya i el seu contingut). Accepta array d'objectes o string JSON | string | `undefined` | Obligatori |
| `titleSheetMobile` | `title-sheet-mobile` | Títol del panell emergent que apareix a breakpoints mobile | string | `undefined` | Obligatori |
| `visibilityDividerBpMediumSmall` | `visibility-divider-bp-medium-small` | Visibilitat del divisor entre pestanyes a breakpoints medium-small | boolean | `true` | Opcional |

Nota: el contingut de l'interior de les tabs es pot introduir com a slot per permetre l'addició d'HTML. S'haurà d'introduir l'slot tal com està indicat a l'exemple d'ús. L'atribut `slot` del `div` que contingui l'slot ha de ser `tab-content-X`, sent X l'índex de la tab on es vol que s'introdueixi aquest slot.

**Propietats de l'array `tabs`**

| Propietat | Atribut | Descripció | Tipus | Obligatori |
|---|---|---|---|---|
| `id` | `id` | ID de la tab | String | Opcional |
| `name` | `name` | Nom de la tab | String | Opcional |
| `content` | `content` | Contingut de la tab | String | Opcional |

**Esdeveniments**

| Esdeveniment | Descripció | Tipus / paràmetre | Origen |
|---|---|---|---|
| `keydownButtonMobileEvent` | Es propaga en prémer alguna tecla del teclat en versió mòbil | `CustomEvent<KeyboardEvent>` (`event.detail`) | `tab-bar-horizontal-component` |
| `tabSelected` | Es llança en fer clic en una pestanya, propagant-ne l'índex | `CustomEvent<{ index: number; }>` (índex de la pestanya) | `tab-bar-horizontal-component` |
| `clickTab` | Es propaga en prémer la pestanya | `id`, `isOpen` | `horizontal-tab-component` |
| `keydownEvent` | Es llança cada cop que es fa clic en una opció del menú desplegable | Esdeveniment emès | `vertical-tabs-component` |
| `dropdownTabClick` | Es propaga en seleccionar una subpestanya amb clic o prement Enter | `childIndex` | `vertical-tabs-component` |

**Depèn de:** `horizontal-tab-component` ([Pestanyes](component-pestanyes.md)), `sheet-component` ([Panell emergent](component-panell-emergent.md)), `vertical-tabs-component` ([Pestanyes](component-pestanyes.md)).

**Utilitzat per:** `horizontal-menu-component` ([Menú horitzontal](component-menu-horitzontal.md)).

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<tab-bar-horizontal-component 
  visibility-divider-bp-medium-small="true" 
  show-content-tab="true" 
  title-sheet-mobile="Títol de pàgina"
  tabs='[
        {"id":"id1", "name": "Element 1", "content": ""},
        {"id":"id2", "name": "Element 2", "content": ""},
        {"id":"id3", "name": "Element 3", "content": "Element 3 content goes here."},
        {"id":"id4", "name": "Element 4", "content": "Element 4 content goes here."},
        {"id":"id5", "name": "Element 5", "content": "Element 5 content goes here."}
    ]'>

    <div slot="tab-content-0">
      <button-component 
        class-name-button="btn-primary"
        class-name-icon="" 
        size-button="btn-size-L"
        mode-color-button="mode-color-primary-light" 
        text="Botó" 
        left-icon-chevron="true" 
        right-icon-chevron="false"
        left-icon=false 
        right-icon=false
        text-alternative=""
        is-spinner=false
        custom-id=""
        type-button="button">
      </button-component>
      <br>
      <switch-component
                title-switch="Etiqueta"
                description-switch="Descripció"
                is-disabled="false"
      ></switch-component>
    </div>
  
    <div slot="tab-content-1">
      <link-component 
        text="Enllaç" 
        class-name-icon="bi-box-arrow-up-right" 
        target="_blank" 
        class-name-link="link-small"
        href-link="https://www.google.com" 
        visibility-icon="true">
      </link-component>
      <br>
      <tag-component size="medium" tags='[
        { "type": "readonly", "text": "Text curt" },
        { "type": "dismissible", "text": "Dismissible" },
        { "type": "dismissible", "text": "Etiqueta", "color": "color-alert", "textInfoTooltip": "Dismissible" },
        { "type": "readonly", "text": "Fora de termini", "color": "color-alert" },
        { "type": "readonly", "text": "Error", "color": "color-error" },
        { "type": "readonly", "text": "Atenció", "color": "color-error", "textInfoTooltip": "Error" }
      ]'></tag-component>
    </div>
  </tab-bar-horizontal-component>
```

**Exemple d'instància (PDF)**

```html
<tab-bar-horizontal-component
show-content-tab=true
tabs="texto-ejemplo"
title-sheet-mobile="texto-ejemplo"
visibility-divider-bp-medium-small=true
></tab-bar-horizontal-component>
```

### `<tab-bar-vertical-component>`

Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatori (lloc) |
|---|---|---|---|---|---|
| `buttonText` | `button-text` | Text descriptiu del botó del desplegable | string | `undefined` | Obligatori |
| `numberOfRows` | `number-of-rows` | Nombre de pestanyes a mostrar (files visibles). Opcions: 10, 2, 3, 4, 5, 6, 7, 8, 9 | string | `2` | Obligatori |
| `tabItems` | `tab-items` | Col·lecció d'elements: array amb les propietats de `vertical-tabs-component`, en format JSON, que conté la informació de les pestanyes que es mostraran. Accepta array d'objectes o string JSON | string | `undefined` | Obligatori |
| `titleSheetMobile` | `title-sheet-mobile` | Títol del panell emergent que apareix a breakpoints mobile | string | `undefined` | Obligatori |

**Variants:** `numberOfRows` = `2, 3, 4, 5, 6, 7, 8 , 9, 10` (valor predeterminat `2`).

**Propietats de l'array `tabItems`**

| Propietat | Atribut | Descripció | Tipus | Obligatori |
|---|---|---|---|---|
| `text` | `text` | Text principal de la tab | String | Obligatori |
| `dropdownContent` | `dropdown-content` | Indica els elements que conté a l'interior | String (Array) | Opcional |
| `tabSelected` | `tab-selected` | Indica si la tab està seleccionada | Boolean | Opcional |

**Esdeveniments**

| Esdeveniment | Descripció | Tipus / paràmetre | Origen |
|---|---|---|---|
| `tabClick` | Salta en seleccionar una pestanya (es llança quan l'usuari fa clic al component) | `CustomEvent<{ index: any; }>` (`index`) | `tab-bar-vertical-component` |
| `keydownEvent` | Es llança cada cop que es fa clic en una opció del menú desplegable | Esdeveniment emès | `vertical-tabs-component` |
| `dropdownTabClick` | Es propaga en seleccionar una subpestanya amb clic o prement Enter | `childIndex` | `vertical-tabs-component` |

**Depèn de:** `vertical-tabs-component` ([Pestanyes](component-pestanyes.md)), `sheet-component` ([Panell emergent](component-panell-emergent.md)).

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<tab-bar-vertical-component
      button-text = "Pestanya seleccionada"
      number-of-rows ="8"
      title-sheet-mobile="Títol de pàgina"
      tab-items='[
        {
        "tabSelected": false,
        "iconPrevText": "bi-bar-chart",
        "text": "Pestanya",
        "isDropdown": true,
        "isBadge": false,
        "numberBadge": "",
        "textAlternativeBadge": "",
        "iconState": "complete",
        "tag": [
          {
            "type": "readonly",
            "text": "Opcional",
            "color": "color-white"
          }
        ],
        "dropdownContent": [
          {
            "tabSelected": false,
            "iconPrevText": "bi-bar-chart",
            "text": "Pestanya 1.1",
            "isBadge": true,
            "numberBadge": "",
            "textAlternativeBadge": "",
            "iconState": "complete",
            "tag": [
              {
                "type": "readonly",
                "text": "Opcional",
                "color": "color-white"
              }
            ]
          },
          {
            "tabSelected": false,
            "iconPrevText": "bi-bar-chart",
            "text": "Pestanya 1.2",
            "isBadge": true,
            "numberBadge": "7",
            "textAlternativeBadge": "7",
            "iconState": "complete"
          }
        ]
      }
    ,
        {
          "iconPrevText": "bi-bar-chart",
          "text": "Pestanya 2",
          "isDropdown": true,
          "isBadge": true,
          "tabSelected": false,
          "numberBadge": "",
          "textAlternativeBadge": "",
          "iconState": "complete",
          "tag": [
            { "type": "readonly", "text": "Opcional", "color": "color-white" }
          ]
        },
        {
          "tabSelected": false,
          "iconPrevText": "bi-bar-chart",
          "text": "Pestanya 3",
          "isDropdown": true,
          "isBadge": false,
          "numberBadge": "",
          "textAlternativeBadge": "",
          "iconState": "complete",
          "tag": [
            {
              "type": "readonly",
              "text": "Opcional",
              "color": "color-white"
            }
          ],
          "dropdownContent": [
            {
              "tabSelected": false,
              "iconPrevText": "bi-bar-chart",
              "text": "Pestanya 3.1",
              "isBadge": true,
              "numberBadge": "",
              "textAlternativeBadge": "",
              "iconState": "complete",
              "tag": [
                {
                  "type": "readonly",
                  "text": "Opcional",
                  "color": "color-white"
                }
              ]
            },
            {
              "tabSelected": false,
              "iconPrevText": "bi-bar-chart",
              "text": "Pestanya 3.2",
              "isBadge": true,
              "numberBadge": "7",
              "textAlternativeBadge": "7",
              "iconState": "complete"
            }
          ]
        }
      ,
        {
          "iconPrevText": "bi-bar-chart",
          "text": "Pestanya 4",
          "isDropdown": true,
          "isBadge": true,
          "tabSelected": false,
          "numberBadge": "",
          "textAlternativeBadge": "",
          "iconState": "complete",
          "tag": [
            { "type": "readonly", "text": "Opcional", "color": "color-white" }
          ]
        },
        {
          "iconPrevText": "bi-bar-chart",
          "text": "Pestanya 5",
          "isDropdown": true,
          "isBadge": true,
          "tabSelected": false,
          "numberBadge": "",
          "textAlternativeBadge": "",
          "iconState": "complete",
          "tag": [
            { "type": "readonly", "text": "Opcional", "color": "color-white" }
          ]
        },
        {
          "iconPrevText": "bi-bar-chart",
          "text": "Pestanya 6",
          "isDropdown": true,
          "isBadge": true,
          "tabSelected": false,
          "numberBadge": "",
          "textAlternativeBadge": "",
          "iconState": "complete",
          "tag": [
            { "type": "readonly", "text": "Opcional", "color": "color-white" }
          ]
        }, {
          "iconPrevText": "bi-bar-chart",
          "text": "Pestanya 7",
          "isDropdown": true,
          "isBadge": true,
          "tabSelected": false,
          "numberBadge": "",
          "textAlternativeBadge": "",
          "iconState": "complete",
          "tag": [
            { "type": "readonly", "text": "Opcional", "color": "color-white" }
          ]
        }, {
          "iconPrevText": "bi-bar-chart",
          "text": "Pestanya 8",
          "isDropdown": true,
          "isBadge": true,
          "tabSelected": false,
          "numberBadge": "",
          "textAlternativeBadge": "",
          "iconState": "complete",
          "tag": [
            { "type": "readonly", "text": "Opcional", "color": "color-white" }
          ]
        }, {
          "iconPrevText": "bi-bar-chart",
          "text": "Pestanya 9",
          "isDropdown": true,
          "isBadge": true,
          "tabSelected": false,
          "numberBadge": "",
          "textAlternativeBadge": "",
          "iconState": "complete",
          "tag": [
            { "type": "readonly", "text": "Opcional", "color": "color-white" }
          ]
        }, {
          "iconPrevText": "bi-bar-chart",
          "text": "Pestanya 10",
          "isDropdown": true,
          "isBadge": true,
          "tabSelected": false,
          "numberBadge": "",
          "textAlternativeBadge": "",
          "iconState": "complete",
          "tag": [
            { "type": "readonly", "text": "Opcional", "color": "color-white" }
          ]
        }
      ]'
  ></tab-bar-vertical-component>
```

**Exemple d'instància (PDF)**

```html
<tab-bar-vertical-component
button-text="texto-ejemplo"
number-of-rows='2'
tab-items="texto-ejemplo"
title-sheet-mobile="texto-ejemplo"
></tab-bar-vertical-component>
```

## Claus de text (internacionalització)
Vegeu les [claus](dev-referencia-de-claus-disponibles.md) (`tabBarHorizontal`).

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.4.0 | 11.0.0 | 09 setembre, 2026 | Disseny: es revinculen alguns components a les seves versions més actualitzades que havien quedat obsoletes. |
| 12.2.0 | 11.0.0 | 10 juliol, 2026 | Disseny: s'actualitzen les pestanyes unificades. |
| 12.0.0 | 11.0.0 | 19 juny, 2026 | Desenvolupament: 1. Barra de pestanyes vertical: s'afegeix el component sheet en breakpoints mòbil; s'eliminen les descripcions de vertical-tabs-component; es corregeixen errors en seleccionar pestanyes. 2. Barra de pestanyes horitzontal: s'afegeix el component sheet en breakpoints mòbil. |
| 12.0.0 | 9.3.0 | 29 maig, 2026 | Disseny: es modifiquen les versions per punt de tall small en desplegables perquè s'obrin en panells emergents inferiors. S'ha afegit la funcionalitat de slots als frames que contenen les pestanyes, tant de la barra vertical com de l'horitzontal. |
| 8.2.0 | 9.3.0 | 20 març, 2026 | Desenvolupament: s'elimina padding intern al contingut del component. La línia divisòria entre les pestanyes i el contingut s'allarga fins al final del contingut. |
| 8.2.0 | 9.1.0 | 6 febrer, 2026 | Desenvolupament: adaptacions d'accessibilitat pel que fa a mides de font extra gran i augment de pantalla a la barra de pestanyes vertical. |
| 8.2.0 | 8.0.0 | 14 novembre, 2025 | Desenvolupament: resolució de problemes. |
| 8.2.0 | 6.2.1 | 27 octubre, 2025 | Disseny: s'ha modificat el màxim d'amplada de la barra de pestanyes verticals fixe a 959px. S'ha afegit una instància de text a la barra de pestanyes verticals fixe amb dues variants amb marges esquerres diferents: 32px per punts de tall small - medium; 12px per punts de tall large. S'ha afegit la variable de color de fons al contenidor del desplegable. |
| 7.0.0 | 6.2.1 | 3 octubre, 2025 | Desenvolupament: resolució de problemes. |
| 7.0.0 | 6.1.0 | 12 setembre, 2025 | Desenvolupament: resolució de problemes. |
| 7.0.0 | 6.0.1 | 28 juliol, 2025 | Disseny: ajustament de l'amplada màxima de la pestanya en la versió petita a 895px. Desenvolupament: resolució de problemes. |
| 4.0.0 | 3.0.0 | 2 maig, 2025 | Disseny: s'ajusten els marges de la barra de pestanyes horitzontal per a mobile. |
| 3.0.0 | 3.0.0 | 28 abril, 2025 | Desenvolupament del component. |
| 3.0.0 | No aplica | 31 març, 2025 | Disseny i documentació del component. |

## Vegeu també
- [Acordió](component-acordio.md): per mostrar o amagar informació individualment d'un llistat d'ítems.
- [Menú horitzontal](component-menu-horitzontal.md): per navegar pels elements principals de la pàgina.
- [Pestanyes](component-pestanyes.md): per organitzar contingut relacionat en seccions o categories.
- [Panell emergent](component-panell-emergent.md)
