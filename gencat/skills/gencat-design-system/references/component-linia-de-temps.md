# Línia de temps (Timeline)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/24ebe2 · Web component: `<timeline-component>` (paquet core) · Font actualitzada el 2026-10-15 · Extret el 2026-10-28

## Què és i quan usar-lo
Indicador visual que s'utilitza per mostrar l'estructura d'un procés seqüencial i cronològic de forma clara i ordenada, sense ser interactiu. No serveix per navegar, sinó per orientar l'usuari i donar context sobre en quin punt del procés es troba i quin pas vindrà després.

Quan s'utilitza: quan cal mostrar el recorregut complet d'un procés de forma cronològica, però sense demanar una acció per part de l'usuari.

## Quan NO usar-lo / alternatives
- Quan l'usuari ha de realitzar una acció per avançar dins d'un procés (vegeu [Pas a pas](component-pas-a-pas.md)).
- Quan el procés no és lineal o no té un ordre definit.
- Per a informació en temps real sobre el progrés, els problemes i els resultats relacionats amb aquestes activitats (vegeu [Rastrejador d'estat](component-rastrejador-d-estat.md)).
- Si el procés únicament té un pas.
- En casos on l'usuari hagi de navegar entre passos; si el procés requereix interacció, cal utilitzar un component de navegació específic.

## Anatomia
Figma: Anatomia (línia de temps amb passos; cada pas té informació (data i etiqueta), cos (descripció i enllaç/botó/mostra més), línia i indicador de pas).

## Variants, tipus i estats

### Propietats del component línia de temps

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Extra Large - Large / Medium - Small | - |
| Step indicator | True / False | True |

### Propietats de l'ítem (pas)

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Extra Large - Large / Medium - Small | - |
| Available | True / False | True |
| Show step indicator | True / False | False |
| Show Line | True / False | True |
| Show information | True / False | True |
| Show Body | True / False | True |

Variants Figma del pas (`_Timeline step`): Show Body = False | True; Show line = True | False; Show Step Indicator = False | True; Show Date = True | False; Show Tag = False | True; Breakpoint = Extra Large - Large | Medium - Small; Available = True | False.

### Propietats del cos

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Type | Link / Button / Show more | - |
| Show link | True / False | True |
| Show description | True / False | True |

Variants Figma (`_Content container`): Show Description = True | False; Show link = True | False; Type = Link | Button | Show more.

### Propietats de la informació

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Show Tag | True / False | False |
| Show Date | True / False | True |

Variants Figma (`_Information`): Show Tag = True | False; Show Date = True | False.

### Propietats de l'indicador del pas

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Type | Current / Following | - |
| Pointer alignment | Right / Bottom | - |

Variants Figma (`_Step indicator`): Type = Current | Following; Pointer alignment = Right | Bottom.

## Comportament i interacció
- **Passos disponibles:** la línia de temps pot mostrar fins a **12 passos**, encara que es recomana utilitzar el mínim possible. Aquests es troben ocults en el component i es poden activar manualment.
- **Indicador de pas:** es mostra només en el pas que correspon al moment actual. Si entre dos passos hi ha un període d'espera que no es reflecteix al component, s'afegeix un indicador de 'pròxim' per informar de quin serà el següent pas que podrà fer l'usuari. Si el cas d'ús no necessita cap indicador de pas, desactiva, per al punt de tall *Extra Large - Large*, la propietat "Step indicator". El punt de tall *Medium - Large* [sic; a verificar: probablement Medium - Small] funciona en tots dos casos amb la propietat activada.
- **Etiquetes:** serveixen per indicar l'estat en què es troba el pas. Principalment s'utilitzen els estats "en termini", "fora de termini" i "disponible" (per aquells passos on, per exemple, l'usuari pot consultar una llista publicada, però no ha de realitzar cap procés).
- Punts de tall: Extra Large - Large i Medium - Small (variants Figma Extra large i Small).
- Des de la v9.2.0 s'eliminen els truncats i màxims per fer adaptacions en vertical sense límit.

## Contingut i microcopy
- Dates: format dd/mm/aaaa.
- Textos breus i descriptius per cada pas. Exemples a l'exemple de codi: "Pas 1", "Descripció del pas 1", "Enllaç al pas 1", "Botó del pas 2".

## Bones pràctiques

### Claredat i simplicitat
- **FER:** Mostra només les etapes necessàries per entendre el procés.
- **NO FER:** No incloguis massa passos o informació excessiva que pugui confondre l'usuari.
- **FER:** Utilitza textos breus i descriptius per cada pas.
- **NO FER:** Evita textos massa llargs o tècnics.
- **FER:** Assegura't que l'ordre dels elements sigui lògic i fàcil de seguir.
- **FER:** Redueix el contingut textual al mínim necessari: si es pot evitar la descripció, millor.
- **FER:** Utilitza el botó "Mostrar més" només quan sigui estrictament necessari i evita que aparegui en tots els passos.

### Context i orientació
- **FER:** Indica clarament en quin punt del procés es troba l'usuari.
- **FER:** Mostra quins passos venen abans i després per oferir una visió general del recorregut.
- **NO FER:** No utilitzis només el color per indicar l'estat (ex: actual, completat, pendent), ja que això pot generar problemes d'accessibilitat.

### Dates
- **FER:** Introdueix les dates sempre en el mateix format (dd/mm/aaaa).

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG):
- **1.4.1 Ús del color (A):** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. El color del badge sempre és el mateix; no hi ha un canvi d'aquest per indicar alguna informació. (https://www.w3.org/Translations/WCAG22-ca/#use-of-color · https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **1.4.3 Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. (https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum · https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **1.4.4 Canvia la mida del text (AA):** excepte subtítols i imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. (https://www.w3.org/Translations/WCAG22-ca/#resize-text · https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **1.4.11 Contrast d'elements no textuals (AA):** els elements gràfics presenten un contrast mínim de 3:1. (https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast · https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **2.1.1 Teclat (A):** tota la funcionalitat del contingut (navegar pels enllaços) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. (https://www.w3.org/Translations/WCAG22-ca/#keyboard · https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **2.4.7 Focus visible (AA):** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. (https://www.w3.org/Translations/WCAG22-ca/#focus-visible · https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

## Implementació (component web)

### `<timeline-component>`
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Obligatorietat (lloc) | Tipus | Per defecte (PDF) |
|---|---|---|---|---|---|
| `showStepIndicator` | `show-step-indicator` | Mostra l'etiqueta que a l'element que s'indiqui. (PDF: mostra o amaga aquest element) | Opcional | Boolean | `true` |
| `steps` | `steps` | Array que conté la informació de cada step de la llista. (PDF: valor del pas actual del stepper) | Obligatori | String (array) | `[]` |
| `textStepIndicatorCurrent` | `text-step-indicator-current` | Text visible al component (indicador "Actual"). | (no consta al lloc) | string | `` (buit) |
| `textStepIndicatorNext` | `text-step-indicator-next` | Text visible al component (indicador "Pròxim"). | (no consta al lloc) | string | `` (buit) |

[discrepància: `textStepIndicatorCurrent` i `textStepIndicatorNext` consten al PDF però no a la taula de la pàgina del lloc]

**Props que accepten JSON: `steps`** (array d'objectes)

| Propietat | Descripció | Atribut | Obligatorietat | Tipus |
|---|---|---|---|---|
| `available` | Mostrar si l'step està disponible. | `available` | Opcional | Boolean |
| `date` | Data. | `date` | Opcional | string |
| `description` | Descripció que acompanya la pestanya | `description` | Obligatori | String |
| `isCurrent` | Mostrar si l'step és l'actiu. | `isCurrent` | Opcional | Boolean |
| `link` | Enllaç de la pestanya | `link` | Opcional | String (JSON) |
| `showBody` | Mostrar el body de l'step (descripció i enllaços o botons). | `showBody` | Opcional | Boolean |
| `showDate` | Mostrar la data de la informació. | `showDate` | Opcional | Boolean |
| `showDescription` | Mostrar la descripció. | `showDescription` | Opcional | Boolean |
| `showInformation` | Mostra les dades d'informació (data i tags). | `showInformation` | Opcional | Boolean |
| `showLink` | Mostra l'enllaç de l'step. | `showLink` | Opcional | Boolean |
| `showMore` | Mostrar l'opció mostrar més per col·lapsar la descripció. | `showMore` | Opcional | Boolean |
| `showTag` | Mostrar l'etiqueta de la informació. | `showTag` | Opcional | Boolean |
| `stepIndicatorCurrent` | Mostra l'indicador "Actual". | `stepIndicatorCurrent` | Opcional | Boolean |
| `stepIndicatorNext` | Mostra l'indicador "Pròxim". | `stepIndicatorNext` | Opcional | Boolean |
| `title` | Títol que acompanya la pestanya | `title` | Obligatori | String |
| `typeTag` | Etiqueta de l'step | `typeTag` | Opcional | String |

Objecte `link`:

| Propietat | Descripció | Atribut | Obligatorietat | Tipus |
|---|---|---|---|---|
| `attributes` | Objecte amb els atributs de l'enllaç. | `attributes` | Obligatori | string (JSON) |
| `type` | Indica el tipus de link: Botó, Enllaç o 'Mostrar més'. | `type` | Obligatori | string |

Objecte `attributes`:

| Propietat | Descripció | Atribut | Obligatorietat | Tipus |
|---|---|---|---|---|
| `customId` | Identificador personalitzat de l'enllaç | `custom-id` | Opcional | string |
| `mode` | Permet configurar si l'enllaç és extern o intern; si és extern el target serà blank i apareixerà icona; si és intern, el target serà self i l'enllaç no tindrà icona | `mode` | Opcional | string |
| `text` | Text que es mostra dins de l'enllaç. | `text` | Obligatori | string |

**Variants**

Variants de l'objecte `link`:

| Propietat | Opcions |
|---|---|
| `type` | `link` `button` |

Variants de `typeTag`:

| Propietat | Opcions | Valor |
|---|---|---|
| `typeTag` | `1` `2` `3` | `1`: En termini · `2`: Fora de termini · `3`: Disponible |

**Esdeveniments:** el PDF indica "Sense events declarats" per a `timeline-component`; la pàgina del lloc llista els heretats dels components fills:

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `blurButton` | Es llança cada cop que es treu el focus en un botó. | - | `button-component` |
| `focusButton` | Es llança cada cop que es fa focus en un botó. | - | `button-component` |
| `handlerClick` | Es llança cada cop que es fa clic en un botó i com a paràmetre conté les dades de l'esdeveniment. | `id` | `button-component` |
| `blurLink` | Es llança cada cop que es treu el focus en un enllaç | - | `link-component` |
| `focusLink` | Es llança cada cop que es fa focus en un enllaç | - | `link-component` |
| `linkEmit` | Esdeveniment llançat en fer clic sobre el link | `id` | `link-component` |
| `toggle` | Indica si el botó de veure més està en mode col·lapsat o no. | - | `toggle` |

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<timeline-component
  steps='[
    {
      "title": "Pas 1",
      "description": "Descripció del pas 1",
      "date": "01/01/2023",
      "typeTag": "2",
      "link": {
        "type": "link",
        "attributes": {
          "text": "Enllaç al pas 1",
          "mode": "external"
        }
      },
      "stepIndicatorCurrent": true,
      "stepIndicatorNext": false,
      "showMore": true,
      "showInformation": true,
      "showDescription": true,
      "showBody": true,
      "showTag": true,
      "showDate": true,
      "showLink": true,
      "available": true
    },
    {
      "title": "Pas 2",
      "description": "Descripció del pas 2",
      "isCurrent": true,
      "date": "02/01/2023",
      "typeTag": "1",
      "link": {
        "type": "button",
        "attributes": {
          "text": "Botó del pas 2"
        }
      },
      "stepIndicatorCurrent": true,
      "stepIndicatorNext": false,
      "showMore": false,
      "showInformation": true,
      "showDescription": true,
      "showBody": true,
      "showTag": true,
      "showDate": true,
      "showLink": true,
      "available": true
    },
    {
      "title": "Pas 3",
      "description": "Descripció del pas 3. Aquest pas és opcional i pot no ser necessari en tots els casos.  Per exemple, si el procés només té dos passos, aquest tercer pas pot ser omès. També pot ser que el tercer pas sigui un pas de revisió o confirmació. En aquest cas, el tercer pas pot ser opcional i només es mostrarà si l`usuari ha completat els passos anteriors correctament. Descripció del pas 3. Aquest pas és opcional i pot no ser necessari en tots els casos.  Per exemple, si el procés només té dos passos, aquest tercer pas pot ser omès. També pot ser que el tercer pas sigui un pas de revisió o confirmació. En aquest cas, el tercer pas pot ser opcional i només es mostrarà si l`usuari ha completat els passos anteriors correctament.",
      "date": "03/01/2023",
      "typeTag": "3",
      "stepIndicatorCurrent": true,
      "stepIndicatorNext": false,
      "showMore": true,
      "showInformation": true,
      "showDescription": true,
      "showBody": true,
      "showTag": true,
      "showDate": true,
      "showLink": true,
      "available": false
    }
  ]'
  show-step-indicator="true"
></timeline-component>
```

**Exemple d'instància (PDF)**

```html
<timeline-component
show-step-indicator=true
steps='[]'
text-step-indicator-current=''
text-step-indicator-next=''
></timeline-component>
```

**Depèn de:** `button-component` ([Botons](component-botons.md)), `link-component` ([Enllaços](component-enllacos.md)), `show-more-component` ([Mostra més](component-mostra-mes.md)), `tag-component` ([Etiquetes](component-etiquetes.md)).

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 9.1.0 | 11.0.0 | 11 setembre, 2026 | Desenvolupament: les rutes relatives a absolutes s'han corregit |
| 9.1.0 | 11.0.0 | 19 juny, 2026 | Desenvolupament: s'elimina el truncat en descripcions llargues quan showMore és false |
| 9.1.0 | 9.4.0 | 17 abril, 2026 | Desenvolupament: s'han corregit errors d'accessibilitat. |
| 9.1.0 | 9.2.0 | 20 març, 2026 | Disseny: eliminació de truncats i màxims per fer adaptacions en vertical sense límit. |
| 8.0.0 | 9.2.0 | 27 febrer, 2025 | Desenvolupament: es crea la propietat customId per a l'enllaç |
| 8.0.0 | 6.2.1 | 3 octubre, 2025 | Desenvolupament: nova propietat afegida o eliminada |
| 8.0.0 | 6.1.0 | 12 setembre, 2025 | Disseny: es modifiquen estils de text del step indicator i el timeline step. Desenvolupament: resolució de problemes |
| 5.0.0 | 5.0.0 | 10 juny, 2025 | Disseny: s'enllaça correctament la booleana per mostrar / treure la data; s'ajusta l'espaiat quan es mostra l'indicador de posició. |
| 4.1.0 | 5.0.0 | 9 juny, 2025 | Desenvolupament del component |
| 4.1.0 | - | 19 maig, 2025 | Disseny i documentació del component. |

## Vegeu també
- [Pas a pas](component-pas-a-pas.md): per guiar l'usuari a través d'un procés complex.
- [Rastrejador d'estat](component-rastrejador-d-estat.md): per monitorar, informar i mostrar l'estat de tasques, projectes, etc.
