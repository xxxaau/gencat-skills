# Xat a pantalla completa (Full width chat)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/3006bf · Font actualitzada el 2026-09-17 · Extret el 2026-10-28

## Què és i quan usar-lo
El xat de pantalla completa aprofita l'espai disponible de pantalla i és útil quan el xat és el producte, no funciona com una eina de suport.

### Quan s'utilitza
S'utilitza quan la conversa és:
- La tasca principal.
- Complexa.
- Profunda.
- Amb múltiples iteracions.
- Amb necessitat de concentració.

Aquí el xat no és suport. És el producte.

## Quan NO usar-lo / alternatives
- Quan cal una eina d'ajuda contextual, no un espai principal de treball. Alternatives: [Xat flotant](patro-xat-flotant.md), [Xat lateral](patro-xat-lateral.md).

Per a obtenir més informació sobre el funcionament dels xatbots a través de la intel·ligència artificial, consulta la Guia de Xatbot.

## Anatomia
Figma: `Anatomia`. El xat a pantalla completa està format per les peces següents:
- **Capçalera de xat** ([Capçalera de xat](component-capcalera-de-xat.md)).
- **Cos del xat:** estructura on s'inclouen missatges de xat ([Missatge de xat](component-missatge-de-xat.md)) i altres possibles elements com botons de resposta ràpida.
  - **Botó de reinici de conversa:** es troba dins el cos com a element més inferior.
- **Camp d'entrada** ([Camp d'entrada de xat](component-camp-d-entrada-de-xat.md)).

## Mides i espaiats

### Ubicació i alçada
- El xat es col·loca dins l'estructura de la pàgina, just per sota dels fils d'Ariadna ([Fils d'Ariadna](component-fils-d-ariadna.md)).
- L'alçada varia en funció de l'alçada de pantalla, sent un 90% de la pantalla (equival a 90 vh).
- Es deixa un marge inferior entre el camp i el final de pantalla de 32 px en punts de tall Extra Large i Large, 24 px en Medium i 8 px en Small.

### Distàncies i alineacions
- **Botó de tornar a baix:** s'alinea centralment al cos del xat i es col·loca a 32 px superiorment al camp d'entrada ([Botó tornar a baix](component-boto-tornar-a-baix.md)).
- **Botó de reiniciar conversa:** s'alinea centralment al cos del xat i es col·loca a 16 px inferiorment al camp d'entrada. En punt de tall Small va a amplada completa.

## Comportament

### Adaptació responsive
- **Punt de tall Extra Large - Large:** tots els elements que conformen el xat es situen a la part central de la pàgina ocupant les 6 columnes centrals. Figma: `Adaptació responsive_XL`.
- **Punt de tall "Extra Medium"** (sic; [a verificar: probablement Medium]): tots els elements que conformen el xat es situen a la part central de la pàgina ocupant les 6 columnes centrals. Alineació centrada amb una amplada mínima de 416 px tant pel cos com pel camp d'entrada. Figma: `Adaptació responsive_M`.
- **Punt de tall Small:** tots els elements que conformen el xat es situen a pantalla completa. Figma: `Adaptació responsive_S`.

### Elements fixes i scroll
**Extra Large - Medium**
- **Header:** la capçalera es desplaça quan l'usuari fa scroll.
- **Cos:** el cos del xat té un scroll separat de l'scroll de pàgina.
- **Auto-scroll:** per defecte, si l'usuari no ha fet scroll cap amunt, quan arriba un missatge nou, el xat fa scroll automàtic fins al final.
- **Smart Scrolling:** si l'usuari ha pujat manualment per llegir missatges antics, el xat no ha de saltar cap avall automàticament si arriba un missatge nou, a no ser que sigui l'usuari qui hagi escrit una nova pregunta. Això afecta, principalment, converses amb persones i no xatbots. S'ha de mostrar un **avís tipus: "Tens missatges nous a sota"**.

**Small**
- **Chat Header:** fa scroll conjuntament amb el cos.

**Degradat**
Quan hi ha scroll del contingut apareix un degradat blanc just per sobre del camp d'entrada. Aquest fa 16 px d'alçada. Figma: `Degradat`. (La secció "Scroll del contingut" de la font repeteix la mateixa dada: 16 px d'alçada.)

### Temps d'espera
Si un usuari deixa la pestanya amb el xat oberta un temps superior al que permet mantenir la conversa activa, cal notificar a l'usuari que la conversa s'ha perdut i que ha d'iniciar-ne una de nova.

### Botó de tornar a baix
Apareix quan l'usuari realitza un scroll cap amunt equivalent a 0.75 viewport (si és en un mòbil de 853 px d'alt, apareixerà en sobrepassar 639,75 px).

## Accessibilitat (WCAG)
- **Orientació (AA) 1.3.4:** el contingut de l'àrea de text s'adapta a les diferents orientacions de la pantalla, com ara vertical o horitzontal, cosa que permet visualitzar el contingut. [CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Ús del color (A) 1.4.1:** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a diferenciar els diferents estats s'inclouen subratllats, es juga amb la presència de farciment i el gruix de la vora. [CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA) 1.4.3:** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA) 1.4.4:** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA) 1.4.11:** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A) 2.1.1:** tota la funcionalitat del contingut (navegar pels diferents botons) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Ordre del focus (A) 2.4.3:** presenta un ordre lògic del focus dels elements interns per facilitar la navegació per teclat o altres dispositius d'entrada. L'ordre ha de seguir el flux de la informació o les tasques que s'estan presentant. (El text original parla de "modals" [a verificar: text heretat d'un altre component].) L'ordre ha de ser el següent: [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-order) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-order)
  1. Cos del xat, per a poder fer scroll del contingut mitjançant fletxes.
  2. Elements interactius dins del cos del xat.
  3. Camp d'entrada.
  4. Botons adicionals: es comença d'esquerra a dreta. Poden ser botons com adjuntar arxius, activar transcripció de veu a text, etc.
  - Figma: `Ordre del focus`.
- **Focus visible (AA) 2.4.7:** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

### Navegació per teclat

| Tecla | Acció |
|---|---|
| Tabulació | Navegació fins al component. Navegar per les diferents opcions del desplegable (un cop obert) |
| Fletxes | Fer scroll vertical del contingut del xat |
| Intro | Seleccionar una acció o enllaç |

## Historial de versions

| Versió Figma | Data | Descripció |
|---|---|---|
| 2.0.0 | 2 març, 2026 | Disseny i documentació del patró |

## Vegeu també
[Xat flotant](patro-xat-flotant.md) · [Xat lateral](patro-xat-lateral.md) · [Capçalera de xat](component-capcalera-de-xat.md) · [Missatge de xat](component-missatge-de-xat.md) · [Camp d'entrada de xat](component-camp-d-entrada-de-xat.md) · [Botó tornar a baix](component-boto-tornar-a-baix.md) · [Fils d'Ariadna](component-fils-d-ariadna.md)
