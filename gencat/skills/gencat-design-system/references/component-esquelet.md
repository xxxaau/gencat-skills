# Esquelet (Skeleton)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/27ba9f · Font actualitzada el 2026-03-06 · Extret el 2026-10-28

## Què és i quan usar-lo
Element visual que actua com a marcador de posició mentre es carrega el contingut real d'una pàgina o secció. S'utilitza per simular la forma del contingut pendent de carregar.

El component esquelet és un element visual que actua com a previsualització dels elements mentre es carrega el contingut real d'una pàgina o secció. Simula la forma del contingut pendent de carregar mitjançant blocs grisos amb animació. D'aquesta manera es millora la percepció i l'experiència de càrrega de la pàgina i el seu contingut.

Quan s'utilitza:
- Quan el contingut depèn de dades carregades de forma asíncrona.
- En seccions o pàgines amb temps de càrrega perceptibles (entre 0.5 i 2 segons).
- Per mantenir l'estructura visual mentre es carreguen llistes de resultats, targetes, imatges o perfils.
- Quan es vol evitar un canvi brusc de disseny durant la càrrega.

## Quan NO usar-lo / alternatives
- Quan el contingut es carrega de forma immediata i l'esquelet seria innecessari o confús.
- Si el component interfereix en l'ordre visual o genera distracció.
- En elements petits o amb informació que no canvia (com una etiqueta).
- Segons la durada de la càrrega (vegeu Comportament): menys d'1 segon, no utilitzar esquelets; més de 10 segons, barra de progrés.

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Type | Rectangle / Line / Ellipse / Subheader imatge | - |

Variants Figma: Skeleton [Type = Rectangle].

## Comportament i interacció

### Visualització inicial
- L'esquelet apareix de forma automàtica quan una secció amb contingut dinàmic inicia el procés de càrrega.
- Es mostra al mateix lloc on es renderitzarà el contingut real, mantenint l'estructura i la distribució per evitar canvis de disseny visibles.

### Durada
- L'esquelet desapareix tan bon punt el contingut real està disponible.
- **Menys d'1 segon:** no s'han d'utilitzar esquelets, ja que la càrrega és prou ràpida i poden generar una percepció de parpelleig molest.
- **Entre 2 i 10 segons:** és el rang ideal per utilitzar l'esquelet o l'indicador de càrrega, ja que ajuden a reduir l'ansietat de l'usuari i a millorar la percepció de càrrega i l'experiència de velocitat.
  - **Indicador de càrrega:** recomanat per a càrregues puntuals o mòduls concrets.
  - **Esquelet:** preferible quan es carrega tota la pantalla, ja que dóna una idea anticipada de l'estructura i redueix la càrrega cognitiva.
- **Més de 10 segons:** cal mostrar una barra de progrés amb indicació explícita del temps o estat de càrrega per gestionar millor les expectatives de l'usuari.
- [a verificar: la font situa "Quan s'utilitza" a 0.5–2 s i el rang ideal de durada a 2–10 s; no cobreix explícitament l'interval d'1 a 2 s]

### Interacció
Mentre l'esquelet és visible:
- **No es poden fer accions interactives** (com editar, seleccionar o ordenar si es tracta d'una taula).
- El focus del teclat no pot accedir als components en càrrega.

### Animació
- L'esquelet utilitza una animació suau de tipus "degradat en moviment" per indicar que és una previsualització temporal del contingut.

## Bones pràctiques

Estructura i forma:
- **FER:** mantén la forma i les dimensions del contingut real el màxim possible.
- **NO FER:** no utilitzis blocs grisos genèrics sense sentit visual.
- **NO FER:** no facis canvis bruscos de mida o posició quan es carregui el contingut real.

## Accessibilitat

### Pautes d'accessibilitat del contingut web (WCAG)
- **Contingut ignorat per lectors de pantalla (Nivell A) — 1.1.1 Contingut no textual:** els esquelets actuen com a elements decoratius i no aporten informació significativa. Per tant, han d'estar ocults per a tecnologies d'assistència mitjançant `aria-hidden="true"`. [CAT](https://www.w3.org/Translations/WCAG21-ca/#non-text-content) / [EN](https://www.w3.org/WAI/WCAG21/Understanding/non-text-content.html)
- **No interfereix amb el focus ni amb la navegació per teclat (Nivell A) — 2.1.1 Teclat:** el component no ha de rebre focus ni interferir en l'ordre de navegació per teclat mentre es mostra. Quan es carrega el contingut real, aquest ha de ser fàcilment accessible amb el teclat. [CAT](https://www.w3.org/Translations/WCAG21-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG21/Understanding/keyboard.html)
- **Ordre del focus coherent (Nivell A) — 2.4.3 Ordre del focus:** quan el contingut carregat inclou elements interactius, aquests han de seguir un ordre de focus lògic i coherent per facilitar la navegació per teclat. [CAT](https://www.w3.org/Translations/WCAG21-ca/#focus-order) / [EN](https://www.w3.org/WAI/WCAG21/Understanding/focus-order.html)
- **Reducció de moviment (Nivell AAA) — 2.3.3 Animació a petició:** els esquelets amb animació han de respectar la preferència de l'usuari de reduir moviment. Es pot fer mitjançant la regla CSS `prefers-reduced-motion`. [CAT](https://www.w3.org/Translations/WCAG21-ca/#animation-from-interactions) / [EN](https://www.w3.org/WAI/WCAG21/Understanding/animation-from-interactions.html)

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 4.1.0 | - | 19 maig, 2025 | Disseny i documentació del component |

## Vegeu també
- [Indicador de càrrega](component-indicador-de-carrega.md): representació d'un procés que està en curs.
- [Barra de progrés](component-barra-de-progres.md): mostra l'estat d'avanç d'una tasca, reflectint-ne el progrés en temps real.
- Suport: https://zeroheight.com/38669693e/p/57c57a-suport-i-contacte · https://zeroheight.com/38669693e/p/72240b-preguntes-frequents · https://zeroheight.com/38669693e/p/690b45 · https://zeroheight.com/38669693e/p/342611

> Nota: no hi ha API de component web documentada a la v12.0.0 ni pestanya de codi amb contingut a la font.
