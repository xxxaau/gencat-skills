# Descripció emergent (Popover)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/311ac2 · Web component: `<popover-component>` (paquet core); el capítol PDF `<tooltip-component>` (paquet core) també s'assigna a aquest fitxer · Font actualitzada el 2026-09-30 · Extret el 2026-10-28

## Què és i quan usar-lo
Petit contenidor superposat que mostra informació contextual. Apareix quan l'usuari interactua amb un element de la pàgina en clicar i roman obert fins que es tanquen.

A diferència de l'indicador de funció, aquest pot incloure elements interactius com botons o enllaços.

Es fa servir en els casos següents:
- Per **mostrar informació que ajudi a aclarir o entendre un concepte** o element de la interfície sense perdre el context o la seva posició actual. Inclou informació més complexa que l'indicador de funció no permet.
- Per **proporcionar informació addicional** (i més complexa que l'indicador de funció) relacionada amb un element de la pàgina.

## Quan NO usar-lo / alternatives
No es farà servir el component en les situacions següents:
- Com a **substitució de menús.**
- Per a **grans quantitats d'informació.**
- Per **introduir dades.**
- Com a **substitució de l'[indicador de funció](component-indicador-de-funcio.md).** Això inclou:
  - Per **ajudar els usuaris a comprendre el significat o el propòsit d'un element** de la interfície que no té etiqueta, com per exemple icones o botons.
  - Per **mostrar la versió completa d'un text** truncat.
  - Per **mostrar el text alternatiu d'una imatge.**
  - Per **afegir informació contextual** (no essencial) a un element que necessita més context, especialment en aquells casos que hi hagi poc espai per incloure-la en línia (en aquests casos s'utilitzaria la icona de l'indicador de funció).
- Com a **substitució de la [modal](component-modals.md).** Això inclou:
  - **Notificar l'usuari sobre un error** urgent.
  - **Demanar una informació.** Aquesta informació és necessària per continuar amb la tasca. En aquest cas, s'inclouen camps de text o selectors.
  - **Mostrar informació crítica** que requereix una tasca, decisió o reconeixement específic de l'usuari.
  - **Confirmar la decisió** d'un usuari en relació amb una acció. Per a tasques curtes i poc freqüents, com ara tasques d'edició o gestió.

## Anatomia
Figma: Popover [Show text = True, Show footer = True, L-Center = True, T-Center = True, Show image = True, B-Center = True, Show grid = True, R-Center = True, Type = Informational]; Popover [Show footer = True, Show aditional content = True, Show text = True, Show scroll bar = False, Pointer alignment = Bottom]; Popover_HelpButton [Size = Medium, State = Default].

## Variants, tipus i estats

### Descripció emergent

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Extra Large - Medium / Small | Extra Large - Medium |
| Pointer aligment | Right / Left / Bottom / Top | Bottom |

Subseccions de la font: Punt de tall i Alineació del punter (variants Figma Popover [Show footer = True, Show aditional content = True, Show text = True, Show scroll bar = False, Pointer alignment = Bottom]).

### Botó d'ajuda
Per a camps de formulari, s'utilitzarà aquest element per activar la descripció emergent.

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Default / Hover / Pressed / Focus | Default |

Variant Figma: Popover_HelpButton [Size = Medium, State = Default].

## Comportament i interacció
### Adaptació responsiva
En dispositius mòbils, la descripció emergent s'obre en format panell emergent. Per a construir la versió small cal introduir la variant small del component dins el component [panell emergent (sheet)](component-panell-emergent.md).

## Bones pràctiques

**Ubicació consistent**
- **FER:** Assegura't que la descripció emergent es desplega a prop de l'element amb què està relacionat, però sense arribar a tapar-lo. Això ajuda a mantenir la relació clara i evita confusió.

**Claredat**
- **FER:** Els títols han de ser tan curts com sigui possible i rellevants segons el context.
- **NO FER:** Evita sobrecarregar la finestra emergent contextual amb informació innecessària. Només s'utilitzarà un quadre de text per cada finestra emergent amb una extensió màxima de 120 caràcters. El contingut que aparegui dins ha de ser directe i rellevant.

**Fletxes**
- **FER:** Utilitza, en la versió d'escriptori, fletxes o indicadors visuals per assenyalar la relació entre la descripció emergent i l'element activador. Això ajuda els usuaris a entendre la connexió entre tots dos.

**Quantitat**
- **NO FER:** Evita mostrar més d'una finestra emergent contextual a la vegada. Per millorar la usabilitat, si apareix una nova finestra emergent mentre n'hi ha una d'oberta, la primera es tancarà automàticament.

**Imatges**
- **NO FER:** Es recomana no usar imatges si no és estrictament necessari, però en el cas de ser-ho es limitarà el seu ús a una única imatge.
- **NO FER:** No utilitzis imatges decoratives.

## Accessibilitat

### Pautes d'accessibilitat del contingut web (WCAG)
- **Orientació (AA):** el contingut de l'àrea de text s'adapta a les diferents orientacions de la pantalla, com ara vertical o horitzontal, cosa que permet visualitzar el contingut. [1.3.4 Orientació - CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Teclat (A):** tota la funcionalitat del contingut (navegar pels diferents botons) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [2.1.1 Teclat - CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Sense trampa de teclat (A):** si el focus del teclat es pot moure a un component de la pàgina mitjançant una interfície de teclat, llavors el focus es pot allunyar d'aquest component utilitzant només una interfície de teclat. Amb la tecla "Esc" l'usuari pot sortir de la descripció emergent. [2.1.2 Sense trampa de teclat - CAT](https://www.w3.org/Translations/WCAG22-ca/#no-keyboard-trap) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/no-keyboard-trap)
- **Focus visible (AA):** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [2.4.7 Focus visible - CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- **Ordre del focus (A):** les modals presenten un ordre lògic del focus dels elements interns per facilitar la navegació per teclat o altres dispositius d'entrada. L'ordre ha de seguir el flux de la informació o les tasques que s'estan presentant. L'ordre ha de ser el següent: 1. Primer element interactiu al cos de la modal començant per la part superior esquerra. 2. Desplaçament d'esquerra a dreta i de dalt a baix per la resta dels elements del cos. 3. Acció primària. 4. Acció secundària. 5. Acció terciària. 6. Icona de tancament. [2.4.3 Ordre del focus - CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-order) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-order)
- **Focus visible (AA)** (repetit a la font): la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle.
- **Focus no ocult (AA):** en la variant per a dispositius mòbils (panell emergent), el focus ha de quedar atrapat dins del panell mentre és obert. En tancar-se, el focus ha de tornar al botó d'ajuda que el va activar. La descripció emergent no pot ocultar cap element que tingui el focus de teclat. Aquesta consideració és especialment rellevant en dispositius mòbils i tauletes amb zoom de pantalla activat. [2.4.11 Focus no ocult - CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-not-obscured-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-not-obscured-minimum)

## Implementació (component web)

### `<popover-component>`

Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat (lloc) |
|---|---|---|---|---|---|
| `contextualImageUrl` | `contextual-image-url` | URL de la imatge mostrada a la descripció emergent contextual | string | `undefined` | Opcional |
| `description` | `description` | Descripció que es mostra al cos de la descripció emergent | string | `undefined` | Opcional |
| `imgDescription` | `img-description` | Descripció de la imatge contextual, utilitzada com a atribut `alt` | string | `undefined` | Opcional |
| `linkModePopover` | `link-mode-popover` | Indica de quin tipus serà l'enllaç que inclou el component. Opcions: `external`, `internal` | string | `internal` | Opcional |
| `linkTextPopover` | `link-text-popover` | Text de l'enllaç que apareix al peu de la descripció emergent | string | `undefined` | Opcional |
| `padding` | `padding` | Espai intern (padding) utilitzat per evitar desbordaments de la descripció emergent en mides de pantalla inferiors a 960px | number | `undefined` | Opcional |
| `popoverTitle` | `popover-title` | Títol de la descripció emergent que es mostra a la capçalera | string | `Popover title` | Opcional |
| `sizeTextOpen` | `size-text-open` | Grandària del text que obre el popover. Opcions: `medium`, `small` | string | `medium` | Opcional |
| `textItems` | `text-items` | Elements de text en format JSON que es mostren a la descripció emergent informativa | string (JSON) | `[]` | Opcional |
| `textOpen` | `text-open` | Text que en fer-hi clic obre el popover | string | `undefined` | Obligatori |
| `textTooltipClosePopover` | `text-tooltip-close-popover` | Text del tooltip que es mostra en passar el cursor (hover) sobre el botó de tancar descripció emergent | string | `Tancar descripció emergent` | Opcional |
| `version` | `version` | Tipus de descripció emergent: informacional o contextual. Opcions: `contextual`, `informational` | string | `informational` | Opcional |

**Variants**

| Propietat | Defecte | Valors |
|---|---|---|
| `mode` | - | `internal`, `external` |
| `sizeTextOpen` | `medium` | `small`, `medium` |
| `type` | - | `icon`, `text` |
| `version` | `informational` | `informational`, `contextual` |

**Props que accepten JSON.** `textItems` (array d'objectes):

| Propietat | Atribut | Descripció | Tipus | Obligatorietat |
|---|---|---|---|---|
| `iconClass` | `icon-class` | Si el `type` és `icon`, permet introduir la classe de la icona de bootstrap que es vulgui | string | Opcional |
| `isLink` | `is-link` | Permet indicar si l'ítem és un enllaç o no, vàlid per a `type` `icon` i `text` | Boolean | Opcional |
| `mode` | `mode` | Indica si el mode de l'enllaç és `external` o `internal` | string | Opcional |
| `prefix` | `prefix` | Si `type` és `text`, es refereix al text previ al text principal de l'ítem | string | Opcional |
| `text` | `text` | Text principal de l'ítem, vàlid per a `type` `icon` i `text` | string | Obligatori |
| `textUrl` | `text-url` | Indica el text o l'URL que es mostrarà com a enllaç dins del component | string | Opcional |
| `type` | `type` | Tipus d'ítem, pot ser `icon` o `text` | string | Obligatori |

**Mètodes públics**

| Mètode | Descripció | Paràmetre |
|---|---|---|
| `togglePopoverVisibility()` | Alterna l'estat de visibilitat del popover entre obert i tancat | - |

**Esdeveniments (lloc)**

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `blurButton` | Esdeveniment llançat en treure el focus d'algun dels botons | - | `button-component` |
| `focusButton` | Esdeveniment llançat en fer focus sobre algun dels botons | - | `button-component` |
| `handlerClick` | Esdeveniment llançat en fer clic en algun botó | `id` | `button-component` |
| `blurLink` | Es llança cada cop que es treu el focus de l'enllaç | - | `link-component` |
| `focusLink` | Esdeveniment llançat en fer focus sobre l'enllaç | - | `link-component` |
| `linkEmit` | Esdeveniment llançat en fer clic sobre l'enllaç | `id` | `link-component` |
| `closeSheet` | Esdeveniment emès en tancar-se el panell emergent | closed: `true` | `sheet-component` |

[discrepància: el lloc llista aquests esdeveniments heretats dels components fills; el PDF diu «Sin eventos declarados» per a `popover-component`]

**Depèn de:** `button-component` ([Botons](component-botons.md)), `link-component` ([Enllaços](component-enllacos.md)), `sheet-component` ([Panell emergent](component-panell-emergent.md)).

**Utilitzat per / en:** `backoffice-subheader-component` ([Capçalera per aplicacions internes](component-capcalera-per-aplicacions-internes.md)), `dropdown-component` ([Desplegable](component-desplegable.md)), `file-uploader-component` ([Carregador d'arxius](component-carregador-d-arxius.md)), `inputtext-component` ([Camp d'entrada](component-camp-d-entrada.md)), `searchfield-component` ([Camp de cerca](component-camp-de-cerca.md)), `textarea-component` ([Àrea de text](component-area-de-text.md)).

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<popover-component 
  text-open="Ajuda" 
  padding="20px" 
  size-text-open="small" 
  popover-title="Exemple de títol"
  description="Aquest és un exemple de descripció per al popover." 
  version="informational"
  contextual-image-url="/assets/photos/img_1.png" 
  img-description="Imatge descriptiva"
  link-text-popover="Més informació" 
  link-mode-popover="external"
  text-tooltip-close-popover="Tancar descripció emergent" 
  text-items='[
    { "type": "icon", "iconClass": "bi-info-circle", "prefix": "Ítem 1:", "text": "Aquest és el primer ítem", "isLink": false, "mode": "internal" },
    { "type": "icon", "iconClass": "bi-info-circle", "prefix": "Ítem 2:", "text": "Aquest és el segon ítem", "isLink": true, "mode": "internal" },
    { "type": "icon", "iconClass": "bi-info-circle", "prefix": "Ítem 3:", "text": "Aquest és el tercer ítem", "isLink": true, "mode": "internal" }
  ]'
></popover-component>
```

**Exemple d'instància (PDF)**

```html
<popover-component
contextual-image-url="texto-ejemplo"
description="texto-ejemplo"
img-description="texto-ejemplo"
link-mode-popover='internal'
link-text-popover="texto-ejemplo"
padding=0
popover-title='Popover title'
size-text-open='medium'
text-items='[]'
text-open="texto-ejemplo"
text-tooltip-close-popover='Tancar descripció emergent'
version='informational'
></popover-component>
```

### `<tooltip-component>`

Paquet: core. (Capítol de l'API assignat a aquest fitxer; no apareix a la pàgina del lloc de la descripció emergent. Vegeu [Indicador de funció](component-indicador-de-funcio.md).)

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte |
|---|---|---|---|---|
| `message` | `message` | Contingut del missatge | string | `undefined` |
| `placement` | `placement` | Posició de l'element flotant respecte a la seva àncora. Opcions: `bottom`, `left`, `right`, `top` | string | `undefined` |
| `tooltipButton` | `tooltip-button` | Activa o desactiva aquesta característica | boolean | `false` |

**Esdeveniments:** sense esdeveniments declarats.

**Utilitzat per:** `button-component` ([Botons](component-botons.md)), `chat-button-component` ([Botó de xat](component-boto-de-xat.md)).

**Exemple d'instància (PDF)**

```html
<tooltip-component
message="texto-ejemplo"
placement="bottom"
tooltip-button=false
></tooltip-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.0.0 | 12.0.3 | 4 setembre, 2026 | Desenvolupament: es corregeix el problema pel qual el modal es tancava en prémer la tecla ESC mentre la descripció emergent estava actiu. S'aplica un z-index elevat. |
| 12.0.0 | 12.0.0 | 10 juliol, 2026 | Desenvolupament: s'utilitza el token correcte per al color de text que obre el popover, per al títol, descripció i metadata. |
| 12.0.0 | 11.0.0 | 19 juny, 2026 | Desenvolupament: s'afegeix el component sheet en breakpoints mòbil. Millores d'accessibilitat en mode focus i lector de pantalla. |
| 12.0.0 | 9.2.0 | 29 maig, 2026 | Disseny: es crea la variant per punts de tall small. |
| 8.6.0 | 9.2.0 | 27 febrer, 2026 | Desenvolupament: es fan millores d'accessibilitat. |
| 8.6.0 | 8.5.0 | 9 febrer, 2026 | Disseny: s'eliminen màxims i s'afegeix scroll per si creix en excés per temes d'augment de text. S'ha modificat la ubicació del títol perquè es desplaci amb el contingut i no quedi fix juntament amb el botó de tancament. |
| 8.4.0 | 8.5.0 | 5 desembre, 2025 | Disseny: s'ajusta l'alçada màxima del popover a 448 px. Desenvolupament: resolució de problemes menors. |
| 8.2.0 | 8.0.0 | 14 novembre, 2025 | Desenvolupament: resolució de problemes. |
| 8.2.0 | 6.2.1 | 27 octubre, 2025 | Disseny: s'aplica una alçada màxima de 152 px al cos de text. S'aplica una alçada màxima de 592 px al popover. S'aplica una alçada màxima de 48 px al text dels ítems de l'aditional content i un clip content. S'aplica amplada màxima de 320 px al frame "structure". S'aplica un marge entre títol i botó de tancament de 4 px. Revisió d'estils tipogràfics. |
| 2.3.0 | 6.2.1 | 3 octubre, 2025 | Desenvolupament: nova propietat afegida o eliminada. |
| 2.3.0 | 6.1.0 | 12 setembre, 2025 | Desenvolupament: nova propietat afegida. |
| 2.3.0 | 6.0.0 | 3 juliol, 2025 | Desenvolupament: resolució de problemes. |
| 2.3.0 | 5.0.0 | 9 juny, 2025 | Desenvolupament: resolució de problemes. |
| 2.3.0 | 1.0.0 | 31 gener, 2025 | Sense canvis. |
| 2.2.0 | 0.1.1 | 20 gener, 2025 | Sense canvis. |
| 2.1.0 | 0.1.1 | 04 desembre, 2024 | Disseny de la mida Small del botó d'ajuda (per aplicar a l'àrea de text). |
| 2.0.0 | 0.1.0 | 02 desembre, 2024 | Sense canvis. |
| 1.1.0 | 0.1.0 | 22 novembre, 2024 | Desenvolupament del component. |
| 1.1.0 | No aplica | 19 novembre, 2024 | Disseny i documentació del component. |

## Vegeu també
- [Indicador de funció](component-indicador-de-funcio.md): per mostrar un text breu en passar el cursor per sobre d'una icona o activador.
- [Modals](component-modals.md): per proporcionar informació crítica o quan cal demanar una decisió.
- [Panell emergent](component-panell-emergent.md)
