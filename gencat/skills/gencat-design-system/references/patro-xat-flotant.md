# Xat flotant (Floating chat)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/079d5f · Font actualitzada el 2026-09-17 · Extret el 2026-10-28

## Què és i quan usar-lo
El xat flotant és una eina d'ajuda transversal, però simple. No és l'espai principal de treball.

### Quan s'utilitza
- Quan la conversa ha de ser persistent mentre l'usuari navega.
- Quan el xat és un canal secundari, no el contingut principal.
- Quan el xat ha de ser transversal a diferents pàgines.
- Quan la conversa és de baixa profunditat.
- Quan és una eina d'ajuda, no l'espai principal de treball.

**És una eina d'ajuda, no l'espai principal de treball.**

## Quan NO usar-lo / alternatives
- Quan la conversa és el contingut principal.
- Quan l'usuari necessita multitasca intensiva dins del xat (adjuntar fitxers complexos, múltiples fils).
- Quan el canal és purament informatiu (FAQs, articles, guies).

### Comparativa amb altres tipus de contenidors
Per a obtenir més informació sobre el funcionament dels xatbots a través de la intel·ligència artificial, consulta la Guia de Xatbot.
- [Xat a pantalla completa](patro-xat-a-pantalla-completa.md)
- [Xat lateral](patro-xat-lateral.md)

## Components implicats (anatomia)
Per a conèixer l'anatomia del patró, consulteu la dels components principals que el conformen:
- [Botó de xat](component-boto-de-xat.md) (flotant)
- [Contenidor de xat](component-contenidor-de-xat.md) (flotant)

Components relacionats: [Botó tornar a baix](component-boto-tornar-a-baix.md), [Botó Tornar amunt](component-boto-tornar-amunt.md).

## Ubicació i distàncies

### Botó de xat
Per convenció i per a una accessibilitat òptima, el Botó de Xat Flotant es col·loca de manera fixa a la part inferior dreta de la pantalla. Aquesta posició es manté inalterable durant l'esdeveniment de scroll de la pàgina, gràcies al seu estat fix.

Pel que fa a l'espaiat, el component se separa de la vora inferior i lateral de la finestra (viewport) per un marge que varia en funció del punt de tall. Les mesures establertes asseguren que el botó estigui sempre disponible, però que no s'adhereixi massa a la vora, evitant possibles solapaments amb barres de desplaçament del sistema operatiu o altres elements d'interfície.

| Punt de tall | Marge inferior | Marge lateral |
|---|---|---|
| Extra Large column fixed i extra large column variable | 40 px | 48 px |
| Large | 40 px | 40 px |
| Medium | 40 px | 32 px |
| Small | 16 px | 12 px |

Figma: Xat flotant/Components/Botó de xat/Xat flotant/Disseny/Ubicació i distàncies/{XL, L, M, S}.

### Contenidor de xat flotant
El contenidor de xat es col·loca respectant les mateixes distàncies respecte el marge que el botó. Això aplica als punts de tall des de Extra Large fins a 768 px (està dins del punt de tall Medium). De 767 px cap a baix s'aplica la versió en bottom sheet que ocupa tota l'amplada de pantalla.
- Extra Large - Medium (fins a 767 px). Figma: `Xat flotant_XL`.
- Medium - Small. Figma: `Xat flotant_S`.

## Comportament

### Adaptació responsive
- **Punt de tall Extra Large - Large:** col·locat a la part inferior dreta de la pantalla amb una amplada fixa de 400 px.
- **Punt de tall Medium:** conviuen les dues formes del xat, com a element flotant i com a panell emergent. El canvi entre un i l'altre es realitza a 768 px. A partir dels 767 px es mostra amb la versió per a punt de tall Medium - Small.
- **Punt de tall Small:** tots els elements que conformen el xat es situen a pantalla completa.

Figma: Xat flotant/Components/Botó de xat/Xat flotant/Disseny/Responsive/{XL, M, S}.

### Elements fixes i scroll
- **Sticky Header:** la capçalera es manté fixa a la part superior.
- **Subheader:** la subcapçalera fa scroll amb els missatges del xat.
- **Sticky Input:** el camp d'entrada es manté fixe a la part inferior.
- **Auto-scroll del cos:** per defecte, quan arriba un missatge nou, el xat fa scroll automàtic a mesura que es genera la resposta. Quan l'usuari envia missatge a la IA fa scroll automàtic. Si l'usuari ha pujat manualment per llegir missatges antics, el xat no ha de saltar cap avall automàticament si arriba un missatge nou (conversa amb persones). S'ha de mostrar un **avís tipus: "Tens missatges nous"**.
- Per més informació consulta el component [Botó tornar a baix](component-boto-tornar-a-baix.md).

#### Degradat
Quan hi ha scroll del contingut apareix un degradat blanc just per sobre del camp d'entrada. Aquest fa 8 px d'alçada. Figma: `Degradat`.

### Botó de tornar a baix
- El botó de tornar a baix apareix quan l'usuari realitza un scroll cap amunt equivalent a 75% de l'alçada del contenidor. Figma: `Botó tornar a baix`.
- Quan apareixen missatges nous el botó passa al seu estat de notificació. Figma: `Botó tornar a baix_nous missatges`.

### Tancament del xat
- El comportament en el patró de [Xat a pantalla completa](patro-xat-a-pantalla-completa.md) és diferent. Revisa el patró per veure com funciona.
- Al tancar el xat apareix un missatge de seguretat.
- Si l'usuari tanca definitivament el xat, s'eliminarà la conversa i, si torna a obrir el xat, aquest començarà la conversa de nou.
- D'altra banda, si minimitza no perdrà informació de la conversa mentre no tanqui la pestanya o passi el temps d'espera delimitat.
- Figma: `Tancament`.

### Temps d'espera
Si un usuari deixa la pestanya amb el xat oberta un temps superior al que permet mantenir la conversa activa, cal notificar a l'usuari que la conversa s'ha perdut i que ha d'iniciar-ne una de nova.

### Combinació de botó de xat flotant amb Tornar amunt
Els botons es col·loquen alineats al centre entre ells i el botó de xat és el que marca la distància amb el marge lateral i inferior. Vegeu [Botó Tornar amunt](component-boto-tornar-amunt.md).
Variants Figma: Combinació botó xat + botó tornar amunt = XL (Extra Large column fix i Extra Large column variable) | L | M | S.

## Accessibilitat (WCAG)
- **Orientació (AA) 1.3.4:** el contingut de l'àrea de text s'adapta a les diferents orientacions de la pantalla, com ara vertical o horitzontal, cosa que permet visualitzar el contingut. [CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Ús del color (A) 1.4.1:** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a diferenciar els diferents estats s'inclouen subratllats, es juga amb la presència de farciment i el gruix de la vora. [CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA) 1.4.3:** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA) 1.4.4:** en fer un augment de text al 200% cal assegurar que cap element es talli o sobresurti de pantalla. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
  - Capçalera: si no hi ha espai suficient perquè nom i botons estiguin en línia, el nom passarà a una segona línia i els botons quedaran alineats a la part superior dreta.
  - Camp d'entrada: els botons salten de línia i es col·loquen inferiorment al text. Si hi ha més botons dels que caben en línia, aquests es col·lapsaran en un menú. El botó per adjuntar elements no entrarà dins d'aquest desplegable.
  - Figma: `Augment de text01`, `Augment de text02`, `Augment de text03`.
- **Redistribució (AA) 1.4.10:** en fer zoom al 400% en Desktop (1280 x 1024 px) cal assegurar que cap element dificulti la lectura o interacció dels elements. Per aquest motiu, l'alçada del camp de text es limita a un màxim de 84 px d'alçada. Figma: `Zoom 400% 01`, `Zoom 400% 02`. [CAT](https://www.w3.org/Translations/WCAG22-ca/#reflow) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/reflow)
- **Contrast d'elements no textuals (AA) 1.4.11:** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A) 2.1.1:** tota la funcionalitat del contingut (navegar pels diferents botons) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Ordre del focus (A) 2.4.3:** l'ordre del focus per a navegar per teclat (sense lector) és el següent:
  1. Botó de xat: apareix com a últim element de la pantalla. Un cop col·locat sobre el botó, l'usuari prem "enter" per obrir el xat.
  2. Contenidor de xat:
     1. Input: el focus es col·loca sobre l'input del xat. Seguint amb l'ordre del tab el focus aniria a:
        1. Botó per afegir elements adjunts.
        2. Grup de botons començant d'esquerra a dreta; l'últim serà el d'enviar.
        3. Botó de document adjunts.
  3. Capçalera: començant pel botó situat més a l'esquerra. L'últim sempre el de tancar.
  4. Cos del xat: començant pel primer missatge que es va enviar en la conversa.
  - En el cas de navegar amb Shift + Tab partint del camp d'entrada, el primer element interactiu seria l'últim element interactiu de l'últim missatge enviat al body.
  - Quan l'usuari es troba en focus dins d'un element del cos, les fletxes permeten fer scroll del contingut.
  - Figma: `Ordre focus01` a `Ordre focus04`. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-order) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-order)
- **Focus visible (AA) 2.4.7:** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- **Encapçalaments de secció (AAA) 2.4.10:** si el lector de pantalla està activat, un cop l'usuari surti del camp d'entrada (si utilitza les tecles alfabètiques mentre és a l'input escriuria), pot utilitzar la tecla H per a navegar entre els headings dels missatges. Per aquest motiu cada missatge ha de tenir un H4, H5, etc. en funció de l'estructura de la pàgina que indicarà:
  - Missatge de l'usuari: "has dit"
  - Missatge del xatbot: "l'agent ha dit"
  - Si dins del missatge del xatbot hi ha seccions, aquestes tindran un H inferior al del missatge (H6, per exemple).
  - [CAT](https://www.w3.org/Translations/WCAG22-ca/#section-headings) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/section-headings)
- **Nom, funció, valor (A) 4.1.2:** usa atributs com `aria-checked` per reflectir l'estat del commutador als lectors de pantalla. Si dins dels missatges hi ha text amb format com, per exemple, negreta, aquest es llegirà de forma normal sense indicar elements com asteriscs. Exemple de mala pràctica: en ChatGPT, mentre llegeix i hi ha una negreta, va llegint "asterisc, asterisc" abans i després de cada negreta. [CAT](https://www.w3.org/Translations/WCAG21-ca/#name-role-value) · [EN](https://www.w3.org/TR/WCAG21/#name-role-value)
- **Missatges d'estat (AA) 4.1.3:** [CAT](https://www.w3.org/Translations/WCAG22-ca/#status-messages) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/status-messages.html)
  - Lectura dels missatges: quan l'usuari envia un missatge, el lector haurà d'informar en veu alta dels estats. Per exemple, si està generant la resposta haurà de dir "s'està generant la resposta". Aquest missatge es repetirà cada 5 segons fins que es generi. Un cop s'ha generat tota la resposta, començarà la lectura d'aquesta iniciant amb un "el xat diu". Etiquetes:
    - `role="status"` indica al lector que és una zona d'informació no intrusiva però rellevant.
    - `aria-live="polite"` fa que el lector anunciï el canvi quan no interrompi res important.
    - `aria-atomic="true"` assegura que s'anuncia el missatge complet, no només fragments.
  - Nous missatges: si l'usuari està navegant pel xat i li arriba un nou missatge, apareixerà el botó de nous missatges. Això també s'ha de notificar mitjançant el lector a través d'etiquetes ARIA (`aria-live` i `aria-atomic`).

## Historial de versions

| Versió Figma | Data | Descripció |
|---|---|---|
| 3.0.0 | 17 abril, 2026 | Disseny: documentació de la combinació de botó de xat flotant amb tornar amunt |
| 2.1.0 | 20 març, 2026 | Disseny i documentació del patró |

## Vegeu també
[Xat lateral](patro-xat-lateral.md) · [Xat a pantalla completa](patro-xat-a-pantalla-completa.md) · [Botó de xat](component-boto-de-xat.md) · [Contenidor de xat](component-contenidor-de-xat.md) · [Botó tornar a baix](component-boto-tornar-a-baix.md) · [Botó Tornar amunt](component-boto-tornar-amunt.md)
