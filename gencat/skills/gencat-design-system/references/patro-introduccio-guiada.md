# Introducció guiada (Onboarding)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/88e371 · Patró · Font actualitzada el 2026-07-23 · Extret el 2026-10-28

## Què és i quan usar-lo
Solució d'orientació breu que acompanya la persona usuària en el primer accés a un servei, espai o experiència digital per ajudar-la a entendre què hi pot fer i com començar. És adequat quan cal oferir una orientació inicial breu abans de començar a utilitzar un espai digital, especialment quan l'entorn és nou o pot generar dubtes en el primer accés.

Es pot presentar mitjançant una modal o una seqüència curta de pantalles inicials. També pot tenir una variant relacionada per introduir novetats o funcionalitats noves dins d'un entorn ja conegut.

### Quan utilitzar
- Quan la persona usuària accedeix per primera vegada a un servei, espai o experiència digital i es vol reduir la desorientació inicial.
- Quan cal donar un context inicial abans de començar a utilitzar l'entorn sense interrompre necessàriament.
- Quan convé explicar de manera breu què es pot fer, quin és el valor de l'espai o quin és el primer pas recomanat.
- Quan es vol destacar una funcionalitat o novetat rellevant dins d'un entorn ja conegut, com a variant relacionada.
- Quan es vol oferir una guia breu de consulta voluntària.

## Quan NO usar-lo / alternatives
- Quan la interfície ja és prou clara i autoexplicativa per si sola.
- Quan la persona usuària arriba amb un objectiu immediat i l'onboarding només afegeix fricció.
- Quan es vol utilitzar per explicar tot el sistema de manera exhaustiva.
- Quan el que cal és guiar la persona usuària a través d'un procés seqüencial i obligatori per completar una tasca; en aquests casos és més adequat un wizard ([Pas a pas](component-pas-a-pas.md)).

## Anatomia
Figma: disseny extralarge | small (modal als punts de tall grans; pantalla completa a Small).

## Punts de tall
- Extra Large, Large i Medium: la introducció guiada es presenta en format modal ([Modals](component-modals.md)).
- Small: la introducció guiada passa a ocupar tota la pantalla.

## Comportament i interacció

### Obertura
- Es mostra quan la persona usuària accedeix per primera vegada a un espai, servei o funcionalitat. El recorregut s'inicia des del primer pas i es presenta de manera seqüencial, mostrant un sol pas cada vegada, si escau.
- En els casos en què també hi hagi un gestor de cookies, la modal s'ha d'obrir un cop aquest s'hagi resolt, deixant un marge de 2 segons i apareixent de manera suau per no generar una interrupció brusca.
- Sempre que sigui possible, es recomana oferir l'accés a la introducció guiada des d'un element visible dins la pàgina, com ara un avís, un banner o un bloc destacat, en lloc d'obrir-la automàticament ([Avisos](component-avisos.md), [Bàner](component-baner.md), [Panell destacat](component-panell-destacat.md)).

### Navegació entre passos
Quan el recorregut té més d'un pas, es pot mostrar una paginació per indicar l'estat d'avanç.
- Primer pas: l'acció principal s'etiqueta com a **Comença**.
- Passos intermedis: la navegació es resol mitjançant fletxes laterals per tornar al pas anterior o avançar al següent.
- Pas final: l'acció principal passa a ser **Finalitza**.

### Tancament
La modal ha d'incloure una acció de tancament visible a la part superior. Si la persona usuària la tanca abans de completar el recorregut, la introducció guiada es considera descartada.

### Recuperació
Si la persona usuària tanca la introducció guiada o no la completa, no s'ha de tornar a mostrar automàticament. Si cal tornar-la a consultar, ha d'estar disponible des d'un punt estable de suport o ajuda dins de l'entorn.

## Bones pràctiques

### Contingut i claredat
- **FER:** Prioritza només la informació imprescindible per començar amb un missatge breu i clar.
- **FER:** Mostra una única idea principal per pantalla o pas.
- **FER:** El títol ha de ser breu i la descripció no hauria de superar les quatre línies en condicions normals de visualització.
- **FER:** Si un dels passos incorpora il·lustració, es recomana mantenir el recurs també a la resta del recorregut per coherència visual.
- **NO FER:** No facis servir textos llargs, genèrics o promocionals.
- **NO FER:** No repeteixis contingut que ja és evident a la interfície.
- **NO FER:** No ha de tenir interaccions alienes a la modal, com enllaços o accessos.
- **FER:** Adapta l'onboarding segons l'entorn, el perfil o el context, encara que sigui en part.

### Estructura del recorregut
- **FER:** Si es presenta en diversos passos, aquests han de ser pocs, breus i fàcils de recórrer.
- **FER:** Permet ometre la introducció guiada.
- **NO FER:** No obliguis a recórrer múltiples pantalles si no aporten valor real.
- **NO FER:** No ha de tenir desplaçament vertical, excepte en casos de zoom o augment de text.
- **FER:** Prioritza, sempre que sigui possible, una entrada activable abans que una interrupció automàtica.

### Finalitat del patró
- **NO FER:** No el converteixis en un tutorial complet del producte.
- **NO FER:** No utilitzis aquest patró per resoldre errors, avisos o validacions.

### Il·lustracions
- Són opcionals, no obligatòries.
- Si la introducció guiada és per passos i un d'aquests té una il·lustració, la resta hauria de tenir-ne també.
- Han de reforçar el missatge, no explicar informació crítica per si soles.
- Han de ser simples, clares i secundàries respecte al text.
- No han de competir amb el títol, la descripció ni les accions.
- Han d'evitar detall excessiu, soroll visual o metàfores difícils d'interpretar.
- Han de ser coherents amb el to visual institucional.
- No han d'incloure text integrat dins la pròpia il·lustració.
- La informació important no ha de dependre de la imatge.

Per als criteris d'ús i tractament de les il·lustracions, vegeu [Il·lustracions](fonaments-illustracions.md) (font: https://sistemadedisseny.gencat.cat/38669693e/p/55aba8).

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG):

- **Orientació (AA)** — 1.3.4. El contingut de l'àrea de text s'adapta a les diferents orientacions de la pantalla, com ara vertical o horitzontal, cosa que permet visualitzar el contingut. [CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Contrast mínim (AA)** — 1.4.3. Els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA)** — 1.4.4. Excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA)** — 1.4.11. Els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A)** — 2.1.1. Tota la funcionalitat del contingut (navegar pels diferents botons) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Sense trampa de teclat (A)** — 2.1.2. Si el focus del teclat es pot moure a un component de la pàgina mitjançant una interfície de teclat, llavors el focus es pot allunyar d'aquest component utilitzant només una interfície de teclat. Amb la tecla "Esc" l'usuari pot sortir de la modal. [CAT](https://www.w3.org/Translations/WCAG22-ca/#no-keyboard-trap) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/no-keyboard-trap)
- **Ordre del focus (A)** — 2.4.3. Les modals presenten un ordre lògic del focus dels elements interns per facilitar la navegació per teclat o altres dispositius d'entrada. L'ordre ha de seguir el flux de la informació o les tasques que s'estan presentant. L'ordre ha de ser el següent: [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-order) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-order)
  1. Quan la modal s'obre, el focus ha d'entrar dins del diàleg.
  2. El contingut s'ha d'anunciar correctament a tecnologies de suport, incloent-hi el pas actual, el títol i el text descriptiu.
  3. Un cop anunciat el contingut, el focus s'ha de desplaçar als controls interactius començant per l'acció principal, si no hi ha cap altre element interactiu previ rellevant.
  4. En els passos intermedis o finals, el focus ha de recórrer les accions del peu en l'ordre visual establert, per exemple Anterior, Següent o Finalitza, i continuar després amb l'acció de tancament.
  5. En tancar la modal, el focus ha de tornar a l'element des d'on s'ha obert o, si s'ha obert automàticament, al primer element interactiu rellevant de la pantalla.
- **Focus visible (AA)** — 2.4.7. La navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

### Navegació per teclat
| Tecla | Acció |
|---|---|
| Tabulació | Navegar al següent element interactiu. |
| Shift + Tabulació | Navegar a l'anterior element interactiu. |
| Intro / Enter | Activa l'element seleccionat. |
| Esc | Tanca el diàleg. |

### Focus
- Quan la modal s'obre, el focus ha d'entrar dins del diàleg.
- El contingut s'ha d'anunciar correctament a tecnologies de suport, incloent-hi el pas actual, el títol i el text descriptiu.
- Un cop anunciat el contingut, el focus s'ha de desplaçar als controls interactius començant per l'acció principal, si no hi ha cap altre element interactiu previ rellevant.
- En els passos intermedis o finals, el focus ha de recórrer les accions del peu en l'ordre visual establert, per exemple Anterior, Següent o Finalitza, i continuar després amb l'acció de tancament.
- En tancar la modal, el focus ha de tornar a l'element des d'on s'ha obert o, si s'ha obert automàticament, al primer element interactiu rellevant de la pantalla.

## Components implicats
[Modals](component-modals.md), [Paginació](component-paginacio.md), [Botons](component-botons.md), [Avisos](component-avisos.md), [Bàner](component-baner.md), [Panell destacat](component-panell-destacat.md).

## Historial de versions
| Versió Figma | Data | Descripció |
|---|---|---|
| 11.0.0 | 08 maig, 2026 | Disseny i documentació del patró |
