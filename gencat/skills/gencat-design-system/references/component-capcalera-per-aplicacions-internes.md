# Capçalera per aplicacions internes (Back-office Header)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/44c2a4 · Web component: `<header-component>` (paquet core) · Font actualitzada el 2026-10-22 · Extret el 2026-10-28

## Què és i quan usar-lo
Una capçalera és la secció superior d'una pàgina web o aplicació que proporciona un lloc coherent per a la marca, la cerca i l'accés a les accions globals de l'aplicació, com ara la configuració i les notificacions.

Quan s'utilitza: per a aplicacions internes, de gestió interna i productes web d'utilització interna. S'inclourà en cadascuna de les pàgines del portal a dissenyar.

## Quan NO usar-lo / alternatives
- Per a pàgines públiques (vegeu [Capçalera web pública](component-capcalera-web-publica.md)).

## Anatomia

### Nom de la capçalera
Figma: Extra Large (Capçalera aplicacions internes/Documentació Zeroheight/DOC_Disseny/Anatomia/Cercador/Extra Large). Per a més informació sobre els logotips, vegeu [Marca](fonaments-marca.md).

### Cercador
Figma: Extra Large (mateix origen).

### Barra d'utilitats
Està formada per:
1. **Botó de perfil (menú desplegable):** mostra a primer nivell el nom de l'usuari (format: primera lletra de cada cognom, nom de pila) i informació sobre l'usuari (com data d'últim accés), canvi entre eines a les quals l'usuari té accés i altres possibles opcions relacionades amb el perfil de l'usuari.
2. **Botons principals (notificacions i ajuda).**
3. **Botó addicional (opcional):** espai per introduir un botó extra en cas de ser necessari.
4. **Més opcions (opcional):** botó que permet incloure un menú desplegable on poder incloure més elements contextuals o d'utilitat pels usuaris de back-office.

Figma: Small3 i Small2 (Capçalera aplicacions internes/Documentació Zeroheight/DOC_Disseny/Anatomia/Barra utilitats).

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Extra Large Column Variable / Large / Medium / Small | Extra Large Column Variable |
| Search | Simple / Advanced | Simple |
| Show Subtitle | True / False | False |
| Show Tag | True / False | False |
| Show placeholder icon | True / False | False |
| Show more options button | True / False | True |
| Show Searchfield | True / False | True |
| Profile menu | True / False | False |

Variants Figma: Header [Show Subtitle = False, Name = Nom de l'aplicació, Show Tag = False, Show placeholder Icon = False, Show more options button = True, Show Searchfield = True, Advanced search = False]; Header [..., Change logo = Disposition = Left, Color = Color, State = Default, Breakpoint = Extra Large Column Variable].

## Mides i espaiats
- El nom de l'aplicació té una amplada màxima de 480 px.
- Per a pantalles inferiors a 359 píxels d'amplada (dispositius mòbils), el logotip de la Generalitat se simplifica i es converteix en isotip.
- Els marges laterals s'adaptaran segons les característiques de la retícula aplicada a cada [punt de tall](fonaments-punt-de-tall-i-quadricules.md).
- Es configura el min width de 1440 px a Extra Large Column Variable (historial de versions: Figma 12.3.0, 31 juliol 2026).

## Comportament i interacció

### Interacció
Les notificacions arribaran al botó corresponent de notificacions sigui quina sigui la relació amb aquestes. Des d'aquesta pàgina es redirigirà l'usuari a la secció específica.

### Posició
Situat a la part superior de la pàgina. Queda fix per mantenir els usuaris orientats i donar-los més control.

### Adaptació responsiva
- Als punts de tall *Extra Large* i *Large*, tot el contingut es mostra en un sol bloc.
- Als punts de tall *Medium* i *Small*, el contingut es divideix en dos blocs:
  - Bloc superior: *burger menu* (menú d'hamburguesa), logotip de la Generalitat de Catalunya i un màxim de 3 icones d'utilitats.
  - Bloc inferior: nom de l'aplicació i subtítol.
- El nom de l'aplicació té una amplada màxima de 480 px.

Funcionalitat de cerca:
- Al breakpoint *Extra Large* la cerca es realitza a la mateixa capçalera.
- Al breakpoint *Large* la cerca es realitza al bloc que es desplega sota la capçalera.
- Als breakpoints *Medium* i *Small* la cerca es desplaça al *burger menu* (menú d'hamburguesa).

### Prototipat (Figma)
Per a prototipar la interacció amb els menús desplegables de la capçalera cal realitzar la interacció manualment enllaçant el *frame* (marc) principal del botó amb el menú desplegable (*burger menu*) aplicant l'opció *overlay* (cobrir) o bé creant un segon *frame* amb el desplegable visible.

## Bones pràctiques

### Navegació
- **FER:** Utilitza la capçalera per als elements essencials. Deixa els elements de navegació per al menú horitzontal.
- **NO FER:** No utilitzis la capçalera per a enllaços de navegació de les seccions principals de la web. Inclou en la capçalera elements contextuals i d'utilitat.

### Barra d'utilitat
- **FER:** Si necessites incloure més elements a la capçalera, considera agrupar-los en el botó de més opcions o traslladar-los a un lloc secundari a la pàgina.
- **NO FER:** No sobrecarreguis la capçalera amb múltiples elements a primer nivell. És preferible que hi hagi poques opcions clau visibles.

### Cerca avançada
- **FER:** Es recomana que la cerca avançada aparegui en una pàgina nova.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG) que cita el component:
- **1.4.1 Ús del color (A):** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a indicar els diferents canvis d'estat, es modifiquen els píxels de la vora del component i/o s'afegeixen elements complementaris com la segona vora pel focus o la icona i el text d'error. (CAT: https://www.w3.org/Translations/WCAG22-ca/#use-of-color · EN: https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **1.4.3 Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són excepció d'aquesta norma. (CAT: https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum · EN: https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **1.4.4 Canvia la mida del text (AA):** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. (CAT: https://www.w3.org/Translations/WCAG22-ca/#resize-text · EN: https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **1.4.11 Contrast d'elements no textuals (AA):** els elements gràfics com icones (error i indicador de funció) i vores presenten un contrast mínim de 3:1. (CAT: https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast · EN: https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **2.1.1 Teclat (A):** tota la funcionalitat del contingut (accedir al camp de text) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. (CAT: https://www.w3.org/Translations/WCAG22-ca/#keyboard · EN: https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **2.4.7 Focus visible (AA):** la navegació al camp de l'àrea de text és visible mitjançant un rectangle extern. (CAT: https://www.w3.org/Translations/WCAG22-ca/#focus-visible · EN: https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- **2.4.11 Focus no ocult (AA):** la capçalera, en ser un element fix a la part superior de la pàgina, no pot ocultar cap element que tingui el focus de teclat durant el desplaçament de la pàgina. Això inclou el comportament de reaparició de la capçalera en fer desplaçament cap amunt (sticky reveal), que tampoc pot ocultar cap element enfocat en aquell moment. Aquesta consideració és especialment rellevant en dispositius mòbils i tauletes amb zoom de pantalla activat, ja que la capçalera ocupa proporcionalment més espai de la pantalla visible. (CAT: https://www.w3.org/Translations/WCAG22-ca/#focus-not-obscured-minimum · EN: https://www.w3.org/WAI/WCAG22/Understanding/focus-not-obscured-minimum)

## Implementació (component web)

### `<header-component>`
Paquet: core.

**Propietats**

Taula de la pàgina del lloc (amb obligatorietat):

| Propietat | Atribut HTML | Descripció | Obligatorietat | Tipus |
|---|---|---|---|---|
| `buttonFilterSearchfield` | `button-filter-searchfield` | Controla la visibilitat del botó de filtrar del searchfield | Opcional | Boolean |
| `dataKeyFieldSearchfield` | `data-key-field-searchfield` | Quan es carreguen les dades mitjançant URL, indica al component quina columna o columnes ha de prendre | Opcional | String o String (array) |
| `dataSearchfield` | `data-searchfield` | Permet carregar dades no gaire grans en un string (array) | Opcional | String (JSON) |
| `dataUrlSearchfield` | `data-url-searchfield` | Permet carregar dades grans mitjançant una URL connectada a backend | Opcional | String |
| `popoverConfigSearchfield` | `popover-config-searchfield` | Dades del popover del searchfield | Opcional | String |
| `searchfieldId` | `searchfield-id` | Identificador de l'input de tipus text del searchfield | Obligatori | String |
| `searchfieldName` | `searchfield-name` | Nom de l'input de tipus text del searchfield | Obligatori | String |
| `searchfieldValue` | `searchfield-value` | Valor del searchfield | Opcional | String |
| `secondtButtonIcon` | `second-button-icon` | Icona del botó secundari que apareix en mode mobile sota el searchfield | Obligatori | String |
| `secondButtonText` | `second-button-text` | Text del botó secundari que apareix en mode mobile sota el searchfield | Obligatori | String |
| `selectorSearch` | `selector-search` | Text de l'indicador de Selector per al camp de cerca que recull dades per introduir-les al cercador de la capçalera. | Obligatori | String |
| `showPopoverValueSearchfield` | `show-popover-value-searchfield` | Mostrar o amagar notificació emergent del searchfield | Opcional | Boolean |
| `showSearchfield` | `show-searchfield` | Permet amagar o mostrar el cercador | Opcional | Boolean |
| `showTooltipSearchfield` | `show-tooltip-searchfield` | Mostrar o amagar icona i amb tooltip del searchfield | Opcional | Boolean |
| `subtitleHead` | `subtitle-head` | Subtítol de la capçalera. | Opcional | String |
| `textButtonFilterSearchfield` | `text-button-filter-searchfield` | Text alternatiu del botó de filtrar del searchfield | Opcional | String |
| `textEtiquetaSearchfield` | `text-etiqueta-searchfield` | Text de l'etiqueta del searchfield | Opcional | String |
| `textInfoSearchfield` | `text-info-searchfield` | Text informatiu ubicat sota el searchfield | Opcional | String |
| `textInfoTooltipSearchfield` | `text-info-tooltip-searchfield` | Text del tooltip de la icona i del searchfield | Opcional | String |
| `textTag` | `text-tag` | Text de l'etiqueta. | Opcional | String |
| `titleHead` | `title-head` | Títol principal de la capçalera. | Obligatori | String |
| `titleSearchfield` | `title-searchfield` | Títol del searchfield en breakpoints compresos entre 960 i 1280px | Opcional | String |
| `tooltipFilterSearchfield` | `tooltip-filter-searchfield` | Text del tooltip del botó de filtrat del camp de cerca. | Opcional | String |
| `tooltipSearchfield` | `tooltip-searchfield` | Text del tooltip del botó de cerca. | Obligatori | String |

Valors per defecte segons el PDF (v12.0.0; el PDF no recull totes les propietats de la taula anterior):

| Propietat | Atribut HTML | Descripció (PDF) | Tipus | Per defecte |
|---|---|---|---|---|
| `buttonFilterSearchfield` | `button-filter-searchfield` | Activa o desactiva aquesta característica. | boolean | `false` |
| `dataKeyFieldSearchfield` | `data-key-field-searchfield` | Dada de configuració del cercador. | string | `text` |
| `dataSearchfield` | `data-searchfield` | Dades per al camp de cerca. Accepta array d'objectes o string JSON. | string | `[]` |
| `dataUrlSearchfield` | `data-url-searchfield` | URL de l'endpoint que proveeix les dades del cercador. | string | (cadena buida) |
| `searchfieldId` | `searchfield-id` | Identificador únic de l'element. | string | (cadena buida) |
| `searchfieldName` | `searchfield-name` | Atribut name del camp de cerca. | string | (cadena buida) |
| `searchfieldValue` | `searchfield-value` | Valor actual del camp de cerca. | string | (cadena buida) |
| `selectorSearch` | `selector-search` | Selector CSS de l'element àncora del cercador. | string | (cadena buida) |
| `showSearchfield` | `show-searchfield` | Mostra o amaga aquest element. | boolean | `true` |
| `subtitleHead` | `subtitle-head` | Títol del component. | string | (cadena buida) |
| `textButtonFilterSearchfield` | `text-button-filter-searchfield` | Text del botó. | string | (cadena buida) |
| `textTag` | `text-tag` | Nivell de l'encapçalament HTML. | string | (cadena buida) |
| `titleHead` | `title-head` | Títol del component. | string | (cadena buida) |
| `tooltipFilterSearchfield` | `tooltip-filter-searchfield` | Text del tooltip associat a l'element. | string | (cadena buida) |
| `tooltipSearchfield` | `tooltip-searchfield` | Text del tooltip associat a l'element. | string | (cadena buida) |

[discrepància: el PDF descriu `textTag` com a "Nivell de l'encapçalament HTML"; el lloc el descriu com a "Text de l'etiqueta"]
[discrepància: `selectorSearch` és obligatori al lloc; el PDF el descriu com a selector CSS de l'element àncora del cercador amb valor per defecte buit]
[discrepància: el lloc documenta les propietats `popoverConfigSearchfield`, `secondtButtonIcon`, `secondButtonText`, `showPopoverValueSearchfield`, `showTooltipSearchfield`, `textEtiquetaSearchfield`, `textInfoSearchfield`, `textInfoTooltipSearchfield` i `titleSearchfield`, que no apareixen al PDF v12.0.0; a verificar]
[a verificar: la propietat `secondtButtonIcon` (amb "t" sobrera) figura així al lloc, i el seu atribut s'escriu `second-button-icon` a l'exemple]

**Slots**
Els components següents s'introdueixen per slot:
- **Dropdown-menu:** a l'etiqueta HTML de `<dropdown-menu-component>` afegeix l'atribut `slot="dropdownMenu"`.
- **Buttons:** aquests botons formen part del component `group-button` que ja està introduït dins del component capçalera. S'ubiquen a la dreta del dropdown-menu. Cada botó ha de portar l'atribut `slot="groupButtons"`. Com a màxim es poden introduir tres botons en aquest slot; si se n'introdueixen més, saltarà un avís (warning) a la consola del navegador indicant aquesta limitació, tot i que es visualitzin tots els botons.

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `logoClick` | Esdeveniment llançat en pressionar el logo de la Generalitat superior esquerre de la capçalera (PDF: `CustomEvent<void>`, s'emet quan l'usuari fa clic al component) | --- | `header-component` |
| `secondButtonClick` | Esdeveniment llançat en fer clic al botó secundari ubicat sota el searchfield en breakpoints inferiors a 480px | --- | `head-component` |
| `valueChange` | Es llança cada vegada que es fa clic al botó de cerca o enter al camp de cerca | `value` | `searchfield-component` |
| `filterButtonClick` | Detecta el clic al botó de filtre propagant el seu ID | `ID` | `searchfield-component` |
| `handlerClick` | Es llança cada cop que es fa clic en un botó i com a paràmetre conté les dades de l'esdeveniment | id | `button-component` |
| `focusButton` | Es llança cada cop que es fa focus en un botó | --- | `button-component` |
| `blurButton` | Es llança cada cop que es treu el focus en un botó | --- | `button-component` |
| `tabSelectedSection2` | Esdeveniment llançat en seleccionar algun element de la secció 2 del menú desplegable | `index` | `dropdown-menu-component` |
| `tabSelectedSection3` | Esdeveniment llançat en seleccionar algun element de la secció 3 del menú desplegable | `index` | `dropdown-menu-component` |

**Depèn de:** `divider-component` ([Divisor](component-divisor.md)), `tag-component` ([Etiquetes](component-etiquetes.md)), `searchfield-component` ([Camp de cerca](component-camp-de-cerca.md)), `button-component` ([Botons](component-botons.md)), `dropdown-menu-component` ([Menú desplegable](component-menu-desplegable.md)), `group-button-component` ([Grup de botons](component-grup-de-botons.md)). [El PDF llista com a dependències `divider-component`, `tag-component`, `searchfield-component` i `group-button-component`.]

**Props que accepten JSON:** `dataSearchfield` (array d'objectes en string JSON), `dataKeyFieldSearchfield` (string o array, p. ex. `'["name", "email"]'`); a l'exemple, el component fill `dropdown-menu-component` rep `options-section-two` i `options-section-three` en JSON.

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<header-component 
  title-head="Title" 
  subtitle-head="Subtitle" 
  text-tag="PRE" 
  button-filter-searchfield=true
  text-button-filter-searchfield="Filtrar" 
  tooltip-searchfield="Tooltip de la cerca"
  tooltip-filter-searchfield="Tooltip del filtre"
  selector-search="h2"
  show-searchfield="true"
  second-button-text="Ajuda"
  second-button-icon="bi-question-circle"
  searchfield-value="" 
  searchfield-id="searchfield-id" 
  searchfield-name="searchfield-name" 
  data-url-searchfield='https://jsonplaceholder.typicode.com/users'
  data-searchfield="https://jsonplaceholder.typicode.com/users"
  data-key-field-searchfield='["name", "email"]'>
  <dropdown-menu-component 
    slot="dropdownMenu" 
    text-button="Menu" 
    description-button="Descripció" 
    icon-button="true" 
    size-button="small"
    nom="Nom" 
    rol="Rol"
    departament="Departament"
    date-last-session="Últim accés: 25/11/2024" 
    title-section-two="Títol"
    options-section-two='[
      {"title": "Pestanya", "tabSelected": "true", "isBadge": true, "numberBadge": "3", "iconState": "complete", "iconPrevText": "bi-bar-chart"},
      {"title": "Pestanya"},
      {"title": "Pestanya"},
      {"title": "Pestanya"},
      {"title": "Pestanya", "iconPrevText": "bi-bar-chart", "isDropdown": true, "dropdownContent": [
        { "id": "1", 
          "tabSelected": false, 
          "iconPrevText": "bi-clipboard-data", 
          "text": "Subpestanya 1", 
          "isBadge": false, 
          "numberBadge": "", 
          "iconState": "", 
          "tag": ""
        }, 
        { "id": "2", 
          "tabSelected": false, 
          "iconPrevText": "bi-clipboard-data", 
          "text": "Subpestanya 2", 
          "isBadge": false, 
          "numberBadge": "", 
          "iconState": "", 
          "tag": ""
        }, 
        { "id": "3", 
          "tabSelected": false, 
          "iconPrevText": "bi-clipboard-data", 
          "text": "Subpestanya 3", 
          "isBadge": false, 
          "numberBadge": "", 
          "iconState": "", 
          "tag": ""
        }
      ]
    }]' 
    title-section-three="Títol"
    options-section-three='[{"title": "Opció", "iconClass": "bi-copy"},{"title": "Opció", "iconClass": "bi-copy"},{"title": "Opció", "iconClass": "bi-copy"},{"title": "Opció", "iconClass": "bi-copy"},{"title": "Opció", "iconClass": "bi-copy"}]'
    mode-section-three="actions" 
    footer-button="true" 
    icon-state-options-section-two="true"
    icon-prev-options-section-two="true" 
    show-more-button-section-two="true" 
    show-more-button-section-three="true">
    <button-component 
      slot="footerButton" 
      class-name-button="btn-tertiary" 
      class-name-icon="" 
      size-button="btn-size-M"
      mode-color-button="mode-color-tertiary-light" 
      text="Tanca la sessió" 
      left-icon-chevron="false"
      right-icon-chevron="false" 
      left-icon=false 
      right-icon=false 
      text-tooltip="" 
      is-spinner=false
      custom-id="log-out-button"
    >
    </button-component>
  </dropdown-menu-component>
    <button-component 
      slot="groupButtons" 
      class-name-button="icn-btn-tertiary" 
      class-name-icon="bi-bell" 
      size-button="icn-btn-size-S"
      mode-color-button="mode-color-tertiary-grey" 
      left-icon-chevron="false" 
      right-icon-chevron="false"
      left-icon=true right-icon=false 
      is-spinner=false 
      custom-id="first-button">
    </button-component>
    <button-component 
      slot="groupButtons" 
      class-name-button="icn-btn-tertiary" 
      class-name-icon="bi-question-circle" 
      size-button="icn-btn-size-S"
      mode-color-button="mode-color-tertiary-grey" 
      left-icon-chevron="false" 
      right-icon-chevron="false"
      left-icon=true 
      right-icon=false 
      is-spinner=false 
      custom-id="second-button"
    >
    </button-component>
    <dropdown-button-component 
      slot="groupButtons" 
      class-name-button="icn-btn-tertiary" 
      class-name-icon="bi-three-dots-vertical"
      size-button="icn-btn-size-S"
      mode-color-button="mode-color-tertiary-grey" 
      right-icon="true" 
      text-tooltip="" 
      custom-id="dropdown1"
      options='[
        { "label": "Opción 1", "id": "1", "icon": "bi-copy" },
        { "label": "Opción 2", "id": "2", "icon": "bi-copy" },
        { "label": "Opción 3", "id": "3", "icon": "bi-copy" }
      ]'></dropdown-button-component>
</header-component>
```

**Exemple d'instància (PDF)**

```html
<header-component
button-filter-searchfield=false
data-key-field-searchfield='text'
data-searchfield='[]'
data-url-searchfield=''
searchfield-id=''
searchfield-name=''
searchfield-value=''
selector-search=''
show-searchfield=true
subtitle-head=''
text-button-filter-searchfield=''
text-tag=''
title-head=''
tooltip-filter-searchfield=''
tooltip-searchfield=''
></header-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 10.0.0 | 12.1.2 | 5 octubre, 2026 | Desenvolupament: s'elimina l'atribut textTooltipIconSearchfield |
| 12.4.0 | 12.1.0 | 09 setembre, 2026 | Disseny: es modifica el camp de cerca de la variant "Medium" del Menu a la versió desktop en el punt de tall més petit ("small") |
| 12.2.0 | 12.1.0 | 7 setembre, 2026 | Desenvolupament: s'introdueix l'opció d'ancorar el menú horitzontal i s'afegeixen les propietats del searchfield que faltaven |
| 12.3.0 | 10.0.0 | 31 juliol, 2026 | Disseny: es revisa que totes les capes estiguin en Fill/Hug segons convingui; es configura el min width de 1440 px a Extra Large Column Variable |
| 12.2.0 | 10.0.0 | 10 juliol, 2026 | Disseny: s'afegeixen les versions medium i small de la capçalera, així com les variants medium i small amb els nivells de navegació First level i Second-third level del menú |
| 12.0.0 | 10.0.0 | 29 maig, 2026 | Disseny: es mostra el logotip per defecte; s'adapta la versió pel punt de tall large per a tenir suficient espai per tots els elements; el camp de cerca en punt de tall Large passa a ser un llençol |
| 8.6.0 | 10.0.0 | 8 maig, 2026 | Desenvolupament: s'emet un esdeveniment quan es fa clic al logotip de la Generalitat |
| 8.6.0 | 9.2.0 | 27 febrer, 2026 | Desenvolupament: s'afegeixen les tres propietats noves del searchfield per carregar dades des d'un backend; s'eliminen les propietats nameUser, nameUserDropdown, rolUser, departamentUser, lastAccessUser, titleSectionTwo, optionsSectionTwo, titleSectionThree, optionsSectionThree, titleSectionTwoOptional, optionsSectionTwoOptional, titleSectionThreeOptional, options (ara el dropdown-menu s'introdueix per slot); s'eliminen les propietats notificationBell, tooltipIconQuestion, iconOptional, iconDots, tooltipBell (ara els tres botons a la dreta del dropdown s'introdueixen mitjançant un slot) |
| 8.6.0 | 9.1.0 | 9 febrer, 2026 | Disseny: s'afegeix l'opció d'amagar el camp de cerca |
| 8.3.0 | 9.1.0 | 6 febrer, 2026 | Desenvolupament: s'elimina la property placeholder Search; s'afegeix property que permet amagar o mostrar el searchfield |
| 8.3.0 | 6.2.1 | 14 novembre, 2025 | Disseny: s'ha aplicat la variable de color de fons |
| 8.2.0 | 6.2.1 | 27 octubre, 2025 | Disseny: revisió d'estils tipogràfics |
| 6.0.0 | 6.2.1 | 3 octubre, 2025 | Desenvolupament: nova propietat afegida o eliminada |
| 6.0.0 | 6.1.0 | 12 setembre, 2025 | Desenvolupament: nova propietat afegida |
| 6.0.0 | 5.0.0 | 8 juliol, 2025 | Disseny: se substitueix el botó de menú d'icona pel botó d'icona |
| 2.4.0 | 5.0.0 | 9 juny, 2025 | Desenvolupament: resolució de problemes |
| 2.4.0 | 3.0.0 | 28 abril, 2025 | Desenvolupament: resolució de problemes |
| 2.4.0 | 2.0.0 | 10 març, 2025 | Disseny: s'elimina el menú desplegable del component |
| 2.3.0 | 2.0.0 | 7 març, 2025 | Desenvolupament: resolució de problemes |
| 2.3.0 | 1.0.0 | 31 gener, 2025 | Desenvolupament del component |
| 2.2.0 | No aplica | 20 gener, 2025 | Sense canvis |
| 2.1.0 | No aplica | 4 desembre, 2024 | Disseny i documentació del component |

## Vegeu també
- [Menú horitzontal](component-menu-horitzontal.md): per navegar pels elements principals de la pàgina.
- [Camp de cerca](component-camp-de-cerca.md): per a realitzar cerques o explorar un lloc web o aplicació.
- [Insígnia](component-insignia.md): per a cridar l'atenció dels usuaris sobre un element en la pàgina.
- [Etiquetes](component-etiquetes.md): per mostrar l'estat d'un element, les propietats clau o les categories.
- [Menú desplegable](component-menu-desplegable.md)
- [Grup de botons](component-grup-de-botons.md)
- [Capçalera web pública](component-capcalera-web-publica.md)
- [Capçalera secundària de BO](component-capcalera-secundaria-de-bo.md)
