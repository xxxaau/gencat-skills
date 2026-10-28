# Arrodoniment (Corner radius)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/5305a6 · Font actualitzada el 2025-10-28 · Extret el 2026-10-28

## Introducció
***Corner radius***
El sistema de disseny permet cantonades arrodonides a una varietat de components. Per a una referència simple, els valors mètrics per al radi de la cantonada són 12, 8, 4 i 2. Aquestes mètriques de radi depenen de la mida del component al qual s'aplica.

## Ús genèric

### Descripció i ús

#### Quan s'utilitza

##### Botons
Aplicar el radi de la cantonada als botons pot suavitzar les seves vores, fet que els dona un aspecte més acollidor i tàctil. Les cantonades arrodonides també poden ajudar a distingir els botons primaris i secundaris, ja que els radis més grans sovint s'utilitzen per a accions primàries, cridant així més l'atenció.

##### Targetes
El radi de cantonada s'utilitza sovint en targetes i panells per crear una sensació de profunditat i separació entre seccions de contingut. Les cantonades arrodonides donen a les targetes un aspecte més modern i polit, millorant el seu atractiu visual.
**Camps d'entrada i controls de formulari**
Les cantonades arrodonides en camps d'entrada, caselles de selecció, botons d'opció i altres controls de formulari fan que semblin més amigables i accessibles. Un radi de cantonada subtil també millora els objectius tàctils, facilitant als usuaris interactuar amb aquests elements en dispositius tàctils.
**Insígnies i etiquetes**
El radi de cantonada estilitza insígnies o etiquetes, afegint un toc decoratiu i mantenint la coherència amb altres components de la interfície d'usuari.
**Modals i diàlegs**
Les cantonades arrodonides en modals i diàlegs suavitzen la seva aparença i creen una experiència d'usuari més acollidora. També ajuden a distingir aquests elements superposats de l'àrea de contingut principal.

### Variants

| **Nom** | **Rem** | **Pixels** | **Exemple** |
|---|---|---|---|
| *Cap* | 0 | 0 px | [Figma] Exemples01 ⟨         Sí 07. Arrodoniment/Fonaments/Arrodoniment/Exemples01⟩ |
| *Petita* | 0,25 | 4 px | [Figma] Exemples02 ⟨         Sí 07. Arrodoniment/Fonaments/Arrodoniment/Exemples02⟩ |
| *Mitjana* | 0,5 | 8 px | [Figma] Exemples03 ⟨         Sí 07. Arrodoniment/Fonaments/Arrodoniment/Exemples03⟩ |
| *Llarga* | 0,75 | 12 px | [Figma] Exemples04 ⟨         Sí 07. Arrodoniment/Fonaments/Arrodoniment/Exemples04⟩ |
| *Extrallarga* | 1 | 16 px | [Figma] Exemples05 ⟨         Sí 07. Arrodoniment/Fonaments/Arrodoniment/Exemples05⟩ |
| *Ple* | 50% | 50% | [Figma] Exemples06 ⟨         Sí 07. Arrodoniment/Fonaments/Arrodoniment/Exemples06⟩ |

### Bones pràctiques

#### **Consistència**
- **FER:** Es manté la consistència en radis de cantonades a través de diversos components dins del sistema de disseny. Això ajuda a crear un llenguatge visual coherent i harmoniós a tota la interfície.
- **NO FER:** No es manté la consistència en radis de cantonades a través de diversos components dins del sistema de disseny.

#### Jerarquia
- **FER:** Utilitza diferents radis de les cantonades per establir la jerarquia visual dins dels components de la interfície d'usuari. Els radis de cantonada més grans s'utilitzen per a elements primaris o prominents, mentre que els radis més petits es poden aplicar a elements secundaris.
- **NO FER:** No utilitzis diferents radis de les cantonades per establir la jerarquia visual dins dels components de la interfície d'usuari. Els radis de cantonada més petits s'utilitzen per a elements primaris o prominents, mentre que els radis més grans es poden aplicar a elements secundaris.

## Token

### Corner Radius

| **Token** | **Referència** |
|---|---|
| --full | --spacing-96 |
| --xl | --spacing-16 |
| --lg | --spacing-12 |
| --md | --spacing-8 |
| --sm | --spacing-4 |
| --xs | --spacing-2 |

## Primitives
> Els valors primitius per a les elevacions es prenen primitives d'[espaiats](fonaments-espaiat.md).

## Versions

### Versions

| **Versió Figma** | **Versió Github** | **Data** | **Descripció** |
|---|---|---|---|
| 2.2.0 | 0.1.1 | 20 gener, 2025 | Sense canvis |
| 2.1.0 | 0.1.1 | 04 desembre, 2024 | Sense canvis |
| 2.0.0 | 0.1.0 | 02 desembre, 2024 | Sense canvis |
| 1.1.0 | 0.1.0 | 22 novembre, 2024 | Sense canvis |
| 1.1.0 | 0.0.4 | 18 novembre, 2024 | Sense canvis |
| 1.0.0 | 0.0.3 | 1 novembre, 2024 | **Disseny**, **desenvolupament** i **documentació** del fonament |

> Nota: la taula de variants indica "Ple" = 50%, mentre que el token `--full` referencia `--spacing-96` (96px). [discrepància: variants diuen 50%; token diu --spacing-96] [a verificar]. Els tokens de la pestanya Token (xs, sm, md, lg, xl, full) no tenen variant "Cap" (0 px).
