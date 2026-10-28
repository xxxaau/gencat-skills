# Dades estructurades (Summary list)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/40d92e · Web component: `<summary-list-component>` (paquet core) · Font actualitzada el 2026-10-22 · Extret el 2026-10-28

## Què és i quan usar-lo
Les dades estructurades són un conjunt de metadades que resumeixen la informació clau abans del contingut principal.

S'utilitzen per presentar un resum clar i estructurat de la informació clau, que permet als usuaris comprendre ràpidament els detalls essencials sense haver d'explorar tot el contingut. Mostren dades organitzades, com ara descripcions, especificacions o característiques d'un servei o un tràmit, millorant l'experiència d'usuari mitjançant una visualització concisa i accessible.

Quan s'utilitza:
- Quan hi ha la necessitat de visualitzar dades rellevants o informació clau (metadades) de forma resumida, fàcil d'escanejar i visual.

### Característiques principals
- **Disposició horitzontal:** disposició a l'amplada total de la pàgina, a manera de resum i presentació de dades rellevants, que compta normalment amb poques metadades.
- **Disposició vertical:** disposició en columnes, a manera de presentació de moltes dades que són editables i inclouen accions, com en casos d'aplicacions i gestió interna o bé en casos de tramitacions.
- **Interactivitat:** el mateix component no té estats interactius, però els elements que inclou sí que són interactius, com: mostra més, enllaços, i accions com per exemple editar, esborrar i copiar.

## Quan NO usar-lo / alternatives
- Quan ja existeix un menú lateral, o una altra forma de navegació estructurada que cobreix la mateixa funcionalitat.

## Anatomia
- Disposició vertical. Figma: Vertical summary list.
- Disposició horitzontal. Figma: Horizontal summary list [Title = Title, Show Title = True, Description = Description, Show Description = True, Show Column 4 = False, Show Column 3 = True, Show Column 5 = False, Breakpoint = Extra Large - Medium].

## Variants, tipus i estats

### Dades en disposició vertical
Context: el component es mostra amb un fons blanc i sense divisor entre files. Està pensat per presentar dades que poden ser editables i contenir accions. S'adapta per a dispositiu gran i petit; es pot dissenyar amb fila de mida mitjana o petita segons el cas d'ús. En una aplicació interna amb moltes dades a presentar, quan es requereix que la taula sigui més compacta, s'ha d'utilitzar la mida més petita.

Taula de dades:

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Show title | True / False | True |
| Show description | True / False | True |
| Show more button | True / False | True |
| Show more button (Breakpoint) | Extra Large-Medium / Small | Extra Large-Medium |

Fila de dades (Figma: _Horizontal list item [Show Description = True, Show Link = True, Show icon = True, Description = Row description, Title = Row title, Show Actions = True, ShowTag = True, Icon = calendar4, Show title = True, Size = Medium]):

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Size | Medium / Small | Medium |
| Show icon | True / False | True |
| Show title | True / False | True |
| Show description | True / False | True |
| Show Link | True / False | True |
| Show Tag | True / False | True |
| Show Actions | True / False | True |
| Interactive actions | Nº actions (1, 2, 3) | 3 |

### Dades en disposició horitzontal
Context: el component es mostra amb un fons gris per destacar-lo, ja que les dades estructurades horitzontalment actuen com a elements de presentació, ressaltant-ne el contingut. Conté divisors a cada columna menys a l'última, per cohesió visual amb el seu contorn.

Taula de dades:

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Extra Large - Large / Medium | Small |
| Show title | True / False | True |
| Show description | True / False | True |
| Show Column 3 | True / False | True |
| Show Column 4 | True / False | True |
| Show Column 5 | True / False | True |

Fila de dades (Figma: Vertical, _Vertical list item):

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Show icon | True / False | True |
| Show title | True / False | True |
| Show description | True / False | True |
| Show Link | True / False | True |
| Show Tag | True / False | True |
| Show divider | True / False | True |

### Combinació de diversos components de dades estructurades
- Les dades en format horitzontal apareixen al principi, seguides de les dades en format vertical, que poden estar en columnes de dos.
- Les dades en format vertical també poden aparèixer en una columna d'amplada total, l'una sota l'altra.

## Mides i espaiats
- El component en disposició vertical s'adapta a l'amplada del contenidor i els elements salten de línia automàticament quan no hi ha prou espai. En la versió per a mòbils, és a dir, quan el component fa menys de 455 px, el botó "Mostra més" s'ha de centrar horitzontalment (Figma: comportament_salt01 a comportament_salt06).
- Historial de disseny: amplada mínima de 150 px del "Container" del "Horizontal list item"; mínim del frame del títol de 100 px i màxim de 150 px (vegeu Historial de versions).

## Comportament i interacció
### Desplega / replega
Per defecte, el component de dades estructurades que tingui més de sis opcions inclou un botó de mostrar més dades que apareix replegat. L'usuari pot desplegar les opcions que queden replegades amb el botó de mostrar més i tornar a replegar-les.

## Bones pràctiques
### Utilització dels divisors
- **FER:** Utilitza els divisors de línia correctament, sense deixar un divisor de línia a l'última línia.
- **NO FER:** No utilitzis un divisor a l'última línia, visualment no és correcte.

### Format
- **FER:** Utilitza correctament l'espai determinat per a les dades estructurades.
- **NO FER:** No facis un ús erroni de l'espai.

### Redacció
- **FER:** Utilitza noms consistents i significatius per als usuaris.
- **NO FER:** No utilitzis noms o dades que no són significatius per als usuaris.
- **FER:** Evita noms o dades que no siguin significatius per als usuaris.

### Ordre
- **FER:** Quan tinguis dos tipus de metadades, l'ordre marca la jerarquia d'importància; per tant, primer cal col·locar el component de disposició horitzontal seguit del vertical.
- **NO FER:** No utilitzis un mal ordre del contingut de dades estructurades.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG):
- **Orientació (AA)** (1.3.4): el contingut s'adapta a les diferents orientacions de la pantalla, com vertical o horitzontal, cosa que permet visualitzar el contingut. [CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Ús del color (A)** (1.4.1): el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per diferenciar els diferents estats s'inclouen subratllats, es juga amb la presència de farciment i el gruix de la vora. [CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA)** (1.4.3): els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA)** (1.4.4): excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA)** (1.4.11): els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A)** (2.1.1): tota la funcionalitat del contingut (navegar pels diferents botons) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Ordre del focus (A)** (2.4.3): els diferents elements que componen el component s'han de presentar en un ordre lògic per facilitar la navegació per teclat o altres dispositius d'entrada. L'ordre ha de seguir el flux de la informació o les tasques que es presenten (la font esmenta "taules dinàmiques" en aquest punt). [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-order) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-order)
- **Focus visible (AA)** (2.4.7): la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

### Navegació per teclat
L'usuari pot navegar mitjançant el teclat per tots els elements interactius dins del component.

| Tecla | Acció |
|---|---|
| Tabulació | Navegar a l'element interactiu següent |
| Shift + Tabulació | Navegar a l'element interactiu anterior |
| Enter | Activar element interactiu |

## Implementació (component web)

### `<summary-list-component>`
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat (lloc) |
|---|---|---|---|---|---|
| `summaries` | `summaries` | Array amb les propietats de `summary-list-component`, en format JSON. Cada objecte conté la informació necessària per renderitzar una targeta a la llista. Accepta array d'objectes o string JSON. | string (JSON) | `[]` | Obligatori |
| `summaryDescription` | `summary-description` | Descripció de la targeta. | string | `undefined` | Opcional |
| `summaryTitle` | `summary-title` | Títol de la targeta. | string | `undefined` | Opcional |
| `summaryVertical` | `summary-vertical` | Mode de vista de summary-list (vertical/horitzontal). Per defecte vertical. | boolean | `true` | Obligatori |

**Props que accepten JSON: array `summaries`**

| Propietat | Descripció | Obligatori | Tipus |
|---|---|---|---|
| `summaryDescriptionLine` | Descripció de línia. | Opcional | String |
| `summaryIcon` | Icona que acompanya la targeta. | Opcional | String |
| `summaryIconAction` | Array amb les dades per generar accions mitjançant el component Button. | Opcional | Array |
| `summaryLink` | Array amb les dades per generar enllaços mitjançant el component Link. Només accepta les propietats `text` i `customId`. | Opcional | Array |
| `summaryTag` | Dades per generar l'etiqueta mitjançant el component Tag. | Opcional | String (Object) |
| `summaryTitleLine` | Títol de línia. | Opcional | String |

**Array `summaryIconAction`**

| Propietat | Descripció | Obligatori | Tipus |
|---|---|---|---|
| `classNameIcon` | Classe bootstrap de la icona del botó | Obligatori | String |
| `tooltip` | Text tooltip del botó icona | Obligatori | String |

**Esdeveniments** (el PDF indica "sense esdeveniments declarats"; el lloc llista els dels subcomponents)

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `blurButton` | Es llança cada cop que es treu el focus d'un botó del component. | - | `buttom-component` |
| `focusButton` | Es llança cada cop que es fa focus en un botó del component. | - | `buttom-component` |
| `handlerClick` | Esdeveniment llançat en fer clic sobre algun dels botons | `id`, `originalEvent` | `buttom-component` |
| `blurLink` | Es llança cada vegada que es treu el focus d'un enllaç del component. | - | `link-component` |
| `focusLink` | Es llança cada cop que es fa focus en un enllaç del component. | - | `link-component` |
| `linkEmit` | Esdeveniment llançat en fer clic sobre el link | `id` | `link-component` |
| `toggle` | Indica si el botó està en mode col·lapsat o no | - | `show-more-component` |

(El nom d'origen `buttom-component` és tal com surt a la font; el component és `button-component`.)

**Depèn de:** `button-component` ([Botons](component-botons.md)), `divider-component` ([Divisor](component-divisor.md)), `link-component` ([Enllaços](component-enllacos.md)), `show-more-component` ([Mostra més](component-mostra-mes.md)), `tag-component` ([Etiquetes](component-etiquetes.md)).

**Exemple d'ús** (la font repeteix 7 vegades el mateix objecte dins `summaries`, perquè el botó de mostrar més apareix amb més de sis opcions; aquí es mostra 1 objecte)

```html
<!-- /index.html -->
<summary-list-component
  summary-vertical="true"
  summary-title="Títol"
  summary-description="Aquí tens un resum dels serveis disponibles."
  summaries='[
    {
      "summaryIcon":"bi bi-calendar",
      "summaryTitleLine":"Row title",
      "summaryDescriptionLine":"Row Description",
      "summaryLink":[{"text":"Link"}],
      "summaryTag": { "type": "readonly", "text": "Etiqueta", "color": "color-white" },
      "summaryIconAction":[
        {"classNameIcon":"bi bi-pencil", "tooltip":"Edita"},
        {"classNameIcon":"bi bi-copy", "tooltip": "Còpia"},
        {"classNameIcon":"bi bi-three-dots-vertical", "tooltip": "Més accions"}
      ]}
  ]'></summary-list-component>
```

Exemple d'instància (PDF):

```html
<summary-list-component
summaries='[]'
summary-description="texto-ejemplo"
summary-title="texto-ejemplo"
summary-vertical=true
></summary-list-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 8.6.0 | 12.0.0 | 10 juliol, 2026 | Desenvolupament: s'utilitza el token correcte per al color de la icona prèvia al títol |
| 8.6.0 | 9.2.0 | 27 febrer, 2026 | Desenvolupament: es crea la propietat customIdLink per a l'enllaç |
| 8.6.0 | 9.1.0 | 9 febrer, 2026 | Disseny: s'augmenta l'amplada mínima a 150 px del "Container" del "Horizontal list item". |
| 8.3.0 | 9.1.0 | 6 febrer, 2026 | Desenvolupament: adaptacions d'accessibilitat pel que fa a mides de font extra gran i augment de pantalla |
| 8.3.0 | 6.2.1 | 14 novembre, 2025 | Disseny: s'ha ajustat la construcció del component per tal que es comporti de manera responsiva. S'ha modificat el mínim del frame del títol a 100 px i s'ha afegit un màxim de 150 px. |
| 8.2.0 | 6.2.1 | 27 octubre, 2025 | Disseny: revisió d'estils tipogràfics |
| 6.0.0 | 6.2.1 | 3 octubre, 2025 | Desenvolupament: nova propietat afegida o eliminada |
| 6.0.0 | 6.1.0 | 12 setembre, 2025 | Desenvolupament: nova propietat afegida |
| 6.0.0 | 6.0.1 | 28 juliol, 2025 | Desenvolupament: resolució de problemes |
| 6.0.0 | 5.0.0 | 8 juliol, 2025 | Disseny: no es limita el nombre de línies a mostrar en títols i descripcions. S'ajusta perquè l'enllaç permeti un llistat d'enllaços. |
| 4.0.0 | 5.0.0 | 9 juny, 2025 | Desenvolupament del component |
| 2.4.0 | - | 10 març, 2025 | Disseny i documentació del component. |

## Vegeu també
- [Acordió](component-acordio.md): per mostrar o amagar informació individualment d'un llistat d'ítems.
- [Etiquetes](component-etiquetes.md): per mostrar l'estat d'un element, les propietats clau o les categories.
- [Enllaços](component-enllacos.md): per connectar diferents pàgines web o recursos.
- [Mostra més](component-mostra-mes.md): per expandir contingut addicional d'una secció que inicialment està ocult.
- [Botons](component-botons.md): per a realitzar accions.
- [Divisor](component-divisor.md)
