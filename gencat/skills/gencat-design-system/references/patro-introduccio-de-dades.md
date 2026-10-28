# Introducció de dades (Data input)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/48165f · Font actualitzada el 2026-06-09 · Extret el 2026-10-28

## Què és i quan usar-lo
Patró que defineix com utilitzar els camps d'entrada quan l'usuari ha d'introduir dades amb una unitat, un prefix, un sufix o un format específic.

Aquest patró no substitueix el component de camp d'entrada ([Camp d'entrada](component-camp-d-entrada.md)). Defineix com utilitzar-lo i combinar-lo amb altres components quan el valor necessita més context per entendre's, introduir-se o validar-se correctament.

S'aplica quan un camp d'entrada necessita donar més context sobre el valor esperat: la unitat en què s'ha d'introduir, una part fixa (com €, kg, etc.) que l'usuari no ha d'escriure o un format concret per poder validar la dada. Serveix per unificar el tractament d'aquests casos i evitar solucions diferents per a necessitats similars.

Exemples habituals: imports, percentatges, unitats de mesura, dates, hores, durades, telèfons, codis, identificadors...

### Quan s'utilitza
- Quan el valor necessita una unitat per entendre's, com m², kg, litres, %, € o hores.
- Quan la unitat pot ser seleccionada per l'usuari.
- Quan el valor ha de seguir un format concret, com una data, una hora, un telèfon o un codi.
- Quan una part del valor és fixa (com €, kg, etc.) i no l'ha d'escriure l'usuari.
- Quan cal combinar un camp d'entrada amb un altre component, com un desplegable o botons d'opció.

## Quan NO usar-lo / alternatives
- Quan l'etiqueta i el camp d'entrada ja són suficients per entendre la dada.
- Quan la informació es resol millor amb un altre component específic, com un selector de data ([Selector de data](component-selector-de-data.md)), un grup de botons d'opció ([Botó d'opció](component-boto-d-opcio.md)) o un desplegable independent ([Desplegable](component-desplegable.md)).
- Quan el format no aporta valor a l'usuari o pot generar més complexitat.
- Quan el prefix, sufix o unitat no és necessari per entendre el valor.

## Components implicats
- [Camp d'entrada](component-camp-d-entrada.md): component base. La configuració tècnica per aplicar el format en camps numèrics és al component (https://sistemadedisseny.gencat.cat/38669693e/p/7912b2-camp-dentrada/b/76e45a).
- [Desplegable](component-desplegable.md) o [Botó d'opció](component-boto-d-opcio.md): per a unitats, prefixos o sufixos seleccionables.

## Bones pràctiques

### Etiqueta i text d'ajuda
- **FER:** Utilitza una etiqueta clara que indiqui quina dada ha d'introduir l'usuari.
- **FER:** Afegeix text d'ajuda quan el format, la unitat, el prefix o el sufix pugui generar dubtes.
- **FER:** Si el camp mostra una unitat abreujada, explica'n el significat complet al label o al text d'ajuda.

### Unitats, prefixos i sufixos
- **FER:** Mostra unitats, prefixos o sufixos quan siguin parts fixes del valor que l'usuari no ha d'escriure.
- **FER:** Si la unitat, prefix o sufix és seleccionable, combina el camp amb un desplegable o amb botons d'opció.
- **FER:** Quan la unitat sigui seleccionable, mostra el nom complet i el símbol entre parèntesis.
- **NO FER:** No obliguis l'usuari a escriure manualment una unitat, prefix o sufix si el sistema ja el pot mostrar.
- **NO FER:** No dupliquis la unitat: si ja es tria en un desplegable, no cal mostrar-la també com a sufix del camp.
- **NO FER:** No utilitzis només símbols o abreviatures si poden generar dubtes.
- **NO FER:** No combinis el símbol i la unitat escrita dins del mateix camp.

### Formats estructurats
- **FER:** Explica el format esperat amb text d'ajuda visible i, quan sigui útil, amb un exemple concret.
- **FER:** Normalitza el valor en sortir del camp només quan el sistema el pugui interpretar amb seguretat.
- **NO FER:** No utilitzis màscares estrictes o format automàtic mentre l'usuari escriu com a comportament per defecte.
- **NO FER:** No indiquis només formats tècnics, com dd/mm/aaaa o hh:mm, sense explicació o exemple.
- **FER:** Si el valor no compleix la longitud o el format esperat, mostra un error específic que indiqui com corregir-lo.
- **NO FER:** No mostris errors genèrics si pots explicar què cal corregir.

## Criteris generals de disseny

### Validacions
- La validació de format es realitza quan l'usuari surt del camp. No s'interromp l'usuari mentre escriu.
- El camp no mostra cap indicació visual quan el valor és correcte: l'absència d'error indica que el valor és vàlid.
- L'estat d'error desapareix quan l'usuari realitzi qualsevol canvi dins del camp. Si el valor continua sense ser vàlid en tornar a sortir, el missatge d'error reapareix.
- El missatge d'error ha d'explicar el problema i mostrar un exemple del format esperat. No n'hi ha prou amb indicar que el valor no és vàlid.
- Figma: `disseny_validacio` (Introducció de dades/Introducció guiada/DOC_introducciodades/disseny_validacio).

### Normalització
- Quan l'usuari surt del camp, el sistema transforma automàticament el valor introduït al format de presentació correcte. L'usuari escriu lliurement i el sistema s'encarrega d'aplicar el format.
- En cap cas el sistema modifica el valor mentre l'usuari escriu.
- Si el valor introduït no es pot interpretar, el camp mostra un error amb un exemple del format esperat.

Exemples de normalització per tipus de dada:

| Tipus de dada | Entrada acceptada | Visualització normalitzada |
|---|---|---|
| Telèfon espanyol | 612345678, 612 345 678, +34 612345678 | 612 345 678 |
| Codi postal | 8001, 08001 | 08001 |
| NIF/NIE | 12345678z, 12345678-Z | 12345678Z |
| IBAN | es9121000418450200051332 | ES91 2100 0418 4502 0005 1332 |
| Matrícula | 1234abc, 1234-ABC | 1234 ABC |
| Data | 13052026, 13-05-2026 | 13/05/2026 |
| Hora | 930, 9:30, 9.30 | 09:30 |
| Import | 1234,50 | 1.234,50 |

### Decimals i milers
- Sempre que sigui possible, els camps numèrics han de seguir el sistema espanyol: coma com a separador decimal i punt com a separador de milers. Com a bona pràctica es recomana que els camps admetin com a màxim dos decimals.
- Per aplicar el format corresponent en camps numèrics, consulta la configuració tècnica del component [Camp d'entrada](component-camp-d-entrada.md).
- El separador de milers és un element de presentació. El sistema l'afegeix automàticament quan l'usuari surt del camp. Si l'usuari l'escriu, el sistema l'accepta sempre que el format sigui inequívoc.
- La regla d'interpretació és fixa i s'aplica sempre:
  - Una coma s'interpreta sempre com a decimal. Punt seguit de coma s'interpreta com a milers i decimal respectivament. Qualsevol altra combinació dona error.
  - Per reduir errors silenciosos en camps on pot haver-hi confusió entre milers i decimals, el camp ha d'incloure un text d'ajuda amb un exemple del format esperat.
  - En pàgines multilingües, els valors numèrics s'han de mostrar segons el format corresponent a l'idioma o configuració regional activa. El valor s'ha de guardar internament sense format visual i mostrar-se amb els separadors de milers, decimals o moneda que corresponguin en cada cas.

Exemples de validacions:

| Camp escrit | Estat | Missatge d'error |
|---|---|---|
| 1234 | Vàlid | — |
| 1234,5 | Vàlid | — |
| 1,234 | Vàlid | — |
| 1.234 | Vàlid | — |
| 1.234,56 | Vàlid | — |
| 1.234.56 | Error | Format no vàlid. Utilitza la coma per als decimals i el punt per als milers. |
| 1,234,56 | Error | Format no vàlid. Utilitza la coma per als decimals i el punt per als milers. |
| 1234 , 50 | Error | Format no vàlid. Exemple: 1234.50 |

Exemples de normalització numèrica:

| Camp escrit | El sistema mostra | Observacions |
|---|---|---|
| 1234 | 1.234 | Afegeix separador de milers |
| 1234,5 | 1.234,50 | Completa decimals (camps monetaris) + separador de milers |
| 1,234 | 1,23 | Arrodoneix |
| 1.234 | Vàlid | Es llegeix com a milers |
| 1.234,56 | Vàlid | — |
| 01234 | 1.234 | Elimina el zero inicial en cas de valor monetari i afegeix el separador |
| 0,5 | 0,50 | Completa els decimals |

### Referència lingüística d'unitats
Per a l'escriptura correcta de símbols, abreviatures i noms d'unitats de mesura, consulteu la [referència lingüística oficial](https://canigo.ctti.gencat.cat/plataformes/dadesref/dadesref/). Aquesta referència determina si una unitat s'escriu en majúscula o minúscula, si porta punt abreujatiu i si el símbol va precedit d'espai.

## Criteris específics

### Superíndex
- Quan una unitat apareix com a opció seleccionable, mostra el nom complet de la unitat i el símbol entre parèntesis. Figma: `dissenyunitatmesura`.
- Evita mostrar només el símbol o l'abreviatura, especialment si pot generar dubtes. Per exemple, **m²** pot no ser prou clar per a tots els usuaris sense el text "metres quadrats". Per tant, el text d'ajuda ha d'explicar el nom complet de la unitat. Figma: `dissenym2`.

### Text d'ajuda per a formats
- Quan un camp requereix un format concret, el text d'ajuda ha d'explicar el format en llenguatge natural i incloure un exemple real.
- No és suficient indicar només el patró tècnic, com dd/mm/aaaa o hh:mm, perquè pot no ser prou clar per a tots els usuaris.
- Estructura recomanada: etiqueta + text d'ajuda persistent amb exemple concret. Figma: `disseny_textajuda`.

### Durada
- Quan una durada s'introdueix en camps separats, com hores i minuts, al resum del formulari s'ha de mostrar com un únic valor llegible. Figma: `disseny_durada`.
- Evita mostrar la durada com **2:30**, perquè es pot confondre amb una hora del dia.
- Si una de les parts és zero, mostra només la part necessària: 1 h; 45 min; 2 h 30 min.
- Evita formats com 1 h 0 min o 0 h 45 min si no aporten valor.

### Prefix de telèfon
- Utilitza el signe + per representar el prefix internacional. No utilitzis 0034 com a format visual de referència.
- Si el prefix és fix, mostra'l com a prefix del camp. Figma: `disseny_prefixfixa`.
- Si l'usuari ha de seleccionar el país o prefix, utilitza un selector associat al camp. Mostra el país i el codi en text. Evita els parèntesis en el prefix, com (+34), perquè poden fer pensar que el codi és opcional. Mantén el mateix criteri per a totes les opcions del desplegable. Figma: `disseny_prefixselect`.

### Normalització del telèfon
- Els números de telèfon s'han de mostrar separats en blocs per facilitar-ne la lectura.
- Format recomanat: +34 612 345 678. Figma: `disseny_normalitzaciotelf`.

### Milers i milions
- Evita abreviatures com M o MM per referir-se a milers o milions, ja que poden tenir significats diferents segons el context.
- Escriu sempre la paraula sencera: "3 milions", "50.000" o "50 milers". Figma: `disseny_MM`.

## Comportament

### Formats estructurats
Són camps on el valor ha de seguir una estructura concreta, com una data, una hora, un telèfon o un codi. El sistema pot adoptar dos comportaments, segons la complexitat del camp i el valor que aporti al context.

- **Comportament base: text d'ajuda i validació.** El format s'explica de manera visible i persistent mitjançant el text d'ajuda. Si l'usuari no l'escriu correctament, el sistema mostra un error en sortir del camp que indica el problema i el format esperat. Figma: `compotament1`.
- **Comportament avançat: normalització en sortir del camp.** Quan aporti valor a l'experiència, el sistema pot transformar automàticament el valor introduït al format correcte en sortir del camp. Si el valor no es pot interpretar o no és vàlid, el camp mostra l'error de format en lloc de normalitzar. El comportament avançat sempre inclou el comportament base: el text d'ajuda ha d'estar present independentment de si el camp normalitza o no. Figma: `disseny_comportament2`.

### Unitats
Quan un camp numèric requereix una unitat per entendre's, la unitat pot ser fixa o seleccionable segons si ve definida pel servei o si l'usuari l'ha d'escollir.

- **Camps amb unitat fixa:** quan la unitat ve definida pel servei i no pot canviar, es mostra dins del camp. L'etiqueta o el text d'ajuda han d'explicar sempre què s'està demanant, sense dependre únicament de la unitat per transmetre la informació. Figma: `disseny_comportament3`.
- **Camps amb unitat seleccionable:** l'usuari ha d'escollir la unitat. Es combina un camp numèric amb un component de selecció. Hi ha dues opcions segons el context:
  - **Botons d'opció abans del camp:** quan hi ha poques opcions i és important que l'usuari les vegi totes abans d'introduir el valor. Figma: `disseny_comportament4`.
  - **Desplegable al costat del camp:** quan cal compactar l'espai o quan la unitat forma part directa del valor i han d'anar visiblement units. Figma: `disseny_comportament5`.

### Prefixos i sufixos
Quan una part del valor és fixa i no l'ha d'escriure l'usuari, es mostra com a prefix o sufix del camp. El text d'ajuda ha d'explicar quina part ha d'introduir l'usuari.

- **Fixos:** el prefix o sufix es mostra sempre i no és editable. S'usa quan la part fixa del valor és constant per a tots els usuaris, com ara +34, https://, EXP-, etc. Figma: `disseny_comportament6`.
- **Seleccionables:** quan el prefix, sufix o unitat pot variar, s'usa un desplegable o botons d'opció associats al camp per permetre a l'usuari escollir l'opció correcta. Figma: `disseny_comportament7`.

## Accessibilitat (WCAG)
- **Orientació (AA) 1.3.4:** el contingut de l'àrea de text s'adapta a les diferents orientacions de la pantalla, com ara vertical o horitzontal, cosa que permet visualitzar el contingut. [CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Ús del color (A) 1.4.1:** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a indicar els diferents estats, es modifiquen els píxels de la vora del component i/o s'afegeixen elements complementaris com la segona vora pel focus o la icona i el text d'error. [CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA) 1.4.3:** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són excepció d'aquesta norma. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA) 1.4.4:** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA) 1.4.11:** els elements gràfics com icones (error i indicador de funció) i vores presenten un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Espaiat del text (AA) 1.4.12:** quan es desenvolupa contingut utilitzant llenguatges de marcatge que permeten aplicar les propietats d'estil de text, no es perd cap contingut ni funcionalitat si s'ajusten les propietats següents: alçada de línia (interlineat) de com a mínim 1,5 vegades la mida de la lletra; espaiat entre els paràgrafs de com a mínim dues vegades la mida de la lletra; espaiat entre lletres (tracking) de com a mínim 0,12 vegades la mida de la lletra; espaiat entre paraules de com a mínim 0,16 vegades la mida de la lletra. [CAT](https://www.w3.org/Translations/WCAG22-ca/#text-spacing) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/text-spacing)
- **Teclat (A) 2.1.1:** tota la funcionalitat del contingut (accedir al camp de text) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Focus visible (AA) 2.4.7:** la navegació al camp de l'àrea de text és visible mitjançant un rectangle extern. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- **Identificació d'errors (A) 3.3.1:** si es detecta un error en el component, s'identifica clarament que aquest presenta un error mitjançant un canvi de color i gruix de la vora i amb la indicació visual (icona) i textual (descripció de l'error) de l'error. [CAT](https://www.w3.org/Translations/WCAG22-ca/#error-identification) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/error-identification)

## Historial de versions

| Versió Figma | Data | Descripció |
|---|---|---|
| 12.0.0 | 29 maig, 2026 | Disseny i documentació del patró |

## Vegeu també
[Camp d'entrada](component-camp-d-entrada.md) · [Desplegable](component-desplegable.md) · [Botó d'opció](component-boto-d-opcio.md) · [Selector de data](component-selector-de-data.md) · [Selector d'hora](patro-selector-d-hora.md)
