# Insígnia (Badge)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/479737 · Web component: `<badge-component>` (paquet core) · Font actualitzada el 2026-10-07 · Extret el 2026-10-28

## Què és i quan usar-lo
Indicador visual emprat per dirigir l'atenció de l'usuari cap a un element de la web.

La insígnia és un indicador visual que **afegeix informació a un altre element**. Serveix per cridar l'atenció dels usuaris sobre un element en la pàgina o per destacar esdeveniments relacionats amb aquest element. Existeixen **dues tipologies**: la insígnia de punt i la insígnia numèrica.

### Context d'ús
Aquest indicador serveix per dirigir l'atenció cap a aquella informació dinàmica dins d'una funcionalitat, secció o element important per a l'usuari, com per exemple l'activitat de la web que requereix alguna acció o configuracions d'una funcionalitat que afecten la visualització de la pàgina.

#### Insígnia numèrica
S'utilitza per quantificar les novetats o canvis dins d'una funcionalitat o secció. S'usa en aquells casos en què la informació dinàmica del component és computable i especialment rellevant per a l'usuari. Casos d'ús:
- Per indicar el nombre de notificacions pendents de llegir.
- Per indicar el nombre de filtres aplicats.
- Per indicar el nombre de tasques pendents a realitzar.

#### Insígnia de punt
S'utilitza per a un únic element o per mostrar informació dinàmica dins de la funcionalitat que no és computable. Es recomana fer servir aquest tipus d'insígnia en aquells casos en què no interessa destacar el nombre d'ítems, ja sigui perquè els valors són molt alts i poden generar massa tensió o perquè la informació no és rellevant per a l'usuari. Casos d'ús:
- Per indicar si un missatge està pendent de llegir.
- Per indicar elements funcionals que necessiten atenció de l'usuari.

## Quan NO usar-lo / alternatives
- La categorització d'un element en cap cas s'indica amb una insígnia: es recomana l'ús d'etiquetes (vegeu [Etiquetes](component-etiquetes.md)).
- Les insígnies no han de ser utilitzades per previsualitzar informació estàtica d'un component: en aquests casos es recomana incloure la informació en forma de text.

## Anatomia
La **insígnia de punt** està feta d'un contenidor i un contorn (opcional) que utilitza el mateix color de fons sobre el qual es col·loca. La **insígnia numèrica** està feta d'un contenidor, un contorn (opcional) i un valor numèric.

Figma: Badge [Text = ###, Size = Medium, Border = false, Dark Background = False].

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Size | Medium / Small / ExtraSmall | Small |
| Border | True / False | False |
| Dark Background | True / False | False |

La font mostra les subseccions Mides, Bora i Fons obscur (mateixa variant Figma: Badge [Text = ###, Size = Medium, Border = false, Dark Background = False]).

## Mides i espaiats

### Posició
- **Insígnia amb icona:** per a mides XS, la insígnia es col·loca alineada a la cantonada superior dreta. Per a mides S, es col·loca a partir de la meitat d'aquest component i 1/4 per sobre de la seva base superior. Així, si la icona fa 24 x 24px, la insígnia va col·locada a partir del píxel 12 i 4 píxels per sobre de la part superior.
- **Insígnia amb text:** per a mides XS, la insígnia es col·loca a la cantonada superior dreta de l'element, amb una separació de 4 pt. Per a mides M, se situa centrada a la dreta del text, amb una separació de 8 pt.
- **Insígnia en un component:** la insígnia també pot anar inclosa dins d'un component. Per a aquests casos concrets, la seva posició s'especifica en el mateix disseny del component.

## Comportament i interacció

### Consideracions generals
- La insígnia és un element complementari que mai pot aparèixer sol. **Ha d'anar sempre acompanyant d'un altre element**, preferentment d'un text o una icona, tot i que també pot anar integrat dins d'un altre component.
- Quan la insígnia s'usi **superposada sobre una icona**, s'utilitzen les variables amb **contorn en les mides: petita (S) i extra petita (XS)**. Quan la insígnia acompanya un text, es fan servir les variants sense contorn en les mides extra petita XS i mitjana M.
- El **contorn** de la insígnia sempre és del **mateix color que el del fons** del component on es troba.
- La insígnia numèrica permet d'un a tres caràcters. Si se superen els tres caràcters, s'afegeix un signe "+".

### Interacció
Una insígnia per si sola no és un element interactiu, però enllaça amb el text o icona que acompanya. Aquest element desapareix únicament quan l'usuari fa clic en el component, text o icona que contingui la insígnia. També desapareix quan les configuracions aplicades que afecten una funcionalitat ja no hi són (com en el cas dels filtres).

### Adaptació responsiva
No requereix un disseny específic per a dispositius mòbils o tauletes: l'adaptació a les diferents mides de pantalla depèn del component on estigui col·locada la insígnia.

## Bones pràctiques

### Ús moderat
Les insígnies s'utilitzen únicament per destacar informació realment rellevant per a l'usuari. Un ús excessiu pot fer perdre la seva eficàcia i provocar fatiga visual.
- **FER:** Utilitza-la per a notificacions que requereixen una acció per part de l'usuari, com per exemple una secció de tasques pendents o una bústia de notificacions.
- **NO FER:** No facis ús excessiu d'insígnies en una mateixa pàgina. Evita usar-les per a contingut redundant o evident, com per exemple destacar informació ja representada per un altre component.

### Ús de valors numèrics limitats
Les notificacions numèriques poden ser estressants quan augmenten ràpidament i amb freqüència. En aquests casos es recomana limitar els valors numèrics a un màxim raonable o utilitzar una insígnia de punt.
- **FER:** Considera l'ús d'un valor màxim de 99+ per a aquelles notificacions que són susceptibles d'augmentar ràpidament.
- **NO FER:** No utilitzis insígnies numèriques amb més de tres caràcters.

### Ús del component correcte segons el context d'ús
Les insígnies s'utilitzen per destacar informació dinàmica que canvia amb certa freqüència, com l'activitat d'una pàgina o les configuracions que fa l'usuari dins d'una aplicació.
- **NO FER:** La categorització d'un element en cap cas s'indica amb una insígnia. En aquests casos es recomana l'ús d'etiquetes.
- **NO FER:** Les insígnies no han de ser utilitzades per previsualitzar informació estàtica d'un component. En aquests casos es recomana incloure la informació en forma de text.
- **FER:** Utilitza la insígnia per visualitzar els filtres aplicats en una pàgina.
- **FER:** Utilitza-la per destacar missatges nous dins d'una secció de notificacions.

### Ús de variables definides
L'ús de possibles variables ha de limitar-se únicament a les contemplades en el disseny del component.
- **NO FER:** No facis ús de valors de text o icones dins d'una insígnia. Es recomana utilitzar valors numèrics.
- **NO FER:** No la utilitzis amb colors no definits en el disseny del component.

## Accessibilitat

### Pautes WCAG
- **Contingut no textual (A):** tot el contingut no text que es presenta a l'usuari té una alternativa de text que serveix per a la finalitat equivalent. Per a les persones que utilitzen lectors de pantalla, les insígnies són invisibles; per tant, és una bona pràctica assegurar que qualsevol icona o concepte representat amb una insígnia inclogui una etiqueta de lector de pantalla. Aquestes etiquetes no són visibles, però són llegides pels lectors de pantalla per aclarir la interfície per als usuaris amb problemes de visió. En insígnies numèriques, l'etiqueta del lector de pantalla ha d'indicar què és el recompte que s'enumera. Per a insígnies de punts, l'etiqueta del lector de pantalla ha de dir què indica el punt (per exemple, una insígnia de punts en una entrada de filtres indica que els filtres s'han aplicat). [1.1.1 CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-content) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color) [a verificar: l'enllaç EN de la font apunta a use-of-color]
- **Ús del color (A):** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. El color del badge sempre és el mateix, no hi ha un canvi d'aquest per indicar alguna informació. [1.4.1 CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. [1.4.3 CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA):** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [1.4.4 CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA):** els elements gràfics com el fons de la insígnia presenten un contrast mínim de 3:1. [1.4.11 CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)

## Implementació (component web)

### `<badge-component>`

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat |
|---|---|---|---|---|---|
| `badgeId` | `badge-id` | Identificador del badge | `string` | `undefined` | Obligatori |
| `borderColor` | `border-color` | Indica si hi ha vora de color | `boolean` | `false` | Opcional |
| `darkBackground` | `dark-background` | Indica si es fa servir el fons fosc | `boolean` | `false` | Opcional |
| `iconClassName` | `icon-class-name` | Nom de la classe de la icona de Bootstrap (p. ex. `bi-check`). [Biblioteca d'icones Bootstrap](https://icons.getbootstrap.com/) | `string` | `undefined` | Opcional |
| `nextToTextSmall` | `next-to-text-small` | Propietat vàlida per als badge que es trobin a la mateixa línia del text. `true` si es desitja que la seva mida sigui small i `false` si es desitja que la seva mida sigui medium | `boolean` | `undefined` | Opcional |
| `text` | `text` | Text que es mostra dins de la insígnia | `string` | `undefined` | Opcional |

**Variants**

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `darkBackground` | `true` `false` | `false` |
| `borderColor` | `true` `false` | `false` |

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre / tipus | Origen |
|---|---|---|---|
| `badgeClick` | Propaga l'esdeveniment click al badge | `id` — `CustomEvent<string>` | `badge-component` |

**Utilitzat per:** `button-component` ([Botons](component-botons.md)), `vertical-tabs-component` ([Pestanyes](component-pestanyes.md)).

**Exemple d'ús**

```html
<!-- /index.html -->
<badge-component
  badge-id="notifications"
  icon-class-name="bi bi-bell"
  text="12"
  border-color="true"
  dark-background="false"
  next-to-text-small="true"
></badge-component>
```

Exemple d'instància (PDF):

```html
<badge-component
badge-id="texto-ejemplo"
border-color=false
dark-background=false
icon-class-name="texto-ejemplo"
next-to-text-small=false
text="texto-ejemplo"
></badge-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 6.0.0 | 10.0.0 | 8 maig, 2026 | **Desenvolupament**: ajustos d'accessibilitat |
| 6.0.0 | 4.0.1 | 8 juliol, 2025 | **Disseny**: Es dissenya la versió del badge sobre fons fosc. |
| 4.0.0 | 4.0.1 | 19 maig, 2025 | **Desenvolupament**: Resolució de problemes |
| 2.3.0 | 1.0.0 | 31 gener, 2025 | Sense canvis. |
| 2.2.0 | 0.1.1 | 20 gener, 2025 | Sense canvis. |
| 2.1.0 | 0.1.1 | 04 desembre, 2024 | Sense canvis. |
| 2.0.0 | 0.1.0 | 02 desembre, 2024 | Sense canvis. |
| 1.1.0 | 0.1.0 | 22 novembre, 2024 | Sense canvis. |
| 1.1.0 | 0.0.4 | 18 novembre, 2024 | Sense canvis. |
| 1.0.0 | 0.0.3 | 1 novembre, 2024 | **Disseny**, **desenvolupament** i **documentació** del component. |

Actualitzacions (legacy): versió 1.0, sense data ni descripció.

## Vegeu també
- [Etiquetes](component-etiquetes.md)
- [Botons](component-botons.md)
- [Pestanyes](component-pestanyes.md)
- [Filtres](component-filtres.md)
