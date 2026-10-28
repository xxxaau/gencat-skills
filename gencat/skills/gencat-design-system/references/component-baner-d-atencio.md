# Bàner d'atenció (Support banner)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/747869 · Web component: `<support-banner-component>` (paquet core) · Font actualitzada el 2026-07-10 · Extret el 2026-10-28

## Què és i quan usar-lo
Destacat que busca captar la mirada de l'usuari i proporcionar informació de contacte de manera ràpida i accessible.

És un element destacat que **busca captar la mirada de l'usuari** i proporcionar informació de contacte de manera ràpida i accessible. Aquest tipus de peça està dissenyada per guiar l'usuari cap a una acció específica, com ara contactar amb el servei d'atenció a l'usuari, fer una videotrucada, trobar informació de suport o localitzar una oficina propera.

S'utilitza quan es vol captar ràpidament l'atenció de l'usuari sobre una informació rellevant, o **guiar l'usuari cap a una acció específica**, com ara:
- Contactar amb el servei d'atenció ciutadana.
- Fer una videotrucada amb l'equip de suport.
- Accedir a informació de suport o preguntes freqüents.
- Localitzar una oficina o un servei en concret.

Característiques principals:
- **Es destaca visualment** per captar ràpidament l'atenció del ciutadà sense ser intrusiva. S'aconsegueix aquest objectiu utilitzant el color d'accent com a element clau.
- **Conté un missatge clar i directe:** la informació essencial es troba en una frase curta i entenedora, evitant tecnicismes o textos massa llargs.
- **És clar, accessible, útil i visualment atractiu**, i evita saturar la pàgina i generar distraccions.

## Quan NO usar-lo / alternatives
No s'utilitza en aplicacions de gestió interna: és una informació que va encarada a la població. Tampoc s'utilitza en pàgines interiors, com ara de detall o d'enllaços, i sempre es fa servir a la pàgina principal.

## Anatomia
Figma: Support Banner [Breakpoint = Extra Large Column Fix]. Compost per un títol, un subtítol i d'1 a 4 targetes de contingut disposades en una estructura flexible. Cada targeta inclou una icona, un text breu i una icona.

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Extra Large Column fix / Extra Large Column variable / Large / Medium / Small | Extra Large Column fix |
| Card number | 4 / 3 / 2 / 1 | 4 |
| Title | Text | --- |
| Description | Text | --- |

## Mides i espaiats
Per a dispositius grans, el bàner d'atenció s'adapta a les mides i punts de tall *Extra-Large Column fix*, *Extra-Large Column variable* i *Large*, assegurant una distribució equilibrada de les targetes en una o dues files.

En dispositius petits com tauletes i mòbils, la peça es reorganitza en una disposició vertical, on les targetes de contingut s'apilen per garantir una millor llegibilitat i accessibilitat tàctil.

## Comportament i interacció
Aquest bàner està dissenyat perquè l'usuari accedeixi ràpidament a la informació d'ajuda que necessita amb un sol clic. Cada targeta de contingut és interactiva i funciona com a enllaç que porta l'usuari a cada pàgina d'atenció.

### Adaptació responsiva
El component s'adapta en diferents punts de tall: extraLarge, Large, Medium, Small (la font mostra una captura de Figma per a cadascun).

## Bones pràctiques

### Il·lustracions correctes
- **FER:** Utilitza les il·lustracions representatives que s'han pensat per aquest component.
- **NO FER:** No utilitzis il·lustracions abstractes o decoratives que no siguin les icones representatives creades per aquest component.

### Combinació amb altres bàners
- **FER:** Intenta que els dos bàners estiguin separats, així hi ha prou contrast per diferenciar les seccions.
- **NO FER:** No utilitzis els dos bàners junts, sense un espaiat o un altre element que els separi.

### Contingut de les targetes
- **FER:** Fes servir les targetes que et convinguin (des d'1 fins a 4).
- **NO FER:** No utilitzis dos o més bàners per mostrar diferents targetes amb informació de contacte.

### Combinacions de colors
- **FER:** Si el bàner d'atenció queda per sota d'una secció amb fons gris, utilitza un espaiat per diferenciar les seccions.
- **NO FER:** Evita posar el bàner d'atenció a sota d'una secció amb fons gris i, si no és possible, utilitza espaiat per separar-les.

## Accessibilitat

### Pautes d'accessibilitat del contingut web (WCAG)
- **Ús del color (A), 1.4.1:** el color no es fa servir com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a indicar el pas, percentatge, etc. en què es troba el procés o tasca, s'utilitza informació textual a part de gràfica. [CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA), 1.4.3:** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA), 1.4.4:** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA), 1.4.11:** els elements gràfics presenten un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A), 2.1.1:** tota la funcionalitat del contingut (navegar pels enllaços) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Focus visible (AA), 2.4.7:** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

### Navegació per teclat

| Tecla | Acció |
|---|---|
| Tabulació | Navegació al següent element interactiu |
| Enter | Activar element interactiu |

## Implementació (component web)

### `<support-banner-component>`
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatori |
|---|---|---|---|---|---|
| `bannerDescription` | `banner-description` | Descripció del banner. | string | `undefined` | Opcional |
| `bannerTitle` | `banner-title` | Títol del banner. | string | `undefined` | Obligatori |
| `cardsData` | `cards-data` | Array amb les propietats de `card-navigation-basic-component`, en format JSON, que conté la informació de les targetes que es mostraran. | `any[] \| string` (String (Array)) | --- | Obligatori |

**Esdeveniments**

[discrepància: el lloc documenta els esdeveniments següents; el PDF diu "Sin eventos declarados"]

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `clickCard` | Esdeveniment llançat en seleccionar una targeta del bàner d'atenció. | `id` | `card-navigation-basic-component` |
| `handlerClick` | Esdeveniment llançat en seleccionar el botó del bàner. | `id` | `button-component` |

**Depèn de:** `card-navigation-basic-component` (vegeu [Targetes](component-targetes.md)).

**Props que accepten JSON:** `cardsData` (`cards-data`): array d'objectes amb les propietats de `card-navigation-basic-component`. Camps usats a l'exemple: `cardIcon`, `titleCard`, `goActionLink`, `goActionLinkTarget`, `description`, `footerIcon`.

**Exemple d'ús**

```html
<!-- /index.html -->
<support-banner-component
  banner-title="Necessites ajuda?";
  banner-description="Contacta amb nosaltres i t'ajudarem a resoldre els teus dubtes. Contacta amb nosaltres i t'ajudarem";
  cards-data='[
    {
      "cardIcon": "/assets/illustrations/small/Cerca_oficina.svg",
      "titleCard": "Cerca una oficina",
      "goActionLink": "https://ejemplo1.com",
      "goActionLinkTarget": "_blank",
      "description": "",
      "footerIcon": "internal"
    },
    {
      "cardIcon": "/assets/illustrations/small/Truca.svg",
      "titleCard": "Truca`ns al 012",
      "goActionLink": "https://ejemplo1.com",
      "goActionLinkTarget": "_blank",
      "description": "",
      "footerIcon": "internal"
    },
    {
      "cardIcon": "/assets/illustrations/small/Videotrucada.svg",
      "titleCard": "Parlem per vodeotrucada",
      "goActionLink": "https://ejemplo1.com",
      "goActionLinkTarget": "_blank",
      "description": "",
      "footerIcon": "internal"
    },
    {
      "cardIcon": "/assets/illustrations/small/Formulari.svg",
      "titleCard": "Escriu-nos",
      "goActionLink": "https://ejemplo2.com",
      "goActionLinkTarget": "_blank",
      "description": "",
      "footerIcon": "internal"
    }
  ]''
 ></support-banner-component>
```

(L'exemple es transcriu tal com surt a la font, incloent-hi els punts i coma després d'atributs, la cometa final `]''` i els errors tipogràfics `Truca`ns` i `vodeotrucada`. [a verificar])

**Exemple d'instància (PDF)**

```html
<support-banner-component
  banner-description="texto-ejemplo"
  banner-title="texto-ejemplo"
  cards-data="texto-ejemplo"
></support-banner-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 4.0.0 | 12.0.0 | 10 juliol, 2026 | Desenvolupament: s'utilitza el token correcte per al color de text de títol i descripció. |
| 4.0.0 | 11.0.0 | 19 juny, 2026 | Desenvolupament: es canvia el nom de la variable del background. |
| 4.0.0 | 10.1.0 | 29 maig, 2026 | Desenvolupament: es corregeixen els talls que es produïen en augmentar la mida del text amb el navegador. |
| 4.0.0 | - | 30 abril, 2025 | Disseny i documentació del component. |

## Vegeu també
- [Enllaços](component-enllacos.md): per facilitar la navegació entre parts del contingut o funcionalitats.
- [Il·lustracions](fonaments-illustracions.md)
- [Targetes](component-targetes.md)
- [Bàner](component-baner.md)
