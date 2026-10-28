# Notificacions (Notifications)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/41b40a · Patró · Font actualitzada el 2026-06-19 · Extret el 2026-10-28

## Què és i quan usar-lo
El patró de notificacions permet informar l'usuari sobre novetats, avisos o canvis rellevants relacionats amb la seva activitat dins d'un entorn logat. S'utilitza per mostrar avisos, novetats o actualitzacions que l'usuari ha de poder consultar dins d'un entorn logat.

Permet oferir una vista ràpida de les notificacions recents o no llegides i, alhora, una pàgina completa on revisar l'historial, aplicar filtres i gestionar l'estat de lectura quan sigui necessari.

### Quan s'utilitza
- Quan cal informar l'usuari sobre novetats, avisos o canvis d'estat relacionats amb la seva activitat.
- Quan les notificacions han de quedar disponibles perquè l'usuari les pugui consultar més endavant.
- Quan cal agrupar en un únic espai notificacions de diferents tràmits, expedients, sol·licituds o processos.
- Quan cal diferenciar entre notificacions llegides i no llegides.

## Quan NO usar-lo / alternatives
- Quan el missatge requereix una acció immediata o té un nivell d'urgència alt. En aquest cas, utilitza una alerta, un avís o un modal ([Avisos](component-avisos.md), [Modals](component-modals.md)).
- Quan es tracta d'un error o validació d'un formulari. Aquests missatges han d'aparèixer en el context del camp o bloc corresponent.
- Quan la informació només té sentit dins d'una pàgina o moment concret i no cal conservar-la com a notificació consultable.
- Quan només cal confirmar una acció puntual, com ara que un canvi s'ha desat correctament.
- Quan el contingut és promocional, publicitari o no està vinculat al servei.

## Anatomia

### En desplegable
1. **Capçalera**: mostra el títol del desplegable, com ara **Notificacions**.
2. **Comptador**: indica el nombre de notificacions no llegides, si és necessari.
3. **Llistat de notificacions**: mostra una selecció limitada de notificacions (entre 3 i 5, evitant desplaçament), ordenades de més recent a més antiga.
4. **Notificació**: cada element del llistat inclou títol, data i tipus de notificació.
5. **Prioritat**: etiqueta opcional que indica si una notificació requereix atenció preferent.
6. **Accés a la pàgina completa**: acció que porta a l'historial complet de notificacions.
7. **Estat buit**: missatge que s'utilitza quan no hi ha notificacions recents o no llegides per mostrar.

### En pàgina de notificacions

**Pàgina**
1. **Selecció:** permet seleccionar una o diverses notificacions per aplicar accions en bloc sense modificar-ne l'estat directament.
2. **Etiquetes:** ajuden a identificar ràpidament la prioritat i el tipus de notificació.
3. **Data:** indica quan s'ha generat o rebut la notificació.
4. **Títol:** comunica el motiu principal de la notificació.
5. **Descripció:** complementa el títol amb informació de context o següents passos.
6. **Metadades:** agrupen dades de context, com fase, venciment, expedient o estat de lectura.
7. **Estat de lectura:** informa textualment si la notificació està llegida o no llegida.

**Taula.** En la variant de taula, cada notificació es representa com una fila. Les columnes poden incloure:
- **Selecció**: checkbox per seleccionar una o diverses notificacions.
- **Motiu**: títol principal de la notificació i, si cal, una línia de context.
- **Tipus**: categoria funcional de la notificació.
- **Prioritat**: indica si requereix atenció preferent.
- **Estat**: indica si la notificació està llegida o no llegida.
- **Venciment**: data límit associada, si existeix.
- **Data**: moment en què s'ha generat o rebut la notificació.

La fila pot ser desplegable si cal mostrar informació addicional sense sobrecarregar la taula. El contingut desplegat pot incloure la descripció completa, l'expedient, la fase, el servei o altres metadades relacionades.

## Comportament i interacció
El comportament del patró es divideix en tres parts:
- **Icona de notificacions a la capçalera**, que informa de si hi ha notificacions pendents amb la insígnia.
- **Desplegable de notificacions**, que mostra una vista ràpida de les notificacions noves o no llegides.
- **Pàgina de notificacions**, que permet consultar l'historial complet i gestionar l'estat de lectura.

### Desplegable de notificacions
El desplegable s'obre des de la icona de notificacions de la capçalera i funciona com una vista ràpida. Ha de mostrar una selecció limitada de notificacions no llegides o noves, ordenades de més recent a més antiga. Es recomana mostrar un màxim de 3 a 5 notificacions per evitar que el desplegable sigui massa llarg i evitant scroll (desplaçament).

Si hi ha més notificacions no llegides de les que es mostren al desplegable, l'usuari ha de poder accedir a la pàgina completa mitjançant el botó "Veure totes les notificacions".

Si no hi ha notificacions no llegides, el desplegable ha de mostrar un estat buit breu ([Estat buit](component-estat-buit.md)).

El desplegable no substitueix la pàgina completa de notificacions. Només ofereix una consulta ràpida de les notificacions pendents.

### Pàgina de notificacions
Funciona com un historial complet. Ha de permetre consultar notificacions llegides i no llegides, navegar entre pàgines, aplicar filtres i gestionar l'estat de lectura quan sigui necessari. Per defecte, es recomana mostrar les notificacions en format de llistat compacte, ordenades de més recent a més antiga. Aquest format facilita la lectura del contingut, la comprensió del context i l'escaneig ràpid de notificacions amb títol, descripció i metadades bàsiques.

La pàgina pot incloure:
- Recompte total de notificacions.
- Nombre de notificacions no llegides.
- Filtres/ordenació per estat, tipus, prioritat o data.
- Acció per marcar totes les notificacions no llegides com a llegides a partir de la casella de selecció.
- Paginació.
- Selector de resultats per pàgina.
- Acció per gestionar les preferències de notificacions.

#### Format de taula
En casos d'ús més orientats a la gestió, la pàgina pot adoptar un format de **taula dinàmica** ([Taules dinàmiques](component-taules-dinamiques.md)). És adequat quan l'usuari necessita comparar notificacions, ordenar-les, filtrar-les o gestionar-les de manera més operativa. La taula permet mostrar la informació en columnes i facilita la lectura transversal de dades com el tipus, l'estat, la prioritat, la data o el venciment.

La taula és recomanable quan:
- Hi ha un volum elevat de notificacions.
- Cal comparar notificacions entre si.
- L'usuari necessita ordenar o filtrar per camps concrets.
- Cal mostrar metadades de manera estructurada.
- Es vol permetre una gestió més explícita, com seleccionar diverses notificacions i aplicar accions en bloc.

Incorpora una columna de selecció amb checkbox (casella de selecció) i una barra d'accions contextual quan hi ha notificacions seleccionades. El checkbox només ha de servir per seleccionar files, no ha de canviar directament l'estat de lectura.

Exemple de comportament:
1. L'usuari selecciona una o diverses notificacions.
2. Apareix una barra contextual amb el nombre de notificacions seleccionades.
3. L'usuari pot aplicar una acció en bloc, com "Marcar com a llegides".
4. Les notificacions seleccionades actualitzen el seu estat després de confirmar l'acció.

### Adaptació responsiva
- En escriptori, el desplegable de notificacions es mostra com una capa flotant vinculada a la icona de la capçalera.
- En mòbil, aquest comportament s'adapta a un bottom sheet (panell emergent inferior), mantenint el mateix contingut essencial: títol, notificacions recents o no llegides, estat buit i accés a la pàgina completa.
- La pàgina de notificacions s'ha d'adaptar a una visualització vertical, prioritzant la lectura del contingut. Les metadades es reorganitzen en línies secundàries i les accions han de mantenir-se properes a la notificació corresponent.

### Comportament de la selecció
La selecció de notificacions permet aplicar accions en bloc sobre una o diverses notificacions.
- Quan no hi ha cap notificació seleccionada, es mostra l'opció "Seleccionar totes".
- Quan l'usuari selecciona una o més notificacions, la barra de selecció mostra el nombre d'elements seleccionats i l'acció disponible. Exemple: 1 notificació seleccionada = "Marcar com a llegida"; 3 notificacions seleccionades = "Marcar com a llegides".
- L'acció "Marcar com a llegides" només afecta les notificacions seleccionades que estiguin en estat "No llegida". Les notificacions que ja estan llegides no canvien d'estat.
- El checkbox de selecció no ha de modificar l'estat de lectura per si mateix.

### Insígnia de notificacions
La icona de notificacions de la capçalera pot incorporar una insígnia numèrica per indicar el nombre de notificacions no llegides ([Insígnia](component-insignia.md)).
- La insígnia només ha de comptabilitzar notificacions pendents de lectura. No ha d'incloure notificacions llegides ni el total de notificacions de l'historial.
- Obrir el desplegable no marca automàticament les notificacions com a llegides ni fa desaparèixer la insígnia. La insígnia només s'actualitza quan canvia l'estat de lectura de les notificacions.

### Dates de les notificacions
Les notificacions recents poden mostrar una data relativa. Les notificacions antigues han de mostrar una data absoluta. Criteris recomanats:
- Menys d'1 hora: fa 5 min
- Avui: fa 3 hores
- Ahir o últims dies: ahir o fa 2 dies
- Més d'una setmana: 12/06/2026 o 12 juny 2026

Cal mantenir un format coherent dins del mateix llistat, tant de la pàgina de notificacions com del desplegable.

### Prioritat
Una notificació pot tenir prioritat quan requereix atenció preferent. La prioritat és independent de l'estat de lectura: una notificació pot ser prioritària i llegida, o prioritària i no llegida. S'ha de representar amb una etiqueta textual, com ara "Prioritària", i es pot reforçar visualment amb color taronja ([Etiquetes](component-etiquetes.md)).

### Tipus de notificació
Les notificacions poden incorporar una etiqueta de color neutral per ajudar l'usuari a identificar ràpidament la naturalesa del missatge. El tipus ha de descriure l'origen o la categoria funcional de la notificació, no el seu estat. Per exemple:
- Expedient
- Documentació
- Comunicació
- Termini
- Assignació
- Sistema

El tipus no s'ha de confondre amb altres estats de la notificació, com No llegida, Llegida o Prioritària. Es recomana mostrar el tipus quan ajuda a escanejar el llistat, aplicar filtres o entendre el context de la notificació. Si totes les notificacions d'una vista són del mateix tipus, es pot ometre per evitar informació repetida.

## Bones pràctiques

### Claredat i qualitat del contingut
- **FER:** Redacta notificacions clares i específiques, perquè l'usuari entengui ràpidament què ha passat o què ha canviat.
- **NO FER:** No utilitzis títols genèrics com "Nova notificació" o "Avís" si no aporten informació suficient.
- **FER:** Utilitza un títol descriptiu que resumeixi el motiu de la notificació entre 70 i 90 caràcters.
- **FER:** Afegeix una descripció només quan calgui aportar context o explicar el següent pas, entre 180 i 250 caràcters.

### Jerarquia i lectura del llistat
- **FER:** Mostra primer les notificacions més recents.
- **NO FER:** No acumulis notificacions repetides o redundants que dificultin la lectura del llistat.
- **FER:** Diferencia en les metadades les notificacions llegides i no llegides.
- **FER:** Les etiquetes s'han d'ordenar segons la seva rellevància funcional. Primer la prioritat, quan existeixi, i a continuació el tipus de notificació (Expedient, Documentació...).

### Coherència i accions del patró
- **FER:** Mantén un comportament coherent entre el desplegable de la capçalera i la pàgina de notificacions.
- **FER:** Inclou accions globals, com marcar-ho tot com a llegit, només quan siguin útils i estiguin justificades.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG):

- **Orientació (AA)** — 1.3.4. El contingut de l'àrea de text s'adapta a les diferents orientacions de la pantalla, com ara vertical o horitzontal, cosa que permet visualitzar el contingut. [CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Ús del color (A)** — 1.4.1. El color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a diferenciar els diferents estats s'inclouen subratllats, es juga amb la presència de farciment i el gruix de la vora. [CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA)** — 1.4.3. Els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA)** — 1.4.4. Excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Redistribució (AA)** — Al fer zoom al 400% en Desktop (1280 x 1024 px) cal assegurar que cap element dificulti la lectura o interacció dels elements. Per aquest motiu, la part inferior del desplegable quedarà sticky (fixa) i la resta farà scroll (desplaçament).
- **Contrast d'elements no textuals (AA)** — 1.4.11. Els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A)** — 2.1.1. Tota la funcionalitat del contingut (navegar pels diferents botons) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Focus visible (AA)** — 2.4.7. La navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

## Components implicats
[Insígnia](component-insignia.md), [Etiquetes](component-etiquetes.md), [Casella de selecció](component-casella-de-seleccio.md), [Taules dinàmiques](component-taules-dinamiques.md), [Paginació](component-paginacio.md), [Estat buit](component-estat-buit.md), [Panell emergent](component-panell-emergent.md) (bottom sheet en mòbil), [Filtres](component-filtres.md).

## Historial de versions
| Versió Figma | Data | Descripció |
|---|---|---|
| 12.1.0 | 17 de juny, 2026 | Disseny i documentació del patró |

## Vegeu també
Ajuda: [Suport i contacte](suport-suport-i-contacte.md), [Preguntes més freqüents](sobre-preguntes-mes-frequents.md), [Sol·licituds](suport-sollicituds.md), [Guies d'ús](sobre-guies-d-us.md).
