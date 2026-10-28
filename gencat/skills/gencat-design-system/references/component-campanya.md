# Campanya (Featured carousel)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/2296bc · Web component: `<featured-carousel-component>` (paquet core) · Font actualitzada el 2026-10-05 · Extret el 2026-10-28

## Què és i quan usar-lo
Component que mostra contingut destacat en format carrusel, com ara notícies, avisos, campanyes o altra informació rellevant. Permet navegar entre els diferents elements mitjançant els controls de navegació manuals.

La campanya és un component que **presenta una selecció de continguts destacats en format carrusel per donar visibilitat a informació rellevant**, com ara notícies, avisos, campanyes o altres continguts d'interès. Se sol situar a la part superior de la pàgina, just a sota del Fil d'Ariadna.

Els usuaris poden navegar entre els diferents elements mitjançant **controls manuals (*chevrons*)**, cosa que els permet explorar el contingut al seu ritme i mantenir el control sobre la interacció.

És especialment adequat per destacar **informació prioritària** a la pàgina d'inici o en seccions amb contingut dinàmic.

Quan s'utilitza:
- Cal destacar contingut rellevant o prioritari.
- Tots els elements tenen una importància equivalent.
- L'espai disponible és limitat i es vol optimitzar la superfície ocupada.
- Els usuaris poden beneficiar-se d'explorar diversos continguts sense abandonar la pàgina.
- El nombre d'elements a mostrar és de 2, 3 o 4.

## Quan NO usar-lo / alternatives
- Existeix una jerarquia clara entre els continguts.
- Tots els elements han de ser visibles simultàniament.
- El contingut és crític i no s'hauria d'amagar dins d'un carrusel.
- El nombre d'elements a mostrar és de només 1 o més de 4.

En aquests casos és preferible utilitzar una graella de targetes a l'estil del [Visor de notícies](component-visor-de-noticies.md) o un altre component que mostri tota la informació alhora.

## Anatomia
1. **Imatge:** element visual principal de la campanya. Ha de complementar i reforçar el contingut textual.
2. **Contenidor de contingut:** superfície que agrupa la informació de la campanya.
3. **Títol:** presenta el missatge principal de la campanya de manera breu i clara.
4. **Subtítol:** aporta informació complementària al títol. És opcional.
5. **Crida a l'acció:** enllaç o botó que permet accedir al contingut relacionat amb la campanya.
6. **Navegació del carrusel:** inclou els indicadors de posició i els controls que permeten navegar entre les diferents campanyes.

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Small / Medium / Large / Extra Large Column Variable / Extra Large Column Fixed | - |
| Title | - | Títol |
| Subtitle | - | Subtítol |

Variants Figma: Featured carousel [Title = Títol, Subtitle = Subtítol, Breakpoint = Extra Large Column Fixed].

## Comportament i interacció

### Comportament de la imatge
- **Mode per defecte: Fill (omplir).** La imatge de la campanya s'escala per omplir completament el contenidor sense deixar espais buits. Pot retallar-se si la seva relació d'aspecte no coincideix amb la del contenidor.
- **Mode opcional: Crop (retallar)**, quan es vol enfocar una àrea específica. Es pot definir un punt focal o triar manualment quina part de la imatge es retalla.

### Navegació del carrusel
- Els indicadors permeten identificar la posició de l'element actiu dins del carrusel. L'indicador actiu presenta un tractament visual diferenciat de la resta.
- Els controls de navegació permeten avançar o retrocedir entre campanyes sense modificar la posició de la resta del contingut de la pàgina.
- Quan només hi hagi una campanya, no s'han de mostrar els indicadors ni els controls de navegació.
- Variants Figma: _Carrusel controls [Icon button right = Type Tertiary, Size Large, State Default, Background Default; Icon button left = Type Tertiary, Size Large, State Default, Background Default; Positions = 2; Active position = First].

## Contingut i microcopy
- Títols breus, de fins a 70 caràcters.
- Subtítols concisos, centrats en una única idea i de fins a 120 caràcters.

## Bones pràctiques

Contingut rellevant:
- **FER:** prioritza la informació més útil o d'interès general i actualitza els continguts quan deixin de ser rellevants.
- **NO FER:** no incloguis continguts únicament per omplir el carrusel ni per promocionar informació secundària o obsoleta.

Nombre d'elements:
- **FER:** limita el carrusel a entre dos i quatre elements per facilitar-ne l'exploració.
- **NO FER:** evita crear carrusels amb un únic element o amb més de quatre diapositives.

Coherència gràfica:
- **FER:** assegura't que les imatges reforcen el contingut i tenen un estil visual consistent.
- **NO FER:** evita imatges que no representin el contingut o que siguin poc específiques.
- **FER:** assegura't que els elements importants de les imatges són visibles.
- **NO FER:** evita tallar els elements importants de les imatges o ocultar-los darrere la targeta.
- **FER:** utilitza imatges sense text per evitar desviar l'atenció del contingut de la targeta.
- **NO FER:** no utilitzis imatges amb text que provoquin una lectura addicional innecessària.

Límits textuals:
- **FER:** escriu títols breus, de fins a 70 caràcters, i subtítols concisos, centrats en una única idea i de fins a 120 caràcters.
- **NO FER:** evita textos massa breus o extensos que dificultin la comprensió o ocultin gran part de la imatge.

## Accessibilitat

### Pautes d'accessibilitat del contingut web (WCAG)
- **Ús del color (A) — 1.4.1:** el color no es fa servir com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per indicar el pas, el percentatge, etc. en què es troba el procés o tasca, s'utilitza informació textual a part de la gràfica. [CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA) — 1.4.3:** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA) — 1.4.4:** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA) — 1.4.11:** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A) — 2.1.1:** tota la funcionalitat del contingut (navegar pels enllaços) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Focus visible (AA) — 2.4.7:** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

### Navegació per teclat

| Tecla | Acció |
|---|---|
| Tabulació | Navegació al següent element interactiu |
| Enter | Activar element interactiu |

## Implementació (component web)

### `<featured-carousel-component>`
Paquet: core. (La font del lloc documenta el component; no hi ha capítol PDF assignat.)

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatori |
|---|---|---|---|---|---|
| `autoplay` | `autoplay` | Indica si el carrusel s'inicia automàticament i avança després d'un interval de temps determinat, definit per l'atribut `interval` | Boolean | - | Opcional |
| `interval` | `interval` | Defineix l'interval de temps, en mil·lisegons, entre cada canvi automàtic del carrusel | Number | - | Opcional |
| `items` | `items` | Defineix els elements que es mostraran al carrusel mitjançant un array d'objectes en format JSON | String (JSON) | - | Obligatori |

**Props que accepten JSON: `items`**

| Propietat | Descripció | Atribut | Obligatori | Tipus |
|---|---|---|---|---|
| `title` | Títol que es mostra a la diapositiva | `title` | Opcional | String |
| `subtitle` | Subtítol o text descriptiu que es mostra sota el títol | `subtitle` | Opcional | String |
| `image` | URL de la imatge que es mostra a la diapositiva | `image` | Opcional | String |

**Depèn de:** [`button-component`](component-botons.md).

**Exemple d'ús**

```html
<!-- /index.html -->
<featured-carousel-component
  items='[
    {
      "title": "Titular destacat",
      "subtitle": "Descripció curta i clara que acompanya la imatge principal del carrusel.",
      "image": "/assets/photos/img_1.png"
    },
    {
      "title": "Segon titular",
      "subtitle": "Una segona notícia amb el mateix estil per mostrar la variació del contingut.",
      "image": "/assets/photos/img_2.png"
    },
    {
      "title": "Tercer titular",
      "subtitle": "Tercer bloc de contingut destacat amb un CTA ben visible.",
      "image": "/assets/photos/img_3.png"
    }
  ]'
  autoplay="false"
  interval="5000"
></featured-carousel-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.3.0 | 12.1.2 | 5 octubre, 2026 | Desenvolupament: ajustos d'accessibilitat del carousel; es corregeixen errors relacionats amb el mode de focus |
| 12.3.0 | - | 31 juliol, 2026 | Disseny i documentació del component |

## Vegeu també
- [Botons](component-botons.md): per a realitzar accions.
- [Visor de notícies](component-visor-de-noticies.md)
- [Fils d'Ariadna](component-fils-d-ariadna.md)
- Suport: https://zeroheight.com/38669693e/p/57c57a-suport-i-contacte · https://zeroheight.com/38669693e/p/72240b-preguntes-frequents · https://zeroheight.com/38669693e/p/690b45 · https://zeroheight.com/38669693e/p/342611

> Nota: no hi ha capítol d'API de component web a la v12.0.0 del PDF per a aquest component; el codi prové de la pestanya Codi del lloc.
