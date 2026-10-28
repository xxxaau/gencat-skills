# Missatge de xat (Chat message)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/9091df · Web component: `<chat-message-component>` (paquet conversational) · Font actualitzada el 2026-06-09 · Extret el 2026-10-28

## Què és i quan usar-lo
És l'element bàsic de comunicació dins d'una conversa i representa cada intervenció d'un participant. Inclou el contingut del missatge (text, icones o multimèdia), l'origen (usuari, sistema o agent), i metadades contextuals com l'hora o l'estat d'enviament/lectura.

[a verificar: la secció "Descripció i ús" de la pàgina del lloc reprodueix literalment la descripció del Botó de xat ("El Botó de Xat és un element persistent de la interfície d'usuari (UI) que serveix com a porta d'accés ràpid al diàleg de xat. La funció principal és assegurar que l'usuari pugui iniciar una conversa d'assistència des de qualsevol punt de l'aplicació o web, sense necessitat de navegar a una pàgina específica."), probablement per error de documentació.]

Quan s'utilitza:
- **Fluxos conversacionals:** sempre que hi hagi un intercanvi de missatges entre dues o més entitats (usuari-IA, usuari-agent).

## Quan NO usar-lo / alternatives
- **Input de text:** no s'ha de confondre amb el camp on l'usuari escriu (ChatInput). Vegeu [Camp d'entrada de xat](component-camp-d-entrada-de-xat.md).
- **Bàners informatius:** per a avisos que no formen part de la seqüència temporal de la conversa, cal fer servir components de Notification o Alert (vegeu [Avisos](component-avisos.md) i [Notificació emergent](component-notificacio-emergent.md)).
- **Comentaris:** per a fils de comentaris en blogs o documents, on la jerarquia i l'estètica solen ser diferents del xat en temps real.

## Anatomia
Figma: Chat message [Type = System]. El missatge de xat està format per instàncies de dos components: missatge del sistema i missatge de l'usuari.

## Variants, tipus i estats

### Missatge de xat

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Type | System / User (la font escriu "Sytem") | System |

### Missatge del sistema
És aquell missatge enviat per un agent conversacional o un treballador.

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Default / Thinking / Error | Default |
| Show Name | True / False | False |

Variant Figma: `_System message` [Show Name = False, State = Default]. L'estat Error està pensat per a errors del sistema o de connexió que provoquin que no es pugui enviar el missatge.

**Mostra nom:** la propietat per mostrar nom s'utilitzarà únicament en aquells xats que tinguin nom específic o s'interactuï amb un treballador. En el cas del xat de gencat.cat no s'utilitzarà. No obstant, sempre cal tenir un nom com a heading per al lector de pantalla. (Figma: Mostra nom, Missatge de xat / Components / Botó de xat / DOC_Missatge de xat / Disseny / Propietats / Mostra nom.)

### Missatge de l'usuari
És aquell missatge enviat per un usuari.

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Default / Error | Default |
| Show Header | True / False | True |
| Show attached files | True / False | False |

Variant Figma: `_User message` [Show Header = True, Show Attached files = False, State = Default].

### Fitxer adjunt (anatomia)
Figma: Attached file [File name = Nom.format, File weight = Pes.format, State = Default]; Attached image [Change Icon = image, File name = Nom.format, File weight = Pes.format, State = Default].

## Comportament i interacció

### Funció d'enraonament de l'agent
La funció d'enraonament indica que el sistema està processant la consulta de l'usuari abans de generar una resposta. Aquest estat permet comunicar que el sistema està analitzant la informació o realitzant diferents accions internes per elaborar la resposta. Aquesta indicació ajuda a gestionar les expectatives de l'usuari i a fer visible que el sistema continua treballant. (Figma: Enraonament, Missatge de xat / Components / Botó de xat / DOC_Missatge de xat / Disseny / Comportament / Enraonament.)

#### Temps d'aparició i durada dels estats
Per evitar mostrar indicadors d'activitat innecessaris o canvis massa ràpids a la interfície, els estats de processament s'han de mostrar només quan el temps de resposta del sistema ho requereix. Com a criteri general:
- Si la resposta es genera en menys d'1 segon, no cal mostrar cap estat intermedi.
- Si la resposta supera aproximadament 1 segon, es recomana mostrar l'estat de processament.

Un cop mostrat l'estat, aquest ha de mantenir-se visible com a mínim durant 1 segon abans de mostrar la resposta final, per evitar canvis massa ràpids que puguin resultar confusos per a l'usuari.

#### Estats del sistema
Els missatges d'estat indiquen l'activitat actual del sistema mentre prepara la resposta.

| Estat | Etiqueta |
|---|---|
| Pensant | Pensant… |
| Cercant informació | Cercant informació… |
| Analitzant | Analitzant imatge/fitxer… |
| Generant resposta | Generant resposta… |
| Humà escrivint | Escrivint... |
| Processant consulta (xatbot no generatiu) | Processant consulta… |

Quan el sistema no és generatiu (per exemple, un xatbot basat en regles o en recuperació d'informació), és preferible evitar missatges com "Pensant…", ja que poden suggerir un comportament cognitiu que no correspon al funcionament real del sistema.

### Alineacions de bombolla i text
**Missatge del sistema**
- La bombolla del missatge s'alinea sempre a l'esquerra.
- L'alineació del text i altres components dins la bombolla serà a l'esquerra.

(Figma: Alineacions_sistema.)

**Missatge de l'usuari**
- La bombolla del missatge s'alinea sempre a la dreta.
- L'alineació del text dins la bombolla serà a l'esquerra.

(Figma: Alineacions_susuari.)

### Botons d'acció
El missatge del sistema utilitza el component [Grup de botons](component-grup-de-botons.md) (https://sistemadedisseny.gencat.cat/38669693e/p/66a89d) per a les accions. Aquest permet fins a 6 botons a primer nivell. Els botons que s'utilitzin hauran de ser sempre en format **icona** i de mida ***small (petita)***. (Figma: Botons acció.) Es pot utilitzar el botó desplegable en format icona per agrupar diverses accions. (Figma: Desplegable.) Vegeu [Botons](component-botons.md).

### Missatges seguits
Si **l'usuari** envia diversos missatges seguits, aquests apareixen en **bombolles separades**, una sota l'altra. La icona i l'hora només es mostren en la primera bombolla del grup. Si és el **sistema** (un treballador, per exemple) el que envia els missatges seguits, apareixeran amb un salt de línia. (Figma: Missatges seguit_usuari; Missatges seguit_sistema.)

Nota de la font: les seccions que segueixen (missatge amb fitxer adjunt) estan en procés de treball.

### Missatge amb fitxer adjunt
Permet mostrar un fitxer que l'usuari ha adjuntat a la conversa un cop ha enviat el missatge. Es presenta mitjançant un element de previsualització que permet identificar ràpidament el contingut enviat. Aquesta visualització inclou la informació bàsica del fitxer perquè l'usuari pugui reconèixer-lo fàcilment dins la conversa. Per entendre el flux anterior a l'adjunció d'un fitxer, consulta l'apartat "Comportament" del component [Camp d'entrada de xat](component-camp-d-entrada-de-xat.md) (https://sistemadedisseny.gencat.cat/38669693e/p/5513cb), on s'explica el procés complet d'adjuntar i gestionar fitxers abans de l'enviament del missatge.

**Previsualització de fitxers:** en clicar sobre el component d'un fitxer adjunt (imatge o document), s'obre una previsualització en format modal que permet consultar el contingut sense sortir de la conversa. Aquest comportament és el mateix en tots els punts de tall, on la previsualització també es mostra en modal ocupant el focus de la pantalla. (Figma: Previsualització01; Previsualització02.)

## Contingut i microcopy
Etiquetes d'estat del sistema: vegeu la taula d'Estats del sistema. Textos d'exemple del codi: autor "System" / "Jo"; hora "10:21" / "10:23"; text d'error "Text d'error"; tooltip del botó d'error "Recarregar"; text "Lorem ipsum dolor"; fitxer "Nom.format" / "Pes.format". Encapçalaments per a lectors de pantalla: "has dit" / "l'agent ha dit" (vegeu Accessibilitat).

## Bones pràctiques

### Rols
- **FER:** Utilitza l'alineació i el color per indicar l'origen. L'usuari sol anar a la dreta (color de marca) i l'assistent a l'esquerra (color neutre).

### Agrupació de missatges
- **FER:** Si un mateix autor envia diversos missatges seguits, es recomana amagar l'avatar i el nom en els missatges consecutius per reduir el soroll visual.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG) que cita el component:
- **1.4.1 Ús del color (A):** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a diferenciar els diferents estats s'inclouen subratllats, es juga amb la presència de farciment i el gruix de la vora. (https://www.w3.org/Translations/WCAG22-ca/#use-of-color · https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **1.4.3 Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. (https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum · https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **1.4.4 Canvia la mida del text (AA):** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. (https://www.w3.org/Translations/WCAG22-ca/#resize-text · https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **1.4.11 Contrast d'elements no textuals (AA):** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. (https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast · https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **2.1.1 Teclat (A):** tota la funcionalitat del contingut (navegar pels diferents botons) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. (https://www.w3.org/Translations/WCAG22-ca/#keyboard · https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **2.4.7 Focus visible (AA):** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. (https://www.w3.org/Translations/WCAG22-ca/#focus-visible · https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- **2.4.10 Encapçalaments de secció (AAA):** si el lector de pantalla està activat, un cop l'usuari surti del camp d'entrada (si utilitza les tecles alfabètiques mentre és a l'input, escriuria), pot utilitzar la tecla H per navegar entre els headings dels missatges. Per aquest motiu cada missatge ha de tenir un H4, H5, etc. en funció de l'estructura de la pàgina, que indicarà: missatge de l'usuari: "has dit"; missatge del xatbot: "l'agent ha dit". Si dins del missatge del xatbot hi ha seccions, aquestes tindran un H inferior al del missatge (H6, per exemple). (https://www.w3.org/Translations/WCAG22-ca/#section-headings · https://www.w3.org/WAI/WCAG22/Understanding/section-headings)

## Implementació (component web)

### `<chat-message-component>`
Paquet: conversational.

**Propietats**

Taula de la pàgina del lloc (amb obligatorietat):

| Propietat | Atribut HTML | Descripció | Obligatorietat | Tipus |
|---|---|---|---|---|
| `attachedFiles` | `attached-files` | Dades del fitxer adjunt | Opcional | String \| Array |
| `authorName` | `author-name` | Nom de l'usuari o sistema que envia el missatge | Opcional | String |
| `avatarSettings` | `avatar-settings` | Permet configurar el tipus d'avatar. Només està habilitat per als missatges del sistema. Les propietats són les mateixes que les del component [Avatar](component-avatar.md) (https://sistemadedisseny.gencat.cat/38669693e/p/0971aa). | Obligatori | String \| Object |
| `dateTime` | `date-time` | Data en format ISO per facilitar la comunicació amb el navegador | Obligatori | String |
| `iconButtonError` | `icon-button-error` | Icona del botó que acompanya el text d'error | Obligatori | String |
| `messageHeadingLevel` | `message-heading-level` | Permet indicar el grau de l'etiqueta H del missatge. Aquesta propietat és important per a l'accessibilitat | Obligatori | String |
| `messageId` | `message-id` | Identificador del missatge | Obligatori | String |
| `messageType` | `message-type` | Tipus de missatge | Obligatori | String |
| `mode` | `mode` | Permetre triar entre missatge de text, fitxer o imatge. Cadascun tindrà una vista diferent. | Obligatori | String |
| `nameFile` | `name-file` | Nom del fitxer, en el cas que hagi estat adjuntat | Opcional | String |
| `showHeader` | `show-header` | Amagar i mostrar capçalera del missatge que conté l'authorName i l'hora d'enviament del missatge. Quan l'usuari enviï dos o més missatges seguits, a partir del segon missatge s'haurà d'ocultar la capçalera introduint showHeader com a false. Tot i això, en el cas del sistema, cada missatge haurà de tenir la seva pròpia capçalera. | Opcional | Boolean |
| `sizeFile` | `size-file` | Grandària del fitxer, en el cas que hagi estat adjuntat | Opcional | String |
| `state` | `state` | Estat del missatge. Veure a la taula "Variants" les possibles opcions | Obligatori | String |
| `textError` | `text-error` | Text d'error a mostrar quan el missatge no s'ha pogut enviar o rebre | Obligatori | String |
| `textTooltipButtonError` | `text-tooltip-button-error` | Text ubicat a l'interior del tooltip del botó que acompanya el text d'error | Opcional | String |
| `timeLabel` | `time-label` | Hora en què va ser enviat o rebut el missatge en format hh:mm. La seva finalitat només és la de ser mostrat a l'etiqueta | Obligatori | String |

Valors per defecte i matisos segons el PDF (v12.0.0):

| Propietat | Atribut HTML | Descripció (PDF) | Tipus | Per defecte |
|---|---|---|---|---|
| `attachedFiles` | `attached-files` | Fitxers adjunts. Accepta array d'objectes o string JSON. | `ChatMessageFileDetail[] \| string` | (no indicat) |
| `authorName` | `author-name` | Nom de l'autor del missatge. | string | undefined |
| `avatarSettings` | `avatar-settings` | Configuració de l'avatar. Accepta objecte o string JSON amb la interfície AvatarSettings. | `AvatarSettings \| string` | (no indicat) |
| `dateTime` | `date-time` | Data en format ISO 8601. | string | undefined |
| `iconButtonError` | `icon-button-error` | Classe Bootstrap Icons del botó d'acció en estat d'error. | string | undefined |
| `messageHeadingLevel` | `message-heading-level` | Nivell de l'encapçalament semàntic (h2–h6). Opcions: `h2`, `h3`, `h4`, `h5`, `h6`. | string | `h4` |
| `messageId` | `message-id` | Identificador únic de l'element. | string | undefined |
| `messageType` | `message-type` | Tipus d'element. Opcions: `systemMessage`, `userMessage`. | string | `systemMessage` |
| `mode` | `mode` | Variant visual del component. Opcions: `file`, `image`, `text`. | string | `text` |
| `nameFile` | `name-file` | Nom del fitxer adjunt. | string | undefined |
| `showErrorTextButton` | `show-error-text-button` | Mostra o amaga aquest element. | boolean | true |
| `showHeader` | `show-header` | Mostra o amaga aquest element. | boolean | true |
| `sizeFile` | `size-file` | Mida del component. | string | undefined |
| `state` | `state` | Estat actual del component. Opcions: `error`, `send`, `thinking`. | string | `send` |
| `textError` | `text-error` | Text del missatge d'error que es mostra a l'usuari. | string | undefined |
| `textTooltipButtonError` | `text-tooltip-button-error` | Text que es mostra al tooltip associat. | string | undefined |
| `timeLabel` | `time-label` | Etiqueta llegible de l'hora per mostrar a l'usuari. | string | undefined |

[discrepància: el PDF documenta la propietat `showErrorTextButton` (`show-error-text-button`), que no apareix a la taula del lloc]
[discrepància: la taula de variants del lloc escriu `systemaMessage` com a opció de `messageType` i `systemMessage` com a valor per defecte; el PDF diu `systemMessage` / `userMessage` (`systemMessage` per defecte)]

**Variants (lloc)**

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `messageHeadingLevel` | `h2` `h3` `h4` `h5` `h6` | `h4` |
| `messageType` | `systemaMessage` `userMessage` | `systemMessage` |
| `mode` | `text` `file` `image` | `text` |
| `state` | `send` `thinking` `error` | `send` |

**Props que accepten JSON**

`avatarSettings` — string JSON (objecte) amb l'estructura `AvatarSettings` (PDF; les unions de tipus apareixen truncades a la font):

| Clau | Tipus | Requerida |
|---|---|---|
| `avatarColor` | `'white'` \| `'black'` … (truncat a la font) | (truncat a la font) |
| `mode` | `'bubble'` \| `'icon'` … (truncat a la font) | (truncat a la font) |
| `src` | string | No |
| `initials` | string | No |
| `color` | `'blue'` \| `'green'` … (truncat a la font) | (truncat a la font) |

Les opcions completes de cada clau són les de l'[Avatar](component-avatar.md) (`avatarColor`: black, color, white; `mode`: bubble, icon, initials, image, loading; `color`: blue, green, yellow, red, purple, dark, white).

```json
{
"avatarColor": "white",
"mode": "bubble",
"src": "texto-ejemplo",
"initials": "texto-ejemplo",
"color": "blue"
}
```

`attachedFiles` — string JSON (array d'objectes) amb l'estructura `ChatMessageFileDetail`:

| Clau | Tipus | Requerida |
|---|---|---|
| `file` | File | Sí |
| `clientMessageId` | string | Sí |

```json
[
{
"file": "value",
"clientMessageId": "texto-ejemplo"
}
]
```

**Slots**

Components que es poden introduir mitjançant slot:
- **`button-component`:** seran els botons d'acció que s'introduiran sota el missatge enviat pel sistema. Cal portar l'atribut `slot="groupButtonChatMessage"`.
- **`dropdown-button-component`:** formarà part dels botons d'acció que s'introduiran sota el missatge enviat pel sistema. Cal portar l'atribut `slot="groupButtonChatMessage"`.
- **`suggestions-component`:** suggeriments de resposta al missatge enviat pel sistema. Cal portar l'atribut `slot="suggestions-slot"`. Utilitzar només per a `messageType = systemMessage`.
- **Qualsevol HTML:** utilitza l'atribut `slot="textMessage"` a l'etiqueta de l'HTML contenidora del text del missatge.

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre | Tipus (PDF) |
|---|---|---|---|
| `fileRequested` | Esdeveniment llançat en fer clic sobre un missatge en mode file. L'obertura del fitxer no està gestionada pel component. (PDF: s'emet quan l'usuari sol·licita obrir un fitxer adjunt) | Objecte: `messageId` `files: ChatMessageFileDetail[]` `message` | `CustomEvent<ChatMessageRetryRequestedDetail>` |
| `retryRequested` | Esdeveniment llançat en fer clic sobre el botó contigu al text d'error del missatge. (PDF: s'emet quan l'usuari sol·licita reintentar l'acció) | Objecte: `messageId` `files: ChatMessageFileDetail[]` `message` | `CustomEvent<ChatMessageRetryRequestedDetail>` |

**Exemple d'ús (lloc): SystemMessage**

```html
<!-- /index.html -->
<chat-message-component 
      message-id="msg-01" 
      message-type="systemMessage" 
      state="send"
      message-heading-level="h5"
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
        <suggestions-component 
          slot="suggestions-slot"
          suggestions='["Suggestion 1","Suggestion 2","Suggestion 3"]'
        ></suggestions-component>
  </chat-message-component>
```

**Exemple d'ús (lloc): UserMessage**

```html
<!-- /index.html -->
<chat-message-component 
      slot="chat-floating-content-messages" 
      message-id="msg-02"
      message-type="userMessage" 
      state="send" 
      mode="file" 
      name-file="Nom.format" 
      size-file="Pes.format"
      author-name="Jo" 
      time-label="10:23" 
      text-error="Text d'error" 
      icon-button-error="bi-arrow-clockwise"
      text-tooltip-button-error="Recarregar"
  >
        <span slot="textMessage">Lorem ipsum dolor</span>
</chat-message-component>
```

**Exemple d'instància (PDF)**

```html
<chat-message-component
attached-files=[]
author-name="texto-ejemplo"
avatar-settings="texto-ejemplo"
date-time="texto-ejemplo"
icon-button-error="texto-ejemplo"
message-heading-level='h4'
message-id="texto-ejemplo"
message-type='systemMessage'
mode='text'
name-file="texto-ejemplo"
show-error-text-button=true
show-header=true
size-file="texto-ejemplo"
state='send'
text-error="texto-ejemplo"
text-tooltip-button-error="texto-ejemplo"
time-label="texto-ejemplo"
></chat-message-component>
```

Exemple amb props JSON (PDF):

```html
<chat-message-component
avatar-settings='{"avatarColor":"white","mode":"bubble","src":"texto-ejemplo","initials":"texto-ejemplo","color":"blue"}'
></chat-message-component>
<chat-message-component
attached-files='[{"file":"value","clientMessageId":"texto-ejemplo"}]'
></chat-message-component>
```

**Depèn de:** `avatar-component` ([Avatar](component-avatar.md)), `button-component` ([Botons](component-botons.md)), `dropdown-button-component` ([Botons](component-botons.md)), `group-button-component` ([Grup de botons](component-grup-de-botons.md)), `advanced-image-component` ([Imatge avançada](component-imatge-avancada.md)). Slot opcional: `suggestions-component` ([Suggeriments](component-suggeriments.md)).

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 2.1.0 | 10.0.0 | 8 maig, 2026 | Desenvolupament: s'afegeix estat d'error per als fitxers i les imatges |
| 2.1.0 | 9.4.0 | 17 abril, 2026 | Desenvolupament: s'han creat les vistes de file i image utilitzades en la nova propietat `mode`, el contingut del missatge ara s'estableix mitjançant la propietat `textMessage` en lloc d'un slot; s'ha permès mostrar o ocultar el header del component, s'ha creat l'event `retryRequested` que es dispara en reintentar l'enviament d'un missatge; s'ha creat l'event `fileRequested` que es dispara en fer clic en un missatge de tipus file. |
| 2.1.0 | 9.3.0 | 20 març, 2026 | Disseny: s'eliminen bombolles extres del missatge de l'usuari; s'afegeix text enviat per l'usuari en l'estat d'error; s'afegeix booleana de fitxers adjunts al missatge de l'usuari; es creen els components de missa… (la font talla el text). Desenvolupament: s'hi afegeixen les noves propietats de l'avatar per poder utilitzar el mode icon, bubble, loading o initials; s'arregla l'amplada del text bombolla en mode userMessage |
| 1.1.0 | 9.2.0 | 27 febrer, 2026 | Desenvolupament del component |
| 1.1.0 | - | 09 febrer, 2026 | Disseny del component |

## Vegeu també
- [Avatar](component-avatar.md), [Suggeriments](component-suggeriments.md), [Grup de botons](component-grup-de-botons.md), [Botons](component-botons.md), [Camp d'entrada de xat](component-camp-d-entrada-de-xat.md), [Imatge avançada](component-imatge-avancada.md), [Contenidor de xat](component-contenidor-de-xat.md)
