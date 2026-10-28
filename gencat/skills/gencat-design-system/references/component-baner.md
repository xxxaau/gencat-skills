# Bàner (Banner)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/50d7d2 · Web component: `<banner-component>` (paquet core) · Font actualitzada el 2026-10-07 · Extret el 2026-10-28

## Què és i quan usar-lo
El component bàner és un element visual que s'utilitza per destacar informació important o promocional.

Serveix per **destacar informació rellevant**, com ara campanyes promocionals o novetats. Conté una imatge, un títol, un text descriptiu i un botó.

Quan s'utilitza:
- Per comunicar un missatge destacat.
- Per guiar l'usuari cap a una acció específica.

## Quan NO usar-lo / alternatives
- Quan la informació no és essencial o no requereix una visibilitat immediata.
- Per a missatges extensos que requereixen molta lectura.
- Quan es poden utilitzar altres components més adequats, com targetes ([Targetes](component-targetes.md)) o avisos ([Avisos](component-avisos.md)).

## Anatomia
Figma: Banner [Breakpoint = Extra Large Column Fix]. Elements: imatge, títol, text descriptiu (subtítol) i botó.

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Small / Medium / Large / Extra Large Column Variable / Extra Large Column Fix | Extra Large Column Fix |
| Show subtitle | True / False | True |

## Comportament i interacció
### Adaptació responsiva
El bàner s'adaptarà automàticament a l'amplada de la pantalla. La font mostra com es visualitza en els diferents punts de tall (Figma: Breakpoints_ExtraLarge, Breakpoints_Large, Breakpoints_Medium, Breakpoints_Small).

## Bones pràctiques

**Claredat i brevetat**
- **FER:** Sigues concís i directe en el missatge.
- **NO FER:** No utilitzis missatges massa llargs o complicats.

**Ús únic per pàgina**
- **FER:** Utilitza només un bàner per pàgina.
- **NO FER:** No utilitzis més d'un bàner simultàniament.

**Combinació amb altres seccions**
- **FER:** Evita que el fons del bàner tingui el mateix color que el contingut immediatament anterior o posterior.
- **NO FER:** No utilitzis seccions de fons gris en contacte directe amb el fons vermell del bàner.
- **NO FER:** Si el punt anterior no es pot evitar, afegeix un espaiat clar entre els dos elements per millorar la visibilitat.

## Accessibilitat

### Pautes d'accessibilitat del contingut web (WCAG)
- **Ús del color (A):** el color no es fa servir com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a indicar el pas, percentatge, etc. en el que es troba el procés o tasca s'utilitza informació textual a part de gràfica. [1.4.1 Ús del color - CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. [1.4.3 Contrast mínim - CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA):** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [1.4.4 Canvia la mida del text - CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA):** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [1.4.11 Contrast d'elements no textuals - CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A):** tota la funcionalitat del contingut (navegar pels enllaços) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [2.1.1 Teclat - CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Focus visible (AA):** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [2.4.7 Focus visible - CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

### Navegació per teclat

| Tecla | Acció |
|---|---|
| Tabulació | Navegació al següent element interactiu |
| Enter | Activar element interactiu |

## Implementació (component web)

### `<banner-component>`

Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatori (lloc) |
|---|---|---|---|---|---|
| `bannerDescription` | `banner-description` | Descripció del bàner | string | `undefined` | Opcional |
| `bannerImage` | `banner-image` | Imatge principal del bàner (URL de la imatge) | string | `undefined` | Obligatori |
| `bannerTitle` | `banner-title` | Títol del bàner | string | `undefined` | Obligatori |
| `buttonText` | `button-text` | Text que conté el botó | string | `undefined` | Obligatori |

**Esdeveniments (lloc)**

| Esdeveniment | Descripció | Paràmetre | Origen |
|---|---|---|---|
| `handlerClick` | Esdeveniment llançat en seleccionar el botó del bàner | `id` | `button-component` |

[discrepància: el lloc documenta `handlerClick` (heretat de `button-component`); el PDF diu «Sin eventos declarados» per a `banner-component`]

**Depèn de:** `button-component` ([Botons](component-botons.md)).

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<banner-component 
  banner-title="Necessites ajuda?"
  banner-description="Contacta amb nosaltres i t'ajudarem a resoldre els teus dubtes. Contacta amb nosaltres i t'ajudarem"
  banner-image="/assets/photos/hero_banner.png"
  button-text="Informa´t aquí"
></banner-component>
```

**Exemple d'instància (PDF)**

```html
<banner-component
banner-description="texto-ejemplo"
banner-image="texto-ejemplo"
banner-title="texto-ejemplo"
button-text="texto-ejemplo"
></banner-component>
```

## Claus de text (internacionalització)
Vegeu les [claus](dev-referencia-de-claus-disponibles.md) (`banner`).

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.0.0 | 11.0.0 | 19 juny, 2026 | Desenvolupament: es canvia el nom de la variable del background. |
| 12.0.0 | 10.1.0 | 29 maig, 2026 | Disseny: s'aplica el token específic pels fons dels components per adaptació a altres modes de color. Desenvolupament: es corregeixen els talls que es produïen en augmentar la mida del text amb el navegador. |
| 11.0.0 | 10.0.0 | 8 maig, 2026 | Disseny: reset del heading block del bàner d'atenció. Desenvolupament: es divideix banner-component en support-banner-component i banner-component. S'ajusta l'amplada mínima en mòbil. |
| 10.0.0 | 9.1.0 | 17 abril, 2026 | Disseny: amplada mínima del punt Small a 320 px. |
| 8.6.0 | 9.1.0 | 9 febrer, 2026 | Disseny: modificació de l'alçada del fons en funció del text. |
| 8.5.0 | 9.1.0 | 6 febrer, 2026 | Desenvolupament: s'elimina text truncat, i s'ajusten algunes alçades mínimes. |
| 8.5.0 | 8.5.0 | 20 gener, 2026 | Disseny: s'eliminen truncats de títols i descripcions. El frame content del bàner es posa amb una alçada en hug i una alçada mínima de 456 px per als punts de tall extra large column fixed, extra large column variable i large. El contingut de les targetes del bàner de suport es posen amb una alçada en hug. |
| 8.2.0 | 8.5.0 | 5 desembre, 2025 | Desenvolupament: resolució de problemes menors. |
| 8.2.0 | 6.2.1 | 27 octubre, 2025 | Disseny: revisió d'estils tipogràfics. |
| 5.0.0 | 6.2.1 | 3 octubre, 2025 | Desenvolupament: nova propietat afegida o eliminada. |
| 5.0.0 | 6.0.0 | 3 juliol, 2025 | Desenvolupament: resolució de problemes. |
| 5.0.0 | 0.1.1 | 10 juny, 2025 | Disseny: disseny del component Peça d'atenció. Disseny del component Bàner. |
| 1.0.0 | 0.0.3 | 1 novembre, 2024 | Disseny, desenvolupament i documentació del component. |

## Vegeu també
- [Botons](component-botons.md): per a realitzar accions.
- [Imatge](fonaments-imatge.md)
- [Bàner d'atenció](component-baner-d-atencio.md)
