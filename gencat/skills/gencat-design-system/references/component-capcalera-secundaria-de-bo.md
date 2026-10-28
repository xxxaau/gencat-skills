# Capçalera secundària de BO (Backoffice Subheader)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/25ba21 · Web component: `<backoffice-subheader-component>` (paquet core) · Font actualitzada el 2026-10-06 · Extret el 2026-10-28

## Què és i quan usar-lo
La capçalera secundària de BO és un component estructural que proporciona context i accions rellevants dins d'una vista interna d'un sistema de gestió.

S'utilitza per mostrar el títol de la secció, accions contextuals i elements de navegació complementaris al nivell principal. Forma part de la jerarquia visual que facilita la identificació ràpida del contingut i la coherència entre aplicacions corporatives.

Quan s'utilitza:
- En pantalles internes de gestió (*backoffice*) on es requereixi un nivell jeràrquic inferior a la capçalera principal.
- Quan l'usuari necessita accedir a accions globals de la pàgina actual (crear, exportar, etc.).
- En entorns amb fluxos de treball complexos per mantenir la coherència entre pantalles.

Per veure com s'aplica a pàgina: [exemples d'ús de gestió interna](exemple-gestio-interna.md).

## Quan NO usar-lo / alternatives
- En la capçalera principal del sistema (no substitueix la capçalera global).
- En pantalles sense contingut jeràrquic o sense accions contextuals.
- En aplicacions orientades al ciutadà (només ús intern, no públic).

## Anatomia
1. **Fils d'Ariadna (opcional)**: indiquen la ubicació de l'usuari dins l'estructura del sistema i permeten navegar als nivells anteriors.
2. **Títol de pàgina**: identifica de manera clara el contingut o secció activa. És l'element de màxima jerarquia visual.
3. **Descripció emergent (opcional)**: informació complementària vinculada al títol. Pot ampliar, matisar o contextualitzar el contingut principal.
4. **Metadades (opcional)**: informació clau associada al contingut principal (data, autor, estat, identificadors...). S'empren per aportar context addicional de manera concisa.
5. **Etiquetes informatives (opcional)**: destaquen categories, estats o atributs del contingut. No són interactives.
6. **Grup de botons d'icona (opcional)**: accions que afecten la vista global de la pàgina (imprimir, exportar, etc.).

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Extra Large / Large / Medium | Extra Large |
| Show breadcrumbs | True / False | False |
| Show Content Container | True / False | False |
| ↳ Show Metadata | True / False | False |
| ↳ Show Button Group | True / False | False |
| Show Popover | True / False | False |
| Show Tags | True / False | False |
| ↳ Show Tag 02 | True / False | False |

Figma (punt de tall): Capçalera secundària back office [↳ Show Metadata = True, ↳ Show Button Group = True, Show Breadcrumbs = False, Show Content Container = False, Breakpoint = Extra Large].

Tipus de metadada (component web): `text` (per defecte) | `icon`.

## Mides i espaiats
Ubicació:
- Quan hi ha el menú horitzontal, la capçalera secundària de BO s'ubica immediatament sota aquest.
- Quan hi ha menú lateral, la capçalera se situa alineada amb el menú lateral i per sota de la capçalera principal.
- Quan coexisteixen el menú horitzontal i el lateral, la capçalera es disposa sota el menú horitzontal i per sobre del menú lateral.

Punts de tall disponibles: Extra Large, Large i Medium.

## Comportament i interacció
Navegació per teclat:

| Tecla | Acció |
|---|---|
| Tabulació | Navega fins al primer element interactiu del component (panell emergent o botó del grup de botons). Navegar per les diferents opcions |
| Intro | Acciona un dels elements interactius |
| Esc | Cancel·la una acció |

## Bones pràctiques
Ús del contingut:
- **NO FER:** Evita títols massa llargs que puguin trencar la jerarquia visual.
- **NO FER:** No es recomana utilitzar les metadades per a textos extensos; només informació rellevant i concisa.
- **FER:** Utilitza la descripció emergent per mostrar informació complementària del títol o del context immediat.
- **NO FER:** No utilitzis la descripció emergent per informació que no sigui complementària, com textos llargs, notes internes o dades que pertanyen al cos de la pàgina.

Etiquetes i accions:
- **FER:** Mostra només les accions que realment s'utilitzaran en el context immediat de la pàgina, per exemple imprimir o compartir.
- **FER:** Es recomana un màxim de 4–5 accions per evitar saturació. Si n'hi ha més, agrupa-les en un menú d'opcions.
- **NO FER:** No facis servir noms genèrics com "Més informació" per a l'etiqueta de la descripció emergent; utilitza sempre el nom complet i específic del contingut, per exemple nom del tràmit o de l'expedient.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG):
- **Orientació (AA)** — [1.3.4](https://www.w3.org/Translations/WCAG22-ca/#orientation) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html): el contingut de l'àrea de text s'adapta a les diferents orientacions de la pantalla, vertical o horitzontal, cosa que permet visualitzar el contingut. (Text tal com surt a la font.)
- **Contrast mínim (AA)** — [1.4.3](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum): els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma.
- **Canvia la mida del text (AA)** — [1.4.4](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text): excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat.
- **Espaiat del text (AA)** — [1.4.12](https://www.w3.org/Translations/WCAG22-ca/#text-spacing) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/text-spacing): quan es desenvolupa contingut utilitzant llenguatges de marcatge que permeten aplicar les propietats d'estil de text, no es perd cap contingut ni funcionalitat si s'ajusten les propietats següents:
  - Alçada de línia (interlineat) de com a mínim 1,5 vegades la mida de la lletra.
  - Espaiat entre els paràgrafs de com a mínim dues vegades la mida de la lletra.
  - Espaiat entre lletres (*tracking*) de com a mínim 0,12 vegades la mida de la lletra.
  - Espaiat entre paraules de com a mínim 0,16 vegades la mida de la lletra.

Pautes aplicables a fils d'Ariadna:
- **Teclat (A)** — [2.1.1](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard): tota la funcionalitat del contingut (navegar pels diferents enllaços i el botó desplegable) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals.

## Implementació (component web)

### `<backoffice-subheader-component>`
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat |
|---|---|---|---|---|---|
| `breadcrumbItems` | `breadcrumb-items` (el lloc indica `breadcrumbItems`) | Elements del breadcrumb. Col·lecció d'elements: accepta array d'objectes o string JSON. | string (JSON) | undefined | Opcional |
| `buttonsConfig` | `buttons-config` | Permet afegir botons a la subcapçalera; per cada línia amb l'atribut `icon` i `tooltip` que s'escrigui, s'afegirà un botó. Màxim 4 botons. Acepta objecte o string JSON. | string (JSON) | undefined | Opcional |
| `metadataItems` | `metadata-items` | Elements de la metadada. Col·lecció d'elements: accepta array d'objectes o string JSON. | string (JSON) | undefined | Opcional |
| `popoverContent` | `popover-content` (el lloc indica `popoverContent`) | Contingut del popover (HTML o text del component). | string (object) | undefined | Opcional |
| `tagContent` | `tag-content` | Contingut de les tags (HTML o text del component). Màxim 2 botons [sic; vol dir etiquetes: el lloc diu "Màxim 2 botons"]. | string (JSON) | undefined | Opcional |
| `titleSubHeader` | `title-sub-header` (el lloc indica `titleSubheader` / `title-subheader`) | Títol de la subcapçalera. | string | undefined | Opcional |
| `typeMetadata` | `type-metadata` | Tipus de metadada, ja sigui de text o d'icona. Opcions: `icon`, `text`. | string | `text` | Opcional |

[discrepància: el lloc escriu els atributs `breadcrumbItems`, `popoverContent` i `title-subheader`; el PDF i l'exemple de codi usen `breadcrumb-items`, `popover-content` i `title-sub-header`]

**Propietats del string JSON `breadcrumbItems`**

| Propietat | Descripció | Tipus |
|---|---|---|
| `content` | Títol del nivell breadcrumb | String |
| `active` | Indica si el nivell està actiu o no | Boolean |
| `id` | Identificador del nivell | String |

**Propietats del string JSON `popoverContent`**

| Propietat | Descripció | Tipus |
|---|---|---|
| `textOpen` | Text de l'element que obre el popover | String |
| `popoverTitle` | Títol del popover | String |
| `description` | Descripció del popover | String |

**Propietats del string JSON `tagContent`**

| Propietat | Descripció | Tipus |
|---|---|---|
| `text` | Text de l'etiqueta | String |
| `color` | Color de l'etiqueta; valors possibles: `color-information` `color-success` `color-alert` `color-error` `color-new` `color-dark` `color-white` | String |

**Propietats del string JSON `buttonsConfig`**

| Propietat | Descripció | Tipus |
|---|---|---|
| `icon` | Classe de la icona de bootstrap | String |
| `tooltip` | Text de l'interior del tooltip del botó | String |

**Propietats del string JSON `metadataItems`**

| Propietat | Descripció | Tipus |
|---|---|---|
| `title` | Títol de la metadada | String |
| `description` | Descripció de la metadada | String |
| `classIcon` | En cas que `typeMetadata` sigui `icon`, indicar en aquesta propietat la classe de la icona de bootstrap | String |

**Variants**

| Propietat | Per defecte | Valors |
|---|---|---|
| `typeMetadata` | `text` | `text` `icon` |

**Esdeveniments** (el PDF indica "sense esdeveniments declarats"; el lloc en documenta aquests)

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `handlerClick` | Es llança cada vegada que es canvia de ràdio button | value | `button-component` |
| `focusButton` | Esdeveniment llançat en fer focus sobre algun dels botons. | - | `button-component` |
| `button-component` | Esdeveniment llançat en treure el focus d'algun dels botons [sic: el lloc llista aquest nom d'esdeveniment com a `button-component`; probablement `blurButton`; a verificar]. | - | `button-component` |
| `clickLevel` | Esdeveniment llançat en seleccionar un nivell del breadcrumb | `id` | `breadcrumb-component` |

**Depèn de:** `breadcrumb-component` ([Fils d'Ariadna](component-fils-d-ariadna.md)), `tag-component` ([Etiquetes](component-etiquetes.md)), `button-component` ([Botons](component-botons.md)), `group-button-component` ([Grup de botons](component-grup-de-botons.md)), `popover-component` ([Descripció emergent](component-descripcio-emergent.md)).

**Exemple d'ús**

```html
<!-- /index.html -->
<backoffice-subheader-component 
  breadcrumb-items='[
    { "content": "Nivell", "active": false, "id": "nivell-1" },
    { "content": "Nivell", "active": false, "id": "nivell-2" },
    { "content": "Nivell actual", "active": true, "id": "nivell-3" }
  ]' 
  title-sub-header="Lorem ipsum dolor sit amet consectetur adipiscing elit gravida ligula maecenas viverra, curabitur dignissim rhoncus pretium arcu semper vestibulum eleifend rutrum. Et quisque cras massa mauris varius himenaeos dictum odio, tortor eros curabitur luctus sagittis ridiculus facilisis, torquent primis egestas nisl euismod metus purus." 
  popover-content='{
    "text-open": "Ajuda",
    "popover-title": "Títol de prova",
    "description": "Lorem ipsum dolor sit amet consectetur adipiscing elit gravida ligula maecenas viverra, curabitur dignissim rhoncus pretium arcu semper vestibulum eleifend rutrum. Et quisque cras massa mauris varius himenaeos dictum odio, tortor eros curabitur luctus sagittis ridiculus facilisis, torquent primis egestas nisl euismod metus purus."
  }'
  tag-content='[
        { "text": "Etiqueta 1" },
        { "text": "Etiqueta 2", "color": "color-alert" }
  ]'
  buttons-config='[
    { "icon": "bi-pencil", "tooltip": "Editar" },
    { "icon": "bi-trash", "tooltip": "Eliminar" },
    { "icon": "bi-pencil", "tooltip": "Editar" },
    { "icon": "bi-trash", "tooltip": "Eliminar" }
  ]'
  type-metadata="text"
  metadata-items='[
    {"title":"Lorem ipsum","description":"Lorem ipsum","classIcon":"bi-geo-alt"},
    {"title":"Lorem ipsum","description":"Lorem ipsum","classIcon":"bi-geo-alt"},
    {"title":"Lorem ipsum","description":"Lorem ipsum","classIcon":"bi-geo-alt"},
    {"title":"Lorem ipsum","description":"Lorem ipsum","classIcon":"bi-geo-alt"},
    {"title":"Lorem ipsum","description":"Lorem ipsum","classIcon":"bi-geo-alt"}
  ]'>
</backoffice-subheader-component>
```

Exemple d'instància del PDF:

```html
<backoffice-subheader-component
breadcrumb-items="texto-ejemplo"
buttons-config="texto-ejemplo"
metadata-items="texto-ejemplo"
popover-content="texto-ejemplo"
tag-content="texto-ejemplo"
title-sub-header="texto-ejemplo"
type-metadata='text'
></backoffice-subheader-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 10.0.0 | 12.0.0 | 10 juliol, 2026 | **Desenvolupament**: es corregeix l'alineament entre botons i metadades |
| 10.0.0 | 9.0.0 | 17 abril, 2026 | **Disseny**: S'actualitza el grup de botons amb la funcionalitat de slots. |
| 8.4.0 | 9.0.0 | 12 gener, 2026 | **Desenvolupament**: S'introdueixen dos punts de tall nous |
| 8.4.0 | 8.5.0 | 5 desembre, 2025 | **Disseny**: Es dissenyen les versions pels punts de tall Large i Medium. / S'ajusta la posició del botó per activar la descripció emergent quan hi ha dues o més línies de títol. **Desenvolupament** del component |
| 8.3.0 | - | 14 novembre, 2025 | **Disseny** i **documentació** del component |

## Vegeu també
- [Capçalera secundària](component-capcalera-secundaria.md): per indicar el propòsit de la pàgina.
- [Fils d'Ariadna](component-fils-d-ariadna.md): per proporcionar una trajectòria clara de les pàgines visitades.
- [Grup de botons](component-grup-de-botons.md): agrupa dos o més botons que tenen una relació funcional o contextual.
- [Etiquetes](component-etiquetes.md): mostra l'estat d'un element, les propietats clau o les categories.
- [Descripció emergent](component-descripcio-emergent.md): apareix quan l'usuari interactua amb un element de la pàgina en clicar i roman obert fins que es tanquen.
- [Gestió interna (exemple)](exemple-gestio-interna.md)
