# Capçalera de xat (Chat header)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/628537 · Web component: `<chat-header-component>` (paquet conversational) · Font actualitzada el 2026-10-20 · Extret el 2026-10-28

## Què és i quan usar-lo
Secció superior d'un xat que proporciona un lloc coherent per a la marca i l'accés a funcionalitats globals. Aquesta capçalera s'adapta en funció d'on s'ubica el xat.

La capçalera serveix per **identificar el xat** i **permetre accions immediates** relacionades amb la finestra (tancar, minimitzar o col·lapsar). No busca aportar informació secundària ni opcions avançades, sinó mantenir el focus en la conversa.

Quan s'utilitza:
- Apareix quan la finestra és inequívocament un **mòdul de xat** i cal una capçalera mínima però informativa.

## Quan NO usar-lo / alternatives
- No és adequada quan el component deixa de ser estrictament un xat o quan la capçalera ha de complir funcions més àmplies.

## Anatomia
Figma: Chat header [Show Subheader = False, ↳ Subheader = Especialitat del xat, Type = Full width]; Anatomia (Capçalera de xat / Components / Botó de xat / DOC_Capçalera de xat / Anatomia).

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Type | Full width / Floating / Side | Full width |
| Show subheader | True / False | False |
| ↳ Subheader | Text | Especialitat del xat |

Per veure com s'utilitza la capçalera en funció del punt de tall, consulta la documentació del [Contenidor de xat](component-contenidor-de-xat.md) (xat flotant; https://sistemadedisseny.gencat.cat/38669693e/p/919d00).

## Comportament i interacció

### Ubicació i scroll
**Pantalla completa**
- Apareix a la part superior del xat i no queda fixada: fa scroll amb el contingut del xat o la pàgina.
- Per veure en més detall el layout a pantalla completa consulta el patró [Xat a pantalla completa](patro-xat-a-pantalla-completa.md) (https://sistemadedisseny.gencat.cat/38669693e/p/3006bf).

**Xat flotant**
- Apareix a la part superior del xat i queda fixada: no fa scroll amb el contingut del xat o la pàgina.
- Per veure en més detall el layout consulta el patró [Xat flotant](patro-xat-flotant.md).

**Xat lateral**
- Apareix a la part superior del xat i queda fixada: no fa scroll amb el contingut del xat o la pàgina.
- Per veure en més detall el layout consulta el patró [Xat lateral](patro-xat-lateral.md).

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG) que cita el component:
- **1.4.1 Ús del color (A):** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a diferenciar els diferents estats s'inclouen subratllats, es juga amb la presència de farciment i el gruix de la vora. (https://www.w3.org/Translations/WCAG22-ca/#use-of-color · https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **1.4.3 Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. (https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum · https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **1.4.4 Canvia la mida del text (AA):** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. Si el text de la capçalera creix i no hi ha suficient espai, aquest saltarà de línia i es col·locarà inferiorment als botons de la capçalera. Els botons es mantindran a la part superior dreta. (Figma: Augment de text, Capçalera de xat / Components / Botó de xat / DOC_Capçalera de xat / Augment de text.) (https://www.w3.org/Translations/WCAG22-ca/#resize-text · https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **1.4.11 Contrast d'elements no textuals (AA):** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. (https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast · https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **2.1.1 Teclat (A):** tota la funcionalitat del contingut (navegar pels diferents botons) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. (https://www.w3.org/Translations/WCAG22-ca/#keyboard · https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **2.4.3 Ordre del focus (A):** la capçalera presenta un ordre lògic del focus dels elements interns per facilitar la navegació per teclat o altres dispositius d'entrada. L'ordre ha de seguir el flux de la informació o les tasques que s'estan presentant. L'ordre ha de ser el següent: (1) primer botó començant per l'esquerra, per exemple el menú (opcional); (2) segon botó en direcció de lectura esquerra-dreta, que sempre serà el de minimitzar; (3) tercer i últim botó, que sempre serà el de tancament. (https://www.w3.org/Translations/WCAG22-ca/#focus-order · https://www.w3.org/WAI/WCAG22/Understanding/focus-order)
- **2.4.7 Focus visible (AA):** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. (https://www.w3.org/Translations/WCAG22-ca/#focus-visible · https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- **2.4.11 Focus no ocult (AA):** la capa de superposició del modal no pot ocultar cap element que tingui el focus de teclat. Mentre el modal és obert, el focus ha de quedar atrapat dins seu i no pot accedir als elements de la pàgina de darrere. Aquesta consideració és especialment rellevant en dispositius mòbils i tauletes amb zoom de pantalla activat. (https://www.w3.org/Translations/WCAG22-ca/#focus-not-obscured-minimum · https://www.w3.org/WAI/WCAG22/Understanding/focus-not-obscured-minimum)

## Implementació (component web)

### `<chat-header-component>`
Paquet: conversational.

**Propietats**

Taula de la pàgina del lloc (amb obligatorietat):

| Propietat | Atribut HTML | Descripció | Obligatorietat | Tipus |
|---|---|---|---|---|
| `mode` | `mode` | Permet configurar la vista de la capçalera en funció de si es farà servir en xat flotant o en xat a pantalla completa | Obligatori | String |
| `nameChat` | `name-chat` | Nom del xat | Obligatori | String |
| `category` | `category` | Categoria o especialitat del xat | Opcional | String |

Valors per defecte i matisos segons el PDF (v12.0.0):

| Propietat | Atribut HTML | Descripció (PDF) | Tipus | Per defecte |
|---|---|---|---|---|
| `category` | `category` | Categoria o secció a la qual pertany l'element. | string | undefined |
| `mode` | `mode` | Variant visual del component. Opcions: `floating`, `full-width`. | string | `floating` |
| `nameChat` | `name-chat` | Nom que es mostra a la capçalera del xat. | string | undefined |

**Variants (lloc)**

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `mode` | `floating` `full-width` | `floating` |

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre | Origen | Tipus (PDF) |
|---|---|---|---|---|
| `chatAction` | Esdeveniment vàlid per al mode floating. Es dispara en prémer el botó de tancament o minimitzat, indicant l'acció que s'està realitzant. (PDF: s'emet quan es produeix aquest esdeveniment al component.) | Acció: `close` `minimize` | `chat-header-component` | `CustomEvent<"close" …` (el PDF talla el tipus; valors `close` / `minimize`) |

**Slots**

Components que es poden introduir mitjançant slot:
- **`button-component`:** s'utilitzarà per ser introduït a la capçalera del xat dins del grup de botons que inclou el botó de minimitzar i tancar xat. Atribut: `slot="group-button-chat-header"`.

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<chat-header-component 
  mode="full-width"
  name-chat="Pregunta'm" 
  category="Especialitat del xat"
></chat-header-component>
```

**Exemple d'instància (PDF)**

```html
<chat-header-component
category="texto-ejemplo"
mode='floating'
name-chat="texto-ejemplo"
></chat-header-component>
```

**Depèn de:** `divider-component` (lloc; [Divisor](component-divisor.md)); `group-button-component` i `button-component` (PDF; [Grup de botons](component-grup-de-botons.md), [Botons](component-botons.md)).

**Utilitzat per:** `floating-chat-container-component` (lloc i PDF), `side-panel-chat-component` (PDF) ([Contenidor de xat](component-contenidor-de-xat.md)).

[discrepància: el lloc diu que depèn de `divider-component`; el PDF diu que depèn de `group-button-component` i `button-component`]

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 10.0.0 | 11.0.0 | 19 juny, 2026 | Desenvolupament: es modifica l'alçada a partir de la qual s'introdueix la classe wrapper-buttons-full-width |
| 10.0.0 | 9.4.0 | 17 abril, 2026 | Disseny: s'elimina la subcapçalera com a asset i es posa com a component nou. Desenvolupament: s'ha desenvolupat la variant floating, diferenciada de full-width mitjançant la propietat `mode`. |
| 2.1.0 | 9.3.0 | 20 març, 2026 | Disseny: disseny de variant per xat flotant. Desenvolupament del component |
| 2.0.0 | - | 02 març, 2026 | Disseny del component |

## Vegeu també
- [Capçalera secundària de xat](component-capcalera-secundaria-de-xat.md), [Contenidor de xat](component-contenidor-de-xat.md), [Botons](component-botons.md), [Xat a pantalla completa](patro-xat-a-pantalla-completa.md), [Xat flotant](patro-xat-flotant.md), [Xat lateral](patro-xat-lateral.md)
