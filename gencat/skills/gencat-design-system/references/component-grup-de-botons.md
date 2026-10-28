# Grup de botons (Button group)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/66a89d · Web component: `<group-button-component>` (paquet core) · Font actualitzada el 2026-10-06 · Extret el 2026-10-28

## Què és i quan usar-lo
Component que agrupa dos o més botons que tenen una relació funcional o contextual. Es fa servir per indicar accions relacionades i mantenir la jerarquia i coherència visual entre elles.

Casos d'ús:
- Accions relacionades (ex: editar, eliminar).
- Accions dins d'un formulari (ex: desar, cancel·lar).
- Accions dins d'elements emergents (ex: modals, notificació emergent).

## Anatomia
Figma: Button group [Change Button 01..06 = _Button_slot, Show Button 02 = True, Show Button 03 = True, Show Button 04 = True, Show Button 05 = False, Show Button 06 = False, Layout = Horizontal].

El component s'ha construït amb *slots* (espai reservat) per poder afegir botons o botons d'icona des del panell de propietats o arrossegant.

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Layout | Horizontal / Vertical | Horizontal |
| Button Slot | Slot | --- |

Variants Figma: Change Button 01 | 02 | 03 | 04 | 05 | 06 = _Button_slot; Show Button 02 | 03 | 04 | 05 | 06 = True | False; Layout = Horizontal | Vertical.

## Comportament i interacció

### Adaptació responsiva
L'adaptació del grup de botons es pot donar en dos formats diferents:

**Disposició:** els botons passen d'una disposició **horitzontal** a **vertical**. Es recomana utilitzar-la:
- En pantalles petites (mòbil) quan el nombre de botons és **reduït (2-3)**.
- Quan totes les accions són importants i han d'estar visibles.
- Quan es vol mantenir la jerarquia visual dels botons (ex: primari a baix de tot).

**Agrupació:** els botons passen a estar agrupats en un botó desplegable. Es recomana utilitzar-la:
- Quan hi ha **més de 3 accions** i no hi ha espai per mostrar-les totes.
- Quan només una o dues accions són prioritàries i les altres són opcionals.
- Per simplificar la interfície i reduir la càrrega cognitiva.

## Bones pràctiques

### Generals

Botó primari:
- **NO FER:** Es recomana no utilitzar més d'un botó primari per grup.
- **FER:** Es pot utilitzar més d'un botó primari únicament quan es tracta d'accions obligatòries que ha de realitzar l'usuari per a completar un procés.

Jerarquia:
- **FER:** Es recomana utilitzar el mateix estil per a tots els botons sempre que sigui possible: o tots botons de text, o tots botons de text amb icona, o tots botons d'icona.

Màxims i mínims:
- **FER:** Utilitza un mínim de dos botons. Si només necessites un, utilitza el component botó.
- **FER:** Es recomana mostrar un màxim de quatre botons a primer nivell i la resta sota un botó desplegable. En funció de l'espai disponible es pot reduir la quantitat de botons a primer nivell (exemple: taules dinàmiques).

Botons desplegables:
- **NO FER:** No utilitzis el botó de menú desplegable com a botó dins del grup de botons. Si vols incloure accions, utilitza el botó desplegable.
- **FER:** Els botons primaris sempre aniran fora del desplegable.

### En pàgina

Jerarquia:
- **FER:** Ordena els botons jeràrquicament d'esquerra a dreta. El botó més a l'esquerra serà el primari, després el secundari i per últim el terciari.
- **FER:** Si has de combinar botons de text amb botons d'icona, comença pels de text d'esquerra a dreta per ordre de jerarquia.
- **FER:** Utilitza la mateixa jerarquia, o jerarquia inferior, per al botó d'icona que l'últim botó de text utilitzat.
- **NO FER:** No utilitzis una jerarquia superior a la de l'últim botó de text si després has d'incloure un botó d'icona. Aquest haurà de ser de la mateixa jerarquia o inferior.

Processos:
- **FER:** Utilitza un màxim de tres botons per grup quan es tracti d'accions relacionades amb un procés.

Alineació:
- **FER:** Alinea els botons a l'esquerra de la pàgina.

### En contenidors

Jerarquia:
- **FER:** Ordena els botons jeràrquicament de dreta a esquerra. El botó més a la dreta serà el primari, després el secundari i per últim el terciari.
- **FER:** Si has de combinar botons de text amb botons d'icona, comença pels de text de dreta a esquerra per ordre de jerarquia.
- **FER:** Utilitza la mateixa jerarquia, o jerarquia inferior, per al botó d'icona que l'últim botó de text utilitzat.
- **NO FER:** No utilitzis una jerarquia superior a la de l'últim botó de text si després has d'incloure un botó d'icona. Aquest haurà de ser de la mateixa jerarquia o inferior.

Alineació:
- **FER:** Alinea els botons a la dreta del contenidor. Excepció: si els botons d'un procés es posen dins d'un element flotant perquè siguin fixos, es col·loquen a l'esquerra.

## Accessibilitat

### Pautes d'accessibilitat del contingut web (WCAG)
- **Ús del color (A), 1.4.1:** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a diferenciar els diferents estats. [CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA), 1.4.3:** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA), 1.4.4:** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA), 1.4.11:** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Espaiat del text (AA), 1.4.12:** quan es desenvolupa contingut utilitzant llenguatges de marcatge que permeten aplicar les propietats d'estil de text, no es perd cap contingut ni funcionalitat si s'ajusten les propietats següents: [CAT](https://www.w3.org/Translations/WCAG22-ca/#text-spacing) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/text-spacing)
  - Alçada de línia (interlineat) de com a mínim 1,5 vegades la mida de la lletra.
  - Espaiat entre els paràgrafs de com a mínim dues vegades la mida de la lletra.
  - Espaiat entre lletres (*tracking*) de com a mínim 0,12 vegades la mida de la lletra.
  - Espaiat entre paraules de com a mínim 0,16 vegades la mida de la lletra.
- **Teclat (A), 2.1.1:** tota la funcionalitat del contingut (navegar pels diferents botons) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Ordre del focus (A), 2.4.3:** tant en pàgina com en contenidor l'ordre del focus sempre ha de ser el mateix: 1. botó primari, 2. botó secundari, 3. botó terciari. Tenint en compte això, hi ha diferents ordres de focus segons si el botó primari està situat a l'esquerra (en pàgina) o a la dreta (en contenidor); la font ho il·lustra amb captures de Figma (Pàgina, Contenidors). [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-order) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-order)
- **Focus visible (AA), 2.4.7:** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

### Navegació per teclat

| Tecla | Acció |
|---|---|
| Tabulació | Navega al següent element interactiu |
| Shift + Tabulació | Navega a l'anterior element interactiu |
| Enter | Activa l'element interactiu |

## Implementació (component web)

### `<group-button-component>`
Paquet: core.

Aquest component no té propietats declarades. El contingut s'introdueix mitjançant slots. És necessari ajustar els estils a les necessitats de cada situació. Aquest component només té els estils següents:

```css
/* /style.css */
.group-button-component-gecat {
  display: flex;
  flex-direction: row;
  gap: $spacing-layout-x1;
}
```

**Esdeveniments**

[discrepància: el lloc diu "aquest component no té propietats ni esdeveniments" però després llista els tres esdeveniments següents (origen `button-component`); el PDF diu "Sin eventos declarados"]

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `handlerClick` | Es llança cada cop que es fa clic en un botó i com a paràmetre conté les dades de l'esdeveniment. | id | `button-component` |
| `focusButton` | Es llança cada cop que es fa focus en un botó. | --- | `button-component` |
| `blurButton` | Es llança cada cop que es treu el focus en un botó. | --- | `button-component` |

**Depèn de:** `button-component` (vegeu [Botons](component-botons.md)).

**Utilitzat per:**
- Segons el lloc, core: `backoffice-subheader-component` ([Capçalera secundària de BO](component-capcalera-secundaria-de-bo.md)), `dropdown-menu-component` ([Desplegable](component-desplegable.md)), `header-component` ([Capçalera per aplicacions internes](component-capcalera-per-aplicacions-internes.md)), `modal-component` ([Modals](component-modals.md)), `poi-component` ([Visor de mapa](component-visor-de-mapa.md)), `sheet-component` ([Panell emergent](component-panell-emergent.md)).
- Segons el lloc, conversational: `chat-header-component` ([Capçalera de xat](component-capcalera-de-xat.md)), `chat-input-component` ([Camp d'entrada de xat](component-camp-d-entrada-de-xat.md)), `chat-message-component` ([Missatge de xat](component-missatge-de-xat.md)).
- Segons el PDF: `chat-header-component`, `chat-input-component`, `chat-message-component`, `modal-component`.

**Exemple d'ús**

```html
<!-- /index.html -->
<group-button-component>
    <button-component 
      class-name-button="btn-primary" 
      class-name-icon="" size-button="btn-size-L"
      mode-color-button="mode-color-primary-light" 
      text="Button" 
      left-icon-chevron="true"
      right-icon-chevron="false" 
      left-icon=false 
      right-icon=false 
      text-alternative="" 
      is-spinner=false 
      custom-id="first-button">
    </button-component>
    <button-component 
      class-name-button="icn-btn-tertiary" 
      class-name-icon="" 
      size-button="icn-btn-size-L"
      mode-color-button="mode-color-tertiary-light" 
      text="" 
      left-icon-chevron="true" 
      right-icon-chevron="false"
      left-icon=false 
      right-icon=false 
      text-alternative="" 
      is-spinner=false 
      custom-id="second-button">
    </button-component>
    <button-component 
      class-name-button="btn-tertiary" 
      class-name-icon="" 
      size-button="btn-size-L"
      mode-color-button="mode-color-tertiary-light" 
      text="Button" 
      left-icon-chevron="true"
      right-icon-chevron="false" 
      left-icon=false 
      right-icon=false 
      text-alternative="" 
      is-spinner=false 
      custom-id="third-button">
    </button-component>
  </group-button-component>
```

**Exemple d'instància (PDF)**

```html
<group-button-component></group-button-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 10.0.0 | 11.0.0 | 19 juny, 2026 | Desenvolupament: ajustos de disseny per a dispositius mòbils. |
| 10.0.0 | 6.0.0 | 17 abril, 2026 | Disseny: s'apliquen slots al component. |
| 8.2.0 | 6.0.0 | 27 octubre, 2025 | Disseny: s'ha afegit la propietat booleana "Show button 02". |
| 5.0.0 | 6.0.0 | 3 juliol, 2025 | Desenvolupament del component botó desplegable. |
| 5.0.0 | No aplica | 10 juny, 2025 | Disseny del component. |

## Vegeu també
- [Botons](component-botons.md): permet a l'usuari dur a terme accions en una pàgina o pantalla.
