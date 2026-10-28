# Llista d'enllaços (Link list)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/720e0b · Web component: `<link-list-component>` (paquet core) · Font actualitzada el 2026-10-15 · Extret el 2026-10-28

## Què és i quan usar-lo
Agrupacions d'enllaços.

S'utilitzen per a llistes d'enllaços que permeten als usuaris **navegar a diferents pàgines** o quan es proporciona una llista de **recursos o referències**.

### Llista d'enllaços
Quan es vol oferir una llista de diversos enllaços.

### Llista d'enllaços avançada
- **Llista d'enllaços destacats:** quan es vol oferir diversos enllaços de major importància sota una mateixa etiqueta o categoria.
- **Llista d'enllaços relacionats:** quan es vol oferir diversos enllaços relacionats sota una mateixa etiqueta o categoria.

## Quan NO usar-lo / alternatives
- No utilitzis llistes d'enllaços quan l'usuari necessiti escollir entre seccions o categories: utilitza targetes de navegació ([Targetes](component-targetes.md)).
- No utilitzis la llista d'enllaços quan sigui necessari un suport visual com icones, imatges o accions destacades: utilitza targetes de navegació.
- Per mostrar un únic enllaç, utilitza el component [Enllaços](component-enllacos.md) (la llista avançada requereix un mínim de dos enllaços).

## Anatomia
La font només mostra imatges d'anatomia per a la llista d'enllaços i per a la llista d'enllaços avançada.

Variant Figma de la llista avançada: Advanced link list [Show Column 02 = True, Show Column 03 = True, Show Show more button = True, Breakpoint = Extra Large Column Fixed, Type = Highlighted, Full width = True].

## Variants, tipus i estats

### Llista d'enllaços

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Size | Large / Medium / Small | Medium |
| Position | Vertical / Horizontal | Vertical |
| Show Description | True / False | False |
| Show related content link | True / False | False |

Variant Figma: Link list [Show Related content link = False, Size = Large, Position = Vertical].

### Llista d'enllaços avançada

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Extra Large Column Fixed / Extra Large Column Variable / Large / Medium / Small | Medium |
| Type | Highlighted / Related | Highlighted |
| Full width | True / False | True |

- **Mida completa (Full width):** utilitza la mida completa quan el component sigui una secció individual de la pàgina. Si el llistat s'inclou dins d'una secció en què conviu amb altres elements (text, imatges, altres components, etc.), utilitza la versió sense mida completa.
- Els **enllaços** utilitzats dins del component **poden ser tant interns com externs**.

## Mides i espaiats
- **Medium (mitjana):** mida predefinida; s'utilitza en la gran **majoria de situacions i contextos**.
- **Small (petita):** reservada per a **espais reduïts** com el peu de pàgina.
- **Large (gran):** reservada per a espais on cal **equilibrar el pes** amb la resta d'elements.
- Disposició per **defecte** en **vertical**; la disposició horitzontal s'usa en casos concrets com el peu de pàgina.
- Llista avançada: màxim de **dotze enllaços** distribuïts en un màxim de **tres columnes** segons el punt de tall o la col·locació a la pàgina. Es poden distribuir en una o diverses files. Si el nombre d'enllaços no es pot distribuir uniformement en totes les columnes, la primera columna és la que té més enllaços.
- Amb la mida petita, mostra un **màxim de 6 enllaços** quan està replegat.
- Màxim de 640 px al component Link List Item (historial de versions).
- Llistat d'enllaços en una pàgina de detall **dins del contingut**: **màxim de dues columnes** als punts de tall Extra Large Column Fixed i Variable, i **màxim d'una columna** al punt de tall Large i inferiors.

## Comportament i interacció

### Adaptació responsiva
- El contingut de la llista s'adapta a la mida de pantalla o al contingut segons el cas.
- La versió **full width** (amplada completa) ocupa tot **l'espai de pantalla**; la versió sense full width respecta els marges del punt de tall si utilitza les tres columnes disponibles.
- La versió per dins de seccions es pot combinar amb la versió d'enllaços relacionats per aprofitar l'espai disponible.

### Prototipat
Per utilitzar el comportament desplegable de la versió per a mòbil cal dissenyar dues pantalles: una amb el component utilitzant la versió replegada del botó i una segona amb el botó desplegat i mostrant més enllaços.

## Bones pràctiques

### Elements decoratius
- **FER:** Utilitza-les sense vinyetes o altres elements decoratius.
- **NO FER:** No les utilitzis amb vinyetes o elements decoratius.

### Mida
- **FER:** Utilitza tots els elements amb la mateixa mida d'enllaç.
- **NO FER:** No utilitzis diferents mides d'enllaç.

### Diverses llistes seguides
- **FER:** Si hi ha dues o més llistes seguides que no disposen de frase introductòria, inclou un títol propi per diferenciar els continguts. Aquest títol depèn de la maquetació de la pàgina.

### Enllaços o targetes de navegació
- **FER:** Utilitza llista d'enllaços quan aquests no formen part d'una mateixa secció o categoria, sinó només accessos a informació específica.
- **NO FER:** No utilitzis llistes d'enllaços quan l'usuari necessiti escollir entre seccions o categories. En aquest cas, utilitza targetes de navegació.
- **NO FER:** No utilitzis la llista d'enllaços quan sigui necessari utilitzar un suport visual com icones, imatges o accions destacades. En aquest cas, utilitza targetes de navegació.
- **FER:** Utilitza la llista d'enllaços quan sigui necessari incloure diferents arxius per descarregar.
- Més informació sobre bones pràctiques a la secció d'[Enllaços](component-enllacos.md).

## Accessibilitat
Pautes WCAG 2.2:
- **Contrast mínim (AA) – 1.4.3:** contrast d'almenys 4,5:1 als elements textuals; els inactius o deshabilitats en són excepció. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA) – 1.4.4:** el text es pot canviar de mida fins al 200 % sense pèrdua de contingut ni de funcionalitat (excepte subtítols i imatges de text). [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA) – 1.4.11:** elements gràfics amb contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A) – 2.1.1:** tota la funcionalitat (navegar pels enllaços) es pot operar amb teclat sense requerir temps específics per a pulsacions. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Focus visible (AA) – 2.4.7:** la navegació amb teclat pels elements és visible a través d'un rectangle. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

## Tokens
- S'aplica un token específic per al fons dels enllaços destacats (versió Github 9.1.0, 29 maig 2026); la font no en dona el nom.
- Es canvia el color de la descripció del Link List Item a `label-default`.

## Implementació (component web)

### `<link-list-component>`

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Obligatori | Per defecte |
|---|---|---|---|---|---|
| `fullWidth` | `full-width` | Indica al component si ha d'ocupar l'amplada completa de la pantalla o si, per contra, el seu contenidor pare tindrà paddings o margins. | boolean | Opcional | `true` |
| `linkList` | `link-list` | Array que conté la informació de cada enllaç de la llista. Accepta array d'objectes o string JSON. | string (JSON) | Obligatori | `undefined` |
| `mode` | `mode` | Variant visual: permet seleccionar link-list de tipus highlighted o related. Opcions: `highlighted`, `related`. | string | Obligatori | `highlighted` |
| `titleList` | `title-list` | Títol de la llista. | string | Obligatori | `undefined` |

**Props que accepten JSON: propietats dels elements de l'array `linkList`**

| Propietat | Atribut | Descripció | Tipus | Obligatori |
|---|---|---|---|---|
| `customId` | `customId` | Identificador personalitzat de l'enllaç. | string | Opcional |
| `mode` | `mode` | Indica si l'enllaç és extern o intern. Valors: `external` o `internal`. | string | Obligatori |
| `text` | `text` | Text de l'enllaç. | string | Obligatori |

**Variants**

| Propietat | Valor predeterminat | Opcions |
|---|---|---|
| `mode` | `highlighted` | `highlighted` `related` |

**Esdeveniments** (el PDF declara que el component no té esdeveniments propis; la pàgina llista els dels components fills)

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `blurButton` | Es llança cada cop que es treu el focus d'un botó. | - | `button-component` |
| `focusButton` | Es llança cada cop que es fa focus en un botó. | - | `button-component` |
| `handlerClick` | Es llança cada cop que es fa clic en un botó; com a paràmetre conté les dades de l'esdeveniment. | id | `button-component` |
| `blurLink` | Es llança cada cop que es treu el focus d'un enllaç. | - | `link-component` |
| `focusLink` | Es llança cada cop que es fa focus en un enllaç. | - | `link-component` |
| `linkEmit` | Es llança en fer clic sobre el link. | `id` | `link-component` |
| `toggle` | Indica si el botó està en mode col·lapsat o no. | - | `show-more-component` |

**Depèn de:** `link-component` ([Enllaços](component-enllacos.md)), `show-more-component` ([Mostra més](component-mostra-mes.md)).

**Exemple d'ús (pàgina)**

```html
<!-- /index.html -->
<link-list-component 
      link-list='[
        {"text":"Google","mode":"external"},
        {"text":"Google","mode":"external"},
        {"text":"Google","mode":"external"}
      ]'
      title-list="Títol"
      mode="highlighted"
      full-width="false"
    ></link-list-component>
```

**Exemple d'instància (PDF)**

```html
<link-list-component
full-width=true
link-list="texto-ejemplo"
mode='highlighted'
title-list="texto-ejemplo"
></link-list-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.0.0 | 11.0.0 | 19 juny, 2026 | Desenvolupament: es canvia el nom de la variable del background; s'eliminen els min i max width que trencaven la vista en fer zoom i augmentar la mida del text. |
| 12.0.0 | 9.1.0 | 29 maig, 2026 | Disseny: s'aplica el token específic pel fons dels enllaços destacats. |
| 9.0.0 | 9.1.0 | 10 febrer, 2026 | Disseny: s'eliminen els truncats del títol. |
| 8.1.0 | 9.1.0 | 27 febrer, 2026 | Desenvolupament: es crea la propietat `customId`. |
| 8.1.0 | 9.1.0 | 6 febrer, 2026 | Desenvolupament: adaptacions d'accessibilitat per a mides de font extra grans i augment de pantalla. |
| 8.1.0 | 6.2.1 | 6 octubre, 2025 | Disseny: màxim de 640 px al component Link List Item; estil de text a la descripció del Link List Item i color de la descripció a `label-default`. Desenvolupament: nova propietat afegida o eliminada. |
| 8.0.0 | 6.0.1 | 12 setembre, 2025 | Disseny: l'estil del titular de la llista d'enllaços avançada incrustada al contingut passa de XS a SM; la icona passa a la mida medium. |
| 5.0.0 | 6.0.1 | 28 juliol, 2025 | Desenvolupament: resolució de problemes. |
| 5.0.0 | 5.0.0 | 10 juny, 2025 | Disseny: canvi de color del fons de la llista d'enllaços destacada. |
| 4.1.0 | 5.0.0 | 9 juny, 2025 | Desenvolupament: resolució de problemes. |
| 4.1.0 | 4.0.1 | 19 maig, 2025 | Desenvolupament del component. |
| 3.0.0 | No aplica | 31 març, 2025 | Disseny i documentació del component. |

## Vegeu també
- [Enllaços](component-enllacos.md): per facilitar la navegació entre parts del contingut o funcionalitats.
- [Llista](component-llista.md): per a agrupacions de contingut relacionat.
- [Mostra més](component-mostra-mes.md)
- [Targetes](component-targetes.md)
