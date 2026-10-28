# Avisos (Callout)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/614b8c · Web component: `<callout-component>` (paquet core) · Font actualitzada el 2026-07-14 · Extret el 2026-10-28

## Què és i quan usar-lo
Missatges contextuals usats per informar de situacions importants, com ara errors o advertències.

Les alertes són **missatges contextuals que s'utilitzen per comunicar un estat específic** d'una pàgina o característica, i solen requerir una acció per part de l'usuari. No desapareixen fins que l'usuari les desestima o es resol la situació que les ha provocat.

Es fan servir per a informar l'usuari sobre situacions importants o crítiques, com poden ser errors, advertències o confirmacions d'accions. Habitualment són breus i concises, presentades en un format destacat per captar l'atenció de manera efectiva.

Les alertes també serveixen per guiar l'usuari a través de l'experiència de navegació. Per exemple, una alerta d'èxit confirma que s'ha completat una tasca correctament, proporcionant a l'usuari una retroalimentació positiva. En canvi, una notificació d'advertència alerta l'usuari de possibles problemes que requereixen atenció.

Els avisos poden ser usats en els contextos següents:
- **Validació dins un formulari:** mostrant errors o missatges d'èxit.
- **Alertes específiques de context:** proporcionant informació crítica o avisos relacionats amb una secció específica del contingut (per exemple, un missatge d'error sobre una secció de càrrega de dades fallida).
- **Actualitzacions o instruccions d'estat importants:** que l'usuari ha de reconèixer o a les quals ha de reaccionar.

## Quan NO usar-lo / alternatives
No s'utilitzen els avisos per a les situacions següents:
- **Comunicar informació trivial:** no rellevant o no important per a l'usuari.
- **Fer seguiment d'una acció rutinària** realitzada per l'usuari que no és crítica (missatges de retroalimentació efímera). En aquests casos, es fa servir una notificació emergent ([Notificació emergent](component-notificacio-emergent.md)).

## Anatomia
Figma: Avisos [Body = Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua., Title = Títol avís, Show Actions = True, Show Link = True, Show Title = True, Show Close button = True, Breakpoint = Extra Large - Medium, State = Informative].

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Error / Success / Warning / Info | - |
| Title | True / False | True |
| Actions | None / Single action / Multiple action | None |
| Close button | True / False | False |

### Estats (tipologies)
- **Informació:** proporciona als usuaris informació general o actualitzacions no urgents.
- **Confirmació:** informa els usuaris que una acció que han realitzat s'ha completat amb èxit. Exemples: "El teu pagament s'ha processat amb èxit" o "El fitxer s'ha pujat correctament".
- **Alerta:** avisa els usuaris sobre un possible problema que pot requerir la seva atenció, però que no és crític de manera immediata. Exemples: "La contrasenya caducarà en set dies" o "Bateria baixa".
- **Error o alerta crítica:** informa els usuaris que alguna cosa ha anat malament o destaca un problema crític que requereix atenció immediata. Normalment, aquests missatges bloquegen el procés fins que l'usuari resolgui la incidència. Exemples: "Els canvis no s'han desat correctament. Torneu-ho a provar" o "S'ha detectat una bretxa de seguretat".

### Combinacions de text
Les alertes poden contenir un missatge breu o un contingut més extens, amb títol i descripció. Sempre que l'alerta tingui un contingut més llarg o complex, és recomanable utilitzar un títol que permeti a l'usuari identificar ràpidament el tema principal de l'alerta.

### Accions
Les alertes poden incloure 1 o 2 accions per ajudar l'usuari a resoldre l'alerta.
- **Acció única:** s'utilitzarà un botó secundari.
- **Dues accions:** el botó secundari s'assignarà a l'acció principal; el botó terciari s'assignarà a l'acció secundària.

Mai no hi haurà més de dues accions en una alerta, i no es permetrà l'ús de botons primaris dins d'una alerta. A més, els avisos poden incloure enllaços dins o després del cos del missatge, als quals els usuaris, si necessiten més informació, hi poden accedir.

### Botó de tancament
Els avisos poden contenir opcionalment un botó de tancament, però és recomanable que aquest no aparegui si es tracta d'una informació crítica.
- Com a norma general, sempre que sigui una alerta relacionada amb una acció que ha realitzat l'usuari i que requereix una acció per part d'aquest, el botó de tancament no estarà visible i l'alerta només desapareixerà si la situació que ha causat l'alerta s'ha resolt.
- Si l'alerta actua com a ampliadora d'una informació no crítica, com per exemple destacar una actualització del sistema, i aquesta informació es pot trobar en alguna altra secció de la web o aplicació, el botó de tancament estarà visible perquè l'usuari pugui eliminar manualment l'alerta si ho desitja.

## Mides i espaiats
- L'amplada de les notificacions en línia varia en funció del contingut i la disposició. Poden expandir-se fins a omplir el contenidor o l'àrea de contingut amb la qual es relacionen. L'alçada es basa en la longitud del contingut.
- La posició dels botons varia en funció de l'amplada del component.
  - Si el contenidor és prou ample (la caixa de text ocupa més de 360 dp), els botons es col·locaran a la part dreta del component.
  - Si la caixa de text ocupa menys de 360 dp d'amplada, els botons es col·locaran a sota de la caixa de text.
- Per mantenir una bona llegibilitat, la caixa de text pot tenir una amplada màxima de 800 dp; així, si l'alerta és més ampla, el text quedarà justificat a la part dreta, deixant la part esquerra sense text.

## Comportament i interacció

### Interacció
- Les alertes no es descarten automàticament. Persisteixen a la pàgina fins que l'usuari les desestima o pren mesures que resolen la notificació.

### Posició
- Les notificacions apareixen a l'inici de la pàgina o a prop dels elements relacionats, integrades dins de la maquetació de la pàgina. Poden expandir-se per omplir l'amplada de l'àrea de contenidor o contingut en la qual es troben i han d'estar alineades amb les columnes de la quadrícula.
- En el cas dels formularis, si les notificacions d'error s'apliquen a entrades de text individuals, aquestes s'han de marcar directament en els camps corresponents com a missatges d'error. Quan l'usuari faci clic al botó d'enviar, la pàgina hauria de fer un desplaçament automàtic al primer error que trobi. Si el missatge d'error no fa referència a un camp específic, és recomanable col·locar l'alerta just a sobre dels botons d'enviament i cancel·lació (o a l'inici de la pàgina).

### Adaptació responsiva i desbordament de text
- Per a pantalles més petites de 480 dp, tots els elements han d'estar alineats verticalment. Seguint els criteris definits en el comportament dels botons, aquests s'alinearan amb l'amplada total del contingut.
- Seguint aquests mateixos criteris, si l'amplada de la pantalla és superior a 480 dp, el botó es mostrarà en disposició horitzontal. Si la pantalla ocupa menys de 480 dp, el botó s'ajustarà al seu contenidor i es disposarà de manera vertical.
- **En augments de text al 200%:** si l'amplada dels botons és superior al contenidor, aquests es col·locaran un sota l'altre i, en el cas que el text d'un botó no càpiga en l'espai disponible, el text del botó saltarà a una segona línia.

## Contingut i microcopy
Exemples de la font: títol "Títol avís"; text del tooltip del botó de tancar "Tancar avís"; exemples de missatge a la secció Estats.

## Bones pràctiques

**Contingut**
- **FER:** Utilitza un títol breu i descriptiu, explicant la informació més important.
- **NO FER:** No utilitzis un títol llarg i excessivament descriptiu.
- **FER:** Inclou un text que no repeteixi o parafrasegi el títol.
- **NO FER:** No incloguis un text que repeteixi o parafrasegi el títol.
- **FER:** Utilitza un to de veu positiu sense fer judicis. Evita culpar els usuaris amb afirmacions que suggereixin que estan fent alguna cosa malament, i evita termes com "invàlid", "il·legal" o "incorrecte".
- **NO FER:** No adoptis un to de veu negatiu que fa judicis de l'usuari.
- **FER:** En avisos d'alerta o error, explica com resoldre el problema incloent accions de resolució o pròxims passos.
- **NO FER:** Evita avisos d'error que no proporcionen informació o vies alternatives de com resoldre el problema.
- **FER:** Utilitza avisos amb les icones corresponents per a cada tipologia.
- **NO FER:** No utilitzis alertes sense icona o amb una icona diferent de la definida segons la tipologia. Les alertes han de reflectir clarament l'estat i incloure la icona adequada que indiqui aquesta informació.
- **FER:** Fes que cada alerta faci referència a un avís o tema específic. Si hi ha diversos missatges relacionats amb el mateix tema, és millor simplificar-los en un de sol.
- **NO FER:** No facis que cada alerta es refereixi a diversos avisos o temes alhora.
- **FER:** Es poden tenir diverses alertes en una mateixa pàgina si és necessari, però és recomanable minimitzar-ne l'ús per evitar la sobresaturació de missatges per part dels usuaris.
- **NO FER:** No utilitzis les alertes de forma desmesurada.

## Accessibilitat

### Pautes d'accessibilitat del contingut web (WCAG)
- **Orientació (AA):** el contingut de l'àrea de text s'adapta a les diferents orientacions de la pantalla, vertical o horitzontal, cosa que permet visualitzar el contingut. [1.3.4 Orientació - CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Ús del color (A):** el color no es fa servir com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a diferenciar les diferents tipologies d'avisos, s'inclouen icones específiques per a cadascuna. [1.4.1 Ús del color - CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són excepció d'aquesta norma. [1.4.3 Contrast mínim - CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA):** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [1.4.4 Canvia la mida del text - CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Redistribució (AA):** el contingut es pot presentar sense pèrdua d'informació o funcionalitat, i sense necessitat de desplaçar-se en dues dimensions per: contingut de desplaçament vertical amb una amplada equivalent a 320 píxels CSS; contingut de desplaçament horitzontal amb una alçària equivalent a 256 píxels CSS. [1.4.10 Redistribució - CAT](https://www.w3.org/WAI/WCAG22/Understanding/reflow) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/reflow)
- **Contrast d'elements no textuals (AA):** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [1.4.11 Contrast d'elements no textuals - CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Espaiat del text (AA):** quan es desenvolupa contingut utilitzant llenguatges de marcatge que permeten aplicar les propietats d'estil de text, no es perd cap contingut ni funcionalitat si s'ajusten les propietats següents: alçada de línia (interlineat) de com a mínim 1,5 vegades la mida de la lletra; espaiat entre els paràgrafs de com a mínim dues vegades la mida de la lletra; espaiat entre lletres (tracking) de com a mínim 0,12 vegades la mida de la lletra; espaiat entre paraules de com a mínim 0,16 vegades la mida de la lletra. [1.4.12 Espaiat del text - CAT](https://www.w3.org/Translations/WCAG22-ca/#text-spacing) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/text-spacing)
- **Teclat (A):** tota la funcionalitat del contingut (navegar pels enllaços i botons) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [2.1.1 Teclat - CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Ordre del focus (A):** els avisos presenten un ordre lògic del focus dels elements interns per facilitar la navegació per teclat o altres dispositius d'entrada. L'ordre ha de seguir el flux de la informació o les tasques que s'estan presentant. L'ordre ha de ser el següent: 1. Enllaç. 2. Acció primària. 3. Acció secundària. 4. Icona de tancament. [2.4.3 Ordre del focus - CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-order) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-order)
- **Focus visible (AA):** la navegació pels diferents botons i enllaços mitjançant teclat és visible a través d'un rectangle. [2.4.7 Focus visible - CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

## Implementació (component web)

### `<callout-component>`

Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat (lloc) |
|---|---|---|---|---|---|
| `buttonText` | `button-text` | Text del botó | string | `undefined` | Opcional |
| `calloutTitle` | `callout-title` | Títol de l'avís | string | `undefined` | Opcional |
| `customIdLink` | `custom-id-link` | Identificador personalitzat per a l'enllaç (PDF: «URL de l'enllaç») | string | `undefined` | Opcional |
| `dismissible` | `dismissible` | Si és `true` mostra un botó per tancar l'avís; si és `false` es desactiva | boolean | `false` | Opcional |
| `linkMode` | `link-mode` | Tria si l'enllaç és extern o intern. Opcions: `external`, `internal` | string | `internal` | Opcional |
| `linkText` | `link-text` | Text de l'enllaç | string | `undefined` | Opcional |
| `message` | `message` | Missatge de l'avís (contingut del missatge) | string | `undefined` | Obligatori |
| `secondButtonText` | `second-button-text` | Text del segon botó | string | `undefined` | Opcional |
| `showButton` | `show-button` | `true`/`false`: determina si es mostra o no el botó | boolean | `false` | Opcional |
| `showLink` | `show-link` | `true`/`false`: determina si es mostra o no l'enllaç | boolean | `false` | Opcional |
| `showSecondButton` | `show-second-button` | `true`/`false`: determina si es mostra o no el segon botó | boolean | `false` | Opcional |
| `textTooltipCloseButton` | `text-tooltip-close-button` | Text del tooltip del botó de tancar avís | string | `Tancar avís` | Opcional |
| `type` | `type` | Tipus d'avís. Opcions: `error`, `informative`, `success`, `warning` | string | `informative` | Opcional |

**Variants**

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `linkMode` | `external`, `internal` | `internal` |
| `textTooltipCloseButton` | - | Tancar avís |
| `type` | `error`, `informative`, `success`, `warning` | `informative` |

**Esdeveniments (lloc)**

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `linkEmit` | Esdeveniment llançat en fer clic sobre l'enllaç | `id` | `link-component` |
| `focusLink` | Esdeveniment llançat en fer focus sobre l'enllaç | - | `link-component` |
| `blurLink` | Es llança cada cop que es treu el focus de l'enllaç | - | `link-component` |
| `handlerClick` | Esdeveniment llançat en fer clic sobre algun dels botons | `id` | `button-component` |
| `focusButton` | Esdeveniment llançat en fer focus sobre algun dels botons | - | `button-component` |
| `button-component` | Esdeveniment llançat en treure el focus d'algun dels botons | - | `button-component` |

[discrepància: el lloc llista aquests esdeveniments heretats dels components fills; el PDF diu «Sin eventos declarados» per a `callout-component`] [a verificar: l'última fila del lloc porta el nom `button-component` a la columna d'esdeveniment, que sembla un error d'origen]

**Depèn de:** `link-component` ([Enllaços](component-enllacos.md)), `button-component` ([Botons](component-botons.md)).

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<callout-component
  custom-id-link=""
  type="informative" 
  dismissible="true" 
  callout-title="Títol avís"
  message="Lorem ipsum dolor sit amet, consectetur adipiscing elit."
  show-link="true" 
  link-text="Enllaç" 
  link-mode="external"
  show-button="true" 
  button-text="Botó"
  show-second-button="true" 
  second-button-text="Botó"
  text-tooltip-close-button="Tancar avís">
</callout-component>
```

**Exemple d'instància (PDF)**

```html
<callout-component
button-text="texto-ejemplo"
callout-title="texto-ejemplo"
custom-id-link="texto-ejemplo"
dismissible=false
link-mode="internal"
link-text="texto-ejemplo"
message="texto-ejemplo"
second-button-text="texto-ejemplo"
show-button=false
show-link=false
show-second-button=false
text-tooltip-close-button='Tancar avís'
type='informative'
></callout-component>
```

## Claus de text (internacionalització)
Vegeu les [claus](dev-referencia-de-claus-disponibles.md) (`callout`).

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.0.0 | 9.3.0 | 29 maig, 2026 | Disseny: es posen els frames "Container" de l'avís informatiu i d'èxit en el punt de tall Extra Large - Medium en fill. |
| 9.0.0 | 9.3.0 | 20 febrer, 2026 | Disseny: s'han intercanviat les icones dels avisos d'error i d'alerta. S'ha modificat l'alçada de l'avís informatiu per tal que sigui consistent amb la resta. Desenvolupament: actualització de les icones de warning i error. |
| 8.5.0 | 9.2.0 | 27 febrer, 2026 | Desenvolupament: es crea la propietat customIdLink. |
| 8.5.0 | 9.1.0 | 6 febrer, 2026 | Desenvolupament: quan els botons són més amples que el contenidor salten un sota l'altre. Quan el text dels botons és més ample que el contenidor, aquest salta de línia. Es fan adaptacions d'accessibilitat pel que fa a mides de font extra gran i augment de pantalla. |
| 8.5.0 | 8.0.0 | 20 gener, 2026 | Disseny: s'eliminen truncats de títols i descripcions. |
| 8.3.0 | 8.0.0 | 14 novembre, 2025 | Disseny: s'ha afegit un màxim de 5 línies de descripció i un màxim d'amplada en la versió small de 264 px. Desenvolupament: resolució de problemes. |
| 8.0.0 | 6.2.1 | 3 octubre, 2025 | Desenvolupament: nova propietat afegida o eliminada. |
| 8.0.0 | 6.1.0 | 12 setembre, 2025 | Disseny: s'elimina l'amplada màxima de contenidor i es posa directament en el text per evitar que els botons quedin separats del marge dret. Desenvolupament: nova propietat afegida. |
| 6.0.0 | 6.0.1 | 28 juliol, 2025 | Desenvolupament: resolució de problemes. |
| 6.0.0 | 6.0.0 | 8 juliol, 2025 | Disseny: s'ajusten mides màximes de contenidors. |
| 5.0.0 | 6.0.0 | 3 juliol, 2025 | Desenvolupament: resolució de problemes. |
| 5.0.0 | 5.0.0 | 10 juny, 2025 | Disseny: es modifica la posició dels botons en els dos punts de tall. |
| 4.0.0 | 5.0.0 | 9 juny, 2025 | Desenvolupament: resolució de problemes. |
| 4.0.0 | 4.0.1 | 19 maig, 2025 | Desenvolupament: resolució de problemes. |
| 1.0.0 | 0.0.3 | 1 novembre, 2024 | Disseny, desenvolupament i documentació del component. |

## Vegeu també
- [Indicador de funció](component-indicador-de-funcio.md): per a mostrar temporalment text breu i contextual.
- [Modals](component-modals.md): per proporcionar informació crítica o demanar una decisió.
- [Notificació emergent](component-notificacio-emergent.md) (Toast): per a notificacions breus i temporals que no requereixen una acció.
- [Botons](component-botons.md)
- [Enllaços](component-enllacos.md)
