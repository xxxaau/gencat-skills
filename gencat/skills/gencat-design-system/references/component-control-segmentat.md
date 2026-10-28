# Control segmentat (Segmented control)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/858408 · Web component: `<segmented-control-component>` (paquet core) · Font actualitzada el 2026-10-19 · Extret el 2026-10-28

## Què és i quan usar-lo
Un control segmentat és un conjunt de botons alineats que permeten triar una opció de visualització concreta.

Es presenta com una barra horitzontal dividida en segments (botons), cadascun representant una opció de visualització del contingut. Només un segment pot estar seleccionat a la vegada. Quan l'usuari fa clic a un segment, aquest s'activa i desactiva l'anterior seleccionat.

Quan s'utilitza:
- Quan es vol fer un canvi de visualització del contingut.
- Quan hi ha més de dues i fins a quatre formes de visualització del contingut.
- Quan el canvi d'opció és immediat i no requereix confirmació.

## Quan NO usar-lo / alternatives
- Si hi ha més de quatre opcions, el control segmentat es fa difícil d'interactuar per l'usuari.
- Quan l'usuari vol fer una selecció múltiple o una altra acció que no tingui a veure amb un canvi de visualització del contingut.

## Anatomia
Figma: Segmented control [Show Item 04 = True, Show Item 03 = True, Type = Text, Selected item = 1].

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Type | Text / Icon | Text |
| Selected item | 1 / 2 / 3 / 4 | 1 |
| Show item 03 | Yes / No | Yes |
| Show item 04 | Yes / No | Yes |

Estats (Figma): `_Segmented control item` [Icon = list-ul, Show icon = True, Text = Button, Type = Text, State = Default, Selected = True]. La font mostra dues subseccions: control segmentat de tipus text i de tipus icona (mateixa variant Figma).

### Nombre d'opcions
Per garantir una experiència d'usuari clara i eficient, cal limitar el nombre d'opcions disponibles dins del control segmentat:
- Mínim: 2 elements.
- Màxim: 4 elements.

## Comportament i interacció
1. Per defecte, l'opció posicionada a l'esquerra és la que sempre apareix seleccionada.
2. En el moment que l'usuari fa clic sobre un segment, aquest **es marca automàticament com a seleccionat** i mostra de manera immediata el contingut, oferint una resposta fluida i intuïtiva.
3. Per reforçar aquesta interacció, el segment actiu es destaca visualment mitjançant un canvi d'estat clar i coherent amb el disseny general, assegurant que l'usuari identifiqui fàcilment quina opció està activa en tot moment.

### Adaptació responsiva
- **Desktop (escriptori):** hi ha més espai disponible; és preferible mostrar tant el **text com la icona** en cada opció del segment. Aquesta combinació facilita la comprensió immediata de les opcions i millora l'accessibilitat.
- **Mobile (dispositiu mòbil):** l'espai és més limitat; es recomana mostrar **només la icona** per mantenir una interfície neta i funcional. Aquesta simplificació visual ajuda a evitar la saturació de contingut i manté la claredat en pantalles petites, sempre que les icones siguin prou representatives i comprensibles per si soles.

## Bones pràctiques

### Claredat
- **FER:** Aporta claredat en les etiquetes de les diferents opcions.
- **NO FER:** Evita etiquetes amb significat ambigu o poc clar.

### Icones
- **FER:** Utilitza icones simples i universalment reconegudes que reforcin el significat de l'etiqueta.
- **NO FER:** Evita icones complexes o poc relacionades amb l'etiqueta que acompanyen.

### Espaiats
- **FER:** Mantingues una mida coherent entre totes les opcions, inclosa la seleccionada.
- **NO FER:** Evita que l'opció seleccionada sigui més gran que les no seleccionades.

### Consistència
- **FER:** Mantingues la consistència visual entre totes les opcions.
- **NO FER:** Evita utilitzar formats diferents (amb icona i sense) entre les opcions.

### Estat actiu per defecte
- **NO FER:** No utilitzis el control segmentat en estat deshabilitat.

### Selecció
- **NO FER:** No utilitzis el control segmentat per habilitar més d'una opció a la vegada.

### Mida de les icones
- **FER:** Mantingues una mida d'icona consistent entre totes les opcions, inclosa la seleccionada.
- **NO FER:** Evita fer més gran la icona de l'opció seleccionada.

## Accessibilitat

### Pautes WCAG
- **Contrast d'elements no textuals (AA):** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. Els elements decoratius, com el divisor, estan exempts. [1.4.11 CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Encapçalaments i etiquetes descriptives (AA):** inclou etiquetes descriptives o `aria-label` per indicar clarament la funció del switch. [2.4.6 CAT](https://www.w3.org/Translations/WCAG22-ca/#headings-and-labels) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/headings-and-labels)
- **Nom, funció, valor (A):** usa atributs com `aria-checked` per reflectir l'estat del switch als lectors de pantalla. [4.1.2 CAT](https://www.w3.org/Translations/WCAG21-ca/#name-role-value) / [EN](https://www.w3.org/TR/WCAG21/#name-role-value)

### Navegació per teclat

| Tecla | Acció |
|---|---|
| Shift + Tabulador | Navegar a l'element anterior. |
| Fletxes dreta i esquerra | Navegar entre les diferents pestanyes. |
| Enter | Seleccionar una pestanya |

## Implementació (component web)

### `<segmented-control-component>`

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat |
|---|---|---|---|---|---|
| `items` | `items` | Elements del component. Accepta array d'objectes o string JSON | `string` (JSON) | `undefined` | Obligatori |
| `showIcons` | `show-icons` | Mostrar o amagar icones dels elements | `boolean` | `true` | Opcional |
| `showItem3` | `show-item-3` | Mostrar o amagar el tercer element | `boolean` | `true` | Opcional |
| `showItem4` | `show-item-4` | Mostrar o amagar el quart element | `boolean` | `true` | Opcional |
| `showLabels` | `show-labels` | Mostrar o amagar etiquetes dels elements | `boolean` | `true` | Opcional |

**Propietats de l'array `items`**

| Propietat | Atribut | Descripció | Tipus | Obligatorietat |
|---|---|---|---|---|
| `icon` | `icon` | Classe de la icona de bootstrap | `string` | Obligatori |
| `label` | `label` | Text de l'etiqueta | `string` | Obligatori |

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre / tipus | Origen |
|---|---|---|---|
| `itemSelected` | Es propaga en seleccionar un element | `index`, `item` — `CustomEvent<{ index: number; item: any; }>` | `segmented-control-component` |

**Exemple d'ús**

```html
<!-- /index.html -->
<segmented-control-component
  items='[
    { "label": "Opció 1", "icon": "bi-list-ul" },
    { "label": "Opció 2", "icon": "bi-list-ul" },
    { "label": "Opció 3", "icon": "bi-list-ul" },
    { "label": "Opció 4", "icon": "bi-list-ul" }
  ]'
  show-icons="true"
  show-item-3="true"
  show-item-4="true"
  show-labels="true">
</segmented-control-component>
```

Exemple d'instància (PDF):

```html
<segmented-control-component
items="texto-ejemplo"
show-icons=true
show-item-3=true
show-item-4=true
show-labels=true
></segmented-control-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 8.2.0 | 6.2.1 | 27 octubre, 2025 | **Disseny**: revisió d'estils tipogràfics |
| 6.0.0 | 6.2.1 | 3 octubre, 2025 | **Desenvolupament**: Resolució de problemes. |
| 6.0.0 | - | 08 juliol, 2025 | **Disseny** i **documentació** del component. |

## Vegeu també
- [Botons](component-botons.md)
- [Pestanyes](component-pestanyes.md)
