# Pas a pas (Stepper)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/728dba · Web component: `<stepper-component>` (paquet core) · Font actualitzada el 2026-10-15 · Extret el 2026-10-28

## Què és i quan usar-lo
Seqüència de passos que guien l'usuari a través d'un procés complex.

Component ideal per a formularis o processos complexos en què s'ha de guiar l'usuari per un conjunt de **mínim dos passos** que requereixen una **acció per part de l'usuari** per avançar.

Quan s'utilitza: per organitzar la informació en seccions lògiques i consecutives, el procés esdevé menys aclaparador i més estructurat. Això ajuda a garantir que els usuaris completin totes les seccions necessàries sense ometre informació crucial, facilitant així la recopilació de dades de manera eficient i precisa. Exemples d'ús:
- Procés de registre.
- Compres en línia.
- Sol·licituds.
- Inscripcions.
- Registres mèdics.

## Quan NO usar-lo / alternatives
El pas a pas no s'ha de fer servir quan **el procés es pot completar en qualsevol ordre** o quan **el nombre de passos pot canviar en funció de la lògica condicional**.

No s'ha de confondre amb la barra de progrés ni amb el rastrejador d'estat:

| Component | Descripció | Exemples |
|---|---|---|
| [Barra de progrés](component-barra-de-progres.md) | Fa un seguiment del progrés dels objectius que són més grans i que no es poden completar d'una vegada. L'usuari ha de fer una acció, però no pot revertir el progrés un cop s'ha completat. | Completar dades d'un perfil (LinkedIn). |
| [Rastrejador d'estat](component-rastrejador-d-estat.md) | Mostra el progrés i l'estat actuals sense requerir accions de l'usuari per avançar. Principalment informatiu, no requereix interactivitat per completar el procés. | Seguiment d'enviaments, estat de processament de sol·licituds, fases d'un projecte. |

## Anatomia
Figma: _Stepper_items [Show Line Right = True, Show Line Left = True, Step name = Nom del pas, State = Current].

## Variants, tipus i estats
El component pas a pas no disposa de variants en ell mateix (Figma: Stepper), però sí cadascun dels seus ítems.

Ítems del pas a pas:

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Current / Done / Pending | Current |

- **En progrés (Current):** l'usuari està interactuant amb la informació d'aquell pas.
- **Completat (Done):** l'usuari ha omplert la informació requerida i ha progressat al següent pas.
- **Pendent (Pending):** indica els següents passos que haurà de fer l'usuari.

Variants Figma de l'ítem: Show Line Right = True | False; Show Line Left = True | False (propietats booleanes vinculades a les línies de cada pas, des de la versió Figma 2.4.0); Step name = Nom del pas; State = Current | Done | Pending.

## Mides i espaiats
- L'amplada mínima del pas a pas (stepper) és de **960 px**. A partir d'aquest punt de ruptura (breakpoint) es passa a utilitzar la **barra de passos seqüencial** de la secció de la [barra de progrés](component-barra-de-progres.md).
- Figma de la barra de passos seqüencial: Step bar [Show Step 7 = True, Show Step 6 = True, Show Step 5 = True, Show Step 4 = True, Steps = Pas X de Y, Type = Sequence, Step = First].

## Comportament i interacció
### Tornar enrere
Si l'usuari està editant un pas i torna enrere, el pas que estava editant en un primer moment apareix com a pendent i l'actual com a en progrés. Si l'usuari havia introduït dades en aquell pas, el sistema guarda les dades i, si no estan lligades amb la informació del pas o contingut que modifiqui l'usuari, es manté guardada la informació.

### Desar el procés
Els processos han de permetre que l'usuari guardi la informació que ha omplert fins al moment. La notificació que s'ha guardat correctament es fa a través d'una notificació. Sempre que sigui possible, i encara que s'incorpori el botó de desar, el sistema hauria de guardar el procés de forma automàtica.

### Adaptació responsiva
Vegeu "Mides i espaiats": per sota de 960 px es passa a la barra de passos seqüencial (en la visualització mòbil el text `textPrePas` es mostra davant del número de pas).

## Bones pràctiques
### Etiquetes
- **FER:** Utilitza etiquetes clares i concises (entre una i tres paraules) per indicar el nom de cada pas.
- **NO FER:** No utilitzis etiquetes molt llargues i excessivament descriptives. Evita també utilitzar noms genèrics que no contextualitzen cada pas del procés, com per exemple "pas 1", "pas 2", etc.
- **FER:** Mantingues una coherència entre el nom del pas i el títol de la secció, utilitzant les mateixes paraules en els dos casos.
- **NO FER:** Evita que el títol de la secció tingui un nom diferent de l'etiqueta del pas, ja que pot confondre l'usuari sobre quin punt del procés està.

### Disposició dels passos
- **NO FER:** No utilitzis un pas a pas amb més de set passos, ja que pot crear problemes de maquetació i carregar la pàgina de massa informació.
- **FER:** Si tens un procés llarg o complex (més de set passos), agrupa el contingut en passos més genèrics i divideix cada pas en diferents subapartats.
- **NO FER:** No utilitzis un component pas a pas niat dins d'un altre, ja que pot crear confusió en la navegació i jerarquia de continguts.
- **FER:** Si un pas del procés té diferents subapartats, utilitza altres recursos visuals per organitzar la informació, com ara subtítols o divisors.
- **FER:** Informa l'usuari de la posició o pas del procés on es troba.
- **NO FER:** No col·loquis el component sense cap pas marcat. Sempre hi ha d'haver com a mínim el primer pas en procés.
- **FER:** Ofereix a l'usuari formes de sortir del procés i, sempre que es pugui, l'opció de guardar el progrés realitzat, sigui amb un botó de guardar o a través d'un procés automàtic. En qualsevol dels casos, s'ha d'informar l'usuari.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG):
- **Orientació (AA)** (1.3.4): el contingut de l'àrea de text s'adapta a les diferents orientacions de la pantalla, com ara vertical o horitzontal, cosa que permet visualitzar el contingut. [CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Ús del color (A)** (1.4.1): el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a indicar els diferents estats es fan servir icones representatives. [CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA)** (1.4.3): els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA)** (1.4.4): excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA)** (1.4.11): els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)

## Implementació (component web)

### `<stepper-component>`
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat (lloc) |
|---|---|---|---|---|---|
| `steps` | `steps` | Array amb la informació de cada pas (el PDF el descriu com a "valor del pas actual del stepper"). | string (array JSON) | `undefined` | Obligatori |
| `textPrePas` | `text-pre-pas` | Text visible davant del número de pas en la visualització mòbil. | string | `undefined` | Opcional |

**Props que accepten JSON: estructura de `steps`**

| Propietat | Descripció | Atribut | Obligatorietat | Tipus |
|---|---|---|---|---|
| `nomPas` | Nom del pas | `nomPas` | Obligatori | String |
| `number` | Número de l'step | `number` | Opcional | Number |
| `state` | Estat d'aquest pas. Possibles valors: `done`, `pending`, `current` | `state` | Obligatori | String |

**Esdeveniments**

| Esdeveniment | Descripció | Tipus / paràmetre | Origen |
|---|---|---|---|
| `stepStatus` | Es llança cada vegada que es fa clic en un pas; com a paràmetre conté les dades del pas. | `CustomEvent<string>` | `stepper-component` |
| `stepChanged` | Es dispara quan es canvia el pas actual (paràmetre: number del pas). | `CustomEvent<number>` | `stepper-component` |

**Mètodes públics**

| Mètode | Acció | Paràmetre |
|---|---|---|
| `changeStep(change: number)` | Permet avançar o retrocedir passos i dispara l'esdeveniment `stepChanged`. | `change` |

**Depèn de:** `progress-bar-component` ([Barra de progrés](component-barra-de-progres.md)).

**Exemple d'ús**

```html
<!-- /index.html -->
<stepper-component
    text-pre-pas="Pas"
    steps='[
      { "number": 1, "nomPas": "Nombre paso 1", "state": "done" },
      { "number": 2, "nomPas": "Nombre paso 2", "state": "done" },
      { "number": 3, "nomPas": "Nombre paso 3", "state": "done" },
      { "number": 4, "nomPas": "Nombre paso 4", "state": "done" },
      { "number": 5, "nomPas": "Nombre paso 5", "state": "current" },
      { "number": 6, "nomPas": "Nombre paso 6", "state": "pending" },
      { "number": 7, "nomPas": "Nombre paso 7", "state": "pending" }
    ]'
></stepper-component>
```

Exemple d'instància (PDF):

```html
<stepper-component
steps="texto-ejemplo"
text-pre-pas="texto-ejemplo"
></stepper-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 2.4.0 | 11.0.0 | 19 juny, 2026 | Desenvolupament: ajustos d'accessibilitat amb lector de pantalla |
| 2.4.0 | 2.0.0 | 10 març, 2025 | Disseny: es vinculen propietats relacionades amb les línies de cada pas (booleanes de Line Right i Line Left). |
| 2.3.0 | 1.0.0 | 31 gener, 2025 | Sense canvis |
| 2.2.0 | 0.1.1 | 20 desembre, 2024 | Sense canvis |
| 2.1.0 | 0.1.1 | 04 desembre, 2024 | Sense canvis |
| 2.0.0 | 0.1.0 | 02 desembre, 2024 | Sense canvis |
| 1.1.0 | 0.1.0 | 22 novembre, 2024 | Sense canvis |
| 1.1.0 | 0.0.4 | 18 novembre, 2024 | Sense canvis |
| 1.0.0 | 0.0.3 | 1 novembre, 2024 | Disseny, desenvolupament i documentació del component |

## Vegeu també
- [Barra de progrés](component-barra-de-progres.md): per a indicar l'avanç d'una tasca amb el pas del temps.
- [Rastrejador d'estat](component-rastrejador-d-estat.md): per monitorar, informar i mostrar l'estat de tasques, projectes, etc.
