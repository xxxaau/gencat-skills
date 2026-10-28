# Camp d'entrada (Input field)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/7912b2 · Web component: `<inputtext-component>` (paquet core) · Font actualitzada el 2026-10-22 · Extret el 2026-10-28

## Què és i quan usar-lo
Component recurrentment utilitzat en formularis per a la recollida de dades.

El camp d'entrada és un element interactiu que **permet als usuaris introduir i enviar dades** en formularis o aplicacions de manera intuïtiva i eficient.

S'utilitza de forma generalitzada en formularis per a la recollida de dades. Permet introduir informació com ara noms, correus electrònics, números de telèfon, adreces i altres detalls necessaris per al registre, subscripcions, compres o consultes.

## Quan NO usar-lo / alternatives
- No es recomana en cas que l'usuari hagi d'escollir entre una llista predefinida d'opcions: s'usa un desplegable, una casella de selecció o un botó d'opció.
- No es fa servir per mostrar informació que no sigui editable: s'usen altres elements com ara etiquetes o textos estàtics.

Components relacionats:
- [Àrea de text](component-area-de-text.md): per a la recollida de dades extenses.
- [Camp de cerca](component-camp-de-cerca.md): per realitzar cerques o explorar un lloc web o aplicació.
- [Desplegable](component-desplegable.md): per seleccionar un o diversos elements d'una llista d'opcions predefinides.

## Anatomia
Existeixen dos components amb anatomia pròpia (la font només mostra les imatges d'anatomia):
- Camp d'entrada de text (`DOC_input_field`).
- Camp d'entrada numèric (`DOC_input_field_number`).

## Variants, tipus i estats

### Propietats del camp d'entrada de text

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Type | Default / Hover / Focus | Default |
| Size | Large / Medium / Small | Large |
| State | Enabled / Filled / Error / Disabled-Empty / Disabled-Filled | Empty [discrepància: la font llista els estats Enabled/Filled/Error/Disabled-Empty/Disabled-Filled però indica el valor per defecte "Empty"] |
| Show Label | True / False | True |
| Label | Text | Etiqueta |
| Show Units | True / False | True |
| Show Help text | True / False | True |
| Show Validation | True / False | False |
| Show Error Text | True / False | True |
| Show Delete Content | True / False | True |
| Text | Text | Contingut omplert |
| Show Popover Button | True / False | False |
| Show Icon Button | True / False | False |

Variant Figma (Input): Show Tooltip = True | False (False per defecte); Show Help text = True; Show Validation = False; Show Error text = True; Show Delete content = True; Label = Etiqueta; Text = Contingut omplert; Show Popover button = False; Show Label = True; Show Icon Button = False; Help text = Text d'ajuda; Type = Default | Hover | Focus; Size = Large | Medium | Small; State = Enabled | Filled | Error | Disabled-Empty | Disabled-Filled.

### Propietats del camp d'entrada numèric

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Type | Default / Hover / Focus | Default |
| Size | Large / Medium / Small | Large |
| State | Enabled / Filled / Error / Disabled-Empty / Disabled-Filled (la font escriu "Disabeld-Filled") | Enabled |
| Show Label | True / False | True |
| Show Help text | True / False | False |
| Show Prefix | True / False | False |
| Prefix | Text | + |
| Show Units | True / False | True |
| Units | Text | € |
| Show Validation | True / False | False |
| Show Error text | True / False | True |
| Show Delete Content | True / False | True |
| Number | Number | 100 |

Variant Figma (Input_number): Show Help text = False; Show Placeholder = True; Show Validation = False; Show Error text = True; Show Delete content = True; Number = 100; Show units = True; Units = €; Show Label = True; Prefix = +; Show Prefix = False; Type = Default; Size = Large; State = Enabled.

## Mides i espaiats
- **Large:** mida per defecte en l'entorn del ciutadà. S'utilitza en tots els casos on l'usuari hagi d'introduir dades, sigui en formularis, enquestes o altres processos.
- **Medium / Small:** mida per a l'entorn del treballador (backoffice). Es fa servir en situacions en què es vol estalviar espai. [a verificar: la font mostra dues variants addicionals sense distingir-ne el nom en el text; per les propietats són Medium i Small]

## Comportament i interacció

### Interacció
- Els usuaris poden seleccionar, editar o eliminar el text dins del camp d'entrada utilitzant el cursor del ratolí o el teclat. Poden suprimir caràcters o text seleccionat utilitzant les tecles d'eliminació o retrocés del teclat.

### Validació de dades
- El camp ha d'indicar visualment si les dades introduïdes no són vàlides i proporcionar indicacions a l'usuari sobre la seva correcció.
- La validació de format es realitza un cop l'usuari surt del camp.
- Les validacions funcionals que necessitin una comprovació de dades en el sistema es duen a terme quan l'usuari fa clic al botó d'acció del formulari.
- L'**estat d'error** desapareix quan l'usuari realitza qualsevol canvi dins del camp. Si els canvis de text no s'ajusten a les indicacions requerides, el missatge d'error torna a aparèixer un cop l'usuari surt del camp.

### Adaptació responsiva i desbordament de text
- L'amplada del camp ha de ser sempre adequada perquè hi càpiga bé el contingut a omplir. Si la resposta és més llarga que el contenidor, el camp fa scroll horitzontal mentre l'usuari escriu. Quan l'usuari surt del camp, el text es recol·loca a l'inici i es talla el contingut fins a l'últim caràcter que hi càpiga.
- L'etiqueta no hauria de ser mai més llarga que el seu contenidor. Si en algun cas excepcional l'extensió de l'etiqueta sobrepassa l'ample del component, el text salta a una segona línia. Si l'etiqueta conté un tooltip (indicador de funció), aquest queda alineat a la part superior dreta.

### Emmascarament de text
De manera opcional, el camp d'entrada pot aplicar l'**emmascarament de text**, que permet formatar automàticament les dades introduïdes seguint un patró específic (per exemple, per a números de telèfon o targetes de crèdit).

### Unitats i prefixos (camp numèric)
El camp d'entrada numèric pot incorporar una unitat o un prefix per ajudar a entendre el valor que s'ha d'introduir. Aquests elements poden aparèixer abans o després del valor, segons el tipus de dada.
- Les unitats mètriques indiquen el context del valor introduït (per exemple, km, €, kg). Quan l'element a mesurar té una unitat mètrica concreta, aquesta és obligatòria i es mostra clarament dins el camp.
- Quan el valor no correspon a una mesura amb unitat (per exemple, nombre de fills, habitants o altres comptatges), no s'inclou la unitat dins del camp. La informació contextual es trasllada a l'etiqueta del camp, indicant clarament què representa el valor sense afegir una unitat que podria confondre l'usuari.
- Per als criteris d'ús de les unitats, prefixos, sufixos, formats específics i normalització de valors, vegeu el patró [Introducció de dades](patro-introduccio-de-dades.md).

### Accions dins del camp
El camp pot incorporar una acció associada quan ajuda l'usuari a introduir, revisar o modificar el valor. Es mostra habitualment amb un botó d'icona dins del camp. Per exemple, en camps de contrasenya, un botó d'icona per alternar entre mostrar i ocultar el valor introduït. L'estat del botó ha de deixar clara l'acció disponible, per exemple "Mostra la contrasenya" o "Oculta la contrasenya".

### Placeholder (espai reservat)
Per evitar problemes d'accessibilitat es prescindeix del placeholder en tots els components d'entrada (inputs). La informació necessària per entendre quina informació ha d'introduir l'usuari va a l'etiqueta o al text d'ajuda.

## Contingut i microcopy
Textos per defecte als exemples: etiqueta "Etiqueta", text d'ajuda "Text d'ajuda", contingut omplert "Contingut omplert", prefix "+", unitat "€", número 100. Exemples de text per a botons d'acció dins del camp: "Mostra la contrasenya", "Oculta la contrasenya".

## Bones pràctiques

### Etiquetes
- **FER:** Utilitza etiquetes concises, comprensibles i que comencin amb la primera lletra en majúscula.
- **NO FER:** No utilitzis etiquetes poc concises o comprensibles, ni que tinguin totes les lletres en majúscules o la primera lletra en minúscula.
- **FER:** Utilitza el text sense elements tipogràfics per indicar que l'etiqueta acompanya el camp.
- **NO FER:** No facis servir dos punts al final d'una etiqueta per indicar que aquesta aplica al camp que acompanya. Un correcte disseny del component ja comunica la relació entre l'etiqueta i el camp d'entrada.

### Text d'ajuda i informació addicional
- **FER:** Fes ús del text d'ajuda per indicar de forma simple i directa informació addicional sobre el format del camp.
- **NO FER:** No facis ús del text d'ajuda per indicar que el camp és obligatori o opcional. Aquesta informació s'inclou en l'etiqueta del camp.
- **FER:** En cas necessari, fes ús de l'indicador de funció per afegir informació addicional sobre l'etiqueta del camp.
- **NO FER:** No utilitzis els indicadors de funció per ocultar informació rellevant. Aquesta informació es pot afegir com a text d'ajuda sota el camp.

### Camps obligatoris i opcionals
- **FER:** Destaca únicament els camps menys comuns. En cas de comptar amb cinc camps obligatoris i un d'opcional, destaca només aquest últim per evitar càrrega cognitiva.
- **NO FER:** No utilitzis l'asterisc per indicar un camp opcional. L'asterisc només s'utilitza en camps obligatoris. Els camps opcionals s'indiquen entre parèntesis en la mateixa etiqueta.
- **FER:** En cas d'emprar un asterisc (*) per marcar els camps obligatoris, inclou una llegenda explícita.
- **NO FER:** No utilitzis diferents criteris per indicar l'obligatorietat o l'opcionalitat dels camps al llarg de tot el formulari.

### Maquetació
- **FER:** Es recomana maquetar els camps en una sola columna, ja que facilita l'escaneig dels continguts.
- **NO FER:** Evita maquetar els camps d'entrada en una quantitat excessiva de columnes.
- **FER:** Utilitza una amplada del component que no sigui excessivament llarga.
- **NO FER:** No estiris el component en excés, ja que pot dificultar la usabilitat dels formularis.

## Accessibilitat
Pautes WCAG 2.2 que compleix el component:

- **Orientació (AA) – 1.3.4:** el contingut s'adapta a les diferents orientacions de la pantalla (vertical o horitzontal). [CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Ús del color (A) – 1.4.1:** el color no és l'únic mitjà visual per transmetre informació. Per indicar els estats, es modifiquen els píxels de la vora del component i/o s'afegeixen elements complementaris com la segona vora pel focus o la icona i el text d'error. [CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA) – 1.4.3:** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats en són excepció. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA) – 1.4.4:** excepte subtítols i imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA) – 1.4.11:** les icones (error i indicador de funció) i les vores tenen un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Espaiat del text (AA) – 1.4.12:** no es perd contingut ni funcionalitat si s'ajusten: alçada de línia d'almenys 1,5 vegades la mida de la lletra; espaiat entre paràgrafs d'almenys dues vegades la mida de la lletra; espaiat entre lletres (tracking) d'almenys 0,12 vegades; espaiat entre paraules d'almenys 0,16 vegades. [CAT](https://www.w3.org/Translations/WCAG22-ca/#text-spacing) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/text-spacing)
- **Teclat (A) – 2.1.1:** tota la funcionalitat (accedir al camp de text) es pot operar amb teclat sense requerir temps específics per a pulsacions de tecles individuals. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Focus visible (AA) – 2.4.7:** la navegació al camp és visible mitjançant un rectangle extern. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- **Identificació d'errors (A) – 3.3.1:** l'error s'identifica mitjançant un canvi de color i gruix de la vora i amb indicació visual (icona) i textual (descripció de l'error). [CAT](https://www.w3.org/Translations/WCAG22-ca/#error-identification) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/error-identification)

## Implementació (component web)

### `<inputtext-component>`

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte |
|---|---|---|---|---|
| `deleteCross` | `delete-cross` | "true" o "false": mostra la creu per esborrar el contingut del camp. | boolean | undefined |
| `dividerIconName` | `divider-icon-name` | Nom de la icona que va després del divisor. No és compatible amb la icona de calendari. | string | undefined |
| `iconCalendar` | `icon-calendar` | Mostra o amaga una icona de calendari dins del camp. | boolean | undefined |
| `inputClass` | `input-class` | Classe CSS addicional per aplicar estils personalitzats al camp. | string | undefined |
| `isDisabled` | `is-disabled` | Determina si el camp està deshabilitat o habilitat. | boolean | undefined |
| `maxLength` | `max-length` | Longitud màxima de caràcters per a type text i password. | number | undefined |
| `popoverConfig` | `popover-config` | Configuració del popover (atributs). Accepta objecte o string JSON. | string (array) | `{}` |
| `prefixText` | `prefix-text` | Valor del prefix, mostrat abans del valor. | string | undefined |
| `showPopoverValue` | `show-popover-value` | Mostra el popover. | boolean | false |
| `showPrefix` | `show-prefix` | Permet mostrar o amagar el prefix. Només funciona per a inputs de tipus number. | boolean | false |
| `showTextError` | `show-text-error` | Funciona conjuntament amb `textError`. Quan és true mostra `textError` i quan és false l'amaga, independentment que hi hagi res escrit a `textError`. | boolean | false |
| `showTooltip` | `show-tooltip` | "true" o "false": mostra o no l'indicador de funció. | boolean | false |
| `size` | `size` | Mida. Opcions: `large`, `medium`, `small`. | string | `medium` |
| `textAlternativeError` | `text-alternative-error` | Text alternatiu de l'exclamació del text d'error. | string | undefined |
| `textError` | `text-error` | Text d'error que es mostra. Quan no s'escriu res, no apareix l'error. | string | undefined |
| `textEtiqueta` | `text-etiqueta` | Text de l'etiqueta que va al costat de la icona de l'indicador de funció. | string | undefined |
| `textHelp` | `text-help` | Text d'ajuda de sota el camp. | string | undefined |
| `textIconTooltip` | `text-icon-tooltip` | Tooltip que porta la icona de després del divisor. | string | undefined |
| `textInfoTooltip` | `text-info-tooltip` | Text de l'indicador de funció de la icona informativa. | string | undefined |
| `typeInput` | `type-input` | Tipus HTML natiu del camp d'entrada; defineix el tipus de camp. | string | undefined |
| `units` | `units` | Unitats de mesura del valor mostrat; quan l'input és de tipus number s'hi poden introduir les unitats corresponents. | string | undefined |
| `value` | `value` | Valor actual de l'input. | any (string a la pàgina) | undefined |
| `visibilityTextHelp` | `visibility-text-help` | "true" per mostrar el text d'ajuda, "false" per no mostrar-lo. | boolean | undefined |

Obligatorietat segons la pàgina: `showTextError`, `size` i `textEtiqueta` són obligatoris; la resta, opcionals. [discrepància: la pàgina dona `size` per defecte `medium` (variants: `small` `medium` `large`) mentre el disseny Figma té Large per defecte]

**Variants**

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `size` | `small` `medium` `large` | `medium` |

**Esdeveniments**

| Esdeveniment | Descripció | Tipus / Paràmetre | Origen |
|---|---|---|---|
| `focusChanged` | Es llança quan l'input rep el focus (emet true) o quan el perd (emet false). | `CustomEvent<boolean>` | `inputtext-component` |
| `hanlerdRef` | Permet que des del component pare t'enganxis a aquest esdeveniment i rebis la referència a l'input. | `CustomEvent<HTMLInputElement>` (referència a l'element input) | `inputtext-component` |
| `maxLengthReached` | Es llança en assolir el `maxLength` a l'input. | `CustomEvent<number>` (maxLength) | `inputtext-component` |
| `valueChange` | Es llança de manera immediata cada vegada que hi ha un canvi a l'input. | `CustomEvent<string>` (Value) | `inputtext-component` |
| `valueChangeRetarded` | Es llança cada cop que hi ha un canvi a l'input; s'emet al cap de 5 segons d'inactivitat. | `CustomEvent<string>` (Value) | `inputtext-component` |

**Depèn de:** `tooltip-component` ([Indicador de funció](component-indicador-de-funcio.md)), `popover-component` ([Descripció emergent](component-descripcio-emergent.md)), `button-component` ([Botons](component-botons.md)), `divider-component` ([Divisor](component-divisor.md)).

**Utilitzat per:** `date-picker-component` ([Selector de data](component-selector-de-data.md)), `slider-component` ([Control de rang](component-control-de-rang.md)).

**Props que accepten JSON:** `popoverConfig` (`popover-config`). Claus de l'exemple: `text-open`, `padding`, `size-text-open`, `popover-title`, `description`, `version`, `contextual-image-url`, `img-description`, `link-text-popover`.

**Comportament addicional**
- Perquè en mode *disabled* no aparegui el text d'error juntament amb la vora vermella, cal esborrar el contingut de la variable `textError`.
- Si es requereix compatibilitat amb el sistema numèric espanyol, el camp s'ha de configurar amb `typeInput: "text"`, ja que el tipus number natiu només admet punt flotant com a separador. En aquest cas, la validació del valor numèric queda fora de l'abast del component i és responsabilitat del desenvolupador que el consumeixi.

**Exemple d'ús (pàgina)**

```html
<!-- /index.html -->
<inputtext-component 
  text-etiqueta="Etiqueta" 
  text-help="Text d’ajuda" 
  size="small" 
  text-error="Text error"
  show-text-error="false"
  is-disabled="false" 
  visibility-text-help="true" 
  icon-calendar=false 
  text-info-tooltip="Text Tooltip" 
  delete-cross=false 
  text-alternative-error="Text d'error input text 1" 
  show-tooltip="false"
  show-popover-value="true"
  value="Text"
  input-class=""
  type-input=""
  units=""
  max-length="10"
  prefix-text="+34"
  show-prefix="false"
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
    }'>
</inputtext-component>
```

**Exemple d'instància (PDF)**

```html
<inputtext-component
delete-cross=false
divider-icon-name="texto-ejemplo"
icon-calendar=false
input-class="texto-ejemplo"
is-disabled=false
max-length=0
popover-config='{}'
prefix-text="texto-ejemplo"
show-popover-value=false
show-prefix=false
show-text-error=false
show-tooltip=false
size='medium'
text-alternative-error="texto-ejemplo"
text-error="texto-ejemplo"
text-etiqueta="texto-ejemplo"
text-help="texto-ejemplo"
text-icon-tooltip="texto-ejemplo"
text-info-tooltip="texto-ejemplo"
type-input="texto-ejemplo"
units="texto-ejemplo"
value="valor"
visibility-text-help=false
></inputtext-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.0.0 | 12.0.3 | 4 setembre, 2026 | Desenvolupament: deixar la propietat `textHelp` buida evita que es renderitzi el contenidor del text d'ajuda. |
| 12.0.0 | 11.0.0 | 19 juny, 2026 | Desenvolupament: s'afegeix prefix (noves propietats `prefixText` i `showPrefix`); propietat per establir la longitud màxima; padding-right quan existeix `dividerIconName`; s'afegeixen estats al botó de neteja. |
| 12.0.0 | 10.1.0 | 29 maig, 2026 | Disseny: es crea l'asset del botó de la creu per eliminar el contingut al camp d'entrada i al numèric amb els seus estats; estats deshabilitats al camp numèric medium; prefix i propietat booleana de prefix al numèric. Desenvolupament: es corregeix el padding-right del `deleteCross` quan té a la dreta la icona del calendari; s'afegeix l'estat deshabilitat amb contingut. |
| 11.0.0 | 10.0.0 | 8 maig, 2026 | Disseny: variant per estat deshabilitat amb contingut i propietat per modificar el text d'ajuda. Desenvolupament: mida medium, nou botó i divisor; es corregeix el refresc de `textError` dins del modal. |
| 10.0.0 | 9.2.0 | 17 abril, 2026 | Disseny: variant Medium al camp d'entrada i al numèric; botó terciari dins el camp com a booleana. |
| 9.1.0 | 9.2.0 | 20 març, 2026 | Disseny: la variant Medium passa a dir-se Large; alçada del frame de l'etiqueta small a hug; arrodoniment del camp numèric small a 4 px. |
| 8.5.0 | 9.2.0 | 27 febrer, 2026 | Desenvolupament: s'elimina l'esdeveniment valueChange Immediate i `valueChange` s'emet immediatament; es crea `valueChangeRetarded` que emet el valor amb retard de 5 s. |
| 8.5.0 | 9.1.0 | 6 febrer, 2026 | Desenvolupament: s'elimina la property placeholder. |
| 8.5.0 | 8.5.0 | 20 gener, 2026 | Disseny: s'eliminen placeholders del camp d'entrada i del numèric; s'elimina el truncat de l'etiqueta del numèric. |
| 8.3.0 | 8.5.0 | 5 desembre, 2025 | Desenvolupament: `showPopover` passa a dir-se `showPopoverValue`. |
| 8.3.0 | 7.0.0 | 14 novembre, 2025 | Disseny: s'elimina la propietat per mostrar la icona de calendari. |
| 8.2.0 | 7.0.0 | 27 octubre, 2025 | Disseny: text del placeholder truncat a una línia; "clip content" als camps omplerts perquè el text que superi l'amplada màxima quedi tallat. |
| 8.1.0 | 7.0.0 | 24 octubre, 2025 | Desenvolupament: nova propietat afegida o eliminada. |
| 8.1.0 | 6.0.0 | 6 octubre, 2025 | Disseny del camp numèric. |
| 5.0.0 | 6.0.0 | 3 juliol, 2025 | Desenvolupament: resolució de problemes. |
| 5.0.0 | 5.0.0 | 10 juny, 2025 | Disseny: nova propietat Show label per controlar la visualització de l'etiqueta. |
| 4.0.0 | 5.0.0 | 9 juny, 2025 | Desenvolupament: resolució de problemes. |
| 4.0.0 | 4.0.1 | 19 maig, 2025 | Desenvolupament: resolució de problemes. |
| 2.3.0 | 3.0.0 | 28 abril, 2025 | Desenvolupament: resolució de problemes. |
| 2.3.0 | 1.0.0 | 31 gener, 2025 | Sense canvis |
| 2.2.0 | 0.1.1 | 20 gener, 2025 | Sense canvis |
| 2.1.0 | 0.1.1 | 04 desembre, 2024 | Disseny: s'afegeix el botó d'ajuda per mostrar la descripció emergent. |
| 2.0.0 | 0.1.0 | 02 desembre, 2024 | Sense canvis |
| 1.1.0 | 0.1.0 | 22 novembre, 2024 | Sense canvis |
| 1.1.0 | 0.0.4 | 18 novembre, 2024 | Sense canvis |
| 1.0.0 | 0.0.3 | 1 novembre, 2024 | Disseny, desenvolupament i documentació del component |

## Vegeu també
- [Àrea de text](component-area-de-text.md)
- [Camp de cerca](component-camp-de-cerca.md)
- [Desplegable](component-desplegable.md)
- [Indicador de funció](component-indicador-de-funcio.md)
- [Descripció emergent](component-descripcio-emergent.md)
- [Selector de data](component-selector-de-data.md)
- [Control de rang](component-control-de-rang.md)
- [Introducció de dades](patro-introduccio-de-dades.md)
