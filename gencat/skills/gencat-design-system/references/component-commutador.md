# Commutador (Switch)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/318d13 · Web component: `<switch-component>` (paquet core) · Font actualitzada el 2026-10-19 · Extret el 2026-10-28

## Què és i quan usar-lo
El commutador és un element d'interacció que permet a l'usuari activar o desactivar una funció de manera ràpida i intuïtiva. Es representa habitualment com un botó lliscant que canvia d'estat (actiu o inactiu) amb un sol clic. La seva aparença i comportament estan dissenyats per ser fàcilment reconeixibles i accessibles en qualsevol dispositiu.

Quan s'utilitza:
- Per representar un canvi immediat i binari o habilitar/deshabilitar funcionalitats amb un estat clar d'activació o desactivació.

## Quan NO usar-lo / alternatives
- Quan es requereix confirmar el canvi amb una acció addicional (per exemple, un botó "Desa").
- Per organitzar contingut relacionat en seccions o categories dins d'una única àrea de visualització, s'utilitzen les pestanyes ([Pestanyes](component-pestanyes.md)).
- Per a seleccions múltiples dins d'un grup, s'utilitzen els botons d'opció ([Botó d'opció](component-boto-d-opcio.md)).
- Quan es vol seleccionar o desseleccionar múltiples opcions independents en un formulari, s'utilitza la casella de selecció ([Casella de selecció](component-casella-de-seleccio.md)).

## Anatomia
Figma: Anatomia (Commutador/Bones pràctiques/DOC_Switch/Anatomia). Un commutador té el control lliscant, una etiqueta (Label Text) i, opcionalment, una descripció (Description Text).

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Default / Hover / Focus / Disabled | Default |
| Selected | True / False | --- |
| Label Text | --- | Etiqueta |
| Description | True / False | False |
| Description Text | --- | Descripció |

Variants Figma: Switch [Label text = Etiqueta, Description text = Descripció, Show Description = True, Selected = True, State = Default]. La font mostra aquesta mateixa variant a les subseccions Estat i Selecció.

## Bones pràctiques

### Estat i claredat
- **FER:** Assegura't que el commutador indica clarament l'estat actual (actiu/inactiu).
- **NO FER:** Evita etiquetes poc clares que no ajudin l'usuari a entendre què activa o desactiva el commutador.

### Etiqueta i descripció
- **FER:** Afegeix una etiqueta descriptiva al costat del commutador per indicar quina funcionalitat controla.
- **NO FER:** No utilitzis el commutador per accions complexes que impliquin més d'un canvi d'estat.
- **FER:** L'etiqueta i/o la descripció del commutador han d'estar redactades en termes positius, indicant l'acció desitjada en habilitar l'opció.

### Ús adequat
- **FER:** Ha de proporcionar una resposta visual immediata quan es canvia d'estat.
- **NO FER:** No l'apliquis a opcions on el canvi no sigui immediat o necessiti passos addicionals.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG) que cita el component:
- **1.4.11 Contrast d'elements no textuals (AA):** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. Els elements decoratius, com el divisor, estan exempts. (CAT: https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast · EN: https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **2.4.6 Encapçalaments i etiquetes descriptives (AA):** inclou etiquetes descriptives o `aria-label` per indicar clarament la funció del commutador. (CAT: https://www.w3.org/Translations/WCAG22-ca/#headings-and-labels · EN: https://www.w3.org/WAI/WCAG22/Understanding/headings-and-labels)
- **4.1.2 Nom, funció, valor (A):** usa atributs com `aria-checked` per reflectir l'estat del commutador als lectors de pantalla. (CAT: https://www.w3.org/Translations/WCAG21-ca/#name-role-value · EN: https://www.w3.org/TR/WCAG21/#name-role-value)
- **1.4.3 Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. (CAT: https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum · EN: https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)

### Navegació per teclat

| Tecla | Acció |
|---|---|
| Tabulador | Navegar fins al commutador o passar al següent element interactiu. |
| Shift + Tabulador | Navegar a l'element interactiu anterior. |
| Enter | Activar o desactivar el commutador. |

## Implementació (component web)

### `<switch-component>`
Paquet: core.

**Propietats**

Taula de la pàgina del lloc (amb obligatorietat):

| Propietat | Atribut HTML | Descripció | Obligatorietat | Tipus |
|---|---|---|---|---|
| `descriptionSwitch` | `description-switch` | Descripció de l'etiqueta que acompanya el switch | Opcional | string |
| `isDisabled` | `is-disabled` | Habilitar o desactivar el switch | Opcional | boolean |
| `titleSwitch` | `title-switch` | Títol de l'etiqueta que acompanya el switch. | Obligatori | string |
| `value` | `value` | Value de l'input del commutador | Opcional | string |

Valors per defecte segons el PDF (v12.0.0):

| Propietat | Atribut HTML | Descripció (PDF) | Tipus | Per defecte |
|---|---|---|---|---|
| `descriptionSwitch` | `description-switch` | Descripció de l'element. | string | undefined |
| `isDisabled` | `is-disabled` | Activa aquesta característica quan és true. | boolean | false |
| `titleSwitch` | `title-switch` | Títol del component. | string | undefined |
| `value` | `value` | Valor actual del component. | string | false |

Variants (lloc):

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `isDisabled` | `true` `false` | `false` |
| `value` | `true` `false` (en string, no boolean) | `false` |

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre / tipus |
|---|---|---|
| `switchToggled` | Es llança en fer clic al switch (PDF: s'emet quan l'estat del component s'alterna). | `CustomEvent<{ id: string; checked: boolean; value: string; }>` |
| `valueChange` | Es llança en fer clic al switch (PDF: s'emet quan el valor del component canvia). | `CustomEvent<string>` |

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<switch-component
          title-switch="Etiqueta"
          description-switch="Descripció"
          is-disabled="false"
          value="true"
></switch-component>
```

**Exemple d'instància (PDF)**

```html
<switch-component
description-switch="texto-ejemplo"
is-disabled=false
title-switch="texto-ejemplo"
value='false'
></switch-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 10.0.0 | 12.0.0 | 10 juliol, 2026 | Desenvolupament: s'utilitza el token correcte per al color de la boleta |
| 10.0.0 | 10.0.0 | 8 maig, 2026 | Desenvolupament: ajust de tipografia |
| 10.0.0 | 9.1.0 | 17 abril, 2026 | Disseny: es modifica l'estil de text de les etiquetes; es passa de Regular a Semibold |
| 9.0.0 | 9.1.0 | 10 febrer, 2026 | Disseny: s'elimina el truncament de la descripció |
| 4.0.0 | 9.1.0 | 6 febrer, 2026 | Desenvolupament: es fa reactiva la propietat value; es fan adaptacions d'accessibilitat pel que fa a mides de font extra gran i augment de pantalla |
| 4.0.0 | 6.1.0 | 12 setembre, 2025 | Desenvolupament: nova propietat afegida |
| 4.0.0 | 4.0.1 | 19 maig, 2025 | Desenvolupament: resolució de problemes |
| 2.3.0 | 1.1.0 | 17 febrer, 2025 | Desenvolupament del component |
| 2.3.0 | - | 31 gener, 2025 | Disseny i documentació del component |

## Vegeu també
- [Casella de selecció](component-casella-de-seleccio.md): per a seleccionar una o més opcions d'una llista predefinida.
- [Botó d'opció](component-boto-d-opcio.md): per a seleccionar una opció dins d'un conjunt d'opcions mútuament excloents.
- [Pestanyes](component-pestanyes.md)
