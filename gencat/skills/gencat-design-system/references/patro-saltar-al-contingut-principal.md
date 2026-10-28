# Saltar al contingut principal (Skip button)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/029510 · Patró · Font actualitzada el 2026-04-30 · Extret el 2026-10-28

## Què és i quan usar-lo
Botó d'accessibilitat que permet als usuaris que naveguen per teclat o lectors de pantalla saltar directament al contingut principal, evitant la navegació repetitiva de la capçalera. Només es mostra quan rep el focus. És especialment útil en pàgines amb menús llargs o elements repetitius.

### Quan s'utilitza
S'implementa en totes les pàgines del portal web per garantir una experiència d'accessibilitat coherent.

## Anatomia
1. **Botó**: botó principal, en estat focus per defecte ([Botons](component-botons.md)).

## Comportament i interacció
1. **Focus inicial**
   - El component és invisible per defecte i només es mostra quan rep el focus mitjançant teclat (primer Tab de la pàgina).
   - Quan apareix, el botó es manté fix a la part superior de la pàgina, sobre la capçalera, independentment del desplaçament. Aquesta fixació és temporal: només dura mentre el botó és visible i té focus.
2. **Activació** (prement Enter o Espai)
   - El focus es trasllada al primer element del contingut principal (dins el `main` del codi HTML). Els fils d'Ariadna, si es consideren navegació secundària, queden exclosos ([Fils d'Ariadna](component-fils-d-ariadna.md)).
   - El botó i el focus desapareixen immediatament un cop activat.
   - Quan es torna a prémer la tecla de tabulació, el focus anirà al primer element interactiu del contingut principal.
3. **Comportament visual després de l'acció**
   - Un cop el focus està al contingut principal, l'usuari pot continuar navegant amb Tab pels elements interactius del contingut.
   - Si es navega cap enrere amb Shift + Tab, el focus no retorna automàticament al botó; aquest només reapareix si es refresca la pàgina i es torna a prémer Tab.
4. **Si no s'acciona el botó**
   - L'usuari haurà de navegar manualment pels elements del menú i la capçalera abans d'arribar al contingut principal.

### Suport en dispositius mòbils
No s'ha d'eliminar l'element en pantalles petites: el botó de salt pot ser útil per a persones que fan servir teclat o dispositius d'assistència, fins i tot en entorns tàctils.

## Ubicació
El botó "Saltar al contingut principal" es troba just a sobre de la capçalera de la pàgina ([Capçalera web pública](component-capcalera-web-publica.md)), de manera que sigui el primer element interactiu accessible mitjançant teclat. Això permet als usuaris saltar directament al contingut principal sense haver de navegar per tot el menú o elements de la capçalera.

## Codi i jerarquia
El component ha d'estar situat el més amunt possible dins del `<body>`, normalment com el primer element interactiu de la pàgina. Ha d'aparèixer abans de:
- La capçalera.
- El menú de navegació.
- Qualsevol altre bloc repetitiu.

Els únics elements que han d'aparèixer, si escau, abans del botó de salt al contingut principal són:
- Bàner de política de galetes.
- Avisos d'emergència ([Emergències](patro-emergencies.md)).

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG):

- **Orientació (AA)** — 1.3.4. El contingut de l'àrea de text s'adapta a les diferents orientacions de la pantalla, com ara vertical o horitzontal, cosa que permet visualitzar el contingut. [CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Ús del color (A)** — 1.4.1. El color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a diferenciar els diferents estats s'inclouen subratllats, es juga amb la presència de farciment i el gruix de la vora. [CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA)** — 1.4.3. Els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA)** — 1.4.4. Excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA)** — 1.4.11. Els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A)** — 2.1.1. Tota la funcionalitat del contingut (navegar pels diferents botons) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Ordre del focus (A)** — 2.4.3. El focus de teclat segueix un ordre lògic en tota la pàgina, amb el botó de salt al contingut principal com a primer element interactiu a excepció del bàner de cookies i avisos d'emergències. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-order) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-order)
- **Focus visible (AA)** — 2.4.7. La navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- **Identificació d'errors (A)** — 3.3.1. Si es detecta un error en el component, s'identifica clarament que aquest presenta un error mitjançant un canvi de color i gruix de la vora i amb la indicació visual (icona) i textual (descripció de l'error) de l'error. [CAT](https://www.w3.org/Translations/WCAG22-ca/#error-identification) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/error-identification)
- **On Focus (A)** — 3.2.1. Els elements que reben focus no generen canvis inesperats; només es fa visible quan el botó de salt al contingut principal rep focus. [CAT](https://www.w3.org/Translations/WCAG21-ca/#on-focus) / [EN](https://www.w3.org/WAI/WCAG21/quickref/#on-focus)
- **On Input (A)** — 3.2.2. L'activació del botó de salt al contingut principal (Intro o Espai) mou el focus i la vista al contingut principal sense comportaments inesperats. [CAT](https://www.w3.org/Translations/WCAG21-ca/#on-input) / [EN](https://www.w3.org/WAI/WCAG21/quickref/#on-input)

### Navegació per teclat
| Tecla | Acció |
|---|---|
| Tabulació | El botó es mostra i rep el focus. |
| Intro o Espai | El focus i la vista salten directament al `<main>`. |

## Components implicats
[Botons](component-botons.md), [Capçalera web pública](component-capcalera-web-publica.md), [Fils d'Ariadna](component-fils-d-ariadna.md).

## Historial de versions
| Versió Figma | Data | Descripció |
|---|---|---|
| 8.1.0 | 6 octubre, 2025 | Disseny i documentació del patró |
