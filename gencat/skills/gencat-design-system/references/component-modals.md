# Modals (Modal)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/66aa32 · Web component: `<modal-component>` (paquet core) · Font actualitzada el 2026-10-15 · Extret el 2026-10-28

## Què és i quan usar-lo
Presenta contingut d'una manera separada i enfocada que impedeix la interacció amb la vista principal i requereix una acció explícita per part de l'usuari per a tancar-ho.

Les modals apareixen com a finestres sobre la pàgina actual en la qual es troba l'usuari i **proporcionen informació crítica o demanen una decisió**. Desactiven totes les funcionalitats de l'aplicació quan apareixen i romanen a la pantalla fins que es confirmen, descarten o s'hagi realitzat una acció necessària.

Quan s'utilitza:
- Per notificar a l'usuari sobre un error urgent. Per determinar si l'error és prou greu per necessitar una modal cal considerar si:
  - L'error és irreversible i provocarà pèrdua d'informació.
  - El problema serà més fàcil o més complex de corregir si l'atenció de l'usuari es desplaça de la tasca que està realitzant. En un formulari anirà acompanyat de l'input, però per indicar que l'ordinador es reiniciarà en 10 segons seria millor utilitzar una modal.
- Per demanar una informació que és necessària per continuar amb la tasca. S'inclouen camps de text o selectors.
- Per mostrar informació crítica que requereix una tasca, decisió o reconeixement específic de l'usuari.
- Per confirmar la decisió d'un usuari amb relació a una acció.
- Per a tasques curtes i poc freqüents, com ara tasques d'edició o gestió.

## Quan NO usar-lo / alternatives
- Si el contingut no està relacionat amb el flux de treball actual.
- Per mostrar grans quantitats de dades o fluxos amb passos múltiples.
- Per recrear una aplicació o una pàgina completa.
- Si la modal no apareix com a resultat d'una acció.
- Si un usuari necessita fer una tasca de manera repetida: considera que la tasca es pugui fer des de la pàgina principal.
- Alternatives: [Avisos](component-avisos.md) per comunicar un estat que és específic d'una pàgina o característica; [Indicador de funció](component-indicador-de-funcio.md) per mostrar un text breu en passar el cursor per sobre d'una icona o activador.

## Anatomia
1. **Capçalera**:
   1. Icona d'estat (opcional)
   2. Títol
   3. Botó de tancament
2. **Cos**: missatge de text i/o diferents components segons cada cas d'ús (camps de text, àrees de text, botons de selecció, etc.). Es recomana utilitzar el mínim contingut possible per a evitar un desplaçament excessiu (es recomana fins a un màxim de set elements).
3. **Peu**: inclou una o dues accions.

### Errors
Per als missatges d'error es farà servir la icona d'error a la part superior esquerra. En aquests casos, el cos de la modal únicament inclourà text. Les modals sempre inclouran la icona de tancament.

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Extra large - Medium / Small | Extra large - Medium |
| Title | Títol | - |
| Show Icon State | True / False | False |
| Show buttons | True / False | True |
| Show secondary button | True / False | True |
| Show close button | True / False | False |
| Show scroll bar | True / False | - |
| Content Slot | Content | - |
| Icon State | Error / Alert / Success | Error |

Variants Figma (`Modal`): Show Scroll bar = True | False; Show Icon State = False | True; Show Secondary Button = True | False; Show Close button = True | False; Title = Títol; Show buttons = True | False; Content slot = (slot de contingut); Breakpoint = Extra Large - Medium | Small. Estats de l'icona (`_State Icon Modal`): Icon state = Error | Alert | Success.

## Mides i espaiats
- **Escriptori** (pantalles superiors a 511 px d'amplada): s'adapta a l'espai del contenidor, amb amplada màxima de 600 px i mínima de 480 px. Alçada: s'adapta al contingut fins a ocupar un màxim del 80% de la pantalla.
- **Mòbil** (pantalles inferiors a 511 px d'amplada): s'adapta al contenidor, amb amplada màxima de 479 px. Alçada: s'adapta al contingut fins a ocupar un màxim del 80% de la pantalla.
- Espaiat entre slots: 24 px (en lloc de 32 px, des de la versió Figma 9.0.0). La icona d'error s'alinea amb el títol i té una mida de 24 px.
- Overlay (superposició): valor #333333 amb una opacitat del 25%.

## Comportament i interacció
- L'usuari pot tancar la modal mitjançant el botó de tancar (X) o prement la tecla "Esc". La modal **no** es tancarà si l'usuari fa clic fora de la modal.
- Quan apareix la modal es desactiven els elements inferiors afegint un overlay (superposició) de valor #333333 amb una opacitat del 25%.
- Les àrees de text usades dins de les modals no disposaran de la funcionalitat de redimensionament. La mida vindrà marcada segons el cas d'ús.
- **Posició:** la modal sempre anirà posicionada al centre de la pantalla.

### Desbordament de contingut
- **Extra Large - Medium** (variant amb peu fix): si el contingut de la modal ocupa més que l'espai disponible dins del contenidor, apareixerà un desplaçament al contenidor del cos de la modal, mantenint el botó de tancament i el peu de la modal fixos i sempre visibles a la pantalla.
- **Extra Large - Medium** (segona variant, tal com surt a la font): apareixerà un desplaçament al contenidor del cos de la modal, mantenint només el botó de tancament fix. [a verificar: la font repeteix l'etiqueta "Extra Large - Medium" per a les dues variants; la segona correspon probablement al punt de tall Small, on el contingut (botons inclosos) fa scroll excepte la creu de tancament]
- En mòbil, quan l'usuari clica sobre un camp de text i apareix el teclat, es farà un desplaçament automàtic dins de la pròpia modal perquè el camp sempre estigui visible.

## Bones pràctiques

**Ús**
- **FER:** Escriu una acció primària positiva en relació amb el verb que indica la modal, o de confirmació.
- **NO FER:** No escriguis una acció primària que no té relació amb el verb que indica la modal, o de confirmació.
- **NO FER:** No usis una modal en fluxos de gran risc com un procés de pagament.
- **NO FER:** No usis una modal per a la presa de decisions complexes que requereixin fonts d'informació addicionals no disponibles a la modal.
- **NO FER:** No usis una modal per a informació que necessita ser comparada.
- **NO FER:** No utilitzis modals niades.
- **NO FER:** No usis modals que ocupin tot l'espai de pantalla. Utilitza les mides definides en el component.
- **NO FER:** No usis una modal per proporcionar més explicacions sobre un terme específic de la pàgina.
- **NO FER:** No incloguis components complexos com taules amb diferents funcionalitats.
- **NO FER:** No mostris la modal abans que el contingut de la pàgina s'hagi carregat. Sempre s'ha d'activar a partir d'una acció de l'usuari.

## Accessibilitat

### Pautes WCAG
- **Orientació (AA)**: el contingut s'adapta a les diferents orientacions de la pantalla, com ara vertical o horitzontal, cosa que permet visualitzar el contingut. [1.3.4 Orientació - CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Contrast mínim (AA)**: els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. [1.4.3 Contrast mínim - CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA)**: excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [1.4.4 Canvia la mida del text - CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA)**: els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [1.4.11 Contrast d'elements no textuals - CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A)**: tota la funcionalitat del contingut (navegar pels diferents botons) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [2.1.1 Teclat - CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Sense trampa de teclat (A)**: si el focus del teclat es pot moure a un component de la pàgina mitjançant una interfície de teclat, llavors el focus es pot allunyar d'aquest component utilitzant només una interfície de teclat. Amb la tecla "Esc" l'usuari pot sortir de la modal. [2.1.2 Sense trampa de teclat - CAT](https://www.w3.org/Translations/WCAG22-ca/#no-keyboard-trap) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/no-keyboard-trap)
- **Ordre del focus (A)**: les modals presenten un ordre lògic del focus dels elements interns per facilitar la navegació per teclat o altres dispositius d'entrada. L'ordre ha de seguir el flux de la informació o les tasques que s'estan presentant, i ha de ser el següent: (1) primer element interactiu al cos de la modal començant per la part superior esquerra; (2) desplaçament d'esquerra a dreta i de dalt a baix per la resta dels elements del cos; (3) acció primària; (4) acció secundària; (5) acció terciària; (6) icona de tancament. [2.4.3 Ordre del focus - CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-order) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-order)
- **Focus visible (AA)**: la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [2.4.7 Focus visible - CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- **Identificació d'errors (A)**: si es detecta un error en el component, s'identifica clarament mitjançant un canvi de color i gruix de la vora i amb la indicació visual (icona) i textual (descripció de l'error). [3.3.1 Identificació d'errors - CAT](https://www.w3.org/Translations/WCAG22-ca/#error-identification) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/error-identification)
- **Focus no ocult (AA)**: la capa de superposició de la modal no pot ocultar cap element que tingui el focus de teclat. Mentre la modal és oberta, el focus ha de quedar atrapat dins seu i no pot accedir als elements de la pàgina de darrere. Aquesta consideració és especialment rellevant en dispositius mòbils i tauletes amb zoom de pantalla activat. [2.4.11 Focus no ocult - CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-not-obscured-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-not-obscured-minimum)

### Navegació per teclat

| Tecla | Acció |
|---|---|
| Tabulació | Navegar al següent element interactiu |
| Shift + Tabulació | Navegar a l'anterior element interactiu |
| Intro / Enter | Activa l'element seleccionat |
| Esc | Tanca el diàleg |

### Focus
- Es desplaça el focus dins del diàleg quan s'activa.
- Després d'obrir el diàleg, el focus inicial s'hauria de posar al primer element interactiu de la modal.
- El focus ha d'estar atrapat dins del diàleg i no s'ha de moure fora de la modal fins que no es tanqui.
- Després de tancar un diàleg modal, el focus hauria de tornar a l'element que va invocar la modal.

## Implementació (component web)

### `<modal-component>`

Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte |
|---|---|---|---|---|
| `iconTitle` | `icon-title` | Indica quina icona es mostrarà. Opcions: `alert`, `error`, `success`. Opcional | string | `undefined` |
| `titleModal` | `title-modal` | Títol de la modal. **Obligatori** | string | `undefined` |
| `tooltipButtonClose` | `tooltip-button-close` | Tooltip del botó de tancament de la modal. Opcional | string | `undefined` |
| `visibilityIconClose` | `visibility-icon-close` | Indica si es mostra una aspa per tancar la modal. Opcional | boolean | `undefined` |

**Variants**

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `iconTitle` | `alert` `error` `success` | - |

**Slots** (components que s'introdueixen per slot)
- El **contingut del body de la modal** s'introdueix mitjançant `slot="body"` i ha d'estar embolcallat dins d'un `div` amb la classe `body-content`, que s'utilitza per aplicar els estils corresponents.
- Els **botons del footer** de la modal s'introdueixen mitjançant `slot="footer"`.

**Mètodes públics**

| Mètode | Descripció | Paràmetre |
|---|---|---|
| `openModalMethod(focusFirst: boolean = this.shouldAutoFocusOnOpen())` | Obre la modal | `focusFirst` (boolean; per defecte `this.shouldAutoFocusOnOpen()`) |
| `closeModalMethod()` | Tanca la modal | - |

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `modalToggle` | Es llança en obrir o tancar la modal. Si està oberta el seu paràmetre booleà serà `true` i si està tancada, `false` (tipus `CustomEvent<boolean>`) | `open` | `modal-component` |
| `blurButton` | Es llança cada cop que es treu el focus en un botó | - | `button-component` |
| `focusButton` | Es llança cada cop que es fa focus en un botó | - | `button-component` |
| `handlerClick` | Es llança cada cop que es fa clic en un botó i com a paràmetre conté les dades de l'esdeveniment | `id` | `button-component` |

**Depèn de**: `button-component` ([Botons](component-botons.md)), `group-button-component` ([Grup de botons](component-grup-de-botons.md)).

**Utilitzat per**: core: `header-public-component` ([Capçalera web pública](component-capcalera-web-publica.md)); conversational: `chat-input-component` ([Camp d'entrada de xat](component-camp-d-entrada-de-xat.md)), `floating-chat-container-component` ([Xat flotant](patro-xat-flotant.md)).

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<p id="modal-button">This click open the modal</p>

<modal-component 
  id="modal" 
  title-modal="Títol" 
  icon-title="alert" 
  visibility-icon-close="true"  
  tooltip-button-close="Tanca el modal"
  >
</modal-component>

<script>
    document.getElementById('modal-button').addEventListener('click', () => {
      const modal = document.getElementById('modal');

      Array.from(modal.querySelectorAll('button-component[slot="footer"]')).forEach(btn => btn.remove());

      const btn1 = document.createElement('button-component');
      btn1.setAttribute('slot', 'footer');
      btn1.setAttribute('class-name-button', 'btn-primary');
      btn1.setAttribute('size-button', 'btn-size-S');
      btn1.setAttribute('mode-color-button', 'mode-color-primary-light');
      btn1.setAttribute('text', 'Acció primaria');
      btn1.setAttribute('left-icon-chevron', 'false');
      btn1.setAttribute('right-icon-chevron', 'false');
      btn1.setAttribute('left-icon', 'false');
      btn1.setAttribute('class-name-icon', '');
      btn1.setAttribute('text-alternative', '');
      btn1.setAttribute('aria-label', 'Acció primaria');

      const btn2 = document.createElement('button-component');
      btn2.setAttribute('slot', 'footer');
      btn2.setAttribute('class-name-button', 'btn-secundary');
      btn2.setAttribute('size-button', 'btn-size-S');
      btn2.setAttribute('mode-color-button', 'mode-color-secundary-light');
      btn2.setAttribute('text', 'Acció secundaria');
      btn2.setAttribute('left-icon-chevron', 'false');
      btn2.setAttribute('right-icon-chevron', 'false');
      btn2.setAttribute('left-icon', 'false');
      btn2.setAttribute('class-name-icon', '');
      btn2.setAttribute('text-alternative', '');
      btn2.setAttribute('aria-label', 'Acció secundaria');

      modal.appendChild(btn1);
      modal.appendChild(btn2);

      Array.from(modal.querySelectorAll('[slot="body"]')).forEach(el => el.remove());

      const bodyContent = document.createElement('div');
      bodyContent.setAttribute('slot', 'body');
      bodyContent.innerHTML = `
        <inputtext-component
          placeholder="Write here..."
          text-etiqueta="Etiqueta"
          text-help="Text d’ajuda"
          size="small"
          text-error="Text error"
          show-text-error="false"
          is-disabled="false"
          visibility-text-help="true"
          icon-calendar=false
          text-info-tooltip="Text Tooltip"
          delete-cross=false
          text-alternative-error="Text d'error input text 1"
          show-tooltip="false"
          show-popover="true"
          value="Text"
          popover-config='{
                  "text-open": "Ajuda",
                  "padding": 20,
                  "size-text-open": "small",
                  "popover-title": "Títol de prova",
                  "description": "Descripció del popover",
                  "version": "contextual",
                  "contextual-image-url": "/assets/photos/img_1.png",
                  "img-description": "Descripció de la imatge",
                  "link-text-popover": "Més informació"
            }'>
        </inputtext-component>
        <content-tree-component tree='[
          {
            "label": "Principal",
            "children": [
              {
                "label": "Blog",
                "tags": [
                  { "text": "NW", "color": "color-lila", "textAlternative": "Notícia Web" }
                ],
                "children": [
                  {
                    "label": "2024",
                    "children": [
                      {
                        "label": "Enero",
                        "isLink": true,
                        "tags": [
                          { "text": "OK", "color": "color-verd", "textAlternative": "Òptim Kriteri" }
                        ]
                      },
                      {
                        "label": "Febrero",
                        "isLink": true,
                        "tags": [
                          { "text": "RV", "color": "color-taronja", "textAlternative": "Revisar Vista" },
                          { "text": "DR", "color": "color-vermell", "textAlternative": "Dades Ràpides" }
                        ]
                      }
                    ]
                  },
                  {
                    "label": "2023",
                    "tags": [
                      { "text": "HI", "color": "color-gris", "textAlternative": "Històric Important" }
                    ],
                    "children": [
                      {
                        "label": "Marzo",
                        "isLink": true
                      }
                    ]
                  }
                ]
              },
              {
                "label": "Prueba",
                "isLink": true
              },
              {
                "label": "Proyectos",
                "tags": [
                  { "text": "AC", "color": "color-verd", "textAlternative": "Acceptat Correctament" }
                ],
                "children": [
                  {
                    "label": "Proyecto A",
                    "isLink": true,
                    "tags": [
                      { "text": "IN", "color": "color-blau", "textAlternative": "Iniciat Nou" }
                    ]
                  },
                  {
                    "label": "Proyecto B",
                    "isLink": true,
                    "tags": [
                      { "text": "UR", "color": "color-verd", "textAlternative": "Urgent Requereix" }
                    ],
                    "children": [
                      {
                        "label": "Subproyecto B1",
                        "isLink": true
                      },
                      {
                        "label": "Subproyecto B2",
                        "isLink": true,
                        "tags": [
                          { "text": "NW", "color": "color-gris", "textAlternative": "Notícia Web" },
                          { "text": "RV", "color": "color-neutre", "textAlternative": "Revisar Vista" }
                        ]
                      }
                    ]
                  }
                ]
              },
              {
                "label": "Contacto",
                "isLink": true,
                "tags": [
                  { "text": "ON", "color": "color-blau", "textAlternative": "On Line" },
                  { "text": "SP", "color": "color-verd", "textAlternative": "Suport Professional" }
                ]
              }
            ]
          }
        ]'></content-tree-component>
        <radio-component
          class="radio-component"
          text-etiqueta="Etiqueta prueba"
          is-disabled="false"
          text-error=""
          value="opcio1"
          group="radio0"
          text-info-tooltip="Texto Tooltip"
          visibility-description="true"
          show-tooltip="true"
          radio-props='[
                  { "option": "Opció 1", "description": "Descripció 1", "value": "opcio1" },
                  { "option": "Opció 2", "description": "Descripció 2", "value": "opcio2" },
                  { "option": "Opció 3", "description": "Descripció 3", "value": "opcio3" }
                ]'
          ></radio-component>
      `;
  
      modal.appendChild(bodyContent);

      modal.openModalMethod();
    });
  </script>
```

**Exemple d'instància (PDF)**

```html
<modal-component
icon-title="alert"
title-modal="texto-ejemplo"
tooltip-button-close="texto-ejemplo"
visibility-icon-close=false
></modal-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 10.0.0 | 12.0.3 | 4 setembre, 2026 | Desenvolupament: es corregeix el problema pel qual la modal es tancava en prémer la tecla ESC mentre un altre component, com un datepicker o un desplegable, estava actiu |
| 12.3.0 | 12.0.3 | 31 juliol, 2026 | Disseny: es modifica l'adaptació flotant de la barra d'scroll |
| 10.0.0 | 12.0.0 | 10 juliol, 2026 | Desenvolupament: s'utilitza el token correcte per al color de text del títol |
| 10.0.0 | 11.0.0 | 19 juny, 2026 | Desenvolupament: es fan correccions per al lector de pantalla quan s'obre la modal amb la tecla enter |
| 10.0.0 | 10.0.0 | 8 maig, 2026 | Desenvolupament: correcció de posicionament dels elements del body i footer |
| 10.0.0 | 9.4.0 | 17 abril, 2026 | Disseny: es posa la barra d'scroll en posició absoluta en el punt de tall Extra Large - Medium. Desenvolupament: s'ha corregit el comportament del focus en obrir la modal; s'ha eliminat la propietat `visibilityIconError` i s'ha creat la propietat `iconTitle` |
| 9.1.0 | 9.3.0 | 20 març, 2026 | Disseny: s'han afegit estats a l'icona de la modal; s'ha aplicat "hug" a un frame de la modal small; s'ha modificat la propietat "Show close button" per tal que apliqui a tot el contenidor. Desenvolupament: ajust espai entre els slot content |
| 9.0.0 | 9.2.0 | 21 febrer, 2026 | Disseny: s'ajusta l'espaiat entre slots a 24 px (en lloc de 32 px); s'elimina l'amplada màxima del contenidor dels slots per permetre un comportament més flexible; es retira l'opció Clip content del contenidor dels slots i es trasllada al frame principal de la modal; s'optimitza el frame del scroll: s'escurça i es configura amb posició absoluta; s'alinea la icona d'error amb el títol i se'n redueix la mida a 24 px |
| 8.6.0 | 9.2.0 | 27 febrer, 2026 | Desenvolupament: es fan millores d'accessibilitat |
| 8.6.0 | 9.1.0 | 9 febrer, 2026 | Disseny: s'han afegit slots a la modal per permetre inserir els components que es vulguin (amb llista de preferred); a desktop, el títol fa scroll juntament amb el contingut; a mobile, tot el contingut fa scroll (botons inclosos), excepte la creu de tancament; s'ha aplicat la variable de color al títol |
| 8.2.0 | 9.1.0 | 6 febrer, 2026 | Desenvolupament: es fan adaptacions d'accessibilitat pel que fa a mides de font extra gran i augment de pantalla |
| 8.2.0 | 6.1.0 | 27 octubre, 2025 | Disseny: revisió d'estils tipogràfics |
| 8.0.0 | 6.1.0 | 12 setembre, 2025 | Disseny: es revincula el checkbox (apareixia com "restore component"). Desenvolupament: nova propietat afegida |
| 4.0.0 | 6.0.0 | 3 juliol, 2025 | Desenvolupament: resolució de problemes |
| 5.0.0 | 4.0.1 | 10 juny, 2025 | Disseny: es modifica la posició dels botons en els dos punts de tall |
| 4.0.0 | 4.0.1 | 19 maig, 2025 | Desenvolupament: resolució de problemes |
| 2.3.0 | 1.0.0 | 31 gener, 2025 | Sense canvis |
| 2.2.0 | 0.1.1 | 20 gener, 2025 | Sense canvis |
| 2.1.0 | 0.1.1 | 04 desembre, 2024 | Sense canvis |
| 2.0.0 | 0.1.0 | 02 desembre, 2024 | Sense canvis |
| 1.1.0 | 0.1.0 | 22 novembre, 2024 | Desenvolupament del component |
| 1.1.0 | 0.0.4 | 19 novembre, 2024 | Disseny del component i actualització de la documentació |

## Vegeu també
- [Avisos](component-avisos.md)
- [Indicador de funció](component-indicador-de-funcio.md)
- [Botons](component-botons.md)
- [Grup de botons](component-grup-de-botons.md)
