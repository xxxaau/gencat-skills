# Menú desplegable (Dropdown menu)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/745c88 · Web component: `<dropdown-menu-component>` (paquet core) · Font actualitzada el 2026-10-15 · Extret el 2026-10-28

## Què és i quan usar-lo
Presenta una llista d'elements informatius o de navegació quan l'usuari fa clic sobre un element activador. Permet optimitzar l'ús de l'espai i mantenir una interfície neta, mostrant contingut addicional només quan és necessari.

El menú desplegable s'utilitza en diversos escenaris on cal seleccionar una opció entre diverses, organitzar continguts o accedir a funcionalitats de manera compacta. S'utilitzarà principalment per a donar accés a funcionalitats o configuracions en el context de l'etiqueta o icona a la qual acompanya. Per exemple, per a mostrar les opcions del perfil d'usuari o per seleccionar l'idioma d'un portal.

## Anatomia
El menú desplegable està format per:
1. **Botó desplegable.** Format per:
   1. Etiqueta: text del botó.
   2. Icona (opcional).
   3. Descripció (opcional).
   4. Chevron: indica si està replegat o desplegat segons la direcció.
2. **Secció informativa (opcional).** Inclou elements d'informació com:
   1. Nom d'usuari.
   2. Rol.
   3. Departament.
   4. Últim accés.
3. **Secció de selecció (opcional).** Per a canvis de visualització o entorns. Inclou:
   1. Títol.
   2. Pestanyes.
4. **Secció de navegació (opcional).** Per a elements de navegació relacionats amb el context de l'etiqueta del botó. Inclou:
   1. Títol.
   2. Enllaços i accions.
5. **Tanca sessió (opcional):** grup de botons amb la possibilitat d'afegir un segon botó.

## Variants, tipus i estats

### Botó desplegable

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Default / Hover / Focus | Default |
| Collapsed | True / False | True |
| Show Icon | True / False | - |
| Show Description | True / False | - |

Variants Figma: Menú desplegable [State = Default, Collapsed = True, Size = Medium] (en les dues vistes: Not Collapsed i Collapsed).

### Menú

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Desktop / Mobile | - |
| Show Information | True / False | True |
| Show selection panel | True / False | True |
| Show selection title | True / False | True |
| Show more button 01 | True / False | False |
| Show navigation panel | True / False | True |
| Show selection title (segona fila de la taula de la font) | True / False | True |
| Show more button 02 | True / False | False |
| Show End session | True / False | True |
| Show button group | True / False | True |
| Show scroll bar | True / False | False |

Variants Figma: Menú desplegable [Show Information = True, Show Selection panel = True, Show navigation panel = True, Show Group Button = True, ↳ Show Navigation Title = True, ↳ Show Selection Title = True, Show scroll bar = False, Show more button 01 = False, Show more button 02 = False, Breakpoint = Desktop].

### Menú desplegable

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Collapsed | True / False | True |

Variants Figma: Menú desplegable [Collapsed = True].

Estats d'`iconState` de les pestanyes (component web): `complete`, `urgent`, `inProgress`, `block`.

## Mides i espaiats
- El **text del botó** s'adapta al contingut; cal evitar textos massa llargs. L'amplada màxima ideal seria d'uns 144 px.
- **Opcions de navegació:** com a màxim, el text d'opció podrà contenir cent cinquanta caràcters. Si no hi ha espai suficient a la pantalla perquè el llistat creixi de forma horitzontal i el contingut del llistat d'opcions càpiga en una línia, els textos de les opcions podran saltar de línia.
- Mida del botó (component web): `medium` (per defecte) | `small`.
- Historial de disseny: reducció del padding esquerra de 8 a 4px (Figma 12.1.0).

## Comportament i interacció
- **Adaptació responsiva:** en punts de tall més petits (*mobile*), el contingut del desplegable apareix en un panell emergent inferior (*sheet*).
- **Tancament intuïtiu:** el menú ha de tancar-se automàticament quan l'usuari selecciona una opció o fa clic fora.
- Si l'usuari surt del menú en prémer la tecla de tabulació i passa al següent o anterior element interactiu de la pàgina, el menú es tancarà automàticament.
- Navegació per teclat:

| Tecla | Acció |
|---|---|
| Tabulació | Navegar al següent element interactiu. |
| Shift + Tabulació | Navegar a l'anterior element interactiu. |
| Intro / Enter | Obrir el menú. |
| Chevrons a baix i a dalt | Desplaçar-se per les diferents opcions interactives del menú. |
| Tecla Esc | Tancar el menú |

- El focus a la secció d'opcions 3 es desplaça només amb tab, no amb les fletxes del teclat (versió Github 10.1.0).

## Bones pràctiques
Claredat:
- **FER:** Utilitza un text clar o una icona significativa que indiqui la funció del menú.
- **NO FER:** No utilitzis etiquetes fora de context del menú.
- **NO FER:** No incloguis contingut excessivament llarg, intenta que el contingut sigui el mínim possible.

Context:
- **NO FER:** No mostris opcions que no tinguin rellevància segons el context d'ús.

Jerarquia i consistència:
- **FER:** Ordena les opcions segons la seva rellevància o ús més freqüent.
- **FER:** Utilitza el mateix estil de menú desplegable en tot el lloc web o aplicació per evitar confusions.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG):
- **Ús del color (A)** — [1.4.1](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color): el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a diferenciar els diferents estats s'inclouen subratllats, es juga amb la presència de farciment i el gruix de la vora.
- **Contrast mínim (AA)** — [1.4.3](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum): els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma.
- **Canvia la mida del text (AA)** — [1.4.4](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text): excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat.
- **Contrast d'elements no textuals (AA)** — [1.4.11](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast): els elements gràfics com icones i vores presenten un contrast mínim de 3:1.
- **Teclat (A)** — [2.1.1](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard): tota la funcionalitat del contingut (navegar pels diferents botons) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals.
- **Focus visible (AA)** — [2.4.7](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible): la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle.
- **Focus no ocult (AA)** — [2.4.11](https://www.w3.org/Translations/WCAG22-ca/#focus-not-obscured-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-not-obscured-minimum): en tancar-se el menú, el focus ha de tornar a l'element que el va activar. El menú no pot ocultar cap element que tingui el focus de teclat. Aquesta consideració és especialment rellevant en dispositius mòbils i tauletes amb zoom de pantalla activat.

Vegeu també la taula de navegació per teclat a "Comportament i interacció".

## Implementació (component web)

### `<dropdown-menu-component>`
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatori |
|---|---|---|---|---|---|
| `dateLastSession` | `date-last-session` | Data del darrer inici de sessió de l'usuari. | string | `` (buit) | Opcional |
| `departament` | `departament` | Departament de l'usuari. | string | `` (buit) | Opcional |
| `descriptionButton` | `description-button` | Descripció del botó. | string | `` (buit) | Opcional |
| `footerButton` | `footer-button` | Visibilitat del botó o botons del final del desplegable. S'introduiran per slot i poden ser un o més. Només s'accepta a l'slot botons. Els botons han de portar l'atribut `slot="footerButton"`. | boolean | false | Opcional |
| `iconButton` | `icon-button` | Visibilitat de la icona de l'interior del botó desplegable. | boolean | true | Opcional |
| `iconPrevOptionsSectionTwo` | `icon-prev-options-section-two` | Visibilitat de la icona prèvia de les pestanyes verticals de la secció 2. | boolean | false | Opcional |
| `iconStateOptionsSectionTwo` | `icon-state-options-section-two` | Visibilitat de la icona d'estat de les pestanyes verticals de la secció 2. | boolean | false | Opcional |
| `modeSectionThree` | `mode-section-three` | A la secció 3 els elements es poden veure com a opcions o com a accions. Variant de la tercera secció. Opcions: `options`, `actions`. | string | `options` | Opcional |
| `nom` | `nom` | Nom de l'usuari. | string | `` (buit) | Opcional |
| `optionsSectionThree` | `options-section-three` | Opcions de la tercera secció del desplegable. Només per al mode section three `actions`. | string (array) | undefined | Opcional |
| `optionsSectionTwo` | `options-section-two` | Opcions de la segona secció del desplegable. Aquesta propietat és reactiva per permetre modificar el `tabSelected` d'una pestanya quan es vulgui que estigui activa. | string (array) | undefined | Opcional |
| `rol` | `rol` | Rol de l'usuari. | string | `` (buit) | Opcional |
| `showMoreButtonSectionThree` | `show-more-button-section-three` | Visibilitat del botó mostrar més de la secció 3. | boolean | false | Opcional |
| `showMoreButtonSectionTwo` | `show-more-button-section-two` | Visibilitat del botó mostrar més de la secció 2. | boolean | false | Opcional |
| `sizeButton` | `size-button` | Grandària del botó. Opcions: `medium`, `small`. | string | `medium` | Opcional |
| `textButton` | `text-button` | Text del botó. | string | `` (buit) | Opcional |
| `titleSectionThree` | `title-section-three` | Títol de la tercera secció del desplegable. | string | undefined | Opcional |
| `titleSectionTwo` | `title-section-two` | Títol de la segona secció del desplegable. | string | undefined | Opcional |

**Propietats de l'array `optionsSectionTwo`**

| Propietat | Descripció | Atribut | Obligatorietat | Tipus |
|---|---|---|---|---|
| `description` | Descripció de la tab | `description` | Opcional | String |
| `dropdownContent` | Si la tab és un dropdown, aquí caldrà introduir-ne el contingut | `dropdownContent` | Opcional | String (array) |
| `iconPrevText` | Icona prèvia al text de la tab. Cal utilitzar una classe de la biblioteca d'icones de Bootstrap | `iconPrevText` | Opcional | String |
| `iconState` | Si la tab té estat, cal indicar-la aquí | `iconState` | Opcional | String |
| `isBadge` | Indica si la tab conté badge | `isBadge` | Opcional | Boolean |
| `isDropdown` | Indica si aquesta tab és un dropdown vertical o no | `isDropdown` | Obligatori | Boolean |
| `numberBadge` | En cas que el badge contingui un número, cal introduir-lo aquí | `numberBadge` | Opcional | String |
| `tabSelected` | Tab seleccionada al menú lateral | `tabSelected` | Obligatori | Boolean |
| `tag` | Tag de la tab amb el contingut | `tag` | Opcional | String (array) |
| `title` | Text principal de la tab | `title` | Obligatori | String |

**Propietats de l'array `dropdownContent`**

| Propietat | Descripció | Atribut | Obligatorietat | Tipus |
|---|---|---|---|---|
| `description` | Descripció de la tab | `description` | Opcional | String |
| `iconPrevText` | Icona prèvia al text de la tab. Cal utilitzar una classe de la biblioteca d'icones de Bootstrap | `iconPrevText` | Opcional | String |
| `iconState` | Si la tab té estat, cal indicar-la aquí. Valors possibles: `complete`, `urgent`, `inProgress` o `block` | `iconState` | Opcional | String |
| `id` | Identificador de la pestanya | `id` | Obligatori | String |
| `isBadge` | Indica si la tab conté badge | `isBadge` | Opcional | Boolean |
| `numberBadge` | En cas que el badge contingui un número, cal introduir-lo aquí | `numberBadge` | Opcional | String |
| `tabSelected` | Tab seleccionada al menú lateral | `tabSelected` | Obligatori | Boolean |
| `text` | Text principal de la tab | `text` | Obligatori | String |

**Propietats de l'array `optionsSectionThree`**

| Propietat | Descripció | Atribut | Obligatori | Tipus |
|---|---|---|---|---|
| `iconClass` | Afegeix aquesta propietat quan `modeSectionThree` sigui `actions`. Indica la icona de bootstrap a mostrar | `iconClass` | Opcional | String |
| `title` | Títol de la pestanya | `title` | Obligatori | String |

**Variants**

| Propietat | Valors | Per defecte |
|---|---|---|
| `iconState` | `complete` `urgent` `inProgress` `block` | - |
| `modeSectionThree` | `options` `actions` | `options` |
| `sizeButton` | `medium` `small` | `medium` |

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `blurButton` | Es llança cada cop que es treu el focus d'un botó. | - | `button-component` |
| `focusButton` | Es llança cada cop que es fa focus en un botó. | - | `button-component` |
| `handlerClick` | Es llança cada cop que es fa clic en un botó i com a paràmetre conté les dades de l'esdeveniment. | id | `button-component` |
| `tabSelectedSection2` | Esdeveniment llançat en seleccionar algun element de la secció 2 (`CustomEvent<number>`) | `index` | `dropdown-menu-component` |
| `tabSelectedSection3` | Esdeveniment llançat en seleccionar algun element de la secció 3 (`CustomEvent<EventEmitter<any>>`) | `index` | `dropdown-menu-component` |
| `toggle` | Indica si el botó de mostrar més està en mode col·lapsat o no. | - | `show-more-component` |
| `dropdownTabClick` | Es propaga en seleccionar una subpestanya amb clic o prement enter | `childIndex` | `vertical-tabs-component` |
| `keydownEvent` | Es llança cada cop que es fa clic una opció del menú desplegable | Esdeveniment emès | `vertical-tabs-component` |

**Depèn de:** `button-component` ([Botons](component-botons.md)), `group-button-component` ([Grup de botons](component-grup-de-botons.md)), `show-more-component` ([Mostra més](component-mostra-mes.md)), `vertical-tabs-component` ([Pestanyes](component-pestanyes.md)).

**Utilitzat per:** `header-component` ([Capçalera per aplicacions internes](component-capcalera-per-aplicacions-internes.md)), `header-public-component` ([Capçalera web pública](component-capcalera-web-publica.md)), `horizontal-menu-component` ([Menú horitzontal](component-menu-horitzontal.md)).

**Exemple d'ús**

```html
<!-- /index.html -->
<dropdown-menu-component 
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
    {"title": "Pestanya","description": "Descripcio", "tabSelected": "true", "isBadge": true, "numberBadge": "3", "iconState": "complete", "iconPrevText": "bi-bar-chart"},
    {"title": "Pestanya"},
    {"title": "Pestanya"},
    {"title": "Pestanya","description": "Descripcio"},
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
        "description": "Descripcio", 
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
  show-more-button-section-three="true"
>
  <button-component slot="footerButton" class-name-button="btn-tertiary" class-name-icon="" size-button="btn-size-M"
    mode-color-button="mode-color-tertiary-light" text="Tanca la sessió" href-button="" left-icon-chevron="false"
    right-icon-chevron="false" left-icon=false right-icon=false text-tooltip="" is-spinner=false custom-id="log-out-button">
  </button-component>
</dropdown-menu-component>
```

Exemple d'instància del PDF:

```html
<dropdown-menu-component
date-last-session=''
departament=''
description-button=''
footer-button=false
icon-button=true
icon-prev-options-section-two=false
icon-state-options-section-two=false
mode-section-three='options'
nom=''
options-section-three="texto-ejemplo"
options-section-two="texto-ejemplo"
rol=''
show-more-button-section-three=false
show-more-button-section-two=false
size-button='medium'
text-button=''
title-section-three="texto-ejemplo"
title-section-two="texto-ejemplo"
></dropdown-menu-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.2.0 | 12.0.3 | 4 setembre, 2026 | **Desenvolupament**: La secció tres no es renderitzarà si no té dades per a les seves propietats corresponents. / S'ha corregit l'etiqueta aria del botó |
| 12.2.0 | 12.0.0 | 10 juliol, 2026 | **Disseny**: S'actualitzen les pestanyes unificades. |
| 12.1.0 | 12.0.0 | 10 juliol, 2026 | **Desenvolupament**: s'utilitza el token correcte per al color de text dels títols de les seccions |
| 12.1.0 | 10.1.0 | 19 juny, 2026 | **Disseny**: Reducció del padding esquerra de 8 a 4px. |
| 9.1.0 | 10.1.0 | 29 maig, 2026 | **Desenvolupament**: el focus a la secció d'opcions 3 es desplaça ara només amb tab, no amb les fletxes del teclat |
| 9.1.0 | 9.4.0 | 17 abril, 2026 | **Disseny:** S'actualitza el component de grup de botons amb la funcionalitat d'slots. **Desenvolupament**: S'ha ajustat el color del mode hover al botó principal. |
| 9.1.0 | 9.2.0 | 20 març, 2026 | **Disseny**: Es modifica el color de fons del hover del botó desplegable. |
| 9.0.0 | 9.2.0 | 20 febrer, 2026 | **Disseny**: S'ajusta el divisor entre les dues seccions perquè estigui configurat com a Inside, ja que en mode Outside no es visualitza correctament. / Es modifica el comportament per defecte del button group, establint el Button 01 com a opció visible per defecte (en lloc del Button 03). / Es renomena la propietat "Show button" a "Show button group". |
| 8.6.0 | 9.2.0 | 27 febrer, 2026 | **Desenvolupament**: Propietats noves afegides: iconButton, descriptionButton, sizeButton, footerButton, iconStateOptionsSectionTwo, iconPrevOptionsSectionTwo, showMoreButtonSectionTwo, showMoreButtonSectionThree i modeSectionThre [sic]. / S'elimina la propietat logOut. / Els botons del peu del desplegable ara s'introdueixen mitjançant slot. / S'hi afegeix barra d'scroll. / Es construeix mode mobile. |
| 8.6.0 | 9.1.0 | 9 febrer, 2026 | **Disseny**: S'han afegit slots al menú per permetre inserir els components (amb llista de preferred). / S'ha afegit una descripció i una icona opcional al botó desplegable. / S'ha afegit un grup de botons al menú per permetre afegir més d'un botó. / S'ha afegit la variable mobile del menú desplegable amb el sheet. |
| 8.2.0 | 9.1.0 | 6 febrer, 2026 | **Desenvolupament**: Es fan adaptacions d'accessibilitat pel que fa a mides de font extra gran i augment de pantalla |
| 8.2.0 | 8.5.0 | 5 desembre, 2025 | **Desenvolupament**: Resolució de problemes menors |
| 8.2.0 | 8.0.0 | 14 novembre, 2025 | **Desenvolupament**: Resolució de problemes |
| 8.2.0 | 6.2.1 | 27 octubre, 2025 | **Disseny**: S'ajusta el text amb alineació a l'esquerra de l'asset Action Button en Hover. / S'eliminen els màxims del botó del menú desplegable i s'ajusta el text. També s'apliquen els estils tipogràfics correctes. |
| 6.0.0 | 6.2.1 | 3 octubre, 2025 | **Desenvolupament**: Nova propietat afegida o eliminada |
| 6.0.0 | 6.0.0 | 8 juliol, 2025 | **Disseny**: S'elimina el botó d'icona pel menú. Es disposa del botó icona amb badge. |
| 4.0.0 | 6.0.0 | 3 juliol, 2025 | **Desenvolupament**: Resolució de problemes |
| 5.0.0 | 5.0.0 | 10 juny, 2025 | **Disseny**: S'afegeix la mida medium per al botó del menú desplegable. |
| 4.0.0 | 5.0.0 | 9 juny, 2025 | **Desenvolupament**: Resolució de problemes |
| 4.0.0 | 4.0.1 | 19 maig, 2025 | **Desenvolupament**: Resolució de problemes |
| 2.4.0 | 2.0.0 | 10 març, 2025 | **Disseny**: S'ha ajustat l'alçada de les tabs "options" i l'estat focus. |
| 2.3.0 | 1.0.0 | 31 gener, 2025 | **Disseny**: Es prototipa l'estat *hover* del botó desplegable en passar per sobre amb el ratolí. **Desenvolupament** del component. |
| 2.2.0 | No aplica | 20 gener, 2025 | **Disseny**: S'han unificat les pestanyes al component combinat del menú desplegable, afegint el component "Dropdown Menu Options" amb els seus estats i substituint el chevron per una fletxa per diferenciar-lo visualment com a component navegable. |
| 2.1.0 | No aplica | 4 desembre, 2024 | **Disseny** i **documentació** del component |

## Vegeu també
Components relacionats segons la font (les etiquetes del lloc no coincideixen amb la descripció ni amb l'enllaç; es llisten per la descripció i l'enllaç [a verificar]):
- [Llista](component-llista.md): per agrupacions de contingut relacionat (etiquetat com "Botons" al lloc).
- [Paginació](component-paginacio.md): per separar grups de contingut en diverses pàgines (etiquetat com "Insígnia" al lloc).
- [Acordió](component-acordio.md): per mostrar o amagar informació individualment d'un llistat d'ítems (etiquetat com "Pestanyes" al lloc).
- [Botons](component-botons.md)
- [Grup de botons](component-grup-de-botons.md)
- [Mostra més](component-mostra-mes.md)
- [Pestanyes](component-pestanyes.md)
