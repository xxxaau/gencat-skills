# Estat buit (Empty state)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/74975a · Web component: `<empty-state-component>` (paquet core) · Font actualitzada el 2026-10-05 · Extret el 2026-10-28

## Què és i quan usar-lo
Element que indica que no hi ha contingut per mostrar. Pot aparèixer quan l'usuari encara no ha afegit dades, quan una cerca no retorna resultats o quan s'aplica un filtre que deixa la vista buida.

Serveix per evitar que l'usuari es trobi amb una pàgina on no hi ha resultats de contingut o amb un component que no té dades a mostrar i que no tingui context del que ha pogut passar.

Els principals casos:
- Quan l'usuari arriba a una pàgina amb una secció sense informació o dades.
- En una pàgina de cerca quan no hi ha resultats de contingut.
- En components petits que no tenen dades a mostrar, com per exemple una agenda, una taula o unes dades estructurades.

## Quan NO usar-lo / alternatives
- Quan l'absència de dades és temporal i molt breu, com en una càrrega de pàgina.
- Quan es tracta d'un error amb un component o amb la pàgina.
- Quan ja s'ha comunicat l'estat a través d'un altre element de la interfície (per exemple la cel·la d'una taula que està buida i que mostri (-) quan no té dades).

## Anatomia
Figma: Empty state [Show Button = True, Show Link = True, Show Illustration = True, Illustration = No resultats, Variant = Page]. Elements possibles: il·lustració, títol, descripció, enllaç i botó.

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Variant | Page / Component | Page |
| Show Illustration | True / False | True |
| Show Link | True / False | True |
| Show Button | True / False | True |
| Show Title | True / False | True |
| Show Description | True / False | True |
| Title | - | Títol |
| Description | - | Descripció |

### Variant Component
Utilitza la variant **Component** quan l'estat buit afecta únicament una part de la interfície i la resta de la pàgina continua sent rellevant i funcional. Casos habituals:
- Una taula sense registres.
- Una llista sense elements.
- Una targeta o bloc de contingut sense informació.
- Un panell lateral buit.
- Una àrea de resultats sense resultats.
- Un bloc dins d'un formulari o procés que encara no conté informació.
- Un component d'un quadre de comandament sense dades.

### Variant Page (Pàgina)
Utilitza la variant **Page** quan l'estat buit afecta el contingut principal de la pàgina i no hi ha cap altre contingut rellevant per mostrar en aquesta àrea. Casos habituals:
- Una pàgina el contingut principal de la qual encara no s'ha creat.
- Una secció principal sense cap element per mostrar.
- Una pàgina de detall sense informació disponible.
- Una pàgina el contingut de la qual depèn d'una acció prèvia que encara no s'ha realitzat.

### Tipus d'estat buit
- **No hi ha resultats de cerca:** s'utilitza en pàgines de cerca quan no s'han trobat resultats.
- **No hi ha informació disponible:** s'utilitza en pàgines o seccions on no hi ha contingut a mostrar.

## Elements i criteris d'ús
Els elements de l'Estat buit són **opcionals segons la situació**. No cal mostrar-los tots en tots els casos.

### Criteris generals
- Prioritza la simplicitat. Mostra només els elements necessaris.
- Evita redundàncies. El títol, la descripció i les accions han d'aportar informació diferent.
- Tingues en compte l'espai disponible. En contextos compactes, redueix elements visuals o contingut secundari.
- Evita repeticions. Si hi ha diversos estats buits en una mateixa vista, simplifica la composició per reduir soroll visual.
- Revisa el context immediat. No repeteixis accions o informació que ja estiguin disponibles a prop.
- Mantingues una jerarquia clara. Si hi ha una acció principal per resoldre l'estat, prioritza-la.
- Adapta la composició al breakpoint. En espais reduïts alguns elements opcionals es poden simplificar o ometre.
- Assegura la comprensió textual. L'estat no ha de dependre únicament de la il·lustració o d'altres recursos visuals.

La combinació dels elements depèn del context. El Sistema de Disseny defineix els elements disponibles i els criteris generals d'ús, però no estableix una composició única per a cada component o cas d'ús.

### Il·lustració
Ha d'ajudar a identificar ràpidament l'estat o aportar significat.
- **Recomanat:** quan facilita una identificació visual ràpida; quan aporta significat i no és només decorativa; quan l'estat buit té prou pes i espai dins de la interfície.
- **Evita-ho:** quan l'espai és reduït; quan no aporta informació; quan hi ha diversos estats buits i la seva repetició genera soroll visual.

### Títol
Ha de comunicar què està passant o què trobarà la persona en aquest espai de forma molt breu.
- **Recomanat:** quan cal entendre l'estat de manera immediata; quan ajuda a identificar clarament el propòsit de l'espai.
- **Evita-ho:** quan el context ja fa evident l'estat; quan repetiria la mateixa informació que la descripció.

### Descripció
Ha d'informar amb detall sobre què està passant.
- **Recomanat:** quan cal complementar el títol; quan cal explicar per què no hi ha contingut; quan cal orientar la persona sobre el següent pas.
- **Evita-ho:** quan no afegeix informació nova; quan només repeteix el títol; quan incrementa innecessàriament la densitat del contingut.

### Enllaç
Ha de redirigir l'usuari a una informació complementària que el pugui ajudar, però que no sigui necessària per resoldre directament l'estat buit.
- **Recomanat:** per a ajuda, documentació o informació secundària; quan la navegació és complementària a l'acció principal.
- **Evita-ho:** quan duplica una acció ja disponible; quan l'acció resol directament l'estat buit; quan competeix amb l'acció principal.

### Botó
Utilitza'l quan hi hagi una acció principal que permeti resoldre o modificar directament l'estat buit.
- **Recomanat:** per crear, afegir, configurar, recuperar o executar una acció relacionada amb el contingut absent; quan representa el següent pas principal.
- **Evita-ho:** quan l'estat és només informatiu; quan no hi ha una acció clara; quan l'acció ja està disponible en el context immediat; quan només serveix per navegar a informació complementària.

## Comportament i interacció
Adapta l'orientació a vertical o horitzontal segons el context d'ús. En components petits només cal la descripció.

## Bones pràctiques

**Missatge concís**
- **FER:** Utilitza un missatge concís que informi l'usuari sobre per què la pantalla està buida.
- **NO FER:** No utilitzis un missatge genèric com "No hi ha res" sense cap indicació que no informi l'usuari.

**Concordança**
- **FER:** Utilitza correctament el text explicatiu i la il·lustració, adients en cada cas.
- **NO FER:** No utilitzis de manera errònia les il·lustracions i el text explicatiu.

**Accions rellevants**
- **FER:** Utilitza el botó si hi ha una acció a realitzar per tal de veure contingut.
- **NO FER:** No utilitzis el botó quan no sigui rellevant fer una acció.

**Adaptació de l'orientació i contingut**
- **FER:** Adapta l'orientació a vertical o horitzontal segons el context d'ús. En components petits només cal la descripció.

## Accessibilitat

### Pautes d'accessibilitat del contingut web (WCAG)
- **Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. [1.4.3 Contrast mínim - CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA):** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [1.4.4 Canvia la mida del text - CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA):** els elements gràfics presenten un contrast mínim de 3:1. [1.4.11 Contrast d'elements no textuals - CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A):** tota la funcionalitat del contingut es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [2.1.1 Teclat - CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Focus visible (AA):** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [2.4.7 Focus visible - CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

### Navegació per teclat

| Tecla | Acció |
|---|---|
| Tabulació | Navegació al següent element interactiu |
| Shift + Tabulació | Navegació a l'anterior element interactiu |
| Enter | Activar element interactiu (Enllaç/Botó) |

## Implementació (component web)

### `<empty-state-component>`

Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatori (lloc) |
|---|---|---|---|---|---|
| `emptyButtonText` | `empty-button-text` | Text que acompanya el botó | string | `undefined` | Opcional |
| `emptyDescription` | `empty-description` | Descripció del component | string | `undefined` | Opcional |
| `emptyImage` | `empty-image` | Imatge del component (URL de la imatge) | string | `undefined` | Opcional |
| `emptyLink` | `empty-link` | Array del component `link-component` (JSON) | string (JSON) | `undefined` | Opcional |
| `emptyPage` | `empty-page` | Mode de vista de `empty-state-component` (page/component); per defecte page | boolean | `true` | Opcional |
| `emptyTitle` | `empty-title` | Títol principal del component | string | `undefined` | Opcional |

**Props que accepten JSON.** Propietats de l'array `emptyLink`:

| Propietat | Atribut | Descripció | Tipus | Obligatori |
|---|---|---|---|---|
| `customId` | `custom-id` | Identificador personalitzat de l'enllaç | String | Opcional |
| `mode` | `mode` | Manera de l'enllaç: `external` o `internal` | String | Opcional |
| `text` | `text` | Text de l'enllaç | String | Obligatori |

**Esdeveniments (lloc)**

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `blurButton` | Es llança cada cop que es treu el focus en un botó del component | - | `button-component` |
| `focusButton` | Es llança cada cop que es fa focus en un botó del component | - | `button-component` |
| `handlerClick` | Esdeveniment llançat en fer clic sobre algun botó del component | `id` | `button-component` |
| `blurLink` | Es llança cada cop que es treu el focus en un enllaç del component | - | `link-component` |
| `focusLink` | Es llança cada cop que es fa focus en un enllaç del component | - | `link-component` |
| `linkEmit` | Esdeveniment llançat en fer clic sobre l'enllaç del component | `id` | `link-component` |

[discrepància: el lloc llista aquests esdeveniments heretats dels components fills; el PDF diu «Sin eventos declarados» per a `empty-state-component`]

**Depèn de:** `link-component` ([Enllaços](component-enllacos.md)), `button-component` ([Botons](component-botons.md)).

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<empty-state-component
  empty-title="Títol"
  empty-description="Descripció"
  empty-image="/assets/design/illustrations/Medium/No-resultats.svg"
  empty-button-text="Fes una altra cerca"
  empty-link='[{"text":"Enllaç 1º linia","mode":"external"}]'
  empty-page="true"
></empty-state-component>
```

**Exemple d'instància (PDF)**

```html
<empty-state-component
empty-button-text="texto-ejemplo"
empty-description="texto-ejemplo"
empty-image="texto-ejemplo"
empty-link="texto-ejemplo"
empty-page=true
empty-title="texto-ejemplo"
></empty-state-component>
```

## Claus de text (internacionalització)
Vegeu les [claus](dev-referencia-de-claus-disponibles.md) (`emptyState`).

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.5.0 | 9.1.0 | 02 octubre, 2026 | Disseny: canvi de nom de la propietat "Show Icon" a "Show Illustration". Correcció del nom de la propietat "Ilustration" a "Illustration". |
| 8.6.0 | 9.2.0 | 27 febrer, 2026 | Desenvolupament: es fan millores d'accessibilitat. |
| 8.6.0 | 9.2.0 | 27 febrer, 2026 | Desenvolupament: es crea la propietat customId. |
| 8.6.0 | 9.1.0 | 9 febrer, 2026 | Disseny: s'eliminen truncats. |
| 4.1.0 | 9.1.0 | 6 febrer, 2026 | Desenvolupament: es fan adaptacions d'accessibilitat pel que fa a mides de font extra gran i augment de pantalla. |
| 4.1.0 | 6.2.1 | 3 octubre, 2025 | Desenvolupament: nova propietat afegida o eliminada. |
| 4.1.0 | 5.0.0 | 9 juny, 2025 | Desenvolupament del component. |
| 4.1.0 | - | 19 maig, 2025 | Disseny i documentació del component. |

## Vegeu també
- [Botons](component-botons.md): per a realitzar accions.
- [Enllaços](component-enllacos.md): per facilitar la navegació entre parts del contingut o funcionalitats.
- [Il·lustracions](fonaments-illustracions.md): per il·lustrar l'acció i la informació que falta.
