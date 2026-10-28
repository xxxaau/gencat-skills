# Botó Tornar amunt (Back to top button)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/9011e0 · Web component: `<back-to-top-button-component>` (paquet core) · Font actualitzada el 2026-10-02 · Extret el 2026-10-28

## Què és i quan usar-lo
El botó Tornar amunt permet als usuaris desplaçar-se ràpidament a la part superior d'una pàgina de contingut llarg. Apareix en determinades condicions i s'oculta quan no és necessari per garantir una experiència d'usuari fluida i accessible.

Quan s'utilitza:
- Quan la pàgina té un contingut llarg i l'usuari ha de desplaçar-se significativament per trobar la capçalera.
- Si la navegació principal no està sempre visible i l'usuari necessita un accés ràpid per reprendre la navegació.
- Quan es vol millorar l'accessibilitat i usabilitat en llocs amb estructures complexes.

## Quan NO usar-lo / alternatives
- En pàgines amb un contingut breu, on desplaçar-se cap amunt és fàcil i intuïtiu.
- Si ja es proporciona un menú fix o persistent que facilita la navegació sense necessitat d'un botó específic.
- Quan interfereix amb altres elements flotants, com botons d'acció ràpida.
- En contextos en què el comportament de desplaçament cap amunt ja està resolt per gestos tàctils o patrons naturals de navegació.

## Anatomia
1. **Contenidor**
2. **Icona**
3. **Elevació**

## Variants, tipus i estats
Aquest component està vinculat al component [Botons](component-botons.md). Tanmateix, no està pensat per modificar-ne cap propietat. Utilitza'l sempre en el tipus **primary** (primari), la mida **large** (gran) i el fons **default** (per defecte).

## Mides i espaiats
Es posiciona a la cantonada inferior dreta amb un marge que varia segons el punt de tall:
- **Extra Large i Large:** 40px del marge dret, 40px del marge inferior.
- **Medium:** 16px del marge dret, 40px del marge inferior.
- **Small:** 12px del marge dret, 40px del marge inferior.

## Comportament i interacció
- Quan l'usuari es desplaça cap avall, el botó roman ocult.
- Quan l'usuari comença a **desplaçar-se cap amunt**, el botó apareix amb una transició suau.
- Quan es fa clic a sobre el botó la pàgina es desplaça amb una animació fluida cap al principi de la pàgina.
- S'oculta automàticament quan l'usuari arriba a la part superior de la pàgina.

## Bones pràctiques
Claredat:
- **NO FER:** Mantenir sempre la mateixa icona; no la substitueixis per una altra.
- **NO FER:** No utilitzis un botó de text.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG):
- **Ús del color (A)** — [1.4.1](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color): el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a diferenciar els diferents estats s'inclouen subratllats, es juga amb la presència de farciment i el gruix de la vora.
- **Contrast mínim (AA)** — [1.4.3](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum): els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma.
- **Contrast d'elements no textuals (AA)** — [1.4.11](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast): els elements gràfics com botó d'icona presenten un contrast mínim de 3:1.
- **Teclat (A)** — [2.1.1](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard): tota la funcionalitat del contingut es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals.
- **Focus visible (AA)** — [2.4.7](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible): la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle.
- **Ajuda consistent (AA)** — [3.2.6](https://www.w3.org/Translations/WCAG22-ca/#consistent-help) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/consistent-help): el botó de tornar amunt ha d'aparèixer sempre en la mateixa posició relativa en totes les pàgines on es mostra.

## Implementació (component web)

### `<back-to-top-button-component>`
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat |
|---|---|---|---|---|---|
| `textTooltip` | `text-tooltip` | Text que es mostra al tooltip associat (text tooltip del botó) | string | undefined | Obligatori |

**Esdeveniments** (origen: `button-component`) [discrepància: el lloc llista aquests tres esdeveniments, però el PDF v12.0.0 indica "Sin eventos declarados" per a aquest component]

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `handlerClick` | Es llança cada cop que es fa clic al botó i com a paràmetre conté les dades de l'esdeveniment. | id | `button-component` |
| `focusButton` | Es llança cada cop que es fa focus al botó. | - | `button-component` |
| `blurButton` | Es llança cada cop que es treu el focus del botó. | - | `button-component` |

**Depèn de:** `button-component` ([Botons](component-botons.md))

**Utilitzat per:** `table-of-contents-component` ([Taula de continguts](component-taula-de-continguts.md))

**Exemple d'ús**

```html
<!-- /index.html -->
<back-to-top-button-component
  text-tooltip='Tornar amunt'>
  </back-to-top-button-component>
```

Exemple d'instància del PDF:

```html
<back-to-top-button-component
text-tooltip="texto-ejemplo"
></back-to-top-button-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.3.0 | 9.2.0 | 31 juliol, 2026 | **Disseny**: S'aplica la variable de color de nou. |
| 8.6.0 | 9.2.0 | 27 febrer, 2026 | **Desenvolupament**: Es fan millores d'accessibilitat |
| 8.6.0 | 8.5.0 | 9 febrer, 2026 | **Disseny**: Es modifica el tipus primari per secundari. |
| 4.0.0 | 8.5.0 | 5 desembre, 2025 | **Desenvolupament**: Resolució de problemes menors |
| 4.0.0 | 6.1.0 | 12 setembre, 2025 | **Desenvolupament**: Resolució de problemes |
| 4.0.0 | 4.0.1 | 19 maig, 2025 | **Desenvolupament** del component |
| 3.0.0 | No aplica | 31 març 2025 | **Disseny** i **documentació** del component |

## Vegeu també
- [Enllaços](component-enllacos.md): per facilitar la navegació entre parts del contingut o funcionalitats.
- [Botons](component-botons.md): element que permet a l'usuari dur a terme accions en una pàgina o pantalla.
- [Taula de continguts](component-taula-de-continguts.md)
