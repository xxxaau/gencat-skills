# Menú horitzontal (Horizontal menu)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/700828 · Web component: `<horizontal-menu-component>` (paquet core) · Font actualitzada el 2026-10-15 · Extret el 2026-10-28

## Què és i quan usar-lo
El menú horitzontal permet una navegació intuïtiva i ordenada. En seleccionar una opció del menú principal, es despleguen noves opcions de manera progressiva, facilitant l'accés a continguts més específics sense saturar la interfície.

És una barra de navegació situada a la part superior de la pàgina web que permet als usuaris accedir ràpidament a les seccions principals del lloc i desplegar opcions addicionals de manera progressiva per a una navegació més estructurada.

Quan s'utilitza: quan es vol maximitzar la visibilitat i l'accés a les pàgines clau d'un lloc web, facilitant la navegació de l'usuari sense necessitat de desplaçar-se per la pàgina.

Característiques principals:
- **Disposició horitzontal:** els elements es presenten en una línia per facilitar la navegació.
- **Descripció amb text:** cada element inclou una etiqueta clara que indica la seva funció, com ara "Inici" o "torna enrere".
- **Interactivitat:** inclou efectes visuals, com un canvi de color o subratllat, per indicar quina secció està activa.

## Quan NO usar-lo / alternatives
- Com a substitut de menú que afecta una sola pàgina.
- Components relacionats que cobreixen altres usos (la font no els presenta explícitament com a alternatives): [Menú lateral](component-menu-lateral.md) per a navegació complementària en gestió interna; [Pestanyes](component-pestanyes.md) per organitzar contingut relacionat en seccions o categories; [Acordió](component-acordio.md) per mostrar o amagar informació individualment d'un llistat d'ítems.

## Anatomia

### Punt de tall Extra large / Large
Menú replegat / desplegat. Figma: Desplegat i Replegat (Menú horitzontal/Components/Menú horitzontal_prototip/.../DOC_Horizontal menu/Anatomia).

### Punt de tall Small
Es col·loca al costat de la **capçalera** del lloc web.
1. **Botó de menú:** quan el menú està obert, la icona d'hamburguesa es transforma en una creu per tancar-lo.
2. **Selector d'espai** (opcional): permet canviar entre espais. Només apareix amb la Capçalera web Gencat, ja que la resta de webs corporatives no disposen d'espais diferenciats.
3. **Pestanyes de navegació:** les pestanyes amb una fletxa a la dreta indiquen que contenen més nivells de profunditat.
4. **Accés a la Seu Electrònica** (opcional).
5. **Accés a "T'atendem".**
6. **Selector d'idioma.**
7. **Botó per tornar al nivell de navegació anterior.**
8. **Botó per accedir a la pàgina de distribució del nivell actual.**

## Variants, tipus i estats

### Horizontal bar desktop (Extra Large / Large)

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Extra-Large column fixed / Extra-Large column variable / Large | --- |
| Show Chevron right | True / False | False |
| Show Chevron left | True / False | False |
| Show menu | True / False | False |

Variants Figma: Horizontal bar desktop / Breakpoint = Extra Large Column fixed | Extra Large Column variable | Large.

### Horizontal bar mobile (nivells del menú desplegat)

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Levels | Second level / Third level | --- |
| Show Additional content | True / False | True |
| Title | Text | --- |
| Description | Text | --- |
| Show Column 1 scroll | True / False | False |
| Show Column 2 scroll | True / False | False |

Variants Figma: Horizontal bar menu / Level = Second level | Third level.

### Punt de tall Small

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Medium / Small | Medium |
| Level | Default / First level / Second - Third level | Default |
| Type | Public / Private | Public |
| Web gencat | True / False | True |
| Show Scroll Bar | True / False | False |

Variants Figma: Horizontal bar mobile / Breakpoint = Medium | Small; Level = Default | First level | Second-Third level; Type = Public | Private.

## Mides i espaiats
- Format: el menú horitzontal està compost per [pestanyes horitzontals](component-pestanyes.md) disposades una al costat de l'altra. Quan hi ha una pestanya desplegable, s'obre el menú, compost per [pestanyes verticals](component-pestanyes.md), que poden anar sense xebró o amb xebró segons si tenen un subnivell de navegació o no.
- El menú horitzontal per a dispositius grans s'adapta a les mides i punts de tall *Extra-Large Column fix*, *Extra-Large Column variable* i *Large*.
- Per adaptar el menú en dispositius petits com tauleta i mòbil, s'ha d'utilitzar el menú horitzontal en versió responsiva.
- Menú obert: l'alçada del desplegable és fixa i ocupa el 80% de la pantalla. Per la part inferior apareix un *overlay* (superposició) del 25% amb el valor #333333.
- Pestanyes: sempre es mostra un **mínim de dues pestanyes** i l'amplada mínima es determina pel contingut d'aquestes dues pestanyes.
- Versió mòbil: format compost per [pestanyes verticals](component-pestanyes.md); l'opció de tornar enrere a un nivell anterior és un [botó](component-botons.md).
- Historial: marge inferior de 40 px al grup de pestanyes (perquè en el prototip es vegi l'última pestanya en fer scroll).

## Comportament i interacció

### Punt de tall Extra large / Large
1. **El menú per defecte es veu replegat amb la primera pestanya seleccionada.** Es mostra una barra horitzontal amb diverses opcions de navegació. Si una opció inclou un xebró, l'usuari pot intuir que hi ha més opcions disponibles; si no en té, quan es fa clic es redirigeix directament a la pàgina corresponent.
2. **L'usuari desplega el segon nivell de navegació.** Apareix un segon nivell amb diferents opcions. Juntament amb aquest segon nivell pot aparèixer una imatge i un text descriptiu (opcionals) que fan referència als enllaços del primer nivell. La imatge que es mostra al desplegable coincideix amb la capçalera de la pàgina de destí, cosa que garanteix coherència visual i millora la navegació.
3. **L'usuari desplega el tercer nivell de navegació.** Si l'usuari fa clic a una pestanya amb xebró en el segon nivell, es desplega a la seva dreta un submenú de tercer nivell.
4. **Quan hi ha més opcions de les que caben a dins del menú**, hi ha una barra de desplaçament indicant que hi ha més opcions que no es veuen. Apareix una barra de desplaçament i dues transparències que amaguen el contingut a mesura que es mostren, perquè sigui més fàcil la navegació.

### Interacció
- Les pestanyes desplegables s'activen quan l'usuari fa clic sobre elles i no en passar amb el ratolí.
- Si una de les pestanyes està desplegada i es fa clic sobre una altra, la primera es tanca automàticament abans d'obrir la segona.
- Si l'usuari fa clic fora de la zona determinada del menú, aquest es tanca.

### Adaptació responsiva
En el cas que el menú sigui més gran que l'amplada de la pantalla, les opcions no visibles s'amaguen i s'hi pot accedir a través d'un botó de navegació.

### Prototipat (Figma)
Per prototipar el menú horitzontal cal maquetar el component en dos *frames* (marcs) diferents: en el primer, la pestanya replegada; en el segon, la desplegada mostrant el menú per sobre la resta d'elements.

### Punt de tall Small
1. **El menú per defecte està tancat.** Es mostra tancat i format per un botó d'icona "hamburguesa" sobre el qual l'usuari ha de fer clic per obrir-lo.
2. **L'usuari obre el menú.** Apareix un llistat vertical de múltiples opcions de primer nivell. L'usuari pot fer-hi clic per arribar a les pàgines de destí o bé a un segon nivell de navegació.
3. **L'usuari accedeix al segon nivell de navegació.** Quan selecciona una pestanya amb xebró accedeix a un segon nivell. Aleshores apareix un botó per tornar enrere que porta al nivell anterior.

#### Selector d'idioma
Mostra una llista d'idiomes que l'usuari pot seleccionar. Per defecte, el selector és tancat, però ja mostra l'opció de català seleccionada. Un cop es canvia l'idioma, el selector tancat actualitza el que mostra per l'opció seleccionada.

#### Selector d'espai
Permet canviar entre diferents espais dins la Capçalera web Gencat (no disponible en altres webs corporatives). En versió mòbil, utilitza el component de [pestanyes horitzontals](component-pestanyes.md) per mostrar les opcions d'espai. Quan es selecciona un espai, el menú actual es tanca automàticament i l'usuari és redirigit a la pàgina d'inici de l'espai escollit. En tornar a obrir el menú, es mostra el menú corresponent al nou espai actiu.

## Contingut i microcopy
- Etiquetes d'exemple: "Inici", "torna enrere".
- Exemple de codi: `submenu-main-link-text="Accedeix a"`, `submenu-back-link-text="Torna a"`, `language-selector-label="Idioma"`, `aria-label-language-selector="Selector d'idioma"`.

## Bones pràctiques

### Alineació i posició
- **FER:** Implementa el menú horitzontal sota la capçalera del lloc web.
- **NO FER:** No implementis el menú horitzontal sobre la capçalera.
- **FER:** Alinea'l a l'esquerra.
- **NO FER:** No l'alineïs a la dreta o a altres posicions que no sigui a l'esquerra.

### Context
- **FER:** Indica la posició on es troba l'usuari.
- **FER:** Distingeix clarament els elements del menú que presenten submenús d'aquells que redirigeixen automàticament a una pàgina nova.

### Comunicació clara
- **FER:** Utilitza paraules clares, descriptives i familiars pels usuaris. No han de sobrepassar els vuitanta caràcters.
- **NO FER:** No utilitzis paraules poc clares, descriptives o no familiars pels usuaris i que sobrepassin els vuitanta caràcters.

### Quantitat d'elements
- **FER:** No recomanem posar més de 7 elements.
- **FER:** En cas que es posin més de 7 elements, cal incloure el xebró.

### Utilització correcta de les icones
- **FER:** Pel menú horitzontal en dispositius petits, utilitza el botó que té una icona d'hamburguesa.
- **NO FER:** No utilitzis una icona diferent de la d'hamburguesa per indicar que és un menú horitzontal.

### Alineació i posició (mòbil)
- **FER:** Posa el menú horitzontal mòbil en la mateixa ubicació que la capçalera del lloc web.
- **NO FER:** No posis el menú horitzontal mòbil en una altra ubicació.
- **NO FER:** El menú se superposa en tota l'amplada del dispositiu mòbil. No s'ha de veure contingut de la pàgina pels costats.

### Etiquetes
- **FER:** Utilitza etiquetes rellevants per les pestanyes i pel botó de tornar a un nivell anterior.
- **NO FER:** No utilitzis etiquetes confuses per navegar a dins del menú i pel botó de tornar a un nivell anterior.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG) que cita el component:
- **1.3.4 Orientació (AA):** el contingut de l'àrea de text s'adapta a les diferents orientacions de la pantalla, com ara vertical o horitzontal, cosa que permet visualitzar el contingut. (CAT: https://www.w3.org/Translations/WCAG22-ca/#orientation · EN: https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **1.4.3 Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. (CAT: https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum · EN: https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **1.4.4 Canvia la mida del text (AA):** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. (CAT: https://www.w3.org/Translations/WCAG22-ca/#resize-text · EN: https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **1.4.11 Contrast d'elements no textuals (AA):** els elements gràfics com icones (*xebrons*) i línies horitzontals presenten un contrast mínim de 3:1. (CAT: https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast · EN: https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **1.4.12 Espaiat del text (AA):** quan es desenvolupa contingut utilitzant llenguatges de marcatge que permeten aplicar les propietats d'estil de text, no es perd cap contingut ni funcionalitat si s'ajusten les propietats següents: alçada de línia (interlineat) de com a mínim 1,5 vegades la mida de la lletra; espaiat entre els paràgrafs de com a mínim dues vegades la mida de la lletra; espaiat entre lletres (*tracking*) de com a mínim 0,12 vegades la mida de la lletra; espaiat entre paraules de com a mínim 0,16 vegades la mida de la lletra. (CAT: https://www.w3.org/Translations/WCAG22-ca/#text-spacing · EN: https://www.w3.org/WAI/WCAG22/Understanding/text-spacing)
- **2.1.1 Teclat (A):** tota la funcionalitat del contingut (accedir als nivells i subnivells) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. (CAT: https://www.w3.org/Translations/WCAG22-ca/#keyboard · EN: https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **2.4.7 Focus visible (AA):** la navegació al camp de l'àrea de text és visible mitjançant un rectangle extern. (CAT: https://www.w3.org/Translations/WCAG22-ca/#focus-visible · EN: https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- **2.4.11 Focus no ocult (AA):** mentre el menú és obert, el focus ha de quedar atrapat dins seu i no pot accedir als elements de la pàgina de darrere. En obrir-se, el focus s'ha de moure al primer element interactiu del menú. En tancar-se, el focus ha de tornar a la pestanya que el va activar. El menú no pot ocultar cap element que tingui el focus de teclat. Aquesta consideració és especialment rellevant en dispositius mòbils i tauletes amb zoom de pantalla activat, on el menú ocupa una proporció més gran de la pantalla visible. (CAT: https://www.w3.org/Translations/WCAG22-ca/#focus-not-obscured-minimum · EN: https://www.w3.org/WAI/WCAG22/Understanding/focus-not-obscured-minimum)

### Navegació per teclat

| Tecla | Acció |
|---|---|
| Tabulació | Navega al següent element interactiu de la pàgina |
| Shift+Tabulació | Navega a l'anterior element interactiu de la pàgina |
| Fletxes dreta i esquerra | Navega per pestanyes horitzontals |
| Fletxes amunt i avall | Navega per pestanyes verticals |
| Enter | Selecciona un element o desplega un element |
| Esc | Replega el menú |

En seleccionar un dels nivells amb desplegable, el focus es trasllada al primer subnivell.

## Implementació (component web)

### `<horizontal-menu-component>`
Paquet: core.

**Propietats**

Taula de la pàgina del lloc (amb obligatorietat):

| Propietat | Atribut HTML | Descripció | Obligatorietat | Tipus |
|---|---|---|---|---|
| `ariaLabelLanguageSelector` | `aria-label-language-selector` | Etiqueta descriptiva (accessibilitat) per a lectors de pantalla associada al selector d'idioma. | Opcional | String |
| `idActive` | `id-active` | Cal indicar l'ID de la pestanya activa, sigui del primer, segon o tercer nivell del menú. És a dir, fa referència a l'ID de la pestanya que coincideix amb l'URL de la pàgina on ens trobem actualment. Cada URL haurà de portar l'ID de la pestanya corresponent. | Obligatori | String |
| `languageSelector` | `language-selector` | JSON amb els idiomes disponibles per seleccionar, incloent-hi codi d'idioma, nom i URL de redirecció. | Obligatori | String (array) |
| `languageSelectorLabel` | `language-selector-label` | Text que actua com a etiqueta visible per al selector d'idioma. | Obligatori | String |
| `menuItems` | `menu-items` | Array amb el nom de cada apartat del menú, així com els enllaços dels mateixos i la informació dels submenús. | Obligatori | String (array) |
| `secondButtonIcon` | `second-button-icon` | Icona del segon botó. | Opcional | String |
| `secondButtonText` | `second-button-text` | Text del segon botó. | Opcional | String |
| `submenuBackLinkText` | `submenu-back-link-text` | Text que apareix com a enllaç de retrocés quan es navega cap a un subnivell dins del menú hamburguesa. | Obligatori | String |
| `submenuMainLinkText` | `submenu-main-link-text` | Fa referència al text que acompanya l'enllaç superior principal del segon i tercer nivell de menú quan està desplegat (menú desktop). | Obligatori | String |

Valors per defecte segons el PDF (v12.0.0):

| Propietat | Atribut HTML | Descripció (PDF) | Tipus | Per defecte |
|---|---|---|---|---|
| `ariaLabelLanguageSelector` | `aria-label-language-selector` | Selector CSS de l'element de referència per al posicionament. | string | (cadena buida) |
| `idActive` | `id-active` | Identificador de l'element actiu. | string | (cadena buida) |
| `languageSelector` | `language-selector` | Configuració del selector d'idioma. Accepta objecte o string JSON. | string | undefined |
| `languageSelectorLabel` | `language-selector-label` | Etiqueta descriptiva de l'element. | string | (cadena buida) |
| `menuItems` | `menu-items` | Col·lecció d'elements. Accepta array d'objectes o string JSON. | string | undefined |
| `submenuBackLinkText` | `submenu-back-link-text` | URL de l'enllaç. | string | (cadena buida) |
| `submenuMainLinkText` | `submenu-main-link-text` | URL de l'enllaç. | string | (cadena buida) |

[discrepància: el PDF descriu `ariaLabelLanguageSelector` com a "Selector CSS de l'element de referència per al posicionament" i `submenuBackLinkText`/`submenuMainLinkText` com a "URL de l'enllaç"; el lloc els descriu com a etiqueta ARIA del selector d'idioma i com a textos d'enllaç]
[discrepància: `secondButtonIcon` i `secondButtonText` figuren al lloc però no al PDF v12.0.0]

**Props que accepten JSON**

Propietats de l'array `menuItems`:

| Propietat | Atribut | Descripció | Obligatorietat | Tipus |
|---|---|---|---|---|
| `description` | `description` | Descripció que acompanya la pestanya. | Opcional | String |
| `dropdownItems` | `dropdownItems` | Si aquesta pestanya té dropdown, aquí s'indiquen les dades de cada opció. Vàlid per a nivell 2 i nivell 3. | Opcional | String (array) |
| `idItem` | `idItem` | Identificador de la pestanya/item. | Obligatori | String |
| `image` | `image` | Imatge que acompanya la pestanya. | Opcional | String |
| `label` | `label` | Text de la pestanya. | Obligatori | String |
| `link` | `link` | Link de la pestanya. | Opcional | String |
| `title` | `title` | Títol que acompanya la pestanya. | Opcional | String |

Propietats de l'array `dropdownItems`:

| Propietat | Atribut | Descripció | Obligatorietat | Tipus |
|---|---|---|---|---|
| `dropdownItems` | `dropdownItems` | Fa referència a aquest mateix array; en aquest cas, fa referència a les pestanyes del tercer nivell. | Opcional | String (array) |
| `idItem` | `idItem` | Identificador de la pestanya/item. | Obligatori | String |
| `label` | `label` | Text de la pestanya. | Obligatori | String |
| `link` | `link` | Link de la pestanya. | Opcional | String |
| `parentId` | `parentId` | Identificador de la pestanya pare. | Obligatori | String |

Propietats de l'array `languageSelector`:

| Propietat | Atribut | Descripció | Obligatorietat | Tipus |
|---|---|---|---|---|
| `active` | `active` | Indica si l'idioma actual està seleccionat (true/false). | Opcional | String |
| `iso` | `iso` | Codi ISO de l'idioma (ex: CA, ES, EN). | Obligatori | String |
| `title` | `title` | Nom de l'idioma que es mostrarà com a opció al selector. | Obligatori | String |
| `translatedText` | `translatedText` | Text tipus (Automaticament traduït) que apareix al costat de title | Opcional | String |

Propietats de l'array `headerTopBar`:

| Propietat | Atribut | Descripció | Obligatorietat | Tipus |
|---|---|---|---|---|
| `title` | `title` | Títol de la pestanya | Obligatori | String |
| `href` | `href` | href de la pestanya | Obligatori | String |
| `active` | `active` | Indica si és la pestanya activa o no | Obligatori | Boolean |

[a verificar: la versió 9.2.0 de Github elimina les propietats `linksTopBar` i `headerTopBar`; la taula `headerTopBar` continua a la documentació del lloc]

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `blurButton` | Es llança cada cop que es treu el focus en un botó. | --- | `button-component` |
| `focusButton` | Es llança cada cop que es fa focus en un botó. | --- | `button-component` |
| `handlerClick` | Es llança cada cop que es fa clic en un botó i com a paràmetre conté les dades de l'esdeveniment. | id | `button-component` |
| `clickLevel` | Esdeveniment llançat en seleccionar un nivell. | `id` | `breadcrumb-component` |
| `clickCard` | En prémer una targeta s'emet un esdeveniment amb l'ID del component. | ID del component | `card-navigation-basic-component` |
| `menuClosed` | Es llança cada cop que es tanca el menú (en mòbil). (PDF: `CustomEvent<void>`) | --- | `horizontal-menu-component` |
| `secondButtonClick` | Es llança quan es fa clic al segon botó. | --- | `horizontal-menu-component` |
| `languageSelected` | Es propaga en seleccionar un llenguatge en el format mobile | id i altres dades | `horizontal-menu-component` |
| `tabClickMenu` | Es propaga en seleccionar una pestanya del menú horitzontal a qualsevol dels seus nivells. (PDF: `CustomEvent<{ subItem: string; }>`) | id i altres dades | `horizontal-menu-component` |
| `keydownButtonMobileEvent` | Es propaga en prémer alguna tecla del teclat en versió mòbil | event.detail | `tab-bar-horizontal-component` |
| `tabSelected` | Es llança en fer clic a una pestanya de headerTopBar (aquest esdeveniment pertany al component tab-bar-horizontal) | Índex de la pestanya | `tab-bar-horizontal-component` |
| `dropdownTabClick` | Es propaga en seleccionar una subpestanya amb clic o prement enter | `childIndex` | `vertical-tabs-component` |
| `keydownEvent` | Es llança cada cop que es fa clic una opció del menú desplegable | Esdeveniment emès | `vertical-tabs-component` |
| `blurLink` | Es llança cada cop que es treu el focus en un enllaç | --- | `link-component` |
| `focusLink` | Es llança cada cop que es fa focus en un enllaç | --- | `link-component` |
| `linkEmit` | Es llança cada cop que es fa clic en un enllaç | `id` | `link-component` |

**Depèn de:**
- `breadcrumb-component` ([Fils d'Ariadna](component-fils-d-ariadna.md))
- `button-component` ([Botons](component-botons.md))
- `card-navigation-basic-component` ([Targetes](component-targetes.md))
- `horizontal-tab-component` ([Pestanyes](component-pestanyes.md))
- `link-component` ([Enllaços](component-enllacos.md))
- `tab-bar-horizontal-component` ([Barra de pestanyes](component-barra-de-pestanyes.md))
- `vertical-tabs-component` ([Pestanyes](component-pestanyes.md))

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<horizontal-menu-component
    aria-label-language-selector="Selector d'idioma"
    submenu-main-link-text="Accedeix a" 
    submenu-back-link-text="Torna a"
    language-selector-label="Idioma" 
    id-active="administracion_submenu_2"
    second-button-icon="bi-plus"
    second-button-text="Acció secundària"
    language-selector='[
      {"iso": "CA", "title": "Catalá","active":"true"},
      {"iso": "ES", "title": "Castellano","active":"false", "translatedText": "(Automáticamente traducido)"},
      {"iso": "EN", "title": "English","active":"false"},
      {"iso": "OA", "title": "Occitan aranés", "active":"false"}
    ]' 
    menu-items='[
        {
          "idItem": "inici",
          "label": "Inici",
          "image": "/assets/photos/hero_banner.png",
          "title": "Inici",
          "description": "Description for Inici"
        },
        {
          "idItem": "temes",
          "label": "Temes",
          "image": "/assets/photos/hero_banner.png",
          "title": "Temes",
          "description": "Description for Temes",
          "dropdownItems": [
            {
              "idItem": "administracio_publica",
              "label": "Administració pública",
              "parentId": "temes",
              "dropdownItems": [
                {
                  "idItem": "administracion_submenu_1",
                  "label": "Administracion submenu",
                  "parentId": "administracio_publica"
                },
                {
                  "idItem": "administracion_submenu_2",
                  "label": "Administracion submenu",
                  "parentId": "administracio_publica"
                },
                {
                  "idItem": "administracion_submenu_3",
                  "label": "Administracion submenu",
                  "parentId": "administracio_publica"
                }
              ]
            },
            {
              "idItem": "agricultura_i_ramaderia_pesca",
              "label": "Agricultura i ramaderia. Pesca",
              "parentId": "temes",
              "dropdownItems": [
                {
                  "idItem": "agricultura_submenu_1",
                  "label": "Administracion submenu",
                  "parentId": "administracio_publica"
                },
                {
                  "idItem": "agricultura_submenu_2",
                  "label": "Administracion submenu",
                  "parentId": "administracio_publica"
                },
                {
                  "idItem": "agricultura_submenu_3",
                  "label": "Administracion submenu",
                  "parentId": "administracio_publica"
                }
              ]
            },
            {
              "idItem": "associacionisme_participacio",
              "label": "Associacionisme. Participació",
              "parentId": "temes"
            },
            {
              "idItem": "catalunya",
              "label": "Catalunya",
              "parentId": "temes",
              "dropdownItems": [
                {
                  "idItem": "catalunya_submenu_1",
                  "label": "Administracion submenu",
                  "parentId": "administracio_publica"
                },
                {
                  "idItem": "catalunya_submenu_2",
                  "label": "Administracion submenu",
                  "parentId": "administracio_publica"
                }
              ]
            }
          ]
        },
        {
          "idItem": "seu_electronica",
          "label": "Seu electrònica",
          "image": "/assets/photos/hero_banner.png",
          "title": "Seu electrònica",
          "description": "Description for Seu electrònica",
          "dropdownItems": [
            {
              "label": "Serveis de la Seu",
              "idItem": "serveis_de_la_seu",
              "parentId": "seu_electronica"
            }
          ]
        },
        {
          "idItem": "tramits",
          "label": "Tràmits",
          "image": "/assets/photos/hero_banner.png",
          "title": "Tràmits",
          "description": "Description for Tràmits",
          "dropdownItems": [
            {
              "label": "Informació a lhora de demanar cita",
              "idItem": "informacio_a_lhora_de_demanar_cita",
              "parentId": "tramits"
            }
          ]
        },
        {
          "idItem": "situacions_de_vida",
          "label": "Situacions de vida",
          "image": "/assets/photos/hero_banner.png",
          "title": "Situacions de vida",
          "description": "Description for Situacions de vida",
          "dropdownItems": [
            {
              "idItem": "submenu_1",
              "label": "Submenú 1",
              "parentId": "situacions_de_vida",
              "dropdownItems": [
                {
                  "idItem": "subsubmenu_1",
                  "label": "SubSubmenú 1",
                  "parentId": "submenu_1"
                },
                {
                  "idItem": "subsubmenu_2",
                  "label": "SubSubmenú 2",
                  "parentId": "submenu_1"
                }
              ]
            }
          ]
        },
        {
          "idItem": "generalitat",
          "label": "Generalitat",
          "image": "/assets/photos/hero_banner.png",
          "title": "Generalitat",
          "description": "Description for Generalitat"
        },
        {
          "idItem": "actualitat",
          "label": "Actualitat",
          "image": "/assets/photos/hero_banner.png",
          "title": "Actualitat",
          "description": "Description for Actualitat"
        }
      ]'></horizontal-menu-component>
```

**Exemple d'instància (PDF)**

```html
<horizontal-menu-component
aria-label-language-selector=''
id-active=''
language-selector="texto-ejemplo"
language-selector-label=''
menu-items="texto-ejemplo"
submenu-back-link-text=''
submenu-main-link-text=''
></horizontal-menu-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.2.0 | 12.1.0 | 7 setembre, 2026 | Desenvolupament: s'afegeixen les propietats `secondButtonText` i `secondButtonIcon`, que permeten afegir un botó al peu del menú en mode mòbil; es crea l'esdeveniment `secondButtonClick` per detectar clics en aquest nou botó |
| 12.2.0 | 12.0.0 | 10 juliol, 2026 | Disseny: s'actualitzen les pestanyes unificades |
| 12.0.0 | 12.0.0 | 10 juliol, 2026 | Desenvolupament: s'utilitza el token correcte per al color de text de títol i descripció de la tercera columna |
| 12.0.0 | 11.0.0 | 19 juny, 2026 | Desenvolupament: ajustos en el comportament del mode focus |
| 12.0.0 | 10.0.0 | 29 maig, 2026 | Disseny: s'ha afegit la funcionalitat de slots als frames que contenen les pestanyes i els màxims d'amplada en aquests |
| 10.0.0 | 10.0.0 | 8 maig, 2026 | Desenvolupament: s'ajusta la vista de les cards del botó Els meus espais |
| 10.0.0 | 9.3.0 | 17 abril, 2026 | Disseny: es crea la variant del menú mobile per àrea privada |
| 8.4.0 | 9.3.0 | 20 març, 2026 | Desenvolupament: s'arreglen els estils de la barra de scroll a desktop; es corregeixen els estils del botó "Els meus espais" a mobile |
| 8.4.0 | 9.2.0 | 27 febrer, 2026 | Desenvolupament: s'eliminen les propietats linksTopBar i headerTopBar; s'afegeix un nou botó per al mode private-àrea de header-public que obre una modal amb més espais; es fan adaptacions als nous requisits del component header-public |
| 8.4.0 | 9.1.0 | 6 febrer, 2026 | Desenvolupament: adaptacions d'accessibilitat pel que fa a mides de font extra gran i augment de pantalla |
| 8.4.0 | 9.0.0 | 12 gener, 2026 | Desenvolupament: s'hi afegeix barra d'scroll en menú mobile i degradat inferior en contenidor principal |
| 8.4.0 | 8.0.0 | 5 desembre, 2025 | Disseny: s'ha afegit un gradient a dalt i a baix de la versió small i una barra de desplaçament; es revinclen els botons per desplaçar les pestanyes |
| 8.2.0 | 8.0.0 | 14 novembre, 2025 | Desenvolupament: nova propietat afegida |
| 8.2.0 | 6.2.1 | 27 octubre, 2025 | Disseny: s'inicialitzen les instàncies de Language Selector Tab per tornar a vincular estils tipogràfics |
| 8.1.0 | 6.2.1 | 6 octubre, 2025 | Disseny: s'afegeix un marge inferior de 40 px al grup de pestanyes perquè en muntar el prototip es pugui veure l'última pestanya en fer scroll; s'ha mogut la barra de desplaçament per sobre les capes. Desenvolupament: nova propietat afegida o eliminada |
| 7.0.0 | 6.1.0 | 12 setembre, 2025 | Desenvolupament: nova propietat afegida |
| 7.0.0 | 6.0.1 | 28 juliol, 2025 | Disseny: s'afegeixen pestanyes corresponents a la capçalera gencat al menú horitzontal per a mides mitjanes i petites. Desenvolupament de l'evolutiu |
| 4.0.0 | 4.0.1 | 19 maig, 2025 | Desenvolupament: resolució de problemes |
| 2.4.0 | 2.0.0 | 10 març, 2025 | Disseny (evolutiu): s'han creat els desplegables a nivell secundari i a nivell terciari, s'ha afegit una imatge i descripció complementària de les principals pestanyes del menú; es contempla que en algunes pestanyes principals no s'escau posar imatge |
| 2.3.0 | 2.0.0 | 7 març, 2025 | Desenvolupament: evolutiu |
| 2.3.0 | 1.0.0 | 31 gener, 2025 | Disseny: s'han ajustat les pestanyes del menú per escriptori de forma que estiguin en Hug i s'ha ajustat la posició dels botons de desplaçament de les pestanyes quan aquestes queden desbordades |
| 2.2.0 | 0.1.1 | 20 gener, 2025 | Disseny: s'han unificat les pestanyes i actualitzat al component combinat del menú horitzontal |
| 2.1.0 | 0.1.1 | 04 desembre, 2024 | Sense canvis |
| 2.0.0 | 0.1.0 | 02 desembre, 2024 | Sense canvis |
| 1.1.0 | 0.1.0 | 22 novembre, 2024 | Sense canvis |
| 1.1.0 | 0.0.4 | 18 novembre, 2024 | Desenvolupament del component i actualització de la documentació |
| 1.0.0 | --- | 1 novembre, 2024 | Disseny i documentació del component |

## Vegeu també
- [Acordió](component-acordio.md): per mostrar o amagar informació individualment d'un llistat d'ítems.
- [Menú lateral](component-menu-lateral.md): per navegació complementària en gestió interna.
- [Pestanyes](component-pestanyes.md): per organitzar contingut relacionat en seccions o categories.
- [Barra de pestanyes](component-barra-de-pestanyes.md)
- [Fils d'Ariadna](component-fils-d-ariadna.md)
- [Botons](component-botons.md)
- [Targetes](component-targetes.md)
- [Enllaços](component-enllacos.md)
