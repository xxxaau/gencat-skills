# Menú lateral (Side menu)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/211de0 · Web component: `<side-menu-component>` (paquet core) · Font actualitzada el 2026-10-15 · Extret el 2026-10-28

## Què és i quan usar-lo
El menú lateral està format per un conjunt d'enllaços que permet a l'usuari accedir a pàgines o seccions dins d'una web.

El menú lateral i el menú lateral avançat s'utilitzen per presentar opcions de navegació addicionals o complementàries a les de la barra de navegació principal situada a la part superior de la pantalla. Són útils en aquestes situacions:
- Pàgines o aplicacions complexes amb **moltes funcionalitats i/o seccions** que **no es poden agrupar de forma lògica.**
- Situacions d'escalabilitat, on cal personalitzar diferents configuracions o afegir noves seccions sense afectar la navegació principal.

Ambdós menús s'utilitzen com a complement a la navegació superior.

| Menú lateral | Menú lateral avançat |
|---|---|
| Destinat a **entorns de ciutadà**. | Destinat a entorns de **gestió interna**. S'utilitza quan: cal visualitzar l'estat d'una secció (*completat, en procés, urgent, bloquejat*); algunes seccions són opcionals i cal indicar-ho; es vol permetre la reducció del menú lateral mantenint un accés visual mitjançant icones; per a **panells de control**, on cal accedir ràpidament a diverses opcions o funcionalitats sense recarregar la pàgina. |

## Quan NO usar-lo / alternatives
El menú lateral i el menú lateral avançat **no** s'han de fer servir com a **substitut** de la navegació principal.

## Anatomia
Menú lateral i menú lateral avançat: Figma Anatomia (Menú lateral/Frame 1000001502/DOC_Side menu/Anatomia). La font no inclou llista numerada de parts.

## Variants, tipus i estats

### Menú lateral

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Collapsed | True / False | False |
| Show Collapse Button | True / False | True |
| Show Scroll Bar | True / False | False |

Variants Figma: Side menu [Type = Expanded simple]; Side menu [Show Collapse Button = True, Show Scroll Bar = True, Slot, Collapsed = False].

### Menú lateral avançat

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Collapsed | True / False | False |
| Show Icon | True / False | True |
| Show Collapse Button | True / False | True |
| Show Scroll Bar | True / False | False |

Variants Figma: Side menu advanced [Show Collapse button = True, Show scroll bar = False, Slot, Collapsed = False, Show Icon = True].

### Collapse button

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Collapsed | Yes / No | Yes |

Variants Figma: _Side menu_Collpased button [Collapsed = False].

## Mides i espaiats
- Amplada fixa del menú lateral: 312 px.

## Comportament i interacció
Els desplegables tenen tota l'àrea clicable i la interacció és la següent:
1. En seleccionar un **desplegable** es mostra el **contingut del nivell alhora que es mostren els subnivells** al menú. Si l'element pare no té contingut, es mostra com una distribuïdora.
2. Si l'usuari és en un **segon nivell** i **selecciona el primer** (pare), **es mostra el contingut del pare** i es tanca el desplegable.
3. Si és en un **segon nivell** i **selecciona el primer nivell d'un desplegable diferent** que està **col·lapsat**, es mostra el contingut i els subnivells.
4. **Si ja estava desplegat**, **mostra la informació, però tanca el desplegable**. Un cop ha seleccionat l'element pare i el torna a seleccionar, es desplega el menú.

Altres regles:
- Si el text de l'etiqueta ocupa més espai del disponible, es produeix un salt de línia; si encara així se sobrepassa, l'espai es trunca amb el text.
- L'scroll del menú lateral és independent del desplaçament de la pàgina per evitar espais en blanc innecessaris.
- Adaptació responsiva: amplada fixa de 312 px. Actualment no hi ha versió per a mòbil.

### Prototipat (Figma)
Per prototipar diferents pàgines amb el menú lateral:
- Per enllaçar una pestanya del menú amb una pàgina nova, utilitza el *frame* (marc) superior del component. Si n'utilitzes un d'inferior tindràs problemes en la interacció dels estats.
- El component està prototipat de manera que es pot col·lapsar clicant al botó de col·lapse. Si hi ha problemes amb les pestanyes desplegables (queden visibles quan es col·lapsa el menú), es pot desactivar la interacció per clic i muntar el prototip en dues pàgines diferents.
- Figma: Prototipat (Menú lateral/Frame 1000001502/DOC_Side menu/Disseny/Prototipat).

## Bones pràctiques

Tots dos menús:
- Posició — **FER:** col·loca el menú a la part esquerra de la pantalla.
- Posició — **NO FER:** no col·loquis el menú a la part dreta de la pantalla.
- Jerarquia — **NO FER:** no utilitzis més de dos nivells. Es poden organitzar amb desplegables.
- Duplicat — **NO FER:** no dupliquis la informació del menú superior.

Menú lateral:
- Icones — **NO FER:** no amaguis la navegació lateral darrere d'icones.

Menú lateral avançat:
- Icones — **FER:** permet amagar i mostrar el menú lateral mitjançant una icona quan sigui necessari.

## Accessibilitat

### Pautes d'accessibilitat del contingut web (WCAG)
- **Orientació (AA) — 1.3.4:** el contingut de l'àrea de text s'adapta a les diferents orientacions de la pantalla, com ara vertical o horitzontal, cosa que permet visualitzar el contingut. [CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Contrast mínim (AA) — 1.4.3:** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA) — 1.4.4:** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA) — 1.4.11:** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A) — 2.1.1:** tota la funcionalitat del contingut (navegar pels diferents botons) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Focus visible (AA) — 2.4.7:** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- **Focus no ocult (AA) — 2.4.11:** en tancar-se el menú, el focus ha de tornar a l'element que el va activar. El menú no pot ocultar cap element que tingui el focus de teclat. Aquesta consideració és especialment rellevant en dispositius mòbils i tauletes amb zoom de pantalla activat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-not-obscured-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-not-obscured-minimum)

### Navegació per teclat
La navegació per teclat es realitza inicialment amb la tecla de tabulació. Un cop l'usuari se situa en el primer element del menú lateral, la navegació es comporta així:

| Tecla | Acció |
|---|---|
| Tabulació | Navegar al següent element interactiu de la pàgina. |
| Shift + Tabulació | Navegar a l'anterior element interactiu de la pàgina. |
| Fletxa avall | Següent element de la llista de pestanyes (situat inferiorment) |
| Fletxa amunt | Anterior element de la llista de pestanyes (situat superiorment) |
| Intro / Enter | Activa l'element seleccionat. |

## Implementació (component web)

### `<side-menu-component>`
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatori (lloc) |
|---|---|---|---|---|---|
| `iconPrevTextGlobal` | `icon-prev-text-global` | Mostrar o ocultar la icona prèvia al text de la tab | `boolean` | `undefined` | Obligatori |
| `iconState` | `icon-state` | Mostrar o amagar la icona d'estat dels tabs | `boolean` | `undefined` | Obligatori |
| `initialStateCollapsed` | `initial-state-collapsed` | Estat inicial del menú: col·lapsat o no col·lapsat | `boolean` | `false` | Opcional |
| `showCollapseButton` | `show-collapse-button` | Mostrar o ocultar el botó de col·lapsat | `boolean` | `undefined` | Obligatori |
| `sideMenuItems` | `side-menu-items` | Elements del menú lateral, que corresponen amb la propietat `tabItems` de les vertical tabs. Accepta array d'objectes (`SideMenuItem[]`) o string JSON | `SideMenuItem[] \| string` | - | Obligatori |
| `sizeFontTab` | `size-font-tab` | Grandària de la font de les tabs. Opcions: `medium`, `small` | `string` | `undefined` | Obligatori |
| `textTooltipCollapseButton` | `text-tooltip-collapse-button` | Text del tooltip que es mostra en passar el cursor (hover) sobre el botó de tancar el menú lateral | `string` | `Col·lapseu menu` | Opcional |

**Props que accepten JSON: `sideMenuItems`** (array d'objectes o string JSON; estructura `SideMenuItem` segons el PDF).

| Clau | Tipus | Requerida |
|---|---|---|
| `id` | string | Sí |
| `tabSelected` | boolean | Sí |
| `iconPrevText` | string | Sí |
| `text` | string | Sí |
| `description` | string | Sí |
| `isDropdown` | boolean | Sí |
| `isBadge` | boolean | Sí |
| `numberBadge` | string | Sí |
| `textAlternativeBadge` | string | Sí |
| `iconState` | `'complete'`, `'urgent'` (i la resta de valors de la variant, vegeu avall) | Sí |
| `tag` | `string` o `{ type: string, ... }` (el PDF queda truncat) | (no indicat) |

La font del lloc descriu l'estructura amb un objecte contenidor: cada element de `sideMenuItems` és `{ "tabItem": { ... } }`.

**Propietats de l'array `sideMenuItems`** (lloc)

| Propietat | Descripció | Atribut | Obligatorietat | Tipus |
|---|---|---|---|---|
| `tabItem` | Configuració d'una pestanya del menú lateral | `tabItem` | Obligatori | String (array) |

**Propietats de `tabItem`** (el lloc les presenta com a segon bloc "Propietats de l'array `sideMenuItems`")

| Propietat | Descripció | Atribut | Obligatorietat | Tipus |
|---|---|---|---|---|
| `description` | Text descriptiu addicional | `description` | Obligatori | String |
| `dropdownContent` | Llistat de subpestanyes quan la pestanya és desplegable | `dropdownContent` | Opcional | String (array) |
| `iconPrevText` | Icona de Bootstrap que es mostra abans del text de la pestanya | `iconPrevText` | Opcional | String |
| `iconState` | Estat de la pestanya | `iconState` | Obligatori | String |
| `id` | Identificador únic de la pestanya | `id` | Obligatori | String |
| `isBadge` | Indica si es mostra o no el badge | `isBadge` | Opcional | Boolean |
| `isDropdown` | Indica si la pestanya conté una llista de subpestanyes desplegable | `isDropdown` | Opcional | Boolean |
| `numberBadge` | Valor numèric mostrat al badge | `numberBadge` | Opcional | String |
| `tabSelected` | Indica si la pestanya apareix inicialment seleccionada. Només hi pot haver una pestanya o subpestanya seleccionada alhora | `tabSelected` | Opcional | Boolean |
| `tag` | Llistat d'etiquetes informatives que es mostren al costat del contingut de la pestanya | `tag` | Opcional | String (JSON) |
| `text` | Text principal de la pestanya | `text` | Obligatori | String |
| `textAlternativeBadge` | Text alternatiu utilitzat per millorar l'accessibilitat del badge | `textAlternativeBadge` | Opcional | String |

**Propietats de l'array `dropdownContent`**

| Propietat | Descripció | Atribut | Obligatorietat | Tipus |
|---|---|---|---|---|
| `description` | Text descriptiu addicional | `description` | Obligatori | String |
| `iconPrevText` | Icona de Bootstrap que es mostra abans del text de la pestanya | `iconPrevText` | Opcional | String |
| `iconState` | Estat de la pestanya | `iconState` | Obligatori | String |
| `id` | Identificador únic de la pestanya | `id` | Obligatori | String |
| `isBadge` | Indica si es mostra o no el badge | `isBadge` | Opcional | Boolean |
| `numberBadge` | Valor numèric mostrat al badge | `numberBadge` | Opcional | String |
| `tabSelected` | Indica si la pestanya apareix inicialment seleccionada. Només hi pot haver una pestanya o subpestanya seleccionada alhora | `tabSelected` | Opcional | Boolean |
| `text` | Text principal de la pestanya | `text` | Obligatori | String |
| `textAlternativeBadge` | Text alternatiu utilitzat per millorar l'accessibilitat del badge | `textAlternativeBadge` | Opcional | String |

**Variants**

| Propietat | Valors | Per defecte |
|---|---|---|
| `iconState` | `block`, `complete`, `inProgress`, `urgent` | - |
| `initialStateCollapsed` | `true`, `false` | `false` |
| `sizeFontTab` | `medium`, `small` | - |
| `textTooltipCollapseButton` | - | Col·lapseu menu |

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `blurButton` | Es llança cada cop que es treu el focus d'un botó | - | `button-component` |
| `focusButton` | Es llança cada cop que es fa focus en un botó | - | `button-component` |
| `handlerClick` | Es llança cada cop que es fa clic en un botó; com a paràmetre conté les dades de l'esdeveniment | `id` | `button-component` |
| `tabClick` | Es propaga en seleccionar una pestanya o subpestanya | `id` | `side-menu-component` |
| `dropdownTabClick` | Es propaga en seleccionar una subpestanya amb clic o prement Enter | `childIndex` | `vertical-tabs-component` |
| `keydownEvent` | Es llança cada cop que es fa clic en una opció del menú desplegable | Esdeveniment emès | `vertical-tabs-component` |

[discrepància: el lloc documenta els esdeveniments anteriors; el PDF v12.0.0 diu "Sin eventos declarados" per a `side-menu-component`]

**Depèn de:** [`button-component`](component-botons.md), [`vertical-tabs-component`](component-pestanyes.md).

**Exemple d'ús**

```html
<!-- /index.html -->
<side-menu-component 
  side-menu-items='[
    {
      "tabItem": {
        "id": "tab1",
        "tabSelected": false,
        "iconPrevText": "bi-bar-chart",
        "text": "Pestanya",
        "description":"Lorem Ipsum is simply dummy",
        "isDropdown": false,
        "isBadge": true,
        "numberBadge": "5",
        "textAlternativeBadge": "5",
        "iconState": "complete"
      }
    },
    {
      "tabItem": {
        "id": "tab2",
        "tabSelected": true,
        "iconPrevText": "bi-bar-chart",
        "text": "Pestanya",
        "description":"Lorem",
        "isDropdown": true,
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
        ],
        "dropdownContent": [
          {
            "id": "tab2-1",
            "tabSelected": false,
            "iconPrevText": "bi-bar-chart",
            "text": "Pestanya",
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
            "id": "tab2-2",
            "tabSelected": false,
            "iconPrevText": "bi-bar-chart",
            "text": "Pestanya",
            "isBadge": true,
            "numberBadge": "7",
            "textAlternativeBadge": "7",
            "iconState": "complete"
          }
        ]
      }
    },
    {
      "tabItem": {
        "id": "tab3",
        "tabSelected": false,
        "iconPrevText": "bi-bar-chart",
        "text": "Pestanya",
        "description":"Lorem Ipsum",
        "isDropdown": false,
        "isBadge": false,
        "numberBadge": "12",
        "textAlternativeBadge": "12",
        "iconState": "inProgress"
      }
    },
    {
      "tabItem": {
        "id": "tab4",
        "tabSelected": false,
        "iconPrevText": "bi-bar-chart",
        "text": "Pestanya",
        "isDropdown": false,
        "isBadge": false,
        "numberBadge": "12",
        "textAlternativeBadge": "12",
        "iconState": "urgent"
      }
    },
    {
      "tabItem": {
        "id": "tab5",
        "tabSelected": false,
        "iconPrevText": "bi-bar-chart",
        "text": "Pestanya",
        "isDropdown": true,
        "isBadge": true,
        "numberBadge": "",
        "textAlternativeBadge": "",
        "iconState": "block",
        "dropdownContent": [
          {
            "id": "tab5-1",
            "tabSelected": false,
            "text": "Pestanya",
            "isBadge": false,
            "numberBadge": "",
            "textAlternativeBadge": "",
            "iconState": "complete"
          },
          {
            "id": "tab5-2",
            "tabSelected": false,
            "text": "Pestanya",
            "description":"Lorem Ipsum is simply dummy",
            "isBadge": false,
            "numberBadge": "",
            "textAlternativeBadge": "7",
            "iconState": "complete"
          }
        ]
      }
    },
    {
      "tabItem": {
        "id": "tab6",
        "tabSelected": false,
        "iconPrevText": "bi-bar-chart",
        "text": "Pestanya",
        "isDropdown": false,
        "isBadge": true,
        "numberBadge": "12",
        "textAlternativeBadge": "12",
        "iconState": "complete"
      }
    },
    {
      "tabItem": {
        "id": "tab7",
        "tabSelected": false,
        "iconPrevText": "bi-bar-chart",
        "text": "Pestanya",
        "description":"Lorem Ipsum is simply dummy text of the printing",
        "isDropdown": false,
        "isBadge": false,
        "numberBadge": "",
        "textAlternativeBadge": "",
        "iconState": "inProgress"
      }
    },
    {
      "tabItem": {
        "id": "tab8",
        "tabSelected": false,
        "iconPrevText": "bi-bar-chart",
        "text": "Pestanya",
        "isDropdown": false,
        "isBadge": false,
        "numberBadge": "",
        "textAlternativeBadge": "",
        "iconState": "urgent"
      }
    }
  ]
  ' 
  size-font-tab="small" 
  icon-prev-text-global="true" 
  icon-state="true" 
  show-collapse-button="true"
  text-tooltip-collapse-button="Col·lapseu menu" 
  initial-state-collapsed="true"
>
</side-menu-component>
```

Exemple d'instància (PDF):

```html
<side-menu-component
icon-prev-text-global=false
icon-state=false
initial-state-collapsed=false
show-collapse-button=false
side-menu-items="texto-ejemplo"
size-font-tab="medium"
text-tooltip-collapse-button='Col·lapseu menu'
></side-menu-component>
```

Exemple amb props JSON (PDF):

```html
<side-menu-component
side-menu-items='[{"id":"texto-ejemplo","tabSelected":true,"iconPrevText":"texto-ejemplo","text":"texto-ejemplo","description":"texto-ejemplo","isDropdown":true,"isBadge":true,"numberBadge":"texto-ejemplo","textAlternativeBadge":"texto-ejemplo","iconState":"complete","tag":"value"}]'
></side-menu-component>
```

[discrepància: l'exemple del lloc embolcalla cada element en `{"tabItem": {...}}`; l'exemple JSON del PDF usa objectes plans sense `tabItem`]

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.2.0 | 11.0.0 | 10 juliol, 2026 | Disseny: s'actualitzen les pestanyes unificades. |
| 2.4.0 | 11.0.0 | 19 juny, 2026 | Desenvolupament: millores d'accessibilitat amb el lector de pantalla |
| 2.4.0 | 7.0.0 | 24 octubre, 2025 | Desenvolupament: resolució de problemes |
| 2.4.0 | 6.2.1 | 3 octubre, 2025 | Desenvolupament: resolució de problemes. |
| 2.4.0 | 6.1.0 | 12 setembre, 2025 | Desenvolupament: nova propietat afegida |
| 2.4.0 | 2.1.0 | 31 març, 2025 | Desenvolupament de l'evolutiu |
| 2.4.0 | 2.0.0 | 10 març, 2025 | Disseny (evolutiu): disseny del menú lateral avançat. |
| 2.3.0 | 1.0.0 | 31 gener, 2025 | Sense canvis |
| 2.2.0 | 0.1,1 | 20 gener, 2025 | Disseny: s'han unificat les pestanyes i actualitzat al component combinat del menú lateral. |
| 2.1.0 | 0.1.1 | 04 desembre, 2024 | Disseny: s'ajusten espaiats i jerarquia |
| 1.1.0 | 0.1.0 | 22 novembre, 2024 | Desenvolupament del component |
| 1.1.0 | 0.0.4 | 19 novembre, 2024 | Disseny i documentació del component |

## Vegeu també
- [Acordió](component-acordio.md): per mostrar o amagar informació individualment d'un llistat d'ítems.
- [Pestanyes](component-pestanyes.md): per organitzar contingut relacionat en seccions o categories.
- [Menú horitzontal](component-menu-horitzontal.md): per navegar pels elements principals de la pàgina.
- Suport: https://zeroheight.com/38669693e/p/57c57a-suport-i-contacte · https://zeroheight.com/38669693e/p/72240b-preguntes-frequents · https://zeroheight.com/38669693e/p/690b45 · https://zeroheight.com/38669693e/p/342611
