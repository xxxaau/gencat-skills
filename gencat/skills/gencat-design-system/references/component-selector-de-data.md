# Selector de data (Date picker)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/35c671 · Web component: `<date-picker-component>` (paquet core) · Font actualitzada el 2026-10-22 · Extret el 2026-10-28

## Què és i quan usar-lo
El calendari permet als usuaris seleccionar una única instància o interval de dates.

Facilita als usuaris l'elecció de dates, siguin anteriors, actuals o futures. Els casos més habituals són:
- Quan es requereix que l'usuari proporcioni una data concreta o aproximada, com en els formularis, per a esdeveniments importants o informació personal.
- Per a la planificació i la programació d'activitats.
- Per filtrar dades per dates específiques.

### Selecció única o selecció de rang
En un únic selector de dates, l'usuari pot introduir manualment una data al camp de text o seleccionar una data específica del calendari del menú. Cal seleccionar un dia, un mes i un any. El selector d'interval de dates funciona de manera molt semblant, però en lloc de triar només una data, l'usuari pot triar una data d'inici i una data de finalització.

### Camp de data
S'utilitza en casos en què l'usuari pot recordar fàcilment la data, com ara la data de naixement, i no necessita un calendari per anticipar-ne les dates. Consisteix només en un camp d'entrada.

## Quan NO usar-lo / alternatives
Per a un nombre limitat d'opcions de dates. En aquest cas és millor proporcionar una llista de les dates aplicables.

## Anatomia
Figma: Date picker [Selection Type = Range, Calendar type = Days, Size = Medium, State = Default, Entry = First, Error = False].

## Variants, tipus i estats

### Numbers (dies del calendari, `_Date picker_Numbers`)

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Type | Individual / Range | Individual |
| State | Default / Hover / Focus / Not available | Default |
| Selected | True / False | False |
| Today | True / False | False |

Variant Figma: `_Date picker_Numbers` [Show Today = False, Type = individual, Selected = False, State = Default].

### Tipus de calendari (`Date picker_Calendar types`)

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Selection Type | Individual / Range | Default |
| Size | - / Medium / Small | Medium |
| Calendar type | Months / Days | Months |

- Mida: només aplica a la versió per rang.
- Tipus de calendari: la versió de rang no disposa de selecció per mesos.
- Variant Figma: [First Month = Maig, Second Month = Juny, Selected days = 0, Selection Type = Individual, Size = -, Calendar type = Days].

### Camp de data

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Type | Enabled / Filled / Error | Enabled |
| Size | Medium / Small | Medium |
| State | Default / Hover / Focus | Default |

Per veure els diferents estats del camp, consulta el [Camp d'entrada](component-camp-d-entrada.md).

### Selector de dates

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Selection Type | Individual / Range | Individual |
| Calendar Type | Days / Months | Days |
| Size | Medium / Small | Medium |
| State | Default / Focus | Default |
| Entry | First / Second | First |
| Error | False / True | False |

Subvariants: Individual selection; Range selection; Range selection en orientació vertical (per als casos en què es produeix un resize de pantalla i el calendari en versió rang sobrepassa l'espai en pantalla, s'utilitza la versió vertical).

El component Calendari ofereix solució a un determinat nombre de casuístiques. Si aquestes no són les que cal resoldre, cal fer servir els components anteriors per construir el calendari seguint les pautes establertes en la documentació.

## Mides i espaiats
- El contenidor del selector de data té una amplada màxima de 780 px.
- Si, en mode rang, el calendari ocupa més espai del disponible a la pantalla, s'adapta a la versió vertical (amplada mínima de la versió vertical: 258 px, segons l'historial de versions).

## Comportament i interacció

### Navegació
L'usuari pot introduir la data manualment, navegar pels mesos seleccionant els xebrons (*chevrons*), o fer clic al botó "Ves a avui" per tornar al punt inicial. En passar a l'estat de focus mitjançant la tecla de tabulació, l'usuari pot desplaçar-se pels dies utilitzant les fletxes del teclat.

### Focus
L'estat de focus es mostra tant quan se selecciona el component amb el teclat com amb el ratolí. Per sortir de l'estat de focus, l'usuari pot prémer la tecla "Esc" o fer clic fora del component. Si l'usuari introdueix la data manualment, el calendari no s'actualitza fins que es confirmi la data i es torni a seleccionar el component: la data no s'actualitza en temps real.

### Selecció
Per seleccionar una data, l'usuari pot:
- **Introduir la data manualment** tant al selector de dates (*date picker*) com al camp de data (*date input*) i prémer la tecla "Intro".
- **Seleccionar una data del calendari** utilitzant el ratolí o el teclat (tecla "Intro").

En **seleccionar un rang de dates per primera vegada**, el desplegable roman visible durant tota la interacció. Si l'usuari vol editar una de les dates un cop seleccionat el rang, el desplegable s'obre de nou i es tanca quan se selecciona la nova data d'inici o de final.

### Cancel·lar
Per cancel·lar una acció, l'usuari pot:
- **Selecció de dia:** prémer la tecla "Esc" o fer clic fora del component.
- **Selecció de mes:** seleccionar el desplegable i tornar a la visualització predeterminada.
- **Selecció de rang de dates:** si l'usuari no selecciona la data de sortida abans de prémer la tecla "Esc" o fer clic fora del component, la selecció es cancel·la.

En cas de cancel·lació, es mostra la selecció predeterminada o la que l'usuari havia realitzat en l'última interacció.

### Visibilitat
- Quan el camp està actiu (habilitat), **l'espai reservat (placeholder) es manté visible** per indicar el format (màscara).
- Quan l'usuari **selecciona un rang de dates**, els dies compresos entre l'inici i la finalització del rang **es destaquen visualment**.
- Mentre l'usuari realitza la selecció d'un rang, **es mostra automàticament el nombre de dies seleccionats**.

### Eliminar data
Un cop l'usuari ha introduït una data en un dels camps i torna a accedir a aquell camp, es mostra una aspa per poder esborrar el contingut de forma ràpida.

### Errors
Si l'usuari fa una selecció de la data d'inici, però no de fi, i es tanca el selector de data, salta error en els dos camps. El mateix comportament es produeix si la selecció és inversa (data de fi sense data d'inici) i es tanca el calendari.

### Adaptació responsiva
- Si, en mode rang, el calendari ocupa més espai del disponible a la pantalla, s'adapta a la versió vertical.
- **Small:** en la versió small de la selecció per rang, quan l'usuari selecciona la primera data, el calendari es tanca automàticament i s'obre el del segon camp.
- Per a dispositius mòbils, **s'utilitza el calendari del sistema operatiu**.

## Bones pràctiques

### Dates il·lògiques
- **FER:** Evita que els usuaris puguin seleccionar dates il·lògiques, com per exemple que introdueixin una data de retorn que tingui lloc abans de la data de sortida.

### Format
- **FER:** Respecta el format de la data local. Per exemple, s'utilitza el format DD/MM/AAAA per a Europa o MM/DD/AAAA per als Estats Units.

### Dia actual
- **FER:** Indica el dia actual de manera que l'usuari no necessiti consultar-ho. Incorpora un botó per tornar al dia actual. Quan els usuaris utilitzen el calendari, és possible que s'allunyin molt.

## Accessibilitat

### Pautes WCAG
- **Orientació (AA):** el contingut s'adapta a les diferents orientacions de la pantalla, com ara vertical o horitzontal, cosa que permet visualitzar el contingut. [1.3.4 CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Ús del color (A):** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per diferenciar els diferents estats dels dies i dels altres elements s'utilitzen subratllats amb diferents gruixos de vores, la presència de farciment, etc. [1.4.1 CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són excepció d'aquesta norma. [1.4.3 CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA):** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [1.4.4 CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA):** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [1.4.11 CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A):** tota la funcionalitat del contingut (navegar pels diferents botons) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [2.1.1 CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Focus visible (AA):** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [2.4.7 CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- **Identificació d'errors (A):** si es detecta un error en el component, s'identifica clarament que presenta un error mitjançant un canvi de color i gruix de la vora i amb la indicació visual (icona) i textual (descripció de l'error). [3.3.1 CAT](https://www.w3.org/Translations/WCAG22-ca/#error-identification) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/error-identification)

### Navegació per teclat

| Tecla | Acció |
|---|---|
| Tabulació | Navegar al camp d'entrada següent |
| Shift + Tabulació | Navegar al camp d'entrada anterior |
| Fletxes | Desplaçar-se pels diferents elements (selecció de mes, any i dies) del calendari |
| Intro | Seleccionar el dia |
| Esc | Cancel·lar una acció |

## Implementació (component web)

### `<date-picker-component>`

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat |
|---|---|---|---|---|---|
| `disablePastDates` | `disable-past-dates` | Deshabilita dies anteriors al dia actual | `boolean` | `false` | Opcional |
| `disabledDates` | `disabled-dates` | Deshabilitar dates concretes. Accepta array o string JSON | `string` (array) | `undefined` | Opcional |
| `disabledWeekends` | `disabled-weekends` | Deshabilita els caps de setmana | `boolean` | `false` | Opcional |
| `isDisabled` | `is-disabled` | Deshabilitar inputs del component | `boolean` | `false` | Opcional |
| `mode` | `mode` | Tipus de selector de dates: `single` per a una única selecció i `range` per a un interval de dates | `string` | `single` | Opcional |
| `requireBothDates` | `require-both-dates` | Permet indicar si es vol que el validador del component esperi rebre dues dates en mode range | `boolean` | (no consta al PDF) | Opcional |
| `showFirstError` | `show-first-error` | Permet mostrar error al primer input de tipus `range` o a l'input de tipus `single` | `boolean` | `false` | Opcional |
| `showSecondError` | `show-second-error` | Permet mostrar error al segon input de tipus `range` | `boolean` | `false` | Opcional |
| `showTooltipsInputs` | `show-tooltips-inputs` | Mostrar o amagar tooltips de les etiquetes | `boolean` | `true` | Opcional |
| `sizeInput` | `size-input` | Permet seleccionar la mida del o dels camps d'entrada | `string` | `medium` (segons variants del lloc) | Opcional |
| `textErrorInvalidCharacter` | `text-error-invalid-character` | Text d'error que es mostra quan s'introdueix un caràcter no vàlid | `string` | `undefined` | Opcional |
| `textFirstError` | `text-first-error` | Text d'error del primer input | `string` | `undefined` | Opcional |
| `textFirstEtiqueta` | `text-first-etiqueta` | Text de l'etiqueta del primer input | `string` | `undefined` | Opcional |
| `textFirstHelp` | `text-first-help` | Text d'ajuda del primer input | `string` | `undefined` | Opcional |
| `textFirstTooltip` | `text-first-tooltip` | Text del tooltip de l'etiqueta del primer input | `string` | `undefined` | Opcional |
| `textSecondError` | `text-second-error` | Text d'error del segon input | `string` | `undefined` | Opcional |
| `textSecondEtiqueta` | `text-second-etiqueta` | Text de l'etiqueta del segon input | `string` | `undefined` | Opcional |
| `textSecondHelp` | `text-second-help` | Text d'ajuda del segon input | `string` | `undefined` | Opcional |
| `textSecondTooltip` | `text-second-tooltip` | Text del tooltip de l'etiqueta del segon input | `string` | `undefined` | Opcional |
| `value` | `value` | Valor per defecte dels inputs en carregar el component. Si `mode` és `single`, cal fer servir `Date`; si és `range`, `Date[]`. Valor actual del component | `Date \| Date[]` | — | Opcional |

[discrepància: el PDF no documenta `requireBothDates` ni `sizeInput`, que sí consten al lloc (afegides a la versió Github 12.1.0); el PDF indica l'atribut de `value` com a "-/"]

**Propietats de l'array `disabledDates`**

| Propietat | Descripció | Atribut | Obligatori | Tipus |
|---|---|---|---|---|
| `-` | Data que no es podrà seleccionar. Ha de seguir el format `YYYY-MM-DD` | `-` | Opcional | `string` |

**Variants**

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `mode` | `single` `range` | `single` |
| `sizeInput` | `small` `medium` `large` | `medium` |

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `blurButton` | Es llança cada cop que es treu el focus en un botó | - | `button-component` |
| `focusButton` | Es llança cada cop que es fa focus en un botó | - | `button-component` |
| `handlerClick` | Es llança cada cop que es fa clic en un botó i com a paràmetre conté les dades de l'esdeveniment | `id` | `button-component` |
| `valueChange` | Es llança cada vegada que es modifica la data del component calendari (PDF: `CustomEvent<any>`) | `Date \| Date[] \| null` | `date-picker-component` |
| `focusChanged` | Es llança quan l'input rep el focus (emet true) o quan el perd (emet false) | - | `inputtext-component` |
| `hanlerdRef` | Permet que des del component pare (o on es faci servir aquest `<inputtext-component>`) es pugui enganxar a aquest esdeveniment `hanlerdRef` i rebre la referència a l'input | Referència a l'element input | `inputtext-component` |
| `maxLengthReached` | Esdeveniment llançat en assolir el maxLength a l'input | `maxLength` | `inputtext-component` |
| `valueChange` | Es llança de manera immediata cada vegada que hi ha un canvi a l'inputtext | `value` | `inputtext-component` |
| `valueChangeRetarded` | Es llança cada cop que hi ha un canvi a l'inputtext. S'emet al cap de 5 segons d'inactivitat | `value` | `inputtext-component` |

**Depèn de:** `button-component` ([Botons](component-botons.md)), `inputtext-component` ([Camp d'entrada](component-camp-d-entrada.md)).

**Utilitzat per:** `filters-component` ([Filtres](component-filtres.md)).

**Exemple d'ús**

```html
<!-- /index.html -->
<date-picker-component  
  mode="range" 
  disabled-weekends="true"
  disabled-dates='["2025-06-02", "2025-06-03"]' 
  disable-past-dates="true" 
  text-first-etiqueta="Etiqueta 1"
  text-second-etiqueta="Etiqueta 2"
  text-first-tooltip="Tooltip 1"
  text-second-tooltip="Tooltip 2"
  text-first-help="Help 1"
  text-second-help="Help 2"
  text-first-error="Error 1"
  text-second-error="Error 2"
  text-error-invalid-character="Caràcter no vàlid"
  is-disabled="false"
  show-first-error="false"
  show-second-error="false"
  show-tooltips-inputs="true"
  size-input="small"
  require-both-dates="true"
>
</date-picker-component>

<!--Les trucades als components només admeten elements HTML, per tant per inicialitzar value, caldrà fer-ho mitjançant un script-->
<script>
    const fechas = [
      new Date(2025, 8, 2), 
      new Date(2025, 8, 4) 
    ];

    const datepicker = document.querySelector('date-picker-component');
    datepicker.value = fechas; 

</script>
```

Exemple d'instància (PDF):

```html
<date-picker-component
disable-past-dates=false
disabled-dates="texto-ejemplo"
disabled-weekends=false
is-disabled=false
mode='single'
show-first-error=false
show-second-error=false
show-tooltips-inputs=true
text-error-invalid-character="texto-ejemplo"
text-first-error="texto-ejemplo"
text-first-etiqueta="texto-ejemplo"
text-first-help="texto-ejemplo"
text-first-tooltip="texto-ejemplo"
text-second-error="texto-ejemplo"
text-second-etiqueta="texto-ejemplo"
text-second-help="texto-ejemplo"
text-second-tooltip="texto-ejemplo"
-/="valor"
></date-picker-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.0.0 | 12.1.2 | 5 octubre, 2026 | **Desenvolupament**: s'ha corregit la selecció de rangs quan la propietat `disabled-dates` no està declarada, i s'ha millorat la tipificació de l'esdeveniment `valueChange` |
| 12.0.0 | 12.1.0 | 7 setembre, 2026 | **Desenvolupament**: s'afegeix la prop `requireBothDates` per habilitar o deshabilitar la validació que ambdues entrades en mode rang tinguin una data seleccionada; s'afegeix la prop `sizeInput` per permetre seleccionar la mida dels inputs. |
| 12.0.0 | 12.0.3 | 4 setembre, 2026 | **Desenvolupament**: en eliminar la data amb la creu de l'input, l'esdeveniment `valueChange` s'emet correctament; en mode de rang, millora l'adaptació visual quan es troba dins de contenidors o altres components com el modal; es corregeix el problema pel qual el modal es tancava en prémer la tecla ESC mentre el selector de data estava actiu |
| 12.0.0 | 12.0.2 | 16 juliol, 2026 | **Desenvolupament**: es corregeixen els errors relacionats amb l'escriptura manual sobre els inputs, es corregeixen alguns comportaments focus erronis detectats i l'objecte date emès per valueChange |
| 12.0.0 | 12.0.1 | 14 juliol, 2026 | **Desenvolupament**: s'estableix com a maxYear l'any actual + 2000; es corregeix l'edició de la data mitjançant escriptura per teclat |
| 12.0.0 | 12.0.0 | 10 juliol, 2026 | **Desenvolupament**: s'afegeixen les properties showFirstError i showSecondError i es limita el tipus de caràcter admès als inputs a numèric i /; s'utilitza el token correcte per al color de text dels dies del calendari |
| 12.0.0 | 10.1.0 | 29 maig, 2026 | **Disseny**: es redueix l'amplada mínima de la versió vertical a 258 px. **Desenvolupament**: correccions en el comportament del focus amb teclat i s'afegeix que en prémer la tecla intro, si hi ha una data introduïda, es validi i se seleccioni |
| 8.6.0 | 10.0.0 | 8 maig, 2026 | **Desenvolupament**: s'inclou al tipatge del value undefined |
| 8.6.0 | 9.4.0 | 17 abril, 2026 | **Desenvolupament**: s'ha solucionat el bug que es disparava en intentar netejar el datepicker després que un usuari seleccionés dates. |
| 8.6.0 | 9.3.0 | 20 març, 2026 | **Desenvolupament**: esborrar les dates seleccionades quan el valor s'estableixi com a buit; corregir validacions de data en carregar el component. |
| 8.6.0 | 9.1.0 | 9 febrer, 2026 | **Disseny**: es torna a mostrar la icona de calendari. |
| 8.0.0 | 9.1.0 | 6 febrer, 2026 | **Desenvolupament**: es fa reactiva la propietat value; s'elimina la property placeholder als input; es fan adaptacions d'accessibilitat pel que fa a mides de font extra gran i augment de pantalla |
| 8.0.0 | 8.5.0 | 5 desembre, 2025 | **Desenvolupament**: el selector d'any es canvia a desplegable |
| 8.0.0 | 8.0.0 | 14 novembre, 2025 | **Desenvolupament**: resolució de problemes |
| 8.0.0 | 6.2.1 | 3 octubre, 2025 | **Desenvolupament**: resolució de problemes. |
| 8.0.0 | 6.1.0 | 12 setembre, 2025 | **Disseny**: es modifica la selecció d'any; es passa de navegació individual a desplegable. **Desenvolupament**: nova propietat afegida |
| 5.0.0 | 6.0.0 | 3 juliol, 2025 | **Desenvolupament**: resolució de problemes |
| 5.0.0 | 5.0.0 | 10 juny, 2025 | **Disseny**: es modifica el nom en català (passa de Calendari (component nou) a Selector de data); s'afegeixen estats per als mesos; s'afegeixen estats per als botons del selector d'any; s'afegeixen estats per al desplegable dels mesos del calendari; s'afegeix un padding de 4 px entre les files del calendari. |
| 2.4.0 | 5.0.0 | 9 juny, 2025 | **Desenvolupament**: resolució de problemes |
| 2.4.0 | 3.0.0 | 28 abril, 2025 | **Desenvolupament**: resolució de problemes |
| 2.4.0 | 2.0.0 | 10 març, 2025 | **Disseny**: se substitueix l'estat deshabilitat per no disponible amb un nou estil; s'ajusten els estils de la resta d'estats dels nombres; s'ajusta el color del text "dies seleccionats". |
| 2.3.0 | 2.0.0 | 7 març, 2025 | **Desenvolupament**: resolució de problemes. |
| 2.3.0 | 1.0.0 | 31 gener, 2025 | Sense canvis. |
| 2.2.0 | 0.1.1 | 20 gener, 2024 | Sense canvis. |
| 2.1.0 | 0.1.1 | 04 desembre, 2024 | Sense canvis. |
| 2.0.0 | 0.1.0 | 02 desembre, 2024 | Sense canvis. |
| 1.1.0 | 0.1.0 | 22 novembre, 2024 | Sense canvis. |
| 1.1.0 | 0.0.4 | 18 novembre, 2024 | Sense canvis. |
| 1.0.0 | 0.0.3 | 1 novembre, 2024 | **Disseny**, **desenvolupament** i **documentació** del component. |

## Vegeu també
- [Camp d'entrada](component-camp-d-entrada.md): per introduir i recopilar dades de manera interactiva.
- [Desplegable](component-desplegable.md): per seleccionar un o diversos elements d'una llista d'opcions predefinides.
- [Calendari](component-calendari.md)
- [Filtres](component-filtres.md)
