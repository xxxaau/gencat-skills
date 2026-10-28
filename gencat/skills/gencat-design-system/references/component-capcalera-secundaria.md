# Capçalera secundària (Secondary header)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/12e0d0 · Web component: `<secondary-header-component>` (paquet core) · Font actualitzada el 2026-10-14 · Extret el 2026-10-28

## Què és i quan usar-lo
Component que proporciona context i estructura a les pàgines secundàries d'una pàgina web pública de caràcter informatiu no transaccional.

S'utilitza per a presentar pàgines de contingut que es troben en la navegació d'un lloc web. És un element situat directament sota el menú de navegació en pàgines que no són la d'inici. És més discret i se centra a proporcionar context o informació bàsica per orientar l'usuari en aquella secció.

### Variants i quan s'utilitza cadascuna
**1. Temàtica** (`Theme`)
- Per a pàgines de segon nivell en la navegació d'un lloc web.
- S'utilitza amb imatge o sense en funció de si es pot utilitzar una imatge prou representativa del contingut de la pàgina.
- S'utilitza sempre que hi ha un element a la columna esquerra de la pàgina.

**2. Sense imatge** (`Without image`)
- S'utilitza per a pàgines de segon nivell en la navegació d'un lloc web.
- S'utilitza sobretot per a pàgines on el titular és molt llarg, com per exemple pàgines de tràmits.

**3. De detall** (`Detail`)
- Per a pàgines de tercer i quart nivell en la navegació d'un lloc web.
- S'utilitza quan no hi ha cap element a la columna esquerra de la pàgina.

Per veure com aplicar cadascuna de les variants, consulta els [exemples d'ús](exemple-exemples-d-us.md).

## Quan NO usar-lo / alternatives
- Tant la capçalera secundària temàtica com la de detall no s'utilitzen en pàgines d'inici. En aquest cas usa el [panell destacat](component-panell-destacat.md).
- No s'utilitza en pàgines transaccionals.

## Anatomia
La capçalera secundària consta de títol, imatge opcional i fil d'Ariadna opcional (Figma `Subheader` [Show Breadcrumbs, Show Image, Breakpoint, Type] i `Capçalera secundària` [Type, Breakpoint]). Variants: 1. Temàtica; 2. Detall; 3. Sense imatge.

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Type | Theme / Detail / Without image | Theme |
| Breakpoint | Small / Medium / Large / Extra Large Column Variable / Extra Large Column Fixed | Extra Large Column Fixed |
| Show Image | True / False | True |
| Breadcrumbs | True / False | True |

Variants Figma: Show Breadcrumbs = True | False; Show Image = True | False; Breakpoint = Extra Large CF (i la resta de punts de tall); Type = Theme | Detail | Without image.

Punts de tall: es mostren les variants 1. Temàtica, 2. Detall i 3. Sense imatge per a cada punt de tall.

### Fil d'Ariadna
- 1. Temàtica: amb fil d'Ariadna / sense fil d'Ariadna.
- 2. Sense imatge: amb fil d'Ariadna / sense fil d'Ariadna.

### Comportament del text
- 1. Temàtica: el títol té un límit de 2 línies.
- 2. Sense imatge: el títol del contenidor s'adapta al text.

## Mides i espaiats
- Versió Figma 8.6.0 / Github 6.2.1: marge superior i posterior de 16 píxels a la variant temàtica large; el comportament és en *hug* per alçades; la imatge s'adapta a l'alçada del contenidor.
- S'ha corregit l'alineació dels laterals del component en punts de tall superiors a 1440px.
- Alineació central del títol quan no hi ha imatge ni breadcrumbs a les versions Medium i Small, i a la versió Extra Large Column Variable.
- El títol de la capçalera temàtica sense imatge ocupa tot l'espai disponible.
- El text del nivell actual del fil d'Ariadna es comporta en *fill* perquè es trunqui si no hi ha espai disponible.

## Comportament i interacció
- Ubicació: directament sota el menú horitzontal.
- El títol té un límit de 2 línies a la variant temàtica; a la variant sense imatge el contenidor s'adapta al text.
- A pàgines de primer i segon nivell es mostra només el títol i la imatge si es requereix.
- Si la intervenció d'IA afecta la imatge de la capçalera secundària, l'[etiquetatge d'IA](component-etiquetatge-d-ia.md) se situa sobre la imatge, a la cantonada inferior dreta.

## Bones pràctiques

**Ubicació**
- **FER:** Utilitza la capçalera secundària just inferiorment al menú horitzontal.
- **NO FER:** No utilitzis la capçalera secundària inferiorment al contingut de la pàgina.

**Imatges**
- **FER:** La imatge ha de ser rellevant i aportar context (per exemple, mostrar una escena relacionada amb el contingut de la pàgina). Si no hi ha una imatge clara que es pugui utilitzar en aquell context, no en facis servir cap.
- **NO FER:** No utilitzis imatges poc rellevants o decoratives que no afegeixen valor. En aquest cas, opta per utilitzar la capçalera sense imatge.

**Text**
- **FER:** El títol ha de ser concís i descriptiu, indicant exactament quin contingut trobarà l'usuari.
- **NO FER:** Evita posar títols redundants o duplicats i que no aportin valor.

**Fil d'Ariadna**
- **FER:** A pàgines de primer i segon nivell es mostra només el títol i la imatge si es requereix.
- **NO FER:** A pàgines de primer i segon nivell no s'ha d'introduir el fil d'Ariadna si es poden trobar a la navegació principal del lloc web.

## Accessibilitat

### Pautes WCAG
- **Orientació (AA)**: el contingut de l'àrea de text s'adapta a les diferents orientacions de la pantalla, vertical o horitzontal, cosa que permet visualitzar el contingut. [1.3.4 Orientació - CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Contrast mínim (AA)**: els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. [1.4.3 Contrast mínim - CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA)**: excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [1.4.4 Canvia la mida del text - CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Espaiat del text (AA)**: quan es desenvolupa contingut utilitzant llenguatges de marcatge que permeten aplicar les propietats d'estil de text, no es perd cap contingut ni funcionalitat si s'ajusten les propietats següents: alçada de línia (interlineat) de com a mínim 1,5 vegades la mida de la lletra; espaiat entre els paràgrafs de com a mínim dues vegades la mida de la lletra; espaiat entre lletres (tracking) de com a mínim 0,12 vegades la mida de la lletra; espaiat entre paraules de com a mínim 0,16 vegades la mida de la lletra. [1.4.12 Espaiat del text - CAT](https://www.w3.org/Translations/WCAG22-ca/#text-spacing) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/text-spacing)

### Pautes aplicables a imatges
- **Text alternatiu per imatges (A)**: cal proporcionar un text alternatiu (atribut alt) per a la imatge de fons. [1.1.1 Contingut no textual - CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-content) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Imatges com a text (AA)**: evitar utilitzar imatges per representar text, excepte en casos on el text dins de la imatge sigui essencial (per exemple, un logotip) o no es pugui aconseguir el mateix efecte visual amb text en format HTML/CSS. [1.4.4 Imatges com a text - CAT](https://www.w3.org/Translations/WCAG21-ca/#images-of-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Contrast mínim (AA)**: si una imatge conté text, el contrast entre el text i el fons de la imatge ha de complir un mínim de 4.5:1 per a textos normals i 3:1 per a textos grans. [1.4.3 Contrast mínim - CAT](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum.html) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Escalabilitat i compatibilitat amb zoom (AA)**: les imatges han de ser escalables sense pèrdua de funcionalitat o claredat quan s'utilitza un zoom de fins al 200%. [1.1.1 Escalabilitat i zoom - CAT](https://www.w3.org/Translations/WCAG21-ca/#non-text-content) / [EN](https://www.w3.org/WAI/WCAG21/Understanding/non-text-content.html)
- **Evitar contingut decoratiu o superflu (AA)**: si la imatge és purament decorativa, no ha de ser llegida per tecnologies de suport. Es pot aconseguir amb un atribut alt="" o etiquetant-la com a contingut decoratiu. [2.4.6 Encapçalaments i etiquetes descriptives - CAT](https://www.w3.org/Translations/WCAG22-ca/#headings-and-labels) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/headings-and-labels)

### Pautes aplicables a fils d'Ariadna
- **Teclat (A)**: tota la funcionalitat del contingut (navegar pels diferents enllaços i el botó desplegable) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [2.1.1 Teclat - CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)

## Implementació (component web)

### `<secondary-header-component>`

Paquet: core. Sense esdeveniments declarats.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte |
|---|---|---|---|---|
| `breadcrumbItems` | `breadcrumb-items` | Array d'objectes que defineix els nivells dels fils d'Ariadna (accepta array d'objectes o string JSON). Opcional | string (JSON) | `undefined` |
| `imageHeader` | `image-header` | Imatge que acompanya la capçalera secundària (URL de la imatge de capçalera). Opcional | string | `undefined` |
| `titleHeader` | `title-header` | Títol de la capçalera secundària. **Obligatori** | string | `undefined` |

**Props que accepten JSON**

`breadcrumbItems`: cada objecte ha de contenir:
- `content`: nom del nivell.
- `active`: boolean; `true` si és l'últim nivell, `false` en els altres nivells.
- `href`: enllaç de redirecció per a cada nivell.

**Depèn de**: `breadcrumb-component` ([Fils d'Ariadna](component-fils-d-ariadna.md)).

**Exemple d'ús**

```html
<!-- /index.html -->
<secondary-header-component
title-header="Titol"
image-header="https://oxygenworkspace.com/wp-content/uploads/2021/06/Despacho-04-1.jpg"
breadcrumb-items='[
    { "content": "Nivell 1", "active": false, "href": "https://www.google.com" },
    { "content": "Nivell 2", "active": false, "href": "https://www.google.com"},
    { "content": "Nivell actual", "active": true, "href": "https://www.google.com"}
  ]'
></secondary-header-component>
```

**Exemple d'instància (PDF)**

```html
<secondary-header-component
breadcrumb-items="texto-ejemplo"
image-header="texto-ejemplo"
title-header="texto-ejemplo"
></secondary-header-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.0.0 | 11.0.0 | 19 juny, 2026 | Desenvolupament: es canvia el nom de la variable del background; es corregeix el posicionament erroni del background amb l'augment de text |
| 12.0.0 | 9.4.0 | 29 maig, 2026 | Disseny: s'aplica el token de color específic pel fons de la capçalera secundària |
| 8.6.0 | 9.4.0 | 17 abril, 2026 | Desenvolupament: s'ha corregit el centrat vertical del títol quan només hi ha una línia de text; s'ha corregit l'alineació dels laterals del component en breakpoints superiors a 1440px |
| 8.6.0 | 9.2.0 | 27 febrer, 2026 | Desenvolupament: es fan millores d'accessibilitat |
| 8.6.0 | 6.2.1 | 9 febrer, 2026 | Disseny: s'elimina el truncat del títol; es posa comportament en hug per alçades; la imatge s'adapta a l'alçada del contenidor; s'ha afegit un marge superior i posterior de 16 píxels a la variant temàtica large |
| 8.5.0 | 6.2.1 | 20 gener, 2026 | Disseny: alineació central del títol quan no hi ha imatge ni breadcrumbs a la versió Medium i Small |
| 8.4.0 | 6.2.1 | 5 desembre, 2025 | Disseny: alineació central del títol quan no hi ha imatge ni breadcrumbs a la versió extra large column variable |
| 8.2.0 | 6.2.1 | 6 octubre, 2025 | Disseny: s'ajusta la posició del desplegable de l'asset Dropdown language public; es crea la variant sense imatge, perquè l'alçada del contenidor s'adapti al text del contingut. Desenvolupament: resolució de problemes |
| 8.0.0 | 5.0.0 | 12 setembre, 2025 | Disseny: es fa un reset a les instàncies de títol i fils d'Ariadna per ajustar correctament la posició del text quan només hi ha títol; el comportament del text del nivell actual del fil d'Ariadna es modifica a fill perquè es trunqui si no hi ha espai disponible |
| 6.1.0 | 5.0.0 | 28 juliol, 2025 | Disseny: s'ajusten marges en les versions Extra Large column variable i Large |
| 5.0.0 | 5.0.0 | 10 juny, 2025 | Disseny: es centra el títol en el punt de tall small quan no hi ha breadcrumbs |
| 4.1.0 | 5.0.0 | 9 juny, 2025 | Desenvolupament: resolució de problemes |
| 4.1.0 | 4.0.1 | 19 maig, 2025 | Disseny (ajustament): el títol de la capçalera temàtica sense imatge passa a ocupar tot l'espai disponible |
| 4.0.0 | 3.0.0 | 30 abril, 2025 | Disseny (ajustament): s'ajusta la disposició dels elements perquè el títol quedi sempre centrat |
| 2.4.0 | 2.0.0 | 10 març, 2025 | Disseny (evolutiu): es reajusta la forma de la imatge i s'afegeix la capçalera secundària específica per a pàgines de detall |
| 2.3.0 | 2.0.0 | 7 març, 2025 | Desenvolupament del component |
| - | - | - | Evolutiu de capçalera secundària |
| 2.3.0 | No aplica | 31 gener, 2025 | Sense canvis |
| 2.2.0 | No aplica | 20 gener, 2025 | Disseny i documentació del component |

## Vegeu també
- [Panell destacat](component-panell-destacat.md): per indicar el propòsit de la pàgina.
- [Fils d'Ariadna](component-fils-d-ariadna.md): per proporcionar una trajectòria clara de les pàgines visitades.
- [Capçalera secundària de BO](component-capcalera-secundaria-de-bo.md)
- [Exemples d'ús](exemple-exemples-d-us.md)
- [Etiquetatge d'IA](component-etiquetatge-d-ia.md)
