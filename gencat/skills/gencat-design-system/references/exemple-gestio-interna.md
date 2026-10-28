# Gestió interna (exemple d'ús, back-office)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/93177c · Font actualitzada el 2026-10-23 · Extret el 2026-10-28

## Què és i quan usar-lo
Exemple d'ús per a pàgines d'aplicacions de gestió interna (back-office): maquetació amb menú lateral, retícula en l'espai de contingut, formularis i taules.

## Fonaments

### Quadrícula
- Inclou el **menú lateral per sota del títol** de la pàgina ([Menú lateral](component-menu-lateral.md)).
- S'implementa la **retícula en l'espai de contingut.** Tant el menú horitzontal com el lateral queden exclosos. Per a cada punt de trencament s'utilitzen totes les columnes disponibles per a maquetar el contingut.
- Es poden implementar **diversos camps d'entrada per fila**, adaptant-los al contingut i a l'espai marcat per les columnes de la retícula.
- **Per sobre dels 1440 px** es fa servir el **grid Extra Large column variable.**

### Comportament amb menú lateral desplegable
En cas de **col·lapse del menú**, hi ha dues opcions per al comportament de la retícula en funció del cas d'ús.

**Opció 1 - Expansió del contingut.** Si es vol que el **contingut s'expandeixi**, però **no es reordeni**, en col·lapsar el menú, s'utilitza aquesta opció. Es **parteix de la retícula utilitzada amb el menú replegat** i es **manté** quan el menú està desplegat. Per exemple, si l'espai dedicat al contingut és de 1408 px en una pantalla de 1440 px amb el menú replegat i es redueix a 1128 px quan el menú es desplega, s'aplica en ambdós casos la retícula *Extra Large Column Variable*. Figma: `Reticula fixe_menu replegat`, `Reticula fixe_menu desplegat`.

**Opció 2 - Reordenació del contingut.** Si es vol que el contingut es **reordeni** en col·lapsar el menú, s'utilitza aquesta versió. Es produeix un **canvi de retícula en funció de l'amplada del cos del contingut.** Si en les dues versions del menú s'hi aplica una retícula diferent (per exemple, quan està desplegat aplica la retícula *Extra Large Column Variable* i quan està replegat aplica la *Large*), **s'adapten els components en el nou espai disponible** i, si és necessari, es pot fer una reorganització per un millor aprofitament de l'espai. Figma: `Reticula dinamica_menu replegat`, `Reticula dinamica_menu desplegat`.

En les dues opcions cal **començar dissenyant tenint en compte la mida de pantalla més petita** per organitzar els components en la retícula i que disposin de prou espai per ser utilitzats correctament. Figma: `Construcció Large`.

A l'hora d'introduir els components cal **respectar l'amplada de les columnes** i **tenir en compte el contingut** d'aquell element. Pot ser que alguna columna quedi sense ocupar si el camp següent necessita més espai del disponible en aquella fila. Es recomana que l'amplada dels components de formulari no sigui superior a **665 px ni inferior a 168 px.**

- Les recomanacions de mides per a formularis són a l'exemple d'ús [Formularis](exemple-formularis.md).
- Les quadrícules utilitzades en cada punt de trencament són a [Punt de tall i quadrícules](fonaments-punt-de-tall-i-quadricules.md).

### Espai vertical
Figma: `Espaiat` (Pàgines back-office/DOC_Exemples d'ús/Backoffice/Espaiat). La taula d'espaiats és a [Exemples d'ús](exemple-exemples-d-us.md).

## Guies d'ús
- Utilitza les **versions small** per defecte en **camps de formulari**.
- La **paginació de taules** s'inclou al final del llistat de resultats ([Paginació](component-paginacio.md)).
- **Evita l'ús de la paginació infinita.**
- **Identifica** clarament **a quina pàgina** de la taula **es troba l'usuari**, mostrant el número de pàgina actual i el nombre total de pàgines.
- Mostra o **dona context sobre la primera i l'última pàgina.**
- Per a més guies sobre com dissenyar taules, consulta [Taules dinàmiques](component-taules-dinamiques.md).

## Components implicats
- [Àrea de text](component-area-de-text.md)
- [Botó d'opció](component-boto-d-opcio.md)
- [Botons](component-botons.md)
- [Camp d'entrada](component-camp-d-entrada.md)
- [Carregador d'arxius](component-carregador-d-arxius.md)
- [Casella de selecció](component-casella-de-seleccio.md)
- [Desplegable](component-desplegable.md)
- [Menú lateral](component-menu-lateral.md)
- [Taules dinàmiques](component-taules-dinamiques.md)
- [Peu de pàgina](component-peu-de-pagina.md)

## Disseny
Els exemples d'ús es poden descarregar a la pàgina [Exemples d'ús](exemple-exemples-d-us.md). El contingut utilitzat pels exemples no és real.

Variants Figma (Pàgines back-office/DOC_Exemples d'ús/Backoffice): `1280_collapsed` | `1280_expanded` | `1440_collapsed` | `1440_expanded`.

## Accessibilitat
Quan es crea un formulari, consulta primer les instruccions d'accessibilitat específiques per a cada component utilitzat.

Indicacions generals:
- S'ha de poder **navegar per teclat** (tabulador) i els **camps obligatoris s'han d'etiquetar clarament com a tals.** Si tots són obligatoris, però n'hi ha algun d'opcional, es marcarà aquest amb una etiqueta.
- **S'han d'incloure missatges de validació** per informar l'usuari de dades que s'introdueixen incorrectament o d'un camp obligatori que no té informació.
- La **informació** que l'usuari ha introduït en un formulari **s'ha de guardar** i no tornar a ser demanada en passos posteriors.

## Vegeu també
[Formularis](exemple-formularis.md) · [Exemples d'ús](exemple-exemples-d-us.md) · [Punt de tall i quadrícules](fonaments-punt-de-tall-i-quadricules.md) · [Menú lateral](component-menu-lateral.md) · [Taules dinàmiques](component-taules-dinamiques.md)
