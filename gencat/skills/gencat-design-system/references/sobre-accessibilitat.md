# Accessibilitat

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/6809a0 · Font actualitzada el 2026-02-23 · Extret el 2026-10-28

El sistema de disseny proporciona una referència sobre accessibilitat que serveix com a base per a productes i experiències digitals.

## Principis

### Navegació per teclat
El sistema de disseny entén que l'accessibilitat no és una característica opcional, sinó un dret fonamental. La **navegació per teclat** és essencial per a persones amb discapacitats motores, visuals o que, simplement, prefereixen l'eficiència del teclat davant del ratolí.
Tots els components de la llibreria estan dissenyats i construïts per ser plenament operatius mitjançant el teclat, seguint els estàndards globals d'usabilitat:
- **Ordre lògic del focus:** el focus segueix l'ordre visual i de lectura de la pàgina (generalment d'esquerra a dreta i de dalt a baix).
- **Indicadors visuals clars (Focus Rings):** mai no s'elimina l'estat `:focus`. Cada component té un indicador visual d'alta visibilitat per saber en tot moment en què es troba l'usuari.
- **Interacció estàndard:** s'utilitza `Tab` per navegar entre elements, `Enter` o `Espai` per activar-los, i les fletxes de direcció per a components complexos com menús o radio-buttons.
- **Trampes de focus (Focus Traps):** en elements modals o diàlegs, el focus queda confinat dins de la finestra emergent fins que es tanca, evitant que l'usuari es perdi en el contingut de fons.

### Control per veu
Molts usuaris naveguen per les interfícies mitjançant ordres de veu. Perquè això funcioni, el programari de reconeixement ha de poder "llegir" la interfície i entendre què és cada element. Si un botó no té una etiqueta clara en el codi, un usuari no podrà dir "Fes clic a Enviar". Els principis que regeixen el control per veu són:
- **L'etiqueta visual ha de coincidir amb el nom accessible:** el que l'usuari llegeix a la pantalla ha de ser part del que el sistema reconeix. Si un botó diu "Contacte", el seu `aria-label` no hauria de ser només "Formulari", sinó que ha d'incloure la paraula "Contacte".
- **Identificació de rols (ARIA Roles):** s'utilitzen rols semàntics perquè l'usuari pugui dir "Mostra els enllaços" o "Fes clic al botó". Sense un rol clar, l'element és invisible per a les eines de veu.
- **Evitar elements clicables sense text:** les icones soles (com una "X" per tancar) són les més problemàtiques. Sempre han de tenir un text alternatiu o una etiqueta ARIA que les identifiqui verbalment.

### Conceptes tècnics clau
**ARIA Labels i Descriptions**
- **`aria-label`**: defineix una cadena de text que etiqueta l'element actual. Útil per a botons amb només icones.
- **`aria-labelledby`**: semblant a l'anterior, però apunta a l'ID d'un altre element de text que ja existeix a la pantalla.
- **`aria-describedby`**: s'utilitza per donar informació addicional (com missatges d'error o descripcions d'ajuda) sense canviar el nom principal de l'objecte.

**L'algoritme "Accessible Name"**
És crucial que desenvolupadors i dissenyadors entenguin com el navegador calcula el nom d'un element. L'ordre de prioritat sol ser:
1. `aria-labelledby`
2. `aria-label`
3. Text intern de l'element (innerText)
4. Atribut `title` (tot i que es recomana evitar-ne l'ús).

### Recursos
Per assegurar que es parla el mateix idioma, es recomana consultar aquestes guies de referència:
- [ARIA Patterns](https://www.w3.org/WAI/ARIA/apg/patterns/): exemples específics amb components.
- [A11y project - Checklist](https://www.a11yproject.com/checklist/#keyboard): checklist d'accessibilitat que inclou navegació per teclat.
- [WebAIM - Keyboard Accessibility](https://webaim.org/techniques/keyboard/): una introducció sobre com els usuaris interactuen amb el teclat.

## Normativa

### Normativa EN 301 549
El sistema de disseny de la Generalitat de Catalunya ha estat desenvolupat amb un ferm compromís cap a l'accessibilitat, garantint que tots els usuaris, independentment de les seves capacitats, puguin gaudir d'una experiència digital inclusiva.
Per això se segueixen rigorosament les pautes establertes a la **normativa EN 301 549** (UNE EN 301 549:2022, en la versió en espanyol), que proporciona els requisits d'accessibilitat per a productes i serveis TIC a Europa. Aquesta normativa es basa en les **Web Content Accessibility Guidelines (WCAG)**, l'estàndard internacional per a l'accessibilitat web. Les WCAG s'organitzen al voltant de quatre **principis fonamentals** que han estat revisats en cadascun dels components:
- **Perceptible**: la informació i els components de la interfície d'usuari han d'estar presentats de manera que puguin ser percebuts per tots els usuaris. Això inclou l'ús de textos alternatius per a imatges, subtítols per a vídeos i garantir que el contingut sigui adaptable per a diferents dispositius i ajuts tècnics.
- **Operable**: els usuaris han de poder interactuar amb els elements de la interfície de manera eficient i sense obstacles. Això implica la possibilitat de navegar i utilitzar el lloc mitjançant el teclat, proporcionar prou temps per executar tasques, i evitar l'ús de contingut que pugui causar atacs epilèptics o problemes de salut similars.
- **Comprensible**: el contingut i la interfície han de ser fàcils d'entendre. Això significa que s'ha d'utilitzar un llenguatge clar i simple, proporcionar instruccions intuïtives i dissenyar de manera coherent perquè els usuaris puguin predir el comportament dels elements i funcions.
- **Robust**: el contingut ha de ser prou robust perquè pugui ser interpretat de manera fiable per una àmplia varietat d'agents d'usuari, incloses tecnologies de suport com els lectors de pantalla. Això garanteix que el lloc sigui accessible ara i en el futur, a mesura que la tecnologia i els estàndards evolucionin.

Complir amb l'EN 301 549 no només reforça el compromís amb l'accessibilitat, sinó que també garanteix que les solucions estiguin alineades amb les millors pràctiques internacionals i compleixin els requisits legals i normatius en matèria d'accessibilitat digital.

### Enllaços d'accessibilitat
Per obtenir més informació sobre accessibilitat:
- [Accedeix a la normativa EN 301 549 V 3.2.1 (Anglès)](https://www.etsi.org/deliver/etsi_en/301500_301599/301549/03.02.01_60/en_301549v030201p.pdf)
- [Accedeix a les pautes de la WCAG 2.2](https://www.w3.org/WAI/WCAG22/Understanding/)

### Com et podem ajudar?
Si cal ajuda, sol·licitar un nou component o modificar-ne un d'existent, o hi ha dubtes sobre l'ús del sistema de disseny, consulta la [secció de suport](suport-suport-i-contacte.md).
- [Consulta les preguntes freqüents](sobre-preguntes-mes-frequents.md)
- [Fes una sol·licitud](suport-sollicituds.md)
- [Accedeix a les guies d'ús](sobre-guies-d-us.md)

## Declaració d'accessibilitat
La directiva europea sobre accessibilitat als webs i aplicacions mòbils obliga a l'elaboració, actualització periòdica i publicació d'una declaració d'accessibilitat sobre la conformitat dels webs i aplicacions mòbils amb els requisits d'accessibilitat establerts.
Les declaracions d'accessibilitat han d'estar en un format accessible i s'han de publicar, en el cas dels webs, al mateix web, i en el cas de les aplicacions mòbils, al web de l'organisme que l'hagi desenvolupat.

Aquesta declaració ha d'incloure la informació següent:
- Quines són les parts no accessibles, el motiu pel qual no ho són i les alternatives que s'ofereixen.
- Quin és el mecanisme de comunicació amb l'organisme competent per notificar l'incompliment dels requisits d'accessibilitat.
- Quin és el mecanisme per sol·licitar informació o formular una queixa relativa a l'accessibilitat web.
- Quin és el procediment que es pot portar a terme en cas que la resposta a la comunicació o sol·licitud d'informació sigui insatisfactòria, o la manca d'aquesta.

L'**URA de Catalunya** ha desenvolupat un model propi de declaració d'accessibilitat que és el que s'ha d'utilitzar per als webs i aplicacions mòbils de la seva competència (Generalitat de Catalunya i sector públic). És obligatori emprar aquest model, ja que és el que inclou els tres mecanismes (comunicació, sol·licitud d'informació o queixa i reclamació).

> Els models de declaració que s'ofereixen en aquesta pàgina són d'ús obligat per a tots els webs de la Generalitat de Catalunya i el seu sector públic.

### Normativa
- [Directiva (UE) 2016/2102 del Parlament Europeu i del Consell de 26 d'octubre de 2016](https://eur-lex.europa.eu/legal-content/ES/TXT/?uri=uriserv:OJ.L_.2016.327.01.0001.01.SPA&toc=OJ:L:2016:327:TOC)
- [Reial Decret 1112/2018](https://www.boe.es/eli/es/rd/2018/09/07/1112/con)
- [Decisió d'execució (UE) 2018/1523](https://eur-lex.europa.eu/legal-content/ES/TXT/?uri=uriserv:OJ.L_.2018.256.01.0103.01.SPA)

### Models de declaració (descàrrega)
- [Model de declaració (Català)](https://atenciociutadana.gencat.cat/web/.content/02_CATALEG_SERVEIS/ACCESSIBILITAT/declaracio/instruccions-declaracio-ca.docx)
- [Model de declaració (Castellà)](https://atenciociutadana.gencat.cat/web/.content/02_CATALEG_SERVEIS/ACCESSIBILITAT/declaracio/instruccions-declaracio-es.docx)
- [Model de declaració (Occità-Aranès)](https://atenciociutadana.gencat.cat/web/.content/02_CATALEG_SERVEIS/ACCESSIBILITAT/declaracio/instruccions-declaracio-oc.docx)
- [Model de declaració (Anglès)](https://atenciociutadana.gencat.cat/web/.content/02_CATALEG_SERVEIS/ACCESSIBILITAT/declaracio/instruccions-declaracio-es.docx)
- [Model de declaració (Francès)](https://atenciociutadana.gencat.cat/web/.content/02_CATALEG_SERVEIS/ACCESSIBILITAT/declaracio/instruccions-declaracio-es.docx)
- [Model de declaració (Alemany)](https://atenciociutadana.gencat.cat/web/.content/02_CATALEG_SERVEIS/ACCESSIBILITAT/declaracio/instruccions-declaracio-es.docx)

> [a verificar] A la font, els models en anglès, francès i alemany apunten a la mateixa URL que el model en castellà (`instruccions-declaracio-es.docx`).
