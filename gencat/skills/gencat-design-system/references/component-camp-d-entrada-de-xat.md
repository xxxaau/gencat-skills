# Camp d'entrada de xat (Chat input)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/5513cb · Web component: `<chat-input-component>` (paquet conversational) · Font actualitzada el 2026-07-10 · Extret el 2026-10-28

## Què és i quan usar-lo
El camp d'entrada ofereix als usuaris l'opció d'enviar missatges, adjuntar arxius, etc. en diferents tipologies de xat.

[a verificar: la secció "Descripció i ús" de la pàgina del lloc reprodueix literalment la descripció del Botó de xat ("El Botó de Xat és un element persistent de la interfície d'usuari (UI) que serveix com a porta d'accés ràpid al diàleg de xat. La funció principal és assegurar que l'usuari pugui iniciar una conversa d'assistència des de qualsevol punt de l'aplicació o web, sense necessitat de navegar a una pàgina específica."), probablement per error de documentació.]

Quan s'utilitza:
- **Fluxos conversacionals:** sempre que hi hagi un intercanvi de missatges entre dues o més entitats (usuari-IA, usuari-agent).

## Quan NO usar-lo / alternatives
- **Input de text:** no s'ha de confondre amb el camp on l'usuari escriu (ChatInput) [text tal com surt a la font].

## Anatomia
Figma: Anatomia, Anatomia 02 i Anatomia 3 (Camp d'entrada / Components / Botó de xat / DOC_Camp d'entrada de xat / Anatomia).

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Default / Hover / Focus / Audio / Listening / Transcribing | Default |
| Chat type | Full width / Floating | Full width |
| Show Left Icon | True / False | False |
| Show attached files button | True / False | False |

Variant Figma base: Botó de xat [Input text = Text, Show Left Icon = False, Show Scroll = False, Show attached files button = True, Show Silence Callout = False, State = Default, Chat Type = Full width].

### Estats
[a verificar: la font mostra quatre instàncies Figma idèntiques, tres amb descripció i sense el nom de l'estat; l'assignació dels textos als estats Default / Listening / Transcribing és una interpretació, i els estats Hover, Focus i Audio no tenen descripció a la font.]
- Default: disposa del botó de micròfon per defecte.
- Listening: per quan s'ha activat el botó de micròfon i el xat escolta.
- Transcribing: estat mentre el xat està recollint la veu de l'usuari en format text.

### Tipus de xat
- Full width: s'utilitza en xats a pantalla completa.
- Floating: s'utilitza en xats flotants.

## Mides i espaiats
- Alçada màxima del camp: 160 px (equival a unes 6 línies de text a 16 pts).
- Amb zoom del 400 %: alçada màxima de 84 px, i de 60 px si també hi ha visible el botó de fitxers adjunts.

## Comportament i interacció

### Ubicació
**Pantalla completa:** el camp d'entrada de xat apareix a la part inferior de la pantalla i ocupa les columnes centrals de la pàgina. Per veure en més detall el layout a pantalla completa consulta el patró [Xat a pantalla completa](patro-xat-a-pantalla-completa.md) (https://sistemadedisseny.gencat.cat/38669693e/p/3006bf).

### Àrea clicable
Tota la zona del camp d'entrada és clicable a excepció dels botons específics interns. El hover del camp conviu amb el hover d'aquests elements. (Figma: Hover intern, Camp d'entrada / Components / Botó de xat / DOC_Camp d'entrada de xat / Disseny / Hover intern.)

### Alçada del camp
A mesura que l'usuari escriu en el camp d'entrada, aquest va creixent fins a un màxim de 160 px (equival a unes 6 línies de text a 16 pts). A partir d'aquest punt apareix una barra d'scroll al lateral per permetre desplaçar el contingut. (Figma: Alçada camp defecte.)

Aquesta alçada es redueix en funció de l'alçada de pantalla. Això aplica principalment al zoom del 400 %. En aquest cas l'alçada màxima serà de 84 px i de 60 px si també hi ha visible el botó de fitxers adjunts. (Figma: Alçada camp zoom.)

### Afegir fitxer adjunt
Aquest botó permet adjuntar fitxers o altres continguts a una conversa perquè el sistema els pugui processar o analitzar com a part de la interacció amb l'usuari. S'utilitza dins del camp d'entrada del xat i dona accés a les opcions disponibles per afegir documents, imatges o altres tipus de fitxer.

S'utilitza quan:
- L'usuari ha d'adjuntar un document perquè el sistema el pugui analitzar.
- Es permet enviar imatges o captures per complementar la consulta.
- El sistema admet entrades multimodals (text + fitxers).

### Flux d'adjunció de contingut
Quan l'usuari selecciona el botó d'adjuntar contingut, el sistema mostra les opcions disponibles per incorporar contingut al missatge. El comportament pot variar segons el punt de tall:
- Extra Large - Medium / Xat flotant: es mostra un menú desplegable amb les accions disponibles.
- Small: s'obre un panell inferior amb les mateixes opcions adaptades al context mòbil.

En tots dos casos, l'usuari pot seleccionar el tipus de contingut que vol adjuntar. (Figma: Adjuntar_contingut_small; Adjuntar_contingut_large_pantalla.)

### Visualització del contingut adjunt
Un cop l'usuari selecciona el contingut, els fitxers adjunts es mostren dins del camp de missatge del xat abans de l'enviament. Els adjunts es representen en forma de botó que indica el nombre de fitxers afegits (per exemple, "1 fitxer adjunt" o "2 fitxers adjunts"). La forma en què es mostren depèn del punt de tall del dispositiu:
- Extra Large - Medium: es mostren en una modal.
- Small: s'obre un panell inferior.

(Figma: Visualització_mobile; Visual desktop.) Quan l'usuari selecciona aquest element, es mostra una modal amb el detall dels fitxers adjunts. En aquesta vista l'usuari pot:
- Veure la llista de fitxers adjunts.
- Eliminar un fitxer abans d'enviar el missatge.

(Figma: Vista.) Per entendre el funcionament dels fitxers un cop s'han enviat al xat, revisa l'apartat "Comportament" del component [Missatge de xat](component-missatge-de-xat.md) (https://sistemadedisseny.gencat.cat/38669693e/p/9091df).

### Interacció de veu a text
Per veure com funciona aquesta interacció consulta el patró [Interacció veu a text](patro-interaccio-veu-a-text.md) (https://sistemadedisseny.gencat.cat/38669693e/p/10954b-interaccio-veu-a-text).

## Contingut i microcopy
Textos d'exemple: placeholder "Escriu…"; valor "Sóc un input"; botons "Enviar nota de veu" i "Dictar text"; etiquetes d'adjunts "1 fitxer adjunt" / "2 fitxers adjunts".

## Bones pràctiques

### Variants
- **NO FER:** No utilitzis la variant per a xats flotants en xats a pantalla completa i viceversa.

### Accions
- **NO FER:** No afegeixis més botons a primer nivell en la zona esquerra del camp d'entrada. Inclou-los dins del desplegable.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG) que cita el component:
- **1.4.1 Ús del color (A):** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a diferenciar els diferents estats s'inclouen subratllats, es juga amb la presència de farciment i el gruix de la vora. (https://www.w3.org/Translations/WCAG22-ca/#use-of-color · https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **1.4.3 Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. (https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum · https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **1.4.4 Canvia la mida del text (AA):** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. (https://www.w3.org/Translations/WCAG22-ca/#resize-text · https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **1.4.11 Contrast d'elements no textuals (AA):** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. (https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast · https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **2.1.1 Teclat (A):** tota la funcionalitat del contingut (navegar pels diferents botons) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. (https://www.w3.org/Translations/WCAG22-ca/#keyboard · https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **2.4.3 Ordre del focus (A):** l'ordre del focus per navegar per teclat és el següent: (1) contenidor de xat, que engloba tot el contenidor; mentre l'usuari és aquí pot escriure; (2) botó per afegir elements adjunts; (3) grup de botons començant d'esquerra a dreta, l'últim serà el d'enviar; (4) botó de documents adjunts. (https://www.w3.org/Translations/WCAG22-ca/#focus-order · https://www.w3.org/WAI/WCAG22/Understanding/focus-order)
- **2.4.7 Focus visible (AA):** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. (https://www.w3.org/Translations/WCAG22-ca/#focus-visible · https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

## Implementació (component web)

### `<chat-input-component>`
Paquet: conversational.

**Propietats**

Taula de la pàgina del lloc (amb obligatorietat):

| Propietat | Atribut HTML | Descripció | Obligatorietat | Tipus |
|---|---|---|---|---|
| `chatInputId` | `chat-input-id` | Identificador del component | Obligatori | String |
| `placeholder` | `placeholder` | Placeholder de l'entrada | Opcional | String |
| `sendOnEnter` | `send-on-enter` | Permet habilitar l'enviament d'un missatge amb la tecla enter | Opcional | Boolean |
| `showAttachButton` | `show-attach-button` | Visibilitat del botó d'adjuntar fitxers | Opcional | Boolean |
| `value` | `value` | Value predeterminat de l'input | Opcional | String |
| `widthChat` | `width-chat` | Indica l'amplada del xat on serà introduït | Obligatori | String |

Valors per defecte i matisos segons el PDF (v12.0.0):

| Propietat | Atribut HTML | Descripció (PDF) | Tipus | Per defecte |
|---|---|---|---|---|
| `chatInputId` | `chat-input-id` | Identificador únic de l'element. | string | undefined |
| `placeholder` | `placeholder` | Text de marcador de posició del camp d'entrada. | string | undefined |
| `sendOnEnter` | `send-on-enter` | Envia el missatge en prémer la tecla Enter. | boolean | true |
| `showAttachButton` | `show-attach-button` | Mostra o amaga aquest element. | boolean | true |
| `showMicButton` | `show-mic-button` | Mostra o amaga aquest element. | boolean | false |
| `value` | `value` | Valor actual del component. | string | `` (cadena buida) |
| `widthChat` | `width-chat` | Amplada del component de xat. Opcions: `floating`, `full-width`. | string | `floating` |

[discrepància: el PDF documenta la propietat `showMicButton` (`show-mic-button`), que no apareix a la taula del lloc; la versió Github 12.0.0 hi afegeix el botó micròfon per transcriure missatges]

**Variants (lloc)**

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `widthChat` | `full-width` `floating` | `floating` |

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre (lloc) | Tipus (PDF) |
|---|---|---|---|
| `attachmentRemoved` | Esdeveniment llançat en eliminar un fitxer adjuntat (PDF: s'emet quan l'usuari elimina un element) | Objecte amb el detall del fitxer eliminat | `CustomEvent<File>` |
| `attachmentSelected` | Esdeveniment en prémer el botó d'enviar missatge o d'adjuntar fitxer (PDF: s'emet quan l'usuari selecciona un element) | Objecte amb el detall del fitxer adjuntat | `CustomEvent<ChatInputAttachmentDetail>` |
| `sendRequest` (lloc) / `sendRequested` (PDF) | Esdeveniment emès en enviar un missatge (PDF: s'emet quan l'usuari envia el formulari o les dades) | Objecte: `clientMessageId` `message` `files` | `CustomEvent<ChatInputSendRequestDetail>` |
| `photoRequest` | Esdeveniment llançat en prémer el botó d'obrir càmera del dispositiu. La funcionalitat d'aquesta acció no està implementada. (PDF: s'emet quan l'usuari sol·licita adjuntar una foto) | Emet l'identificador de l'opció seleccionada i el missatge que contingui l'input | `CustomEvent<ChatInputPhotoRequestDetail>` |
| `valueChange` | Esdeveniment llançat de forma immediata en canviar el value de l'input (PDF: s'emet quan el valor del component canvia) | `value` | `CustomEvent<string>` |
| `valueChangeRetarded` | Esdeveniment llançat en adjuntar un o diversos fitxers (PDF: s'emet quan el valor del component canvia) | `value` | `CustomEvent<string>` |

[discrepància: el lloc anomena l'esdeveniment `sendRequest`; el PDF diu `sendRequested`]

**Mètodes públics (PDF):** `clearDraft()`, `focusInput()`, `getDraft()`.

**Slots**

Components que es poden introduir mitjançant slot:
- **`button-component`:** formen part del grup de botons que inclou el botó d'enviar. Atribut: `slot="group-button-chat-input"`.

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<chat-input-component 
    chat-input-id="chat-input-id-1" 
    placeholder="Escriu…" 
    send-on-enter="true"
    show-attach-button="true"
    value="Sóc un input"
    width-chat="full-width"
>
  <button-component 
      slot="group-button-chat-input" 
      class-name-icon="bi-soundwave" 
      class-name-button="icn-btn-tertiary" 
      size-button="icn-btn-size-S"
      mode-color-button="mode-color-tertiary-light" 
      right-icon-chevron="false" 
      left-icon-chevron="false" 
      left-icon="true"
      right-icon="false" 
      aria="Enviar nota de veu" 
      text-tooltip="Enviar nota de veu" 
      custom-id='audio-button-1'
    ></button-component>
    <button-component 
      slot="group-button-chat-input" 
      class-name-icon="bi-mic" 
      class-name-button="icn-btn-tertiary"
      size-button="icn-btn-size-S" 
      mode-color-button="mode-color-tertiary-light" 
      right-icon-chevron="false"
      left-icon-chevron="false" 
      left-icon="true" 
      right-icon="false" 
      aria="Dictar text" 
      text-tooltip="Dictar text"
      custom-id='audio-button-2'
    ></button-component>
</chat-input-component>
```

**Exemple d'instància (PDF)**

```html
<chat-input-component
chat-input-id="texto-ejemplo"
placeholder="texto-ejemplo"
send-on-enter=true
show-attach-button=true
show-mic-button=false
value=''
width-chat='floating'
></chat-input-component>
```

**Depèn de:** paquet core: `button-component` ([Botons](component-botons.md)), `dropdown-button-component` (lloc i PDF); PDF: també `group-button-component` ([Grup de botons](component-grup-de-botons.md)) i `modal-component` ([Modals](component-modals.md)).

**Utilitzat per:** `floating-chat-container-component` (lloc i PDF), `side-panel-chat-component` (PDF) ([Contenidor de xat](component-contenidor-de-xat.md)).

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 2.1.0 | 12.0.0 | 10 juliol, 2026 | Desenvolupament: s'afegeix botó micròfon per transcriure missatges |
| 2.1.0 | 11.0.0 | 19 juny, 2026 | Desenvolupament: es realitza un ajust d'accessibilitat per al dropdown-button |
| 2.1.0 | 10.1.0 | 29 maig, 2026 | Desenvolupament: es canvia la icona del botó d'enviament |
| 2.1.0 | 9.4.0 | 17 abril, 2026 | Desenvolupament: s'ha afegit la funcionalitat d'adjuntar fitxers fent ús del dropdown button; s'ha introduït la previsualització de fitxers carregats mitjançant modal component; s'han creat events per conèixer l'estat dels fitxers i/o missatges enviats i s'ha millorat l'accessibilitat del component. |
| 2.1.0 | 9.3.0 | 20 març, 2026 | Disseny: es dissenya la variant per al xat flotant; s'afegeix el botó d'arxius adjunts com a booleana. Desenvolupament del component |
| 2.0.0 | - | 02 març, 2026 | Disseny del component |

## Vegeu també
- [Botons](component-botons.md), [Modals](component-modals.md), [Grup de botons](component-grup-de-botons.md), [Contenidor de xat](component-contenidor-de-xat.md), [Missatge de xat](component-missatge-de-xat.md), [Xat a pantalla completa](patro-xat-a-pantalla-completa.md), [Interacció veu a text](patro-interaccio-veu-a-text.md)
