# Glossari (Glossary)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/06c20c · Web component: `<glossary-component>` (paquet core) · Font actualitzada el 2026-10-07 · Extret el 2026-10-28

## Què és i quan usar-lo
El Glossari és un component de consulta que permet presentar definicions, conceptes i continguts ordenats alfabèticament per facilitar-ne la cerca i la comprensió en contextos informatius o de tramitació. Proporciona una navegació clara i estructurada perquè l'usuari pugui accedir ràpidament als termes disponibles i entendre conceptes tècnics o especialitzats relacionats amb el contingut de la pàgina o servei.

Quan s'utilitza:
- Per presentar definicions de conceptes tècnics o especialitzats que apareixen en pàgines informatives o de serveis.
- Quan es necessita una navegació alfabètica ràpida sobre un conjunt de continguts molt extens.
- Quan els continguts no es poden classificar per categories i la forma més pràctica d'organitzar-los és l'ordre alfabètic.

## Quan NO usar-lo / alternatives
- Quan el contingut es pot agrupar millor per temes en lloc de per ordre alfabètic.
- Quan es tracta d'una FAQ o preguntes recurrents (aquí seria un altre component).
- Quan hi ha pocs elements i la navegació alfabètica no aporta valor.
- Quan es necessiten filtres, etiquetes o sistemes de cerca avançada (ja no és un glossari, és un cercador o un directori).

## Anatomia
Figma: anatomia (Glossari/Components/Glossari/DOC_Glossari/Disseny/anatomia). Barra alfabètica (lletres o rangs de lletres, amb xebrons esquerre/dret) i bloc de termes de la secció activa.

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Show right chevron | True / False | True |
| Show left chevron | True / False | --- |
| Letter item states | Default / Hover / Pressed / Focus / Selected | --- |

Variants Figma: Letter_item_states [Letter = A, State = Default]. Versió 9.1.0: s'afegeix l'estat selected-focus.

Modes (propietat `mode`): `single` (alfabet lletra per lletra) i `range` (agrupat per rangs de lletres).

## Comportament i interacció

### Navegació alfabètica (comportament general)
La barra alfabètica permet navegar de manera ràpida entre els diferents blocs de termes del glossari.
- Quan l'usuari selecciona una lletra, aquesta passa a estat actiu i es mostra únicament el contingut associat a aquella secció.
- L'usuari pot canviar de lletra en qualsevol moment a través de la mateixa barra, que funciona com un conjunt de pestanyes (tabs) on cada lletra obre el seu bloc de termes.

### Lletres sense entrades i estat buit
En el glossari, totes les lletres de l'alfabet es mostren sempre a la barra de navegació, encara que alguna d'elles no tingui cap terme associat. Això garanteix una navegació coherent i evita que la barra canviï de forma en funció del contingut.

Quan l'usuari selecciona una lletra que no té cap entrada, en lloc de deixar l'espai en blanc, es mostra un **estat buit** que informa explícitament que no hi ha termes disponibles per a aquella lletra.

### Rangs de lletres (A-D, E-H, ...)
Els trams de lletres són una variant opcional de la navegació alfabètica. En lloc de mostrar totes les lletres individualment, es mostren agrupades (per ex. A-D, E-H, I-N...).

Els trams s'utilitzen quan:
- El glossari té pocs termes.
- Moltes lletres no tenen cap entrada i mostra molts estats buits.

En seleccionar un tram de lletres (per exemple, A-D), es mostren tots els termes que comencen per qualsevol de les lletres incloses en aquell rang. Cada grup de termes s'encapçala amb la lletra corresponent per indicar clarament a quin subgrup pertany. Si alguna de les lletres del tram no té cap entrada, sota el seu encapçalament es mostra l'estat buit.

## Bones pràctiques

### Claredat i simplicitat
- **FER:** Utilitza entrades breus i definicions clares, evitant tecnicismes innecessaris.
- **FER:** Prioritza que cada entrada inclogui un títol concís i un primer paràgraf clar que permeti entendre el concepte ràpidament.
- **NO FER:** No facis servir paràgrafs massa llargs o amb informació no essencial.

### Consistència
- **FER:** Els noms propis i els termes no traduïbles s'han d'ubicar segons la primera lletra del terme tal com s'escriu originalment. Si la lletra inicial no forma part de l'alfabet del glossari, cal afegir-la.
- **FER:** Si hi ha entrades que comencen per números o símbols, s'ha d'afegir la pestanya "!#1" (caràcters especials) al final del glossari.

### Contingut
- **NO FER:** No barregis tipologies de contingut diferents dins d'un mateix glossari (per exemple: definicions + tràmits + normatives).
- **NO FER:** No introdueixis interaccions que no siguin pròpies d'un glossari (acordions, filtres complexos...).

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG) que cita el component:
- **1.3.4 Orientació (AA):** el contingut de la pestanya s'adapta a les diferents orientacions de la pantalla, com ara vertical o horitzontal, cosa que permet visualitzar el contingut. (CAT: https://www.w3.org/Translations/WCAG22-ca/#orientation · EN: https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **1.4.3 Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. (CAT: https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum · EN: https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **1.4.4 Canvia la mida del text (AA):** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. (CAT: https://www.w3.org/Translations/WCAG22-ca/#resize-text · EN: https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **1.4.11 Contrast d'elements no textuals (AA):** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. (CAT: https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast · EN: https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **2.1.1 Teclat (A):** tota la funcionalitat del contingut (navegar per les diferents pestanyes) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. (CAT: https://www.w3.org/Translations/WCAG22-ca/#keyboard · EN: https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **2.4.7 Focus visible (AA):** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. (CAT: https://www.w3.org/Translations/WCAG22-ca/#focus-visible · EN: https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- **2.5.1 Gestos d'apuntament (A):** totes les funcionalitats que requereixen gestos de contacte múltiple o amb desplaçament es poden activar amb un apuntament únic i sense gestos amb desplaçament, tret que els gestos de contacte múltiple o amb desplaçament siguin essencials. La versió per mòbil està dissenyada en format desplegable per facilitar aquesta interacció. (CAT: https://www.w3.org/Translations/WCAG22-ca/#pointer-gestures · EN: https://www.w3.org/WAI/WCAG22/Understanding/pointer-gestures)

### Navegació per teclat

| Tecla | Acció |
|---|---|
| Tabulació | Navega al següent element interactiu de la pàgina |
| Shift+Tabulació | Navega a l'anterior element interactiu de la pàgina |
| Fletxes dreta i esquerra | Navega per la barra del glossari |
| Enter | Selecciona un element |

## Implementació (component web)

> La implementació de l'*empty state* no es troba desenvolupada, ja que no es disposa de la capacitat per detectar quan la resposta retorna un resultat buit; per tant, aquesta funcionalitat haurà de ser implementada pel desenvolupador que utilitzi el component.

### `<glossary-component>`
Paquet: core.

**Propietats**

Taula de la pàgina del lloc (amb obligatorietat):

| Propietat | Atribut HTML | Descripció | Obligatorietat | Tipus |
|---|---|---|---|---|
| `activeTab` | `active-tab` | Indica la lletra o el rang de lletres seleccionades. Propietat reactiva. | Opcional | String |
| `mode` | `mode` | Indica si el component estarà format per l'alfabet de manera individual, lletra per lletra, o agrupat per rangs de lletres. Propietat reactiva. | Obligatori | String |
| `ranges` | `ranges` | Indica els rangs que apareixeran en el component quan estigui en mode ranges. Propietat reactiva. | Opcional | String (JSON) |
| `specialChars` | `special-chars` | Indica si existeixen caràcters especials. | Opcional | Boolean |

Valors per defecte segons el PDF (v12.0.0):

| Propietat | Atribut HTML | Descripció (PDF) | Tipus | Per defecte |
|---|---|---|---|---|
| `activeTab` | `active-tab` | Índex de la pestanya actualment activa. | string | undefined |
| `mode` | `mode` | Variant visual del component. Opcions: `range`, `single`. | string | `single` |
| `ranges` | `ranges` | Rangs de valors disponibles (p. ex. files per pàgina). Accepta array. | `string \| string[]` | --- |
| `specialChars` | `special-chars` | Activa o desactiva aquesta característica. | boolean | `false` |

Variants (lloc):

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `mode` | `single` `range` | `single` |

**Props que accepten JSON:** `ranges` (cadena JSON amb un array de rangs, p. ex. `'["A - D", "E - H", "I - L", "M - P", "Q - T", "U - Z"]'`).

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre / tipus | Origen |
|---|---|---|---|
| `selectTabGlossary` | Es llança cada cop que es selecciona un element de l'alfabet (PDF: s'emet quan l'usuari selecciona un element). | Element seleccionat. `CustomEvent<string>` | `glossary-component` |

**Depèn de:** `button-component` ([Botons](component-botons.md)).

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
 <glossary-component
    mode="range"
    ranges='["A - D", "E - H", "I - L", "M - P", "Q - T", "U - Z"]'
    active-tab="E - H"
    special-chars="true">
  </glossary-component>
```

**Exemple d'instància (PDF)**

```html
<glossary-component
active-tab="texto-ejemplo"
mode='single'
ranges=[]
special-chars=false
></glossary-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 8.6.0 | 10.1.0 | 29 maig, 2026 | Desenvolupament: es soluciona que en prémer la tecla tab sobre una lletra el component no es desplaci cap a la dreta |
| 8.6.0 | 9.2.0 | 27 febrer, 2026 | Desenvolupament: es fan millores d'accessibilitat |
| 8.6.0 | 9.1.0 | 9 febrer, 2026 | Disseny: es modifica la construcció perquè tot estigui amb hug; s'afegeix l'estat selected-focus |
| 8.5.0 | 9.1.0 | 6 febrer, 2026 | Desenvolupament: ajustaments d'estils i correccions d'accessibilitat per control per veu |
| 8.5.0 | 9.0.0 | 20 gener, 2026 | Disseny: es modifica la línia decorativa gris inferior perquè ocupi tot l'espai disponible; es modifiquen els botons de desplaçament a small |
| 8.4.0 | 9.0.0 | 12 gener, 2026 | Desenvolupament del component |
| 8.4.0 | No aplica | 05 desembre, 2025 | Disseny del component |

## Vegeu també
- [Pestanyes](component-pestanyes.md): per organitzar contingut relacionat en seccions o categories.
- [Botons](component-botons.md)
- [Estat buit](component-estat-buit.md)
