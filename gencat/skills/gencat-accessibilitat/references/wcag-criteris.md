# Criteris WCAG 2.1 A+AA Obligatoris — Gencat

50 criteris obligatoris (EN 301 549 V3.2.1, segment C9 Web).
Nivell A: 30 criteris | Nivell AA: 20 criteris

---

## PRINCIPI 1: PERCEPTIBLE

### 1.1 Alternatives de text

| Criteri | Nivell | Nom | Requisit tècnic |
|---------|--------|-----|-----------------|
| **1.1.1** | A | Contingut no textual | Tot contingut no textual té alternativa de text. Decoratives: `alt=""`. Complexes: `alt` curt + `aria-describedby`. |

### 1.2 Mitjans de temps

| Criteri | Nivell | Nom | Requisit tècnic |
|---------|--------|-----|-----------------|
| **1.2.1** | A | Només àudio / Només vídeo | Àudio: transcripció de text. Vídeo sense àudio: alternativa de text o àudio. |
| **1.2.2** | A | Subtítols (pregravat) | Subtítols per a tot l'àudio en vídeo sincronitzat pregravat. |
| **1.2.3** | A | Audiodescripció o alternativa | Audiodescripció o alternativa de text per a vídeo pregravat. |
| **1.2.4** | AA | Subtítols (en directe) | Subtítols per a tot l'àudio en vídeo en directe. |
| **1.2.5** | AA | Audiodescripció (pregravat) | Audiodescripció per a tot el vídeo pregravat sincronitzat. |

### 1.3 Adaptable

| Criteri | Nivell | Nom | Requisit tècnic |
|---------|--------|-----|-----------------|
| **1.3.1** | A | Informació i relacions | Estructura determinable programàticament. Usa HTML semàntic: `<h1-h6>`, `<ul>/<ol>`, `<table>` amb `<th scope>`, `<fieldset>/<legend>`. |
| **1.3.2** | A | Seqüència significativa | L'ordre de lectura és determinable programàticament. |
| **1.3.3** | A | Característiques sensorials | Les instruccions no depenen únicament de forma, mida, posició visual, orientació o so. |
| **1.3.4** | AA | Orientació | El contingut no es restringeix a una sola orientació (portrait/landscape). No usar `orientation: lock`. |
| **1.3.5** | AA | Identificació de la finalitat de l'entrada | Camps que recullen informació personal usen atributs `autocomplete` de la llista HTML. |

```html
<!-- 1.3.5: autocomplete correcte -->
<input type="text" autocomplete="given-name" id="nom">
<input type="text" autocomplete="family-name" id="cognom">
<input type="email" autocomplete="email" id="email">
<input type="tel" autocomplete="tel" id="telefon">
```

### 1.4 Distingible

| Criteri | Nivell | Nom | Requisit tècnic |
|---------|--------|-----|-----------------|
| **1.4.1** | A | Ús del color | El color no és l'únic mitjà visual per transmetre informació. Complementa amb text, icona o patró. |
| **1.4.2** | A | Control d'àudio | Àudio automàtic >3 segons: mecanisme per pausar/aturar/controlar volum. |
| **1.4.3** | AA | Contrast (mínim) | Text normal: **4.5:1**. Text gran (≥18pt o ≥14pt negreta): **3:1**. |
| **1.4.4** | AA | Canvi de mida del text | Text redimensionable fins al 200% sense pèrdua de contingut ni funcionalitat. No usar `px` fixes per a mides de lletra. |
| **1.4.5** | AA | Imatges de text | No usar imatges de text (excepte logotips). |
| **1.4.10** | AA | Reajust | Sense desplaçament bidimensional a 320px d'amplada (equivalent a 400% de zoom en pantalla de 1280px). |
| **1.4.11** | AA | Contrast de contingut no textual | Components UI i elements gràfics: **3:1** contra colors adjacents. |
| **1.4.12** | AA | Espaiat del text | Sense pèrdua de contingut amb: altura de línia ≥ 1,5×; espaiat de paràgraf ≥ 2×; espaiat de lletra ≥ 0,12em; espaiat de paraula ≥ 0,16em. |
| **1.4.13** | AA | Contingut en passar per sobre o en rebre el focus | Contingut addicional en hover/focus ha de ser: descartable (Escape), apuntable (el cursor hi pot entrar) i persistent. |

```css
/* 1.4.4: usa unitats relatives */
body { font-size: 1rem; }        /* Bé */
body { font-size: 16px; }        /* Evita per a base */

/* 1.4.12: no bloquejar espaiat */
p { line-height: 1.5; letter-spacing: normal; }  /* Bé: no usar !important */
```

---

## PRINCIPI 2: OPERABLE

### 2.1 Accessible per teclat

| Criteri | Nivell | Nom | Requisit tècnic |
|---------|--------|-----|-----------------|
| **2.1.1** | A | Teclat | Tota la funcionalitat és operable per teclat sense requerir timings específics. |
| **2.1.2** | A | Sense trampa de teclat | El focus de teclat no queda atrapat en cap component. |
| **2.1.4** | A | Dreceres de tecla de caràcter | Les dreceres de caràcter únic es poden desactivar, reassignar o activar només en focus. |

### 2.2 Temps suficient

| Criteri | Nivell | Nom | Requisit tècnic |
|---------|--------|-----|-----------------|
| **2.2.1** | A | Temps ajustable | Els límits de temps es poden desactivar, ajustar o estendre. |
| **2.2.2** | A | Pausa, atura, amaga | Contingut en moviment/parpelleig: control per pausar/aturar/amagar. |

### 2.3 Convulsions i reaccions físiques

| Criteri | Nivell | Nom | Requisit tècnic |
|---------|--------|-----|-----------------|
| **2.3.1** | A | Tres parpellejos o per sota del llindar | Cap element parpelleja més de 3 vegades per segon. |

### 2.4 Navegable

| Criteri | Nivell | Nom | Requisit tècnic |
|---------|--------|-----|-----------------|
| **2.4.1** | A | Omissió de blocs | Skip link al contingut principal. |
| **2.4.2** | A | Pàgina titulada | Títols de pàgina descriptius i únics. Format recomanat: "Secció — Lloc web". |
| **2.4.3** | A | Ordre del focus | L'ordre de focus preserva el significat i l'operabilitat. |
| **2.4.4** | A | Propòsit de l'enllaç (en context) | El propòsit de l'enllaç és determinable pel text o el context. Evita "aquí", "cliqueu aquí", "llegiu més". |
| **2.4.5** | AA | Múltiples vies | Més d'una manera de localitzar una pàgina (mapa web, cerca, navegació). |
| **2.4.6** | AA | Encapçalaments i etiquetes | Encapçalaments i etiquetes descriptius. |
| **2.4.7** | AA | Focus visible | L'indicador de focus de teclat és visible. No usar `outline: none`. |

### 2.5 Modalitats d'entrada

| Criteri | Nivell | Nom | Requisit tècnic |
|---------|--------|-----|-----------------|
| **2.5.1** | A | Gestos de punter | Els gestos multipunt o de trajectòria tenen alternativa de punter únic. |
| **2.5.2** | A | Cancel·lació del punter | L'esdeveniment `down` no executa funcions (o es pot abortar/desfer). |
| **2.5.3** | A | Etiqueta en el nom | El nom accessible dels components inclou el text de l'etiqueta visible. |
| **2.5.4** | A | Actuació per moviment | Les funcions activades per moviment del dispositiu tenen controls alternatius i es poden desactivar. |

---

## PRINCIPI 3: COMPRENSIBLE

### 3.1 Llegible

| Criteri | Nivell | Nom | Requisit tècnic |
|---------|--------|-----|-----------------|
| **3.1.1** | A | Idioma de la pàgina | L'idioma per defecte és determinable programàticament: `<html lang="ca">`. |
| **3.1.2** | AA | Idioma de les parts | Els canvis d'idioma dins la pàgina s'identifiquen: `<span lang="es">texto en castellano</span>`. |

### 3.2 Predictible

| Criteri | Nivell | Nom | Requisit tècnic |
|---------|--------|-----|-----------------|
| **3.2.1** | A | En rebre el focus | Cap canvi de context en rebre el focus. |
| **3.2.2** | A | En l'entrada | Cap canvi de context automàtic en l'entrada de l'usuari. |
| **3.2.3** | AA | Navegació coherent | La navegació repetida entre pàgines manté el mateix ordre. |
| **3.2.4** | AA | Identificació coherent | Els components amb la mateixa funcionalitat s'identifiquen de forma coherent. |

### 3.3 Assistència en l'entrada

| Criteri | Nivell | Nom | Requisit tècnic |
|---------|--------|-----|-----------------|
| **3.3.1** | A | Identificació d'errors | Els errors d'entrada es detecten i es descriuen en text. |
| **3.3.2** | A | Etiquetes o instruccions | S'ofereixen etiquetes o instruccions per a l'entrada d'usuari. |
| **3.3.3** | AA | Suggeriment d'errors | Es proporcionan suggeriments de correcció quan es detecten errors. |
| **3.3.4** | AA | Prevenció d'errors (legal, financer, de dades) | Les trameses es poden revertir, verificar o confirmar. |

---

## PRINCIPI 4: ROBUST

### 4.1 Compatible

| Criteri | Nivell | Nom | Requisit tècnic |
|---------|--------|-----|-----------------|
| **4.1.1** | A | Anàlisi | HTML vàlid: IDs únics, etiquetes correctament obertes/tancades, anidament correcte. |
| **4.1.2** | A | Nom, rol, valor | Tots els components UI: nom i rol determinables programàticament; estats i propietats determinables i notificats. |
| **4.1.3** | AA | Missatges d'estat | Els missatges d'estat (que no reben focus) es determinen programàticament via rol o propietat (`role="status"`, `role="alert"`, `aria-live`). |

---

## WCAG 2.2 — Criteris nous destacats (referència futura)

| Criteri | Nivell | Nom | Requisit |
|---------|--------|-----|---------|
| **2.4.11** | AA | Focus no amagat (mínim) | El focus de teclat no queda completament amagat per contingut de l'autor. |
| **2.5.7** | AA | Moviments d'arrossegament | Les operacions d'arrossegament tenen alternativa de punter únic. |
| **2.5.8** | AA | Mida de l'objectiu (mínim) | Mida mínima d'objectiu: 24×24 píxels CSS. |
| **3.2.6** | A | Ajuda coherent | Els mecanismes d'ajuda apareixen en ubicació coherent. |
| **3.3.7** | A | Entrada redundant | La informació ja introduïda no es demana de nou en la mateixa sessió. |
| **3.3.8** | AA | Autenticació accessible (mínim) | L'autenticació no depèn exclusivament d'una prova de funció cognitiva (no CAPTCHAs que requereixin transcripció). |
