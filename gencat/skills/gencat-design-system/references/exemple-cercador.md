# Cercador (exemple d'ús)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/169483 · Font actualitzada el 2026-10-23 · Extret el 2026-10-28

## Què és i quan usar-lo
Exemple d'ús per a pàgines de cerca amb llistat de resultats, filtres i paginació, incloent-hi el cercador amb mapa.

## Fonaments

### Quadrícula
- Les columnes laterals es destinen a informació complementària com filtres ([Filtres](component-filtres.md)).
- Les quadrícules utilitzades en cada punt de trencament són a [Punt de tall i quadrícules](fonaments-punt-de-tall-i-quadricules.md).
- Figma: `Reticula` (Pàgines de cerca/DOC_Exemples d'ús/Cerca/Reticula).

### Espai vertical
Figma: `Espaiat` (Pàgines de cerca/DOC_Exemples d'ús/Cerca/Espaiat). La taula d'espaiats és a [Exemples d'ús](exemple-exemples-d-us.md).

## Guies d'ús
- Mostra únicament **resultats relacionats amb la cerca.**
- En entorn treballador, **mantén la configuració de filtratge** que hagi escollit l'usuari per a les cerques i sessions següents.
- **Remarca les paraules clau** introduïdes en el contingut de la pàgina per facilitar-ne l'escaneig.
- Indica la **quantitat total de resultats** obtinguts en la cerca.
- Quan es realitzi la cerca, el **text introduït per l'usuari continuarà sent visible** en el camp.
- El **llistat de resultats** tindrà, de forma predeterminada, **10 opcions visibles per pàgina.** Aquesta visualització es pot modificar amb la paginació.
- La **paginació** s'inclou al **final del llistat de resultats.**
- Utilitza la **paginació** per a resultats de cerca enfront d'altres opcions com carregar més.
- **Evita l'ús de la paginació infinita.**
- **Identifica clarament a quina pàgina es troba l'usuari**, mostrant el número de pàgina actual i el nombre total de pàgines.
- **Mostra o dona context sobre la primera i l'última pàgina.**
- Per a cada resultat, **mostra un títol clar i descriptiu,** seguit d'una breu descripció que contextualitzi el contingut.
- Quan els resultats estan carregant, mostra un **missatge o una animació discreta** (per exemple, un indicador de càrrega, [Indicador de càrrega](component-indicador-de-carrega.md)) per indicar a l'usuari que la pàgina està en procés.

## Components implicats
- [Botó d'opció](component-boto-d-opcio.md)
- [Camp d'entrada](component-camp-d-entrada.md)
- [Desplegable](component-desplegable.md)
- [Camp de cerca](component-camp-de-cerca.md)
- [Casella de selecció](component-casella-de-seleccio.md)
- [Botons](component-botons.md)
- [Etiquetes](component-etiquetes.md)
- [Paginació](component-paginacio.md)
- [Llistat de resultats](component-llistat-de-resultats.md)
- [Xips](component-xips.md)
- [Peu de pàgina](component-peu-de-pagina.md)

## Disseny
Els exemples d'ús es poden descarregar a la pàgina [Exemples d'ús](exemple-exemples-d-us.md).

Variants Figma:
- **Cercador** (Pàgines de cerca/DOC_Exemples d'ús/Cerca): `Fixed 1920` | `Variable 1439` | `1279` | `959` | `479`.
- **Cercador de mapa** (Pàgines de cerca): `Extra Large Fix_mapa` | `Extra Large Variable_mapa` | `Large_mapa` | `Medium_mapa` | `Small_mapa`. Vegeu [Visor de mapa](component-visor-de-mapa.md).

## Accessibilitat
Quan es crea un formulari, consulta primer les instruccions d'accessibilitat específiques per a cada component utilitzat.

Indicacions generals:
- Permet que l'usuari pugui **navegar** pels resultats i altres elements (com filtres i ordenacions) **amb el teclat.** Assegura que hi ha un ordre de tabulació lògic i que el focus és visible.
- **Si una cerca no retorna resultats, mostra un missatge clar** que ho indiqui i **ofereix suggeriments per ajustar la cerca.**

## Vegeu també
[Exemples d'ús](exemple-exemples-d-us.md) · [Camp de cerca](component-camp-de-cerca.md) · [Llistat de resultats](component-llistat-de-resultats.md) · [Paginació](component-paginacio.md) · [Filtres](component-filtres.md)
