# Control de rang (Slider)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/10aa14 · Web component: `<slider-component>` (paquet core) · Font actualitzada el 2026-10-19 · Extret el 2026-10-28

## Què és i quan usar-lo
El control de rang permet a l'usuari seleccionar un valor o un rang de valors dins d'un interval predefinit arrossegant un control lliscant.

És especialment útil en aquells escenaris on l'usuari necessita ajustar de manera ràpida i intuïtiva un valor numèric dins d'uns límits preestablerts. Aquest component proporciona una interacció visual i immediata, evitant la introducció manual de dades i reduint el risc d'errors.

Dins del sistema es distingeixen dues variants del component:
1. **Control de rang simple.** Permet seleccionar un únic valor dins del rang establert.
2. **Control de rang (doble).** Permet seleccionar un interval (valor mínim i màxim) dins del rang establert.

Ambdues variants poden estar **segmentades**, és a dir, el rang pot dividir-se visualment en trams predefinits per ajudar l'usuari a identificar punts de referència dins de l'escala (p. ex. intervals de 10 en 10).

Quan s'utilitza:
- Per seleccionar un únic valor o un interval de valors numèrics.
- En filtres, configuracions, visors de mapa, gràfiques, etc.
- Quan és important que l'usuari percebi de manera visual la posició del valor dins de l'interval.
- Quan un valor relatiu és més important que un valor exacte.

## Quan NO usar-lo / alternatives
- Quan és necessari introduir un valor exacte (en aquest cas és preferible un camp de text numèric, vegeu [Camp d'entrada](component-camp-d-entrada.md)).
- Si el rang de valors és molt gran o molt petit i dificulta la selecció precisa amb un control de rang.
- Quan no hi ha un rang predefinit o el valor no és numèric.

## Anatomia
Figma: anatomia (Control de rang/Control de rang / bones pràctiques/Frame 1000001298/DOC_Control_rang/disseny/anatomia). Elements deduïts de les propietats i del comportament: pista, un o dos controls lliscants, etiqueta, camps d'entrada numèrics, segments (opcionals), línia central, indicador de funció (tooltip) i text d'ajuda [a verificar: la font només mostra la imatge d'anatomia, sense llista numerada].

## Variants, tipus i estats

### Control de rang simple

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Default / Error | Default |
| Show Label | True / False | True |
| Show Tooltip | True / False | False |
| Show Segments | True / False | False |

Variants Figma (Slider_Simple): Show Tooltip = False; Show Segments = False; Show Interval Value = False; Minimum value = 0%; Maximum value = 100%; Label = Etiqueta; Show Label = True; Show Slider Center = False; Show Center Label = False; State = Default.

### Control de rang (doble)

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Default / Error first input / Error second input | Default |
| Show Label | True / False | True |
| Show Tooltip | True / False | False |
| Show Segments | True / False | False |
| Show Slider Center | True / False | True |
| Show Center Label | True / False | False |

Variants Figma (Slider_Advanced): Show Tooltip = False; Show Segments = False; Show Slider Center = True; Minimum value = 0%; Maximum value = 100%; Interval value = Interval value; Label = Etiqueta; Show Center Label = False; Show Interval Value = False; Show Label = True; State = Default.

## Comportament i interacció

### Adaptació responsiva
- En **escriptori**, el control de rang es visualitza complet amb els camps d'entrada numèrica alineats horitzontalment, si l'espai ho permet.
- En **punts de tall més petits**, el control de rang i els camps d'entrada es compacten; en rang doble, si l'ample dels camps d'entrada excedeix l'espai, cada camp passa a una nova línia automàticament.

### Interacció
L'usuari pot interactuar amb el component de diverses maneres:
1. Arrossegant el control lliscant.
2. Clicant directament sobre la pista.
3. Introduint el valor manualment en el camp d'entrada numèric.

El procés és el següent:
1. Mentre es mou el control lliscant, l'etiqueta de l'indicador s'actualitza de manera dinàmica.
2. Un cop l'usuari surt del control, el camp d'entrada s'actualitza, no abans.
3. El mateix passa quan el valor es modifica des del camp d'entrada: el control lliscant només s'actualitza quan l'usuari surt del camp, per evitar canvis constants mentre s'escriu.

Després d'aquesta base comuna, el component es pot presentar en diverses variants segons el tipus d'interacció desitjada: simple, segmentat o dual.

### Control de rang simple
L'usuari ajusta el valor movent el control lliscant al llarg de la pista, i aquest es reflecteix de manera dinàmica mentre es desplaça. És una solució ideal quan es busca seleccionar un valor aproximat dins d'un interval sense necessitat de passos predefinits.

### Control de rang segmentat
La pista es divideix en segments visibles que representen els valors possibles, i el control lliscant s'alinea automàticament amb el segment més proper. Aquest format és ideal quan hi ha pocs passos i es vol que l'usuari pugui identificar clarament els valors disponibles abans de seleccionar-ne un. Pot aparèixer tant en un control de rang (doble) com en un control de rang simple.

### Control de rang avançat (doble)
Compta amb dos controls lliscants, un per al valor mínim i un altre per al valor màxim, que es poden moure de manera independent sense creuar-se. L'interval seleccionat queda ressaltat visualment entre els dos controls, facilitant la comprensió del rang escollit. És especialment útil per a filtres o configuracions on es vol limitar un rang.

### Estat d'error
El control de rang pot entrar en estat d'error quan l'usuari introdueix un valor no vàlid dins del camp numèric associat. Els casos més habituals són:
- **Valor fora de l'interval permès:** quan s'introdueix un nombre més petit o més gran que els límits establerts. El control lliscant es manté en la seva última posició vàlida, mentre que el camp numèric manté el valor erroni i mostra un missatge d'error. Exemple: si l'usuari escriu "-89" i el mínim és "0", el lliscant queda en l'últim valor vàlid introduït, però el camp d'entrada conserva "-89" amb l'error actiu.
- **Format incorrecte:** quan s'introdueixen decimals en un camp configurat per a nombres enters, operacions matemàtiques (sumes, restes, etc.) o caràcters especials. El missatge d'error informa de la restricció corresponent (per exemple: *"Només s'accepten nombres enters dins l'interval"*).

### Restricció de text en el camp numèric
El camp numèric associat al control de rang només accepta valors numèrics vàlids dins l'interval establert. No es permet la introducció de lletres, ni de caràcters especials (tot i que en alguns casos es poden admetre alguns caràcters com el signe decimal o el signe negatiu) ni d'expressions de text, garantint així la coherència entre el valor introduït i el valor que el control pot representar.

### Comportament dinàmic en filtres
En contextos de filtre, el component funciona de manera dinàmica i immediata: quan l'usuari introdueix un valor erroni i surt del focus del camp, apareix el missatge d'error al moment. D'aquesta manera, no cal esperar a aplicar els filtres per validar, i l'usuari rep un retorn clar i instantani sobre la seva entrada.

## Contingut i microcopy
- Exemple de missatge d'error de format: "Només s'accepten nombres enters dins l'interval".
- Exemple de codi: títol "Selecciona tram d'ingressos", etiquetes "Mínim" / "Màxim", text d'error "Valor no válido", text d'ajuda "Text d'ajuda", text informatiu "Text informatiu", unitats "%".

## Bones pràctiques

### Etiquetes
- **FER:** Les etiquetes han de ser curtes, clares i descriptives.
- **NO FER:** No utilitzar etiquetes llargues ni confuses que facin difícil entendre el rang.
- **NO FER:** No utilitzar els segments interns per seleccionar intervals d'1 en 1 pas.

### Valors
- **FER:** Els valors mínim i màxim han de ser sempre visibles i coherents amb els controls.
- **FER:** Si el rang ho requereix, defineix clarament els valors positius i negatius, tant en les etiquetes com en el camp numèric.
- **FER:** Mostra les unitats de mesura (°C, km, €, etc.) per donar context.
- **FER:** Per valors comptables, la unitat no s'inclou i es mostra a l'etiqueta superior.
- **NO FER:** No incloguis els valors comptables dins del camp numèric.
- **NO FER:** Evita intervals massa amplis o massa petits per a la interacció (per exemple, decimals).

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG) que cita el component:
- **1.4.1 Ús del color (A):** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a diferenciar els diferents estats s'inclouen icones (marcat quan està seleccionat i guió quan està en estat indeterminat), s'afegeix farciment al quadrat i s'augmenta el gruix de les vores (*hover*). (CAT: https://www.w3.org/Translations/WCAG22-ca/#use-of-color · EN: https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **1.4.3 Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són excepció d'aquesta norma. (CAT: https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum · EN: https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **1.4.11 Contrast d'elements no textuals (AA):** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. Els elements decoratius, com el divisor, estan exempts. (CAT: https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast · EN: https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **2.4.6 Encapçalaments i etiquetes descriptives (AA):** inclou etiquetes descriptives o `aria-label` per indicar clarament la funció del control de rang. (CAT: https://www.w3.org/Translations/WCAG22-ca/#headings-and-labels · EN: https://www.w3.org/WAI/WCAG22/Understanding/headings-and-labels)
- **4.1.2 Nom, funció, valor (A):** usa atributs com `aria-checked` per reflectir l'estat del control de rang als lectors de pantalla. (CAT: https://www.w3.org/Translations/WCAG21-ca/#name-role-value · EN: https://www.w3.org/TR/WCAG21/#name-role-value)
- **2.4.7 Focus visible (AA):** la navegació del control de rang és visible mitjançant un rectangle extern. (CAT: https://www.w3.org/Translations/WCAG22-ca/#focus-visible · EN: https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- **3.3.1 Identificació d'errors (A):** si es detecta un error en el component, s'identifica clarament que aquest presenta un error mitjançant un canvi de color i gruix de la vora i amb la indicació visual (icona) i textual (descripció de l'error) de l'error. (CAT: https://www.w3.org/Translations/WCAG22-ca/#error-identification · EN: https://www.w3.org/WAI/WCAG22/Understanding/error-identification)

### Navegació per teclat

| Tecla | Acció |
|---|---|
| Fletxa esquerra / Fletxa avall | Disminueix el valor del control de rang en un pas |
| Fletxa dreta / Fletxa amunt | Augmenta el valor del control de rang en un pas |
| Majúscules + Fletxa esquerra / Fletxa avall | Disminueix el valor del control de rang en un pas més gran (per exemple, de -10 en -10) |
| Majúscules + Fletxa dreta / Fletxa amunt | Augmenta el valor del control de rang en un pas més gran (per exemple, de 10 en 10) |
| Fn + fletxa esquerra / Home | Salta al valor mínim |
| Fn + fletxa dreta / End | Salta al valor màxim |
| Tabulació | Navega al següent element interactiu |
| Shift + Tabulació | Navega a l'anterior element interactiu |
| Enter | Activa l'element interactiu seleccionat (concretament el camp d'entrada numèric) |

## Implementació (component web)

### `<slider-component>`
Paquet: core.

**Propietats**

Taula de la pàgina del lloc (amb obligatorietat):

| Propietat | Atribut HTML | Descripció | Obligatorietat | Tipus |
|---|---|---|---|---|
| `centerLine` | `center-line` | Controla la visibilitat de la línia central | Opcional | Boolean |
| `max` | `max` | Valor màxim del rang | Obligatori | Number |
| `middleValue` | `middle-value` | Controla la visibilitat del valor mitjà entre min i màx | Opcional | Boolean |
| `min` | `min` | Valor mínim del rang | Obligatori | Number |
| `mode` | `mode` | Permet alternar entre selecció de màxim i mínim o només màxim | Obligatori | String |
| `showSteps` | `show-steps` | Controla la visibilitat i funció dels steps | Opcional | Boolean |
| `showTextHelp` | `show-text-help` | Visibilitat del text descriptiu | Opcional | Boolean |
| `showTooltip` | `show-tooltip` | Controlar la visibilitat de la icona informativa amb tooltip | Opcional | Boolean |
| `step` | `step` | Valor dels increments. Quan showSteps és false, per defecte el valor d'aquesta property és 1, però no cal definir-la com a 1 | Opcional | Number |
| `textError` | `text-error` | Text d'error quan s'introdueixen valors incorrectes als inputs de tipus text | Obligatori | String |
| `textEtiquetaFirstInput` | `text-etiqueta-first-input` | Text de l'etiqueta de primer input | Obligatori | String |
| `textEtiquetaSecondInput` | `text-etiqueta-second-input` | Text de l'etiqueta del segon input | Obligatori | String |
| `textHelpSlider` | `text-help-slider` | Text descriptiu de l'slider | Opcional | String |
| `textInfoTooltip` | `text-info-tooltip` | Text del tooltip de la icona informativa si està activa | Opcional | String |
| `titleSlider` | `title-slider` | Títol de l'etiqueta global de l'slider | Obligatori | String |
| `units` | `units` | Unitats del rang | Obligatori | String |
| `value` | `value` | Valor o valors min i màx per defecte del slider. En mode double escriure només max, en single min i max | Opcional | String (JSON) |

Valors per defecte segons el PDF (v12.0.0):

| Propietat | Atribut HTML | Descripció (PDF) | Tipus | Per defecte |
|---|---|---|---|---|
| `centerLine` | `center-line` | Activa o desactiva aquesta característica. | boolean | `true` |
| `max` | `max` | Valor numèric. | number | `100` |
| `middleValue` | `middle-value` | Activa o desactiva aquesta característica. | boolean | `true` |
| `min` | `min` | Valor numèric. | number | `0` |
| `mode` | `mode` | Variant visual del component. Opcions: `double`, `single`. | string | `double` |
| `showSteps` | `show-steps` | Mostra o amaga aquest element. | boolean | `false` |
| `showTextHelp` | `show-text-help` | Mostra o amaga aquest element. | boolean | `true` |
| `showTooltip` | `show-tooltip` | Mostra o amaga aquest element. | boolean | `true` |
| `step` | `step` | Valor del pas actual (stepper). | number | `1` |
| `textError` | `text-error` | Text del missatge d'error que es mostra a l'usuari. | string | undefined |
| `textEtiquetaFirstInput` | `text-etiqueta-first-input` | Text visible al component. | string | undefined |
| `textEtiquetaSecondInput` | `text-etiqueta-second-input` | Text visible al component. | string | undefined |
| `textHelpSlider` | `text-help-slider` | Text visible al component. | string | undefined |
| `textInfoTooltip` | `text-info-tooltip` | Text que es mostra al tooltip associat. | string | undefined |
| `titleSlider` | `title-slider` | Títol del component. | string | undefined |
| `units` | `units` | Unitats de mesura del valor mostrat. | string | undefined |
| `value` | `value` | Valor actual del component. | string | undefined |

**Props que accepten JSON**

Propietats de l'array `value`:

| Propietat | Descripció | Obligatori | Tipus |
|---|---|---|---|
| `min` | Valor mínim. Aplicar només en mode double | Opcional | Number |
| `max` | Valor màxim. Aplicar en mode double i single | Obligatori | Number |

[discrepància: la descripció de la propietat `value` diu "En mode double escriure només max, en single min i max", però la taula de l'array `value` indica que `min` només s'aplica en mode double; a verificar]

**Variants (lloc)**

| Propietat | Defecte | Valors |
|---|---|---|
| `showTooltip` | `true` | `true` `false` |
| `showSteps` | `false` | `true` `false` |
| `mode` | `double` | `double` `single` |
| `centerLine` | `true` | `true` `false` |
| `middleValue` | `true` | `true` `false` |
| `showTextHelp` | `true` | `true` `false` |

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre / tipus | Origen |
|---|---|---|---|
| `valueChange` | Es llança cada cop que canvien els valors de l'slider (PDF: s'emet quan el valor del component canvia) | `value`. `CustomEvent<{ min: number; max: number; }>` | `slider-component` |
| `focusChanged` | Es llança quan l'input rep el focus (emet true) o quan el perd (emet false) | --- | `inputtext-component` |
| `hanlerdRef` | Emet la referència de l'input | Referència a l'element input | `inputtext-component` |
| `maxLengthReached` | Esdeveniment llançat en assolir el maxLength a l'input | maxLength | `inputtext-component` |
| `valueChange` | Es llança de manera immediata cada vegada que hi ha un canvi a l'inputtext | Value | `inputtext-component` |
| `valueChangeRetarded` | Es llança cada cop que hi ha un canvi a l'inputtext. S'emet al cap de 5 segons d'inactivitat | Value | `inputtext-component` |

**Depèn de:** `inputtext-component` ([Camp d'entrada](component-camp-d-entrada.md)), `tooltip-component` ([Indicador de funció](component-indicador-de-funcio.md)).

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<slider-component
  center-line="true"
  max="100"
  middle-value="true"
  min="0"
  mode="double"
  show-steps="true"
  show-text-help="true"
  show-tooltip="true"
  step="10"
  text-error="Valor no válido"
  text-etiqueta-first-input="Mínim"
  text-etiqueta-second-input="Màxim"
  text-help-slider="Text d'ajuda"
  text-info-tooltip="Text informatiu"
  title-slider="Selecciona tram d’ingressos"
  units="%"
  value='{"min":20,"max":60}'>
</slider-component>
```

**Exemple d'instància (PDF)**

```html
<slider-component
center-line=true
max=100
middle-value=true
min=0
mode='double'
show-steps=false
show-text-help=true
show-tooltip=true
step=1
text-error="texto-ejemplo"
text-etiqueta-first-input="texto-ejemplo"
text-etiqueta-second-input="texto-ejemplo"
text-help-slider="texto-ejemplo"
text-info-tooltip="texto-ejemplo"
title-slider="texto-ejemplo"
units="texto-ejemplo"
value="texto-ejemplo"
></slider-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 10.0.0 | 9.1.0 | 17 abril, 2026 | Disseny: es modifica l'alineació del frame input_slider (advanced) a la part superior |
| 8.4.0 | 9.1.0 | 6 febrer, 2026 | Desenvolupament: adaptacions d'accessibilitat pel que fa a mides de font extra gran i augment de pantalla |
| 8.4.0 | 7.0.0 | 5 desembre, 2025 | Disseny: s'elimina el marge esquerre de l'input numèric dret i s'afegeixen 4 px de marge dret a l'esquerra per evitar desalineacions quan queden col·locats verticalment |
| 8.3.0 | 7.0.0 | 14 novembre, 2025 | Disseny: s'afegeix un marge de 4 px entre els dos camps numèrics del control d'interval avançat (4 px a la dreta del primer camp i 4 px a l'esquerra del segon); s'elimina el tooltip; s'arrodoneix el focus Thumb; s'afegeix la línia central a la variant simple |
| 8.1.0 | 7.0.0 | 24 octubre, 2025 | Desenvolupament del component |
| 8.1.0 | - | 6 octubre, 2025 | Disseny i documentació del component |

## Vegeu també
- [Camp d'entrada](component-camp-d-entrada.md): component recurrentment utilitzat en formularis per a la recollida de dades.
- [Indicador de funció](component-indicador-de-funcio.md)
