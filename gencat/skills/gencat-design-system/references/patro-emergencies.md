# Emergències (Emergencies)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/37e589 · Patró · Font actualitzada el 2026-06-18 · Extret el 2026-10-28

## Què és i quan usar-lo
Serveix per informar l'usuari sobre situacions d'urgència o risc imminent com alguna DANA, terratrèmols, activitat volcànica o emergències sanitàries.

Hi ha quatre tipus d'emergències, segons el grau d'activació del pla:
- Emergència
- Alerta
- Prealerta
- Fi d'alerta

### Quan s'utilitza
Per informar la ciutadania de situacions d'urgència o risc imminent, com ara:
- Fenòmens meteorològics greus (DANA, inundacions, incendis).
- Sismes o terratrèmols.
- Activitat volcànica.
- Alertes sanitàries o de seguretat.

## Quan NO usar-lo / alternatives
- **Validació dins un formulari:** mostrant errors o missatges d'èxit.
- **Alertes específiques de context:** proporcionant informació crítica o avisos relacionats amb una secció específica del contingut (per exemple, un missatge d'error sobre una secció de càrrega de dades fallida).
- **Actualitzacions o instruccions d'estat importants** que l'usuari ha de reconèixer o a les quals ha de reaccionar.
- **Comunicar informació trivial:** no rellevant o no important per l'usuari.
- **Fer seguiment d'una acció rutinària** realitzada per l'usuari que no és crítica (missatges de retroalimentació efímera). En aquests casos, es fa servir una notificació emergent ([Notificació emergent](component-notificacio-emergent.md)).

## Anatomia
En el cas d'**emergència**, alerta i prealerta, la informació prové de la pàgina detall de l'avís. En el cas d'avisos de **finalització** no hi ha pàgina associada: cal editar el contingut específic per a l'avís.

## Variants, tipus i estats

### Emergència
És l'única tipologia que es presenta en dues modalitats:
- **Extensa:** s'utilitza únicament per a la pàgina principal.
- **Compacta:** s'utilitza a la pàgina principal quan conviu amb altres avisos i per a la resta de pàgines, tant quan es mostra de forma individual com en llistat amb altres emergències.

### Alerta
Sempre en versió compacta. Es mostra en totes les pàgines.

### Prealerta
Sempre en versió compacta. Es mostra únicament a la pàgina principal.

### Fi d'alerta
Sempre en versió compacta. Es mostra en totes les pàgines.

## Ubicació
Les emergències se situen **sempre a la part superior de la pàgina**, just per sobre de la capçalera ([Capçalera web pública](component-capcalera-web-publica.md)).

## Comportament i interacció

### Jerarquia
Quan hi ha diverses emergències a la vegada, es mostren **ordenades en funció de la gravetat** de l'avís:
1. Emergència
2. Alerta
3. Prealerta

**Si conviuen dues o més emergències del mateix nivell**, s'ordenen entre elles **per data d'actualització**, sent la darrera que s'hagi actualitzat la primera a aparèixer (a la part superior).

### Fi d'alerta
Quan el risc d'una emergència hagi passat, es mostra la tipologia de fi d'alerta. És l'única versió que **disposa d'aspa perquè l'usuari pugui tancar l'avís**. Apareix a la ubicació on es trobava l'emergència que ha finalitzat.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG):

- **Ús del color (A)** — 1.4.1. El color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a diferenciar els diferents estats. [CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA)** — 1.4.3. Els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA)** — 1.4.4. Excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA)** — 1.4.11. Els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Espaiat del text (AA)** — 1.4.12. Quan es desenvolupa contingut utilitzant llenguatges de marcatge que permeten aplicar les propietats d'estil de text, no es perd cap contingut ni funcionalitat si s'ajusten les propietats següents: [CAT](https://www.w3.org/Translations/WCAG22-ca/#text-spacing) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/text-spacing)
  - Alçada de línia (interlineat) de com a mínim 1,5 vegades la mida de la lletra.
  - Espaiat entre els paràgrafs de com a mínim dues vegades la mida de la lletra.
  - Espaiat entre lletres (tracking) de com a mínim 0,12 vegades la mida de la lletra.
  - Espaiat entre paraules de com a mínim 0,16 vegades la mida de la lletra.
- **Teclat (A)** — 2.1.1. Tota la funcionalitat del contingut es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Ordre del focus (A)** — 2.4.3. Les emergències presenten un ordre lògic del focus dels elements interns per facilitar la navegació per teclat o altres dispositius d'entrada. L'ordre del focus és el següent: [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-order) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-order)
  1. Giny (si n'hi ha): aquest podria tenir diferents elements interactius que seguirien el seu propi ordre.
  2. Enllaç.
  3. Botó de tancament (si n'hi ha).
- **Focus visible (AA)** — 2.4.7. La navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- **Missatges d'estat (AA)** — 4.1.3. En el contingut implementat mitjançant llenguatges de marques, els missatges d'estat es poden identificar amb programació pel rol o les propietats, de manera que es puguin presentar mitjançant ajudes tècniques sense rebre focus. S'apliquen etiquetes ARIA (`role="alert"` `aria-live="assertive"`). [CAT](https://www.w3.org/Translations/WCAG22-ca/#status-messages) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/status-messages.html)

### Navegació per teclat
| Tecla | Acció |
|---|---|
| Tabulació | Navegació al següent element interactiu |
| Shift + Tabulació | Navegació a l'anterior element interactiu |
| Enter | Activar element interactiu |

## Components implicats
[Capçalera web pública](component-capcalera-web-publica.md) (les emergències se situen just per sobre de la capçalera), [Notificació emergent](component-notificacio-emergent.md) (alternativa per a feedback efímer). La relació amb [Avisos](component-avisos.md) i [Pàgines d'error i manteniment](patro-pagines-d-error-i-manteniment.md) no consta a la font [a verificar].

## Historial de versions
| Versió Figma | Data | Descripció |
|---|---|---|
| 12.1.0 | 19 juny, 2026 | Disseny: s'apliquen slots pel contingut de gràfics. |
| 8.2.0 | 27 octubre, 2025 | Disseny: revisió d'estils tipogràfics |
| 7.0.0 | 28 juliol, 2025 | Disseny i documentació del patró |
