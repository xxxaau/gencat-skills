# Arbre de decisions (Decision tree)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/91809c · Patró · Font actualitzada el 2026-06-09 · Extret el 2026-10-28

## Què és i quan usar-lo
Patró que serveix per guiar l'usuari a través d'una selecció complexa, mostrant només les opcions rellevants en funció de decisions prèvies, fins arribar a un resultat final (grau, màster, doctorat, etc.).

## Estructura del flux: flux dirigit vs filtratge progressiu

### Flux dirigit (Routing Trees)
Un arbre de rutes guia l'usuari per un únic camí actiu. Cada resposta determina quina és la següent pregunta, fins arribar a una conclusió.

**Quan utilitzar-lo**
- Resolució de problemes tècnics o funcionals.
- Assistents pas a pas.
- Validacions d'elegibilitat.

**Quan no utilitzar-lo**
- Quan totes les preguntes són rellevants per a tothom.
- Quan l'objectiu és comparar resultats.
- Quan no hi ha una solució correcta.

**Exemple 1 — Binari (diagnòstic tècnic):** ajuda l'usuari a detectar per què no pot accedir a una plataforma.
Figma: Filtratge orientatiu_Exemple01.

**Exemple 2 — Multi-camí (tràmit administratiu):** un usuari vol fer un tràmit, però el procés canvia completament segons la selecció inicial.
Figma: Flux dirigit_Exemple02.

### Filtratge progressiu (Elimination Trees)
Tots els resultats possibles existeixen des del principi. Cada resposta no crea una nova ruta, sinó que elimina resultats incompatibles fins que en queda un o uns quants. L'arbre no és visible, però la decisió sí.

**Quan utilitzar-lo**
- Recomanadors.
- Orientadors (educació, finançament, serveis).
- Cercadors guiats.
- Matching de polítiques, ajuts, productes.

**Quan no utilitzar-lo**
- Quan l'usuari necessita entendre explícitament totes les rutes.
- Quan la decisió és purament seqüencial.
- Quan es vol resoldre un problema concret.
- Quan hi ha una solució correcta única.
- Quan és més ràpid obtenir el resultat a través de filtres.

**Exemple orientatiu 1 — Finançament empresarial:** orientar una empresa cap a les línies de finançament disponibles. (Exemple orientatiu de les preguntes i respostes, no del flux complet.) Figma: Filtratge orientatiu_Exemple01.
- **Resultat:** el sistema elimina opcions incompatibles i mostra els ajuts o productes aplicables.
- **Per què és filtratge progressiu:** les preguntes no canvien; el que varia és el resultat final, que es basa en la combinació de respostes.

**Exemple 2 — Orientació educativa.** Figma: Filtratge orientatiu_Exemple02.

## Presentació de les preguntes

### Preguntes progressives
Les preguntes es mostren pas a pas, una darrere l'altra, ja sigui en pàgines diferents o en la mateixa.

- **Quan utilitzar-lo:** usuaris no experts; decisions complexes; context institucional o públic.
- **Avantatges:** guia l'usuari; redueix la càrrega cognitiva; millor comprensió del procés.
- **Limitacions:** més lent per a usuaris experts.

Figma: Presentació de les preguntes_Progressives.

### Preguntes visibles
Tots els criteris estan visibles des del principi i l'usuari en selecciona un de cada.

- **Quan utilitzar-lo:** comparació ràpida; quan només hi ha un **màxim de 3 preguntes.**
- **Avantatges:** control total; més ràpid per iterar.
- **Limitacions:** més càrrega cognitiva; pot generar errors si l'usuari no entén els criteris.

Figma: Nombre de preguntes (do).

## Disposició de les preguntes en pantalla

### Una pregunta per pantalla
Les preguntes es mostren pas a pas, una darrere l'altra, cadascuna en la seva pròpia pantalla.

- **Quan utilitzar-lo:**
  - La decisió és complexa o sensible.
  - No cal que l'usuari revisi contínuament respostes anteriors.
  - El procés té un caràcter guiat i seqüencial fort.
  - Les respostes anteriors no aporten context útil per entendre la pregunta actual.
- **Avantatges:**
  - Guia l'usuari.
  - Redueix la càrrega cognitiva.
  - Millor comprensió del procés.
- **Limitacions:**
  - Menys visibilitat del context acumulat.
  - Pot generar sensació de "caixa negra" si no hi ha resum final.
  - Requereix indicador de progrés clar.

Figma: Presentació de les preguntes_Per pantalla 01 | Per pantalla 02.

### Preguntes progressives dins la mateixa pàgina
Cada pregunta apareix sota l'anterior de forma que les respostes queden visibles i l'usuari veu el raonament que està construint.

- **Quan utilitzar-lo:**
  - L'usuari es beneficia de veure el context complet.
  - El procés és orientatiu, no normatiu.
  - Es vol reforçar la transparència i la confiança.
  - La complexitat ve de la combinació de respostes, no de cada pas individual.
- **Avantatges:**
  - Millora la comprensió del procés.
  - Facilita revisar i modificar respostes.
  - Fa visible la lògica d'eliminació.
  - Redueix la sensació d'arbitrarietat.
- **Limitacions:**
  - Augment de la longitud visual de la pàgina.
  - Pot augmentar la càrrega cognitiva si les preguntes són complexes.
  - Gestió del focus i lectura seqüencial més exigent.

Figma: Presentació de les preguntes_Dins de pàgina 01 | 02 | 03 | 04.

## Anatomia
Elements bàsics que ha de tenir el patró. Figma: Anatomia_en pàgina | Anatomia_per passos.

## Comportament

### Interacció entre preguntes dins una mateixa pantalla

**Avançar entre els passos.** L'usuari selecciona una o diverses opcions del pas actiu i prem "Continua". La pregunta següent apareix immediatament a sota i el botó es desplaça juntament amb les preguntes i s'inclou dins l'scroll de pàgina.

**Modificar la resposta d'un pas anterior.** L'usuari clica directament sobre una opció diferent en qualsevol pas completat. En el moment del clic succeeix el següent:
- La nova opció queda seleccionada i la resposta anterior es deselecciona.
- Tots els passos posteriors al modificat desapareixen.
- El botó "Continua" queda associat al pas que s'acaba de modificar.
- L'usuari prem "Continua" per continuar el flux des d'aquell punt.

**Modifica la selecció un cop s'ha mostrat els resultats.** Quan es mostren els resultats el botó desapareix i l'usuari pot modificar les opcions clicant sobre les respostes. Al seleccionar-ne una, les preguntes posteriors desapareixen al igual que els resultats i es torna a mostrar el botó de continua o de mostra resultats (en funció de la pregunta modificada).

### Interacció entre preguntes en passos (diferents pàgines)

**Avançar entre els passos.** L'usuari selecciona una o diverses opcions del pas actiu i prem "Continua". El pas següent apareix immediatament en una nova pàgina.

**Modificar la resposta d'un pas anterior.** L'usuari clica directament sobre el botó "Torna enrere" per tornar al pas anterior i modificar-ne la resposta. Un cop fet el canvi tornarà a prèmer el botó "Continua".

### Adaptació responsive
El contingut de l'arbre s'adapta a l'amplada de pantalla. Si el contingut d'un o diversos camps no cap en una línia, saltarà a una segona.

## Bones pràctiques

### General
**Nombre de preguntes**
- **FER:** Si l'arbre te un màxim de 3 preguntes, pots mostrar totes visibles des d'un inici.
- **NO FER:** Si l'arbre te més de 5 preguntes no utilitzis la versió amb preguntes progressives dins la mateixa pantalla.

**Progrés**
- **FER:** Mostra el progrés per reduir la sensació d'esforç i reforçar la confiança en el procés.
- **FER:** Al mostrar els resultats indica el context acumulat per ajudar l'usuari a entendre per què obté uns resultats concrets.

**Resultats**
- **FER:** Quan els resultats apareixen en pàgina nova indica de forma clara quines respostes han propiciat aquell resultat.

### Flux dirigit
**Transparència del flux**
- **FER:** Fes explícit que el flux canvia segons la resposta per tal que l'usuari entengui que cadascuna d'elles condiciona el camí i no totes les opcions porten al mateix lloc.
- **NO FER:** No facis canvis de flux sense avisar, ja que l'usuari pot pensar que totes les opcions porten al mateix lloc i respondre sense entendre les conseqüències.

**Rellevància de les preguntes**
- **FER:** Assegura que cada pregunta tingui sentit només dins del camí en què apareix. Les preguntes genèriques poden portar l'usuari a un camí incorrecte.

**Resultat final**
- **FER:** Assegura que cada ruta acabi amb una acció, solució o conclusió explícita, coherent amb les respostes donades.
- **NO FER:** No facis que camins diferents acabin amb el mateix resultat genèric, perquè elimina el valor del routing i genera desconfiança.

**Cas sense resultat**
- **FER:** Assegura que totes les rutes acabin amb una conclusió, encara que sigui negativa. Ofereix sempre una acció següent, com: tornar enrere, canviar resposta o contactar amb suport. El routing tree no pot acabar en un buit.

### Filtratge progressiu
**Transparència del flux**
- **FER:** Deixa clar que les preguntes no són per classificar l'usuari, sinó per ajudar el sistema a mostrar opcions adequades.
- **NO FER:** No facis preguntes sense explicar per a què serveixen, perquè l'usuari pot percebre el procés com un formulari arbitrari.

**Consistència del flux**
- **FER:** Totes les persones han de respondre les mateixes preguntes. El que varia és el resultat, no el flux.
- **NO FER:** No incloguis preguntes que no influeixin realment en el resultat, ja que només afegeixen càrrega cognitiva sense valor.

**Claredat de les opcions**
- **FER:** Assegura que les opcions siguin fàcils d'identificar i no es solapin. Quan el concepte pot generar dubtes, cal ajudar l'usuari amb microcopy explicatiu.
- **NO FER:** No utilitzis opcions poc clares o que se solapin, perquè l'usuari pot seleccionar una resposta incorrecta sense adonar-se'n.

**Resultat**
- **FER:** Assegura que el resultat no sigui opac. Cal explicar per què s'ha mostrat cada opció.
- **NO FER:** No presentis els resultats com a decisions opaques, ja que redueix la confiança i la percepció de valor del sistema.
- **NO FER:** No ignoris els casos en què no hi ha resultats, perquè deixes l'usuari bloquejat sense alternatives.

**Cas sense resultat**
- **FER:** Explica explícitament que la manca de resultats és una conclusió del procés, no un error, per evitar que l'usuari percebi que ha fet alguna cosa malament.
- Indica de manera clara per què no hi ha opcions disponibles, aclarint que la combinació de criteris pot ser molt específica en el moment actual.
- Ofereix alternatives clares i orientatives, com contactar amb un assessor o consultar altres vies, per evitar deixar l'usuari bloquejat.

### Icones i il·lustracions
**Icones.** Les icones s'han d'utilitzar només per reforçar el reconeixement visual de categories clares i estables en què la icona sigui un estàndard. El text visible ha de ser sempre suficient per entendre completament el concepte, de manera que l'usuari pugui prendre la decisió sense dependre de la icona. La funció de la icona és accelerar l'escaneig, no explicar ni interpretar el contingut. Si el concepte requereix matís, autoavaluació o interpretació, no s'han d'utilitzar icones.

**Il·lustracions.** S'utilitzaran únicament en la mida Large (92x92px) i sempre que es compleixi el següent:
- Les opcions es diferencien principalment per una configuració física, espacial o funcional visible.
- El concepte no és normatiu ni administratiu, sinó material o d'intervenció física.
- El text (encara que sigui correcte) no permet visualitzar amb facilitat la diferència real entre opcions.
- La il·lustració aporta informació objectiva i neutral, no aspiracional ni emocional.
- El text visible (títol + descripció) és suficient per entendre l'opció sense dependre de la imatge, i la il·lustració només actua com a suport.
- La il·lustració disposa de text alternatiu equivalent per garantir l'accessibilitat.

Exemples:
- Tipus d'adaptacions o intervencions físiques com rampa, plataforma elevadora, ascensor adaptat, lavabo accessible, on la diferència clau és l'espai ocupat i la solució constructiva.
- Tipus d'instal·lacions o equipaments físics com pista coberta vs descoberta, tipus d'espai esportiu o comunitari, on la configuració defineix l'ús possible.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG):

- **Orientació (AA)** — 1.3.4. El contingut de l'àrea de text s'adapta a les diferents orientacions de la pantalla, com ara vertical o horitzontal, cosa que permet visualitzar el contingut. [CAT](https://www.w3.org/Translations/WCAG22-ca/#orientation) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html)
- **Ús del color (A)** — 1.4.1. El color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a diferenciar els diferents estats s'inclouen subratllats, es juga amb la presència de farciment i el gruix de la vora. [CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA)** — 1.4.3. Els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA)** — 1.4.4. Excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA)** — 1.4.11. Els elements gràfics com icones i vores presenten un contrast mínim de 3:1. [CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A)** — 2.1.1. Tota la funcionalitat del contingut (navegar pels diferents botons) es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Ordre del focus (A)** — 2.4.3. Quan apareix un nou pas, el focus del teclat es mou automàticament al títol o al primer element interactiu del nou pas en el moment en què apareix. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-order) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-order)
- **Focus visible (AA)** — 2.4.7. La navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- **Identificació d'errors (A)** — 3.3.1. Si es detecta un error en el component, s'identifica clarament que aquest presenta un error mitjançant un canvi de color i gruix de la vora i amb la indicació visual (icona) i textual (descripció de l'error) de l'error. [CAT](https://www.w3.org/Translations/WCAG22-ca/#error-identification) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/error-identification)
- **Missatges d'estat (AA)** — 4.1.3. Cal informar els usuaris dels canvis importants en el contingut de forma que la tecnologia assistiva notifiqui als usuaris els canvis d'estat que no prenen el focus. Es realitza a través de les etiquetes `role="alert"` i quan `aria-live="polite"`. [CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible) (els enllaços de la font per a aquest criteri apunten a l'ancoratge `focus-visible`).

### Navegació per teclat
Per consultar la navegació per teclat del patró, consulteu la documentació específica dels components utilitzats:
- [Botons](component-botons.md) (font: https://sistemadedisseny.gencat.cat/38669693e/p/36e8ca-botons/b/59a3a6)
- [Botó d'opció](component-boto-d-opcio.md) (font: https://sistemadedisseny.gencat.cat/38669693e/p/828815-boto-dopcio/b/5176fc)
- [Casella de selecció](component-casella-de-seleccio.md) (font: https://sistemadedisseny.gencat.cat/38669693e/p/542d59-casella-de-seleccio/b/18a7c7)

## Components implicats
[Botons](component-botons.md), [Botó d'opció](component-boto-d-opcio.md), [Casella de selecció](component-casella-de-seleccio.md).

## Historial de versions
| Versió Figma | Data | Descripció |
|---|---|---|
| 11.0.0 | 8 maig, 2026 | Disseny i documentació del patró |
