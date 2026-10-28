# Pàgines d'error i manteniment (Error and Maintenance page)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/22baa2 · Font actualitzada el 2026-06-09 · Extret el 2026-10-28

## Què és i quan usar-lo
Pàgines que ajuden l'usuari a entendre quin problema hi ha al lloc web. Serveixen per ajudar l'usuari a entendre quin problema té el lloc web, a reduir la seva frustració i a oferir-li opcions clares per continuar navegant o obtenir suport.

### Pàgina d'error
Quan s'utilitza: en situacions en què hi ha hagut un problema inesperat en el lloc web i que no s'ha pogut preveure. Indica un problema tècnic, un enllaç trencat o una configuració incorrecta. Apareix quan el contingut no es pot visualitzar perquè el servidor retorna errors com per exemple:
- **404:** significa que la pàgina on ha accedit l'usuari no existeix.
- **500:** vol dir que hi ha hagut un error en el servidor.
- **403:** significa que l'usuari que vol accedir a la pàgina no té els permisos necessaris.
- **502 / 503 / 504:** són problemes temporals amb el servidor o amb serveis externs.

### Pàgina de manteniment
Quan s'utilitza: en situacions en què el lloc web està inactiu temporalment de manera voluntària i controlada. Apareix quan s'estan fent actualitzacions, canvis de sistema o manteniment preventiu, com per exemple:
- **Interrupció temporal del servei:** quan s'està fent manteniment programat o actualitzacions tècniques del lloc web.
- **Transformació tecnològica o migració:** durant processos de canvi d'infraestructura o plataforma tecnològica.

## Quan NO usar-lo / alternatives

### Pàgina d'error
- **Per errors en carregar contingut:** en aquests casos s'hauria d'utilitzar un avís informatiu o d'error que expliqui que el contingut no està disponible ([Avisos](component-avisos.md)).
- **Per errors en l'autenticació:** en aquests casos s'hauria de mostrar un avís d'error d'autenticació o autorització, no una pàgina d'error genèrica.

### Pàgina de manteniment
- **Per informar sobre un error tècnic inesperat:** en aquest cas cal mostrar la pàgina d'error.
- **Quan el servei està actiu però amb funcionalitats limitades:** si el sistema funciona parcialment, cal informar l'usuari de les limitacions, però no cal mostrar una pàgina de manteniment completa.
- **Quan no hi ha cap intervenció tècnica real en curs.**

## Anatomia
Figma: `Pàgina d'error`, `Pàgina de manteniment` (Pàgines d'error i manteniment/Disseny).
1. **Capçalera pròpia** que identifica visualment que es tracta d'un espai diferent del flux habitual de navegació del lloc web.
2. **Missatge breu, clar i entenedor**, que explica de manera concisa què ha passat, i les opcions que té l'usuari per continuar navegant pel lloc web.
3. **Il·lustració** ([Il·lustracions](fonaments-illustracions.md)) que serveix per entendre la informació d'una manera clara i entretinguda.
4. **Bàner d'atenció** ([Bàner d'atenció](component-baner-d-atencio.md)) per donar resposta a les necessitats de suport que pugui tenir l'usuari.
5. **Peu de pàgina** ([Peu de pàgina](component-peu-de-pagina.md)) que manté la coherència visual amb la resta de l'entorn web Gencat.

## Comportament

### Adaptació responsiva
Pel que fa a la composició visual, la pàgina s'adapta de manera responsiva segons el dispositiu:
- **En pantalles grans** (punts de tall *extra large* i *large*): el contingut es presenta en dues columnes: el text explicatiu a l'esquerra i la il·lustració a la dreta.
- **En pantalles petites** (punts de tall *medium* i *small*): la disposició s'adapta a un format vertical: primer es mostra la il·lustració i tot seguit el text explicatiu.

Figma: `Responsive`.

## Bones pràctiques

### Consistència visual
- **FER:** Posa les il·lustracions correctes segons el tipus de pàgina.
- **NO FER:** No utilitzis il·lustracions incorrectes o genèriques que no ajudin a identificar el tipus d'incidència.
- **NO FER:** No utilitzis espais en blanc en comptes de les il·lustracions.

### Il·lustracions
- **FER:** Les il·lustracions han d'aparèixer per donar context.
- **NO FER:** No utilitzis espais en blanc en comptes de les il·lustracions.

### Tonalitat del missatge
- **FER:** Utilitza un to proper, institucional i tranquil. Informa amb claredat i empatia.
- **NO FER:** No facis servir missatges tècnics o freds com "Error 500" sense cap explicació addicional.

### Context i classificació
- **FER:** Utilitza la pàgina d'error o manteniment només quan correspongui segons el tipus de problema que s'ha donat.
- **NO FER:** No facis servir la pàgina de manteniment per ocultar contingut no publicat o per redirigir l'usuari sense explicació.

## Components relacionats
- [Enllaços](component-enllacos.md): per facilitar la navegació entre parts del contingut o funcionalitats.
- [Botons](component-botons.md): permet a l'usuari dur a terme accions en una pàgina o pantalla.

## Accessibilitat (WCAG)
- **Orientació (AA) 1.3.4:** el contingut de l'àrea de text s'adapta a les diferents orientacions de la pantalla, com vertical o horitzontal, cosa que permet visualitzar el contingut. [CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Ús del color (A) 1.4.1:** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a diferenciar els diferents estats s'inclouen subratllats, es juga amb la presència de farciment i el gruix de la vora. [CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA) 1.4.3:** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA) 1.4.4:** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA) 1.4.11:** els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A) 2.1.1:** tota la funcionalitat del contingut es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Ordre del focus (A) 2.4.3:** els elements han de presentar-se en un ordre lògic per facilitar la navegació per teclat o altres dispositius d'entrada. L'ordre ha de seguir el flux de la informació o les tasques que s'estan presentant. (El text original esmenta "taules dinàmiques" [a verificar: text heretat d'un altre component].) [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-order) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-order)
- **Focus visible (AA) 2.4.7:** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) · [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

### Navegació per teclat
L'usuari pot navegar mitjançant el teclat per tots els elements interactius.

| Tecla | Acció |
|---|---|
| Tabulació | Navegar al següent element interactiu. |
| Shift + Tabulació | Navegar a l'anterior element interactiu. |
| Intro / Enter | Obrir el menú. |

## Historial de versions

| Versió Figma | Data | Descripció |
|---|---|---|
| 8.0.0 | 12 setembre, 2025 | Disseny i documentació del patró |

## Vegeu també
[Enllaços](component-enllacos.md) · [Botons](component-botons.md) · [Bàner d'atenció](component-baner-d-atencio.md) · [Peu de pàgina](component-peu-de-pagina.md) · [Il·lustracions](fonaments-illustracions.md) · [Avisos](component-avisos.md)
