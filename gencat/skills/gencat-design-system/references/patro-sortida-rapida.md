# Sortida ràpida (Quick exit)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/122e0c · Font actualitzada el 2026-05-06 · Extret el 2026-10-28

## Què és i quan usar-lo
El botó de sortida ràpida permet als usuaris abandonar un servei, lloc web o aplicació de forma immediata i segura.

És una funcionalitat dissenyada per garantir la seguretat i privacitat de l'usuari, que li permet tancar o abandonar de manera immediata un lloc web, aplicació o servei digital. Aquesta opció és especialment útil en contextos delicats on l'usuari pot necessitar sortir discretament per protegir la seva intimitat.

### Quan s'utilitza
Utilitzeu aquest patró quan el vostre servei conté informació delicada que, si es revela, podria posar en perill la seguretat o la privacitat de l'usuari. El botó de sortida ràpida està pensat per oferir una forma immediata de sortir del lloc web o aplicació, evitant sospites i reduint riscos en situacions potencialment perilloses.

Especialment rellevant en serveis que ofereixen suport o ajuda en contextos com:
- **Violència domèstica**, on una persona pot estar cercant recursos per deixar una relació abusiva.
- **Violació o agressió sexual**, on la discreció i la protecció de la víctima són fonamentals.
- **Abús infantil** o **negligència**, on un menor o adult pot estar buscant suport o assessorament.
- **Persecució**, **assetjament** o altres formes d'intimidació, on l'usuari podria ser vigilat.
- **Qualsevol altre tipus d'abús** on la revelació d'activitat digital podria provocar represàlies.

Aquest patró no s'ha d'utilitzar de manera genèrica. És exclusiu per a serveis que tracten temes d'alta sensibilitat, on protegir l'usuari és una prioritat crítica. La implementació ha de ser clara, accessible i fàcilment activable, sense generar sospites.

## Quan NO usar-lo / alternatives
El botó de sortida ràpida està pensat exclusivament per a contextos en què l'usuari pot estar en situació de risc, i la seva privadesa i seguretat poden veure's compromeses.

## Anatomia
El component de sortida ràpida està format per diverses parts, cadascuna amb una funció específica orientada a protegir l'usuari en situacions de risc. Figma: `Anatomia`.
1. **Botó principal:** element visible i interactiu que l'usuari pot prémer per abandonar el lloc de manera immediata. Quan s'activa, redirigeix l'usuari a una pàgina segura i genèrica. El lloc web que s'obrirà està pendent de decisió.
2. **Indicació d'activació per teclat:** informa l'usuari que pot activar la sortida ràpida prement la tecla *Mayús (Shift)* tres vegades de forma consecutiva. Mentre l'usuari prem la tecla apareix un indicador visual del nombre de vegades que l'ha premut.
3. **Enllaç de contingut de seguretat:** un enllaç on s'explica com navegar de forma segura (pàgina de contingut de seguretat).

## Comportament
Abans d'implementar el component, cal afegir la sortida ràpida a la pàgina o procés corresponent, i seguir les pautes descrites a continuació per garantir que compleix correctament la seva funció de protecció i discreció.

### Com l'usuari activa la sortida
Dues vies principals d'activació:

| Activació manual amb el botó | Activació per teclat |
|---|---|
| Quan l'usuari fa clic al botó: s'obre una pàgina externa en la mateixa pestanya; el contingut anterior desapareix i es trepitja l'historial, evitant tornar enrere amb el botó de retrocés. | L'usuari pot prémer la tecla *Mayús* (*Shift*) tres cops seguits. El sistema mostra un indicador visual (1, 2, 3) que s'il·lumina progressivament amb cada pulsació. Hi ha un límit de temps de 10 segons per prémer la tecla, entre premuda i premuda. Figma: `Anatomia_passos`. |

### Protecció visual immediata
Quan s'activa el component:
- El contingut anterior es reemplaça de manera instantània, evitant que ningú pugui llegir el que hi havia abans.
- Aquesta acció no esborra l'historial complet del navegador, només evita la navegació enrere immediata.

### Pàgines de suport necessàries
Per completar el patró, cal crear contingut complementari al lloc web.

**Pàgina de contingut de seguretat.** A més del component de sortida ràpida, és essencial oferir als usuaris una pàgina informativa amb recomanacions clares i pràctiques sobre com protegir la seva privacitat en línia. Aquesta pàgina ha de servir com a recurs per ajudar l'usuari a reduir el risc digital, especialment si accedeix a un servei que ajuda en una situació de vulnerabilitat. Els continguts específics poden variar segons el servei i el públic objectiu, però en general ha d'incloure recomanacions bàsiques com:
- **Utilitzar un dispositiu públic o compartit**, com ara un ordinador d'una biblioteca o centre comunitari, per evitar deixar rastres personals.
- **Navegar en mode privat o incògnit.**
- **Esborrar l'historial de navegació, galetes i dades de formularis** després de visitar el lloc. Cal incloure també instruccions específiques per als navegadors més habituals (Chrome, Firefox, Safari, Edge).

Aquest patró no garanteix la protecció total de l'usuari. Tot i que amaga ràpidament el contingut del lloc, hi ha altres formes de control que poden posar en risc les víctimes.

> La pàgina de contingut de seguretat encara no està disponible. Quan estigui finalitzada es publicarà en aquesta pàgina del Sistema de Disseny.

### Adaptació lingüística
El component adapta el text de la tecla segons l'idioma de la pàgina:
- En català i castellà, es mostra *Mayús*.
- En anglès (i altres idiomes), es mostra *Shift*.

Això garanteix que l'usuari entengui fàcilment què ha de prémer, segons l'idioma de navegació.

### Ubicació
- El botó de sortida ràpida se situa sempre sota el panell destacat ([Panell destacat](component-panell-destacat.md)) o els fils d'Ariadna ([Fils d'Ariadna](component-fils-d-ariadna.md)) o la capçalera, en funció dels elements que tingui la pàgina. Figma: `ubicacio`.
- En cas que hagi de conviure amb una barra de pestanyes vertical *fixa (sticky)* ([Barra de pestanyes](component-barra-de-pestanyes.md)), aquesta es posiciona just a sota del component de sortida ràpida, mantenint l'ordre jeràrquic i la visibilitat prioritària del botó. Figma: `sticky`.

### Scroll en punt de tall small
1. El component es mostra per defecte amb tots els seus elements i situat per sota la subcapçalera. Figma: `Scroll 01 - Posició inicial`.
2. Quan l'usuari fa scroll vertical i el component arriba a la part superior de la pàgina, aquest es queda fixat. Figma: `Scroll 02 - Posició superior pas 1`.
3. A partir d'aquest punt, la part informativa fa scroll i només queda fixat el botó. Figma: `Scroll 03 - Posició superior pas 2`.

## Accessibilitat (WCAG)
- **Ús del color (A) 1.4.1:** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. [CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA) 1.4.3:** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA) 1.4.4:** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA) 1.4.11:** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Espaiat del text (AA) 1.4.12:** no es perd cap contingut ni funcionalitat si s'ajusten les propietats següents: alçada de línia (interlineat) de com a mínim 1,5 vegades la mida de la lletra; espaiat entre els paràgrafs de com a mínim dues vegades la mida de la lletra; espaiat entre lletres (tracking) de com a mínim 0,12 vegades la mida de la lletra; espaiat entre paraules de com a mínim 0,16 vegades la mida de la lletra. [CAT](https://www.w3.org/Translations/WCAG22-ca/#text-spacing) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/text-spacing)
- **Teclat (A) 2.1.1:** tota la funcionalitat del contingut es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Focus visible (AA) 2.4.7:** la navegació pels diferents elements interactius mitjançant teclat és visible a través d'un rectangle. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

### Navegació per teclat

| Tecla | Acció |
|---|---|
| Tabulació | Navegació al següent element interactiu |
| Shift + Tabulació | Navegació a l'anterior element interactiu |
| Shift (Mayús) x3 | Activar el botó prement la tecla 3 vegades. |
| Enter | Activar element interactiu |

## Historial de versions

| Versió Figma | Data | Descripció |
|---|---|---|
| 8.2.0 | 27 octubre, 2025 | Disseny: revisió d'estils tipogràfics |
| 8.1.0 | 6 octubre, 2025 | Disseny: s'apliquen tokens a colors de fons i es corregeix el color de l'estat focus |
| 7.0.0 | 28 juliol, 2025 | Disseny i documentació del patró |

## Vegeu també
[Panell destacat](component-panell-destacat.md) · [Fils d'Ariadna](component-fils-d-ariadna.md) · [Barra de pestanyes](component-barra-de-pestanyes.md) · [Botons](component-botons.md)
