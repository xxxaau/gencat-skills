# Àrea de text (Text area)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/765f1d · Web component: `<textarea-component>` (paquet core) · Font actualitzada el 2026-10-22 · Extret el 2026-10-28

## Què és i quan usar-lo
Camps de text utilitzats en formularis per a la recollida de dades extenses.

L'àrea de text s'utilitza per **recollir dades extenses en formularis**. Suporta els mateixos estats que els camps d'entrada, tot i que compta amb algunes funcionalitats úniques, com ara el control de redimensionament o el comptador de caràcters.

S'utilitza en aquelles situacions en què s'espera que l'usuari empleni un text extens i de diverses línies. El seu ús habitual va dirigit a funcions com comentaris o descripcions per part de l'usuari.

## Quan NO usar-lo / alternatives
En cas que la informació a visualitzar no sigui editable i, per tant, no requereixi cap interacció, no s'ha d'utilitzar l'àrea de text. En aquest cas es pot fer ús d'etiquetes o textos estàtics.

## Anatomia
Figma: Text_area [Show Tooltip = True, Show Help = True, Show Characters counter = True, Show Resize handle = True, Label = Etiqueta, Help text = Text d'ajuda, Error text = Text d'error, Show Popover button = True, Show Scroll bar = False, Size = Medium, Interaction = Default, State = Enabled].

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Size | Medium / Small | Medium |
| Interaction | Default / Hover / Focus | Default |
| State | Enabled / Filled / Error / Disabled | Enabled |
| Show Tooltip | True / False | False |
| Show Help | True / False | True |
| Show Characters Counter | True / False | True |
| Show Resize handle | True / False | True |
| Show Popover button | True / False | False |

Variant booleana addicional a Figma (versió 9.1.0): barra de desplaçament (Show Scroll bar; False a l'anatomia).

### Interacció (estats d'interacció)
- **Default:** quan un usuari no ha interactuat amb el camp.
- **Hover:** quan un usuari passa el cursor per sobre de l'àrea del camp.
- **Focus:** un contorn blau apareix al voltant del camp quan un usuari fa clic sobre el component o utilitza els controls del teclat per navegar. Els estats de focus no apareixen als camps inactius.

### Estats
Enabled, Filled, Error i Disabled (vegeu la taula de propietats).

### Mides
Medium (per defecte) i Small. Component web: `size` = `small` | `medium` (per defecte `medium`).

## Mides i espaiats
Alçada mínima de 120 px per a l'input i 152px per al component (versió de disseny 10.0.0).

## Comportament i interacció
- **Interacció:** els usuaris poden seleccionar, editar o eliminar el text dins del camp d'entrada utilitzant el cursor del ratolí o el teclat. També poden suprimir caràcters o text seleccionat utilitzant les tecles d'eliminació o de retrocés del teclat.
- **Validació de dades:** l'estat d'error apareixerà únicament quan l'usuari no hagi omplert l'àrea de text en cas que es tracti d'un camp obligatori. El missatge d'error desapareixerà quan l'usuari faci qualsevol canvi dins del camp.
- **Limitació de caràcters:** si el camp té una limitació en nombre de caràcters, l'usuari no podrà introduir més text un cop arribi al màxim establert.
- **Adaptació responsiva i desbordament de text:**
  - L'amplada i alçada del camp han de ser adequades al tipus d'informació a omplir. Si la resposta és més llarga que el contenidor del camp, apareixerà un **desplaçament vertical** mentre l'usuari escriu, mantenint el cursor sempre visible a la part inferior i desbordant el text per la part superior. Quan el camp perd el focus, el text ha de desbordar-se per la part inferior del camp, mostrant l'inici del text.
  - L'**etiqueta** no hauria de ser més llarga que el seu contenidor. Si en algun cas l'extensió de l'etiqueta sobrepassa l'amplada del component, el text saltarà a una segona línia. Si l'etiqueta conté un indicador de funció, aquest quedarà alineat amb l'última paraula del text.
  - Si el **control de redimensionament** està activat, l'usuari podrà manipular l'alçada del camp, fent-lo més llarg o més curt, perquè s'acomodi bé al contingut. El redimensionament del component desplaçarà el contingut maquetat situat sota del camp. Aquest control no està disponible per a dispositius mòbils ni tauletes.
- **Placeholder (espai reservat):** per evitar problemes d'accessibilitat es prescindeix del placeholder en tots els components d'entrada (inputs). La informació necessària per entendre quina informació ha d'introduir l'usuari anirà a l'etiqueta o al text d'ajuda.
- El tooltip (indicador de funció) i el popover (descripció emergent) no es poden mostrar alhora; cal regular-ne la visibilitat amb `showPopoverValue` i `showTooltip` (versió Github 9.3.0).

## Contingut i microcopy
Textos d'exemple de l'anatomia: Etiqueta, Text d'ajuda, Text d'error. Exemple de codi: "Etiqueta", "Text d'ajuda", "Texto Tooltip", "Ajuda", "Títol de prova", "Descripció del popover", "Més informació".

## Bones pràctiques
Etiquetes:
- **FER:** Utilitza etiquetes que siguin concises, comprensibles i que comencin amb el primer caràcter en majúscula.
- **NO FER:** No utilitzis els elements tipogràfics (":") per indicar que l'etiqueta s'aplica al camp que acompanya. El disseny del component ja comunica la relació entre l'etiqueta i el camp d'entrada.

Text d'ajuda i informació addicional:
- **FER:** Utilitza el text d'ajuda per proporcionar informació addicional sobre el format del camp de manera simple i directa.
- **NO FER:** No utilitzis el text d'ajuda per indicar que el formulari és obligatori o opcional. Aquesta informació ha d'incloure's a l'etiqueta del camp.
- **FER:** En cas necessari, utilitza l'indicador de funció per afegir informació addicional sobre l'etiqueta del camp.
- **NO FER:** No amaguis informació rellevant sobre el format del camp dins d'un indicador de funció. Aquesta informació es pot afegir com a text d'ajuda sota el camp.

Camps obligatoris i opcionals:
- **FER:** Indica si els camps són obligatoris o opcionals, destacant únicament aquells que en siguin menys. Per exemple, en cas que hi hagi cinc camps obligatoris i un d'opcional, només es destacarà aquest últim per tal de reduir la càrrega cognitiva.
- **NO FER:** No utilitzis l'asterisc per indicar camps opcionals. Aquesta icona només s'ha d'utilitzar per als camps obligatoris. En el cas dels camps opcionals, indica-ho entre parèntesis a la mateixa etiqueta.
- **FER:** En cas d'emprar un asterisc (*) per marcar els camps obligatoris, inclou una llegenda explícita.
- **FER:** Utilitza sempre el mateix criteri per indicar si els camps són obligatoris o opcionals al llarg de tot el formulari.

Maquetació:
- **FER:** En entorns orientats al ciutadà, és recomanable maquetar els camps en una o dues columnes per facilitar l'escaneig del contingut.
- **NO FER:** Evita estendre els camps en excés, ja que pot dificultar la usabilitat dels formularis.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG):
- **Orientació (AA)** — [1.3.4](https://www.w3.org/Translations/WCAG22-ca/#orientation) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html): el contingut de l'àrea de text s'adapta a les diferents orientacions de la pantalla, vertical o horitzontal, cosa que permet visualitzar el contingut.
- **Ús del color (A)** — [1.4.1](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color): el color no es fa servir com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per indicar els diferents estats, es modifiquen els píxels de la vora del component i/o s'afegeixen elements complementaris, com ara una segona vora pel focus o icones i text d'error.
- **Contrast mínim (AA)** — [1.4.3](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum): els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma.
- **Canvia la mida del text (AA)** — [1.4.4](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text): excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat.
- **Contrast d'elements no textuals (AA)** — [1.4.11](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast): els elements gràfics com icones (error i tooltip) i vores presenten un contrast mínim de 3:1.
- **Espaiat del text (AA)** — [1.4.12](https://www.w3.org/Translations/WCAG22-ca/#text-spacing) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/text-spacing): quan es desenvolupa contingut utilitzant llenguatges de marcatge que permeten aplicar les propietats d'estil de text, no es perd cap contingut ni funcionalitat si s'ajusten les propietats següents:
  - Alçada de línia (interlineat) de com a mínim 1,5 vegades la mida de la lletra.
  - Espaiat entre els paràgrafs de com a mínim dues vegades la mida de la lletra.
  - *Tracking* (espaiat entre lletres) de com a mínim 0,12 vegades la mida de la lletra.
  - Espaiat entre paraules de com a mínim 0,16 vegades la mida de la lletra.
- **Teclat (A)** — [2.1.1](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard): tota la funcionalitat del contingut (accedir al camp de text) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals.
- **Focus visible (AA)** — [2.4.7](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible): la navegació al camp de l'àrea de text és visible mitjançant un rectangle extern.
- **Identificació d'errors (A)** — [3.3.1](https://www.w3.org/Translations/WCAG22-ca/#error-identification) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/error-identification): si es detecta un error en el component, s'identifica clarament que aquest presenta un error mitjançant un canvi de color i gruix de la vora i amb la indicació visual (icona) i textual (descripció de l'error) de l'error.

## Implementació (component web)

### `<textarea-component>`
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat |
|---|---|---|---|---|---|
| `idTextarea` | `id-textarea` | Identificador de l'àrea de text. | string | undefined | Obligatori |
| `isDisabled` | `is-disabled` | Deshabilitar o habilitar l'àrea de text. | boolean | false | Opcional |
| `maxChars` | `max-chars` (el lloc escriu `mar-chars`) | Configurar el màxim de caràcters que es poden introduir a l'àrea de text. | number | undefined | Opcional |
| `nameTextarea` | `name-textarea` | Atribut name del camp de formulari (nom del textarea). | string | undefined | Obligatori |
| `placeholder` | `placeholder` | Text de marcador de posició del camp d'entrada. | string | undefined | Opcional |
| `popoverConfig` | `popover-config` | Configuració del popover (atributs). Accepta objecte o string JSON. | string (object) | `{}` | Opcional |
| `showPopoverValue` | `show-popover-value` | Mostra o oculta el popover. | boolean | false | Opcional |
| `showTooltip` | `show-tooltip` | Mostra o oculta la icona informativa, indicant la funcionalitat de l'etiqueta. | boolean | false | Opcional |
| `size` | `size` | Mida de l'àrea de text. Opcions: `medium`, `small`. | string | `medium` | Opcional |
| `textAlternativeError` | `text-alternative-error` | Text alternatiu de l'exclamació del text d'error. | string | undefined | Opcional |
| `textError` | `text-error` | Text d'error que es vol mostrar. Quan no hi hagi res escrit, no sortirà cap error. | string | undefined | Opcional |
| `textEtiqueta` | `text-etiqueta` | Text de l'etiqueta que va al costat de la icona. | string | undefined | Obligatori |
| `textHelp` | `text-help` | Text d'ajuda a sota de l'àrea de text. | string | undefined | Opcional |
| `textInfoTooltip` | `text-info-tooltip` | Text de l'indicador de funció de la icona informativa (tooltip associat). | string | undefined | Opcional |
| `value` | `value` | Valor actual de l'àrea de text. | string | `` (cadena buida) | Opcional |
| `visibilityCharCounter` | `visibility-char-counter` | Habilitar o no el comptador de caràcters. | boolean | false | Opcional |
| `visibilityTextHelp` | `visibility-text-help` | Habilitar o no el text d'ajuda. | boolean | true | Opcional |

[discrepància: el lloc escriu l'atribut `mar-chars`; el PDF i l'exemple de codi usen `max-chars`]

**Variants**

| Propietat | Per defecte | Valors |
|---|---|---|
| `size` | `medium` | `small` `medium` |

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre / tipus | Origen |
|---|---|---|---|
| `focusTextArea` | Es llança quan el text area pren el focus (true) o el perd (false). | Boolean (`CustomEvent<boolean>`) | `textarea-component` |
| `valueChange` | Es llança cada cop que hi ha un canvi en un textarea. S'emet de forma immediata. | value (`CustomEvent<string>`) | `textarea-component` |
| `valueChangeDelayed` | Es llança cada cop que hi ha un canvi en un textarea. S'emet al cap de 5 segons d'inactivitat. | value (`CustomEvent<string>`) | `textarea-component` |

**Depèn de:** `tooltip-component` ([Indicador de funció](component-indicador-de-funcio.md)), `popover-component` ([Descripció emergent](component-descripcio-emergent.md)).

**Exemple d'ús**

```html
<!-- /index.html -->
<textarea-component 
  id-textarea="id-textarea"
  name-textarea="name-textarea"
  placeholder="Write here..." 
  text-etiqueta="Etiqueta" 
  text-help="Text d'ajuda" 
  size="small"
  text-error=""
  text-alternative-error=""
  is-disabled=false 
  visibility-text-help=true 
  visibility-char-counter=false 
  text-info-tooltip="Texto Tooltip" 
  show-tooltip="false"
  show-popover-value="true" 
  value=""
  max-chars=""
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
></textarea-component>
```

Exemple d'instància del PDF:

```html
<textarea-component
id-textarea="texto-ejemplo"
is-disabled=false
max-chars=0
name-textarea="texto-ejemplo"
placeholder="texto-ejemplo"
popover-config='{}'
show-popover-value=false
show-tooltip=false
size='medium'
text-alternative-error="texto-ejemplo"
text-error="texto-ejemplo"
text-etiqueta="texto-ejemplo"
text-help="texto-ejemplo"
text-info-tooltip="texto-ejemplo"
value=''
visibility-char-counter=false
visibility-text-help=true
></textarea-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 10.0.0 | 9.4.0 | 17 abril, 2026 | **Disseny:** Alçada mínima de 120 px per l'input i 152px pel component. **Desenvolupament**: S'han fet ajustos de layout. |
| 9.1.0 | 9.3.0 | 20 març, 2026 | **Disseny**: Es posa el frame de content a alçada fill i el text a alçada hug. / Es posen els texts a amplada fill. / Es fa un clip content del frame content. / S'afegeix una variant booleana de barra de scroll. **Desenvolupament**: Es reconfigura el component perquè tooltip i popover no es puguin mostrar alhora, s'ha de jugar amb les showPopoverValue i showTooltip per regular la seva visibilitat |
| 9.0.0 | 9.1.0 | 20 febrer, 2026 | **Disseny**: S'afegeix un contenidor per agrupar etiqueta i tooltip. Es posa el contenidor de Label (inclou etiqueta, tooltip i popover) a wrap. |
| 4.0.0 | 9.1.0 | 6 febrer, 2026 | **Desenvolupament**: L'esdeveniment valueChange s'emet a l'instant i l'esdeveniment valueChangeDelayed s'emet als 5s. |
| 4.0.0 | 8.5.0 | 5 desembre, 2025 | **Desenvolupament**: Es canvia el nom de la property showPopover a showPopoverValue |
| 4.0.0 | 7.0.0 | 24 octubre, 2025 | **Desenvolupament**: Resolució de problemes |
| 4.0.0 | 6.1.0 | 12 setembre, 2025 | **Desenvolupament**: nova propietat afegida |
| 4.0.0 | 6.0.0 | 3 juliol, 2025 | **Desenvolupament**: Resolució de problemes |
| 4.0.0 | 5.0.0 | 9 juny, 2025 | **Desenvolupament**: Resolució de problemes |
| 4.0.0 | 4.0.1 | 19 maig, 2025 | **Desenvolupament**: Resolució de problemes |
| 2.3.0 | 1.1.0 | 17 febrer, 2025 | **Desenvolupament**: Resolució de problemes |
| 2.2.0 | 0.1.1 | 20 gener, 2025 | Modificació de la variant de mida del botó d'ajuda en la mida *Small* del component. |
| 2.1.0 | 0.1.1 | 04 desembre, 2024 | **Disseny:** S'afegeix el botó d'ajuda per mostrar la descripció emergent. |
| 1.0.0 | 0.0.3 | 1 novembre, 2024 | **Disseny**, **desenvolupament** i **documentació** del component |

## Vegeu també
- [Camp d'entrada](component-camp-d-entrada.md): per a introduir i recopilar dades de manera interactiva.
- [Camp de cerca](component-camp-de-cerca.md): per a realitzar cerques o explorar un lloc web o aplicació.
- [Desplegable](component-desplegable.md): per a seleccionar elements d'una llista d'opcions predefinides.
- [Indicador de funció](component-indicador-de-funcio.md)
- [Descripció emergent](component-descripcio-emergent.md)
- [Formularis (exemple)](exemple-formularis.md)
