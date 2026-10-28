# Llista (List)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/374cd5 · Web component: `<list-component>` (paquet core) · Font actualitzada el 2026-10-08 · Extret el 2026-10-28

## Què és i quan usar-lo
Agrupacions de contingut relacionat. Les llistes s'utilitzen per a **millorar la lectura en escaneig**.

### Llistes no ordenades
Presenten vinyetes i es fan servir per a llistats d'elements que **no tenen un ordre específic** o que els diferents elements presenten un valor o estat equivalent.

### Llistes ordenades
S'utilitzen nombres per **indicar l'ordre dels elements** quan aquest és rellevant. Són ideals per a passos seqüencials en un procés, instruccions a seguir en un ordre específic, o per mostrar elements amb una prioritat o cronologia, com agendes o esdeveniments. Les llistes ordenades poden combinar-se amb llistes de punts i llistes numèriques.

### Llistes amb icones
S'utilitzen quan es vol **reforçar visualment el significat** de cada element de la llista mitjançant una icona.

### Llista avançada
Les llistes avançades són adequades quan:
- Cal presentar **conjunts d'elements gestionables** (usuaris, documents, registres, configuracions, etc.).
- Cada element necessita **accions directes** sense sortir del context de la llista.
- És important mantenir una **lectura clara i escaneig ràpid**, alhora que s'ofereix funcionalitat.
- Els elements poden tenir diferents nivells de detall, però comparteixen la mateixa estructura.

Aquest tipus de llista és habitual en **entorns d'administració**, taulers de gestió o pantalles on l'usuari ha de **consultar, revisar o modificar elements individuals** de manera eficient.

## Quan NO usar-lo / alternatives
- Per a agrupacions d'enllaços, utilitza la [Llista d'enllaços](component-llista-d-enllacos.md) (el tipus de llista `links` està documentat en aquest component).
- No incloguis enllaços en tots els elements d'una llista ordenada o no ordenada: en aquest cas s'ha d'utilitzar la llista d'enllaços.
- No les utilitzis per a destacar o ratificar informació.

## Anatomia
- Llista no ordenada i llista ordenada: Figma Frame 1000001241 [First level = Primer nivell, Second level = Segon nivell, Thrid level = Tercer nivell, Size = Small, Ordered = False, Level = First].
- Llista d'enllaços: Figma Llista (Llista d'enllaços/Llista/Link list/Size = Medium, Position = Vertical); Llista [Type = Default].
- Llista d'icones: Figma Llista (Llista/Llista/Icon list/Size = Medium).
- Llista avançada:
  1. Etiqueta
  2. Descripció (opcional)
  3. Grup de botons: màxim 3.

## Variants, tipus i estats

### Llista (ordenada / no ordenada)

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Ordered | No / Yes | No |
| Level | First / Second / Third | First |
| Size | Large / Medium / Small | Small |

Variants Figma: Frame 1000001241 [First level = Primer nivell, Second level = Segon nivell, Thrid level = Tercer nivell, Size = Small, Ordered = False, Level = First]. La font mostra les subseccions No ordenada, Tamanys, Ordenada, Tamanys.

### Llista d'icones

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Size | Large / Medium / Small | Small |

Variants Figma: `_Icon List items` Size = Large | Medium | Small.

### Llista avançada

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Slot | Advanced item list | --- |

Figma: Advanced item list [Show description = False, Label = Etiqueta, Description = Descripció]. Els ítems de la llista tenen les propietats següents:

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Label | Text | Etiqueta |
| Show Description | True / False | False |
| Description | Text | Descripció |
| Slot (Button group) | Icon button | Trash |

Variants mostrades: Show description = False | True.

## Comportament i interacció

### Llista no ordenada
Les llistes no ordenades utilitzen diferents estils en funció del nivell:
- **Primer** nivell: cercle amb farciment.
- **Segon** nivell: cercle sense farciment.
- **Tercer** nivell: quadrat.

A partir del **quart** nivell es repeteixen els estils anteriors de forma successiva. La distància entre el marge i la llista augmenta a mesura que augmenta el nivell. Aquest augment és de **16 px**.

### Llista ordenada
Les llistes ordenades utilitzen diferents estils en funció del nivell:
- **Primer** nivell: nombre.
- **Segon** nivell: lletra.
- **Tercer** nivell: nombre romà.

A partir del **quart** nivell es repeteixen els estils anteriors de forma successiva. La distància entre el marge i la llista augmenta a mesura que augmenta el nivell. Aquest augment és de **16 px**.

### Adaptació responsiva
El contingut de la llista s'adaptarà a la mida de pantalla.

## Bones pràctiques

### General
- **FER:** Utilitza una construcció de frases paral·leles per als elements de la llista. És a dir, segueixen un mateix estil de redacció.
- **NO FER:** No utilitzis una construcció de frases no paral·leles per als elements de la llista. És a dir, que no segueixen un mateix estil de redacció.
- **NO FER:** No repeteixis les mateixes paraules al començament de cada element de la llista.
- **FER:** Introdueix els elements de la llista amb una frase clara i descriptiva.
- **FER:** Mantingues una coherència en tot el format. Escriu amb majúscula la primera paraula de cada element de la llista i utilitza la puntuació final, excepte en casos on els elements de la llista són fragments.
- **NO FER:** No utilitzis icones per a substituir les vinyetes o els nombres.
- **FER:** Es recomana escriure els elements de la llista de forma que tinguin longituds de línia similars (principi d'equivalència).
- **NO FER:** No es recomana escriure els elements de la llista de forma que tinguin longituds de línia molt diferents.
- **FER:** Utilitza-les per agrupar un seguit d'elements relacionats.
- **NO FER:** No les utilitzis per a destacar o ratificar informació.

### Llistes ordenades i no ordenades
- **FER:** Inclou enllaços com a part d'una frase o en alguns elements.
- **NO FER:** No incloguis enllaços en tots els elements. En aquest cas s'hauria d'utilitzar la llista per enllaços.

### Llistes amb icones
- **FER:** Utilitza icones que reforcin el significat del text.
- **NO FER:** No facis servir icones decoratives que no aportin informació.
- **FER:** Inclou sempre un text clar i descriptiu al costat de la icona.
- **NO FER:** No confiïs únicament en la icona per transmetre el missatge.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG) que cita el component:
- **1.4.3 Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. (CAT: https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum · EN: https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **1.4.4 Canvia la mida del text (AA):** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. (CAT: https://www.w3.org/Translations/WCAG22-ca/#resize-text · EN: https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **1.4.11 Contrast d'elements no textuals (AA):** els elements gràfics presenten un contrast mínim de 3:1. (CAT: https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast · EN: https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)

## Implementació (component web)

> El tipus de llista *links* (enllaços) està documentat al component [Llista d'enllaços](component-llista-d-enllacos.md).

### `<list-component>`
Paquet: core.

**Propietats**

Taula de la pàgina del lloc (amb obligatorietat):

| Propietat | Atribut HTML | Descripció | Obligatorietat | Tipus |
|---|---|---|---|---|
| `extraLinkData` | `extra-link-data` | Enllaç extra que permet mostrar més contingut. | Opcional | String (JSON) |
| `listData` | `list-data` | Contingut de la llista. | Obligatori | String (JSON) |
| `orientation` | `orientation` | Orientació de la llista. | Opcional | String |
| `showTextBelow` | `show-text-below` | Mostra un text descriptiu sota l'enllaç. Només és aplicable per a la variable de tipus d'enllaç o llista avançada, a la resta de tipus (*types*) no influeix. | Opcional | Boolean |
| `size` | `size` | Mida. | Opcional | String |
| `type` | `type` | Tipus de llista. | Opcional | String |

Valors per defecte segons el PDF (v12.0.0):

| Propietat | Atribut HTML | Descripció (PDF) | Tipus | Per defecte |
|---|---|---|---|---|
| `extraLinkData` | `extra-link-data` | URL de l'enllaç. | string | undefined |
| `listData` | `list-data` | Dades del component. Accepta objecte o string JSON. | string | undefined |
| `orientation` | `orientation` | Orientació del component (horizontal o vertical). Opcions: `horizontal`, `vertical`. | string | `vertical` |
| `showTextBelow` | `show-text-below` | Mostra o amaga aquest element. | boolean | `false` |
| `size` | `size` | Mida del component. Opcions: `large`, `medium`, `small`. | string | `medium` |
| `type` | `type` | Tipus d'element. Opcions: `advanced-list`, `icon-list`, `links`, `ordered`, `unordered`. | string | `unordered` |

[discrepància: la mida per defecte de la Llista a Figma és Small; al codi (lloc i PDF) és `medium`]
[discrepància: el PDF descriu `extraLinkData` com a "URL de l'enllaç" (string); el lloc el descriu com a enllaç extra en format String (JSON) amb `text`, `mode` i `customId`]

**Props que accepten JSON**

Propietats de l'array `extraLinkData`:

| Propietat | Atribut | Descripció | Obligatori | Tipus |
|---|---|---|---|---|
| `customId` | `custom-id` | Identificador personalitzat de l'enllaç | Opcional | String |
| `mode` | `mode` | Aplicable a les llistes de tipus links. Indica si el link és intern o extern | Opcional | String |
| `text` | `text` | Text del link extra a les llistes de tipus `links` | Obligatori | String |

Propietats de l'array `listData`:

| Propietat | Atribut | Descripció | Obligatori | Tipus |
|---|---|---|---|---|
| `buttons` | `buttons` | Botons per a la llista avançada | Opcional | String (JSON) |
| `children` | `children` | Crea una sublista aniuada dins un element per als links de tipus ordered i unordered. | Opcional | String (JSON) |
| `class-name-icon` | `class-name-icon` | Nom de la classe de la icona prèvia al text en type icon-list | Opcional | String |
| `customId` | `custom-id` | Aplicable a les llistes de tipus links. Identificador personalitzat de l'enllaç | Opcional | String |
| `linkComponent` | `linkComponent` | Defineix l'enllaç associat a l'element de la llista. | Opcional | String (JSON) |
| `mode` | `mode` | Aplicable a les llistes de tipus links. Indica si el link és intern o extern | Opcional | String |
| `text` | `text` | Text de l'element de la llista | Obligatori | String |
| `textBelow` | `text-below` | Text sota l'enllaç a les llistes de tipus `links` o `advanced-list` | Opcional | String |

Propietats de l'array `buttons`:

| Propietat | Atribut | Descripció | Obligatori | Tipus |
|---|---|---|---|---|
| `customId` | `customId` | Identificador personalitzat del botó. | Opcional | String |
| `icon` | `icon` | Icona que apareixerà al botó. | Obligatori | String |
| `tooltip` | `tooltip` | Text tooltip que es mostra quan es passa el cursor (hover) sobre el botó. | Obligatori | String |

Propietats de l'array `linkComponent`:

| Propietat | Atribut | Descripció | Obligatori | Tipus |
|---|---|---|---|---|
| `mode` | `mode` | Aplicable a les llistes de tipus links. Indica si el link és intern o extern. | Opcional | String |
| `text` | `text` | Text de l'enllaç. | Obligatori | String |

**Variants (lloc)**

| Propietat | Defecte | Valors |
|---|---|---|
| `mode` | --- | `internal` `external` |
| `orientation` | `vertical` | `horizontal` `vertical` |
| `size` | `medium` | `small` `medium` `large` |
| `type` | `unordered` | `advanced-list` `icon-list` `links` `ordered` `unordered` |

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `blurButton` | Es llança cada vegada que es treu el focus en un element botó del component. | --- | `button-component` |
| `focusButton` | Es llança cada cop que es fa focus en un element botó del component. | --- | `button-component` |
| `handlerClick` | Es llança cada cop que es fa clic en un botó i com a paràmetre conté les dades de l'esdeveniment. | id | `button-component` |
| `blurLink` | Es llança cada cop que es treu el focus en un enllaç | --- | `link-component` |
| `focusLink` | Es llança cada cop que es fa focus en un enllaç | --- | `link-component` |
| `linkEmit` | Esdeveniment llançat en fer clic sobre el link. | `id` | `link-component` |

[discrepància: el lloc documenta aquests esdeveniments (heretats dels components fills); el PDF diu "Sin eventos declarados"]

**Depèn de:** `button-component` ([Botons](component-botons.md)), `group-button-component` ([Grup de botons](component-grup-de-botons.md)), `link-component` ([Enllaços](component-enllacos.md)).

**Utilitzat per:** `dynamic-table-component` ([Taules dinàmiques](component-taules-dinamiques.md)), `poi-component` ([Visor de mapa](component-visor-de-mapa.md)).

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<list-component
            type="links"
            size="small"
            orientation="vertical"
            show-text-below="true"
            extra-link-data='{
              "text": "Més contingut relacionat",
              "mode": "external"
            }'
            list-data='[
              { "text": "Google", "mode": "external", "textBelow": "Search the web with Google" },
              { "text": "Bing", "mode": "external", "textBelow": "Search the web with Bing" }
            ]'
    ></list-component>
```

**Exemple d'instància (PDF)**

```html
<list-component
extra-link-data="texto-ejemplo"
list-data="texto-ejemplo"
orientation='vertical'
show-text-below=false
size='medium'
type='unordered'
></list-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 11.0.0 | 12.0.0 | 10 juliol, 2026 | Desenvolupament: s'utilitza el token correcte per al color d'icona i text en el mode icon-list |
| 11.0.0 | 10.0.0 | 8 maig, 2026 | Disseny: s'apliquen slots pel contingut de les llistes. Desenvolupament: s'afegeix llista avançada |
| 10.0.0 | 9.2.0 | 17 abril, 2026 | Disseny: disseny del component llista avançada. Desenvolupament: s'ha afegit el tipus de llista avançada |
| 9.0.0 | 9.2.0 | 10 febrer, 2025 | Disseny: s'ha eliminat el truncat de la llista d'icones |
| 4.0.0 | 9.2.0 | 27 febrer, 2025 | Desenvolupament: es crea la propietat customId |
| 4.0.0 | 7.0.0 | 24 octubre, 2025 | Desenvolupament: resolució de problemes |
| 4.0.0 | 6.2.1 | 3 octubre, 2025 | Desenvolupament: nova propietat afegida o eliminada |
| 4.0.0 | 5.0.0 | 9 juny, 2025 | Desenvolupament: resolució de problemes |
| 4.0.0 | 4.0.1 | 19 maig, 2025 | Desenvolupament: resolució de problemes |
| 3.0.0 | 2.0.0 | 31 març, 2025 | Disseny: se separa la llista d'enllaços i es crea el component [llista d'enllaços](component-llista-d-enllacos.md) |
| 2.4.0 | 2.0.0 | 10 març, 2025 | Sense canvis |
| 2.3.0 | 1.0.0 | 31 gener, 2025 | Sense canvis |
| 2.2.0 | 0.1.1 | 20 gener, 2025 | Sense canvis |
| 2.1.0 | 0.1.1 | 04 desembre, 2024 | Sense canvis |
| 2.0.0 | 0.1.0 | 02 desembre, 2024 | Sense canvis |
| 1.1.0 | 0.1.0 | 22 novembre, 2024 | Sense canvis |
| 1.1.0 | 0.0.4 | 18 novembre, 2024 | Sense canvis |
| 1.0.0 | 0.0.3 | 1 novembre, 2024 | Disseny, desenvolupament i documentació del component |

## Vegeu també
- [Tipografia](fonaments-tipografia.md)
- [Llista d'enllaços](component-llista-d-enllacos.md): per a agrupacions d'enllaços.
- [Botons](component-botons.md)
- [Grup de botons](component-grup-de-botons.md)
- [Enllaços](component-enllacos.md)
