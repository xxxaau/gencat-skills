# Peu de pàgina (Footer)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/562431 · Web component: `<footer-component>` (paquet core) · Font actualitzada el 2026-10-15 · Extret el 2026-10-28

## Què és i quan usar-lo
El peu de pàgina és un component que es troba a la part inferior de les pàgines web i proporciona informació complementària i enllaços rellevants.

És l'última secció del web i està format per tres elements diferenciats:
- **El pre faldó:** opcional; inclou logotips institucionals que es vulguin mostrar en cada web.
- **El faldó:** opcional; conté enllaços d'interès del mateix web així com d'altres webs externs.
- **El peu de pàgina:** obligatori; inclou el logotip de la Generalitat i enllaços sobre continguts corporatius i de compliment normatiu del web.

Quan s'utilitza:
- En totes les pàgines del web per garantir coherència i accessibilitat.
- Per facilitar l'accés a informació rellevant i millorar la navegació.
- En els webs corporatius per reforçar la identitat visual i institucional.

## Anatomia
Figma: Anatomia general. L'estructura general del peu de pàgina es compon de:
1. **Pre faldó amb logotips** (opcional)
2. **Faldó** (opcional)
3. **Secció de xarxes socials** (opcional)
4. **Peu de pàgina.**

(La font diu "tres parts principals" però en llista quatre.)

### Pre faldó amb logotips
- **Ubicació:** es mostra al final del contingut de la pàgina, just abans del faldó. Peça **opcional**, que es pot afegir segons les necessitats de cada pàgina.
- **Composició:**
  - **Logotips:** es poden afegir fins a **8 logotips** diferents.
  - **Mides:** els logotips es mostren amb una alçada fixa de **44px**, mantenint sempre les proporcions originals.
  - **Marge entre logotips:** **32px** entre cada logotip.
  - **Distribució:** quan els logotips no entren en una sola línia, es distribueixen en diverses línies de manera automàtica.
- **Directrius generals per a la presentació de logotips:**
  - **Harmonització:** és fonamental que els logotips compleixin les normatives d'ús establertes i que la seva presentació visual sigui coherent amb la identitat institucional.
  - **Consulta de manuals:** per a una aplicació correcta, es recomana consultar els manuals d'identitat corporativa corresponents.
  - Enllaç d'interès: https://identitatcorporativa.gencat.cat/ca/inici/

### Faldó
- **Ubicació:** és l'espai del web que es troba abans del peu de pàgina. També opcional. S'utilitza per mostrar informació addicional que es repeteix a totes les pàgines, amb l'objectiu de transmetre missatges de comunicació o enllaçar amb altres recursos.
- **Composició:** dissenyat perquè els gestors del lloc web puguin editar i afegir contingut segons sigui necessari. Les seccions principals que el componen són 3 seccions d'enllaços (Figma: Anatomia faldó).
- **1. Secció d'enllaços:** cada secció té un títol, un subtítol i es compon de tres columnes, cadascuna amb el seu títol i una llista d'enllaços. Si només es vol mostrar un títol i els enllaços associats, el títol que es mostra és el de la secció.
  - Nota: el màxim de columnes a mostrar és **6**. Es poden distribuir en diferents combinacions, com 3 seccions amb 2 columnes cadascuna, 2 seccions amb 3 columnes cadascuna, o altres combinacions. Si se supera aquest límit, la visualització no és correcta.

### Secció de xarxes socials
Permet mostrar enllaços a les xarxes socials associades al lloc web. Cada botó de xarxa social redirigeix a la pàgina corresponent (Figma: Anatomia xarxes socials).

### Peu de pàgina
- **Ubicació:** és l'espai del web que es troba al final de la pàgina, després del faldó si n'hi ha, o després del contingut si no n'hi ha (Figma: Anatomia peu).
- **1. Logotip:** tots els webs de la Generalitat han d'incorporar, al marge inferior esquerre, el logotip de la Generalitat de Catalunya, que ha d'enllaçar amb la pàgina principal de Gencat (https://web.gencat.cat). Aquest logotip pot conviure amb la identificació pròpia d'un organisme, sempre que estigui registrada al **Programa d'Identificació Visual.**
  - Requisits dels logotips: han de ser blancs (#FFFFFF); han de tenir el fons transparent; l'alineació s'ha de fer en horitzontal.
  - Enllaços d'interès: [Identificació bàsica de la Generalitat de Catalunya](https://identitatcorporativa.gencat.cat/ca/descarregues/identificacio-basica/cat/) · [Harmonització dels logotips per departament](https://identitatcorporativa.gencat.cat/ca/descarregues/departaments-i-imatges-propies/)
- **2. Enllaços:** el peu està preparat per incloure fins a **vuit enllaços**. Els enllaços obligatoris són:
  - **Avís legal:** generalment el publicat a Gencat (https://web.gencat.cat/ca/ajuda/avis_legal/), però se'n pot incloure un de propi si cal.
  - **Política de galetes:** pàgina pròpia del web.
  - **Mapa web:** pàgina pròpia del web.
  - **Declaració d'accessibilitat:** pàgina pròpia del web.
  - Els enllaços són editables.

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Extra Large Column Variable / Extra Large Column Fix / Large / Medium / Small | Extra Large Column Fix |
| Show logos | True / False | True |
| Show pre-footer | True / False | True |
| Show Section 2 | True / False | True |
| Show Section 3 | True / False | True |
| Show social media | True / False | True |
| Show additional logo | True / False | True |

## Mides i espaiats
- Logotips del pre faldó: alçada fixa de 44px, marge de 32px entre logotips, fins a 8 logotips.
- Slots dels logos (v9.0.0 de Figma): Extra Large - Large: 220 x 44 px; Medium - Small: 180 x 36 px.
- Amplada mínima en versió small: 320 px (abans 360 px).
- Faldó: màxim 6 columnes.

## Comportament i interacció
### Adaptació responsiva
S'adapta automàticament a l'amplada de pantalla (Figma: Adaptació responsiva, mostra com es visualitza en els diferents punts de tall: Extra Large Column Variable, Extra Large Column Fix, Large, Medium, Small).

## Bones pràctiques

### Evita sobrecarregar
- **FER:** Mantingues una estructura neta i senzilla amb enllaços essencials.
- **NO FER:** No sobrecarreguis el peu de pàgina amb massa informació o enllaços.

### Visibilitat i contrast
- **FER:** Assegura un bon contrast entre el text i el fons per facilitar la lectura.
- **NO FER:** No utilitzis combinacions de colors que dificultin la llegibilitat.

### Logotips de color
- **FER:** Inclou logotips en blanc per mantenir la coherència visual.
- **NO FER:** No utilitzis logotips a color sobre el peu de pàgina.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG):
- **1.4.1 Ús del color (A):** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per indicar els canvis d'estat es modifiquen els píxels de la vora del component i/o s'afegeixen elements complementaris com la segona vora pel focus o la icona i el text d'error. (https://www.w3.org/Translations/WCAG22-ca/#use-of-color · https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **1.4.3 Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són excepció d'aquesta norma. (https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum · https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **1.4.4 Canvia la mida del text (AA):** excepte subtítols i imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. (https://www.w3.org/Translations/WCAG22-ca/#resize-text · https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **1.4.11 Contrast d'elements no textuals (AA):** els elements gràfics com logotips i botons d'icona presenten un contrast mínim de 3:1. (https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast · https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **2.1.1 Teclat (A):** tota la funcionalitat del contingut (accedir a enllaços i botons) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. (https://www.w3.org/Translations/WCAG22-ca/#keyboard · https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **2.4.7 Focus visible (AA):** la navegació a través dels diferents elements interactius (enllaços i botons) és visible mitjançant un rectangle extern. (https://www.w3.org/Translations/WCAG22-ca/#focus-visible · https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

## Implementació (component web)

### `<footer-component>`
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Obligatorietat (lloc) | Tipus | Per defecte (PDF) |
|---|---|---|---|---|---|
| `linksFooter` | `links-footer` | JSON per als enllaços del footer bottom | Opcional | String(Array) · PDF: `Link[]` o `string` | (no definit) |
| `logoAdditionalFooter` | `logo-additional-footer` | JSON de Logo addicional del footer | Opcional | String(Object) · PDF: `Logo` o `string` | (no definit) |
| `logoFooter` | `logo-footer` (lloc: `logo-Footer`) | JSON de Logo del footer | Opcional | String(Object) · PDF: `Logo` o `string` | (no definit) |
| `sections` | `sections` | JSON de les seccions del prefooter (PDF: accepta array d'objectes o string JSON) | Opcional | String(Array) · PDF: `Section[]` o `string` | (no definit) |
| `showAdditionalLogo` | `show-additional-logo` | Mostrar logo addicional | Opcional | boolean | `true` |
| `showLogos` | `show-logos` | Mostrar Logos | Opcional | boolean | `true` |
| `showPrefooter` | `show-prefooter` | Mostrar Prefooter | Opcional | boolean | `true` |
| `showSection2` | `show-section-2` | Mostrar Section 2 | Opcional | boolean | `true` |
| `showSection3` | `show-section-3` | Mostrar Section 3 | Opcional | boolean | `true` |
| `showSocialMedia` | `show-social-media` | Mostrar Xarxes socials | Opcional | boolean | `true` |
| `socialLinks` | `social-links` | JSON per als perfils de les xarxes socials | Opcional | String(Object) · PDF: `SocialLink` o `string` | (no definit) |
| `thirdpartyLogos` | `thirdparty-logos` | JSON dels logos de tercers (PDF: logotips; accepta array d'objectes o string JSON) | Opcional | String(Array) · PDF: `ThirdPartyLogo[]` o `string` | (no definit) |

**Props que accepten JSON (estructures)**

`thirdpartyLogos` (array d'objectes `ThirdPartyLogo`):

| Clau | Descripció | Atribut | Obligatorietat | Tipus |
|---|---|---|---|---|
| `alt` | Text alternatiu per a la imatge | `alt` | Obligatori | String |
| `url` | Url de la imatge | `url` | Obligatori | String |

`sections` (array d'objectes `Section`):

| Clau | Descripció | Atribut | Obligatorietat | Tipus |
|---|---|---|---|---|
| `columns` | JSON amb les dades de cada columna de la secció i els links | `columns` | Opcional (PDF: requerida) | String (Array) · PDF: `Column[]` |
| `sectionSubtitle` | Subtítol de la secció | `section-subtitle` | Opcional (PDF: requerida) | String |
| `sectionTitle` | Títol de la secció | `section-title` | Opcional (PDF: requerida) | String |

`columns` (array d'objectes `Column`):

| Clau | Descripció | Atribut | Obligatorietat | Tipus |
|---|---|---|---|---|
| `links` | JSON de la llista de links | `links` | Opcional | String(Array) |
| `title` | Títol de la columna de la secció | `title` | Opcional | String |

`links` (dins de `columns`):

| Clau | Descripció | Atribut | Obligatorietat | Tipus |
|---|---|---|---|---|
| `customId` | Identificador personalitzat per a l'enllaç. | `custom-id` | Opcional | String |
| `text` | Text que es mostra dins de l'enllaç. | `text` | Obligatori | string |

`socialLinks` (objecte `SocialLink`):

| Clau | Descripció | Atribut | Obligatorietat | Tipus |
|---|---|---|---|---|
| `socialProfiles` | JSON de la llista de links de xarxes socials | `social-profiles` | Opcional (PDF: requerida) | String (Array) · PDF: `SocialProfile[]` |
| `socialTitle` | Títol de la secció de xarxes socials | `social-title` | Opcional (PDF: requerida) | String |

`socialProfiles` (dins de `socialLinks`):

| Clau | Descripció | Atribut | Obligatorietat | Tipus |
|---|---|---|---|---|
| `ariaLabel` | Text alternatiu per a l'enllaç. | `aria-label` | Opcional | string |
| `icon` | Icona xarxa social. | `icon` | Opcional | string |
| `text` | Text que es mostra dins de l'enllaç. | `text` | Opcional | string |
| `textTooltip` | Text del tooltip | `text-tooltip` | Obligatori | string |

`logoFooter` (objecte `Logo`):

| Clau | Descripció | Atribut | Obligatorietat | Tipus |
|---|---|---|---|---|
| `alt` | Text alternatiu per a la imatge | `alt` | Obligatori | String |
| `url` | Url de la imatge | `url` | Obligatori | String |

`logoAdditionalFooter` (objecte `Logo`): mateixa estructura (`alt` obligatori, `url` obligatori; ambdós String).

`linksFooter` (array d'objectes `Link`):

| Clau | Descripció | Atribut | Obligatorietat | Tipus |
|---|---|---|---|---|
| `customId` | Identificador personalitzat del link del footer. | `custom-id` | Opcional | string |
| `text` | Text que es mostra dins de l'enllaç. | `text` | Obligatori | string |

Exemples JSON mínims (PDF):

```html
<footer-component
thirdparty-logos='[{"url":"texto-ejemplo","alt":"texto-ejemplo"}]'
></footer-component>
<footer-component
sections='[{"sectionTitle":"texto-ejemplo","sectionSubtitle":"texto-ejemplo","columns":"value"}]'
></footer-component>
<footer-component
social-links='{"socialTitle":"texto-ejemplo","socialProfiles":"value"}'
></footer-component>
<footer-component
logo-footer='{"url":"texto-ejemplo","alt":"texto-ejemplo"}'
></footer-component>
<footer-component
logo-additional-footer='{"url":"texto-ejemplo","alt":"texto-ejemplo"}'
></footer-component>
<footer-component
links-footer='[{"text":"texto-ejemplo","customId":"texto-ejemplo"}]'
></footer-component>
```

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre | Origen | Tipus (PDF) |
|---|---|---|---|---|
| `blurButton` | Es llança cada cop que es treu el focus en un botó. | - | `button-component` | |
| `focusButton` | Es llança cada cop que es fa focus en un botó. | - | `button-component` | |
| `handlerClick` | Esdeveniment llançat en fer clic sobre algun dels botons | `id` | `button-component` | |
| `blurLink` | Es llança cada cop que es treu el focus en un enllaç | - | `link-component` | |
| `focusLink` | Es llança cada cop que es fa focus en un enllaç | - | `link-component` | |
| `linkEmit` | Esdeveniment llançat en fer clic sobre el link | `id` | `link-component` | |
| `logoClicked` | Esdeveniment llançat en pressionar algun dels dos logos de la cantonada inferior esquerra del peu de pàgina | Logotip: `1` `2` | `footer-component` | `CustomEvent<number>` |

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<footer-component 
  show-logos='true' 
  show-prefooter='true' 
  show-section-2='true' 
  show-section-3='true'
  show-additional-logo='true'
  show-social-media="true"
  thirdparty-logos='[{"url":"/assets/logos/Feder.svg","alt":"Logo de la Generalitat de Catalunya"},{"url":"/assets/logos/NextGeneration.svg","alt":"Logo de la Generalitat de Catalunya"},{"url":"/assets/logos/Feder.svg","alt":"Logo de la Generalitat de Catalunya"},{"url":"/assets/logos/NextGeneration.svg","alt":"Logo de la Generalitat de Catalunya"},{"url":"/assets/logos/Feder.svg","alt":"Logo de la Generalitat de Catalunya"},{"url":"/assets/logos/NextGeneration.svg","alt":"Logo de la Generalitat de Catalunya"},{"url":"/assets/logos/Feder.svg","alt":"Logo de la Generalitat de Catalunya"},{"url":"/assets/logos/NextGeneration.svg","alt":"Logo de la Generalitat de Catalunya"}]'
  sections='[{"sectionTitle":"Informació general","sectionSubtitle":"Seccion subtitol","columns":[{"title":"Tràmits i serveis","links":[{"text":"Cita prèvia"},{"text":"Ajuts i subvencions"},{"text":"Certificats"}]},{"title":"Ciutadania","links":[{"text":"Educació"},{"text":"Habitatge"}]}]},{"sectionTitle":"Transparència","sectionSubtitle":"Seccion subtitol","columns":[{"title":"Accés obert","links":[{"text":"Pressupostos"},{"text":"Contractes"}]}]},{"sectionTitle":"Informació general","sectionSubtitle":"Seccion subtitol","columns":[{"title":"Tràmits i serveis","links":[{"text":"Cita prèvia"},{"text":"Ajuts i subvencions"},{"text":"Certificats"}]},{"title":"Ciutadania","links":[{"text":"Educació"},{"text":"Habitatge"}]}]}]'
  social-links='{ "socialTitle": "Segueix-nos a les xarxes socials", "socialProfiles": [ { "icon": "twitter", "text": "Segueix-nos a Twitter", "ariaLabel": "Enllaç extern a Twitter", "textTooltip": "Enllaç a Twitter" }, { "icon": "facebook", "text": "Segueix-nos a Facebook", "ariaLabel": "Enllaç extern a Facebook", "textTooltip": "Enllaç a Facebook" }, { "icon": "instagram", "text": "Segueix-nos a Instagram", "ariaLabel": "Enllaç extern a Instagram", "textTooltip": "Enllaç a Instagram" }, { "icon": "telegram", "text": "Segueix-nos a Telegram", "ariaLabel": "Enllaç extern a Telegram", "textTooltip": "Enllaç a Telegram" }, { "icon": "linkedin", "text": "Segueix-nos a Linkedin", "ariaLabel": "Enllaç extern a Linkedin", "textTooltip": "Enllaç a Linkedin" }, { "icon": "whatsapp", "text": "Segueix-nos a Whatsapp", "ariaLabel": "Enllaç extern a Whatsapp", "textTooltip": "Enllaç a Whatsapp" } ] }'
  logo-footer='{"url":"/assets/logos/gencat/gencat_horizontal_white_logo.svg","alt":"Logo de la Generalitat de Catalunya"}'
  logo-additional-footer='{"url":"/assets/logos/logoadditionalFooter.svg","alt":"Logo de la Generalitat de Catalunya"}'
  links-footer='[{"text":"Accessibilitat","alt":"Enllaç a la declaració d’accessibilitat", "customId":"link-accessibilitat"},{"text":"Sobre gencat","alt":"Enllaç a la pàgina de \"Sobre gencat\""},{"text":"Avís legal","alt":"Enllaç a l’avís legal"},{"text":"Política de galetes","alt":"Enllaç a la pàgina de Política de galetes"},{"text":"Mapa web","alt":"Enllaç a la pàgina del Mapa web"}]'>
  </footer-component>
```

**Exemple d'instància (PDF)**

```html
<footer-component
links-footer=[]
logo-additional-footer="texto-ejemplo"
logo-footer="texto-ejemplo"
sections=[]
show-additional-logo=true
show-logos=true
show-prefooter=true
show-section-2=true
show-section-3=true
show-social-media=true
social-links="texto-ejemplo"
thirdparty-logos=[]
></footer-component>
```

**Depèn de:** `button-component` ([Botons](component-botons.md)), `divider-component` ([Divisor](component-divisor.md)), `link-component` ([Enllaços](component-enllacos.md)).

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.0.0 | 10.0.0 | 29 maig, 2026 | Disseny: s'afegeix el component de llista d'enllaços (ara amb slot) en el prefooter subsection; s'aplica el component grup de botons pels botons de xarxes socials; s'aplica el component llista d'enllaços horitzontal (amb slot) pels enllaços inferiors. |
| 10.0.0 | 10.0.0 | 8 maig, 2026 | Desenvolupament: s'emet un esdeveniment quan es fa clic al logotip de la Generalitat; es reordenen els logotips inferiors |
| 10.0.0 | 9.3.0 | 17 abril, 2026 | Disseny: es substitueix la imatge per a logotips per un slot. |
| 9.0.0 | 9.3.0 | 27 febrer, 2026 | Disseny: s'ha modificat la mida dels slots dels logos a Extralarge - Large (220 x 44 px) i Medium - Small (180 x 36 px). Desenvolupament: ajust amplada i alçada dels logos superiors |
| 8.6.0 | 9.1.0 | 9 febrer, 2026 | Disseny: es modifica l'amplada mínima en versió small de 360 px a 320 px. |
| 8.2.0 | 9.1.0 | 6 febrer, 2026 | Desenvolupament: adaptacions d'accessibilitat pel que fa a mides de font extra gran i augment de pantalla |
| 8.2.0 | 6.2.1 | 27 octubre, 2025 | Disseny: revisió d'estils tipogràfics |
| 4.1.0 | 6.2.1 | 3 octubre, 2025 | Desenvolupament: nova propietat afegida o eliminada |
| 4.1.0 | 6.1.0 | 12 setembre, 2025 | Desenvolupament: nova propietat afegida |
| 4.1.0 | 6.0.1 | 28 juliol, 2025 | Desenvolupament: resolució de problemes |
| 4.1.0 | 5.0.0 | 9 juny, 2025 | Desenvolupament: resolució de problemes |
| 4.1.0 | 4.0.1 | 19 maig, 2025 | Disseny (ajustament): s'elimina la mida d'amplada màxima definida al punt de tall Extra Large Variable. Desenvolupament del component. |
| 4.0.0 | - | 2 maig, 2025 | Disseny i documentació del component |

## Vegeu també
- [Enllaços](component-enllacos.md): per facilitar la navegació entre parts del contingut o funcionalitats.
- [Menú horitzontal](component-menu-horitzontal.md): per navegar pels elements principals de la pàgina.
- [Pestanyes](component-pestanyes.md): per organitzar contingut relacionat en seccions o categories.
- [Llista d'enllaços](component-llista-d-enllacos.md), [Grup de botons](component-grup-de-botons.md).
