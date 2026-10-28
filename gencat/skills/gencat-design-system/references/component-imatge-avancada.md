# Imatge avançada (Advanced image)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/349c08 · Web component: `<advanced-image-component>` (paquet core) · Font actualitzada el 2026-10-06 · Extret el 2026-10-28

## Què és i quan usar-lo
Component que permet mostrar imatges amb opcions addicionals, com peu d'imatge, ampliació o visualització en galeria, segons les necessitats del disseny.

Permet afegir imatges en pàgines de detall, com per exemple articles i notícies. Inclou la possibilitat d'afegir un peu d'imatge i ofereix tres mides d'imatge:
- **Gran** (Large): ocupa tota l'amplada del contenidor. Proporció recomanada de 16:9.
- **Mitjà** (Medium): s'insereix dins del text amb flotació. Proporció recomanada d'1:1.
- **Petit** (Small): també s'insereix dins del text amb flotació. Proporció recomanada d'1:1.

El component també permet afegir un botó opcional que, quan es fa clic, obre una galeria d'imatges (si hi ha més d'una imatge) o amplia la imatge per veure-la en detall.

Quan s'utilitza:
- Quan una imatge aporta informació rellevant i contextualitza el contingut.
- Quan es vol oferir la possibilitat de veure imatges en una galeria.

## Quan NO usar-lo / alternatives
- Quan no aporta valor informatiu.
- Quan genera confusió o dificulta la lectura.

## Anatomia
Components de la imatge avançada:
1. **Imatge:** per defecte en mode *Fill (omplir)*; opcional en mode *Crop (retallar)*.
2. **Botó** (opcional): si hi ha una sola imatge, es mostra el botó per ampliar-la. Si hi ha més d'una imatge, es mostra el botó de galeria, indicant quantes imatges addicionals hi ha a la galeria.
3. **Peu d'imatge** (opcional): text complementari a la imatge.

Aclariment sobre els modes:
- **Mode per defecte: Fill (omplir).** La imatge s'escala per omplir completament el contenidor sense deixar espais buits. Pot retallar-se si la seva relació d'aspecte no coincideix amb la del contenidor.
- **Mode opcional: Crop (retallar)** (quan es vol enfocar una àrea específica). Es pot definir un punt focal o triar manualment quina part de la imatge es retalla.

### Modal d'ampliació d'imatge
1. **Imatge:** es redimensiona perquè encaixi completament dins del contenidor sense retallar-se, amb el mode *fit (encaixar)*. Manté la proporció original de la imatge; pot deixar espais buits si les proporcions no coincideixen.
2. **Botó de tancament del modal** (la modal també es tanca en fer clic fora).
3. **Botons per veure la imatge següent i anterior** (només quan hi ha una galeria).
4. **Botons per ampliar i reduir la imatge.** Si es fa clic en tots dos, apareix un tercer botó que, en fer-hi clic, restaura la imatge a la seva mida original. També es pot ampliar o reduir la imatge mitjançant el comportament estàndard (vegeu Accessibilitat).
5. **Peu d'imatge** (opcional): text complementari a la imatge.
6. **Indicador d'estat** (només quan hi ha una galeria): el primer número mostra la imatge que s'està visualitzant i el segon indica el total d'imatges de la galeria.
7. **Miniatures d'imatges** (només quan hi ha una galeria): es mostren en miniatura les imatges de la galeria. Són clicables i redirigeixen a la imatge corresponent de la galeria.

## Variants, tipus i estats

Imatge:

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Size | Large / Medium / Small | Large |
| Show Image caption | True / False | True |
| Image caption text | Text | Image caption |
| Button | True / False | True |
| Button type | Zoom in / Gallery | Zoom in |
| Image aspect ratio | 16:9 / 1:1 | 16:9 |
| State | Default / Error | Default |

Modal:

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | ExtraLarge - Large / Medium - Small | ExtraLarge - Large |
| Show Image caption | True / False | True |
| Show Gallery | True / False | True |
| Pagination text | Text | 1/8 |

Variants Figma: Imatge avançada [State = Default]; Imatge avançada [Aspect ratio = 16:9]; exemple de botó ampliat o reduït amb botó per tornar a la mida original.

## Mides i espaiats

### Mida mínima i màxima
- **Large (gran):** s'adapta al contingut de la pàgina. Té una mida mínima i màxima de 640 px.
- **Medium (mitjà):** mida fixa de 304 px per a tots els dispositius.
- **Small (petit):** mida fixa de 192 px per a tots els dispositius.

### Proporció recomanada
Large (16:9), Medium (1:1) i Small (1:1).

### Adaptació a quadrícula
La mida "gran" s'ajusta completament a l'amplada del contenidor, mentre que les mides "mitjà" i "petit" es posicionen amb flotació dins del text, respectant sempre un marge de 24 px i alineant la imatge a l'esquerra o a la dreta, però mai al centre. Vegeu [Punt de tall i quadrícules](fonaments-punt-de-tall-i-quadricules.md).

### Modal: marges
La modal s'ajusta a l'amplada de la pantalla, però sempre deixant un marge entre els costats de la modal i la pantalla. En dispositius *Extralarge* (extragran) i *large* (gran), aquest marge és de 24px a cada costat; en dispositius *Medium* (mitjà) i *Small* (petit), de 12px. La modal no toca els límits de la pantalla.

L'alçada de la modal s'ajusta a la mida del seu contingut, sempre que sigui menor que l'altura de la pantalla. Si la supera, la modal es redueix automàticament deixant un marge de 24px des de la part superior i inferior de la pantalla, ajustant l'altura de la imatge perquè tota la modal hi càpiga.

## Comportament i interacció

### Interactivitat
En fer clic al botó opcional, s'obre una galeria d'imatges on es pot ampliar i reduir la imatge mitjançant els botons de zoom.

### Gestió d'errors en imatges
En cas que es produeixi un error en carregar una imatge, es mostra una imatge específica d'error. A més, s'inclou un text alternatiu per informar l'usuari que s'ha produït un error.

### Compatibilitat
Es pot incrustar tant dins del contingut principal com en elements interactius, com per exemple pestanyes i acordions.

## Bones pràctiques

### Mida adequada segons la disposició i importància de la imatge
- **FER:** Escull mides d'imatge que s'adaptin a la disposició de la pàgina per mantenir l'harmonia visual.
- **NO FER:** No utilitzis imatges massa petites que puguin dificultar la comprensió.

### Organització d'imatges en galeries
- **FER:** Utilitza una galeria d'imatges quan tinguis moltes imatges per mostrar, per evitar que la pàgina es faci massa llarga o desordenada.
- **NO FER:** No col·loquis imatges l'una sota l'altra, ja que pot dificultar la navegació i fer que la pàgina sigui difícil de navegar.

### Peu d'imatge només quan sigui necessari
- **FER:** Inclou un peu d'imatge clar i breu que expliqui el contingut de la imatge quan sigui rellevant per a la comprensió.
- **NO FER:** Evita peus d'imatge excessivament llargs que desvien l'atenció de la imatge.

### Botó d'ampliació només quan sigui necessari
- **FER:** Incorpora un botó d'ampliació només si els detalls de la imatge són importants per a l'usuari. Si la imatge necessita ampliació, mostra-la en una mida "Gran" o "Mitjà".
- **NO FER:** No utilitzis el botó d'ampliació en imatges de mida petita "Small".

### Racionalitza el nombre d'imatges
- **FER:** Ubica les imatges de manera que complementin el contingut sense interferir en la lectura.
- **NO FER:** No saturis el text amb imatges flotants que puguin fer que el contingut es torni difícil de llegir.

### Resolució d'imatge
- **FER:** Utilitza imatges de resolució alta per garantir una visualització nítida i professional, i opta per formats adequats que permetin una càrrega ràpida sense perdre qualitat.
- **NO FER:** No utilitzis imatges borroses o de baixa resolució que deteriorin l'experiència visual.

## Accessibilitat
Els requisits WCAG per a imatges es consulten a l'apartat d'accessibilitat d'imatges: [Imatge](fonaments-imatge.md).

### Navegació per teclat

Imatge avançada:

| Tecla | Acció |
|---|---|
| Tabulació | Navega a l'element interactiu |
| Intro / Enter | Activa l'element seleccionat |

Modal:

| Tecla | Acció |
|---|---|
| Tabulació | Navega per elements interactius |
| Fletxes dreta i esquerra | Navega dins dels elements miniatura de la galeria |
| Intro / Enter | Activa l'element seleccionat |
| Esc | Tanca el modal |

### Focus en el diàleg modal
El focus ha d'estar atrapat dins del diàleg i no s'ha de moure fora de la modal fins que es tanqui. Lectura del contingut del modal en ordre:
- **Botons de zoom de la imatge:** si l'usuari prem **Tab**, el focus es mou entre els botons de zoom.
- **Botons de navegació:** si l'usuari prem **Tab**, el focus es mou entre els botons de navegació.
- **Miniatures a la part inferior:** si l'usuari prem **Tab**, el focus es desplaça a la llista de miniatures; si prem les **fletxes dreta i esquerra**, es desplaça dins dels elements de la galeria.
- **Botó de tancament:** si l'usuari prem **Esc**, el modal es tanca. El focus ha d'estar atrapat dins del diàleg i no s'ha de moure fora de la modal fins que es tanqui.

Després de tancar el diàleg modal, el focus ha de tornar a l'element que el va invocar.

### Comportament per ampliar o reduir la imatge
Es pot ampliar o reduir la imatge mitjançant el comportament estàndard:
- **Roda del ratolí + tecla Ctrl (Windows/Linux) o Cmd (Mac):** fa zoom a la imatge.
- Gestos en el *trackpad*, a la tauleta i al mòbil:
  - **Interactuar amb dos dits:** apropa/allunya la imatge (si el sistema o el navegador ho permet).
  - **Doble toc amb dos dits:** fa zoom a la imatge seleccionada.

## Implementació (component web)

### `<advanced-image-component>`

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat |
|---|---|---|---|---|---|
| `alignImg` | `align-img` | Alineació de la imatge quan no és gran. Opcions: ``, `left`, `right` | `string` | `` (buit) | Obligatori |
| `buttonImg` | `button-img` | Indica si la imatge tindrà botó de visualitzador d'imatge | `boolean` | `true` | Opcional |
| `images` | `images` | Col·lecció d'imatges: array amb l'enllaç de cada imatge i la seva descripció si en té. Accepta array d'objectes o string JSON | `string` (array) | `` (buit) | Obligatori |
| `showPreview` | `show-preview` | Indica si es mostra o no la imatge i la vista prèvia (previsualització que obre la modal amb la galeria d'imatges) | `boolean` | `true` | Opcional |
| `sizeImg` | `size-img` | Indica la mida de la imatge. Opcions: `large`, `medium`, `small` | `string` | `large` | Opcional |

**Variants**

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `alignImg` | `left` `right` | — |
| `sizeImg` | `large` `medium` `small` | `large` |

**Propietats de l'array `images`**

| Propietat | Descripció | Obligatorietat | Tipus |
|---|---|---|---|
| `url` | Enllaç on es troba la imatge | Obligatori | `string` |
| `description` | Descripció breu de la imatge | Opcional | `string` |

**Mètodes públics**

| Mètode | Descripció | Paràmetre |
|---|---|---|
| `openModalMethod()` | Obre la modal. | - |

**Esdeveniments** (segons el lloc; origen `button-component`)

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `blurButton` | Es llança cada cop que es treu el focus en un botó. | - | `button-component` |
| `focusButton` | Es llança cada cop que es fa focus en un botó. | - | `button-component` |
| `handlerClick` | Es llança cada cop que es fa clic en un botó i com a paràmetre conté les dades de l'esdeveniment. | `id` | `button-component` |

[discrepància: el lloc documenta els esdeveniments `blurButton`, `focusButton` i `handlerClick` (propagats del botó intern); el PDF diu "Sin eventos declarados"]

**Depèn de:** `button-component` ([Botons](component-botons.md)).

**Utilitzat per / en:**
- Core: `file-uploader-component` ([Carregador d'arxius](component-carregador-d-arxius.md)).
- Conversational: `chat-message-component` ([Missatge de xat](component-missatge-de-xat.md)).

**Exemple d'ús**

```html
<!-- /index.html -->
   <advanced-image-component images='[{"url": "/assets/photos/img_1.png", "description": "Image caption"},
  {"url": "/assets/photos/img_2.png", "description": "Imagen 1 con un diseño atractivo."},
  {"url": "/assets/photos/img_3.png", "description": "Imagen 2 que ilustra nuestra última oferta."},
  {"url": "/assets/photos/img_4.png", "description": "Imagen 3 con una presentación dinámica."},
  {"url": "/assets/photos/img_5.png", "description": "Imagen 4 que destaca nuestros productos destacados."}]'
  button-img="true" size-img="small" align-img="" show-preview="true">
    </advanced-image-component>
```

Exemple d'instància (PDF):

```html
<advanced-image-component
align-img=''
button-img=true
images=''
show-preview=true
size-img='large'
></advanced-image-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 10.0.0 | 12.0.3 | 4 setembre, 2026 | **Desenvolupament**: s'ha corregit el posicionament del modal. |
| 10.0.0 | 12.0.0 | 10 juliol, 2026 | **Desenvolupament**: s'utilitza el token correcte per al color del text de la paginació |
| 10.0.0 | 11.0.0 | 19 juny, 2026 | **Desenvolupament**: es canvien les dues icones de material per una icona de bootstrap i de la pròpia biblioteca |
| 10.0.0 | 10.0.0 | 8 maig, 2026 | **Desenvolupament**: ajustos d'accessibilitat |
| 10.0.0 | 9.4.0 | 17 abril, 2026 | **Disseny**: s'afegeix l'estat Error com a variant de les imatges; es puja l'opacitat de les imatges del carrusel al 100%. **Desenvolupament**: s'ha corregit l'aspect ratio de la imatge de portada a 16/9 en mida large; s'ha afegit la propietat `showPreview` que permet mostrar o ocultar la previsualització que obre la modal amb la galeria d'imatges. |
| 8.6.0 | 9.2.0 | 27 febrer, 2026 | **Desenvolupament**: es fan millores d'accessibilitat |
| 8.6.0 | 8.5.0 | 9 febrer, 2026 | **Disseny**: s'afegeixen els estats al botó d'acció (ampliar imatge/galeria); s'elimina el truncat del "image caption" |
| 8.1.0 | 8.5.0 | 5 desembre, 2025 | **Desenvolupament**: resolució de problemes menors |
| 8.1.0 | 8.0.0 | 14 novembre, 2025 | **Desenvolupament**: resolució de problemes |
| 8.1.0 | 7.0.0 | 24 octubre, 2025 | **Desenvolupament**: resolució de problemes |
| 8.1.0 | 6.1.0 | 6 octubre, 2025 | **Disseny**: s'afegeix amplada mínima al component Advanced Image Large. |
| 8.0.0 | 6.1.0 | 12 setembre, 2025 | **Disseny**: l'estil de text del "pagination text" es modifica de Body a Label. **Desenvolupament**: resolució de problemes |
| 6.0.0 | 6.0.1 | 28 juliol, 2025 | **Desenvolupament**: resolució de problemes |
| 6.0.0 | 6.0.0 | 8 juliol, 2025 | **Disseny**: s'ha ajustat l'amplada màxima de les imatges. |
| 2.4.0 | 6.0.0 | 3 juliol, 2025 | **Desenvolupament**: resolució de problemes |
| 2.4.0 | 5.0.0 | 9 juny, 2025 | **Desenvolupament**: resolució de problemes |
| 2.4.0 | 3.0.0 | 28 abril, 2025 | **Desenvolupament**: resolució de problemes |
| 2.4.0 | 2.1.0 | 31 març, 2025 | **Desenvolupament** del component |
| 2.4.0 | No aplica | 10 març, 2025 | **Disseny** del component. |

## Vegeu també
- [Botons](component-botons.md): per realitzar accions.
- [Imatge](fonaments-imatge.md)
- [Punt de tall i quadrícules](fonaments-punt-de-tall-i-quadricules.md)
