# Espaiat (Layout / Spacing)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/27e32c · Font actualitzada el 2025-10-28 · Extret el 2026-10-28

## Introducció
***Layout***
L'espaiat garanteix uniformitat i un ritme visual consistent en tot el disseny, des de l'interlineat tipogràfic i la mida de les icones fins als marges interns dels components.

## Ùs genèric

### Descripció i ús
El nostre sistema de disseny adopta una escala basada en múltiples de quatre i vuit píxels. Aquesta estructura garanteix uniformitat i un ritme visual consistent en tot el disseny, des de l'interlineat tipogràfic i la mida de les icones fins als marges interns dels components. Aquest enfocament assegura espaiats coherents, tant en els elements individuals del sistema com en les disposicions generals dels components.

#### Quan s'utilitza

##### Per millorar la llegibilitat
L'espaiat adequat entre elements de text (com paràgrafs, línies i lletres) milloren la llegibilitat, fent que el contingut sigui més fàcil de seguir i entendre.
**Per crear jerarquia visual**
Els espais poden ser usats per indicar la importància relativa de diferents elements a la pantalla, guiant l'atenció de l'usuari a àrees clau.
**Per organitzar el contingut**
En separar clarament grups d'elements o seccions de contingut a través dels espaiats adequats a la interfície facilita l'accés a la informació i millora la navegabilitat.
**Per millorar l’estètica i confort vidual**
Els espais creen dissenys agradables i confortables per a l'usuari.
**Per facilitar la interacció**
L'espai adequat al voltant d'elements interactius, com botons i enllaços, asseguren una millor experiència d'usuari, especialment en dispositius tàctils on la mida de l'àrea tocable és crítica.

### Valors d'espaiat

| **Valors primitius** | **Rem** | **Tokens mida** (`--size-x*`, vegeu [Iconografia](fonaments-iconografia.md)) | **Disposició de tokens** (`--layout-*`) |
|---|---|---|---|
| 0 px | x0 |  | Sí |
| 2 px | x0,125 |  |  |
| 4 px | x0,25 | Sí | Sí |
| 8 px | x0,5 | Sí | Sí |
| 12 px | x0,75 | Sí | Sí |
| 16 px | x1 | Sí | Sí |
| 20 px | x1,25 | Sí |  |
| 24 px | x1,5 | Sí | Sí |
| 32 px | x2 | Sí | Sí |
| 40 px | x2,5 | Sí | Sí |
| 48 px | x3 | Sí | Sí |
| 56 px | x3,5 | Sí | Sí |
| 64 px | x4 | Sí | Sí |
| 72 px | x4,5 |  |  |
| 80 px | x5 | Sí | Sí |
| 88 px | x5,5 |  |  |
| 96 px | x6 |  |  |
| 128 px | x8 |  | Sí |

## Primitives
> Les primitives són variables base del sistema de disseny i no han de ser utilitzades ni modificades directament.

### Spacing

| **Primitiva ** | **Valor** |
|---|---|
| --spacing-0 | 0px |
| --spacing-2 | 2px |
| --spacing-4 | 4px |
| --spacing-8 | 8px |
| --spacing-12 | 12px |
| --spacing-16 | 16px |
| --spacing-20 | 20px |
| --spacing-24 | 24px |
| --spacing-32 | 32px |
| --spacing-40 | 40px |
| --spacing-48 | 48px |
| --spacing-56 | 56px |
| --spacing-64 | 64px |
| --spacing-72 | 72px |
| --spacing-80 | 80px |
| --spacing-88 | 88px |
| --spacing-96 | 96px |
| --spacing-128 | 128px |

## Tokens

### Layout

| **Token** | **Valor** |
|---|---|
| --layout-none | --spacing-0 |
| --layout-x0-175 | --spacing-2 |
| --layout-x0-25 | --spacing-4 |
| --layout-x0-5 | --spacing-8 |
| --layout-x0-75 | --spacing-12 |
| --layout-x1 | --spacing-16 |
| --layout-x1-5 | --spacing-24 |
| --layout-x2 | --spacing-32 |
| --layout-x2-5 | --spacing-40 |
| --layout-x3 | --spacing-48 |
| --layout-x3-5 | --spacing-56 |
| --layout-x4 | --spacing-64 |
| --layout-x5 | --spacing-80 |
| --layout-x8 | --spacing-128 |

## Versions

### Versions

| **Versió Figma** | **Versió Github** | **Data** | **Descripció** |
|---|---|---|---|
| 2.2.0 | 0.1.1 | 20 de gener, 2025 | Sense canvis |
| 2.1.0 | 0.1.1 | 04 desembre, 2024 | Sense canvis |
| 2.0.0 | 0.1.0 | 02 desembre, 2024 | **Disseny**: S’afegeix la mida Extra small per a mides d’icones. |
| 1.1.0 | 0.0.4 | 22 novembre, 2024 | Sense canvis |
| 1.0.0 | 0.0.3 | 1 novembre, 2024 | **Disseny, desenvolupament** i **documentació** del fonament |

> Nota: a la taula de valors, 2 px no marca cap casella de token, però existeixen `--layout-x0-175` i `--size-x0-175` (→ `--spacing-2`); i 72 px i 128 px tenen `--size-x4-5` / `--size-x8`. [discrepància: taula del lloc vs. taules de tokens] [a verificar]
