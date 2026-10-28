# Etiquetes (Tags)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/19379b · Web component: `<tag-component>` (paquet core) · Font actualitzada el 2026-10-22 · Extret el 2026-10-28

## Què és i quan usar-lo
Una etiqueta és un component estàtic i no accionable que mostra l'estat d'un element, les propietats clau o les categories.

Les etiquetes s'utilitzen per facilitar l'escaneig i la comprensió de la informació dins de la interfície. Segons la variant, poden servir per categoritzar continguts, indicar l'estat d'un procés, mostrar informació temporal o identificar continguts generats o modificats amb IA. Algunes variants incorporen recursos visuals específics, com ara el color, per ajudar a diferenciar-ne el significat, sempre mantenint els criteris d'accessibilitat i coherència definits pel Sistema de Disseny.

## Anatomia
Figma: `_Tags_read_only` [Size = Large, State = Blue]; `_Tags_date`.

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Type | Read-only / Date | Read-only |

### Read-only
Utilitza les etiquetes no interactives per categoritzar elements d'una web o indicar l'estat d'un procés. Aquesta tipologia inclou variables de color per ajudar a diferenciar visualment un estat d'un altre.

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Size | Large / Small | Large |
| Color | Blue / Green / Orange / Red / Purple / Grey / Neutral | Neutral |

#### Mida
Hi ha dues mides d'etiquetes: petita o mitjana (a Figma: Large / Small).
- **Gran (Large):** utilitza-la per defecte, sempre que hi hagi suficient espai. Per exemple, dins d'una pàgina d'una sol·licitud o dins d'un llistat de tràmits.
- **Petita (Small):** utilitza-la quan l'etiqueta vagi inclosa dins d'un altre component i es disposi d'un espai més limitat. Per exemple, dins d'una targeta, dins d'una taula de dades o dins d'un camp de cerca.

#### Color
Els colors semàntics només estan disponibles en la versió no interactiva (read-only). Utilitza els colors de forma coherent d'acord amb les associacions especificades.

Significats associats als colors (la font els mostra en aquest ordre, un per variant de color Figma):
- Error, cancel·lat o denegat.
- Deshabilitat, inactiu o arxivat.
- Neutre, per representar categories nominals.
- Novetat o destacat.
- Confirmació, activació, vigència.
- Informació o actiu.
- Precaució, pendent, esborrany o en procés.

[a verificar: la font no explicita quin color Figma correspon a cada significat; la correspondència amb les opcions de codi és `color-error`, `color-white`/neutre, `color-new`, `color-success`, `color-information`, `color-alert`, `color-dark`]

Regles de simplificació:
- Intenta simplificar al màxim el nombre de tipologies o estats d'etiquetes a les mínimes necessàries. Si disposes de més estats que les variables de color disponibles, considera agrupar-los en estats més genèrics i deixar l'especificació del "subestat" com a element informatiu dins de la pàgina o component.
- Per a les etiquetes de categoria que no representen estats, és recomanable utilitzar la tipologia "neutre" i no fer diferenciació de color, ja que tenir massa colors dins d'una pàgina pot crear massa soroll visual i perjudicar l'experiència d'usuari.

### Data
Les etiquetes de data estan pensades per ser utilitzades individualment i dins de components específics com les [targetes](component-targetes.md).

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Range | True / False | False |
| First number | 00 | --- |
| First month | MES | --- |
| Second number | 00 | --- |
| Second month | MES | --- |

Variants Figma: Rang_False | Rang_True (data única o rang de dates).

### Etiquetatge d'IA
Aquestes etiquetes permeten identificar de manera clara i coherent els continguts generats o modificats amb intel·ligència artificial. Per obtenir més informació sobre els criteris d'ús, les variants i el comportament, consulta [Etiquetatge d'IA](component-etiquetatge-d-ia.md).

## Mides i espaiats
- Separació entre etiquetes consecutives: 8 px.
- L'etiqueta de data té alçada en hug amb una alçada mínima de 56 px, padding inferior de 0 px i padding superior de 8 px (versió 9.1.0 de Github).
- Màxim de 24 caràcters per etiqueta.

## Comportament i interacció

### Posició
Quan hi hagi diverses etiquetes seguides, s'alinearan horitzontalment mantenint una separació de 8 px. Si no hi ha espai disponible, saltaran a una segona línia, mantenint la mateixa separació de 8 px.

### Adaptació responsiva
L'amplada de les etiquetes s'adaptarà al seu contingut. Com a màxim, l'etiqueta podrà contenir 24 caràcters. Si l'etiqueta té més de 24 caràcters, el text es truncarà. [discrepància: l'historial de versions indica que a la versió 10.1.0 de Github (29 maig 2026) "s'elimina el truncat"]

### Altres
En casos puntuals i necessaris, les etiquetes d'estat podran anar acompanyades d'un indicador de funció que aporti aclariments sobre el significat de l'estat (vegeu [Indicador de funció](component-indicador-de-funcio.md); a codi: `textInfoTooltip`).

## Bones pràctiques

### Contingut
- **FER:** Les etiquetes han de ser concises i clares. Utilitza adjectius per descriure estats o noms per indicar categories.
- **NO FER:** Evita etiquetes que siguin massa llargues, ja que poden trencar el disseny i ser difícils de llegir.
- **NO FER:** No utilitzis verbs (paraules d'acció), ja que pot portar l'usuari a pensar que fer clic a una etiqueta desencadenarà alguna acció.

### Quantitat
- **NO FER:** No sobrecarreguis una interfície amb massa etiquetes. Això pot provocar una sobrecàrrega cognitiva per a l'usuari.

### Consistència
- **FER:** Mantingues un conjunt coherent d'etiquetes en tot el sistema per evitar confusió. Estableix un sistema de nomenclatura i colors per a les etiquetes i segueix sempre aquest patró.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG) que cita el component:
- **1.4.3 Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. (CAT: https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum · EN: https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **1.4.4 Canvia la mida del text (AA):** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. (CAT: https://www.w3.org/Translations/WCAG22-ca/#resize-text · EN: https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **1.4.11 Contrast d'elements no textuals (AA):** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. (CAT: https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast · EN: https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)

## Implementació (component web)

### `<tag-component>`
Paquet: core.

**Propietats**

Taula de la pàgina del lloc (amb obligatorietat):

| Propietat | Atribut HTML | Descripció | Obligatorietat | Tipus |
|---|---|---|---|---|
| `dataTagDate` | `data-tag-date` | Dades de la tag de tipus `date` | Opcional | String (JSON) |
| `size` | `size` | Grandària de les etiquetes de tipus `readonly` | Opcional | String |
| `tags` | `tags` | Dades del grup de tags del tipus `readonly` | Obligatori | String (JSON) |
| `type` | `type` | Tipus de tag: `readonly` o `date` | Obligatori | String |

Valors per defecte segons el PDF (v12.0.0):

| Propietat | Atribut HTML | Descripció (PDF) | Tipus | Per defecte |
|---|---|---|---|---|
| `dataTagDate` | `data-tag-date` | Etiqueta de data per a les dades. | string | `[]` |
| `size` | `size` | Mida del component. Opcions: `medium`, `small`. | string | `small` |
| `tags` | `tags` | Etiquetes de l'element. Accepta array d'objectes o string JSON. | string | `[]` |
| `type` | `type` | Tipus d'element. Opcions: `date`, `readonly`. | string | `readonly` |

**Props que accepten JSON**

Propietats de l'array `tags`:

| Propietat | Atribut | Descripció | Obligatori | Tipus |
|---|---|---|---|---|
| `color` | `color` | Color de l'etiqueta. | Opcional | String |
| `text` | `text` | Text de l'etiqueta. | Obligatori | String |
| `textInfoTooltip` | `text-info-tooltip` | Text de l'indicador de funció de l'etiqueta. | Opcional | String |

Propietats de l'array `dataTagDate`:

| Propietat | Atribut | Descripció | Obligatori | Tipus |
|---|---|---|---|---|
| `day` | `day` | Primera data del rang o del mode single | Obligatori | String |
| `endDay` | `end-day` | Segon dia del rang | Opcional | String |
| `endMonth` | `end-month` | Segon mes del rang | Opcional | String |
| `mode` | `mode` | Mode de l'etiqueta `single` o `range` | Obligatori | String |
| `month` | `month` | Primer mes del rang o mode single | Obligatori | String |

**Variants (lloc)**

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `color` | `color-information` `color-success` `color-alert` `color-error` `color-new` `color-dark` `color-white` | `color-white` |
| `mode` | `single` `range` | --- |
| `size` | `small` `medium` | `small` |
| `type` | `readonly` `date` | `readonly` |

**Esdeveniments:** cap declarat.

**Depèn de:** `tooltip-component` ([Indicador de funció](component-indicador-de-funcio.md)).

**Utilitzat per:**
- `backoffice-subheader-component` ([Capçalera secundària de BO](component-capcalera-secundaria-de-bo.md))
- `card-info-component`, `card-info-evolutive-component`, `card-news-component` ([Targetes](component-targetes.md))
- `dynamic-table-component` ([Taules dinàmiques](component-taules-dinamiques.md))
- `header-component` ([Capçalera per aplicacions internes](component-capcalera-per-aplicacions-internes.md))
- `poi-component` ([Visor de mapa](component-visor-de-mapa.md))
- `results-list-component` ([Llistat de resultats](component-llistat-de-resultats.md))
- `summary-list-component` ([Dades estructurades](component-dades-estructurades.md))
- `timeline-component` ([Línia de temps](component-linia-de-temps.md))
- `vertical-tabs-component` ([Pestanyes](component-pestanyes.md))
- `viewer-component` ([Visor de notícies](component-visor-de-noticies.md))

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<tag-component 
  size="medium" 
  type="readonly" 
  tags='[
        { "text": "Text curt" },
        { "text": "Etiqueta" },
        { "text": "Alert", "color": "color-alert", "textInfoTooltip": "Text tag" },
        { "text": "Fora de termini", "color": "color-alert" },
        { "text": "Error", "color": "color-error" },
        { "text": "Atenció", "color": "color-error", "textInfoTooltip": "Error" }
      ]' 
  data-tag-date='[ { "mode": "single", "day": "15", "month": "set.", "endDay": "10", "endMonth": "June" } ]'
></tag-component>
```

**Exemple d'instància (PDF)**

```html
<tag-component
data-tag-date='[]'
size='small'
tags='[]'
type='readonly'
></tag-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.4.0 | 12.0.3 | 09 setembre, 2026 | Disseny: nova variant del component d'etiquetes per identificar continguts generats o modificats amb IA |
| 9.0.0 | 12.0.3 | 4 setembre, 2026 | Desenvolupament: les propietats `tags` i `dataTagDate` s'han fet reactives |
| 9.0.0 | 12.0.0 | 10 juliol, 2026 | Desenvolupament: s'utilitza el token correcte per al color dels textos |
| 9.0.0 | 10.1.0 | 29 maig, 2026 | Desenvolupament: s'elimina el truncat |
| 9.0.0 | 9.3.0 | 20 març, 2026 | Desenvolupament: posar l'alçada en hug a la tag de tipus data |
| 9.0.0 | 9.1.0 | 11 febrer, 2026 | Disseny: l'etiqueta de data passa de tenir alçada fixa a alçada en hug amb una alçada mínima de 56 px, padding inferior de 0 px i padding superior de 8 px |
| 8.2.0 | 9.1.0 | 6 febrer, 2026 | Desenvolupament: adaptacions d'accessibilitat pel que fa a mides de font extra gran i augment de pantalla |
| 8.2.0 | 8.5.0 | 5 desembre, 2025 | Desenvolupament: resolució de problemes menors |
| 8.2.0 | 8.0.0 | 14 novembre, 2025 | Desenvolupament: resolució de problemes |
| 8.2.0 | 6.0.1 | 27 octubre, 2025 | Disseny: revisió d'estils tipogràfics |
| 7.0.0 | 6.0.1 | 28 juliol, 2025 | Disseny: s'ajusta el comportament del contenidor de les etiquetes; es passa d'alçada fixa a Hug. Desenvolupament: resolució de problemes |
| 6.0.0 | 4.0.1 | 8 juliol, 2025 | Disseny: s'ajusta el comportament del contenidor de la data final del rang a Hug |
| 4.0.0 | 4.0.1 | 19 maig, 2025 | Desenvolupament: resolució de problemes |
| 2.3.0 | 1.1.0 | 17 febrer, 2025 | Desenvolupament: resolució de problemes |
| 2.3.0 | 1.0.0 | 31 gener, 2025 | Sense canvis |
| 2.2.0 | 0.1.1 | 20 gener, 2025 | Sense canvis |
| 2.1.0 | 0.1.1 | 04 desembre, 2024 | Disseny: s'ajusta el comportament del text perquè s'adapti al contingut |
| 2.0.0 | 0.1.0 | 02 desembre, 2024 | Sense canvis |
| 1.1.0 | 0.1.0 | 22 novembre, 2024 | Desenvolupament del component |
| 1.1.0 | 0.0.4 | 19 novembre, 2024 | Disseny i documentació del component |

## Vegeu també
- [Botons](component-botons.md): per a realitzar accions.
- [Insígnia](component-insignia.md): per a cridar l'atenció dels usuaris sobre un element en la pàgina.
- [Targetes](component-targetes.md)
- [Etiquetatge d'IA](component-etiquetatge-d-ia.md)
- [Indicador de funció](component-indicador-de-funcio.md)
