# Guia de colors (Color palette)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/09b729 · Font actualitzada el 2026-07-20 · Extret el 2026-10-28

## Introducció
***Color palette***
Per garantir interfícies digitals coherents i atractives a tota la Generalitat, sigui en aplicacions o altres experiències, és fonamental disposar d'una guia detallada sobre l'ús del color. Els conceptes següents estableixen les bases per aconseguir l'equilibri i l'harmonia en el disseny de les nostres interfícies d'usuari.
***Avís: està pendent de fer evolutius a desenvolupament***

## Disseny

### *Marca *(*brand*)
Aquest color s’utilitza predominantment en elements interactius com botons, pestanyes actives i altres components que requereixen una acció o destaquen dins la interfície. La seva aplicació reforça la identitat visual de la marca i contribueix a una experiència d’usuari coherent i reconeixible. A més, facilita la navegació i la comprensió de l’estat dels elements, millorant l’accessibilitat i la usabilitat del producte digital.
[Tokens] color.brand.primary.500

### *Neutre (neutral)*
Per a cos de text, etiquetes i components en estat en passar el cursor (hover) amb algunes excepcions (enllaços, fils d'Ariadna). També s'utilitza en components en estat seleccionat en el qual el color primari pot portar problemes a causa de la seva semblança amb el color d'error (caselles de selecció, botons d'opció).
[Tokens] color.neutral.700

### Sentit dels colors
Els colors s’apliquen amb criteri i sentit, tenint en compte tant la semàntica com la jerarquia visual. Més enllà del color principal de marca, que s’utilitza per destacar elements interactius, la paleta incorpora colors funcionals que comuniquen estats específics de manera clara i accessible: /
- **Vermell**: Indica errors, advertències crítiques o accions fallides. S’utilitza per alertar l’usuari de manera immediata.
- **Verd**: Representa estats positius, èxit en accions o confirmacions. Transmet seguretat i validació.
- **Taronja**: S’empra per alertes o avisos que requereixen atenció però no són crítiques.
- **Blau**: S’associa a informació complementària, suggeriments o estats neutrals que no impliquen acció immediata.
- **Blau elèctric:** Indica l’estat de focus en camps, botons o components interactius, reforçant la percepció d’interactivitat i guiant l’usuari en el flux d’acció.
- **Lila (color alternatiu):** S’utilitza per estats visitats, etiquetes que poden indicar novetat i el botó de sortida ràpida, aportant diferenciació sense competir amb el color principal.
- **Paleta vermells pastels i grisos: **per a il·lustracions.
Aquest sistema cromàtic contribueix a una experiència d’usuari intuïtiva, coherent i alineada amb les bones pràctiques d’accessibilitat i disseny inclusiu.

### *Opacitat*
Alguns components, com les modals o els diàlegs emergents, requereixen enfosquir el contingut subjacent per centrar l’atenció de l’usuari en l’element actiu. Per garantir consistència i accessibilitat, aquests components han d’aplicar una opacitat definida en el sistema de disseny: /
- Color base: #333333
- Opacitat: 25%
Aquesta capa semitransparent crea un efecte de bloqueig visual sense eliminar completament la percepció del context, mantenint una experiència clara i ordenada. L’ús d’aquesta opacitat està normalitzat per assegurar coherència en totes les interfícies i evitar variacions que puguin afectar la llegibilitat o la jerarquia visual.

### Colors sobre diferents fons
Alguns components o textos poden aparèixer sobre fons foscos, com per exemple els enllaços situats al footer o botons en seccions amb contrast elevat. Per garantir la llegibilitat i la coherència visual, el sistema de disseny defineix tokens específics per a aquests casos, que inclouen l’etiqueta -darkbackground-. Exemple:
/  content-buttons-secondary-darkbackground-default
/  Aquests tokens asseguren que els estils aplicats (colors, contrast i estats) compleixin els criteris d’accessibilitat i mantinguin la identitat visual en entorns amb fons foscos. L’ús d’aquesta convenció evita inconsistències i facilita la implementació en diferents components del producte.

### Jerarquia
La jerarquia de color de 70-20-10 estableix un balanç visual en assignar 70% de l’espai al color dominant, 20% al secundari, i 10% a un color d’accent. Aquest enfocament assegura cohesió i atractiu visual, destacant elements clau sense sobrecarregar l'usuari. El color d'accent, aplicat estratègicament, guia l'atenció cap a crides a l'acció o àrees importants, millorant l'experiència de l'usuari i la navegabilitat del lloc.

### Bones pràctiques
- **FER:** Se segueixen les pautes marcades en els fonaments.
- **NO FER:** No se segueixen les pautes marcades en els fonaments.
- **FER:** Es respecten els criteris d’accessibilitat.
- **NO FER:** No es respecten els criteris d'accessibilitat.

## Primitives
> Les primitives són variables de color de base del sistema de disseny i no s'han d'utilitzar ni modificar directament.

### Gencat

#### *Marca (brand)*

| **Primitiva** | **Valor hexadecimal** | **Valor rgb** |
|---|---|---|
| --color-brand-secondary-50 | #f9e5e5 | rgb(249, 229, 229) |
| --color-brand-secondary-100 | #f2cccc | rgb(242, 204, 204) |
| --color-brand-primary-300 | #d96666 | rgb(217, 102, 102) |
| --color-brand-primary-500 | valor canònic a [foundations.md](foundations.md) | rgb(192, 0, 0) |
| --color-brand-primary-600 | #900000 | rgb(144, 0, 0) |
| --color-brand-primary-700 | #660000 | rgb(102, 0, 0) |

#### *Neutre (neutral)*

| **Primitiva** | **Valor hexadecimal** | **Valor rgb** |
|---|---|---|
| --color-neutral-100 | #f5f5f5 | rgb(245, 245, 245) |
| --color-neutral-200 | #f2f2f2 | rgb(242, 242, 242) |
| --color-neutral-300 | #dddddd | rgb(221, 221, 221) |
| --color-neutral-400 | #939393 | rgb(147, 147, 147) |
| --color-neutral-500 | #6e6e6e | rgb(110, 110, 110) |
| --color-neutral-700 | #333333 | rgb(51, 51, 51) |

#### Base

| **Primitiva** | **Valor hexadecimal** | **Valor rgb** |
|---|---|---|
| --color-base-black | #000000 | rgb(0, 0, 0) |
| --color-base-white | #ffffff | rgb(255, 255, 255) |

#### *Informatiu (informative)*

| **Primitiva** | **Valor hexadecimal** | **Valor rgb** |
|---|---|---|
| --color-informative-300 | #ecf9fb | rgb(236, 249, 251) |
| --color-informative-500 | #c8e5f8 | rgb(200, 229, 248) |
| --color-informative-700 | #006db5 | rgb(0, 109, 181) |

#### *Positiu (positive)*

| **Primitiva** | **Valor hexadecimal** | **Valor rgb** |
|---|---|---|
| --color-positive-300 | #eaf9ea | rgb(234, 249, 234) |
| --color-positive-500 | #c4e4c4 | rgb(196, 228, 196) |
| --color-positive-700 | #3f7200 | rgb(63, 114, 0) |

#### *Alerta (alert)*

| **Primitiva** | **Valor hexadecimal** | **Valor rgb** |
|---|---|---|
| --color-alert-300 | #fff5e1 | rgb(255, 245, 225) |
| --color-alert-500 | #fbe4bc | rgb(251, 228, 188) |
| --color-alert-700 | #bc5000 | rgb(188, 80, 0) |

#### Error

| **Primitiva** | **Valor hexadecimal** | **Valor rgb** |
|---|---|---|
| --color-error-300 | #fbeeed | rgb(251, 238, 237) |
| --color-error-500 | #f5b4b4 | rgb(245, 180, 180) |
| --color-error-700 | #dd0404 | rgb(221, 4, 4) |

#### Focus

| **Primitiva** | **Valor hexadecimal** | **Valor rgb** |
|---|---|---|
| --color-focus-500 | #2c93f2 | rgb(44, 147, 242) |

#### *Alternatiu (alternative)*

| **Primitiva** | **Valor hexadecimal** | **Valor rgb** |
|---|---|---|
| --color-alternative-300 | #dcc0f8 | rgb(220, 192, 248) |
| --color-alternative-500 | #a36fb4 | rgb(163, 111, 180) |
| --color-alternative-700 | #7320c2 | rgb(115, 32, 194) |

### ATC
> Els únics colors que varien respecte gencat són els de marca. Pots consultar la resta en les taules superiors.

#### *Marca (brand)*

| **Primitiva** | **Valor hexadecimal** | **Valor rgb** |
|---|---|---|
| --color-brand-secondary-50 | #ebf6ff | rgb(235, 246, 255) |
| --color-brand-secondary-100 | #cce3f4 | rgb(204, 227, 224) |
| --color-brand-secondary-300 | #76a8cc | rgb(118, 168, 204) |
| --color-brand-primary-500 | #a81a8d | rgb(168, 26, 141) |
| --color-brand-primary-600 | #80146c | rgb(128, 20, 108) |
| --color-brand-primary-700 | #550c47 | rgb(85, 12, 71) |

### GAIP
> Els únics colors que varien respecte gencat són els de marca. Pots consultar la resta en les taules superiors.

#### *Marca (brand)*

| **Primitiva** | **Valor hexadecimal** | **Valor rgb** |
|---|---|---|
| --color-brand-secondary-50 | #e5f1f3 | rgb(229, 241, 243) |
| --color-brand-secondary-100 | #a6ced6 | rgb(166, 206, 214) |
| --color-brand-secondary-300 | #4d9faf | rgb(77, 159, 175) |
| --color-brand-primary-500 | [discrepància: la font escriu el hex de la marca Gencat; el valor rgb correspon a #00768c] | rgb(0, 118, 140) |
| --color-brand-primary-600 | #005665 | rgb(0, 86, 101) |
| --color-brand-primary-700 | #0d2326 | rgb(13, 35, 38) |

### Loteries
> Els únics colors de primitives que varien respecte gencat són els de marca i els neutrals. Pots consultar la resta en les taules superiors. A nivell de tokens hi ha algunes variacions per components específics. Consulta la pestanya de tokens per veure més informació.

#### *Marca (Brand)*

| **Primitiva** | **Valor hexadecimal** | **Valor rgb** |
|---|---|---|
| --color-brand-secondary-50 | #deafc | rgb(222, 234, 252) |
| --color-brand-secondary-100 | #c6d9f5 | rgb(196, 217, 245) |
| --color-brand-secondary-300 | #627fb9 | rgb(98, 127, 185) |
| --color-brand-primary-500 | #017939 | rgb(1, 121, 57) |
| --color-brand-primary-600 | #005C2b | rgb(0, 92, 43) |
| --color-brand-primary-700 | #003c1c | rgb(0, 60, 28) |

#### *Neutre (Neutral)*

| **Primitiva** | **Valor hexadecimal** | **Valor rgb** |
|---|---|---|
| --color-neutral-100 | #f5f5f5 | rgb(247, 250, 253) |
| --color-neutral-200 | #f2f2f2 | rgb(238, 245, 255) |
| --color-neutral-300 | #e4eefd | rgb(228, 238, 253) |
| --color-neutral-400 | #7994C9 | rgb(121, 148, 201) |
| --color-neutral-500 | #5a72a3 | rgb(90, 114, 163) |
| --color-neutral-700 | #173571 | rgb(23, 53, 113) |

### Infraestructures
> Els únics colors que varien respecte gencat són els de marca i el neutral 400. Pots consultar la resta en les taules superiors.

#### *Marca (brand)*

| **Primitiva** | **Valor hexadecimal** | **Valor rgb** |
|---|---|---|
| --color-brand-secondary-50 | #ebf8e2 | rgb(235, 248, 226) |
| --color-brand-secondary-100 | #ceeeb8 | rgb(206, 238, 184) |
| --color-brand-secondary-300 | #5eac28 | rgb(94, 172, 40) |
| --color-brand-primary-500 | #48841e | rgb(72, 132, 30) |
| --color-brand-primary-600 | #2D5213 | rgb(45, 82, 19) |
| --color-brand-primary-700 | #1d350c | rgb(29, 53, 12) |

#### *Neutre (Neutral)*

| **Primitiva** | **Valor hexadecimal** | **Valor rgb** |
|---|---|---|
| --color-neutral-400 | #9a9a9a | rgb(154, 154, 154) |

/

## Tokens

### Tokens
A continuació es mostren els tokens de color del sistema de disseny disponibles a la llibreria.
Utilitza els tipus següents segons el cas d'ús:
- ***Fons***** (*****background*****)**: per a colors de fons.
- ***Vora *****(*****border*****)**: per a vores.
- ***Contingut***** (*****content*****)**: per a text i icones.
> Gencat, ATC i GAIP mantenen una equivalència en tots els tokens, però en el cas de Loteries existeixen algunes exepcions en components específics.

#### *General*

##### *Fons (background)*

| **Token** | **Referència** |
|---|---|
| --background-accent-darkbackground-default | --color-brand-secondary-50 |
| --background-accent-default | --color-brand-primary-500 |
| --background-accent-pressed | --color-brand-primary-700 |
| --background-alert-primary | --color-alert-300 |
| --background-alert-secondary | --color-alert-500 |
| --background-alert-tertiary | --color-alert-700 |
| --background-alternative-primary | --color-alternative-300 |
| --background-alternative-tertiary | --color-alternative-500 |
| --background-alternative-secondary | --color-alternative-700 |
| --background-baner-primary | --color-brand-secondary-50 |
| --background-buttons-primary-colorbackground-default | --background-tertiary |
| --background-buttons-primary-colorbackground-hover | --background-secondary-hover |
| --background-buttons-primary-darkbackground-default | --background-primary |
| --background-buttons-primary-darkbackground-hover | --background-secondary-hover |
| --background-buttons-primary-darkbackground-pressed | --background-secondary-darkbackground |
| --background-buttons-primary-default | --background-accent-default |
| --background-buttons-primary-hover | --background-tertiary |
| --background-buttons-primary-pressed | --background-accent-pressed |
| --background-buttons-tertiary-darkbackground-hover | --background-secondary-hover |
| --background-buttons-tertiary-hover | --background-primary-hover |
| --background-decorative | --color-neutral-200 |
| --background-disabled | --color-neutral-100 |
| --background-error-primary | --color-error-300 |
| --background-error-secondary | --color-error-500 |
| --background-error-tertiary | --color-error-700 |
| --background-herobanner-primary | --color-brand-secondary-50 |
| --background-highlitedlink-primary | --color-brand-secondary-50 |
| --background-information-primary | --color-informative-300 |
| --background-information-secondary | --color-informative-500 |
| --background-information-tertiary | --color-informative-700 |
| --background-inputs-default | --background-primary |
| --background-inputs-disabled | --background-disabled |
| --background-inputs-selected | --background-tertiary |
| --background-inputs-selected-hover | --background-tertiary |
| --background-neutral | --color-neutral-300 |
| --background-primary | --color-base-white |
| --background-primary-hover | --color-neutral-100 |
| --background-secondary | --color-neutral-400 |
| --background-secondary-darkbackground | --color-neutral-500 |
| --background-secondary-hover | --color-neutral-300 |
| --background-subheader-primary | --background-decorative |
| --background-success-primary | --color-positive-300 |
| --background-success-secondary | --color-positive-500 |
| --background-success-tertiary | --color-positive-700 |
| --background-tertiary | --color-neutral-700 |
| --background-tertiary-opacity-25 | --color-neutral-700-25 |

##### *Vora (border)*

| **Token** | **Referència** |
|---|---|
| --border-accent-primary-default | --color-brand-primary-500 |
| --border-accent-primary-pressed | --color-brand-priimary-700 |
| --border-accent-secondary | --color-brand-primary-600 |
| --border-alert | --color-alert-700 |
| --border-buttons-secondary-colobackground | --border-primary |
| --border-buttons-secondary-darkbackground-default | --border-primary-darkbackground-default |
| --border-buttons-secondary-default | --border-accent-primary-default |
| --border-buttons-secondary-hover | --border-primary |
| --border-buttons-secondary-pressed | --border-accent-primary-pressed |
| --border-disabled | --color-neutral-400 |
| --border-disabled-on-content | --color-base-white |
| --border-dividers-primary | --border-tertiary |
| --border-dividers-secondary | --border-secondary |
| --border-error | --color-error-700 |
| --border-focus | --color-focus-500 |
| --border-informative | --color-informative-700 |
| --border-inputs-primary-default | --border-secondary |
| --border-inputs-primary-disabled | --border-tertiary |
| --border-inputs-primary-hover | --border-primary |
| --border-inputs-primary-pressed | --border-accent-primary-pressed |
| --border-inputs-primary-selected | --border-primary |
| --border-links-primary-darkbackground-default | --border-primary-darkbackground-default |
| --border-links-primary-default | --border-primary |
| --border-links-primary-hover | --border-accent-secondary |
| --border-links-primary-pressed | --border-accent-primary-pressed |
| --border-links-primary-visited | --border-visited |
| --border-not-available | --color-neutral-500 |
| --border-primary | --color-neutral-700 |
| --border-primary-darkbackground-default | --color-base-white |
| --border-secondary | --color-neutral-400 |
| --border-succes | --color-positive-700 |
| --border-tertiary | --color-neutral-300 |
| --border-visited | --color-alternative-700 |

##### *Contingut (content)*

| **Token** | **Referència** |
|---|---|
| --content-accent-primary-default | --color-brand-primary-500 |
| --content-accent-primary-pressed | --color-brand-primary-700 |
| --content-accent-secondary | --color-brand-primary-600 |
| --content-alert | --color-alert-700 |
| --content-buttons-primary-darkbackground-default | --content-primary-default |
| --content-buttons-primary-default | --content-tertiary-default |
| --content-buttons-secondary-darkbackground-default | --content-primary-darkbackgroiund-default |
| --content-buttons-secondary-default | --content-accent-primary-default |
| --content-buttons-secondary-hover | --content-primary-default |
| --content-buttons-secondary-pressed | --content-accent-primary-pressed |
| --content-disabled | --color-neutral-400 |
| --content-error | --color-error-700 |
| --content-hover | --color-neutral-700 |
| --content-illustration-decorative-primary | --color-neutral-200 |
| --content-illustration-decorative-secondary | --color-neutral-300 |
| --content-illustration-primary | --color-brand-secondary-300 |
| --content-illustration-secondary | --color-brand-secondary-100 |
| --content-illustration-tertiary | --color-brand-secondary-50 |
| --content-illustration-white | --color-base-white |
| --content-informative | --color-informative-700 |
| --content-links-primary-darkbackground-default | --content-primary-darkbackgroiund-default |
| --content-links-primary-default | --content-primary-default |
| --content-links-primary-hover | --content-accent-secondary |
| --content-links-primary-pressed | --content-links-primary-pressed |
| --content-links-primary-visited | --content-visited |
| --content-primary-darkbackgroiund-default | --color-base-white |
| --content-primary-default | --color-neutral-700 |
| --content-secondary-darkbackground-default | --color-neutral-400 |
| --content-secondary-default | --color-neutral-500 |
| --content-succes | --color-positive-700 |
| --content-tertiary-darkbackground-default | --color-neutral-300 |
| --content-tertiary-default | --color-base-white |
| --content-texts-body | --content-primary-default |
| --content-texts-label-darkbackground-primary-default | --content-links-primary-darkbackground-default |
| --content-texts-label-primary-defualt | --content-primary-default |
| --content-texts-label-secondary-default | --content-secondary-default |
| --content-texts-title | --content-primary-default |
| --content-visited | --color-alternative-700 |

#### Loteries
A continuació es mostren els tokens específics que es modifiquen per Loteries.

##### *Fons (background)*

| **Token** | **Referència** |
|---|---|
| --background-banner-primary | --color-neutral-200 |
| --background-herobanner-primary | --color-neutral-200 |
| --background-highlitedlink-primary | --color-neutral-200 |
| --background-subheader-primary | --color-neutral-200 |

##### *Vora (border)*

| **Token** | **Referència** |
|---|---|
| --border-links-primary | -border-accent-primary-default |

##### *Contingut (content)*

| **Token** | **Referència** |
|---|---|
| --content-links-primary | -content-accent-primary-default |

### Usos

#### Marca

| **Color** | **Ús** |
|---|---|
| 50 | Fons decoratius. |
| 100 | Elements decoratius com il·lustracions |
| 300 | Elements decoratius com il·lustracions |
| 500 | Color primari. Usat en botons *default* (*per defecte)* i alguns elements com les pestanyes en estat seleccionat. |
| 600 | Per als estats *hover* (en passar el cursor). |
| 700 | Per als estats *pressed* (*actiu)*. |

#### Neutral

| **Color** | **Ús** |
|---|---|
| neutral-100 |  |
| neutral-200 | Per a fons en elements que no necessitin passar criteris d’accessibilitat. S'utilitza com a fons en estats en passar el cursor (*hover)*, però mai com a únic element. |
| neutral-300 | Per a fons en elements que no necessitin passar criteris d’accessibilitat. S'utilitza com a fons en estats en passar el cursor (*hover)* sobre fons fosc, però mai com a únic element. |
| neutral-400 | Per a elements gràfics com separadors, línies i altres elements. |
| neutral-500 | Per a texts secundaris. |
| neutral-700 | Per a cos de text, etiquetes i components en estat en passar el cursor (*hover)* amb algunes excepcions (enllaços, fils d'Ariadna). També s'utilitza en components en estat seleccionat en el qual el color primari pot portar problemes a causa de la seva semblança amb el color d'error (caselles de selecció, botons d'opció). |

#### Informatiu

| **Color** | **Ús** |
|---|---|
| informative-300 | Fons d’elements informatius. |
| informative-500 | Fons d'elements que indiquen algun estat. |
| informative-700 | Elements gràfics d’elements informatius. |

#### Positiu

| **Color** | **Ús** |
|---|---|
| positive-300 | Fons d’elements que indiquen èxit. |
| positive-500 | Fons d'elements que indiquen algun estat. |
| positive-700 | Elements gràfics d’elements que indiquen èxit. |

#### Alerta

| **Color** | **Ús** |
|---|---|
| alert-300 | Fons d’elements que indiquen alerta. |
| alert-500 | Fons d'elements que indiquen algun estat. |
| alert-700 | Elements gràfics d’elements que indiquen alerta. |

#### Error

| **Color** | **Ús** |
|---|---|
| error-300 | Fons d’elements que indiquen error. |
| error-500 | Fons d'elements que indiquen algun estat. |
| error-700 | Elements gràfics que indiquen error. |

#### Alternatiu

| **Color** | **Ús** |
|---|---|
| alternative-300 | Fons d'elements com etiquetes. |
| alternative-500 | Fons d'elements que indiquen algun estat. |
| alternative-700 | Per a enllaços visitats i altres elements que requereixin un color diferenciat del de marca. |

#### Focus

| **Color** | **Ús** |
|---|---|
| focus-500 | Focus |

## Accessibilitat

### Accessibilitat segons UNE-EN 301549:2022 - WCAG 2.2
Els criteris d’accessibilitat que ha de passar qualsevol web del servei públic ve determinat per segons la Norma Europea d'Accessibilitat per a Productes i Serveis de Tecnologies de la Informació i Comunicació (TIC) V3.2.1 (2021-03). En espanyol **UNE-EN 301549:2022.** Aquesta fa referència a les directrius marcades per la WCAG 2.2.
En relació amb el contrast de color de text sobre fons de color i/o imatges, complim amb la següent especificació:
**1.4.3 Contrast (Mínim)**: La presentació visual de text i imatges de text té una relació de contrast d'almenys 4.5: 1, tret de les següents excepcions pròpies del nivell AA:
- **Text gran:** El text a gran escala i les imatges de text a gran escala tenen una relació de contrast d'almenys 3: 1. El text gran ha de tenir almenys una mida de 18.66 px en cos *Bold* o una mida igual o superior a 24px.
- **Incidental:** El text o imatges de text que formen part d'un component de la interfície d'usuari inactiu, que són pura decoració, que no són visibles per a ningú o que formen part d'una imatge que conté un altre contingut visual significatiu, no tenen requisits de contrast.
- **Logotips:** El text que forma part d'un logotip o marca no té un requisit mínim de contrast.
> **Contrast de color: **pots veure en més detall aquesta comparació dins la llibreria del sistema de disseny.
Figma: Taula comparativa - accessibilitat (Colors/Fonaments/ Colors-accessibilitat/Taula comparativa - accessibilitat)

## Versions

### Versions

| **Versió Figma** | **Versió Github** | **Data** | **Descripció** |
|---|---|---|---|
| 6.0.1 | 2.0.0 | 10 juliol, 2026 | **Disseny**: - Creació del mode de color per Infraestructures (Primitives i Tokens). |
| 5.0.0 | 2.0.0 | 29 maig, 2026 | **Disseny**: - Creació del mode de color per Loteries (Primitives i Tokens). |
| 4.0.0 | 2.0.0 | 8 maig, 2026 | **Disseny**: - Creació del mode de color per GAIP. |
| 3.0.0 | 2.0.0 | 17 abril, 2026 | **Disseny**: - Separació del color de marca en primari i secundari. - Creació del mode ATC. |
| 2.0.0 | 2.0.0 | 05 desembre, 2025 | **Disseny**: - Es modifica el color del focus perquè passi contrast de 3:1 sobre el background decorative i el background accent. / - S’intercanvien els noms dels colors alternatius 500 i 300 per alinear-los amb la resta de colors. |
| 1.1.1 | 2.0.0 | 14 novembre, 2025 | **Disseny**: Es vinculen tokens de color del background input i del border links als tokens generals corresponetns. |
| Traspàs a nova llibreria |  |  |  |
| 8.1.0 | 2.0.0 | 6 octubre, 2025 | **Disseny**: Es modifiquen alguns noms de variables i s’eliminen duplicitats, per tal de simplificar i donar més sentit a les nomenclatures. |
| 5.0.0 | 2.0.0 | 10 juny, 2025 | **Disseny**: S’afegeixen els nous colors primaris 50 i 200. |
| 2.4.0 | 2.0.0 | 10 març, 2025 | **Disseny**: S'afegeix el color per overlay. |
| 2.3.0 | 2.0.0 | 7 març, 2025 | **Desenvolupament**: es modifica el color-grey-100. |
| 2.2.0 | 0.1.1 | 20 gener, 2025 | **Disseny:** Nous colors primaris 100 i 300. Nou color gris decoratiu. |
| 1.0.0 | 0.0.3 | 1 novembre, 2024 | **Disseny**, **desenvolupament** i **documentació** del fonament |


## Notes de fidelitat i discrepàncies detectades a la font

- Els noms dels tokens es reprodueixen verbatim, incloent-hi errates de la font: `--color-brand-priimary-700` (a `--border-accent-primary-pressed`), `--content-primary-darkbackgroiund-default` (nom i referències), `--border-buttons-secondary-colobackground`, `--content-texts-label-primary-defualt`, `--border-succes` / `--content-succes` (sense doble s), `--background-baner-primary` (general) enfront de `--background-banner-primary` (Loteries), i les referències `-border-accent-primary-default` / `-content-accent-primary-default` (amb un sol guió) de Loteries. [a verificar] quin és el nom oficial.
- `--content-links-primary-pressed` apunta a ella mateixa (`--content-links-primary-pressed`) a la font. [a verificar]
- `--background-tertiary-opacity-25` referencia `--color-neutral-700-25`, que no apareix a cap taula de primitives; per la secció Opacitat correspon a la primitiva neutral 700 al 25% d'opacitat.
- Primitives Gencat: hi ha `--color-brand-primary-300`, però no `--color-brand-secondary-300`, que sí que apareix a la resta de modes (ATC, GAIP, Loteries, Infraestructures) i que els tokens `--content-illustration-primary` referencien. [a verificar]
- Les primitives de la pestanya amb valors incoherents entre hex i rgb a la font (ATC secondary-100, GAIP primary-500, Loteries secondary-50, neutral-100 i neutral-200) estan resoltes a `foundations.md`.
- La taula de tokens ordena `--background-alternative-tertiary` (alternative-500) abans de `--background-alternative-secondary` (alternative-700): es manté l'ordre i la referència de la font.
- La pestanya Accessibilitat cita la Norma Europea EN 301 549 versió V3.2.1 (2021-03) i, en castellà, UNE-EN 301549:2022.
