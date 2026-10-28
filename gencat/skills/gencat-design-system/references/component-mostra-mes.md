# Mostra més (Show more)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/06a441 · Web component: `<show-more-component>` (paquet core) · Font actualitzada el 2026-10-22 · Extret el 2026-10-28

## Què és i quan usar-lo
És un botó que permet als usuaris expandir contingut addicional d'una secció que inicialment està ocult.

El component Mostrar més és ideal per a **mostrar contingut rellevant que**, tot i ser important, **no necessita ser visible immediatament**. Aquest contingut pot incloure informació addicional, detalls extres o dades complementàries que enriqueixen l'experiència de l'usuari.

El component **permet mantenir la interfície visualment neta i manejable**, especialment en situacions en què l'espai és limitat, com en dispositius mòbils. Es presenta primer la informació més essencial, mentre que el contingut addicional es pot revelar sota demanda de l'usuari, garantint una experiència optimitzada i completa sense sobrecarregar la pantalla.

A diferència de la finestra emergent, que dona detalls extres d'un contingut específic, el botó de Mostrar més **presenta una versió més extensa del contingut inicial.**

## Quan NO usar-lo / alternatives
- **Contingut crític:** no facis servir aquest component per amagar informació essencial que tots els usuaris necessiten veure per completar una tasca o prendre una decisió. El contingut ocult ha de ser opcional o complementari.
- **Quan es vol centrar l'atenció de l'usuari en un determinat context** i la informació ha de ser concreta, com en [Modals](component-modals.md) o [Avisos](component-avisos.md).
- **Formularis o processos** on l'usuari necessita veure tots els camps o instruccions alhora per evitar errors o confusió.
- **Per jerarquitzar continguts** en diferents seccions. Per a pàgines amb diferents seccions i contingut extens on cal estructurar el contingut en apartats, s'utilitza l'[Acordió](component-acordio.md).

## Anatomia
Figma: Show more Button [Collapsed = True]. És un botó (mida small) amb text que canvia segons l'estat col·lapsat o no.

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Collapsed | True / False | False |
| State | Default / Hover / Focus / Pressed | Default |

El component mostrar més està creat a partir del component [Botons](component-botons.md), però només compta amb la versió de mida petita (small).

## Comportament i interacció
El comportament de mostrar o amagar contingut del component "mostra més" s'aplica a totes les columnes d'aquella secció, per tal que no es creïn desplaçaments de contingut o espais en blanc que descompensin l'estructura de la pàgina.

## Contingut i microcopy
Textos d'exemple: "Mostra tots els passos" (col·lapsat) / "Mostra menys passos" (no col·lapsat).

## Bones pràctiques

### Contingut de l'etiqueta
- **FER:** Utilitza una etiqueta descriptiva del contingut que es mostrarà. Aquesta no ha de ser excessivament extensa (màxima 30 caràcters).
- **FER:** Utilitza el verb "mostra" juntament amb l'adverbi "més" o "menys" i el nom d'allò que es mostrarà (enllaços, passos, estats, etc.).
- **NO FER:** Evita usar l'etiqueta "mostra més" o similars on no hi ha context.
- **FER:** Adapta el text de l'acció del component quan aquest està desplegat, de forma que indiqui el nou comportament d'amagar contingut. Aquest text s'ha d'adaptar segons el context.

### Adaptació amb altres elements
- **FER:** Adapta la visualització del component quan aquest es combina amb altres més complexos.
- **FER:** Si el contingut amagat és text i no es mostra completament, trunca'l al final de l'última línia visible amb punts suspensius.
- **NO FER:** No incloguis informació molt extensa amagada.

### Ús
- **NO FER:** No utilitzis el "mostrar més" de forma niada o dins d'altres components amb funcionalitats similars (com l'acordió).
- **NO FER:** No l'utilitzis de forma excessiva, per no augmentar la complexitat de la pàgina.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG):
- **1.4.1 Ús del color (A):** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per diferenciar els estats s'inclouen subratllats i es juga amb la presència de farciment i el gruix de la vora. (https://www.w3.org/Translations/WCAG22-ca/#use-of-color · https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **1.4.3 Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. (https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum · https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **1.4.4 Canvia la mida del text (AA):** excepte subtítols i imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. (https://www.w3.org/Translations/WCAG22-ca/#resize-text · https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **1.4.11 Contrast d'elements no textuals (AA):** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. (https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast · https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **2.1.1 Teclat (A):** tota la funcionalitat del contingut es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. (https://www.w3.org/Translations/WCAG22-ca/#keyboard · https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **2.4.7 Focus visible (AA):** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. (https://www.w3.org/Translations/WCAG22-ca/#focus-visible · https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- **3.2.2 A l'entrada (A):** canviar la configuració de qualsevol component de la interfície d'usuari no provoca automàticament un canvi de context tret que l'usuari hagi estat informat del comportament abans d'utilitzar el component. (https://www.w3.org/WAI/WCAG21/Understanding/on-input.html)

## Implementació (component web)

### `<show-more-component>`
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Obligatorietat (lloc) | Tipus | Per defecte (PDF) |
|---|---|---|---|---|---|
| `textCollapsed` | `text-collapsed` | Text del botó col·lapsat. | Obligatori | String | undefined |
| `textNoCollapsed` | `text-no-collapsed` | Text del botó no col·lapsat. | Obligatori | String | undefined |
| `idShowMore` | `id-show-more` | ID per identificar l'element (PDF: identificador del botó "mostrar més") | Opcional | String | undefined |

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre | Origen | Tipus (PDF) |
|---|---|---|---|---|
| `blurButton` | Es llança cada cop que es treu el focus en un botó. | - | `button-component` | |
| `focusButton` | Es llança cada cop que es fa focus en un botó. | - | `button-component` | |
| `handlerClick` | Es llança cada cop que es fa clic en un botó i com a paràmetre conté les dades de l'esdeveniment. | id | `button-component` | |
| `toggle` | Indica si el botó està en mode col·lapsat o no (PDF: s'emet quan l'estat del component s'alterna) | - | `show-more-component` | `CustomEvent<boolean>` |

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<show-more-component
  id-show-more="show-more"
  text-collapsed="Mostra tots els passos"
  text-no-collapsed="Mostra menys passos"
></show-more-component>
```

**Exemple d'instància (PDF)**

```html
<show-more-component
id-show-more="texto-ejemplo"
text-collapsed="texto-ejemplo"
text-no-collapsed="texto-ejemplo"
></show-more-component>
```

**Depèn de:** `button-component` ([Botons](component-botons.md)).

**S'utilitza a:** `chip-component` ([Xips](component-xips.md)), `dropdown-menu-component` ([Menú desplegable](component-menu-desplegable.md)), `filter-component` ([Filtres](component-filtres.md)), `link-list-component` ([Llista d'enllaços](component-llista-d-enllacos.md)), `status-tracker-component` ([Rastrejador d'estat](component-rastrejador-d-estat.md)), `summary-list-component` ([Dades estructurades](component-dades-estructurades.md)), `timeline-component` ([Línia de temps](component-linia-de-temps.md)).

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 11.0.0 | 4.0.1 | 8 maig, 2026 | Disseny: reset del component botó per arreglar la interacció del hover. |
| 4.0.0 | 4.0.1 | 19 maig, 2025 | Desenvolupament: resolució de problemes |
| 2.3.0 | 1.0.0 | 31 gener, 2025 | Sense canvis |
| 2.2.0 | 0.1.1 | 20 gener, 2025 | Sense canvis |
| 2.1.0 | 0.1.1 | 04 desembre, 2024 | Sense canvis |
| 2.0.0 | 0.1.0 | 02 desembre, 2024 | Sense canvis |
| 1.1.0 | 0.1.0 | 22 novembre, 2024 | Desenvolupament del component |
| 1.1.0 | 0.0.4 | 19 novembre, 2024 | Disseny i documentació del component |

## Vegeu també
- [Acordió](component-acordio.md): per mostrar o amagar informació individualment d'un llistat d'ítems.
- [Botons](component-botons.md)
