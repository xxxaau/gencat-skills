# Desplegable (Dropdown)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/88ad59 · Web component: `<dropdown-component>` (paquet core) · Font actualitzada el 2026-10-22 · Extret el 2026-10-28

## Què és i quan usar-lo
Element de control gràfic que permet **seleccionar un o diversos elements d'una llista d'opcions predefinides.** Els desplegables s'utilitzen sovint en interfícies d'usuari per conservar l'espai de la pantalla i proporcionar una forma estructurada perquè els usuaris facin seleccions d'un conjunt d'opcions.

Quan s'utilitza: en formularis web, aplicacions i interfícies gràfiques, i com una acció per a filtrar o ordenar el contingut existent.

### Tipologies
- **Selecció única** (`Tipologia_selecció_única`): presenta una llista d'opcions d'entre les quals l'usuari només pot seleccionar un element.
- **Selecció múltiple** (`Tipologia_selecció_múltiple`): presenta una llista d'opcions d'entre les quals l'usuari pot seleccionar més d'un element.

## Quan NO usar-lo / alternatives
- No utilitzar el desplegable per a casos amb menys de tres opcions: considerar un [botó d'opció](component-boto-d-opcio.md) o una [casella de selecció](component-casella-de-seleccio.md).
- [Botó d'opció](component-boto-d-opcio.md): per a seleccionar una opció dins d'un conjunt d'opcions mútuament excloents.
- [Camp de cerca](component-camp-de-cerca.md): per a realitzar cerques o explorar un lloc web o aplicació.
- [Casella de selecció](component-casella-de-seleccio.md): per a seleccionar una o més opcions d'una llista predefinida.

## Anatomia
1. **Etiqueta**: indica el nom de la informació del camp i s'alinea a l'esquerra, just per sobre de l'àrea d'entrada.
2. **Indicador de funció** *(opcional)*: icona que conté instruccions o context addicional sobre l'etiqueta del camp.
3. **Camp de selecció única**: contenidor on apareix el valor que ha seleccionat l'usuari.
4. **Camp de selecció múltiple**: contenidor on apareixen els valors que ha seleccionat l'usuari.
5. **Desplegable d'opcions**: llistat dels valors que l'usuari pot seleccionar.
6. **Opció seleccionada.**
7. **Casella de selecció**: casella utilitzada per seleccionar múltiples opcions.
8. **Desplaçament** (scroll): apareixerà quan el llistat del desplegable conté més de 7 opcions.
9. **Camp de cerca**: permet cercar les diferents opcions presents dins del desplegable.
10. **Botó de netejar filtres**: permet netejar la/les opcions seleccionades.

## Variants, tipus i estats

### Propietats del camp d'entrada del desplegable

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Type | Enabled / Filled / Disabled / Error | Default |
| State | Default / Hover / Focus | Default |
| Size | Large / Medium / Small | Large |
| Tooltip | True / False | False |

Variants Figma del camp (`_Dropdown`): Show Tooltip = False | True; Show Help text = False | True; Label = Etiqueta; Error text = Text d'error; Show Popover button = False | True; Type = Enabled | Filled | Disabled | Error; Size = Medium | Large | Small; State = Default | Hover | Focus.

Llistat d'opcions (selecció única i multiselecció), variants Figma (`Frame 1000001294`): Option = Opció; Type = Standard; Selected = False | True; State = Default; Size = Large.

### Propietats del desplegable

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Size | Large / Small | Large |
| Collapsed | True / False | False |

### Propietats de la llista del desplegable

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Type | Standard / Multi-selector | Standard |
| Size | Large / Small | Large |
| Breakpoint | Extra Large-Medium / Small | Extra Large-Medium |
| Show Search field | True / False | False |
| Show Clear Filters button | True / False | False |
| Show scroll | True / False | False |

Variants Figma de la llista (`Desplegable`): Show Search field = False; Show Clean Filters button = False; Show scroll = True; Type = Standard; Size = Large; Breakpoint = Extralarge-Medium.

## Mides i espaiats
- Mida per defecte en l'entorn del ciutadà (la font mostra dues variants de mida del camp; la primera correspon al ciutadà).
- Mida per a l'entorn del treballador (backoffice): la segona variant; es fa servir en situacions en què es vol estalviar espai.
- Mides mínimes i màximes d'amplada i alçada (versió 6.0.1, juliol 2025): Large a 56 px i Small a 48 px.
- Arrodoniment a *small* (4 px) (versió 1.0.0).
- Punt de tall: la variant de la llista per a punt de tall small s'ha d'aplicar dins el component de [panell emergent](component-panell-emergent.md) (variant inferior).

## Comportament i interacció

### Desplegable de selecció única
- Quan l'usuari fa clic en el camp del desplegable, una llista d'opcions "baixa" i apareix sota el camp, presentant a l'usuari una selecció d'opcions. En seleccionar una opció del menú, aquest es tanca i el text de l'opció seleccionada reemplaça l'espai reservat (placeholder) en el camp.
- Si l'usuari torna a clicar el camp, el text seleccionat es mantindrà dins del camp.
- Si el camp del desplegable no és obligatori d'omplir, apareixerà una opció "neutre" a l'inici del llistat, equivalent a deixar la pregunta sense contestar. El text d'aquesta opció variarà en funció del tipus de contingut que es demani. Alguns descriptius possibles: "prefereixo no contestar", "ometre aquesta pregunta", "deixar sense resposta", "No ho sé / prefereixo no contestar" o "sense valor".

### Desplegable de selecció múltiple
- Quan l'usuari fa clic en el camp del desplegable, una llista d'opcions "baixa" i apareix sota el camp, presentant a l'usuari una selecció d'opcions que van acompanyades d'una casella de selecció. L'usuari podrà seleccionar una o diverses opcions. A mesura que se seleccionen, aquestes es van afegint en el camp de text del component, separades per una coma (",") i per ordre de selecció.
- El llistat d'opcions no es tancarà fins que l'usuari faci clic fora del desplegable.

### Adaptació responsiva
En punts de tall small, el desplegable no es visualitza com un element amb overlay dins la pantalla, sinó que les opcions apareixeran en un panell emergent inferior. El títol d'aquest haurà d'incloure el nom de l'etiqueta del camp.

Per a construir la versió small cal introduir la variant small del component dins el component [panell emergent (sheet)](component-panell-emergent.md).

### Adaptació del contingut i posició
Visualització del contingut dins del camp:
- **Desplegable de selecció única:** si l'opció seleccionada no cap dins del camp del desplegable, el text es trunca afegint tres punts suspensius.
- **Desplegable de selecció múltiple:** el camp mostrarà les diferents opcions seleccionades separades per una coma (",") i per ordre de selecció. Si no hi caben totes les opcions dins del camp, s'indicarà únicament el nombre total d'opcions seleccionades, per exemple "tres opcions seleccionades" o "una opció seleccionada".
- Quan es tanqui el desplegable després de seleccionar opcions, i es torni a obrir, les opcions seleccionades es reordenaran automàticament i apareixeran a la part superior de la llista. Aquesta agrupació facilita la visibilitat i gestió de les seleccions realitzades prèviament.

### Comportament del llistat d'opcions
- La llista del desplegable (dropdown list) ocuparà per defecte l'ample del camp del desplegable. Si el contingut de la llista és més llarg que l'espai disponible, l'ample del llistat augmentarà a l'amplada del contingut més llarg.
- Per defecte, el llistat d'opcions apareixerà sota el camp alineat a l'esquerra, però si no hi ha espai suficient, el llistat es recol·locarà a l'esquerra i/o a sobre del camp en funció de l'espai disponible.
- Si no hi ha espai suficient a la pantalla perquè el llistat creixi de forma horitzontal i el contingut del llistat d'opcions càpiga en una línia, els textos de les opcions podran saltar de línia.
- En el llistat d'opcions, com a màxim, es mostraran set opcions visibles a primer nivell. Si el desplegable té més opcions, aquestes quedaran amagades dins del desplaçament (scroll). En el cas que no hi hagi espai suficient en la pantalla perquè se'n vegin set, la mida del llistat d'opcions s'adaptaria a l'espai màxim disponible de la pantalla i la resta d'opcions quedarien amagades dins del desplaçament (scroll).
- Quan l'usuari tingui el desplegable obert i premi una lletra en el teclat, anirà a la primera opció que comenci per aquesta lletra.

### Comportament del camp de cerca
- En introduir text al camp de cerca, es mostraran únicament les opcions que continguin la paraula o les lletres escrites.
- Les coincidències dins del text de cada opció es ressaltaran visualment en negreta, ajudant l'usuari a identificar més ràpidament les opcions rellevants.

### Placeholder (espai reservat)
Per evitar problemes d'accessibilitat es prescindeix del placeholder en tots els components d'entrada (inputs). La informació necessària per entendre quina informació ha d'introduir l'usuari anirà a l'etiqueta o al text d'ajuda.

## Contingut i microcopy
- Opció neutra (camp no obligatori): "prefereixo no contestar", "ometre aquesta pregunta", "deixar sense resposta", "No ho sé / prefereixo no contestar", "sense valor".
- Resum de selecció múltiple: "tres opcions seleccionades", "una opció seleccionada".

## Bones pràctiques

**Etiquetes**
- **FER:** Fes ús d'etiquetes descriptives al desplegable per indicar el seu propòsit i el tipus d'opcions que conté. L'etiqueta ha de ser concisa però informativa.
- **NO FER:** No facis ús d'etiquetes poc descriptives al desplegable que no acudeixin a indicar el seu propòsit i el tipus d'opcions que conté.
- **NO FER:** No utilitzis elements tipogràfics per indicar que l'etiqueta s'aplica al camp que acompanya. El disseny del component ja comunica la relació entre etiqueta i camp d'entrada.

**Llistat d'opcions**
- **FER:** Mostra la llista d'elements ordenada alfabèticament o utilitzant un criteri lògic en funció del cas d'ús (p. ex. mostrar opcions més comunes primer en una llista de pocs elements).
- **NO FER:** No mostris la llista d'elements sense cap mena d'ordre alfabètic o lògic.
- **FER:** Si el camp té menys de tres opcions, considera l'ús d'un botó d'opció o una casella de selecció.
- **NO FER:** No utilitzis el desplegable per casos amb menys de tres opcions.
- **FER:** No repeteixis la mateixa paraula o frase al principi del text de cada opció, ja que pot confondre l'usuari.
- **NO FER:** No utilitzis la mateixa paraula o frase al principi del text de cada opció.
- **NO FER:** No utilitzis opcions de més de 150 caràcters de llargada. Procura que les opcions siguin clares, directes i el més curtes possibles.

**Preselecció**
- **FER:** Limita l'ús d'una preselecció als casos en què es prevegi que més del 90% dels usuaris seleccionaran el valor, sent aquest d'obligat compliment.
- **NO FER:** No facis ús d'una preselecció d'un valor que no és d'obligat compliment, pot condicionar la resposta de l'usuari.

**Maquetació**
- **FER:** Utilitza una amplada del desplegable ajustada a l'extensió del seu contingut.
- **NO FER:** No estiris el component en excés, ja que pot dificultar la usabilitat del camp.

## Accessibilitat

### Pautes WCAG
- **Orientació (AA)**: el contingut s'adapta a les diferents orientacions de la pantalla, com ara vertical o horitzontal, cosa que permet visualitzar el contingut. [1.3.4 Orientació - CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Ús del color (A)**: el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a diferenciar els diferents estats s'inclouen subratllats, es juga amb la presència de farciment i el gruix de la vora. [1.4.1 Ús del color - CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA)**: els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. [1.4.3 Contrast mínim - CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA)**: excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [1.4.4 Canvia la mida del text - CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA)**: els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [1.4.11 Contrast d'elements no textuals - CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A)**: tota la funcionalitat del contingut (navegar pels diferents botons) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [2.1.1 Teclat - CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Focus visible (AA)**: la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [2.4.7 Focus visible - CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- **Identificació d'errors (A)**: si es detecta un error en el component, s'identifica clarament mitjançant un canvi de color i gruix de la vora i amb la indicació visual (icona) i textual (descripció de l'error). [3.3.1 Identificació d'errors - CAT](https://www.w3.org/Translations/WCAG22-ca/#error-identification) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/error-identification)

### Navegació per teclat

| Tecla | Acció |
|---|---|
| Tabulació | Navegació fins al component; navegar per les diferents opcions del desplegable (un cop obert); desplaçar-se per les diferents opcions del desplegable de selecció múltiple |
| Fletxes | Desplaçar-se per les diferents opcions del desplegable de selecció individual |
| Intro | Seleccionar una o diverses opcions (segons el tipus) |
| Esc | Cancel·lar una acció |

## Implementació (component web)

### `<dropdown-component>`

Paquet: core.

**Propietats** (el lloc i el PDF difereixen en alguns valors per defecte i descripcions; es recullen les dues fonts)

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte |
|---|---|---|---|---|
| `idPagination` | `id-pagination` | Indica si el dropdown s'utilitza per a la paginació i genera els identificadors necessaris per als seus elements. Opcional | boolean | `false` |
| `isDisabled` | `is-disabled` | Indica si el menú desplegable està deshabilitat, impedint qualsevol interacció de l'usuari. Opcional | boolean | `undefined` |
| `mode` | `mode` | Defineix si el menú desplegable és d'opció única o de múltiples opcions. Opcions: `multiple`, `single`. Opcional | string | `single` |
| `options` | `options` | Llista d'opcions disponibles en el menú desplegable. Accepta array d'objectes o string JSON. **Obligatori** | `options[]` \| string (JSON) | — |
| `popoverConfig` | `popover-config` | Atributs del popover. Accepta objecte o string JSON. Opcional | string (JSON) | `{}` |
| `showCleanButton` | `show-clean-button` | Visibilitat de la creu per eliminar les opcions seleccionades. Opcional | boolean | `false` |
| `showFilter` | `show-filter` | Mostrar o ocultar filtratge. Opcional | boolean | `false` |
| `showPopoverValue` | `show-popover-value` | Mostra popover. Opcional | boolean | `false` |
| `showTooltip` | `show-tooltip` | Permet habilitar o deshabilitar la visibilitat de la icona tooltip. Opcional | boolean | `true` |
| `size` | `size` | Controla la mida del menú desplegable. Opcions: `large`, `medium`, `small`. Opcional | string | `large` |
| `textAlternativeError` | `text-alternative-error` | Text alternatiu de l'exclamació del text d'error. Opcional | string | `undefined` |
| `textError` | `text-error` | Text d'error; quan es deixa buit no es mostra. Opcional | string | `undefined` |
| `textEtiqueta` | `text-etiqueta` | Text de l'etiqueta. Opcional | string | `undefined` |
| `textInfoTooltip` | `text-info-tooltip` | Text de la icona informativa de l'indicador de funció. Opcional | string | `undefined` |
| `titleSheetMobile` | `title-sheet-mobile` | Títol del panell emergent que apareix a breakpoints mobile. Opcional | string | `undefined` |
| `value` | `value` | Valor per defecte de l'opció seleccionada quan es carrega el component. En mode single utilitzar string i en mode multiple string[]. Opcional | string \| string[] | — |

**Variants**

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `mode` | `single` `multiple` | `single` |
| `size` | `small` `medium` `large` | `large` |

**Props que accepten JSON**

`options` — string JSON (array d'objectes):

| Key | Tipus | Requerida | Descripció |
|---|---|---|---|
| `value` | string | Sí | Text de l'opció que es mostra a l'usuari |
| `label` | string | Sí (PDF) / Opcional (lloc) | Valor associat a l'opció, que es torna com a selecció |

[discrepància: lloc diu que `label` és opcional; PDF diu que és requerida]

```json
[
  {
    "value": "texto-ejemplo",
    "label": "texto-ejemplo"
  }
]
```

`popoverConfig` — propietats de l'objecte:

| Propietat | Atribut | Descripció | Obligatorietat | Tipus |
|---|---|---|---|---|
| `contextualImageUrl` | `contextual-image-url` | URL de la imatge de la variant contextual | Opcional | string |
| `description` | `description` | Text descriptiu del popover | Opcional | string |
| `imgDescription` | `img-description` | Text alternatiu de la imatge contextual | Opcional | string |
| `linkModePopover` | `link-mode-popover` | Tipus de navegació de l'enllaç inferior | Opcional | string |
| `linkTextPopover` | `link-text-popover` | Text de l'enllaç que es mostra al final del contingut | Opcional | string |
| `padding` | `padding` | Espaiat utilitzat per evitar desbordaments del popover | Opcional | number |
| `popoverTitle` | `popover-title` | Títol que es mostra a la capçalera del popover | Opcional | string |
| `sizeTextOpen` | `size-text-open` | Mida del text que activa el popover | Opcional | string |
| `textItems` | `text-items` | Elements informatius en una cadena JSON que conté un array | Opcional | string (JSON) |
| `textOpen` | `text-open` | Text de l'activador del popover | Obligatori | string |
| `textTooltipClosePopover` | `text-tooltip-close-popover` | Etiqueta accessible del tooltip del botó de tancament | Opcional | string |
| `version` | `version` | Variant del popover | Opcional | string |

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `valueChange` | Salta en fer clic en una opció o opcions del desplegable (PDF: s'emet quan el valor del component canvia; tipus `CustomEvent<string[]>`) | `value` | `dropdown-component` |
| `blurButton` | Llançat en treure el focus d'algun dels botons | - | `button-component` |
| `focusButton` | Llançat en fer focus sobre algun dels botons | - | `button-component` |
| `handlerClick` | Llançat en fer clic en algun botó | `id` | `button-component` |
| `blurLink` | Es llança cada cop que es treu el focus de l'enllaç | - | `link-component` |
| `focusLink` | Llançat en fer focus sobre l'enllaç | - | `link-component` |
| `linkEmit` | Llançat en fer clic sobre l'enllaç | `id` | `link-component` |
| `closeSheet` | Emès en tancar-se el panell emergent | closed: `true` | `sheet-component` |

**Depèn de**: `button-component` ([Botons](component-botons.md)), `popover-component` ([Descripció emergent](component-descripcio-emergent.md)), `sheet-component` ([Panell emergent](component-panell-emergent.md)), `tooltip-component` ([Indicador de funció](component-indicador-de-funcio.md)).

**Utilitzat per**: `filter-component` ([Filtres](component-filtres.md)), `pagination-component` ([Paginació](component-paginacio.md)).

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<dropdown-component 
  mode="single" 
  text-etiqueta="Selección única" 
  text-error=""
  size="small" 
  text-info-tooltip="Texto Tooltip" 
  text-alternative-error="Texto alternativo dropdown"
  show-tooltip="false" 
  show-filter="true" 
  value='Opció 1'
  title-sheet-mobile="Títol de pàgina"
  options='[
              {
                "value": "Opció 1",
                "label": "Opció 1"
              },
              {
                "value": "Opció 2",
                "label": "Opció 2"
              },
              {
                "value": "Opció 3",
                "label": "Opció 3 - Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry"
              },
              {
                "value": "Opció 4",
                "label": "Opció 4"
              },
              {
                "value": "Opció 5",
                "label": "Opció 5"
              },
              {
                "value": "Opció 6",
                "label": "Opció 6"
              },
              {
                "value": "Opció 7",
                "label": "Opció 7"
              },
              {
                "value": "Opció 8",
                "label": "Opció 8"
              },
              {
                "value": "Opció 9",
                "label": "Opció 9"
              }
            ]
            ' 
  show-popover-value="true" 
  show-clean-button="true"
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
</dropdown-component>
```

**Exemple d'instància (PDF)**

```html
<dropdown-component
id-pagination=false
is-disabled=false
mode='single'
options=[]
popover-config='{}'
show-clean-button=false
show-filter=false
show-popover-value=false
show-tooltip=true
size='large'
text-alternative-error="texto-ejemplo"
text-error="texto-ejemplo"
text-etiqueta="texto-ejemplo"
text-info-tooltip="texto-ejemplo"
title-sheet-mobile="texto-ejemplo"
value="texto-ejemplo"
></dropdown-component>
```

Exemple amb props JSON (PDF):

```html
<dropdown-component
options='[{"value":"texto-ejemplo","label":"texto-ejemplo"}]'
></dropdown-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.0.0 | 12.1.2 | 5 octubre, 2026 | Desenvolupament: es modifica el padding-bottom del div-etiqueta |
| 12.0.0 | 12.1.1 | 11 setembre, 2026 | Desenvolupament: corregit un error on fer clic a la barra de desplaçament mentre un desplegable es troba dins d'un component modal tancava inadvertidament el desplegable |
| 12.0.0 | 12.0.3 | 4 setembre, 2026 | Desenvolupament: el z-index del popup del desplegable es canvia a 10000; les icones de les caselles de verificació es modifiquen a SVG; es corregeix el problema pel qual el modal es tancava en prémer la tecla ESC mentre el desplegable estava actiu |
| 12.0.0 | 12.0.0 | 10 juliol, 2026 | Desenvolupament: en realitzar una cerca a l'input ara només apareixen les opcions coincidents més les seleccionades |
| 12.0.0 | 11.0.0 | 19 juny, 2026 | Desenvolupament: s'afegeix el component sheet en breakpoints mòbil; s'afegeixen estats al botó de neteja |
| 12.0.0 | 10.1.0 | 29 maig, 2026 | Disseny: es crea la variant per punt de tall small de la dropdown list; s'aplica l'asset de botó d'eliminació de contingut. Desenvolupament: s'arregla el buidatge correcte de la UI en esborrar la selecció; ajustos d'accessibilitat |
| 10.0.0 | 10.0.0 | 8 maig, 2026 | Desenvolupament: s'afegeix variant de mida mitjana; resolt problema de Race Condition i problema de neteja del textError |
| 10.0.0 | 9.2.0 | 17 abril, 2026 | Disseny: s'afegeix la variant Medium; es corregeix l'ordre de les variants d'estat i mida dins les propietats |
| 8.6.0 | 9.2.0 | 27 febrer, 2026 | Desenvolupament: es corregeix l'error pel qual, en seleccionar una opció i després modificar el valor de valor, el component no s'actualitzava amb el nou valor |
| 8.6.0 | 9.1.0 | 9 febrer, 2026 | Disseny: s'aplica el botó d'eliminar el contingut en l'estat filled |
| 8.5.0 | 9.1.0 | 6 febrer, 2026 | Desenvolupament: en l'input desplegable en mode multiple s'introdueixen els label al lloc dels value; input i botó es tornen scrolleables, ja no són sticky; es fa reactiva la propietat value; adaptacions d'accessibilitat pel que fa a mides de font extra gran i augment de pantalla; s'hi afegeix botó per eliminar opcions seleccionades i s'elimina la property textDropdown |
| 8.5.0 | 8.5.0 | 20 gener, 2026 | Disseny: s'eliminen placeholders |
| 8.2.0 | 8.5.0 | 5 desembre, 2025 | Desenvolupament: es canvia el nom de la property showPopover a showPopoverValue |
| 8.2.0 | 6.2.1 | 27 octubre, 2025 | Disseny: revisió d'estils tipogràfics |
| 8.0.0 | 6.2.1 | 3 octubre, 2025 | Desenvolupament: resolució de problemes |
| 8.0.0 | 6.1.0 | 12 setembre, 2025 | Desenvolupament: nova propietat afegida. Disseny: s'ajusta el comportament del focus quan hi ha, o no, scroll bar; es modifica el text de les etiquetes de la mida Medium (passa de SM a MD) |
| 7.0.0 | 6.0.1 | 28 juliol, 2025 | Disseny: s'ajusten mínims i màxims d'amplada i alçades (Large a 56 px i Small a 48 px). Desenvolupament: evolutiu amb camp de cerca i botó de netejar filtres |
| 6.0.0 | 6.0.0 | 8 juliol, 2025 | Disseny: s'ha afegit un camp de cerca i un botó per netejar tots els filtres aplicats; s'ha eliminat la mida medium i s'ha creat la mida large, que la substitueix |
| 5.0.0 | 6.0.0 | 3 juliol, 2025 | Desenvolupament: resolució de problemes |
| 5.0.0 | 5.0.0 | 10 juny, 2025 | Disseny: s'ha incorporat una nova propietat (Show label), que permet controlar la visualització de l'etiqueta |
| 4.0.0 | 5.0.0 | 9 juny, 2025 | Desenvolupament: resolució de problemes |
| 4.0.0 | 4.0.1 | 19 maig, 2025 | Desenvolupament: resolució de problemes |
| 2.3.0 | 2.0.0 | 7 març, 2025 | Desenvolupament: resolució de problemes |
| 2.3.0 | 1.0.0 | 31 gener, 2025 | Desenvolupament: s'ajusta l'arrodoniment a small (4 px) |
| 2.2.0 | 0.1.1 | 20 gener, 2025 | Disseny: s'han afegit dissenys medium i small al component desplegable, així com l'opció de propietat entre "standard" i "multi-select" |
| 2.1.0 | 0.1.1 | 04 desembre, 2024 | Disseny: s'afegeix el botó d'ajuda per mostrar la descripció emergent |
| 2.0.0 | 0.1.0 | 02 desembre, 2024 | Sense canvis |
| 1.1.0 | 0.1.0 | 22 novembre, 2024 | Sense canvis |
| 1.1.0 | 0.0.4 | 18 novembre, 2024 | Sense canvis |
| 1.0.0 | 0.0.3 | 1 novembre, 2024 | Disseny, desenvolupament i documentació del component |

## Vegeu també
- [Botó d'opció](component-boto-d-opcio.md)
- [Camp de cerca](component-camp-de-cerca.md)
- [Casella de selecció](component-casella-de-seleccio.md)
- [Panell emergent](component-panell-emergent.md)
- [Descripció emergent](component-descripcio-emergent.md)
- [Indicador de funció](component-indicador-de-funcio.md)
- [Filtres](component-filtres.md)
- [Paginació](component-paginacio.md)
