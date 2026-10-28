# Visor de notícies (News viewer)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/75b39a · Web component: `<viewer-component>`, `<carousel-component>` i `<card-news-component>` (paquet core) · Font actualitzada el 2026-10-22 · Extret el 2026-10-28

## Què és i quan usar-lo
Component dissenyat per oferir una previsualització compacta i estructurada de diverses notícies, facilitant-ne la consulta ràpida i l'accés a informació rellevant. Permet destacar continguts de manera visualment atractiva, mantenint una jerarquia clara que afavoreix la lectura i la navegació. Adaptable a diferents dispositius, garanteix una experiència d'usuari fluida i coherent dins del sistema de disseny.

Quan s'utilitza:
- Quan cal agrupar informació de manera visual, accessible i jerarquitzada referent a notícies o articles.
- Quan cal mostrar campanyes (contingut estacional).

## Quan NO usar-lo / alternatives
- Quan el contingut no es renova amb freqüència, ja que un visor de notícies sense actualitzacions pot semblar obsolet.
- Quan la quantitat de notícies és molt gran i cal una estructura més complexa, com filtres avançats o cerques: pot ser millor una quadrícula de dades o un sistema de categories.

## Anatomia
Figma: Visor de notícies [Show card 04 = True, Breakpoint = Extra Large Column fixed, Type = Hierarchical, Column number = -]. La font només mostra la imatge d'anatomia.

## Variants, tipus i estats

### Propietats del visor de notícies

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Extra Large Column Fixed / Extra Large Column Variable / Large / Medium / Small | Extra Large Column Fixed |
| Type | Hierarchical / Columns | Hierarchical |
| Column number | 4-3 / 2 / - | — |
| Show card 04 | True / False | True |

- **Tipus:** jerarquitzat (Hierarchical) o per columnes (Columns).
- **Visor de tipus columnat:** permet modificar algunes propietats de les targetes per adaptar-lo segons les necessitats.
- **Nombre de columnes:** aquesta propietat només afecta els tipus de visor en columna (no jerarquitzat). La booleana Show card 04 permet adaptar-lo a 3 columnes.

### Propietats de les targetes del visor

**Targeta destacada de notícies**

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Large-Extra Large / Medium-Small | Extra Large Column Fixed |
| State | Default / Hover / Focus / Pressed | Default |

Variant Figma: Visor de notícies [Breakpoint = Extra Large - Large, State = Default]. El punt de tall Extra Large - Large aplica als dos punts de tall Extra Large.

**Targetes de notícies**
S'apliquen als visors per columnes. En el visor jerarquitzat s'ha utilitzat un component de targeta diferent per adaptar-se a les diferents mides dels punts de tall. Per construir un **visor no jerarquitzat amb més de 4 targetes**, cal utilitzar aquestes.

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Image position | Top / Right | Top |
| State | Default / Hover / Focus / Pressed | Default |
| Description | True / False | True |
| Show image | True / False | True |
| Breakpoint | Medium-Extra Large / Small | Medium-Extra Large |
| Date | True / False | True |
| Tag | True / False | True |

Variants Figma: Visor de notícies [Show image = True, Image position = Top, State = Default]; News card [Show image = True, Image position = Top, State = Default, Show Description = True]. Subseccions de la font: Posició de la imatge, Estat, Descripció, Punt de tall (Extra large / small), Imatge (true / false), Data (true / false), Etiqueta (true / false).

## Comportament i interacció

### Adaptació responsiva
**Visor jerarquitzat**
- Les targetes es van reorganitzant als diferents punts de tall. En cadascun s'adapta la disposició i la proporció d'aspecte de les imatges.
- En els punts de tall més petits, el visor jerarquitzat s'adapta distribuint els elements un sota l'altre; tots són sempre visibles.

**Visor a 4 i 3 columnes**
- Les targetes tenen una alçada en funció del contingut. La targeta amb un text més llarg marca l'alçada de la resta de targetes de la fila.
- En els punts de tall més petits, el visor a 4 i 3 columnes distribueix els elements un al costat de l'altre i els amaga sota un carrusel.

**Visor a 2 columnes**
- Les targetes tenen una alçada específica en funció dels elements que es mostren.
- En els punts de tall més petits, el visor s'adapta distribuint els elements l'un sota l'altre; tots són sempre visibles.

### Focus
- L'ordre del focus en el visor jerarquitzat segueix un desplaçament d'esquerra a dreta i de dalt a baix i s'adapta a la distribució de cada punt de tall.
- La navegació es fa amb la tecla tabuladora.

### Carrusel
En els punts de tall on el visor es mostra en format carrusel, la navegació amb la tecla tabuladora accedeix a la primera targeta del visor i el desplaçament entre targetes es fa amb les fletxes dreta i esquerra.

## Contingut i microcopy
- Títol de la notícia a la qual redirigeix: concret i clar.
- Frases curtes, precises i fàcils d'entendre.
- Format de data únic en totes les targetes.
- Icones de la targeta (Bootstrap Icons): `bi-arrow-right-short` (per defecte) o `bi-box-arrow-up-right`.

## Bones pràctiques
- **FER:** Utilitza frases curtes, precises i fàcils d'entendre per comunicar el missatge de manera efectiva.
- **NO FER:** No utilitzis frases llargues o complexes per comunicar el missatge.
- **FER:** Inclou el títol de la notícia a la qual redirigeix. Aquest hauria de ser concret i clar.
- **FER:** Assegura't que les imatges siguin rellevants (aportin context), de qualitat i respectin l'estil visual definit al sistema de disseny.
- **NO FER:** No utilitzis imatges que no siguin rellevants (fora de context), de poca qualitat o que no respectin l'estil visual definit al sistema de disseny.
- **FER:** Utilitza el mateix format en totes les dates.
- **NO FER:** No variïs el format en les dates.

## Accessibilitat
Pautes WCAG 2.2:
- **Contrast mínim (AA) – 1.4.3:** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats en són excepció. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA) – 1.4.4:** excepte subtítols i imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA) – 1.4.11:** els elements gràfics presenten un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A) – 2.1.1:** tota la funcionalitat (navegar pels enllaços) es pot operar amb teclat sense requerir temps específics per a pulsacions de tecles individuals. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Focus visible (AA) – 2.4.7:** la navegació amb teclat pels diferents elements és visible mitjançant un rectangle. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

### Navegació per teclat

| Tecla | Acció |
|---|---|
| Tabulació | Navegació al següent element interactiu |
| Shift + Tabulació | Navegació a l'anterior element interactiu |
| Enter | Activar element interactiu |

**Carrusel**

| Tecla | Acció |
|---|---|
| Tabulació | Navegació al següent element interactiu |
| Fletxa dreta / esquerra | Navegació per les diferents targetes del visor |
| Shift + Tabulació | Navegació a l'anterior element interactiu |
| Enter | Activar element interactiu |

## Implementació (component web)

### `<viewer-component>`

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Obligatori | Per defecte |
|---|---|---|---|---|---|
| `isHierarchical` | `is-hierarchical` | Vista jerarquitzada. | boolean | Obligatori | `true` |
| `isCarousel` | `is-carousel` | Activació del carrusel. | boolean | Obligatori | `false` |
| `columnNumber` | `column-number` | Elecció entre 2 i 3-4 columnes (opcions: `2`, `3-4`). | string | Opcional | `undefined` |
| `carouselColumnNumber` | `carousel-column-number` | Elecció de 3 o 4 columnes (opcions: `3`, `4`). Número de columnes visibles al carrusel. | string | Opcional | `undefined` |
| `cardsData` | `cards-data` | Array amb les propietats de `card-news-component`, en format JSON, que conté la informació de les targetes que es mostraran. | string (Array) / `any[]` | Obligatori | — |
| `columnFixed` | `column-fixed` | Activació de marges adaptatius en pantalles amples. | boolean | Obligatori | `true` |

**Esdeveniments:** sense esdeveniments declarats.

**Variants**

| Propietat | Opcions | Per defecte |
|---|---|---|
| `columnNumber` | `2` `3-4` `undefined` | `undefined` |
| `carouselColumnNumber` | `3` `4` `undefined` | `undefined` |
| `isHierarchical` | `true` `false` | `true` |
| `isCarousel` | `true` `false` | `false` |
| `columnFixed` | `true` `false` | `true` |

**Combinacions d'ús**

| Vista | Propietats del visor | Propietats de l'array `cardsData` |
|---|---|---|
| Tipus hierarchical | `isHierarchical: true`, `isCarousel: false`, `columnFixed: true o false`, `columnNumber: undefined`, `carouselColumnNumber: undefined` | `isHighlight: true`, `imgRightNews: false` |
| Tipus columnat 4 | `isHierarchical: false`, `isCarousel: true`, `columnFixed: true o false`, `columnNumber: 3-4`, `carouselColumnNumber: 4` | `isHighlight: false`, `imgRightNews: false` |
| Tipus columnat 3 | `isHierarchical: false`, `isCarousel: true`, `columnFixed: true o false`, `columnNumber: 3-4`, `carouselColumnNumber: 3` | `isHighlight: false`, `imgRightNews: false` |
| Tipus columnat 2 | `isHierarchical: false`, `isCarousel: false`, `columnFixed: true o false`, `columnNumber: 2`, `carouselColumnNumber: undefined` | `isHighlight: false`, `imgRightNews: true` |

**Depèn de:** `button-component` ([Botons](component-botons.md)), `carousel-component`, `card-news-component`.

**Props que accepten JSON:** `cardsData` (`cards-data`): array d'objectes amb les propietats de `card-news-component` (vegeu `<card-news-component>`); `cardTagArray` dins de cada objecte és un array d'objectes `{ "type": "readonly", "text": "...", "color": "color-white" }`.

**Exemple d'ús (pàgina)**

```html
<!-- /index.html -->
<viewer-component
    is-hierarchical="false"
    column-number="3-4"
    carousel-column-number="3"
    column-fixed="false"
    is-carousel="false"
    cards-data='[
    {
      "headerImage": "https://oxygenworkspace.com/wp-content/uploads/2021/06/Despacho-04-1.jpg",
      "dateCard": "23-23-2333",
      "titleCard": "Descripción de la tarjeta Descripción de la tarjetaDescripción de la tarjetaDescripción de la tarjetaDescripción de la tarjetaDescripción de la tarjetaDescripción de la tarjetaDescripción de la tarjeta",
      "descriptionCard": "",
      "isHighlight": false,
      "imgRightNews": false,
      "iconCard": "bi-arrow-right-short",
      "goActionLink": "#",
      "goActionLinkTarget": "_blank",
      "cardTagArray": [
        { "type": "readonly", "text": "Etiqueta 2", "color": "color-white" },
        { "type": "readonly", "text": "Etiqueta 2", "color": "color-white" }
      ]
    },
    {
      "headerImage": "/assets/hero_banner.png",
      "dateCard": "",
      "titleCard": "Título de la tarjeta",
      "descriptionCard": "Descripción de la tarjeta",
      "isHighlight": false,
      "imgRightNews": false,
      "iconCard": "bi-arrow-right-short",
      "goActionLink": "#",
      "goActionLinkTarget": "_blank",
     "cardTagArray": [{"type": "readonly", "text": "Etiqueta 1", "color": "color-white"},
      {"type": "readonly", "text": "Etiqueta 2", "color": "color-white"}]
    },
    {
      "headerImage": "https://oxygenworkspace.com/wp-content/uploads/2021/06/Despacho-04-1.jpg",
      "dateCard": "23-23-2333",
      "titleCard": "Descripción de la tarjeta Descripción de la tarjetaDescripción de la tarjetaDescripción de la tarjetaDescripción de la tarjetaDescripción de la tarjetaDescripción de la tarjetaDescripción de la tarjeta",
      "descriptionCard": "",
      "isHighlight": false,
      "imgRightNews": false,
      "iconCard": "bi-arrow-right-short",
      "goActionLink": "#",
      "goActionLinkTarget": "_blank",
      "cardTagArray": [
        { "type": "readonly", "text": "Etiqueta 2", "color": "color-white" }
      ]
    },
    {
      "headerImage": "",
      "dateCard": "",
      "titleCard": "Títol Les targetes són components visuals dissenyats per organitzar i presentar contingut de forma clara i atractiva.",
      "descriptionCard": "",
      "isHighlight": true,
      "imgRightNews": false,
      "iconCard": "bi-arrow-right-short",
      "goActionLink": "#",
      "goActionLinkTarget": "_blank",
      "cardTagArray": [
        { "type": "readonly", "text": "Etiqueta 2", "color": "color-white" }
      ]
    },
     {
      "headerImage": "",
      "dateCard": "",
      "titleCard": "Títol Les targetes són components visuals dissenyats per organitzar i presentar contingut de forma clara i atractiva.",
      "descriptionCard": "",
      "isHighlight": true,
      "imgRightNews": false,
      "iconCard": "bi-arrow-right-short",
      "goActionLink": "#",
      "goActionLinkTarget": "_blank",
      "cardTagArray": [
        { "type": "readonly", "text": "Etiqueta 2", "color": "color-white" },
        { "type": "readonly", "text": "Etiqueta 2", "color": "color-white" }
      ]
    }
  ]'
></viewer-component>
```

**Exemple d'instància (PDF)**

```html
<viewer-component
cards-data="texto-ejemplo"
carousel-column-number="3"
column-fixed=true
column-number="2"
is-carousel=false
is-hierarchical=true
></viewer-component>
```

### `<carousel-component>`

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Obligatori | Per defecte |
|---|---|---|---|---|---|
| `cardsData` | `cards-data` | Array amb les propietats de `card-news-component`, en format JSON, que conté la informació de les targetes que es mostraran. | Array (`any[]` o string) | Obligatori | — |

**Esdeveniments:** sense esdeveniments declarats.

**Depèn de:** `card-news-component`, `button-component` ([Botons](component-botons.md)). **Utilitzat per:** `viewer-component`.

**Exemple d'ús (pàgina; la font repeteix el mateix objecte fins a 7 targetes, aquí es mostren les variants diferents)**

```html
<!-- /index.html -->
<carousel-component 
  cards-data='[
    {
      "headerImage": "/assets/hero_banner.png",
      "dateCard": "2025-03-18",
      "titleCard": "Título de la tarjeta",
      "descriptionCard": "Descripción de la tarjeta",
      "isHighlight": false,
      "imgRightNews": false,
      "iconCard": "bi-arrow-right-short",
      "goActionLink": "#",
      "goActionLinkTarget": "_blank",
     "cardTagArray": [{"type": "readonly", "text": "Etiqueta 1", "color": "color-white"},
      {"type": "readonly", "text": "Etiqueta 2", "color": "color-white"}]
    },
    {
      "headerImage": "https://oxygenworkspace.com/wp-content/uploads/2021/06/Despacho-04-1.jpg",
      "dateCard": "2025-03-18",
      "titleCard": "Título de la tarjeta",
      "descriptionCard": "Descripción de la tarjeta",
      "isHighlight": false,
      "imgRightNews": false,
      "iconCard": "bi-arrow-right-short",
      "goActionLink": "#",
      "goActionLinkTarget": "_blank",
      "cardTagArray": [{"type": "readonly", "text": "Etiqueta 1", "color": "color-white"}]
    }
    /* ... fins a 7 targetes amb la mateixa estructura (headerImage alternant entre "/assets/hero_banner.png" i la URL externa) */
  ]'></carousel-component>
```

**Exemple d'instància (PDF)**

```html
<carousel-component
cards-data="texto-ejemplo"
></carousel-component>
```

### `<card-news-component>`

**Propietats** (a la pàgina del lloc corresponen a les claus de cada objecte de `cardsData`)

| Propietat | Atribut HTML | Descripció | Tipus | Obligatori | Per defecte |
|---|---|---|---|---|---|
| `headerImage` | `header-image` | Imatge de la targeta (URL de la imatge de capçalera). En vistes no jerarquitzades, per mostrar imatges, totes les targetes han de tenir imatge. Si almenys una targeta no té `headerImage`, no es mostra cap imatge a la vista no jerarquitzada. | string | Obligatori | `` |
| `titleCard` | `title-card` | Títol de la targeta. | string | Obligatori | `` |
| `descriptionCard` | `description-card` | Descripció de la targeta. | string | Opcional | `` |
| `dateCard` | `date-card` | Data de la targeta. | string | Opcional | `` |
| `cardTagArray` | `card-tag-array` | Llista d'etiquetes associades a la targeta; es rep com a array en format JSON (accepta array d'objectes o string JSON). | string | Opcional | `` |
| `isHighlight` | `is-highlight` | Opció per triar entre targetes destacades o de notícies. | boolean | Obligatori | `false` |
| `imgRightNews` | `img-right-news` | Opció per col·locar la imatge a la dreta a les targetes de notícies. | boolean | Obligatori | `false` |
| `iconCard` | `icon-card` | Icona de la targeta (classe de Bootstrap Icons). | string | Obligatori | `bi-arrow-right-short` |

Altres claus que apareixen als exemples de `cardsData`: `goActionLink` (p. ex. `"#"`), `goActionLinkTarget` (p. ex. `"_blank"`). [a verificar: no consten a la taula de propietats de la font]

**Esdeveniments:** sense esdeveniments declarats.

**Variants**

| Propietat | Opcions | Per defecte |
|---|---|---|
| `IconCard` | `bi-arrow-right-short` `bi-box-arrow-up-right` | `bi-arrow-right-short` |

**Depèn de:** `button-component` ([Botons](component-botons.md)) segons la pàgina; `tag-component` segons el PDF. **Utilitzat per:** `carousel-component`, `viewer-component`.

**Props que accepten JSON:** `cardTagArray`: array d'objectes `{ "type": "readonly", "text": "Etiqueta 1", "color": "color-white" }`.

**Exemple d'ús (pàgina)**

```html
<!-- /index.html -->
  <card-news-component
  header-image="https://oxygenworkspace.com/wp-content/uploads/2021/06/Despacho-04-1.jpg"
  date-card="data"
  title-card="Títol Les targetes són components visuals dissenyats per organitzar i presentar contingut de forma clara i atractiva. Les targetes són components visuals dissenyats per organitzar i presentar contingut de forma clara i atractiva Les targetes són components visuals dissenyats per components."
  description-card="Descripció Les targetes són components visuals dissenyats per organitzar i presentar contingut de forma clara i atractiva. Les targetes són components visuals dissenyats per organitzar i presentar contingut de forma clara i atractiva Les targetes són components visuals dissenyats per organitzar."
  card-tag-array='[
    { "type": "readonly", "text": "Etiqueta 1", "color": "color-white" },
    { "type": "readonly", "text": "Etiqueta 2", "color": "color-white" }
  ]'
  is-highlight="true"
  img-right-news="false"
  icon-card="bi-arrow-right-short"
></card-news-component>
```

**Exemple d'instància (PDF)**

```html
<card-news-component
card-tag-array=''
date-card=''
description-card=''
header-image=''
icon-card='bi-arrow-right-short'
img-right-news=false
is-highlight=false
title-card=''
></card-news-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.3.0 | 11.0.0 | 31 juliol, 2026 | Disseny: s'afegeix un arrodoniment a les targetes del visor "News card". |
| 9.0.0 | 11.0.0 | 19 juny, 2026 | Desenvolupament: ajustos d'accessibilitat. |
| 9.0.0 | 9.2.0 | 27 febrer, 2026 | Desenvolupament: millores d'accessibilitat en targetes de notícies i en visor de notícies. |
| 8.6.0 | 9.1.0 | 9 febrer, 2026 | Disseny: s'eliminen alçades màximes de les targetes i contenidors; totes les alçades a hug; es redueix l'alçada mínima del Column News cards text a 88 px; canvia la distribució de les targetes en el visor jerarquitzat als punts de tall Extra large column variable i large; s'elimina l'alçada mínima de targetes; s'alineen les cards de les variants dels visors. |
| 8.5.0 | 9.1.0 | 6 febrer, 2026 | Desenvolupament: adaptacions d'accessibilitat per a mides de font extra grans i augment de pantalla. |
| 8.5.0 | 6.2.1 | 20 gener, 2026 | Disseny: mínim d'alçada de 374 px a la targeta "Highlight News Card" del punt de tall medium - small; l'estil tipogràfic Heading passa a Body al text de les targetes "News card highlited viewer". |
| 8.4.0 | 6.2.1 | 5 desembre, 2025 | Disseny: actualització del nom de les targetes a la versió 4-3 i al jeràrquic; es treu el clip content a la versió 4-3; s'aplica estil de color als fons de les targetes. |
| 8.0.0 | 6.2.1 | 3 octubre, 2025 | Desenvolupament: resolució de problemes. |
| 8.0.0 | 6.0.0 | 12 setembre, 2025 | Disseny: l'estil tipogràfic Label passa a Body al text de les targetes. |
| 6.0.0 | 6.0.0 | 8 juliol, 2025 | Disseny: s'aplica l'elevació 1 a totes les targetes. |
| 4.0.0 | 6.0.0 | 3 juliol, 2025 | Desenvolupament: resolució de problemes. |
| 4.0.0 | 4.0.1 | 19 maig, 2025 | Desenvolupament: resolució de problemes. |
| 2.4.0 | 2.1.0 | 31 març, 2025 | Desenvolupament del component. |
| 2.4.0 | No aplica | 10 març, 2025 | Disseny del component. |

## Vegeu també
- [Enllaços](component-enllacos.md): per facilitar la navegació entre parts del contingut o funcionalitats.
- [Etiquetes](component-etiquetes.md): per mostrar l'estat d'un element, les propietats clau o les categories.
- [Imatge](fonaments-imatge.md)
- [Targetes](component-targetes.md)
- [Botons](component-botons.md)
- [Campanya](component-campanya.md)
