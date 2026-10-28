# Targetes (Cards)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/489c4e · Web component: `<card-highlight-component>`, `<card-info-component>`, `<card-info-evolutive-component>`, `<card-navigation-basic-component>`, `<card-navigation-component>`, `<card-social-component>` (paquet core) · Font actualitzada el 2026-10-26 · Extret el 2026-10-28

## Què és i quan usar-lo
Les targetes són components visuals dissenyats per organitzar i presentar contingut de forma clara i atractiva. Es fan servir per destacar informació, **guiar l'usuari entre seccions i comunicar contingut clau**. El component ofereix diverses variants segons l'objectiu i el context d'ús.

### 1. Targeta destacada (Highlight card)
Dissenyada per **captar l'atenció de l'usuari i ressaltar contingut específic**. El seu principal objectiu és destacar informació clau mitjançant una crida a l'acció clara, que fomenti la interacció o l'accés a un contingut determinat.
Figma: Highlight Card [Description = La descripció de la targeta que és opcional i varia segons la tipologia., Title = El títol de la targeta, Show Description = True, Size = ≥480].

### 2. Targeta de navegació (Navigation card)
S'utilitza **per facilitar l'exploració i la navegació** dins del lloc web. Les targetes de **tipus bàsic** són més directes: tota la targeta és clicable. Les targetes de **tipus avançat** inclouen tres enllaços destacats i un botó que dirigeix a la pàgina de secció.
Figma: Navigation Card [Show Icon / Illustration = True, Show Button = True, Title = El títol de la targeta, Description text = La descripció de la targeta que és opcional i varia segons la tipologia., Change Illustration = Feina i negoci, Breakpoint = -, State = Default, Show Link list = False, Size = -, Show Description = True].

#### 2.1 Targeta de xarxes socials
Permet dirigir l'usuari a les diferents plataformes de xarxes socials, fomentant la interacció, la difusió de continguts i la construcció de comunitat. Figma: targeta xarxa social.

#### 2.2 Targeta d'atenció
Pensada per facilitar la navegació de l'usuari a pàgines d'atenció i contacte. Figma: targeta atenció.

#### Recomanacions per a les diferents targetes de navegació
- Utilitza descriptor només quan sigui necessari.
- Utilitza títols concisos amb llenguatge clar i directe.
- Afegeix icona quan aporti context i diferenciació sobre la resta del contingut.
- Utilitza la icona quan es tracti d'una targeta de navegació de tipus bàsic i utilitza il·lustració per a les de tipus avançat o quan es tracti d'un contingut que vulguis destacar, com per exemple la informació d'atenció i contacte.
- En cas d'enllaçar les xarxes socials al teu web, utilitza les targetes de xarxes socials.

### 3. Targeta d'informació (Information card)
Serveix per **comunicar informació clau a l'usuari**. Tot i que pot incloure enllaços a seccions, el seu objectiu principal no és guiar l'usuari entre pàgines, sinó oferir una vista informativa del contingut. Hi ha diferents tipologies segons el cas d'ús: informació, agenda, butlletí i tràmits.
Figma: Information card [Show Metadata = True, Show Bottom Tags = True, Show Logo = True, Show Top Content = True, Show Location = True, Titile = El títol de la targeta, Space = Espai o recinte, Location = Localitat, Type = Default, State = Default].

## Quan NO usar-lo / alternatives
- No es barregen targetes amb diferents variants dins d'un mateix conjunt o secció (vegeu Bones pràctiques).
- La targeta d'informació no s'ha d'usar com a eina principal de navegació entre pàgines: per a això, targetes de navegació.

## Anatomia
- Targeta destacada: Figma Highlight Card [Description, Title, Show Description = True, Size = ≥480].
- Targeta de navegació, tipus bàsic i avançat: Figma Navigation Card [Show Icon / Illustration = True, Show Button = True, Title, Description text, Change Illustration = Feina i negoci, Breakpoint = -, State = Default, Show Link list = False, Size = -, Show Description = True].
- Targeta de xarxes socials: 1 Icona; 2 Títol de la targeta; 3 Icona indicativa d'enllaç extern.
- Targeta d'atenció: 1 Icona; 2 Títol de la targeta; 3 Icona indicativa d'enllaç.
- Targeta d'informació (tots els tipus): Figma Information card [Show Metadata, Show Bottom Tags, Show Logo, Show Top Content, Show Location, Titile, Space, Location, Type = Default, State = Default].

## Variants, tipus i estats

### Targeta destacada

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Card size | ≥480 / <480 | ≥480 |
| Description | True / False | True |

### Targeta de navegació, tipus bàsic

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | - / Extra Large - Medium / Small | - |
| State | Default / Hover / Focus / Pressed | Default |
| Show Link list | True / False | False |
| Size | - / ≥480 / <480 | - |
| Show Description | True / False | True |
| Description text | Text | Text |
| Title | Text | El títol de la targeta |
| Icon size | Small / Medium | Small |
| Type | Icon / Illustration / Logo | Icon |
| Change icon left | Icon | Envelope |
| Link | Internal / External | External |

Variants: targeta de xarxes socials i targeta d'atenció (vegeu Anatomia).

### Targeta de navegació, tipus avançat

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Extra Large - Medium / Small / - | - |
| State | Default / Hover / Focus / Pressed | Default |
| Show Link list | True / False | False |
| Size | ≥480 / <480 / - | - |
| Show Description | True / False | True |
| Link | Internal / External | Internal |
| Show Button | True / False | True |
| Show Icon / Illustration | True / False | True |
| Change Icon Left | Icon | - |
| Change Illustration | Illustration | - |

Aclariment (quan utilitzar etiquetes o metadades):
- **Utilitza tags (etiquetes)** quan la informació forma part d'un conjunt limitat d'opcions conegudes, com ara el nom de departament, la temàtica o l'estat.
- **Utilitza metadades amb icona** quan la informació és estructurada però amb contingut variable, que no es pot limitar a una llista tancada, com ara dates, adreces o horaris.

Aclariment: diferència entre breakpoint (punt de tall) i card size (mida):
- **Punt de tall:** segons el punt de tall, la targeta es comporta de manera diferent. Quan el punt de tall és small (petit), la targeta s'ajusta al contingut que tingui. En versions medium (mitjà), large (gran) i extra large (molt gran), l'alçada és fixa per evitar que les targetes de la mateixa fila tinguin diferents alçades. Vegeu [Punt de tall i quadrícules](fonaments-punt-de-tall-i-quadricules.md).
- **Mida (size):** controla la disposició de la il·lustració dins de la targeta. A partir d'una certa mida de targeta, la il·lustració passa a la part superior en lloc d'estar a la dreta. Aquest comportament no està directament vinculat al punt de tall. Exemple: en una pantalla large, dues targetes una al costat de l'altra tindran una mida superior a 408 px i mostraran la il·lustració a la dreta; tres targetes una al costat de l'altra tindran menys amplada i la il·lustració es col·loca a la part superior.

### Targeta d'informació

**Tipus informació**

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Default / Hover / Focus / Pressed | Default |
| Show logo | True / False | True |
| Show Metadata | True / False | True |
| Show Bottom Tags | True / False | True |
| Show Image | True / False | True |
| Show Main label | True / False | True |
| Show Description | True / False | True |
| Breakpoint | Medium-Large / Small | True [a verificar: la font dóna "True" com a valor per defecte d'una propietat de punt de tall] |
| Link | Internal / External | Internal |

Aclariment punt de tall: quan és small, la targeta s'ajusta al contingut; en medium i large, l'alçada és fixa per evitar que les targetes de la mateixa fila tinguin diferents alçades.

**Tipus agenda**

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Default / Hover / Focus / Pressed | Default |
| Title | - | - |
| Show Bottom Tags | True / False | True |
| Show Location | True / False | True |

**Tipus butlletí**

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Default / Hover / Focus / Pressed | Default |
| Show Bottom Tags | True / False | True |
| Show Top content | True / False | True |

**Tipus tràmits**

| Propietat | Valor | Valor per defecte |
|---|---|---|
| State | Default / Hover / Focus / Pressed | Default |
| Title | - | - |
| Show Bottom Tags | True / False | True |

## Mides i espaiats
Les targetes s'adapten dinàmicament a la mida de la pantalla i s'organitzen en un sistema de graella basat en columnes.

### Quadrícula
- Les targetes es poden distribuir en configuracions de quatre, tres o dues columnes segons l'espai disponible, procurant sempre oferir la millor visualització per al contingut que es vol mostrar.
- Cal triar el tipus de targeta més adequat segons el propòsit i el context, seleccionar la configuració òptima de columnes i ajustar els textos perquè siguin concisos i clars, assegurant que el contingut es mostri de manera entenedora i sense truncar elements essencials com els títols.
- Per als punts de tall que utilitzen la variant petita, les targetes sempre es mostren en una sola columna per garantir-ne la llegibilitat i la funcionalitat en espais reduïts.
- Les quadrícules usades en cada punt de trencament es consulten a [Punt de tall i quadrícules](fonaments-punt-de-tall-i-quadricules.md). Figma: mides.

### Mida màxima i mínima per tipus
**Targeta destacada.** Quan l'espai on es col·loca la targeta té una amplada inferior a 480 px, cal utilitzar la variant adequada (Card size < 480), que optimitza l'estructura i els elements visuals per garantir la claredat i la llegibilitat.
- Mida de la targeta ≥480: amplada màxima 940px; amplada mínima 480px.
- Mida de la targeta <480px: amplada màxima 479px; amplada mínima 292px.
- Historial: amplada mínima de 252 px del contenidor de títol i text en la versió Card size = ≥480.

**Targeta de navegació, tipus bàsic.** Ideal quan només es vol mostrar una única acció dins de la targeta. No li aplica la card size (mida de la targeta) ni el breakpoint (punt de tall): independentment del dispositiu i la posició, la visualització es manté constant.
- Amplada màxima: 940px
- Amplada mínima: 292px

**Targeta de navegació, tipus avançat.** Quan cal mostrar subcategories amb un llistat d'enllaços, les variants de mida de la targeta i punt de tall sí que apliquen. Quan l'espai té una amplada inferior a 480px, cal utilitzar la variant adequada (Card size < 480). En pantalles de desktop o tablet, el punt de tall és medium-large perquè les targetes han de tenir una alçada fixa i es vegin totes de la mateixa mida. En mòbil, s'ha d'ajustar el punt de tall a small perquè la targeta s'ajusti al contingut, evitant espais en blanc que no aporten res.
- Mida de la targeta < 480: amplada màxima 616px; amplada mínima 480px.
- Mida de la targeta ≥480: amplada màxima 479px; amplada mínima 292px.
- [discrepància: la font assigna aquests intervals amb les etiquetes "<480" i "≥480" possiblement invertides respecte de la targeta destacada; es transcriuen tal com surten, a verificar]

**Targeta d'informació.**
- Amplada màxima: 640px
- Amplada mínima: 296px

## Comportament i interacció
### Agenda
La targeta agenda utilitza l'etiqueta específica per indicar la data de l'esdeveniment. Format:
- **Dates específiques i rangs:** s'indica el dia a la part superior i el mes a la inferior. El mes s'introdueix sempre en majúscules i abreviat. Per exemple, agost s'escriu "AG." i maig "MAIG". Figma: targetes_agenda_especifiques.
- **Dates recurrents:** s'utilitza el camp pels números per indicar el dia de la setmana o del mes i el camp pel mes per indicar la recurrència (mensual, setmanal...). Figma: targetes_agenda_recurrents.

### Tràmit
La variant per a tràmits s'adapta al contingut de la targeta: si un tràmit té un títol molt extens, la targeta s'adapta per no tallar el text. Les targetes de tràmits dins d'una mateixa fila s'adapten a la de contingut més extens. Figma: targetes_agenda_tramit. Aquesta adaptació s'ha de fer manualment (disseny) modificant l'alçada de la targeta de "hug" a "fill" i el mateix per al frame "Info" que conté el títol.

### Adaptació responsiva
La font mostra com es visualitzen les diferents tipologies de targetes en els diferents punts de tall (Figma: adaptacio_responsiva_navegacio_simple, adaptacio_responsiva_destacada, adaptacio_responsiva_navegacio_avançada, adaptacio_responsiva_informacio). Vegeu també Mides i espaiats.

### Teclat i focus
Vegeu Accessibilitat (taula de tecles). Estats d'interacció: Default, Hover, Focus, Pressed.

## Contingut i microcopy
- Compte de xarxa social: s'escriu com a (@elteucompte).
- Classificació d'escriptura segons cada xarxa social. Es recomana consultar les dades obertes de la Generalitat de Catalunya per identificar el nom oficial de cada xarxa social usada per les pàgines institucionals: https://analisi.transparenciacatalunya.cat/Sector-P-blic/Directori-de-xarxes-socials-de-la-Generalitat-de-C/ng4r-dc32/about_data

| Xarxa social | Exemple |
|---|---|
| Whatsapp | Generalitat de Catalunya |
| Instagram | @agriculturacat |
| Linkedin | /culturacat |
| x | /icec_cat |
| Youtube | @loteriesdecatalunya3742 |
| Tiktok | @mossoscat |
| Facebook | @emergenciescat |
| Blog | notesdeseguretat.blog.gencat.cat |
| Bulletí | /bulleti_govern |

- Textos d'exemple: "El títol de la targeta", "La descripció de la targeta que és opcional i varia segons la tipologia.", "Espai o recinte", "Localitat".

## Bones pràctiques
### Proporció de les imatges
- **FER:** Utilitza una proporció de 16:9.
- **NO FER:** Evita imatges allargades verticalment, ja que es tallarà part del contingut que podria ser rellevant.

### Títols
- **FER:** Utilitza textos concisos per evitar que es trunquin.
- **NO FER:** No utilitzis textos massa llargs que es puguin truncar.

### Imatges i icones
- **FER:** Fes servir elements visuals que aportin valor i reforcin el contingut.
- **NO FER:** No afegeixis elements visuals innecessaris o que distreguin del missatge principal.

### Icones de xarxes socials
- **FER:** Fes servir les icones disponibles a la llibreria.
- **NO FER:** Utilitza les icones corresponents a les xarxes socials que trobaràs a la llibreria. En cas de no trobar-ne l'adequada, utilitza el mateix estil visual.

### Espaiat entre targetes
- **FER:** Col·loca les targetes d'una manera proporcionada relacionada amb l'espai disponible de la quadrícula.
- **NO FER:** No col·loquis les targetes sense utilitzar una quadrícula.
- **NO FER:** No col·loquis totes les xarxes socials en una sola fila. Intenta distribuir les targetes de manera equilibrada.
- **NO FER:** No facis servir diferents mides quan es tracta de col·locar targetes en una mateixa secció.

### Compte de xarxes socials
- **FER:** Escriu el compte de la xarxa social corresponent de la següent manera (@elteucompte).
- **NO FER:** No cal que escriguis tota la URL de la xarxa social com a títol de la targeta.

### Múltiples targetes en una secció
- **FER:** Mantingues les targetes d'un mateix conjunt o secció amb una sola variant consistent.
- **NO FER:** No barregis targetes amb diferents variants dins d'un mateix conjunt o secció.

### Enllaços
- **FER:** Utilitza enllaços curts i clars perquè es mostrin correctament sense ser tallats.
- **NO FER:** No facis servir enllaços massa llargs, ja que es tallaran i apareixeran amb punts suspensius. Tria la composició que millor s'adapti per garantir una visualització clara i completa.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG):
- **Contrast mínim (AA)** (1.4.3): els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA)** (1.4.4): excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA)** (1.4.11): els elements gràfics presenten un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A)** (2.1.1): tota la funcionalitat del contingut es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Focus visible (AA)** (2.4.7): la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

### Navegació per teclat

| Tecla | Acció |
|---|---|
| Tabulació | Navegació al següent element interactiu |
| Shift + Tabulació | Navegació a l'anterior element interactiu |
| Fletxes | Mou el focus dins de la targeta als elements accessibles dins de la targeta. Si s'inclou un botó a les targetes, aquest hauria de rebre el focus primer. |
| Enter | Activar element interactiu |

## Implementació (component web)

### `<card-highlight-component>` (targeta destacada)
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat (lloc) |
|---|---|---|---|---|---|
| `cardButtonText` | `card-button-text` | Text que es mostra dins de l'enllaç / text del botó. | string | `undefined` | Opcional |
| `description` | `description` | Descripció de la targeta. | string | `undefined` | Opcional |
| `titleCard` | `title-card` | Títol de la targeta. (El lloc escriu el nom de la propietat com `title-card`.) | string | `undefined` | Opcional |

**Esdeveniments** (el PDF indica "sense esdeveniments declarats"; el lloc llista els del subcomponent)

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `blurButton` | Es llança cada cop que es treu el focus en un botó. | - | `button-component` |
| `focusButton` | Es llança cada cop que es fa focus en un botó. | - | `button-component` |
| `handlerClick` | Esdeveniment llançat en fer clic sobre algun dels botons | `id` | `button-component` |

**Depèn de:** `button-component` ([Botons](component-botons.md)).

```html
<!-- /index.html -->
<card-highlight-component
      title-card="El títol de la targeta"
      description="La descripció de la targeta que és opcional i varia segons la tipologia."
      card-button-text="Button"
></card-highlight-component>
```

Exemple d'instància (PDF):

```html
<card-highlight-component
card-button-text="texto-ejemplo"
description="texto-ejemplo"
title-card="texto-ejemplo"
></card-highlight-component>
```

### `<card-info-component>` (targeta d'informació)
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat (lloc) |
|---|---|---|---|---|---|
| `cardDescription` | `card-description` | Descripció de la targeta. | string | `` (buit) | Opcional |
| `cardTitle` | `card-title` | Títol de la targeta. | string | `` (buit) | Opcional |
| `customId` | `custom-id` | ID del component (identificador HTML personalitzat). | string | `undefined` | Obligatori |
| `headerUrlImage` | `header-url-image` | Imatge principal de fons de la capçalera (URL de la imatge). | string | `` (buit) | Opcional |
| `logoImg` | `logo-img` | Logo de la marca (URL de la imatge). | string | `` (buit) | Opcional |
| `logoText` | `logo-text` | Text de la marca. | string | `` (buit) | Opcional |
| `mainLabel` | `main-label` | Etiqueta principal de la targeta. | string (array) | `` (buit) | Opcional |
| `metadata` | `metadata` | Informació addicional de la targeta. Accepta objecte o string JSON. | string (array) | `` (buit) | Opcional |
| `mode` | `mode` | Determina on s'obrirà l'enllaç. Opcions: `external`, `internal`. | string | `internal` | Opcional |
| `textTag` | `text-tag` | Llista d'etiquetes. (El PDF descriu `textTag` com "nivell de l'encapçalament HTML"; descripció aparentment errònia.) | string (array) | `` (buit) | Opcional |
| `tagArray` | - (el PDF mostra `-/`) | Array d'etiquetes. Accepta array d'objectes o string JSON. Tipus: `{ type: string; text: string; color: string; }` | array d'objectes | `[]` | no documentat al lloc |

**Props que accepten JSON**

`mainLabel` (array de strings): text de l'etiqueta principal. El component només mostra els dos primers elements. Propietat `-`, opcional, string.

`metadata`:

| Propietat | Descripció | Obligatori | Tipus |
|---|---|---|---|
| `icon` | Classe de la icona Bootstrap mostrada al costat del text. | Obligatori | String |
| `text` | Text de la metadada. | Obligatori | String |

`textTag` (array de strings): text de l'etiqueta del peu. El component només mostra els dos primers elements.

**Variants**

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `mode` | `internal` `external` | `internal` |

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `idEmit` | En prémer una targeta s'emet un esdeveniment amb l'ID del component (`CustomEvent<string>`). | ID del component | `card-info-component` |

**Depèn de:** `tag-component` ([Etiquetes](component-etiquetes.md)).

```html
<!-- /index.html -->
<card-info-component
      custom-id="card_info"
      header-url-image="https://oxygenworkspace.com/wp-content/uploads/2021/06/Despacho-04-1.jpg"
      main-label='["mainLabel"]'
      logo-img="https://cdn-icons-png.freepik.com/256/16000/16000950.png?semt=ais_hybrid"
      logo-text="Centro de estudios"
      card-title="Curabitur eu urna eget eros"
      card-description="Sed vel arcu et quam egestas luctus ut id enim. Donec urna turpis, ultrices ut finibus non, molestie ut libero. Cras faucibus nisl tortor, ut faucibus justo faucibus ornare. Nulla ac elementum leo."
      text-tag='["Etiqueta 1", "Etiqueta 2","Etiqueta 3","Etiqueta 4","Etiqueta 5","Etiqueta 6","Etiqueta 7"]'
      metadata='[{"icon": "bi-geo-alt", "text": "Facultat d´Educació"},{"icon": "bi-check2-circle", "text": "Presencial"},{"icon": "bi-database", "text": "240 ECTS"}]'
      mode="internal">
</card-info-component>
```

Exemple d'instància (PDF):

```html
<card-info-component
card-description=''
card-title=''
custom-id="texto-ejemplo"
header-url-image=''
logo-img=''
logo-text=''
main-label=''
metadata=''
mode='internal'
-/=[]
text-tag=''
></card-info-component>
```

### `<card-info-evolutive-component>` (targeta d'informació, evolutiu: agenda, butlletí, tràmit)
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat (lloc) |
|---|---|---|---|---|---|
| `cardDescription` | `card-description` | Descripció de la targeta. Només per al tipus butlletí. | string | `undefined` | Opcional |
| `cardTitle` | `card-title` | Títol de la targeta. | string | `undefined` | Obligatori |
| `customId` | `custom-id` | ID del component. | string | `undefined` | Obligatori |
| `dayDate` | `day-date` | Primera data del rang o única data pel mode individual (dia del mes). Només per a targetes tipus agenda. | string | `undefined` | Obligatori |
| `endDayDate` | `end-day-date` | Segona data del rang (dia final). Només tipus agenda. | string | `undefined` | Opcional |
| `endMonthDate` | `end-month-date` | Segon mes del rang. Només tipus agenda. | string | `undefined` | Opcional |
| `headerTag` | `header-tag` | Array amb el text i el color de l'etiqueta superior. Només per a targetes de tipus butlletí i tràmit. (El PDF diu "nivell de l'encapçalament HTML"; descripció aparentment errònia.) | string (object) | `undefined` | Opcional |
| `imageCard` | `image-card` | Imatge de la targeta (URL). Només tipus agenda. | string | `undefined` | Obligatori |
| `location` | `location` | Espai o recinte on es durà a terme l'esdeveniment. Només tipus agenda. | string | `undefined` | Obligatori |
| `locationDescription` | `location-description` | Ciutat o localitat on es durà a terme l'esdeveniment. Només tipus agenda. | string | `undefined` | Opcional |
| `modeDate` | `mode-date` | Mode per a l'etiqueta de data (`single` o `range`). Només tipus agenda. | string | `undefined` | Obligatori |
| `modeLink` | `mode-link` | Determina on s'obrirà l'enllaç. Opcions: `external`, `internal`. | string | `internal` | Obligatori |
| `monthDate` | `month-date` | Primer mes del rang o únic mes pel mode individual. Només tipus agenda. | string | `undefined` | Obligatori |
| `textTags` | `text-tags` | Text de les etiquetes inferiors. Només tipus agenda i butlletí. | string (array) | `undefined` | Opcional |
| `type` | `type` | Tipus de targeta. Opcions: `agenda`, `newsletter`, `procedure`. | string | `undefined` | Obligatori |

**Props que accepten JSON**

`headerTag`:

| Propietat | Descripció | Atribut | Obligatori | Tipus |
|---|---|---|---|---|
| `color` | Color de l'etiqueta. | `color` | Obligatori | String |
| `text` | Text de l'etiqueta. | `text` | Obligatori | String |

`textTags` (array de strings): text de l'etiqueta del peu. El component només mostra els dos primers elements.

**Variants**

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `modeLink` | `internal` `external` | `internal` |
| `modeDate` | `single` `range` | - |
| `type` | `agenda` `newsletter` `procedure` | - |

**Atributs de cada tipus de targeta**

| Targeta d'agenda | Targeta de butlletí | Targeta de tràmit |
|---|---|---|
| `customId` | `customId` | `customId` |
| `type` | `type` | `type` |
| `cardTitle` | `cardTitle` | `cardTitle` |
| `location` | `cardDescription` | `link` |
| `locationDescription` | `textTags` | `textTags` |
| `modeLink` | `modeLink` | `modeLink` |
| `modeDate` | | |
| `dayDate` | | |
| `monthDate` | | |
| `endDayDate` | | |
| `endMonthDate` | | |

(`link` apareix a la columna de tràmit però no figura a la taula de propietats [a verificar].)

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `idEmit` | En prémer una targeta s'emet un esdeveniment amb l'ID del component (`CustomEvent<string>`). | ID del component | `card-info-evolutive-component` |

**Depèn de:** `tag-component` ([Etiquetes](component-etiquetes.md)).

```html
<!-- /index.html -->
<card-info-evolutive-component
      custom-id="card_info_evolutive"
      type="agenda"
      image-card="https://oxygenworkspace.com/wp-content/uploads/2021/06/Despacho-04-1.jpg"
      header-tag='[{"text":"Etiquete","color":"color-success"}]'
      location="Espai o recinte"
      location-description="Localitat"
      card-title="El títol de la targeta"
      card-description="La descripció de la targeta que és opcional i varia segons la tipologia."
      text-tags='["Etiqueta"]'
      mode-link="internal"
      mode-date="single"
      day-date="00"
      month-date="MES"
      end-day-date="00"
      end-month-date="MES">
</card-info-evolutive-component>
```

Exemple d'instància (PDF):

```html
<card-info-evolutive-component
card-description="texto-ejemplo"
card-title="texto-ejemplo"
custom-id="texto-ejemplo"
day-date="texto-ejemplo"
end-day-date="texto-ejemplo"
end-month-date="texto-ejemplo"
header-tag="texto-ejemplo"
image-card="texto-ejemplo"
location="texto-ejemplo"
location-description="texto-ejemplo"
mode-date="range"
mode-link='internal'
month-date="texto-ejemplo"
text-tags="texto-ejemplo"
type="agenda"
></card-info-evolutive-component>
```

### `<card-navigation-basic-component>` (targeta de navegació, tipus bàsic)
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat (lloc) |
|---|---|---|---|---|---|
| `cardIcon` | `card-icon` | Nom de la icona de Bootstrap a mostrar (usa les icones de la [biblioteca d'icones de Bootstrap](https://icons.getbootstrap.com/)). També és possible introduir una URL amb una il·lustració o una ruta relativa o absoluta cap a una il·lustració. | string | `undefined` | Opcional |
| `customId` | `custom-id` | ID del component. | string | `undefined` | Obligatori |
| `description` | `description` | Descripció de la targeta. | string | `undefined` | Opcional |
| `mode` | `mode` | Determina on s'obrirà l'enllaç. Opcions: `external`, `internal`. | string | `internal` | Obligatori |
| `sizeCardIcon` | `size-card-icon` | Mida de la icona principal del component. Opcions: `medium`, `small`. | string | `small` | Opcional |
| `titleCard` | `title-card` | Títol de la targeta. | string | `undefined` | Obligatori |

**Variants**

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `mode` | `internal` `external` | `internal` |
| `sizeCardIcon` | `small` `medium` | `small` |

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `clickCard` | En prémer una targeta s'emet un esdeveniment amb l'ID del component (`CustomEvent<string>`). | ID del component | `card-navigation-basic-component` |

**Utilitzat per:** `card-social-component`, `header-public-component` ([Capçalera web pública](component-capcalera-web-publica.md)), `horizontal-menu-component` ([Menú horitzontal](component-menu-horitzontal.md)), `support-banner-component` ([Bàner d'atenció](component-baner-d-atencio.md)).

```html
<!-- /index.html -->
<card-navigation-basic-component
  card-icon="bi-envelope"
  title-card="El títol de la targeta La descripció de la targeta que és opcional i varia segons la tipologia"
  description="La descripció de la targeta que és opcional i varia segons la tipologia.La descripció de la targeta que és opcional i varia segons la tipologia"
  mode="internal"
  custom-id="card-navigation-basic-id"
  size-card-icon="medium"
></card-navigation-basic-component>
```

Exemple d'instància (PDF):

```html
<card-navigation-basic-component
card-icon="texto-ejemplo"
custom-id="texto-ejemplo"
description="texto-ejemplo"
mode='internal'
size-card-icon='small'
title-card="texto-ejemplo"
></card-navigation-basic-component>
```

### `<card-navigation-component>` (targeta de navegació, tipus avançat)
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat (lloc) |
|---|---|---|---|---|---|
| `cardButtonIcon` | `card-button-icon` | Elecció d'icona d'enllaç intern o extern (classe Bootstrap Icons del botó). Opcions: `external`, `internal`. | string | `internal` | Opcional |
| `cardButtonText` | `card-button-text` | Text del botó de la targeta. | string | `undefined` | Opcional |
| `cardImage` | `card-image` | Imatge de la targeta (URL). | string | `undefined` | Opcional |
| `description` | `description` | Descripció de la targeta. | string | `undefined` | Opcional |
| `goActionListLinks` | `go-action-list-links` | Llista d'enllaços en format JSON que es mostraran a la targeta. Accepta array d'objectes o string JSON. | string (array) | `undefined` | Obligatori |
| `titleCard` | `title-card` | Títol de la targeta. | string | `undefined` | Obligatori |

**Props que accepten JSON: `goActionListLinks`**

| Propietat | Descripció | Atribut | Obligatori | Tipus |
|---|---|---|---|---|
| `customId` | Identificador personalitzat de l'enllaç | `custom-id` | Opcional | String |
| `mode` | Tipus d'enllaç: `internal` o `external` | `mode` | Obligatori | String |
| `text` | Text de l'enllaç | `text` | Obligatori | String |

**Variants**

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `cardButtonIcon` | `external` `internal` | `internal` |

**Esdeveniments** (el PDF indica "sense esdeveniments declarats"; el lloc llista els dels subcomponents)

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `blurButton` | Es llança cada cop que es treu el focus en un botó. | - | `button-component` |
| `focusButton` | Es llança cada cop que es fa focus en un botó. | - | `button-component` |
| `handlerClick` | Esdeveniment llançat en fer clic sobre algun dels botons. | `id` | `button-component` |
| `blurLink` | Es llança cada cop que es treu el focus en un enllaç. | - | `link-component` |
| `focusLink` | Es llança cada cop que es fa focus en un enllaç. | - | `link-component` |
| `linkEmit` | Esdeveniment llançat en fer clic sobre el link. | `id` | `link-component` |

**Depèn de:** `button-component` ([Botons](component-botons.md)), `link-component` ([Enllaços](component-enllacos.md)).

```html
<!-- /index.html -->
<card-navigation-component
  card-image="https://cdn-icons-png.flaticon.com/512/3112/3112931.png"
  title-card="El títol de la targeta"
  description="La descripció de la targeta que és opcional i varia segons la tipologia."
  go-action-list-links='[
    { "text": "Enllaç 1 linia", "mode": "internal", "customId": "link-1" },
    { "text": "Enllaç 2 linia", "mode": "internal", "customId": "link-2" },
    { "text": "Enllaç 3 linia", "mode": "internal", "customId": "link-3" }
    ]'
  card-button-text="Enllaç categoria"
  card-button-icon="internal"
>
</card-navigation-component>
```

Exemple d'instància (PDF):

```html
<card-navigation-component
card-button-icon='internal'
card-button-text="texto-ejemplo"
card-image="texto-ejemplo"
description="texto-ejemplo"
go-action-list-links="texto-ejemplo"
title-card="texto-ejemplo"
></card-navigation-component>
```

### `<card-social-component>` (targeta de xarxes socials)
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat (lloc) |
|---|---|---|---|---|---|
| `customId` | `custom-id` | ID del component. | string | `undefined` | Obligatori |
| `goActionLinkSocial` | `go-action-link-social` | URL de destinació de l'enllaç. | string | `undefined` | Obligatori |
| `social` | `social` | Nom de la xarxa social. Opcions: `Blog`, `Bulletins`, `Facebook`, `Instagram`, `Linkedin`, `Tiktok`, `Youtube`, `x`. | string | `undefined` | Obligatori |
| `textSocial` | `text-social` | Títol de la targeta (text visible). | string | `undefined` | Obligatori |

**Variants**

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `social` | `x` `Facebook` `Instagram` `Youtube` `Blog` `Bulletins` `Linkedin` `Tiktok` | - |

**Esdeveniments** (el PDF indica "sense esdeveniments declarats"; el lloc en llista un)

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `clickCard` | En prémer una targeta s'emet un esdeveniment amb l'ID del component. | ID del component | `card-navigation-basic-component` |

**Depèn de:** `card-navigation-basic-component`.

```html
<!-- /index.html -->
<card-social-component
  custom-id="custom-id"
  text-social="xarxes socials"
  social="Youtube"
  go-action-link-social="#"
  >
  </card-social-component>
```

Exemple d'instància (PDF):

```html
<card-social-component
custom-id="texto-ejemplo"
go-action-link-social="texto-ejemplo"
social="Blog"
text-social="texto-ejemplo"
></card-social-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 10.0.0 | 12.1.2 | 5 octubre, 2026 | Desenvolupament: targeta destacada: s'ajusta l'amplada del component quan es troba dins d'un contenidor |
| 10.0.0 | 12.1.1 | 11 setembre, 2026 | Desenvolupament: targeta de xarxes socials: les rutes relatives a absolutes s'han corregit |
| 10.0.0 | 12.0.0 | 10 juliol, 2026 | Desenvolupament: targeta de navegació avançat: s'elimina la property cardHeightFixed; targeta d'informació: s'utilitza el token correcte per al color dels textos; targeta d'informació evolutiu: s'utilitza el token correcte per al color de text del títol; targeta de navegació bàsic: s'utilitza el token correcte per al color de la icona |
| 10.0.0 | 10.1.0 | 29 maig, 2026 | Desenvolupament: ajustos de disseny en targeta info evolutiva |
| 10.0.0 | 10.0.0 | 8 maig, 2026 | Desenvolupament: s'ajusta min width i logotip a la targeta de navegació bàsica |
| 10.0.0 | 9.2.0 | 17 abril, 2026 | Disseny: es redueix l'amplada mínima de targetes de navegació a 296 px. S'incorpora la variant de logotip a les targetes de navegació. |
| 9.1.0 | 9.2.0 | 20 març, 2026 | Disseny: targeta de navegació: es col·loca a layout left right el focus de la card de navegació sense descripció. |
| 8.5.0 | 9.2.0 | 27 febrer, 2026 | Desenvolupament: es crea la propietat customId en targeta de navegació tipus avançat. A la targeta de navegació bàsica es crea la propietat sizeCardIcon que permet seleccionar la mida de la icona principal del component. |
| 8.5.0 | 9.1.0 | 6 febrer, 2026 | Desenvolupament: s'elimina text truncat i alçades fixes a totes les targetes |
| 8.5.0 | 9.0.0 | 20 gener, 2026 | Disseny: s'eliminen tots els truncats i alçades mínimes dels texts de les targetes. A la targeta destacada se li afegeix al contenidor de títol i text una amplada mínima de 252 px en la versió Card size = ≥480. S'arregla l'estat focus de 3 targetes. |
| 8.4.0 | 9.0.0 | 12 gener, 2026 | Desenvolupament: a card-navigation es canvia la mida de tipografia del títol de la targeta en breakpoint small |
| 8.4.0 | 8.0.0 | 5 desembre, 2025 | Disseny: es modifica l'estil de text aplicat al títol de la targeta de navegació en el punt de tall small. |
| 8.2.0 | 8.0.0 | 14 novembre, 2025 | Desenvolupament: resolució de problemes |
| 8.2.0 | 6.2.1 | 27 octubre, 2025 | Disseny: s'actualitzen els estils del títol de la targeta destacada, s'aplica un estil amb mida inferior. Es fa una revisió dels estils tipogràfics de la targeta d'informació. |
| 8.1.0 | 6.2.1 | 6 octubre, 2025 | Disseny: s'afegeix estat hover i pressed a l'asset Card link_small per evitar desvinculacions de color. S'ajusta correctament la distància del focus a la targeta de navegació. Desenvolupament: nova propietat afegida o eliminada |
| 8.0.0 | 6.1.0 | 12 setembre, 2025 | Disseny: es modifica l'estil tipogràfic Label per Body al text de les targetes. Desenvolupament: resolució de problemes |
| 6.0.0 | 6.0.0 | 8 juliol, 2025 | Disseny: s'ajusta l'alineació d'etiquetes de la targeta informativa. |
| 5.0.0 | 6.0.0 | 3 juliol, 2025 | Desenvolupament: resolució de problemes |
| 5.0.0 | 5.0.0 | 10 juny, 2025 | Disseny: s'aplica l'elevació 1 a totes les targetes. |
| 4.0.0 | 5.0.0 | 9 juny, 2025 | Desenvolupament de card info evolutive |
| 4.0.0 | 4.0.1 | 19 maig, 2025 | Desenvolupament: resolució de problemes |
| 2.4.0 | 3.0.0 | 28 abril, 2025 | Desenvolupament: resolució de problemes |
| 2.4.0 | 2.1.0 | 31 març, 2025 | Desenvolupament: errors |
| 2.4.0 | 2.0.0 | 10 març, 2025 | Disseny: s'iguala l'estil de la imatge de la targeta informativa perquè sigui igual al visor de notícies (sense marges laterals). |
| 2.3.0 | 1.1.0 | 17 febrer, 2025 | Desenvolupament del component. |
| 2.3.0 | No aplica | 31 gener, 2025 | Disseny: optimització de la construcció de les targetes. |
| 2.2.0 | No aplica | 20 gener, 2025 | Disseny i documentació del component. |

## Vegeu també
- [Botons](component-botons.md): per a realitzar accions.
- [Enllaços](component-enllacos.md): per facilitar la navegació entre parts del contingut o funcionalitats.
- [Etiquetes](component-etiquetes.md): per mostrar l'estat d'un element, les propietats clau o les categories.
- [Il·lustracions](fonaments-illustracions.md)
- [Imatge](fonaments-imatge.md)
- [Punt de tall i quadrícules](fonaments-punt-de-tall-i-quadricules.md)
