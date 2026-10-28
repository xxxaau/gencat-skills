# Fonts de coneixement (References)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/892f85 · Web component: `<references-component>` (paquet conversational) · Font actualitzada el 2026-07-10 · Extret el 2026-10-28

## Què és i quan usar-lo
Fonts que han generat una resposta del model dins una conversa de xat IA. *Component pendent de desenvolupament* (nota de la pàgina del lloc; la pestanya de versions registra el desenvolupament a la versió Github 12.0.0 del 10 juliol 2026) [a verificar].

Element interactiu inserit dins el cos del text d'una resposta de xat, indicant que aquell fragment concret té fonts externes verificables.

Quan s'utilitza:
- Quan la resposta del model es basa en fonts externes verificables (articles, documentació, webs oficials).
- Quan es vol donar transparència a l'usuari sobre l'origen de la informació proporcionada.
- Quan l'usuari pot beneficiar-se de llegir més informació al detall sobre un tema concret.

## Quan NO usar-lo / alternatives
- Quan la resposta és de coneixement general i no requereix citació de fonts específiques.
- Quan les fonts no han estat verificades o podrien induir a error a l'usuari.
- Quan el context de la conversa és casual i afegir fonts trencaria el flux natural del diàleg.

## Anatomia

### Fonts en línia
Figma: Inline reference drodpdown (Fonts de coneixement / Botó de xat / Inline reference drodpdown); Botó de xat [Show more references = False, Text = Etiqueta, More references text = +1, Collapsed = True, State = Default].

### Fonts globals
Figma: Botó de xat (Fonts de coneixement / Botó de xat / Global references / Collapsed = False).

## Variants, tipus i estats

### Referència en línia

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Collapsed | True / False | True |
| State | Default / Hover / Focus | Default |

Variant Figma (col·lapsat i estat): Botó de xat [Show more references = False, Text = Etiqueta, More references text = +1, Collapsed = True, State = Default].

### Desplegable de la referència en línia

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Slot | Content | Reference |

### Fonts globals

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Collapsed | True / False | True |
| State | Default / Hover / Focus | Default |

Variants Figma: Botó de xat (Fonts de coneixement / Botó de xat / Global references / Collapsed = True | False); Frame 1 [State = Default, Collapsed = True].

## Mides i espaiats
Construcció de les fonts de coneixement (vegeu Comportament, "Combinació de fonts de coneixement"): padding inferior de 8 px al contenidor del body; distància entre Body, divisor i fonts generals de 16 px.

## Comportament i interacció

### Fonts en línia
- **Clic sobre la píndola:** en fer clic sobre la píndola tancada, s'expandeix el desplegable amb el detall de les fonts. El desplegable s'insereix en el flux del document i empeny el contingut de sota cap avall, com un acordió; no se superposa al text adjacent. En fer clic sobre la píndola oberta, el desplegable es col·lapsa i el contingut de sota recupera la seva posició. Les fonts en línia obertes es mantenen així fins que l'usuari les tanca manualment. (Figma: Menu lateral, Fonts de coneixment / Components / Botó de xat / DOC_Fonts de coneixment / Menu lateral.)
- **Clic sobre l'enllaç:** en fer clic sobre l'enllaç dins el desplegable, s'obre la font en una nova pestanya per no perdre la conversa o procés en el qual es troba l'usuari i el desplegable roman obert.
- **Resposta generada progressivament:** si la resposta es genera de forma streaming, les píndoles inline poden aparèixer a mesura que es genera el text, i el resum final es mostra un cop la resposta és completa.
- **Aplicació en diferents tipus de xat:** el component es comporta de manera idèntica al xat en pantalla completa, lateral i flotant. No hi ha diferències estructurals ni funcionals entre contextos, únicament d'amplada disponible.

### Fonts globals
- **Clic sobre la capçalera:** en fer clic sobre la capçalera col·lapsada, la secció s'expandeix i mostra la llista de fonts. El contingut de sota es desplaça cap avall, igual que un acordió; no se superposa a cap element. En fer clic sobre la capçalera expandida, la secció es col·lapsa i el contingut de sota recupera la seva posició.
- **Clic sobre l'enllaç:** en fer clic sobre un enllaç dins la secció expandida, s'obre la font en una nova pestanya. La secció roman oberta.
- **Aplicació en diferents tipus de xat:** el component es comporta de manera idèntica al xat en pantalla completa, lateral i flotant. No hi ha diferències estructurals ni funcionals entre contextos, únicament d'amplada disponible. (Figma: Pantalla completa, Fonts de coneixment / Components / Botó de xat / DOC_Fonts de coneixment / Pantalla completa.)

### Combinació de fonts de coneixement
Les referències en línia apareixen distribuïdes al llarg del cos del text. Les globals es troben sempre al final del missatge, després de tot el contingut textual i separat per un divisor. Per construir les fonts de coneixement correctament dins els diferents xats cal:
1. Veure en quin contenidor es col·locarà el text i adaptar l'amplada d'una caixa de text a l'espai disponible. (Figma: Construcció_01.)
2. Muntar el text a part i col·locar la píndola de forma que quedi just després del text. Si hi ha espai perquè quedi a la mateixa línia que l'última paraula, cal agrupar l'última línia i la píndola dins d'un frame amb auto-layout. (Figma: Construcció_02.)
3. Un cop es tingui el text, introduir-lo dins el contenidor necessari. (Figma: Construcció_03.)
4. Al final de tot, col·locar el component de referències general separat per un divisor. Al contenidor del body cal aplicar-li un padding inferior de 8 px. La distància entre Body, divisor i fonts generals serà de 16 px. (Figma: Construcció_04.)
5. Per mostrar una de les fonts oberta, col·locar-la just per sota de la font de coneixement en línia, amb aquesta en la seva versió no col·lapsada. (Figma: Construcció_05.)

(Els frames Figma de construcció són de la forma Fonts de coneixment / Components / Botó de xat / DOC_Fonts de coneixment / Construcció_0N.)

## Contingut i microcopy
Exemples dels textos de l'exemple de codi: etiqueta "Etiqueta"; títol del desplegable en mode inline "Fonts utilitzades en el fragment (Lorem ipsum)"; títol en mode global "Fonts d'aquesta resposta (3)"; textos d'enllaç "Tràmits i gestions - Departament de Salut", "Centre de Telecomunicacions i Tecnologies de la Informació", "Seu electrònica de la Generalitat de Catalunya"; dominis `gencat.cat`, `ctti.gencat.cat`, `seu.gencat.cat`.

## Bones pràctiques

### Genèriques
- **NO FER:** No mostris URLs crues; sempre usa un títol llegible com a text de l'enllaç.
- **FER:** Indica clarament el nom de la font (domini web) per ajudar l'usuari a avaluar la credibilitat.

### Fonts en línia
- **FER:** Mostra les fonts en línia just després del paràgraf on es referencien.
- **NO FER:** No mostris les fonts en línia al mig d'una frase o paràgraf.

### Fonts globals
- **FER:** Mostra les fonts globals sempre al final del missatge, separades del cos del text per un divisor horitzontal.
- **FER:** Indicar el nombre total de fonts a la capçalera per ajudar l'usuari a decidir si vol expandir la secció.
- **FER:** Mantingues l'ordre de les fonts consistent amb l'ordre en què apareixen referenciades al text, si escau.

## Accessibilitat
Pautes d'accessibilitat del contingut web (WCAG) que cita el component:
- **1.4.1 Ús del color (A):** el color no s'utilitza com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a diferenciar els diferents estats. (La font acaba la frase així.) (https://www.w3.org/Translations/WCAG22-ca/#use-of-color · https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **1.4.3 Contrast mínim (AA):** els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. (https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum · https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **1.4.4 Canvia la mida del text (AA):** excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. (https://www.w3.org/Translations/WCAG22-ca/#resize-text · https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **1.4.12 Espaiat del text (AA):** quan es desenvolupa contingut utilitzant llenguatges de marcatge que permeten aplicar les propietats d'estil de text, no es perd cap contingut ni funcionalitat si s'ajusten les propietats següents: alçada de línia (interlineat) de com a mínim 1,5 vegades la mida de la lletra; espaiat entre els paràgrafs de com a mínim dues vegades la mida de la lletra; espaiat entre lletres (*tracking*) de com a mínim 0,12 vegades la mida de la lletra; espaiat entre paraules de com a mínim 0,16 vegades la mida de la lletra. (https://www.w3.org/Translations/WCAG22-ca/#text-spacing · https://www.w3.org/WAI/WCAG22/Understanding/text-spacing)
- **2.1.1 Teclat (A):** tota la funcionalitat del contingut es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. (https://www.w3.org/Translations/WCAG22-ca/#keyboard · https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **2.4.7 Focus visible (AA):** la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. (https://www.w3.org/Translations/WCAG22-ca/#focus-visible · https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)

### Lector de pantalla
- **Fonts en línia:** el lector de pantalla, quan se situï sobre les fonts de coneixement en línia, llegirà les primeres 3 paraules del paràgraf al qual fa referència, el domini visible i, si hi ha més fonts, el nombre de N fonts extres. Per exemple, amb la frase generada "La transició energètica requereix una inversió pública sostinguda [gencat.cat +2]", el lector de pantalla llegiria:
  - Font tancada: "Font de 'la transició energètica', gencat.cat, i 2 fonts més, replegat"
  - Font oberta: "Font de 'la transició energètica', gencat.cat, i 2 fonts més, desplegat"
- **Fonts globals:** el lector llegirà el títol del desplegable, per exemple:
  - Font tancada: "Fonts d'aquesta respota (8), replegat"
  - Font oberta: "Fonts d'aquesta respota (8), desplegat"
  - Un cop obert, i en desplaçar-se als enllaços, llegirà cadascun a mesura que hi vagi fent focus.

## Implementació (component web)

### `<references-component>`
Paquet: conversational.

**Propietats**

Taula de la pàgina del lloc (amb obligatorietat):

| Propietat | Atribut HTML | Descripció | Obligatorietat | Tipus |
|---|---|---|---|---|
| `label` | `label` | Títol de l'etiqueta que obre el desplegable en mode `inline` | Obligatori | String |
| `mode` | `mode` | Tipus de font de coneixement | Obligatori | String |
| `moreReferencesCount` | `more-references-count` | Comptador del nombre de referències en mode `inline` | Opcional | Number |
| `references` | `references` | Informació de les fonts de coneixement | Obligatori | String \|\| Array |
| `referencesTitle` | `references-title` | Títol del desplegable que conté totes les fonts de coneixement | Obligatori | String |

Valors per defecte i matisos segons el PDF (v12.0.0):

| Propietat | Atribut HTML | Descripció (PDF) | Tipus | Per defecte |
|---|---|---|---|---|
| `label` | `label` | Etiqueta descriptiva de l'element. | string | `Etiqueta` |
| `mode` | `mode` | Variant visual del component. Opcions: `global`, `inline`. | string | `inline` |
| `moreReferencesCount` | `more-references-count` | Valor numèric. | number | 0 |
| `references` | `references` | Referències mostrades al component. Accepta array d'objectes o string JSON. | `ReferenceItem[] \| string` | (no indicat) |
| `referencesTitle` | `references-title` | Títol del component. | string | `` (cadena buida) |

**Variants (lloc)**

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `mode` | `inline` `global` | `inline` |

**Props que accepten JSON:** `references` — string JSON (array d'objectes) amb l'estructura `ReferenceItem`.

Segons el lloc (propietats del string `references`):

| Propietat | Atribut | Descripció | Obligatorietat | Tipus |
|---|---|---|---|---|
| `domainLabel` | `domain-label` | Domini de l'etiqueta de la font de coneixement | Obligatori | String |
| `linkText` | `link-text` | Text de l'enllaç | Obligatori | String |

Segons el PDF:

| Clau | Tipus | Requerida |
|---|---|---|
| `domainLabel` | string | No |
| `linkText` | string | Sí |

[discrepància: el lloc diu que `domainLabel` és obligatori; el PDF diu que no és requerida]

```json
[
{
"domainLabel": "texto-ejemplo",
"linkText": "texto-ejemplo"
}
]
```

**Esdeveniments**

| Esdeveniment | Descripció | Paràmetre | Origen | Tipus (PDF) |
|---|---|---|---|---|
| `referenceItemClicked` | Esdeveniment llançat en fer clic sobre l'enllaç d'una referència (PDF: s'emet quan l'usuari fa clic al component) | item | `reference-component` | `CustomEvent<ReferenceItem>` |

**Exemple d'ús (lloc)**

```html
<!-- /index.html -->
<!--Font de coneixement mode inline-->
<references-component 
  mode="inline" 
  label="Etiqueta" 
  more-references-count="1"
  references-title="Fonts utilitzades en el fragment (Lorem ipsum)"
  references='[{"domainLabel": "gencat.cat", "linkText": "Tràmits i gestions - Departament de Salut"}]'>
</references-component>

<!--Font de coneixement mode global-->
<references-component
  mode="global" 
  references-title="Fonts d'aquesta resposta (3)" 
  references='[
      {"domainLabel": "gencat.cat", "linkText": "Tràmits i gestions - Departament de Salut"},
      {"domainLabel": "ctti.gencat.cat", "linkText": "Centre de Telecomunicacions i Tecnologies de la Informació"},
      {"domainLabel": "seu.gencat.cat", "linkText": "Seu electrònica de la Generalitat de Catalunya"}
  ]'>
</references-component>
```

**Exemple d'instància (PDF)**

```html
<references-component
label='Etiqueta'
mode='inline'
more-references-count=0
references=[]
references-title=''
></references-component>
```

Exemple amb props JSON (PDF):

```html
<references-component
references='[{"domainLabel":"texto-ejemplo","linkText":"texto-ejemplo"}]'
></references-component>
```

**Depèn de:** `link-component` (paquet core; [Enllaços](component-enllacos.md)).

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 5.1.0 | 12.0.0 | 10 juliol, 2026 | Desenvolupament del component |
| 5.1.0 | - | 19 juny, 2026 | Disseny i documentació del component |

## Vegeu també
- [Missatge de xat](component-missatge-de-xat.md), [Enllaços](component-enllacos.md), [Divisor](component-divisor.md), [Acordió](component-acordio.md)
