# Filtres (Filters)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/914590 · Web component: `<filter-component>` (paquet core) · Font actualitzada el 2026-10-22 · Extret el 2026-10-28

## Què és i quan usar-lo
Conjunt d'elements interactius que permeten refinar i limitar els resultats d'una llista.

Els filtres són una eina clau, especialment en sistemes amb grans volums de dades, ja que permeten als usuaris trobar de manera ràpida i eficient la informació rellevant. Milloren la rellevància dels resultats, redueixen la càrrega cognitiva, estalvien temps i ofereixen una experiència més personalitzada.

### Estructura i agrupació dels filtres
- **Blocs individuals:** s'utilitzen quan els filtres són independents i no tenen relació entre ells. Cada filtre funciona de manera autònoma i es pot aplicar per separat. Exemples: Tipus de document, Data de publicació, Nota de tall, etc.
- **Agrupació per categories:** s'utilitzen quan diversos filtres estan relacionats temàticament. És recomanable agrupar-los sota una mateixa categoria per reforçar-ne la relació i facilitar la cerca. Exemples: dins la categoria Ubicació, podríem trobar: Comarca, Municipi, Districte, Ciutat.
  Figma: Estructura i agrupació dels filtres.

### Quan s'utilitza
- Quan es mostra una gran quantitat o varietat de contingut (ex: llistes llargues, dades amb múltiples atributs).
- Quan cal refinar o acotar resultats segons diversos criteris (ex: dates, estats, ubicació, categories).

## Quan NO usar-lo / alternatives
- Quan hi ha poc contingut: no cal filtrar si la informació és molt limitada o específica (ex: una llista amb només 3 o 4 elements).
- Quan els criteris són massa simples: si els filtres no aporten valor real, poden resultar innecessaris (ex: un filtre "actiu/inactiu" en una llista molt curta).
- Quan els filtres poden generar confusió perquè són poc intuïtius (ex: filtres amb noms tècnics o poc familiars per a l'usuari).

## Anatomia
Figma: Anatomia (DOC_Filters / Disseny / Anatomia).

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Show more button | True / False | True |
| Slot | Content | - |
| Text | Títol | - |
| Show Tooltip | True / False | True |
| Collapsed | True / False | True |
| Show Title | True / False | True |

### Vistes
El tipus de vista determina si el panell de filtres és **visible** o **ocult**, i per tant quin **tipus de comportament** s'activa.

| Vista | Dispositiu | Panell | Tipus de filtratge |
|---|---|---|---|
| Targeta | Escriptori / Tauleta | Visible (esquerra) | Dinàmic |
| Llista | Escriptori / Tauleta | Visible (esquerra) | Dinàmic |
| Taula | Escriptori / Tauleta | Ocult (panell emergent) | Per blocs |
| Mapa | Escriptori / Tauleta | Ocult (panell emergent) | Per blocs |
| Totes les vistes | Mòbil | Ocult (panell emergent) | Per blocs |

### Selecció del component segons el nombre d'opcions
Per definir el component d'un filtre multiselecció, cal tenir en compte el nombre d'opcions, la longitud dels literals, la freqüència d'ús i la necessitat de veure-les totes.

| Nombre d'opcions | Component recomanat | Quan utilitzar-lo |
|---|---|---|
| Fins a 5 | Llista de caselles de selecció | Utilitza-la quan totes les opcions siguin rellevants i sigui útil veure-les i comparar-les directament. |
| De 6 a 15 | Caselles de selecció amb "Mostra'n més" | Prioritza aquesta opció quan l'usuari necessiti descobrir, revisar o comparar les opcions. |
| De 6 a 15 | Desplegable multiselecció | Utilitza'l quan el filtre sigui secundari, l'espai sigui limitat o les opcions siguin fàcilment previsibles o localitzables, per exemple, si segueixen un ordre alfabètic o una classificació coneguda. |
| Més de 15 | Desplegable multiselecció amb cercador | Utilitza'l quan el nombre d'opcions faci poc eficient recórrer tota la llista i l'usuari pugui cercar una opció pel seu nom o terme conegut. |

## Mides i espaiats
- Amplada màxima: 456 px (augmentada des de la versió Figma 10.0.0; vegeu Historial de versions).

## Comportament i interacció
El sistema de filtres contempla dos comportaments principals segons el context d'ús i el tipus de visualització segons el dispositiu.

### Filtres aplicats
**Filtratge dinàmic.** Els filtres s'apliquen de manera automàtica i progressiva, sense cap acció addicional de l'usuari.
- Cada vegada que l'usuari interactua amb un filtre (marca, desmarca, selecciona...), s'inicia un temporitzador de 500 ms.
- Si es produeix una nova interacció abans que acabi aquest temps, el comptador es reinicia. D'aquesta manera, es retarda la petició fins que l'usuari ha acabat d'aplicar tots els filtres desitjats, evitant crides múltiples i innecessàries al sistema.
- Quan el temps finalitza i no hi ha cap altra interacció, la vista de resultats es refresca automàticament amb els nous filtres aplicats.
- Aquest refresc es fa de forma suau i progressiva, mostrant un efecte skeleton per indicar visualment que els resultats s'estan actualitzant.

**Filtratge per blocs.** Els filtres es configuren combinant diverses opcions, però no s'apliquen fins que l'usuari prem el botó "Aplicar filtres".
- L'usuari pot seleccionar, escriure o modificar múltiples opcions dins del panell, però no es fa cap crida al sistema ni es refresca la vista fins que es confirma manualment.
- Un cop l'usuari prem el botó "Aplicar filtres", el panell es tanca automàticament i es retorna a la pàgina de resultats amb els filtres aplicats.
- El botó "Netejar" permet restablir ràpidament tots els filtres al seu estat inicial.

### Adaptació responsiva
- Punt de tall large i extra-large:
  - Vista targeta i llista: els filtres es mantenen fixos al lateral esquerre de la pantalla i es mostren de manera visible i permanent.
  - Vista mapa i taula: els filtres estan ocults per defecte. Es mostren en un panell emergent quan es fa clic al botó "Filtres".
- Punt de tall medium i small:
  - Totes les vistes (targeta, llista, mapa i taula): els filtres es mostren sempre en un panell emergent, activat mitjançant el botó "Filtres".

## Contingut i microcopy
- Botons: "Mostra més" / "Mostra'n més", "Filtres", "Aplicar filtres", "Netejar".
- Exemple de títol de secció: "Ubicació".

## Bones pràctiques
### Literals
Títols de secció:
- **FER:** Els títols han de ser curts, clars i informatius (ex: "Ubicació").
- **NO FER:** Cal evitar títols llargs, duplicats, genèrics o amb llenguatge tècnic que pugui confondre l'usuari.
- **NO FER:** No s'ha de deixar cap bloc sense títol.

Descripció:
- **FER:** Quan calgui afegir una descripció del títol, es recomana mostrar un indicador de funció.

### Visualització
Vistes:
- **FER:** En pantalles grans, a la vista de targetes i llistes, els filtres es col·loquen al lateral esquerre.
- **FER:** A la vista de mapa i taula, s'utilitzen panells ocults.
- **FER:** En pantalles petites, els filtres es mostren sempre mitjançant panells ocults, independentment de la vista.

Mostratge parcial ("Veure més"):
- **FER:** En els camps d'entrada, desplegables i selectors de data, quan hi ha més de tres components disponibles, per defecte només se'n mostren tres, juntament amb el botó "Mostra més".
- **FER:** En caselles de selecció i botons d'opció, si hi ha més de cinc elements, per defecte només se'n mostren cinc, juntament amb el botó "Mostra més".
- **FER:** En xips, si hi ha molts elements, es mostren fins a dues línies per defecte, juntament amb el botó "Mostra més".

### Estructura i agrupació
Jerarquia:
- **FER:** Els filtres més importants o habituals s'han de mostrar al principi del panell per facilitar-ne l'accés.

Blocs individuals vs categories:
- **FER:** Es poden combinar blocs individuals i agrupacions per categories dins del mateix espai de filtres, si té sentit segons el contingut.
- **FER:** En agrupacions per categories, s'utilitzen desplegables, selectors de data i camps de text.
- **FER:** Les caselles de selecció, els botons d'opció i els xips sempre es comporten com a blocs individuals, encara que comparteixin temàtica.
- **NO FER:** No s'han d'agrupar les caselles de selecció, els botons d'opció i els xips.

Etiquetes:
- **FER:** En blocs individuals, s'elimina l'etiqueta del component.
- **NO FER:** En blocs individuals, no cal afegir l'etiqueta.
- **FER:** En agrupacions per categories, es conserven les etiquetes dels diferents components per reforçar la relació semàntica i funcional dels camps.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG):
- **Ús del color (A)** (1.4.1): el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual (per diferenciar els diferents estats). [CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA)** (1.4.3): els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA)** (1.4.4): excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA)** (1.4.11): els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Espaiat del text (AA)** (1.4.12): quan es desenvolupa contingut amb llenguatges de marcatge que permeten aplicar propietats d'estil de text, no es perd cap contingut ni funcionalitat si s'ajusten: alçada de línia (interlineat) d'almenys 1,5 vegades la mida de la lletra; espaiat entre els paràgrafs d'almenys dues vegades la mida de la lletra; espaiat entre lletres (tracking) d'almenys 0,12 vegades la mida de la lletra; espaiat entre paraules d'almenys 0,16 vegades la mida de la lletra. [CAT](https://www.w3.org/Translations/WCAG22-ca/#text-spacing) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/text-spacing)
- **Teclat (A)** (2.1.1): tota la funcionalitat del contingut (navegar pels diferents components) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Ordre del focus (A)** (2.4.3): [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-order) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-order)
  - En pàgina: quan es mostren els filtres en el cos de la pàgina, el focus es desplaça pels diferents elements interactius per ordre d'aparició mitjançant la tecla de tabulació (Figma: Accessibilitat_pàgina01). Si algun dels components té un comportament específic, com el desplegable, segueix el comportament establert en el component (Figma: Accessibilitat_pàgina02).
  - En panell: quan els filtres estan amagats darrere un botó que obre un panell contextual, el focus va primer al botó de filtres i en activar-lo s'obre el panell emergent. Ordre: 1) Primer element interactiu (Tab 1): en obrir el panell, el focus es col·loca sobre el primer element interactiu dels filtres; 2) Resta d'elements (Tab 2 - 4): segueix el mateix comportament passant pels diferents filtres; 3) Peu del panell (Tab 5 - 6): botons inferiors (aplica filtres i esborra filtres, per aquest ordre); 4) Botó de tancament del panell (Tab 7). (Figma: Accessibilitat_panell.)
- **Focus visible (AA)** (2.4.7): la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

### Navegació per teclat

| Tecla | Acció |
|---|---|
| Tabulació | Navega al següent element interactiu |
| Shift + Tabulació | Navega a l'anterior element interactiu |
| Enter | Activa l'element interactiu |

## Implementació (component web)

### `<filter-component>`
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat (lloc) |
|---|---|---|---|---|---|
| `filterTitle` | `filter-title` | Títol principal del filtre. | string | `undefined` | Opcional |
| `textInfoTooltip` | `text-info-tooltip` | Text informatiu del tooltip. | string | `undefined` | Opcional |

**Esdeveniments** (el PDF indica "sense esdeveniments declarats"; el lloc llista els dels subcomponents)

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `blurButton` | Es llança cada vegada que es treu el focus d'un botó del component. | - | `button-component` |
| `focusButton` | Es llança cada cop que es fa focus en un botó del component. | - | `button-component` |
| `handlerClick` | Es llança cada cop que es fa clic en un botó; com a paràmetre conté les dades de l'esdeveniment | id | `button-component` |
| `toggle` | Indica si el botó de "veure més" està en mode col·lapsat o expandit. | - | `show-more-component` |

**Slot.** El contingut de l'interior de les tabs es pot introduir com a slot per permetre l'addició d'HTML. S'ha d'introduir l'slot tal com indica l'exemple d'ús: l'atribut `slot` del `div` que contingui l'slot ha de ser `"filter-slot"`; addicionalment, s'ha d'afegir la classe `filter-slot` al contenidor de l'slot.

**Depèn de:** `tooltip-component` ([Indicador de funció](component-indicador-de-funcio.md)), `show-more-component` ([Mostra més](component-mostra-mes.md)).

**Exemple d'ús**

```html
<!-- /index.html -->
<filter-component filter-title="Mis Filtros" text-info-tooltip="Mis filtros">
  <div slot="filter-slot" class="filter-slot">
    <dropdown-component
      slot="filter-slot"
      text-dropdown="Selecciona una opció"
      multiple="single"
      text-etiqueta="Selección única"
      text-error="Text d'error"
      size="small"
      text-info-tooltip="Texto Tooltip"
      text-alternative-error="Texto alternativo dropdown"
      show-tooltip="false"
      options='[
                  {
                    "value": "Opció 1",
                    "label": "Opció 1"
                  },
                  {
                    "value": "Opció 2",
                    "label": "Opció 2"
                  },
                  {
                    "value": "Opció 3",
                    "label": "Opció 3 "
                  },
                  {
                    "value": "Opció 4",
                    "label": "Opció 4"
                  },
                  {
                    "value": "Opció 5",
                    "label": "Opció 5"
                  },
                  {
                    "value": "Opció 6",
                    "label": "Opció 6"
                  },
                  {
                    "value": "Opció 7",
                    "label": "Opció 7"
                  },
                  {
                    "value": "Opció 8",
                    "label": "Opció 8"
                  },
                  {
                    "value": "Opció 9",
                    "label": "Opció 9"
                  }
                ]
                '>
    </dropdown-component>
  </div>
</filter-component>
```

Exemple d'instància (PDF):

```html
<filter-component
filter-title="texto-ejemplo"
text-info-tooltip="texto-ejemplo"
></filter-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 10.0.0 | 12.0.0 | 10 juliol, 2026 | Desenvolupament: s'utilitza el token correcte per al color de la icona i del títol |
| 10.0.0 | 9.1.0 | 17 abril, 2026 | Disseny: s'han aplicat slots pel contingut del component. Augment de l'amplada màxima a 456 px. |
| 9.0.0 | 9.1.0 | 10 febrer, 2026 | Disseny: s'ha eliminat el truncament del títol; en conseqüència, s'ha eliminat la segona línia del títol. Per tant, el tooltip queda alineat a la dreta i a dalt. |
| 8.1.0 | 9.1.0 | 6 febrer, 2026 | Desenvolupament: adaptacions d'accessibilitat pel que fa a mides de font extra gran i augment de pantalla |
| 8.1.0 | 7.0.0 | 24 octubre, 2025 | Desenvolupament: resolució de problemes |
| 8.1.0 | 6.0.0 | 6 octubre, 2025 | Disseny: es fa una inicialització (reset) a les instàncies del slot. |
| 5.0.0 | 6.0.0 | 3 juliol, 2025 | Desenvolupament del component botó desplegable |
| 5.0.0 | No aplica | 10 juny, 2025 | Disseny del component. |

## Vegeu també
- [Camp d'entrada](component-camp-d-entrada.md): per introduir i recopilar dades de manera interactiva.
- [Camp de cerca](component-camp-de-cerca.md): per realitzar cerques o explorar un lloc web o aplicació.
- [Desplegable](component-desplegable.md): per seleccionar elements d'una llista d'opcions predefinides.
- [Calendari](component-calendari.md): per seleccionar una data, o un rang de dates.
- [Casella de selecció](component-casella-de-seleccio.md): per seleccionar una o més opcions d'una llista predefinida.
- [Botó d'opció](component-boto-d-opcio.md): per seleccionar una opció dins d'un conjunt d'opcions mútuament excloents.
- [Botons](component-botons.md): permet a l'usuari dur a terme accions en una pàgina o pantalla.
- [Xips](component-xips.md): permet visualitzar els filtres que ja han estat seleccionats.
- [Indicador de funció](component-indicador-de-funcio.md): per mostrar un text breu en passar el cursor per sobre d'una icona o activador.
- [Panell emergent](component-panell-emergent.md): per oferir funcionalitats complementàries de manera contextual i no intrusiva.
- [Mostra més](component-mostra-mes.md): permet als usuaris expandir contingut addicional d'una secció.
