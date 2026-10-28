# Botó de compartir (Share button)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/066166 · Patró · Font actualitzada el 2026-06-16 · Extret el 2026-10-28

## Què és i quan usar-lo
El botó de compartir és un element interactiu que permet a l'usuari distribuir el contingut de la pàgina a xarxes socials o altres canals. Permet enviar el contingut de l'article o notícia a xarxes socials o altres canals de forma ràpida i intuïtiva. És especialment útil en articles, notícies i continguts editorials on es vol incentivar la difusió.

### Quan s'utilitza
S'ha d'utilitzar en pàgines de notícies, articles o continguts editorials on tingui sentit que l'usuari pugui difondre la informació a altres persones. Facilita que el contingut arribi a més audiència i permet que l'usuari participi activament en la seva distribució. És especialment recomanable quan:
- Es vol potenciar la difusió de continguts d'interès general.
- Es busquen interaccions socials i trànsit de retorn.
- El disseny de la pàgina prioritza la visibilitat i accessibilitat de les opcions de compartició.

## Quan NO usar-lo / alternatives
No s'ha d'incloure el botó de compartir en pantalles que no siguin pàgines de notícies o articles, com ara fluxos transaccionals, formularis, espais privats de l'usuari o continguts interns. Afegir-lo en aquests contextos podria generar soroll visual i confondre l'usuari sobre la rellevància de compartir aquell contingut.

## Anatomia
1. **Botó de compartir** ([Botons](component-botons.md)).
2. **Desplegable** que conté les opcions disponibles per compartir la informació. L'ordre d'aquestes opcions és fix i segueix la seqüència: Copia l'enllaç, WhatsApp, X (Twitter), Facebook i Correu.

## Comportament i interacció
El comportament s'adapta als diferents punts de tall:
- **Escriptori:** en fer clic a la icona s'obre un petit menú amb els diferents canals per compartir.
- **Dispositius petits:** es desplega el menú de compartir natiu de cada sistema operatiu.

## Ubicació
El component es col·loca sempre a la part superior dreta del contenidor de l'article/notícia. Si existeixen el títol i el subtítol, el botó es mostra sota aquests elements, alineat a la dreta, al costat de la data i hora de publicació.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG):

- **Orientació (AA)** — 1.3.4. El contingut de l'àrea de text s'adapta a les diferents orientacions de la pantalla, com ara vertical o horitzontal, cosa que permet visualitzar el contingut. [CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Ús del color (A)** — 1.4.1. El color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a diferenciar els diferents estats s'inclouen subratllats, es juga amb la presència de farciment i el gruix de la vora. [CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA)** — 1.4.3. Els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA)** — 1.4.4. Excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA)** — 1.4.11. Els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A)** — 2.1.1. Tota la funcionalitat del contingut (navegar pels diferents botons) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Focus visible (AA)** — 2.4.7. La navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- **Identificació d'errors (A)** — 3.3.1. Si es detecta un error en el component, s'identifica clarament que aquest presenta un error mitjançant un canvi de color i gruix de la vora i amb la indicació visual (icona) i textual (descripció de l'error) de l'error. [CAT](https://www.w3.org/Translations/WCAG22-ca/#error-identification) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/error-identification)

### Navegació per teclat
| Tecla | Acció |
|---|---|
| Tabulació | Navegació fins al component. Navegar per les diferents opcions del desplegable (un cop obert) |
| Fletxes | Desplaçar-se per les diferents opcions del desplegable |
| Intro | Seleccionar una o diverses opcions (segons el tipus) |
| Esc | Cancel·lar una acció |

## Components implicats
[Botons](component-botons.md), [Menú desplegable](component-menu-desplegable.md) (desplegable d'opcions), [Visor de notícies](component-visor-de-noticies.md).

## Historial de versions
| Versió Figma | Data | Descripció |
|---|---|---|
| 8.1.0 | 6 octubre, 2025 | Disseny i documentació del patró |
