# Catàleg de components — Sistema de Disseny Gencat

> Índex de tots els components documentats al Sistema de Disseny (llibreria de components v12.6.0; documentació del codi v12.0.0 · extret el 2026-10-28). Cada fila apunta al fitxer amb la documentació completa: anatomia, variants, estats, mides, bones pràctiques, accessibilitat, tokens, API del component web i historial de versions.

**Com triar:** identifica la necessitat a les agrupacions de sota, obre el fitxer del component i segueix-ne la secció "Implementació". Si no hi ha cap component oficial, vegeu "Quan NO existeix un component oficial" a `SKILL.md`. Visió general oficial: [component-components-core.md](component-components-core.md) i [component-components-conversacionals.md](component-components-conversacionals.md); criteris de selecció: [sobre-components.md](sobre-components.md).

Els components es publiquen com a **web components** en dos paquets: `core` (79 elements) i `conversational` (12). Inventari de tots els tags: [dev-visio-general-paquets-web-components.md](dev-visio-general-paquets-web-components.md).


## Components core

### Accions

| Component | Equivalent comú | Per a què serveix | Web component(s) |
|---|---|---|---|
| [Botons](component-botons.md) | Buttons | Per realitzar accions. | `<button-component>`, `<dropdown-button-component>` |
| [Mostra més](component-mostra-mes.md) | Show more | Per expandir contingut addicional que inicialment està ocult. | `<show-more-component>` |
| [Botó Tornar amunt](component-boto-tornar-amunt.md) | Back to top button | Permet tornar ràpidament a la part superior de la pàgina després de fer scroll. | `<back-to-top-button-component>` |
| [Grup de botons](component-grup-de-botons.md) | Button group | Per agrupar botons que tenen una relació funcional o contextual. | `<group-button-component>` |

### Contingut

| Component | Equivalent comú | Per a què serveix | Web component(s) |
|---|---|---|---|
| [Reproductor de vídeo i àudio](component-reproductor-de-video-i-audio.md) | Video and Audio Player | Per integrar contingut multimèdia. | `<video-audio-player-component>` |
| [Imatge avançada](component-imatge-avancada.md) | Advanced image | Per expandir contingut addicional que inicialment està ocult. | `<advanced-image-component>` |
| [Text destacat](component-text-destacat.md) | Highlight text | Per ressaltar informació rellevant dins d'una interfície digital. | `<highlight-text-component>` |
| [Bàner](component-baner.md) | Banner | Per destacar informació important o promocional. | `<banner-component>` |
| [Bàner d'atenció](component-baner-d-atencio.md) | Support banner | Captar la mirada de l'usuari i proporcionar informació de contacte de manera ràpida i accessible. | `<support-banner-component>` |

### Navegació

| Component | Equivalent comú | Per a què serveix | Web component(s) |
|---|---|---|---|
| [Barra de pestanyes](component-barra-de-pestanyes.md) | Tab bar | Per navegar entre seccions d’una pàgina sense afectar altres elements. | `<tab-bar-horizontal-component>`, `<tab-bar-vertical-component>` |
| [Control segmentat](component-control-segmentat.md) | Segmented control | Botons alineats que permeten triar una opció de visualització concreta. | `<segmented-control-component>` |
| [Enllaços](component-enllacos.md) | Links | Per facilitar la navegació entre parts del contingut o funcionalitats. | `<highlighted-link-component>`, `<link-component>` |
| [Fils d'Ariadna](component-fils-d-ariadna.md) | Breadcrumbs | Per proporcionar una trajectòria clara de les pàgines visitades. | `<breadcrumb-component>` |
| [Llistat de resultats](component-llistat-de-resultats.md) | Results list | Per agrupar un conjunt de resultats. | `<results-list-component>` |
| [Menú desplegable](component-menu-desplegable.md) | Dropdown menu | Permet optimitzar l'ús de l'espai  mostrant contingut addicional només quan és necessari. | `<dropdown-menu-component>` |
| [Menú horitzontal](component-menu-horitzontal.md) | Horizontal menu | Per navegar pels elements principals de la pàgina. | `<horizontal-menu-component>` |
| [Menú lateral](component-menu-lateral.md) | Side menu | Per accedir a pàgines o seccions dins d’una web. | `<side-menu-component>` |
| [Paginació](component-paginacio.md) | Pagination | Per separar grups de contingut en diverses pàgines. | `<pagination-component>` |
| [Pas a pas](component-pas-a-pas.md) | Stepper | Per a guiar a l’usuari a través d’un procés complex. | `<stepper-component>` |
| [Pestanyes](component-pestanyes.md) | Tabs | Per organitzar contingut relacionat en seccions o categories. | `<horizontal-tab-component>`, `<vertical-tabs-component>` |
| [Targetes](component-targetes.md) | Cards | Per organitzar i presentar contingut de forma clara i atractiva. | `<card-highlight-component>`, `<card-info-component>`, `<card-info-evolutive-component>`, `<card-navigation-basic-component>`, `<card-navigation-component>`, `<card-social-component>` |
| [Taula de continguts](component-taula-de-continguts.md) | Table of contents | Facilita l'accés ràpid i estructurat al contingut. | `<table-of-contents-component>` |
| [Visor de notícies](component-visor-de-noticies.md) | News viewer | Per oferir una previsualització de diverses notícies. | `<card-news-component>`, `<carousel-component>`, `<viewer-component>` |

### Introducció de dades

| Component | Equivalent comú | Per a què serveix | Web component(s) |
|---|---|---|---|
| [Àrea de text](component-area-de-text.md) | Text area | Per la recollida de dades extenses. | `<textarea-component>` |
| [Botó d'opció](component-boto-d-opcio.md) | Radio button | Per a seleccionar una opció dins d'un conjunt d'opcions mútuament excloents. | `<advanced-radio-button-component>`, `<radio-component>` |
| [Camp d'entrada](component-camp-d-entrada.md) | Input field | Per a introduir i recopilar dades de manera interactiva. | `<inputtext-component>` |
| [Camp de cerca](component-camp-de-cerca.md) | Searchfield | Per a realitzar cerques o explorar un lloc web o aplicació. | `<searchfield-component>` |
| [Carregador d'arxius](component-carregador-d-arxius.md) | File uploader | Per seleccionar i pujar arxius a un lloc específic. | `<file-uploader-component>` |
| [Casella de selecció](component-casella-de-seleccio.md) | Checkbox | Per a seleccionar una o més opcions d'una llista predefinida. | `<advanced-checkbox-component>`, `<checkbox-component>` |
| [Desplegable](component-desplegable.md) | Dropdown | Per a seleccionar un o diversos elements d'una llista d'opcions predefinides. | `<dropdown-component>` |
| [Commutador](component-commutador.md) | Switch | Per alternar entre dos estats mútuament excloents. | `<switch-component>` |
| [Selector de data](component-selector-de-data.md) | Date picker | Per seleccionar una única instància o interval de dates. | `<date-picker-component>` |
| [Xips](component-xips.md) | Chips | Per representar accions específiques de forma compacta | `<chip-component>` |
| [Calendari](component-calendari.md) | Calendar | Per navegar i seleccionar dates dins d’una vista setmanal o mensual. | `<calendar-component>` |
| [Control de rang](component-control-de-rang.md) | Slider | Permet seleccionar un valor o un rang de valors dins d’un interval predefinit arrossegant un control lliscant. | `<slider-component>` |

### Indicadors d'estat i retroacció

| Component | Equivalent comú | Per a què serveix | Web component(s) |
|---|---|---|---|
| [Avisos](component-avisos.md) | Callout | Per comunicar un estat que és específic d'una pàgina o característica. | `<callout-component>` |
| [Barra de progrés](component-barra-de-progres.md) | Progress bar | Per mostrar l'estat d'avanç d'una tasca, reflectint el seu progrés en temps real. | `<progress-bar-component>` |
| [Descripció emergent](component-descripcio-emergent.md) | Popover | Per mostrar informació contextual. | `<popover-component>`, `<tooltip-component>` |
| [Esquelet](component-esquelet.md) | Skeleton | Per simular la forma del contingut pendent de carregar. | — |
| [Estat buit](component-estat-buit.md) | Empty state | Indica que no hi ha contingut per mostrar. | `<empty-state-component>` |
| [Etiquetes](component-etiquetes.md) | Tags | Per mostrar l'estat d'un element, les propietats clau o les categories. | `<tag-component>` |
| [Indicador de funció](component-indicador-de-funcio.md) | Tooltip | Per mostrar un text breu en passar el cursor per sobre d'una icona o activador. | — |
| [Indicador de càrrega](component-indicador-de-carrega.md) | Spinner | Representa un procés està en curs durant un període d’espera indeterminat. | `<spinner-component>` |
| [Insígnia](component-insignia.md) | Badge | Per a cridar l'atenció dels usuaris sobre un element en la pàgina | `<badge-component>` |
| [Notificació emergent](component-notificacio-emergent.md) | Toast | Per a notificacions breus i temporals (no requereix acció de l'usuari). | `<toast-component>` |
| [Rastrejador d'estat](component-rastrejador-d-estat.md) | Status tracker | Per monitorar, informar i mostrar l'estat de tasques, projectes, etc. | `<status-tracker-component>` |
| [Etiquetatge d'IA](component-etiquetatge-d-ia.md) | IA labeling | Permet identificar de manera clara, coherent i accessible els continguts creats o editats amb intel·ligència artificial | — |

### Contenidors i estructura

| Component | Equivalent comú | Per a què serveix | Web component(s) |
|---|---|---|---|
| [Acordió](component-acordio.md) | Accordion | Per mostrar o amagar informació individualment d'un llistat d'ítems. | `<accordion-component>` |
| [Arbre de continguts](component-arbre-de-continguts.md) | Content tree | Per representar la informació de manera jeràrquica. | `<content-tree-component>` |
| [Capçalera per aplicacions internes](component-capcalera-per-aplicacions-internes.md) | Back-office Header | Per proporcionar un lloc coherent per a la marca, la cerca i l'accés a les accions globals | `<header-component>` |
| [Capçalera secundària](component-capcalera-secundaria.md) | Secondary header | Per proporcionar context i estructura a les pàgines secundàries. | `<secondary-header-component>` |
| [Divisor](component-divisor.md) | Divider | Per separar contingut o seccions dins d’una pàgina o entre elements. | `<divider-component>` |
| [Filtres](component-filtres.md) | Filters | Per refinar i limitar els resultats d’una llista. | `<filter-component>` |
| [Línia de temps](component-linia-de-temps.md) | Timeline | Per mostrar l’estructura d’un procés seqüencial de forma clara i ordenada. | `<timeline-component>` |
| [Llista](component-llista.md) | List | Per agrupacions de contingut relacionat. | `<list-component>` |
| [Llista d'enllaços](component-llista-d-enllacos.md) | Link list | Per agrupacions d'enllaços. | `<link-list-component>` |
| [Modals](component-modals.md) | Modal | Per proporcionar informació crítica o quan cal demanar una decisió. | `<modal-component>` |
| [Panell destacat](component-panell-destacat.md) | Hero banner | Per indicar el propòsit de la pàgina. | `<hero-banner-component>` |
| [Panell emergent](component-panell-emergent.md) | Sheet | Per oferir funcionalitats  complementàries de manera contextual i no intrusiva, | `<sheet-component>` |
| [Capçalera web pública](component-capcalera-web-publica.md) | Public Website Header | Per la navegació i l'accés a funcionalitats globals. | `<header-public-component>` |
| [Campanya](component-campanya.md) | Featured carousel | Mostra contingut destacat en format carrusel. | — |

### Visualització de dades

| Component | Equivalent comú | Per a què serveix | Web component(s) |
|---|---|---|---|
| [Taules dinàmiques](component-taules-dinamiques.md) | Dynamic tables | Per organitzar i mostrar les dades de manera eficient. | `<dynamic-table-component>` |
| [Dades estructurades](component-dades-estructurades.md) | Summary list | Per resumir la informació clau abans del contingut principal. | `<summary-list-component>` |
| [Dades destacades](component-dades-destacades.md) | Key data | Per ressaltar informació clau de manera visual i concisa. | `<key-data-component>` |
| [Visor de mapa](component-visor-de-mapa.md) | Map viewer | Permet explorar i entendre informació geogràfica de manera visual i intuïtiva. | `<icon-poi-component>`, `<poi-component>` |


### Altres components core (no llistats a la visió general oficial)

| Component | Equivalent comú | Per a què serveix | Web component(s) |
|---|---|---|---|
| [Capçalera secundària de BO](component-capcalera-secundaria-de-bo.md) | Backoffice Subheader | La capçalera secundària de BO és un component estructural que proporciona context i accions rellevants dins d'una vista interna d'un sistema de gestió. | `<backoffice-subheader-component>` |
| [Glossari](component-glossari.md) | Glossary | El Glossari és un component de consulta que permet presentar definicions, conceptes i continguts ordenats alfabèticament per facilitar-ne la cerca i la comprensió en cont | `<glossary-component>` |
| [Peu de pàgina](component-peu-de-pagina.md) | Footer | El peu de pàgina és un component que es troba a la part inferior de les pàgines web i proporciona informació complementària i enllaços rellevants. | `<footer-component>` |

## Components conversacionals (xat / IA)

### Identitat

| Component | Equivalent comú | Per a què serveix | Web component(s) |
|---|---|---|---|
| [Avatar](component-avatar.md) | Avatar | Per representa l’assistent virtual en una conversa amb | `<avatar-component>` |

### Accions

| Component | Equivalent comú | Per a què serveix | Web component(s) |
|---|---|---|---|
| [Botó de xat](component-boto-de-xat.md) | Chat button | Per iniciar una conversa amb el servei d’assistència virtual. | `<chat-button-component>`, `<side-chat-button-component>` |
| [Botó tornar a baix](component-boto-tornar-a-baix.md) | Back to bottom button | Per tornar a l'últim missatge de la conversa | `<back-to-bottom-button-component>` |

### Contingut

| Component | Equivalent comú | Per a què serveix | Web component(s) |
|---|---|---|---|
| [Missatge de xat](component-missatge-de-xat.md) | Chat message | Per representar la intervenció d’un participant. | `<chat-message-component>` |
| [Fonts de coneixement](component-fonts-de-coneixement.md) | References | Per mostrar les fonts que ha generat una resposta. | `<references-component>` |

### Introducció de dades

| Component | Equivalent comú | Per a què serveix | Web component(s) |
|---|---|---|---|
| [Camp d'entrada de xat](component-camp-d-entrada-de-xat.md) | Chat input | Per enviar missatges | `<chat-input-component>` |
| [Suggeriments](component-suggeriments.md) | Suggestions | Element interactiu que mostra opcions de respostes de seguiment vinculades a l'últim missatge. | `<suggestions-component>` |

### Contenidors i estructura

| Component | Equivalent comú | Per a què serveix | Web component(s) |
|---|---|---|---|
| [Capçalera de xat](component-capcalera-de-xat.md) | Chat header | Per proporcionar un lloc per a la marca i l'accés a funcionalitats globals. | `<chat-header-component>` |
| [Contenidor de xat](component-contenidor-de-xat.md) | Chat container | Per doanr estructura. | `<floating-chat-container-component>`, `<side-panel-chat-component>` |
| [Capçalera secundària de xat](component-capcalera-secundaria-de-xat.md) | Chat subheader | Per aportar context funcional i legal. | `<chat-subheader-component>` |
