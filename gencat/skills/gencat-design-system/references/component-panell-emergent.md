# Panell emergent (Sheet)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/718daf · Web component: `<sheet-component>` (paquet core) · Font actualitzada el 2026-10-22 · Extret el 2026-10-28

## Què és i quan usar-lo
Contenidor que permet mostrar contingut addicional, com filtres o accions.

Els panells emergents són contenidors desplegables que es mostren o s'amaguen segons la interacció de l'usuari. Permeten oferir funcionalitats complementàries de manera contextual i no intrusiva, adaptant-se a les característiques de cada dispositiu.

Quan s'utilitza:
- Quan la disposició (*layout*) no té prou espai per mostrar de forma permanent informació addicional, com filtres o accions avançades.
- Quan es vol evitar que la pantalla es vegi massa carregada d'accions.

## Quan NO usar-lo / alternatives
- Quan la disposició (*layout*) ja té prou espai per mostrar la informació de forma directa i permanent.
- Quan no hi ha prou contingut o complexitat per justificar un panell ocult.
- No s'utilitza per a formularis llargs, processos pas a pas ni per mostrar alertes (vegeu Bones pràctiques).

## Anatomia
Figma: Sheet [Show Scroll = False, Show Button Group = True, Slot, Type = Lateral, Breakpoint = Extra Large - Medium]. La font no inclou llista numerada de parts. Elements esmentats a la documentació: títol a la capçalera, botó de tancament, àrea de contingut (slot) i grup de botons (botonera) fix.

## Variants, tipus i estats

### Generals

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Type | Lateral / Inferior | Lateral |
| Breakpoint | Extra Large - Medium / Small | Extra Large - Medium |
| Show Scroll | True / False | True |
| Show Button Group | True / False | True |
| Slot | Content | - |

Variants Figma (tipus i punts de tall del tipus lateral): Sheet [Show Scroll = False, Show Button Group = True, Slot, Type = Lateral, Breakpoint = Extra Large - Medium].

### Grup de botons
Encara que el component permet la disposició vertical, aquesta no està pensada per al panell emergent. [Nota literal de la font: "Utilitza sempre la disposició vertical."] [a verificar: la nota diu que el component "permet la disposició vertical" però que no està pensada per al panell; la instrucció final i les bones pràctiques demanen vertical]

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Layout | Horizontal / Vertical | Horizontal |
| Button Slot | Slot | - |

## Mides i espaiats
- Pantalles grans (escriptori i tauleta): ocupa un 40 % de l'amplada total de la pantalla; amplada fixa, no s'adapta al contingut.
- Alçada a pantalles grans: fixa i igual a l'alçada visible del dispositiu, sense desbordar ni adaptar-se al contingut.
- Pantalles petites (mòbil): el panell s'adapta segons el contingut, fins a ocupar el 100 % de la pantalla si cal. No és expansible manualment per l'usuari.
- Figma: alçada_do, alçada mobile_do.

## Comportament i interacció

### Adaptació responsiva
Pantalles grans (escriptori i tauleta):
- Ocupa un 40 % de l'amplada total de la pantalla.
- L'alçada del panell és fixa i igual a l'alçada visible del dispositiu, sense desbordar ni adaptar-se al contingut.
- Es manté fixat al lateral dret mentre està actiu.
- L'amplada és fixa, no s'adapta al contingut.

Pantalles petites (mòbil):
- El panell s'adapta segons el contingut, fins a ocupar el 100 % de la pantalla si cal.
- No és expansible manualment per part de l'usuari.

### Àrea de desplaçament
- Pantalles grans (escriptori i tauleta): quan el contingut del panell supera l'alçada disponible de la pantalla, el botó de tancament i el grup de botons de la part inferior es mantenen fixos. La resta del contingut queda dins de l'àrea desplaçable.
- Pantalles petites (mòbil): quan el contingut supera l'alçada disponible, el botó de tancament es manté fix a la part superior del panell. La resta del contingut, inclosa la botonera, queda dins de l'àrea desplaçable.

### Aparició
- Pantalles grans (escriptori i tauleta): el panell apareix amb una animació de dreta a esquerra. Es plega amb la mateixa animació en sentit invers.
- Pantalles petites (mòbil): el panell apareix des de la part inferior amb una animació de baix a dalt. Es tanca amb una animació de dalt a baix.
- Figma: aparició, aparició_02.

## Bones pràctiques

Context d'ús:
- **FER:** utilitza el panell emergent per a filtres o, en el cas del mòbil, també per a accions secundàries.
- **NO FER:** no utilitzis el panell emergent per a formularis llargs o processos pas a pas, ni per mostrar alertes.

Posició:
- **FER:** en pantalles grans, col·loca el panell emergent al costat dret.
- **NO FER:** en pantalles grans, no col·loquis el panell al costat esquerre.

Estructura:
- **FER:** inclou un títol clar i contextual a la capçalera del panell.
- **NO FER:** no ometis el títol ni n'utilitzis un de genèric que no aporti context.
- **NO FER:** en pantalles grans (filtres) no oblidis incloure una botonera fixa, obligant l'usuari a fer scroll per accedir a les accions. Capçalera i grup de botons han de ser sempre fixos.
- **FER:** utilitza un botó de tancament per sortir del panell.
- **FER:** col·loca els botons de la botonera en vertical, l'un sota l'altre.
- **NO FER:** no col·loquis els botons de la botonera en horitzontal, un al costat de l'altre.

## Accessibilitat

### Pautes d'accessibilitat del contingut web (WCAG)
- **Ús del color (A) — 1.4.1:** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual (per diferenciar els diferents estats). [CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA) — 1.4.3:** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA) — 1.4.4:** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA) — 1.4.11:** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A) — 2.1.1:** tota la funcionalitat del contingut (navegar pels diferents elements) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Ordre del focus (A) — 2.4.3:** l'ordre del focus en panells emergents, tant lateral com inferior, és: (1) primer element interactiu del cos (Tab 1); (2) resta d'elements interactius del cos (Tab 2 - 4); (3) zona botonera: botó primari (Tab 5), botó secundari (Tab 6), botó terciari; (4) botó de tancament del panell (Tab 7). [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-order) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-order)
- **Focus visible (AA) — 2.4.7:** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- **Focus no ocult (AA) — 2.4.11:** mentre el panell emergent és obert, el focus ha de quedar atrapat dins seu i no pot accedir als elements de la pàgina de darrere. En tancar-se, el focus ha de tornar a l'element que el va activar. El panell emergent no pot ocultar cap element que tingui el focus de teclat. Especialment rellevant en dispositius mòbils i tauletes amb zoom de pantalla activat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-not-obscured-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-not-obscured-minimum)

### Navegació per teclat

| Tecla | Acció |
|---|---|
| Tabulació | Navega al següent element interactiu |
| Shift + Tabulació | Navega a l'anterior element interactiu |
| Enter | Activa l'element interactiu |
| Esc | Tanca el panell emergent. |

## Implementació (component web)

### `<sheet-component>`
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat (lloc) |
|---|---|---|---|---|---|
| `buttonsOrientation` | `buttons-orientation` | Orientació del grup de botons. Opcions: `horizontal`, `vertical` | `string` | `horizontal` | Opcional |
| `groupButtons` | `group-buttons` | Grup de botons ubicats al peu del panell. Accepta array d'objectes (`GroupButtonItem[]`) o string JSON | `GroupButtonItem[] \| string` | - | Obligatori |
| `sheetTitle` | `sheet-title` | Títol del panell emergent | `string` | `undefined` | Obligatori |
| `textTooltipCloseSheet` | `text-tooltip-close-sheet` | Text del tooltip que es mostra en passar el cursor (hover) sobre el botó de tancar el panell emergent | `string` | `Tancar panell emergent` | Opcional |

**Propietats de l'array `groupButtons`**

| Propietat | Descripció | Atribut | Obligatorietat | Tipus |
|---|---|---|---|---|
| `props` | Propietats del component button. Consulteu la documentació de `button-component` ([Botons](component-botons.md)) per conèixer quines propietats es poden incloure | `props` | Obligatori | Array |

**Variants**

| Propietat | Valors | Per defecte |
|---|---|---|
| `buttonsOrientation` | `horizontal`, `vertical` | `horizontal` |
| `textTooltipCloseSheet` | - | Tancar panell emergent |

**Mètodes públics**

Per obrir el panell emergent cal que un `button-component` o un altre component tingui associat un esdeveniment de clic que activi el mètode que obre el panell. Aquest mètode és `openSheet()`.

| Mètode | Acció | Paràmetre |
|---|---|---|
| `handleFilterScroll()` | Recalcula l'alçada i l'scroll intern del panell | - |
| `openSheet()` | Obre el panell emergent (signatura al PDF: `openSheet(shouldFocusFirst: boolean = this.shouldAutoFocusOnOpen())`) | `closed: true` (lloc) |

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre / tipus | Origen |
|---|---|---|---|
| `blurButton` | Es llança cada cop que es treu el focus d'un botó | - | `button-component` |
| `focusButton` | Es llança cada cop que es fa focus en un botó | - | `button-component` |
| `handlerClick` | Es llança cada cop que es fa clic en un botó; com a paràmetre conté les dades de l'esdeveniment | `id` | `button-component` |
| `closeSheet` | Esdeveniment emès en tancar-se el panell emergent | `closed: true` — `CustomEvent<{ closed: boolean; }>` | `sheet-component` |

**Depèn de:** [`button-component`](component-botons.md), [`group-button-component`](component-grup-de-botons.md).

**Utilitzat per:** `dropdown-button-component` ([Botons](component-botons.md)), `dropdown-component` ([Desplegable](component-desplegable.md)), `popover-component` ([Descripció emergent](component-descripcio-emergent.md)), `tab-bar-horizontal-component` i `tab-bar-vertical-component` ([Barra de pestanyes](component-barra-de-pestanyes.md)).

**Exemple d'ús**

Es permet la introducció de slots com a contingut del sheet. És important que el contingut que s'introdueixi porti associat l'atribut `slot="sheet-content"`.

```html
<!-- /index.html -->
<button-component 
    custom-id="btn_zoom_in" 
    type-button="button" 
    text-alternative="" 
    class-name-button="icn-btn-secundary"
    class-name-icon="bi-sliders" 
    size-button="icn-btn-size-L" 
    mode-color-button="mode-color-primary-light"
    left-icon="true" 
    aria="Botó: Apropar imatge" 
    id="openSheetBtn"
></button-component>
  <sheet-component 
    id="mysheet" 
    sheet-title="Títol de la fulla" 
    buttons-orientation="vertical" 
    text-tooltip-close-sheet="Tancar panell emergent"
    group-buttons='[
    {"props": 
      {"class-name-button": "btn-primary", "size-button": "btn-size-M", "text": "Button 1", "custom-id": "first", "mode-color-button": "mode-color-primary-light", "right-icon-chevron": "true", "left-icon-chevron": "true"}
    },
    {"props": 
    {"class-name-button": "btn-secundary", "size-button": "btn-size-M", "text": "Button 1", "custom-id": "first", "mode-color-button": "mode-color-secundary-light", "right-icon-chevron": "true", "left-icon-chevron": "true"}
    },
    {"props": 
    {"class-name-button": "btn-tertiary", "size-button": "btn-size-M", "text": "Button 1", "custom-id": "first", "mode-color-button": "mode-color-tertiary-light", "right-icon-chevron": "true", "left-icon-chevron": "true"}
    }
  ]'
></sheet-component>

<script>
  document.getElementById('openSheetBtn').addEventListener('click', () => {
    const sheet = document.getElementById('mysheet');

    Array.from(sheet.querySelectorAll('[slot="sheet-content"]')).forEach(el => el.remove());

    const filterContent = document.createElement('div');
    filterContent.setAttribute('slot', 'sheet-content');
    filterContent.innerHTML = `
    <inputtext-component
      placeholder="Escribe aquí..."
      text-etiqueta="Filtro"
      text-help="Ayuda"
      size="small">
    </inputtext-component>
    <br><br>
    <calendar-component
      disabled-weekends="true"
      disabled-dates='["2025-06-19", "2025-06-20"]'
      disable-past-dates="true" >
    </calendar-component>
    <br><br>
    <status-tracker-component
      statuses='[
        { "number": 1, "statusName": "Pas 1", "state": "done", "description": "Descripció 1" },
        { "number": 2, "statusName": "Pas 2", "state": "current", "description": "Descripció 2" },
        { "number": 3, "statusName": "Pas 3", "state": "pending", "description": "Descripció 3" },
        { "number": 3, "statusName": "Pas 4", "state": "pending" },
        { "number": 4, "statusName": "Pagat", "state": "pending" }
      ]'
      text-etiqueta="Títol"
      text-info-tooltip="Títol info tooltip"
      text-link="Enllaç"
      mode-link="external"
      show-more="true"
      show-link="true"
      show-title="true"
      show-tooltip="true"
    ></status-tracker-component>

  `;

    sheet.appendChild(filterContent);
    sheet.openSheet();
  });
</script>
```

Exemple d'instància (PDF):

```html
<sheet-component
buttons-orientation='horizontal'
group-buttons=[]
sheet-title="texto-ejemplo"
text-tooltip-close-sheet='Tancar panell emergent'
></sheet-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.0.0 | 12.0.0 | 10 juliol, 2026 | Desenvolupament: s'utilitza el token correcte per al color de text del títol |
| 12.0.0 | 11.0.0 | 19 juny, 2026 | Desenvolupament: s'aplica focus trap en mòbil i només es tanca amb ESC o prement el botó de tancar Sheet; ajustos d'accessibilitat en fer zoom al 400% |
| 12.0.0 | 9.4.0 | 29 maig, 2026 | Disseny: s'ha modificat la propietat d'scroll a false. |
| 10.0.0 | 9.4.0 | 17 abril, 2026 | Disseny: es posa el frame del header a amplada fill; s'ha aplicat slots per introduir contingut en el cos del component. Desenvolupament: s'ha corregit la visibilitat de les opcions en mode mobile. |
| 9.0.0 | 9.3.0 | 20 febrer, 2026 | Disseny: s'ha modificat el frame del scroll a posició absoluta; s'han modificat els paddings interiors. Desenvolupament: l'amplada i l'alçada de l'overlay de la modal es canvien d'unitats vh i vw a %. |
| 8.6.0 | 9.2.0 | 27 febrer, 2026 | Desenvolupament: es crea l'esdeveniment closeSheet que s'emet cada cop que es tanca el panell emergent; s'arregla un problema de visualització del component en mode mobile; es fan millores d'accessibilitat |
| 8.6.0 | 8.0.0 | 9 febrer, 2026 | Disseny: s'han aplicat els estils de color al títol i eliminat els truncats; el títol de les variants i els botons de la versió mobile no són sticky; s'ha fet reset de la instància del component "Sheet slot". |
| 8.4.0 | 8.0.0 | 5 desembre, 2025 | Disseny: s'ha fet que l'ombra que apareix quan hi ha scroll arribi a banda i banda del contenidor. |
| 8.3.0 | 8.0.0 | 14 novembre, 2025 | Disseny: s'ha afegit una amplada mínima de 320 px al panell emergent de mida small; s'ha afegit un marge de 16 px entre el títol i el botó de tancar i en el marge dret i esquerre d'aquests perquè quedi alineat amb el contingut. Desenvolupament: resolució de problemes |
| 8.1.0 | 6.1.0 | 6 octubre, 2025 | Disseny: es fa una inicialització (reset) de les instàncies del slot. |
| 7.0.0 | 6.1.0 | 12 setembre, 2025 | Desenvolupament: nova propietat afegida |
| 7.0.0 | 6.0.1 | 28 juliol, 2025 | Disseny: es modifica l'alineació del títol respecte a la icona de tancament. Desenvolupament: resolució de problemes |
| 5.0.0 | 6.0.0 | 3 juliol, 2025 | Desenvolupament del component botó desplegable |
| 5.0.0 | No aplica | 10 juny, 2025 | Disseny del component. |

## Vegeu també
- [Botons](component-botons.md): permet a l'usuari dur a terme accions en una pàgina o pantalla.
- [Grup de botons](component-grup-de-botons.md): per agrupar diversos botons que tenen una relació funcional o contextual.
- [Filtres](component-filtres.md): per refinar i limitar els resultats d'una llista.
- Suport: https://zeroheight.com/38669693e/p/57c57a-suport-i-contacte · https://zeroheight.com/38669693e/p/72240b-preguntes-frequents · https://zeroheight.com/38669693e/p/690b45 · https://zeroheight.com/38669693e/p/342611
