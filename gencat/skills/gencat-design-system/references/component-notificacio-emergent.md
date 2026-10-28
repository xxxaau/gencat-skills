# Notificació emergent (Toast)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/818a50 · Web component: `<toast-component>` (paquet core) · Font actualitzada el 2026-10-22 · Extret el 2026-10-28

## Què és i quan usar-lo
Notificacions breus i temporals que no interrompen l'experiència ni requereixen una acció per part de l'usuari.

La notificació emergent és un component que s'utilitza per a **mostrar notificacions o missatges breus en una aplicació o pàgina web**. És especialment útil per donar retroalimentació a l'usuari sobre les seves accions sense interrompre el flux de la interacció en curs. Apareix temporalment en pantalla, sense bloquejar ni limitar l'ús de l'aplicació.

Inclou sempre un botó per tancar la finestra emergent. Opcionalment, pot incloure un altre botó addicional per realitzar una acció específica relacionada amb el missatge.

Quan s'utilitza:
- Realimentació del sistema: informar els usuaris que el resultat de les seves accions s'ha completat correctament (p. ex. "Els vostres canvis s'han desat", "El missatge s'ha enviat").

## Quan NO usar-lo / alternatives
- Quan la informació a comunicar és crítica o urgent i requereix interrompre el flux d'usuari.
- Quan la informació és llarga o complexa i requereix una atenció especial de l'usuari per entendre-la o per realitzar una acció amb èxit.
- Per informar d'errors o missatges d'alerta: s'utilitza el component d'avisos ([Avisos](component-avisos.md)). La font ho anomena "component d'alerta".

## Anatomia
Figma: Toast [Show Button = True, Description = "Introdueix el missatge aquí (màxim pot contenir 60 caràcters).", Show Link = True, Breakpoint = Extra Large - Large].

La notificació emergent sempre ha d'incloure el missatge i el botó de tancament. Opcionalment, pot contenir:
- Un botó secundari per desfer l'acció indicada al missatge. Aquesta acció mai pot ser crítica ni obligatòria: sempre són accions rutinàries i opcionals, com desfer un missatge enviat.
- Un enllaç, que només es pot utilitzar per donar un accés ràpid a un document, carpeta o pàgina directament relacionada amb el missatge (per exemple, veure el document que s'ha pujat dins d'una carpeta d'una aplicació).
- Mai hi pot haver més d'un enllaç a la vegada, ni un enllaç i un botó dins la mateixa notificació emergent.

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Buttons | True / False | False |

## Mides i espaiats
- Posició: part superior central de la pantalla, a **40 dp** del marge superior.
- Màxim **tres** notificacions emergents a la vegada.
- Amplada no fixa: s'adapta al contingut.
- El botó es posiciona per defecte a la dreta del missatge, alineats horitzontalment. Si no hi ha prou espai (la caixa de text ocupa menys de **240 dp**), el botó es posiciona sota el text.
- Si la pantalla és menor de **480 dp**, el botó s'adapta al contenidor de la notificació emergent (criteri del comportament dels botons).
- Versió small: amplada mínima; padding de 8px entre el botó i el text quan el botó passa a la línia inferior (historial de versions).

## Comportament i interacció

### Interacció
- Component no intrusiu: apareix i s'amaga automàticament després d'un temps equivalent a llegir-lo a un ritme normal (entre quatre i deu segons).
- No necessita interacció per desaparèixer. L'usuari pot tancar-la manualment amb el botó de tancament.
- Pot contenir 1 botó d'acció que realitzi una acció o redirigeixi l'usuari a una pàgina de més detall.
- Quan es fa focus dins del component, aquest no marxa després del temps indicat: es queda fix fins que l'usuari realitza una acció o surt del component.

### Posició
Apareixen a la part superior central de la pantalla, a 40 dp del marge superior. Com a molt, tres a la vegada. Si n'hi ha més d'activades alhora, van apareixent escalonadament a mesura que desapareixen les que hi ha en pantalla.

### Adaptació responsiva
- Per defecte el missatge es maqueta en una sola línia.
- Màxim de 60 caràcters perquè l'usuari pugui llegir còmodament el text abans que desaparegui automàticament.
- Si la pantalla és massa petita i el missatge no hi cap en una línia, el text salta a una segona línia.

### Microanimació
Les notificacions apareixen amb un petit moviment vertical de baix cap a dalt i un "fos" de 0 a 100 % d'opacitat, perquè l'usuari detecti més ràpidament el missatge.

## Contingut i microcopy
- Missatge de 60 caràcters com a màxim. Text d'exemple: "Introdueix el missatge aquí (màxim pot contenir 60 caràcters)."
- Exemples de missatge: "Els vostres canvis s'han desat", "El missatge s'ha enviat".
- Tooltip del botó de tancament per defecte: "Tancar notificació emergent".
- Textos d'exemple del codi: enllaç "Enllaç", botó "Button".

## Bones pràctiques
- **FER:** Utilitza missatges breus (màxim 60 caràcters), descrivint el resultat d'una acció de manera clara i concisa.
- **NO FER:** No incloguis missatges molt llargs (superiors a 60 caràcters) ni complexos, ja que l'usuari no pot captar bé la informació.
- **FER:** Si el context ho necessita, inclou un botó per desfer accions rutinàries i opcionals (per exemple, desfer l'enviament d'un missatge).
- **NO FER:** No incloguis més d'una acció per notificació emergent ni accions principals que requereixin una atenció especial de l'usuari.
- **FER:** Utilitza la notificació emergent per donar retroalimentació sobre accions rutinàries (per exemple, enviar un missatge o activar/desactivar alguna funcionalitat).
- **NO FER:** No utilitzis la notificació emergent en excés ni amb massa freqüència. Tot i que no són tan transgressores com els diàlegs, interrompen l'atenció de l'usuari fins a cert grau.
- **NO FER:** No utilitzis la notificació emergent per mostrar missatges d'error o alerta, ni facis servir altres colors per representar estats. Per indicar accions fallides o missatges crítics, fes servir el component d'avisos ([Avisos](component-avisos.md)).

## Accessibilitat
Pautes WCAG 2.2:
- **Ús del color (A) – 1.4.1:** el color no és l'únic mitjà visual per transmetre informació. Per diferenciar les tipologies d'avisos s'inclouen icones específiques per a cadascuna. [CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA) – 1.4.3:** contrast d'almenys 4,5:1 als elements textuals; els elements inactius o deshabilitats en són excepció. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA) – 1.4.4:** el text es pot canviar de mida fins al 200 % sense pèrdua de contingut ni funcionalitat (excepte subtítols i imatges de text). [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Redistribució (AA) – 1.4.10:** el contingut es pot presentar sense pèrdua d'informació o funcionalitat, i sense desplaçament en dues dimensions: contingut de desplaçament vertical amb una amplada equivalent a 320 píxels CSS; contingut de desplaçament horitzontal a una alçada equivalent a 256 píxels CSS. [CAT](https://www.w3.org/WAI/WCAG22/Understanding/reflow) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/reflow)
- **Contrast d'elements no textuals (AA) – 1.4.11:** icones i vores amb contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Espaiat del text (AA) – 1.4.12:** no es perd contingut ni funcionalitat si s'ajusten: alçada de línia d'almenys 1,5 vegades la mida de la lletra; espaiat entre paràgrafs d'almenys dues vegades; espaiat entre lletres (tracking) d'almenys 0,12 vegades; espaiat entre paraules d'almenys 0,16 vegades. [CAT](https://www.w3.org/Translations/WCAG22-ca/#text-spacing) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/text-spacing)
- **Teclat (A) – 2.1.1:** tota la funcionalitat (navegar pels enllaços i botons) es pot operar amb teclat sense requerir temps específics per a pulsacions. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Focus visible (AA) – 2.4.7:** la navegació amb teclat per botons i enllaços és visible mitjançant un rectangle. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- **Missatges d'estat (AA) – 4.1.3:** cal informar dels canvis importants en el contingut de forma que la tecnologia assistiva notifiqui els canvis d'estat que no prenen el focus. Es fa amb `role="alert"` i `aria-live="polite"`. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible) [a verificar: els enllaços de la font apunten a focus-visible]
- **Focus no ocult (AA) – 2.4.11:** en aparèixer a la part superior de la pantalla, la notificació no pot ocultar cap element que tingui el focus de teclat en aquell moment. Quan un element de la notificació té el focus, aquesta no desapareix fins que l'usuari realitza una acció o en surt. Especialment rellevant en dispositius mòbils i tauletes amb zoom de pantalla activat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-not-obscured-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-not-obscured-minimum)

### Navegació per teclat

| Tecla | Acció |
|---|---|
| Tabulació | Navegar al següent element interactiu |
| Shift + Tabulació | Navegar a l'anterior element interactiu |
| Intro / Enter | Activa l'element seleccionat |
| Esc | Tancar la notificació emergent |

## Implementació (component web)

### `<toast-component>`

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Obligatori | Per defecte |
|---|---|---|---|---|---|
| `assetBasePath` | `asset-base-path` | Ruta base des de la qual es carreguen els recursos (imatges); permet afegir a la ruta de la icona check la ruta a la qual apunta el projecte. | string | Opcional | `` |
| `buttonText` | `button-text` | Text del botó. | string | Opcional | `undefined` |
| `customIdLink` | `custom-id-link` | Identificador personalitzat de l'enllaç. | string | Opcional | `undefined` |
| `linkMode` | `link-mode` | Enllaç extern o intern. Opcions: `external`, `internal`. | string | Opcional | `undefined` |
| `linkText` | `link-text` | Text de l'enllaç. | string | Opcional | `undefined` |
| `message` | `message` | Missatge de la notificació emergent. | string | Obligatori | `undefined` |
| `textTooltipCloseToast` | `text-tooltip-close-toast` | Text del tooltip del botó que tanca la notificació emergent. | string | Obligatori | `Tancar notificació emergent` |
| `timerDuration` | `timer-duration` | Permet establir un límit de temps de visualització del toast entre 4 i 10 segons. | string | Opcional | `6` |
| `visibilityButton` | `visibility-button` | Per mostrar o no el botó. | boolean | Opcional | `false` |
| `visibilityLink` | `visibility-link` | Per mostrar o no l'enllaç. | boolean | Opcional | `false` |

[discrepància: `timerDuration` consta a la pàgina del lloc però no al PDF v12.0.0; l'historial de versions la introdueix a la versió Github 12.1.0 (la pàgina l'esmenta com a `timeDuration` a l'historial)]

**Variants**

| Propietat | Valors | Per defecte |
|---|---|---|
| `linkMode` | `external` `internal` | - |
| `textTooltipCloseToast` | - | Tancar notificació emergent |
| `timerDuration` | `4` `5` `6` `7` `8` `9` `10` | `6` |

**Mètodes públics**

| Mètode | Descripció | Paràmetre |
|---|---|---|
| `initialize()` | Inicialitza i mostra el toast. | - |

**Esdeveniments** (el PDF no declara esdeveniments propis; la pàgina llista els dels components fills)

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `blurButton` | Es llança cada cop que es treu el focus d'algun dels botons. | - | `button-component` |
| `focusButton` | Es llança cada cop que es fa focus sobre algun dels botons. | - | `button-component` |
| `handlerClick` | Es llança en fer clic sobre algun dels botons. | `id` | `button-component` |
| `blurLink` | Es llança cada cop que es treu el focus del link. | - | `link-component` |
| `focusLink` | Es llança cada cop que es fa focus sobre el link. | - | `link-component` |
| `linkEmit` | Es llança en fer clic sobre el link. | `id` | `link-component` |

**Depèn de:** `button-component` ([Botons](component-botons.md)), `link-component` ([Enllaços](component-enllacos.md)).

**Exemple d'ús (pàgina)**

```html
<!-- /index.html -->
<!--Botó que farà que salti el toast-->
<button-component 
  id="toast-button" 
  class-name-button="btn-primary" 
  size-button="btn-size-L"
  mode-color-button="mode-color-primary-light" 
  text="Primary" 
  left-icon-chevron=false 
  right-icon-chevron=true
  left-icon=true 
  text-alternative=""
></button-component>

<!--Contenidor del toast. Recomano utilitzar aquests mateixos estils per centrar a la part superior el toast-component-->
<div 
  id="toast-container" 
  style="
    position: fixed; 
    display: flex; 
    flex-direction: column-reverse; 
    width: 100%; 
    top: 40px; 
    gap: 7px; 
    left: 0; 
    padding-left: 15px; 
    padding-right: 15px"
  ></div>

<!--Codi JavaScript que detecta un clic sobre el botó que hem creat per crear la trucada al component toast i inicialitzar-lo.-->
  <script>
    document.querySelector("#toast-button").addEventListener('click', async function () {
  
        const toastComponent = document.createElement('toast-component');
        toastComponent.setAttribute('id', 'tostada');
        toastComponent.setAttribute('custom-id-link', 'link-toast');
        toastComponent.setAttribute('message', 'Introdueix el missatge aquí (màxim pot contenir 60 caràcters).');
        toastComponent.setAttribute('link-text', 'Enllaç');
        toastComponent.setAttribute('link-mode', 'internal');
        toastComponent.setAttribute('visibility-link', 'true');
        toastComponent.setAttribute('button-text', 'Button');
        toastComponent.setAttribute('visibility-button', 'true');
        toastComponent.setAttribute('timer-duration', '4');
        toastComponent.setAttribute('asset-base-path', '');
        toastComponent.setAttribute('text-tooltip-close-toast', 'Tancar notificació emergent');
    
        const toastContainer = document.getElementById("toast-container");
        toastContainer.appendChild(toastComponent);
    
        if (typeof toastComponent.initialize === 'function') {
            await toastComponent.initialize();
        }
    });
  </script>
```

**Exemple d'instància (PDF)**

```html
<toast-component
asset-base-path=''
button-text="texto-ejemplo"
custom-id-link="texto-ejemplo"
link-mode="external"
link-text="texto-ejemplo"
message="texto-ejemplo"
text-tooltip-close-toast='Tancar notificació emergent'
visibility-button=false
visibility-link=false
></toast-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 9.1.0 | 12.1.0 | 7 setembre, 2026 | Desenvolupament: es crea una propietat anomenada `timeDuration` que permet establir un límit de temps de visualització del toast entre 4 i 10 segons. |
| 9.1.0 | 12.0.0 | 10 juliol, 2026 | Desenvolupament: nova propietat `assetBasePath` que permet afegir a la ruta de l'icon check la ruta a la qual apunta el projecte usuari. |
| 9.1.0 | 11.0.0 | 19 juny, 2026 | Desenvolupament: s'afegeix amplada i alçada a l'icon-check; es millora l'alineació de l'icon-check. |
| 9.1.0 | 9.4.0 | 17 abril, 2026 | Desenvolupament: ajustos d'accessibilitat. |
| 9.1.0 | 9.2.0 | 20 març, 2026 | Disseny: alineació de la icona de check i del botó de tancament a la part superior en Extra Large - Large. |
| 8.0.0 | 9.2.0 | 27 febrer, 2026 | Desenvolupament: es crea la propietat `customIdLink` per a l'enllaç. |
| 8.0.0 | 9.1.0 | 6 febrer, 2026 | Desenvolupament: adaptacions d'accessibilitat per a mides de font extra grans i augment de pantalla. |
| 8.0.0 | 6.2.1 | 3 octubre, 2025 | Desenvolupament: nova propietat afegida o eliminada. |
| 8.0.0 | 6.1.0 | 12 setembre, 2025 | Disseny: l'estil de text del cos passa de Label a Body. Desenvolupament: nova propietat afegida. |
| 6.0.0 | 4.0.1 | 8 juliol, 2025 | Disseny: amplada mínima a la versió small; padding de 8px entre el botó i el text quan el botó passa a la línia inferior. |
| 4.0.0 | 4.0.1 | 19 maig, 2025 | Desenvolupament: resolució de problemes. |
| 2.3.0 | 1.0.0 | 31 gener, 2025 | Sense canvis |
| 2.2.0 | 0.1.1 | 05 desembre, 2025 | Sense canvis (data tal com consta a la font) |
| 2.1.0 | 0.1.1 | 04 desembre, 2024 | Sense canvis |
| 2.0.0 | 0.1.0 | 02 desembre, 2024 | Sense canvis |
| 1.1.0 | 0.1.0 | 22 novembre, 2024 | Sense canvis |
| 1.1.0 | 0.0.4 | 18 novembre, 2024 | Sense canvis |
| 1.0.0 | 0.0.3 | 1 novembre, 2024 | Disseny, desenvolupament i documentació del component |

## Vegeu també
- [Avisos](component-avisos.md): per comunicar un estat específic d'una pàgina o característica.
- [Indicador de funció](component-indicador-de-funcio.md): per mostrar un text breu en passar el cursor per sobre d'una icona o activador.
- [Modals](component-modals.md): per proporcionar informació crítica o demanar una decisió.
- [Botons](component-botons.md)
- [Enllaços](component-enllacos.md)
