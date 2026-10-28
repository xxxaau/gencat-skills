# Divisor (Divider)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/5025f5 · Web component: `<divider-component>` (paquet core) · Font actualitzada el 2026-03-23 · Extret el 2026-10-28

## Què és i quan usar-lo
Element lineal decoratiu per separar grups de contingut.

Un divisor és un element lineal que realitza la funció visual de separar contingut o seccions dins d'una pàgina o entre elements de la interfície per tal de millorar l'organització i la llegibilitat del contingut.

Quan s'utilitza:
- **Separar seccions de contingut:** són útils per separar diferents temes o seccions, ajudant així els lectors a comprendre millor l'estructura del contingut. Aquesta tècnica facilita la lectura en dividir textos llargs en segments més manejables.
- **Formularis:** poden separar diferents seccions o grups de camps, com ara informació personal, detalls de contacte i preferències, fent que el procés d'ompliment sigui més clar i menys aclaparador per a l'usuari.
- **Delimitar elements en el peu de pàgina:** serveixen per a separar diferents àrees o categories d'enllaços, com seccions del lloc, xarxes socials i dades de contacte, oferint una navegació més ordenada i estèticament agradable.

## Anatomia
Figma: Divider [Background = Dark, Position = Horizontal].

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Background | Light / Dark | Light |
| Orientation | Horizontal / Vertical | Horizontal |

Variants Figma: Background = Light | Dark; Position (Orientation) = Horizontal | Vertical.

## Bones pràctiques

### Separar contingut
- **FER:** Utilitza'l per separar seccions de contingut a la pantalla.
- **NO FER:** No l'utilitzis per separar seccions dins d'una mateixa secció de contingut a la pantalla.

### Adaptació
- **FER:** Utilitza els divisors d'amplada completa per separar continguts o seccions.
- **NO FER:** No empris els divisors d'amplada completa per separar elements relacionats.
- **FER:** Usa els divisors adaptats a la composició de pàgina per a separar elements relacionats.
- **NO FER:** No usis els divisors adaptats a la composició de pàgina per separar continguts o seccions.

### Únic element de separació
- **FER:** Utilitza el divisor com a únic element que genera aquest efecte.
- **NO FER:** No utilitzis un altre element que generi el mateix efecte (imatges, fons, ombres) combinat amb el divisor.

## Accessibilitat
Els divisors són elements decoratius i, per tant, queden exclosos dels criteris d'accessibilitat del contingut web (WCAG).

## Implementació (component web)

Nota: perquè aparegui el divisor, el contenidor on s'introdueixi ha de tenir un `height` concret; altrament es renderitzarà però no serà visible per pantalla.

### `<divider-component>`
Paquet: core.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte | Obligatorietat |
|---|---|---|---|---|---|
| `orientation` | `orientation` | Orientació del component (horizontal o vertical). Opcions: `horizontal`, `vertical`. | string | `horizontal` | Opcional |
| `theme` | `theme` | Tema visual del component. Opcions: `dark`, `light`. | string | `light` | Opcional |

**Esdeveniments:** cap esdeveniment declarat.

**Utilitzat per:**
- Segons el lloc: `accordion-component`, `footer-component`, `results-list-component`, `summary-list-component`, `header-component` (core); `chat-header-component` (conversational).
- Segons el PDF: `accordion-component`, `footer-component`, `header-component`, `header-public-component`, `inputtext-component`, `results-list-component`, `summary-list-component`, `table-of-contents-component`.

**Exemple d'ús**

```html
<!-- /index.html -->
<divider-component 
  orientation="vertical" 
  theme="dark">
</divider-component>
```

**Exemple d'instància (PDF)**

```html
<divider-component
  orientation='horizontal'
  theme='light'
></divider-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 2.3.0 | 1.0.0 | 31 gener, 2025 | Sense canvis. |
| 2.2.0 | 0.1.1 | 20 gener, 2025 | Sense canvis. |
| 2.1.0 | 0.1.1 | 04 desembre, 2024 | Sense canvis. |
| 2.0.0 | 0.1.0 | 02 desembre, 2024 | Sense canvis. |
| 1.1.0 | 0.1.0 | 22 novembre, 2024 | Sense canvis. |
| 1.1.0 | 0.0.4 | 18 novembre, 2024 | Sense canvis. |
| 1.0.0 | 0.0.3 | 1 novembre, 2024 | Disseny, desenvolupament i documentació del component. |

Release notes (llegat): 1.0 · 10 d'abril, 2024.

## Vegeu també
- [Acordió](component-acordio.md)
- [Peu de pàgina](component-peu-de-pagina.md)
- [Llistat de resultats](component-llistat-de-resultats.md)
- [Capçalera per aplicacions internes](component-capcalera-per-aplicacions-internes.md)
