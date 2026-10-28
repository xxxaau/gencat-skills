# Xat lateral (Side panel chat)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/02ab59 · Font actualitzada el 2026-09-17 · Extret el 2026-10-28

## Què és i quan usar-lo
El xat lateral és una eina d'ajuda integrada en un panell lateral que permet consultar, generar o complementar informació sense abandonar completament la tasca principal ni substituir tota la pantalla.

Patró de conversa integrat en un panell lateral que apareix al costat del contingut principal de la interfície. Aquest patró és adequat quan el xat té una funció de suport contextual, assistència continuada o col·laboració dins d'un entorn de treball més ampli.

### Quan s'utilitza
- És rellevant per a la tasca principal.
- Acompanya el contingut principal, però no el substitueix.
- Està pensat per acompanyar l'usuari mentre consulta o edita informació, facilitant un accés continuat al xat durant la tasca.
- Ajuda a interpretar, completar, revisar o generar contingut relacionat amb l'àrea principal.
- Forma part d'un flux on l'usuari necessita fer anades i tornades entre contingut i conversa.

## Quan NO usar-lo / alternatives
- La conversa requereix concentració i ha de ser l'element central de la pantalla: en aquest cas seria un xat a pantalla completa ([Xat a pantalla completa](patro-xat-a-pantalla-completa.md)).
- L'espai disponible és massa reduït i el panell compromet la llegibilitat del contingut principal.
- El xat només resol una acció puntual i seria suficient un patró més lleuger, com ara un xat flotant ([Xat flotant](patro-xat-flotant.md)).
- L'ús és transversal i poc vinculat al context concret de la pàgina.

## Bones pràctiques

### Activació i context
- **FER:** El panell s'obre des d'una acció explícita de l'usuari.
- **FER:** La conversa ha d'estar relacionada amb el context actual de la pàgina, document o tasca.
- **NO FER:** No s'ha d'obrir de manera intrusiva sense context clar.

### Relació amb el contingut
- **FER:** Es manté visible mentre l'usuari continua interactuant amb el contingut principal.
- **NO FER:** No ha de tapar informació crítica ni bloquejar accions principals innecessàriament.
- **NO FER:** No s'ha de presentar com un element persistent si no aporta valor durant la tasca.

### Ús i funcionalitat
- **FER:** El panell pot permetre consultar, escriure, revisar resultats, adjuntar contingut o reprendre una conversa.
- **NO FER:** No ha de duplicar funcionalitats que ja es resolen amb ajuda contextual més simple.

Per a obtenir més informació sobre el funcionament dels xatbots a través de la intel·ligència artificial, consulta la Guia de Xatbot.

## Components implicats (anatomia)
Per a conèixer l'anatomia del patró, consulteu la dels components principals que el conformen:
- [Botó de xat](component-boto-de-xat.md) (lateral)
- [Contenidor de xat](component-contenidor-de-xat.md) (lateral)

Components relacionats: [Botó tornar a baix](component-boto-tornar-a-baix.md); patrons relacionats: [Xat a pantalla completa](patro-xat-a-pantalla-completa.md), [Xat flotant](patro-xat-flotant.md).

## Ubicació i distàncies

### Botó de xat lateral
- **Extra-Large - Medium (<768 px):** a diferència del botó de xat flotant, aquest botó se situa a la part superior de la pantalla, adherit a la subcapçalera quan n'hi ha. Quan l'usuari fa scroll i la subcapçalera deixa de ser visible, el botó es reubica just sota la capçalera, i es manté fix, per garantir-ne la visibilitat persistent. Figma: `Ubi_botó_extra`.
- **Small - Medium (>768 px):** en el punt de tall Medium poden conviure dues variants del botó: la **versió fixa**, situada a la capçalera o a la subcapçalera, segons correspongui (tal com s'ha explicat anteriorment), i la **versió no fixa**, adherida a la capçalera o a la subcapçalera. En el cas de la versió no fixa, el seu comportament depèn de si hi ha subcapçalera o no:
  - **Si no hi ha subcapçalera** i el botó queda situat just sota la capçalera, passarà a formar-ne part. Per tant, quan es faci scroll cap amunt i torni a aparèixer la capçalera, el botó també reapareixerà.
  - **Si hi ha subcapçalera**, el botó quedarà vinculat a aquesta zona i no es mantindrà visible. Per tornar-hi a accedir, caldrà fer scroll fins arribar de nou a la subcapçalera.
  - El canvi entre un i l'altre es realitza a 768 px. A partir dels 767 px es mostra amb la versió per a punt de tall Medium - Small. Figma: `Ubi_botó_small`.

### Panell lateral de xat
- El panell es mostra en punts de tall extra-large i medium fins a 768 píxels, ja que es tracta d'una eina conversacional orientada principalment a entorns privats i de back office. En aquest punt, si hi ha subcapçalera, el panell es desplegarà sota aquesta. Si no, ho farà des de la capçalera.
- En els casos en què sigui necessari mostrar-lo en punts de tall inferiors, aquest es presenta superposat sobre el contingut i amb una amplada més reduïda, mantenint totes les funcionalitats. Aquesta adaptació permet alternar la interacció entre el contingut principal i el xat.
- En punts de tall small i medium inferior a 768 píxels, el xat es transforma en una experiència de pantalla completa. En aquest punt el panell sempre es desplegarà en pantalla completa.

Per punt de tall:
- **Extra-large:** quan s'obre, el contingut principal s'adapta en amplada i disposició per conviure amb el panell, sempre que l'espai disponible ho permeti. Figma: `Ubi_panell_extra`.
- **Large - Medium (< 768 px):** en el punt de tall Medium conviuen les dues formes del xat, com a element emergent lateral i com a pantalla completa. El canvi entre un i l'altre es realitza a 768 px. A partir dels 767 px es mostra amb la versió per a punt de tall Medium (>768 px) - Small. Figma: `Ubi_panell_large`.
- **Small:** Figma: `Ubi_panell_small`.

## Comportament

### Elements fixes i scroll
- **Botó de xat sticky:** quan el panell de xat està col·lapsat, el botó es manté visible i fix a la part superior de la pantalla en punts de tall Extra large - Medium (<768 px). En punts Medium (>768 px) - Small, el botó és sticky quan es troba, només, sota la capçalera en realitzar scroll cap amunt. Consulta el component [Botó de xat](component-boto-de-xat.md) (lateral).
- Capçalera versió *medium (>768 px) - small*: sticky a la part superior de la pantalla.
- **Subheader:** la subcapçalera fa scroll amb els missatges del xat.
- **Sticky Input:** el camp d'entrada es manté fix a la part inferior.
- **Auto-scroll del cos:** per defecte, quan arriba un missatge nou, el xat fa scroll automàtic a mesura que es genera la resposta. Quan l'usuari envia missatge a la IA fa scroll automàtic. Si l'usuari ha pujat manualment per llegir missatges antics, el xat no ha de saltar cap avall automàticament si arriba un missatge nou (conversa amb persones). S'ha de mostrar un **avís tipus: "Tens missatges nous"**. Consulta el component [Botó tornar a baix](component-boto-tornar-a-baix.md).

#### Degradat
Quan hi ha scroll del contingut apareix un degradat blanc just per sobre del camp d'entrada. Aquest fa 8 px d'alçada. Figma: `Degradat`.

### Botó de tornar a baix
- Apareix quan l'usuari realitza un scroll cap amunt equivalent a 75% de l'alçada del contenidor. Figma: `Tornar_simple`.
- Quan apareixen missatges nous el botó passa al seu estat de notificació. Figma: `Tornar_avançat`.

### Moviment i direcció del panell
L'obertura i el tancament del panell es produeixen sempre lateralment: el panell emergeix des d'un dels costats de la interfície i s'hi replega novament.

## Accessibilitat (WCAG)
- **Orientació (AA) 1.3.4:** el contingut de l'àrea de text s'adapta a les diferents orientacions de la pantalla, com ara vertical o horitzontal, cosa que permet visualitzar el contingut. [CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Ús del color (A) 1.4.1:** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a diferenciar els diferents estats s'inclouen subratllats, es juga amb la presència de farciment i el gruix de la vora. [CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA) 1.4.3:** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA) 1.4.4:** en fer un augment de text al 200% cal assegurar que cap element es talli o sobresurti de pantalla. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
  - Capçalera: si no hi ha espai suficient perquè nom i botons estiguin en línia, el nom passarà a una segona línia i els botons quedaran alineats a la part superior dreta.
  - Camp d'entrada: els botons salten de línia i es col·loquen inferiorment al text. Si hi ha més botons dels que caben en línia, aquests es col·lapsaran en un menú. El botó per adjuntar elements no entrarà dins d'aquest desplegable. Figma: `Textresizer`.
- **Redistribució (AA) 1.4.10:** en fer zoom al 400% en Desktop (1280 x 1024 px) cal assegurar que cap element dificulti la lectura o interacció dels elements. Per aquest motiu, l'alçada del camp de text es limita a un màxim de 84 px d'alçada. Figma: `Zoom`. [CAT](https://www.w3.org/Translations/WCAG22-ca/#reflow) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/reflow)
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
  - Figma: `Focus`. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-order) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-order)
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
| 3.0.0 | 17 d'abril, 2026 | Disseny i documentació del patró |

## Vegeu també
[Xat flotant](patro-xat-flotant.md) · [Xat a pantalla completa](patro-xat-a-pantalla-completa.md) · [Botó de xat](component-boto-de-xat.md) · [Contenidor de xat](component-contenidor-de-xat.md) · [Botó tornar a baix](component-boto-tornar-a-baix.md)
