# Pestanyes (Tabs)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/40de43 · Web component: `<horizontal-tab-component>` i `<vertical-tabs-component>` (paquet core) · Font actualitzada el 2026-10-22 · Extret el 2026-10-28

## Què és i quan usar-lo
Element de navegació per organitzar contingut relacionat en seccions o categories dins d'una única àrea de visualització.

Les pestanyes s'utilitzen per organitzar contingut relacionat i jeràrquicament equivalent de manera estructurada i fàcilment navegable. El seu ús permet a l'usuari accedir a continguts relacionats sense sortir del context de la pantalla, ajudant a reduir la càrrega cognitiva.

Hi ha tres tipologies de pestanyes: **horitzontals, verticals i verticals avançades.**

Quan s'utilitza:
- **Categorització i ordenació d'ítems:** per representar els criteris de categorització o filtratge més rellevants per a l'usuari, com poden ser els ítems més populars o les últimes novetats.
- **Panells de control:** les pestanyes poden ser usades per canviar entre diferents panells o tipus de dades.
- **Configuració i preferències:** també es pot fer servir per agrupar opcions relacionades entre diferents categories.

Per tipologia:
- **Pestanyes horitzontals:** per a barres de pestanyes que s'utilitzen dins del contingut d'una pàgina.
- **Pestanyes verticals:** per a construir diferents menús, com el lateral o el desplegable del menú horitzontal.
- **Pestanyes verticals avançades:** específiques per a aplicacions internes.

## Quan NO usar-lo / alternatives
- **Navegació principal:** les pestanyes no s'utilitzen per a la navegació principal d'una web, especialment si aquesta és complexa i compta amb diferents nivells de contingut. En aquests casos es considerarà l'ús de menús de navegació horitzontals o verticals, juntament amb els fils d'Ariadna.
- **Continguts no relacionats:** si els continguts no tenen cap relació entre ells, es recomana l'ús d'altres elements com els botons o els enllaços a la barra de navegació per accedir-hi de manera individual.
- **Indicadors de progrés:** per a indicar el progrés en un procés o un conjunt d'accions dividides en etapes, s'usarà un *pas a pas* en lloc de pestanyes.
- **Contingut seqüencial:** si el contingut és seqüencial i ha de ser llegit en un ordre particular, es jerarquitzarà el contingut amb tècniques com diferents estils tipogràfics o l'espaiat; en cap cas s'usaran pestanyes per a la lectura d'un text continuat.
- **Comparació de continguts:** si l'usuari necessita comparar informació, no es farà ús de pestanyes, ja que s'augmentaria la càrrega cognitiva i el cost d'interacció.
- **Funcionalitats rellevants ocultes:** evita amagar contingut o funcionalitats importants darrere de pestanyes sense una indicació clara. L'usuari ha de poder accedir fàcilment a tota la informació rellevant sense haver de navegar per múltiples pestanyes.

Barra de pestanyes versus menú horitzontal o lateral: tot i que els dos patrons utilitzen pestanyes, hi ha una diferència important en el comportament. En una barra de pestanyes col·locada dins del contingut, quan l'usuari canvia de pestanya aquella secció mostra una vista diferent. En canvi, en un menú de navegació horitzontal o lateral, quan l'usuari canvia de pestanya navega a una pàgina diferent.

## Anatomia

### Pestanyes horitzontals
1. **Etiqueta:** el text visible que es mostra a la pestanya, indicant el seu contingut o funció.
2. **Indicador de tabulació:** el senyal visual (subratllat) que ressalta la pestanya seleccionada.
3. **Xebró.**

### Pestanyes verticals
Figma: Anatomia_pestanya avançada.

## Variants, tipus i estats

### Pestanyes verticals
Propietat `Type`:

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Type | Tab / Dropdown-folded / Dropdown-unfolded / Dropdown-horizontal | Tab |

Aquestes pestanyes tenen les **interaccions i estats niats (nested instances).**

#### Tab

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Size | Medium / Small | Medium |
| State | Default / Hover / Pressed / Selected / Focus | Default |
| Show Badge | True / False | True |
| Show State icon | True / False | True |
| Change icon | Icon | - |
| Show Divider | True / False | True |
| Level | First / Second | First |
| Show description | True / False | - |

(La font repeteix la fila "Show State Icon = True / False, per defecte True".)

Variants Figma — Mida: Pestanyes verticals [Show Divider = True, Show Badge = True, Size = Medium, State = Default]. Estats: Vertical_Tabs [Badge = True, Divider = True, Size = Medium, Type = Tab, States = Default, Chevron = None, Collapse = None].

#### Dropdown-folded i dropdown-unfolded

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Size | Medium / Small | Medium |
| State | Default / Hover / Pressed / Focus / Selected / Selected-focus | Default |
| Show Divider | True / False | True |
| Show Badge | True / False | True |
| Level | First / Second | First |

Variants Figma (mida i estat): Pestanyes verticals [Show Divider = True, Show Badge = True, Size = Medium, State = Default].

#### Dropdown-horizontal

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Size | Medium / Small | Medium |
| State | Default / Hover / Pressed / Focus / Selected | Default |
| Show Divider | True / False | True |
| Show Badge | True / False | True |
| Level | First / Second | First |

Variants Figma (mida i estats): _Vertical_Tabs_Default [Show State Icon = False, Show Divider = True, Show Opcional Tag = False, Size = Medium, State = Default].

#### Dropdown-unfolded i dropdown-folded (versió avançada)

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Size | Medium / Small | Medium |
| State | Default / Hover / Pressed / Selected / Focus / Selected-focus | Default |
| Show badge | True / False | True |
| Show state icon | True / False | True |
| Change icon | Icon | - |
| Show Divider | True / False | True |
| Level | First / Second | First |

Variants Figma (mida i estat): _Vertical_Tabs_Dropdown_Collapsed [Show Divider = True, Show Opcional Tag = False, Show State Icon = False, Size = Medium, State = Default].

#### Dropdown-horizontal (versió avançada)

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Size | Medium / Small | Medium |
| State | Default / Hover / Pressed / Selected / Focus | Default |
| Show badge | True / False | True |
| Show state Icon | True / False | True |
| Change state icon | Icona | - |
| Show Divider | True / False | True |
| Level | First / Second | First |

Variants Figma (mida i estat): _Vertical_Tabs_Dropdown_Horizontal [Show Divider = True, Show Opcional Tag = False, Show State Icon = False, Size = Medium, State = Default].

#### Icon

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Default / Hover / Pressed / Selected / Focus | Default |
| Divider | True / False | True |

Variants Figma (estat): _Vertical_Tabs_Icon [Show Divider = True, State = Default].

#### State icon
Les pestanyes avançades disposen d'icones per indicar l'estat. Variants Figma: _State Icon [Icon state = Complete, State = Default]. Textos d'estat que mostra la font: "En procés d'edició." i "Cal completar passos anteriors perquè estigui disponible."

### Pestanyes horitzontals
Organitzen el contingut de forma horitzontal, dissenyades per a la barra de pestanyes i el menú de navegació horitzontal. Estan pensades per a *desktop* (escriptori).

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Default / Hover / Pressed / Focus / Selected | Default |

Variants Figma (estats): _Tabs_desktop [Content = Pestanya, State = Default].

## Comportament i interacció

### General
- Sempre hi ha d'haver una de les pestanyes preseleccionades; no pot haver-hi una situació en què les pestanyes es mostrin però no se'n seleccioni cap prèviament, perquè els usuaris se sentirien perduts. Per defecte, estarà preseleccionada la primera.
- Les pestanyes són mútuament excloents: només es pot seleccionar una pestanya a la vegada.

### Pestanyes verticals
Interacció:
- Tota la pestanya és clicable i només hi ha una interacció amb aquesta acció.
- La icona d'estat disposa d'un estat *hover* (en passar amb el ratolí) per mostrar el text de l'estat. Figma: Comportament_icona estat.

Jerarquia:
- El primer nivell (propietat *Level: First*) tindrà la tipografia en **semibold** per defecte per destacar-lo.
- Aquest primer nivell pot estar format per **pestanyes horitzontals** (com el cas del menú horitzontal per a escriptori) **o verticals**, que es mostrarien en *semibold*.
- Els nivells inferiors (propietat *Level: Second*) utilitzaran una tipografia en **regular**, però si alguna pestanya dels nivells inferiors està seleccionada (*selected*), també es mostrarà en *semibold* per ressaltar-ne la importància. Això ajuda a establir una jerarquia visual clara i enfocada.
- Aquesta jerarquia es pot modificar des del panell de propietats. Figma: ComportamentJerarquia.

Adaptació responsiva (escriptori):
- L'amplada del contenidor de la pestanya és fixa a 312 px.
- Si les pestanyes no es poden mostrar en l'espai disponible de pantalla, s'afegirà un *scroll* (barra de navegació) vertical.
- **Avançades:** el text de les pestanyes salta de línia. Quan es produeix aquest salt, la insígnia es queda fixada a la part superior dreta de la pestanya. Figma: Comportament_line text.

Adaptació a mòbil:
- Les pestanyes verticals en la versió per a mòbil (punt de tall *small*) es mostren amb un desplegable.
- Quan l'usuari selecciona aquest desplegable, les opcions es mostren dins d'un [panell emergent](component-panell-emergent.md) inferior i el títol d'aquest correspon al títol de secció o pàgina.
- Figma: Anatomiaverticals_adaptacioplegat, Anatomiaverticals_adaptaciodesplegat.

### Pestanyes horitzontals
Interacció:
- Els usuaris poden seleccionar una pestanya fent-hi clic. Quan se selecciona una pestanya, es mostra el seu contingut associat, mentre que el contingut associat a les altres pestanyes s'oculta.

Adaptació responsiva:
- L'ample del contenidor de la pestanya s'adapta a l'extensió del seu contingut.
- **Escriptori:** si el total de pestanyes ocupa més que l'espai disponible, aquestes queden amagades en un *slider* (control lliscant) horitzontal. En els extrems on el contingut quedi amagat (dret i/o esquerre) apareixen uns xebrons que permeten a l'usuari desplaçar-se horitzontalment per accedir a les pestanyes amagades. Figma: Comportament_responsive_desktop.

Adaptació a mòbil:
- Les pestanyes horitzontals en la versió per a mòbil (punt de tall *small*) es mostren amb un desplegable.
- Quan l'usuari selecciona aquest desplegable, les opcions es mostren dins d'un [panell emergent](component-panell-emergent.md) inferior i el títol d'aquest correspon al títol de secció o pàgina.
- Figma: Anatomiahoritzontals_adaptacioplegat, Anatomiahoritzontals_adaptaciodesplegat.

### Altres consideracions
- **Actualització d'URL:** seleccionar una pestanya actualitzarà l'URL a la barra d'adreces del navegador per reflectir l'estat actual de la interfície. Això permet als usuaris compartir adreces d'interès a pestanyes específiques.
- **Persistència (opcional):** en algunes implementacions, la pestanya seleccionada pot persistir entre càrregues de pàgina o sessions. Si un usuari selecciona una pestanya i després navega fora de la pàgina o la torna a carregar, la pestanya seleccionada roman activa, proporcionant continuïtat en l'experiència d'usuari.

## Bones pràctiques

### General
Etiquetes clares i curtes:
- **FER:** fes ús d'etiquetes concises i significatives que siguin fàcilment comprensibles per als usuaris. L'extensió dels noms no hauria de superar els vint-i-cinc o trenta caràcters.
- **NO FER:** no facis ús d'etiquetes ambigües que puguin confondre l'usuari sobre el propòsit de la pestanya.

Organització de continguts:
- **FER:** utilitza les pestanyes per agrupar continguts relacionats entre si i que tenen un nivell de jerarquia similar.
- **NO FER:** no utilitzis les pestanyes per organitzar contingut que no està relacionat entre si ni és jeràrquicament equivalent.
- **NO FER:** no utilitzis pestanyes niades dins d'altres pestanyes. Treballar amb subnivells dificulta el seguiment de relacions entre continguts.

### Horitzontals
Nombre limitat de pestanyes:
- **FER:** limita el nombre de pestanyes a una quantitat manejable, d'un màxim de cinc o set pestanyes, evitant així la sobrecàrrega cognitiva.
- **NO FER:** evita l'ús de moltes pestanyes en una sola pantalla. En cas de treballar amb una gran quantitat d'informació, es pot recórrer a altres tècniques d'organització com la paginació, l'ús d'un índex, filtres o un cercador.

### Verticals
Jerarquia:
- **FER:** utilitza el primer nivell de jerarquia per a les pestanyes verticals principals.

## Accessibilitat

### Pautes d'accessibilitat del contingut web (WCAG)
- **Informació i relacions (A) — 1.3.1:** la informació, l'estructura i les relacions que es transmeten mitjançant la presentació es poden determinar mitjançant programació o estan disponibles en text. És essencial proporcionar una etiqueta clara i descriptiva per a cada pestanya. Les etiquetes de les pestanyes han d'estar associades correctament amb els seus elements utilitzant un marcatge HTML adequat. [CAT](https://www.w3.org/WAI/WCAG22/Understanding/info-and-relationships) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/info-and-relationships)
- **Orientació (AA) — 1.3.4:** el contingut de les pestanyes s'adapta a les diferents orientacions de la pantalla, com ara vertical o horitzontal, i permet visualitzar el contingut. [CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Ús del color (A) — 1.4.1:** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per indicar els diferents canvis d'estat es modifiquen els píxels de la vora del component i/o s'afegeixen elements complementaris, com la segona vora pel focus, o la icona i el text d'error. [CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA) — 1.4.3:** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA) — 1.4.4:** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA) — 1.4.11:** els elements gràfics com icones (error i indicador de funció) i vores presenten un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Espaiat del text (AA) — 1.4.12:** quan es desenvolupa contingut amb llenguatges de marcatge que permeten aplicar propietats d'estil de text, no es perd cap contingut ni funcionalitat si s'ajusten aquestes propietats: alçada de línia (interlineat) d'almenys 1,5 vegades la mida de la lletra; espaiat entre els paràgrafs d'almenys dues vegades la mida de la lletra; espaiat entre lletres (*tracking*) d'almenys 0,12 vegades la mida de la lletra; espaiat entre paraules d'almenys 0,16 vegades la mida de la lletra. [CAT](https://www.w3.org/Translations/WCAG22-ca/#text-spacing) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/text-spacing)
- **Teclat (A) — 2.1.1:** tota la funcionalitat del contingut (navegar per les pestanyes i seleccionar-les) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Ordre del focus (A) — 2.4.3:** les pestanyes s'han de presentar en un ordre lògic per facilitar la navegació per teclat o altres dispositius d'entrada. L'ordre ha de seguir el flux de la informació o les tasques que es presenten. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-order) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-order)
- **Focus visible (AA) — 2.4.7:** la navegació al camp de l'àrea de text és visible mitjançant un rectangle extern. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

### Navegació per teclat

| Tecla | Acció |
|---|---|
| Tabulador | Accedir a la primera pestanya i al següent element interactiu dins d'una pestanya o al següent element interactiu de la pàgina. |
| Shift + Tabulador | Navegar a l'element anterior. |
| Fletxes dreta i esquerra | Navegar entre les diferents pestanyes. |
| Enter | Seleccionar una pestanya. |

Patró ARIA: https://www.w3.org/WAI/ARIA/apg/patterns/tabs/

## Implementació (component web)

### `<horizontal-tab-component>`
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat (lloc) |
|---|---|---|---|---|---|
| `active` | `active` | Indica si la pestanya està activa o no | `boolean` | `undefined` | Opcional |
| `idHorizontalTab` | `id-horizontal-tab` | Identificador únic (identificador de la pestanya horitzontal) | `string` | `undefined` | Obligatori |
| `isDropdown` | `is-dropdown` | Indica si la pestanya tindrà icona dropdown | `boolean` | `false` | Opcional |
| `isOpen` | `is-open` | Indica si la pestanya és oberta o tancada | `boolean` | `false` | Opcional |
| `text` | `text` | Text que contindrà la pestanya (text principal visible del component) | `string` | `undefined` | Obligatori |

**Esdeveniments**

| Esdeveniment | Descripció | Tipus / paràmetre | Origen |
|---|---|---|---|
| `clickTab` | Es propaga en prémer la pestanya (l'usuari hi fa clic) | `CustomEvent<{ id: string; isOpen?: boolean; }>` (paràmetres `id`, `isOpen`) | `horizontal-tab-component` |

**Utilitzat per:** [`horizontal-menu-component`](component-menu-horitzontal.md), [`tab-bar-horizontal-component`](component-barra-de-pestanyes.md).

**Exemple d'ús**

```html
<!-- /index.html -->
<horizontal-tab-component 
  id-horizontal-tab="id-tab-1" 
  text="Tab 1" 
  active="true" 
  is-dropdown="true"
  is-open="false"
></horizontal-tab-component>
```

Exemple d'instància (PDF):

```html
<horizontal-tab-component
active=false
id-horizontal-tab="texto-ejemplo"
is-dropdown=false
is-open=false
text="texto-ejemplo"
></horizontal-tab-component>
```

### `<vertical-tabs-component>`
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat (lloc) |
|---|---|---|---|---|---|
| `activeHorizontalMenu` | `active-horizontal-menu` | Indica si el menú horitzontal associat està actiu | `boolean` | `false` | Opcional |
| `dropdownItemsHorizontalMenu` | `dropdown-items-horizontal-menu` | Indica si existeixen elements desplegables en el menú horitzontal | `boolean` | `false` | Opcional |
| `iconPrevTextGlobal` | `icon-prev-text-global` | Les tabs sempre formaran part d'un component on es replicaran. Aquesta propietat controla globalment la visibilitat de totes les icones prèvies al text de les tabs que formen part d'aquest component | `boolean` | `undefined` | Obligatori |
| `iconStateGlobal` | `icon-state-global` | Les tabs sempre formaran part d'un component on es replicaran. Aquesta propietat controla globalment la visibilitat de totes les icones d'estat de les tabs que formen part d'aquest component | `boolean` | `undefined` | Obligatori |
| `idTab` | `id-tab` | Identificador de la pestanya (tab) | `string` | `undefined` | Opcional |
| `itemsHorizontalMenu` | `items-horizontal-menu` | Elements del menú horitzontal associat (configuració). Accepta array d'objectes o string JSON | `string` | `undefined` | Opcional |
| `sizeFontTab` | `size-font-tab` | Grandària de la font del text de la tab. Opcions: `medium`, `small` | `string` | `medium` | Obligatori |
| `tabItems` | `tab-items` | Col·lecció d'elements: array amb el nom de la pestanya i el contingut. Accepta array d'objectes o string JSON | `string` (array) | `undefined` | Obligatori |

**Propietats de l'array `tabItems`**

| Propietat | Atribut | Descripció | Obligatorietat | Tipus |
|---|---|---|---|---|
| `description` | `description` | Descripció de la tab | Opcional | String |
| `dropdownContent` | `dropdownContent` | Si la tab és un dropdown, aquí cal introduir-ne el contingut | Opcional | String (array) |
| `iconPrevText` | `iconPrevText` | Icona prèvia al text de la tab. Cal utilitzar una classe de la biblioteca d'icones de Bootstrap | Opcional | String |
| `iconState` | `iconState` | Si la tab té estat, cal indicar-lo aquí | Opcional | String |
| `id` | `id` | Identificador de la pestanya | Obligatori | String |
| `isBadge` | `isBadge` | Indica si la tab conté badge | Obligatori | Boolean |
| `isDropdown` | `isDropdown` | Indica si aquesta tab és un dropdown vertical o no | Obligatori | Boolean |
| `numberBadge` | `numberBadge` | En cas que el badge contingui un número, cal introduir-lo aquí | Opcional | String |
| `tabSelected` | `tabSelected` | Tab seleccionada al menú lateral | Obligatori | Boolean |
| `tag` | `tag` | Tag de la tab amb el contingut | Opcional | String (array) |
| `text` | `text` | Text principal de la tab | Obligatori | String |
| `textAlternativeBadge` | `textAlternativeBadge` | Text alternatiu del badge per a accessibilitat | Opcional | String |

**Propietats de l'array `dropdownContent`**

| Propietat | Atribut | Descripció | Obligatorietat | Tipus |
|---|---|---|---|---|
| `description` | `description` | Descripció de la tab | Opcional | String |
| `iconPrevText` | `iconPrevText` | Icona prèvia al text de la tab. Cal utilitzar una classe de la biblioteca d'icones de Bootstrap | Opcional | String |
| `iconState` | `iconState` | Si la tab té estat, cal indicar-lo aquí | Opcional | String |
| `id` | `id` | Identificador de la pestanya | Obligatori | String |
| `isBadge` | `isBadge` | Indica si la tab conté badge | Obligatori | Boolean |
| `numberBadge` | `numberBadge` | En cas que el badge contingui un número, cal introduir-lo aquí | Opcional | String |
| `tabSelected` | `tabSelected` | Tab seleccionada al menú lateral | Obligatori | Boolean |
| `text` | `text` | Text principal de la tab | Obligatori | String |

**Variants**

| Propietat | Valors | Per defecte |
|---|---|---|
| `iconState` | `complete`, `urgent`, `inProgress`, `block` | - |
| `sizeFontTab` | `medium`, `small` | `medium` |

**Esdeveniments**

| Esdeveniment | Descripció | Tipus / paràmetre | Origen |
|---|---|---|---|
| `badgeClick` | Propaga l'esdeveniment click al badge | `id` | `badge-component` |
| `dropdownTabClick` | Es propaga en seleccionar una subpestanya amb clic o prement Enter | `CustomEvent<{ childIndex: number; }>` (paràmetre `childIndex`) | `vertical-tabs-component` |
| `keydownEvent` | Es llança cada cop que es fa clic en una opció del menú desplegable (l'usuari prem una tecla) | `CustomEvent<KeyboardEvent>` | `vertical-tabs-component` |

**Mètodes públics**

| Mètode | Descripció | Paràmetre |
|---|---|---|
| `closeDropdownFromOutside()` | Tanca tots els dropdowns oberts | - |
| `toggleDropdownFromOutside(index)` | Obre o tanca un dropdown externament | `index: number` |

**Depèn de:** [`badge-component`](component-insignia.md), [`tag-component`](component-etiquetes.md), [`tooltip-component`](component-indicador-de-funcio.md).

**Utilitzat per:** `dropdown-menu-component`, `horizontal-menu-component` ([menú horitzontal](component-menu-horitzontal.md)), `side-menu-component` ([Menú lateral](component-menu-lateral.md)), `tab-bar-horizontal-component` i `tab-bar-vertical-component` ([Barra de pestanyes](component-barra-de-pestanyes.md)).

**Exemple d'ús**

```html
<!-- /index.html -->
<vertical-tabs-component
  id-tab="tab-principal" 
  size-font-tab="small" 
  icon-prev-text-global="true" 
  icon-state-global="true"
  items-horizontal-menu=''
  tab-items='[
      {
        "id": "tab1",
        "iconPrevText": "bi-bar-chart", 
        "text": "Pestanya",
        "description": "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
        "isDropdown": true, 
        "isBadge": true, 
        "tabSelected": false, 
        "numberBadge": "", 
        "iconState": "complete",
        "textAlternativeBadge": "Noves notificacions",
        "tag": [
          { 
            "type": "readonly", 
            "text": "Opcional", 
            "color": "color-white"
          }
        ], 
        "dropdownContent": [
          {
            "id": "tab1-1",
            "tabSelected": false,
            "iconPrevText": "bi-bar-chart",
            "text": "Pestanya 1",
            "description": "Lorem ipsum dolor sit amet.",
            "isBadge": true, 
            "numberBadge": "", 
            "iconState": "complete"
          },
          {
            "id": "tab1-2",
            "tabSelected": true,
            "iconPrevText": "bi-bar-chart",
            "text": "Pestanya 2",
            "description": "Lorem ipsum dolor.",
            "isBadge": true, 
            "numberBadge": "7", 
            "iconState": "complete"
          }
        ]
      }
    ]'
  active-horizontal-menu="false"
  dropdown-items-horizontal-menu="false">
  </vertical-tabs-component>
```

Exemple d'instància (PDF):

```html
<vertical-tabs-component
active-horizontal-menu=false
dropdown-items-horizontal-menu=false
icon-prev-text-global=false
icon-state-global=false
id-tab="texto-ejemplo"
items-horizontal-menu="texto-ejemplo"
size-font-tab='medium'
tab-items="texto-ejemplo"
></vertical-tabs-component>
```

[discrepància: el lloc marca `dropdownContent`, `iconState`, etc. amb atribut igual al nom camelCase i `dropdownItemsHorizontalMenu` amb atribut "Opcional"; el PDF dóna l'atribut `dropdown-items-horizontal-menu`, que és el que s'usa a l'exemple]

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.2.0 | 12.0.3 | 4 setembre, 2026 | Desenvolupament: es fa una correcció al patró de focus |
| 12.2.0 | 11.0.0 | 10 juliol, 2026 | Disseny: s'unifiquen les pestanyes verticals i les pestanyes verticals avançades. |
| 12.0.0 | 11.0.0 | 19 juny, 2026 | Desenvolupament: 1. Pestanyes verticals: s'ajusta l'alineació del badge i s'introdueixen les configuracions necessàries quan el component és utilitzat en altres components que necessiten obrir el sheet-component; millores d'accessibilitat en el lector de pantalla per al badge |
| 12.0.0 | 10.1.0 | 29 maig, 2026 | Disseny: s'ha afegit el frame d'slot a les pestanyes desplegables. Desenvolupament: ajust del gruix de la vora per als estats seleccionat i de desplaçament de les pestanyes horitzontals |
| 11.0.0 | 9.3.0 | 8 maig, 2026 | Disseny: es modifica el gruix de línia de la pestanya horitzontal. L'estat default passa de 3px a 2px i el hover de 2px a 3px. |
| 9.1.0 | 9.3.0 | 20 març, 2026 | Disseny: s'ha vinculat correctament el component badge a les pestanyes avançades. Desenvolupament: en pestanyes verticals, s'actualitza una de les icones d'estats urgents |
| 9.0.0 | 9.2.0 | 20 febrer, 2026 | Disseny: s'ha modificat la descripció perquè s'adapti correctament a l'amplada de la pestanya. / S'ha modificat la icona d'urgent. |
| 8.6.0 | 9.2.0 | 27 febrer, 2026 | Desenvolupament: es fan millores d'accessibilitat i es crea la propietat description a tabItems |
| 8.6.0 | 8.0.0 | 9 febrer, 2026 | Disseny: s'ha afegit una descripció a les pestanyes avançades, vinculat correctament l'etiqueta i eliminat el truncat de text. |
| 4.0.0 | 8.0.0 | 14 novembre, 2025 | Desenvolupament: resolució de problemes |
| 4.0.0 | 7.0.0 | 24 octubre, 2025 | Desenvolupament: nova propietat afegida o eliminada |
| 4.0.0 | 6.2.1 | 3 octubre, 2025 | Desenvolupament: nova propietat afegida o eliminada |
| 4.0.0 | 6.1.0 | 12 setembre, 2025 | Desenvolupament: resolució de problemes |
| 4.0.0 | 6.0.0 | 3 juliol, 2025 | Desenvolupament: resolució de problemes |
| 4.0.0 | 3.0.0 | 2 maig, 2025 | Disseny: es prototipa pestanyes horitzontals i verticals amb desplegable. |
| 2.4.0 | 3.0.0 | 28 abril, 2025 | Desenvolupament: resolució de problemes |
| 2.4.0 | 2.1.0 | 31 març, 2025 | Desenvolupament de l'evolutiu |
| 2.4.0 | 2.0.0 | 10 març, 2025 | Disseny (evolutiu): la línia que indica l'estat de les tabs horitzontals s'ha desplaçat un píxel per sobre de la línia del divisor i s'ha reduït l'alçada del focus. / S'ha optimitzat la construcció de les tabs verticals i horitzontals. |
| 2.3.0 | 2.0.0 | 7 març, 2025 | Desenvolupament (evolutiu): resolució de problemes i creació de pestanyes verticals. |
| 2.3.0 | 1.0.0 | 31 gener, 2025 | Sense canvis. |
| 2.2.0 | 0.1.1 | 20 gener, 2025 | Disseny: s'han unificat i reordenat les pestanyes en tres categories (Vertical Tabs, Horizontal Tabs i Menu Tabs), afegint mides (medium i small), transicions, opcions de visibilitat del badge/divisor, ajustos tipogràfics i l'estat focus per millorar la navegabilitat. |
| 2.1.0 | 0.1.1 | 04 desembre, 2024 | Sense canvis. |
| 2.0.0 | 0.1.0 | 02 desembre, 2024 | Sense canvis. |
| 1.1.0 | 0.1.0 | 22 novembre, 2024 | Sense canvis. |
| 1.1.0 | 0.0.4 | 18 novembre, 2024 | Sense canvis. |
| 1.0.0 | 0.0.3 | 1 novembre, 2024 | Disseny, desenvolupament i documentació del component. |

## Vegeu també
- [Barra de pestanyes](component-barra-de-pestanyes.md): barra de pestanyes dins del contingut.
- [Menú lateral](component-menu-lateral.md)
- [Panell emergent](component-panell-emergent.md)
- [Menú horitzontal](component-menu-horitzontal.md): per navegar pels elements principals de la pàgina.
- Pas a pas: per guiar l'usuari a través d'un procés complex (https://zeroheight.com/38669693e/p/728dba).
- Suport i sol·licituds: https://zeroheight.com/38669693e/p/57c57a-suport-i-contacte · https://zeroheight.com/38669693e/p/72240b-preguntes-frequents · https://zeroheight.com/38669693e/p/690b45 · https://zeroheight.com/38669693e/p/342611
