---
name: gencat-accessibilitat
description: "Aplica les directrius d'accessibilitat digital de la Generalitat de Catalunya quan desenvolupes, revises o audites aplicacions web i mòbils per a serveis públics catalans. Usa aquesta skill sempre que implementis components, formularis, navegació, contingut multimèdia, documents PDF, o qualsevol interfície destinada a serveis Gencat. Activa-la quan l'usuari mencioni WCAG, accessibilitat, EN 301 549, IRA, a11y, daltonisme, lector de pantalla, contrast, focus, ARIA, o demani complir amb el Decret 216/2023. S'ha d'usar tant en fase de disseny com d'implementació i revisió."
---

# Accessibilitat Digital — Generalitat de Catalunya

## Abast de la skill

### Què cobreix
- Compliment de WCAG 2.1 AA, EN 301 549 i marc normatiu aplicable
- Revisió tècnica de components, formularis, navegació, multimèdia i documents
- Guia d'implementació HTML/ARIA i metodologia d'avaluació

### Què NO cobreix
- Definició visual de marca o identitat corporativa (delegar a `gencat-identitat-corporativa`)
- Disseny de catàleg de components i sistematització visual completa (delegar a `gencat-design-system`)
- Redacció d'estil administratiu o de campanyes més enllà de la comprensió accessible (delegar a `gencat-comunicacio-clara`)

### Skills complementàries
- `gencat-design-system` per aplicar patrons visuals i de component oficials
- `gencat-comunicacio-clara` per missatges i contingut textual entenedor
- `gencat-tramits` quan es revisen fitxes de tràmit publicades a gencat.cat

---

## Marc legal obligatori

| Norma | Àmbit | Requeriment |
|-------|-------|-------------|
| **Decret 216/2023** (DOGC 9057) | Catalunya | Accessibilitat de webs i apps de la Generalitat |
| **Reial Decret 1112/2018** | Espanya | Transposició de la Directiva UE 2016/2102 |
| **EN 301 549 V3.2.1** | Estàndard tècnic | 137 criteris d'avaluació (en vigor des de 12/02/2022) |
| **WCAG 2.1 Nivell AA** | Referència tècnica | 50 criteris obligatoris (30×A + 20×AA) |
| **WCAG 2.2** | Referència futura | Traducció oficial al català disponible (22/05/2024) |

**Nivell mínim obligatori: WCAG 2.1 AA** — tots els criteris A i AA.

---

## Els 4 principis WCAG (POUR)

1. **Perceptible** — La informació és presentable a tots els usuaris
2. **Operable** — La interfície és navegable i usable
3. **Comprensible** — El contingut i el funcionament és entenedor
4. **Robust** — El contingut pot ser interpretat per tecnologies d'assistència

---

## Guies de referència detallades

- `references/wcag-criteris.md` — Els 50 criteris A+AA obligatoris amb implementació
- `references/errors-habituals.md` — Errors més freqüents en webs Gencat i com corregir-los
- `references/components-accessibles.md` — Patrons HTML/ARIA per a components concrets
- `references/eines-i-avaluacio.md` — Eines de verificació i metodologia IRA/WCAG-EM

---

## Regles d'aplicació immediata

### HTML base
```html
<!-- Idioma obligatori -->
<html lang="ca">

<!-- Skip link (primer element del body) -->
<a href="#contingut-principal" class="skip-link">Ves al contingut principal</a>

<!-- Punt d'ancoratge -->
<main id="contingut-principal">
```

### Contrast mínim
- Text normal: **4.5:1**
- Text gran (≥18pt o ≥14pt negreta): **3:1**
- Components UI i elements gràfics: **3:1**

### Imatges
```html
<!-- Informativa: alt descriptiu (màx. 125 caràcters) -->
<img src="mapa.jpg" alt="Mapa de les oficines d'atenció ciutadana de Barcelona">

<!-- Decorativa: alt buit -->
<img src="separador.png" alt="">

<!-- Funcional (botó/enllaç): descriu l'acció -->
<button><img src="cerca.svg" alt="Cercar"></button>
```

### Formularis
```html
<!-- Label sempre associat -->
<label for="dni">DNI o NIE *</label>
<input type="text" id="dni" name="dni"
       required aria-required="true"
       autocomplete="on"
       aria-describedby="dni-error">
<span id="dni-error" role="alert" class="error"></span>
```

### Focus visible — mai eliminar
```css
/* MAI fer això */
:focus { outline: none; }

/* SÍ: focus visible personalitzat */
:focus-visible {
  outline: 3px solid #C00000;
  outline-offset: 2px;
}
```

### Missatges d'estat dinàmics
```html
<!-- Notificació no disruptiva -->
<div role="status" aria-live="polite">Dades desades correctament</div>

<!-- Error urgent -->
<div role="alert" aria-live="assertive">Error en enviar el formulari</div>
```

---

## Llista de verificació ràpida (pre-lliurament)

### Estructura
- [ ] `<html lang="ca">` present
- [ ] Un sol `<h1>` per pàgina, jerarquia H1→H2→H3 sense salts
- [ ] `<title>` descriptiu i únic
- [ ] Skip link al inici del `<body>`
- [ ] Landmarks semàntics: `<header>`, `<nav>`, `<main>`, `<footer>`

### Contingut
- [ ] Totes les imatges informatives tenen `alt` descriptiu
- [ ] Imatges decoratives amb `alt=""`
- [ ] Vídeos amb subtítols
- [ ] Documents PDF etiquetats i accessibles

### Interacció
- [ ] Tota la funcionalitat operable per teclat (Tab, Enter, Escape, fletxes)
- [ ] Focus visible en tots els elements interactius
- [ ] No hi ha trampes de teclat
- [ ] Tots els inputs tenen `<label>` associat

### Contingut dinàmic
- [ ] Modals gestionen focus (focus trap) i tanquen amb Escape
- [ ] Errors de formulari anunciats amb `role="alert"`
- [ ] Contingut actualitzat dinàmicament usa `aria-live`

### Visual
- [ ] Contrast text normal ≥ 4.5:1
- [ ] Contrast text gran ≥ 3:1
- [ ] Contrast components UI ≥ 3:1
- [ ] La informació no es transmet únicament per color
- [ ] Contingut llegible al 200% de zoom sense scroll horitzontal

### Codi
- [ ] HTML vàlid (W3C validator)
- [ ] IDs únics
- [ ] Atributs ARIA correctament usats (role, aria-label, aria-describedby)
