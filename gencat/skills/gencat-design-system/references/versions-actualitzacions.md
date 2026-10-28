# Actualitzacions del Sistema de Disseny (registre de versions i estat)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/70697a · Font actualitzada el 2026-10-26 · Extret el 2026-10-28

Registre de versions i estat dels fonaments i components del Sistema de Disseny de la Generalitat de Catalunya. Pensat per comparar-lo amb el lloc i detectar què ha canviat. La pàgina de la font té tres pestanyes: General (pròximament i estat), Disseny (llibreries Figma i historial de disseny) i Desenvolupament (repositori de codi i historial de desenvolupament). Descripció de la font: "Coneix les darreres característiques afegides i canvis realitzats en el sistema de disseny." Mantenir un registre de versions permet conèixer les darreres característiques afegides, les correccions d'errors i els canvis significatius, amb transparència i traçabilitat.

## Versió actual de cada llibreria o paquet

Llibreries de Figma (adjunts de la pestanya Disseny):

| Llibreria / paquet | Versió | Data | Mida |
|---|---|---|---|
| SDGC - Llibreria v.12.6.0 (components core) | 12.6.0 | 26 Oct, 2026 (fitxer); publicació 22/10/2026 | 63.2MB |
| SDGC - Fonaments V.6.2.1 | 6.2.1 | 2 Oct, 2026 (fitxer); publicació 02/10/2026 | 33.6MB |
| SDGC - Llibreria de components conversacionals 5.1.0 | 5.1.0 | 23 Sep, 2026 (fitxer); darrera publicació 19/06/2026 | 15.7MB |
| SDGC - Exemples d'ús | v.4.0.0 | 29/05/2026 (darrera publicació a l'historial) | - |

Repositori de codi (pestanya Desenvolupament, repositori de GitHub: https://ctti.ghe.com/ctti-dev/3693.00-sdc-eixam-library):

| Concepte | Valor | Data |
|---|---|---|
| Darrera versió publicada | 12.1.2 | 05/10/2026 |
| Versions en manteniment | 12.1.0 i 12.1.2 | - |
| Documentació d'antigues versions (PDF) | documentation-v12.0.0.pdf | 14 Jul, 2026 |

Paquets del monorepositori (des de la 8.0.0, 14/11/2025): components core `@ctti-dev/gencat-core` i components conversacionals `@ctti-dev/gencat-conversational`.

> Nota: a partir de la versió 12.0.0 cal que els usuaris de la llibreria afegeixin als seus projectes el fitxer `gencat.css`. Cal seguir els passos de la configuració del framework que s'usi (secció Desenvolupament del lloc).

## Adjunts citats

| Adjunt | Data | Mida | Pestanya / secció |
|---|---|---|---|
| SDGC - Llibreria de components conversacionals 5.1.0.fig | 23 Sep, 2026 | 15.7MB | Disseny / Llibreries de Figma |
| SDGC - Fonaments V.6.2.1.fig | 2 Oct, 2026 | 33.6MB | Disseny / Llibreries de Figma |
| SDGC - Llibreria v.12.6.0.fig | 26 Oct, 2026 | 63.2MB | Disseny / Llibreries de Figma |
| documentation-v12.0.0.pdf | 14 Jul, 2026 | 3.4MB | Desenvolupament / Versionat històric de la llibreria |


## Pròximament

Pròximament en disseny:
- Nous patrons de BO
- Evolutiu de bàner
- Ajustaments de components

Pròximament en desenvolupament:
- Fonts de coneixement
- Specs per agents IA
- Correccions de bugs

## Estat dels fonaments i components

Legenda d'estats (a la font apareix com a icona):

| Estat | Definició |
|---|---|
| Nou | Nou |
| Evolutiu | Evolutiu |
| Ajustament | Ajustament |
| Disponible | Disponible |
| En procés | En procés |
| Pendent | Pendent |
| - | No aplica |

Quan l'estat va seguit d'una versió (p. ex. "Ajustament 11.0.0"), sembla la versió de la llibreria en què es va produir i el text després del guió la novetat [a verificar: la font no ho defineix].

### Fonaments

| Fonaments | Disseny | Desenvolupament |
|---|---|---|
| Marca | Disponible | Nou 11.0.0 - logo Loteries de Catalunya |
| Tipografia | Disponible | Disponible |
| Guia de Colors | Disponible | Nou 11.0.0 - mode Loteries de Catalunya |
| Iconografia | Ajustament 5.0.1 - S'ajusta icona stop | Disponible |
| Il·lustracions | Disponible | Disponible |
| Imatge | Disponible | - |
| Elevacions | Disponible | Disponible |
| Punt de tall i quadrícules | Disponible | Disponible |
| Espaiat | Disponible | Disponible |
| Arrodoniment | Disponible | Disponible |
| Tokens | Disponible | Nou 11.0.0 - variables Loteries de Catalunya |
| Comunicació clara | Disponible | - |
| Conversacional | Disponible | - |
| Gràfics, mapes, diagrames i quadres de comandament | Disponible | - |

### Components core

| Components core | Disseny | Desenvolupament |
|---|---|---|
| Arbre de continguts | Disponible | Disponible |
| Àrea de text | Disponible | Disponible |
| Acordió | Disponible | Disponible |
| Avisos | Disponible | Disponible |
| Bàner | Disponible | Ajustament 11.0.0 |
| Bàner d'atenció | Disponible | Ajustament 11.0.0 |
| Barra de progrés | Disponible | Disponible |
| Barra de pestanyes | Disponible | Evolutiu 11.0.0 |
| Botó d'opció | Disponible | Disponible |
| Botó Tornar amunt | Disponible | Disponible |
| Botons | Disponible | Ajustament 11.0.0 - Botó desplegable |
| Calendari | Disponible | Disponible |
| Camp d'entrada | Disponible | Disponible |
| Camp de cerca | Disponible | Ajustament 11.0.0 |
| Capçalera per aplicacions internes | Disponible | Disponible |
| Capçalera web pública | Disponible | Evolutiu 11.0.0 |
| Capçalera secundària | Disponible | Ajustament 11.0.0 |
| Capçalera secundària BO | Disponible | Disponible |
| Carregador d'arxius | Ajustament 12.1.0 | Disponible |
| Caselles de selecció | Disponible | Disponible |
| Commutador | Disponible | Disponible |
| Control de rang | Disponible | Disponible |
| Control segmentat | Disponible | Disponible |
| Dades destacades | Disponible | Disponible |
| Dades estructurades | Disponible | Disponible |
| Descripció emergent | Disponible | Evolutiu 11.0.0 |
| Desplegable | Disponible | Evolutiu 11.0.0 |
| Divisor | Disponible | Disponible |
| Enllaços | Disponible | Disponible |
| Etiquetes | Disponible | Disponible |
| Esquelet | Disponible | - |
| Estat buit | Disponible | Disponible |
| Fils d'Ariadna | Disponible | Disponible |
| Filtres | Disponible | Disponible |
| Glossari | Disponible | Disponible |
| Grup de botons | Disponible | Ajustament 11.0.0 |
| Imatge avançada | Disponible | Ajustament 11.0.0 |
| Indicador de càrrega | Disponible | Disponible |
| Indicador de funció | Disponible | Disponible |
| Insígnia | Disponible | Disponible |
| Línia de temps | Disponible | Ajustament 11.0.0 |
| Llista | Disponible | Disponible |
| Llista d'enllaços | Disponible | Ajustament 11.0.0 |
| Llistat de resultats | Disponible | Disponible |
| Menú desplegable | Ajustament 12.1.0 | Disponible |
| Menú lateral | Disponible | Ajustament 11.0.0 |
| Menú horitzontal | Disponible | Disponible |
| Modals | Disponible | Ajustament 11.0.0 |
| Mostra més | Disponible | Disponible |
| Notificació emergent | Disponible | Ajustament 11.0.0 |
| Paginació | Disponible | Ajustament 11.0.0 |
| Panell destacat | Disponible | Ajustament 11.0.0 |
| Panell emergent | Disponible | Ajustament 11.0.0 |
| Pas a pas | Disponible | Ajustament 11.0.0 |
| Pestanyes | Disponible | Ajustament 11.0.0 |
| Peu de pàgina | Disponible | Disponible |
| Rastrejador d'estat | Disponible | Disponible |
| Reproductor de vídeo i àudio | Disponible | Ajustament 11.0.0 |
| Selector de data | Disponible | Disponible |
| Taula de continguts | Disponible | Disponible |
| Taules dinàmiques | Disponible | Ajustament 11.0.0 |
| Targetes | Disponible | Disponible |
| Text destacat | Disponible | Disponible |
| Visor de mapa | Ajustament 12.1.0 | Ajustament 11.0.0 - POI |
| Visor de notícies | Disponible | Ajustament 11.0.0 |
| Xips | Disponible | Disponible |
| Patrons (subgrup) | | |
| Arbre de decisions | Disponible | - |
| Botó compartir | Disponible | - |
| Emergències | Evolutiu 12.1.0 | - |
| Introducció de dades | Disponible | - |
| Introducció guiada | Disponible | - |
| Notificacions | Nou 12.1.0 | - |
| Pàgines d'error i manteniment | Disponible | - |
| Saltar al contingut principal | Disponible | - |
| Sortida ràpida | Disponible | - |
| Selector d'hora | Disponible | - |

### Components conversacionals

| Components conversacionals | Disseny | Desenvolupament |
|---|---|---|
| Avatar | Disponible | Disponible |
| Botó de tornar a baix | Disponible | Disponible |
| Botó de xat | Disponible | Disponible |
| Camp d'entrada de xat | Evolutiu 5.1.0 | Ajustament 11.0.0 |
| Capçalera de xat | Disponible | Ajustament 11.0.0 |
| Capçalera secundària de xat | Disponible | Disponible |
| Contenidor de xat flotant | Disponible | Ajustament 11.0.0 |
| Fonts de coneixement | Nou 5.1.0 | Pendent |
| Missatge de xat | Disponible | Disponible |
| Suggeriments | Disponible | Evolutiu 11.0.0 |
| Patrons (subgrup) | | |
| Interacció veu a text | Nou 5.1.0 | - |
| Xat a pantalla completa | Disponible | - |
| Xat flotant | Disponible | - |
| Xat lateral | Disponible | - |

### Exemples d'ús

| Exemples d'ús | Disseny |
|---|---|
| Pàgina de formulari | Disponible |
| Pàgina de continguts | Disponible |
| Cercador | Disponible |
| Àrea privada | Disponible |
| Gestió interna | Disponible |
| Xat conversacional | Disponible |

Enllaços de suport de la pàgina: secció de suport (https://zeroheight.com/38669693e/p/57c57a-suport-i-contacte), preguntes freqüents (https://zeroheight.com/38669693e/p/72240b-preguntes-frequents), fer una sol·licitud (https://zeroheight.com/38669693e/p/690b45) i guies d'ús (https://zeroheight.com/38669693e/p/342611). Per sol·licitar un nou component, modificar-ne un d'existent o resoldre dubtes d'ús.

## Historial de versions de disseny (Figma)

Cada entrada: data de publicació, llibreries/versions publicades i canvis (categoria: components afectats). Format de data de la font (DD/MM/AAAA; algunes files antigues DD/MM/AA).

### 22/10/2026 - SDGC - Llibreria de components core v.12.6.0

**Llibreria de components core v.12.6.0**
- Nou component: Etiquetatge d'IA
- Ajustaments: Etiquetes

### 02/10/2026 - SDGC - Llibreria de components core v.12.5.0

**Llibreria de components core v.12.5.0**
- Evolutius: Reproductor de vídeo i àudio
- Ajustaments: Estat buit; Enllaços

### 02/10/2026 - SDGC - Fonaments v.6.2.1

**Llibreria de fonaments v.6.2.1**
- Nova iconografia: Iconografia - Icones per adelantar o retrocedir 10 segons una reproducció

### 09/09/2026 - SDGC - Llibreria de components core v.12.4.0

**Llibreria de components core v.12.4.0**
- Evolutius: Botons; Etiquetes
- Ajustaments: Barra de pestanyes; Capçalera d’aplicació interna

### 09/09/2026 - SDGC - Fonaments v.6.1.1

**Llibreria de fonaments v.6.1.1**
- Nova iconografia: Iconografia - Icona per arrossegar i reordenar elements verticalment

### 31/07/2026 - SDGC - Llibreria de components core v.12.3.0

**Llibreria de components core v.12.3.0**
- Nous components: Campanya
- Ajustaments: Visor de notícies; Modal; Capçalera aplicació interna; Panell destacat; Botó tornar amunt; Botons; Enllaços

### 10/07/2026 - SDGC - Fonaments v.6.0.1; SDGC - Llibreria de components core v.12.2.0

**Llibreria de fonaments v.6.0.1**
- Nova iconografia: Iconografia - Icona de cap persona
- Nous fonaments: Colors - Infraestructures
**Llibreria de components core v.12.2.0**
- Evolutius: Capçalera per aplicacions internes; Visor de mapa; Pestanyes
- Ajustaments: Barra de pestanyes; Menú horitzontal; Menú desplegabe; Desplegable; Menú lateral; Botó d'opció; Fils d'ariadna; Camp de cerca; Capçalera web pública; Línia de temps; Paginació

### 19/06/2026 - SDGC - Fonaments v.5.0.1; SDGC - Llibreria de components core v.12.1.0; SDGC - Llibreria de components conversacionals v.5.1.0

**Llibreria de fonaments v.5.0.1**
- Ajustaments: Iconografia - Icona de stop
**Llibreria de components core v.12.1.0**
- Nous patrons: Notificacions
- Evolutius: Patró d'emergències
- Ajustaments: Carregador d'arxius, menú desplegable i visor de mapa
**Llibreria de components conversacionals v.5.1.0**
- Nous components: Fonts de coneixement
- Nous patrons: Interacció veu a text
- Evolutius: Camp d'entrada de xat

### 29/05/2026 - SDGC - Fonaments v.5.0.0; SDGC - Llibreria de components core v.12.0.0; SDGC - Llibreria de components conversacionals v.5.0.0; SDGC - Exemples d'ús v.4.0.0

**Llibreria de fonaments v.5.0.0**
- Nous fonaments: Marca - Loteries de Catalunya; Colors - Loteries de Catalunya; Tipografia - Loteries de Catalunya; Gràfics, diagrames, mapes i quadres de comandament
**Llibreria de components core v.12.0.0**
- S'afegeixen slots: Pestanyes; Barra de pestanyes; Carregador d'arxius; Menú horitzontal; Peu de pàgina; Taules dinàmiques
- Evolutius: Desplegable; Camp d'entrada; Camp de cerca; Bàner; Barra de pestanyes; Botons; Capçalera d'aplicació interna; Capçalera secundària; Capçalera de web pública; Descripció emergent; Enllaços; Llista d'enllaços; Panell destacat
- Ajustaments: Avisos; Selector de data; Botó d'opció avançat; Camp de cerca; Casella de selecció avançada; Panell emergent
- Nous patrons: Introducció de dades
**Llibreria de components conversacionals v.5.0.0**
- Evolutius: Suggeriments
**Exemples d'ús v.4.0.0**
- Nou exemple d'ús: Xat conversacional

### 08/05/2026 - SDGC - Fonaments v.4.0.0; SDGC - Llibreria de components core v.11.0.0; SDGC - Llibreria de components conversacionals v.4.0.0

**Llibreria de fonaments v.4.0.0**
- Nous fonaments: Iconografia; Variables
- Evolutius: Marca
**Llibreria de components core v.11.0.0**
- Nous components: Casella de selecció avançada; Botó d'opció avançat
- S'afegeixen slots: Llista; Llista d'enllaços; Taula de continguts; Llistat de resultats
- Evolutius: Capçalera de web pública; Camp d'entrada
- Ajustaments: Mostra més; Pestanyes; Taules dinàmiques; Bàner
- Nous patrons: Arbre de decisions; Introducció guiada
**Llibreria de components conversacionals v.4.0.0**
- Evolutius: Botó de xat

### 20/04/2026 - SDGC - Fonaments v.3.0.0; SDGC - Llibreria de components core v.10.0.0; SDGC - Llibreria de components conversacionals v.3.0.0

**Llibreria de fonaments v.3.0.0**
- Nous fonaments: Marca; Guia de colors; Iconografia; Il·lustracions
- Ajustaments: Marca
**Llibreria de components core v.10.0.0**
- Nous components: Llista avançada
- Evolutius: Capçalera de web pública; Desplegable; Menú horitzontal; Peu de pàgina; Camp d'entrada; Visor de mapa; Panell emergent; Modals; Menú desplegable; Filtres; Capçalera secundària BO; Grup de botons; Acordió
- Evolutius en patrons: Sortida ràpida
- Ajustaments: Commutador; Control de rang; Imatge avançada; Taules dinàmiques; Bàner; Àrea de text
**Llibreria de components conversacionals v.3.0.0**
- Nous components: Botó de xat lateral; Capçalera secundària de xat; Contenidor de xat lateral; Suggeriments
- Evolutius: Capçalera de xat
- Nous patrons: Xat lateral
- Evolutius en patrons: Xat flotant
- Ajustaments: Missatge de xat

### 20/03/2026 - SDGC - Llibreria de components v.9.1.0; SDGC - Llibreria de components conversacionals v.2.1.0

**Llibreria de components core v.9.1.0**
- Ajustaments: Camp d'entrada; POI; Àrea de text; Targetes; Notificació emergent; Línia de temps; Menú desplegable; Pestanyes avançades; Modal; Xips
**Llibreria de components conversacionals v.2.1.0**
- Nou patró:: Xat flotant
- Nou component: Contenidor de xat flotant
- Evolutius: Camp d’entrada de xat; Capçalera de xat; Missatge de xat; Botó tornar a baix
- Ajustaments: Missatge de xat; Botó tornar a baix

### 27/02/2026 - SDGC - Fonaments v.3.0.0; SDGC - Llibreria de components v.9.0.0; SDGC - Llibreria de components conversacionals v.2.0.0

**SDGC - Fonaments v.3.0.0**
- Nous fonaments: icones de Vimeo, Flickr i dibuixar àrea poligonal.
**SDGC - Llibreria de components v.9.0.0**
- Nous patrons: Selector d'hora
- Evolutius: Visor de mapa; Xips
- Ajustaments: Filtres; Enllaços; Llista; Commutador; Llista d’enllaços; Etiquetes; Carregador d’arxius; Taula de continguts; Àrea de text; Taules dinàmiques; Avisos; Modals; Pestanyes; Panell emergent; Menú desplegable; Capçalera de web pública; Peu de pàgina
**SDGC - Llibreria de components conversacionals v.2.0.0**
- Components nous: Botó de tornar a baix; Camp d'entrada de xat; Capçalera de xat
- Nou patrons: Xat a pantalla completa

### 09/02/2026 - SDGC - Fonaments v.2.0.0; SDGC - Llibreria de components v.8.6.0; SDGC - Llibreria de components conversacionals v.1.1.0; Exemples d'ús v.3.0.0

**Llibreria components v.8.6.0**
- Evolutius: Capçalera pública; Glossari
- Ajustaments: Panell emergent; Pestanyes; Modals; Menú desplegable; Peu de pàgina; Capçalera secundària; Descripció emergent; Estat buit; Llistat de resultats; Panell destacat; Rastrejador d’estat; Selector de data; Visor de notícies; Taules dinàmiques; Desplegable; Dades destacades; Bàner; Botó tornar amunt; Imatge avançada; Capçalera BO
**Llibreria components conversacionals v.1.1.0**
- Components nous: Missatge de xat
- Evolutius: Avatar

### 20/01/2026 - SDGC - Fonaments v.2.0.0; SDGC - Llibreria de components v.8.5.0; SDGC - Llibreria de components conversacionals v.1.0.0; Exemples d'ús v.3.0.0

- Evolutius: Capçalera web pública
- Ajustaments de components: Visor de notícies; Glossari; Capçalera secundaria; Capçalera web pública; Bàner; Botó d’opció; Casella de selecció; Desplegable; Paginació; Targetes; Avisos; Camp de cerca; Camp d’enrtada

### 05/12/25 - SDGC - Fonaments v.2.0.0; SDGC - Llibreria de components v.8.4.0; SDGC - Llibreria de components conversacionals v.1.0.0; Exemples d'ús v.3.0.0

**Fonaments v.2.0.0**
- Fonament nou: Conversacional; Elevació nivell 4
- Evolutius: Icona dibuixar en el mapa
- Ajustaments: Color focus; Tipografia
**Llibreria components v.8.4.0**
- Components nous: Glossari
- Evolutius: Capçalera secundària BO; Visor de mapa
- Ajustaments de components: Menú horitzontal; Capçalera secundària; Taules dinàmiques; Targetes; Camp de cerca; Descripció emergent; Visor de notícies; Desplegable; Control de rang; Carregador d'arxius; Barra de progrés
**Llibreria de components conversacionals v.1.0.0**
- Components nous: Avatar; Botó de xat

### 14/11/25 - SDGC - Fonaments v.1.1.1; SDGC - Llibreria de components v.8.3.0; Exemples d'ús v.3.0

**Llibreria components v.8.3.0**
- Components nous: Capçalera secundària BO
- Ajustaments de components: Dades estructurades; Descripció emergent; Camp d’entrada; Camp de cerca; Avisos; Barra pestanyes; Panell emergent; Botó d’opció; Control de rang; Capçalera d’aplicació interna
**Exemples d'ús v.3.0.0**
- Actualitzacions d'exemples d'ús

### 27/10/25 - SDGC - Fonaments v.1.1.1; SDGC - Llibreria de components v.8.2.0; Exemples d'ús v.2.0

**Llibreria fonaments v.1.1.1**
- Ajustaments: Es corregeix l'interlineat de la tipografia Body; Es corregeix la vinculació d'alguns tokens de color
**Llibreria components v.8.2.0**
- Evolutius: Visor mapa: POI actiu; Camp de cerca
- Ajustaments de components i patrons: Es corregeix la vinculació trencada de tokens tipogràfics en alguns components; Ajustament de màxims i mínims en alguns components

### 06/10/25 - SDGC - Fonaments v.1.1; SDGC - Llibreria de components v.8.1

**Llibreria fonaments v.1.1**
- Evolutius: Colors: 2 noves variables de color; Icones: 3 icones noves
**Llibreria components v.8.1**
- Nous components: Control de rang
- Nous patrons: Botó compartir; Botó saltar al contingut principal
- Evolutius: Visor mapa: POI actiu; Botó desplegable; Capçalera secundària; Xips; Camp d’entrada: camp numèric
- Ajustaments
- Sortida ràpida: Panell emergent; Taula de continguts; Targetes; Paginació; Llistat de resultats; Llista d’enllaços i avançada; Imatge avançada; Filtres; Enllaços destacats; Menú horitzontal; Panell destacat

### 12/09/25 - SDGC - Fonaments v.1; SDGC - Llibreria de components v.8

**Nova llibreria fonaments v.1**
- Evolutiu de fonaments: Marca; Il·lustracions
**Llibreria components v.8**
- Disseny de components nous: Visor de mapes
- Disseny de patrons nous: Pàgines d’error i manteniment
- Evolutius: Calendari; Selector de data; Targetes
- Ajustaments: Botons; Desplegable; Camp de cerca; Enllaços; Llista avançada d'enllaços; Imatge avançada; Línia de temps; Fil d’ariadna; Modals; Paginació; Notificació emergent; Selector de data; Visor de notícies; Taules dinàmiques; Capçalera secundària; Avisos

### 28/07/25 - 7.0.0

- Disseny de components nous: Capçalera web pública
- Evolutiu de fonaments: Iconografia
- Ajustament de components: Desplegable; Capçalera secundària; Etiquetes; Panell emergent; Menú horitzontal; Barra de pestanyes

### 08/07/2025 - 6.0.0

- Disseny de components nous: Control segmentat
- Evolutiu de fonaments: Iconografia; Il·lustracions; Tipografia
- Evolutiu de components: Botons; Camp de cerca; Casella de selecció; Desplegable; Insígnia; Panell destacat; Llistat de resultats
- Ajustament de components: Avisos; Calendari; Capçalera aplicació interna; Dades estructurades; Etiquetes; Imatge avançada; Menú desplegable; Notificació emergent; Paginació; Reproductor de vídeo i àudio; Targetes; Visor de notícies

### 10/06/2025 - 5.0.0

- Disseny de components nous: Arbre de continguts; Calendari; Grup de botons; Filtres; Panell emergent
- Evolutiu de fonaments: Guia de colors; Il·lustracions
- Evolutiu de components: Rastrejador d'estat; Xips
- Ajustament de components: Selector de data; Avisos; Modals; Menú desplegable

### 19/05/2025 - 4.1.0

- Disseny de components nous: Dades destacades; Esquelet; Estat buit; Línia de temps
- Evolutiu de fonaments: Il·lustracions
- Evolutiu de components: Llista
- Ajustament de fonaments: Il·lustracions; Iconografia
- Ajustament de components: Avisos; Capçalera secundària; Enllaços; Llista; Llista d'enllaços; Peu de pàgina

### 02/05/2025 - 4.0.0

- Disseny de components nous: Reproductor de vídeo i àudio; Peu de pàgina; Xips
- Evolutiu de components: Etiquetes; Targetes
- Evolutiu de fonaments: Iconografia; Imatge
- Ajustaments de fonaments: Il·lustracions; Elevacions
- Ajustaments de components: Acordió; Barra de pestanyes; Capçalera secundària; Descripció emergent; Imatge avançada; Llista; Menú horitzontal; Pestanyes; Taula de continguts; Taules dinàmiques

### 31/03/2025 - 3.0.0

- Disseny de fonaments nous: Color d'accent; Il·lustracions; Elevacions
- Disseny de components nous: Barra de pestanyes; Botó Tornar amunt; Llista d'enllaços
- Evolutiu de components: Tipografia; Taula de continguts; Acordió
- Ajustament de components: Targetes; Visor de notícies; Capçalera secundària; Carregador d'arxius; Camp d'entrada; Descripció emergent; Paginació; Modals; Taules dinàmiques

### 10/03/2025 - 2.4.0

- Disseny de components nous: Dades estructurades; Imatge avançada; Llistat de resultats; Taula de continguts; Text destacat; Visor de notícies
- Evolutiu de components: Capçalera secundària; Menú horitzontal; Menú lateral; Pestanyes
- Evolutiu de fonaments: Color
- Ajustament de components: Calendari; Enllaços; Paginació; Pas a pas; Taules dinàmiques; Camp de cerca; Menú desplegable; Capçalera per aplicacions internes; Targetes
- Ajustament de fonaments: Color

### 31/01/2025 - 2.3.0

- Disseny de components nous: Commutador
- Evolutiu de components: Taules dinàmiques
- Ajustament de components: Menú desplegable; Casella de selecció; Targetes; Menú horitzontal; Paginació
- Ajustament de fonaments: Marca

### 13/01/2025 - 2.2.0

- Disseny de fonaments nous: Il·lustracions; Imatge
- Disseny de components nous: Capçalera secundària; Panell destacat; Targetes
- Evolutiu de components: Botons: nova mida small.; Camp de cerca: nova mida small.
- Evolutiu de fonaments: Colors: creació del color primari 100 i 300 i el gris 100.
- Ajustament de components: Enllaços: adaptació a dues i tres línies.; Àrea de text: Modificació de la variant de mida del botó d’ajuda en la mida Small del component.
- Ajustament de fonaments: Iconografia: Creació de la versió small d'enllaç extern.

### 09/12/2024 - 2.1.0

- Disseny de components nous: Capçalera per aplicacions internes; Menú desplegable
- Evolutiu de components: Botons: nova mida small.; Camp de cerca: nova mida small.
- Ajustament de components: Acordió: espaiats i alineació.; Etiquetes: adaptació segons contingut.; Enllaços: alineació; Àrea de text: s'afegeix el botó d'ajuda per activar la descripció emergent.; Camp d'entrada: s'afegeix el botó d'ajuda per activar la descripció emergent.; Desplegable: s'afegeix el botó d'ajuda per activar la descripció emergent.; Carregador d'arxius: s'afegeix el botó d'ajuda per activar la descripció emergent. S'ajusten espaiats i s'afegeix poder seleccionar l'opció small des del component principal.; Menú lateral: alineació i jerarquia.
- Exemple d'ús: Exemples dús aplicant els components del sistema de disseny.

### 02/12/2024 - 2.0.0

- Evolutiu de fonaments: Iconografia: s'afegeix una nova mida Extra small.
- Ajustament de fonaments: Iconografia: correcció de les mides de les icones de termòmetre.; Punts de tall I quadrícules: actualització de marges i gutters.

### 22/11/2024 - 1.1.0

- Disseny i desenvolupament de components nous: Descripció emergent; Etiquetes; Modals; Mostrar més; Menú lateral
- Només disseny de components: Taules dinàmiques
- 6 colors nous en Fonaments
- Ajustos en llibreria de disseny
- Bugs resolts

### 01/11/2024 - 1.0.0

- Disseny i desenvolupament de 25 components

## Historial de versions de desenvolupament (repositori de codi)

Versions en manteniment: 12.1.0 i 12.1.2. Repositori: https://ctti.ghe.com/ctti-dev/3693.00-sdc-eixam-library. Cada entrada: data, versió, repositori (Core / Conversational / Global) i canvis.

### 12.1.2 - 05/10/2026

**Repositori Core**
- Correccions bugs: Botons; Selector de data; Targetes; Desplegable; Indicador de funció; Capçalera web pública; Campanya; Casella de selecció
- Millores d'accessibilitat en diversos components

### 12.1.1 - 11/09/2026

**Repositori Core**
- Correccions bugs: Targetes; Capçalera web pública; Paginació; Desplegable

### 12.1.0 - 07/09/2026

**Repositori Core**
- Correccions bugs: Capçalera web pública
- Evolutiu de components: Capçalera web pública; Selector de data; Carregador d'arxius; Taules dinàmiques; Menú horiztonal; Capçalera per aplicacions internes; Camp de cerca; Notificació emergent; Visor de mapa
- Global: Es crea un fitxer i18n que actua com a diccionari per permetre la modificació de textos no introduïts per prop en components a altres idiomes.; S'afegeix una nova icona.; S'ha afegit un tema per a infraestructures.

### 12.0.3 - 04/09/2026

**Repositori Core**
- Correccions bugs: Carregador d'arxius; Etiquetes; Menú desplegable; Desplegable; Casella de selecció; Taules dinàmiques; Selector de data; Camp d'entrada; Imatge avançada; Modals; Descripció emergent; Camp de cerca; Pestanya vertical; Botó desplegable

### 12.0.2 - 16/07/2026

**Repositori Core**
- Correccions bugs: Selector de data

### 12.0.1 - 14/07/2026

**Repositori Core**
- Correccions bugs: Calendari; Selector de data; Taules dinámiques; Botó d'opció; Fils d'Ariadna

### 12.0.0 - 10/07/2026

**Repositori Core**
- Evolutiu de components: Targetes; Selector de data
- Correccions bugs: Imatge avançada; Capçalera secundària de BO; Targetes; Xips; Selector de data; Menú desplegable; Taules dinàmiques; Filtres; Enllaços; Menú horitzontal; Modals; Visor de mapa; Llista; Descripció emergent; Botó d'opció; Barra de progrés; Llistat de resultats; Panell emergent; Dades estructurades; Bàner d'atenció; Commutador; Etiquetes; Desplegable; Notificació emergent; Capçalera web pública
**Repositori Conversational**
- Nous components: Fonts de coneixement
- Evolutiu de components: Suggeriments; Camp d'entrada de xat; Contenidor de xat
**Global**
- Reducció de mida de tots els components compilats. Per part de l'usuari cal afegir el fitxer gencat.css al vostre projecte. Consulta la documentació del teu framework per seguir els passos: Configuració del teu projecte

### 11.0.0 - 19/06/2026

**Repositori Core**
- Evolutiu de components: Barra de pestanyes; Descripció emergent; Desplegable; Camp d'entrada; Capçalera web pública
- Correccions bugs: Modals; Botó desplegable; Reproductor de vídeo i àudio; Visor de notícies; Pestanya vertical; Notificació emergent; Línia de temps; Barra de pestanyes vertical; Pas a pas; Bàner; Panell destacat; Llista d'enllaços; Capçalera secundària; Bàner d'atenció; Menú lateral; Descripció emergent; Panell emergent; Paginació; Visor de mapa; Camp d'entrada; Menú horitzontal; Imatge avançada; Taules dinàmiques; Grup de botons; Camp de cerca; Desplegable; Capçalera web pública
**Repositori Conversational**
- Evolutiu de components: Suggeriments
- Correccions bugs: Camp d'entrada de xat; Contenidor de xat flotant; Capçalera de xat
**Global**
- S'afegeixen els logos per a loteries
- S'afegeixen nous tokens i tema per a loteries, així com canvis en la generació de les variables css a partir de build-tokens.cjs
- S'elimina de fonts MaterialSymbolsOutlined-VariableFontFILL.ttf
- Creació de fitxer AGENTS.md amb regles per a agents IA

### 10.1.0 - 29/05/2026

**Repositori Core**
- Nous components: Casella de selecció avançada; Botó d'opció avançat
- Evolutiu de components: Carregador d'arxius; Panell destacat; Taules dinàmiques; Capçalera web pública; Botons
- Correccions bugs: Camp de cerca; Taules dinàmiques; Capçalera web pública; Bàner; Bàner d'atenció; Desplegable; Indicador de funció; Glossari; Botó desplegable; Selector de data; Camp d'entrada; Menú desplegable; Calendari; Xips; Pestanyes; Targetes; Etiquetes; Arbre de continguts
**Repositori Conversational**
- Evolutiu de components: Botó de xat lateral
- Correccions bugs: Camp d'entrada de xat; Contenidor de xat flotant
**Global SCSS**
- S'hi afegeixen els colors de marca i logos de gaip

### 10.0.0 - 08/05/2026

**Repositori Core**
- Evolutiu de components: Bàner; Bàner d'atenció; Camp d'entrada; Llista; Desplegable; Indicador de funció
- Correccions bugs: Modals; Capçalera per aplicacions internes; Capçalera web pública; Peu de pàgina; Selector de data; Menú horitzontal; Targetes; Imatge avançada; Commutador; Insígnia; Calendari; Taules dinàmiques
**Repositori Conversational**
- Nous components: Contenidor de xat lateral; Suggeriments
- Correccions bugs: Contenidor de xat flotant; Missatge de xat; Botó de xat
- Wrapper Angular: Es corregeix ruta incorrecta del defineCustomElement al wrapper de cada component
**Global CSS**
- S'hi inclou la importació de formularis de Bootstrap a _global.scss
- S'hi inclouen colors primaris i secundaris d'ATC, i canvien noms de variables brand primary i secondary
- S'hi afegeixen noves il·lustracions i una icona nova de mapes. També es fa reorganització de carpetes
- S'hi afegeixen logos de la Generalitat i d'ATC

### 9.4.0 - 17/04/2026

**Repositori Core**
- Evolutiu de components: Imatge avançada; Indicador de càrrega; Botons; Llista; Modals
- Correccions bugs: Selector de data; Botons; Capçalera secundària; Imatge avançada; Modals; Panell emergent; Menú desplegable; Línia de temps; Visor de mapa; Àrea de text; Xips; Notificació emergent; Botó d'opció; Acordió
**Repositori conversational**
- Nous components: Contenidor de xat flotant
- Evolutiu de components: Botó tornar a baix; Capçalera de xat; Missatge de xat; Avatar; Camp d'entrada de xat

### 9.3.0 - 20/03/2026

**Repositori core**
- Evolutiu de components: Taules dinàmiques
- Correccions bugs: Taules dinàmiques; Menú horitzontal; Àrea de text; Botons; Panell emergent; Barra de pestanyes; Selector de data; Indicador de funció; Peu de pàgina; Modals; Pestanyes verticals; Avisos; Taula de cotnginuts; Etiquetes
**Repositori conversational**
- Nous components: Camp d'entrada de xat; Capçalera de xat; Botó tornar a baix
- Evolutius: Missatge de xat
- Correccions bugs: Botó de xat; Missatge de xat

### 9.2.0 - 27/02/2026

**Repositori core**
- Evolutiu de components: Camp de cerca; Capçalera per aplicacions internes; Panell destacat; Menú desplegable; Capçalera web pública; Menú horitzontal; Camp d'entrada; Panell emergent; Carregador d'arxius; Enllaços; Avisos; Targetes; Estat buit; Llista d'enllaços; Llista; Visor de mapa; Llistat de resultats; Dades estructurades; Línia de temps; Notificació emergent
- Ajustaments de components: Taules dinàmiques; Paginació; Modals; Desplegable
- Ajustaments d'accessibilitat: Imatge avançada; Botó tornar amunt; Calendari; Visor de notícies; Estat buit; Glossari; Descripció emergent; Llistat de resultats; Capçalera secundària; Panell emergent; Pestanyes; Visor de notícies
**Repositori conversational**
- Evolutiu de components: Avatar
- Nous components: Missatge de xat

### 9.1.0 - 06/02/2026

**Repositori core**
- Evolutiu de components: Àrea de text; Desplegable; Camp d'entrada; Taules dinàmiques; Capçalera per aplicacions internes; Camp de cerca; Panell destacat
- Ajustaments de components: Casella de selecció; Botons; Desplegable; Taules dinàmiques; Glossari; Calendari; Commutador; Selector de data; Bàner; Targetes; Paginació; Avisos
- Ajustaments d'accessibilitat: Targetes; Selector de data; Desplegable; Estat buit; Carregador d'arxius; Filtres; Peu de pàgina; Panell destacat; Menú horitzontal; Dades destacades; Enllaços; Modals; Dades estructurades; Avisos; Llistat de resultats; Rastrejador d'estat; Commutador; Barra de pestanyes; Taula de continguts; Visor de notícies
- Wrapper d'Angular: Es genera un script per crear un wrapper Angular per a cada component.
- Documentació: Noves vies de configuració de projectes Angular per reduir mides de compilació en utilitzar la llibreria de components.

### 9.0.0 - 12/01/2026

**Ajustaments fonaments**
- Canvi de mida de diverses tipografies
- Dues icones noves pel repositori conversacional
- Icona nova per a visor de mapa
**Repositori core**
- Evolutiu de components: Visor de mapa
- Ajustaments de components: Carregador d'arxius; Taules dinàmiques; Targetes; Menú horitzontal; Capçalera secundària de BO; Visor de mapa; Indicador de funció
- Nous components: Glossari
**Repositori conversacional**
- Nous components: Avatar; Botó de xat

### 8.5.0 - 05/12/2025

- Wrapper d'Angular: S'han corregit les rutes incorrectes del fitxer proxies.ts referents al wrapper d'Angular i se n'ha redactat en documentació la guia d'utilització
- Nous components: Capçalera secundària de BO
- Evolutiu de components: Selector de data; Calendari; Botons; Desplegable; Carregador d'arxius; Camp d'entrada; Camp de cerca; Àrea de text; Taules dinàmiques
- Ajustaments de components: Descripció emergent; Botó Tornar amunt; Imatge avançada; Bàner; Etiquetes; Indicador de funció; Xips; Arbre de continguts; Visor de mapa; Menú desplegable

### 8.0.0 - 14/11/25

- Reorganització del repositori a monorepositori multipaquet: Paquet components core: @ctti-dev/gencat-core; Paquet components conversacional: @ctti-dev/gencat-conversational
- Fonaments: Correcció de tokens de color
- Nous components: Icona del POI
- Evolutiu de components: Capçalera de web pública; Menú horitzontal; Taules dinàmiques
- Ajustaments de components: Indicador de funció; POI; Targeta destacada; Barra de pestanyes; Xips; Imatge avançada; Descripció emergent; Menú desplegable; Capçalera de web pública; Pestanyes verticals; Fils d’Ariadna; Calendari; Visor de notícies; Selector de data; Targeta de navegació; Avisos; Panell emergent

### 7.0.0 - 24/10/2025

- Fonaments: S'afegeixen tres noves icones
- Nous components: Visor de mapa; Control de rang
- Evolutiu de components: Camp d' entrada; Pestanyes; Taules dinàmiques
- Ajustaments de components: Imatge avançada; Llista; Llistat de resultats; Camp de cerca; Botó desplegable; Àrea de text; Casella de selecció; Botó d'opció; Xips; Carregador d'arxius; Filtres; Rastrejador d'estat; Menú lateral; Fils d'Ariadna
- Nous assets: Exportació css variables
- Actualització de dependències: Stencil Angular Output Target a la versió 1.0.0, compatible amb versions d’Angular superiors a v.19.

### 6.2.1 - 03/10/2025

- Evolutiu de components: Targetes; Bàner; Fils d'Ariadna; Botons; Enllaços; Avisos; Arbre de continguts; Taules dinàmiques; Estat buit; Peu de pàgina; Capçalera web pública; Enllaç destacat; Menú horitzontal; Llista d'enllaços; Llista; Paginació; Llistat de resultats; Rastrejador d'estat; Dades estructurades; Línia de temps; Notificació emergent; Menú desplegable; Capçalera per aplicacions internes; Descripció emergent; Pestanyes; Reproductor de vídeo i àudio; Panell destacat
- Ajustaments de components: Desplegable; Calendari; Casella de selecció; Visor de notícies; Camp de cerca; Selector de data; Menú lateral; Xips; Capçalera secundària; Control segmentat; Barra de pestanyes

### 6.1.0 - 12/09/25

- Components nous: Pestanyes horitzontals
- Evolutiu de components: Capçalera web pública; Camp de cerca; Modals; Peu de pàgina; Taula de continguts; Avisos; Botó desplegable; Panell destacat; Descripció emergent; Panell emergent; Dades estructurades; Notificació emergent; Taules dinàmiques; Menú lateral; Menú horitzontal; Àrea de text; Capçalera d’aplicació interna; Commutador; Casella de selecció; Botó d’opció; Desplegable; Calendari; Selector de data; Pestanyes
- Ajustaments de components: Paginació; Capçalera web pública; Imatge avançada; Indicador de funció; Botó tornar amunt; Botons; Pestanyes verticals; Targetes de navegació bàsica i avançada; Xips; Dades destacades; Barra de pestanyes vertical; Línia de temps; Reproductor de vídeo i àudio
- Canvi de nomenclatura: Horizontal tabs --> tab-bar-horizontal; Tab bar --> tab-bar-vertical

### 6.0.1 - 28/07/25

- Components nous: Capçalera web pública
- Evolutiu de components: Desplegable; Casella de selecció; Taules dinàmiques; Botons; Camp de cerca; Panell destacat; Capçalera per aplicacions internes; Calendari; Menú horitzontal
- Ajustaments de components: Peu de pàgina; Arbre de continguts; Carregador d’arxius; Enllaços; Pestanyes; Llista d’enllaços; Llistat de resultats; Panell emergent; Dades estructurades; Taula de continguts; Etiquetes; Reproductor de vídeo i àudio; Paginació; Avisos; Imatge avançada; Fils d’Ariadna

### 6.0.0 - 03/07/2025

- Global CSS: Canvi color color-grey-500; Nou color color-grey-50; Noves elevacions; Mesures convertides de px a rem
- Components nous: Calendari; Botó desplegable; Filtres; Grup de botons; Panell emergent; Arbre de continguts
- Evolutius de components: Rastrejador d'estat; Xips
- Bugs majors de components solucionats: Modals; Casella de selecció; Desplegable; Descripció emergent; Camp d'entrada; Àrea de text; Carregador d'arxius
- Bugs menors de components solucionats: Imatge avançada; Targetes; Visor de notícies; Botons; Bàner; Enllaços; Indicador de funció; Selector de data; Botó d'opció; Menú desplegable; Camp de cerca; Indicador de càrrega; Avisos; Acordió; Pestanyes

### 5.0.0 - 09/06/2025

- Global CSS: Corregir tipografia Display; Organitzar carpeta Assets
- Components nous: Enllaç destacat; Dades estructurades; Estat buit; Reproductor de vídeo i àudio; Línia de temps; Targeta d'informació; Dades destacades
- Bugs de components solucionats: Enllaços; Paginació; Menú desplegable; Capçalera per aplicacions internes; Capçalera secundària; Selector de data; Llista; Llista d'enllaços; Avisos; Xips; Peu de pàgina; Taula de continguts; Camp de cerca; Desplegable; Acordió; Casella de selecció; Camp d'entrada; Botó d'opció; Àrea de text; Descripció emergent; Imatge avançada

### 4.0.1 - 19/05/2025

- Global CSS: Canvi color-grey-200Canvi color-grey-20; New colors: $color-accent-extra-light: #FEF9E7 and $color-accent-light: #FCF3CF; New spacing: $spacing-layout-x0_175: 2px; Fix rem all headings mobile and desktop
- Components nous: Llista d'enllaços; Targetes de xarxes socials; Xips; Peu de pàgina; Botó tornar amunt; Llista de resultats
- Bugs de components solucionats: Mostrar més; Enllaços; Paginació; Avisos; Targeta de navegació; Carregador d'arxius; Menú horitzontal; Llista; Taula de continguts; Notificació emergent; Àrea de text; Botons; Insígnia; Casella de selecció; Etiquetes; Modals; Menú desplegable; Taules dinàmiques; Targetes de notícies; Commutador; Camp d'entrada; Desplegable; Visor de notícies

### 3.0.0 - 28/04/2025

- Global CSS: Canvi color-grey-200
- Components nous: Taula de continguts; Barra de pestanyes
- Evolutiu: Menú horitzontal; Pestanyes
- Bugs de components solucionats: Acordió; Botons; Calendari; Carregador d'arxius; Camp d'entrada; Capçalera per aplicacions internes; Imatge avançada; Insígnia; Modals; Targetes; Visor de notícies

### 2.1.0 - 31/03/2025

- Components nous: Imatge avançada; Visor de notícies
- Evolutiu: Menú lateral; Pestanyes
- Bugs de components solucionats: Targetes

### 2.0.0 - 07/03/2025

- Global CSS: Canvi color-grey-100
- Components nous: Capçalera secundària; Text destacat
- Evolutiu: Menú horitzontal; Pestanyes
- Bugs de components solucionats: Desplegable; Capçalera per aplicacions internes; Botons; Pestanyes; Paginació; Taules dinàmiques; Calendari; Casella de seleció; Camp de cerca; Menú desplegable

### 1.1.0 - 17/02/2025

- Components nous: Panell destacat; Targetes; Commutador
- Bugs de components solucionats: Taules dinàmiques; Camp de cerca; Etiquetes; Indicador de funció; Àrea de text; Botons

### 1.0.0 - 31/01/2025

- Components nous: Taules dinàmiques; Capçalera per aplicacions internes
- Bugs de components solucionats: Camp de cerca; Botons; Indicador de funció; Desplegable; Paginació

### 0.1.1 - 04/12/2024

- Bugs de components solucionats: Carregador d'arxius; Pas a pas; Modals; Descripció emergent; Etiquetes

### 0.1.0 - 22/11/2024

- Components nous: Descripció emergent; Etiquetes; Modals; Mostrar més; Menú lateral
- Bugs de components solucionats: Menú horitzontal; Paginació; Insígnia; Botons; Casella de selecció; Notificació emergent

### 0.0.4 - 01/11/2024

- Desenvolupament de 25 components

