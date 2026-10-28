# Etiquetatge d'IA (IA labeling)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/732227 · Web component: cap (component pendent de desenvolupament) · Font actualitzada el 2026-10-23 · Extret el 2026-10-28

## Què és i quan usar-lo
Permet identificar de manera clara, coherent i accessible els continguts creats o editats amb intel·ligència artificial i consultar informació complementària sobre la seva intervenció. **Component pendent de desenvolupament.**

El component d'etiquetatge d'IA permet identificar els continguts creats o editats mitjançant intel·ligència artificial i informar de manera transparent sobre la participació d'aquesta tecnologia. Inclou diferents variants segons el grau d'intervenció de la IA i contempla una segona capa d'informació per als casos en què una etiqueta breu no és suficient per explicar com s'ha utilitzat la tecnologia.

Per conèixer els criteris i les obligacions de transparència en l'ús de la intel·ligència artificial, consulta el document de referència de la Generalitat de Catalunya [Obligacions de transparència en l'ús d'intel·ligència artificial](https://presidencia.bibliotecadigital.gencat.cat/bitstream/handle/20.500.14623/2623/Obligacions%20de%20transpar%C3%A8ncia%20en%20l'%C3%BAs%20d'intel%C2%B7lig%C3%A8ncia%20artificial.pdf?sequence=1&isAllowed=y).

Quan s'utilitza:
- Quan un contingut públic ha estat generat o modificat amb intel·ligència artificial i cal identificar aquesta intervenció.
- Quan una imatge, un vídeo o un àudio incorpora contingut sintètic o manipulat amb IA que requereix identificació.
- Quan un text de caràcter informatiu ha estat generat o modificat amb IA i cal informar de la participació de la tecnologia.
- Quan un camp o una opció de formulari incorpora informació generada o modificada amb IA.
- Quan cal oferir informació complementària sobre com s'ha utilitzat la IA.

### Quina variant utilitzar
- **IA** (variant bàsica, `Basic`): utilitza aquesta variant quan hi ha intervenció d'IA però no es pot concretar clarament si el contingut és creat o editat, o quan combina diferents tipus d'intervenció. És l'única variant que pot donar accés a una segona capa informativa.
- **Creat amb IA** (`Created`): utilitza aquesta variant quan el contingut ha estat creat completament mitjançant intel·ligència artificial.
- **Editat amb IA** (`Edited`): utilitza aquesta variant quan es parteix d'un contingut original o creat per una persona i aquest ha estat editat de manera substantiva mitjançant intel·ligència artificial.

## Quan NO usar-lo / alternatives
- Quan la IA només s'utilitza per corregir ortografia o gramàtica.
- Quan només es fan ajustos tècnics sobre una imatge, com ara retall, color o lluminositat.
- Quan el contingut és una il·lustració estilitzada o una infografia clarament no fotorealista.
- Quan el contingut es manté en un entorn intern, com ara una intranet, un correu intern, un esborrany o un document compartit amb un equip concret.
- Quan un text ha passat per una revisió humana substantiva i existeix una responsabilitat editorial identificada, sempre que després no hi hagi una nova intervenció substantiva d'IA.

## Anatomia
El component disposa de tres variants estàtiques i una variant interactiva, que permet consultar informació complementària sobre la intervenció de la intel·ligència artificial.

**Etiquetes estàtiques**
1. **Etiqueta (IA, Creat amb IA, Editat amb IA)**: indica el tipus d'intervenció d'intel·ligència artificial en el contingut.
2. **Identificador IA**: element gràfic circular que acompanya el literal i facilita el reconeixement visual de l'etiquetatge d'IA.

**Etiqueta interactiva**
1. **Contenidor**: delimita l'àrea interactiva del component.
2. **Literal IA**: identifica la participació de la intel·ligència artificial.
3. **Icona de desplegament**: indica que es pot consultar informació complementària.
4. **Panell desplegable**: mostra la informació contextual sobre la intervenció de la IA, que pot incloure un títol, una descripció, dades complementàries i un enllaç.

## Variants, tipus i estats

### Variants estàtiques

| Propietat | Valor | Valor per defecte |
|---|---|---|
| AI variants | Basic / Created / Edited | - |
| Interactivity | True / False | False |

Variants Figma (`AI Tags`): AI Variants = Basic | Created | Edited.

### Variant interactiva
S'utilitza quan l'etiqueta breu no és suficient per explicar de manera clara quin ús s'ha fet de la intel·ligència artificial. Permet accedir a una segona capa d'informació mitjançant un panell desplegable, mantenint el context del contingut identificat.

| Propietat | Valor | Valor per defecte |
|---|---|---|
| States | Default / Hover / Focus | Default |
| Collapsed | True / False | True |

Variants Figma (`_AI trigger`): States = Default | Hover | Focus; Collapsed = True | False.

Quan utilitzar la variant interactiva:
- Quan un mateix contingut combina parts generades, modificades i originals.
- Quan cal especificar quin element concret ha estat generat o modificat.
- Quan el grau d'intervenció no es pot explicar únicament amb les etiquetes estàtiques.
- Quan cal aportar context addicional per entendre correctament l'ús de la IA.

### Contingut del desplegable
El panell desplegable proporciona informació complementària sobre la intervenció de la intel·ligència artificial. El contingut s'ha d'adaptar a cada cas i pot incloure:
- **Tipus de contingut afectat:** text, imatge, àudio o vídeo.
- **Tipus d'intervenció:** generació, modificació o combinació d'ambdues.
- **Element afectat:** veu, imatge, fragment de text, escena o camp de formulari.
- **Informació complementària:** criteris, abast de la intervenció o altres dades rellevants.
- **Enllaços relacionats:** accés a informació addicional, quan sigui necessari.

## Comportament i interacció
L'etiquetatge d'IA ha de mantenir-se clar, visible i associat al contingut identificat durant tota l'experiència d'ús. El comportament varia segons si s'utilitza una etiqueta estàtica o la variant interactiva.

### Funcionament del desplegable
En activar l'etiqueta interactiva, s'obre un panell associat que mostra la informació complementària. La persona usuària pot consultar-ne el contingut sense abandonar la pàgina ni perdre el context de navegació. El panell es pot tornar a tancar i l'etiqueta recupera el seu estat inicial.

### Visibilitat i relació amb el contingut
L'etiqueta s'ha de mostrar des de la primera exposició al contingut i no pot quedar oculta per altres elements de la interfície. S'ha de situar prou a prop de l'element que identifica perquè la seva relació sigui inequívoca, especialment en contextos amb diversos continguts o camps de formulari.

### Persistència i contingut multimèdia
- Quan el contingut es descarrega o es comparteix, la identificació de la IA ha de continuar vinculada al contingut, quan correspongui.
- En vídeos o altres continguts reproduïbles, la identificació ha de continuar sent perceptible durant el consum del contingut quan sigui necessari.

### Aplicació segons el tipus de contingut
L'etiquetatge d'IA s'adapta als diferents tipus de contingut i components del Sistema de Disseny, mantenint una relació clara amb l'element identificat i respectant la jerarquia visual de cada context.

**Contingut multimèdia**
- **Imatge:** situa l'etiqueta immediatament sota la imatge i abans del peu de foto, de manera que quedi clar que fa referència al contingut visual.
- **Galeria i visor:** situa l'etiqueta sota la imatge activa i abans del peu de foto i la numeració del visor, mantenint-la vinculada a l'element que s'està visualitzant.
- **Vídeo:** situa l'etiqueta immediatament sota el reproductor, de manera que sigui perceptible des de l'inici i quedi clar que identifica el contingut audiovisual.
- **Àudio:** situa l'etiqueta immediatament sota el reproductor d'àudio, mantenint una associació directa amb la peça que identifica.

**Components de contingut**
- **Capçalera secundària:** si la intervenció de la IA afecta la imatge de la capçalera secundària, situa l'etiqueta sobre la imatge, a la cantonada inferior dreta.
- **Targetes i Visor de notícies:** si la intervenció d'IA afecta només la imatge de la targeta, situa l'etiqueta sobre la imatge, a la cantonada inferior dreta. Si afecta el contingut de la targeta en conjunt, situa l'etiqueta fora de la imatge i integrada en el bloc de contingut, separada de les categories, estats i altres metadades.
- **Notícia i contingut de pàgina:** si la intervenció d'IA afecta el contingut editorial de la notícia o d'una pàgina, situa l'etiqueta abans del titular i dins del mateix bloc de contingut, perquè la persona usuària identifiqui la intervenció abans de començar a llegir.

**Components de formulari**
L'etiquetatge d'IA es pot incorporar als components de formulari per identificar els camps o les opcions que contenen informació generada o modificada amb intel·ligència artificial. La seva disposició ha de respectar la jerarquia dels elements del formulari i mantenir una associació clara amb el contingut identificat.
- **Camps d'entrada, àrea de text, selector de data i desplegable:** situa l'etiquetatge d'IA a continuació de l'etiqueta del camp i abans dels elements d'ajuda, respectant l'ordre jeràrquic: Etiqueta del camp → IA → Tooltip → Ajuda → Comptador de caràcters. Es pot utilitzar tant la variant estàtica com la interactiva, segons la necessitat d'oferir informació complementària.
- **Botons d'opció i caselles de selecció:** quan diverses opcions incorporen etiquetes d'IA, cal mantenir una distribució coherent a tot el grup.

### Convivència i espaiat
Quan l'etiquetatge d'IA conviu amb altres elements del formulari, cal respectar les separacions definides i mantenir-ne l'alineació vertical per garantir una distribució visual equilibrada. Consulta la configuració de cada component de formulari per conèixer les especificacions d'espaiat i posicionament corresponents.

## Bones pràctiques
- **FER:** Utilitza sempre la variant que descrigui amb més precisió la intervenció de la IA: IA, Creat amb IA o Editat amb IA.
- **NO FER:** No utilitzis IA si es pot especificar clarament Creat amb IA o Editat amb IA.
- **FER:** Mantén l'etiqueta visualment vinculada a l'element concret que identifica.
- **NO FER:** No facis servir l'etiqueta com si fos una categoria, un estat o un filtre.
- **FER:** Fes servir la variant interactiva només quan calgui ampliar el context amb una segona capa.
- **NO FER:** No utilitzis la segona capa per explicar informació que ja queda clara amb el literal principal.
- **FER:** Quan la intervenció afecti només una part del contingut, associa l'etiqueta directament a aquell element.
- **NO FER:** No situïs l'etiqueta en un lloc que pugui generar dubtes sobre quin contingut identifica.
- **FER:** Quan la intervenció afecti el contingut en conjunt, situa l'etiqueta en el bloc principal de contingut.
- **NO FER:** No barregis l'etiqueta d'IA amb altres etiquetes o metadades de manera que es puguin confondre.
- **NO FER:** No introdueixis iconografia, colors o variants visuals alternatives fora de les definides al patró.
- **FER:** Quan l'etiqueta conviu amb altres elements del formulari, cal ajustar-ne l'alineació i l'espaiat per mantenir la coherència visual.
- **FER:** Situa l'etiqueta d'IA immediatament després de l'etiqueta del camp i abans dels elements d'ajuda, respectant la jerarquia.

## Accessibilitat

### Pautes WCAG
- **Ús del color (A)**: el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual; per diferenciar els diferents estats del desplegable. [1.4.1 Ús del color - CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA)**: els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. [1.4.3 Contrast mínim - CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA)**: excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [1.4.4 Canvia la mida del text - CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA)**: els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [1.4.11 Contrast d'elements no textuals - CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Espaiat del text (AA)**: quan es desenvolupa contingut utilitzant llenguatges de marcatge que permeten aplicar les propietats d'estil de text, no es perd cap contingut ni funcionalitat si s'ajusten les propietats següents: alçada de línia (interlineat) de com a mínim 1,5 vegades la mida de la lletra; espaiat entre els paràgrafs de com a mínim dues vegades la mida de la lletra; espaiat entre lletres (tracking) de com a mínim 0,12 vegades la mida de la lletra; espaiat entre paraules de com a mínim 0,16 vegades la mida de la lletra. [1.4.12 Espaiat del text - CAT](https://www.w3.org/Translations/WCAG22-ca/#text-spacing) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/text-spacing)
- **Teclat (A)**: tota la funcionalitat del contingut (desplegar el desplegable de l'etiqueta interactiva) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [2.1.1 Teclat - CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)

## Historial de versions

| Versió Figma | Data | Descripció |
|---|---|---|
| 12.6.0 | 23 d'octubre, 2026 | Disseny i documentació del component |

> Nota: no hi ha API de component web documentada a la v12.0.0 (component pendent de desenvolupament).

## Vegeu també
- [Etiquetes](component-etiquetes.md)
- [Reproductor de vídeo i àudio](component-reproductor-de-video-i-audio.md)
- [Capçalera secundària](component-capcalera-secundaria.md)
- [Targetes](component-targetes.md)
- [Visor de notícies](component-visor-de-noticies.md)
- [Camp d'entrada](component-camp-d-entrada.md)
- [Àrea de text](component-area-de-text.md)
- [Selector de data](component-selector-de-data.md)
- [Desplegable](component-desplegable.md)
- [Botó d'opció](component-boto-d-opcio.md)
- [Casella de selecció](component-casella-de-seleccio.md)
- [Imatge](fonaments-imatge.md)
