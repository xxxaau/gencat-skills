# Canvi d'idioma dels components

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/847317 · Font actualitzada el 2026-09-09 · Extret el 2026-10-28

La pàgina té dues pestanyes: Personalització de textos i Referència de claus disponibles. El mateix contingut es documenta també a [Personalització de textos](dev-personalitzacio-de-textos.md) i [Referència de claus disponibles](dev-referencia-de-claus-disponibles.md).

# Pestanya: Personalització de textos

## Personalització de textos dels components
Alguns components de la biblioteca inclouen textos predeterminats (etiquetes, botons d'acció, missatges d'estat, etc.). Pots substituir-los pels de la teva aplicació sense necessitat de modificar el component: n'hi ha prou d'invocar la funció `setLocale` una sola vegada a l'inici de l'aplicació.

## Com funciona
La funció `setLocale`, exportada des de `gencat-core`, accepta un objecte parcial amb els textos que vols sobreescriure. Només cal que indiquis les claus que vols canviar; la resta conserven el valor per defecte.

```ts
import { setLocale } from 'gencat-core';  

setLocale({   
    pagination: { previous: 'Anterior', next: 'Següent', pageSummary: 'Pàgina {current} de {total}' },   
    accordion: { expandAll: 'Expandeix-ho tot', collapseAll: 'Redueix-ho tot' },   // ... només els que necessitis canviar }); 
```
> **Important:** Has de cridar `setLocale` abans que es munti qualsevol component. D'aquesta manera, quan es renderitzin per primera vegada ja tindran els textos correctes.


## Integració per framework

### Angular
Afegeix la crida a `setLocale` a **`main.ts`** (o a `app.component.ts`), abans de l'arrencada del mòdul:

```ts
import { setLocale } from 'gencat-core'; 
import { platformBrowserDynamic } from '@angular/platform-browser-dynamic'; 
import { AppModule } from './app/app.module';  

setLocale({ pagination: { previous: 'Anterior', next: 'Següent' }, });  

platformBrowserDynamic().bootstrapModule(AppModule); 
```

### React
Afegeix la crida a `setLocale` a **`main.tsx`** o **`index.tsx`**, abans del render inicial:

```ts
import { setLocale } from 'gencat-core'; 
import ReactDOM from 'react-dom/client'; 
import App from './App';  

setLocale({   pagination: { previous: 'Anterior', next: 'Següent' }, });  
ReactDOM.createRoot(document.getElementById('root')!).render(<App />); 
```

### Vue
Afegeix la crida a `setLocale` a **`main.ts`**, abans del muntatge de l'aplicació:

```ts
import { setLocale } from 'gencat-core'; 
import { createApp } from 'vue'; 
import App from './App.vue';  

setLocale({   pagination: { previous: 'Anterior', next: 'Següent' }, });  
createApp(App).mount('#app'); 
```


## Notes
- `setLocale` és **acumulativa**: si la crides diverses vegades, cada crida sobreescriu únicament les claus indicades, sense afectar les que no s'han especificat.
- Els textos que accepten variables dinàmiques (com ara `pageSummary`) utilitzen la sintaxi `{nomVariable}`. No modifiquis el nom de les variables, ja que el component les substitueix en temps d'execució.

# Pestanya: Referència de claus disponibles

Claus de text de cada component i valor per defecte. Cada secció `####` és el grup de claus (component) dins de l'objecte passat a `setLocale`.

### Paquet principal (`gencat-core`)

#### `accordion`

| Clau | Valor per defecte |
|---|---|
| `expandAll` | `'Desplega tots'` |
| `collapseAll` | `'Replega tots'` |

#### `advancedImage`

| Clau | Valor per defecte |
|---|---|
| `expandImage` | `'Ampliar imatge'` |
| `expandImageAria` | `'Ampliar imatge'` |
| `morePhotos` | `'{count} fotos més'` |
| `openGalleryAria` | `'Botó: Obrir galeria, {count} fotos més'` |
| `galleryOpenAnnouncement` | `"Galeria d'imatges, diàleg obert."` |
| `altFirstImage` | `'Imatge 1 de {total} : {description}'` |
| `altGalleryImage` | `'Imatge {index} de {total}: {description}'` |
| `altThumbnailSelected` | `'Miniatura seleccionada: {description}'` |
| `altThumbnail` | `'Botó, miniatura {index} de {total}: {description}'` |
| `zoomOutAria` | `'Botó: Allunyar imatge'` |
| `zoomOutTooltip` | `'Allunyar imatge'` |
| `zoomInAria` | `'Botó: Apropar imatge'` |
| `zoomInTooltip` | `'Apropar imatge'` |
| `resetAria` | `'Botó: resetejar imatge'` |
| `resetTooltip` | `'Resetejar imatge'` |
| `prevImageAria` | `'Botó: Anterior'` |
| `nextImageAria` | `'Botó: Següent.'` |
| `thumbnailsAriaLabel` | `'Llista de miniatures'` |
| `closeGalleryTooltip` | `'Tancar galeria'` |
| `closeGalleryAria` | `'Botó: Tancar galeria.'` |

#### `backofficeSubheader`

| Clau | Valor per defecte |
|---|---|
| `closePopoverTooltip` | `'Tancar descripció emergent'` |

#### `badge`

| Clau | Valor per defecte |
|---|---|
| `newAlerts` | `'Noves alertes'` |
| `notifications` | `'{count} Notificacions'` |
| `notification` | `'Notificacion'` |
| `notificationAriaLabel` | `'{text} notificació'` |

#### `banner`

| Clau | Valor per defecte |
|---|---|
| `decorativeImageAlt` | `'Imatge decorativa'` |

#### `breadcrumb`

| Clau | Valor per defecte |
|---|---|
| `ellipsis` | `'...'` |
| `menuExpanded` | `'Menu expandit'` |
| `menuClosed` | `'Menu tancat'` |

#### `button`

| Clau | Valor per defecte |
|---|---|
| `loading` | `'Cargando'` |

#### `calendar`

| Clau | Valor per defecte |
|---|---|
| `months` | `['Gener','Febrer','Març','Abril','Maig','Juny','Juliol','Agost','Setembre','Octubre','Novembre','Desembre']` |
| `monthsLower` | `['gener','febrer','març','abril','maig','juny','juliol','agost','setembre','octubre','novembre','desembre']` |
| `shortMonths` | `['Gen.','Feb.','Mar.','Abr.','Mai.','Jun.','Jul.','Ago.','Set.','Oct.','Nov.','Des.']` |
| `weekdaysLong` | `['Diumenge','Dilluns','Dimarts','Dimecres','Dijous','Divendres','Dissabte']` |
| `weekdaysShort` | `['Dl.','Dt.','Dc.','Dj.','Dv.','Ds.','Dg.']` |
| `monthAnnouncement` | `'Mes de {month} del {year}'` |
| `weekAnnouncement` | `'Setmana del {from} al {to} de {month} de {year}'` |
| `dayAriaLabel` | `'{dayName}, {day} de {month} de {year}'` |
| `dayAriaLabelUnavailable` | `'{dayName}, {day} de {month} de {year}, no disponible'` |
| `lastAvailableMonth` | `'Últim mes disponible'` |
| `prevMonth` | `'Mes previ'` |
| `prevMonthAria` | `'Mes anterior'` |
| `goToday` | `"Vés a avui"` |
| `goTodayAria` | `"Anar al dia d'avui"` |
| `nextMonth` | `'Mes següent'` |
| `nextMonthAria` | `'Mes següent'` |
| `expandMonthView` | `'Expandir vista de mes'` |
| `collapseMonthView` | `'Col·lapsar vista de mes'` |
| `prevWeek` | `'Canviar a setmana anterior'` |
| `nextWeek` | `'Canviar a setmana següent'` |
| `monthNavAriaLabel` | `'Mes seleccionat: {month}. Fer clic per navegar entre mesos'` |
| `monthListAriaLabel` | `'Llista de mesos'` |
| `prevMonths` | `'Mesos anteriors'` |
| `nextMonths` | `'Mesos següents'` |
| `monthSelectedAriaLabel` | `'Mes seleccionat: {month}'` |
| `yearNavAriaLabel` | `'Any seleccionat: {year}. Fer clic per navegar entre anys'` |
| `yearListAriaLabel` | `"Llista d'anys"` |
| `prevYears` | `'Anys anteriors'` |
| `nextYears` | `'Anys següents'` |
| `yearSelectedAriaLabel` | `'Any seleccionat: {year}'` |
| `yearAriaLabel` | `'Any {year}'` |
| `weekAnnouncementCrossMonth` | `'Setmana del {from} de {month} al {to} de {endMonth} de {year}'` |
| `weekAnnouncementCrossYear` | `'Setmana del {from} de {startMonth} al {to} de {endMonth} de {year}'` |

> Els arrays com `months` o `weekdaysLong` s'han de passar complets: no es fusionen element per element.

#### `callout`

| Clau | Valor per defecte |
|---|---|
| `closeAria` | `'Tancar avís'` |

#### `cardNavigation`

| Clau | Valor per defecte |
|---|---|
| `goToAriaLabel` | `'Go to {text}'` |
| `goToFallbackAriaLabel` | `'Go to '` |

#### `cardNavigationBasic`

| Clau | Valor per defecte |
|---|---|
| `iconAlt` | `'Card Icon'` |

#### `checkbox`

| Clau | Valor per defecte |
|---|---|
| `openOptions` | `"Obrir llista d'opcions"` |
| `closeOptions` | `"Tancar llista d'opcions"` |

#### `chip`

| Clau | Valor per defecte |
|---|---|
| `clearFilters` | `'Neteja els filtres'` |
| `showMore` | `'Mostra més'` |
| `showLess` | `'Mostra menys'` |
| `expandedAnnouncement` | `'Xips expandida'` |
| `collapsedAnnouncement` | `'Xips col·lapsada'` |

#### `contentTree`

| Clau | Valor per defecte |
|---|---|
| `showSublevels` | `'Mostra nivells inferiors'` |
| `hideSublevels` | `'Oculta nivells inferiors'` |

#### `datePicker`

| Clau | Valor per defecte |
|---|---|
| `selectedDaysPlural` | `'{count} días seleccionados'` |
| `selectedDaysSingular` | `'1 día seleccionado'` |
| `selectedDaysZero` | `'0 días seleccionados'` |
| `daysGridAriaLabel` | `'Dies del mes'` |
| `selectMonthAriaLabel` | `'Seleccionar mes. Mes seleccionat {month}'` |
| `monthListAriaLabel` | `'Seleccionar mes'` |
| `selectYearAriaLabel` | `'Seleccionar any'` |
| `yearAriaLabel` | `'Any {year}'` |
| `prevYears` | `'Anys anteriors'` |
| `prevYearsAria` | `'Mostrar anys anteriors'` |
| `nextYears` | `'Anys posteriors'` |
| `nextYearsAria` | `'Mostrar anys posteriors'` |
| `dayAriaLabel` | `'{day} de {month} de {year}'` |

#### `dropdown`

| Clau | Valor per defecte |
|---|---|
| `optionsSelected` | `'{count} opcions seleccionades'` |
| `optionSelected` | `'{count} opció seleccionada'` |
| `resultsPerPage` | `'resultats per pàgina'` |
| `searchPlaceholder` | `'Buscar'` |
| `optionsListAriaLabel` | `"Llista d'opcions"` |
| `clearFilters` | `'Neteja els filtres'` |
| `itemSelected` | `'seleccionado'` |

#### `dropdownButton`

| Clau | Valor per defecte |
|---|---|
| `selectedOption` | `'Opció seleccionada: {option}'` |
| `sheetFallbackTitle` | `'Opciones'` |
| `dropdownAria` | `'{text} Botó desplegable replegat'` |
| `menuOptionsAriaLabel` | `'Opciones del menú desplegable'` |

#### `dropdownMenu`

| Clau | Valor per defecte |
|---|---|
| `ariaLabel` | `'Menú desplegable'` |
| `showMore` | `'Mostra més'` |
| `showLess` | `'Mostra menys'` |
| `closeTooltip` | `'Tancar menú desplegable'` |

#### `dynamicTable`

| Clau | Valor per defecte |
|---|---|
| `noAdditionalContent` | `'No hi ha contingut addicional'` |
| `unknownContentType` | `'Tipus de contingut desconegut'` |
| `actionsAriaLabel` | `'Actions'` |
| `printTitle` | `'Imprimir taula'` |
| `unordered` | `'Sense ordenar'` |
| `ascendingOrder` | `'Ordre ascendent'` |
| `descendingOrder` | `'Ordre descendent'` |
| `rowAria` | `'Fila amb valor {value}, {state}'` |
| `rowSelected` | `'seleccionada'` |
| `rowUnselected` | `'no seleccionada'` |
| `expandRowTooltip` | `'Expandir fila'` |
| `expandRowAria` | `'Mostra o amaga informació addicional de la fila'` |
| `selectRowAria` | `'Selecciona la fila {index}'` |
| `imageAlt` | `'Imatge'` |
| `selectAllAria` | `'Seleccionar totes les files'` |
| `selectAllDescription` | `'Selecciona o desmarca totes les files de la taula'` |
| `tableHeaderAria` | `'Capçalera de la taula'` |
| `tableConfigAria` | `'Opcions de configuració de la taula'` |
| `configButtonsAria` | `'Botons de configuració'` |
| `submenuAria` | `'Submenú de la taula'` |
| `searchFieldAria` | `'Cercar entre les files'` |
| `totalRows` | `'Hi ha un total de {count} {entry}'` |
| `selectedOptionsAria` | `'Opcions seleccionades'` |
| `selectedOptionsText` | `'opcions seleccionades'` |
| `cancelButton` | `"Cancel·la"` |
| `cancelSelectionAria` | `"Cancel·la la selecció d'opcions"` |
| `actionsSelectedAria` | `'Accions per opcions seleccionades'` |
| `filterCategoryAria` | `'Filtrar per la categoria {index}'` |
| `filterColumnPlaceholder` | `'Filtra a tota la columna'` |
| `filterColumnAria` | `'Filtra a tota la columna'` |
| `noOptions` | `'Sense opcions'` |
| `filterColumnLabel` | `'Filtre de la columna {index}'` |
| `clearFilter` | `'Neteja el filtre'` |
| `sortColumnAria` | `'Ordenar columna'` |
| `filterResultsTooltip` | `'Filtra resultats'` |
| `searchRowsTooltip` | `'Cerca entre les files'` |

#### `emptyState`

| Clau | Valor per defecte |
|---|---|
| `imageAlt` | `'No-resultats'` |

#### `featuredCarousel`

| Clau | Valor per defecte |
|---|---|
| `consultInfo` | `'Consulta la informació'` |
| `consultAllInfo` | `'Consulta tota la informació'` |
| `prevTooltip` | `'Anterior'` |
| `nextTooltip` | `'Següent'` |
| `goToSlide` | `'Anar a {index}'` |

#### `fileUploader`

| Clau | Valor per defecte |
|---|---|
| `cancel` | `"Cancel·la"` |
| `cancellationMessage` | `"S'ha cancel·lat la pujada"` |
| `cancelFileAria` | `'Cancel·la la pujada de {fileName}'` |
| `remove` | `'Elimina'` |
| `retry` | `'Torna a pujar'` |
| `uploadFilesAria` | `'Pujar fitxers'` |

#### `filter`

| Clau | Valor per defecte |
|---|---|
| `showMore` | `'Mostra més'` |
| `showLess` | `'Mostra menys'` |

#### `glossary`

| Clau | Valor per defecte |
|---|---|
| `scrollLeftAria` | `'Scroll left'` |
| `scrollRightAria` | `'Scroll right'` |

#### `header`

| Clau | Valor per defecte |
|---|---|
| `logoAlt` | `'Logo de la Generalitat de Catalunya'` |
| `openMenuTooltip` | `'Obrir menú'` |
| `closeMenuTooltip` | `'Tancar menú'` |
| `searchTooltip` | `'Cerca'` |

#### `headerPublic`

| Clau | Valor per defecte |
|---|---|
| `openMenuTooltip` | `'Obrir menú'` |
| `closeMenuTooltip` | `'Tancar menu'` |
| `searchTooltip` | `'Cerca'` |
| `searchOpen` | `'Tanca'` |
| `searchClosed` | `'Cerca'` |
| `mySpacesTitle` | `'Els meus espais'` |
| `closeModalTooltip` | `'Tanca el modal'` |
| `gencatLogoAlt` | `'Logotip de la Generalitat de Catalunya'` |
| `orgLogoAlt` | `"Logotip de l'organització"` |
| `privateArea` | `'Àrea privada'` |
| `scrollLeftTitle` | `'Scroll Left'` |
| `scrollLeftAria` | `'Scroll esquerra'` |
| `scrollRightTitle` | `'Scroll right'` |
| `scrollRightAria` | `'Scroll dreta'` |
| `electronicSite` | `'Seu electrònica'` |
| `weServeYou` | `"T'atenem"` |
| `mySpacesButton` | `'Els meus espais'` |
| `scrollLeftTooltip` | `"Desplaceu-vos cap a l'esquerra"` |
| `languageSelectorAria` | `'Seleccioneu un idioma'` |
| `languageSelectorFallback` | `'Seleccionar'` |

#### `highlightedLink`

| Clau | Valor per defecte |
|---|---|
| `imageAlt` | `"Imatge decorativa d´un enllaç"` |

#### `highlightText`

| Clau | Valor per defecte |
|---|---|
| `quoteAlt` | `'quote'` |

#### `horizontalMenu`

| Clau | Valor per defecte |
|---|---|
| `backButton` | `'Back'` |
| `goBackBreadcrumb` | `'Tornar enrere'` |
| `mySpacesBreadcrumb` | `'Els meus espais'` |
| `mySpacesTitle` | `'Els meus espais'` |
| `menuAriaLabel` | `'Horizontal Menu'` |
| `mobileMenuAriaLabel` | `'Mobile Menu'` |
| `desktopMenuAriaLabel` | `'Desktop Menu'` |
| `scrollLeftTitle` | `'Scroll Left'` |
| `scrollLeftAria` | `'Scroll left'` |
| `scrollRightTitle` | `'Scroll Right'` |
| `scrollRightAria` | `'Scroll right'` |
| `submenuLevel2AriaLabel` | `'Submenu'` |
| `submenuLevel3AriaLabel` | `'Submenu Level 3'` |
| `mySpacesButton` | `'Els meus espais'` |
| `electronicSite` | `'Seu electrònica'` |
| `weServeYou` | `"T'atenem"` |

#### `inputText`

| Clau | Valor per defecte |
|---|---|
| `inputAriaLabel` | `"Camp d'entrada"` |
| `clearTooltip` | `'Esborrar'` |

#### `link`

| Clau | Valor per defecte |
|---|---|
| `externalSuffix` | `'Enllaç extern'` |
| `internalSuffix` | `'Enllaç intern'` |

#### `linkList`

| Clau | Valor per defecte |
|---|---|
| `showMore` | `'Mostra més'` |
| `showLess` | `'Mostra menys'` |
| `showMoreAriaLabel` | `'Mostra més o menys enllaços'` |

#### `modal`

| Clau | Valor per defecte |
|---|---|
| `closeAriaLabel` | `'Close modal'` |

#### `pagination`

| Clau | Valor per defecte |
|---|---|
| `previous` | `'Anterior'` |
| `next` | `'Següent'` |
| `pageSummary` | `'Pàgina {current} de {total}'` |
| `show` | `'Mostra'` |
| `resultsPerPage` | `'resultats per pàgina'` |
| `ariaLabel` | `'Paginación'` |
| `loadMoreAriaLabel` | `'Cargar más resultados'` |
| `resultsSeenOption1` | `'Has vist {seen} resultats de {total}'` |
| `resultsRangeOption2` | `'Resultats del {from} al {to} de {total}'` |
| `ariaLabelDropdown` | `'Seleccionar el nombre de resultats per pàgina'` |
| `pageAria` | `'Pàgina {page}'` |
| `currentPageAria` | `'Pàgina {page}, pàgina actual'` |
| `advancePages` | `'Avançar 3 pàgines'` |
| `retreatPages` | `'Retrocedir 3 pàgines'` |

#### `poi`

| Clau | Valor per defecte |
|---|---|
| `detailTitle` | `'Detall de {title}, finestra emergent.'` |
| `detailTitleScrollable` | `'Detall de {title}, finestra emergent, contingut desplaçable.'` |

#### `progressBar`

| Clau | Valor per defecte |
|---|---|
| `ariaLabel` | `'Progress bar'` |
| `stepAriaLabel` | `'Step {step} is {status}'` |
| `stepCounter` | `'{step} de {total}'` |

#### `radio`

| Clau | Valor per defecte |
|---|---|
| `optionFallback` | `'Opció'` |

#### `searchField`

| Clau | Valor per defecte |
|---|---|
| `searchAriaLabel` | `'Campo de búsqueda'` |
| `clearTooltip` | `'Esborrar'` |
| `resultsAriaLabel` | `'Resultats de cerca'` |
| `searchButtonAria` | `'Buscar'` |
| `searchButtonAriaAlt` | `'Busca'` |
| `searchButtonText` | `'Busca'` |
| `closeModalAria` | `'Cerrar'` |
| `clearSearchAria` | `'Limpiar búsqueda'` |

#### `sheet`

| Clau | Valor per defecte |
|---|---|
| `closeTooltip` | `'Tancar panell emergent'` |

#### `sideMenu`

| Clau | Valor per defecte |
|---|---|
| `hideText` | `'Amaga'` |
| `showAria` | `'Show side menu'` |
| `hideAria` | `'Hide side menu'` |
| `showAriaExpanded` | `'Mostrar menú lateral. Menu lateral contret'` |
| `hideAriaExpanded` | `'Amagar menú lateral. Menu lateral expandit'` |
| `collapseTooltip` | `'Col·lapseu menú'` |

#### `slider`

| Clau | Valor per defecte |
|---|---|
| `valueAnnouncement` | `'Valor actual: {value}. Increment de {step}.'` |
| `minLabel` | `'Valor mínim'` |
| `maxLabel` | `'Valor màxim'` |
| `minCurrentLabel` | `'Valor mìnim actual'` |
| `maxCurrentLabel` | `'Valor màxim actual'` |

#### `spinner`

| Clau | Valor per defecte |
|---|---|
| `loading` | `'Loading'` |
| `loadingWithText` | `'Loading, {text}'` |

#### `statusTracker`

| Clau | Valor per defecte |
|---|---|
| `ariaLabel` | `'Status Tracker'` |
| `showMore` | `'Mostra més estats'` |
| `showLess` | `'Mostra menys estats'` |
| `listExpanded` | `'Llista expandida'` |
| `listCollapsed` | `'Llista col·lapsada'` |
| `statusAriaLabel` | `'Status {name}, {state}'` |
| `completedStatus` | `'Completed status'` |
| `currentStatusAlert` | `'Current status with alert'` |
| `currentStatus` | `'Current status'` |
| `pendingStatus` | `'Pending status'` |
| `expiredStatus` | `'Expired status'` |
| `inProgressStatus` | `'In progress status'` |

#### `stepper`

| Clau | Valor per defecte |
|---|---|
| `sequential` | `'Secuencial'` |
| `done` | `'completado'` |
| `current` | `'paso actual'` |
| `pending` | `'pendiente'` |
| `unknownState` | `'estado desconocido'` |

#### `summaryList`

| Clau | Valor per defecte |
|---|---|
| `showMore` | `'Mostra més'` |
| `showLess` | `'Mostra menys'` |
| `showMoreAriaLabel` | `'Mostra més o menys enllaços'` |

#### `switchComponent`

| Clau | Valor per defecte |
|---|---|
| `ariaLabel` | `'Element'` |

#### `tabBarHorizontal`

| Clau | Valor per defecte |
|---|---|
| `scrollLeftTitle` | `'Scroll Left'` |
| `scrollLeftAria` | `'Scroll Left'` |
| `scrollRightTitle` | `'Scroll Right'` |
| `scrollRightAria` | `'Scroll Right'` |
| `selectTabFallback` | `'Select Tab'` |

#### `tableOfContents`

| Clau | Valor per defecte |
|---|---|
| `onThisPage` | `'En aquesta pàgina'` |

#### `timeline`

| Clau | Valor per defecte |
|---|---|
| `onTime` | `'En termini'` |
| `outOfTime` | `'Fora de termini'` |
| `available` | `'Disponible'` |
| `current` | `'Actual'` |
| `next` | `'Pròxim'` |
| `showMore` | `'Mostra més'` |
| `showLess` | `'Mostra menys'` |
| `showMoreAriaLabel` | `'Mostra més o menys'` |

#### `toast`

| Clau | Valor per defecte |
|---|---|
| `checkIconAlt` | `'Check icon'` |
| `contentAriaLabel` | `'Toast message content'` |
| `messageAriaLabel` | `'Toast message'` |
| `closeTooltip` | `'Tancar notificació emergent'` |

#### `verticalTabs`

| Clau | Valor per defecte |
|---|---|
| `urgentTooltip` | `'Urgent'` |
| `inProgressTooltip` | `'En procès'` |
| `blockedTooltip` | `'Bloquejat'` |
| `completedTooltip` | `'Completat'` |
| `newUpdates` | `'Noves novetats'` |
| `oneUpdate` | `'1 novetat'` |
| `updatesCount` | `'{count} novetats'` |
| `submenuAriaLabel` | `'{text} submenu'` |
| `checkIconAlt` | `'Icona de verificació'` |

#### `videoAudioPlayer`

| Clau | Valor per defecte |
|---|---|
| `unsupportedUrl` | `'URL no soportada.'` |
| `thumbnailAlt` | `'Miniatura del vídeo'` |
| `playAudioAria` | `'Reproducir àudio. {title}'` |
| `playVideoAria` | `'Reproducir vídeo. {title}'` |


### Paquet conversacional (`gencat-conversational`)

#### `avatar`

| Clau | Valor per defecte |
|---|---|
| `loading` | `'Carregant'` |
| `alt` | `"Avatar de l'assistent virtual"` |

#### `backToBottomButton`

| Clau | Valor per defecte |
|---|---|
| `newMessagesAnnouncement` | `"Tens missatges nous. Torna a l'últim missatge"` |
| `announcement` | `"Torna a l'últim missatge"` |
| `newMessagesText` | `'Tens missatges nous'` |
| `tooltip` | `"Torna a l'últim missatge"` |

#### `chatButton`

| Clau | Valor per defecte |
|---|---|
| `ariaFallback` | `'Botó de xat'` |

#### `chatHeader`

| Clau | Valor per defecte |
|---|---|
| `minimizeTooltip` | `'Minimitzar xat'` |
| `closeTooltip` | `'Tancar xat'` |

#### `chatInput`

| Clau | Valor per defecte |
|---|---|
| `attachImage` | `'Adjuntar una imatge'` |
| `attachFile` | `'Adjuntar un fitxer'` |
| `takePhoto` | `'Fer una fotografia'` |
| `singleFile` | `'1 fitxer adjunt'` |
| `multipleFiles` | `'{count} fitxers adjunts'` |
| `micAlertAria` | `"No es detecta cap so. L'enregistrament s'aturarà en {count} segons."` |
| `micAlertPrefix` | `"No es detecta cap so. L'enregistrament s'aturarà en"` |
| `micAlertSuffix` | `'segons.'` |
| `stopRecordingAria` | `'Aturar gravació'` |
| `startRecordingAria` | `'Iniciar gravació de veu'` |
| `recordVoiceTooltip` | `'Gravar veu'` |
| `stopRecordingTooltip` | `'Aturar gravació'` |
| `sendMessage` | `'Enviar missatge'` |
| `moreOptions` | `'Mes opcions'` |
| `attach` | `'Adjuntar'` |
| `addFile` | `'Afegir fitxer'` |
| `close` | `'Tancar'` |
| `deleteFile` | `'Eliminar {fileName}'` |
| `ariaFallback` | `'Chat input'` |
| `optionFallback` | `'Opcio {index}'` |

#### `chatMessage`

| Clau | Valor per defecte |
|---|---|
| `thinking` | `'Pensant'` |
| `agentThinking` | `"L'agent està pensant"` |
| `userSaid` | `'Has dit'` |
| `agentSaid` | `"L'agent ha dit"` |
| `sentMessage` | `'Missatge enviat'` |
| `receivedMessage` | `'Missatge rebut'` |
| `sentImage` | `'Imatge enviada'` |
| `receivedImage` | `'Imatge rebuda'` |
| `sentFile` | `'Fitxer enviat'` |
| `receivedFile` | `'Fitxer rebut'` |
| `defaultImageName` | `'Imatge adjunta'` |
| `defaultFileName` | `'Fitxer adjunt'` |
| `openImage` | `"Obrir imatge {fileName} en un diàleg"` |
| `openFile` | `'Obrir fitxer {fileName}'` |
| `messageFrom` | `'Missatge de {authorName}'` |
| `errorPrefix` | `'Error'` |
| `imageType` | `'Imatge'` |
| `fileType` | `'Fitxer'` |

#### `floatingChatContainer`

| Clau | Valor per defecte |
|---|---|
| `newMessagesAnnouncement` | `"Tens missatges nous. Torna a l'ultim missatge."` |
| `announcement` | `"Torna a l'ultim missatge."` |
| `closeModalTitle` | `'Tanca el xat'` |
| `closeModalDescription` | `"Si tanques el xat s'eliminarà la conversa. Estàs segur que el vols tancar?"` |
| `closeModalConfirm` | `'Tancar el xat'` |
| `closeModalCancel` | `'Continua xatejant'` |

#### `sideChatButton`

| Clau | Valor per defecte |
|---|---|
| `tooltip` | `'En què et puc ajudar?'` |
| `ariaLabel` | `'Botó de xat lateral'` |

#### `sidePanelChat`

| Clau | Valor per defecte |
|---|---|
| `title` | `"Pregunta'm"` |
| `inputPlaceholder` | `'Escriu...'` |
| `newMessagesAnnouncement` | `"Tens missatges nous. Torna a l'ultim missatge."` |
| `announcement` | `"Torna a l'ultim missatge."` |

#### `suggestions`

| Clau | Valor per defecte |
|---|---|
| `ariaLabel` | `'Suggeriment: {suggestion}'` |

> **Nota:** Les claus que contenen `{placeholders}` accepten variables dinàmiques que el component substitueix en temps d'execució. No modifiquis el nom dels placeholders, només el text que els envolta.
