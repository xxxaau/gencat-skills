# Capçalera secundària de xat (Chat subheader)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/56ee7a · Web component: `<chat-subheader-component>` (paquet conversational) · Font actualitzada el 2026-09-10 · Extret el 2026-10-28

## Què és i quan usar-lo
Component informatiu que se situa just sota la capçalera principal del xat. Té com a objectiu aportar **context funcional i legal** a l'usuari abans d'iniciar o continuar la conversa.

Inclou:
- **Especialitat del xat** (àmbit o tema pel qual està optimitzat l'assistent).
- **Avís legal** que informa que les respostes són generades per IA.

Aquest component **no és interactiu** i actua exclusivament com a **element de suport a la comprensió i transparència** del servei.

El component s'utilitza en els formats de xat següents:
- **Xat flotant:** integrat dins d'un panell modal o flotant, immediatament sota la capçalera principal.
- **Xat lateral:** integrat dins d'un panell lateral persistent, mantenint la mateixa jerarquia visual i semàntica.

En tots dos casos el contingut és **idèntic**; només varia l'amplada disponible, però **no el comportament ni la funció** del component.

## Anatomia
Figma: Botó de xat [Show category = True, Show disclaimer = True, Chat type = Floating].

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Chat type | Floating / Full width | Floating |
| Show Category* | True / False | True |
| Show Disclaimer* | True / False | True |

\* Aquestes propietats només estan disponibles per a la versió flotant.

## Comportament i interacció
La capçalera secundària es mostra a la part superior del xat, just per sota de la capçalera (si n'hi ha). Aquesta fa scroll amb la resta del cos del xat.

## Contingut i microcopy
Vegeu Bones pràctiques (enllaç a l'avís legal, longitud del text, títol de l'especialitat).

## Bones pràctiques

### Contingut i redacció
- **FER:** Inclou un enllaç a l'avís legal, en cas de necessitar ampliar la informació.
- **NO FER:** No incloguis textos excessivament llargs.
- **NO FER:** No utilitzis títols de l'especialitat massa ambigus.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG) que cita el component:
- **1.4.1 Ús del color (A):** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a diferenciar els diferents estats. (La font acaba la frase així.) (https://www.w3.org/Translations/WCAG22-ca/#use-of-color · https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **1.4.3 Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. (https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum · https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **1.4.4 Canvia la mida del text (AA):** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. (https://www.w3.org/Translations/WCAG22-ca/#resize-text · https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **1.4.12 Espaiat del text (AA):** quan es desenvolupa contingut utilitzant llenguatges de marcatge que permeten aplicar les propietats d'estil de text, no es perd cap contingut ni funcionalitat si s'ajusten les propietats següents: alçada de línia (interlineat) de com a mínim 1,5 vegades la mida de la lletra; espaiat entre els paràgrafs de com a mínim dues vegades la mida de la lletra; espaiat entre lletres (*tracking*) de com a mínim 0,12 vegades la mida de la lletra; espaiat entre paraules de com a mínim 0,16 vegades la mida de la lletra. (https://www.w3.org/Translations/WCAG22-ca/#text-spacing · https://www.w3.org/WAI/WCAG22/Understanding/text-spacing)

## Implementació (component web)

### `<chat-subheader-component>`
Paquet: conversational. La pestanya "Codi" de la pàgina del lloc és buida; les dades provenen del PDF (v12.0.0).

**Propietats (PDF)**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte |
|---|---|---|---|---|
| `descriptionSubheader` | `description-subheader` | Descripció de l'element. | string | undefined |
| `titleSubheader` | `title-subheader` | Títol del component. | string | undefined |

**Esdeveniments:** cap esdeveniment declarat.

**Exemple d'instància (PDF)**

```html
<chat-subheader-component
description-subheader="texto-ejemplo"
title-subheader="texto-ejemplo"
></chat-subheader-component>
```

**Utilitzat per (PDF):** `floating-chat-container-component`, `side-panel-chat-component` ([Contenidor de xat](component-contenidor-de-xat.md)).

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 3.0.0 | - | 17 abril, 2026 | Disseny del component |

## Vegeu també
- [Capçalera de xat](component-capcalera-de-xat.md), [Contenidor de xat](component-contenidor-de-xat.md)
