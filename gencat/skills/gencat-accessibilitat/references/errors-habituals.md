# Errors Habituals d'Accessibilitat — Webs Gencat

Els errors més freqüents detectats en auditories IRA de webs de la Generalitat de Catalunya, amb criteris WCAG associats i correccions.

---

## Error 1: Alt text incorrecte o absent (1.1.1 — Nivell A)

El més freqüent. Cinc categories d'imatges, cinc regles:

| Tipus d'imatge | Regla d'alt text | Exemple |
|---------------|-----------------|---------|
| Informativa simple | Descriu el contingut (màx. 125 car.). Sense "Imatge de" ni "Foto de" | `alt="Oficina d'atenció ciutadana de Girona"` |
| Decorativa | Buit obligatòriament | `alt=""` |
| Conté text | Replica el text visible | `alt="Termini: 31 de març de 2024"` |
| Funcional (botó/link) | Descriu l'acció o destí | `alt="Cercar"` / `alt="Anar a la pàgina d'inici"` |
| Complexa (gràfic, mapa) | Alt curt + descripció llarga via `aria-describedby` | Vegeu exemple avall |

```html
<!-- Complexa: gràfic de dades -->
<figure>
  <img src="grafic-visits.svg"
       alt="Evolució de visites web 2020-2024"
       aria-describedby="grafic-desc">
  <figcaption id="grafic-desc">
    Les visites van créixer de 2M el 2020 fins a 5,3M el 2024,
    amb un pic de 6,1M el 2022. [...]
  </figcaption>
</figure>
```

---

## Error 2: Jerarquia d'encapçalaments trencada (1.3.1 — Nivell A)

```html
<!-- ❌ Incorrecte: salta de H1 a H3 -->
<h1>Tràmits en línia</h1>
<h3>Sol·licitud de certificat</h3>

<!-- ✅ Correcte: seqüència contínua -->
<h1>Tràmits en línia</h1>
  <h2>Sol·licituds de certificats</h2>
    <h3>Certificat d'empadronament</h3>
  <h2>Consultes i informació</h2>
```

Regles:
- Un sol `<h1>` per pàgina, al contingut principal
- No usar encapçalaments per a estètica (usa CSS)
- No usar negreta o text gran com a substitut d'encapçalaments
- Verificar amb l'extensió HeadingsMap

---

## Error 3: Taules inaccessibles (1.3.1 — Nivell A)

```html
<!-- ❌ Incorrecte: sense capçaleres ni títol -->
<table>
  <tr><td>Servei</td><td>Horari</td><td>Telèfon</td></tr>
  <tr><td>Atenció ciutadana</td><td>8h-20h</td><td>012</td></tr>
</table>

<!-- ✅ Correcte: capçaleres, scope, caption, describedby -->
<p id="taula-desc">Horaris i telèfons dels serveis d'atenció ciutadana de la Generalitat.</p>
<table aria-describedby="taula-desc">
  <caption>Serveis d'atenció ciutadana</caption>
  <thead>
    <tr>
      <th scope="col">Servei</th>
      <th scope="col">Horari</th>
      <th scope="col">Telèfon</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">Atenció ciutadana</th>
      <td>De dilluns a divendres, 8h–20h</td>
      <td>012</td>
    </tr>
  </tbody>
</table>
```

Per a taules complexes (capçaleres múltiples), usa `id` + `headers`:
```html
<th id="col-horari" scope="col">Horari</th>
<td headers="col-horari">8h–20h</td>
```

---

## Error 4: Contrast insuficient (1.4.3 / 1.4.11 — Nivell AA)

**Ratios mínims:**
- Text normal (<18pt i <14pt negreta): **4.5:1**
- Text gran (≥18pt o ≥14pt negreta): **3:1**
- Components UI i gràfics: **3:1** contra colors adjacents

```css
/* ❌ Exemples que fallen */
color: #999999 sobre #FFFFFF  /* 2.85:1 — FALLA */

/* ⚠️ Al límit */
color: #767676 sobre #FFFFFF  /* 4.54:1 — passa AA pels pèls; no hi ha marge d'error */

/* ✅ Exemples que superen */
color: #595959 sobre #FFFFFF  /* 7.0:1 — Supera AA i AAA */
color: #C00000 sobre #FFFFFF  /* 6.5:1 — Supera AA */
color: #FFFFFF sobre #C00000  /* 6.5:1 — Supera AA */
color: #333333 sobre #FFFFFF  /* 12.6:1 — Excel·lent */
```

**Eines de verificació:**
- WebAIM Contrast Checker: https://webaim.org/resources/contrastchecker/
- Colour Contrast Analyser (TPG): aplicació d'escriptori

**Combinacions a evitar:** vermell-verd, blau-groc (problemes per a persones daltòniques).

---

## Error 5: Formularis sense etiquetes (4.1.2 / 3.3.2 — Nivell A)

```html
<!-- ❌ Incorrecte: sense label, placeholder no substitueix -->
<input type="text" placeholder="Nom">

<!-- ❌ Incorrecte: label no associat -->
<label>Nom</label>
<input type="text">

<!-- ✅ Correcte: label associat per id/for -->
<label for="nom">Nom *</label>
<input type="text" id="nom" name="nom" required>

<!-- ✅ Alternatiu: aria-label quan no hi ha label visual -->
<input type="search" aria-label="Cercar al lloc web"
       placeholder="Cerqueu...">

<!-- ✅ Alternatiu: aria-labelledby -->
<p id="nom-label">Nom complet</p>
<input type="text" aria-labelledby="nom-label">
```

Errors de validació (3.3.1 + 3.3.3):
```html
<label for="email">Adreça electrònica *</label>
<input type="email" id="email"
       aria-describedby="email-error"
       aria-invalid="true">
<span id="email-error" role="alert">
  Introduïu una adreça electrònica vàlida (exemple: nom@domini.cat)
</span>
```

---

## Error 6: Enllaços no descriptius (2.4.4 — Nivell A)

```html
<!-- ❌ Incorrecte: no descriptiu fora de context -->
<a href="doc.pdf">Cliqueu aquí</a>
<a href="noticies.html">Llegiu més</a>
<a href="serveis.html">Aquí</a>

<!-- ✅ Correcte: descriptiu en si mateix -->
<a href="doc.pdf">Descarregueu la guia d'accessibilitat (PDF, 2,3 MB)</a>
<a href="noticies.html">Llegiu més sobre l'actualitat de Governació</a>

<!-- ✅ Alternativa: text ocult per a lectors de pantalla -->
<a href="noticies.html">
  Llegiu més
  <span class="visually-hidden"> sobre accessibilitat digital</span>
</a>
```

```css
.visually-hidden {
  position: absolute;
  width: 1px; height: 1px;
  padding: 0; margin: -1px;
  overflow: hidden;
  clip: rect(0,0,0,0);
  white-space: nowrap;
  border: 0;
}
```

---

## Error 7: Focus de teclat no visible o eliminat (2.4.7 — Nivell AA)

```css
/* ❌ MAI fer això */
*:focus { outline: none; }
button:focus { outline: 0; }
a:focus { outline: none; }

/* ✅ Focus visible personalitzat amb colors corporatius */
:focus-visible {
  outline: 3px solid #C00000;
  outline-offset: 2px;
  border-radius: 2px;
}

/* ✅ Per a elements sobre fons vermell */
.btn-primary:focus-visible {
  outline: 3px solid #FFFFFF;
  outline-offset: 2px;
}
```

---

## Error 8: Elements `<b>` i `<u>` semànticament incorrectes (1.3.1 — Nivell A)

```html
<!-- ❌ Incorrecte: b sense semàntica -->
<p>Termini: <b>31 de març</b></p>

<!-- ✅ Correcte: strong per a importància semàntica -->
<p>Termini: <strong>31 de març</strong></p>

<!-- ✅ Si és únicament estètic, usa CSS -->
<p>Termini: <span class="destacat">31 de març</span></p>
<style>.destacat { font-weight: bold; }</style>

<!-- ❌ u genera confusió amb hipervincles en web -->
<p>Veure <u>condicions d'ús</u></p>

<!-- ✅ Usa CSS per a subratllat decoratiu -->
<p>Veure <span class="annotacio">condicions d'ús</span></p>
```

---

## Error 9: Iframes sense títol (4.1.2 — Nivell A)

```html
<!-- ❌ Incorrecte -->
<iframe src="mapa.html"></iframe>

<!-- ✅ Correcte -->
<iframe
  src="mapa.html"
  title="Mapa de les oficines d'atenció ciutadana">
</iframe>
```

---

## Error 10: Idioma de pàgina no declarat (3.1.1 — Nivell A)

```html
<!-- ❌ Incorrecte: sense lang -->
<html>

<!-- ✅ Correcte: català -->
<html lang="ca">

<!-- Canvis d'idioma dins la pàgina (3.1.2 — Nivell AA) -->
<p>El terme anglès <span lang="en">plain language</span> es refereix...</p>
<blockquote lang="es">
  <p>La accesibilidad web significa que los sitios web...</p>
</blockquote>
```

---

## Error 11: Contingut dinàmic sense `aria-live` (4.1.3 — Nivell AA)

```html
<!-- Notificació no urgent: polite (espera a que l'usuari acabi) -->
<div role="status" aria-live="polite" aria-atomic="true">
  <!-- Contingut injectat dinàmicament aquí -->
</div>

<!-- Error urgent: assertive (interromp immediatament) -->
<div role="alert" aria-live="assertive" aria-atomic="true">
  <!-- Missatge d'error crític -->
</div>

<!-- Comptador en temps real -->
<div aria-live="polite" aria-atomic="false">
  S'han carregat <span id="comptador">0</span> resultats
</div>
```

---

## Error 12: Modal sense gestió de focus (2.1.1 / 2.1.2 — Nivell A)

```javascript
// Al obrir el modal
function obrirModal(modal) {
  modal.removeAttribute('hidden');
  modal.setAttribute('aria-modal', 'true');

  // Desa l'element que tenia el focus
  modal.dataset.focusReturn = document.activeElement.id;

  // Mou el focus al primer element enfocable dins el modal
  const primerFocus = modal.querySelector('button, [href], input, select, textarea, [tabindex]:not([tabindex="-1"])');
  primerFocus?.focus();

  // Tanca amb Escape
  modal.addEventListener('keydown', e => {
    if (e.key === 'Escape') tancarModal(modal);
  });
}

// Al tancar el modal
function tancarModal(modal) {
  modal.setAttribute('hidden', '');
  // Retorna el focus a l'element que el tenia
  document.getElementById(modal.dataset.focusReturn)?.focus();
}
```

```html
<div role="dialog"
     aria-modal="true"
     aria-labelledby="modal-titol"
     aria-describedby="modal-desc">
  <h2 id="modal-titol">Confirmeu l'eliminació</h2>
  <p id="modal-desc">Aquesta acció no es pot desfer.</p>
  <button>Eliminar</button>
  <button>Cancel·lar</button>
</div>
```

---

## Error 13: CAPTCHA sense alternativa accessible (1.1.1 — Nivell A)

Un CAPTCHA només visual exclou les persones amb discapacitat visual; un de només auditiu, les persones amb discapacitat auditiva.

Regles:
- Prioritza mecanismes **sense repte per a l'usuari**: validació al servidor, camps honeypot, límits de freqüència
- Si cal un repte, ofereix **dues modalitats com a mínim** (visual + àudio), operables per teclat i amb lector de pantalla
- Instruccions clares en català i un canal alternatiu de contacte si l'usuari no el pot superar
- Si uses un servei de tercers (p. ex. reCAPTCHA), comprova-ho igualment: la responsabilitat del compliment és del servei Gencat

---

## Antipatrons ARIA freqüents

Primera regla d'ARIA: **no usis ARIA si l'HTML natiu ja ho fa**.

| ❌ Antipatró | ✅ Correcte | Per què |
|-------------|------------|---------|
| `<button disabled aria-disabled="true">` | `<button disabled>` | `disabled` natiu ja exposa l'estat |
| `<input required aria-required="true">` | `<input required>` | `required` natiu ja exposa l'estat |
| `aria-label` que repeteix o canvia el text visible | Sense `aria-label` | `aria-label` SUBSTITUEIX el text visible, no l'amplia; si difereixen, els usuaris de control per veu no poden activar l'element |
| `<button role="button">` | `<button>` | Rol redundant |
| `tabindex` més gran que 0 | `tabindex="0"` o ordre natural del DOM | Trenca l'ordre de tabulació |
| `aria-hidden="true"` en un element enfocable | Treure'l també del focus (`tabindex="-1"`, `disabled`) | El focus aterra en un element invisible per al lector de pantalla |
| `aria-sort` al botó d'ordenació | `aria-sort` al `<th>` | L'atribut només és vàlid en capçaleres de columna/fila |
