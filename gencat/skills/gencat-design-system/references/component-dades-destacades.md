# Dades destacades (Key data)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/045064 · Web component: `<key-data-component>` (paquet core) · Font actualitzada el 2026-09-29 · Extret el 2026-10-28

## Què és i quan usar-lo
El component de dades destacades ressalta informació clau de manera visual i concisa, tant quantitativa com qualitativa. Serveix per reforçar missatges i facilitar una lectura ràpida.

Posa en relleu informació clau de manera visual i sintètica. Pot incloure valors quantitatius (per exemple, % de reciclatge, nombre de tràmits digitals, etc.) o conceptes qualitatius com valors institucionals (per exemple, transparència, compromís, equitat, etc.).

Quan s'utilitza:
- Per destacar mètriques o indicadors importants dins una pàgina.
- Per mostrar valors o conceptes clau vinculats a l'organització o a una temàtica.

## Quan NO usar-lo / alternatives
- Quan la informació necessita molt de context per ser entesa.
- Per mostrar grans blocs de text o narracions detallades.
- Si hi ha massa xifres que poden aclaparar visualment (establir màxim).
- Per presentar un resum clar i estructurat de la informació clau: vegeu [Dades estructurades](component-dades-estructurades.md).

## Anatomia
Components Figma: `Anatomia`, `Anatomia_ilu`, `Anatomia_text`. [a verificar: la font només en dona els noms; la interpretació com a variants amb il·lustració / de tipus text i la composició de l'ítem (element visual, número, títol, descripció) es dedueix de les propietats]

## Variants, tipus i estats

### Propietats de dades destacades

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Extra Large Column Fixed / Extra Large Column Variable / Large / Medium / Small | - |

Variants Figma (`Key data`): Breakpoint = Extra Large Column Fixed (i la resta).

### Propietats de la dada

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Extra Large Column Fixed / Extra Large Column Variable / Large / Medium / Small | - |
| Type | Data / Text / Empty | Data |
| Number | - | - |
| Show Icon | True / False | True |
| Change icon | - | - |
| Show Label | True / False | True |
| Títol | - | - |

Variants Figma (`_Key data items`): Show Description = True; Show Icon = True; Show Label = True; Number = 00; Description = Descripció; Títol = Títol; Breakpoint = Extra Large Column Fixed; Type = Data.

### Propietats de l'element visual de dada

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Visual | Icon / Illustration | - |
| Change icon | - | - |

Variants Figma (`_Visual item`): Change Icon = bus-front; Change Illustration = Cerca oficina; Visual = Icon.

## Comportament i interacció
El component està dissenyat per mostrar blocs d'informació clau de manera visualment equilibrada. Per mantenir una bona jerarquia i llegibilitat, ha de contenir com a mínim **dos ítems** i pot arribar fins a un màxim de **sis**. La disposició dels ítems s'organitza en un sistema de **màxim dues files**.

### Com es comporten els ítems dins del component
Cada ítem pot tenir un tipus específic, definit mitjançant la propietat *type (tipus)*. Hi ha tres opcions:
- *Data (dada)*
- *Text*
- *Empty (buit)*: aquest tipus no mostra cap contingut visible, però ocupa un espai dins del conjunt. La seva funció és purament estructural: permet **mantenir l'alineació** quan el nombre d'ítems no omple completament una fila.

L'ús del tipus *empty* garanteix una alineació coherent i equilibrada del component. L'absència d'elements *empty* provoca una disposició desequilibrada i poc consistent.

## Bones pràctiques

**Claredat i simplicitat**
- **FER:** Mostra només la informació essencial per garantir una lectura àgil i clara.
- **NO FER:** Evita mostrar massa dades en un mateix espai, ja que això pot dificultar-ne la comprensió i saturar visualment l'usuari.

**Context i comprensió**
- **FER:** Si es mostra un concepte (ex: equitat), assegura't que té context o relació clara amb el contingut del voltant.
- **NO FER:** Evita posar una xifra o concepte sola sense indicar clarament a què fa referència.

**Organització visual**
- **FER:** És important agrupar les dades relacionades en blocs visuals coherents, com files o columnes, per facilitar-ne la lectura.
- **NO FER:** No es poden combinar tipus diferents d'elements (dades, text, icones o il·lustracions) dins d'un mateix grup; cal mantenir una coherència visual i de contingut.

**Funcionalitat visual**
- **FER:** Si s'hi afegeix una icona, ha de tenir significat funcional o semàntic, no només decoratiu.
- **NO FER:** Cal evitar elements visuals purament decoratius que no aportin cap valor informatiu.

## Accessibilitat

### Pautes WCAG
- **Orientació (AA)**: el contingut de l'àrea de text s'adapta a les diferents orientacions de la pantalla, com vertical o horitzontal, cosa que permet visualitzar el contingut. [1.3.4 Orientació - CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Contrast mínim (AA)**: els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. [1.4.3 Contrast mínim - CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA)**: excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [1.4.4 Canvia la mida del text - CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA)**: els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [1.4.11 Contrast d'elements no textuals - CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)

## Implementació (component web)

### `<key-data-component>`

Paquet: core. Sense esdeveniments declarats.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte |
|---|---|---|---|---|
| `keys` | `keys` | Dades dels ítems (array d'objectes en JSON). **Obligatori**. El PDF la descriu com a "noms dels camps clau per a les columnes de la taula" | string (JSON) | `undefined` |

**Variants**

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `type` | `data` `text` | `data` |

**Props que accepten JSON**

`keys` — propietats de cada element de l'array:

| Propietat | Atribut | Descripció | Obligatori | Tipus |
|---|---|---|---|---|
| `dada` | `dada` | Dada del component. Només per a dades destacades de tipus dada | Opcional | string |
| `description` | `description` | Descripció del component. Només per a dades destacades de tipus text | Opcional | string |
| `icon` | `icon` | Imatge superior | Opcional | string |
| `title` | `title` | Títol del component | Opcional | string |
| `type` | `type` | Tipus de dada: `data` o `text` | Obligatori | string |

**Exemple d'ús**

```html
<!-- /index.html -->
<key-data-component 
      keys='[
        {"icon":"bi-cash","dada":"34","title":"Ventas","description":"Total de ventas este mes","type":"data"},
        {"icon":"bi-people","dada":"128","title":"Usuarios","description":"Usuarios registrados","type":"data"},
        {"icon":"bi-chat-left-text","dada":"56","title":"Comentarios","description":"Total de comentarios","type":"data"},
        {"icon":"bi-truck","dada":"22","title":"Envíos","description":"Pedidos enviados esta semana","type":"data"},
        {"icon":"bi-star-fill","dada":"4.8","title":"Valoración","description":"Promedio de valoración de productos","type":"data"}
        ]'
  ></key-data-component>
```

**Exemple d'instància (PDF)**

```html
<key-data-component
keys="texto-ejemplo"
></key-data-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 8.6.0 | 9.1.0 | 9 febrer, 2026 | Disseny: s'eliminen truncats |
| 4.1.0 | 9.1.0 | 6 febrer, 2026 | Desenvolupament: es fan adaptacions d'accessibilitat pel que fa a mides de font extra gran i augment de pantalla |
| 4.1.0 | 6.1.0 | 12 setembre, 2025 | Desenvolupament: resolució de problemes |
| 4.1.0 | 5.0.0 | 9 juny, 2025 | Desenvolupament del component |
| 4.1.0 | - | 19 maig, 2025 | Disseny i documentació del component |

## Vegeu també
- [Dades estructurades](component-dades-estructurades.md)
