# Llistat de resultats (Results list)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/156685 · Web component: `<results-list-component>` (paquet core) · Font actualitzada el 2026-10-15 · Extret el 2026-10-28

## Què és i quan usar-lo
Conjunt d'elements en resposta a una cerca, filtratge o navegació.

La **llista de resultats** mostra un conjunt d'elements generats a partir d'una cerca, filtratge o consulta específica. Cada element de la llista presenta informació clau de manera estructurada, cosa que permet als usuaris identificar ràpidament les opcions més rellevants.

Quan s'utilitza:
- Quan es mostren múltiples elements com a resultat d'una cerca, filtratge o navegació.

## Quan NO usar-lo / alternatives
- En galeries, carrusels, seccions distribuïdores o com a elements destacats.
- Quan els ítems requereixen una interacció complexa que no es pot resumir en una llista (exemple: dades molt detallades que necessiten una vista de taula).

## Anatomia
Figma: anatomia (Llistat de resultats / Disseny / anatomia). Un resultat pot incloure: categoria de contingut (a sobre del titular), titular (enllaç), descripció, imatge, etiquetes, metadades (amb icona, text o etiqueta) i botó, i un divisor. [a verificar: la font només mostra l'anatomia com a imatge; aquesta llista es dedueix de les propietats i de les bones pràctiques]

## Variants, tipus i estats

### Llista de resultats individual

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Large - Extra Large / Medium-Small | Large - Extra Large |
| Highlighted text | True / False | False |
| Show Description | True / False | True |
| Show Content label | True / False | False |
| Show Tags | True / False | False |
| Show Metadata | True / False | False |
| Show Image | True / False | False |
| Show divider | True / False | True |

Variants Figma: Results list [Show Description = True, Show Tags = False, Show Metadata = False, Show Image = False, Show divider = True, Show Content label = False, Show Button = False, Breakpoint = Large-Extra Large, Show Highlited text = False]. La versió petita no disposa d'imatge.

### Grup de llista de resultats
El component de grup de resultats disposa de dues opcions de resultats amb les quals poder disposar de les diferents opcions plantejades a la visualització de resultats en una pàgina, especificades en el component de [Paginació](component-paginacio.md) (12, 24, 48 i 96). L'últim element del llistat ha d'anar sempre sense divisor.

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Results lists Slot | Results list | Results list |

Variants Figma: Results list group [Number of results = 12].

## Mides i espaiats
El llistat de resultats s'adapta a diferents punts de tall ocupant l'espai disponible. Tanmateix, està pensat per ocupar unes columnes específiques i, per això, es defineixen les amplades màximes i mínimes següents.

| Punts de tall | Amplada màxima | Amplada mínima |
|---|---|---|
| Large-Extra Large | 736 px | 536 px |
| Medium-Small | 665 px | 296 px |

## Comportament i interacció
### Adaptació responsiva
- **Imatge:** per aprofitar al màxim l'espai vertical, el component no disposa d'imatge en la versió per a punts de tall Medium-Small.
- **Etiquetes i metadades:** si les etiquetes o metadades necessiten més espai del disponible en una línia, aquestes saltaran a una segona línia.

### Paraules clau
Quan es realitza una cerca amb una paraula o diverses paraules clau, aquestes haurien d'aparèixer ressaltades en els resultats.

### Ordenació dels resultats
El selector d'ordenació ha d'indicar clarament **quin criteri s'aplica** i **com es mostraran els resultats**. Cal evitar que cada projecte utilitzi fórmules diferents per expressar el mateix ordre.

## Contingut i microcopy
### Literals recomanats per a l'ordenació

| Tipus de dada | Ordre recomanat |
|---|---|
| Text | De l'A a la Z / De la Z a l'A |
| Data | Més recent primer / Més antiga primer |
| Valor numèric | De menor a major / De major a menor |
| Preu | Preu més baix primer / Preu més alt primer |
| Valoració | Més ben valorats primer / Menys ben valorats primer |
| Popularitat | Més populars primer / Menys populars primer |
| Cerca | Rellevància |

Quan el selector inclogui diferents camps, cal indicar també el nom del camp:
- Títol: de l'A a la Z
- Títol: de la Z a l'A
- Data de publicació: més recent primer
- Data de publicació: més antiga primer

### Evitar
- Alfabètic
- Títol ascendent
- Data descendent
- Títol ↓
- A-Z

Quan el literal seleccionat no cap en una sola línia, el selector ha de permetre que el text salti de línia i augmenti l'alçada del camp per mostrar-lo complet. Cal evitar truncar el contingut ocultant-ne una part, especialment quan el text seleccionat aporta informació necessària per entendre el criteri d'ordenació.

En funció de l'espai disponible:
- En amplades grans, el selector pot ampliar-se horitzontalment sempre que no comprometi la resta d'elements de la interfície.
- En amplades reduïdes, el literal pot ocupar més d'una línia i el selector ha d'adaptar la seva alçada.
- Si la disposició horitzontal no permet mostrar correctament el contingut, l'etiqueta "Ordena per" pot situar-se sobre el selector.

Els exemples de la font mostren com s'ha d'adaptar el selector segons l'espai disponible, mantenint sempre visible el literal complet.

## Bones pràctiques
Coherència:
- **FER:** Mantingues la coherència en els noms: els noms dels resultats han de coincidir amb els dels elements de navegació.

Metadades, etiquetes i botó:
- **FER:** Utilitza les metadades per elements amb opcions infinites com adreces, números de telèfon, dates, etc.
- **FER:** Utilitza les etiquetes per a elements finits com departaments, temes, etc.
- **FER:** Utilitza les metadades amb icona per aquells elements que tinguin una representació visual estandarditzada.
- **FER:** Utilitza la categoria de contingut (a sobre del titular) per indicar el tipus de contingut del resultat.
- **FER:** Utilitza les etiquetes amb color si cal indicar un estat, com per exemple "En termini".
- **FER:** Quan utilitzis el botó de preinscripció en el llistat de resultats fes servir el secundari.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG):
- **Canvia la mida del text (AA)** — [1.4.4](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text): excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat.
- **Contrast d'elements no textuals (AA)** — [1.4.11](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast): els elements gràfics com icones i vores presenten un contrast mínim de 3:1. Els elements decoratius, com el divisor, estan exempts.
- **Teclat (A)** — [2.1.1](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard): tota la funcionalitat del contingut (navegar pels resultats) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals.
- **Focus visible (AA)** — [2.4.7](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible): la navegació entre els resultats és visible mitjançant un rectangle extern.

## Implementació (component web)

> Nota important: al component no va inclosa la lògica que aplica lletra bold als resultats coincidents amb la cerca. Cal que l'usuari del component l'implementi i l'associï amb l'element de cerca inclòs a la pàgina.

### `<results-list-component>`
Paquet: core. El PDF indica "sense esdeveniments declarats"; el lloc documenta els esdeveniments de `link-component` (vegeu més avall).

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat |
|---|---|---|---|---|---|
| `dividerResults` | `divider-results` | Línia divisòria entre targetes (activa o desactiva aquesta característica). | boolean | true | Obligatori |
| `maxCards` | `max-cards` | Número de targetes a mostrar. Per defecte seran 10 targetes. | number | 10 | Opcional |
| `results` | `results` (el lloc escriu `banner`) | Llistat de resultats: array amb les propietats de `results-list-component`, en format JSON, que conté la informació de les targetes que es mostraran. Accepta array d'objectes o string JSON. | string (array) | `[]` | Obligatori |

[discrepància: el lloc indica l'atribut `banner` per a `results`; el PDF i l'exemple de codi usen `results`]

**Propietats de l'array `results`**

| Propietat | Descripció | Atribut | Obligatori | Tipus |
|---|---|---|---|---|
| `category` | Especifica de quin tipus de contingut es tracta. | `category` | Opcional | String |
| `description` | Descripció de la targeta. | `description` | Opcional | String |
| `iconMetadata` | Icona que apareix a les metadades. Màxim 6 | `iconMetadata` | Opcional | String (array) |
| `image` | Imatge que acompanya la targeta. | `image` | Opcional | String |
| `links` | Array del component `link-component` | `links` | Obligatori | String (array) |
| `showIconMetadata` | Propietat per mostrar o no la icona. | `showIconMetadata` | Opcional | Boolean |
| `textMetadata` | Text que acompanya la icona o tag de les metadades. | `textMetadata` | Opcional | String (array) |
| `tags` | Array del component `tag-component`. Màxim 6 | `tags` | Opcional | String (array) |
| `tagMetadata` | Etiqueta que apareix a les metadades. Màxim 3 | `tagMetadata` | Opcional | String (array) |

**Propietats de l'array `links`**

| Propietat | Descripció | Atribut | Obligatori | Tipus |
|---|---|---|---|---|
| `customId` | Identificador personalitzat de l'enllaç | `customId` | Opcional | String |
| `text` | Text de l'enllaç | `text` | Obligatori | String |
| `mode` | Manera de l'enllaç: `internal` o `external` | `mode` | Opcional | String |

**Esdeveniments** (segons el lloc)

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `blurLink` | Es llança cada cop que es treu el focus d'un enllaç | - | `link-component` |
| `focusLink` | Es llança cada cop que es fa focus en un enllaç | - | `link-component` |
| `linkEmit` | Esdeveniment llançat en fer clic sobre l'enllaç | `id` | `link-component` |

**Depèn de:** `divider-component` ([Divisor](component-divisor.md)), `link-component` ([Enllaços](component-enllacos.md)), `tag-component` ([Etiquetes](component-etiquetes.md)).

**Exemple d'ús** (el codi original repeteix deu cops l'estructura del segon element; aquí es mostren els dos primers elements i el patró repetit un cop; la resta són idèntics al tercer)

```html
<!-- /index.html -->
<results-list-component 
  max-cards="10" 
  divider-results="true" 
  results='[
      {
        "image": "/assets/photos/hero_banner.png",
        "category": "Tech",
        "description": "Per les etiquetes de categoria que no representen estats, és recomanable utilitzar la tipologia «neutre» i no fer diferenciació de color, ja que tenir masses color dins d’una pàgina pot crear massa soroll visual i perjudicar l",
        "showIconMetadata": false,
        "iconMetadata": ["bi bi-geo-alt", "bi bi-star"],
        "textMetadata": [""],
        "tagMetadata": [""],
        "tags": [{ "text": "Alert", "color": "color-information"},
        { "text": "Fora de termini", "color": "color-white" }],
        "links": [
          { "text": "Per les etiquetes de categoria que no representen estats, és recomanable utilitzar la tipologia «neutre» i no fer diferenciació de color, ja que tenir masses color dins d’una pàgina pot crear massa soroll visual i perjudicar.", "mode": "internal" }
        ]
      },
      {
        "image": "/assets/photos/hero_banner.png",
        "category": "Tech",
        "description": "A great tech product",
        "showIconMetadata": true,
        "iconMetadata": ["bi bi-geo-alt", "bi bi-star"],
        "textMetadata": ["New Arrival", "Best Seller"],
        "tagMetadata": ["Etiqueta:", "Etiqueta:"],
        "tags": [{ "text": "Alert", "color": "color-information"},
        { "text": "Fora de termini", "color": "color-white" }],
        "links": [
          { "text": "View Details", "mode": "internal" }
        ]
      },
      {
        "image": "/assets/photos/hero_banner.png",
        "category": "Tech",
        "description": "A great tech product",
        "showIconMetadata": false,
        "iconMetadata": ["bi bi-geo-alt", "bi bi-star"],
        "textMetadata": ["New Arrival", "Best Seller"],
        "tagMetadata": ["Etiqueta:", "Etiqueta:"],
        "tags": [{ "text": "Alert", "color": "color-information"},
        { "text": "Fora de termini", "color": "color-white" }],
        "links": [
          { "text": "View Details", "mode": "internal" }
        ]
      }
    ]'></results-list-component>
```

Exemple d'instància del PDF:

```html
<results-list-component
divider-results=true
max-cards=10
results='[]'
></results-list-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 11.0.0 | 12.0.0 | 10 juliol, 2026 | **Desenvolupament**: s'utilitza el token correcte per al color de text de la descripció |
| 11.0.0 | 9.2.0 | 8 maig, 2026 | **Disseny:** S'apliquen slots pel llistat d'elements. |
| 8.6.0 | 9.2.0 | 27 febrer, 2026 | **Desenvolupament**: Es crea la propietat customId per a l'enllaç / Es fan millores d'accessibilitat |
| 8.6.0 | 9.1.0 | 9 febrer, 2026 | **Disseny**: S'eliminen truncats. / S'ha modificat el text a hug. |
| 8.1.0 | 9.1.0 | 6 febrer, 2026 | **Desenvolupament**: Es fan adaptacions d'accessibilitat pel que fa a mides de font extra gran i augment de pantalla |
| 8.1.0 | 7.0.0 | 24 octubre, 2025 | **Desenvolupament**: Resolució de problemes |
| 8.1.0 | 6.2.1 | 6 octubre, 2025 | **Disseny**: S'ajusta l'autolayout de les metadades perquè saltin de línia si no hi ha prou espai amb una. S'afegeixen tres etiquetes més al conjunt d'etiquetes. **Desenvolupament**: Nova propietat afegida o eliminada |
| 6.0.0 | 6.0.1 | 28 juliol, 2025 | **Desenvolupament**: Resolució de problemes |
| 6.0.0 | 4.0.1 | 8 juliol, 2025 | **Disseny**: Es modifiquen els llistats perquè coincideixin amb la paginació (12 i 24). |
| 4.0.0 | 4.0.1 | 19 maig, 2025 | **Desenvolupament** del component. |
| 2.4.0 | No aplica | 10 març, 2025 | **Disseny** del component. |

## Vegeu també
- [Divisor](component-divisor.md): per separar contingut o seccions dins d'una pàgina o entre elements.
- [Enllaços](component-enllacos.md): per facilitar la navegació entre parts del contingut o funcionalitats.
- [Etiquetes](component-etiquetes.md): per mostrar l'estat d'un element, les propietats clau o les categories.
- [Imatge](fonaments-imatge.md)
- [Paginació](component-paginacio.md)
