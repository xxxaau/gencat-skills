# Panell destacat (Hero banner)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/30eef7 · Web component: `<hero-banner-component>` (paquet core) · Font actualitzada el 2026-10-22 · Extret el 2026-10-28

## Què és i quan usar-lo
Component introductori que dona visibilitat al missatge principal d'una pàgina o portal. Se situa habitualment a la part superior i permet destacar informació rellevant, contextualitzar el contingut i orientar l'usuari cap a una acció o contingut principal.

Quan s'utilitza: a la pàgina d'inici d'un portal web. El propòsit és:
- Presentar el missatge principal o la proposta de valor del portal.
- Introduir i contextualitzar el contingut de la pàgina.
- Donar visibilitat a una acció o contingut prioritari.
- Facilitar l'accés a la cerca o a un punt d'entrada principal, quan sigui necessari.

## Quan NO usar-lo / alternatives
- Per a pàgines de contingut d'un portal web.

## Anatomia
Figma: Hero banner [Text Domain = gencat.cat, Text Title = Títol, Breakpoint = Extra Large Column Fixed]. Elements: domini web (`webDomain`) sobre el títol, títol (`titleBanner`), camp de cerca opcional i contingut multimèdia (imatge o vídeo) de fons.

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Extra Large Column Fixed / Extra Large Column Variable / Large / Medium / Small | Extra large Column Fixed |

Variants Figma: Text Domain = gencat.cat; Text Title = Títol; Breakpoint = Extra Large Column Fixed | Extra Large Column Variable | Large | Medium | Small.

Tipus de contingut multimèdia (codi): `image`, `external-video`, `internal-video` (per defecte `image`).

## Mides i espaiats
- Versió Large: alçada mínima de **604 px**; layout de la imatge a la part superior (v9.1.0 de Figma).
- Títol: límit de text de **5 línies** (des de la v8.1.0 de Figma, que n'elimina el subtítol i el descriptor).
- Text de la proposta de valor: màxim **85 caràcters**.

## Comportament i interacció

### Adaptació responsiva
- El component **s'adapta a cadascun dels punts de tall** perquè tant la imatge com la targeta de contingut s'adaptin als canvis de retícula.
- A partir del **punt de tall *Medium*** s'utilitza el **camp de cerca** amb la mida *Medium*.
- Versions a Figma: ExtraLarge-fixed, ExtraLarge-variable, Large, Medium, Small.

## Contingut i microcopy
Textos d'exemple: domini web "gencat.cat", títol "Títol", etiqueta del camp de cerca "Cerca", tooltip del botó de cerca "Cercar" (PDF per defecte: "Cerca").

## Bones pràctiques

### Ubicació
- **FER:** El panell destacat va sempre ubicat a la part superior de la pantalla, just per sota del menú horitzontal o de la capçalera (si no hi hagués menú).
- **NO FER:** No ubiquis el panell destacat en una posició inferior o desordenada a la pantalla, ja que pot dificultar la visualització immediata.

### Claredat i concisió
- **FER:** Evita sobrecarregar el panell destacat amb informació o elements visuals excessius; el focus ha d'estar en un únic missatge central. El text de la proposta de valor ha de contenir un màxim de 85 caràcters.
- **NO FER:** No sobrecarreguis el panell destacat amb massa informació, perquè pot fer que el missatge principal sigui difícil d'identificar.

### Jerarquia visual
- **FER:** Utilitza tipografia destacada i espais blancs per garantir que el missatge principal sigui fàcilment identificable.
- **NO FER:** No utilitzis tipografia petita i poc espai blanc que dificulti la identificació del missatge principal.

### Propòsit
- **FER:** Mostra el propòsit del portal web de forma clara i concisa.
- **NO FER:** No mostris informació confusa o irrellevant sobre el propòsit del portal web.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG) del component:
- **1.3.4 Orientació (AA):** el contingut de l'àrea de text s'adapta a les diferents orientacions de la pantalla, vertical o horitzontal. (https://www.w3.org/Translations/WCAG22-ca/#orientation · https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **1.4.3 Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. (https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum · https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **1.4.4 Canvia la mida del text (AA):** excepte subtítols i imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. (https://www.w3.org/Translations/WCAG22-ca/#resize-text · https://www.w3.org/WAI/WCAG22/Understanding/resize-text)

### Pautes aplicables a imatges
- **1.1.1 Contingut no textual — text alternatiu per imatges (A):** cal proporcionar un text alternatiu (atribut alt) per a la imatge de fons. (https://www.w3.org/Translations/WCAG22-ca/#non-text-content · https://www.w3.org/WAI/WCAG22/Understanding/non-text-content)
- **1.4.3 Contrast mínim (AA):** si una imatge conté text, el contrast entre el text i el fons de la imatge ha de complir un mínim de 4,5:1 per a textos normals i 3:1 per a textos grans. (https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum · https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **1.4.5 Imatges com a text (AA):** evitar utilitzar imatges per representar text, excepte quan el text dins de la imatge sigui essencial (per exemple, un logotip) o no es pugui aconseguir el mateix efecte visual amb text en format HTML/CSS. (https://www.w3.org/WAI/WCAG22/Understanding/images-of-text)
- **1.4.10 Redistribució — escalabilitat i compatibilitat amb zoom (AA):** les imatges han de ser escalables sense pèrdua de funcionalitat o claredat amb un zoom de fins al 200%. (https://www.w3.org/Translations/WCAG22-ca/#reflow · https://www.w3.org/WAI/WCAG22/Understanding/reflow)
- **Evitar contingut decoratiu o superflu (AA):** si la imatge és purament decorativa, no ha de ser llegida per tecnologies de suport; es pot aconseguir amb un atribut alt="" o etiquetant-la com a contingut decoratiu. La font cita 2.4.6 Encapçalaments i etiquetes descriptives (https://www.w3.org/Translations/WCAG21-ca/#non-text-content · https://www.w3.org/Translations/WCAG22-ca/#headings-and-labels · https://www.w3.org/WAI/WCAG22/Understanding/headings-and-labels).

### Pautes aplicables a vídeos
- **1.2.1 Contingut multimèdia només amb àudio o vídeo (A):** per a contingut que només conté àudio o només vídeo, cal proporcionar una transcripció textual equivalent. (https://www.w3.org/Translations/WCAG22-ca/#audio-only-and-video-only-prerecorded · https://www.w3.org/WAI/WCAG22/Understanding/audio-only-and-video-only-prerecorded.html)
- **1.2.2 Subtítols, contingut pregravat (A):** tots els vídeos amb contingut multimèdia pregravat han de tenir subtítols sincronitzats. (https://www.w3.org/Translations/WCAG22-ca/#captions-prerecorded · https://www.w3.org/WAI/WCAG22/Understanding/captions-prerecorded.html)
- **2.1.1 Teclat — controls accessibles per al reproductor de vídeo (A):** tots els reproductors han de ser operables amb teclat i compatibles amb tecnologies assistives (lectors de pantalla). Han de permetre accions bàsiques: reproduir / pausar el vídeo; activar / desactivar els subtítols i les audiodescripcions. (https://www.w3.org/Translations/WCAG22-ca/#keyboard · https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **2.2.2 Posar en pausa, aturar o amagar (A):** si un vídeo es reprodueix automàticament en carregar-se, ha de permetre's posar-lo en pausa o aturar-lo immediatament. (https://www.w3.org/WAI/WCAG22/Understanding/pause-stop-hide.html)
- **2.3.1 Tres centelleigs o per sota del llindar — contingut segur per a persones amb epil·lèpsia (A):** els vídeos no han de contenir contingut que pugui provocar atacs epil·lèptics (com flashos entre 3 i 50 Hz). (https://www.w3.org/WAI/WCAG22/Understanding/three-flashes-or-below-threshold.html)
- **1.4.3 Contrastos visuals adequats (AA):** els textos o subtítols sobreimposats al vídeo han de complir els estàndards de contrast mínim: 4,5:1 per a textos normals, 3:1 per a textos grans. (https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum · https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)

## Implementació (component web)

### `<hero-banner-component>`
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Obligatorietat (lloc) | Tipus | Per defecte (PDF) |
|---|---|---|---|---|---|
| `dataKeyFieldSearchfield` | `data-key-field-searchfield` | Quan es carreguen les dades mitjançant URL, indica al component quina columna o columnes ha de prendre | Opcional | String o String(array) | `text` |
| `dataSearchfield` | `data-searchfield` | Permet carregar dades no gaire grans en un string(array) (PDF: accepta array d'objectes o string JSON) | Opcional | String (array) | `[]` |
| `dataUrlSearchfield` | `data-url-searchfield` | Permet carregar dades grans mitjançant una URL connectada a backend (PDF: URL de l'endpoint que proveeix les dades del cercador) | Opcional | String | `` (buit) |
| `imgDescription` | `img-description` | Descripció de la imatge per a l'accessibilitat. | Obligatori | String | undefined |
| `multimedia` | `multimedia` | Elecció del tipus de fitxer multimèdia (PDF: configuració del contingut multimèdia; accepta objecte o string JSON) | Opcional | String | `image` |
| `searchfieldId` | `searchfield-id` | Identificador de l'input de tipus text del searchfield | Obligatori | String | undefined |
| `searchfieldName` | `searchfield-name` | Nom de l'input de tipus text del searchfield (atribut name) | Obligatori | String | undefined |
| `searchfieldTextEtiqueta` | `searchfield-text-etiqueta` | Text de l'etiqueta del camp de cerca | Opcional | String | undefined |
| `searchfieldValue` | `searchfield-value` | Valor del searchfield | Opcional | String | `` (buit) |
| `selectorSearch` | `selector-search` | Selector del camp de cerca. (PDF: selector CSS de l'element àncora del cercador) | Obligatori | String | `` (buit) |
| `showSearchfield` | `show-searchfield` | Visibilitat del camp de cerca | Opcional | Boolean | `true` |
| `srcMultimedia` | `src-multimedia` | Ruta del fitxer multimèdia (imatge o vídeo) | Obligatori | String | undefined |
| `titleBanner` | `title-banner` | Títol del panell destacat. | Obligatori | String | undefined |
| `tooltipButtonSearch` | `tooltip-button-search` | Text tooltip que es mostra quan es passa el cursor (hover) sobre el botó icona de cerca. | Opcional | String | `Cerca` |
| `webDomain` | `web-domain` | Text del domini web ubicat a sobre de `titleBanner` | Obligatori | String | undefined |

**Variants**

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `multimedia` | `image` `external-video` `internal-video` | `image` |

**Esdeveniments:** el PDF indica "Sense events declarats" per a `hero-banner-component`; la pàgina del lloc llista els del `searchfield-component`:

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `valueChange` | Es llança cada vegada que es fa clic al botó de cerca o enter al camp de cerca. | `value` | `searchfield-component` |
| `filterButtonClick` | Detecta el clic al botó de filtre propagant el seu ID. | `ID` | `searchfield-component` |

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<hero-banner-component 
  multimedia="image"
  src-multimedia="/assets/photos/hero_banner.png" 
  img-description="Description image"
  title-banner="Títol" 
  show-searchfield="true"
  searchfield-text-etiqueta="Cerca"
  web-domain="gencat.cat"
  searchfield-id="searchfield-id" 
  searchfield-name="searchfield-name"
  data-key-field-searchfield="text"
  data-searchfield='["Barcelona","Girona","Lleida","Tarragona"]'
  data-url-searchfield="/api/search-data"
  searchfield-value="Barcelona"
  selector-search=".search-result"
  tooltip-button-search="Cercar"
>
</hero-banner-component>
```

**Exemple d'instància (PDF)**

```html
<hero-banner-component
data-key-field-searchfield='text'
data-searchfield='[]'
data-url-searchfield=''
img-description="texto-ejemplo"
multimedia='image'
searchfield-id="texto-ejemplo"
searchfield-name="texto-ejemplo"
searchfield-text-etiqueta="texto-ejemplo"
searchfield-value=''
selector-search=''
show-searchfield=true
src-multimedia="texto-ejemplo"
title-banner="texto-ejemplo"
tooltip-button-search='Cerca'
web-domain="texto-ejemplo"
></hero-banner-component>
```

**Depèn de:** `searchfield-component` ([Camp de cerca](component-camp-de-cerca.md)).

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.3.0 | 11.0.0 | 31 juliol, 2026 | Disseny: s'ha modificat el panell destacat eliminant la imatge d'aquest. |
| 12.0.0 | 11.0.0 | 19 juny, 2026 | Desenvolupament: es canvia el nom de la variable del background |
| 12.0.0 | 10.1.0 | 29 maig, 2026 | Disseny: s'aplica el token específic pel fons del component per adaptació a altres modes de color. Desenvolupament: s'afegeix la property searchfieldTextEtiqueta i s'habilita de forma obligatòria l'etiqueta del Searchfield; es corregeix la mida de la imatge quan s'augmenta la mida del text |
| 8.6.0 | 9.2.0 | 27 febrer, 2026 | Desenvolupament: s'afegeixen les tres properties noves del search field per carregar dades des d'un backend |
| 8.6.0 | 9.1.0 | 9 febrer, 2026 | Disseny: s'eliminen truncats de tots els texts; s'aplica alçada mínima de 604 px a la versió Large; layout de la imatge a la versió Large a la part superior. |
| 8.2.0 | 9.1.0 | 6 febrer, 2026 | Desenvolupament: adaptacions d'accessibilitat pel que fa a mides de font extra gran i augment de pantalla; s'elimina la property placeholder |
| 8.2.0 | 6.2.1 | 27 octubre, 2025 | Disseny: es fa un reset de la instància de l'asset per actualitzar espaiats i tipografies correctament. |
| 8.1.0 | 6.2.1 | 6 octubre, 2025 | Disseny: s'elimina el subtítol i descriptor i també s'incrementa el límit de text del títol a 5 línies. Desenvolupament: nova propietat afegida o eliminada |
| 6.0.0 | 6.1.0 | 12 setembre, 2025 | Desenvolupament: nova propietat afegida |
| 6.0.0 | 6.0.1 | 28 juliol, 2025 | Desenvolupament de l'evolutiu |
| 6.0.0 | 1.1.0 | 8 juliol, 2025 | Disseny: nou disseny del component. |
| 2.3.0 | 1.1.0 | 17 febrer, 2025 | Desenvolupament del component |
| 2.2.0 | No aplica | 20 de desembre, 2024 | Disseny i documentació del component |

## Vegeu també
- Subcapçalera (la font l'enllaça a la pàgina de [Components](sobre-components.md)).
- [Menú horitzontal](component-menu-horitzontal.md): per navegar pels elements principals de la pàgina.
- [Camp de cerca](component-camp-de-cerca.md)
