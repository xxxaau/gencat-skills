# Casella de selecció (Checkbox)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/542d59 · Web component: `<checkbox-component>` i `<advanced-checkbox-component>` (paquet core) · Font actualitzada el 2026-10-22 · Extret el 2026-10-28

## Què és i quan usar-lo
Element de control gràfic utilitzat en formularis o quadres de diàleg que permet a l'usuari seleccionar una o més opcions d'una llista predefinida.

Element d'interfície utilitzat en formularis web i aplicacions que **permet fer seleccions múltiples entre diverses opcions**. Cada casella de selecció funciona de manera independent, així l'usuari pot marcar o desmarcar cadascuna segons les seves preferències.

### Estàndard
Les caselles de selecció són elements versàtils que s'utilitzen per fer seleccions múltiples. Casos d'ús comuns:
- **Formularis:** s'utilitzen habitualment en formularis quan l'usuari ha de fer una selecció. Per exemple, els usuaris poden necessitar acceptar termes i condicions, optar per comunicacions comercials o indicar el seu consentiment per al tractament de dades.
- **Filtres:** a les interfícies on els usuaris poden filtrar o ordenar les dades, es poden utilitzar caselles de selecció per permetre als usuaris seleccionar múltiples criteris simultàniament.
- **Configuració de preferències:** es poden utilitzar per recollir preferències d'usuari o paràmetres en aplicacions o pàgines web, com, per exemple, preferències de comunicació, concedir o revocar permisos o habilitar/inhabilitar funcions de seguretat.
- **Gestió de tasques:** en llistes de tasques pendents o eines de gestió de projectes, es poden utilitzar per marcar tasques com a completades.

Casella de selecció *versus* Botó d'opció: els botons d'opció representen un grup d'opcions que són mútuament excloents. S'utilitzen botons d'opció en els casos on només es permet seleccionar una sola opció, en comptes de la casella de selecció.

Casella de selecció *versus* Commutador: el commutador és un selector que permet triar entre un estat actiu o inactiu. S'utilitza quan l'acció resultant s'aplica instantàniament sense necessitat de confirmació addicional, normalment per aplicar variables del sistema. Les caselles de selecció generalment representen una entrada en un flux major que requereix un pas de confirmació final.

### Avançada
Una casella de selecció avançada és un element de control gràfic que, mantenint el comportament d'una casella de selecció estàndard, ofereix una presentació visual enriquida amb suport opcional per a icones o il·lustracions. Està dissenyada per a contextos on la representació visual de cada opció afavoreix la comprensió i la presa de decisions. Es pot utilitzar en:
- [Arbre de decisions](patro-arbre-de-decisions.md).

## Quan NO usar-lo / alternatives
- Casella avançada: quan es vol substituir l'estàndard.
- Opcions mútuament excloents: s'usen botons d'opció ([Botó d'opció](component-boto-d-opcio.md)).
- Acció que s'aplica instantàniament sense confirmació: s'usa el [Commutador](component-commutador.md).

## Anatomia

### Casella de selecció estàndard
- Casella de selecció per defecte. Figma: Checkbox [Show Description = True, Show Label = True, Show Tooltip = True, Label text = Etiqueta, Option = Opció, Description text = Descripció, Type = Unselected, Size = Small, State = Default]; Casella de selecció [Error text = Text d'error, Show Tooltip = True, Label = Etiqueta, Show Label = True, Size = Small, Error = False].
- Casella de selecció de tipus desplegable. Figma: Casella de selecció [Checkbox Type = Default, Size = Small].

### Casella de selecció avançada
Figma: Advanced checkbox [State = Default, Visual element = Icon | Illustration, Selected = False]; Advanced Checkbox group [Error = False | True].

## Variants, tipus i estats

### Estàndard

**Caixa de selecció**

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Type | Unselected / Selected / Indeterminate / Error | Unselected |
| State | Default / Hover / Focus / Disabled | Default |
| Size | Medium / Small | Medium |

Estats mostrats: Desseleccionat, Seleccionat, Indeterminat, Error. Figma: Casella de selecció [Type = Unselected, Size = Small, State = Default].

**Casella de selecció**

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Type | Unselected / Selected / Indeterminate / Error / Disabled | Unselected |
| State | Default / Hover / Focus | Default |
| Size | Medium / Small | Medium |
| Show Label | True / False | True |
| Show Description | True / False | True |
| Show Tooltip | True / False | True |

**Grup de caselles de selecció**

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Size | Medium / Small | Primary [a verificar: la font indica "Primary" com a valor per defecte, que no és un valor de Size] |
| Error | True / False | False |
| Show Label | True / False | True |
| Show Tooltip | True / False | True |

Figma del grup amb error: Checkbox group [Error text = Text d'error, Checkbox 03 = True, Checkbox 04 = True, Checkbox 05 = True, Tooltip = True, Label = Etiqueta, Size = Small, Error = No].

**Tipus de caselles de selecció**

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Checkbox Type | Default / Dropdown-collapsed / Dropdown-expanded | Default |
| Size | Medium / Small | Medium |
| Type | Unselected / Selected / Indeterminate / Error / Disabled | Unselected |
| State | Default / Hover / Focus | Default |
| Show Chevron | True / False | False |
| Show Label | True / False | False |
| Show Tooltip | True / False | False |
| Show Description | True / False | False |

### Avançada

**Casella de selecció avançada**

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Default / Hover / Selected / Focus / Disabled | Primary [a verificar: valor per defecte tal com consta a la font] |
| Visual Element | Icon / Illustration | False [a verificar: valor per defecte tal com consta a la font] |
| Selected | True / False | True |
| Change Text | Text | Text |
| Show Icon | True / False | True |
| Change Icon (subpropietat de Show Icon) | Icon | House |
| Change Illustration | Illustration | Habitatge |

Estats mostrats: Default, Disabled, Hover, Focus; element visual (icona / il·lustració); seleccionat (False / True).

**Grup de caselles de selecció avançades**

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Error | True / False | False |
| Slot | Advanced checkbox | Advanced checkbox |
| Text Error | Text | Text d'error |

## Mides i espaiats
- Utilitza caselles de selecció ***medium*** en la majoria dels casos.
- Les caselles de selecció més petites (small) funcionen bé a les pàgines on és útil fer-les menys visibles. Per exemple, en una taula de dades en les quals es poden seleccionar files per editar-les.
- Error amb una sola casella: el gruix de la vora augmenta a 2px.

## Comportament i interacció

### Errors (estàndard)
La forma de mostrar els errors varia en funció del nombre de caselles de selecció. Si només n'hi ha una, es marca en vermell la casella de selecció i el gruix de la vora augmenta a 2px. A partir de dues caselles apareix una línia vermella que abraça les diferents opcions del llistat.

### Interacció (estàndard)
- **Marcar/desmarcar:** els usuaris poden seleccionar o desmarcar una casella de selecció fent clic a qualsevol àrea del component (casella o text).
- A diferència dels botons d'opció, les caselles de selecció representen opcions independents, de manera que marcar-ne una no desmarca les altres, tret que tinguin una relació pare-fill.
- El desplegable es pot expandir clicant en qualsevol lloc del camp o sobre el xebró.
- El desplegable **no es tanca automàticament** en seleccionar una opció, permetent seleccions múltiples.

### Caselles niades
Les caselles de selecció poden tenir una relació pare-fill amb altres caselles de selecció.
- Quan la casella de selecció pare està marcada, totes les caselles de selecció filles estan marcades.
- Si una casella de selecció pare no està marcada, totes les caselles de selecció filles no estan marcades.
- Si algunes, però no totes, les caselles de selecció filles estan marcades, la casella de selecció pare es converteix en una casella de selecció indeterminada.
- **Activació:** la casella de selecció sempre té una activació per part de l'usuari; el sistema no pot fer canvis de seleccions sense que l'usuari ho hagi sol·licitat.

### Desplegament de les opcions niades (tipus desplegable)
- Les opcions filles es poden ocultar o mostrar mitjançant un botó d'expansió (representat amb una icona de xebró).
- Aquesta acció d'expandir o col·lapsar el grup es fa **només** clicant sobre el xebró.
- El clic sobre l'etiqueta (label) o la casella pare només activa o desactiva la selecció, **sense modificar** l'estat expandit o col·lapsat.

### Adaptació responsiva
Per a espais reduïts, les etiquetes llargues poden saltar a una segona línia. En aquests casos, el text creix cap avall de manera que la casella i l'etiqueta quedin alineats a la part superior i el text tabulat en un mateix nivell.

### Avançada: nombre d'elements, errors i interacció
- **Nombre d'elements:** en les caselles de selecció avançades mai hi ha una única opció; sempre són mínim dues.
- **Errors:** l'error es mostra sempre de forma global.
- **Marcar/desmarcar:** els usuaris poden seleccionar o desmarcar una casella fent clic a qualsevol part del contenidor del component. Les caselles representen opcions independents (marcar-ne una no desmarca les altres tret que tinguin una relació pare-fill).
- **Activació:** sempre per part de l'usuari; el sistema no pot fer canvis de seleccions sense que l'usuari ho hagi sol·licitat.
- **Adaptació responsiva:** igual que l'estàndard (etiquetes llargues a una segona línia).

## Contingut i microcopy
Exemples de la font: etiqueta "Etiqueta", opció "Opció", descripció "Descripció", "Text d'error"; avançada: "Cal seleccionar almenys una opció", "Error de validació".

## Bones pràctiques

### Estàndard

#### Àrea clicable
- **FER:** Augmenta l'àrea clicable de les caselles de selecció, cosa que permet a l'usuari seleccionar l'opció tant clicant en la casella com en la seva etiqueta. Els objectes clicables petits són més propensos a causar errors i frustració, especialment en dispositius tàctils.
- **NO FER:** No limitis l'àrea clicable només a la casella de selecció, ja que això pot fer que l'usuari tingui dificultats per seleccionar l'opció correcta.

#### Escaneig
- **FER:** És recomanable dissenyar la llista d'opcions verticalment per facilitar l'escaneig dels continguts.
- **NO FER:** No és recomanable dissenyar la llista d'opcions horitzontalment, ja que dificulta l'escaneig de continguts.

#### Redacció
- **FER:** Utilitza una redacció positiva i activa per als textos d'opcions, de manera que quedi clar el que passarà si l'usuari activa la casella de verificació.
- **NO FER:** No utilitzis negacions com "No m'enviï més correus electrònics": significaria que l'usuari hauria de marcar la casella perquè alguna cosa no succeeixi i pot donar lloc a confusió.
- **FER:** Es recomana que les etiquetes siguin inferiors a 4 paraules, especialment en aquells casos amb opcions múltiples, tot i que poden existir excepcions.
- **NO FER:** No es recomana que les etiquetes siguin superiors a 4 paraules, especialment en aquells casos amb opcions múltiples.

#### Errors
- **FER:** Si es produeix un error relacionat amb les caselles de selecció, proporciona missatges d'error clars i orientació sobre com corregir el problema. Assegura't que els usuaris poden identificar fàcilment quines caselles de selecció requereixen atenció i com resoldre l'error.
- **NO FER:** Si es produeix un error relacionat amb les caselles de selecció, no proporcionis missatges d'error confusos o poc clars que no indiquen com corregir el problema.

#### Selecció predeterminada
- **FER:** Estableix una selecció predeterminada per a les caselles de selecció si un valor és més comú, així com per establir configuracions que s'alineïn amb les expectatives o preferències dels usuaris.
- **NO FER:** No estableixis una selecció predeterminada que pugui conduir a seleccions no intencionades o en casos que l'usuari necessiti prendre una decisió activament.

Casos en què no s'ha de preseleccionar una opció:
- Processos de consentiment: situacions en què l'usuari ha de donar el seu consentiment sobre temes de seguretat o motius legals. L'usuari sempre ha de seleccionar una opció de forma explícita.
- Recopilació de dades imparcials: quan es volen recopilar dades no esbiaixades. Els valors per defecte condicionarien les respostes.

#### Etiqueta
- **FER:** Els grups de caselles de selecció s'acompanyen d'un títol o etiqueta descriptiva per proporcionar context i claredat a l'usuari. Es millora l'accessibilitat i la usabilitat, assegurant una correcta jerarquització dels continguts i facilitant la lectura a les persones amb tecnologies d'assistència.
- **NO FER:** Els grups de caselles de selecció no s'acompanyen d'un títol o etiqueta descriptiu.

#### Sobrecàrrega
- **FER:** Les llistes d'opcions s'agrupen en grups lògics o disposen de cercador. Presentar una llarga llista d'opcions pot crear fatiga visual i dificultar la presa de decisions dels usuaris.
- **NO FER:** Les llistes d'opcions no s'agrupen en grups lògics ni disposen de cercador.

#### Opcions excloents
- **FER:** S'usen en cas que s'hagi de seleccionar d'una llista d'opcions no excloents entre elles.
- **NO FER:** No s'usen quan s'ha de seleccionar una opció d'una llista d'opcions que són mútuament excloents. En aquests casos s'usen botons d'opció.

#### Anidats
- **NO FER:** No s'afegeix la descripció al component de casella de selecció de tipus anidat/desplegable (incloent pare i fills).

#### Nombre de resultats
- **FER:** El nombre total de resultats corresponent a la casella de selecció s'ha d'afegir al mateix títol/etiqueta/label.
- **NO FER:** No s'ha d'afegir el nombre de resultats a la descripció del component.
- **FER:** Totes les caselles de selecció han d'incorporar el nombre de resultats de manera coherent.
- **NO FER:** No deixis d'afegir el nombre de resultats en algunes caselles ni ho facis de manera inconsistent entre opcions.

### Avançada

#### Nombre d'opcions
- **FER:** Utilitza sempre un mínim de 2 opcions.

#### Icones i il·lustracions
- **NO FER:** No barregis estils (només text, icones o il·lustracions) dins les opcions d'una mateixa pregunta. Aplica el mateix a totes les opcions d'una mateixa pregunta.
- **FER:** Les icones s'han d'utilitzar només per reforçar el reconeixement visual de categories clares i estables en què la icona sigui un estàndard.
- **FER:** Utilitza il·lustracions sempre que les opcions es diferenciïn principalment per una configuració física, espacial o funcional visible.
- **NO FER:** No utilitzis il·lustracions per representar conceptes abstractes o subjectius, com ara nivells d'experiència, preferències personals o estats d'ànim. Quan la diferència entre opcions no és física ni espacial, la il·lustració no aporta informació objectiva i pot induir l'usuari a triar basant-se en la imatge en lloc del text.

Informació més detallada sobre quan utilitzar icones i il·lustracions: patró [Arbre de decisions](patro-arbre-de-decisions.md).

## Accessibilitat

### Pautes WCAG
- **Ús del color (A):** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per diferenciar els diferents estats s'inclouen icones (marcat quan està seleccionat i guió quan està en estat indeterminat), s'afegeix farciment al quadrat i s'augmenta el gruix de les vores (*hover*). [1.4.1 CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són excepció d'aquesta norma. [1.4.3 CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA):** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [1.4.4 CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA):** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [1.4.11 CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Espaiat del text (AA):** no es perd cap contingut ni funcionalitat si s'ajusten: alçada de línia (interlineat) de com a mínim 1,5 vegades la mida de la lletra; espaiat entre paràgrafs com a mínim dues vegades la mida de la lletra; espaiat entre lletres (*tracking*) de com a mínim 0,12 vegades la mida de la lletra; espaiat entre paraules de com a mínim 0,16 vegades la mida de la lletra. [1.4.12 CAT](https://www.w3.org/Translations/WCAG22-ca/#text-spacing) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/text-spacing)
- **Teclat (A):** tota la funcionalitat del contingut (navegar pels diferents botons d'opció) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [2.1.1 CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Focus visible (AA):** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [2.4.7 CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible) (també [2.4.7](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible.html))
- **Identificació d'errors (A):** si es detecta un error en el component, s'identifica clarament que presenta un error mitjançant l'aparició d'un element gràfic (augment del gruix de la vora o aparició d'una línia vertical) i amb la indicació visual (icona) i textual (descripció de l'error). [3.3.1 CAT](https://www.w3.org/Translations/WCAG22-ca/#error-identification) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/error-identification)

## Implementació (component web)

### `<checkbox-component>`

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat |
|---|---|---|---|---|---|
| `checkboxProps` | `checkbox-props` | Array amb la informació de cada casella de selecció del grup. Accepta array d'objectes o string JSON | `string` (JSON) | — | Opcional |
| `group` | `group` | Per crear un grup de caselles de selecció: cal donar-li un nom (estil: `group1` o `group2`). Identificador de grup per a camps de formulari relacionats | `string` | `undefined` | Opcional |
| `isDisabled` | `is-disabled` | `true` perquè es mostri deshabilitat, `false` perquè no | `boolean` | `undefined` | Opcional |
| `isError` | `is-error` | `true` si es vol que es mostri el `textError` i `false` si no | `boolean` | `undefined` | Opcional |
| `parentChildBehavior` | `parent-child-behavior` | Permet habilitar el comportament pare-fill dins del grup de checkbox | `boolean` | `true` | Opcional |
| `parentChildDropdown` | `parent-child-dropdown` | Permet habilitar el comportament dropdown pare-fill dins del grup de checkbox | `boolean` | `false` | Opcional |
| `showEtiqueta` | `show-etiqueta` | Mostrar o amagar etiqueta | `boolean` | `true` | Opcional |
| `showTooltip` | `show-tooltip` | `true` o `false` en funció de si es vol mostrar o no l'indicador de funció | `boolean` | `true` | Opcional |
| `size` | `size` | Mida de la casella de selecció. Opcions: `medium`, `small` | `string` | `medium` | Opcional |
| `textAlternativeError` | `text-alternative-error` | Text alternatiu de l'exclamació del text d'error | `string` | `undefined` | Opcional |
| `textError` | `text-error` | Text d'error que es vol mostrar. Quan no s'escriu res en aquest camp, no es mostra cap error | `string` | `undefined` | Opcional |
| `textEtiqueta` | `text-etiqueta` | Text de l'etiqueta que va al costat de la icona de l'indicador de funció | `string` | `undefined` | Opcional |
| `textInfoTooltip` | `text-info-tooltip` | Text de la icona informativa de l'indicador de funció (tooltip associat) | `string` | `undefined` | Opcional |
| `value` | `value` | Checkbox que per defecte surten marcats en carregar el component. Valor actual del component | `string \| string[]` | — | Opcional |
| `visibilityDescription` | `visibility-description` | `true` o `false` per mostrar o amagar la descripció | `boolean` | `undefined` | Opcional |

**Props que accepten JSON**

`checkboxProps` — string JSON (array d'objectes) amb l'estructura:

| Clau | Descripció | Tipus | Requerida |
|---|---|---|---|
| `value` | Nom value de l'element checkbox | `string` | Sí |
| `option` | Títol de la casella de selecció | `string` | Sí |
| `description` | Descripció de la casella de selecció | `string` | Opcional segons el lloc; "Sí" segons el PDF [discrepància] |

Exemple (PDF):

```json
[
{
"value": "texto-ejemplo",
"option": "texto-ejemplo",
"description": "texto-ejemplo"
}
]
```

**Variants**

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `size` | `small` `medium` | `medium` |

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre / tipus | Origen |
|---|---|---|---|
| `checkboxChange` | Salta cada cop que es fa clic en un checkbox (s'emet quan canvia l'estat del checkbox) | `index`, `checked`, `value`, `values` — `CustomEvent<{ index: number; checked: boolean; value: string; values: string[]; }>` | `checkbox-component` |
| `valueChange` | Salta cada cop que es fa clic en un checkbox (s'emet quan canvia el valor del component) | `values` — `CustomEvent<string[]>` | `checkbox-component` |

**Depèn de:** `tooltip-component` ([Indicador de funció](component-indicador-de-funcio.md)).

**Exemple d'ús**

```html
<!-- /index.html -->
<checkbox-component
  checkbox-props='[
    {
      "value": "opcio1",
      "option": "Opció 1",
      "description": "Descripció 1"
    },
    {
      "value": "opcio2",
      "option": "Opció 2",
      "description": "Descripció 2"
    },
    {
      "value": "opcio3",
      "option": "Opció 3",
      "description": "Descripció 3"
    },
    {
      "value": "opcio4",
      "option": "Opció 4",
      "description": "Descripció 4"
    }
  ]'
  group="group1"
  is-disabled="false"
  is-error="false"
  parent-child-behavior="true"
  parent-child-dropdown="false"
  show-etiqueta="true"
  show-tooltip="true"
  size="small"
  text-alternative-error="Text alternative"
  text-error=""
  text-etiqueta="Etiqueta"
  text-info-tooltip="Texto Tooltip"
  value='["opcio2", "opcio3"]'
  visibility-description="true">
</checkbox-component>
```

Exemple d'instància (PDF):

```html
<checkbox-component
checkbox-props=[]
group="texto-ejemplo"
is-disabled=false
is-error=false
parent-child-behavior=true
parent-child-dropdown=false
show-etiqueta=true
show-tooltip=true
size='medium'
text-alternative-error="texto-ejemplo"
text-error="texto-ejemplo"
text-etiqueta="texto-ejemplo"
text-info-tooltip="texto-ejemplo"
value="texto-ejemplo"
visibility-description=false
></checkbox-component>
```

Exemple amb props JSON (PDF):

```html
<checkbox-component
checkbox-props='[{"value":"texto-ejemplo","option":"texto-ejemplo","description":"texto-ejemplo"}]'
></checkbox-component>
```

### `<advanced-checkbox-component>`

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat |
|---|---|---|---|---|---|
| `checkboxItems` | `checkbox-items` | Array que conté la informació de cada checkbox dins d'un mateix grup. Accepta array d'objectes o string JSON | `AdvancedCheckboxItem[] \| string` | — | Obligatori |
| `group` | `group` | Nom del grup (identificador de grup per a camps de formulari relacionats) | `string` | `undefined` | Obligatori |
| `mode` | `mode` | Manera del checkbox; està relacionat amb els seus estats. Opcions: `default`, `disabled`, `error` | `string` | `default` | Obligatori |
| `textAlternativeError` | `text-alternative-error` (el lloc indica l'atribut `textAlternativeError`) | Text alternatiu de la icona d'error | `string` | `` (buit) | Opcional |
| `textError` | `text-error` | Text d'error | `string` | `` (buit) | Opcional |
| `value` | `value` | Value del component en conjunt | `string \| string[]` | — | Opcional |
| `visualElement` | `visual-element` | Elecció de l'element visual que acompanyi el text. Opcions: `icon`, `illustration`, `none` | `string` | `icon` | Opcional |

**Props que accepten JSON**

`checkboxItems` — string JSON (array d'objectes) amb l'estructura `AdvancedCheckboxItem`:

| Clau | Descripció | Tipus | Requerida |
|---|---|---|---|
| `value` | Value del checkbox | `string` | Sí |
| `title` | Títol del checkbox | `string` | Sí |
| `iconOrIllustration` | Si s'ha seleccionat el mode icon, cal introduir la classe de bootstrap. Si s'ha introduït illustration en mode, cal introduir la ruta cap a la il·lustració | `string` | Sí |

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

**Variants**

| Propietat | Defecte | Valors |
|---|---|---|
| `mode` | `default` | `default` `disabled` `error` |
| `visualElement` | `icon` | `icon` `illustration` `none` |

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre / tipus | Origen |
|---|---|---|---|
| `checkboxChange` | S'emet en alternar un checkbox (quan canvia l'estat del checkbox) | `index`, `checked`, `value` — `CustomEvent<{ index: number; checked: boolean; value: string; values: string[]; }>` | `advanced-checkbox-component` |
| `valueChange` | S'emet quan canvia la selecció | `value` — `CustomEvent<string[]>` | `advanced-checkbox-component` |

**Exemple d'ús**

```html
<!-- /index.html -->
<advanced-checkbox-component
    group="grup-error"
    mode="error"
    visual-element="icon"
    text-error="Cal seleccionar almenys una opció"
    text-alternative-error="Error de validació"
    value='[]'
    checkbox-items='[
      {"value":"habitatge","title":"Habitatge lorem ipsum dolor ismet, lorem ipsum","iconOrIllustration":"bi-house"},
      {"value":"treball","title":"Treball","iconOrIllustration":"bi-briefcase"}
    ]'>
  </advanced-checkbox-component>
```

Exemple d'instància (PDF):

```html
<advanced-checkbox-component
checkbox-items=[]
group="texto-ejemplo"
mode='default'
text-alternative-error=''
text-error=''
value="texto-ejemplo"
visual-element='icon'
></advanced-checkbox-component>
```

Exemple amb props JSON (PDF):

```html
<advanced-checkbox-component
checkbox-items='[{"value":"texto-ejemplo","title":"texto-ejemplo","iconOrIllustration":"texto-ejemplo"}]'
></advanced-checkbox-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.0.0 | 12.1.2 | 5 octubre, 2026 | **Desenvolupament**: casella de selecció avançada: s'elimina l'atribut ariaLabelledBy de l'input |
| 12.0.0 | 12.0.3 | 4 setembre, 2026 | **Desenvolupament**: les icones de les caselles de verificació es modifiquen a SVG |
| 12.0.0 | 10.1.0 | 29 maig, 2026 | **Disseny**: modificació del layout i color de la capa per passar les il·lustracions a color neutres en la casella de selecció avançada amb il·lustració. **Desenvolupament** del component de casella de selecció avançada |
| 11.0.0 | 9.1.0 | 8 maig, 2026 | **Disseny**: disseny del component de casella de selecció avançada. |
| 8.5.0 | 9.1.0 | 6 febrer, 2026 | **Desenvolupament**: es fan canvis CSS relatius a mode focus. Es fa reactiva la propietat value |
| 8.5.0 | 7.0.0 | 20 gener, 2026 | **Disseny**: es modifica el focus perquè englobi l'input i no el text. |
| 8.2.0 | 7.0.0 | 27 octubre, 2025 | **Disseny**: revisió d'estils tipogràfics |
| 6.0.0 | 7.0.0 | 24 octubre, 2025 | **Desenvolupament**: resolució de problemes |
| 6.0.0 | 6.2.1 | 3 octubre, 2025 | **Desenvolupament**: resolució de problemes. |
| 6.0.0 | 6.1.0 | 12 setembre, 2025 | **Desenvolupament**: nova propietat afegida |
| 6.0.0 | 6.0.1 | 28 juliol, 2025 | **Desenvolupament** de l'evolutiu |
| 6.0.0 | 6.0.0 | 8 juliol, 2025 | **Disseny**: s'ha creat un nou suport per a caselles de selecció niades i s'han incorporat noves variants. |
| 4.0.0 | 6.0.0 | 3 juliol, 2025 | **Desenvolupament**: resolució de problemes |
| 5.0.0 | 5.0.0 | 10 juny, 2025 | **Disseny**: s'ha incorporat una nova propietat (*Show label*), que permet controlar la visualització de l'etiqueta. |
| 4.0.0 | 5.0.0 | 9 juny, 2025 | **Desenvolupament**: resolució de problemes |
| 4.0.0 | 4.0.1 | 19 maig, 2025 | **Desenvolupament**: resolució de problemes |
| 2.3.0 | 2.0.0 | 7 març, 2025 | **Desenvolupament**: resolució de problemes. |
| 2.3.0 | 1.0.0 | 31 gener, 2025 | **Disseny**: s'eliminen marges laterals de l'estat focus. La separació del focus respecte al contingut passa de 2 px a 1 px. |
| 1.0.0 | 0.0.3 | 1 novembre, 2024 | **Disseny**, **desenvolupament** i **documentació** del component. |

## Vegeu també
- [Botó d'opció](component-boto-d-opcio.md): per seleccionar una opció dins d'un conjunt d'opcions mútuament excloents.
- [Desplegable](component-desplegable.md): per realitzar una selecció única o múltiple d'un llistat conservant espai de pantalla.
- [Commutador](component-commutador.md)
- [Arbre de decisions](patro-arbre-de-decisions.md)
- [Indicador de funció](component-indicador-de-funcio.md)
