# Patrons d'ús — Sistema de Disseny Gencat

Patrons recomanats per als casos d'ús més habituals en aplicacions de la Generalitat de Catalunya.

---

## Formularis

### Estructura base d'un formulari

```html
<form>
  <!-- Títol del formulari -->
  <h1>Títol del formulari</h1>

  <!-- Camp d'entrada estàndard -->
  <div class="form-group">
    <label for="nom">Nom complet *</label>
    <input type="text" id="nom" name="nom" required
           aria-describedby="nom-error" />
    <span id="nom-error" class="error-message" role="alert"></span>
  </div>

  <!-- Selector -->
  <div class="form-group">
    <label for="provincia">Província *</label>
    <select id="provincia" name="provincia" required>
      <option value="">Selecciona una opció</option>
      <option value="bcn">Barcelona</option>
      <option value="gir">Girona</option>
      <option value="llei">Lleida</option>
      <option value="tar">Tarragona</option>
    </select>
  </div>

  <!-- Botons d'acció -->
  <div class="form-actions">
    <button type="submit" class="btn btn-primary">Enviar</button>
    <button type="button" class="btn btn-secondary">Cancel·lar</button>
  </div>
</form>
```

### Regles per a formularis
- Tots els camps requerits s'indiquen amb `*` i el text "Els camps marcats amb * són obligatoris"
- La validació es mostra sota el camp afectat
- Els missatges d'error han de ser descriptius: "El DNI ha de tenir 8 dígits i una lletra"
- Usa `required` natiu (no cal duplicar-lo amb `aria-required`); marca els camps amb error amb `aria-invalid="true"` i associa el missatge amb `aria-describedby`

---

## Pàgines de contingut

### Estructura típica de pàgina

```
[Capçalera web pública]
[Fils d'Ariadna]
[Títol H1]
[Cos del contingut]
  - Seccions H2
  - Subseccions H3
[Taula de continguts] (si la pàgina és llarga)
[Peu de pàgina]
```

---

## Cercador

### Estructura del cercador

```html
<section aria-label="Cercador">
  <!-- Camp de cerca -->
  <div class="search-input-group">
    <label for="cerca" class="visually-hidden">Cercar</label>
    <input type="search" id="cerca" placeholder="Escriu el que cerques..."
           aria-controls="resultats-cerca" />
    <button type="submit" aria-label="Cercar">
      <span aria-hidden="true">🔍</span>
    </button>
  </div>

  <!-- Filtres -->
  <div class="filtres" aria-label="Filtres de cerca">
    <!-- Filtres per categoria, data, etc. -->
  </div>

  <!-- Resultats -->
  <div id="resultats-cerca" role="region" aria-live="polite">
    <p>[N] resultats trobats</p>
    <!-- Llistat de resultats -->
    <!-- Paginació -->
  </div>
</section>
```

---

## Àrea privada (Dashboard)

### Estructura típica

```
[Capçalera per aplicacions internes]
  - Logo + nom aplicació
  - Navegació principal
  - Perfil d'usuari + logout

[Contenidor principal]
  [Menú lateral] | [Contingut principal]
                   [Breadcrumbs]
                   [Títol de la secció]
                   [Contingut]
```

### Botons d'acció en àrea privada
- **Acció principal** (crear, guardar): Botó primari (color brand `#C00000`)
- **Acció secundària** (editar, filtrar): Botó secundari (outline)
- **Acció destructiva** (eliminar): Botó de perill + confirmació amb Modal

---

## Gestió interna

### Taules de dades amb accions

```html
<table aria-label="Llistat de sol·licituds">
  <caption>Sol·licituds pendents de revisió</caption>
  <thead>
    <tr>
      <th scope="col">Referència</th>
      <th scope="col">Data</th>
      <th scope="col">Estat</th>
      <th scope="col">Accions</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>REF-2024-001</td>
      <td>15/01/2024</td>
      <td><span class="insígnia insígnia--pendent">Pendent</span></td>
      <td>
        <button class="btn btn-sm btn-secondary">Veure</button>
        <button class="btn btn-sm btn-primary">Aprovar</button>
      </td>
    </tr>
  </tbody>
</table>
```

---

## Pàgines d'error

### Error 404
```
Títol: "Pàgina no trobada"
Missatge: "La pàgina que cerques no existeix o ha estat moguda."
Accions: [Tornar a l'inici] [Contactar suport]
```

### Error 500
```
Títol: "Hi ha hagut un error"
Missatge: "S'ha produït un error intern. Torna-ho a intentar en uns moments."
Accions: [Tornar enrere] [Tornar a l'inici]
```

---

## Accessibilitat: mínims abans de lliurar

- [ ] Inputs amb `<label>` associat i imatges amb `alt` (o `alt=""` si són decoratives)
- [ ] Navegable completament amb teclat, amb `:focus` visible
- [ ] Errors anunciats amb `role="alert"` o `aria-live`
- [ ] Contrast ≥ 4.5:1 (text normal) / ≥ 3:1 (text gran i components UI)

La llista de verificació completa, els patrons ARIA i els errors freqüents són a la skill **gencat-accessibilitat** — usa-la per a qualsevol auditoria.

---

## Idioma i textos

### Regles de redacció
- Llengua principal: **català** (`lang="ca"`)
- Tractament: **vós** en textos administratius (criteri de la Guia de Comunicació Clara); "tu" només en aplicacions dirigides a joves o contextos informals
- Missatges d'error: clars, concrets, i orientats a la solució
  - ❌ "Error de validació"
  - ✅ "El número de DNI ha de tenir 8 dígits seguits d'una lletra majúscula"

Per a la redacció de literals, to i vocabulari, usa la skill **gencat-comunicacio-clara**.

### Textos habituals
| Context | Text recomanat |
|---------|---------------|
| Enviar formulari | "Enviar" / "Desar" |
| Cancel·lar | "Cancel·lar" |
| Confirmar acció | "Confirmar" |
| Eliminar | "Eliminar" |
| Editar | "Editar" |
| Tornar enrere | "Tornar" |
| Veure més | "Veure més" |
| Càrrega | "S'està carregant..." |
| Sense resultats | "No s'han trobat resultats" |
| Camp requerit | "Aquest camp és obligatori" |
