# Rastrejador d'estat (Status tracker)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/8373f2 · Web component: `<status-tracker-component>` (paquet core) · Font actualitzada el 2026-10-15 · Extret el 2026-10-28

## Què és i quan usar-lo
Component que permet monitorar, informar i mostrar l'estat o condició actual de tasques, projectes, processos o objectius. Proporciona informació en temps real sobre el progrés, els problemes i els resultats relacionats amb aquestes activitats.

Quan s'utilitza:
- Seguiment d'enviaments.
- Estat de processament de sol·licituds.
- Fases d'un projecte.

## Quan NO usar-lo / alternatives
- No utilitzis el rastrejador d'estat per a processos que no són lineals.
- Per guiar l'usuari a través d'un procés complex amb accions: [Pas a pas](component-pas-a-pas.md).

## Anatomia
Figma: DOC_Anatomia (imatge d'anatomia del rastrejador d'estat).

## Variants, tipus i estats

### Propietats del rastrejador d'estat

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Collapsed | True / False | - |
| Show Title | True / False | True |
| Show Tooltip | True / False | False |
| Show Link | True / False | False |
| Type | To continue up / To continue down | - |

Type: Figma _Stratus Tracker expandable position [Type = To continue down].

### Propietats del pas

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Done / Current / Current-Alert / Pending / Expired | - |
| Show description | True / False | False |

### Estats
Variants Figma: _Status_tracker_items [Show Line down = True, Show Line up = True, Step = Nom del pas, State = ...]; per a l'estat Expired: _Status_tracker_items [Step = Nom del pas, Show description = False, Show Bottom Line = True, State = ...].
- **Done:** el pas del procés s'ha completat correctament.
- **Pending:** pas pendent de realitzar.
- **Current:** el pas està en procés de revisió. L'usuari no ha de fer cap acció.
- **Current-Alert:** el procés ja ha estat revisat i ara requereix que l'usuari realitzi una acció perquè el procés pugui continuar.
- **Expired:** el pas del procés no s'ha completat/realitzat i ha expirat. Vegeu "Comportament Estat Expirat".

(La font llista les descripcions en l'ordre Done, Pending, en revisió, requereix acció, expirat; l'assignació als noms d'estat Current / Current-Alert és deduïda del significat [a verificar].)

## Mides i espaiats
Dimensions del rastrejador d'estat:
- Amplada màxima: 436px
- Amplada mínima: 296px

## Comportament i interacció
### Interacció
El component no contempla cap interacció, és merament informatiu. Els estats canvien automàticament quan la informació del sistema s'actualitza.

### Posició
Els estats sempre van alineats verticalment i la col·locació varia en funció de l'estructura i el disseny de la pàgina. El rastrejador d'estat es manté sempre a la mateixa posició i no es desplaça amb el contingut: quan l'usuari fa scroll (es desplaça per la pàgina) no veu el rastrejador d'estat.
Figma: DOC_Posició_alert, DOC_Posició.

### Adaptació responsiva
- En mòbil es mostren a un primer nivell només tres estats o fases: l'estat actual, l'estat anterior i el pròxim estat.
- Si la sol·licitud o procés és a l'inici, es mostren els tres primers estats; si és al final del procés, es mostren els tres últims.
- Apareix una línia difuminada vertical per indicar que el procés continua per dalt o/i per baix.
- L'usuari pot fer clic al botó "Mostra tots els estats" per veure el rastrejador complet, i tornar a minimitzar la visualització amb el botó "Mostra menys estats".
- El màxim de passos que poden aparèixer són 10.
Figma: DOC_responsive.

### Comportament "Estat Expirat"
En situacions en què determinats passos del procés ja no poden ser completats (per exemple, perquè el període per fer-ho ha finalitzat i no són opcionals), es mostren amb un **estat específic** que indica que han quedat **no completats per temps**.
El pas actual on es trobava l'usuari en el moment de finalització del període es mostra com a **completat**, però amb un **text secundari** que reflecteix el resultat obtingut (com ara "Desestimat", "Caducat", etc.). El context complet d'aquesta situació s'ha de reforçar a nivell de pàgina o secció amb contingut addicional.
Aquest enfocament permet reflectir visualment i de manera clara la progressió real dins del procés, tot i que aquest no hagi estat finalitzat de forma habitual.
Figma: estat_expirat.

### Prototipat
Quan es prototipi el rastrejador d'estat en les seves dues versions (estat col·lapsat i estat no col·lapsat, amb el botó "Mostrar més"), cal crear cada estat en una pàgina diferent.

## Contingut i microcopy
- Títol del component (opcional): es recomana incloure'l sempre que sigui possible per reforçar el context del procés. Es pot prescindir del títol visible quan:
  - El component està integrat en una secció o pàgina que ja compta amb un títol clarament descriptiu del procés (per exemple, una pàgina titulada "Validació interna").
  - La jerarquia visual i la proximitat amb altres elements de la interfície fan evident el propòsit del component.
- Botons: "Mostra tots els estats" / "Mostra menys estats" (el prototipat esmenta "Mostrar més").
- Textos secundaris de l'estat expirat: "Desestimat", "Caducat".

## Bones pràctiques
### Generals
- **FER:** Informa sempre l'usuari de la posició o estat del procés on es troba.
- **NO FER:** No col·loquis el rastrejador sense cap estat marcat. Sempre hi ha d'haver com a mínim el primer pas marcat en procés.
- **FER:** Mostra les etiquetes d'estat en ordre cronològic de dalt a baix (vertical).
- **NO FER:** No utilitzis el rastrejador d'estat per a processos que no són lineals.
- **FER:** Distribueix cada pas de manera uniforme dins de l'espai disponible.
- **NO FER:** Evita que els estats es distribueixin de manera irregular dins de l'espai vertical disponible.
- **FER:** Utilitza etiquetes clares i concises (entre una i tres paraules) per indicar l'estat de cada pas.
- **NO FER:** No utilitzis etiquetes molt llargues i excessivament descriptives. Si l'estat del procés requereix una explicació més detallada, considera col·locar aquesta informació addicional maquetada directament a la pàgina.
- **FER:** Sempre que un estat estigui pendent d'una acció de l'usuari, acompanya el rastrejador d'estat amb un avís que indiqui l'acció que ha de fer.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG):
- **Orientació (AA)** (1.3.4): el contingut s'adapta a les diferents orientacions de la pantalla, com ara vertical o horitzontal, cosa que permet visualitzar el contingut. [CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Ús del color (A)** (1.4.1): el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a indicar els diferents estats es fan servir icones representatives. [CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA)** (1.4.3): els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA)** (1.4.4): excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA)** (1.4.11): els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)

## Implementació (component web)

### `<status-tracker-component>`
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat (lloc) |
|---|---|---|---|---|---|
| `customIdLink` | `custom-id-link` | Identificador personalitzat de l'enllaç (PDF: "URL de l'enllaç") | string | `undefined` | Opcional |
| `modeLink` | `mode-link` | Tipus d'enllaç intern o extern. Opcions: `external`, `internal`. | string | `undefined` | Opcional |
| `showLink` | `show-link` | Mostra o amaga l'enllaç. | boolean | `true` | Opcional |
| `showMore` | `show-more` | Mostra o amaga el botó "mostra més". | boolean | `false` | Opcional |
| `showTitle` | `show-title` | Mostra o amaga el títol i la icona informativa. | boolean | `true` | Opcional |
| `showTooltip` | `show-tooltip` | Mostra o amaga el tooltip de la icona informativa. | boolean | `true` | Opcional |
| `statuses` | `statuses` | Llista d'estats disponibles. Accepta array d'objectes o string JSON. | string (objecte) | `undefined` | Obligatori |
| `textEtiqueta` | `text-etiqueta` | Text del títol. | string | `undefined` | Opcional |
| `textInfoTooltip` | `text-info-tooltip` | Text del tooltip. | string | `undefined` | Opcional |
| `textLink` | `text-link` | Text de l'enllaç. | string | `undefined` | Opcional |

[discrepància: els valors per defecte de `showLink` (`true`) i `showTooltip` (`true`) al PDF difereixen dels valors per defecte de les propietats Figma (Show Link = False, Show Tooltip = False)]

**Variants**

| Propietat | Valors | Defecte |
|---|---|---|
| `modeLink` | `external` `internal` | - |

**Props que accepten JSON: array `statuses`**

| Propietat | Descripció | Atribut | Obligatorietat | Tipus |
|---|---|---|---|---|
| `description` | Descripció del pas | `description` | Opcional | String |
| `number` | Número del pas | `number` | Obligatori | String |
| `state` | Estat. Valors possibles: `done`, `current`, `current-alert`, `pending`, `expired` | `state` | Obligatori | String |
| `statusName` | Nom del pas | `statusName` | Obligatori | String |

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `blurLink` | Es llança cada cop que es treu el focus en un enllaç | - | `link-component` |
| `focusLink` | Es llança cada cop que es fa focus en un enllaç | - | `link-component` |
| `linkEmit` | Es llança cada cop que es fa clic en un enllaç | `id` | `link-component` |
| `toggle` | Indica si el botó està en mode col·lapsat o no | - | `show-more-component` |
| `statusChanged` | Emet el número actual del pas després que hagi canviat (`CustomEvent<number>`). | `number` | `status-tracker-component` |

**Mètodes públics**

| Mètode | Descripció | Paràmetre |
|---|---|---|
| `changeStatus(change: number)` | Canvia l'estat del pas. | `change` |

**Depèn de:** `link-component` ([Enllaços](component-enllacos.md)), `show-more-component` ([Mostra més](component-mostra-mes.md)), `tooltip-component` ([Indicador de funció](component-indicador-de-funcio.md)).

**Exemple d'ús**

```html
<!-- /index.html -->
<status-tracker-component
  custom-id-link='status-link-1'
  statuses='[
    { "number": 1, "statusName": "Pas 1", "state": "done", "description": "Descripció 1" },
    { "number": 2, "statusName": "Pas 2", "state": "current", "description": "Descripció 2" },
    { "number": 3, "statusName": "Pas 3", "state": "pending", "description": "Descripció 3" },
    { "number": 3, "statusName": "Pas 4", "state": "pending" },
    { "number": 4, "statusName": "Pagat", "state": "pending" }
  ]'
  text-etiqueta="Títol"
  text-info-tooltip="Títol info tooltip"
  text-link="Enllaç"
  mode-link="external"
  show-more="true"
  show-link="true"
  show-title="true"
  show-tooltip="true"
></status-tracker-component>
```

Exemple d'instància (PDF):

```html
<status-tracker-component
custom-id-link="texto-ejemplo"
mode-link="external"
show-link=true
show-more=false
show-title=true
show-tooltip=true
statuses="texto-ejemplo"
text-etiqueta="texto-ejemplo"
text-info-tooltip="texto-ejemplo"
text-link="texto-ejemplo"
></status-tracker-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 8.6.0 | 9.1.0 | 9 febrer, 2026 | Disseny: s'eliminen truncats i alçades màximes de títols i textos. |
| 5.0.0 | 9.1.0 | 6 febrer, 2026 | Desenvolupament: adaptacions d'accessibilitat pel que fa a mides de font extra gran i augment de pantalla |
| 5.0.0 | 7.0.0 | 24 octubre, 2025 | Desenvolupament: resolució de problemes |
| 5.0.0 | 6.2.1 | 3 octubre, 2025 | Desenvolupament: nova propietat afegida o eliminada |
| 5.0.0 | 6.0.0 | 3 juliol, 2025 | Desenvolupament: resolució de problemes |
| 5.0.0 | 1.0.0 | 10 juny, 2025 | Disseny: s'han afegit tooltip al títol, enllaç i descripció per a cada pas. També s'han definit valors mínims (296) i màxims (436). |
| 2.3.0 | 1.0.0 | 31 gener, 2025 | Sense canvis |
| 2.2.0 | 0.1.1 | 20 gener, 2025 | Disseny: s'han creat els combinats del component en versions no expansible i expansible, amb opcions de col·lapsat, expandit i canvi de posició en l'estat expandit. |
| 2.1.0 | 0.1.1 | 04 desembre, 2024 | Sense canvis |
| 2.0.0 | 0.1.0 | 02 desembre, 2024 | Sense canvis |
| 1.1.0 | 0.1.0 | 22 novembre, 2024 | Sense canvis |
| 1.1.0 | 0.0.4 | 18 novembre, 2024 | Sense canvis |
| 1.0.0 | 0.0.3 | 1 novembre, 2024 | Disseny, desenvolupament i documentació del component |

## Vegeu també
- [Pas a pas](component-pas-a-pas.md): per guiar l'usuari a través d'un procés complex.
- [Enllaços](component-enllacos.md)
- [Mostra més](component-mostra-mes.md)
- [Indicador de funció](component-indicador-de-funcio.md)
