# Formularis (exemple d'ús)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/70452c · Font actualitzada el 2026-10-28 · Extret el 2026-10-28

## Què és i quan usar-lo
Directrius essencials per al disseny de formularis, amb l'objectiu de crear experiències d'usuari eficients i accessibles. Els formularis ben dissenyats han de ser clars, intuïtius i fàcils de completar, facilitant la recollida de dades sense errors ni frustracions.

## Fonaments

### Quadrícula
- Es recomana fer servir un camp per fila, a excepció d'aquells relacionats, com el tipus d'ID i la introducció del nombre corresponent, o camps d'una adreça.
- Aquests camps s'adaptaran en funció del contingut, però també de l'amplada de les columnes de la quadrícula. Si hi ha dos elements connectats que es volen posicionar en una mateixa fila i un té el contingut massa llarg i no respecta la quadrícula, s'ubicarà l'un sota l'altre.
- Per al punt de tall "Petit" (Small) sempre es dissenyarà el formulari a una columna.
- Les quadrícules utilitzades en cada punt de trencament són a [Punt de tall i quadrícules](fonaments-punt-de-tall-i-quadricules.md).
- Figma: `Reticula` (Pàgines formularis/DOC_Exemples d'ús/Formularis/Reticula).

### Espai vertical
- Figma: `Espaiat` (Pàgines formularis/DOC_Exemples d'ús/Formularis/Espaiat).
- La taula d'espaiats és a [Exemples d'ús](exemple-exemples-d-us.md). Vegeu també [Espaiat](fonaments-espaiat.md).

## Guies d'ús

### Generals
- Ús d'**etiquetes descriptives**. Han de ser concises, però informatives.
- Si en un formulari hi ha **camps obligatoris i opcionals**, destaca únicament els camps **menys comuns**. Si, per exemple, hi ha cinc camps obligatoris i un d'opcional, destaca només aquest últim incloent en el text de l'etiqueta la paraula "opcional" entre parèntesis per tal d'evitar càrrega cognitiva.
- Si uses un **asterisc (\*)** per marcar els camps obligatoris, inclou una **llegenda explícita**.
- Utilitza el **mateix criteri** per indicar l'obligatorietat o l'opcionalitat dels camps al llarg de tot el formulari.
- No facis ús d'una **preselecció d'un valor** que no és d'obligat compliment.
- Fes servir un únic botó primari en un mateix context per mantenir claredat en l'acció principal. Utilitza **un únic botó primari** amb l'acció principal.
- Usa el **botó secundari** per a la **segona acció més important**; pot haver-hi més d'un botó secundari en un mateix context.
- **No es farà servir mai un botó deshabilitat.** Si l'usuari no ha omplert tots els camps o els ha omplert de forma incorrecta, s'informarà un cop premi el botó. Proporciona missatges d'error clars i orientació sobre com resoldre el problema.
- Assegura't que en la **versió mòbil** s'utilitza el **botó adaptat a l'espai**.
- Quan l'usuari faci clic al botó d'enviar, la pàgina hauria de fer un **desplaçament automàtic al primer error** que trobem a la pàgina. Si el missatge d'error no fa referència a un camp en específic, és recomanable col·locar l'alerta just a sobre dels botons d'enviament i cancel·lació (o a l'inici de la pàgina).
- Les **notificacions apareixen a l'inici de la pàgina o prop dels seus elements relacionats**, integrades dins de la maquetació de la pàgina. Poden expandir-se per omplir l'amplada de l'àrea de contenidor o contingut en la qual es troben i s'han d'alinear a les columnes de la quadrícula.

### Formulari multi pàgina
- **Tornar enrere:** per navegar a seccions anteriors dins d'un formulari per passos, col·loca el botó (o fils d'Ariadna) a la part superior esquerra de la pàgina ([Fils d'Ariadna](component-fils-d-ariadna.md)).
- **No se superen els 7 passos.** Si és un procés més llarg o complex, s'hauran de fer agrupacions de contingut i dividir el procés en diferents subetapes.
- Afegeix una **secció de confirmació de dades** abans d'enviar el formulari.

### Indicador de funció i descripció emergent
- Els [indicadors de funció](component-indicador-de-funcio.md) proporcionen informació addicional sobre un element quan l'usuari passa el cursor per sobre o hi fa clic. Apareixen en forma de petits quadres de text emergents que contenen explicacions, descripcions o consells relacionats amb l'element sobre el qual s'està passant el cursor.
- La [descripció emergent](component-descripcio-emergent.md) és un petit contenidor superposat que mostra informació contextual. Apareix quan l'usuari interactua amb un element de la pàgina en clicar i roman obert fins que es tanca. A diferència de l'indicador de funció, aquest pot incloure elements interactius com botons o enllaços.
- **Es recomana utilitzar únicament un dels dos components per camp.** Utilitza la descripció emergent si necessites elements interactius amb la informació pertinent.

## Components implicats
- [Camp d'entrada](component-camp-d-entrada.md)
- [Desplegable](component-desplegable.md)
- [Casella de selecció](component-casella-de-seleccio.md)
- [Botó d'opció](component-boto-d-opcio.md)
- [Àrea de text](component-area-de-text.md)
- [Carregador d'arxius](component-carregador-d-arxius.md)
- [Botons](component-botons.md)
- [Pas a pas](component-pas-a-pas.md)
- [Capçalera secundària](component-capcalera-secundaria.md)
- [Peu de pàgina](component-peu-de-pagina.md)
- [Divisor](component-divisor.md)

## Disseny
Els exemples d'ús es poden descarregar a la pàgina [Exemples d'ús](exemple-exemples-d-us.md).

Variants Figma (Pàgines formularis/DOC_Exemples d'ús/Formularis): formulari multipàgina = `Multi_1440` | `Multi_1280` | `Multi_960` | `Multi_480`; formulari d'una sola pàgina = `Unic_1920` | `Unic_1439` | `Unic_1279` | `Unic_959` | `Unic_479`.

## Accessibilitat
Quan es crea un formulari, consulta primer les instruccions d'accessibilitat específiques per a cada component utilitzat.

Indicacions generals:
- Els requisits per al formulari s'han d'anunciar i declarar abans que l'usuari introdueixi el formulari.
- S'ha de poder navegar per teclat (tabulador) i els camps obligatoris s'han d'etiquetar clarament com a tals. Si tots són obligatoris, però n'hi ha algun d'opcional, es marcarà aquest amb una etiqueta.
- S'han d'incloure missatges de validació per informar l'usuari de dades que s'introdueixen incorrectament o d'un camp obligatori que no té informació.
- La informació que l'usuari ha introduït en un formulari s'ha de guardar i no tornar a ser demanada en passos posteriors.

## Vegeu també
[Exemples d'ús](exemple-exemples-d-us.md) · [Punt de tall i quadrícules](fonaments-punt-de-tall-i-quadricules.md) · [Introducció de dades](patro-introduccio-de-dades.md) · [Selector d'hora](patro-selector-d-hora.md) · [Camp d'entrada](component-camp-d-entrada.md) · [Botons](component-botons.md) · [Pas a pas](component-pas-a-pas.md)
