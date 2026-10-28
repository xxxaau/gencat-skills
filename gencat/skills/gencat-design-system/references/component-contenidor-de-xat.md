# Contenidor de xat (Chat container)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/919d00 · Web component: `<floating-chat-container-component>` i `<side-panel-chat-component>` (paquet conversational) · Font actualitzada el 2026-07-10 · Extret el 2026-10-28

## Què és i quan usar-lo
Component estructural que organitza els diferents elements de la conversa en un layout vertical. Permet la comunicació entre l'usuari i un sistema de missatgeria, com ara un bot, una IA o un agent humà. Segons el context d'ús, es pot presentar com a contenidor flotant o com a panell lateral.

La capçalera permet identificar el xat i accedir a les accions immediates disponibles sobre el contenidor, com ara tancar-lo, minimitzar-lo o col·lapsar-lo, segons la variant. La seva funció és operativa i no informativa: no incorpora contingut secundari ni opcions avançades, per tal de mantenir el focus en la conversa.

Existeixen dos tipus de contenidor de xat, que responen a necessitats d'ús diferents segons el context de la interfície: **el contenidor de xat flotant i el panell de xat lateral.**

### Contenidor de xat flotant
Variant superposada del contenidor de xat, pensada per oferir assistència general i transversal sense alterar l'estructura de la pàgina. Vegeu el patró [Xat flotant](patro-xat-flotant.md) (https://sistemadedisseny.gencat.cat/38669693e/p/079d5f-xat-flotant).

Quan s'utilitza:
- Apareix quan la finestra és inequívocament un **mòdul de xat** i cal una capçalera mínima però informativa.

### Panell de xat lateral
Variant integrada lateralment, pensada per oferir assistència contextual i continuada vinculada a la tasca. Vegeu el patró [Xat lateral](patro-xat-lateral.md) (https://sistemadedisseny.gencat.cat/38669693e/p/02ab59-xat-lateral).

Quan s'utilitza:
- Quan l'assistència està vinculada al contingut o a la tasca que l'usuari està realitzant, i cal una experiència integrada dins la pàgina que permeti conviure el xat amb el contingut principal.

## Quan NO usar-lo / alternatives
- **Contenidor flotant:** no és adequat quan el component deixa de ser estrictament un xat o quan la capçalera ha de complir funcions més àmplies.
- **Panell lateral:** quan es busca una ajuda general, transversal i puntual, o quan l'espai disponible no permet mostrar el panell sense comprometre la llegibilitat o l'ús del contingut principal.

## Anatomia

### Contenidor de xat flotant
Figma: Anatomia (Contenidor de xat flotant / Components / Botó de xat / DOC_Contenidor de xat flotant / Anatomia).

### Contenidor de xat lateral
- Extra large - Medium: Figma Side chat container [Show Scroll Bar = False, Show Back to Bottom Button = False, Breakpoint = Extra Large - Medium].
- Medium - Small: Figma Side chat container (la font mostra la mateixa referència de variant).

## Variants, tipus i estats

### Contenidor de xat flotant

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Extra Large - Medium / Medium - Small | Full width |
| Closing | True / False | False |
| Show Scroll | True / False | False |
| Show Back to Bottom Button | True / False | False |

Variant Figma: Floating chat container [Show Scroll = False, Show Back to Bottom Button = False, Breakpoint = Extra Large - Medium, Closing = False].

**Punt de tall**
- Extra Large - Medium: fins a 768 px.
- Medium - Small: de 767 px a 320 px.

En el punt de tall Medium conviuen les dues formes del contenidor del xat, com a element flotant i com a panell emergent. El canvi entre un i l'altre es realitza a 768 px. **A partir dels 767 px es mostra amb la versió per a punt de tall Medium - Small.**

**Closing:** variant Figma Floating chat container [... Closing = False].

### Cos (Body) del contenidor flotant
El Body (Cos) del contenidor està format per un component amb les propietats següents:

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Slot Message | Slot | Chat message |
| Show Subheader | True / False | False |

Figma: cos_subheader (Contenidor de xat flotant / Components / Botó de xat / DOC_Contenidor de xat flotant / cos_subheader); `_Body` (Contenidor de xat / Botó de xat / _Body).

### Contenidor de xat lateral

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Show Scroll | True / False | False |
| Breakpoint | Extra large - Medium / Medium - Small | - |
| Show Back to Bottom Button | True / False | False |

Variant Figma: Side chat container [Show Scroll Bar = False, Show Back to Bottom Button = False, Breakpoint = Extra Large - Medium].

## Mides i espaiats
- Punt de tall del xat flotant: 768 px (fins a 768 px: Extra Large - Medium; de 767 px a 320 px: Medium - Small).
- Alçada màxima del xat flotant: 90 % de la pantalla (versió Github 10.0.0).

## Comportament i interacció
- Per consultar el comportament del contenidor de xat flotant, consulta el patró [Xat flotant](patro-xat-flotant.md) (https://sistemadedisseny.gencat.cat/38669693e/p/079d5f).
- Per consultar el comportament del contenidor de xat lateral, consulta el patró [Xat lateral](patro-xat-lateral.md) (https://sistemadedisseny.gencat.cat/38669693e/p/02ab59-xat-lateral).

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG) que cita el component:
- **1.4.1 Ús del color (A):** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a diferenciar els diferents estats s'inclouen subratllats, es juga amb la presència de farciment i el gruix de la vora. (https://www.w3.org/Translations/WCAG22-ca/#use-of-color · https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **1.4.3 Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. (https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum · https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **1.4.4 Canvia la mida del text (AA):** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. (https://www.w3.org/Translations/WCAG22-ca/#resize-text · https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **1.4.11 Contrast d'elements no textuals (AA):** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. (https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast · https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **2.1.1 Teclat (A):** tota la funcionalitat del contingut (navegar pels diferents botons) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. (https://www.w3.org/Translations/WCAG22-ca/#keyboard · https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **2.4.3 Ordre del focus (A):** la capçalera presenta un ordre lògic del focus dels elements interns per facilitar la navegació per teclat o altres dispositius d'entrada. L'ordre ha de seguir el flux de la informació o les tasques que s'estan presentant. L'ordre ha de ser el següent: (1) input: el focus es col·loca sobre l'input del xat; (2) botó per afegir elements adjunts; (3) grup de botons començant d'esquerra a dreta, l'últim serà el d'enviar; (4) botó de documents adjunts. (https://www.w3.org/Translations/WCAG22-ca/#focus-order · https://www.w3.org/WAI/WCAG22/Understanding/focus-order)
- **2.4.7 Focus visible (AA):** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. (https://www.w3.org/Translations/WCAG22-ca/#focus-visible · https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

### Navegació per teclat

| Tecla | Acció |
|---|---|
| Tabulació | Navega al següent element interactiu de la pàgina |
| Shift+Tabulació | Navega a l'element interactiu de la pàgina (la font no diu "anterior") |
| ESC | Es minimitza el xat sense pèrdua d'informació. |

## Implementació (component web)

### `<floating-chat-container-component>`
Paquet: conversational. Contenidor de xat flotant.

**Propietats**

Taula de la pàgina del lloc (amb obligatorietat):

| Propietat | Atribut HTML | Descripció | Obligatorietat | Tipus |
|---|---|---|---|---|
| `chatButtonAriaLabel` | `chat-button-aria-label` | Aria-label del botó de xat. Important per a l'accessibilitat | Obligatori | String |
| `chatButtonAriaLabelBadge` | `chat-button-aria-label-badge` | Aria-label del badge del botó de xat. Important per a l'accessibilitat | Obligatori | String |
| `chatButtonTooltipMessage` | `chat-button-tooltip-message` | Missatge del tooltip del botó de xat. Important per a l'accessibilitat | Obligatori | String |
| `chatButtonVisibilityBadge` | `chat-button-visibility-badge` | Visibilitat del badge del botó de xat | Obligatori | Boolean |
| `descriptionSubheader` | `description-subheader` | Descripció de la subcapçalera del xat | Opcional | String |
| `inputId` | `input-id` | Identificador del camp d'entrada | Obligatori | String |
| `inputPlaceholder` | `input-placeholder` | Placeholder del camp d'entrada | Obligatori | String |
| `inputShowAttachButton` | `input-show-attach-button` | Permet mostrar o ocultar el botó d'adjuntar fitxers al camp d'entrada | Opcional | Boolean |
| `inputShowMic` | `input-show-mic` | Activa el botó del micròfon per transcriure missatges | Opcional | Boolean |
| `inputValue` | `input-value` | Value del camp d'entrada | Opcional | String |
| `nameChatHeader` | `name-chat-header` | Nom del contenidor del xat flotant | Obligatori | String |
| `showSubheader` | `show-subheader` | Visibilitat de la subcapçalera del xat flotant | Opcional | Boolean |
| `titleSubheader` | `title-subheader` | Títol de la subcapçalera del xat flotant | Opcional | String |

Valors per defecte i matisos segons el PDF (v12.0.0):

| Propietat | Atribut HTML | Descripció (PDF) | Tipus | Per defecte |
|---|---|---|---|---|
| `chatButtonAriaLabel` | `chat-button-aria-label` | Etiqueta descriptiva de l'element. | string | undefined |
| `chatButtonAriaLabelBadge` | `chat-button-aria-label-badge` | Etiqueta ARIA del badge del botó de xat (accessibilitat). | string | undefined |
| `chatButtonTooltipMessage` | `chat-button-tooltip-message` | Text del tooltip associat a l'element. | string | undefined |
| `chatButtonVisibilityBadge` | `chat-button-visibility-badge` | Mostra o amaga aquest element. | boolean | undefined |
| `descriptionSubheader` | `description-subheader` | Descripció de l'element. | string | undefined |
| `inputId` | `input-id` | Identificador únic de l'element. | string | undefined |
| `inputPlaceholder` | `input-placeholder` | Text de marcador de posició del camp d'entrada. | string | undefined |
| `inputShowAttachButton` | `input-show-attach-button` | Mostra el botó d'adjuntar arxius a l'input. | `boolean \| string` | (no indicat) |
| `inputShowMic` | `input-show-mic` | Mostra el botó de gravació de veu. | boolean | false |
| `inputValue` | `input-value` | Valor actual del camp d'entrada. | string | undefined |
| `nameChatHeader` | `name-chat-header` | Nom que es mostra a la capçalera del xat. | string | undefined |
| `showSubheader` | `show-subheader` | Mostra o amaga aquest element. | boolean | true |
| `titleSubheader` | `title-subheader` | Títol del component. | string | undefined |

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre | Tipus (PDF) |
|---|---|---|---|
| `chatClosed` | Esdeveniment emès en confirmar el tancament del xat a la modal de confirmació de tancament. No s'emet si simplement obre o tanca el xat sense confirmació. (PDF: s'emet quan el component es tanca.) | Objecte: `reason: 'confirm'`, `messages: []`, `draft: { message, files }` (contingut no enviat del camp d'entrada) | `CustomEvent<FloatingChatClosedDetail>` |

Tots els esdeveniments emesos pels components següents també es poden escoltar i utilitzar: [Camp d'entrada de xat](component-camp-d-entrada-de-xat.md), [Capçalera de xat](component-capcalera-de-xat.md), [Missatge de xat](component-missatge-de-xat.md), [Botó de xat](component-boto-de-xat.md).

**Slots**

Components que es poden introduir mitjançant slot:
- **`button-component`:** s'utilitzarà per ser introduït a la capçalera del xat dins del grup de botons que inclou el botó de minimitzar i tancar xat. Atribut: `slot="group-button-chat-header"`.
- **`chat-message-component`:** s'introduirà al xat com a contingut de la conversa. Atribut: `slot="chat-floating-content-messages"`.

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<floating-chat-container-component
      name-chat-header="Pregunta'm"
      title-subheader="Especialitat del xat"
      description-subheader="Les respostes del xat són generdes per IA."
      show-subheader="true"
      input-id="chat-floating-input-1"
      input-placeholder="Escriu..."
      input-value=""
      input-show-attach-button="true"
      chat-button-tooltip-message="Missatge tooltip"
      chat-button-visibility-badge="true"
      chat-button-aria-label="Botó de xat"
      chat-button-aria-label-badge="Nou missatge"
    >
      <button-component 
        slot="group-button-chat-header"
        class-name-button="icn-btn-tertiary" 
        class-name-icon="bi-bell" 
        size-button="icn-btn-size-S"
        mode-color-button="mode-color-tertiary-dark" 
        left-icon-chevron="false" 
        right-icon-chevron="false" 
        left-icon="true"
        right-icon="false" 
        text-tooltip="Més accions" 
        custom-id="mes-accions"
        ></button-component>
      <chat-message-component 
        slot="chat-floating-content-messages" 
        message-id="msg-01" 
        message-type="systemMessage" 
        state="send"
        mode="text" 
        author-name="System" 
        time-label="10:21"
        text-error="Text d'error" 
        icon-button-error="bi-arrow-clockwise"
        text-tooltip-button-error="Recarregar" 
        avatar-settings='{"mode":"icon", "color": "purple"}'>
        <span slot="textMessage">Lorem ipsum dolor</span>
        <button-component 
          slot="groupButtonChatMessage" 
          class-name-button="icn-btn-tertiary" 
          class-name-icon="bi-hand-thumbs-up"
          size-button="icn-btn-size-S" 
          mode-color-button="mode-color-tertiary-light" 
          left-icon-chevron="false"
          right-icon-chevron="false" 
          left-icon="true" 
          right-icon="false" 
          text-tooltip="Like button"
          custom-id="like-button"
        ></button-component>
        <button-component 
          slot="groupButtonChatMessage" 
          class-name-button="icn-btn-tertiary"
          class-name-icon="bi-hand-thumbs-down" 
          size-button="icn-btn-size-S" 
          mode-color-button="mode-color-tertiary-light"
          left-icon-chevron="false" 
          right-icon-chevron="false" 
          left-icon="true" 
          right-icon="false" 
          text-tooltip="Dislike button"
          custom-id="no-like-button"
        ></button-component>
        <dropdown-button-component 
          slot="groupButtonChatMessage" 
          class-name-icon="bi-three-dots" 
          class-name-button="icn-btn-tertiary"
          size-button="icn-btn-size-S" 
          mode-color-button="mode-color-tertiary-light" 
          right-icon="true"
          text-tooltip="Dropdown" 
          custom-id="dropdown1" 
          options='[
              { "label": "Opción 1", "id": "1", "icon": "bi-copy" },
              { "label": "Opción 2", "id": "2", "icon": "bi-copy" },
              { "label": "Opción 3", "id": "3", "icon": "bi-copy" }
            ]'
        ></dropdown-button-component>
      </chat-message-component>
</floating-chat-container-component>
```

**Exemple d'instància (PDF)**

```html
<floating-chat-container-component
chat-button-aria-label="texto-ejemplo"
chat-button-aria-label-badge="texto-ejemplo"
chat-button-tooltip-message="texto-ejemplo"
chat-button-visibility-badge=false
description-subheader="texto-ejemplo"
input-id="texto-ejemplo"
input-placeholder="texto-ejemplo"
input-show-attach-button=true
input-show-mic=false
input-value="texto-ejemplo"
name-chat-header="texto-ejemplo"
show-subheader=true
title-subheader="texto-ejemplo"
></floating-chat-container-component>
```

**Recomanacions d'ús**
- **Gestió de missatges mitjançant codi:** tots els missatges que apareixen al `floating-chat-container-component` s'han de crear i afegir dinàmicament mitjançant JavaScript. No es recomana declarar missatges a l'HTML estàtic, excepte per mostrar missatges inicials de benvinguda. Els components chat-message introduïts per slot hauran de ser inclosos al contenidor amb la classe `slot-chat-floating-messages` perquè apareguin dins de la conversa del xat.
- **Enviament de missatges des de l'input:** quan l'usuari prem el botó d'enviar, el component emet l'esdeveniment `sendRequest`. Cal escoltar aquest esdeveniment per inserir el nou `chat-message-component` al contenidor. [discrepància: el lloc diu `sendRequest`; el PDF del Camp d'entrada de xat anomena l'esdeveniment `sendRequested`]
- **Missatges amb text i fitxers adjunts:** si l'usuari envia alhora text i un o diversos fitxers, es recomana crear un `chat-message-component` independent per a cada element: un per al text (amb `mode="text"`) i un per cada fitxer (amb `mode="file"` o `mode="image"` si és una imatge).

**Depèn de**
- Paquet conversational (lloc): `chat-header-component`, `chat-subheader-component`, `back-to-bottom-component` (lloc; el PDF diu `back-to-bottom-button-component`), `chat-input-component`, `chat-button-component`.
- Paquet core (lloc): `button-component`.
- PDF: `chat-header-component`, `modal-component`, `button-component`, `chat-subheader-component`, `back-to-bottom-button-component`, `chat-input-component`, `chat-button-component`.

Enllaços: [Capçalera de xat](component-capcalera-de-xat.md), [Capçalera secundària de xat](component-capcalera-secundaria-de-xat.md), [Botó tornar a baix](component-boto-tornar-a-baix.md), [Camp d'entrada de xat](component-camp-d-entrada-de-xat.md), [Botó de xat](component-boto-de-xat.md), [Botons](component-botons.md), [Modals](component-modals.md).

### `<side-panel-chat-component>`
Paquet: conversational. Contenidor de xat lateral.

**Propietats**

Taula de la pàgina del lloc (amb obligatorietat):

| Propietat | Atribut HTML | Descripció | Obligatorietat | Tipus |
|---|---|---|---|---|
| `chatTitle` | `chat-title` | Nom del contenidor del xat flotant | Obligatori | String |
| `descriptionSubheader` | `description-subheader` | Descripció de la subcapçalera del xat | Opcional | String |
| `inputId` | `input-id` | Identificador del camp d'entrada | Obligatori | String |
| `inputPlaceholder` | `input-placeholder` | Placeholder del camp d'entrada | Obligatori | String |
| `inputShowAttachButton` | `input-show-attach-button` | Permet mostrar o ocultar el botó d'adjuntar fitxers al camp d'entrada | Opcional | Boolean |
| `inputShowMic` | `input-show-mic` | Activa el botó del micròfon per transcriure missatges | Opcional | Boolean |
| `inputValue` | `input-value` | Value del camp d'entrada | Opcional | String |
| `showSubheader` | `show-subheader` | Visibilitat de la subcapçalera del xat flotant | Opcional | Boolean |
| `sideChatButtonAriaLabel` | `side-chat-button-aria-label` | Aria-label del botó de xat. Important per a l'accessibilitat | Obligatori | String |
| `sideChatButtonId` | `side-chat-button-id` | Identificador del botó de xat lateral | Obligatori | String |
| `sideChatButtonStickyReferenceSelector` | `side-chat-button-sticky-reference-selector` | Selector al qual es quedarà fix el panell lateral en estat sticky. Exemple: header-public-component, secondary-header-component | Opcional | String |
| `sideChatButtonTooltipMessage` | `side-chat-button-tooltip-message` | Missatge del tooltip del botó de xat. Important per a l'accessibilitat | Obligatori | String |
| `titleSubheader` | `title-subheader` | Títol de la subcapçalera del xat flotant | Opcional | String |

Valors per defecte i matisos segons el PDF (v12.0.0):

| Propietat | Atribut HTML | Descripció (PDF) | Tipus | Per defecte |
|---|---|---|---|---|
| `chatTitle` | `chat-title` | Títol del component. | string | `Pregunta'm` |
| `descriptionSubheader` | `description-subheader` | Descripció de l'element. | string | undefined |
| `inputId` | `input-id` | Identificador únic de l'element. | string | `side-panel-chat-input` |
| `inputPlaceholder` | `input-placeholder` | Text de marcador de posició del camp d'entrada. | string | `Escriu.//` |
| `inputShowAttachButton` | `input-show-attach-button` | Mostra el botó d'adjuntar arxius. | boolean | true |
| `inputShowMic` | `input-show-mic` | Mostra el botó de gravació de veu. | boolean | false |
| `inputValue` | `input-value` | Valor actual del camp d'entrada. | string | `` (cadena buida) |
| `showSubheader` | `show-subheader` | Mostra o amaga aquest element. | boolean | true |
| `sideChatButtonAriaLabel` | `side-chat-button-aria-label` | Etiqueta descriptiva de l'element. | string | undefined |
| `sideChatButtonId` | `side-chat-button-id` | Identificador únic de l'element. | string | undefined |
| `sideChatButtonStickyReferenceSelector` | `side-chat-button-sticky-reference-selector` | Selector CSS de l'element de referència per al posicionament. | string | undefined |
| `sideChatButtonTooltipMessage` | `side-chat-button-tooltip-message` | Text del tooltip associat a l'element. | string | undefined |
| `titleSubheader` | `title-subheader` | Títol del component. | string | undefined |

**Esdeveniments:** el PDF no declara esdeveniments propis. El lloc indica que tots els esdeveniments emesos pels components següents també es poden escoltar i utilitzar: Camp d'entrada, Capçalera de xat, Missatge de xat, Botó de xat.

**Slots**
- **`chat-message-component`:** s'introduirà al xat com a contingut de la conversa. Atribut: `slot="chat-lateral-content-messages"`.

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<side-panel-chat-component 
      chat-title="Pregunta'm" 
      input-id="side-panel-chat-input" 
      input-placeholder="Escriu..."
      input-value="" 
      input-show-attach-button="true" 
      show-subheader="true"
      title-subheader="Especialitat del xat"
      description-subheader="Les responses del xat són generdes per IA."
      side-chat-button-sticky-reference-selector="header-public-component, secondary-header-component"
      side-chat-button-id="side-chat-button-01"
      side-chat-button-tooltip-message="Obrir xat lateral"
      side-chat-button-aria-label="Obrir xat lateral">
        <chat-message-component slot="chat-lateral-content-messages" message-id="msg-001" message-type="systemMessage" state="send"
          author-name="System" time-label="10:30" avatar-settings='{"mode":"icon","avatarColor":"black"}'>
          <span slot="textMessage">Hola! En què et puc ajudar?</span>
      
          <button-component slot="groupButtonChatMessage" class-name-button="icn-btn-tertiary"
            class-name-icon="bi-hand-thumbs-up" size-button="icn-btn-size-S" mode-color-button="mode-color-tertiary-light"
            left-icon="true" right-icon="false" left-icon-chevron="false" right-icon-chevron="false" text-tooltip="Like"
            custom-id="msg-001-like"></button-component>
      
          <button-component slot="groupButtonChatMessage" class-name-button="icn-btn-tertiary"
            class-name-icon="bi-hand-thumbs-down" size-button="icn-btn-size-S" mode-color-button="mode-color-tertiary-light"
            left-icon="true" right-icon="false" left-icon-chevron="false" right-icon-chevron="false" text-tooltip="Dislike"
            custom-id="msg-001-dislike"></button-component>
        </chat-message-component>
    </side-panel-chat-component>
```

**Exemple d'instància (PDF)**

```html
<side-panel-chat-component
chat-title="Pregunta'm"
description-subheader="texto-ejemplo"
input-id='side-panel-chat-input'
input-placeholder='Escriu.//'
input-show-attach-button=true
input-show-mic=false
input-value=''
show-subheader=true
side-chat-button-aria-label="texto-ejemplo"
side-chat-button-id="texto-ejemplo"
side-chat-button-sticky-reference-selector="texto-ejemplo"
side-chat-button-tooltip-message="texto-ejemplo"
title-subheader="texto-ejemplo"
></side-panel-chat-component>
```

**Recomanacions d'ús**
- **Gestió de missatges mitjançant codi:** tots els missatges que apareixen al contenidor (la font diu `floating-chat-container-component`, copiat de l'apartat flotant) s'han de crear i afegir dinàmicament mitjançant JavaScript. No es recomana declarar missatges a l'HTML estàtic, excepte per mostrar missatges inicials de benvinguda. Els components chat-message introduïts per slot hauran de ser inclosos al contenidor amb la classe `messages-slot` perquè apareguin dins de la conversa del xat.
- **Enviament de missatges des de l'input:** quan l'usuari prem el botó d'enviar, el component emet l'esdeveniment `sendRequest`. Cal escoltar aquest esdeveniment per inserir el nou `chat-message-component` al contenidor.
- **Missatges amb text i fitxers adjunts:** si l'usuari envia alhora text i un o diversos fitxers, es recomana crear un `chat-message-component` independent per a cada element: un per al text (amb `mode="text"`) i un per cada fitxer (amb `mode="file"` o `mode="image"` si és una imatge).

**Depèn de**
- Paquet conversational (lloc): `chat-header-component`, `chat-subheader-component`, `back-to-bottom-component` (lloc; el PDF diu `back-to-bottom-button-component`), `chat-input-component`, `side-chat-button-component`.
- Paquet core (lloc): `button-component`.
- PDF: `side-chat-button-component`, `chat-header-component`, `chat-subheader-component`, `back-to-bottom-button-component`, `chat-input-component`.

Enllaços: [Botó de xat](component-boto-de-xat.md), [Capçalera de xat](component-capcalera-de-xat.md), [Capçalera secundària de xat](component-capcalera-secundaria-de-xat.md), [Botó tornar a baix](component-boto-tornar-a-baix.md), [Camp d'entrada de xat](component-camp-d-entrada-de-xat.md), [Botons](component-botons.md).

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 2.1.0 | 12.0.0 | 10 juliol, 2026 | Desenvolupament: (1) contenidor de xat flotant: s'afegeix la property `inputShowMic` per habilitar el botó de micròfon; (2) contenidor de xat lateral: s'afegeix la property `inputShowMic` per habilitar el botó de micròfon |
| 2.1.0 | 11.0.0 | 19 juny, 2026 | Desenvolupament: (contenidor de xat flotant) s'altera l'ordre dels botons en la modal de tancar xat perquè el focus es mogui primer al botó primari |
| 2.1.0 | 10.1.0 | 29 maig, 2026 | Desenvolupament: s'fan ajustos d'accessibilitat i comportament del focus del contenidor de xat flotant. Botó de xat lateral: s'elimina l'ombra del botó per a breakpoints inferiors a 768px; s'fan ajustos quant a la posició sticky |
| 2.1.0 | 10.0.0 | 8 maig, 2026 | Desenvolupament: s'ajusta l'alçada màxima del xat al 90% de la pantalla al contenidor de xat flotant; es desenvolupa el component de xat lateral |
| 2.1.0 | 9.4.0 | 17 abril, 2026 | Desenvolupament del component |
| 2.1.0 | - | 20 març, 2026 | Disseny del component |

## Vegeu també
- [Xat flotant](patro-xat-flotant.md), [Xat lateral](patro-xat-lateral.md), [Xat a pantalla completa](patro-xat-a-pantalla-completa.md)
- [Capçalera de xat](component-capcalera-de-xat.md), [Capçalera secundària de xat](component-capcalera-secundaria-de-xat.md), [Missatge de xat](component-missatge-de-xat.md), [Camp d'entrada de xat](component-camp-d-entrada-de-xat.md), [Botó de xat](component-boto-de-xat.md), [Botó tornar a baix](component-boto-tornar-a-baix.md)
