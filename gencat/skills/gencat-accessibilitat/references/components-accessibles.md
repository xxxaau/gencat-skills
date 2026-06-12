# Components Accessibles — Patrons HTML/ARIA per a Gencat

Patrons d'implementació per als components del Sistema de Disseny Gencat. Per a cada component,
la implementació accessible és la mínima requerida.

---

## Botons

```html
<!-- Botó estàndard -->
<button type="button">Enviar la sol·licitud</button>

<!-- Botó amb icona + text (sempre text visible o aria-label) -->
<button type="button">
  <svg aria-hidden="true" focusable="false">...</svg>
  Descarregar
</button>

<!-- Botó únicament icona -->
<button type="button" aria-label="Tancar el diàleg">
  <svg aria-hidden="true" focusable="false">...</svg>
</button>

<!-- Botó amb estat de càrrega (disabled natiu ja exposa l'estat; no hi afegeixis aria-disabled) -->
<button type="button" aria-busy="true" disabled>
  <span aria-hidden="true">Processant...</span>
  <span class="visually-hidden">S'està enviant la sol·licitud, espereu</span>
</button>
```

**Evita:**
- `<div onclick>` o `<span onclick>` en lloc de `<button>`
- Botons sense text accessible
- `disabled` sense indicació visual clara

---

## Formularis complets

```html
<form novalidate>
  <fieldset>
    <legend>Dades personals</legend>

    <!-- Camp de text -->
    <div class="form-group">
      <label for="nom">
        Nom <span aria-hidden="true">*</span>
        <span class="visually-hidden">(obligatori)</span>
      </label>
      <input type="text" id="nom" name="nom"
             required
             autocomplete="given-name"
             aria-describedby="nom-error nom-help">
      <span id="nom-help" class="help-text">
        Tal com apareix al DNI
      </span>
      <span id="nom-error" role="alert" class="error" hidden></span>
    </div>

    <!-- Selector -->
    <div class="form-group">
      <label for="provincia">Província *</label>
      <select id="provincia" name="provincia"
              required>
        <option value="">Seleccioneu una província</option>
        <option value="bcn">Barcelona</option>
        <option value="gir">Girona</option>
        <option value="llei">Lleida</option>
        <option value="tar">Tarragona</option>
      </select>
    </div>

    <!-- Ràdio -->
    <fieldset>
      <legend>Via de contacte preferida *</legend>
      <div>
        <input type="radio" id="contact-email" name="contact" value="email">
        <label for="contact-email">Correu electrònic</label>
      </div>
      <div>
        <input type="radio" id="contact-tel" name="contact" value="tel">
        <label for="contact-tel">Telèfon</label>
      </div>
    </fieldset>

    <!-- Checkbox -->
    <div class="form-group">
      <input type="checkbox" id="accepta" name="accepta" required>
      <label for="accepta">
        He llegit i accepto la
        <a href="/politica-privacitat">política de privacitat</a>
      </label>
    </div>

  </fieldset>

  <!-- Indicació camps obligatoris -->
  <p>Els camps marcats amb * són obligatoris</p>

  <button type="submit">Enviar la sol·licitud</button>
</form>
```

---

## Navegació i menús

```html
<!-- Navegació principal -->
<nav aria-label="Navegació principal">
  <ul>
    <li><a href="/" aria-current="page">Inici</a></li>
    <li><a href="/tràmits">Tràmits</a></li>
    <li><a href="/contacte">Contacte</a></li>
  </ul>
</nav>

<!-- Breadcrumbs (Fils d'Ariadna) -->
<nav aria-label="Fil d'Ariadna">
  <ol>
    <li><a href="/">Inici</a></li>
    <li><a href="/tràmits">Tràmits</a></li>
    <li aria-current="page">Sol·licitud de certificat</li>
  </ol>
</nav>

<!-- Menú desplegable accessible -->
<nav aria-label="Menú principal">
  <ul>
    <li>
      <button aria-expanded="false" aria-controls="submenu-tràmits">
        Tràmits
        <svg aria-hidden="true"><!-- chevron --></svg>
      </button>
      <ul id="submenu-tràmits" hidden>
        <li><a href="/tràmits/certificats">Certificats</a></li>
        <li><a href="/tràmits/llicències">Llicències</a></li>
      </ul>
    </li>
  </ul>
</nav>
```

---

## Pestanyes (Tabs)

```html
<div>
  <!-- Llista de pestanyes -->
  <ul role="tablist" aria-label="Seccions del tràmit">
    <li role="presentation">
      <button role="tab"
              id="tab-info"
              aria-controls="panel-info"
              aria-selected="true"
              tabindex="0">
        Informació
      </button>
    </li>
    <li role="presentation">
      <button role="tab"
              id="tab-docs"
              aria-controls="panel-docs"
              aria-selected="false"
              tabindex="-1">
        Documentació
      </button>
    </li>
  </ul>

  <!-- Panells de contingut -->
  <div role="tabpanel"
       id="panel-info"
       aria-labelledby="tab-info">
    <p>Contingut de la pestanya Informació</p>
  </div>

  <div role="tabpanel"
       id="panel-docs"
       aria-labelledby="tab-docs"
       hidden>
    <p>Contingut de la pestanya Documentació</p>
  </div>
</div>
```

**Gestió de teclat obligatòria** — sense aquest JavaScript el component NO és accessible (criteri 2.1.1):

```javascript
const tabs = [...document.querySelectorAll('[role="tab"]')];

tabs.forEach(tab => {
  tab.addEventListener('keydown', e => {
    let nou = null;
    if (e.key === 'ArrowRight') nou = tabs[(tabs.indexOf(tab) + 1) % tabs.length];
    if (e.key === 'ArrowLeft')  nou = tabs[(tabs.indexOf(tab) - 1 + tabs.length) % tabs.length];
    if (e.key === 'Home') nou = tabs[0];
    if (e.key === 'End')  nou = tabs[tabs.length - 1];
    if (nou) { e.preventDefault(); activarTab(nou); }
  });
  tab.addEventListener('click', () => activarTab(tab));
});

function activarTab(tab) {
  tabs.forEach(t => {
    const seleccionada = t === tab;
    t.setAttribute('aria-selected', String(seleccionada));
    t.tabIndex = seleccionada ? 0 : -1;
    document.getElementById(t.getAttribute('aria-controls')).hidden = !seleccionada;
  });
  tab.focus();
}
```

Comportament: fletxes ←→ mouen el focus entre pestanyes (amb cicle), Home/End van a la primera/última, Tab surt cap al panell. Només la pestanya activa té `tabindex="0"`.

---

## Acordió (Accordion)

```html
<div class="acordio">
  <h3>
    <button aria-expanded="false"
            aria-controls="acordio-1-cos"
            id="acordio-1-cap">
      Quins documents necessito?
      <svg aria-hidden="true"><!-- chevron --></svg>
    </button>
  </h3>
  <div id="acordio-1-cos"
       role="region"
       aria-labelledby="acordio-1-cap"
       hidden>
    <p>Necessiteu el DNI, el certificat d'empadronament i...</p>
  </div>
</div>
```

---

## Modals

```html
<!-- Trigger -->
<button type="button" id="btn-obrir-modal"
        aria-controls="modal-confirmar"
        aria-haspopup="dialog">
  Eliminar l'expedient
</button>

<!-- Modal -->
<div role="dialog"
     id="modal-confirmar"
     aria-modal="true"
     aria-labelledby="modal-titol"
     aria-describedby="modal-desc"
     hidden>

  <h2 id="modal-titol">Confirmar eliminació</h2>
  <p id="modal-desc">
    Esteu a punt d'eliminar l'expedient REF-2024-001.
    Aquesta acció no es pot desfer.
  </p>

  <div class="modal-accions">
    <button type="button" class="btn-perill">Eliminar</button>
    <button type="button" id="btn-tancar-modal">Cancel·lar</button>
  </div>
</div>
```

---

## Modal de temps de sessió (timeout)

Criteri 2.2.1 (Temps ajustable): si la sessió caduca, cal avisar l'usuari i permetre estendre-la.

```html
<div role="alertdialog"
     aria-modal="true"
     aria-labelledby="timeout-titol"
     aria-describedby="timeout-desc">
  <h2 id="timeout-titol">La sessió està a punt de caducar</h2>
  <p id="timeout-desc">
    La vostra sessió caducarà en 5 minuts per inactivitat.
    Si caduca, es perdran les dades que no hàgiu desat.
  </p>
  <button type="button">Continuar la sessió</button>
  <button type="button">Tancar la sessió</button>
</div>
```

Requisits:
- Mostra l'avís amb prou antelació (mínim 2 minuts abans) i mou-hi el focus en obrir-se
- "Continuar la sessió" estén el temps sense perdre les dades introduïdes
- Gestió de focus i Escape com a qualsevol modal (vegeu `errors-habituals.md`, Error 12)

---

## Avisos (Alerts)

```html
<!-- Avís informatiu (no urgent) -->
<div role="status" aria-live="polite" class="avis avis--info">
  <svg aria-hidden="true"><!-- icona info --></svg>
  <p>El termini de presentació acaba el 31 de març de 2024.</p>
</div>

<!-- Avís d'error (urgent) -->
<div role="alert" aria-live="assertive" class="avis avis--error">
  <svg aria-hidden="true"><!-- icona error --></svg>
  <p>
    <strong>S'ha produït un error.</strong>
    No s'ha pogut enviar la sol·licitud. Torneu-ho a intentar.
  </p>
</div>

<!-- Avís d'èxit -->
<div role="status" aria-live="polite" class="avis avis--exit">
  <svg aria-hidden="true"><!-- icona check --></svg>
  <p>La sol·licitud s'ha enviat correctament. Referència: REF-2024-001.</p>
</div>
```

---

## Indicador de càrrega (Loading)

```html
<!-- Inline loading -->
<button type="submit" aria-busy="true" disabled>
  <svg aria-hidden="true" class="spinner">...</svg>
  <span>Enviant...</span>
</button>

<!-- Loading de pàgina completa -->
<div role="status" aria-live="polite" aria-label="Carregant contingut">
  <svg aria-hidden="true" class="spinner">...</svg>
  <span class="visually-hidden">S'està carregant, espereu</span>
</div>

<!-- Skeleton loader: marcar com aria-hidden mentre carrega -->
<div aria-hidden="true" class="skeleton">
  <div class="skeleton-line"></div>
  <div class="skeleton-line"></div>
</div>
```

---

## Taules dinàmiques

```html
<div role="region" aria-label="Resultats de la cerca" aria-live="polite">
  <table>
    <caption>
      Sol·licituds registrades
      <span class="caption-detall">
        (Mostrant 1–10 de 47 resultats)
      </span>
    </caption>
    <thead>
      <tr>
        <!-- aria-sort va al <th>, no al botó; el botó no necessita aria-label
             (duplicaria el text visible) -->
        <th scope="col" aria-sort="ascending">
          <button>
            Referència
            <span class="visually-hidden">(ordenat ascendentment; activeu per canviar l'ordre)</span>
          </button>
        </th>
        <th scope="col">Data</th>
        <th scope="col">Estat</th>
        <th scope="col">
          <span class="visually-hidden">Accions</span>
        </th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>REF-2024-001</td>
        <td><time datetime="2024-01-15">15/01/2024</time></td>
        <td>
          <span class="insígnia insígnia--pendent"
                aria-label="Estat: Pendent de documentació">
            Pendent
          </span>
        </td>
        <td>
          <a href="/expedient/1">
            Veure detalls
            <span class="visually-hidden">de REF-2024-001</span>
          </a>
        </td>
      </tr>
    </tbody>
  </table>
</div>
```

---

## Paginació

```html
<nav aria-label="Paginació de resultats">
  <ul>
    <li>
      <a href="?pag=1" aria-label="Pàgina anterior">
        <svg aria-hidden="true"><!-- fletxa esquerra --></svg>
        <span class="visually-hidden">Anterior</span>
      </a>
    </li>
    <li>
      <a href="?pag=1" aria-label="Pàgina 1">1</a>
    </li>
    <li>
      <a href="?pag=2" aria-label="Pàgina 2, pàgina actual"
         aria-current="page">2</a>
    </li>
    <li>
      <a href="?pag=3" aria-label="Pàgina 3">3</a>
    </li>
    <li>
      <a href="?pag=3" aria-label="Pàgina següent">
        <svg aria-hidden="true"><!-- fletxa dreta --></svg>
        <span class="visually-hidden">Següent</span>
      </a>
    </li>
  </ul>
</nav>
```

---

## Pas a pas (Stepper)

```html
<nav aria-label="Passos del tràmit">
  <ol>
    <li aria-current="step" class="pas pas--actiu">
      <span class="pas-num" aria-hidden="true">1</span>
      <span class="pas-nom">Dades personals</span>
    </li>
    <li class="pas">
      <span class="pas-num" aria-hidden="true">2</span>
      <span class="pas-nom">Documentació</span>
    </li>
    <li class="pas pas--pendent">
      <span class="pas-num" aria-hidden="true">3</span>
      <span class="pas-nom">Revisió i enviament</span>
    </li>
  </ol>
</nav>
<p class="visually-hidden">
  Pas 1 de 3: Dades personals
</p>
```

---

## Insígnies d'estat (Badges)

```html
<!-- Insígnia amb text accessible -->
<span class="insígnia insígnia--aprovat">
  Aprovat
</span>

<!-- Insígnia amb codi de color + text (mai únicament color) -->
<span class="insígnia insígnia--pendent"
      aria-label="Estat: Pendent de resolució">
  <span class="insígnia-dot" aria-hidden="true"></span>
  Pendent
</span>

<!-- Comptador de notificacions -->
<button type="button" aria-label="Notificacions (3 de noves)">
  <svg aria-hidden="true"><!-- campana --></svg>
  <span class="badge" aria-hidden="true">3</span>
</button>
```

---

## Capçalera web pública

```html
<header role="banner">
  <!-- Skip link (primer element) -->
  <a href="#contingut-principal" class="skip-link">
    Ves al contingut principal
  </a>

  <!-- Logotip -->
  <a href="/" aria-label="Generalitat de Catalunya - Inici">
    <img src="logo-gencat.svg" alt="Generalitat de Catalunya">
  </a>

  <!-- Navegació principal -->
  <nav aria-label="Navegació principal">
    <!-- ... -->
  </nav>

  <!-- Cerca -->
  <form role="search" aria-label="Cerca al lloc web">
    <label for="cerca" class="visually-hidden">Cercar</label>
    <input type="search" id="cerca" name="q"
           placeholder="Cerqueu...">
    <button type="submit" aria-label="Cercar">
      <svg aria-hidden="true"><!-- lupa --></svg>
    </button>
  </form>
</header>

<main id="contingut-principal" tabindex="-1">
  <!-- Contingut principal -->
</main>

<footer role="contentinfo">
  <!-- Peu de pàgina -->
</footer>
```
