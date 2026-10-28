# Xips (Chips)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/379eca · Web component: `<chip-component>` (paquet core) · Font actualitzada el 2026-10-22 · Extret el 2026-10-28

## Què és i quan usar-lo
Una xip és un component que representa informació breu o accions específiques de forma visualment compacta. Permet a l'usuari interactuar amb aquesta informació, sigui seleccionant, eliminant o visualitzant un valor actiu dins d'un conjunt.

És un component d'interfície compacte i interactiu que permet seleccionar, aplicar o eliminar informació breu dins d'un conjunt. És especialment útil per gestionar filtres, opcions o categories de manera visualment clara i eficient, optimitzant l'espai disponible sense comprometre l'experiència d'usuari.

Dins del sistema es distingeixen dues variants del component Xip: les de **filtre** (*dismissible*) i les de **selecció** (*choice*). Cada una té comportaments i disseny específics:
- Les **xips de selecció** es troben dins de modals, panells laterals o filtres emergents, com a part d'un procés de selecció no definitiva.
- Les **xips de filtre** s'utilitzen principalment en pàgines de resultats o seccions de contingut, mostrant els filtres actius que l'usuari pot modificar o eliminar.

Quan s'utilitza:
- Quan l'usuari selecciona criteris per filtrar contingut (com categories, preus, marques...), mostrar aquestes seleccions i permetre'n l'eliminació ràpida.
- Dins de components emergents (com modals o llençols en dispositius mòbils), les xips permeten escollir múltiples opcions d'una manera visual i clara.
- Per fer seleccions múltiples dins d'un conjunt.
- Per representar eleccions que poden ser modificades.
- Quan cal optimitzar l'espai.
- Per visualitzar categories seleccionades amb opcions de modificació com en llistats o pàgines de resultats.

## Quan NO usar-lo / alternatives
- Per executar accions primàries (com "Desar", "Enviar" o "Continuar"), utilitza un [botó](component-botons.md).
- Per mostrar una categoria, estat o etiqueta sense interacció, utilitza una [etiqueta](component-etiquetes.md).
- Per mostrar nombres o estats, utilitza la [insígnia](component-insignia.md).
- Per navegar entre pantalles o seccions, utilitza [pestanyes](component-barra-de-pestanyes.md) o un altre component de navegació.
- En entorns amb poc espai sense una jerarquia clara, utilitza un altre patró com ara una [llista](component-llista.md) de caselles de selecció.

## Anatomia
Figma: Anatomia (DOC_Chips/Anatomia) i Mostra més (DOC_Chips/Anatomia/Mostramés).

### Nom del filtre: quan mostrar-lo
El gestor pot definir quan mostrar el nom del filtre i quan no.
- **Per defecte**, només es mostra el valor seleccionat (ex. Exposicions).
- **Mostrar el nom del filtre** en els casos següents:
  - Quan hi ha múltiples filtres actius del mateix tipus.
  - Quan el valor coincideix amb el d'un altre filtre (ex. *Barcelona* com a ubicació i com a organisme).
  - Quan el resultat del filtre és un número (ex. *6* en Nota de tall: 6).

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Type | Filter / Choice | Filter |
| Show button | True / False | False |
| States | Default / Hover / Pressed / Focus | Default |
| Selected | True / False | False |
| Label | Text | Text |
| Show icon | True / False | False |
| Show clean chip button | True / False | False |
| Collapsed | True / False | False |
| Show Tooltip | True / False | False |
| Structure | Group / Single | - |
| Size | Small / Large | - |

Variants Figma:
- Tipus: Chips [Show button = False, Type = Filter].
- Estats xips de filtre: `_Filter_Chip_States` [Show icon = False, Change Icon = geo-alt, Label = Etiqueta, States = Default, Selected = True, Size = Small].
- Estats xips de selecció: `_Choice_Chip_States` [Show icon = False, Change Icon = geo-alt, Label = Etiqueta, States = Default, Selected = False, Size = Small].
- Mida: ambdues variants anteriors amb Size = Small (i Large; vegeu l'historial de versions: mida Large de 56 px).

## Comportament i interacció

### Interacció
- Les **xips de filtre**, que tenen la icona d'aspa, permeten eliminar el filtre aplicat amb un sol clic. Apareixen sempre que un filtre ja ha estat seleccionat i aplicat directament sobre el contingut.
- Les **xips de selecció**, que no inclouen cap creu, s'activen i es desactiven amb un sol clic. No impliquen una acció immediata sobre el contingut, sinó que formen part d'un procés de tria prèvia, habitualment en panells o modals.

### Visibilitat i adaptabilitat
- Quan les **xips de filtre** es mostren agrupades, el component limita la seva visualització a dues línies màximes independentment del dispositiu. Si el nombre de xips és superior, a la tercera línia apareix un botó "Mostra més" que desplega la resta. Aquest comportament permet evitar la saturació visual en pàgines amb molts filtres aplicats.
- Les **xips de selecció** no tenen límit de línies ni apareix cap botó per mostrar-ne més. La interfície es pot adaptar segons sigui necessari, ja que aquestes xips no formen part d'un entorn amb contingut ja actiu, sinó d'una etapa de configuració.

Figma: comparativa (DOC_Xips/Disseny/Comportament/comparativa).

## Bones pràctiques

### Contingut
- **FER:** Les xips han de ser concises i clares. El contingut ha d'incloure noms (seleccionables) o verbs (operacionals).
- **NO FER:** No utilitzis adjectius per descriure estats o noms per indicar categories, ja que pot portar a confondre's amb una etiqueta.
- **NO FER:** Evita, sempre que sigui possible, utilitzar etiquetes de les xips amb més de 20 caràcters. Si sobrepassa el límit, saltarà a segona línia.

### Funcionalitat
- **FER:** Utilitza xips de filtre (que inclouen la icona d'aspa) per mostrar filtres ja aplicats directament en el contingut.
- **NO FER:** No mostris la icona d'aspa en filtres encara no aplicats o en fase de selecció, ja que pot generar confusió.
- **NO FER:** Evita utilitzar les xips de filtre amb icones de confirmació, ja que poden crear confusió sobre l'estat de la selecció.

## Accessibilitat

### Pautes WCAG
- **Ús del color (A):** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual (per diferenciar els diferents estats). [1.4.1 CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. [1.4.3 CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA):** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [1.4.4 CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA):** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [1.4.11 CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Espaiat del text (AA):** quan es desenvolupa contingut utilitzant llenguatges de marcatge que permeten aplicar propietats d'estil de text, no es perd cap contingut ni funcionalitat si s'ajusten les propietats següents: alçada de línia (interlineat) de com a mínim 1,5 vegades la mida de la lletra; espaiat entre paràgrafs de com a mínim dues vegades la mida de la lletra; espaiat entre lletres (*tracking*) de com a mínim 0,12 vegades la mida de la lletra; espaiat entre paraules de com a mínim 0,16 vegades la mida de la lletra. [1.4.12 CAT](https://www.w3.org/Translations/WCAG22-ca/#text-spacing) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/text-spacing)
- **Teclat (A):** tota la funcionalitat del contingut (navegar per les diferents xips) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [2.1.1 CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Focus visible (AA):** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [2.4.7 CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

## Implementació (component web)

### `<chip-component>`

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat |
|---|---|---|---|---|---|
| `chips` | `chips` | Dades de les xips. Accepta array d'objectes o string JSON | `string` (array) | `[]` | Obligatori |
| `idChips` | `id-chips` | Identificador del component chips | `string` | `undefined` | (no indicat al lloc) |
| `showTooltip` | `show-tooltip` | Mostra o oculta la icona informativa, indicant la funcionalitat de l'etiqueta | `boolean` | `false` | Opcional |
| `textEtiqueta` | `text-etiqueta` | Text de l'etiqueta que va al costat de la icona | `string` | `undefined` | Opcional |
| `textInfoTooltip` | `text-info-tooltip` | Text de l'indicador de funció de la icona informativa (tooltip associat) | `string` | `undefined` | Opcional |
| `type` | `type` | Tipus de xip: `filter` o `choice` | `string` | `filter` | Obligatori |

**Propietats de l'array `chips`**

| Propietat | Atribut | Descripció | Tipus | Obligatorietat |
|---|---|---|---|---|
| `text` | `text` | Text del xip | `string` | Obligatori |
| `icon` | `icon` | Icona del xip | `string` | Opcional |

**Variants**

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `type` | `filter` `choice` | `filter` |

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre / tipus |
|---|---|---|
| `chipsActiveEmit` | Es llança cada cop que es fa clic en un xip de tipus elecció, enviant un array amb tots els xips seleccionats | Array dels xips seleccionats — `CustomEvent<{ text: string; icon?: string; }[]>` |
| `chipDeletedEmit` | Es llança cada cop que s'elimina un xip de tipus filtre, emetent el xip esborrat | Xip eliminat — `CustomEvent<{ text: string; icon?: string; }>` |
| `chipClearDOM` | Es llança cada cop que s'eliminen tots els xips i també el component | Xips eliminats — `CustomEvent<chipClearDOMEvent>` |

**Depèn de:** `show-more-component`, `tooltip-component`, `button-component` ([Botons](component-botons.md)).

**Utilitzat per:** `filters-component` ([Filtres](component-filtres.md)).

**Exemple d'ús**

```html
<!-- /index.html -->
<chip-component 
      type="filter"
      chips='[{"text":"Marketing","icon":"bi-megaphone"},{"text":"Diseño","icon":"bi-palette"},{"text":"Ventas"},{"text":"Finanzas"},{"text":"Recursos Humanos"},{"text":"Logística"},{"text":"Legal"},{"text":"Atención al Cliente"},{"text":"Producto"},{"text":"Tecnología","icon":"bi-cpu"},{"text":"Datos","icon":"bi-bar-chart"},{"text":"Calidad"},{"text":"Operaciones"},{"text":"Innovación"},{"text":"Sostenibilidad"}]'
      text-etiqueta="Etiqueta"
      text-info-tooltip="Text Tooltip"
      show-tooltip="true"  
  ></chip-component>
```

Exemple d'instància (PDF):

```html
<chip-component
chips='[]'
id-chips="texto-ejemplo"
show-tooltip=false
text-etiqueta="texto-ejemplo"
text-info-tooltip="texto-ejemplo"
type='filter'
></chip-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 9.1.0 | 12.0.0 | 10 juliol, 2026 | **Desenvolupament**: s'utilitza el token correcte per al color de la icona i de la creu de tancament |
| 9.1.0 | 10.1.0 | 29 maig, 2026 | **Desenvolupament**: s'ajusta el text truncat del chip; es fan ajustos de comportament |
| 9.1.0 | 9.4.0 | 17 abril, 2026 | **Desenvolupament**: s'han fet ajustos en el color de la vora. |
| 9.1.0 | 8.5.0 | 20 març, 2026 | **Disseny**: s'ha modificat un "clip content" d'un dels frames de la xip tipus "choice"; s'ha modificat el color de la vora de la xip tipus "choice". |
| 9.0.0 | 8.5.0 | 27 febrer, 2026 | **Disseny**: s'ha eliminat la configuració específica per a xips amb text llarg; s'ha retirat el truncament de text; s'ha eliminat el tooltip associat a la visualització del contingut complet de la xip; s'han eliminat les restriccions de màxim d'amplada; s'ha incorporat una nova mida Large (56 px). |
| 8.1.0 | 8.5.0 | 5 desembre, 2025 | **Desenvolupament**: resolució de problemes menors |
| 8.1.0 | 8.0.0 | 14 novembre, 2025 | **Desenvolupament**: resolució de problemes |
| 8.1.0 | 7.0.0 | 24 octubre, 2025 | **Desenvolupament**: resolució de problemes |
| 8.1.0 | 6.2.1 | 3 octubre, 2025 | **Desenvolupament**: resolució de problemes. |
| 8.1.0 | 6.0.0 | 6 octubre, 2025 | **Disseny**: s'ha afegit un tooltip opcional a cada xip. Quan el text d'un chip excedeix el límit establert, aquest es trunca visualment. El tooltip mostra tot el text complet permetent llegir-lo íntegrament. També s'ha modificat el màxim de l'etiqueta de la xip tipus filtre a 216 px d'amplada. |
| 5.0.0 | 6.0.0 | 12 setembre, 2025 | **Desenvolupament**: resolució de problemes |
| 5.0.0 | 6.0.0 | 3 juliol, 2025 | **Desenvolupament**: resolució de problemes |
| 5.0.0 | 5.0.0 | 10 juny, 2025 | **Disseny**: s'ha incorporat una nova propietat (*Show label*), que permet controlar la visualització de l'etiqueta. S'afegeix el botó de netejar tots els filtres als xips de filtre. |
| 4.0.0 | 5.0.0 | 9 juny, 2025 | **Desenvolupament**: resolució de problemes |
| 4.0.0 | 4.0.1 | 19 maig, 2025 | **Desenvolupament** del component |
| 4.0.0 | - | 2 maig, 2025 | **Disseny** i **documentació** del component |

## Vegeu també
- [Casella de selecció](component-casella-de-seleccio.md): per seleccionar una o més opcions d'una llista predefinida.
- [Desplegable](component-desplegable.md): per seleccionar un o diversos elements d'una llista d'opcions predefinides.
- [Botó d'opció](component-boto-d-opcio.md): per seleccionar una opció dins d'un conjunt d'opcions mútuament excloents.
- [Botons](component-botons.md): permet a l'usuari dur a terme accions en una pàgina o pantalla.
- [Etiquetes](component-etiquetes.md)
- [Insígnia](component-insignia.md)
- [Filtres](component-filtres.md)
- [Mostra més](component-mostra-mes.md)
