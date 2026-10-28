# Indicador de càrrega (Spinner)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/408ab8 · Web component: `<spinner-component>` (paquet core) · Font actualitzada el 2026-10-06 · Extret el 2026-10-28

## Què és i quan usar-lo
Indicador gràfic que representa visualment que un procés està en curs durant un període d'espera indeterminat.

Representa visualment que un procés està en curs, normalment associat a la càrrega de dades o a accions del sistema iniciades per un usuari. Proporciona senyals visuals durant un període d'espera breu i indeterminat.

A diferència de la barra de progrés, un indicador de càrrega és un indicador indeterminat, que no informa del temps d'espera. S'utilitza quan es desconeix el progrés, quan els temps de càrrega són ràpids o quan no és necessari indicar el temps que trigarà un procés.

Quan s'utilitza:
- Per a processos de càrrega indeterminats, on no es pot fer una estimació del temps total de càrrega ni indicar-ne el progrés.
- Quan es preveu un temps d'espera entre dos i deu segons.

## Quan NO usar-lo / alternatives
- No s'utilitza per a processos que triguen molt de temps a carregar-se (més de deu segons), ja que pot provocar frustració a l'usuari. En aquests casos, fes servir una barra de progrés per indicar el temps d'espera, o valora altres formes de comunicar el procés mitjançant alertes o modals. Vegeu [Barra de progrés](component-barra-de-progres.md): per a indicar l'avanç d'una tasca amb el pas del temps.
- No és necessari si una pàgina triga menys d'un segon a carregar-se, perquè és probable que no suposi una diferència en l'experiència d'usuari.

## Anatomia
Figma: Spinner [Size = Large, Color = Default].

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Color | Default / Red / Black / White | Default |
| Size | Medium / Small | Medium |

[discrepància: el lloc llista les mides Medium / Small amb valor per defecte Medium, però l'anatomia Figma mostra Size = Large i el codi defineix `spinner-large` / `spinner-small` amb valor per defecte `spinner-large`]

### Color
Variants Figma: Spinner [Size = Large, Color = Default | ...]. Usos:
- Per a la càrrega de pàgines i per a l'estat de càrrega del botó secundari i terciari sobre fons blanc.
- Per a l'estat de càrrega del botó primari sobre fons de color.
- Per a l'estat de càrrega del botó primari sobre fons fosc.
- Per a l'estat de càrrega del botó primari sobre fons blanc.

(La font mostra quatre variants de color amb aquests usos, en aquest ordre, sense assignar explícitament cada ús a Red / Black / White; [a verificar] la correspondència.)

### Mida
- Gran (large): s'utilitza en càrrega de pàgines o resultats.
- Petita (small): s'utilitza dins de components, com botons, on es disposa de poc espai.

## Mides i espaiats
- Si l'indicador va acompanyat d'un text, el text es col·loca centrat sota l'indicador a una distància de 16 dp per a la versió large i a 12 dp per a la versió small.

## Comportament i interacció
- L'indicador de càrrega no és un element interactiu.
- Posició: centrat dins del contenidor o la pàgina que estigui carregant. Quan es carreguin més elements en una pàgina, l'indicador es col·loca a l'espai buit on apareix el nou contingut, sense superposar-se al contingut existent.
- Si l'indicador va integrat dins d'un component, com per exemple un [botó](component-botons.md) o un [carregador d'arxius](component-carregador-d-arxius.md), la seva posició està especificada en el mateix component.

## Contingut i microcopy
Exemples de text contextual: "Carregar dades...", "Processant la seva sol·licitud...". Exemple de codi: "Recopilant dades...".

## Bones pràctiques
- **FER:** Acompanya l'indicador de càrrega amb informació contextual sobre què s'està carregant o processant. Per exemple, "Carregar dades...", "Processant la seva sol·licitud...".
- **NO FER:** No utilitzis diversos indicadors de càrrega a la vegada. Un ús excessiu pot crear massa distraccions, perjudicant l'experiència d'usuari.
- **FER:** Utilitza l'indicador de càrrega per a processos de càrrega indeterminats i que tenen una previsió de càrrega curta.
- **NO FER:** No l'utilitzis per a processos que triguen més de 10 segons a carregar-se, ja que pot provocar frustració a l'usuari. En aquests casos, utilitza una barra de progrés.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG):
- **Contrast mínim (AA)** (1.4.3): els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Contrast d'elements no textuals (AA)** (1.4.11): els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)

## Implementació (component web)

### `<spinner-component>`
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat (lloc) |
|---|---|---|---|---|---|
| `colorSpinner` | `color-spinner` | Color de l'indicador de càrrega. Opcions: `black`, `default`, `red`, `white`. | string | `default` | Obligatori |
| `sizeSpinner` | `size-spinner` | Mida de l'indicador de càrrega. Opcions: `spinner-large`, `spinner-small`. | string | `spinner-large` | Obligatori |
| `textSpinner` | `text-spinner` | Text visible sota l'indicador de càrrega. | string | `undefined` | Opcional |
| `visibilityTextSpinner` | `visibility-text-spinner` | Mostra o amaga el text sota l'indicador de càrrega. | boolean | `false` | Opcional |

**Variants**

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `colorSpinner` | `default` `red` `black` `white` | `default` |
| `sizeSpinner` | `spinner-large` `spinner-small` | `spinner-large` |

**Esdeveniments:** cap declarat.

**Utilitzat per:** `button-component` ([Botons](component-botons.md)).

**Exemple d'ús**

```html
<!-- /index.html -->
<spinner-component
  color-spinner="red"
  size-spinner="spinner-large"
  text-spinner="Recopilant dades..."
  visibility-text-spinner=true
></spinner-component>
```

Exemple d'instancia (PDF):

```html
<spinner-component
color-spinner='default'
size-spinner='spinner-large'
text-spinner="texto-ejemplo"
visibility-text-spinner=false
></spinner-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 2.3.0 | 9.4.0 | 17 abril, 2026 | Desenvolupament: s'ha substituït la propietat `srcSpinner` per `colorSpinner`, ja que l'spinner ja no es carrega mitjançant un GIF sinó que es genera per CSS i HTML. S'han eliminat els fitxers GIF de l'spinner. |
| 2.3.0 | 6.0.0 | 3 juliol, 2025 | Desenvolupament: resolució de problemes |
| 2.3.0 | 1.0.0 | 31 gener, 2025 | Sense canvis. |
| 2.2.0 | 0.1.1 | 20 gener, 2025 | Sense canvis. |
| 2.1.0 | 0.1.1 | 04 desembre, 2024 | Sense canvis. |
| 2.0.0 | 0.1.0 | 02 desembre, 2024 | Sense canvis. |
| 1.1.0 | 0.1.0 | 22 novembre, 2024 | Sense canvis. |
| 1.1.0 | 0.0.4 | 18 novembre, 2024 | Sense canvis. |
| 1.0.0 | 0.0.3 | 1 novembre, 2024 | Disseny, desenvolupament i documentació del component. |

## Vegeu també
- [Barra de progrés](component-barra-de-progres.md)
- [Botons](component-botons.md)
- [Carregador d'arxius](component-carregador-d-arxius.md)
