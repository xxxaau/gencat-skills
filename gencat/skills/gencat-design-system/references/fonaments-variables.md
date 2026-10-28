# Variables (Tokens)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/63a481 · Font actualitzada el 2026-09-09 · Extret el 2026-10-28

## Introducció
***Tokens***
El sistema de disseny està creat a partir de variables que recullen una peça d’informació com un color, mida, espaiat, etc. Cada variable disposa d’un nom per identificar-la.

## Què són les variables?

### Què són les variables?
Les variables fan referència a valors que es poden utilitzar per definir estils en un sistema de disseny o en un projecte. Aquestes variables ajuden a estandarditzar i centralitzar elements del disseny, com ara colors, espaiats, i altres atributs visuals, assegurant consistència i facilitant el manteniment del disseny. També ajuden a realitzar canvis globals ràpidament. Cadascun d’aquestes variables tenen un nom associat.

### Organització

#### Primitives
Les variables primitives són aquelles que recullen els valors de color i espaiat utilitzats en el sistema de disseny de forma general. Serveixen per crear els conceptes semàntics i no s’aplicaran mai directament sobre un element del sistema de disseny. Aquí s’inclou els colors de la marca i possibles submarques.
Figma: TokensPrimitius  (08. Tokens/SD-Corner_radius/Frame 1000001233/Frame 1000001296/Frame 1000001302/Fonaments/TokensPrimitius)

#### Semàntiques
Les variables semàntiques estan creades a partir de les primitives. Fan referència a elements d’un component com el fons (*background), *la vora *(border), *el contingut* (content),* etc. Cadascuna d’elles aplica únicament a les característiques a les quals fa referència. Per exemple, els fons* s'*apliquen a les formes* (shapes)* i als marcs (*frames)* o les vores (*borders)* a les traces (*stroke)*. Una variable semàntica es pot aplicar a diferents components.
Figma: TokensSemantics  (08. Tokens/SD-Corner_radius/Frame 1000001233/Frame 1000001296/Frame 1000001302/Fonaments/TokensSemantics)

#### Específiques
Són aquelles variables que apliquen a un component específic. Es troben dins la mateixa secció que les semàntiques, però en un nivell inferior. Es formen a partir de les semàntiques i apliquen a aquell element pel qual fa referència.
Figma: TokensPEspecífics  (08. Tokens/SD-Corner_radius/Frame 1000001233/Frame 1000001296/Frame 1000001295/Frame 1000001302/Fonaments/TokensPEspecífics)

### Aplicació al disseny
Per conèixer com s'han aplicat aquestes variables als diferents elements i components del SD consulteu la secció de Figma on es parla de [llibreries](figma-llibreries.md).

## Disseny

### Disseny
El sistema de disseny recull diferents **modes** en funció de la marca a aplicar. Aquests modes modifiquen els fonaments per adaptar-los a l'estil visual de la marca escollida. Actualment el SD cobreix les necessitats de:
- gencat
- ATC (Agència Tributària de Catalunya)
- GAIP (comissió de Garantia al dret d'Accés de la Informació Pública)

#### Com aplicar els diferents modes a Figma
Per utilitzar els modes de les diferents marques, caldrà, primer de tot, que estigueu utilitzant les últimes versions de les llibreries. Si no treballeu dins l'espai de Figma de la Generalitat, les podeu descarregar des de la pàgina [d'actualitzacions](versions-actualitzacions.md).
Un cop estigueu utilitzant les llibreries més actuals, haureu de seguir aquests passos:
1. Crear un frame per al teu disseny.
Figma: Aplicar diferents modes a figma 01 (Variables/SD-Corner_radius/Frame 1000001233/Aplicar diferents modes a figma 01)
2. Introduir un component o element que tingui aplicades les variables de fonaments del SD.
Figma: Aplicar diferents modes a figma 02 (Variables/SD-Corner_radius/Frame 1000001233/Aplicar diferents modes a figma 02)
3. Amb el frame seleccionat anar al menú lateral, a la secció "Aparença" i seleccionar el botó "Aplica mode de variable".
Figma: Aplicar diferents modes a figma 3 (Variables/SD-Corner_radius/Frame 1000001233/Aplicar diferents modes a figma 3)
4. Seleccionar el mode que us interessi (gencat, ATC, GAIP). El canvi s'hauria de fer automàticament i es veurien les modificacions aplicades a tots els components i elements amb variables enllaçades.
Figma: Aplicar diferents modes a figma 4 -GAIP (Variables/SD-Corner_radius/Frame 1000001233/Aplicar diferents modes a figma 4 -GAIP) ; Aplicar diferents modes a figma 4 -ATC (Variables/SD-Corner_radius/Frame 1000001233/Aplicar diferents modes a figma 4 -ATC)
Figma: Aplicar diferents modes a figma 5 - GAIP (Variables/SD-Corner_radius/Frame 1000001233/Aplicar diferents modes a figma 5 - GAIP) ; Aplicar diferents modes a figma 5 - ATC (Variables/SD-Corner_radius/Frame 1000001233/Aplicar diferents modes a figma 5 - ATC)

## Desenvolupament

### Desenvolupament
El sistema de disseny recull diferents **modes** en funció de la marca a aplicar. Aquests modes modifiquen els fonaments per adaptar-los a l'estil visual de la marca escollida. Actualment el SD cobreix les necessitats de:
- gencat
- ATC (Agència Tributària de Catalunya)
- GAIP (comissió de Garantia al dret d'Accés de la Informació Pública)
- Loteries de Catalunya
- Infraestructures

#### Com aplicar els diferents modes al teu projecte
El tema per defecte és **gencat**, per la qual cosa no cal especificar-lo per utilitzar-lo. Si voleu aplicar qualsevol dels altres dos temes, només heu d'afegir l'atribut `data-theme` a l'etiqueta `<html>` del vostre document amb el valor corresponent:
- Per ATC: `data-theme="atc"`

```html
<!-- /index.html -->
<html dir="ltr" lang="en" data-theme="atc">
```
- Per GAIP: `data-theme="gaip"`

```html
<!-- /index.html -->
<html dir="ltr" lang="en" data-theme="gaip">
```
- Per Loteries de Catalunya: `data-theme="loteries"`

```html
<!-- /index.html -->
<html dir="ltr" lang="en" data-theme="loteries">
```
- Per Infraestructures: `data-theme="infraestructures"`

```html
<!-- /index.html -->
<html dir="ltr" lang="en" data-theme="infraestructures">
```

> Nota: la pestanya Disseny cobreix els modes gencat, ATC i GAIP, mentre que la pestanya Desenvolupament cobreix també Loteries de Catalunya i Infraestructures. La pestanya Desenvolupament parla de "qualsevol dels altres dos temes" tot i llistar quatre temes alternatius a `data-theme`. Vegeu les primitives de cada mode a [Guia de colors](fonaments-guia-de-colors.md) i [Fonaments canònics](foundations.md).
