# Iconografia (Iconography)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/43ad0e · Font actualitzada el 2026-09-09 · Extret el 2026-10-28

## Introducció
***Iconography***
Conjunt de símbols i icones visuals que representen accions, idees o funcionalitats, i que ajuden a comunicar la informació i guiar els usuaris a través de la interfície.

## Ús genéric

### Descripció i ús
La llibreria d'icones *Bootstrap icons* disposa de 2.000 icones diferents, és gratuïta i està disponible amb llicència MIT. Es poden incloure com SVGs, SVG sprite o fonts web.
[https://icons.getbootstrap.com](https://icons.getbootstrap.com)

#### Quan s'utilitza

##### Navegació i orientació
Ajuden els usuaris a trobar el seu camí i entendre com interactuar amb la interfície. Permeten un escaneig ràpid sense necessitat de llegir tot el contingut textual. Per exemple, una icona de lupa per a la cerca o les icones que acompanyen a diferents targetes.

##### Eines i funcionalitats
Indiquen eines disponibles i funcionalitats, com ara editar, compartir, descarregar, etc. Permeten als usuaris identificar ràpidament l'acció que cada botó realitzarà.

##### Indicació d’estats
Mostren l'estat d'un procés o element, com ara carregar, completar, error o notificacions. Això ajuda els usuaris a comprendre l'estat actual de les interaccions o de l'aplicació.

### Anatomia
S'utilitzaran tres mides per a la iconografia segons l'aplicació d'aquesta:
- **Accions i etiquetes:** 20px, 24 px.
- **Suport visual:** 32 px, 48 px.

| **Token** | **Valor** |
|---|---|
| *Extra Small* | 20 px |
| *Small* | 24 px |
| *Medium* | 32 px |
| *Large* | 48 px |

Pel que fa a la **tipologia** d'icones usades de la llibreria, s'usaran aquelles que **no tenen farciment.**

### Bones pràctiques

#### Elements complementaris
- **FER:** En l’entorn del ciutadà, acompanya de text les icones amb significats més abstractes.
- **NO FER:** En l’entorn del ciutadà, no deixis les icones amb significats més abstractes sense acompanyar de text.
- **FER:** En l’entorn Personal intern, les icones poden aparèixer soles però acompanyades d’un indicador de funció.
- **NO FER:** En l’entorn Personal intern, no mostris les icones soles sense un indicador de funció.

#### Alineació
- **FER:** Centra les icones verticalment respecte al text que acompanyen.
- **NO FER:** Evita alinear les icones a la part superior o inferior del text al qual acompanyen.

#### Context
- **NO FER:** No utilitzis icones en menús de navegació de portals públics orientats a la ciutadania.

#### Mida
- **FER:** Utilitza icones d'una mida mínima de 24 px.
- **NO FER:** No utilitzis icones d'una mida mínima inferior a 24 px.

#### Representació visual
- **FER:** Utilitza icones només quan el text al qual volem introduir una icona no té una representació visual clara.
- **NO FER:** No utilitzis icones quan el text al qual volem introduir una icona  té una representació visual clara.

## Iconografia

### Iconografia
Figma: Action (Iconografia/Action) ; Navigation (Iconografia/Navigation) ; Visualization (Iconografia/Visualization) ; Communication (Iconografia/Communication) ; Objects (Iconografia/Objects) ; Specific functions (Iconografia/Specific functions) ; Multimedia (Iconografia/Multimedia) ; Placeholder (Iconografia/Placeholder) ; Notifications & states (Iconografia/Notifications & states)

## Tokens
A continuació es mostren els tokens de mida de la iconografia. Usar preferentment "Size Icons". "Size" són les referències dels tokens de "Size Icons" i el seu ús es recomana per definir mides no definides per "Size Icons".

### Size Icons

| **Token** | **Referència** |
|---|---|
| --size-icons-lg | --size-x3 |
| --size-icons-md | --size-x2 |
| --size-icons-sm | --size-x1-5 |
| --size-icons-xs | --size-x1-25 |
| --size-icons-xxs | --size-x1 |

### Size

| **Token** | **Referència** |
|---|---|
| --size-x0-175 | --spacing-2 |
| --size-x0-25 | --spacing-4 |
| --size-x0-5 | --spacing-8 |
| --size-x0-75 | --spacing-12 |
| --size-x1 | --spacing-16 |
| --size-x1-25 | --spacing-20 |
| --size-x1-5 | --spacing-24 |
| --size-x2 | --spacing-32 |
| --size-x2-5 | --spacing-40 |
| --size-x3 | --spacing-48 |
| --size-x3-5 | --spacing-56 |
| --size-x4 | --spacing-64 |
| --size-x4-5 | --spacing-72 |
| --size-x5 | --spacing-80 |
| --size-x8 | --spacing-128 |

### Mides d'icones resoltes (resolució derivada de les referències de la font)

| Token | Referència | Via | Valor |
|---|---|---|---|
| --size-icons-lg | --size-x3 | --spacing-48 | 48px (Large) |
| --size-icons-md | --size-x2 | --spacing-32 | 32px (Medium) |
| --size-icons-sm | --size-x1-5 | --spacing-24 | 24px (Small) |
| --size-icons-xs | --size-x1-25 | --spacing-20 | 20px (Extra Small) |
| --size-icons-xxs | --size-x1 | --spacing-16 | 16px |

> Nota: el text diu "tres mides" però en llista quatre (Extra Small 20, Small 24, Medium 32, Large 48); la bona pràctica fixa una mida mínima de 24 px. `--size-icons-xxs` (16 px) existeix com a token però no figura a l'anatomia. [a verificar]

## Primitives
> Els valors primitius per a la iconografia es prenen de les primitives d'[espaiats](fonaments-espaiat.md).

## Versions

### Versions

| **Versió Figma** | **Versió Github** | **Data** | **Descripció** |
|---|---|---|---|
| 5.0.1 | 3.0.0 | 19 juny, 2026 | **Disseny**: Modificació de la icona de “stop”. S’augmenta la mida de la icona dins el contenidor a 16 px. |
| 4.0.0 | 3.0.0 | 8 maig, 2026 | **Disseny**: nova icona per enviar missatges de xat. |
| 3.0.0 | 3.0.0 | 17 abril, 2026 | **Disseny**: - S’inclou icona per dibuixar un polígon en el mapa. / - S’inclouen 2 icones noves a la categoria Communications, la icona de Flickr i de Vimeo. |
| 2.0.0 | 3.0.0 | 05 desembre, 2025 | **Disseny**: S’inclou icona per dibuixar en el mapa. |
| 1.1.0 | 3.0.0 | 06 octubre, 2025 | **Disseny**: S’inclouen 2 icones a la categoria Altres, relacionades amb equipaments. |
| 1.0.0 | 3.0.0 | 12 setembre, 2025 | **Disseny**: S’enllacen variables de color i mides correctament. |
| Traspàs a nova llibreria |  |  |  |
| 7.0.0 | 3.0.0 | 28 juliol, 2025 | **Disseny**: s'afegeix la icona Telegram_icon. |
| 6.0.0 | 3.0.0 | 08 juliol, 2025 | **Disseny**: s'afegeixen les icones Whatsapp_icon, crosshair, satellite, baby_changing_station, elevator, handshake, Lost and Found, sign-parking, sign_language i dog. |
| 4.0.0 | 3.0.0 | 09 juny, 2025 | **Disseny:** s'afegeixen noves icones. |
| 2.2.0 | 0.1.1 | 20 gener, 2025 | **Disseny:** Creació de la versió *small* de la icona d'enllaç extern. |
| 2.1.0 | 0.1.1 | 04 desembre, 2024 | Sense canvis |
| 2.0.0 | 0.1.0 | 02 desembre, 2024 | **Disseny:** Es corregeix la mida d’icones relacionada amb termòmetres. |
| 1.1.0 | 0.1.0 | 22 novembre, 2024 | Sense canvis |
| 1.1.0 | 0.0.4 | 18 novembre, 2024 | Sense canvis |
| 1.0.0 | 0.0.3 | 1 novembre, 2024 | **Disseny**, **desenvolupament** i **documentació** del fonament |
