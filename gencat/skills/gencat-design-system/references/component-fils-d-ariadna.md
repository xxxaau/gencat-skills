# Fils d'Ariadna (Breadcrumbs)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/26cc61 · Web component: `<breadcrumb-component>` (paquet core) · Font actualitzada el 2026-10-20 · Extret el 2026-10-28

## Què és i quan usar-lo
Indiquen en tot moment en quin punt de la web es troba l'usuari dins la jerarquia d'aquesta.

El fil d'Ariadna és un **llistat d'enllaços que s'utilitza per proporcionar una trajectòria clara de les pàgines** dins de la jerarquia d'un lloc o aplicació. S'usa per ajudar l'usuari a entendre on es troba dins de l'estructura d'un lloc web i facilitar-li la navegació entre els diferents nivells.

- **FER:** Utilitza els enllaços sempre en format text, i mai amb icones.
- **NO FER:** No utilitzis enllaços en format icona.

## Anatomia
Figma: Breadcrumbs [Text = Nivell actual, Breakpoint = Extra Large - Large, Type = Default]. Parts: nivells (enllaços, amb el nivell actual al final), botó de col·lapsar ("…") i desplegable amb els nivells ocults.

## Variants, tipus i estats

### Nivells (`_Breadcrumbs_levels`)

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Default / Hover / Pressed / Focus | Default |

Variants Figma: Text = Nivell; State = Default.

### Botó col·lapsar (`_Breadcrumbs_collapsed button`)

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Default / Hover / Pressed / Focus | Default |
| Selected | True / False | False |

### Desplegable (`_Breadcrumb_collapsed menu`)

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Levels | 1 level / 2 levels / 3 levels / 4 levels | 1 level |

### Fils d'Ariadna (component principal)

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Extra Large - Large / Medium - Small | Extra Large - Large |
| Type | Default / Collapsed-unselected / Collapsed-selected | Default |

Variants Figma: Text = Nivell actual; Breakpoint = Extra Large - Large | Medium - Small; Type = Default | Collapsed-unselected | Collapsed-selected.

## Mides i espaiats
- Mida dels chevrons: 20 px (v12.0.1 de desenvolupament; a Figma 12.2.0 "es redueix la mida dels chevrons a 20px").
- Punt de tall que canvia el comportament: 960 px.

## Comportament i interacció

### Estat Default
- Els fils d'Ariadna van sempre ubicats a la part superior esquerra, per sota del *header*.
- En seleccionar un dels nivells, s'obre l'enllaç en la mateixa pestanya.
- Es mostren fins a un màxim de 3 nivells visibles, incloent-hi el nivell actual.
- A partir del cinquè nivell de jerarquia, els nivells inicials es col·lapsen dins del botó "…", mantenint visibles els nivells més propers a la pàgina actual.
- En seleccionar el botó de col·lapse, es desplegaran els nivells ocults respectant l'ordre jeràrquic, d'inici a final.

[a verificar: la font diu alhora "màxim de 3 nivells visibles" i "a partir del cinquè nivell… es col·lapsen"; l'exemple de codi té 5 nivells]

### Arquitectura
- Els enllaços que es mostren als fils d'Ariadna fan referència a l'arquitectura del lloc, i no a la navegació que ha realitzat l'usuari.
- Per a punts de tall **Extra Large i Large**, els nivells que siguin visibles des d'un menú de navegació **no s'inclouen dins dels fils d'Ariadna**. El primer element és aquell que no és visible. Això es fa per evitar duplicitats amb la navegació per pestanyes en la capçalera. (La font mostra exemples FER / NO FER només com a imatge: Arquitectura_nivell 1, 2 i 3.)
- Per a punts de tall **Medium i Small**, **sempre hi ha fils d'Ariadna visibles a partir del segon nivell de jerarquia**, ja que els primers nivells són ocults al menú hamburguesa. En aquest cas, s'indica, al fil d'Ariadna, el nivell justament anterior.

### Estat col·lapsat
El desplegable mostra els nivells d'inici a final. Si, per exemple, el desplegable conté 3 nivells, l'ordre de dalt a baix és: nivell 1, nivell 2 i nivell 3.

### Adaptació responsiva
- **Breakpoints iguals o superiors a 960px:** en els casos excepcionals en què els *breadcrumbs* sobrepassin l'espai disponible de pantalla, el component ha de permetre el salt de línia (*wrap*), distribuint el contingut en línies consecutives segons sigui necessari.
- **Breakpoints inferiors a 960px:** es mostra únicament el nivell anterior amb la icona de fletxa "←".

## Contingut i microcopy
Textos d'exemple: "Nivell 1" ... "Nivell 4", "Nivell actual"; identificadors `link1`...`link5`.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG):
- **1.4.1 Ús del color (A):** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per diferenciar els estats es juga amb la presència de subratllats i el seu gruix. (https://www.w3.org/Translations/WCAG22-ca/#use-of-color · https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **1.4.3 Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. (https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum · https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **1.4.4 Canvia la mida del text (AA):** excepte subtítols i imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. (https://www.w3.org/Translations/WCAG22-ca/#resize-text · https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **1.4.11 Contrast d'elements no textuals (AA):** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. (https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast · https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **2.1.1 Teclat (A):** tota la funcionalitat del contingut (navegar pels diferents enllaços i el botó desplegable) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. (https://www.w3.org/Translations/WCAG22-ca/#keyboard · https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **2.4.7 Focus visible (AA):** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. (https://www.w3.org/Translations/WCAG22-ca/#focus-visible · https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

## Implementació (component web)

### `<breadcrumb-component>`
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Obligatorietat (lloc) | Tipus | Per defecte (PDF) |
|---|---|---|---|---|---|
| `items` | `items` | Array d'objectes que defineix els nivells dels fils d'Ariadna. Cada objecte ha de contenir: `content` (nom del nivell), `active` (boolean; `true` si és l'últim nivell, `false` en els altres nivells) i `id` (identificador del nivell). PDF: accepta array d'objectes o string JSON. | Obligatori | String (array\|JSON) · PDF: `items[]` o `string` | (no definit) |

**Props que accepten JSON: `items`** (array d'objectes)

| Propietat | Descripció | Atribut | Obligatorietat | Tipus |
|---|---|---|---|---|
| `active` | Indica quin nivell està actiu. | `active` | Obligatori | Boolean |
| `content` | Nom del nivell. | `content` | Obligatori | String |
| `id` | Identificador de nivell. | `id` | (no indicat) | String |

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre | Origen | Tipus (PDF) |
|---|---|---|---|---|
| `clickLevel` | Esdeveniment llançat en seleccionar un nivell | `id` | `breadcrumb-component` | `CustomEvent<void>` |

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<breadcrumb-component 
  items='[
          {
            "content": "Nivell 1",
            "active": false,
            "id": "link1"
          },
          {
            "content": "Nivell 2",
            "active": false,
            "id": "link2"
          },
          {
            "content": "Nivell 3",
            "active": false,
            "id": "link3"
          },
          {
            "content": "Nivell 4",
            "active": false,
            "id": "link4"
          },
          {
            "content": "Nivell actual",
            "active": true,
            "id": "link5"
          }
        ]
        '
  ></breadcrumb-component>
```

**Exemple d'instància (PDF)**

```html
<breadcrumb-component
items=[]
></breadcrumb-component>
```

**Utilitzat per:** `backoffice-subheader-component` ([Capçalera secundària de BO](component-capcalera-secundaria-de-bo.md)), `horizontal-menu-component` ([Menú horitzontal](component-menu-horitzontal.md)), `secundary-header-component` (al PDF: `secondary-header-component`) ([Capçalera secundària](component-capcalera-secundaria.md)).

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.2.0 | 12.0.1 | 10 juliol, 2026 | Disseny: es redueix la mida dels chevrons a 20px. |
| 8.2.0 | 12.0.1 | 14 juliol, 2026 | Desenvolupament: s'amplia la mida de la icona chevron a 20px, s'elimina el truncat i s'aplica flex-wrap: wrap perquè el component s'adapti correctament a textos extensos |
| 8.2.0 | 8.0.0 | 14 novembre, 2025 | Desenvolupament: resolució de problemes |
| 8.2.0 | 7.0.0 | 27 octubre, 2025 | Disseny: revisió d'estils tipogràfics |
| 8.0.0 | 7.0.0 | 24 octubre, 2025 | Desenvolupament: resolució de problemes |
| 8.0.0 | 6.2.1 | 3 octubre, 2025 | Desenvolupament: nova propietat afegida o eliminada |
| 8.0.0 | 6.0.1 | 12 setembre, 2025 | Disseny: es modifica l'estil dels "Levels" de Body a Label. |
| 1.0.0 | 6.0.1 | 28 juliol, 2025 | Desenvolupament: resolució de problemes |
| 1.0.0 | 0.0.3 | 1 novembre, 2024 | Disseny, desenvolupament i documentació del component. |

[discrepància: la mida dels chevrons a la versió de disseny 12.2.0 és "es redueix a 20px" i a la de desenvolupament "s'amplia a 20px"]

## Vegeu també
- [Botons](component-botons.md): per realitzar accions.
- [Enllaços](component-enllacos.md): per facilitar la navegació entre parts del contingut o funcionalitats.
