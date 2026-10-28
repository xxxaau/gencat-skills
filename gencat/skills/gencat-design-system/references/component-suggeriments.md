# Suggeriments (Suggestions)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/37658c · Web component: `<suggestions-component>` (paquet conversational) · Font actualitzada el 2026-07-10 · Extret el 2026-10-28

## Què és i quan usar-lo
Element interactiu que mostra opcions de respostes de seguiment vinculades a l'últim missatge. Permet a l'usuari avançar la conversa de manera ràpida, reduint l'esforç d'escriptura i fent visibles possibles següents passos.

### Només text
Quan s'utilitza:
- Quan el sistema pot proposar següents passos clars i útils.
- Quan es vol reduir la càrrega d'escriptura.
- Quan hi ha poques opcions rellevants i l'usuari es pot beneficiar de guia.
- En fluxos on cal desencallar la conversa o orientar-la.
- Després d'una resposta del sistema, quan té sentit oferir: ampliació d'informació; accions freqüents; consultes relacionades; reformulacions.

### Metadades i text adicional
Quan s'utilitza:
- Quan cada opció té un atribut contextual rellevant (una dada breu: ubicació, data, categoria, estat…) que ajuda a identificar-la o a prendre la decisió.
- Quan cal mostrar una descripció addicional estructurada per donar més detall sense allargar el text principal.
- Quan les opcions són similars en nom però es diferencien per les seves metadades.

## Quan NO usar-lo / alternatives

### Només text
- Per mostrar llistes molt llargues d'opcions.
- Quan les opcions no siguin prou específiques o aportin poc valor.
- Com a substitut de la navegació principal.
- Quan l'usuari necessita fer una entrada complexa o molt personalitzada.
- Per forçar un camí massa tancat si el xat ha de continuar sent flexible.

### Metadades i text adicional
- Quan la metadada no aporta valor diferencial real per a la tria.
- Quan la informació addicional és massa extensa per caber de forma compacta.
- Quan només una de les opcions té metadades disponibles i la resta no, creant inconsistència visual.

## Anatomia
Figma: Anatomia (Suggeriments / Components / Botó de xat / DOC_Suggeriments / Anatomia).

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| States | Default / Hover / Focus | Default |
| Show metadata | True / False | False |
| ↳ Metadatatext | Text | Text |
| Show secondary content | True / False | False |
| ↳ Label | Text | Etiqueta |
| ↳ Information | Text | Informació |

Variant Figma: Suggestions [States = Default].

## Comportament i interacció

### Interacció
Quan l'usuari selecciona una de les opcions suggerides, aquesta s'envia automàticament com a missatge d'usuari i la resta de suggeriments desapareixen. Si l'usuari s'equivoca en la selecció, no és possible desfer l'acció des del mateix conjunt de suggeriments: caldrà esperar que el sistema torni a oferir noves opcions, tornar-les a demanar o reiniciar la conversa tancant el xat. (Figma: Comportament, Suggeriments / Components / Botó de xat / DOC_Suggeriments / Comportament.)

## Bones pràctiques

### Contingut i redacció
- **FER:** Mantenir textos breus i autoexplicatius.
- **NO FER:** No fer suggeriments massa genèrics tipus "Més informació" si no queda clar sobre què.
- **NO FER:** No mostrar textos massa llargs que trenquin la llegibilitat.

### Rellevància i context
- **FER:** Fer que estiguin contextualment connectats amb l'última resposta.
- **FER:** Ordenar-los per rellevància.
- **NO FER:** No repetir suggeriments ja utilitzats sense sentit.

### Estructura i agrupació
- **FER:** Mostrar entre 2 i 5 suggeriments rellevants.
- **NO FER:** No barrejar dins el mateix grup opcions de naturalesa molt diferent.

### Llegibilitat i format
- **FER:** Es recomana mantenir un màxim de 20 caràcters per garantir una bona llegibilitat i un escaneig ràpid.

### Interacció
- **FER:** Permetre que l'usuari pugui ignorar-los i continuar escrivint lliurement.
- **NO FER:** No fer-los passar per filtres o tags si la seva funció real és una acció conversacional.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG) que cita el component:
- **1.4.1 Ús del color (A):** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a diferenciar els diferents estats. (La font acaba la frase així.) (https://www.w3.org/Translations/WCAG22-ca/#use-of-color · https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **1.4.3 Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. (https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum · https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **1.4.4 Canvia la mida del text (AA):** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. (https://www.w3.org/Translations/WCAG22-ca/#resize-text · https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **1.4.12 Espaiat del text (AA):** quan es desenvolupa contingut utilitzant llenguatges de marcatge que permeten aplicar les propietats d'estil de text, no es perd cap contingut ni funcionalitat si s'ajusten les propietats següents: alçada de línia (interlineat) de com a mínim 1,5 vegades la mida de la lletra; espaiat entre els paràgrafs de com a mínim dues vegades la mida de la lletra; espaiat entre lletres (*tracking*) de com a mínim 0,12 vegades la mida de la lletra; espaiat entre paraules de com a mínim 0,16 vegades la mida de la lletra. (https://www.w3.org/Translations/WCAG22-ca/#text-spacing · https://www.w3.org/WAI/WCAG22/Understanding/text-spacing)
- **2.1.1 Teclat (A):** tota la funcionalitat del contingut (navegar pels diferents suggeriments) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. (https://www.w3.org/Translations/WCAG22-ca/#keyboard · https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **2.4.7 Focus visible (AA):** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. (https://www.w3.org/Translations/WCAG22-ca/#focus-visible · https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

## Implementació (component web)

### `<suggestions-component>`
Paquet: conversational.

**Propietats**

Taula de la pàgina del lloc (amb obligatorietat):

| Propietat | Atribut HTML | Descripció | Obligatorietat | Tipus |
|---|---|---|---|---|
| `suggestions` | `suggestions` | Suggeriments de respostes per a missatge del sistema | Obligatori | Array \| String(JSON) |

Segons el PDF (v12.0.0):

| Propietat | Atribut HTML | Descripció (PDF) | Tipus | Per defecte |
|---|---|---|---|---|
| `suggestions` | `suggestions` | Suggeriments disponibles per a l'usuari. Accepta array d'objectes o string JSON. | `(string \| SuggestionItem)[]` | (no indicat) |

**Propietats de l'array/objecte `suggestions` (lloc)**

| Propietat | Atribut | Descripció | Obligatorietat | Tipus |
|---|---|---|---|---|
| `id` | `id` | Identificador del suggeriment. Si no es proporciona, el component el genera de manera autònoma | Opcional | String |
| `suggestion` | `suggestion` | Text del suggeriment | Obligatori | String |
| `metadataIcon` | `metadata-icon` | Icona de bootstrap de la metadata | Opcional | String |
| `metadataIconLabel` | `metadata-icon-label` | Text alternatiu de la icona de bootstrap de la metadata | Opcional | String |
| `metadataText` | `metadata-text` | Text de la metadata | Opcional | String |
| `secondaryLabel` | `secondary-label` | Etiqueta del text secundari | Opcional | String |
| `secondaryText` | `secondary-text` | Contingut del text secundari | Opcional | String |

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre | Origen | Tipus (PDF) |
|---|---|---|---|---|
| `suggestionSelected` | Llançat en fer clic sobre un suggeriment (PDF: s'emet quan l'usuari selecciona un element) | `id` `suggestion` `index` `metadataIcon` `metadataIconLabel` `metadataText` `secondaryLabel` `secondaryText` | `suggestions-component` | `CustomEvent<SuggestionSelectedDetail>` |

**Exemples d'ús (lloc)**

HTML amb text separat per comes:

```html
<suggestions-component 
  suggestions="Oficina d&apos;atenció ciutadana més propera,Consultar l&apos;estat del meu tràmit,Suggeriment simple sense metadades">
</suggestions-component>
```

HTML amb JSON de strings:

```html
<suggestions-component 
  suggestions='["Oficina d&apos;atenció ciutadana més propera","Consultar l&apos;estat del meu tràmit","Suggeriment simple sense metadades"]'>
</suggestions-component>
```

HTML amb JSON d'objectes:

```html
<suggestions-component 
  suggestions='[{"suggestion":"Oficina d&apos;atenció ciutadana més propera","metadataIcon":"bi-geo-alt","metadataIconLabel":"Ubicació","metadataText":"Barcelona","secondaryLabel":"Etiqueta","secondaryText":"Informació addicional sobre la suggerència seleccionada."},{"suggestion":"Consultar l&apos;estat del meu tràmit","metadataIcon":"bi-clock","metadataIconLabel":"Data d&apos;actualització","metadataText":"Actualitzat avui"},"Suggeriment simple sense metadades"]'>
</suggestions-component>
```

JSX/TSX (Stencil/React-like) amb array de strings:

```jsx
<suggestions-component
  suggestions={["Oficina d'atenció ciutadana més propera", "Consultar l'estat del meu tràmit", "Suggeriment simple sense metadades"]}
/>
```

JSX/TSX amb array d'objectes:

```jsx
<suggestions-component
  suggestions={[
    {
      suggestion: "Oficina d'atenció ciutadana més propera",
      metadataIcon: "bi-geo-alt",
      metadataIconLabel: "Ubicació",
      metadataText: "Barcelona",
      secondaryLabel: "Etiqueta",
      secondaryText: "Informació addicional sobre la suggerència seleccionada."
    },
    {
      suggestion: "Consultar l'estat del meu tràmit",
      metadataIcon: "bi-clock",
      metadataIconLabel: "Data d'actualització",
      metadataText: "Actualitzat avui"
    },
    "Suggeriment simple sense metadades"
  ]}
/>
```

**Exemple d'instància (PDF)**

```html
<suggestions-component
suggestions=[]
></suggestions-component>
```

**Utilitzat per:** `chat-message-component` ([Missatge de xat](component-missatge-de-xat.md)).

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 3.0.0 | 12.0.0 | 10 juliol, 2026 | Desenvolupament: s'afegeix metadata i text secundari |
| 3.0.0 | 11.0.0 | 19 juny, 2026 | Desenvolupament: s'afegeix metadada i text secundari |
| 3.0.0 | 10.0.0 | 8 maig, 2026 | Desenvolupament del component |
| 3.0.0 | - | 17 abril, 2026 | Disseny i documentació del component |

## Vegeu també
- [Missatge de xat](component-missatge-de-xat.md)
