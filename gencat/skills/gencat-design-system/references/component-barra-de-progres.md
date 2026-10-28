# Barra de progrés (Progress bar)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/38e023 · Web component: `<progress-bar-component>` (paquet core) · Font actualitzada el 2026-07-10 · Extret el 2026-10-28

## Què és i quan usar-lo
La barra de progrés és un element visual que mostra l'estat d'avanç d'una tasca, reflectint el seu progrés en temps real. **Representa visualment el progrés determinat d'una tasca o procés de càrrega mitjançant una barra horitzontal que s'omple gradualment.** Els usuaris poden veure el percentatge, el temps restant o els passos de finalització.

Es fa servir per a casos en què el temps d'espera és superior a 10 segons. Si el temps és superior a aquests 10 segons, però és indeterminat, caldrà valorar altres formes de comunicar el procés mitjançant alertes o modals.

### Barra de càrrega
El procés es produeix de forma automàtica. S'usa per a:
- Tasques com càrrega o descàrrega d'arxius, instal·lar una actualització, executar una anàlisi de dades, entre altres. Són casos on es pot indicar el percentatge o valor del procés.
- Processos de molts passos. Encara que, per defecte, per a processos s'utilitzi la barra de progrés per passos, si aquest és excessivament llarg, s'utilitzarà la barra de progrés lineal per evitar saturar l'usuari.

### Barra de passos
El procés avança de forma escalonada cada cop que l'usuari realitza l'acció de continuar. S'utilitza per a:
- Processos en els quals s'indica per quin pas va l'usuari i quants li queden per finalitzar. En aquest cas, no se sap quant de temps trigarà l'usuari a completar el procés.

El progrés per passos lineal es podrà fer servir tant en versió escriptori com en mòbil, mentre que el continu s'usarà únicament per a mòbil. Per a la versió d'escriptori s'usarà el [Pas a pas](component-pas-a-pas.md).

## Quan NO usar-lo / alternatives
### Barra de càrrega
- Quan el progrés sigui indeterminat; en aquests casos s'usarà l'[Indicador de càrrega](component-indicador-de-carrega.md).

### Barra de passos
- Per a progressos de menys de set passos en la versió d'escriptori.

## Anatomia
Figma (barra de càrrega): Loading [Show Label = True, Show Help = True, Show Check icon = True, Show Tootilp = True, Label text = Etiqueta, Help text = Text d'ajuda, State = Loading 5%].

Figma (barra de passos, seqüencial i lineal): Step bar [Show Step 7 = True, Show Step 6 = True, Show Step 5 = True, Show Step 4 = True, Steps = Pas X de Y, Type = Sequencce, Step = First].

## Variants, tipus i estats

### Barra de càrrega

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Step | First / Second / Third / Fourth / Fifth / Sixth / Seventh | First |
| Error | No / Yes | No |

### Barra de passos

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Step | First / Second / Third / Fourth / Fifth / Sixth / Seventh / Eighth / Nineth / Tenth | First |
| Type | Lineal / Sequence | Sequence |

Tipus de barra (component web): `linear-bar`, `loading-bar`, `sequential-bar`. Estats (component web): `current`, `done`, `error`, `loaded`, `loading`, `pending`.

## Mides i espaiats
La barra de progrés (en totes les seves versions) s'adaptarà al contenidor fins a una amplada màxima:
- La barra de **càrrega** i la de **passos** **lineal** tindran una **amplada màxima de 600 px.**
- En el cas de la barra pas a pas **seqüencial**, enfocada a la versió mòbil, tindrà una **amplada màxima de 480 px.**

## Comportament i interacció
- **Barra de càrrega:** la barra de procés es carrega de forma automàtica, de manera proporcional a la càrrega del procés.
- **Barra de passos:** els dos tipus (seqüencial i lineal) es carreguen a mesura que l'usuari realitza l'acció de continuar dins d'un procés.

### Èxit
Quan el procés o tasca ha finalitzat correctament, apareix la confirmació a través de l'estat completat. Un cop completat el procés, la barra pot tenir diferents comportaments segons el cas d'ús:
- **Desaparèixer:** en casos en què es disposi d'un element fix que mostri que s'ha completat el procés. Exemple: en el carregador d'arxius apareix que el fitxer s'ha pujat.
- **Missatge de confirmació:** en casos en què no es disposi d'un element fix que mostri que s'ha completat el procés. Exemple: instal·lació d'una aplicació.

### Errors
- Si el component de la barra de progrés forma part d'un altre element, com per exemple un *file uploader* (carregador de fitxers), l'error apareixerà integrat dins d'aquest segon component.
- Si s'utilitza la barra de progrés contínua de manera independent, l'error pot manifestar-se a **la barra** o, en el cas d'una **acció crítica,** a través d'una **modal**.

### Adaptació responsiva
Vegeu "Mides i espaiats" (amplades màximes de 600 px i 480 px).

## Bones pràctiques
### Barra de càrrega
Cancel·lar:
- **FER:** Si és possible, permet posar en pausa o cancel·lar el procés.

Unitats:
- **FER:** Utilitza unitats de temps específiques o aproximades. Es permet fer servir un rang de temps per indicar el procés restant.
- **NO FER:** No utilitzis unitats de temps que siguin imprecises o confuses.

### Barra de passos
Versió seqüencial vs. versió lineal:
- **FER:** Utilitza la versió seqüencial per processos que no superen els set passos en dispositius mòbils.
- **FER:** Utilitza la versió lineal quan el procés supera els set passos.

### General
Canvis de component:
- **FER:** Mantingues el mateix tipus d'indicador de procés (indicador de càrrega o barra de progrés) durant tot el procés o tasca.
- **NO FER:** No canviïs d'un tipus d'indicador de procés (indicador de càrrega o barra de progrés) a un altre a la meitat del procés o tasca.
- **FER:** Utilitza la barra de progrés indicant el valor que correspongui segons el context.
- **NO FER:** No utilitzis la barra de progrés sense indicar el valor que correspongui segons el context.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG):
- **Ús del color (A)** — [1.4.1](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color): el color no es fa servir com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a indicar el pas, percentatge, etc. en el que es troba el procés o tasca s'utilitza informació textual a part de gràfica.
- **Contrast mínim (AA)** — [1.4.3](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum): els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma.
- **Canvia la mida del text (AA)** — [1.4.4](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text): excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat.
- **Contrast d'elements no textuals (AA)** — [1.4.11](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast): els elements gràfics com icones i vores presenten un contrast mínim de 3:1.
- **Identificació d'errors (A)** — [3.3.1](https://www.w3.org/Translations/WCAG22-ca/#error-identification) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/error-identification): si hi ha un error en la càrrega de fitxers, aquest es mostra clarament mitjançant un canvi de color de la barra i una indicació visual (icona) i textual (descripció de l'error).

## Implementació (component web)

### `<progress-bar-component>`
Paquet: core. Sense esdeveniments declarats.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat |
|---|---|---|---|---|---|
| `barType` | `bar-type` | Tipus de barra de progrés: `linear-bar`, `loading-bar` o `sequential-bar`. | string | undefined | Obligatori |
| `errorMessage` | `error-message` | Missatge que es mostra quan hi ha un error en el procés. | string | undefined | Opcional |
| `helpText` | `help-text` | Text d'ajuda o instrucció per a l'usuari, sota la barra de càrrega. | string | undefined | Opcional |
| `progress` | `progress` | Número que indica el percentatge de progrés (del 0 al 100). | number | undefined | Obligatori |
| `progressTitle` | `progress-title` | Títol del component (text de l'etiqueta). | string | undefined | Obligatori |
| `showTooltip` | `show-tooltip` | Indica si s'ha de mostrar l'indicador de funció (mostra o oculta aquest element). | boolean | true | Obligatori |
| `status` | `status` | Estat actual de la barra de progrés. Opcions: `current`, `done`, `error`, `loaded`, `loading`, `pending`. | string | undefined | Obligatori |
| `stepStatus` | `step-status` | *Array* que representa l'estat de cada pas en barres de tipus `sequential-bar` o `linear-bar` (valor del pas actual del stepper). Si hi ha vuit passos o més la `sequential-bar` es converteix en `linear-bar`. | string (array) | `[]` | Obligatori |
| `textAlternativeError` | `text-alternative-error` | Text alternatiu que descriu l'error; es mostra en passar el ratolí per sobre de la icona d'error. | string | undefined | Opcional |
| `textPrePas` | `text-pre-pas` | Text anterior al nombre de passos en la `linear-bar` (text visible al component). | string | undefined | Obligatori |
| `tooltiptext` | `tooltiptext` | Text que es mostra en passar el ratolí sobre l'indicador de funció (tooltip associat). | string | `Tooltip Text` | Opcional |

**Variants**

| Propietat | Per defecte | Valors |
|---|---|---|
| `barType` | - | `linear-bar` `loading-bar` `sequential-bar` |
| `progress` | - | Número del 0 al 100 |
| `status` | - | `current` `done` `error` `loaded` `loading` `pending` |

**Depèn de:** `tooltip-component` ([Indicador de funció](component-indicador-de-funcio.md))

**Utilitzat per:** `file-uploader-component` ([Carregador d'arxius](component-carregador-d-arxius.md)), `stepper-component` ([Pas a pas](component-pas-a-pas.md))

**Exemple d'ús**

```html
<!-- /index.html -->
<progress-bar-component
      progress-title="Etiqueta"
      help-text="L'operació va ser reeixida"
      progress="100"
      status="loaded"
      bar-type="loading-bar"
      step-status='["done","done","done","done","done","done","current","pending","pending","pending"]'
      show-tooltip="true"
      tooltiptext="Text tooltip"
      error-message="Error"
      text-alternative-error="Text alternatiu"
      text-pre-pas="Pas"
></progress-bar-component>
```

Exemple d'instància del PDF:

```html
<progress-bar-component
bar-type="linear-bar"
error-message="texto-ejemplo"
help-text="texto-ejemplo"
progress=0
progress-title="texto-ejemplo"
show-tooltip=true
status="current"
step-status='[]'
text-alternative-error="texto-ejemplo"
text-pre-pas="texto-ejemplo"
tooltiptext='Tooltip Text'
></progress-bar-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 8.4.0 | 12.0.0 | 10 juliol, 2026 | **Desenvolupament:** s'utilitza el token correcte per al color dels textos i barra de progrés |
| 8.4.0 | 0.0.3 | 5 desembre, 2025 | **Disseny**: Es modifica la posició fixa de la barra per una adaptativa perquè s'adapti a mides inferiors dins el carregador d'arxius o altres components. |
| 1.0.0 | 0.0.3 | 1 novembre, 2024 | **Disseny**, **desenvolupament** i **documentació** del component |

## Vegeu també
- [Carregador d'arxius](component-carregador-d-arxius.md): per seleccionar i pujar arxius a un lloc específic.
- [Pas a pas](component-pas-a-pas.md): per guiar a l'usuari a través d'un procés complex.
- [Rastrejador d'estat](component-rastrejador-d-estat.md): per monitorar, informar i mostrar l'estat de tasques, projectes, etc.
- [Indicador de càrrega](component-indicador-de-carrega.md)
- [Indicador de funció](component-indicador-de-funcio.md)
