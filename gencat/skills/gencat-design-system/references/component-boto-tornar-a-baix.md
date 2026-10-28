# Botó tornar a baix (Back to bottom button)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/122880 · Web component: `<back-to-bottom-button-component>` (paquet conversational) · Font actualitzada el 2026-06-09 · Extret el 2026-10-28

## Què és i quan usar-lo
El botó de tornar abaix permet als usuaris desplaçar-se ràpidament a la part inferior d'una conversa de xat.

El botó Tornar a baix permet als usuaris desplaçar-se ràpidament a la part inferior d'un xat. Apareix en determinades condicions i s'oculta quan no és necessari per garantir una experiència d'usuari fluida i accessible.

Quan s'utilitza:
- Quan la conversa del xat té un contingut llarg i l'usuari ha de desplaçar-se significativament per tornar a l'últim missatge.

## Quan NO usar-lo / alternatives
- Quan la conversa encara només disposa de pocs missatges.

## Anatomia
Figma: Back to bottom (Botó tornar a baix / Botó de xat / Back to bottom).

## Comportament i interacció

### Ubicació i scroll
- El botó de tornar a baix apareix quan l'usuari realitza un scroll cap amunt equivalent a **0.75 viewport** (si estem en un mòbil de 853 px d'alt, apareixerà al sobrepassar 639,75 px).
- Es situa a la part inferior del cos del xat, a **16 px per sobre del límit inferior.**
- Exemple en pàgina al patró [Xat a pantalla completa](patro-xat-a-pantalla-completa.md) (https://sistemadedisseny.gencat.cat/38669693e/p/3006bf).

### Nous missatges
Quan l'usuari està parlant amb una segona persona, ha fet scroll per consultar missatges antics i rep un nou missatge, el botó de tornar a baix mostra un text per indicar que hi ha missatges nous.

## Bones pràctiques

### Claredat
- **NO FER:** Mantenir sempre la mateixa icona; no la substitueixis per una altra.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG) que cita el component:
- **1.4.1 Ús del color (A):** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a diferenciar els diferents estats s'inclouen subratllats, es juga amb la presència de farciment i el gruix de la vora. (https://www.w3.org/Translations/WCAG22-ca/#use-of-color · https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **1.4.3 Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. (https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum · https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **1.4.4 Canvia la mida del text (AA):** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. (https://www.w3.org/Translations/WCAG22-ca/#resize-text · https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **1.4.11 Contrast d'elements no textuals (AA):** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. (https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast · https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **2.1.1 Teclat (A):** tota la funcionalitat del contingut (navegar pels diferents botons) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. (https://www.w3.org/Translations/WCAG22-ca/#keyboard · https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **2.4.7 Focus visible (AA):** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. (https://www.w3.org/Translations/WCAG22-ca/#focus-visible · https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- **4.1.3 Missatges d'estat (AA):** en el contingut implementat mitjançant llenguatges de marques, els missatges d'estat es poden identificar amb programació pel rol o les propietats, de manera que es puguin presentar mitjançant ajudes tècniques sense rebre focus. S'apliquen etiquetes ARIA (`role="alert"` `aria-live="assertive"`). Quan hi hagi un missatge nou, s'avisarà a l'usuari mitjançant aquestes etiquetes. (https://www.w3.org/Translations/WCAG22-ca/#status-messages · https://www.w3.org/WAI/WCAG22/Understanding/status-messages.html)

## Implementació (component web)

### `<back-to-bottom-button-component>`
Paquet: conversational.

**Propietats**

Taula de la pàgina del lloc (amb obligatorietat):

| Propietat | Atribut HTML | Descripció | Obligatorietat | Tipus |
|---|---|---|---|---|
| `newMessages` | `new-messages` | Quan el valor sigui true, el botó contindrà un text que indiqui que hi ha nous missatges. Quan sigui false, el botó no tindrà text | Opcional | Boolean |

Segons el PDF (v12.0.0):

| Propietat | Atribut HTML | Descripció (PDF) | Tipus | Per defecte |
|---|---|---|---|---|
| `newMessages` | `new-messages` | Activa o desactiva aquesta característica. | boolean | false |

**Esdeveniments:** cap esdeveniment declarat.

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<back-to-bottom-button-component
  newMessages="true">
</back-to-bottom-button-component>
```

**Exemple d'instància (PDF)**

```html
<back-to-bottom-button-component
new-messages=false
></back-to-bottom-button-component>
```

**Depèn de:** `button-component` ([Botons](component-botons.md)).

**Utilitzat per:** `floating-chat-container-component` (lloc i PDF), `side-panel-chat-component` (PDF) ([Contenidor de xat](component-contenidor-de-xat.md)).

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 2.1.0 | 9.4.0 | 17 abril, 2026 | Desenvolupament: s'ha afegit la propietat `newMessages`. |
| 2.1.0 | 9.3.0 | 20 març, 2026 | Disseny: s'elimina la rotació de 180º del component; s'afegeix la variant per quan hi ha missatges nous al xat. Desenvolupament del component |
| 2.0.0 | - | 02 març, 2026 | Disseny del component |

## Vegeu també
- [Botons](component-botons.md), [Contenidor de xat](component-contenidor-de-xat.md), [Xat a pantalla completa](patro-xat-a-pantalla-completa.md)
