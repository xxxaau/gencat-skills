# Botó de xat (Chat button)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/29d061 · Web component: `<chat-button-component>` i `<side-chat-button-component>` (paquet conversational) · Font actualitzada el 2026-09-28 · Extret el 2026-10-28

## Què és i quan usar-lo
El botó d'assistent virtual és l'element interactiu que permet a l'usuari iniciar una conversa amb el servei d'assistència virtual.

El Botó de Xat és un element persistent de la interfície d'usuari (UI) que serveix com a porta d'accés ràpid al diàleg de xat. La funció principal és assegurar que l'usuari pugui iniciar una conversa d'assistència des de qualsevol punt de l'aplicació o web, sense necessitat de navegar a una pàgina específica.

Segons el context d'ús, aquest botó pot presentar-se en dues variants: flotant i lateral.
- **Botó de xat flotant:** permet accedir a una assistència general i transversal des de qualsevol punt de la interfície. Es mostra superposat sobre el contingut i està pensat per a consultes puntuals o suport no vinculat a una tasca concreta.
- **Botó de xat lateral:** permet accedir a una assistència contextual vinculada al contingut o a la tasca que l'usuari està realitzant. Es posiciona integrat a la part superior de la pantalla i activa un panell lateral que conviu amb el contingut principal.

Quan s'utilitza:
- Quan és necessari oferir un punt d'accés visible i persistent a una experiència conversacional, ja sigui com a assistència general o com a suport contextual vinculat a la tasca que l'usuari està realitzant. S'utilitza quan es vol facilitar l'inici d'una conversa sense requerir navegació addicional, mantenint l'accés al xat disponible dins la mateixa interfície.

## Quan NO usar-lo / alternatives
- Quan l'accés al xat pugui interferir amb elements interactius o amb contingut rellevant de la interfície.
- Quan la conversa no aporta valor en aquell context, o quan existeixen mecanismes d'ajuda més simples i adequats per resoldre la necessitat de l'usuari.

## Anatomia

### Botó de xat flotant
1. **Botó de xat.**
2. **Insígnia:** serveix per indicar a l'usuari que hi ha un missatge nou quan el xat es troba minimitzat.
3. **Indicador de funció:** apareix a l'estat hover i conté la frase "En què et puc ajudar" o similar per donar context a l'usuari sobre la funcionalitat.

### Botó de xat lateral
Figma: Anatomia (Botó xat / Components / Botó de xat / DOC_Botó de xat / Anatomia).
1. **Botó de xat.**
2. **Indicador de funció:** apareix a l'estat hover i conté la frase "En què et puc ajudar" o similar per donar context a l'usuari sobre la funcionalitat.

## Variants, tipus i estats

### Botó de xat flotant

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Default / Hover / Pressed / Focus | Default |

### Botó de xat lateral

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Extra large - Medium >768 px / Medium <767 px - Small | - |
| State | Default / Hover / Pressed / Focus | Default |

Variants Figma: Side Chat button [Breakpoint = Extra large - Medium >768 px, State = Default] (subseccions Estats i Punt de tall).

## Comportament i interacció

### Botó de xat flotant: ubicació
Per convenció i per a una accessibilitat òptima, el Botó de Xat Flotant es col·loca de manera fixa a la **part inferior dreta** de la pantalla. Aquesta posició es manté inalterable durant l'esdeveniment de *scroll* de la pàgina, gràcies al seu estat fix.

Pel que fa a l'espaiat, el component se separa de la vora inferior de la finestra (*viewport*) per un marge de **40 píxels** i de la vora lateral (dreta) per un marge de **48 píxels**. Aquesta mesura assegura que el botó estigui sempre disponible, però que no s'adhereixi massa a la vora, evitant possibles solapaments amb barres de desplaçament del sistema operatiu o altres elements d'interfície.

### Botó de xat lateral: ubicació
A diferència del botó de xat flotant, aquest botó se situa a la part superior de la pantalla, adherit a la subcapçalera quan n'hi ha. Quan l'usuari fa scroll i la subcapçalera deixa de ser visible, el botó es reubica just sota la capçalera, i es manté fixa, per garantir-ne la visibilitat persistent. (Figma: Scroll, Botó xat / Components / Botó de xat / DOC_Botó de xat / Scroll.)

### En passar el ratolí (hover)
Per donar context a l'usuari sobre la funcionalitat del botó abans del clic, s'utilitza la interacció en passar el ratolí (*hover*). Quan l'usuari col·loca el punter del ratolí sobre el Botó de xat, s'ha de mostrar un **indicador de funció** amb un text breu i contextual.

## Contingut i microcopy
El text de l'indicador de funció serà sempre "En què et puc ajudar?" a excepció de quan s'utilitzi a pàgines amb identitat pròpia.

## Bones pràctiques

### Ubicació
- **NO FER:** No modifiquis la posició del botó en les diferents pàgines. Han de mantenir consistència.

### Color
- **NO FER:** No modifiquis el color del botó. Utilitza sempre el primari.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG) que cita el component:
- **1.4.1 Ús del color (A):** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a diferenciar els diferents estats s'inclouen subratllats, es juga amb la presència de farciment i el gruix de la vora. (https://www.w3.org/Translations/WCAG22-ca/#use-of-color · https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **1.4.3 Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. (https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum · https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **1.4.4 Canvia la mida del text (AA):** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. (https://www.w3.org/Translations/WCAG22-ca/#resize-text · https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **1.4.11 Contrast d'elements no textuals (AA):** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. (https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast · https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **2.1.1 Teclat (A):** tota la funcionalitat del contingut (navegar pels diferents botons) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. (https://www.w3.org/Translations/WCAG22-ca/#keyboard · https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **2.4.7 Focus visible (AA):** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. (https://www.w3.org/Translations/WCAG22-ca/#focus-visible · https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- **3.2.6 Ajuda consistent (AA):** el botó de xat, en tant que mecanisme d'ajuda i atenció a l'usuari, ha d'aparèixer sempre en la mateixa posició relativa en totes les pàgines on es mostra. (https://www.w3.org/Translations/WCAG22-ca/#consistent-help · https://www.w3.org/WAI/WCAG22/Understanding/consistent-help)

### Navegació per teclat
El botó de xat es situarà com a **últim element de la pàgina** pel que fa a l'ordre de teclat.

## Implementació (component web)

### `<chat-button-component>`
Paquet: conversational. Botó de xat flotant.

**Propietats**

Taula de la pàgina del lloc (amb obligatorietat):

| Propietat | Atribut HTML | Descripció | Obligatorietat | Tipus |
|---|---|---|---|---|
| `ariaLabelChatButton` | `aria-label-chat-button` | Aria label del xat button | Opcional | String |
| `ariaLabelBadge` | `aria-label-badge` | Aria label del badge | Opcional | String |
| `tooltipMessage` | `tooltip-message` | Missatge intern del tooltip | Opcional | String |
| `visibilityBadge` | `visibility-badge` | Visibilitat del badge | Opcional | Boolean |
| `uniqueId` | `unique-id` | Identificador únic per al botó | Obligatori | String |

Valors per defecte i matisos segons el PDF (v12.0.0):

| Propietat | Atribut HTML | Descripció (PDF) | Tipus | Per defecte |
|---|---|---|---|---|
| `ariaLabelBadge` | `aria-label-badge` | Atribut d'accessibilitat ARIA. | string | undefined |
| `ariaLabelChatButton` | `aria-label-chat-button` | Atribut d'accessibilitat ARIA. | string | undefined |
| `disabled` | `disabled` | Deshabilita el component impedint la interacció. | boolean | false |
| `tooltipMessage` | `tooltip-message` | Text del tooltip associat a l'element. | string | undefined |
| `uniqueId` | `unique-id` | Identificador únic de l'element. | string | undefined |
| `visibilityBadge` | `visibility-badge` | Mostra o amaga aquest element. | boolean | false |

[discrepància: el PDF documenta la propietat `disabled`, que no apareix a la taula del lloc]

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre | Tipus (PDF) |
|---|---|---|---|
| `chatButtonClick` | Esdeveniment llançat en fer clic sobre el botó (PDF: s'emet quan l'usuari fa clic al component) | `id` | `CustomEvent<string>` |

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<chat-button-component 
  tooltip-message="Missatge tooltip" 
  visibility-badge=true 
  aria-label-chat-button="Botó de xat"
  aria-label-badge="Nou missatge"
  unique-id="chat-button-1"
></chat-button-component>
```

**Exemple d'instància (PDF)**

```html
<chat-button-component
aria-label-badge="texto-ejemplo"
aria-label-chat-button="texto-ejemplo"
disabled=false
tooltip-message="texto-ejemplo"
unique-id="texto-ejemplo"
visibility-badge=false
></chat-button-component>
```

**Depèn de:** `tooltip-component` (paquet core; [Indicador de funció](component-indicador-de-funcio.md)).

**Utilitzat per:** `floating-chat-container-component` ([Contenidor de xat](component-contenidor-de-xat.md)).

### `<side-chat-button-component>`
Paquet: conversational. Botó de xat lateral. Aquest capítol només existeix al PDF; la pàgina del lloc no en documenta les propietats.

**Propietats (PDF)**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte |
|---|---|---|---|---|
| `buttonAriaLabel` | `button-aria-label` | Etiqueta descriptiva de l'element. | string | `Botó de xat lateral` |
| `customId` | `custom-id` | Identificador HTML personalitzat de l'element. | string | `side-chat-button-component-gencat` |
| `panelOpen` | `panel-open` | Activa o desactiva aquesta característica. | boolean | false |
| `stickyReferenceSelector` | `sticky-reference-selector` | Selector CSS de l'element de referència per al posicionament. | string | `` (cadena buida) |
| `tooltipMessage` | `tooltip-message` | Text del tooltip associat a l'element. | string | `En què et puc ajudar?` |

**Esdeveniments**

| Esdeveniment | Descripció | Tipus (PDF) |
|---|---|---|
| `sideChatButtonClick` | S'emet quan l'usuari fa clic al component. | `CustomEvent<string>` |

**Exemple d'instància (PDF)**

```html
<side-chat-button-component
button-aria-label='Botó de xat lateral'
custom-id='side-chat-button-component-gencat'
panel-open=false
sticky-reference-selector=''
tooltip-message='En què et puc ajudar?'
></side-chat-button-component>
```

**Depèn de:** `button-component` ([Botons](component-botons.md)).

**Utilitzat per:** `side-panel-chat-component` ([Contenidor de xat](component-contenidor-de-xat.md)).

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 4.0.0 | 10.0.0 | 8 maig, 2026 | Disseny: s'afegeix la variant "Medium <768 - Small". Desenvolupament: es posiciona el tooltip a la seva esquerra |
| 3.0.0 | 9.3.0 | 17 d'abril, 2026 | Disseny i documentació del component "Botó de xat lateral" |
| 1.0.0 | 9.3.0 | 20 març, 2026 | Desenvolupament: s'hi afegeix espai entre el tooltip del botó i el botó; s'introdueixen les mides de la imatge svg del botó en píxels perquè es redimensioni correctament en canviar la mida de font al navegador. |
| 1.0.0 | 9.0.0 | 12 gener, 2026 | Desenvolupament del component |
| 1.0.0 | - | 5 desembre, 2025 | Disseny i documentació del component |

## Vegeu també
- [Botons](component-botons.md): permet a l'usuari dur a terme accions en una pàgina o pantalla.
- [Contenidor de xat](component-contenidor-de-xat.md), [Indicador de funció](component-indicador-de-funcio.md), [Insígnia](component-insignia.md)
