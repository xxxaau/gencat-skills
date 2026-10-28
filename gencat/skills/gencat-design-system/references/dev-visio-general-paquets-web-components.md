# Visió general dels paquets de web components

> Font: PDF de documentació de components `documentation-v12.0.0` (SDGC Stencil Component Library, generat automàticament a partir del codi font) i pàgina https://sistemadedisseny.gencat.cat/38669693e/p/61ee3b · Extret el 2026-10-28

## Portada i índex del PDF

- Títol: SDGC STENCIL COMPONENT LIBRARY, Documentació de components (el PDF és en castellà: "Documentación de componentes").
- Versió: **12.0.0**
- Data de generació: **2026-07-13** (13 de juliol de 2026). Generat automàticament a partir del codi font.
- Paquet **core** (`gencat-core`): **79 components**.
- Paquet **conversational** (`gencat-conversational`): **12 components**.
- Total: 91 components web (tags). El paquet conversational requereix també tenir instal·lat el paquet core (vegeu [Desenvolupament](dev-desenvolupament.md)).

Instal·lació: `npm install gencat-core` / `npm install gencat-conversational` (vegeu [Desenvolupament](dev-desenvolupament.md)). Configuració per framework: [Angular](dev-projectes-angular.md), [React](dev-projectes-react.md), [Vue](dev-projectes-vue.md). Textos i idioma: [Personalització de textos](dev-personalitzacio-de-textos.md), [Canvi d'idioma](dev-canvi-d-idioma-dels-components.md), [Referència de claus](dev-referencia-de-claus-disponibles.md).

Convencions observades: tots els tags acaben en `-component`; als atributs HTML les propietats camelCase s'escriuen en kebab-case (p. ex. `title-switch`, `is-disabled`). Les rutes d'importació per component són `gencat-core/dist/components/<tag>.js` (Custom Elements; p. ex. `switch-component.js`) i, per als wrappers, `gencat-core/plugins/<framework>/...` (vegeu els fitxers de projecte).

## Paquet `core` (79 components)

| Tag | Component del lloc | Fitxer |
|---|---|---|
| `<accordion-component>` | Acordió | [component-acordio.md](component-acordio.md) |
| `<advanced-checkbox-component>` | Casella de selecció | [component-casella-de-seleccio.md](component-casella-de-seleccio.md) |
| `<advanced-image-component>` | Imatge avançada | [component-imatge-avancada.md](component-imatge-avancada.md) |
| `<advanced-radio-button-component>` | Botó d'opció | [component-boto-d-opcio.md](component-boto-d-opcio.md) |
| `<back-to-top-button-component>` | Botó Tornar amunt | [component-boto-tornar-amunt.md](component-boto-tornar-amunt.md) |
| `<backoffice-subheader-component>` | Capçalera secundària de BO | [component-capcalera-secundaria-de-bo.md](component-capcalera-secundaria-de-bo.md) |
| `<badge-component>` | Insígnia | [component-insignia.md](component-insignia.md) |
| `<banner-component>` | Bàner | [component-baner.md](component-baner.md) |
| `<breadcrumb-component>` | Fils d'Ariadna | [component-fils-d-ariadna.md](component-fils-d-ariadna.md) |
| `<button-component>` | Botons | [component-botons.md](component-botons.md) |
| `<calendar-component>` | Calendari | [component-calendari.md](component-calendari.md) |
| `<callout-component>` | Avisos | [component-avisos.md](component-avisos.md) |
| `<card-highlight-component>` | Targetes | [component-targetes.md](component-targetes.md) |
| `<card-info-component>` | Targetes | [component-targetes.md](component-targetes.md) |
| `<card-info-evolutive-component>` | Targetes | [component-targetes.md](component-targetes.md) |
| `<card-navigation-basic-component>` | Targetes | [component-targetes.md](component-targetes.md) |
| `<card-navigation-component>` | Targetes | [component-targetes.md](component-targetes.md) |
| `<card-news-component>` | Visor de notícies | [component-visor-de-noticies.md](component-visor-de-noticies.md) |
| `<card-social-component>` | Targetes | [component-targetes.md](component-targetes.md) |
| `<carousel-component>` | Visor de notícies | [component-visor-de-noticies.md](component-visor-de-noticies.md) |
| `<checkbox-component>` | Casella de selecció | [component-casella-de-seleccio.md](component-casella-de-seleccio.md) |
| `<chip-component>` | Xips | [component-xips.md](component-xips.md) |
| `<content-tree-component>` | Arbre de continguts | [component-arbre-de-continguts.md](component-arbre-de-continguts.md) |
| `<date-picker-component>` | Selector de data | [component-selector-de-data.md](component-selector-de-data.md) |
| `<divider-component>` | Divisor | [component-divisor.md](component-divisor.md) |
| `<dropdown-button-component>` | Botons | [component-botons.md](component-botons.md) |
| `<dropdown-component>` | Desplegable | [component-desplegable.md](component-desplegable.md) |
| `<dropdown-menu-component>` | Menú desplegable | [component-menu-desplegable.md](component-menu-desplegable.md) |
| `<dynamic-table-component>` | Taules dinàmiques | [component-taules-dinamiques.md](component-taules-dinamiques.md) |
| `<empty-state-component>` | Estat buit | [component-estat-buit.md](component-estat-buit.md) |
| `<file-uploader-component>` | Carregador d'arxius | [component-carregador-d-arxius.md](component-carregador-d-arxius.md) |
| `<filter-component>` | Filtres | [component-filtres.md](component-filtres.md) |
| `<footer-component>` | Peu de pàgina | [component-peu-de-pagina.md](component-peu-de-pagina.md) |
| `<glossary-component>` | Glossari | [component-glossari.md](component-glossari.md) |
| `<group-button-component>` | Grup de botons | [component-grup-de-botons.md](component-grup-de-botons.md) |
| `<header-component>` | Capçalera per aplicacions internes | [component-capcalera-per-aplicacions-internes.md](component-capcalera-per-aplicacions-internes.md) |
| `<header-public-component>` | Capçalera web pública | [component-capcalera-web-publica.md](component-capcalera-web-publica.md) |
| `<hero-banner-component>` | Panell destacat | [component-panell-destacat.md](component-panell-destacat.md) |
| `<highlight-text-component>` | Text destacat | [component-text-destacat.md](component-text-destacat.md) |
| `<highlighted-link-component>` | Enllaços | [component-enllacos.md](component-enllacos.md) |
| `<horizontal-menu-component>` | Menú horitzontal | [component-menu-horitzontal.md](component-menu-horitzontal.md) |
| `<horizontal-tab-component>` | Pestanyes | [component-pestanyes.md](component-pestanyes.md) |
| `<icon-poi-component>` | Visor de mapa | [component-visor-de-mapa.md](component-visor-de-mapa.md) |
| `<inputtext-component>` | Camp d'entrada | [component-camp-d-entrada.md](component-camp-d-entrada.md) |
| `<key-data-component>` | Dades destacades | [component-dades-destacades.md](component-dades-destacades.md) |
| `<link-component>` | Enllaços | [component-enllacos.md](component-enllacos.md) |
| `<link-list-component>` | Llista d'enllaços | [component-llista-d-enllacos.md](component-llista-d-enllacos.md) |
| `<list-component>` | Llista | [component-llista.md](component-llista.md) |
| `<modal-component>` | Modals | [component-modals.md](component-modals.md) |
| `<pagination-component>` | Paginació | [component-paginacio.md](component-paginacio.md) |
| `<poi-component>` | Visor de mapa | [component-visor-de-mapa.md](component-visor-de-mapa.md) |
| `<popover-component>` | Descripció emergent | [component-descripcio-emergent.md](component-descripcio-emergent.md) |
| `<progress-bar-component>` | Barra de progrés | [component-barra-de-progres.md](component-barra-de-progres.md) |
| `<radio-component>` | Botó d'opció | [component-boto-d-opcio.md](component-boto-d-opcio.md) |
| `<results-list-component>` | Llistat de resultats | [component-llistat-de-resultats.md](component-llistat-de-resultats.md) |
| `<searchfield-component>` | Camp de cerca | [component-camp-de-cerca.md](component-camp-de-cerca.md) |
| `<secondary-header-component>` | Capçalera secundària | [component-capcalera-secundaria.md](component-capcalera-secundaria.md) |
| `<segmented-control-component>` | Control segmentat | [component-control-segmentat.md](component-control-segmentat.md) |
| `<sheet-component>` | Panell emergent | [component-panell-emergent.md](component-panell-emergent.md) |
| `<show-more-component>` | Mostra més | [component-mostra-mes.md](component-mostra-mes.md) |
| `<side-menu-component>` | Menú lateral | [component-menu-lateral.md](component-menu-lateral.md) |
| `<slider-component>` | Control de rang | [component-control-de-rang.md](component-control-de-rang.md) |
| `<spinner-component>` | Indicador de càrrega | [component-indicador-de-carrega.md](component-indicador-de-carrega.md) |
| `<status-tracker-component>` | Rastrejador d'estat | [component-rastrejador-d-estat.md](component-rastrejador-d-estat.md) |
| `<stepper-component>` | Pas a pas | [component-pas-a-pas.md](component-pas-a-pas.md) |
| `<summary-list-component>` | Dades estructurades | [component-dades-estructurades.md](component-dades-estructurades.md) |
| `<support-banner-component>` | Bàner d'atenció | [component-baner-d-atencio.md](component-baner-d-atencio.md) |
| `<switch-component>` | Commutador | [component-commutador.md](component-commutador.md) |
| `<tab-bar-horizontal-component>` | Barra de pestanyes | [component-barra-de-pestanyes.md](component-barra-de-pestanyes.md) |
| `<tab-bar-vertical-component>` | Barra de pestanyes | [component-barra-de-pestanyes.md](component-barra-de-pestanyes.md) |
| `<table-of-contents-component>` | Taula de continguts | [component-taula-de-continguts.md](component-taula-de-continguts.md) |
| `<tag-component>` | Etiquetes | [component-etiquetes.md](component-etiquetes.md) |
| `<textarea-component>` | Àrea de text | [component-area-de-text.md](component-area-de-text.md) |
| `<timeline-component>` | Línia de temps | [component-linia-de-temps.md](component-linia-de-temps.md) |
| `<toast-component>` | Notificació emergent | [component-notificacio-emergent.md](component-notificacio-emergent.md) |
| `<tooltip-component>` | Descripció emergent | [component-descripcio-emergent.md](component-descripcio-emergent.md) |
| `<vertical-tabs-component>` | Pestanyes | [component-pestanyes.md](component-pestanyes.md) |
| `<video-audio-player-component>` | Reproductor de vídeo i àudio | [component-reproductor-de-video-i-audio.md](component-reproductor-de-video-i-audio.md) |
| `<viewer-component>` | Visor de notícies | [component-visor-de-noticies.md](component-visor-de-noticies.md) |

## Paquet `conversational` (12 components)

| Tag | Component del lloc | Fitxer |
|---|---|---|
| `<avatar-component>` | Avatar | [component-avatar.md](component-avatar.md) |
| `<back-to-bottom-button-component>` | Botó tornar a baix | [component-boto-tornar-a-baix.md](component-boto-tornar-a-baix.md) |
| `<chat-button-component>` | Botó de xat | [component-boto-de-xat.md](component-boto-de-xat.md) |
| `<chat-header-component>` | Capçalera de xat | [component-capcalera-de-xat.md](component-capcalera-de-xat.md) |
| `<chat-input-component>` | Camp d'entrada de xat | [component-camp-d-entrada-de-xat.md](component-camp-d-entrada-de-xat.md) |
| `<chat-message-component>` | Missatge de xat | [component-missatge-de-xat.md](component-missatge-de-xat.md) |
| `<chat-subheader-component>` | Capçalera secundària de xat | [component-capcalera-secundaria-de-xat.md](component-capcalera-secundaria-de-xat.md) |
| `<floating-chat-container-component>` | Contenidor de xat | [component-contenidor-de-xat.md](component-contenidor-de-xat.md) |
| `<references-component>` | Fonts de coneixement | [component-fonts-de-coneixement.md](component-fonts-de-coneixement.md) |
| `<side-chat-button-component>` | Botó de xat | [component-boto-de-xat.md](component-boto-de-xat.md) |
| `<side-panel-chat-component>` | Contenidor de xat | [component-contenidor-de-xat.md](component-contenidor-de-xat.md) |
| `<suggestions-component>` | Suggeriments | [component-suggeriments.md](component-suggeriments.md) |

## Components del lloc que agrupen diversos tags

- [Barra de pestanyes](component-barra-de-pestanyes.md) (core): `<tab-bar-horizontal-component>`, `<tab-bar-vertical-component>`
- [Botons](component-botons.md) (core): `<button-component>`, `<dropdown-button-component>`
- [Botó d'opció](component-boto-d-opcio.md) (core): `<advanced-radio-button-component>`, `<radio-component>`
- [Botó de xat](component-boto-de-xat.md) (conversational): `<chat-button-component>`, `<side-chat-button-component>`
- [Casella de selecció](component-casella-de-seleccio.md) (core): `<advanced-checkbox-component>`, `<checkbox-component>`
- [Contenidor de xat](component-contenidor-de-xat.md) (conversational): `<floating-chat-container-component>`, `<side-panel-chat-component>`
- [Descripció emergent](component-descripcio-emergent.md) (core): `<popover-component>`, `<tooltip-component>`
- [Enllaços](component-enllacos.md) (core): `<highlighted-link-component>`, `<link-component>`
- [Pestanyes](component-pestanyes.md) (core): `<horizontal-tab-component>`, `<vertical-tabs-component>`
- [Targetes](component-targetes.md) (core): `<card-highlight-component>`, `<card-info-component>`, `<card-info-evolutive-component>`, `<card-navigation-basic-component>`, `<card-navigation-component>`, `<card-social-component>`
- [Visor de mapa](component-visor-de-mapa.md) (core): `<icon-poi-component>`, `<poi-component>`
- [Visor de notícies](component-visor-de-noticies.md) (core): `<card-news-component>`, `<carousel-component>`, `<viewer-component>`

## Nota

Cada tag té un capítol propi al PDF; la seva API (propietats, esdeveniments, mètodes, exemples) està transcrita a la secció "Implementació (component web)" del fitxer indicat.
