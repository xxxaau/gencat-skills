# Botó d'opció (Radio button)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/828815 · Web component: `<radio-component>` i `<advanced-radio-button-component>` (paquet core) · Font actualitzada el 2026-10-22 · Extret el 2026-10-28

## Què és i quan usar-lo
Element de control gràfic que permet seleccionar una opció dins d'un conjunt d'opcions mútuament excloents. S'utilitza en escenaris on els usuaris necessiten **fer una única selecció d'un conjunt predefinit d'opcions.**

### Botó d'opció estàndard
Quan s'utilitza:
- **Formularis:** a l'hora d'omplir formularis els usuaris poden necessitar indicar preferències mitjançant botons d'opció, com marcar disponibilitat d'horaris, especificar informació demogràfica, o seleccionar altres preferències.
- **Qüestionaris o enquestes:** per a enquestes o qüestionaris en línia, els botons d'opció s'utilitzen per presentar preguntes d'elecció múltiple on els enquestats poden seleccionar una única opció com a resposta.
- **Configuració de preferències:** en aplicacions o llocs web on els usuaris poden personalitzar l'experiència, es poden utilitzar botons d'opció per seleccionar preferències com ara l'idioma, la configuració de notificacions, etc.
- **Filtratge:** a les interfícies de cerca o a les taules de dades, els botons d'opció poden ser usats per filtrar o ordenar els resultats per criteris, com ara l'interval de preus, l'interval de dates o la rellevància.

### Botó d'opció avançat
Element de control gràfic que, mantenint el comportament d'un botó d'opció estàndard, ofereix una presentació visual enriquida amb suport opcional per a icones o il·lustracions. Està dissenyat per a contextos on la representació visual de cada opció afavoreix la comprensió i la presa de decisions.

Es pot utilitzar en:
- [Arbres de decisions](patro-arbre-de-decisions.md).

## Quan NO usar-lo / alternatives
### Botó d'opció estàndard
- Si l'usuari ha de seleccionar més d'una opció, és preferible utilitzar la casella de selecció en lloc del botó d'opció.
- Si l'usuari té més de vuit opcions a escollir, l'ús del botó d'opció no és recomanable, ja que una llista llarga pot provocar fatiga visual i dificultar la presa de decisions. Com a alternativa, es poden agrupar les opcions en categories lògiques o utilitzar elements com els menús desplegables per facilitar seleccions complexes.

### Botó d'opció avançat
- Quan es vol substituir l'estàndard.

## Anatomia
### Botó d'opció estàndard
Figma: Radio button [Show Description = True, Option = Opció, Description text = Descripció, Size = Small, Selected = No, State = Default]; Radio button_group [Show Radio button 05 = True, Show Radio button 03 = True, Show Radio button 04 = True, Error text = Text d'error, Show Tooltip = True, Label = Etiqueta, Show Label = True, Size = Small, Error = False].

### Botó d'opció avançat
Figma: Advanced radio button [Change text = Text, Change Icon = house, Show Icon = True, Change Illustration = Habitatge, State = Default, Visual element = Icon, Selected = False]; Advanced Radio Button Group [Slot, Text Error = Text d'error, Error = False].

## Variants, tipus i estats

### Botó d'opció estàndard

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Size | Medium / Small | Medium |
| Selected | True / False | False |
| State | Default / Hover / Focus / Disabled | Unselected |
| Option | Text | Opció |
| Show Description | True / False | False |
| Description text | Text | Descripció |

Subseccions de la font: Estat, Interacció i Mida (totes sobre la variant Figma Radio button anterior).

### Botó d'opció avançat

Grup:

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Error | True / False | False |
| Slot | Content | Radio button |
| Text error | Text | Text d'error |

Variant Figma d'error: Advanced Checkbox group [Slot, Text Error = Text d'error, Error = False].

Individual:

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Default / Hover / Focus / Disabled | Unselected |
| Visual element | Icon / Illustration | Default |
| Selected | True / False | False |
| Change Text | Text | Text |
| Show Icon | True / False | True |
| Change Icon (dins Show Icon) | Icon | House |
| Change Illustration | Illustration | Habitatge |

Subseccions de la font: Estat, Element visual i Seleccionat (variant Figma Advanced checkbox [Change text = Text, Change Icon = house, Show Icon = True, Change Illustration = Habitatge, State = Default, Visual element = Icon, Selected = False]).

## Mides i espaiats
- **Small:** els botons d'opció de mida petita funcionen bé a les pàgines on és útil fer-los menys visibles.
- **Medium:** utilitza la mida mitjana en la majoria dels casos.

[discrepància: el disseny (Figma) dóna les mides Medium / Small; el component web dóna `radio-size-L` / `radio-size-M`]

## Comportament i interacció
### Interacció
- Els usuaris poden seleccionar un botó d'opció fent-hi clic.
- Els botons d'opció dins del mateix grup són mútuament excloents: només es pot seleccionar una opció alhora. Quan un usuari selecciona un botó d'opció, qualsevol botó d'opció seleccionat prèviament dins del mateix grup es desselecciona automàticament.

### Adaptació responsiva
- Per a espais reduïts, els textos d'opció llargs poden saltar a una segona línia. En aquests casos, el text creixeria cap avall, de manera que la casella i el text d'opció quedin alineats a la part superior.

## Bones pràctiques

### Botó d'opció estàndard

**Textos descriptius i etiquetes**
- **FER:** Utilitza textos concisos, descriptius i fàcilment comprensibles per les diferents opcions que expliquin de forma clara cadascuna d'elles.
- **NO FER:** Evita l'ús de textos ambigus o poc clars que puguin confondre els usuaris sobre el significat de cada elecció.
- **FER:** Acompanya el grup de botons d'opció d'una etiqueta que descrigui i contextualitzi les opcions que es poden seleccionar.
- **NO FER:** No deixis el llistat de botons de selecció sense una etiqueta que ajudi a entendre i a contextualitzar les opcions disponibles.

**Àrea clicable**
- **FER:** Amplia l'àrea clicable dels botons d'opció, de forma que permeti que l'usuari seleccioni el component fent clic tant en la casella com en el text descriptiu.
- **NO FER:** No limitis l'àrea clicable només a la casella del botó d'opció, això pot augmentar els errors i la frustració de l'usuari.

**Posició**
- **FER:** Organitza els botons d'opció de forma vertical per facilitar l'escaneig de continguts.
- **NO FER:** No organitzis els botons d'opció de manera horitzontal, ja que poden dificultar l'escaneig de continguts.

**Retroalimentació**
- **FER:** En cas d'error relacionat amb els botons d'opció, ofereix missatges d'error clars i orientats a corregir el problema, d'aquesta manera ajudaràs l'usuari a identificar i resoldre la qüestió.
- **NO FER:** Evita els missatges d'error poc clars o confusos, ja que això dificulta la comprensió de l'error i la seva solució per part de l'usuari.
- **FER:** Indica l'error de manera global quan afecti un mateix grup de botons d'opció, oferint una solució clara i concisa per a resoldre-ho.
- **NO FER:** Evita repetir els missatges d'error per a cada botó dins del mateix grup. És millor mostrar el missatge només una vegada, al final del llistat d'opcions, per evitar confusions.

**Utilització**
- **FER:** Utilitza botons d'opció en lloc de menús desplegables quan hi hagi poques opcions a seleccionar, ja que és un component més directe que agilitza els processos de selecció.
- **NO FER:** No utilitzis menús desplegables quan hi hagi poques opcions a seleccionar, ja que poden complicar la selecció i alentir el procés.
- **FER:** Fes ús de valors per defecte quan aquests no condicionin les respostes i quan hi hagi una opció estàndard clara.
- **NO FER:** No facis servir valors per defecte que puguin influir en les respostes dels usuaris quan no existeixi una opció estàndard clara.

### Botó d'opció avançat

**Nombre d'opcions**
- **FER:** Utilitza sempre un mínim de 2 opcions.

**Icones i il·lustracions**
- **NO FER:** No barregis estils (només text, icones o il·lustracions) dins les opcions d'una mateixa pregunta. Aplica el mateix a totes les opcions d'una mateixa pregunta.
- **FER:** Les icones s'han d'utilitzar només per reforçar el reconeixement visual de categories clares i estables en què la icona sigui un estàndard.
- **FER:** Utilitza il·lustracions sempre que les opcions es diferenciïn principalment per una configuració física, espacial o funcional visible.
- **NO FER:** No utilitzis il·lustracions per representar conceptes abstractes o subjectius, com ara nivells d'experiència, preferències personals o estats d'ànim. Quan la diferència entre opcions no és física ni espacial, la il·lustració no aporta informació objectiva i pot induir l'usuari a triar basant-se en la imatge en lloc del text.

Informació més detallada sobre quan utilitzar icones i il·lustracions al patró [arbre de decisions](patro-arbre-de-decisions.md).

## Accessibilitat

### Pautes d'accessibilitat del contingut web (WCAG)
- **Ús del color (A):** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a diferenciar els diferents estats s'inclouen formes (un cercle quan està seleccionat) i es modifica el gruix de les vores (en estat hover). [1.4.1 Ús del color - CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. [1.4.3 Contrast mínim - CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA):** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [1.4.4 Canvia la mida del text - CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA):** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [1.4.11 Contrast d'elements no textuals - CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Espaiat del text (AA):** quan es desenvolupa contingut utilitzant llenguatges de marcatge que permeten aplicar les propietats d'estil de text, no es perd cap contingut ni funcionalitat si s'ajusten les propietats següents: alçada de línia (interlineat) de com a mínim 1,5 vegades la mida de la lletra; espaiat entre els paràgrafs de com a mínim dues vegades la mida de la lletra; espaiat entre lletres (tracking) de com a mínim 0,12 vegades la mida de la lletra; espaiat entre paraules de com a mínim 0,16 vegades la mida de la lletra. [1.4.12 Espaiat del text - CAT](https://www.w3.org/Translations/WCAG22-ca/#text-spacing) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/text-spacing)
- **Teclat (A):** tota la funcionalitat del contingut (navegar pels diferents botons d'opció) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [2.1.1 Teclat - CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Focus visible (AA):** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [2.4.7 Focus visible - CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- **Identificació d'errors (A):** si es detecta un error en el component, s'identifica clarament que aquest presenta un error mitjançant l'aparició d'un element gràfic (línia vertical) i amb la indicació visual (icona) i textual (descripció de l'error) de l'error. [3.3.1 Identificació d'errors - CAT](https://www.w3.org/Translations/WCAG22-ca/#error-identification) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/error-identification)

## Implementació (component web)

### `<radio-component>`

Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat (lloc) |
|---|---|---|---|---|---|
| `group` | `group` | Nom que agrupa els botons d'opció (identificador de grup per a camps de formulari relacionats) | string | `undefined` | Obligatori |
| `isDisabled` | `is-disabled` | Deshabilita o no la selecció | boolean | `false` | Opcional |
| `radioProps` | `radio-props` | Array que conté la informació de cada botó d'opció dins d'un mateix grup. Accepta array d'objectes o string JSON (`RadioProps[]` o string) | string (Array) | (sense valor per defecte; exemple PDF `[]`) | Obligatori |
| `showTooltip` | `show-tooltip` | Mostra o no la icona de l'indicador de funció (opcional) | boolean | `true` | Opcional |
| `sizeRadio` | `size-radio` | Mida dels botons d'opció. Opcions: `radio-size-L`, `radio-size-M` | string | `radio-size-M` | Opcional |
| `textAlternativeError` | `text-alternative-error` | Text alternatiu de l'exclamació del text d'error | string | `undefined` | Opcional |
| `textError` | `text-error` | Text d'error que vols que es mostri. Quan no s'escriu res en aquest camp, no surt cap error | string | `undefined` | Opcional |
| `textEtiqueta` | `text-etiqueta` | Text de l'etiqueta (visible al component) que va al costat de la icona de l'indicador de funció | string | `undefined` | Obligatori |
| `textInfoTooltip` | `text-info-tooltip` | Text de l'indicador de funció de la icona informativa (text que es mostra al tooltip associat) | string | `undefined` | Opcional |
| `value` | `value` | Opció que per defecte surt marcada en carregar el component (valor actual del component) | string | `undefined` | Opcional |
| `visibilityDescription` | `visibility-description` | Mostra o amaga la descripció de totes les opcions | boolean | `true` | Opcional |

**Variants**

| Propietat | Defecte | Valors |
|---|---|---|
| `sizeRadio` | `radio-size-M` | `radio-size-L`, `radio-size-M` |

**Props que accepten JSON.** `radioProps` accepta string JSON (array d'objectes) amb l'estructura `RadioProps`:

| Clau | Descripció | Tipus | Requerida |
|---|---|---|---|
| `option` | Títol de l'opció | string | Sí |
| `description` | Descripció de l'opció | string | Sí |
| `value` | Nom valor de l'opció | string | Sí |

Exemple (PDF):

```json
[
  {
    "option": "texto-ejemplo",
    "description": "texto-ejemplo",
    "value": "texto-ejemplo"
  }
]
```

**Esdeveniments**

| Esdeveniment | Descripció | Tipus / paràmetre | Origen |
|---|---|---|---|
| `valueChange` | Es llança cada vegada que es canvia de botó d'opció (el valor del component canvia) | `CustomEvent<String>` (`value`) | `radio-component` |

**Depèn de:** `tooltip-component` ([Indicador de funció](component-indicador-de-funcio.md)).

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<radio-component 
  class="radio-component" 
  text-etiqueta="Etiqueta prueba" 
  is-disabled="false" 
  text-error=""
  text-alternative-error=""
  value="opcio1"
  group="radio0"
  text-info-tooltip="Texto Tooltip" 
  visibility-description="true" 
  show-tooltip="true"
  size-radio="radio-size-M"
  radio-props='[
          { "option": "Opció 1", "description": "Descripció 1", "value": "opcio1" },
          { "option": "Opció 2", "description": "Descripció 2", "value": "opcio2" },
          { "option": "Opció 3", "description": "Descripció 3", "value": "opcio3" }
        ]'
  ></radio-component>
```

**Exemple d'instància (PDF)**

```html
<radio-component
group="texto-ejemplo"
is-disabled=false
radio-props=[]
show-tooltip=true
size-radio='radio-size-M'
text-alternative-error="texto-ejemplo"
text-error="texto-ejemplo"
text-etiqueta="texto-ejemplo"
text-info-tooltip="texto-ejemplo"
value="texto-ejemplo"
visibility-description=true
></radio-component>
```

Exemple amb props JSON (PDF):

```html
<radio-component
radio-props='[{"option":"texto-ejemplo","description":"texto-ejemplo","value":"texto-ejemplo"}]'
></radio-component>
```

### `<advanced-radio-button-component>`

Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat (lloc) |
|---|---|---|---|---|---|
| `group` | `group` | Nom del grup (identificador de grup per a camps de formulari relacionats) | string | `undefined` | Obligatori |
| `mode` | `mode` | Variant visual del component (manera del botó d'opció; relacionada amb els seus estats). Opcions: `default`, `disabled`, `error` | string | `default` | Obligatori |
| `radioItems` | `radio-items` | Array que conté la informació de cada botó d'opció dins d'un mateix grup. Accepta array d'objectes o string JSON (`AdvancedRadioItem[]` o string) | string (Array) \| Array | (sense valor per defecte; exemple PDF `[]`) | Obligatori |
| `textAlternativeError` | `text-alternative-error` | Text alternatiu de la icona d'error (text del missatge d'error que es mostra a l'usuari) | string | `` (buit) | Opcional |
| `textError` | `text-error` | Text d'error (text del missatge d'error que es mostra a l'usuari) | string | `` (buit) | Opcional |
| `value` | `value` | Valor del component en conjunt (valor actual) | string | `undefined` | Opcional |
| `visualElement` | `visual-element` | Elecció de l'element visual que acompanyi el text (tipus d'element visual decoratiu). Opcions: `icon`, `illustration`, `none` | string | `icon` | Opcional |

[discrepància: el lloc escriu l'atribut de `textAlternativeError` com `textAlternativeError`; el PDF diu `text-alternative-error`]

**Variants**

| Propietat | Defecte | Valors |
|---|---|---|
| `mode` | `default` | `default`, `disabled`, `error` |
| `visualElement` | `icon` | `icon`, `illustration`, `none` |

**Props que accepten JSON.** `radioItems` accepta string JSON (array d'objectes) amb l'estructura `AdvancedRadioItem`:

| Clau | Descripció | Tipus | Requerida |
|---|---|---|---|
| `value` | Value de l'opció | string | Sí |
| `title` | Títol de l'opció | string | Sí |
| `iconOrIllustration` | Si s'ha seleccionat el mode icon, cal introduir la classe de bootstrap. Si s'ha introduït illustration en mode, cal introduir la ruta cap a la il·lustració | string | Sí |

Exemple (PDF):

```json
[
  {
    "value": "texto-ejemplo",
    "title": "texto-ejemplo",
    "iconOrIllustration": "texto-ejemplo"
  }
]
```

**Esdeveniments**

| Esdeveniment | Descripció | Tipus / paràmetre | Origen |
|---|---|---|---|
| `radioChange` | S'emet quan canvia l'opció seleccionada (el lloc diu «en alternar un checkbox») | `CustomEvent<{ index: number; value: string; }>` (lloc: `index`, `checked`, `value`) | `advanced-radio-button-component` |
| `valueChange` | S'emet quan canvia la selecció (el valor del component canvia) | `CustomEvent<string>` (`value`) | `advanced-radio-button-component` |

[discrepància: el lloc llista els paràmetres de `radioChange` com `index` `checked` `value`; el PDF només `{ index: number; value: string; }`]

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<advanced-radio-button-component
    group="radio-grup-error"
    mode="error"
    visual-element="icon"
    text-error="Cal seleccionar una opció"
    text-alternative-error="Error de validació"
    value=''
    radio-items='[
      {"value":"habitatge","title":"Habitatge lorem ipsum dolor ismet, lorem ipsum","iconOrIllustration":"bi-house"},
      {"value":"treball","title":"Treball","iconOrIllustration":"bi-briefcase"}
    ]'>
  </advanced-radio-button-component>
```

**Exemple d'instància (PDF)**

```html
<advanced-radio-button-component
group="texto-ejemplo"
mode='default'
radio-items=[]
text-alternative-error=''
text-error=''
value="texto-ejemplo"
visual-element='icon'
></advanced-radio-button-component>
```

Exemple amb props JSON (PDF):

```html
<advanced-radio-button-component
radio-items='[{"value":"texto-ejemplo","title":"texto-ejemplo","iconOrIllustration":"texto-ejemplo"}]'
></advanced-radio-button-component>
```

## Claus de text (internacionalització)
Vegeu les [claus](dev-referencia-de-claus-disponibles.md) (`radio`).

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.0.0 | 12.0.1 | 14 juliol, 2026 | Desenvolupament: botó d'opció avançat: es canvia el border radius del botó d'opció a 16px. |
| 12.0.0 | 12.0.0 | 10 juliol, 2026 | Desenvolupament: s'utilitza el token correcte per al color de tots els textos. |
| 12.0.0 | 10.1.0 | 29 maig, 2026 | Disseny: modificació del layout i color de la capa per passar les il·lustracions a color neutres en el botó d'opció avançat amb il·lustració. Desenvolupament del component de botó d'opció avançat. |
| 11.0.0 | 9.4.0 | 8 maig, 2026 | Disseny: disseny del component de botó d'opció avançat. |
| 8.5.0 | 9.4.0 | 17 abril, 2026 | Desenvolupament: s'han fet correccions d'estils. |
| 8.5.0 | 7.0.0 | 20 gener, 2026 | Disseny: es modifica el focus per tal que englobi únicament l'input i no el text. |
| 8.3.0 | 7.0.0 | 14 novembre, 2025 | Disseny: canvi d'estil de color del text d'error. De border-error a content-error. |
| 5.0.0 | 7.0.0 | 24 octubre, 2025 | Desenvolupament: resolució de problemes. |
| 5.0.0 | 6.1.0 | 12 setembre, 2025 | Desenvolupament: nova propietat afegida. |
| 5.0.0 | 6.0.0 | 3 juliol, 2025 | Desenvolupament: resolució de problemes. |
| 5.0.0 | 5.0.0 | 10 juny, 2025 | Disseny: s'ha incorporat una nova propietat (Show label), que permet controlar la visualització de l'etiqueta. |
| 2.3.0 | 5.0.0 | 9 juny, 2025 | Desenvolupament: resolució de problemes. |
| 2.3.0 | 1.0.0 | 31 gener, 2025 | Sense canvis. |
| 2.2.0 | 0.1.1 | 20 gener, 2025 | Sense canvis. |
| 2.1.0 | 0.1.1 | 04 desembre, 2024 | Sense canvis. |
| 2.0.0 | 0.1.0 | 02 desembre, 2024 | Sense canvis. |
| 1.1.0 | 0.1.0 | 22 novembre, 2024 | Sense canvis. |
| 1.1.0 | 0.0.4 | 18 novembre, 2024 | Sense canvis. |
| 1.0.0 | 0.0.3 | 1 novembre, 2024 | Disseny, desenvolupament i documentació del component. |

## Vegeu també
- [Casella de selecció](component-casella-de-seleccio.md): per a seleccionar una o més opcions d'una llista predefinida.
- [Desplegable](component-desplegable.md): per a seleccionar un o diversos elements d'una llista d'opcions predefinides.
- [Arbre de decisions](patro-arbre-de-decisions.md)
- [Indicador de funció](component-indicador-de-funcio.md)
