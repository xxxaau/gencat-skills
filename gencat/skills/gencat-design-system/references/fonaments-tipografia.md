# Tipografia (Typography)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/81ac5e · Font actualitzada el 2026-08-24 · Extret el 2026-10-28

## Introducció
***Typography***
La tipografia ajuda a crear jerarquies clares, organitzar la informació i guiar els usuaris mitjançant un producte o experiència.

## Ús genèric

### Família tipogràfica

#### Open Sans
Open Sans és la família tipogràfica corporativa de la Generalitat de Catalunya per a publicacions web.
Està dissenyada amb formes obertes i arrodonides, i ofereix una aparença amable i neutra. Està optimitzada per a impressió, web i interfícies mòbils, i té una excel·lent llegibilitat.
- És una Font de Google humanista, sense serifa, amb llicència Apache 2.0.
- Dissenyada per Steve Matteson, director de tipografia d’Ascender Corp.
- Conté 897 caràcters i inclou els de l'estàndard ISO Latin 1, Latin CE, Greek i Cyrillic.
Aquesta està disponible per a descarregar a [Google Fonts](https://fonts.google.com/specimen/Open+Sans).

#### FS Pimlico
FS Pimlico és la tipografia corporativa de Loteries de Catalunya i s'utilitza únicament per aquesta marca.

### Estils tipogràfics

#### Visualització

##### Escriptori
Figma: MD Regular (Display/Desktop/MD Regular)

##### Mòbil
Figma: MD Regular (Display/Mobile/MD Regular)

#### Encapçalament

##### Escriptori
Figma: XS Semibold (Heading/Desktop/XS Semibold) ; LG Semibold (Heading/Desktop/LG Semibold) ; XL Semibold (Heading/Desktop/XL Semibold) ; MD Semibold (Heading/Desktop/MD Semibold) ; SM Semibold (Heading/Desktop/SM Semibold)

##### Mòbil
Figma: XL Semibold (Heading/Mobile/XL Semibold) ; LG Semibold (Heading/Mobile/LG Semibold) ; MD Semibold (Heading/Mobile/MD Semibold) ; SM Semibold (Heading/Mobile/SM Semibold) ; XS Semibold (Heading/Mobile/XS Semibold)

#### Cos
Figma: LG Semibold (Body/LG Semibold) ; LG Regular (Body/LG Regular) ; SM Semibold (Body/SM Semibold) ; MD Regular (Body/MD Regular) ; LG Bold (Body/LG Bold) ; SM Bold (Body/SM Bold) ; SM Regular (Body/SM Regular) ; MD Semibold (Body/MD Semibold) ; MD Bold (Body/MD Bold)

#### Etiquetes
Figma: MD Regular (Label/MD Regular) ; LG Semibold (Label/LG Semibold) ; XS Semibold (Label/XS Semibold) ; MD Semibold (Label/MD Semibold) ; LG Regular (Label/LG Regular) ; SM Regular (Label/SM Regular) ; SM Semibold (Label/SM Semibold)

### Bones pràctiques

#### Context
- **FER:** Utilitza cada estil de text en el seu context d’ús. 
- **NO FER:** No utilitzis un estil de text diferent del determinat pel seu context d’ús.

#### Amplada
- **FER:** Utilitza una amplada de paràgraf d'entre 45 i 75 caràcters.
- **NO FER:** No utilitzis una amplada de paràgraf inferior a 45 caràcters o superior a 75 caràcters.

#### Minúscules
- **FER:** Prioritza l'ús de minúscules.
- **NO FER:** No prioritzis l'ús de majúscules.

## Primitives
> Les primitives són variables base del sistema de disseny i no han de ser utilitzades ni modificades directament.

### Gencat

#### Weight

| **Primitiva** | **Valor** |
|---|---|
| --weight-bold | 700 |
| --weight-semibold | 600 |
| --weight-regular | 400 |

#### Spacing
Veure a [Espaiat](fonaments-espaiat.md)

#### Size

| **Primitiva** | **Valor** |
|---|---|
| --size-xs | 12px |
| --size-s | 14px |
| --size-m | 16px |
| --size-l | 18px |
| --size-xl | 20px |
| --size-2xl | 24px |
| --size-3xl | 28px |
| --size-4xl | 32px |
| --size-5xl | 36px |
| --size-6xl | 40px |
| --size-7xl | 48px |
| --size-8xl | 56px |
| --size-9xl | 60px |
| --size-10xl | 72px |

#### Font family

| **Primitiva** | **Valor** |
|---|---|
| --family-primary | Open Sans |

### Loteries de Cataljunya

#### Weight

| **Primitiva** | **Valor** |
|---|---|
| --weight-bold | 700 |
| --weight-semibold | 600 |
| --weight-regular | 400 |

#### Spacing
Veure a [Espaiat](fonaments-espaiat.md)

#### Size

| **Primitiva** | **Valor** |
|---|---|
| --size-xs | 14px |
| --size-s | 16px |
| --size-m | 18px |
| --size-l | 20px |
| --size-xl | 24px |
| --size-2xl | 28px |
| --size-3xl | 32px |
| --size-4xl | 36px |
| --size-5xl | 40px |
| --size-6xl | 48px |
| --size-7xl | 56px |
| --size-8xl | 60px |
| --size-9xl | 72px |
| --size-10xl | 80px |

#### Font family

| **Primitiva** | **Valor** |
|---|---|
| --family-primary | FS Pimlico |

## Tokens
A continuació es mostren els tokens de tipografia del sistema de disseny disponibles a la llibreria. Utilitza els tipus següents segons el cas d'ús.

### Body

| **Token** | **Referència** |
|---|---|
| --body-family | --family-primary |
| --body-l-bold-weight | --weight-bold |
| --body-l-paragraph-spacing | --spacing-16 |
| --body-l-regular-weight | --weight-regular |
| --body-l-semibold-weight | --weight-semibold |
| --body-l-size | --size-xl |
| --body-m-bold-weight | --weight-bold |
| --body-m-paragraph-spacing | --spacing-12 |
| --body-m-regular-weight | --weight-regular |
| --body-m-semibold-weight | --weight-semibold |
| --body-m-size | --size-m |
| --body-s-bold-weight | --weight-bold |
| --body-s-paragraph-spacing | --spacing-8 |
| --body-s-regular-weight | --weight-regular |
| --body-s-semibold-weight | --weight-semibold |
| --body-s-size | --size-s |

### Display

| **Token** | **Referència** |
|---|---|
| --display-desktop-m-size | --size-8xl |
| --display-family | --family-primary |
| --display-mobile-m-size | --size-7xl |
| --display-weight | --weight-regular |

### Heading

| **Token** | **Referència** |
|---|---|
| --heading-family | --family-primary |
| --heading-weight | --weight-semibold |
| --heading-desktop-xl-size | --size-7xl |
| --heading-desktop-l-size | --size-6xl |
| --heading-desktop-m-size | --size-4xl |
| --heading-desktop-s-size | --size-3xl |
| --heading-desktop-xs-size | --size-2xl |
| --heading-mobile-xl-size | --size-5xl |
| --heading-mobile-l-size | --size-4xl |
| --heading-mobile-m-size | --size-3xl |
| --heading-mobile-s-size | --size-2xl |
| --heading-mobile-xs-size | --size-xl |

### Label

| **Token** | **Referència** |
|---|---|
| --label-family | --family-primary |
| --label-l-regular-weight | --weight-regular |
| --label-l-semibold-weight | --weight-semibold |
| --label-l-size | --size-l |
| --label-m-regular-weight | --weight-regular |
| --label-m-semibold-weight | --weight-semibold |
| --label-m-size | --size-m |
| --label-s-regular-weight | --weight-regular |
| --label-s-semibold-weight | --weight-semibold |
| --label-s-size | --size-s |
| --label-xs-semibold-weight | --weight-semibold |
| --label-xs-size | --size-xs |

## Mides resoltes dels estils (resolució derivada de les referències de la font)

Les mides següents no figuren com a taula a la pàgina: s'obtenen resolent cada token `--*-size` cap a la primitiva `--size-*` i el valor d'aquesta primitiva al mode Gencat (Open Sans) o Loteries de Catalunya (FS Pimlico).

| Token | Referència | Mida Gencat | Mida Loteries |
|---|---|---|---|
| --body-l-size | --size-xl | 20px | 24px |
| --body-m-size | --size-m | 16px | 18px |
| --body-s-size | --size-s | 14px | 16px |
| --display-desktop-m-size | --size-8xl | 56px | 60px |
| --display-mobile-m-size | --size-7xl | 48px | 56px |
| --heading-desktop-xl-size | --size-7xl | 48px | 56px |
| --heading-desktop-l-size | --size-6xl | 40px | 48px |
| --heading-desktop-m-size | --size-4xl | 32px | 36px |
| --heading-desktop-s-size | --size-3xl | 28px | 32px |
| --heading-desktop-xs-size | --size-2xl | 24px | 28px |
| --heading-mobile-xl-size | --size-5xl | 36px | 40px |
| --heading-mobile-l-size | --size-4xl | 32px | 36px |
| --heading-mobile-m-size | --size-3xl | 28px | 32px |
| --heading-mobile-s-size | --size-2xl | 24px | 28px |
| --heading-mobile-xs-size | --size-xl | 20px | 24px |
| --label-l-size | --size-l | 18px | 20px |
| --label-m-size | --size-m | 16px | 18px |
| --label-s-size | --size-s | 14px | 16px |
| --label-xs-size | --size-xs | 12px | 14px |

Equivalència entre els estils de Figma i els tokens: Display MD = `display-*-m`; Heading XL/LG/MD/SM/XS = `heading-*-xl|l|m|s|xs`; Body LG/MD/SM = `body-l|m|s`; Label LG/MD/SM/XS = `label-l|m|s|xs`.

- L'interlineat només el dona la font per al cos de text: 150% en totes les variants de Body (versió 1.1.1). La font no indica l'interlineat dels estils de visualització, encapçalament ni etiquetes.
- Espaiat entre paràgrafs del cos: `--body-l-paragraph-spacing` = `--spacing-16` (16px), `--body-m-paragraph-spacing` = `--spacing-12` (12px), `--body-s-paragraph-spacing` = `--spacing-8` (8px).
- Pesos: encapçalament = `--heading-weight` (semibold, 600); visualització = `--display-weight` (regular, 400); cos i etiquetes tenen regular, semibold i, només al cos, bold.

> [discrepància: l'historial (versió 2.0.0, 05 desembre 2025) diu que el Heading XL passa de 48 a 40 px i el Heading L de 40 a 36 px a escriptori; els tokens `--heading-desktop-xl-size` i `--heading-desktop-l-size` apunten a `--size-7xl` (48px) i `--size-6xl` (40px)] [a verificar]. La versió 5.0.0 de Loteries està datada "29 maig, 2025" a la font, anterior a la versió 2.0.0 de desembre de 2025 [a verificar].

## Versions

### Versions

| **Versió Figma** | **Versió Github** | **Data** | **Descripció** |
|---|---|---|---|
| 5.0.0 | 2.1.0 | 29 maig, 2025 | **Disseny**: Creació del mode de tipografia per Loteries (Primitives) amb la tipografia FS Pimlico. |
| 2.0.0 | 2.1.0 | 05 desembre, 2025 | **Disseny: **Es modifica la mida del Heading XL (de 48 a 40 px) i del Heading L (de 40 a 36 px) per Desktop. |
| 1.1.1 | 2.1.0 | 14 novembre, 2025 | **Disseny: **Es corregeix l’interlineat del Body, es posa a 150% en totes les seves versions. |
| 1.0.0 | 2.1.0 | 12 setembre, 2025 | **Disseny**: Es creen les variables de tipografia i s’enllacen amb els corresponents estils. |
| Traspàs a nova llibreria |  |  |  |
| 6.0.0 | 2.1.0 | 08 juliol 2025 | **Disseny**: s'afegeixen els estils bold per a body large, medium i small. |
| 3.0.0 | 2.1.0 | 31 març. 2025 | **Disseny i documentació**: Modificacions de les mides dels Headings. |
| 1.0.0 | 0.0.3 | 1 novembre, 2024 | **Disseny**, **desenvolupament** i **documentació** del fonament |
