# Taules dinàmiques (Dynamic tables)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/030c12 · Web component: `<dynamic-table-component>` (paquet core) · Font actualitzada el 2026-10-27 · Extret el 2026-10-28

## Què és i quan usar-lo
Les taules de dades dinàmiques s'utilitzen per organitzar i mostrar les dades de manera eficient. El component de la taula de dades dinàmica permet la personalització amb funcionalitats addicionals, segons les necessitats dels usuaris del producte.

Quan s'utilitza:
- Per a organitzar i mostrar grans quantitats de dades de forma estructurada.

Dos tipus de taula:
- **Taula dinàmica (Dynamic):** s'utilitza més per entorns privats i de gestió interna on els treballadors treballin i necessitin manipular moltes dades. Tot i que pot aparèixer en dispositius grans, és la versió òptima per utilitzar en dispositius mòbils [sic; a verificar: la font diu això per a les dues taules].
- **Taula estàtica (Static):** s'utilitza més en entorns de webs públiques on el ciutadà comprova dades de visualització, tot i que es pot utilitzar també en entorns privats i de gestió interna. També, tot i que pot aparèixer en dispositius grans, és la versió òptima per utilitzar en dispositius mòbils. La taula estàtica **no inclou elements interactius** com accions o filtres. Tot i això, cada cel·la pot contenir diversos elements, com text, nombres o etiquetes, segons les necessitats.

## Quan NO usar-lo / alternatives
- Quan es tracta de dades que tenen relacions molt complexes o quan es volen trobar "patrons" dins de les dades, les visualitzacions de gràfics són més efectives.
- Alternatives relacionades: [Acordió](component-acordio.md) (per mostrar o amagar informació individualment d'un llistat d'ítems), [Llista](component-llista.md) (per agrupacions de contingut relacionat), [Paginació](component-paginacio.md) (per separar grups de contingut en diverses pàgines).

## Anatomia
El sistema de disseny disposa del **component taula** on es troben els diferents elements que la conformen units en un únic component. Si aquesta taula no és adient per al cas, es pot **construir des de zero** amb els diferents elements (vegeu "Construcció de taules a Figma").

Parts de la taula completa: barra superior (mòdul d'accions dinàmiques, zona de botons, filtre global, text de resultats i botó per netejar filtres), taula (capçalera i files), barra de desplaçament horitzontal i paginació.

Figma de la taula completa: Table [Show Dynamic actions = False, Show Scroll bar = True, Show Global filter = True, Show Filter button = False, Show Buttons = True, Show Pagination = True, Breakpoint = Extra Large - Medium, Type = Dynamic].

## Variants, tipus i estats

### Propietats de la taula completa

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Type | Dynamic / Static | Dynamic |
| Device | Desktop / Mobile | Desktop |
| Dynamic actions | True / False | False |
| Scroll bar | True / False | True |
| Global filter | True / False | True |
| Filter button | True / False | False |
| Buttons | True / False | True |

- **Dispositiu:** la versió mòbil està disponible, de moment, només per a la taula estàtica.
- **Barra superior:** inclou el mòdul d'accions dinàmiques, la zona de botons, el filtre global, el text de resultats i el botó per netejar els filtres. S'hi apliquen les propietats Dynamic Actions, Global Filter, Filter Button i Buttons. Variants: accions dinàmiques i botó de netejar filtres; sense filtre global; sense zona de botons.
- **Sense barra de desplaçament:** si la taula es pot visualitzar sense necessitat de desplaçament horitzontal, aquesta s'amagarà.
- **Paginació:** si la taula no necessita més d'una pàgina, la paginació es pot amagar.

### Taula (files)
La taula està construïda a partir de files i es poden modificar els seus estats seleccionant cadascuna d'elles.

**Capçalera (_Header row)**

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Column fixed | None / First / Last / Both | None |
| Device | Desktop / Mobile | Desktop |
| Interactive | Default / non-interactive / Interactive | Default |
| Chevron space | True / False | True |
| Checkbox | True / False | True |

Figma: _Header row [Show Chevron space = True, Show Checkbox = True, Show Actions header = True, Breakpoint = Extra Large - Medium, Column fixed = None, Interactive = True].

**Fila (_Rows)**

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Column fixed | None / First / Last / Both | None |
| Device | Desktop / Mobile | Desktop |
| Size | Medium / Large | Medium |
| States | Default / Hover / Selected / Focus / Focus-Selected | Default |
| Interaction | No / Yes | No |
| Second level | True / False | False |

Figma: _Rows [Chevron = True, Checkbox = True, Actions = True, Second level = False, Breakpoint = Extra Large - Medium, Size = Small, Interactive = False, Column fixed = None, State = Default].

- **Segon nivell:** la fila de segon nivell està incorporada com una booleana. Per mostrar correctament aquesta segona fila, caldrà també modificar el selector de la fila i seleccionar el tipus *Dropdown-expanded*.

### Propietats dels elements
Utilitza els **elements** de forma individual per crear la taula des de zero o utilitza la **taula completa** si s'adapta a les necessitats.

**Cel·la - Capçaleres de columna (Column Headers)**

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Type | Default / Empty / Selector | --- |
| Size | Medium / Small | Small |
| Tooltip | True / False | True |
| Shadow right | True / False | False |
| Shadow left | True / False | False |
| Filter | True / False | True |
| Sorting | True / False | True |

Figma: Table items_Header cells [Show Tooltip = True, Show Shadow right = False, Show Shadow left = False, Show Filter = True, Show Sorting = True, Label text = Etiqueta, Show buttons = True, Type = Default, Size = Small].

Quan el text o l'etiqueta superi l'espai disponible, caldrà canviar manualment de "Hug" a "Fill Container" per evitar que el text sobresurti del contenidor.

La subsecció "Mida" de les capçaleres de columna és marcada a la font com a "pendent d'afegir".

**Cel·la - Files**

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Size | Medium / Small | Small |
| Type | Content / Selector / Actions / Dropdown-collapsed / Dropdown-expanded / Secondary / Slot | Content |
| State | Default / Hover / Selected / Focus | Default |
| Position | Middle / End / Beginning / Default | --- |
| Shadow right | True / False | False |
| Shadow left | True / False | False |

Figma: Table items_Row cells [Show Shadow Right = False, Show Shadow Left = False, Cell slot = (slot), Type = Content, Size = Small, Position = Default, State = Default]. Variant amb tipus Link: [Shadow Left = False, Shadow Right = False, Secondary text = Secondary text, Numeric value = 000,00, Nominal value = Cell content, Secondary content = True, Size = Medium, Type = Link, State = Default, Position = Middle].

El tipus **"Content"** disposa d'una instància anidada (_Cell items small [Nominal value = Cell content, Numeric value = 000,00, Type = Nominal]) que permet canviar el contingut entre Nominal, Numèric, Enllaç i Etiqueta.

**Menú d'accions**: quan les accions no puguin estar totes visibles en un primer nivell i s'utilitzi el botó per agrupar accions es mostrarà el menú d'accions.

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Number actions | 2 / 3 / 4 / 5 | --- |

Figma: Table items_Action menu [Nº actions = 2].

**Menú de filtres**: en seleccionar el botó de filtre apareixerà un menú desplegable (Table items_Filter menu).

**Desplaçament horitzontal**: si la taula disposa de més columnes de les que es poden visualitzar en pantalla caldrà utilitzar desplaçament horitzontal i introduir el component Table items_Horizontal scroll a la part inferior.

**Menú d'accions múltiples**: quan s'aplica la selecció múltiple en la taula dinàmica apareixerà el menú d'accions múltiples (Table items_Dynamic actions menu), que permetrà col·locar tres accions o bé, si n'hi ha més de tres, l'opció d'integrar un menú.

## Mides i espaiats

### Mides de taula
- Les taules de mida **Medium** s'utilitzaran quan només sigui necessari un element textual en totes les cel·les de la taula.
- Les taules de mida **Large** s'utilitzaran en el cas que sigui necessari introduir un text secundari en una o més cel·les de la taula.

### Alçada
L'alçada de la taula es defineix pel nombre de files visibles.
- **Escriptori:** es recomana mostrar **12 resultats per pàgina** per defecte. L'usuari pot augmentar aquest nombre mitjançant el desplegable de resultats per pàgina.
- **Dispositius mòbils:** també es recomana **12 resultats per pàgina** (la font diu "12t"; [a verificar]), però sense possibilitat d'ampliar-los per garantir una millor experiència d'ús.

### Amplada de columna
L'amplada de columna està limitada amb un **mínim de 168 px** i un **màxim de 360 px**. Aquesta amplada anirà en funció del contingut de la capçalera o les cel·les.
- Si la mida total de la taula és inferior a l'espai disponible, quedarà alineada a l'esquerra. En canvi, si la taula creix i sobrepassa l'espai, apareixerà l'scroll horitzontal respectant els màxims.
- Per poder construir la taula en funció del contingut cal construir-la a partir dels components individuals de cel·la i capçalera (vegeu "Construcció de taules a Figma").
- Les [Etiquetes](component-etiquetes.md) que s'utilitzin dins les cel·les hauran de respectar la mida màxima establerta en aquest component (24 caràcters). Si l'amplada de columna és més petita que l'amplada de l'etiqueta, aquesta saltarà de línia.
- Els [Enllaços](component-enllacos.md) ocuparan l'espai disponible de cel·la i, si són més extensos, saltaran de línia.
- Aquest comportament de la mida de l'etiqueta i l'enllaç s'haurà de **modificar manualment** al contingut de la cel·la, modificant el nombre de línies a través de les propietats en el cas dels enllaços o passant de "Hug" a "Fill container" en el cas de les etiquetes.

### Resultats
El text a utilitzar en el nombre de resultats que ofereix la taula pot variar en funció del context. Alguns exemples: Entrades, Files, Registres.

### Dades nominals versus dades numèriques
- **Dades nominals:** sempre s'alinearan a l'esquerra. Per exemple: noms, categories, codis postals.
- **Dades numèriques:** generalment, s'han d'alinear a la dreta per facilitar la lectura i la comparació. Si els números són identificadors arbitraris (com codis postals, adreces IP o números de telèfon), s'alinearan a l'esquerra perquè no es poden comparar ni combinar matemàticament.
- **Alineació amb decimals:** quan els números tenen decimals han d'estar alineats a la dreta, assegurant que la coma dels decimals sempre estigui situada a la mateixa posició. Si hi ha diferències en el nombre de decimals, la coma ha de quedar sempre en la mateixa posició.

## Comportament i interacció

### Accions
Cada fila pot contenir una o diverses accions associades.
- **Accions per fila:** cada fila pot tenir fins a 3 accions visibles. Si hi ha més accions, s'inclouran en un menú desplegable amb la icona de 3 punts. Desenvolupament: el menú desplegable no està desenvolupat dins la taula, però es pot introduir manualment.
- **Posició i icones:** les icones de les accions sempre es col·loquen a l'última columna de la fila. Cada icona inclou un indicador de funció (*tooltip*) amb el nom de l'acció, que apareix quan l'usuari hi passa el cursor (*hover*) durant 1,5 segons, tal com estableix el comportament dels indicadors de funció.
- **Desplegable:** quan es despleguin més accions, es mostraran tant el nom de l'acció com la seva icona.
- **Accions múltiples:** l'usuari pot seleccionar diverses files per realitzar accions en massa. Quan se seleccionen files, apareix un mòdul sobre la taula amb el nombre total de files seleccionades i les accions disponibles.
  - Totes les accions mostraran la icona. Les que no càpiguen es col·locaran en un menú desplegable de "Més accions".
  - També hi haurà un botó de "Cancel·la" al costat del total de files seleccionades, que permetrà desseleccionar-les ràpidament.

### Ordenar per columnes
Desenvolupament: la funcionalitat per ordenar columnes **no està implementada**. Serà responsabilitat del desenvolupador del projecte incorporar aquesta funcionalitat mitjançant codi propi.
- Els usuaris poden ordenar la informació de la taula clicant a les capçaleres de les columnes.
- Les columnes que permeten ordenar estaran marcades amb una icona de "doble fletxa", indicant que l'etiqueta és clicable.
  - Quan l'usuari faci clic a la icona, la taula s'ordenarà automàticament per aquella columna en ordre descendent.
  - Si l'usuari fa un segon clic a la mateixa icona, l'ordenació canviarà a ascendent.
- La columna que està ordenant la taula mostrarà una fletxa cap amunt (ordenació ascendent) o cap avall (ordenació descendent), substituint la "doble fletxa" inicial.
- Per defecte, la taula no s'ordena.

### Taules interactives
Les taules poden ser merament informatives, sense incloure cap element interactiu, o poden incloure elements que permeten seleccionar dades, configurar la visualització, navegar cap a altres pàgines o realitzar accions sobre la mateixa taula.

- **Hover:** quan una fila disposa de casella de selecció, es podrà seleccionar clicant en qualsevol àrea de la fila que no tingui un element interactiu. Si no disposa de casella de selecció, el hover només indicarà en quina fila es situa l'usuari.
- **Selecció:**
  - L'usuari pot seleccionar una o diverses files fent servir **caselles de selecció** (*checkboxes*) per realitzar accions múltiples.
  - Si la fila només ofereix l'opció de selecció, sense cap enllaç o acció addicional, l'usuari podrà seleccionar-la clicant a qualsevol part de la fila. En aquest cas, s'aplicarà l'estat de *hover* a tota la fila per indicar la selecció.
  - Si una fila inclou enllaços o accions, el hover es seguirà aplicant a tota la fila per indicar on es troba l'usuari, però per activar un element interactiu haurà de col·locar-se just a sobre d'aquest.
- **Focus:** l'usuari podrà navegar mitjançant el teclat per tots aquells elements interactius de la taula. El desplaçament es realitzarà de forma seqüencial amb la **tecla tabulació**. En arribar a la taula el focus es col·locarà en el primer element interactiu de la capçalera i es desplaçarà d'esquerra a dreta i de dalt a baix.
- **Paginació:** depenent del cas d'ús, les taules podran anar acompanyades d'una paginació.
- **Filtratge:** Desenvolupament: la funcionalitat per filtrar columnes no està desenvolupada. El desenvolupador del projecte haurà d'introduir-la amb codi propi.
  - La taula disposa de **dues formes de filtratge**: el filtratge **global** i l'**específic** de columna.
  - Quan s'apliqui qualsevol d'aquests filtres apareixerà automàticament el **botó de "Neteja filtres"** a la dreta dels resultats de la taula.
  - En el **filtratge de columna**, apareixerà una **insígnia** sobre el botó específic de filtratge en aquella columna en la qual s'ha aplicat un filtre.
  - La font mostra un exemple amb la combinació del filtre global i de columna.

### Adaptació responsiva

**Comportament responsiu en escriptori (desktop)**
- Si la taula conté moltes columnes que no hi caben a la pantalla, apareixerà un **desplaçament horitzontal**. La primera columna es mantindrà fixa per ajudar l'usuari a contextualitzar les dades, facilitant-ne la lectura.
- Es mostraran uns **xebrons** a la cantonada superior dreta per facilitar la navegació horitzontal. Alternativament, l'usuari podrà utilitzar la barra de **desplaçament** a la part inferior de la taula per desplaçar-se lateralment.
- Si la taula inclou una columna amb accions, aquesta també es mantindrà fixa a la dreta de la pantalla, millorant l'accessibilitat a les opcions d'interacció.
- Quan el ratolí estigui sobre la taula, l'usuari podrà desplaçar-se **horitzontalment** utilitzant la roda del ratolí, oferint una experiència més fluida i intuïtiva.

**Paginació:** la paginació de la taula s'adapta segons l'espai disponible a la pantalla.
- **Escriptori:** es mostrarà la paginació completa, amb opcions per navegar entre pàgines i seleccionar el nombre de resultats per pàgina.
- **Mòbil:** es reduirà a un màxim de **3 elements visibles** per facilitar la navegació i optimitzar l'espai. L'opció de reduir fins a 3 elements **no està actualment com a propietat**; aquest canvi s'haurà de fer **manualment** ocultant els elements.

**Comportament responsiu a mòbil (recomanacions):** la versió per a mòbil està **disponible per a la versió estàtica** de la taula. Si el cas no es soluciona amb aquesta versió en pantalles petites (tauleta i mòbil), es poden seguir aquestes recomanacions:
- **Dissenyar una versió responsiva personalitzada:** si es tracta d'una taula amb poc contingut, pot ser una bona opció dissenyar un component nou tipus targeta que distribueixi la informació en blocs, oferint una visualització més clara per a mòbils.
- **Mostrar només el contingut important:** en alguns casos, pot ser una bona solució mostrar només una part del contingut, deixant la versió completa de la taula per a dispositius d'escriptori. Una altra opció podria ser "obligar" l'usuari a seleccionar a través de filtres o selectors les dades que necessita veure abans de mostrar-les. D'aquesta manera es limita la quantitat de dades a un màxim definit i s'assegura una bona visualització en pantalles petites.
- **Replegar el contingut amb acordions:** si la taula inclou dades que es poden agrupar en categories lògiques, utilitza acordions per permetre als usuaris tenir una visió general del contingut i mantenir un accés més directe a la informació d'interès.
- **Habilitar desplaçament horitzontal:** si la taula té moltes columnes, activa el scroll horitzontal per permetre a l'usuari desplaçar-se d'esquerra a dreta. Mantén sempre la primera columna fixa per facilitar la consulta sense perdre de vista la informació de referència.

### Construcció de taules a Figma
Per construir una taula amb el comportament descrit (l'amplada de columna s'adapta en funció del contingut fins a un màxim) i les funcionalitats que ofereix el sistema de disseny, es poden seguir aquests passos (exemple amb 4 columnes i interacció).

**Creació de les files.** Primer es crea la fila base per a la capçalera i la resta de cel·les:
1. Arrossega els diferents components de capçalera i cel·la en funció del nombre de columnes.
2. Construeix la fila de la capçalera de forma que el **primer** element sigui el component **capçalera amb la propietat Empty-Small**, el **segon** tingui la propietat **Selector** i el **tercer** correspongui a la **primera columna amb contingut**.
3. Crea un **frame amb auto-layout** (sense padding) per agrupar la resta de columnes (en aquest cas, tres).
4. Col·loca un **frame sense auto-layout** just per sobre de l'anterior (sense padding). Col·loca el conjunt just després de la resta d'elements. Això permetrà moure les columnes si hi ha scroll horitzontal.
5. Afegeix un component de **capçalera** amb la propietat **Empty-Large**.
6. Per a les **files**, segueix el **mateix procediment** que per a la capçalera, però utilitzant el component corresponent; a la primera columna utilitza'l amb la propietat "**Dropdown-collapsed**" i a l'última amb la d'"**Actions**".
7. Per afegir la **fila secundària** que apareix en interactuar amb el desplegable, col·loca-la dins un auto-layout amb la fila corresponent sense marges. El component ha d'estar en **fill**. Si la fila es troba desplegada, canvia la propietat de la primera cel·la de dropdown-collapsed a dropdown-expanded.
8. Per a la resta de files repeteix el procediment i agrupa-les amb la capçalera. No afegeixis espais entre files. De moment, no coincidirà l'amplada de les files amb la capçalera.

**Adaptació de les columnes.**
9. Un cop creada la taula base, afegeix contingut i adapta les amplades de les columnes en funció de la cel·la amb més contingut. Si el contingut és curt (com edats) no caldrà modificar res, però si el text és més extens, caldrà adaptar el frame principal i el frame del contingut a Hug. Les cel·les (o capçalera) de la mateixa columna que tinguin amplades inferiors hauran d'adaptar-se amb una amplada fixa de 360 px.

**Scroll horitzontal.**
10. En cas que calgui scroll horitzontal, afegeix el component per a la barra just sota de l'última fila.

**Vora.**
11. Aplica una vora amb el color "**tertiary**". Ha d'estar en posició "**inside**" i s'hi aplica un **arrodoniment** de **8 px**.

**Elements adicionals.**
12. Afegeix la resta d'elements: zona botonera, camp de cerca (per filtres) i botó per netejar filtres i el menú d'accions dinàmiques (aquest en format prototip en interactuar amb els checkbox de les files).

## Bones pràctiques

### Organització
- **FER:** Organitza les columnes per ordre d'importància d'esquerra a dreta: posa les dades amb les quals els usuaris interactuaran més a l'àrea visible sense desplaçament horitzontal.
- **NO FER:** No organitzis les columnes per ordre d'importància de dreta a esquerra.

### Format
- **FER:** Les dades dins de les columnes tenen un format coherent. Per exemple, les dates en el mateix format, els nombres amb la mateixa precisió decimal o alineació dins de la casella.
- **NO FER:** Les dades dins de les columnes no segueixen un mateix format.

### Redacció
- **FER:** Evita noms o dades que no siguin significatius per als usuaris, com ara identificadors o codis generats automàticament que estan destinats a representar informació complexa.
- **NO FER:** No utilitzis noms o dades que no són significatius per als usuaris.

## Accessibilitat

### Pautes d'accessibilitat del contingut web (WCAG)
- **Orientació (AA), 1.3.4:** el contingut de l'àrea de text s'adapta a les diferents orientacions de la pantalla, com vertical o horitzontal, cosa que permet visualitzar el contingut. [CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Ús del color (A), 1.4.1:** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a diferenciar els diferents estats s'inclouen subratllats, es juga amb la presència de farciment i el gruix de la vora. [CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA), 1.4.3:** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA), 1.4.4:** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA), 1.4.11:** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A), 2.1.1:** tota la funcionalitat del contingut (navegar pels diferents botons) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Ordre del focus (A), 2.4.3:** les taules dinàmiques i els diferents elements que les componen han de presentar-se en un ordre lògic per facilitar la navegació per teclat o altres dispositius d'entrada. L'ordre ha de seguir el flux de la informació o les tasques que s'estan presentant. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-order) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-order)
- **Focus visible (AA), 2.4.7:** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

### Navegació per teclat
L'usuari podrà navegar mitjançant el teclat per tots aquells elements interactius de la taula. Podrà seleccionar amb la tecla "enter" la primera fila de la taula, i navegar per les diferents files utilitzant la tabulació.

| Tecla | Acció |
|---|---|
| Tabulació | Navegar al camp d'entrada següent |
| Shift + Tabulació | Navegar al camp d'entrada anterior |
| Enter | Seleccionar fila i accions |
| Esc | Cancel·lar una acció |

## Implementació (component web)

### `<dynamic-table-component>`
Paquet: core.

**Propietats**

Els valors per defecte i els tipus provenen del PDF; la descripció i l'obligatorietat, del lloc.

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat |
|---|---|---|---|---|---|
| `actionsButtonsRow` | `actions-buttons-row` | Conté la informació sobre els tres botons d'accions que acompanyaran cada fila. Accepta array d'objectes o string JSON. | String (Array) | `undefined` | Obligatori només per a mode dynamic |
| `buttonFilterSearchfield` | `button-filter-searchfield` | Controla la visibilitat del botó de filtrar del searchfield. | Boolean | `false` | Opcional |
| `data` | `data` | Conté la informació de les cel·les. Accepta objecte o string JSON. | String (Array) | `undefined` | Obligatori |
| `filterOptions` | `filter-options` | Conté la informació dels elements filtrats a la taula. Pensat perquè qui utilitzi el component elabori el seu propi codi per filtrar les dades de la base de dades i les introdueixi posteriorment en aquest prop. Accepta array d'objectes o string JSON. | String (Object) | `undefined` | Opcional |
| `headers` | `headers` | Fa referència al nom de cada columna, així com altra informació, com si les dades de les cel·les tindran text secundari, seran una tag o un link. Important posar sempre en primer lloc la columna ID per al funcionament correcte de la taula. Accepta array d'objectes o string JSON. | String (Array) | `undefined` | Obligatori |
| `itemsButtonsSelectedOptions` | `items-buttons-selected-options` | Configuració dels tres botons del contenidor pop up que apareix en seleccionar una o diverses opcions. Accepta array d'objectes o string JSON. | String (Array) | `undefined` | Obligatori només per a mode dynamic |
| `leftColumnFixed` | `left-column-fixed` | Permet fixar la primera columna de dades. | Boolean | `true` | Opcional |
| `mode` | `mode` | Mode de la taula: dinàmic o estàtic (variant visual). Opcions: `dynamic`, `static`. | String | `dynamic` | Obligatori |
| `rightColumnFixed` | `right-column-fixed` | Permet fixar la darrera columna, ja sigui de dades o la d'accions. | Boolean | `false` | Opcional |
| `searchfieldId` | `searchfield-id` | Identificador de l'input de tipus text del searchfield. | String | `undefined` | Obligatori |
| `searchfieldName` | `searchfield-name` | Nom de l'input de tipus text del searchfield (atribut name del camp de cerca). | String | `undefined` | Obligatori |
| `searchfieldShowTooltip` | `searchfield-show-tooltip` | Permet mostrar o amagar la icona informativa amb tooltip del camp de cerca. | Boolean | `undefined` | Opcional |
| `searchfieldTextEtiqueta` | `searchfield-text-etiqueta` | Text de l'etiqueta del camp de cerca. | String | `undefined` | Obligatori |
| `searchfieldTextInfoTooltip` | `searchfield-text-info-tooltip` | Text del tooltip que apareix sobre la icona informativa al camp de cerca. | String | `undefined` | Opcional |
| `showIdColumn` | `show-id-column` | Mostrar o amagar columna ID. | Boolean | `false` | Opcional |
| `textButtonFilterSearchfield` | `text-button-filter-searchfield` | Text alternatiu del botó de filtrar del searchfield. | String | `''` (buit) | Opcional |
| `textEntry` | `text-entry` | Personalització de la darrera paraula del text que indica el nombre de files/entrades que té la taula. | String | `undefined` | Obligatori |
| `tooltipButtonFilterSearchfield` | `tooltip-button-filter-searchfield` | Text tooltip del botó de filtrar del camp de cerca. | String | `Filtra resultats` | Opcional |
| `tooltipButtonSearchSearchfield` | `tooltip-button-search-searchfield` | Text tooltip del botó de cerca del camp de cerca. | String | `Cerca entre les files` | Opcional |
| `totalItems` | `total-items` | Informa al component quin és el nombre total d'ítems de la taula (imprescindible per a la paginació). | Number | `undefined` | Obligatori |
| `valueSearchfield` | `value-searchfield` | Valor del searchfield (valor actual del camp de cerca). | String | `''` (buit) | Opcional |
| `visibilityButtonsMenu` | `visibility-buttons-menu` | Visibilitat dels botons imprimir, configurar i exportar. | Boolean | `true` | Opcional |
| `visibilityCheckboxRow` | `visibility-checkbox-row` | Visibilitat del checkbox de cada fila. | Boolean | `true` | Opcional |
| `visibilityDropdownRow` | `visibility-dropdown-row` | Visibilitat del botó dropdown que mostra la fila secundària. | Boolean | `true` | Opcional |
| `visibilityFilter` | `visibility-filter` | Visibilitat del botó de filtre dels caps de columna. | Boolean | `true` | Opcional |
| `visibilityOrder` | `visibility-order` | Visibilitat del botó d'ordenar dels caps de columna. | Boolean | `true` | Opcional |
| `visibilitySearchfield` | `visibility-searchfield` | Visibilitat del component cercador. | Boolean | `true` | Opcional |

Variants: `mode` = `dynamic` | `static` (per defecte `dynamic`).

**Propietats de l'array `headers`**

| Propietat | Descripció | Obligatorietat | Tipus |
|---|---|---|---|
| `ariaLabelIcon` | Quan la capçalera de la taula porti només una icona, és requisit imprescindible per complir accessibilitat emplenar aquesta property. | Opcional | String |
| `field` | Indica el nom d'aquesta columna a la base de dades. | Obligatori | String |
| `hasSecondaryText` | Indica si les cel·les d'aquesta columna tenen text secundari o no. | Obligatori | Boolean |
| `iconClass` | Si es vol tenir icona al header, afegeix la classe de la icona de bootstrap. | Opcional | String |
| `iconOnly` | Si s'ha afegit la property `iconClass` i es vol que només hi hagi icona al header, sense text, dóna valor `true` a aquesta property. | Opcional | Boolean |
| `iconPosition` | Si s'ha afegit la property `iconClass`, permet indicar la posició de la icona a esquerra o dreta del text. Si no s'indica, es col·locarà a la dreta. Valors: `right` o `left`. | Opcional | String |
| `id` | Identificador de la columna. | Obligatori | String |
| `isLink` | Indica si les cel·les d'aquesta columna seran un enllaç. | Obligatori | Boolean |
| `isList` | Permet introduir una llista desordenada a les cel·les d'aquesta columna. A la propietat `data` caldrà introduir les dades com un array a la columna desitjada. Exemple: `[{"text": "Femení"}, {"text": "Administratiu"}]`. | Opcional | Boolean |
| `isTag` | Indica si les cel·les d'aquesta columna seran una tag. | Obligatori | Boolean |
| `orderButton` | Controla la visibilitat del botó d'ordenació. | Opcional | Boolean |
| `text` | Text de la capçalera. | Obligatori | String |
| `textInfoTooltip` | Text del tooltip que acompanya el text principal. | Opcional | String |
| `visibilityIconTooltip` | Visibilitat de la icona informativa que acompanya el tooltip. | Opcional | Boolean |

**Propietats de l'array `actionsButtonsRow`**

| Propietat | Descripció | Obligatorietat | Tipus |
|---|---|---|---|
| `classNameIcon` | Nom de la classe de la icona de bootstrap. | Obligatori | String |
| `customID` | Identificador del botó. | Obligatori | String |
| `textTooltipButton` | Text tooltip del botó. | Obligatori | String |

**Propietats de l'array `itemsButtonsSelectedOptions`**

| Propietat | Descripció | Obligatorietat | Tipus |
|---|---|---|---|
| `classNameIcon` | Nom de la classe de la icona de bootstrap. | Obligatori | String |
| `customID` | Identificador del botó. | Obligatori | String |
| `isDropdownButton` | Indica si aquest botó és un dropdown amb opcions seleccionables. | Obligatori | Boolean |
| `textTooltipButton` | Text tooltip del botó. | Obligatori | String |

(A l'exemple, el botó dropdown inclou també `itemsDropdownButton`: array d'objectes amb `text`, `classNameIcon` i `customID`.)

**Propietats de l'array `data`**

| Propietat | Descripció | Obligatorietat | Tipus |
|---|---|---|---|
| (Nom de columna a què està lligada aquesta dada; ha de coincidir amb `field` de `headers`) | --- | Obligatori | String |
| `colorTag` | Indica el color de la tag; vegeu la documentació de `tag-component` per conèixer quins valors accepta aquesta propietat. | Opcional | String |
| `extraRowData` | En cas que es vulgui afegir fila extra, aquesta propietat contindrà les dades relacionades amb ella. | Obligatori | String (Object) |
| `iconClass` | Si es vol tenir icona a la cel·la al text primari, afegeix la classe de la icona de bootstrap. | Opcional | String |
| `iconOnly` | Si s'ha afegit `iconClass` i es vol que només hi hagi icona al text primari, sense text, dóna valor `true` a aquesta property. | Opcional | Boolean |
| `iconPosition` | Si s'ha afegit `iconClass`, permet indicar la posició de la icona a esquerra o dreta del text primari. Si no s'indica, es col·locarà a la dreta. Valors: `right` o `left`. | Opcional | String |
| `secondaryIconClass` | Si es vol tenir icona a la cel·la al text secundari, afegeix la classe de la icona de bootstrap. | Opcional | String |
| `secondaryIconPosition` | Si s'ha afegit `secondaryIconClass`, permet indicar la posició de la icona a esquerra o dreta del text secundari. Si no s'indica, es col·locarà a la dreta. Valors: `right` o `left`. | Opcional | String |
| `textAlternativeIcon` | Quan a la cel·la només serà visible la icona, sense text, cal emplenar aquesta property amb un text alternatiu a la icona perquè, en exportar a PDF, XLSX o CSV, la casella no surti en blanc. | Opcional | String |

Nota: si alguna de les dades és un link, dins de l'array d'aquesta dada hi ha d'haver les propertys `primary` i `mode`, essent `mode` `internal` o `external`.

**Propietats de l'objecte `extraRowData`**

Type `content`:

| Propietat | Descripció | Obligatorietat | Tipus |
|---|---|---|---|
| `primaryText` | Text primari | Obligatori | String |
| `secondaryText` | Text secundari | Obligatori | String |
| `type` | Indica la tipologia de la fila extra. En aquest cas, és `content`. | Obligatori | String |

Type `list`:

| Propietat | Descripció | Obligatorietat | Tipus |
|---|---|---|---|
| `dataList` | Array d'una sola propietat, anomenada `text`, amb el valor de cada posició de la llista. | Obligatori | Array |
| `type` | Indica la tipologia de la fila extra. En aquest cas, és `list`. | Obligatori | String |
| `typeList` | Tipus de llista. Pot ser: `ordered` o `unordered`. | Obligatori | String |

Type `link`:

| Propietat | Descripció | Obligatorietat | Tipus |
|---|---|---|---|
| `mode` | Configuració d'enllaç: `external` o `internal`. | Obligatori | String |
| `secondaryText` | Text secundari | Obligatori | String |
| `sizeLink` | Mida del link. Pot ser: `link-small`, `link-medium` o `link-large`. | Obligatori | String |
| `textLink` | Text del link | Obligatori | String |
| `type` | Indica la tipologia de la fila extra. En aquest cas, és `link`. | Obligatori | String |

Type `image`:

| Propietat | Descripció | Obligatorietat | Tipus |
|---|---|---|---|
| `imageUrl` | Ruta de la imatge | Obligatori | String |
| `type` | Indica la tipologia de la fila extra. En aquest cas, és `image`. | Obligatori | String |

**Propietats de l'objecte `filterOptions`**

| Propietat | Descripció | Obligatorietat | Tipus |
|---|---|---|---|
| (Índex de la columna; l'índex 0 és la primera columna amb dades, excloent la columna amb dropdown i checkbox si n'hi hagués) | El valor d'aquesta propietat serà el text d'aquestes opcions filtrades. | Obligatori | Array |

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `blurButton` | Es llança cada cop que es treu el focus en un botó. | --- | `button-component` |
| `focusButton` | Es llança cada cop que es fa focus en un botó. | --- | `button-component` |
| `handlerClick` | Esdeveniment clic heretat de `button-component`. | `id` | `button-component` |
| `optionSelected` | S'emet en fer clic sobre una opció. | índex de l'opció seleccionada | `dropdown-button-component` |
| `actionButtonClicked` | Esdeveniment llançat en fer clic sobre algun dels tres botons d'acció de cada fila. Tipus (PDF): `CustomEvent<{ detail: any; extraData: any; }>` | id del botó i fila a la qual pertany | `dynamic-table-component` |
| `dropdownOptionSelected` | Esdeveniment llançat en seleccionar una opció del botó dropdown del contenidor d'opcions seleccionades. Tipus (PDF): `CustomEvent<{ optionId: string; }>` | `optionId` | `dynamic-table-component` |
| `filterChanged` | Esdeveniment llançat en fer clic en una opció de qualsevol filtre. Tipus (PDF): `CustomEvent<any>` | `columnIndex` `value` `checked` | `dynamic-table-component` |
| `linkClicked` | Esdeveniment llançat en seleccionar un enllaç. Tipus (PDF): `CustomEvent<{ id: string; columnIndex: number; rowIndex: number; }>` | `id` `columnIndex` `rowIndex` | `dynamic-table-component` |
| `orderChanged` | Esdeveniment llançat en prémer algun botó d'ordenació de columna. Tipus (PDF): `CustomEvent<{ state: string; columnIndex: number; field: string; isTag: boolean; sorts: { columnIndex: number; state: string; field: string; isTag: boolean; }[]; }>` | `state` `columnIndex` `field` `isTag` `sorts` | `dynamic-table-component` |
| `rowSelectionChanged` | Es llança quan se selecciona o desselecciona una fila. Tipus (PDF): `CustomEvent<{ id: number; selected: boolean; }>` | `id` (fila a què pertany) `selected` | `dynamic-table-component` |
| `searchBoxBlur` | Esdeveniment llançat en perdre el focus l'input de cerca de cada filtre. Tipus (PDF): `CustomEvent<{ index: number; }>` | `index` | `dynamic-table-component` |
| `searchBoxFocus` | Esdeveniment llançat en rebre el focus l'input de cerca de cada filtre. Tipus (PDF): `CustomEvent<{ index: number; }>` | `index` | `dynamic-table-component` |
| `searchBoxInput` | Esdeveniment llançat en escriure a l'input de cerca de cada filtre. Tipus (PDF): `CustomEvent<{ index: number; value: string; }>` | --- (el PDF indica `index` i `value`) | `dynamic-table-component` |
| `selectAllChanged` | Esdeveniment llançat en seleccionar o deseleccionar el checkbox pare de la taula. Tipus (PDF): `CustomEvent<{ selected: boolean; }>` | `selected` | `dynamic-table-component` |
| `blurLink` | Es llança cada cop que es treu el focus en un enllaç. | --- | `link-component` |
| `focusLink` | Es llança cada cop que es fa focus en un enllaç. | --- | `link-component` |
| `linkEmit` | Es llança cada cop que es fa clic en un enllaç. | `id` | `link-component` |
| `pageChange` | Es llança en prémer sobre una pàgina de la paginació. Conté la pàgina actual i les files per pàgina. | `currentPage` `rowsPerPage` | `pagination-component` |
| `rowsPerPageChange` | Es llança quan se selecciona un valor del dropdown de resultats a mostrar. Conté el valor seleccionat. | `rowsPerPage` | `pagination-component` |
| `valueChange` | Es llança cada vegada que es fa clic al botó de cerca o enter al camp de cerca. | `value` | `searchfield-component` |
| `filterButtonClick` | Detecta el clic al botó de filtre propagant el seu ID. | `ID` | `searchfield-component` |

**Mètodes públics**

| Mètode | Descripció | Paràmetre |
|---|---|---|
| `printTable()` | Imprimeix la taula o els elements seleccionats de la taula. | --- |
| `exportXLSXDoc()` | Exporta la taula a XLSX o els elements seleccionats de la taula. | --- |
| `exportCSVDoc()` | Exporta la taula a CSV o els elements seleccionats de la taula. | --- |
| `updateRowData(rowIndex, fieldName, newValue)` | Actualitza el valor d'un camp concret d'una fila de la taula indicant l'índex de la fila, el nom del camp i el nou valor. | `rowIndex` `fieldName` `newValue` (`rowIndex: number`, `fieldName: string`, `newValue: any`) |

**Depèn de:**
[Botons](component-botons.md) (`button-component`, `dropdown-button-component`), [Grup de botons](component-grup-de-botons.md) (`group-button-component`), [Enllaços](component-enllacos.md) (`link-component`), [Llista](component-llista.md) (`list-component`), [Paginació](component-paginacio.md) (`pagination-component`), [Camp de cerca](component-camp-de-cerca.md) (`searchfield-component`), [Etiquetes](component-etiquetes.md) (`tag-component`), [Indicador de funció](component-indicador-de-funcio.md) (`tooltip-component`).

**Props que accepten JSON:** `actionsButtonsRow`, `data`, `filterOptions`, `headers`, `itemsButtonsSelectedOptions` (estructura a les taules anteriors).

Notes de la font: quan el nombre d'entrades i el valor de la property `totalItems` és igual o inferior a 12, la paginació s'amaga per defecte; no hi ha una property que permeti ocultar-la. L'exemple de paginació següent és al propi entorn de desenvolupament sense fer cap crida a base de dades; en un cas real caldrà fer aquesta crida amb les dades corresponents a la pàgina que es vol mostrar.

**Exemple d'ús**

```html
<!-- /index.html -->
<dynamic-table-component 
      mode="dynamic" 
      text-entry="entrades" 
      right-column-fixed=true 
      left-column-fixed=true
      visibility-filter=true 
      visibility-order=true 
      visibility-dropdown-row=true 
      visibility-checkbox-row=true
      visibility-buttons-menu=true 
      visibility-searchfield=true 
      button-filter-searchfield=true
      text-button-filter-searchfield="Filtrar"
      filter-options='{"0":["Activo","Inactivo"],"1":["Barcelona","Madrid","Valencia"]}' 
      show-id-column=false 
      tooltip-button-filter-searchfield="Filtra resultats"
      tooltip-button-search-searchfield="Cerca entre les files" 
      value-searchfield="" 
      searchfield-id="searchfield-id"
      searchfield-name="searchfield-name" 
      searchfield-text-etiqueta="Cerca un resultat a la taula"
      searchfield-show-tooltip="true"
      searchfield-text-info-tooltip="Text informatiu"
      headers='[
                    { "id":"id","text": "id_usuario", "textInfoTooltip": "Tooltip ID", "hasSecondaryText": true, "field": "id_usuario", "orderButton": true },
                    { "id":"idNombre","text": "Nombre", "textInfoTooltip": "Tooltip nombre", "hasSecondaryText": true, "field": "nombre_usuario", "orderButton": true, "iconClass": "bi-key", "iconPosition": "left", "iconOnly": true },
                    { "id":"idEdad","text": "Edad", "textInfoTooltip": "Tooltip edad", "isTag": true, "field": "edad_usuario", "orderButton": false, "visibilityIconTooltip": false },
                    { "id":"idCorreo","text": "Correo", "textInfoTooltip": "Tooltip correo", "isLink": true, "hasSecondaryText": true, "field": "correo_usuario", "orderButton": true },
                    { "id":"idCiudad","text": "Ciudad", "textInfoTooltip": "Tooltip edad", "field": "ciudad_usuario", "orderButton": false },
                    { "id":"idDNI","text": "DNI", "textInfoTooltip": "Tooltip edad", "field": "dni_usuario", "orderButton": true },
                    { "id":"idGénero","text": "Género", "textInfoTooltip": "Tooltip edad", "field": "genero_usuario", "orderButton": false }
                  ]' 
      actions-buttons-row='[
                    {
                      "classNameIcon": "bi-pencil",
                      "textTooltipButton": "Editar",
                      "customID": "editRowTD"
                    },
                    {
                      "classNameIcon": "bi-trash3",
                      "textTooltipButton": "Eliminar",
                      "customID": "deleteRowTD"
                    },
                    {
                      "classNameIcon": "bi-three-dots-vertical",
                      "textTooltipButton": "Menu desplegable",
                      "customID": "menuRowTD"
                    }
                  ]' 
      items-buttons-selected-options='[
                    {
                      "classNameIcon": "bi-pencil",
                      "textTooltipButton": "Editar",
                      "customID": "editRowTD",
                      "isDropdownButton": false
                    },
                    {
                      "classNameIcon": "bi-trash3",
                      "textTooltipButton": "Eliminar",
                      "customID": "deleteRowTD",
                      "isDropdownButton": false
                    },
                    {
                      "classNameIcon": "bi-three-dots-vertical",
                      "textTooltipButton": "Menu desplegable",
                      "customID": "menuRowTD",
                      "isDropdownButton": true,
                      "itemsDropdownButton": [
                        {
                          "text": "Duplicar",
                          "classNameIcon": "bi-copy",
                          "customID": "duplicateRowTD"
                        },
                        {
                          "text": "Bloquejar", 
                          "classNameIcon": "bi-ban",
                          "customID": "blockRowTD"
                        }
                      ]
                    }
                  ]
                  ' 
      data='[
                  {
                    "id_usuario": 1,
                    "nombre_usuario": { "primary": "Valeria", "iconClass": "bi-1-circle", "iconPosition": "right", "secondary": "Admin", "secondaryIconClass": "bi-info-circle", "secondaryIconPosition": "left", "secondaryIconOnly": true },
                    "edad_usuario": 56,
                    "correo_usuario": { "primary": "valeria@correo.com", "secondary": "Gmail", "mode": "external" },
                    "ciudad_usuario": "Estepona",
                    "dni_usuario": "04021248D",
                    "genero_usuario": [{"text": "Femenino"}, {"text": "Administrativo"}],
                    "extraRowData": {
                      "type": "content",
                      "primaryText": "Cell content",
                      "secondaryText": "Secondary Text"
                    },
                    "colorTag": "color-success"
                  },
                      {
                        "id_usuario": 2, 
                        "nombre_usuario": {"iconClass": "bi-check-circle", "iconOnly": true, "textAlternativeIcon": "Checked"}, 
                        "edad_usuario": 28, 
                        "correo_usuario": { "primary": "valeria@correo.com","mode": "external" }, 
                        "ciudad_usuario": "Estepona", 
                        "dni_usuario": "04021248D", 
                        "genero_usuario": "Femenino", 
                        "extraRowData": {
                          "type": "list",
                          "typeList": "ordered",
                          "dataList": [
                            {"text": "Google"}, {"text": "Bing"}
                          ]
                      }
                    },
                      {
                        "id_usuario": 3, 
                        "nombre_usuario": "Jose", 
                        "edad_usuario": 28, 
                        "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, 
                        "ciudad_usuario": "Estepona", 
                        "dni_usuario": "04021248D", 
                        "genero_usuario": "Femenino", 
                        "extraRowData": {
                          "type": "link",
                          "textLink": "This is a link",
                          "sizeLink": "link-small",
                          "mode": "external",
                          "secondaryText": "Secondary Text"
                        }
                      },
                      {
                        "id_usuario": 4, 
                        "nombre_usuario": "María", 
                        "edad_usuario": 28, 
                        "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, 
                        "ciudad_usuario": "Estepona", 
                        "dni_usuario": "04021248D", 
                        "genero_usuario": "Femenino", 
                        "extraRowData": {
                          "type": "image",
                          "imageUrl": "./assets/hero_banner.png"
                        }
                      },
                      {"id_usuario": 5, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino"},
                      {"id_usuario": 6, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino"},
                      {"id_usuario": 7, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino"},
                      {"id_usuario": 8, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino"},
                      {"id_usuario": 9, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino"},
                      {"id_usuario": 10, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino"},
                      {"id_usuario": 11, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino"},
                      {"id_usuario": 12, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino"}
                    ]' 
      total-items="28">
                      <button-component class-name-button="btn-tertiary" class-name-icon="bi-printer" size-button="btn-size-M"
                        mode-color-button="mode-color-tertiary-light" text="Print" left-icon-chevron="false"
                        right-icon-chevron="false" left-icon=false right-icon=true text-tooltip="" is-spinner=false custom-id=""
                        type-button="button" badge="false" text-badge="12">
                      </button-component>    
                      <button-component class-name-button="btn-tertiary" class-name-icon="bi-printer" size-button="btn-size-M"
                        mode-color-button="mode-color-tertiary-light" text="Print" left-icon-chevron="false"
                        right-icon-chevron="false" left-icon=false right-icon=true text-tooltip="" is-spinner=false custom-id=""
                        type-button="button" badge="false" text-badge="12">
                      </button-component> 
                      <button-component class-name-button="btn-tertiary" class-name-icon="bi-printer" size-button="btn-size-M"
                        mode-color-button="mode-color-tertiary-light" text="Print" left-icon-chevron="false" right-icon-chevron="false"
                        left-icon=false right-icon=true text-tooltip="" is-spinner=false custom-id="" type-button="button" badge="false"
                        text-badge="12">
                      </button-component>
      </dynamic-table-component>
```

Exemple de paginació amb esdeveniments:

```html
<!-- /index.html -->
 <script>
    const table = document.querySelector('dynamic-table-component');
    const page1Data = [
      {
        "id_usuario": 1,
        "nombre_usuario": { "primary": "Valeria", "secondary": "Admin" },
        "edad_usuario": 56,
        "correo_usuario": { "primary": "valeria@correo.com", "secondary": "Gmail", "mode": "external" },
        "ciudad_usuario": "Estepona",
        "dni_usuario": "04021248D",
        "genero_usuario": "Femenino",
        "extraRowData": {
          "type": "content",
          "primaryText": "Cell content",
          "secondaryText": "Secondary Text"
        }
      },
      {
        "id_usuario": 2,
        "nombre_usuario": "Carlos",
        "edad_usuario": 28,
        "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" },
        "ciudad_usuario": "Estepona",
        "dni_usuario": "04021248D",
        "genero_usuario": "Femenino",
        "extraRowData": {
          "type": "list",
          "typeList": "ordered",
          "dataList": [
            { "text": "Google" }, { "text": "Bing" }
          ]
        }
      },
      {
        "id_usuario": 3,
        "nombre_usuario": "Jose",
        "edad_usuario": 28,
        "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" },
        "ciudad_usuario": "Estepona",
        "dni_usuario": "04021248D",
        "genero_usuario": "Femenino",
        "extraRowData": {
          "type": "link",
          "textLink": "This is a link",
          "sizeLink": "link-small",
          "mode": "external",
          "href": "www.google.com",
          "secondaryText": "Secondary Text"
        }
      },
      {
        "id_usuario": 4,
        "nombre_usuario": "María",
        "edad_usuario": 28,
        "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" },
        "ciudad_usuario": "Estepona",
        "dni_usuario": "04021248D",
        "genero_usuario": "Femenino",
        "extraRowData": {
          "type": "image",
          "imageUrl": "./assets/hero_banner.png"
        }
      },
      { "id_usuario": 5, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
      { "id_usuario": 6, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
      { "id_usuario": 7, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
      { "id_usuario": 8, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
      { "id_usuario": 9, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
      { "id_usuario": 10, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
      { "id_usuario": 11, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
      { "id_usuario": 12, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" }
    ]
    const page2Data = [
      { "id_usuario": 13, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
      { "id_usuario": 14, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
      { "id_usuario": 15, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
      { "id_usuario": 16, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
      { "id_usuario": 17, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
      { "id_usuario": 18, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
      { "id_usuario": 19, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
      { "id_usuario": 20, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
      { "id_usuario": 21, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
      { "id_usuario": 22, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
      { "id_usuario": 23, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
      { "id_usuario": 24, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" }
    ];
    const page3Data = [
        { "id_usuario": 25, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
        { "id_usuario": 26, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
        { "id_usuario": 27, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
        { "id_usuario": 28, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
        { "id_usuario": 29, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
        { "id_usuario": 30, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
        { "id_usuario": 31, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
        { "id_usuario": 32, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
        { "id_usuario": 33, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
        { "id_usuario": 34, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
        { "id_usuario": 35, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
        { "id_usuario": 36, "nombre_usuario": "Juan", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" }
      ];
    const page24 = [
        { "id_usuario": 1, "nombre_usuario": "Valeria", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
      { "id_usuario": 2, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
      { "id_usuario": 3, "nombre_usuario": "Jose", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
      { "id_usuario": 4, "nombre_usuario": "María", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
      { "id_usuario": 5, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
      { "id_usuario": 6, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
      { "id_usuario": 7, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
      { "id_usuario": 8, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
      { "id_usuario": 9, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
      { "id_usuario": 10, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
      { "id_usuario": 11, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
      { "id_usuario": 12, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
        { "id_usuario": 13, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
        { "id_usuario": 14, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
        { "id_usuario": 15, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
        { "id_usuario": 16, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
        { "id_usuario": 17, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
        { "id_usuario": 18, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
        { "id_usuario": 19, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
        { "id_usuario": 20, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
        { "id_usuario": 21, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
        { "id_usuario": 22, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
        { "id_usuario": 23, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" },
        { "id_usuario": 24, "nombre_usuario": "Carlos", "edad_usuario": 28, "correo_usuario": { "primary": "valeria@correo.com", "mode": "external" }, "ciudad_usuario": "Estepona", "dni_usuario": "04021248D", "genero_usuario": "Femenino" }
      ];
    
    table.addEventListener('pageChange', function (event) {
      const { currentPage, rowsPerPage } = event.detail;
      console.log(rowsPerPage)
      if (currentPage === 2) {
        table.setAttribute('data', JSON.stringify(page2Data));
      }

      if (currentPage === 1) {
        table.setAttribute('data', JSON.stringify(page1Data));
      }

      if (currentPage  === 1 && rowsPerPage === 24) {
        table.setAttribute('data', JSON.stringify(page24));
      }

      if (currentPage === 3) {
        table.setAttribute('data', JSON.stringify(page3Data));
      }
    });

    table.addEventListener('rowsPerPageChange', function (event) {
      const page = 1;
      const perPage = event.detail;

      if (perPage === 24) {
        table.setAttribute('data', JSON.stringify(page24));
      }
    });
 
    document.querySelector('dynamic-table-component').addEventListener('actionButtonClicked', function (event) {
      const { detail, extraData } = event.detail;

      console.log('Detalle:', detail);
      console.log('Extra data:', extraData);
    });

    document.querySelector('dynamic-table-component').addEventListener('orderChanged', function (event) {
      console.log('Evento capturado:', event.detail.state);
      console.log('Índice de columna:', event.detail.columnIndex);
    });

    document.querySelector('dynamic-table-component').addEventListener('rowSelectionChanged', function (event) {
        console.log('Evento capturado:', event.detail.id);
        console.log('Evento capturado:', event.detail.selected);
      });
  </script>
```

**Exemple d'instància (PDF)**

```html
<dynamic-table-component
actions-buttons-row="texto-ejemplo"
button-filter-searchfield=false
data="texto-ejemplo"
filter-options="texto-ejemplo"
headers="texto-ejemplo"
items-buttons-selected-options="texto-ejemplo"
left-column-fixed=true
mode='dynamic'
right-column-fixed=false
searchfield-id="texto-ejemplo"
searchfield-name="texto-ejemplo"
searchfield-show-tooltip=false
searchfield-text-etiqueta="texto-ejemplo"
searchfield-text-info-tooltip="texto-ejemplo"
show-id-column=false
text-button-filter-searchfield=''
text-entry="texto-ejemplo"
tooltip-button-filter-searchfield='Filtra resultats'
tooltip-button-search-searchfield='Cerca entre les files'
total-items=0
value-searchfield=''
visibility-buttons-menu=true
visibility-checkbox-row=true
visibility-dropdown-row=true
visibility-filter=true
visibility-order=true
visibility-searchfield=true
></dynamic-table-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.0.0 | 12.1.0 | 7 setembre, 2026 | Desenvolupament: S'ha afegit l'opció d'afegir llistes de tipus vinyeta. |
| 12.0.0 | 12.0.3 | 4 setembre, 2026 | Desenvolupament: les icones de les caselles de verificació es modifiquen a SVG |
| 12.0.0 | 12.0.1 | 14 juliol, 2026 | Desenvolupament: s'estableix que per a menys de 12 registres totals s'amaga la paginació completa. Per a valors superiors, s'amagarà la paginació i es mostrarà resultats per pàgina quan s'estiguin mostrant els resultats totals en una mateixa pàgina |
| 12.0.0 | 12.0.0 | 10 juliol, 2026 | Desenvolupament: - S'utilitza el token correcte per al color de text de la capçalera i icona i / - Es corregeixen estils a les cel·les per a paraules sense espais |
| 12.0.0. | 11.0.0 | 19 juny, 2026 | Desenvolupament: l'esdeveniment orderChanged emet més informació per millorar l'ordenació |
| 12.0.0 | 10.1.0 | 29 maig, 2026 | Disseny: S’aplica la funcionalitat de slots a la cel·la slot. Desenvolupament: - Es fan correccions en el comportament del mode focus, d'accessibilitat del lector de pantalla / - S'afegeixen tres noves properties per configurar el text de l'etiqueta del searchfield i de la icona i amb tooltip / - La paginació ja no desapareix en seleccionar al dropdown un valor superior al total d'entrades de la taula. / - Es modifica l'ordre dels botons d'ordenació i filtratge a les capçaleres |
| 11.0.0 | 10.0.0 | 8 maig, 2026 | Disseny: S’inverteix l’ordre dels botons i text a les capçaleres de les columnes (Column headers). Desenvolupament: es corregeix l'índex de les columnes en prémer el botó d'ordenació |
| 10.0.0 | 9.3.0 | 17 abril, 2026 | Disseny: - S’adapten alçades i alineacions d’ombres de les cel·les. / - Es redueix el padding de les cel·les medium a 4 px per alineaments d’ombres. |
| 9.0.0 | 9.3.0 | 20 Març, 2026 | Desenvolupament - Es redueix la mida del fitxer estàtic d'aquest component causat per la importació completa de llibreries a l'inici del component. / - S'introdueixen max-width i min-width per a les cel·les i capçaleres de columna i s'elimina el truncat a la capçalera i links. / - S'arregla error d'accessibilitat a causa del head de la columna d'accions sense text / - S'elimina la llibreria pdfmake del projecte |
| 9.0.0 | 9.2.0 | 27 febrer, 2026 | Disseny: - Es modifica l’alçada de les cel·les i capçalera de fixe a Hug amb un mínim d’alçada (56 o 64px). / - S’eliminen truncats de text. / - El text de l’Action menu es posa a fill. Desenvolupament: les cel·les que són una tag ja són reactives a canvis dinàmics. |
| 8.6.0 | 9.1.0 | 9 febrer, 2026 | Disseny: S’actualitza el component paginació als diferents punts de tall. |
| 8.4.0 | 9.1.0 | 6 febrer, 2026 | Desenvolupament: - S'arreglen problemes d'accessibilitat a causa de l'existència d'etiquetes label no enllaçades correctament. / - L'esdeveniment linkClicked emet a més el rowIndex i s'arregla la visibilitat del filter-container / - S'elimina la property placeholderSearchfield |
| 8.4.0 | 9.0.0 | 12 gener, 2026 | Desenvolupament: Canvis menors d'estils, s'introdueix truncat al text secundari de les files desplegables i s'afegeix una nova mida de tipografia al head de la taula |
| 8.4.0 | 8.5.0 | 5 desembre, 2025 | Disseny: - Es limita el text secundari del desplegable a 2 línies. / - S’afegeix la mida Medium pel titular de les columnes. Desenvolupament: Se substitueix la botonera superior dreta per group-button i s'exposen mètodes per imprimir i exportar taula |
| 8.0.0 | 8.0.0 | 14 novembre, 2025 | Desenvolupament: Nova propietat afegida |
| 8.0.0 | 7.0.0 | 24 octubre, 2025 | Desenvolupament: Nova propietat afegida o eliminada |
| 8.0.0 | 6.2.1 | 3 octubre, 2025 | Desenvolupament: Nova propietat afegida o eliminada |
| 8.0.0 | 6.1.0 | 12 setembre, 2025 | Disseny: Es vinculen els botons d’accions amb els botons de la llibreria. Es vinculen estils de color correctament. Desenvolupament: nova propietat afegida |
| 6.0.0 | 6.0.1 | 28 juliol, 2025 | Desenvolupament de l'evolutiu |
| 6.0.0 | 4.0.1 | 8 juliol, 2025 | Disseny: Se substitueixen els menús desplegables per botons desplegables. |
| 4.0.0 | 4.0.1 | 19 maig, 2025 | Desenvolupament: Resolució de problemes |
| 3.0.0 | 2.0.0 | 31 març, 2025 | Disseny: S’ajusta el comportament del autolayuout (Hug) a la cel·la Empty-Large, Empty-Medium i Empty-Small. |
| 2.4.0 | 2.0.0 | 10 març, 2025 | Disseny: Es canvia el comportament Filled per Hug dels botons d’acció de fila. / Es modifica l’arrodoniment de l’estat focus de les opcions del menú d’accions i s’afegeix un marge global de 4px al menú. |
| 2.3.0 | 2.0.0 | 7 març, 2025 | Desenvolupament: Resolució de problemes. |
| 2.3.0 | 1.1.0 | 17 febrer, 2025 | Desenvolupament: Resolució de problemes. |
| 2.3.0 | 1.0.0 | 31 gener, 2025 | Disseny: - S’ha modificat els components de forma que ara els diferents estats estan en les cel·les de fila i capçalera de taula. / - S’ha afegit el botó de filtres a la capçalera de taula. / - S’ha creat el component Taula on es pot editar per files. / - S’ha afegit l’opció de scroll horitzontal amb primera i última columna fixada. Desenvolupament del component. |
| 2.2.0 | No aplica | 20 gener, 2025 | Sense canvis. |
| 2.1.0 | No aplica | 04 desembre, 2024 | Sense canvis. |
| 2.0.0 | No aplica | 02 desembre, 2024 | Sense canvis. |
| 1.1.0 | No aplica | 22 novembre, 2024 | Sense canvis. |
| 1.1.0 | No aplica | 19 novembre, 2024 | Disseny i documentació del component |

## Vegeu també
- [Acordió](component-acordio.md)
- [Llista](component-llista.md)
- [Paginació](component-paginacio.md)
- [Botons](component-botons.md)
- [Grup de botons](component-grup-de-botons.md)
- [Enllaços](component-enllacos.md)
- [Etiquetes](component-etiquetes.md)
- [Camp de cerca](component-camp-de-cerca.md)
- [Indicador de funció](component-indicador-de-funcio.md)
