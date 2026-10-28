# Paginació (Pagination)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/049885 · Web component: `<pagination-component>` (paquet core) · Font actualitzada el 2026-10-22 · Extret el 2026-10-28

## Què és i quan usar-lo
La paginació separa grups de contingut en diverses pàgines indicant a l'usuari on es troba.

S'utilitza per **gestionar grans quantitats de resultats** que no caben en una sola pàgina. Ajuda a reduir els temps de càrrega del sistema i evita sobrecarregar l'usuari amb un excés d'informació en una única vegada. És comunament aplicada en situacions com **taules, resultats de cerca i directoris**, facilitant la navegació i l'accés a la informació de manera organitzada i escalonada.

### Paginació numerada
Mostra els números de pàgina i permet navegar d'una en una o saltar directament a una pàgina concreta. És la variant estàndard per als resultats de cerca, llistats i directoris, on l'ordre dels resultats és rellevant per a l'usuari.

### Resultats per pàgina
Permet a l'usuari triar quantes files vol veure simultàniament. Està pensada per a taules de dades on el contingut s'organitza en files i columnes, i l'usuari necessita llegir o comparar registres, encara que també pot usar-se en altres casos com resultats de cerca o directoris. Ajustar el nombre de files és especialment útil en pantalles grans o quan es treballa amb moltes dades.

El selector de resultats per pàgina es mostra quan el nombre total de registres és igual o superior al valor mínim configurat (12 per defecte). Pot aparèixer tant si els resultats es distribueixen en diverses pàgines com si tots caben en una única pàgina. Quan el nombre total de registres és inferior a aquest llindar, el selector s'oculta.

Quan la paginació numerada és visible, el selector de resultats per pàgina l'acompanya sempre. En aquest cas, és **imprescindible que el component sigui visible de forma consistent en tots els punts de tall** (breakpoints): si la paginació apareix en desktop, ha d'estar accessible també en tablet i mòbil.

### Paginació, desplaçament infinit i carregar més

| Mètode | Pros | Contres |
|---|---|---|
| Paginació | Ofereix una navegació estructurada i previsible, reduint la càrrega cognitiva. / Facilita la referència de contingut, cosa que permet als usuaris tornar a pàgines específiques. / Regula les expectatives dels usuaris mostrant la quantitat de dades disponibles. / Proporciona una sensació de progrés i assoliment quan es passa de pàgina. / Els resultats per pàgina proporcionen control. | Experiència de navegació interrompuda amb clics addicionals, que pot ser frustrant per als usuaris. / Càrrega inicial més lenta, que pot dissuadir alguns usuaris de continuar navegant. |
| Scroll infinit | Navegació fluida i sense interrupcions, que ofereix una experiència contínua. / Augmenta el temps de permanència a la pàgina, ja que els usuaris continuen explorant sense necessitat de clics addicionals. / Interfície neta sense botons addicionals, que permet centrar-se en el contingut. / Ideal per a contingut visual o social on es vol fomentar la descoberta contínua. / Ideal per a visualització mòbil. | Pot provocar addicció i ús excessiu, dificultant la desconnexió. / Difícil de tornar a un punt específic, especialment en llocs amb molt contingut. / Pot resultar aclaparador amb contingut interminable, sense una estructura clara. / No es pot arribar al peu de pàgina. / Pot crear problemes de rendiment amb càrregues contínues, especialment en dispositius amb menys recursos. |
| Carregar més | Combinació de control i fluïdesa, pel fet que permet carregar més contingut a voluntat. / Redueix el temps de càrrega inicial, perquè només es carrega una part del contingut al principi. / Botó discret i fàcil d'entendre, que no interfereix amb la navegació principal. / Proporciona una sensació de control als usuaris, ja que decideixen quan carregar més contingut. | Pot ser molest per als usuaris haver de fer clic repetidament per veure més contingut. / Interromp la navegació contínua, fent que l'experiència sigui menys fluida que el scroll infinit. / Pot resultar poc intuïtiu per a alguns usuaris que esperen una navegació més contínua. / No és ideal per a grans quantitats de contingut, pel fet que pot suposar haver de fer molts clics. |

L'opció de **carregar més** s'utilitza principalment en contextos en què es vol fomentar l'exploració de l'usuari. Els contextos més recomanats són:
- Galeries d'imatges o vídeos.
- Seccions de notícies i actualitzacions.
- Agenda d'activitats i esdeveniments.
- Informació en estat real de situacions com a resultats d'eleccions, estat del trànsit, emergències, etc.

Aquest carregar més es pot substituir per l'opció de **desplaçament infinit**, encara que no és recomanable.

## Anatomia
Figma: `_Results per page` [State = Default]; `_Pagination` [State = First]; Load more [Show Results = True, Results seen = "Has vist 20 resultats de 250", Results shown = "Resultats del 10 al 20 de 250", Error text = "Text d'error", State = Default].

## Variants, tipus i estats

Items de paginació (`_Pagination item`):

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Default / Hover / Pressed / Focus / Selected | Default |
| Collapsed | True / False | False |

Variant Figma: `_Pagination item` [Collapsed = False, State = Default].

Paginació (`_Pagination`):

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | First / Second / Middle / Last | First |

Resultats per pàgina (desplegable, `_Results per page`):

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Default / Focus | Default |

Carregar més (Load more):

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Default / Loading / Results / Error | Default |
| Show Results | True / False | True |

## Comportament i interacció

### Paginació
- Es pot navegar a través dels **números**, dels enllaços **anterior** (per navegar a les pàgines anteriors) i **posterior** (per navegar a les següents pàgines) i dels **salts de pàgines** (truncat) per desplaçar el nombre de pàgines que s'està visualitzant (per exemple, si la paginació mostra a la part central les pàgines 5, 6, 7, 8 i 9, en seleccionar el salt de pàgina dret es mostren les pàgines 10, 11, 12, 13, 14 i 15).
- Quan està activa la primera pàgina, no es mostra l'enllaç "anterior".
- Sempre hi ha un element actiu indicat de forma clara.
- El nombre de resultats per defecte és de deu. [discrepància: aquesta frase diu deu; la secció "Resultats per pàgina" diu 12 per defecte]

### Resultats per pàgina
- En seleccionar les files per pàgina, s'activa un menú desplegable per seleccionar el nombre de files per pàgina. Això canvia l'interval que es mostra actualment.
- Si no hi ha prou espai per desplegar les opcions cap avall perquè és el final de la pantalla, es desplega cap amunt.
- El nombre de resultats per defecte és de 12. Les opcions per defecte són: 12, 24, 48, 96.

La visualització dels controls de paginació depèn del nombre total de registres disponibles:

| Situació | Selector de registres per pàgina | Paginació numerada |
|---|---|---|
| Menys de 12 registres | Ocultar | Ocultar |
| 12 o més registres que caben en una única pàgina | Mostrar | Ocultar |
| Resultats distribuïts en més d'una pàgina | Mostrar | Mostrar |

La paginació numerada només es mostra quan existeixen diverses pàgines de resultats. El selector de registres per pàgina es manté visible sempre que el nombre de registres sigui igual o superior al valor mínim configurat.

### Carregar més
Quan l'usuari selecciona el botó per carregar més, si no es pot fer una estimació del temps total de càrrega ni indicar-ne el progrés i es preveu un temps d'espera entre dos i deu segons, s'utilitza l'estat loading.

### Adaptació responsiva
- El component ocupa tot l'espai de pantalla mostrant fins a un màxim de nou elements (comptant pàgina inicial i final i elements de col·lapse) i es va reduint en funció de la mida de la pantalla.
- En versions mòbils no s'utilitza l'opció de resultats per pàgina.
- En cas que es decideixi utilitzar "resultats per pàgina", aquest ha d'aparèixer en **tots els punts de tall**.
- Figma: Adaptació desktop, tablet i mobile.

## Contingut i microcopy
Exemples de la font: "Has vist 20 resultats de 250", "Resultats del 10 al 20 de 250", "Text d'error", "Carrega més".

## Bones pràctiques

### Paginació
- **FER:** Inclou la paginació en la part inferior de la pàgina o element al qual acompanya (com una taula). Això permet a l'usuari veure tots els detalls i contingut abans de passar a més informació.
- **NO FER:** No incloguis la paginació en la part superior de la pàgina o element al qual acompanya (com una taula).
- **FER:** Identifica clarament a quina pàgina es troba l'usuari, mostrant el número de pàgina actual i el nombre total de pàgines.
- **NO FER:** No deixis sense identificar la pàgina en la qual es troba l'usuari.
- **FER:** Mostra o dona context sobre la primera i l'última pàgina.
- **NO FER:** No oblidis mostrar o donar context sobre la primera i l'última pàgina.

### Carregar més (redacció)
- **FER:** Segueix la guia de comunicació clara ([Comunicació clara](fonaments-comunicacio-clara.md)). Utilitza l'imperatiu en català o l'infinitiu en castellà.

## Accessibilitat

### Pautes WCAG
- **Orientació (AA):** el contingut s'adapta a les diferents orientacions de la pantalla, com ara vertical o horitzontal, cosa que permet visualitzar el contingut. [1.3.4 CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Ús del color (A):** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per indicar els diferents canvis d'estat es modifiquen els píxels de la vora del component i/o s'afegeixen elements complementaris com la segona vora pel focus o la icona i el text d'error (carregar més). [1.4.1 CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. [1.4.3 CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Contrast d'elements no textuals (AA):** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [1.4.11 CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A):** tota la funcionalitat del contingut (navegar pels diferents botons) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [2.1.1 CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Focus visible (AA):** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [2.4.7 CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

### Navegació per teclat

| Tecla | Acció |
|---|---|
| Tabulació | Navegar al següent element interactiu. |
| Shift + Tabulació | Navegar a l'anterior element interactiu. |
| Intro / Enter | Activa l'element seleccionat. |

## Implementació (component web)

### `<pagination-component>`

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat |
|---|---|---|---|---|---|
| `loadButtonText` | `load-button-text` | En mode `load`, text del botó | `string` | `undefined` | Opcional |
| `mode` | `mode` | Alternar entre mode paginació o mode resultats carregats. Opcions: `load`, `pagination` | `string` | `pagination` | Opcional |
| `paginationResultsVisibility` | `pagination-results-visibility` | Per mostrar o no els resultats de la pàgina | `boolean` | `true` | Opcional |
| `resultsRange` | `results-range` | Rang de resultats vistos (mode `load` - `option-2`), p. ex. "1–10 de 100" | `string` (array) | `undefined` | Opcional |
| `resultsSeen` | `results-seen` | Resultats vistos (mode `load` - `option-1`) | `string` | `undefined` | Opcional |
| `textAlternativeError` | `text-alternative-error` | Text alternatiu de l'exclamació del text d'error | `string` | `undefined` | Opcional |
| `textError` | `text-error` | Text d'error que es vol mostrar; si no, no s'escriu res en aquest camp | `string` | `undefined` | Opcional |
| `textLoadResult` | `text-load-result` | Alternar entre les dues opcions de text de visualització de resultats en el mode `load`. Opcions: `option-1`, `option-2` | `string` | `option-1` | Opcional |
| `totalPages` | `total-pages` | Nombre total de pàgines que tindrà la paginació | `number` | `undefined` | Obligatori |
| `totalResults` | `total-results` | Resultats totals (mode `load` - `option-1`/`option-2`) | `string` | `undefined` | Opcional |

**Propietats de l'array `resultsRange`**

| Propietat | Descripció | Atribut | Obligatori | Tipus |
|---|---|---|---|---|
| `resultsRange` | Indica el rang de resultats que es mostraran | `results-range` | Opcional | `string` |

**Variants**

| Propietat | Valors | Defecte |
|---|---|---|
| `mode` | `pagination` `load` | `pagination` |
| `textLoadResult` | `option-1` `option-2` | `option-1` |

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre / tipus | Origen |
|---|---|---|---|
| `blurButton` | Es llança cada cop que es treu el focus en un botó | - | `button-component` |
| `focusButton` | Es llança cada cop que es fa focus en un botó | - | `button-component` |
| `handlerClick` | Es llança cada cop que es fa clic en un botó i com a paràmetre conté les dades de l'esdeveniment | `id` | `button-component` |
| `valueChange` | Salta en fer clic en una opció o opcions del desplegable | `value` | `dropdown-component` |
| `blurLink` | Es llança cada cop que es treu el focus en un enllaç | - | `link-component` |
| `focusLink` | Es llança cada cop que es fa focus en un enllaç | - | `link-component` |
| `linkEmit` | Es llança cada cop que es fa clic en un enllaç | `id` | `link-component` |
| `pageChange` | Esdeveniment llançat en canviar de pàgina (PDF: s'emet quan canvia la pàgina activa) | `currentPage`, `rowsPerPage` — `CustomEvent<{ currentPage: number; rowsPerPage: number; }>` | `pagination-component` |
| `rowsPerPageChange` | Esdeveniment llançat en canviar el nombre de files mostrades en taules dinàmiques | `rowsPerPage` — `CustomEvent<number>` | `pagination-component` |

**Depèn de:** `button-component` ([Botons](component-botons.md)), `dropdown-component` ([Desplegable](component-desplegable.md)), `link-component` ([Enllaços](component-enllacos.md)).

**Utilitzat per:** `dynamic-tables-component` ([Taules dinàmiques](component-taules-dinamiques.md)); el PDF el nomena `dynamic-table-component`.

**Exemple d'ús**

```html
<!-- /index.html -->
<pagination-component 
  total-pages="25" 
  pagination-results-visibility="true" 
  results-seen="10"
  mode="pagination" 
  text-error="Text d'error" 
  text-alternative-error="Text alternative error" 
  load-button-text="Carrega més" 
  text-load-result="option-2" 
  results-range='["10","20"]' 
  total-results="40">
</pagination-component>
```

Exemple d'instància (PDF):

```html
<pagination-component
load-button-text="texto-ejemplo"
mode='pagination'
pagination-results-visibility=true
results-range="texto-ejemplo"
results-seen="texto-ejemplo"
text-alternative-error="texto-ejemplo"
text-error="texto-ejemplo"
text-load-result='option-1'
total-pages=0
total-results="texto-ejemplo"
></pagination-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 8.5.0 | 12.1.1 | 11 setembre, 2026 | **Desenvolupament**: corregit el problema de paginació en taules dinàmiques |
| 8.5.0 | 11.0.0 | 19 juny, 2026 | **Desenvolupament**: ajustos d'accessibilitat per al lector de pantalla; es simplifica la paginació deixant només una única vista per a tots els breakpoints |
| 8.5.0 | 9.2.0 | 27 febrer, 2026 | **Desenvolupament**: l'alineació de la paginació es canvia a flex-start |
| 8.5.0 | 9.1.0 | 6 febrer, 2026 | **Desenvolupament**: es fan ajustaments flex wrap; es fan adaptacions d'accessibilitat pel que fa a mides de font extra gran i augment de pantalla |
| 8.5.0 | 6.2.1 | 20 gener, 2026 | **Disseny**: es modifica el component de "pagination" perquè s'adapti a tots els punts de tall i cada element salti de línia en funció de l'espai; la posició del component de resultats per pàgina es col·loca inferiorment a la paginació en tots els punts de tall. |
| 8.1.0 | 6.2.1 | 6 octubre, 2025 | **Disseny**: es recol·loca la posició del desplegable de l'asset Results per page. **Desenvolupament**: nova propietat afegida o eliminada |
| 8.0.0 | 6.1.0 | 12 setembre, 2025 | **Disseny**: es nomena correctament la capa de l'error del carregar més. **Desenvolupament**: resolució de problemes |
| 6.0.0 | 5.0.0 | 8 juliol, 2025 | **Disseny**: es modifiquen les opcions de desplegable de resultats per pàgina perquè siguin múltiples de 3-4. **Desenvolupament**: resolució de problemes |
| 4.0.0 | 5.0.0 | 9 juny, 2025 | **Desenvolupament**: resolució de problemes |
| 4.0.0 | 4.0.1 | 19 maig, 2025 | **Desenvolupament**: resolució de problemes |
| 2.4.0 | 2.0.0 | 10 març, 2025 | **Disseny**: s'ajusta l'estil de l'estat *hover* (en passar el ratolí) i *pressed* (premut) de la paginació replegada (s'inclou línia inferior). |
| 2.3.0 | 2.0.0 | 7 març, 2025 | **Desenvolupament**: resolució de problemes. |
| 2.3.0 | 1.0.0 | 31 gener, 2025 | **Disseny**: ajustament d'estils. |
| 2.2.0 | 0.1.1 | 20 gener, 2025 | **Disseny**: s'han creat els combinats del component en les tres mides disponibles per garantir la seva adaptabilitat. |
| 2.1.0 | 0.1.1 | 04 desembre, 2024 | Sense canvis. |
| 2.0.0 | 0.1.0 | 02 desembre, 2024 | Sense canvis. |
| 1.1.0 | 0.1.0 | 22 novembre, 2024 | Sense canvis. |
| 1.1.0 | 0.0.4 | 18 novembre, 2024 | Sense canvis. |
| 1.0.0 | 0.0.3 | 1 novembre, 2024 | **Disseny**, **desenvolupament** i **documentació** del component. |

## Vegeu també
- [Botons](component-botons.md): per realitzar accions.
- [Enllaços](component-enllacos.md): per facilitar la navegació entre parts del contingut o funcionalitats.
- [Desplegable](component-desplegable.md)
- [Taules dinàmiques](component-taules-dinamiques.md)
- [Mostra més](component-mostra-mes.md)
