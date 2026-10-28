# Botons (Buttons)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/36e8ca · Web component: `<button-component>` i `<dropdown-button-component>` (paquet core) · Font actualitzada el 2026-10-14 · Extret el 2026-10-28

## Què és i quan usar-lo
Element que permet a l'usuari dur a terme accions en una pàgina o pantalla.

Els botons són un element interactiu que facilita la realització d'accions directes i efectives que provoquen un canvi en el sistema, cosa que permet que els usuaris executin tasques de manera intuïtiva.

Casos més habituals:
- **Ressaltar i fomentar accions principals** en una interfície, com ara les crides a l'acció (CTA).
- **Enviament de formularis.**
- **Aprovació o declinació d'accions crucials.**

### Botó de càrrega
L'estat de càrrega s'utilitza per a **indicar que l'acció iniciada per l'usuari està en procés i encara no s'ha completat.** Exemples: enviament de formularis, càrrega de dades, transaccions.

### Botó desplegable
S'utilitza per agrupar diferents accions relacionades, sigui per falta d'espai o perquè les accions no són prou prioritàries per a posar-les a primer nivell.

### Botó d'icona
- Entorn del **ciutadà**: s'utilitzen per a accions en **maquetacions compactes**, com per exemple el format mòbil.
- Entorn del **treballador** (gestió interna): poden usar-se per a **accions que tinguin una icona estandarditzada**, com l'acció d'editar, copiar o enganxar, entre d'altres.

## Anatomia
Figma: Button [Icon Right = True, Change Icon Right = chevron-right, Icon Left = True, Change Icon Left = chevron-left, Text = Button, Type = Primary, State = Default, Size = Large, Background = Default]. Un botó pot tenir text, una icona a l'esquerra, una icona a la dreta i una insígnia (badge).

## Variants, tipus i estats

### Botó (amb text)

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Type | Primary / Secondary / Tertiary | Primary |
| State | Default / Hover / Focus / Selected / Loading | Default |
| Size | Large / Medium / Small | Medium |
| Icon | With / without icon | Without icon |
| Dark background | True / False | False |
| Color background | True / False | False |
| Show right icon | True / False | False |
| Change right icon | Icones | --- |
| Show left icon | True / False | False |
| Change left icon | Icones | --- |
| Show Badge | True / False | (sense valor per defecte a la font) |

Variants Figma del botó: Show Icon Right = True | False; Change Icon Right = chevron-right; Show Icon Left = True | False; Change Icon Left = chevron-left; Text = Button; Show Badge = True | False; Type = Primary | Secondary | Tertiary; Size = Large | Medium | Small; State = Default | Hover | Focus | Selected | Loading; Background = Default | Dark | Color. La font mostra aquestes variants en les subseccions Tipus, Estat, Mida i Color del fons.

### Botó d'icona (Icon button)

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Type | Primary / Secondary / Tertiary | Primary |
| Size | Large / Medium / Small | Large |
| State | Default / Hover / Focus / Selected / Loading | Default |
| Background | Default / Dark / Color | Default |
| Change icon | Icons | --- |
| Show Tooltip | True / False | False |
| Show Badge | True / False | False |

Variants Figma del botó d'icona: Change Icon = chevron-right; Show Tooltip = True | False; Show Badge = True | False; Type = Primary | Secondary | Tertiary; Size = Large | Medium | Small; State = Default | Hover | Focus | Selected | Loading; Background = Default | Dark | Color.

### Color
El color dels botons depèn del fons sobre el qual es col·loca:
- **Sobre fons blanc (per defecte):** s'utilitza el botó amb el color primari.
- **Sobre fons negre:** s'utilitza el botó en color blanc.
- **Sobre fons de color:** reservat únicament per fer servir amb els diferents tipus d'avisos. S'utilitza el botó en color negre i només s'aplica als secundaris i terciari.

## Mides i espaiats
En els botons, l'amplada depèn de la longitud del text, però té una **amplada mínima de 96 px** en les dues mides. Els botons d'icona tenen una mida fixa de **48x48 px** per la versió small i de **56x56 px** per la versió medium.

- **Gran (Large):** botó estàndard per a les accions principals i per a altres accions importants com enviament de formularis, registre o accions destructives.
- **Mitjana (Medium):** per a elements on l'espai és més limitat o es presenta molta informació, com en taules, llistes de dades, camps de filtre. També s'utilitza en accions que no siguin prioritàries o que s'usin amb menys freqüència.
- **Petita (Small):** dissenyada únicament per la versió d'icona. S'utilitza per a elements específics com el camp de cerca en capçalera.

## Comportament i interacció
- **Acció:** un clic desencadena una acció immediata o porta l'usuari a una nova pantalla o estat de l'aplicació.
- **Retroalimentació:** poden anar acompanyats de retroalimentació, com mostrar un missatge d'error o reflectir un canvi d'estat a la interfície.
- **No hi ha estat deshabilitat:** quan l'usuari no pot realitzar l'acció d'un botó per falta d'informació prèvia (per exemple en formularis), no s'usa l'estat desactivat (*disabled*) sinó el per defecte (*default*). Aquests botons van acompanyats de missatges d'error per guiar l'usuari.
- **Carregant:** l'estat carregant ha de ser de la mateixa amplada que l'estat per defecte. Si, quan està carregant, el text i l'indicador de càrrega ocupen més espai que el text en l'estat per defecte (i, per tant, el botó hauria de ser més ample perquè càpiga el contingut), s'usa la versió amb només l'indicador de càrrega.
- **Indicador de funció:** els botons d'icona disposen d'un indicador de funció (tooltip) per incloure l'acció en format text quan l'usuari hi passa el ratolí per sobre.
- **Insígnia:** els botons secundaris i terciaris inclouen l'opció de mostrar una insígnia per indicar novetats o elements aplicats, com en filtres aplicats.

### Adaptació responsiva
- **Botó de text:** el botó **escala** amb els punts de ruptura o disposició en escriptori fins als **480 px d'amplada**. Per a pantalles o disposicions en escriptori **superiors als 480 px** el botó **s'adapta al contingut.**
- **Botó desplegable:** a punt de tall petit (*small*, inferior a 480 px) s'obre mitjançant un panell emergent inferior. Per construir la versió small cal introduir la variant small del component [panell emergent (sheet)](component-panell-emergent.md) dins el component.

### Prototipat (Figma)
- **Botó desplegable:** el prototip es fa en dues pantalles, o bé amb l'acció "open overlay" dins del panell d'interacció.
- **Indicador de funció:** per activar-lo en prototip cal, primer, posar el botó en l'estat "Hover"; aleshores apareix al panell la booleana per activar-lo i es pot editar el text des de la instància al panell de propietats. Un cop modificat el text, es torna a posar el botó en l'estat "default" i ja està llest per al prototip.

## Bones pràctiques

### Jerarquia
- **FER:** Utilitza un únic botó primari en un mateix context per mantenir claredat en l'acció principal.
- **NO FER:** Evita fer ús de més d'un botó primari en un mateix context, ja que pot causar confusió.
- **FER:** Utilitza el botó secundari per a la segona acció més important; pot haver-hi més d'un botó secundari en un mateix context.
- **NO FER:** No utilitzis el botó secundari per a l'acció més important, això pot desorientar l'usuari sobre quina acció prioritzar.
- **FER:** Utilitza el botó terciari per a accions menys crítiques o addicionals que no requereixin una acció immediata.
- **NO FER:** No utilitzis el botó terciari per a les accions més importants.

### Text
- **FER:** Utilitza un màxim de 4 paraules (30 caràcters), assegurant-te que siguin simples i directes.
- **NO FER:** No facis servir moltes paraules ni termes complexos que puguin confondre l'usuari.
- **FER:** Fes ús de verbs d'acció que informin l'usuari sobre què farà el botó.
- **NO FER:** No facis ús de verbs que no són d'acció o d'altres tipologies de paraules com adverbis.
- **FER:** Utilitza un llenguatge específic per a la tasca.
- **NO FER:** No utilitzis un llenguatge poc específic per a la tasca.
- **FER:** La primera paraula del botó ha de tenir la primera lletra en majúscula.
- **NO FER:** No utilitzis majúscules a l'inici de cada paraula ni escriguis tot el text en majúscules.
- **FER:** Utilitza l'imperatiu de verbs en català i l'infinitiu de verbs en castellà.
- **NO FER:** No utilitzis l'infinitiu de verbs en català ni l'imperatiu de verbs en castellà.

### Icones
- **FER:** Utilitza una única icona per botó. Per defecte, s'utilitza la icona a l'esquerra del text amb algunes excepcions, com per exemple per indicar un procés.
- **NO FER:** No utilitzis dues icones dins un mateix botó.
- **FER:** Utilitza el botó d'icona únicament en casos en què la icona és un estàndard i es disposa de poc espai en pantalla (com en l'accés d'usuari en format mòbil), evitant usar-lo en l'entorn del ciutadà.
- **NO FER:** No facis ús del botó d'icona en l'entorn ciutadà quan hi ha suficient espai o bé quan la icona no és estàndard.

### Botó desplegable
- **FER:** Utilitza el botó desplegable per incloure accions relacionades.
- **NO FER:** No utilitzis desplegables amb accions en les quals es mostri únicament una icona. Utilitza sempre text amb icona (opcional).
- **NO FER:** No utilitzis un botó desplegable per incloure una única acció. Inclou mínim dues.

### Accions destructives
- **FER:** Quan un botó desencadena una acció destructiva permanent (com eliminar un compte), inclou una forma d'assegurar que l'usuari està segur del que fa (en diàlegs concrets) o proporciona l'opció de desfer l'acció (accions recurrents).

### Mides
- **FER:** Utilitza la mida Small únicament en casos específics com la capçalera.
- **NO FER:** No utilitzis la mida Small per a casos no especificats en la documentació.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG) que cita el component:
- **1.4.1 Ús del color (A):** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per diferenciar els estats s'inclouen subratllats i es juga amb la presència de farciment i el gruix de la vora. En el botó terciari sense icona s'ha incorporat el subratllat com a element gràfic addicional per reforçar-ne la identificació com a element interactiu i evitar que depengui únicament del color. (https://www.w3.org/Translations/WCAG22-ca/#use-of-color · https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **1.4.3 Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. (https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum · https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **1.4.4 Canvia la mida del text (AA):** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. (https://www.w3.org/Translations/WCAG22-ca/#resize-text · https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **1.4.10 Redistribució (AA):** els botons han de ser escalables sense pèrdua de funcionalitat o claredat amb un zoom de fins al 200 %. Si el botó té una amplada major que el seu contenidor (perquè és massa llarg o s'ha aplicat l'augment de text), el contingut del botó salta de línia. Sempre que hi hagi espai, el botó ocupa tot l'espai disponible i, si hi ha altres elements a la mateixa fila, aquests es desplacen a una segona línia. (https://www.w3.org/Translations/WCAG22-ca/#reflow · https://www.w3.org/WAI/WCAG22/Understanding/reflow)
- **1.4.11 Contrast d'elements no textuals (AA):** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. (https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast · https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **2.1.1 Teclat (A):** tota la funcionalitat del contingut (navegar pels diferents botons) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. (https://www.w3.org/Translations/WCAG22-ca/#keyboard · https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **2.4.7 Focus visible (AA):** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. (https://www.w3.org/Translations/WCAG22-ca/#focus-visible · https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- **3.3.1 Identificació d'errors (A):** no s'utilitza l'estat deshabilitat per als botons, perquè l'usuari hi pugui interaccionar encara que falti informació o alguna sigui errònia; així es pot indicar l'error comès. (https://www.w3.org/Translations/WCAG22-ca/#error-identification · https://www.w3.org/WAI/WCAG22/Understanding/error-identification)

## Implementació (component web)

### `<button-component>`
Paquet: core.

**Propietats**

Taula de la pàgina del lloc (amb obligatorietat):

| Propietat | Atribut HTML | Descripció | Obligatorietat | Tipus |
|---|---|---|---|---|
| `aria` | `aria` | Atribut aria-label per al botó | Opcional | string |
| `ariaDescribedby` | `aria-describedby` | Atribut aria-describedby per al botó | Opcional | string |
| `badge` | `badge` | Habilitar o deshabilitar badge (no disponible en tots els tipus de botons, veure documentació de disseny) | Opcional | boolean |
| `classNameButton` | `class-name-button` | Selecciona si el botó és de tipus primari, secundari o terciari. | Obligatori | string |
| `classNameIcon` | `class-name-icon` | Nom de la icona de Bootstrap a mostrar, si no s'utilitza un xebró (*chevron*). Usa les icones de la [biblioteca d'icones de Bootstrap](https://icons.getbootstrap.com/). | Opcional | string |
| `customId` | `custom-id` | Identificador únic per al botó, per a proves o personalització. | Opcional | string |
| `isSpinner` | `is-spinner` | Indica si s'ha de mostrar un indicador de càrrega. | Opcional | boolean |
| `leftIcon` | `left-icon` | Activa la icona a l'esquerra del botó, si no s'utilitza un xebró (*chevron*). | Opcional | boolean |
| `leftIconChevron` | `left-icon-chevron` | Mostra o amaga la icona del xebró (*chevron*) a l'esquerra del botó. | Opcional | boolean |
| `modeColorButton` | `mode-color-button` | Defineix el color del botó segons l'estil i tema. | Opcional | string |
| `placementTooltip` | `placement-tooltip` | Posició del tooltip | Opcional | string |
| `rightIcon` | `right-icon` | Activa la icona a la dreta del botó, si no s'utilitza un xebró (*chevron*). | Opcional | boolean |
| `rightIconChevron` | `right-icon-chevron` | Mostra o amaga la icona del xebró (*chevron*) a la dreta del botó. | Opcional | boolean |
| `roleButton` | `role-button` | Definir l'atribut del rol del botó. | Opcional | string |
| `sizeButton` | `size-button` | Defineix la mida del botó. | Opcional | string |
| `text` | `text` | Text que apareix al botó. | Obligatori | string |
| `textBadge` | `text-badge` | Text del badge | Opcional | string |
| `textTooltip` | `text-tooltip` | Text tooltip que es mostra quan es passa el cursor (hover) sobre el botó sense text, només d'icona | Opcional | string |
| `typeButton` | `type-button` | Tipus d'acció del botó: '*button*' (predeterminat), '*submit*' per enviar formulari, o '*reset*' per reiniciar. | Opcional | string |

Valors per defecte i matisos segons el PDF (v12.0.0):

| Propietat | Atribut HTML | Descripció (PDF) | Tipus | Per defecte |
|---|---|---|---|---|
| `aria` | `aria` | Atributs ARIA per a accessibilitat. Accepta un string JSON amb claus `aria-*`. | string | undefined |
| `ariaDescribedby` | `aria-describedby` | ID de l'element que descriu aquest component (aria-describedby). | string | undefined |
| `badge` | `badge` | Mostra el badge decoratiu. | boolean | false |
| `classNameButton` | `class-name-button` | Variant d'estil CSS del component. Opcions: `btn-primary`, `btn-secundary`, `btn-tertiary`, `icn-btn-primary`, `icn-btn-secundary`, `icn-btn-tertiary`. | string | `btn-primary` |
| `classNameIcon` | `class-name-icon` | Classe de la icona Bootstrap Icons (p. ex. `bi-check`). | string | undefined |
| `customId` | `custom-id` | Identificador HTML personalitzat de l'element. | string | undefined |
| `isSpinner` | `is-spinner` | Mostra l'indicador de càrrega. | boolean | undefined |
| `leftIcon` | `left-icon` | Mostra la icona a l'esquerra del text. | boolean | false |
| `leftIconChevron` | `left-icon-chevron` | Mostra la icona a l'esquerra del text. | boolean | undefined |
| `modeColorButton` | `mode-color-button` | Esquema de color i contrast del component. Opcions: `mode-color-primary-dark`, `mode-color-primary-grey`, `mode-color-primary-light`, `mode-color-secundary-dark`, `mode-color-secundary-grey`, `mode-color-secundary-light`, `mode-color-tertiary-dark`, `mode-color-tertiary-grey`, `mode-color-tertiary-light`. | string | `mode-color-primary-light` |
| `placementTooltip` | `placement-tooltip` | Text del tooltip associat a l'element. Opcions: `bottom`, `left`, `right`, `top`. | string | undefined |
| `rightIcon` | `right-icon` | Mostra la icona a la dreta del text. | boolean | false |
| `rightIconChevron` | `right-icon-chevron` | Mostra la icona a la dreta del text. | boolean | undefined |
| `roleButton` | `role-button` | Rol ARIA del botó. | string | undefined |
| `sizeButton` | `size-button` | Variant de mida del botó. Opcions: `btn-size-L`, `btn-size-M`, `btn-size-S`, `icn-btn-size-L`, `icn-btn-size-M`, `icn-btn-size-S`. | string | `btn-size-L` |
| `text` | `text` | Text principal visible del component. | string | undefined |
| `textBadge` | `text-badge` | Text que apareix dins del badge. | string | undefined |
| `textTooltip` | `text-tooltip` | Text que es mostra al tooltip associat. | string | undefined |
| `typeButton` | `type-button` | Tipus HTML natiu del botó (`button`, `submit` o `reset`). Opcions: `button`, `reset`, `submit`. | string | `button` |

[discrepància: la descripció de `placementTooltip` al PDF diu "Text del tooltip associat a l'element" amb opcions de posició (bottom, left, right, top); el lloc diu "Posició del tooltip"]

**Variants (lloc)**

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `classNameButton` | `btn-primary` `btn-secundary` `btn-tertiary` `icn-btn-primary` `icn-btn-secundary` `icn-btn-tertiary` | `btn-primary` |
| `modeColorButton` | `mode-color-primary-dark` `mode-color-primary-grey` `mode-color-primary-light` `mode-color-secundary-dark` `mode-color-secundary-grey` `mode-color-secundary-light` `mode-color-tertiary-dark` `mode-color-tertiary-grey` `mode-color-tertiary-light` | `mode-color-primary-light` |
| `placementTooltip` | `top` `bottom` `left` `right` | - |
| `sizeButton` | `btn-size-L` `btn-size-M` `btn-size-S` `icn-btn-size-L` `icn-btn-size-M` `icn-btn-size-S` | `btn-size-L` |
| `typeButton` | `button` `reset` `submit` | `button` |

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre | Origen | Tipus (PDF) |
|---|---|---|---|---|
| `blurButton` | Es llança cada cop que es treu el focus en un botó. | - | `button-component` | `CustomEvent<void>` |
| `focusButton` | Es llança cada cop que es fa focus en un botó. | - | `button-component` | `CustomEvent<void>` |
| `handlerClick` | Es llança cada cop que es fa clic en un botó i com a paràmetre conté les dades de l'esdeveniment. | id | `button-component` | `CustomEvent<HandlerClickDetail>` |

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<button-component 
  class-name-button="btn-primary"
  class-name-icon="" 
  size-button="btn-size-L"
  mode-color-button="mode-color-primary-light" 
  text="Botó"
  aria=""
  aria-describedby=""
  left-icon-chevron="true" 
  right-icon-chevron="false"
  left-icon=false 
  right-icon=false
  text-tooltip=""
  is-spinner=false
  custom-id=""
  type-button="button"
  role-button=""
  badge="true"
  text-badge="12">
</button-component>
```

**Exemple d'instància (PDF)**

```html
<button-component
aria="texto-ejemplo"
aria-describedby="texto-ejemplo"
badge=false
class-name-button='btn-primary'
class-name-icon="texto-ejemplo"
custom-id="texto-ejemplo"
is-spinner=false
left-icon=false
left-icon-chevron=false
mode-color-button='mode-color-primary-light'
placement-tooltip="bottom"
right-icon=false
right-icon-chevron=false
role-button="texto-ejemplo"
size-button='btn-size-L'
text="texto-ejemplo"
text-badge="texto-ejemplo"
text-tooltip="texto-ejemplo"
type-button='button'
></button-component>
```

**Comportament (lloc)**
- `leftIconChevron` i `rightIconChevron` controlen la visibilitat de les icones del xebró (*chevron*) al costat esquerre i dret.
- Utilitza `leftIcon` amb `classNameIcon` per definir una icona específica.
- Per canviar l'estil del botó entre primari, secundari o terciari, ajusta `classNameButton` i `modeColorButton`.

**Depèn de:** `tooltip-component` (lloc: també `spinner-component`, `badge-component`, `tooltip-component`).

**Utilitzat per (PDF):** `advanced-image-component`, `back-to-bottom-button-component`, `chat-header-component`, `chat-input-component`, `chat-message-component`, `dropdown-button-component`, `floating-chat-container-component`, `modal-component`, `side-chat-button-component`.

**S'utilitza a (lloc):** `callout-component`, `file-uploader-component`, `footer-component`, `horizontal-menu-component`, `pagination-component`, `searchfield-component`, `toast-component`, `dynamic-table-component`, `card-hightlight-component`, `card-navigation-component`, `date-picker-component`, `dropdown-menu-component`, `backoffice-subheader-component`, `modal-component`, `show-more-component`, `side-menu-component`, `summary-list-component`, `empty-state-component`, `timeline-component`, `button-group-component`, `calendar-component`, `dropdown-button-component`, `sheet-component`, `content-tree-component`, `advanced-image-component`, `back-to-top-component`, `banner-component`, `carousel-component`, `chip-component`, `dropdown-component`, `header-public-component`, `header-component`, `glossary-component`, `back-to-bottom-button-component`.

**Dependències (lloc):** `spinner-component` ([Indicador de càrrega](component-indicador-de-carrega.md)), `badge-component` ([Insígnia](component-insignia.md)), `tooltip-component` ([Indicador de funció](component-indicador-de-funcio.md)).

### `<dropdown-button-component>`
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Obligatorietat | Tipus | Per defecte (PDF) |
|---|---|---|---|---|---|
| `classNameButton` | `class-name-button` | Selecciona si el botó és de tipus primari, secundari o terciari. (PDF: variant d'estil CSS; opcions `btn-primary`, `btn-secundary`, `btn-tertiary`, `icn-btn-primary`, `icn-btn-secundary`, `icn-btn-tertiary`) | Obligatori | string | `btn-primary` |
| `classNameIcon` | `class-name-icon` | Classe Bootstrap de la icona del botó (PDF: classe de la icona Bootstrap Icons, p. ex. `bi-check`) | Opcional | string | undefined |
| `customId` | `custom-id` | Identificador únic per al botó, per a proves o personalització. | Opcional | string | undefined |
| `leftIcon` | `left-icon` | Activa la icona a l'esquerra del botó, si no s'utilitza un xebró (*chevron*). | Opcional | boolean | false |
| `modeColorButton` | `mode-color-button` | Defineix el color del botó segons l'estil i tema. | Opcional | string | `mode-color-primary-light` |
| `options` | `options` | Opcions del desplegable (PDF: accepta array d'objectes o string JSON) | Obligatori | string (array) · PDF: `DropdownOption[]` o `string` | (no definit) |
| `rightIcon` | `right-icon` | Activa la icona a la dreta del botó, si no s'utilitza un xebró (*chevron*). | Opcional | boolean | false |
| `sizeButton` | `size-button` | Defineix la mida del botó. | Opcional | string | `btn-size-M` |
| `text` | `text` | Text que apareix al botó. | Obligatori | string | undefined |
| `textTooltip` | `text-tooltip` | Text tooltip que es mostra quan es passa el cursor (*hover*) sobre el botó icona. | Opcional | string | undefined |
| `titleSheetText` | `title-sheet-text` | Títol del sheet a mobile (PDF: "Títol del component") | Opcional | string | undefined |

**Variants**

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `classNameButton` | `btn-primary` `btn-secundary` `btn-tertiary` `icn-btn-primary` `icn-btn-secundary` `icn-btn-tertiary` | `btn-primary` |
| `modeColorButton` | `mode-color-primary-dark` `mode-color-primary-light` `mode-color-primary-grey` `mode-color-secundary-dark` `mode-color-secundary-grey` `mode-color-secundary-light` `mode-color-tertiary-dark` `mode-color-tertiary-grey` `mode-color-tertiary-light` | `mode-color-primary-light` |
| `sizeButton` | `btn-size-M` `btn-size-S` `icn-btn-size-M` `icn-btn-size-S` | `btn-size-M` |

**Props que accepten JSON:** `options` — string JSON (array d'objectes) amb l'estructura `DropdownOption`:

| Clau | Tipus | Requerida |
|---|---|---|
| `label` | string | Sí |
| `id` | string | Sí |
| `icon` | string | Sí |

```json
[
{
"label": "texto-ejemplo",
"id": "texto-ejemplo",
"icon": "texto-ejemplo"
}
]
```

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre | Origen | Tipus (PDF) |
|---|---|---|---|---|
| `optionSelected` | S'emet en fer clic sobre una opció | id de l'opció seleccionada | `dropdown-button-component` | `CustomEvent<DropdownOption>` |
| `handlerClick` | Es llança cada cop que es fa clic en un botó i com a paràmetre conté les dades de l'esdeveniment | id | `button-component` | |
| `focusButton` | Es llança cada cop que es fa focus en un botó | - | `button-component` | |
| `blurButton` | Es llança cada cop que es treu el focus en un botó | - | `button-component` | |

El PDF només documenta `optionSelected` per a aquest component; els altres tres venen de `button-component`.

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<dropdown-button-component 
    class-name-button="btn-primary" 
    class-name-icon="bi-three-dots-vertical"
    size-button="btn-size-S" 
    mode-color-button="mode-color-primary-light" 
    text="Button"
    title-sheet-text="Title sheet"
    left-icon="false"
    right-icon="true"
    text-tooltip="" 
    custom-id="dropdown1"
    options='[
    { "label": "Opción 1", "id": "1", "icon": "bi-copy" },
    { "label": "Opción 2", "id": "2", "icon": "bi-copy" },
    { "label": "Opción 3", "id": "3", "icon": "bi-copy" }
  ]'></dropdown-button-component>
```

**Exemple d'instància (PDF)**

```html
<dropdown-button-component
class-name-button='btn-primary'
class-name-icon="texto-ejemplo"
custom-id="texto-ejemplo"
left-icon=false
mode-color-button='mode-color-primary-light'
options=[]
right-icon=false
size-button='btn-size-M'
text="texto-ejemplo"
text-tooltip="texto-ejemplo"
title-sheet-text="texto-ejemplo"
></dropdown-button-component>
```

Exemple amb props JSON (PDF):

```html
<dropdown-button-component
options='[{"label":"texto-ejemplo","id":"texto-ejemplo","icon":"texto-ejemplo"}]'
></dropdown-button-component>
```

**Depèn de:** `button-component`.

**Utilitzat per:** `chat-input-component` (PDF); `dynamic-table-component` ([Taules dinàmiques](component-taules-dinamiques.md)) (lloc).

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.4.0 | 12.1.2 | 5 octubre, 2026 | Desenvolupament: s'afegeix un element gràfic al botó terciari |
| 12.4.0 | 12.0.3 | 09 setembre, 2026 | Disseny: s'ha afegit un element gràfic als botons terciaris per reforçar-ne la diferenciació i millorar-ne l'accessibilitat. |
| 12.0.0 | 12.0.3 | 4 setembre, 2026 | Desenvolupament: (botó desplegable) s'aplica un z-index elevat. |
| 12.3.0 | 11.0.0 | 31 juliol, 2026 | Disseny: s'apliquen les variables de color de nou als botons i botons amb icona. |
| 12.0.0 | 11.0.0 | 19 juny, 2026 | Desenvolupament: zona morta en el breakpoint de 480px corregida |
| 12.0.0 | 10.1.0 | 29 maig, 2026 | Disseny: es crea la variant per punt de tall small de l'Actions menu. Desenvolupament: s'afegeix la property placementTooltip; botó desplegable: correccions quant al comportament del mode focus |
| 8.0.0 | 9.4.0 | 17 abril, 2026 | Desenvolupament. Botó: s'ha arreglat la vista del botó terciari quan l'spinner està actiu i s'ha adaptat a la nova propietat de l'spinner `colorSpinner`. Botó desplegable: s'ha corregit l'alineament del desplegable quan no cap a la pantalla; s'ha afegit la propietat `classNameIcon`. |
| 8.0.0 | 9.3.0 | 20 març, 2026 | Desenvolupament: s'arreglen estils del mode actiu del botó secundari en mida L i S; s'eliminen elements HTML buits renderitzats quan no s'utilitzen |
| 8.0.0 | 9.1.0 | 6 febrer, 2026 | Desenvolupament: es fan canvis a l'operativa del mode focus al botó desplegable |
| 8.0.0 | 8.5.0 | 5 desembre, 2025 | Desenvolupament: es canvia el nom de la property role a roleButton. S'hi afegeix min-height i min-width |
| 8.1.0 | 7.0.0 | 24 octubre, 2025 | Desenvolupament: resolució de problemes |
| 8.1.0 | 6.2.1 | 6 octubre, 2025 | Disseny: s'afegeix mida small al component action menu per al botó desplegable. Desenvolupament: nova propietat afegida o eliminada |
| 8.0.0 | 6.1.0 | 12 setembre 2025 | Disseny: s'elimina l'alçada fixa i es posa en Hug perquè es puguin adaptar a augments de text (accessibilitat). Desenvolupament: nova propietat afegida |
| 7.0.0 | 6.0.1 | 28 juliol, 2025 | Desenvolupament de l'evolutiu |
| 6.0.0 | 6.0.0 | 8 juliol, 2025 | Disseny: s'afegeix l'opció de mostrar tooltip en fer el hover sobre el botó d'icona. S'afegeix l'opció de mostrar badge en fer el hover sobre el botó de text i el botó d'icona secundari i terciari dels estils depenent del fons. |
| 5.0.0 | 6.0.0 | 3 juliol, 2025 | Desenvolupament del component botó desplegable. Resolució dels bugs del component botó |
| 5.0.0 | 4.0.1 | 10 juny, 2025 | Disseny: es dissenya el panell d'accions per al botó desplegable. Es dissenya la previsualització del botó desplegable. |
| 4.0.0 | 4.0.1 | 19 maig, 2025 | Desenvolupament: resolució de problemes |
| 2.3.0 | 3.0.0 | 28 abril, 2025 | Desenvolupament: resolució de problemes |
| 2.3.0 | 2.0.0 | 7 març, 2025 | Desenvolupament: resolució de problemes. |
| 2.3.0 | 1.1.0 | 17 febrer, 2025 | Desenvolupament: resolució de problemes. |
| 2.3.0 | 1.0.0 | 31 gener, 2025 | Desenvolupament: s'afegeix la mida small. |
| 2.2.0 | 0.1.1 | 20 desembre, 2025 | Disseny: s'afegeix la mida small (40 px d'alçada) al botó. Es modifica la distància del focus al botó, passa de 4 px a 2 px. |
| 2.1.0 | 0.1.1 | 04 desembre, 2024 | Disseny: s'afegeix mida small al botó d'icona. |
| 2.0.0 | 0.1.0 | 02 desembre, 2024 | Sense canvis. |
| 1.1.0 | 0.1.0 | 22 novembre, 2024 | Sense canvis. |
| 1.1.0 | 0.0.4 | 18 novembre, 2024 | Sense canvis. |
| 1.0.0 | 0.0.3 | 1 novembre, 2024 | Disseny, desenvolupament i documentació del component. |

## Vegeu també
- [Enllaços](component-enllacos.md): per facilitar la navegació entre parts del contingut o funcionalitats.
- [Panell emergent](component-panell-emergent.md), [Indicador de càrrega](component-indicador-de-carrega.md), [Insígnia](component-insignia.md), [Indicador de funció](component-indicador-de-funcio.md), [Grup de botons](component-grup-de-botons.md).
