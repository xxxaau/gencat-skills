# Visor de mapa (Map viewer)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/332554 · Web component: `<poi-component>` i `<icon-poi-component>` (paquet core) · Font actualitzada el 2026-10-20 · Extret el 2026-10-28

## Què és i quan usar-lo
El visor de mapa és una eina digital interactiva que permet explorar, consultar i entendre informació geogràfica de manera visual i intuïtiva. Mitjançant elements interactius com POIs (*Points of Interest*), clústers, elements d'ubicació i controls de zoom, l'usuari pot navegar pel territori i accedir a dades rellevants.

Quan s'utilitza (el visor de mapa és útil quan):
- Es vol presentar dades espacials de manera atractiva i interactiva.
- Es combina informació geogràfica amb contingut multimèdia.
- Es busca fomentar l'exploració d'un territori o projecte.

### Tipus de visors de mapa
Hi ha 2 tipus de visors, el simple i l'avançat, segons el cas d'ús.
- **Visor de mapa simple:** mapa interactiu amb menys elements; per exemple, no té l'element d'ubicació. Serveix per visualitzar la ubicació d'un sol punt d'interès. S'utilitza en pàgines de detall on es vol informar d'on es troba el punt d'interès.
- **Visor de mapa avançat:** mapa interactiu amb tots els elements del component. Serveix per ubicar més d'un punt d'interès. S'utilitza en pàgines de resultats de cerca.

## Quan NO usar-lo / alternatives
No és recomanable utilitzar el visor de mapa quan:
- Les dades no tenen un component geogràfic i es poden mostrar millor en un document o gràfic.
- Es vol mostrar contingut multimèdia, com àudios o vídeos.

## Anatomia
- Visor avançat: Figma Map viewer desktop [Show view control = True, Show advanced control = True, Show layers button = True, Breakpoint = Extra large - Medium, View = Map, Type = Advanced].
- Visor simple: la font mostra la mateixa referència Figma que l'avançat (Type = Advanced) [a verificar].
- POI actiu: Figma anatomia (Visor de mapa/Components/Visor de mapa/DOC_Visor_mapa/POI_actiu/anatomia).

## Variants, tipus i estats

### Propietats del visor de mapa

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Extra large - Medium / Small | - |
| View | Map / Satellite | Map |
| Type | Advanced / Simple | Advanced |
| Show view controls | True / False | True |

Variants Figma: Map viewer desktop [Show view control = True, Show advanced control = True, Show layers button = True, Breakpoint = Extra large - Medium, View = Map, Type = Advanced].

### Elements interactius del mapa

#### Tipus de visualitzacions de mapa
És un control segmentat que serveix per canviar el tipus de visualització del mapa. La vista mapa és la representació esquemàtica del territori: mostra carrers, carreteres, noms de llocs, edificis, parcs i altres elements útils per orientar-se. La vista satèl·lit mostra imatges reals captades per satèl·lits: permet veure com és realment el terreny (edificis, vegetació, muntanyes, camps, etc.). Propietats del component a [Control segmentat](component-control-segmentat.md).

#### Controls de navegació
Elements d'interacció que permeten a l'usuari ampliar o reduir el zoom, veure el mapa a pantalla completa i activar la geolocalització per centrar-se en la seva ubicació actual. També s'hi inclouen controls més avançats, com la possibilitat de dibuixar una selecció al mapa o gestionar les capes. Propietats del component a [Botons](component-botons.md) (botó d'icona).

#### Marcador
Element visual que indica la ubicació seleccionada per l'usuari dins del visor de mapa.

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Default / Selected / Drag / Hover | Default |

Variants Figma (estats): Marker [State = Default].

#### Punt d'interès o POIs
Un punt d'interès o POI és una ubicació geogràfica específica que pot ser rellevant o útil per a l'usuari. Pot ser qualsevol lloc amb algun interès cultural, comercial, turístic o pràctic.

Tipus de POI:
- **POI amb icona:** la icona específica indica que el POI està classificat dins d'una temàtica concreta. Per exemple, un POI amb la icona d'un arbre representa un element relacionat amb el medi ambient. Les icones actuen com a símbols visuals que faciliten la identificació ràpida del tipus de contingut.
- **POI sense icona:** no forma part de cap classificació temàtica definida. Pot representar informació genèrica o no categòrica.
- **POI amb icona i text:** la icona permet identificar visualment la temàtica o el tipus d'element, mentre que el text destaca una dada concreta. Aquesta combinació facilita una comprensió més ràpida i precisa del contingut.

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Color | Red / Blue / Purple / Grey / Green / Orange | - |
| State | Default / Selected / Hover | Default |
| Icon | True / False | False |
| Show text | True / False | False |
| Show distance | True / False | - |

Colors i icones: la font mostra una taula (només imatges) amb les files "Amb icona", "Sense icona" i "Amb icona i text" per a les columnes Roig, Blau, Verd, Gris, Marró, Lila.
[discrepància: les propietats Figma llisten Red / Blue / Purple / Grey / Green / Orange; la taula "Colors i icones" llista Roig, Blau, Verd, Gris, Marró, Lila]

Variants Figma (estats): Visor de mapa/POI [Show Icon = False, Color = Red, State = Hover | Default | Selected].

Classificació dels POIs segons tema:
1. Desenvolupament econòmic i productiu: activitats que impulsen el creixement econòmic, la innovació i el treball.
2. Serveis públics i benestar: [la font repeteix literalment la descripció de l'1: "Activitats que impulsen el creixement econòmic, la innovació i el treball."]
3. Medi ambient i sostenibilitat: temes relacionats amb la protecció del medi natural i l'ecologia.
4. Govern, legalitat i estructura institucional: funcions de l'administració pública, la justícia i la gestió institucional.
5. Cultura, llengua i cohesió social: àrees que fomenten la identitat, la cultura, la comunicació i la vida comunitària.

| Desenvolupament econòmic i productiu | Serveis públics i benestar | Govern, legalitat i estructura institucional | Cultura, llengua i cohesió social | Medi ambient i sostenibilitat |
|---|---|---|---|---|
| Agricultura, pesca i ramaderia | Salut | Registres | Cultura | Medi Ambient |
| Comerç i consum | Educació | Administració pública | Esports i lleure | |
| Turisme | Mobilitat i transports | Justícia | Llengua i comunicació | |
| Economia | Universitats | | Societat, ciutadania i famílies | |
| Empresa, indústria i energia | Serveis socials | | | |
| Treball | Habitatge | | | |
| Tecnologia i innovació | Emergència i seguretat | | | |
| Recerca | | | | |

#### Clústers
Agrupacions de punts d'interès quan el mapa es mostra en un zoom allunyat.

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Size | Large / Medium / Small | Large |
| States | Default / Selected / Hover | Default |
| Color | Red / Blue / Purple / Grey / Green / Orange | - |

Variants Figma (mida, estats, colors): Cluster [Size = Small, State = Default, Color = Red].

#### Localització
Representació d'un punt concret sobre la superfície terrestre; serveix per identificar i situar el lloc on es troba l'usuari. Figma: Location (Visor de mapa/Visor de mapa/Location).

#### Targeta POI
Quan l'usuari fa clic sobre un POI, visualitza les dades informatives del lloc d'interès. El format és diferent en cada punt de tall.

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Type | Floating / Lateral / Inferior | Floating |
| Show Image | True / False | True |
| Show Description | True / False | True |
| Show Metadata | True / False | True |
| Show Tags | True / False | True |
| Show Group Button | True / False | True |
| Show Scroll Bar | True / False | False |
| Show Shadow | True / False | False |

Variants Figma (tipus): POI_active [Title = Títol, Show Description = True, Description = Lorem ipsum dolor sit amet consectetur. Massa risus eget mauris hac enim vitae. Lorem ipsum dolor sit amet consectetur., Show Scroll bar = True, Show Metadata = True, Show Tags = True, Show Image = True, Show Button Group = True, Show Shadow = False, Show Distance = True, Distance data = a 250 m, Show Link = True, Show Footer = True, Type = Floating].

Ubicació segons punt de tall:
- **ExtraLarge:** en fer clic al POI apareix una targeta flotant sobre el mapa. El mapa per sota es manté visible i actiu: l'usuari hi pot interactuar. (Figma: panell_lateral_extraLarge.)
- **Large - Medium:** en fer clic al POI apareix un panell emergent lateral amb la informació. El mapa es manté lleugerament visible (té un *overlay*) però no està actiu: l'usuari no hi pot interactuar. (Figma: panell_lateral_Large.)
- **Small:** en fer clic al POI apareix un panell emergent inferior. El mapa es manté lleugerament visible (té un *overlay*) però no està actiu: l'usuari no hi pot interactuar. (Figma: panell_lateral_small.)

## Comportament i interacció

### Adaptació responsiva
El visor de mapa es mostra tant en format escriptori com en dispositius mòbils, adaptant-se automàticament al contenidor on està integrat.

### Tipus de visualitzacions de mapa
El control segmentat de canvi de visualització del mapa es mostra només amb text, però en la versió *small* apareix amb la icona. (Figma: control_segmentat.)

### Targeta POI
- La capçalera del POI, que conté el títol i la creu de tancament, es manté fixa i sempre visible quan l'usuari fa scroll dins de la targeta.
- La part inferior, on hi ha l'enllaç i els botons d'acció, també és fixa, de manera que roman accessible tot i que el contingut de la targeta sigui llarg.
- Si el contingut supera l'espai disponible, apareix un scroll intern que permet navegar per tota la informació de la targeta sense afectar la resta del mapa, acompanyat d'una ombra a la part superior del peu on hi ha el grup de botons i l'enllaç. (Figma: comportament.)

### Clústers
- Per defecte, el zoom inicial del mapa mostra una regió determinada (per exemple, Catalunya) i els POIs es representen com a clústers, segons la densitat.
- Els clústers es representen amb mides diferents depenent del nombre de POIs que inclouen.
- Quan l'usuari fa clic sobre un clúster, el zoom del mapa s'amplia per mostrar de manera dinàmica els punts d'interès. També a mesura que l'usuari amplia o redueix el zoom, apareixen els punts d'interès de la zona.
- Quan dos punts d'interès comparteixen les mateixes coordenades de localització, apareix un clúster amb el número 2. En fer-hi clic, els dos POIs individuals apareixen separats lleugerament.

### Botó "Dibuixar selecció"
Botó que activa els modes de dibuix del visor de mapa. Pot ser simple o desplegable segons les opcions disponibles. En activar un mode, el botó es transforma en acció de cancel·lació i es mostra un avís explicatiu al visor.

## Bones pràctiques
Estructura i forma:
- **FER:** mantingues una estructura clara de tots els elements.
- **NO FER:** no desordenis els elements dins del visor; l'ordre és essencial per mantenir la coherència.

Inclou tots els elements de mapa:
- **FER:** sempre que sigui possible, utilitza tots els elements per garantir que l'experiència de l'usuari sigui completa.

Icones:
- **FER:** fes servir les icones correctament de la nostra llibreria.
- **NO FER:** no utilitzis símbols confusos, o icones que no estan dins de la nostra llibreria.

Colors:
- **FER:** fes servir els colors de les icones segons la categorització documentada.
- **NO FER:** no facis servir els colors d'una manera errònia.

Mida:
- **FER:** fes servir els clústers tal com s'han plantejat, agrupant el nombre correcte d'elements.
- **NO FER:** no facis servir els clústers d'una manera errònia, sense tenir en compte el nombre d'elements que agrupen.

Número:
- **NO FER:** no eliminis el nombre dels elements que engloba cada clúster.

## Accessibilitat

### Pautes d'accessibilitat del contingut web (WCAG)
- **Contrast mínim (AA) — 1.4.3:** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA) — 1.4.4:** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA) — 1.4.11:** els elements gràfics presenten un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A) — 2.1.1:** tota la funcionalitat del contingut es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Focus visible (AA) — 2.4.7:** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

### Navegació per teclat

| Tecla | Acció |
|---|---|
| Tabulació | Navegació al següent element interactiu |
| Shift + Tabulació | Navegació a l'anterior element interactiu |
| Enter | Activar element interactiu |

Els mapes són elements que poden resultar molt complicats de navegar per teclat i, per això, s'ha optat per **no aplicar criteris d'accessibilitat a aquest component.** No obstant això, cal conceptualitzar un **accés alternatiu** a la informació que mostra el mapa, ja sigui mitjançant taules, en cos de text, arxiu descarregable, etc.

## Implementació (component web)

### `<icon-poi-component>`
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatori (lloc) |
|---|---|---|---|---|---|
| `idIconPoi` | `id-icon-poi` | Identificador de la icona del POI. Si no se'n proporciona cap, el component genera automàticament un identificador amb el format `id-icon-poi-XXX`, on XXX és un nombre aleatori | `string` | `undefined` | Opcional |
| `classIcon` | `class-icon` | Classe de Bootstrap Icons amb el nom de la icona (p. ex. `bi-check`) | `string` | `undefined` | Opcional |
| `color` | `color` | Color de la icona. Opcions: `blue`, `green`, `grey`, `orange`, `purple`, `red` | `string` | `red` | Opcional |
| `ariaLabelIconPoi` | `aria-label-icon-poi` | Atribut d'accessibilitat ARIA (aria label) | `string` | `undefined` | Opcional |
| `textIconPoi` | `text-icon-poi` | Permet afegir text | `string` | - | Opcional |

**Variants**

| Propietat | Per defecte | Valors |
|---|---|---|
| `color` | `red` | `red`, `blue`, `purple`, `grey`, `green`, `orange` |

**Esdeveniments**

| Esdeveniment | Descripció | Tipus / paràmetre |
|---|---|---|
| `clickIconPoi` | Es llança cada cop que es fa clic en una icona de POI i conté com a paràmetre l'id de l'element | `CustomEvent<string>` (`id`) |

**Exemple d'ús**

```html
<!-- /index.html -->
 <icon-poi-component
   color="purple"
   class-icon="bi-house">
 </icon-poi-component>
```

Exemple d'instància (PDF):

```html
<icon-poi-component
aria-label-icon-poi="texto-ejemplo"
class-icon="texto-ejemplo"
color='red'
id-icon-poi="texto-ejemplo"
></icon-poi-component>
```

### `<poi-component>`
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatori (lloc) |
|---|---|---|---|---|---|
| `opacity` | `opacity` | Indica si hi ha opacitat darrere del POI | `boolean` | `false` | Obligatori |
| `titlePoi` | `title-poi` | Títol del POI | `string` | `undefined` | Obligatori |
| `urlImage` | `url-image` (el lloc escriu `urlImage`) | URL de la imatge del POI | `string` | `undefined` | Opcional |
| `descriptionImage` | `description-image` | Text alternatiu de la imatge | `string` | `undefined` | Opcional |
| `descriptionPoi` | `description-poi` | Descripció del POI | `string` | `undefined` | Opcional |
| `metadataList` | `metadata-list` | Array amb el llistat de metadades. Màxim 6 metadades. Accepta array d'objectes o string JSON | `string` (array) | `undefined` | Opcional |
| `tagList` | `tag-list` | Array amb el llistat d'etiquetes. Màxim 6 etiquetes. Accepta array d'objectes o string JSON | `string` (array) | `undefined` | Opcional |
| `linkText` | `link-text` | Text que es mostra dins de l'enllaç | `string` | `undefined` | Opcional |
| `linkMode` | `link-mode` (el lloc escriu `linkMode`) | Mode en què s'obre l'enllaç. Opcions: `external`, `internal` | `string` | `internal` | Opcional |
| `customIdLink` | `custom-id-link` | Identificador personalitzat de l'enllaç | `string` | `undefined` | Opcional |
| `buttonFooter` | `button-footer` | Grup de botons ubicats al peu del POI. Màxim 4 botons | `string` (array) | `undefined` | Opcional |
| `distance` | `distance` | Distància o separació | `string` | `undefined` | - (només al PDF) |

**Propietats de l'array `metadataList`**

| Propietat | Descripció | Obligatorietat | Tipus |
|---|---|---|---|
| `text` | Text de la metadada | Obligatori | String |
| `class-name-icon` | Icona que acompanya el text de la metadada | Obligatori | String |

**Propietats de l'array `tagList`**

| Propietat | Descripció | Obligatorietat | Tipus |
|---|---|---|---|
| `text` | Text de l'etiqueta | Obligatori | String |
| `color` | Color de l'etiqueta | Opcional | String |

**Propietats de l'array `buttonFooter`**

| Propietat | Descripció | Obligatorietat | Tipus |
|---|---|---|---|
| `classNameIcon` | Icona del botó | Obligatori | String |
| `textTooltip` | Tooltip del botó | Obligatori | String |
| `customId` | ID del botó | Obligatori | String |

**Variants**

| Propietat | Per defecte | Valors |
|---|---|---|
| `opacity` | `false` | `false`, `true` |
| `linkMode` | `internal` | `internal`, `external` |
| `color` (etiquetes de `tagList`) | `color-white` | `color-white`, `color-information`, `color-success`, `color-alert`, `color-error`, `color-new`, `color-dark` |

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre |
|---|---|---|
| `linkEmit` | Esdeveniment llançat en fer clic sobre l'enllaç | `id` |
| `handlerClick` | Esdeveniment llançat en fer clic sobre algun dels botons | `id` |
| `poiClosed` | Es llança quan el component es tanca (només al PDF) | `CustomEvent<void>` |

**Mètodes públics**

| Mètode | Acció |
|---|---|
| `openPOI()` | Obre el POI |
| `closePOI()` | Tanca el POI (només al PDF) |

**Depèn de:** [`list-component`](component-llista.md), [`tag-component`](component-etiquetes.md), [`link-component`](component-enllacos.md), [`group-button-component`](component-grup-de-botons.md), [`button-component`](component-botons.md).

**Exemple d'ús**

Per obrir el POI cal que l'element que l'obre tingui associat un esdeveniment de clic que, quan està actiu, s'associa amb un mètode per obrir el POI. Aquest mètode s'anomena `openPOI()`.

```html
<!-- /index.html -->
  <icon-poi-component color="green" id-icon-poi="openPOI"></icon-poi-component>

<poi-component 
  id="myPOI" 
  opacity="true" 
  title-poi="Ajuntament d'Abella de la Conca"
  description-poi="Lorem ipsum dolor sit amet consectetur. Massa risus eget mauris hac enim vitae. Lorem ipsum dolor sit amet consectetur."
  url-image="/assets/photos/img_2.png" 
  description-image="HOli"
  tag-list='[
    {"text": "Text curt"},
    {"text": "Dismissible", "color": "color-new"},
    {"text": "Etiqueta", "color": "color-error"},
    {"text": "Fora de termini fora determini"},
    {"text": "Etiqueta", "color": "color-alert"}
  ]'
  link-text="Veure detall" 
  link-mode=""
  metadata-list='[
    {"text": "Lorem ipsum", "class-name-icon": "bi-telephone"},
    {"text": "Lorem ipsum", "class-name-icon": "bi-telephone"},
    {"text": "Lorem ipsum", "class-name-icon": "bi-telephone"},
    {"text": "Lorem ipsum", "class-name-icon": "bi-telephone"},
    {"text": "Lorem ipsum", "class-name-icon": "bi-telephone"},
    {"text": "Lorem ipsum", "class-name-icon": "bi-telephone"}
  ]'
  button-footer='[
    { "classNameIcon": "bi-envelope", "textTooltip": "Correo", "customId": "correo-btn" },
    { "classNameIcon": "bi-telephone", "textTooltip": "Teléfono", "customId": "telefono-btn" },
    { "classNameIcon": "bi-geo-alt", "textTooltip": "Ubicación", "customId": "ubicacion-btn" }
  ]'>
</poi-component>
<script>
  document.querySelector("icon-poi-component").addEventListener('clickIconPoi', function () {
    document.getElementById('myPOI').openPOI();
  });
</script>
```

Exemple d'instància (PDF):

```html
<poi-component
button-footer="texto-ejemplo"
custom-id-link="texto-ejemplo"
description-image="texto-ejemplo"
description-poi="texto-ejemplo"
distance="texto-ejemplo"
link-mode='internal'
link-text="texto-ejemplo"
metadata-list="texto-ejemplo"
opacity=false
tag-list="texto-ejemplo"
title-poi="texto-ejemplo"
url-image="texto-ejemplo"
></poi-component>
```

[discrepància: el lloc documenta `textIconPoi`/`text-icon-poi` a `icon-poi-component`, que el PDF v12.0.0 no inclou; el PDF afegeix `distance`, `poiClosed` i `closePOI()` a `poi-component`, que el lloc no documenta. El PDF descriu `descriptionImage` com "URL de la imatge" i `customIdLink`/`linkText`/`linkMode` com "URL del enllaç" (text genèric); es recull la descripció del lloc.]

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.2.0 | 12.1.0 | 7 setembre, 2026 | Desenvolupament: s'habilita l'opció d'afegir text dins de la icona POI. |
| 12.2.0 | 12.0.0 | 10 juliol, 2026 | Disseny: es modifiquen els POIs i s'afegeix la variable text + icona. |
| 12.1.0 | 12.0.0 | 10 juliol, 2026 | Desenvolupament: s'utilitza el token correcte per al color de text de títol i descripció |
| 12.1.0 | 9.2.0 | 19 juny, 2026 | Disseny: s'arregla la visualització de les icones del llistat d'icones dins el POI; s'elimina el botó d'icona utilitzat dins el component Map button item perquè la interacció funcioni correctament en modificar la icona. Desenvolupament: ajustos d'accessibilitat per a lector de pantalla i comportament del focus |
| 10.0.0 | 9.2.0 | 17 abril, 2026 | Disseny: es corregeix la deformitat dels POIs dins el mapa; s'actualitza el component de grup de botons amb la funcionalitat d'slots. Desenvolupament (Icon Poi): s'han fet ajustos de mida. |
| 9.1.0 | 9.2.0 | 20 març, 2026 | Disseny: s'ajusta la mida dels POIs a 40x40 px. |
| 9.0.0 | 9.2.0 | 27 febrer, 2026 | Disseny: s'ha modificat la ubicació de l'acció de dibuix i s'ha incorporat, de manera opcional, un nou tipus de dibuix poligonal; s'ha afegit un nou tipus d'icona: marcador. Desenvolupament: es crea la propietat customIdLink per a l'enllaç |
| 8.4.0 | 9.0.0 | 12 gener, 2026 | Desenvolupament: es canvia el nom de la property ariaLabel per ariaLabelIconPo a icon-poi i es modifiquen marges i paddings a poi |
| 8.4.0 | 8.5.0 | 5 desembre, 2025 | Disseny: s'han modificat els marges del títol del POI actiu i els marges del contenidor de contingut i scroll del POI actiu; s'han creat i afegit dos botons de control al mapa: "dibuixar selecció" i botó de capes; s'ha afegit el punt de tall de visor de mapa "small". Desenvolupament: resolució de problemes menors |
| 8.2.0 | 8.0.0 | 15 novembre, 2025 | Desenvolupament del subcomponent icon-POI i resolució de problemes de poi |
| 8.2.0 | 7.0.0 | 27 octubre, 2025 | Disseny: s'ha ajustat el màxim d'alçada del POI actiu, concretament, la variable "inferior" a 768px; s'ha afegit l'element de distància "a 250 m" al component POI actiu amb les propietats corresponents; s'ha afegit un mínim de 64 px d'alçada al "footer" del POI actiu; s'han revisat estils tipogràfics del clúster. |
| 8.1.0 | 7.0.0 | 24 octubre, 2025 | Desenvolupament del subcomponent POI |
| 8.1.0 | - | 6 octubre, 2025 | Disseny: disseny del subcomponent POI actiu. |
| 8.0.0 | - | 12 setembre, 2025 | Disseny i documentació del component |

## Vegeu també
- [Control segmentat](component-control-segmentat.md)
- [Botons](component-botons.md)
- [Enllaços](component-enllacos.md)
- [Panell emergent](component-panell-emergent.md)
- Suport: https://zeroheight.com/38669693e/p/57c57a-suport-i-contacte · https://zeroheight.com/38669693e/p/72240b-preguntes-frequents · https://zeroheight.com/38669693e/p/690b45 · https://zeroheight.com/38669693e/p/342611
