# Elevacions (Elevations)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/5436d0 · Font actualitzada el 2026-01-20 · Extret el 2026-10-28

## Introducció
***Elevations***
Les elevacions s'utilitzen per a elevar visualment els elements principals respecte dels secundaris, amb la finalitat de guiar la interacció i ressaltar els elements més importants d'una interfície.

## Ús genèric

### Descripció i ús
L'elevació es defineix com la distància relativa entre dues superfícies al llarg de l'eix z. Fem servir l'elevació per representar visualment aquesta distància mitjançant diversos tipus d'ombra, que s'apliquen a diferents estats d'objectes interactius. Les ombres no només afegeixen profunditat, sinó que també ajuden a destacar elements clau de la pàgina en contrast amb els secundaris, orientant així la interacció de l'usuari i ressaltant els components més rellevants de la interfície.

#### Definir contenidors i jerarquia
Les ombres separen els elements del fons, millorant la jerarquització dels continguts i la comprensió de la informació.  /  / Casos d’ús:
- **Targetes i panells:** Utilitza l'elevació per diferenciar targetes o panells d'informació del fons o d'altres elements a la pàgina. Això és especialment útil en dissenys que presenten contingut agrupat, com ara quadres de comandament o canals de notícies.
- **Barres de navegació i aplicacions:** En aplicacions i llocs web, les barres de navegació i d'eines o capçaleres poden tenir elevacions per destacar la seva importància i posició constant a la jerarquia de navegació.

#### Indicar interactivitat
Els elements interactius, com ara botons o targetes, poden utilitzar elevacions per indicar que es poden fer clic. L'ombra fa que aquests elements flotin sobre la resta de la interfície, convidant a la interacció.
/ Casos d’ús:
- **Botons i controls interactius**: Aplica una elevació subtil a botons per indicar la seva capacitat d'interacció i augmenta la seva elevació en passar el cursor sobre ells o en fer clic, per proporcionar retroacció visual.

#### Organitzar capes
Les elevacions poden ajudar a organitzar visualment el contingut en capes, facilitant la comprensió de l'estructura de la informació i com interactuen els diferents elements i seccions de contingut.
/ Casos d’ús:
- **Menús i finestres modals: **Els menús desplegables, les finestres modals i els diàlegs de confirmació han de tenir elevacions per indicar que es troben per sobre d'altres elements de la interfície, ajudant a focalitzar l'atenció de l'usuari en l'acció o la informació presentada.

### Tipologia
Figma: Level 2 (Level 2) ; Level 3 (Level 3) ; Level 1 (Level 1)

### Bones pràctiques

#### Consistència
- **FER:** Es manté un sistema d'elevació consistent en tota la interfície, definint regles clares sobre quants nivells d'elevació utilitzar i en quins contextos.
- **NO FER:** No es manté un sistema d'elevació consistent en tota la interfície. 

#### Adequació
- **FER:** Utilitza les ombres amb una altura i una difusió adequades en funció de la grandària i la importància de l'element. Els elements més grans o més rellevants poden requerir ombres més pronunciades.
- **NO FER:** No utilitzis les ombres amb una altura i una difusió sense tenir en compte la grandària o importància de l'element.

#### Direcció
- **FER:** Es manté una direcció coherent per a les ombres dins de la interfície, per a evitar incoherències visuals. 
- **NO FER:** No es manté una direcció coherent per a les ombres dins de la interfície, per a evitar incoherències visuals. 

#### Subtilesa
- **FER:** Utilitza elevacions subtils i que no distreuen del contingut principal. L'objectiu és millorar la usabilitat i l'estètica, no sobrecarregar visualment la interfície.
- **NO FER:** No utilitzis elevacions prominents i que distreuen del contingut principal.

## Primitives
> En el cas de les elevacions, si està permès utilitzar les primitives directament.

### Elevations

| **Primitiva** | **Valor** |
|---|---|
| --elevations-level-1 | 0px 4px 30px 0px rgba(102, 102, 102, 0.1) |
| --elevations-level-2 | 0px 1px 4px 0px rgba(0, 0, 0, 0.15) |
| --elevations-level-3 | 0px 4px 16px 1px rgba(51, 51, 51, 0.2) |

## Versions

### Versions

| **Versió Figma** | **Versió Github** | **Data** | **Descripció** |
|---|---|---|---|
| 2.0.0 | 3.0.0 | 05 desmebre, 2025 | **Disseny**: S’afegeix l’elevació de nivell 4. |
| Traspàs a nova llibreria |  |  |  |
| 5.0.0 | 3.0.0 | 10 juny, 2025 | **Disseny**: es modifica l'elevació de nivell 01. |
| 4.0.0 | 3.0.0 | 2 maig, 2025 | **Disseny: **Es reordenen les elevacions per ordre ascendent.  / Level 1 =  Level 2 / Level 2 = Level 3 / Level 3 = Level 1 |
| 3.0.0 | 2.0.0 | 28 abril, 2025 | **Disseny:** s'afegeix el nivell 3. |
| 1.0.0 | 0.0.3 | 1 novembre, 2024 | **Disseny**, **desenvolupament** i **documentació** del fonament |

> Nota: l'historial menciona que s'afegeix l'elevació de nivell 4 (versió Figma 2.0.0, 05 desembre 2025), però la pestanya Primitives només llista `--elevations-level-1`, `--elevations-level-2` i `--elevations-level-3`. [a verificar]
