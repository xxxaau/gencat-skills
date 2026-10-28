# Xat conversacional (exemple d'ús)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/94220b · Exemple d'ús (paquet conversacional) · Font actualitzada el 2026-10-23 · Extret el 2026-10-28

Els exemples d'ús es poden descarregar a la pàgina [Exemples d'ús](exemple-exemples-d-us.md) (font: https://sistemadedisseny.gencat.cat/38669693e/p/967d27). El contingut utilitzat pels exemples no és real.

## Fonaments

### Xat a pantalla completa (Fullscreen chat)

**Introducció.** Component conversacional que ocupa l'espai principal de contingut de la pàgina. S'utilitza quan la interacció conversacional és l'objectiu principal de la pantalla, substituint el contingut habitual. Vegeu [Xat a pantalla completa](patro-xat-a-pantalla-completa.md).

**Ubicació i alçada**
- El xat es col·loca dins l'estructura de la pàgina, just per sota dels fils d'ariadna ([Fils d'Ariadna](component-fils-d-ariadna.md)).
- L'alçada varia en funció de l'alçada de pantalla, sent un 90% de la pantalla (equival a 90 vh).
- Es deixa un marge inferior entre el camp i el final de pantalla de 32 px en punts de tall Extra Large i Large, 24 px en Medium i 8 px en Small.

**Comportament (adaptació responsive)**
- **Extra Large - Large:** tots els elements que conformen el xat es situen a la part central de la pàgina ocupant les 6 columnes centrals. (Figma: Fixed 1920.)
- **Medium:** tots els elements es situen a la part central de la pàgina ocupant les 6 columnes centrals. Alineació centrada amb una amplada mínima de 416 px tant pel cos com pel camp d'entrada. (Figma: Variable 1440.)
- **Small:** tots els elements que conformen el xat es situen a pantalla completa. (Figma: Xat Pantalla completa_479.)

### Xat flotant (Floating chat)

**Introducció.** Component conversacional que es presenta de manera superposada sobre el contingut de la pàgina, sense substituir-lo. L'usuari pot alternar entre el contingut principal i la conversa sense perdre el context de navegació. Vegeu [Xat flotant](patro-xat-flotant.md).

**Ubicació i distàncies**

*Botó de xat* ([Botó de xat](component-boto-de-xat.md)). Per convenció i per a una accessibilitat òptima, el botó de xat flotant es col·loca de manera fixa a la part inferior dreta de la pantalla. Aquesta posició es manté inalterable durant l'scroll de la pàgina. El component se separa de la vora inferior i lateral del viewport per un marge que varia en funció del punt de tall:

| Punt de tall | Marge inferior | Marge lateral |
|---|---|---|
| Extra Large column fixed i variable | 40 px | 48 px |
| Large | 40 px | 40 px |
| Medium | 40 px | 32 px |
| Small | 16 px | 12 px |

*Contenidor de xat flotant* ([Contenidor de xat](component-contenidor-de-xat.md)). El contenidor es col·loca respectant les mateixes distàncies respecte al marge que el botó. Això aplica als punts de tall des d'Extra Large fins a 768 px. De 767 px cap a baix s'aplica la versió en bottom sheet, que ocupa tota l'amplada de pantalla.

**Comportament (adaptació responsive)**
- **Extra Large - Large:** col·locat a la part inferior dreta de la pantalla amb una amplada fixa de 400 px. (Figma: Fixed 1920.)
- **Medium:** en el punt de tall Medium conviuen les dues formes del xat, com a element flotant i com a panell emergent. El canvi entre un i l'altre es realitza a 768 px. A partir dels 767 px es mostra la versió per a Medium - Small. (Figma: Medium_766.)
- **Small:** tots els elements que conformen el xat es situen a pantalla completa. (Figma: Small.)

### Xat lateral (Side chat)

**Introducció.** Component conversacional que es desplega com a panell adherit a un costat de la pantalla, permetent la convivència entre el contingut principal i la conversa. Està orientat principalment a entorns privats i de back office. Vegeu [Xat lateral](patro-xat-lateral.md).

**Ubicació i distàncies**

*Botó de xat lateral*
- **Extra Large - Medium (≥ 768 px):** el botó se situa a la part superior de la pantalla, adherit a la subcapçalera quan n'hi ha. Quan l'usuari fa scroll i la subcapçalera deixa de ser visible, el botó es reubica just sota la capçalera i es manté fix per garantir-ne la visibilitat persistent. (Figma: 1440_expanded.)
- **Small - Medium (< 768 px):** en el punt de tall Medium poden conviure dues variants del botó: la versió fixa, situada a la capçalera o a la subcapçalera, i la versió no fixa. El comportament de la versió no fixa depèn de si hi ha subcapçalera:
  - Si no hi ha subcapçalera, el botó queda situat just sota la capçalera i en forma part. Quan es faci scroll cap amunt i torni a aparèixer la capçalera, el botó també reapareixerà.
  - Si hi ha subcapçalera, el botó queda vinculat a aquesta zona i no es manté visible. Per tornar-hi a accedir, cal fer scroll fins arribar de nou a la subcapçalera.
  - El canvi entre les dues variants (versió fixa i no fixa) es realitza a 768 px. (Figma: Medium.)

*Panell lateral de xat.* El panell es mostra en punts de tall Extra Large i Medium fins a 768 px. En aquest punt, si hi ha subcapçalera, el panell es desplegarà sota aquesta; si no, ho farà des de la capçalera. En els casos en què calgui mostrar-lo en punts de tall inferiors, es presenta superposat sobre el contingut amb una amplada reduïda, mantenint totes les funcionalitats.

**Comportament (adaptació responsive)**
- **Extra Large:** quan s'obre, el contingut principal s'adapta en amplada i disposició per conviure amb el panell, sempre que l'espai disponible ho permeti. (Figma: 1440_collapsed.)
- **Large - Medium (< 768 px):** en el punt de tall Medium conviuen les dues formes del xat, com a element emergent lateral i com a pantalla completa. El canvi entre un i l'altre es realitza a 768 px. (Figma: Large_1279.)
- **Small:** el xat es transforma en una experiència de pantalla completa. El panell sempre es desplega en pantalla completa. (Figma: Small.)

## Disseny: pantalles d'exemple (Figma)
- Xat Pantalla completa: Fixed 1920, Large_1279, Medium_959, Xat Pantalla completa_479.
- Xat Flotant: Medium 1959, Medium_766, Small, Fixed 1920.
- Xat Lateral: 1440_collapsed, Medium, Large_1279, Small.

## Accessibilitat
Quan es dissenyi o s'implementi el xat, cal consultar primer les instruccions d'accessibilitat específiques de cada component utilitzat.

### Indicacions generals
- El xat ha de permetre l'augment de la mida del text fins al 200% sense pèrdua de contingut ni de funcionalitat. Cal assegurar que cap element es talli, se superposi o sobresurti de la pantalla.
- Tots els elements interactius han de ser accessibles mitjançant teclat i han de seguir un ordre de focus lògic, coherent amb l'estructura visual i funcional del xat.

### Comportament amb augment de text
- Quan no hi hagi prou espai perquè el nom i les accions de la capçalera es mantinguin en una mateixa línia, el nom passarà a una segona línia i els botons es mantindran alineats a la part superior dreta.
- En el camp d'entrada, si el text i les accions no caben en una mateixa línia, els botons saltaran a la línia inferior. Si hi ha més accions de les que caben en línia, aquestes es podran agrupar dins d'un menú. El botó per adjuntar elements no s'ha d'incloure dins d'aquest desplegable.

### Estructura dels missatges
Els missatges han de tenir una estructura d'encapçalaments que permeti a les persones usuàries navegar-hi amb lector de pantalla. Cada missatge ha d'incorporar un encapçalament segons l'estructura de la pàgina:
- Missatge de l'usuari: "Has dit".
- Missatge del xatbot: "L'agent ha dit".

Si dins d'un missatge del xatbot hi ha seccions internes, aquestes han de tenir un nivell d'encapçalament inferior al del missatge principal.

### Lectura i estats del xat
- Quan l'usuari enviï un missatge, el lector de pantalla ha d'informar dels canvis d'estat rellevants. Per exemple, mentre s'estigui generant una resposta, s'ha d'anunciar que "s'està generant la resposta".
- Aquest estat s'ha de comunicar de manera no intrusiva i s'ha d'actualitzar fins que la resposta estigui disponible. Un cop generada, el lector de pantalla ha d'iniciar la lectura de la resposta indicant que prové del xat.
- També cal notificar l'arribada de nous missatges quan l'usuari estigui navegant per una altra part del xat. En aquest cas, el botó o avís de nous missatges s'ha d'anunciar correctament mitjançant etiquetes ARIA.

### Navegació per teclat
- El xat ha de permetre la navegació completa per teclat, incloent-hi la capçalera, els missatges, el camp d'entrada, les accions associades i els avisos de nous missatges.
- Quan el focus entri dins del xat, ha de seguir un recorregut coherent i previsible. Les accions principals han de ser accessibles amb tabulador i els missatges han de poder consultar-se amb les tecles de navegació del lector de pantalla.

## Components relacionats
[Xat a pantalla completa](patro-xat-a-pantalla-completa.md), [Xat lateral](patro-xat-lateral.md), [Xat flotant](patro-xat-flotant.md), [Contenidor de xat](component-contenidor-de-xat.md), [Camp d'entrada de xat](component-camp-d-entrada-de-xat.md), [Suggeriments](component-suggeriments.md), [Missatge de xat](component-missatge-de-xat.md), [Capçalera de xat](component-capcalera-de-xat.md), [Avatar](component-avatar.md), [Botó tornar a baix](component-boto-tornar-a-baix.md), [Botó de xat](component-boto-de-xat.md), [Capçalera secundària de xat](component-capcalera-secundaria-de-xat.md).
