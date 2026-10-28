# Capçalera web pública (Public Website Header)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/477d4f · Web component: `<header-public-component>` (paquet core) · Font actualitzada el 2026-10-20 · Extret el 2026-10-28

## Què és i quan usar-lo
Una capçalera és la secció superior d'una pàgina web que proporciona un lloc coherent per a la marca, la navegació i l'accés a funcionalitats globals, com la cerca o l'accés a l'àrea privada.

Aquesta capçalera està pensada per a la **part pública de les webs**. Segons la web en què es trobi, hi ha aquestes tipologies (la font diu "dues tipologies" però en llista sis):
- **Capçalera web principal Gencat:** s'utilitza exclusivament en el lloc [web Gencat.cat](https://web.gencat.cat/ca/inici).
- **Capçalera webs corporatives:** es fa servir en llocs web que segueixen l'estil del Sistema de Disseny de la Generalitat de Catalunya.
- **Capçalera web amb estil propi:** s'utilitza en llocs web de la Generalitat de Catalunya que, tot i mantenir els criteris bàsics d'identificació institucional, disposen d'un disseny visual propi adaptat a la seva identitat, funció o públic objectiu.
- **Capçalera d'àrea privada de web corporativa:** s'utilitza a les àrees privades del lloc web públic de la Generalitat de Catalunya.
- **Capçalera d'àrea privada web amb estil propi:** s'utilitza a les àrees privades de llocs web de la Generalitat de Catalunya amb estil visual propi (per exemple, "La meva salut", ATC, etc.).
- **Capçalera pre àrea privada, tramitació o pre tramitació:** capçalera per a pàgines prèvies a una àrea privada o a l'inici d'un procés de tramitació. Ajuda a contextualitzar el servei i facilita l'accés o la continuïtat cap al procés principal.

## Quan NO usar-lo / alternatives
No s'ha d'utilitzar en aplicacions internes o espais transaccionals amb necessitats específiques diferents (vegeu [Capçalera per aplicacions internes](component-capcalera-per-aplicacions-internes.md)).

## Anatomia

### Capçalera web Gencat
1. **Barra de navegació principal:** permet canviar entre espais. És escalable, mostrant més o menys espais segons les necessitats.
2. **Identitat visual:** logotip de la Generalitat de Catalunya.
3. **Nom de l'espai actiu:** indica en quin espai es troba l'usuari.
4. **Menú horitzontal:** vegeu [Menú horitzontal](component-menu-horitzontal.md).
5. **Accés a la Seu Electrònica.**
6. **Accés a "T'atenem".**
7. **Selector d'idioma.**
8. **Cerca:** botó que obre el cercador.
9. **Àrea privada:** botó destacat en vermell per accedir a l'àrea privada.

### Capçalera web corporativa
1. **Identitat visual:** logotip de la Generalitat de Catalunya.
2. **Nom del departament o organisme.**
3. **Menú horitzontal:** [Menú horitzontal](component-menu-horitzontal.md).
4. **Accés a "T'atenem".**
5. **Selector d'idioma.**
6. **Cerca:** botó que obre el cercador.
7. **Accés a espais privats (opcional):** el nom que s'utilitza ha de ser el que inclou l'acord de govern ([Document oficial de la Generalitat (DOGC)](https://dogc.gencat.cat/ca/document-del-dogc/?documentId=988475)). Els espais privats digitals com *El meu espai ATC*, *La Meva Salut* i *La meva carpeta judicial* han de seguir les directrius d'identitat corporativa. No s'ha de fer servir el concepte d'àrea privada per referir-se a aquests espais.

### Capçalera web amb estil propi
1. **Identitat visual:** logotip de la Generalitat de Catalunya.
2. **Logotip del departament o organisme.**
3. **Nom del departament o organisme.**
4. **Menú horitzontal:** [Menú horitzontal](component-menu-horitzontal.md).
5. **Accés a "T'atenem".**
6. **Selector d'idioma.**
7. **Cerca:** botó que obre el cercador amb el color corresponent al departament o organisme.
8. **Accés a espais privats (opcional).**

### Capçalera d'àrea privada, web corporativa
1. **Identitat visual:** logotip de la Generalitat de Catalunya.
2. **Nom del departament o organisme.**
3. **Accés a "T'atenem".**
4. **Selector d'idioma.**
5. **Accés als espais:** botó que obre una finestra modal amb l'accés als diferents espais del portal.
6. **Cerca:** botó que obre el cercador amb el color corresponent al departament o organisme.
7. **Perfil de l'espai privat:** desplegable que obre un menú amb les opcions de l'usuari.
8. **Franja vermella posterior.**

### Capçalera d'àrea privada, web amb estil propi
1. **Identitat visual:** logotip de la Generalitat de Catalunya.
2. **Logotip del web propi.**
3. **Nom del departament o organisme.**
4. **Accés a "T'atenem".**
5. **Selector d'idioma.**
6. **Accés als espais:** botó que obre una finestra modal amb l'accés als diferents espais del portal.
7. **Cerca:** botó que obre el cercador.
8. **Perfil de l'espai privat:** desplegable que obre un menú amb les opcions de l'usuari.
9. **Franja posterior:** el color de la franja variarà en funció de l'espai web, utilitzant el color primari corresponent.

### Web pre àrea privada, pre tramitació, tramitació
1. **Identitat visual:** logotip de la Generalitat de Catalunya.
2. **Nom del departament o organisme (opcional).**
3. **Accés a "T'atenem".**
4. **Selector d'idioma.**
5. **Perfil de l'espai privat (opcional):** desplegable que obre un menú amb les opcions de l'usuari.
6. **Franja posterior:** el color de la franja variarà en funció de l'espai web, utilitzant el color primari corresponent.

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Type | web Gencat / web corporativa / web amb estil propi / Àrea privada - web amb estil propi / Àrea privada / Pre àrea privada, Pre tramitació, Tramitació | web Gencat |
| Breakpoint | Extra Large Column Fixed / Extra Large Column Variable / Large / Medium / Small | Extra Large Column Fixed |
| Show search button | True / False | True |
| Show private area button | True / False | True |
| Show profile menu | True / False | True |
| Show website name | True / False | True |
| Header logos | Placeholder / Salut / La meva salut / Santa Mònica / ATC | Placeholder |

Variants Figma: Public Website Header [Web name = Nom web, Show search button = True, Logo slot ... Logo slot10 (slots de logotip), Show profile menu = True, Show website name = True, Show private area button = True, Type = web gencat, Breakpoint = Extra Large Column Fixed].

Modes del component web: `gencat-web` (per defecte), `corporate-web`, `own-style-web`, `private-area-corporate-web`, `private-area-own-style-web`, `pre-private-area`, `pre-processing`, `processing`.

## Mides i espaiats
- Per a pantalles inferiors a 359 píxels d'amplada (dispositius mòbils), el logotip de la Generalitat se simplifica i es converteix en isotip.
- Truncats: l'espai disponible per al nom de la capçalera s'adapta segons la mida de la pantalla. Quan no hi ha prou espai, es truncarà. Com a màxim, ocuparà **dues línies de text**.

## Comportament i interacció
### Posició
La capçalera es col·loca a la part superior de la pàgina i té un comportament diferenciat segons la mida de la pantalla.
- **Extra Large Column Fixed / Extra Large Column Variable / Large:** la capçalera es manté fixa a la part superior de la pàgina quan es carrega, però no és persistent en desplaçar-se. Això vol dir que, quan l'usuari es desplaça cap avall, la capçalera desapareix de la vista i no acompanya el contingut.
- **Medium / Small:** la capçalera es desplaça amb el contingut durant la navegació i es torna a mostrar quan l'usuari fa scroll cap amunt, per facilitar l'accés als elements principals de navegació.

### Adaptació responsiva
- En dispositius mòbils, per a pantalles inferiors a 359 píxels d'amplada, el logotip de la Generalitat se simplifica i es converteix en isotip.
- En el cas de les capçaleres de l'àrea privada, el desplegable del perfil es presenta de forma simplificada amb la icona i el *galó (chevron)* en els punts de tall *medium - small*.
- La font inclou imatges Figma de breakpoints per a: web Gencat, web amb estil propi, web àrea privada i cercador; i una conceptualització modal i desplegable (àrea privada).

### Configuració d'idioma
El **selector d'idioma** mostra l'abreviatura "CA" per al català. En fer clic, apareix un [Menú desplegable](component-menu-desplegable.md) amb les opcions d'idioma. En seleccionar-ne un, l'abreviatura canvia i la interfície s'adapta a l'idioma seleccionat. Abreviatures:
- **CA** = Català
- **ES** = Castellano
- **EN** = English (Automatically translated)
- **OC** = Occità aranès

Per a la capçalera web corporativa, el selector d'idioma es comporta exactament igual que el de la capçalera web Gencat.

## Bones pràctiques
Una capçalera per pàgina:
- **FER:** Utilitza només una capçalera per pàgina.
- **NO FER:** No utilitzis múltiples capçaleres en una sola pàgina.

Menú de navegació:
- **FER:** Els títols del menú de navegació han de ser curts i clars per facilitar la comprensió i l'accés ràpid a les seccions.
- **NO FER:** No utilitzis títols llargs o confusos que puguin dificultar la navegació.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG):
- **Ús del color (A)** — [1.4.1](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color): el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a indicar els diferents canvis d'estat, es modifiquen els píxels de la vora del component i/o s'afegeixen elements complementaris com la segona vora pel focus o la icona i el text d'error.
- **Contrast mínim (AA)** — [1.4.3](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum): els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són excepció d'aquesta norma.
- **Canvia la mida del text (AA)** — [1.4.4](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text): excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat.
- **Contrast d'elements no textuals (AA)** — [1.4.11](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast): els elements gràfics com icones i vores presenten un contrast mínim de 3:1.
- **Teclat (A)** — [2.1.1](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard): tota la funcionalitat del contingut es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals.
- **Focus visible (AA)** — [2.4.7](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible): la navegació als elements interactius és visible mitjançant un rectangle extern.
- **Focus no ocult (AA)** — [2.4.11](https://www.w3.org/Translations/WCAG22-ca/#focus-not-obscured-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-not-obscured-minimum): la capçalera, en ser un element fix a la part superior de la pàgina, no pot ocultar cap element que tingui el focus de teclat durant el desplaçament de la pàgina. Això inclou el comportament de reaparició de la capçalera en fer desplaçament cap amunt (*sticky reveal*), que tampoc pot ocultar cap element enfocat en aquell moment. Aquesta consideració és especialment rellevant en dispositius mòbils i tauletes amb zoom de pantalla activat, ja que la capçalera ocupa proporcionalment més espai de la pantalla visible.

## Implementació (component web)

### `<header-public-component>`
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatori |
|---|---|---|---|---|---|
| `cardsMoreSpacesButton` | `cards-more-spaces-button` | En cas que se seleccioni el mode `private-area-corporate-web` o `private-area-own-style-web`, cal proporcionar un llistat dels espais a introduir al modal que s'obre en prémer el botó "Els meus espais" (configuració o contingut de la targeta). | string (array) | undefined | Opcional |
| `dataKeySearchfield` | `data-key-searchfield` | Carrega les dades del searchfield mitjançant URL, indica les columnes que cal prendre. | string o string (array) | [a verificar: no consta al PDF] | Opcional |
| `dataSearchfield` | `data-searchfield` | Permet carregar dades no gaire grans en un string (array) del component searchfield de la capçalera. | string (array) | [a verificar: no consta al PDF] | Opcional |
| `dataUrlSearchfield` | `data-url-searchfield` | Permet carregar dades grans per al cercador de la capçalera mitjançant un URL connectat a backend. | string | [a verificar: no consta al PDF] | Opcional |
| `etiquetaSearchfield` | `etiqueta-searchfield` | Text de l'etiqueta del camp de cerca (etiqueta descriptiva del camp de cerca). | string | undefined | Obligatori |
| `headerTopBar` | `header-top-bar` | Pestanyes de la capçalera ubicades a sobre del logo i nom corporatiu (configuració de la barra superior de capçalera). | string (array) | undefined | Obligatori |
| `languageSelector` | `language-selector` | Llistat dels idiomes disponibles (configuració del selector d'idioma). Accepta objecte o string JSON. | string (array) | undefined | Obligatori |
| `mode` | `mode` | Configuració de la capçalera (variant visual). Opcions: `corporate-web`, `gencat-web`, `own-style-web`, `pre-private-area`, `pre-processing`, `private-area-corporate-web`, `private-area-own-style-web`, `processing`. | string | `gencat-web` | Obligatori |
| `nomWeb` | `nom-web` | Nom de l'aplicació (nom del lloc web). | string | `` (buit) | Obligatori |
| `ownLogo` | `own-logo` | En el cas que se seleccioni el mode `own-style-web` o `private-area-own-style-web`, cal proporcionar el logotip propi en aquesta propietat (URL o configuració del logotip). | string | undefined | Opcional |
| `popoverConfigSearchfield` | `popover-config-searchfield` | Propietats per al component popover del camp de cerca. Accepta objecte o string JSON. | string (array) | `{}` | Opcional |
| `selectorSearchfield` | `selector-searchfield` | Selector per al camp de cerca de la capçalera (selector CSS de l'element àncora del camp de cerca). | string | undefined | Obligatori |
| `showButtonFilterSearchfield` | `show-button-filter-searchfield` | Permet mostrar o amagar el botó de filtre del camp de cerca. | boolean | [a verificar: no consta al PDF] | Opcional |
| `showEtiquetaSearchfield` | `show-etiqueta-searchfield` | Permet mostrar o amagar l'etiqueta del camp de cerca. | boolean | [a verificar: no consta al PDF] | Opcional |
| `showPopoverSearchfield` | `show-popover-searchfield` | Permet mostrar o ocultar la notificació emergent del camp de cerca. | boolean | [a verificar: no consta al PDF] | Opcional |
| `showTooltipSearchfield` | `show-tooltip-searchfield` | Permet mostrar o amagar la icona amb tooltip del camp de cerca. | boolean | [a verificar: no consta al PDF] | Opcional |
| `showUser` | `show-user` | Indica si es mostra el login, només vàlid per als modes `pre-private-area`, `pre-processing` i `processing`. | boolean | true | Opcional |
| `textButtonFilterSearchfield` | `text-button-filter-searchfield` | Text del botó de filtrar del camp de cerca. | string | [a verificar: no consta al PDF] | Opcional |
| `textInfoSearchfield` | `text-info-searchfield` | Text descriptiu sota el camp de cerca. | string | undefined | Opcional |
| `textTooltipSearchfield` | `text-tooltip-searchfield` | Text del tooltip de la icona informativa del component de cerca. | string | undefined | Opcional |
| `titleSearchfield` | `title-searchfield` | Títol del camp de cerca. | string | undefined | Obligatori |
| `tooltipButtonFilter` | `tooltip-button-filter` | Text del tooltip del botó de filtrar del camp de cerca. | string | [a verificar: no consta al PDF] | Opcional |
| `tooltipButtonSearch` | `tooltip-button-search` | Text del tooltip del botó de cerca del camp de cerca. | string | [a verificar: no consta al PDF] | Opcional |
| `valueSearchfield` | `value-searchfield` | Valor d'input de tipus text per al camp de cerca (valor actual). | string | undefined | Opcional |

**Propietats de `languageSelector`**

| Propietat | Descripció | Atribut | Obligatori | Tipus |
|---|---|---|---|---|
| `iso` | ISO del llenguatge | `iso` | Obligatori | String |
| `title` | Títol visible al desplegable | `title` | Obligatori | String |
| `active` | Indica si és el llenguatge actiu | `active` | Obligatori | String |
| `translatedText` | Text tipus (Automàticament traduït) que apareix al costat de title | `translatedText` | Opcional | String |

**Propietats de `headerTopBar`**

| Propietat | Descripció | Atribut | Obligatori | Tipus |
|---|---|---|---|---|
| `text` | Text visible de la pestanya | `text` | Obligatori | String |
| `active` | Indica si és la pestanya activa | `active` | Obligatori | boolean |

[a verificar: l'exemple de codi de la font usa `title` en lloc de `text` als elements de `header-top-bar`]

**Propietats de `cardsMoreSpacesButton`**

| Propietat | Descripció | Atribut | Obligatori | Tipus |
|---|---|---|---|---|
| `title` | Títol de la targeta | `title` | Obligatori | String |
| `icon` | Icona de la targeta | `icon` | Obligatori | String |
| `section` | Secció on s'introduirà la targeta. Pot ser `transversal` o `sectorial` | `section` | Obligatori | String |

**Variants**

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `mode` | `gencat-web` `corporate-web` `own-style-web` `private-area-corporate-web` `private-area-own-style-web` `pre-private-area` `pre-processing` `processing` | `gencat-web` |
| `showUser` | `true` `false` | `true` |

**Slots**

Components que s'introdueixen per slot:
- **Dropdown-menu:** serà necessari quan s'utilitzi la capçalera en mode `private-area-own-style-web` o `private-area-corporate-web`. L'etiqueta `<dropdown-menu-component>` ha de contenir l'atribut `slot="user-menu"` (vegeu [Menú desplegable](component-menu-desplegable.md)).

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `handlerClick` | Esdeveniment llançat en fer clic sobre algun dels botons | `id` | `button-component` |
| `focusButton` | Esdeveniment llançat en fer focus sobre algun dels botons. | - | `button-component` |
| `button-component` | Esdeveniment llançat en treure el focus d'algun dels botons [sic: el lloc llista aquest nom d'esdeveniment; probablement `blurButton`; a verificar]. | - | `button-component` |
| `languageSelected` | Esdeveniment llançat en seleccionar un llenguatge al desplegable (`CustomEvent<String>`) | `iso` | `header-public-component` |
| `linkEmit` | Esdeveniment llançat en fer clic sobre l'enllaç | `id` | `link-component` |
| `focusLink` | Esdeveniment llançat en fer focus sobre l'enllaç. | - | `link-component` |
| `blurLink` | Es llança cada cop que es treu el focus de l'enllaç. | - | `link-component` |
| `logoClicked` | Esdeveniment llançat en fer clic al logo de la capçalera | Tipus de logo: `gencat` `own-style` | `header-public-component` |
| `topBarSelected` | Esdeveniment llançat en seleccionar alguna pestanya ubicada a la barra superior a l'esquerra (`CustomEvent<Number>`) | `index` | `header-public-component` |
| `valueChange` | Es llança cada vegada que es fa clic al botó de cerca o enter al camp de cerca | `value` | `searchfield-component` |
| `filterButtonClick` | Detecta el clic al botó de filtre propagant el seu ID | `ID` | `searchfield-component` |

**Depèn de:** `divider-component` ([Divisor](component-divisor.md)), `searchfield-component` ([Camp de cerca](component-camp-de-cerca.md)), `link-component` ([Enllaços](component-enllacos.md)), `button-component` ([Botons](component-botons.md)), `card-navigation-basic-component` ([Targetes](component-targetes.md)), `modal-component` ([Modals](component-modals.md)).

**Exemple d'ús**

```html
<!-- /index.html -->
<header-public-component 
  mode="gencat-web"
  nom-web="Nom del web"
  own-logo="https://example.com/logo.svg"
  show-user="true"
  language-selector='[
    { "iso": "CA", "title": "Català", "active": "true", "translatedText": "Català" },
    { "iso": "ES", "title": "Castellano", "active": "false", "translatedText": "Castellano" },
    { "iso": "EN", "title": "English", "active": "false", "translatedText": "English" }
  ]'
  header-top-bar='[
    { "title": "Tema 1", "active": true },
    { "title": "Tema 2", "active": false },
    { "title": "Tema 3", "active": false }
  ]'
  cards-more-spaces-button='[
    { "title": "Espai 1", "icon": "bi-file-earmark-text", "section": "transversal" },
    { "title": "Espai 2", "icon": "bi-person", "section": "sectorial" }
  ]'
  title-searchfield="Cercar"
  value-searchfield=""
  show-etiqueta-searchfield="false"
  etiqueta-searchfield="Etiqueta"
  selector-searchfield="h2"
  tooltip-button-search="Cerca"
  data-searchfield='[{ "name": "Resultat 1" }, { "name": "Resultat 2" }]'
  data-key-searchfield='["name"]'
  data-url-searchfield="https://example.com/api/search"
  show-popover-searchfield="false"
  popover-config-searchfield='{}'
  show-button-filter-searchfield="false"
  text-button-filter-searchfield="Filtrar"
  tooltip-button-filter="Filtra els resultats"
  text-info-searchfield="Text informatiu"
  show-tooltip-searchfield="false"
  text-tooltip-searchfield="Tooltip del cercador"
>
  <dropdown-menu-component slot="user-menu" text-button="Menu" description-button="Descripció" icon-button="true" size-button="small"
    nom="Nom" rol="Rol" departament="Departament" date-last-session="Últim accés: 25/11/2024" title-section-two="Títol"
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
        custom-id="log-out-button">
      </button-component>
  </dropdown-menu-component>
</header-public-component>
```

Exemple d'instància del PDF:

```html
<header-public-component
cards-more-spaces-button="texto-ejemplo"
etiqueta-searchfield="texto-ejemplo"
header-top-bar="texto-ejemplo"
language-selector="texto-ejemplo"
mode='gencat-web'
nom-web=''
own-logo="texto-ejemplo"
popover-config-searchfield='{}'
selector-searchfield="texto-ejemplo"
show-user=true
text-info-searchfield="texto-ejemplo"
text-tooltip-searchfield="texto-ejemplo"
title-searchfield="texto-ejemplo"
value-searchfield="texto-ejemplo"
></header-public-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.0.0 | 12.1.1 | 5 octubre, 2026 | **Desenvolupament**: Es corregeix el bloqueig de l'scroll vertical en tancar el camp de cerca / Ajustos d'accessibilitat |
| 12.0.0 | 12.1.1 | 11 setembre, 2026 | **Desenvolupament**: Corregida la ruta de la icona chevron del selector d'idioma / Eliminat console.log |
| 12.0.0 | 12.1.0 | 7 setembre, 2026 | **Desenvolupament:** Es corregeix l'error de focus del component SearchField. / Ajustos d'estil i noves propietats. / S'afegeixen noves propietats per al component SearchField. |
| 12.0.0 | 12.0.0 | 10 juliol, 2026 | **Desenvolupament**: ajustos d'accessibilitat |
| 12.0.0 | 11.0.0 | 19 juny, 2026 | **Desenvolupament**: Afegir propietat showUser / Afegir el component SearchField al botó de cerca / Correcció del background del selector d'idioma / Ajustos d'accessibilitat |
| 12.0.0 | 10.1.0 | 29 maig, 2025 [sic; probablement 2026] | **Disseny**: Es crea el component per al llençol del camp de cerca. **Desenvolupament**: S'afegeixen tres nous modes: pre-private-area, pre-processing i processing / S'elimina getAssetPath |
| 11.0.0 | 10.0.0 | 8 maig, 2026 | **Disseny:** S'afegeix la variant de capçalera de pre àrea privada / pre tramitació / tramitació. **Desenvolupament**: S'emet un esdeveniment quan es fa clic al logotip de la Generalitat / S'ajusta la vista de les cards del botó Els meus espais / S'habilita ruta configurable amb setAssetPath() i millores d'accessibilitat |
| 10.0.0 | 9.2.0 | 17 abril, 2026 | **Disseny**: S'aplica slot per afegir el logotip a les capçaleres per webs amb estil propi. |
| 9.0.0 | 9.2.0 | 27 febrer, 2026 | **Disseny**: S'ha modificat el color dels botons de les variants web amb estil propi. |
| 8.6.0 | 9.2.0 | 27 febrer, 2026 | **Desenvolupament**: S'elimina la propietat linksTopBar, buttonSearch i buttonLogin i s'hi afegeixen les propietats mode, ownLogo i cardsMoreSpacesButton. / S'hi afegeix un botó en mode private-àrea anomenat "Els meus espais" que obre una modal amb cards. / S'introdueix mitjançant slot dropdown-menu per als mode private-àrea. / Entre els diferents modes canvia l'aspecte del header-public. |
| 8.6.0 | 9.1.0 | 9 febrer, 2026 | **Disseny**: S'han dissenyat dues capçaleres d'àrea privada, per la web pública i la d'estil propi. |
| 8.5.0 | 9.1.0 | 6 febrer, 2026 | **Desenvolupament**: Es fan adaptacions d'accessibilitat pel que fa a mides de font extra gran i augment de pantalla |
| 8.5.0 | 8.0.0 | 20 gener, 2026 | **Disseny:** S'ha dissenyat la capçalera de web pública amb estil propi. |
| 8.2.0 | 8.0.0 | 14 novembre, 2025 | **Desenvolupament**: Nova propietat afegida |
| 8.1.1 | 6.2.1 | 27 octubre, 2025 | **Disseny**: S'ha ajustat l'amplada del menú d'idioma i les seves opcions a dins. S'afegeix el text "Automatically trasnlated" a l'opció d'idioma anglès. |
| 7.0.0 | 6.2.1 | 3 octubre, 2025 | **Desenvolupament**: Nova propietat afegida o eliminada |
| 7.0.0 | 6.1.0 | 12 setembre, 2025 | **Desenvolupament**: Resolució de problemes |
| 7.0.0 | 6.0.1 | 28 juliol, 2025 | **Disseny**, **documentació i desenvolupament** del component |

## Vegeu també
- [Enllaços](component-enllacos.md): per facilitar la navegació entre parts del contingut o funcionalitats.
- [Menú horitzontal](component-menu-horitzontal.md): per navegar pels elements principals de la pàgina.
- [Pestanyes](component-pestanyes.md): per organitzar contingut relacionat en seccions o categories.
- [Menú desplegable](component-menu-desplegable.md)
- [Camp de cerca](component-camp-de-cerca.md)
- [Capçalera per aplicacions internes](component-capcalera-per-aplicacions-internes.md)
- [Àrea privada (exemple)](exemple-area-privada.md)
