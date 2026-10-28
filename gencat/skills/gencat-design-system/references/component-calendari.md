# Calendari (Calendar)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/681fe4 · Web component: `<calendar-component>` (paquet core) · Font actualitzada el 2026-10-22 · Extret el 2026-10-28

## Què és i quan usar-lo
Component visual que permet als usuaris navegar per mesos i seleccionar dates concretes dins d'una vista mensual. Està pensat per oferir una interacció dinàmica que facilita la consulta de contingut o informació vinculada a dies específics.

Quan s'utilitza:
- Consultar informació associada a dates concretes dins d'un període mensual.
- Navegar per mesos per localitzar continguts distribuïts cronològicament.
- Mostrar canvis o estats associats a dies (com avisos, activitats, fets rellevants, etc.).
- Afavorir la consulta ràpida de dades temporals sense necessitat de fer cerques textuals o filtratges manuals.
- Espais d'informació contextual que depenen del dia com:
  - Agents institucionals o culturals.
  - Cronologies d'activitats o esdeveniments públics.
  - Seguiment de processos temporals (com períodes d'inscripció, canvis en serveis, etc.).

## Quan NO usar-lo / alternatives
No utilitzis el component de calendari quan:
- L'usuari ha de seleccionar una data o un rang de dates per introduir en un formulari: utilitza el [Selector de data](component-selector-de-data.md).
- No hi ha informació diferenciada per dia: si tot el contingut és genèric o no varia segons la data, no cal mostrar un calendari.
- El volum de dades per dia és massa alt o complex per ser consultat dins la interfície del calendari (potser és millor consultar les dades en una taula o tenir un llistat amb filtres temporals).
- Es necessita una gestió detallada de múltiples franges horàries dins un dia (per això es podria usar un calendari tipus agenda setmanal o diària més avançat).

## Anatomia
Figma: Calendar [Breakpoint = Extra Large - Medium, Months collapsed = True, Collapsed = True, Years collapsed = True].

## Variants, tipus i estats

### Calendari

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Extra Large - Medium / Small | Extra Large - Medium |
| Months collapsed | True / False | True |
| Years collapsed | True / False | True |
| Collapsed | True / False | True |

Subseccions de la font (cadascuna il·lustrada amb la variant Figma Calendar [Breakpoint, Months collapsed, Collapsed, Years collapsed]): Punts de tall, Mesos desplegats/replegats, Calendari desplegat/replegat.

### Números (dies)

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Default / Hover / Focus / Not available | Default |
| Selected | True / False | False |
| Today | True / False | False |

Estats. Figma: _Calendar_Numbers [Show Today = False, State = Default, Selected = False].

### Botó desplegable

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Default / Hover / Focus / Not available | Default |
| Collapsed | True / False | False |

Estats i xebró desplegat/replegat. Figma: _Calendar_Expandable button [State = Default, Collapsed = True].

## Comportament i interacció
### Desplegar / replegar
El calendari, per defecte, es mostra replegat. A través del botó inferior l'usuari pot desplegar la informació per veure el mes complet.

### Navegació

**Calendari replegat**
- Dies: es mostren els set dies de la setmana (de dilluns a diumenge). En seleccionar un dels xebrons (dret o esquerre) es desplacen els dies de la setmana i es mostren els set dies següents, sempre començant pel dilluns (Figma: Dies_replegat). Quan en una setmana coincideixin dos mesos, es mostren al desplegable del mes els dos mesos separats per un guionet; en format mòbil, amb les abreviatures (Figma: Dies_replegat_ultima setmana).
- Mesos: per navegar entre mesos hi ha el desplegable superior que canvia la vista de la setmana a mesos. Es mostren els mesos en format horitzontal i es poden seleccionar o navegar amb els xebrons. Sempre es mostra el mes actual seleccionat (Figma: Mesos_replegat).
- Anys: la navegació entre anys es fa a través del selector de data superior, utilitzant els xebrons corresponents (Figma: Anys).

**Calendari desplegat**
- Dies: es mostren tots els dies del mes, del primer a l'últim. En seleccionar un dels xebrons (dret o esquerre) es desplaça el mes sencer i es mostra el següent o l'anterior (Figma: Desplegat_dies).
- Mesos: el desplegable superior canvia la vista de la setmana a mesos; es mostren en format vertical a tres o quatre columnes (en funció del punt de tall) (Figma: Desplegat_mesos).
- Anys: la navegació entre anys es fa de la mateixa forma que entre mesos, amb el desplegable corresponent de la part superior (Figma: Desplegat_anys).

### Teclat
Vegeu "Accessibilitat" (ordre del focus i taula de tecles).

## Contingut i microcopy
- Botó "ves a avui" (present al calendari desplegat).
- Si en seleccionar una data no hi ha resultats, mostra un estat buit a la pàgina.

## Bones pràctiques
### Filtre
- **NO FER:** No utilitzis el component calendari dins d'un conjunt de filtres. En aquest cas utilitza el selector de data.

### Elements del component
- **NO FER:** No amaguis elements del component com el context temporal (mes/any) o els controls de navegació.
- **NO FER:** No modifiquis la distribució dels mesos de l'any.

### Resultats
- **FER:** Inclou un estat buit a la pàgina si en seleccionar una de les dates no hi ha resultats disponibles perquè aquell dia, per exemple, no hi ha cap esdeveniment.
- **FER:** Inclou la data seleccionada en la maquetació de la pàgina perquè l'usuari no perdi la referència d'on es troba quan es desplaci per les diferents setmanes.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG):
- **Orientació (AA)** (1.3.4): el contingut del calendari s'adapta a les diferents orientacions de la pantalla, com ara vertical o horitzontal, cosa que permet visualitzar el contingut. [CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Ús del color (A)** (1.4.1): el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per diferenciar els diferents estats dels dies i dels altres elements s'utilitzen subratllats amb diferents gruixos de vores, la presència de farciment, etc. [CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA)** (1.4.3): els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són excepció d'aquesta norma. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA)** (1.4.4): excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA)** (1.4.11): els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A)** (2.1.1): tota la funcionalitat del contingut es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Ordre del focus (A)** (2.4.3): [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-order) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-order)
  - Calendari **replegat**: 1) Desplegable del mes; 2) Xebró esquerre del selector d'any; 3) Xebró dret del selector d'any; 4) Xebró esquerre del navegador de dies; 5) Conjunt de dies (la navegació entre els dies es fa amb les fletxes dreta i esquerra); 6) Xebró dret del navegador de dies; 7) Botó desplegable del calendari. Hi ha ordres de focus diferents segons si el botó primari està situat a l'esquerra o la dreta (Figma: Ordre del focus_collapsed).
  - Calendari **desplegat** (l'ordre varia per la distribució dels botons): 1) Desplegable del mes; 2) Xebró esquerre del selector d'any; 3) Xebró dret del selector d'any; 4) Conjunt de dies (navegació amb les fletxes dreta, esquerra, amunt i avall); 5) Xebró esquerre del navegador de dies; 6) Botó "ves a avui"; 7) Xebró dret del navegador de dies; 8) Botó desplegable del calendari (Figma: Ordre del focus_expanded).
- **Focus visible (AA)** (2.4.7): la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- **Redistribució** (1.4.10): si l'usuari augmenta el text al 200% en pantalles petites i no hi ha prou espai per mostrar el calendari en el format per defecte, aquest modifica la disposició dels dies d'horitzontal a vertical (Figma: Redistribució). Aquest comportament està aplicat a desenvolupament, però no a disseny. [CAT](https://www.w3.org/Translations/WCAG22-ca/#reflow) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/reflow)

### Navegació per teclat

| Tecla | Acció |
|---|---|
| Tabulació | Navegar a l'element interactiu següent |
| Shift + Tabulació | Navegar a l'element interactiu anterior |
| Fletxes | Desplaçar-se pels diferents elements (selecció de mes i dies) del calendari |
| Intro | Seleccionar el dia |

## Implementació (component web)

### `<calendar-component>`
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat (lloc) |
|---|---|---|---|---|---|
| `disablePastDates` | `disable-past-dates` | Permet deshabilitar els dies anteriors al dia actual. | boolean | `false` | Opcional |
| `disabledDates` | `disabled-dates` | Permet deshabilitar dates concretes. Accepta array o string JSON. | string (array) | `undefined` | Opcional |
| `disabledWeekends` | `disabled-weekends` | Permet deshabilitar els caps de setmana. | boolean | `false` | Opcional |
| `value` | - (el PDF mostra `-/`; no es defineix com a atribut HTML) | Valor per defecte en carregar el component / valor actual del component. | Date | `undefined` | Opcional |

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `valueChange` | Emès quan es fa clic en una data (PDF: quan el valor del component canvia; `CustomEvent<any>`). El seu valor és la data clicada. | `value` | `calendar-component` |
| `handlerClick` | Es llança cada cop que es fa clic en un botó; com a paràmetre conté les dades de l'esdeveniment | id | `button-component` |
| `focusButton` | Es llança cada cop que es fa focus en un botó | - | `button-component` |
| `blurButton` | Es llança cada cop que es treu el focus en un botó | - | `button-component` |

**Depèn de:** `button-component` ([Grup de botons](component-grup-de-botons.md); [Botons](component-botons.md)).

**Exemple d'ús**

```html
<!-- /index.html -->
<calendar-component
  disabled-weekends="true"
  disabled-dates='["2025-06-19", "2025-06-20"]'
  disable-past-dates="true">
</calendar-component>

<!--Les trucades als components només admeten elements HTML, per tant per inicialitzar value, caldrà fer-ho mitjançant un script-->
<script>
  const calendar = document.querySelector('calendar-component');
  calendar.value = new Date(2025, 8, 2);
</script>
```

Exemple d'instància (PDF):

```html
<calendar-component
disable-past-dates=false
disabled-dates="texto-ejemplo"
disabled-weekends=false
-/="valor"
></calendar-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 8.0.0 | 12.0.1 | 14 juliol, 2026 | Desenvolupament: s'estableix com a maxYear l'any actual + 2000 |
| 8.0.0 | 12.0.0 | 10 juliol, 2026 | Desenvolupament: s'utilitza el token correcte per al color dels textos dels dies del calendari; s'utilitza el token correcte per al color dels dies disabled |
| 8.0.0 | 10.1.0 | 29 maig, 2026 | Desenvolupament: ajustos d'accessibilitat |
| 8.0.0 | 10.0.0 | 8 maig, 2026 | Desenvolupament: correccions del mode focus en mòbil |
| 8.0.0 | 9.2.0 | 27 febrer, 2026 | Desenvolupament: millores d'accessibilitat |
| 8.0.0 | 9.1.0 | 6 febrer, 2026 | Desenvolupament: es fa reactiva la propietat value |
| 8.0.0 | 8.5.0 | 5 desembre, 2025 | Desenvolupament: el selector d'any es canvia a desplegable |
| 8.0.0 | 8.0.0 | 14 novembre, 2025 | Desenvolupament: resolució de problemes |
| 8.0.0 | 6.2.1 | 3 octubre, 2025 | Desenvolupament: resolució de problemes. |
| 8.0.0 | 6.1.0 | 12 setembre, 2025 | Disseny: es modifica la selecció d'any. Es passa de navegació individual any a any a desplegable. Desenvolupament: nova propietat afegida |
| 6.0.0 | 6.0.1 | 28 juliol, 2025 | Desenvolupament de l'evolutiu |
| 6.0.0 | 6.0.0 | 8 juliol, 2025 | Disseny: es mostren números i botons del week i month selector que estaven ocults. |
| 5.0.0 | 6.0.0 | 3 juliol, 2025 | Desenvolupament del component. |
| 5.0.0 | No aplica | 10 juny 2025 | Disseny i documentació del component. |

## Vegeu també
- [Selector de data](component-selector-de-data.md): per a introduir i recopilar dades de manera interactiva. [discrepància: el lloc enllaça aquest text a la pàgina de Camp d'entrada (uid 7912b2); el nom indica Selector de data]
- [Estat buit](component-estat-buit.md)
- [Botons](component-botons.md)
- [Grup de botons](component-grup-de-botons.md)
