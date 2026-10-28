# Avatar (Avatar)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/0971aa · Web component: `<avatar-component>` (paquet conversational) · Font actualitzada el 2026-06-24 · Extret el 2026-10-28

## Què és i quan usar-lo
Element gràfic que representa l'assistent o agent en una conversa amb un usuari dins d'una interfície conversacional.

El component Avatar és un element gràfic que representa visualment un agent, un bot o un actor del sistema dins d'una conversa o llista de participants. La seva funció primordial és l'**Atribució**, identificant de manera ràpida i inequívoca qui és l'emissor del missatge.

Quan s'utilitza:
- **Agent:** quan el missatge prové d'un **agent automatitzat**, proporcionant-li una identitat.
- **Usuari:** quan el missatge prové d'un **treballador**.

## Quan NO usar-lo / alternatives
- Quan l'assistent envia missatges consecutius en un curt període de temps, **només** s'ha de mostrar l'Avatar amb el **primer** missatge del bloc. S'omet en els missatges següents per estalviar espai vertical i enfocar-se en el contingut.

## Anatomia
Figma: Avatar [Type = Agent]. El component està format per diverses instàncies (vegeu Variants, tipus i estats).

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Type | Agent / Human | Agent |

### Estats de l'avatar d'agent (Agent avatar states)

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Default / Thinking | Default |

Variant Figma: `_Avatar states` [State = Default].

### Tipus d'avatar humà (Human avatar type)

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Type | Icon / Text / Image | Icon |

Variant Figma: `_User Avatar type` [Type = Icon].

## Comportament i interacció

### Ubicació
L'Avatar ha d'estar alineat amb la part superior del missatge per mantenir la jerarquia visual i connectar de forma immediata la identitat de l'assistent amb el contingut que proporciona. Per reduir el soroll visual i optimitzar l'espai, l'Avatar de l'Assistent Virtual només ha d'aparèixer amb el **primer missatge d'una seqüència de respostes consecutives**.

## Bones pràctiques

### Forma
- **NO FER:** No modifiquis la forma de la icona.

### Color
- **FER:** Utilitza cadascuna de les versions de color sobre el fons adequat perquè tingui prou contrast (3:1).

### Substitució de la icona
- **NO FER:** No utilitzis la icona d'assistent virtual per l'avatar.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG):
- **1.4.11 Contrast d'elements no textuals (AA):** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. (https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast · https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)

## Implementació (component web)

### `<avatar-component>`
Paquet: conversational.

**Propietats**

Taula de la pàgina del lloc (amb obligatorietat):

| Propietat | Atribut HTML | Descripció | Obligatorietat | Tipus |
|---|---|---|---|---|
| `avatarColor` | `avatar-color` | Color de l'avatar | Obligatori | String |
| `mode` | `mode` | Tipus d'avatar. | Obligatori | String |
| `src` | `src` | URL de la imatge que es mostra com a avatar. | Opcional | String |
| `initials` | `initials` | Inicials que es mostren a l'avatar. | Opcional | String |
| `color` | `color` | Color de fons de l'avatar. | Opcional | String |

Valors per defecte i matisos segons el PDF (v12.0.0):

| Propietat | Atribut HTML | Descripció (PDF) | Tipus | Per defecte |
|---|---|---|---|---|
| `avatarColor` | `avatar-color` | Color de l'element. Opcions: `black`, `color`, `white`. | string | `color` |
| `color` | `color` | Color de l'element. Opcions: `blue`, `dark`, `green`, `purple`, `red`, `white`, `yellow`. | string | undefined |
| `initials` | `initials` | Inicials mostrades a l'avatar de text. | string | undefined |
| `mode` | `mode` | Variant visual del component. Opcions: `bubble`, `icon`, `image`, `initials`, `loading`. | string | `icon` |
| `src` | `src` | URL del recurs associat. | string | undefined |

**Variants (lloc)**

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `avatarColor` | `black` `color` `white` | `color` |
| `mode` | `bubble` `icon` `initials` `image` `loading` | `icon` |
| `color` | `blue` `green` `yellow` `red` `purple` `dark` `white` | - |

**Esdeveniments:** cap esdeveniment declarat.

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
 <avatar-component
   mode="bubble"
   initials="DR"
   avatar-color="white"
   color="purple"
   src="/assets/photos/img_5.png">  
 </avatar-component>
```

**Exemple d'instància (PDF)**

```html
<avatar-component
avatar-color='color'
color="blue"
initials="texto-ejemplo"
mode='icon'
src="texto-ejemplo"
></avatar-component>
```

**Utilitzat per:** `chat-message-component` ([Missatge de xat](component-missatge-de-xat.md)).

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 1.0.0 | 9.4.0 | 17 abril, 2026 | Desenvolupament: s'ha introduït l'animació del `mode` loading mitjançant CSS. |
| 1.0.0 | 9.2.0 | 27 febrer, 2026 | Desenvolupament: s'hi afegeixen les variants d'icona, inicials, imatge de perfil i thinking |
| 1.0.0 | 9.0.0 | 12 gener, 2026 | Desenvolupament del component |
| 1.0.0 | - | 5 desembre, 2025 | Disseny i documentació del component |

## Vegeu també
- [Missatge de xat](component-missatge-de-xat.md)
