# Text destacat (Highlight text)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/264f60 · Web component: `<highlight-text-component>` (paquet core) · Font actualitzada el 2026-10-27 · Extret el 2026-10-28

## Què és i quan usar-lo
S'utilitza per captar l'atenció de l'usuari, guiar-lo en la navegació o reforçar missatges clau. Es pot mostrar com un *pull quote* (idea destacada) o *block quote* (cita literal) amb un estil diferenciat.

El **text destacat** s'utilitza per ressaltar una idea rellevant dins del contingut. Es pot mostrar en dos formats:
- Cita literal (*block quote*).
- Fragment d'idea o destacat (*pull quote*, idea destacada).

Quan s'utilitza:
- Quan es vol ressaltar una frase, una conclusió, una idea principal o una declaració significativa en un article o reportatge: s'utilitza la idea destacada (*pull quote*).
- Quan el contingut conté cites d'experts, personatges públics o autors que aporten valor a la narració i en donen més credibilitat: s'utilitza el *block quote* (cita literal).

## Quan NO usar-lo / alternatives
- Quan es vulgui comunicar un estat específic o una notificació que requereixi una acció per part de l'usuari: utilitza un avís ([Avisos](component-avisos.md)).
- Per destacar informació, guiar l'usuari entre seccions i comunicar contingut clau: utilitza una targeta destacada ([Targetes](component-targetes.md)).
- Evita'n l'ús en components com targetes, capçaleres, formularis, titulars o subtítols.

## Anatomia
- *Pull quote* (idea destacada): la font només mostra la imatge d'anatomia.
- *Block quote* (cita literal): la font només mostra la imatge d'anatomia.

## Variants, tipus i estats

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Quote Type | Block quote / Pull quote | - |
| Source | True / False | True |

## Comportament i interacció

### Adaptació responsiva
- El component ha de ser adaptable a diferents dispositius i resolucions.
- Quan es mostra l'element *pull quote* (idea destacada) en un lateral de la pàgina en dispositius grans, l'adaptació a dispositius petits fa que es desplaci sota la imatge inicial o, si no n'hi ha, a l'inici del contingut.

## Contingut i microcopy
Sempre s'ha d'indicar la font de la cita quan sigui necessari. Per al *block quote*, la font (autor citat) és obligatòria; per al *pull quote*, opcional.

## Bones pràctiques

### Com s'utilitza

**Claredat i rellevància**
- **FER:** Les cites han de ser curtes i significatives, col·locades estratègicament per facilitar la lectura i captar l'atenció.

**Introducció de fonts**
- **FER:** Indica sempre la font de la cita quan sigui necessari.

### Com no utilitzar

**Saturació del contingut**
- **FER:** Utilitza el text destacat amb moderació per mantenir la llegibilitat i l'equilibri visual.
- **NO FER:** No abusis del text destacat fins al punt de saturar el contingut i dificultar-ne la lectura.

**Interrupció de la lectura**
- **FER:** Integra les cites de manera natural perquè no interrompin el flux de lectura.
- **NO FER:** No insereixis cites de forma abrupta que trenquin la coherència del text.

**Cites excessivament llargues**
- **FER:** Resumeix les cites llargues per fer-les més clares i fàcils de comprendre.
- **NO FER:** No deixis cites excessivament llargues sense adaptar-les o sintetitzar-les.

## Accessibilitat
Pautes WCAG:
- **Contrast mínim (AA) – 1.4.3:** cal garantir un contrast mínim de **4.5:1** per a text normal i **3:1** per a text gran. Els elements inactius o deshabilitats en són excepció. [CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA) – 1.4.4:** excepte subtítols i imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Informació i relacions (A) – 1.3.1:** perquè els lectors de pantalla interpretin correctament una cita destacada, s'han d'utilitzar les etiquetes adequades. [CAT](https://www.w3.org/Translations/WCAG21-ca/#info-and-relationships) / [EN](https://www.w3.org/WAI/WCAG21/Understanding/info-and-relationships.html)

## Implementació (component web)

### `<highlight-text-component>`

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Obligatori | Per defecte |
|---|---|---|---|---|---|
| `highlightSource` | `highlight-source` | Autor citat o font (font del text sobre el qual s'aplica el ressaltat). | string | Obligatori per a Blockquote, opcional per a Pullquote | `` |
| `highlightText` | `highlight-text` | Text destacat (fragment de text que es ressalta visualment). | string | Obligatori | `undefined` |
| `pullquote` | `pullquote` | Determina si el text es mostra com una citació destacada (Pullquote) o com un bloc normal (Blockquote). | boolean | Obligatori | `true` |

**Esdeveniments:** sense esdeveniments declarats.

**Exemple d'ús (pàgina)**

```html
<!-- /index.html -->
<highlight-text-component
  highlight-text="Lorem ipsum dolor sit amet consectetur. Praesent pellentesque eu cras in tortor nunc faucibus. Morbi risus quam vestibulum quisque nunc malesuada egestas iaculis."
  highlight-source="Lorem ipsum dolor sit amet consectetur."
  pullquote="true"
  >
</highlight-text-component>
```

**Exemple d'instància (PDF)**

```html
<highlight-text-component
highlight-source=''
highlight-text="texto-ejemplo"
pullquote=true
></highlight-text-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 2.4.0 | 2.0.0 | 10 març, 2025 | Disseny i desenvolupament del component. |

## Vegeu també
- [Avisos](component-avisos.md): missatges contextuals que comuniquen un estat específic d'una pàgina.
- [Targetes](component-targetes.md): bloc visual i funcional que organitza contingut relacionat (targeta destacada).
