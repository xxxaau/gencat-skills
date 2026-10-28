# Indicador de funció (Tooltip)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/56cb35 · Web component: `<tooltip-component>` (paquet core) · Font actualitzada el 2026-10-06 · Extret el 2026-10-28

## Què és i quan usar-lo
Contenidor que mostra temporalment un text breu que s'activa quan l'usuari passa el cursor per sobre d'una icona o activador.

Els indicadors de funció **proporcionen informació addicional sobre un element quan l'usuari passa el cursor per sobre o hi fa clic**. Apareixen en forma de petits quadres de text emergents que contenen explicacions, descripcions o consells relacionats amb l'element sobre el qual s'està passant el cursor.

Quan s'utilitza:
- Per **ajudar** l'usuari a **comprendre el significat** o el propòsit d'un element que no té etiqueta, com ara icones o botons.
- Per **mostrar la versió completa d'un text truncat**.
- Per mostrar el **text alternatiu** d'una imatge.
- Per afegir **informació contextual** (no essencial) a un element que necessita més context, especialment quan hi ha poc espai (en aquests casos s'utilitza la icona de l'indicador de funció).

## Quan NO usar-lo / alternatives
- Per a la **informació que és vital** per completar una tasca: es fa servir el text d'ajuda o text maquetat, que sempre és visible i accessible.
- Per afegir **contingut obvi o redundant**.
- Per a informació crítica o decisions: [Modals](component-modals.md). Per a notificacions breus i temporals que no requereixen acció: [Notificació emergent](component-notificacio-emergent.md) (toast). Per mostrar informació contextual: [Descripció emergent](component-descripcio-emergent.md).

## Anatomia
Figma: Tooltip [Show Pointer = True, Tooltip text = Tooltip text, Pointer alignment = Bottom-center].

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Pointer alignment | Bottom-left / Bottom-center / Bottom-right; Top-left / Top-center / Top-right; Left-top / Left-center / Left-bottom; Right-top / Right-center / Right-bottom | Top-center |

Variant Figma (estats): Tooltip [Show Pointer = True, Tooltip text = Tooltip text, Pointer alignment = Bottom-center].

## Mides i espaiats
- Amplada màxima de **320 dp** i limitació de **cent vint caràcters**.
- Alçada màxima de **152 px** al text (historial de versions).
- Distància entre l'indicador de funció i l'element referenciat: **vuit píxels**, per garantir una distància adequada i mantenir la claredat visual.

## Comportament i interacció
Nota: la font escriu en alguns punts "indicador de càrrega" quan es refereix a l'indicador de funció; aquí s'unifica com a "indicador de funció". [a verificar]

### Interacció en escriptori
- S'activen en l'**estat focus** o quan l'usuari passa el **cursor** per sobre de l'element activador (hover). L'indicador es manté visible mentre l'usuari estigui sobre l'element activador o sobre la finestra emergent de l'indicador.
- Els **associats a la icona d'ajuda** o informació apareixen **immediatament**. Per als **altres elements** convencionals d'interfície d'usuari apareixen **al cap d'1,5 segons**, ja que no s'indiquen de manera clara i que apareguin immediatament seria massa intrusiu.
- **Desapareixen** quan l'usuari **deixa de passar el cursor** per sobre de l'element activador o la finestra emergent, o quan l'element activador **deixa d'estar en estat focus**. L'usuari també pot tancar-lo manualment a través de la icona de tancament del pop-up o prement la **tecla "Esc"** (la font escriu "scape").

### Interacció en mòbil i tauleta
En pantalles tàctils, s'activen i desapareixen de maneres diferents segons el cas d'ús:
- Per **afegir informació contextual** a un element que necessita més context: fent **clic** a la icona de l'indicador.
- Per **afegir el significat o el propòsit** d'un element de la interfície que no té etiqueta: **maquetant el text** directament al costat de la icona o botó. Valora també utilitzar el **component "hotspot"** com a recurs d'onboarding per presentar les funcionalitats de les icones el primer cop que l'usuari accedeix a una aplicació o pàgina web.
- Per mostrar la **versió completa d'un text truncat** que no és interactiu: fent clic sobre el text.
- Per mostrar el **text alternatiu d'una imatge:** com a text descriptiu de la imatge.

### Posició
- Es poden col·locar en **dotze posicions** al voltant de l'element activador: a sobre, a sota, a l'esquerra, a la dreta, i alineats al centre, a la dreta o a l'esquerra. Per defecte s'utilitza la versió **"top-center"**, col·locant la finestra emergent centrada a sota de l'element activador [a verificar: el nom "top-center" i "a sota" que dona la font]. La posició pot variar si oculta informació relacionada o no hi ha prou espai en pantalla.
- Per exemple, en els camps de text és recomanable col·locar l'indicador per sobre de l'etiqueta per evitar tapar el camp que l'usuari ha de completar.

### Adaptació responsiva
Amplada màxima de 320 dp i limitació de cent vint caràcters.

## Bones pràctiques

### Posició
- **FER:** Posiciona l'ajuda emergent perquè no bloquegi o tapi el contingut relacionat. Quan bloquegen el contingut amb el qual estan relacionats, fan que els usuaris repeteixin passos.
- **NO FER:** No posicionis l'ajuda emergent de forma que bloquegi o tapi el contingut directament relacionat.

### Contingut
- **FER:** Inclou contingut breu i limitat a descripcions addicionals relacionades directament amb un element o control concret de la pàgina.
- **NO FER:** No incloguis contingut extens ni informació no relacionada directament amb un element o control concret de la pàgina.

### Contrast
- **FER:** Utilitza el color predefinit que assegura un bon contrast.
- **NO FER:** No utilitzis un color diferent del predefinit.

### Elements interactius
- **NO FER:** No incloguis elements interactius ni altres elements visuals, com icones, imatges, enllaços o botons, dins d'un indicador de funció.

## Accessibilitat
Pautes WCAG 2.2:
- **Contrast mínim (AA) – 1.4.3:** contrast d'almenys 4,5:1 als elements textuals; els inactius o deshabilitats en són excepció. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA) – 1.4.4:** el text es pot canviar de mida fins al 200 % sense pèrdua de contingut ni de funcionalitat (excepte subtítols i imatges de text). [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contingut en passar el cursor o al focus (AA) – 1.4.13:** quan la interacció amb el punter o el focus del teclat fa visible contingut addicional i després s'oculta, cal que sigui cert: **descartable** (hi ha un mecanisme per descartar-lo sense moure el punter o el focus, tret que comuniqui un error d'entrada o no enfosqueixi ni substitueixi un altre contingut); **hoverable** (el punter pot moure's sobre el contingut addicional sense que desaparegui); **persistent** (es manté visible fins que s'elimina l'activador del cursor o el focus, l'usuari el descarta o la informació ja no és vàlida). [CAT](https://www.w3.org/Translations/WCAG22-ca/#content-on-hover-or-focus) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/content-on-hover-or-focus.html)
- **Teclat (A) – 2.1.1:** tota la funcionalitat es pot operar amb teclat sense requerir temps específics per a pulsacions de tecles individuals. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Focus visible (AA) – 2.4.7:** la navegació amb teclat pels elements és visible a través d'un cercle. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

### Navegació per teclat

| Tecla | Acció |
|---|---|
| Tabulació | Visualització de la informació de l'indicador de funció |
| Esc | Tancar la visualització |

## Implementació (component web)

### `<tooltip-component>`

El component envolta l'element activador (slot per defecte). No hi ha capítol PDF per a aquest component a la v12.0.0; les dades provenen de la pàgina del lloc.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Obligatori |
|---|---|---|---|---|
| `message` | `message` | Missatge de l'interior de l'indicador de funció. | string | Obligatori |
| `placement` | `placement` | Indica a quin costat s'ha de posicionar el tooltip si hi ha espai. | string | Opcional |
| `tooltipButton` | `tooltip-button` | Indica si l'element anirà acompanyant un botó. | boolean | Opcional |

**Variants**

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `placement` | `top` `right` `bottom` `left` | `-` |

**Utilitzat per (paquet core):** `button-component` ([Botons](component-botons.md)), `checkbox-component` ([Casella de selecció](component-casella-de-seleccio.md)), `chip-component` ([Xips](component-xips.md)), `dropdown-component` ([Desplegable](component-desplegable.md)), `dynamic-table-component` ([Taules dinàmiques](component-taules-dinamiques.md)), `file-uploader-component` ([Carregador d'arxius](component-carregador-d-arxius.md)), `filter-component` ([Filtres](component-filtres.md)), `inputtext-component` ([Camp d'entrada](component-camp-d-entrada.md)), `progress-bar-component` ([Barra de progrés](component-barra-de-progres.md)), `radio-component` ([Botó d'opció](component-boto-d-opcio.md)), `searchfield-component` ([Camp de cerca](component-camp-de-cerca.md)), `slider-component` ([Control de rang](component-control-de-rang.md)), `status-tracker-component` ([Rastrejador d'estat](component-rastrejador-d-estat.md)), `table-of-contents-component` ([Taula de continguts](component-taula-de-continguts.md)), `tag-component` ([Etiquetes](component-etiquetes.md)), `textarea-component` ([Àrea de text](component-area-de-text.md)), `vertical-tabs-component` ([Pestanyes](component-pestanyes.md)).

**Utilitzat per (paquet conversacional):** `chat-button-component` ([Botó de xat](component-boto-de-xat.md)).

**Exemple d'ús (pàgina)**

```html
<!-- /index.html -->
<tooltip-component 
  message="Missatge de l'interior del tooltip"
  placement="left"
  tooltip-button="false">
        <link-component 
          text="Enllaç" 
          class-name-icon="bi-box-arrow-up-right" 
          target="_blank"
          class-name-link="link-small" 
          href-link="https://www.google.com" 
          visibility-icon="true"
        ></link-component>
</tooltip-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 8.2.0 | 12.1.2 | 5 octubre, 2026 | Desenvolupament: es millora el comportament del tooltip en els botons. |
| 8.2.0 | 10.1.0 | 29 maig, 2026 | Desenvolupament: s'arregla el posicionament de la propietat `placement`. |
| 8.2.0 | 10.0.0 | 8 maig, 2026 | Desenvolupament: s'afegeix la propietat `placement` per controlar la posició. |
| 8.2.0 | 9.3.0 | 20 març, 2026 | Desenvolupament: s'elimina l'etiqueta slot que envolta tot el component. |
| 8.2.0 | 9.0.0 | 12 gener, 2025 | Desenvolupament: ajustaments que regulen la visibilitat (data tal com consta a la font). |
| 8.2.0 | 8.5.0 | 5 desembre, 2025 | Desenvolupament: resolució de problemes menors. |
| 8.2.0 | 8.0.0 | 14 novembre, 2025 | Desenvolupament: resolució de problemes. |
| 8.2.0 | 6.1.0 | 27 octubre, 2025 | Disseny: s'aplica alçada màxima de 152 px al text. |
| 2.3.0 | 6.1.0 | 12 setembre, 2025 | Desenvolupament: resolució de problemes. |
| 2.3.0 | 6.0.0 | 3 juliol, 2025 | Desenvolupament: resolució de problemes. |
| 2.3.0 | 1.1.0 | 17 febrer, 2025 | Desenvolupament: resolució de problemes. |
| 2.3.0 | 1.0.0 | 31 gener, 2025 | Sense canvis. |
| 2.2.0 | 0.1.1 | 20 gener, 2025 | Sense canvis. |
| 2.1.0 | 0.1.1 | 04 desembre, 2024 | Sense canvis. |
| 2.0.0 | 0.1.0 | 02 desembre, 2024 | Sense canvis. |
| 1.1.0 | 0.1.0 | 22 novembre, 2024 | Sense canvis. |
| 1.1.0 | 0.0.4 | 18 novembre, 2024 | Sense canvis. |
| 1.0.0 | 0.0.3 | 1 novembre, 2024 | Disseny, desenvolupament i documentació del component. |

> Nota: no hi ha capítol d'API de component web (`tooltip-component`) documentat a la v12.0.0 del PDF.

## Vegeu també
- [Modals](component-modals.md): per proporcionar informació crítica o quan cal demanar una acció decisiva.
- [Notificació emergent](component-notificacio-emergent.md): per a notificacions breus i temporals que no requereixen acció de l'usuari.
- [Descripció emergent](component-descripcio-emergent.md): per mostrar informació contextual.
