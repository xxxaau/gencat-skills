# Introducció al Sistema de Disseny: onboarding disseny-desenvolupament 2025-2026

> Font: presentació "Sistema de Disseny de la Generalitat de Catalunya. Onboarding Disseny - Desenvolupament 2025 - 2026" (Introducció SD.pdf, adjunt de [Sobre el sistema de disseny](sobre-sobre-el-sistema-de-disseny.md)) · Extret el 2026-10-28

Presentació d'onboarding per a equips de disseny i desenvolupament. Seccions: 1 Context; 2 Eines de disseny (2.1 Organització del Figma, 2.2 Llibreries i arxius de disseny); 3 Eines de desenvolupament (Repositori Git); 4 Canals de consulta i col·laboració. Contacte final: sistemadedisseny@gencat.cat.

## 1. Context

### Què és un sistema de disseny: què és el SDGC
És el sistema de disseny corporatiu de la Generalitat de Catalunya que actua com a referent d'obligat compliment en el disseny de nous webs del govern adreçats a la ciutadania i també en noves aplicacions d'ús intern.
L'objectiu del sistema de disseny és unificar les pràctiques de disseny i assegurar una coherència en tots els productes digitals. També simplifica la feina dels equips de disseny i desenvolupament, proporcionant-los eines i recursos clars per agilitzar els processos de treball. I a més és clau per garantir una comunicació clara i eficaç entre els equips.
(La diapositiva mostra un exemple visual de components amb enllaços d'interès, com "Demana hora", "Adreça i horari de l'OAC", "Què estem fent al territori", "Consum d'aigua", "Mostra més enllaços", i metadades "Nivell", "Pàgina actual", "Sistema de Disseny", "Versió 7.0.0", "Llibreria".)

### Principis del SDGC
El sistema de disseny es fonamenta en tres principis clau que responen a les necessitats en evolució dels ciutadans.
- **Ho fem fàcil:** es basa en la simplificació d'elements i la seva reutilització per guiar l'usuari mitjançant inputs visuals que el guiïn durant la seva experiència.
- **Proximitat i empatia:** l'enfocament transcendeix la mera implementació de tràmits digitals; es dissenyen serveis integrals que se centren en l'experiència de l'usuari, posant les seves necessitats i desitjos al capdavant de cada decisió, respectant els estàndards d'accessibilitat.
- **Flexibilitat i evolució:** el concepte visual en serveis públics redefineix la relació entre treballadors i ciutadans, prioritzant flexibilitat, evolució contínua i adaptabilitat per respondre eficientment als canvis socials i dispositius tecnològics.

Vegeu [Principis de disseny](sobre-principis-de-disseny.md).

### El web de SDGC
Tota la informació sobre el sistema de disseny (principis, com funciona per a dissenyadors i desenvolupadors, llistat de components i patrons, informació sobre les actualitzacions de la llibreria de disseny i la versió del repositori a Github) es troba al web oficial del SDGC, sistemadedisseny.gencat.cat.

### Marc tecnològic
Es fa servir Stencil.js (v4.7), un compilador per crear components web reutilitzables i altament optimitzats, escrits amb sintaxi moderna de TypeScript i JSX.
No és un marc tecnològic tradicional, sinó una eina lleugera que genera components estàndard compatibles amb qualsevol marc tecnològic o projecte (React, Angular, Vue i d'altres). El seu enfocament permet desenvolupar llibreries escalables, amb escriptura forta, i aprofitar funcionalitats com lazy loading, server-side rendering i pre-rendering.

**Què són els components web?** Són una tecnologia nativa del navegador que permet crear components d'interfície encapsulats, reutilitzables i de fàcil manteniment sense dependre de marcs tecnològics específics. Es basen en quatre especificacions clau:
- **Custom Elements:** defineixen nous elements HTML personalitzats amb el seu propi comportament.
- **Shadow DOM:** permet encapsular l'estil i el comportament, evitant conflictes amb la resta de la pàgina.
- **HTML Templates:** possibiliten definir estructures HTML reutilitzables.
- **ES Modules:** afavoreixen la modularitat i reutilització de codi.

Gràcies als components web es poden construir interfícies consistents i fàcils d'integrar en qualsevol projecte, mentre Stencil.js simplifica la seva creació i optimització.

## 2. Eines de disseny

### 2.1 Organització del Figma

#### Gestió de seients
- El Figma de la Direcció General de Serveis Digitals i Experiència Ciutadana (DGSEC) disposa de 25 seients amb permís Full. Per tant els seients es limiten a dissenyadors que treballin amb l'eina en el seu dia a dia.
- Cada proveïdor que entri a treballar en aquest entorn tindrà 2 seients disponibles, que podran editar i treballar amb Figma; la resta només tindrà permisos de visualització.
- Si l'equip de dissenyadors d'un proveïdor és de més de 2 persones, es recomana crear un compte genèric que es pugui utilitzar de forma col·lectiva.

#### Estructura del nou espai de Figma
Jerarquia: Organització > Equip > Projecte > Arxiu. (Diagrama de la font: l'organització DGSEC conté equips com "Sistema de Disseny" (projecte "Llibreria del Sistema de Disseny" amb els arxius SDGC - Llibreria, SDGC - Recursos, SDGC - Fonaments), "AEM - Gencat.cat" (projecte "Web gencat.cat" amb arxius Disseny UX/UI, Llibreria composicions, Main), "Agència Tributària" i d'altres; projectes d'exemple: Concepte, Web agenda.cultura, Projecte X.)

#### Equips
Dins del Figma DGSEC hi ha:
- **Equips:** alguns equivalen a productes digitals de la DGSEC que són transversals a totes les organitzacions, com per exemple Sistema de Disseny o Gencat.cat (AEM). Altres equivalen a organitzacions concretes que són agregadores de diversos projectes, per exemple ATC.
- Per norma general, tots els equips són visibles, però els accessos als equips són privats i només es donen permisos als usuaris que hi treballen.
- Manera correcta de nomenar un equip:
  - A) Nom del producte - detalls si escauen. Ex: Gencat.cat - AEM
  - B) Nom de l'organització (abreviatura si escau). Ex: Agència Tributària de Catalunya (ATC)
- Els administradors de l'organització s'encarreguen de crear els equips.
- Els administradors de l'equip s'encarreguen de donar l'alta i la baixa als diferents usuaris. Si interessa que els usuaris puguin veure tots els projectes, es compartirà l'accés des de l'equip; si no interessa, es compartirà l'accés només al projecte concret.

#### Projectes
- **Projectes:** són els projectes que es realitzen dins de cada producte digital de la DGSEC. En aquest àmbit hi poden haver un o més proveïdors treballant.
- Manera correcta de nomenar un projecte: utilitzar el nom més comú i intuïtiu: Nom del proveïdor i nom del projecte. Ex: Capgemini - Transformació Web.

#### Estructura del projecte
Cada equip pot estructurar el seu projecte de forma diversa, sobretot si hi ha projectes on estan involucrats més d'un proveïdor. Tot i així, es recomana que com a mínim el projecte contingui 3 arxius rellevants:
1. **Main**
2. **Flux funcional o concepte**
3. **Arxiu de disseny UX/UI**
- Arxius addicionals: llibreria de components específics, presentacions.

En general l'accés a aquests arxius està restringit i només es permet l'edició mitjançant invitació. D'aquesta manera es mantenen els arxius de treball o les proves en mode privat.
L'arxiu **Main** és el que conté només els dissenys o prototips validats i finals que es comparteixen amb el client i amb altres equips.
(Exemple visual de la font: arxius "Main", "Concepte" i "Llibreria composicions" del projecte "Transformació Web Gencat.cat", de Generalitat de Catalunya, amb estats com "Feedback", "Disseny", "Completat", "En procés" i tipus "Concepte", "Llibreria".)

Vegeu també [Organització de Figma](figma-organitzacio-de-figma.md) i [Estructuració d'arxius](figma-estructuracio-d-arxius.md).

### 2.2 Llibreries i arxius de disseny

#### Llibreries i arxius de SD
Sistema de Disseny treballa en el disseny de components transversals a totes les experiències digitals de la Generalitat de Catalunya. Els components són tant d'àmbit de web pública (de cara al ciutadà) com d'àmbit de gestió interna (més pensada per als gestors). Actualment hi ha tres llibreries (*):
- **SDGC - Fonaments:** conté el que està relacionat amb els estils: marca, colors, tipografies, punts de tall, criteris d'imatge, etc.
- **SDGC - Llibreria:** conté tots els components i també els patrons.
- **SDGC - Components conversacionals:** conté els components d'interfície conversacional amb assistent virtual.

A més, l'equip de SD també treballa en el disseny d'exemples d'ús (mostra de pàgines estàndard del lloc web gencat.cat) i en recursos de disseny que ajuden els consumidors a treballar més eficientment en els seus dissenys.
(*) S'està treballant en una tercera llibreria de components d'interfície conversacional i de contingut generatiu per a la intel·ligència artificial. [a verificar: la mateixa diapositiva ja enumera tres llibreries, i la nota parla d'una "tercera"]

#### Com utilitzar les llibreries
Per utilitzar de forma òptima la SDGC - Llibreria:
- Utilitza el panell d'Assets i cerca el component o icona que necessitis.
- Escull el tipus de variant que et convingui per mida de disseny i activa o desactiva les propietats booleanes.
- No desvinculis ("detach") el component.
- No copiïs ni enganxis el component d'una llibreria a un arxiu de disseny on treballes per tenir-lo de forma local.
- No modifiquis les variables de color, estils i efectes que té aplicats.
- Si utilitzes estils tipogràfics o variables de color o de mida per a dissenys teus que no siguin components, cerca al panell lateral dret de disseny a "Typography" o a "Fill" i cerca dins de SDGC - Fonaments els que necessitis.

Vegeu [Llibreries](figma-llibreries.md).

#### Actualitzacions de la SDGC - Llibreria
Fins ara les actualitzacions de les llibreries es duien a terme de forma periòdica cada mes, ja que es produïen components nous recollits al backlog. Depenent de les necessitats dels projectes i de la velocitat amb què es facin els components, aquesta periodicitat es pot veure afectada.

**Com funcionen les versions?**
- El **primer número** indica un canvi de fonament que afectarà la base de molts components de la llibreria (si no tots). Per exemple, s'ha afegit un color nou, s'ha modificat un estil tipogràfic.
- El **segon número** indica un canvi mitjà: afegir un component nou, o fer un evolutiu o millora en el disseny d'un component existent.
- El **tercer número** indica un canvi menor o ajustament a algun dels components.

#### Com actualitzar
- Un cop la llibreria és afegida a l'arxiu de treball, cada vegada que l'equip de SD publiqui una actualització apareixerà una notificació emergent que n'informa.
- Es recomana fer les actualitzacions de manera regular i immediata: com més temps es deixi sense actualitzar l'arxiu de treball, més risc hi haurà que les actualitzacions impactin sobre més elements o provoquin canvis inesperats als dissenys.
- En prémer el botó d'actualitzar, el panell que es mostra a continuació indica unes notes de publicació del que conté l'actualització.

#### Estructura de l'arxiu de disseny UX/UI
Els equips de disseny que treballen en el disseny d'un producte digital han d'estructurar de forma clara i organitzada els seus arxius de disseny. L'estructura recomanada consisteix en diferents seccions:
- **Portada:** pàgina que inclou la miniatura o portada que identifica l'arxiu.
- **Dissenys:** dissenys finalitzats; dissenys en procés.
- **Inspiració (Playground):** grup de pàgines que pot incloure inspiracions i referències d'altres webs, estudis d'analítica i d'investigació d'usuari, fluxos, etc.
- **Brossa (Archived):** una o més pàgines per arxivar els dissenys que hagin estat descartats durant el procés.

Si escau, es poden afegir més seccions, com per exemple de requeriments funcionals o de context de projecte.

#### Ús de portades
La portada serveix com a miniatura de l'arxiu i és l'element que indica principalment el tipus d'arxiu i l'estat del treball. Depenent del tipus d'arxiu s'utilitzarà una portada o una altra. Elements de la portada (numerats a la diapositiva):
1. **Organització o client:** sempre ha de figurar l'isologotip i el nom de Generalitat de Catalunya.
2. **Proveïdor:** l'isologotip del proveïdor que està treballant a l'arxiu.
3. **Nom de l'arxiu:** de quin tipus de treball es tracta. Si es vol referenciar dos conceptes es pot utilitzar un guió. Ex: Tràmits - Concepte.
4. **Nom del projecte:** Gencat.cat, GDT, etc.
5. **Estat de l'arxiu:** indica en quin estat es troba. Es pot escollir entre: en procés, completat, pausat, arxivat, preparat per dev, feedback.
6. **Canal:** icona que representa el canal pel qual s'està dissenyant. A escollir entre: lloc web, aplicació o dashboard.
7. **Tipus d'arxiu:** es pot escollir entre llibreria, disseny, concepte i presentació.
8. **Versió:** no sempre és necessària, però es pot indicar la versió de l'arxiu (1.0, 2.0, 3.0).
(Exemple de la font: "Generalitat de Catalunya / Sistema de disseny / Nom projecte / V.1.0 / En procés / Llibreria".) [a verificar: l'assignació exacta de cada número als elements de la imatge no és recuperable del text; es manté l'ordre de la llista de la font]

#### Ús de changelog
És important tenir un històric dels canvis fets en un arxiu de disseny. Aquests canvis es poden monitorar des del panell de versió històrica ("version history") i cada vegada que s'edita l'arxiu es pot crear una nova fita concreta. Si es vol fer de forma més visual sense utilitzar aquest panell, es recomana l'ús del Changelog, que conté:
- **Versió:** número de versió de l'arxiu si segueix algun sistema de versionat segons publicació o temps d'entrega; si no cal, es pot eliminar.
- **Nom autor:** el/la responsable que ha fet els canvis a l'arxiu.
- **Títol:** títol del canvi de disseny que s'ha fet.
- **Etiqueta:** indica el tipus de canvi fet. Ex: nou component, ajustament i evolutiu en el cas del disseny de components.
- **Descripció:** text descriptiu del canvi de disseny realitzat.
- **Data:** quan s'ha realitzat el canvi.
Estructura de la plantilla: capçalera "Changelog / Versió 0.0.0" i, per cada entrada: Nom de l'autor, Data, Títol, Etiqueta, Descripció.

## 3. Eines de desenvolupament

### Repositori Git

#### Accedir al repositori codificat
El projecte està allotjat a GitHub, cosa que permet centralitzar el codi, controlar versions i col·laborar de manera organitzada.

**Com sol·licitar accés** (seguint els passos de la documentació oficial al web del sistema de disseny). En resum:
1. Obtenir el codi GICAR (vegeu [Com saber el teu codi intern de GICAR](sobre-com-saber-el-teu-codi-intern-de-gicar.md)).
2. Enviar el codi GICAR per correu a sistemadedisseny@gencat.cat sol·licitant accés al repositori.
3. Esperar que l'equip del sistema de disseny concedeixi l'accés.
4. Crear un compte a GitHub utilitzant l'usuari GICAR, i així es tindrà accés complet al repositori.

Vegeu [Accessos](suport-accessos.md) i [Github](suport-github.md).

#### Actualitzacions: com es gestionen les versions
- Aproximadament cada 3 setmanes es pugen noves versions de la llibreria amb actualitzacions i millores.
- Les actualitzacions es reflecteixen a la secció Releases de GitHub i a l'arxiu README del projecte.
- Des de GitHub es pot: consultar l'historial complet de versions de la llibreria; obtenir el comandament d'instal·lació corresponent per utilitzar la versió desitjada; revisar issues i pull requests per seguir el progrés i la col·laboració de l'equip; clonar el repositori i treballar de manera local de manera ordenada, garantint que sempre es disposi de la versió més recent del projecte.
- GitHub no només centralitza el codi, sinó que també ofereix transparència i control sobre el desenvolupament, facilitant la col·laboració entre tots els membres de l'equip.

#### Visualització dels components
- **Storybook** és una eina que permet visualitzar i provar els components de forma aïllada, sense necessitat d'aixecar tota l'aplicació. Això facilita tant el desenvolupament com la revisió de la interfície, ja que cada component es pot veure, documentar i testar per separat.
- Perquè disseny i client també hi puguin accedir fàcilment, s'utilitza **Chromatic**, una plataforma que allotja el Storybook públic. Així, qualsevol persona amb accés pot explorar els components actualitzats des de qualsevol lloc, sense instal·lar res localment.
- Cada usuari només necessita crear-se un compte a Chromatic i accedir al projecte. Un cop dins, podrà visualitzar els components en un Storybook allotjat de manera "pública" per a l'equip. Això assegura que tothom vegi el mateix estat dels components i pugui donar feedback de manera senzilla.

## 4. Canals de consulta i col·laboració

### Canals de consulta, incidències i peticions
- L'equip de Sistema de Disseny posa a disposició dels projectes consumidors una bústia de suport, sistemadedisseny@gencat.cat, on es responen a diari les consultes, dubtes i incidències.
- Per demanar accés tant al nou espai de Figma com a Github també cal fer-ho des de la bústia de suport.
- També s'organitzen sessions UX cada 3 setmanes on s'informa de les últimes actualitzacions de les llibreries de disseny i que és l'espai on els dissenyadors seran assessorats sobre l'ús adequat dels components.

Vegeu [Suport i contacte](suport-suport-i-contacte.md).

### Registre de feedback i nous components
- Com que els arxius estan limitats als usuaris convidats, els comentaris queden molt restringits als dissenyadors que hi treballen. La recomanació és tancar-los sempre un cop es resolguin.
- Si algun dissenyador de projecte té la necessitat de sol·licitar un component nou que no existeix a la llibreria, pot enregistrar la sol·licitud a l'arxiu "Registre components nous" i l'equip de SD ho avaluarà en la propera sessió UX.

Contacte: sistemadedisseny@gencat.cat
