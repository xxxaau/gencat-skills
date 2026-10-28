# Carregador d'arxius (File uploader)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/54529a · Web component: `<file-uploader-component>` (paquet core) · Font actualitzada el 2026-09-30 · Extret el 2026-10-28

## Què és i quan usar-lo
Permet als usuaris seleccionar i pujar arxius a un lloc específic.

El carregador de fitxers s'utilitza en situacions en què els usuaris necessiten **transferir fitxers des del dispositiu local a un servidor o plataforma en línia**. Indica de forma clara quins elements pujar, el progrés de càrrega i l'estat de cada arxiu.

Casos comuns d'ús:
- Formularis en línia.
- Correus electrònics.
- Resolució de problemes tècnics.
- Sol·licituds i documentació.

### Tipologies
Hi ha dos tipus de carregadors de fitxers:
1. **Botó:** permet carregar fitxers mitjançant un botó que obre un quadre de diàleg del sistema de fitxers, on es poden seleccionar un o diversos arxius per pujar. És especialment útil en **situacions en què l'espai de la pantalla és limitat**, com en formats web i mòbil.
2. **Arrossegar i deixar anar (drag and drop):** permet carregar fitxers arrossegant-los des del sistema de fitxers i deixant-los anar en una àrea designada dins de l'aplicació. És adient per a casos on es disposa de prou espai en pantalla en format web, però **mai per format mòbil.**

## Anatomia
Dues anatomies a Figma: la del tipus botó (`anatomia`) i la del tipus arrossegar i deixar anar (`anatomia_drag`). Elements configurables a Figma (etiquetes d'exemple): Label = Etiqueta; Error text = Text d'error; Specifications = Especificacions tècniques (tipus de fitxer, MB, etc); tooltip (indicador de funció) i botó popover (descripció emergent) opcionals.

## Variants, tipus i estats

### File uploader (component principal)

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Extra Large - Medium / Small | Extra Large |
| Type | Button / Drag and drop | Button |
| State | Default / Uploaded / Global error / Selector Error | Default |
| Show Tooltip | True / False | False |
| Show Popover Button | True / False | False |

Variants Figma: Show Tooltip = False | True; Show Popover Button = False | True; Label = Etiqueta; Error text = Text d'error; Specifications = Especificacions tècniques (tipus de fitxer, MB, etc); Breakpoint = Extra Large - Medium | Small; Type = Button | Drag and drop; State = Default | Uploaded | Global error | Selector Error.

### Files (fitxers individuals)

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Medium / Small | Medium |
| State | Loading / Uploaded / Error | Uploaded |

Variants Figma: Show Divider = True; File size = Pes arxiu; Error text = Text d'error; Breakpoint = Medium | Small; State = Loading | Uploaded | Error.

### Files container

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Global Error | True / False | False |
| Container | Slot | File uploader files |

Variants Figma: Global Error = False | True (error global del contenidor).

## Mides i espaiats
Les dades de mides de les versions de disseny (historial):
- El contenidor del drag and drop és adaptatiu amb una **amplada màxima de 640 px** per a punts de tall Medium o superior i **479 px** per a Small.
- L'alçada del drag and drop és *hug* amb una **alçada mínima de 200 px**.
- S'han definit mides mínimes i màximes d'amplada a les diferents variants.

## Comportament i interacció

### Botó
- En seleccionar el botó s'obre un diàleg de sistema que permet seleccionar un o diversos fitxers.
- Un cop seleccionat el fitxer es mostra el procés de càrrega dels arxius. En aquest punt l'usuari pot **cancel·lar** la pujada.
- Si hi ha algun error en la pujada, aquesta s'atura i indica el tipus d'error. En aquest punt es permet **tornar a pujar** el mateix fitxer o **eliminar-lo**.
- Un cop ha pujat correctament un fitxer, l'usuari pot eliminar-lo mitjançant el botó d'acció.

### Arrossega i deixa anar
- L'usuari pot optar entre arrossegar i deixar anar o seleccionar un arxiu, com en el cas del botó.
- Quan l'usuari arrossega un fitxer del seu sistema dins del camp, es modifica l'estat d'aquest (variant d'estat a Figma).
- Quan el deixa anar es produeixen els mateixos passos que en el cas del botó.

### Fitxers
- Si el nom del fitxer sobrepassa l'espai disponible, aquest **salta de línia.**
- El nom del fitxer és un *enllaç* que permet **previsualitzar** el document pujat en el navegador.

### Errors
- Quan l'error es dona perquè l'usuari **no ha pujat un arxiu i aquest era necessari**, s'utilitza l'error del botó o del camp d'arrossegar i deixar anar (*drag and drop*).
- Quan l'error es dona per un **excés de documents** pujats, es mostra amb la variable "*global error*".
- Quan l'error és causat per un **problema de l'arxiu**, s'utilitza l'error específic.
- L'usuari pot pujar tots els documents que vulgui, però si **sobrepassa els arxius permesos**, li apareix l'error global i el text d'error corresponent.

### Adaptació responsiva
- Pantalles **inferiors als 480 px:** s'usa la versió ***small*** i sempre amb la versió amb **botó**.
- Pantalles **iguals o superiors a 480 px:** s'usa la versió ***medium*** i es pot fer servir tant la versió amb **botó** com la d'**arrossegar i deixar anar.**

## Contingut i microcopy
Missatges d'error d'exemple: "l'arxiu excedeix la mida màxima permesa", "el format de l'arxiu no suportat", "és obligatori pujar un fitxer".

Textos d'exemple del component: etiqueta "Etiqueta"; especificacions "Especificacions tècniques (tipus de fitxer, MB, etc)"; text d'error "Text d'error"; botó "Selecciona els arixus" / "Puja els arxius"; arrossegar "Arrossega i deixa els arxius".

## Bones pràctiques

### Context
- **FER:** Indica el format i el pes màxim dels arxius que es poden pujar.
- **FER:** Inclou una descripció prèvia amb indicacions o comentaris per a pujar els arxius.

### Estat de càrrega
- **FER:** Informa que s'està produint la càrrega de l'arxiu.

### Errors
- **FER:** Proporciona missatges d'errors específics i útils com "l'arxiu excedeix la mida màxima permesa" o "el format de l'arxiu no suportat" o "és obligatori pujar un fitxer".
- **NO FER:** No proporcionis missatges d'errors poc específics o el fet de no incloure'n cap.
- **FER:** Quan hi ha un error amb el document, ofereix l'opció d'eliminar-lo abans de tornar a pujar-lo.
- **FER:** En cas d'error per problemes del sistema (com problemes de connexió), permet a l'usuari intentar la càrrega de nou sense haver de reiniciar tot el procés.
- **FER:** Si l'error es produeix per sobrepassar el nombre d'arxius permesos, utilitza l'error que engloba tots els documents.
- **NO FER:** Si l'error es produeix per sobrepassar el nombre d'arxius permesos, no utilitzis l'error del botó de pujada d'arxius.

### Mida de l'arxiu
- **FER:** En aquells casos en què l'arxiu pesa menys d'1 MB, indica el pes en kB i sense decimals.
- **NO FER:** En aquells casos en què l'arxiu pesa menys d'1 MB, no indiquis el pes en MB usant decimals.
- **FER:** En aquells casos en què l'arxiu pesa més d'1 MB, inclou els decimals arrodonint a les dècimes.
- **NO FER:** En aquells casos en què l'arxiu pesa més d'1 MB, no incloguis els decimals arrodonint a les centèsimes.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG):
- **1.3.4 Orientació (AA):** el contingut de l'àrea de text s'adapta a les diferents orientacions de la pantalla, com ara vertical o horitzontal. (https://www.w3.org/Translations/WCAG22-ca/#orientation · https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **1.4.1 Ús del color (A):** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per indicar els canvis d'estat es modifiquen els píxels de la vora del component i/o s'afegeixen elements complementaris com la segona vora pel focus o la icona i el text d'error. (https://www.w3.org/Translations/WCAG22-ca/#use-of-color · https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **1.4.3 Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són excepció d'aquesta norma. (https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum · https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **1.4.4 Canvia la mida del text (AA):** excepte subtítols i imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. (https://www.w3.org/Translations/WCAG22-ca/#resize-text · https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **1.4.11 Contrast d'elements no textuals (AA):** els elements gràfics com icones (error i indicador de funció) i vores presenten un contrast mínim de 3:1. (https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast · https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **2.1.1 Teclat (A):** tota la funcionalitat del contingut (accedir al camp de text) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. (https://www.w3.org/Translations/WCAG22-ca/#keyboard · https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **2.4.7 Focus visible (AA):** la navegació al camp és visible mitjançant un rectangle extern. (https://www.w3.org/Translations/WCAG22-ca/#focus-visible · https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- **3.3.1 Identificació d'errors (A):** si es detecta un error, s'identifica clarament mitjançant l'aparició d'un element gràfic (línia vertical) i amb la indicació visual (icona) i textual (descripció de l'error). (https://www.w3.org/Translations/WCAG22-ca/#error-identification · https://www.w3.org/WAI/WCAG22/Understanding/error-identification)

## Implementació (component web)

### `<file-uploader-component>`
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Obligatorietat (lloc) | Tipus | Per defecte (PDF) |
|---|---|---|---|---|---|
| `accept` | `accept` | Indiqueu el tipus de fitxer que voleu adjuntar. | Opcional | string | (no consta al PDF) |
| `browseButtonText` | `browse-button-text` | Text del botó per a l'acció d'arrossegar i deixar anar (*drag and drop*). (PDF: text del botó) | Opcional | string | `Browse Files` |
| `dragAndDropText` | `drag-and-drop-text` | Text per a l'acció d'arrossegar i deixar anar sota la icona de pujada d'arxius. | Opcional | string | `Arrossega i deixa els arxius` |
| `errorMessage` | `error-message` | Text del missatge d'error. | Opcional | string | `Text d'error` |
| `errorMessageFile` | `error-message-file` | Text del missatge d'error d'un fitxer específic. | Opcional | string | `Text d'error` |
| `errorMessageProgressBar` | `error-message-progress-bar` | Text que es mostra quan hi ha un error durant la pujada d'arxius o del procés de càrrega a la barra de progrés. | Opcional | string | `Text d'error` |
| `globalError` | `global-error` | 'true' o 'false' perquè es mostri o no un missatge d'error global. | Opcional | boolean | `false` |
| `hasError` | `has-error` | 'true' o 'false' perquè es mostri o no un missatge d'error d'un fitxer específic. | Opcional | boolean | `false` |
| `mode` | `mode` | Mode de carregador d'arxius. Dos valors admesos: 'button' o 'drag-and-drop'. | Opcional | string | `button` |
| `popoverConfig` | `popover-config` | Atributs del popover (PDF: accepta objecte o string JSON) | Opcional | string (object) | `{}` |
| `progress` | `progress` | Percentatge del progrés de la pujada de fitxers. Es representa com un número entre 0 i 100 i serveix per visualitzar el progrés de la pujada d'arxius a la interfície. | Opcional | number | `0` |
| `showPopoverValue` | `show-popover-value` | Mostra popover | Opcional | boolean | `false` |
| `showTooltip` | `show-tooltip` | 'true' o 'false' en funció de si voleu mostrar o no el tooltip | Opcional | boolean | `true` |
| `simulatedUploadTime` | `simulated-upload-time` | Només aplicable per a l'`uploadMode` immediat. Temps en mil·lisegons que ha de transcórrer fins que l'estat canviï de loading a upload. | Opcional | number | `10000` |
| `statusProgressBar` | `status-progress-bar` | Indica l'estat actual de la barra de progrés. Opcions (PDF): `current`, `done`, `error`, `loaded`, `loading`, `pending`. | Opcional | string | undefined |
| `tooltipText` | `tooltip-text` | Text de l'indicador de funció. | Opcional | string | `Tooltip Text` |
| `uploadButtonText` | `upload-button-text` | Text del botó per pujar fitxers. | Opcional | string | `Upload File` |
| `uploadMode` | `upload-mode` | Mode de pujada immediata o manual. El mode immediat puja o simula la pujada del fitxer a l'instant, és a dir, canvia de forma automàtica l'estat de loading a upload; en manual, el desenvolupador ha de canviar aquest estat fent ús dels mètodes indicats més avall. | Obligatori | string | `immediate` |
| `uploaderDescription` | `uploader-description` | Text descriptiu sota l'àrea d'arrossegar i deixar anar (*drag and drop*). | Opcional | string | `Especificacions tècniques (tipus de fitxer, MB, etc)` |
| `uploaderLabel` | `uploader-label` | Text de l'etiqueta del carregador d'arxius. | Opcional | string | `Etiqueta` |
| `urlUp` | `url-up` | URL on es penjaran els fitxers. | Obligatori | string | undefined |

[discrepància: el lloc diu que `urlUp` és "URL on es penjaran els fitxers" i `simulatedUploadTime` no té valor per defecte; el PDF descriu `urlUp` com a "URL del enlace volver arriba" i dóna `simulatedUploadTime` = 10000]
[discrepància: `accept` i el mètode `setFiles()` consten al lloc però no al PDF v12.0.0]

**Variants**

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `mode` | `button` `drag-and-drop` | `button` |
| `uploadMode` | `immediate` `manual` | `immediate` |

**Props que accepten JSON:** `popoverConfig` (`popover-config`) accepta objecte o string JSON. Estructura vista a l'exemple:

```json
{
  "text-open": "Ajuda",
  "padding": 20,
  "size-text-open": "small",
  "popover-title": "Títol de prova",
  "description": "Descripció del popover",
  "version": "contextual",
  "contextual-image-url": "/assets/photos/img_1.png",
  "img-description": "Descripció de la imatge",
  "link-text-popover": "Més informació",
  "link-href-popover": "https://example.com"
}
```

**Mètodes públics**

| Mètode | Descripció | Paràmetre |
|---|---|---|
| `getFiles()` | Retorna la llista actual de fitxers gestionats pel component. | - |
| `markAsUploaded(id)` | Marca un fitxer específic com a pujat correctament. | id (string) |
| `markAsError(id)` | Marca un fitxer específic amb estat error. | id (string) |
| `removeFile(id)` | Elimina un fitxer de la llista interna del component. | id (string) |
| `setFiles()` | Permet precarregar una llista de fitxers al component sense que l'usuari els hagi pujat manualment. | Rep un array amb: `id`, `name`, `size`, `status`, `link` |

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre | Origen | Tipus (PDF) |
|---|---|---|---|---|
| `blurButton` | Esdeveniment llançat en treure el focus sobre algun dels botons. | - | `button-component` | |
| `focusButton` | Esdeveniment llançat en fer focus sobre algun dels botons. | - | `button-component` | |
| `handlerClick` | Esdeveniment llançat en fer clic en algun botó | `id` | `button-component` | |
| `valueChange` | Es llança en pujar un o diversos fitxers | Dades del fitxer | `file-uploader-component` | `CustomEvent<FileItem[]>` |
| `fileRemoved` | Esdeveniment emès en prémer el botó "Elimina" de l'arxiu que correspongui | Objecte del fitxer amb informació com id, name, size, status i link | `file-uploader-component` | `CustomEvent<FileItem>` |
| `fileCancelled` | Esdeveniment llançat en prémer el botó "Cancel·la" | Objecte del fitxer amb informació com id, name, size, status i link | `file-uploader-component` | `CustomEvent<FileItem>` |
| `fileRetry` | Esdeveniment llançat en prémer el botó "Torna a pujar" | Objecte del fitxer amb informació com id, name, size, status i link | `file-uploader-component` | `CustomEvent<FileItem>` |
| `blurLink` | Es llança cada cop que es treu el focus de l'enllaç. | - | `link-component` | |
| `focusLink` | Esdeveniment llançat en fer focus sobre l'enllaç. | - | `link-component` | |
| `linkEmit` | Esdeveniment llançat en fer clic en algun enllaç | `id` | `link-component` | |

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<file-uploader-component
  accept=".pdf"
  browse-button-text="Selecciona els arixus"
  drag-and-drop-text="Arrossega i deixa els arxius"
  error-message="Text d’error"
  error-message-file="Text d’error"
  error-message-progress-bar="Text d'error del progress bar"
  global-error="false"
  has-error="false"
  mode="button"
  popover-config='{
          "text-open": "Ajuda",
          "padding": 20,
          "size-text-open": "small",
          "popover-title": "Títol de prova",
          "description": "Descripció del popover",
          "version": "contextual",
          "contextual-image-url": "/assets/photos/img_1.png",
          "img-description": "Descripció de la imatge",
          "link-text-popover": "Més informació",
          "link-href-popover": "https://example.com"
  }'
  progress="3"
  show-popover-value="true"
  show-tooltip="true"
  simulated-upload-time="1000"
  status-progress-bar="current"
  tooltip-text="File uploader tooltip"
  upload-button-text="Puja els arxius"
  upload-mode="immediate"
  uploader-description="Especificacions tècniques (tipus de fitxer, MB, etc)"
  uploader-label="Etiqueta"
  url-up="www.example.es"
></file-uploader-component>
```

**Exemple d'instància (PDF)**

```html
<file-uploader-component
browse-button-text='Browse Files'
drag-and-drop-text='Arrossega i deixa els arxius'
error-message='Text d’error'
error-message-file='Text d’error'
error-message-progress-bar='Text d’error'
global-error=false
has-error=false
mode='button'
popover-config='{}'
progress=0
show-popover-value=false
show-tooltip=true
simulated-upload-time=10000
status-progress-bar="current"
tooltip-text='Tooltip Text'
upload-button-text='Upload File'
upload-mode='immediate'
uploader-description='Especificacions tècniques (tipus de fitxer, MB, etc)'
uploader-label='Etiqueta'
url-up="texto-ejemplo"
></file-uploader-component>
```

**Depèn de:** `advanced-image-component` ([Imatge avançada](component-imatge-avancada.md)), `button-component` ([Botons](component-botons.md)), `link-component` ([Enllaços](component-enllacos.md)), `popover-component` ([Descripció emergent](component-descripcio-emergent.md)), `progress-bar-component` ([Barra de progrés](component-barra-de-progres.md)), `tooltip-component`. [discrepància: el lloc enllaça `tooltip-component` a la pàgina Menú desplegable (745c88); el seu component propi és l'[Indicador de funció](component-indicador-de-funcio.md)]

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.0.0 | 12.1.0 | 7 setembre, 2026 | Desenvolupament: s'afegeix el mètode `setFiles` per injectar fitxers des de fora del component; s'afegeix la propietat `accept` per indicar el tipus de fitxer a adjuntar. |
| 12.1.0 | 12.0.3 | 4 setembre, 2026 | Desenvolupament: s'ha corregit perquè quan es prem el botó d'eliminació sobre un fitxer en estat d'error, l'esdeveniment corresponent no s'emeti ni s'executi. |
| 12.1.0 | 10.1.0 | 19 juny, 2026 | Disseny: es modifiquen les alçades del drag and drop a hug amb alçada mínima de 200 px. |
| 12.0.0 | 10.1.0 | 29 maig, 2026 | Disseny: s'apliquen slots pel contingut de les llistes. Desenvolupament: en fer clic en una imatge pujada al component, s'obre el component imatge avançada amb la imatge seleccionada; es canvia la property tooltiptext a camelCase tooltipText |
| 9.0.0 | 9.2.0 | 11 febrer, 2026 | Disseny: s'elimina el truncat de l'enllaç a una línia. |
| 8.4.0 | 9.2.0 | 27 febrer, 2026 | Desenvolupament: es creen els esdeveniments fileRemoved, fileCancelled i fileRetry, per millorar la comunicació amb el component. |
| 8.4.0 | 9.1.0 | 6 febrer, 2026 | Desenvolupament: adaptacions d'accessibilitat pel que fa a mides de font extra gran i augment de pantalla |
| 8.4.0 | 9.0.0 | 12 gener, 2026 | Desenvolupament: correccions d'estils, com ara amplades màximes i mínimes |
| 8.4.0 | 8.5.0 | 5 desembre, 2025 | Disseny: es modifiquen i s'afegeixen mides mínimes i màximes d'amplada a les diferents variants; el contenidor del drag and drop passa a ser adaptatiu amb una amplada màxima de 640 px per punts de tall Medium o superior i 479 per Small. Desenvolupament: es canvia el nom de la property showPopover a showPopoverValue |
| 8.2.0 | 7.0.0 | 27 octubre, 2025 | Disseny: revisió d'estils tipogràfics |
| 4.0.0 | 7.0.0 | 24 octubre, 2025 | Desenvolupament: resolució de problemes |
| 4.0.0 | 6.0.1 | 28 juliol, 2025 | Desenvolupament: resolució de problemes |
| 4.0.0 | 6.0.0 | 3 juliol, 2025 | Desenvolupament: resolució de problemes |
| 4.0.0 | 4.0.1 | 19 maig, 2025 | Desenvolupament: resolució de problemes |
| 2.3.0 | 3.0.0 | 28 abril, 2025 | Desenvolupament: resolució de problemes |
| 2.3.0 | 1.0.0 | 31 gener, 2025 | Sense canvis |
| 2.2.0 | 0.1.1 | 20 gener, 2025 | Sense canvis |
| 2.1.0 | 0.1.1 | 04 desembre, 2024 | Disseny: s'afegeix el botó d'ajuda per mostrar la descripció emergent. Es modifiquen espaiats i s'afegeix el canvi a la mida small des del component principal. |
| 2.0.0 | 0.1.0 | 02 desembre, 2024 | Sense canvis |
| 1.1.0 | 0.1.1 | 22 novembre, 2024 | Sense canvis |
| 1.1.0 | 0.1.0 | 22 novembre, 2024 | Sense canvis |
| 1.1.0 | 0.0.4 | 18 novembre, 2024 | Sense canvis |
| 1.0.0 | 0.0.3 | 1 novembre, 2024 | Disseny, desenvolupament i documentació del component |

## Vegeu també
- [Barra de progrés](component-barra-de-progres.md): per indicar l'avanç d'una tasca amb el pas del temps.
- [Botons](component-botons.md): per realitzar accions.
- [Enllaços](component-enllacos.md): per connectar elements de navegació.
