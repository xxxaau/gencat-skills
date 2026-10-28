# Camp de cerca (Searchfield)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/82e0c6 · Web component: `<searchfield-component>` (paquet core) · Font actualitzada el 2026-10-22 · Extret el 2026-10-28

## Què és i quan usar-lo
El camp de cerca ofereix a l'usuari una manera d'explorar un lloc web o una aplicació mitjançant paraules clau.

És una **àrea on els usuaris poden introduir text per cercar informació** dins d'un lloc web o una aplicació. Permet accedir ràpidament a la informació necessària sense navegar per menús complexos o extenses llistes de contingut. Consta, principalment, d'un camp de text i un botó de cerca.

La cerca es pot utilitzar com a mitjà principal per descobrir contingut o com a filtre per ajudar l'usuari a trobar-lo. Es fa servir per:
- Cercar a **escala global** dins un lloc sencer.
- Cercar en **l'àmbit de pàgina**, quan se cerca contingut en una pàgina específica.

## Anatomia
Figma: Search field desktop [Help = True, Help text = Text d'ajuda, Placeholder = Placeholder, Search text = Cerca introduïda, Partial search text = "cer |", State = Default, Size = Medium, Dark background = No]. La font només mostra la imatge d'anatomia.

## Variants, tipus i estats

### Opcions (desplegable de suggeriments)

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Type | Suggestion / Last search / Options | Suggestion |
| State | Default / Hover / Loading | Default |
| Dark background | Yes / No | No |

Variant Figma: Search field_Options [Autocomplete = autocompletat, Previous search = cerca anterior, Type = Suggestion, State = Default, Dark background = No].

### Desktop

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Default / Hover / Focus-empty / Focus-loading / Focus-filled / Filled / Filled-hover | Default |
| Size | Large / Medium / Small | Medium |
| Dark background | True / False | False |
| Label | True / False | False |
| Popover button | True / False | False |

Variant Figma: Search field desktop [Show Help = False, Help text = Text d'ajuda, Search text = Cerca introduïda, Partial search text = "cer |", Show Advanced search = False, Show Results = True, Show Label = True, Show Popover = False, Show Tooltip = False, Size = Large, State = Default, Dark background = False]. [discrepància: la taula diu que la mida per defecte és Medium; el text diu que Large és la mida per defecte]

### Mobile

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Default / Hover / Focus / Pressed / Loading | Default |
| Dark background | Yes / No | No |

Variant Figma: Search field mobile [Show Help text = True, Partial search text = "cer |", Search text = Cerca introduïda, Show Advanced searched = False, Show Label = True, Show Popover = False, Show Tooltip = False, State = Default, Dark background = False] (versió anterior: Help text, Voice search = False, Placeholder).

## Mides i espaiats
- **Large:** s'utilitza **per defecte**.
- **Medium:** en els **casos en què l'espai de pantalla és reduït**, com en els camps de filtre.
- **Small:** destinada a elements específics com la capçalera.

## Comportament i interacció

### Interacció
- **Default (filled):** després de realitzar una cerca, aquesta roman visible al cercador per facilitar ajustaments posteriors.
- **Focus (empty):** en l'estat focus (quan l'usuari encara no ha escrit res), es mostren les cerques recents fins a un màxim de cinc.
- Quan l'usuari selecciona una de les opcions de cerca, el desplegable es tanca i es mostren els resultats basats en l'opció seleccionada.
- **Focus (filled):** es produeix quan l'usuari selecciona el camp de cerca per començar a escriure. Apareix una icona per eliminar el contingut ('x').
- En introduir text, el cercador mostra resultats mitjançant la funció d'autocompletar del sistema.
- Si la mostra de resultats triga més de dos segons (per exemple, per mala connectivitat), es mostra un missatge de "Cercant..." juntament amb un indicador de càrrega (spinner).
- Si la cerca supera els límits visibles del camp, el text es desplaça horitzontalment cap a la dreta.
- Si l'usuari fa una selecció fora del camp de cerca, aquest es tanca i es manté el text introduït fins al moment.
- **Filled:** si la informació introduïda supera l'amplada del camp de text, es trunca al final, ocupant només l'espai disponible.

### Regles de comportament
- **Caràcters:** s'han de poder introduir un **mínim de vint-i-set caràcters**.
- **Suggeriments:** es mostren fins a un màxim de **nou suggeriments** per evitar aclaparar l'usuari. Les parts **autosuggerides** pel sistema es diferencien de la resta aplicant l'estil de text **semibold**.

### Adaptació responsiva
Si en mòbil es mostra el camp de cerca a primer nivell, ocupa tot l'espai de layout disponible. En seleccionar el camp de cerca (o la icona si només aquesta és visible) **s'obre el cercador en una nova pantalla**, perquè les recomanacions ocupin tot l'espai de pantalla i se centri l'atenció de l'usuari.

## Contingut i microcopy
- Missatge d'espera: "Cercant..." (amb indicador de càrrega) quan la cerca triga més de dos segons.
- Exemples de la font: "Text d'ajuda", "Cerca introduïda", cerca parcial "cer |", "Placeholder".

## Bones pràctiques

### Context
- **FER:** Inclou un text que faci referència al context d'allò que pot buscar l'usuari en l'espai reservat (placeholder). Aquest ha de ser el més clar i concís possible.
- **NO FER:** No incloguis un text que no faci referència al context d'allò que buscarà l'usuari en l'espai reservat.
- **FER:** Mostra els resultats relacionats amb la cerca.
- **NO FER:** No mostris resultats que no estan relacionats amb la cerca.

### Paraules clau
- **FER:** Remarca les paraules clau introduïdes en el contingut de la pàgina per facilitar-ne l'escaneig.
- **NO FER:** No oblidis remarcar les paraules clau introduïdes en el contingut de la pàgina, ja que dificulta l'escaneig.

### Missatges d'estat
- **FER:** Mostra un missatge que indiqui que la cerca no troba cap resultat i ofereix consells de cerca. Per complementar-lo, segons el context, es pot: suggerir una o més categories basades en la consulta de l'usuari; suggerir cerques i categories populars; oferir enllaços d'ajuda o contacte.
- **NO FER:** No oblidis mostrar un missatge que indiqui que la cerca no troba cap resultat, ni oferir consells de cerca.
- **FER:** Indica que el procés de cerca triga més de l'esperat (dos segons) mitjançant un element textual acompanyat, opcionalment, d'un element visual.
- **NO FER:** No oblidis indicar que el procés de cerca triga més de l'esperat (dos segons) amb algun element.

## Accessibilitat
Pautes WCAG 2.2:
- **Orientació (AA) – 1.3.4:** el contingut s'adapta a les diferents orientacions de la pantalla (vertical o horitzontal). [CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Ús del color (A) – 1.4.1:** el color no és l'únic mitjà visual per transmetre informació. Per indicar els estats, es modifiquen els píxels de la vora i/o s'afegeixen elements complementaris com la segona vora pel focus o la icona i el text d'error. [CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA) – 1.4.3:** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats en són excepció. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA) – 1.4.4:** excepte subtítols i imatges de text, el text es pot canviar de mida fins al 200 % sense pèrdua de contingut ni funcionalitat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA) – 1.4.11:** les icones (resultats cercats anteriorment o suggeriments de cerca) i les vores presenten un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A) – 2.1.1:** tota la funcionalitat (accedir al camp de text) es pot operar amb teclat sense requerir temps específics per a pulsacions de tecles individuals. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Focus visible (AA) – 2.4.7:** la navegació al camp de cerca és visible mitjançant un rectangle extern. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

### Navegació per teclat

| Tecla | Acció |
|---|---|
| Tabulació | Navegar al camp d'entrada |
| Shift + Tabulació | Navegar al component anterior |
| Fletxes | Desplaçar-se pels diferents elements del camp de suggeriments (cerques anteriors i suggerides) |
| Intro | Realitzar la cerca |

## Implementació (component web)

### `<searchfield-component>`

Hi ha tres vies de passar dades al component:
- Que les prengui del DOM mitjançant la propietat `selector`.
- Introduir les dades mitjançant la propietat `data` en un string (array).
- Mitjançant `dataUrl` i `dataKeyField`, utilitzant una URL connectada a un backend.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Obligatori | Per defecte |
|---|---|---|---|---|---|
| `breakpoint` | `breakpoint` | Indica a partir de quina mitjana (amplada) es fa el breakpoint a pantalla petita. | number | Opcional | `480` |
| `buttonFilter` | `button-filter` | Mostra o oculta el botó de filtre. Aquest botó no té funcionalitat; s'ha de proporcionar segons les necessitats. | boolean | Opcional | `false` |
| `data` | `data` | Permet carregar dades no gaire grans en un string (array). Accepta objecte o string JSON. | string (array) | Opcional | `[]` |
| `dataKeyField` | `data-key-field` | Quan es carreguen les dades mitjançant URL, indica al component quina columna o columnes ha de prendre (nom del camp clau). | string o string (array) | Opcional | `text` |
| `dataUrl` | `data-url` | Permet carregar dades grans mitjançant una URL connectada a backend. | string | Opcional | `` |
| `idInput` | `id-input` | Identificador de l'input de tipus text. | string | Obligatori | `undefined` |
| `modeColor` | `mode-color` | Mode fosc o mode clar (esquema de color i contrast). Opcions: `dark`, `light`. | string | Obligatori | `light` |
| `modeColorHead` | `mode-color-head` | Indica si el component s'utilitzarà a la capçalera. | boolean | Opcional | `false` |
| `nameInput` | `name-input` | Nom de l'input de tipus text (atribut name del camp de formulari). | string | Obligatori | `undefined` |
| `popoverConfig` | `popover-config` | Propietats per al component popover. Accepta objecte o string JSON. | string (array) | Opcional | `{}` |
| `selector` | `selector` | Selector (CSS) per al camp de cerca que recull dades per introduir-les al cercador. | string | Obligatori | `undefined` |
| `showEtiqueta` | `show-etiqueta` | Visibilitat de l'etiqueta completa juntament amb icona informativa i popover. | boolean | Opcional | `undefined` |
| `showPopoverValue` | `show-popover-value` | Visibilitat del popover. | boolean | Opcional | `undefined` |
| `showTooltip` | `show-tooltip` | Visibilitat de la icona informativa amb tooltip. | boolean | Opcional | `undefined` |
| `size` | `size` | Mida: botó amb text o botó només amb icona. Opcions: `big`, `medium`, `small`. | string | Obligatori | `big` |
| `textButtonFilter` | `text-button-filter` | Text del botó de filtre en mida big. En mides medium i small és el text alternatiu del botó. | string | Opcional | `undefined` |
| `textEtiqueta` | `text-etiqueta` | Text de l'etiqueta. | string | Opcional | `undefined` |
| `textInfo` | `text-info` | Text descriptiu sota el camp de cerca. | string | Opcional | `undefined` |
| `textInfoTooltip` | `text-info-tooltip` | Text del tooltip de la icona informativa. | string | Opcional | `undefined` |
| `tooltipButtonFilter` | `tooltip-button-filter` | Text del tooltip del botó de filtre. [discrepància: la taula de la pàgina escriu l'atribut `text-button-filter`; el PDF i l'exemple usen `tooltip-button-filter`] | string | Opcional | `undefined` |
| `tooltipButtonSearch` | `tooltip-button-search` | Text del tooltip del botó de cerca. | string | Opcional | `undefined` |
| `value` | `value` | Valor de l'input de tipus text. | string | Opcional | `` |

**Variants**

| Propietat | Valors | Per defecte |
|---|---|---|
| `modeColor` | `light` `dark` | `light` |
| `size` | `big` `medium` `small` | `big` |

**Esdeveniments**

| Esdeveniment | Descripció | Tipus / Paràmetre | Origen |
|---|---|---|---|
| `valueChange` | Es llança cada vegada que es fa clic al botó de cerca o s'enter al camp de cerca. | `CustomEvent<string>` (`value`) | `searchfield-component` |
| `filterButtonClick` | Detecta el clic al botó de filtre propagant el seu ID. | `CustomEvent<string>` (`ID`) | `searchfield-component` |
| `handlerClick` | Es llança cada cop que es fa clic en un botó; com a paràmetre conté les dades de l'esdeveniment. | id | `button-component` |
| `focusButton` | Es llança cada cop que es fa focus en un botó. | - | `button-component` |
| `blurButton` | Es llança cada cop que es treu el focus d'un botó. | - | `button-component` |

**Depèn de:** `button-component` ([Botons](component-botons.md)), `tooltip-component` ([Indicador de funció](component-indicador-de-funcio.md)), `popover-component` ([Descripció emergent](component-descripcio-emergent.md)).

**Utilitzat per:** `hero-banner-component` ([Panell destacat](component-panell-destacat.md)), `dynamic-table-component` ([Taules dinàmiques](component-taules-dinamiques.md)), `header-component` ([Capçalera per aplicacions internes](component-capcalera-per-aplicacions-internes.md)), `header-public-component` ([Capçalera web pública](component-capcalera-web-publica.md)).

**Props que accepten JSON:** `popoverConfig` (`popover-config`: claus `text-open`, `padding`, `size-text-open`, `popover-title`, `description`, `version`, `contextual-image-url`, `img-description`, `link-text-popover`); `data` (array); `dataKeyField` (string o array, p. ex. `'["name", "email"]'`).

**Exemple d'ús (pàgina)**

```html
<!-- /index.html -->
<searchfield-component 
  id-input="id-searchfield"
  name-input="name-searchfield"
  selector="h2"
  size="medium" 
  mode-color="light" 
  text-info="Text descriptiu"
  button-filter="true"
  breakpoint="480"
  text-button-filter="Filter"
  tooltip-button-search="Tooltip de la cerca"
  tooltip-button-filter="Tooltip del filtre"
  value=""
  text-etiqueta="Lorem ipsum dolor ismet" 
  text-info-tooltip="Text" 
  show-tooltip="true" 
  show-popover-value="true"
  mode-color-head="true"
  show-etiqueta="true" 
  data='[]'
  data-url="https://jsonplaceholder.typicode.com/users"
  data-key-field='["name", "email"]'
  popover-config='{
      "text-open": "Ajuda",
      "padding": 20,
      "size-text-open": "small",
      "popover-title": "Títol de prova",
      "description": "Descripció del popover",
      "version": "contextual",
      "contextual-image-url": "/assets/photos/img_1.png",
      "img-description": "Descripció de la imatge",
      "link-text-popover": "Més informació"
  }'
></searchfield-component>
```

**Exemple d'instància (PDF)**

```html
<searchfield-component
breakpoint=480
button-filter=false
data='[]'
data-key-field='text'
data-url=''
id-input="texto-ejemplo"
mode-color='light'
mode-color-head=false
name-input="texto-ejemplo"
popover-config='{}'
selector="texto-ejemplo"
show-etiqueta=false
show-popover-value=false
show-tooltip=false
size='big'
text-button-filter="texto-ejemplo"
text-etiqueta="texto-ejemplo"
text-info="texto-ejemplo"
text-info-tooltip="texto-ejemplo"
tooltip-button-filter="texto-ejemplo"
tooltip-button-search="texto-ejemplo"
value=''
></searchfield-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.0.0 | 12.1.0 | 7 setembre, 2026 | Desenvolupament: correcció en el processament de les dades del popover; s'afegeixen noves propietats per a la càrrega de dades. |
| 12.0.0 | 12.0.3 | 4 setembre, 2026 | Desenvolupament: es corregeix el problema pel qual el modal es tancava en prémer la tecla ESC mentre el camp de cerca estava actiu; correcció a l'anàlisi de les dades del popover. |
| 12.0.0 | 11.0.0 | 19 juny, 2026 | Desenvolupament: s'afegeixen estats al botó de neteja. |
| 12.0.0 | 10.1.0 | 29 maig, 2026 | Disseny: s'aplica la propietat Show Help a tots els texts d'ajuda i s'oculten tots per defecte tant a desktop com a mobile; s'apliquen estils d'estat a la creu per eliminar el contingut al camp d'entrada i al camp numèric. Desenvolupament: en introduir una paraula a l'input i prémer el botó de cerca, ja no desapareix. |
| 8.5.0 | 9.2.0 | 27 febrer, 2026 | Desenvolupament: es creen tres noves propietats `data`, `dataUrl` i `dataKeyField` que permeten carregar dades des d'un backend o en un string (array). |
| 8.5.0 | 8.5.0 | 20 gener, 2026 | Disseny: s'eliminen placeholders; s'incorpora un frame pel text perquè es talli quan el contingut sobrepassa l'espai del camp; els textos de les opcions de cerca autocompletada i cerca anterior es posen a fill. |
| 8.4.0 | 8.5.0 | 5 desembre, 2025 | Disseny: truncat de text a una línia al placeholder. Desenvolupament: s'hi afegeix etiqueta, tooltip i popover. |
| 8.3.0 | 7.0.0 | 14 novembre, 2025 | Disseny: s'elimina el botó d'icona del micròfon i la cursiva de la tipografia del botó de cerca avançada. |
| 8.2.0 | 7.0.0 | 27 octubre, 2025 | Disseny: s'afegeix una etiqueta i un "popover button" al camp de cerca; es modifica el layout del frame results container del cercador per a mòbil en estat default i es posa en Hug. |
| 6.0.0 | 7.0.0 | 24 octubre, 2025 | Desenvolupament: resolució de problemes. |
| 6.0.0 | 6.2.1 | 3 octubre, 2025 | Desenvolupament: resolució de problemes. |
| 6.0.0 | 6.1.0 | 12 setembre, 2025 | Desenvolupament: nova propietat afegida. |
| 6.0.0 | 6.0.1 | 28 juliol, 2025 | Desenvolupament de l'evolutiu. |
| 6.0.0 | 6.0.0 | 8 juliol, 2025 | Disseny: s'afegeix el desplegable de cerques anteriors i suggeriments com a component individual. |
| 2.4.0 | 6.0.0 | 3 juliol, 2025 | Desenvolupament: resolució de problemes. |
| 2.4.0 | 5.0.0 | 9 juny, 2025 | Desenvolupament: resolució de problemes. |
| 2.4.0 | 2.0.0 | 10 març, 2025 | Disseny: als estats focus s'afegeix posició absoluta i es fixa Left + Right perquè s'adapti bé en contextos d'altres components com la targeta del panell destacat; la posició del camp de resultats passa a absoluta. |
| 2.3.0 | 2.0.0 | 7 març, 2025 | Desenvolupament: resolució de problemes. |
| 2.3.0 | 1.1.0 | 17 febrer, 2025 | Desenvolupament: resolució de problemes. |
| 2.3.0 | 1.0.0 | 31 gener, 2025 | Sense canvis |
| 2.2.0 | 0.1.1 | 20 gener, 2025 | Sense canvis |
| 2.1.0 | 0.1.1 | 04 desembre, 2024 | Disseny: s'afegeix la mida small. |
| 2.0.0 | 0.1.0 | 02 desembre, 2024 | Sense canvis |
| 1.1.0 | 0.1.0 | 22 novembre, 2024 | Sense canvis |
| 1.1.0 | 0.0.4 | 18 novembre, 2024 | Sense canvis |
| 1.0.0 | 0.0.3 | 1 novembre, 2024 | Disseny, desenvolupament i documentació del component |

## Vegeu també
- [Botons](component-botons.md): per realitzar accions.
- [Camp d'entrada](component-camp-d-entrada.md): per a la recollida de dades.
- [Desplegable](component-desplegable.md): per seleccionar un o diversos elements d'una llista d'opcions predefinides.
