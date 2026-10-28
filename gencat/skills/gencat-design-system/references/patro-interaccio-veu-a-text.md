# Interacció veu a text (Voice-to-text interaction)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/10954b · Patró (paquet conversacional) · Font actualitzada el 2026-06-19 · Extret el 2026-10-28

## Què és i quan usar-lo
Patró que defineix la interacció que permet a l'usuari dictar el seu missatge activant el micròfon en lloc d'escriure'l manualment. El sistema captura l'àudio, el transcriu a text en temps real, i permet enviar-lo o editar-lo.

### Quan s'utilitza
- Quan la velocitat o la comoditat d'entrada de text és clau per a l'usuari.
- Quan el flux és llarg i freqüent.
- Quan el contingut a descriure és extens.
- Quan pots assegurar una certa qualitat en la comprensió de l'usuari (text fidedigne).

## Quan NO usar-lo / alternatives
- Quan el producte opera en dominis on la captura d'àudio pot generar desconfiança en l'usuari (salut, finances, legal).

## Anatomia
El patró es mostra en el component de xat conversacional flotant, però aplicaria d'igual forma en la resta de contenidors (pàgina completa o lateral). Figma: Anatomia.

## Comportament i interacció

### Activació del micròfon
En fer clic al botó de micròfon, el botó canvia de micròfon a botó de "stop" per poder aturar l'enregistrament. El botó d'enviament no es modifica i segueix permetent enviar el missatge.

### Adjuntar fitxers
Al seleccionar el botó per adjuntar fitxers o el de fitxers adjunts mentre el botó d'enregistrament està actiu, s'atura la transcripció sense perdre el text transcrit fins al moment i s'activa el botó seleccionat.

### Transcripció en temps real
A mesura que l'usuari parla, el text transcrit apareix progressivament al camp d'entrada. La transcripció és en directe i l'usuari pot veure com es genera mentre parla. Si l'usuari ja havia escrit alguna cosa, el text es manté i el nou text generat per veu apareix just després.

### Edició durant la transcripció
Si l'usuari fa clic sobre el camp d'entrada mentre s'està generant el text, l'enregistrament s'atura automàticament. El text transcrit fins aquell moment es conserva i el camp queda editable.

### Aturada manual
En fer clic al botó d'aturar, l'enregistrament es deté i el text transcrit fins aquell moment es conserva al camp. L'usuari pot editar-lo abans de confirmar l'enviament.

### Silenci perllongat
- Si el sistema no detecta cap so en els primers 5 segons, apareix un missatge d'alerta dins el camp d'entrada.
- Si passats 15 segons segueix sense captar cap so, l'enregistrament s'atura automàticament. En el missatge d'alerta previ s'indicarà el compte enrere des de 10 segons.

### Confirmació i enviament
Un cop aturat l'enregistrament, l'usuari pot revisar i editar el text transcrit abans d'enviar-lo. L'enviament requereix una acció explícita de confirmació; mai s'envia automàticament en transcórrer un determinat temps o detectar un silenci perllongat.

## Bones pràctiques

### Icones
- **FER:** Utilitza la icona de micròfon per la interacció de veu a text.
- **NO FER:** No utilitzis altres icones per a representar aquesta interacció.

### Temps en silenci
- **FER:** Assegura't que apareix la notificació de no detecció de so abans d'aturar l'enregistrament. No ha de tapar informació crítica ni bloquejar accions principals innecessàriament.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG):

- **Orientació (AA)** — 1.3.4. El contingut de l'àrea de text s'adapta a les diferents orientacions de la pantalla, com ara vertical o horitzontal, cosa que permet visualitzar el contingut. [CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Ús del color (A)** — 1.4.1. El color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a diferenciar els diferents estats s'inclouen subratllats, es juga amb la presència de farciment i el gruix de la vora. [CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA)** — 1.4.3. Els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA)** — 1.4.4. Al fer un augment de text al 200% cal assegurar que cap element es talli o sobresurti de pantalla. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Redistribució (AA)** — 1.4.10. Al fer zoom al 400% en Desktop (1280 x 1024 px) cal assegurar que cap element dificulti la lectura o interacció dels elements. [CAT](https://www.w3.org/Translations/WCAG22-ca/#reflow) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/reflow)
- **Contrast d'elements no textuals (AA)** — 1.4.11. Els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A)** — 2.1.1. Tota la funcionalitat del contingut (navegar pels diferents botons) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Ordre del focus (A)** — 2.4.3. Quan l'usuari activa el mode d'enregistrament un cop ha premut el botó de micròfon, el focus es manté en la mateixa posició, però es modifica el botó i el lector anuncia el canvi. L'ordre a seguir és: [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-order) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-order)
  1. Botó d'aturar (per defecte).
  2. Botó d'enviament.
  3. Botó de fitxers adjunts (si n'hi ha).
  4. A partir d'aquí segueix l'ordre establert pel contenidor de xat.
- **Focus visible (AA)** — 2.4.7. La navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- **Nom, funció, valor (A)** — 4.1.2. Usa atributs com `aria-checked` per reflectir l'estat del commutador als lectors de pantalla [a verificar: la font parla de "commutador" en aquest patró]. Si dins dels missatges hi ha text amb format com, per exemple, negreta, aquest es llegirà de forma normal sense indicar elements com asteriscs. Exemple de mala pràctica citat a la font: en ChatGPT, mentre llegeix i hi ha una negreta, va llegint "asterisc, asterisc" abans i després de cada negreta. [CAT](https://www.w3.org/Translations/WCAG21-ca/#name-role-value) / [EN](https://www.w3.org/TR/WCAG21/#name-role-value)
- **Missatges d'estat (AA)** — 4.1.3. [CAT](https://www.w3.org/Translations/WCAG22-ca/#status-messages) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/status-messages.html)
  - **Lectura dels missatges.** Quan l'usuari enviï un missatge, el lector haurà d'informar en veu alta dels estats. Per exemple, si està generant la resposta haurà de dir "s'està generant la resposta". Aquest missatge es repetirà cada 5 segons fins que es generi. Un cop s'ha generat tota la resposta començarà la lectura d'aquesta iniciant amb un "el xat diu". Etiquetes:
    - `role="status"` indica al lector que és una zona d'informació no intrusiva però rellevant.
    - `aria-live="polite"` fa que el lector anunciï el canvi quan no interrompi res important.
    - `aria-atomic="true"` assegura que s'anuncia el missatge complet, no només fragments.
  - **Notificació de no detecció de veu.** S'utilitza com a feedback en temps real quan el micròfon està actiu però no es detecta entrada d'àudio. És un missatge informatiu i contextual que acompanya l'acció de l'usuari mentre grava, sense bloquejar ni interrompre la interacció. A nivell d'accessibilitat, s'ha de marcar com a status, és a dir, amb `role="status"` i preferiblement `aria-atomic="true"`, perquè el lector de pantalla l'anunciï de manera automàtica però sense interrompre el que s'està llegint.

### Lector de pantalla (microcopy anunciat)
- **En activar el micròfon:** el lector ha d'indicar el nou mode i funcionalitat. Per exemple: "Enregistrament activat. Parla ara." i, com hi ha canvi de funcionalitat del botó, també ho ha d'indicar amb "Botó d'aturada, permet editar el text". Així el lector comunica l'estat nou, dona la instrucció d'acció i indica quin és el botó principal en aquest mode.
- **Quan apareix l'avís de silenci:** als 5 segons es mostra l'avís i s'ha d'anunciar "No es detecta cap so. S'aturarà l'enregistrament en 10 segons"; si encara no detecta so, tornarà a repetir el mateix missatge als 5 segons: "No es detecta cap so. S'aturarà l'enregistrament en 5 segons".
- **Quan s'atura per silenci:** "L'enregistrament s'ha aturat per falta de so." Seguit del focus al camp d'entrada o al botó de confirmar si hi ha text transcrit. (El text de la font està truncat: "Quan han transcorregut el…" [a verificar].)
- **En aturar manualment:** "Enregistrament aturat. Pots editar el text".

## Components implicats
- [Contenidor de xat](component-contenidor-de-xat.md): per donar estructura.
- [Camp d'entrada de xat](component-camp-d-entrada-de-xat.md): per enviar missatges.

## Historial de versions
| Versió Figma | Data | Descripció |
|---|---|---|
| 5.1.0 | 19 juny, 2026 | Disseny i documentació del patró |

## Vegeu també
[Xat flotant](patro-xat-flotant.md), [Xat a pantalla completa](patro-xat-a-pantalla-completa.md), [Xat lateral](patro-xat-lateral.md), [Missatge de xat](component-missatge-de-xat.md).
