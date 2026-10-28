# Acordió (Accordion)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/075e06 · Web component: `<accordion-component>` (paquet core) · Font actualitzada el 2026-10-22 · Extret el 2026-10-28

## Què és i quan usar-lo
Element que permet mostrar o amagar seccions de contingut de manera vertical, desplegant o replegant cada secció quan l'usuari hi fa clic.

L'acordió és un component que s'utilitza en interfícies d'usuari web i mòbils. S'adapta bé a diferents mides de pantalla i és especialment útil en dissenys on es requereix presentar informació jeràrquica de manera organitzada i compacta.

Els acordions es fan servir per organitzar i presentar contingut de manera compacta i eficient. Són particularment útils en situacions en què l'espai és limitat o quan es vol millorar la claredat i la navegabilitat de grans quantitats d'informació. Casos d'ús:

1. **Informació independent:** quan la informació de cada secció és independent i és poc probable que els usuaris necessitin accés simultani a diverses seccions, s'utilitzarà l'acordió. D'aquesta manera els usuaris poden explorar ràpidament les seccions i desplegar només aquelles que vulguin llegir. Un exemple de bon ús seria aplicar-lo a l'apartat de preguntes freqüents.
2. **Informació pas a pas:** es fa servir per centrar l'atenció en un contingut específic durant processos llargs, com ara en tutorials o guies pas a pas.
3. **Contingut extens:** per a pàgines amb diferents seccions i un contingut molt extens on faci falta estructurar la informació en apartats.
4. **Dispositius petits:** quan el contingut és llarg i la mida de la finestra és petita, com en dispositius mòbils, l'ús de l'acordió és recomanable per organitzar la informació, sempre que no contradigui cap mala pràctica d'usabilitat.

## Quan NO usar-lo / alternatives
- No utilitzar acordions quan l'usuari necessiti consultar la majoria o tot el contingut de la pàgina per trobar respostes.
- No utilitzar-los de manera individual (s'usen en grups d'un mínim de tres).
- Alternatives relacionades: [Enllaços](component-enllacos.md) (per facilitar la navegació entre parts del contingut o funcionalitats) i [Pestanyes](component-pestanyes.md) (per a categories o seccions clarament diferenciades).

## Anatomia
Figma: Accordion [Show Icon = True, Change Icon = bell, Subtitle = True, Title = Títol, Subtitle text = Subtítol, Content slot = (slot de contingut), State = Default, Collapsed = True]. Parts: capçalera amb títol, subtítol opcional i icona opcional, i cos de contingut.

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Default / Hover / Focus / Disabled (*) | Default |
| Collapsed | True / False | True |
| Show Icon | True / False | True |
| Change Icon | Bell | Bell |
| Title | Text | Títol |
| Subtitle | True / False | True |
| Subtitle text | Subtítol | Subtítol |
| Content Slot | Contingut | --- |

(*) L'estat Disabled s'usa en entorn de formularis molt extensos o en entorn per treballadors.

Estats d'expansió:
- **Replegat (collapsed):** el contingut està ocult, i es mostra la capçalera o títol de l'element i, si és necessari, la icona i el distintiu.
- **Desplegat:** quan l'usuari interactua amb la capçalera de l'acordió, sigui fent clic o tocant-la, l'acordió es desplega. En aquest estat, es mostra el contingut complet.

## Comportament i interacció
- **Per defecte:** el component acordió es configura **col·lapsat per defecte** (sense panells oberts) per tal de maximitzar l'estalvi d'espai i garantir la percepció d'un contingut concís i escanejable.
- **Estats:** un acordió generalment té dos estats, replegat i desplegat. Determinen si el contingut associat amb l'element és visible o ocult. Alternar-los facilita la navegació i la visualització del contingut rellevant sense haver d'obrir pàgines noves.
- **Animació de la fletxa:** la icona de la fletxa gira 180° en el moment d'obrir o tancar l'acordió.
- **Tancament de l'acordió:** el component es pot tancar prement el mateix element que l'ha obert. Proporciona una manera senzilla i intuïtiva per a l'usuari d'alternar la visibilitat del contingut.
- **Prevenció del desplaçament:** quan l'acordió s'expandeix, és preferible no desplaçar automàticament la pàgina. Això evita que l'usuari tingui la impressió que s'ha carregat una nova pàgina o secció. Mantenint la pàgina estàtica, l'usuari es manté orientat i concentrat en el contingut de l'acordió desplegat.
- **Replec:** quan se selecciona un acordió, la resta es manté en el seu estat, sense replegar-se automàticament, per evitar que l'usuari perdi el context.
- **Agrupació:** quan s'agrupen més de set acordions consecutius es disposa d'un botó general per replegar o desplegar tot el conjunt.

### Adaptació responsiva
L'acordió s'ha d'adaptar a les mides o disposició de la pàgina, estirant-se fins a completar l'espai. La capçalera s'ha d'adaptar al format mòbil segons els estils tipogràfics establerts ([Tipografia](fonaments-tipografia.md)): Heading-mobile-SM Semibold.

## Bones pràctiques

### Unificar criteris
- **FER:** Assegura't que tots els acordions presentin criteris comuns pel que fa a la iconografia.
- **NO FER:** No deixis que els acordions presentin criteris diversos respecte a la iconografia.
- **FER:** Mantingues coherència en la formulació dels textos de cada acordió (preguntes, afirmacions, etc.).
- **NO FER:** No barregis preguntes i afirmacions en la formulació dels textos de cada acordió.

### Extensió màxima
- **FER:** Utilitza un màxim de cent cinquanta caràcters en el títol de l'acordió. Es recomana emprar el mínim possible.
- **NO FER:** No utilitzis més de cent cinquanta caràcters en el títol de l'acordió.

### Agrupació
- **FER:** Utilitza'ls en grups d'un mínim de tres acordions.
- **NO FER:** No els utilitzis de manera individual.

### Ubicació
- **FER:** Col·loca els elements en les columnes centrals de la pàgina per assegurar una millor visibilitat i accessibilitat.
- **NO FER:** No col·loquis els elements en les columnes laterals de la pàgina, ja que poden ser menys visibles i dificultar la interacció.
- **FER:** Col·loca els acordions dins del contingut de la pàgina per organitzar i presentar la informació de manera clara i ordenada.
- **NO FER:** No col·loquis els acordions en capçaleres, ja que poden confondre i dificultar la navegació.

### Contingut
- **FER:** Utilitza acordions quan l'usuari no necessiti consultar la majoria o tot el contingut de la pàgina per trobar respostes.
- **NO FER:** No utilitzis els acordions quan l'usuari necessiti consultar la majoria o tot el contingut de la pàgina per trobar respostes.

### Subnivells
- **FER:** Utilitza l'acordió amb un únic nivell de profunditat.
- **NO FER:** No utilitzis l'acordió amb més d'un nivell de profunditat.

## Accessibilitat

### Pautes d'accessibilitat del contingut web (WCAG)
- **Orientació (AA), 1.3.4:** el contingut de l'àrea de text s'adapta a les diferents orientacions de la pantalla, com ara vertical o horitzontal, cosa que permet visualitzar el contingut. [CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Ús del color (A), 1.4.1:** el color no es fa servir com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per indicar els diferents estats, s'afegeix una vora en l'estat *hover* i *focus*. A més, la icona canvia entre les opcions de desplegat i replegat, i es mostra la informació de l'acordió quan aquest està desplegat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA), 1.4.3:** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA), 1.4.4:** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Redistribució (AA), 1.4.10:** el contingut es pot presentar sense pèrdua d'informació o funcionalitat, i sense necessitat de desplaçar-se en dues dimensions per: contingut de desplaçament vertical amb una amplada equivalent a 320 píxels CSS; contingut de desplaçament horitzontal a una alçària equivalent a 256 píxels CSS. [CAT](https://www.w3.org/WAI/WCAG22/Understanding/reflow) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/reflow)
- **Contrast d'elements no textuals (AA), 1.4.11:** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. Els elements decoratius, com el divisor, estan exempts. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Espaiat del text (AA), 1.4.12:** quan es desenvolupa contingut utilitzant llenguatges de marcatge que permeten aplicar les propietats d'estil de text, no es perd cap contingut ni funcionalitat si s'ajusten les propietats següents: alçada de línia de com a mínim 1,5 vegades la mida de la lletra; espaiat entre els paràgrafs com a mínim dues vegades la mida de la lletra; espaiat entre lletres de com a mínim 0,12 vegades la mida de la lletra; espaiat entre paraules de com a mínim 0,16 vegades la mida de la lletra. [CAT](https://www.w3.org/Translations/WCAG22-ca/#text-spacing) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/text-spacing)
- **Teclat (A), 2.1.1:** tota la funcionalitat del contingut (navegar pels diferents acordions i replegar-los o desplegar-los) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Focus visible (AA), 2.4.7:** la navegació entre acordions és visible mitjançant un rectangle extern. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

## Implementació (component web)

En aquest component està habilitada la introducció de contingut HTML a cada ítem de l'acordió via `<slot>`. Per fer-ho, utilitza com a referència l'HTML de l'exemple d'ús. A l'atribut `slot` cal escriure "description" seguit de l'índex de l'ítem on es vol introduir l'slot. Per exemple, per introduir un `<slot>` al tercer ítem l'atribut serà "description-2". Si no es vol introduir contingut per aquesta via, es pot fer pel JSON de l'atribut `items`, a la propietat `description`.

### `<accordion-component>`
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat |
|---|---|---|---|---|---|
| `items` | `items` | Elements de l'acordió (col·lecció d'elements; accepta array d'objectes o string JSON). | `items[] \| string` (String (array)) | --- | Obligatori |
| `visibilityBell` | `visibility-bell` | Visibilitat de totes les icones prèvies al títol. | boolean | `true` | Opcional |
| `visibilitySubtitle` | `visibility-subtitle` | Visibilitat de tots els subtítols. | boolean | `true` | Opcional |

**Esdeveniments:** cap esdeveniment declarat.

**Depèn de:** `divider-component` (vegeu [Divisor](component-divisor.md)).

**Props que accepten JSON:** `items` accepta un string JSON (array d'objectes) amb l'estructura següent.

[discrepància: el lloc marca `subtitle`, `description`, `classIcon` i `isDisabled` com a opcionals i només `title` com a obligatori; el PDF marca totes les claus com a requerides]

| Clau (atribut) | Descripció | Tipus | Obligatorietat (lloc) | Requerida (PDF) |
|---|---|---|---|---|
| `title` | Títol de l'element. | string | Obligatori | Sí |
| `subtitle` | Subtítol de l'element. | string | Opcional | Sí |
| `description` | Cos de l'element. | string | Opcional | Sí |
| `classIcon` (`class-icon`) | Classe de Bootstrap de la icona de l'element. | string | Opcional | Sí |
| `isDisabled` | Configuració de l'estat disabled. | boolean | Opcional | Sí |

Exemple (PDF):

```json
[
  {
    "title": "texto-ejemplo",
    "subtitle": "texto-ejemplo",
    "description": "texto-ejemplo",
    "classIcon": "texto-ejemplo",
    "isDisabled": true
  }
]
```

**Exemple d'ús**

```html
<!-- /index.html -->
<accordion-component visibility-bell="true" visibility-subtitle="true" items='[
            { "title": "Item 1", "subtitle": "Subtitle 1", "description": "Description 1", "classIcon": "bi-calendar-fill", "isDisabled": true },
            { "title": "Item 2", "subtitle": "Subtitle 2", "description": "Description 2", "classIcon": "bi-camera", "isDisabled": false },
            { "title": "Item 3", "subtitle": "Subtitle 3", "description": "Description 3", "classIcon": "bi-bell", "isDisabled": false },
            { "title": "Item 4", "subtitle": "Subtitle 4", "description": "Description 4", "classIcon": "bi-calendar-fill", "isDisabled": false },
            { "title": "Item 5", "subtitle": "Subtitle 5", "description": "Description 5", "classIcon": "bi-camera", "isDisabled": false },
            { "title": "Item 6", "subtitle": "Subtitle 6", "description": "Description 6", "classIcon": "bi-bell", "isDisabled": false },
            { "title": "Item 7", "subtitle": "Subtitle 7", "description": "Description 7", "classIcon": "bi-calendar-fill", "isDisabled": false },
            { "title": "Item 8", "subtitle": "Subtitle 8", "description": "Description 8", "classIcon": "bi-camera", "isDisabled": false }
          ]'>
        <div slot="description-1">
          <p>Aquest és un contingut <strong>custom</strong> per a l'acordió 1. 
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
          </p>
        </div>
    </accordion-component>
```

**Exemples d'instància (PDF)**

```html
<accordion-component
  items=[]
  visibility-bell=true
  visibility-subtitle=true
></accordion-component>
```

```html
<accordion-component
  items='[{"title":"texto-ejemplo","subtitle":"texto-ejemplo","description":"texto-ejemplo","classIcon":"texto-ejemplo","isDisabled":true}]'
></accordion-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 10.0.0 | 9.4.0 | 17 abril, 2026 | Disseny: s'apliquen slots al components per afegir contingut. Desenvolupament: millores d'accessibilitat. |
| 4.0.0 | 6.0.0 | 3 juliol, 2025 | Desenvolupament: resolució de problemes. |
| 4.0.0 | 5.0.0 | 9 juny, 2025 | Desenvolupament: resolució de problemes. |
| 4.0.0 | 3.0.0 | 02 maig, 2025 | Disseny: s'ajusta l'espaiat entre acordions i del padding superior. |
| 2.3.0 | 3.0.0 | 28 abril, 2025 | Desenvolupament: resolució de problemes. |
| 2.2.0 | 0.1.1 | 20 gener, 2025 | Disseny: s'ajusta l'estat "Focus" amb un marge de 2 px per a millor alineació visual. |
| 2.1.0 | 0.1.1 | 04 desembre, 2024 | Disseny: s'ajusta l'alineació a l'esquerra i els espaiats superior i inferior. |
| 1.0.0 | 0.0.3 | 1 novembre, 2024 | Disseny, desenvolupament i documentació del component. |

Release notes (llegat): 1.0 · 10 d'abril, 2024.

## Vegeu també
- [Enllaços](component-enllacos.md)
- [Pestanyes](component-pestanyes.md)
- [Divisor](component-divisor.md)
- [Botons](component-botons.md)
- [Tipografia](fonaments-tipografia.md)
