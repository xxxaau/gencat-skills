# Selector d'hora (Time picker)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/97ce1e · Font actualitzada el 2026-06-09 · Extret el 2026-10-28

## Què és i quan usar-lo
Permet a la persona usuària seleccionar una hora dins una llista de valors predefinits o introduir-la manualment.

Per implementar aquest patró s'utilitzen els components [Camp d'entrada](component-camp-d-entrada.md) i [Desplegable](component-desplegable.md) del sistema de disseny. Consulta la documentació de cada component per veure'n la configuració i el comportament.

### Selecció predefinida
Adequat quan:
- L'hora forma part d'un procés (cita, període, registre d'activitat).
- Cal limitar la selecció a franges horàries definides.
- Es vol facilitar la selecció mitjançant cerca filtrada.

No és adequat quan:
- L'hora és només informativa.
- El sistema assigna l'hora automàticament.

### Selecció lliure
- Quan la precisió és crítica (ex.: "Hora exacta de l'accident" o "Hora de naixement").
- Quan no hi ha intervals de negoci (cada minut és vàlid).
- Registres històrics: si l'usuari ha de marcar l'hora exacta en què va passar una incidència (ex.: 09:07).

## Anatomia
Figma: `anatomia` (Selector d'hora/Selector d'hora/DOC_Selectorhora/anatomia).

## Comportament
Interacció:
- En fer focus, es desplega la llista d'hores disponibles.
- Si l'usuari comença a escriure, la llista es filtra automàticament.
- L'usuari pot seleccionar una hora de la llista o introduir-la manualment.

Figma: `comportament`.

## Ubicació
S'integra dins de formularis, habitualment:
- Després d'un camp de data ([Selector de data](component-selector-de-data.md)).
- Formant part d'un bloc temporal (inici / finalització).
- Dins de seccions relacionades amb cites, terminis o planificació.

Quan s'utilitza conjuntament amb **dates d'inici i finalització**, l'ordre ha de ser:
1. Date picker
2. Data d'inici
3. Hora d'inici
4. Data de finalització
5. Hora de finalització

Figma: `ubicació`.

## Bones pràctiques
- **FER:** Utilitzar el format 12h (AM/PM) exclusivament per a usuaris angloparlants.
- **NO FER:** En un mateix formulari, tots els camps d'hora han d'utilitzar el mateix patró d'interacció. No es poden combinar models diferents (manual vs. desplegable).

### Selecció predefinida
- **NO FER:** Mantenir l'interval coherent: si fas servir intervals de 15 minuts, no barregis franges de 10 minuts en el mateix formulari. (Redacció de la font; el sentit és mantenir un interval coherent dins del formulari.)
- **FER:** Permetre que l'usuari escrigui per filtrar les opcions de la llista.

### Selecció lliure
- **FER:** No cal introduir un format específic (":") per a mostrar opcions. Ha d'aparèixer automàticament.

## Accessibilitat (WCAG)
- **Orientació (AA) 1.3.4:** el contingut de l'àrea de text s'adapta a les diferents orientacions de la pantalla, com ara vertical o horitzontal, cosa que permet visualitzar el contingut. [CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Ús del color (A) 1.4.1:** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a diferenciar els diferents estats s'inclouen subratllats, es juga amb la presència de farciment i el gruix de la vora. [CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA) 1.4.3:** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA) 1.4.4:** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA) 1.4.11:** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A) 2.1.1:** tota la funcionalitat del contingut (navegar pels diferents botons) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Focus visible (AA) 2.4.7:** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- **Identificació d'errors (A) 3.3.1:** si es detecta un error en el component, s'identifica clarament que aquest presenta un error mitjançant un canvi de color i gruix de la vora i amb la indicació visual (icona) i textual (descripció de l'error) de l'error. [CAT](https://www.w3.org/Translations/WCAG22-ca/#error-identification) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/error-identification)

### Navegació per teclat

| Tecla | Acció |
|---|---|
| Tabulació | Navegació fins al component. Navegar per les diferents opcions del desplegable (un cop obert) |
| Fletxes | Desplaçar-se per les diferents opcions del desplegable de selecció individual. Desplaçar-se pels diferents elements del camp de suggeriments (cerques suggerides que coincideixin amb la introducció de la persona usuària). |
| Intro | Seleccionar una opció |
| Esc | Cancel·lar una acció |

## Historial de versions

| Versió Figma | Data | Descripció |
|---|---|---|
| 9.0.0 | 27 febrer, 2026 | Disseny i documentació del patró |

## Vegeu també
[Camp d'entrada](component-camp-d-entrada.md) · [Desplegable](component-desplegable.md) · [Selector de data](component-selector-de-data.md) · [Introducció de dades](patro-introduccio-de-dades.md)
