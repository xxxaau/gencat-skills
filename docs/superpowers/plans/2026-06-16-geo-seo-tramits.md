# Capa GEO/SEO a `gencat-tramits` — Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Afegir una avaluació GEO/SEO a la skill `gencat-tramits` en dues vessants — principis de redacció i una Capa 5 d'auditoria on-page amb nota independent i spot-check de risc — sense duplicar criteris d'altres skills.

**Architecture:** Un únic reference nou (`references/geo-seo.md`) amb dues seccions (redacció / on-page). El `SKILL.md` hi remet des de la verificació ràpida i des de REVISAR WEB. El `references/revisio-web.md` integra la Capa 5 al workflow, al format d'informe i al consolidat. El `README.md` actualitza les capacitats.

**Tech Stack:** Markdown. Sense framework de tests; la verificació és lectura i `grep` del contingut, més una comprovació manual de coherència.

**Spec de referència:** `docs/superpowers/specs/2026-06-16-geo-seo-tramits-design.md`

**Nota sobre commits:** El projecte treballa sobre `master` local (el push directe està bloquejat pel harness; es fa manualment). Cada tasca acaba amb un commit local a `master`.

---

### Task 1: Crear `references/geo-seo.md`

**Files:**
- Create: `gencat/skills/gencat-tramits/references/geo-seo.md`

- [ ] **Step 1: Escriure el fitxer amb el contingut complet**

Crear `gencat/skills/gencat-tramits/references/geo-seo.md` amb exactament aquest contingut:

````markdown
# GEO/SEO de fitxes de tràmit

GEO (Generative Engine Optimization) és l'optimització perquè una fitxa sigui **recuperada, citada i correctament resumida** pels motors d'IA (ChatGPT, Gemini, Copilot, Perplexity). SEO i GEO són sistemes paral·lels: la posició a Google no prediu la visibilitat en IA.

Aquest reference té dues seccions independents:
- **Secció A — Redacció:** principis aplicables quan s'escriu el text d'una fitxa nova.
- **Secció B — On-page (REVISAR WEB):** auditoria GEO/SEO d'una fitxa publicada, amb nota pròpia i spot-check de risc.

> **No es dupliquen** criteris de `gencat-comunicacio-clara` (frases, veu activa, vocabulari) ni de `gencat-accessibilitat` (jerarquia de títols, textos d'enllaços, instruccions sensorials). S'hi remet quan és rellevant.

---

## Secció A — GEO/SEO en redacció

Principis controlables per qui redacta el text (Schema.org, `canonical` i `meta description` són de plantilla/CMS, no de l'editor → no hi entren):

1. **Títol directe i autocontingut** — el títol ha de dir de què va el tràmit sense context previ. Reforça les normes de títol existents amb l'angle "recuperable per IA".
2. **Respostes extractables** — cada camp resol una pregunta del ciutadà de forma autocontinguda, apta per ser citada per un model sense dependre d'altres camps.
3. **Dades datades i explícites** — imports, terminis i convocatòria amb data concreta; mai "properament" ni "consulteu la convocatòria".
4. **Contingut crític en text** — requisits, terminis, imports i passos en text, no només dins d'un PDF o una imatge.
5. **Encapçalaments en forma de pregunta** quan ajudi ("Qui ho pot demanar?", "Quan puc demanar-ho?") — afinitat amb estructures FAQ que els models recuperen bé.

### Verificació ràpida — GEO/SEO en redacció

- [ ] Títol directe i comprensible sense context?
- [ ] Cada camp és autocontingut i citable per separat?
- [ ] Imports, terminis i convocatòria amb data concreta?
- [ ] Cap dada crítica només en PDF o imatge?
- [ ] Encapçalaments en forma de pregunta on tingui sentit?

---

## Secció B — GEO/SEO on-page (REVISAR WEB)

### Criteris puntuables (nota GEO/SEO /10)

5 criteris, cadascun val **1 punt** si passa sense ❌. Nota = (criteris sense ❌) / 5 × 10.

| # | Criteri | ❌ Error | ⚠️ Millora | Serveix |
|---|---------|---------|-----------|---------|
| 1 | **Dades estructurades** | Sense cap JSON-LD Schema.org rellevant a la pàgina | Schema.org present però incomplet (manca `HowTo`, `FAQPage` o `BreadcrumbList`) | GEO+SEO |
| 2 | **Títol i metadades** | `<title>` absent o genèric · sense `meta description` · `canonical` absent o incorrecte | `<title>` >60 caràcters · `meta description` fora del rang 120-160 caràcters | SEO+GEO |
| 3 | **Atribució oficial** | Òrgan responsable no identificable a la pàgina | Atribució present però poc visible | GEO |
| 4 | **Extractabilitat** | Informació crítica (requisits, terminis, imports, passos) només en PDF/imatge o no autocontinguda | Camps dispersos que dificulten l'extracció per fragments | GEO |
| 5 | **Actualitat datada** | Sense data d'actualització o de convocatòria · imports o terminis sense data | Data present però poc visible | GEO |

> **Com inspeccionar Schema.org:** buscar al HTML blocs `<script type="application/ld+json">`. Els tipus rellevants per a un tràmit són `GovernmentService`, `HowTo`, `FAQPage` i `BreadcrumbList`.

### Spot-check black-box (opcional — NO entra a la nota GEO/10)

Detecta el risc de desinformació quan un model respon sobre el tràmit. Protocol autocontingut en 3 passos:

1. **Resposta cega** — l'agent respon "què diries a un ciutadà sobre aquest tràmit?" (~10 frases) NOMÉS des del seu coneixement, **sense consultar la fitxa**.
2. **Contrast** — es compara la resposta cega amb la fitxa recuperada (ground truth): es busquen contradiccions materials en imports, terminis, requisits o passos.
3. **Sortida** — etiqueta de risc + llista de contradiccions/al·lucinacions detectades.

Criteri de risc:

| Etiqueta | Quan |
|----------|------|
| **Alt** | Contradicció material en dades crítiques (imports, terminis, requisits) o invenció de la font canònica |
| **Mitjà** | Imprecisions menors o orientació incompleta, sense contradicció material |
| **Baix** | Sense contradiccions; resposta alineada amb la fitxa |

### Format de l'informe — Capa 5

S'afegeix al final de l'informe per tràmit, després de la Capa 4:

```
## Capa 5 — GEO/SEO

[Per a cada criteri: ✅/⚠️/❌ + exemple literal del problema]
✅ Dades estructurades — JSON-LD GovernmentService present.
❌ Títol i metadades — Sense meta description.
...

**Nota GEO/SEO: X/10** (independent de la nota editorial)
Risc de desinformació (spot-check): Baix/Mitjà/Alt — [contradiccions detectades, o "cap"]

### Recomanacions GEO accionables
- [p. ex. afegir JSON-LD GovernmentService amb camps del tràmit]
- [p. ex. <title> més directe sense l'any de convocatòria]
- [p. ex. datar la convocatòria al cos de la fitxa]
```
````

- [ ] **Step 2: Verificar el contingut escrit**

Run: `grep -nE "Secció A|Secció B|Nota GEO/SEO|Spot-check|Capa 5" gencat/skills/gencat-tramits/references/geo-seo.md`
Expected: línies per a les dues seccions, la nota, el spot-check i la Capa 5.

- [ ] **Step 3: Commit**

```bash
git add gencat/skills/gencat-tramits/references/geo-seo.md
git commit -m "feat(tramits): reference GEO/SEO (redacció + on-page)

Co-Authored-By: Claude Opus 4.8 (1M context) <noreply@anthropic.com>"
```

---

### Task 2: Integrar GEO/SEO al `SKILL.md`

**Files:**
- Modify: `gencat/skills/gencat-tramits/SKILL.md` (frontmatter description, secció "Estructura", Llista de verificació ràpida, secció REVISAR WEB)

- [ ] **Step 1: Afegir disparadors GEO/SEO a la description del frontmatter**

A la línia `description:` (línia 3), substituir el final `...o quan l'usuari proporcioni URLs de tramit.gencat.cat per revisar.` per:

```
...o quan l'usuari proporcioni URLs de tramit.gencat.cat per revisar. Inclou avaluació GEO/SEO (posicionament en motors d'IA i de cerca, Schema.org, recuperabilitat) tant en redacció com a REVISAR WEB."
```

(Eliminar la cometa de tancament anterior i posar-la al final del text nou; la `description` ha de quedar amb una sola cometa de tancament.)

- [ ] **Step 2: Afegir `geo-seo.md` a la llista de references de la secció "Estructura d'una fitxa de tràmit"**

Després de la línia `Llegeix \`references/vocabulari.md\` per a substitucions de vocabulari i bones pràctiques.` (línia 45), afegir:

```
Llegeix `references/geo-seo.md` per als principis GEO/SEO de redacció i per a l'avaluació GEO/SEO on-page.
```

- [ ] **Step 3: Afegir el bloc "GEO/SEO en redacció" a la Llista de verificació ràpida**

Al final de la secció "Llista de verificació ràpida", just abans de la línia `---` que precedeix `## Mode REVISAR WEB`, afegir:

```
### GEO/SEO en redacció
- [ ] Títol directe i comprensible sense context?
- [ ] Cada camp és autocontingut i citable per separat?
- [ ] Imports, terminis i convocatòria amb data concreta?
- [ ] Cap dada crítica només en PDF o imatge?

Vegeu `references/geo-seo.md` (Secció A) per al detall.
```

- [ ] **Step 4: Afegir la remissió a GEO/SEO a la secció REVISAR WEB**

Al final del fitxer, després de la línia que remet a `references/revisio-web.md`, afegir:

```
La revisió inclou una **Capa 5 — GEO/SEO** amb nota independent i spot-check de risc de desinformació. Vegeu `references/geo-seo.md` (Secció B).
```

- [ ] **Step 5: Verificar els canvis**

Run: `grep -nE "GEO/SEO|geo-seo.md|Capa 5" gencat/skills/gencat-tramits/SKILL.md`
Expected: la description, la remissió de l'estructura, el bloc de verificació, i la remissió de REVISAR WEB.

- [ ] **Step 6: Commit**

```bash
git add gencat/skills/gencat-tramits/SKILL.md
git commit -m "feat(tramits): integra GEO/SEO al SKILL (disparadors + redacció + REVISAR WEB)

Co-Authored-By: Claude Opus 4.8 (1M context) <noreply@anthropic.com>"
```

---

### Task 3: Integrar la Capa 5 al workflow de `revisio-web.md`

**Files:**
- Modify: `gencat/skills/gencat-tramits/references/revisio-web.md` (Pas 0, workflow per URL, format d'informe, consolidat, exemple)

- [ ] **Step 1: Carregar `geo-seo.md` al Pas 0**

A la secció "Pas 0 — Càrrega de normes (obligatori)", afegir un ítem nou a la llista, després del de `vocabulari.md`:

```
- `references/geo-seo.md` (Secció B) — criteris GEO/SEO on-page, spot-check i format de la Capa 5
```

- [ ] **Step 2: Afegir el pas d'avaluació GEO/SEO al "Workflow per a cada URL"**

A la llista numerada del "Workflow per a cada URL", inserir entre el pas 4 (Avaluació transversal) i el pas 5 (Generació de l'informe), renumerant:

```
5. **Avaluació GEO/SEO** → aplicar els 5 criteris on-page de `geo-seo.md` (Secció B) i, si l'usuari ho demana, el spot-check black-box → nota GEO/10 + etiqueta de risc
6. **Generació de l'informe** → cinc capes (veure format d'informe)
```

(El pas 5 anterior "Generació de l'informe → quatre capes" passa a ser el pas 6 i diu "cinc capes".)

- [ ] **Step 3: Afegir la Capa 5 al "Format de l'informe per tràmit"**

Després del bloc de la "Capa 4 — Avaluació transversal", afegir:

```
### Capa 5 — GEO/SEO

Aplicar els criteris de `geo-seo.md` (Secció B):

​```
## Capa 5 — GEO/SEO
✅/⚠️/❌ [Criteri] — [exemple literal]

**Nota GEO/SEO: X/10** (independent de la nota editorial)
Risc de desinformació (spot-check): Baix/Mitjà/Alt — [contradiccions, o "cap"]

### Recomanacions GEO accionables
- [recomanació concreta]
​```
```

(Nota per a l'executor: el bloc de codi intern usa ``` reals; els `​` zero-width d'aquest plan són només per escapar-lo aquí — al fitxer final han de ser triple-backtick normals.)

- [ ] **Step 4: Afegir columnes GEO/Risc al consolidat**

A la secció "Informe consolidat (múltiples URLs)", substituir la taula resum perquè inclogui les columnes GEO i Risc:

```markdown
| Tràmit | Editorial | GEO/SEO | Risc | Prioritat | Principals problemes |
|--------|-----------|---------|------|-----------|---------------------|
| [Títol tràmit 1] | X/10 | X/10 | Alt | ALTA | Taxes absent, sense Schema.org |
| [Títol tràmit 2] | X/10 | X/10 | Baix | MITJANA | Frases llargues a Descripció |
```

- [ ] **Step 5: Afegir la Capa 5 a l'exemple complet d'informe**

Al final del bloc "## Exemple complet d'informe (cas fictici)", després de la Capa 4 de l'exemple (línia que acaba amb "✅ Jerarquia de títols — Sense salts."), afegir dins del mateix bloc d'exemple:

```
## Capa 5 — GEO/SEO
❌ Dades estructurades — La pàgina no inclou cap JSON-LD Schema.org.
⚠️ Títol i metadades — meta description de 210 caràcters (fora del rang 120-160).
✅ Atribució oficial — Departament d'Educació identificat al capçal.
✅ Extractabilitat — Requisits, terminis i import en text pla.
❌ Actualitat datada — La convocatòria no indica data d'actualització.

**Nota GEO/SEO: 3/5 → 6,0/10**
Risc de desinformació (spot-check): Mitjà — la resposta cega situava l'import en 100 € quan la fitxa diu 120 €.

### Recomanacions GEO accionables
- Afegir JSON-LD GovernmentService amb objecte, òrgan i canals del tràmit.
- Escurçar la meta description a 120-160 caràcters.
- Datar la convocatòria al cos de la fitxa.
```

- [ ] **Step 6: Verificar els canvis**

Run: `grep -nE "geo-seo|Capa 5|GEO/SEO|Nota GEO" gencat/skills/gencat-tramits/references/revisio-web.md`
Expected: Pas 0, pas de workflow, format Capa 5, taula consolidada i exemple.

- [ ] **Step 7: Commit**

```bash
git add gencat/skills/gencat-tramits/references/revisio-web.md
git commit -m "feat(tramits): Capa 5 GEO/SEO al workflow de REVISAR WEB

Co-Authored-By: Claude Opus 4.8 (1M context) <noreply@anthropic.com>"
```

---

### Task 4: Actualitzar el `README.md`

**Files:**
- Modify: `README.md:64-71` (descripció de capacitats de `gencat-tramits`)

- [ ] **Step 1: Afegir la dimensió GEO/SEO a la llista de capacitats**

A la secció `### \`gencat-tramits\``, afegir un ítem nou a la llista de capacitats, després de `- Tractament personal coherent (tu / vós) i frases de 20-30 paraules`:

```
- Avaluació GEO/SEO: recuperabilitat per motors d'IA i de cerca (Schema.org, títols directes, dades datades) en redacció i en REVISAR WEB, amb nota independent i spot-check de risc de desinformació
```

- [ ] **Step 2: Afegir `geo-seo.md` a l'arbre de references del README (si hi és)**

Run: `grep -n "passos.md" README.md`
Si l'arbre de fitxers llista els references de `gencat-tramits`, afegir-hi una línia per a `geo-seo.md` seguint el format de les altres (p. ex. `│       ├── geo-seo.md            ← criteris GEO/SEO (redacció + on-page)`). Si no hi apareixen els references individuals, ometre aquest pas.

- [ ] **Step 3: Verificar**

Run: `grep -nE "GEO/SEO|geo-seo" README.md`
Expected: la línia de capacitats (i la de l'arbre si aplica).

- [ ] **Step 4: Commit**

```bash
git add README.md
git commit -m "docs: documenta la dimensió GEO/SEO de gencat-tramits al README

Co-Authored-By: Claude Opus 4.8 (1M context) <noreply@anthropic.com>"
```

---

### Task 5: Verificació final de coherència

**Files:** cap (només lectura)

- [ ] **Step 1: Comprovar que no s'han duplicat criteris d'altres skills**

Run: `grep -niE "llargada de frases|veu activa|jerarquia de títols|textos d'enllaços" gencat/skills/gencat-tramits/references/geo-seo.md`
Expected: cap resultat (o només dins de la nota de remissió "no es dupliquen…"). Si apareixen com a criteris puntuables, és un error: eliminar-los i remetre a la skill corresponent.

- [ ] **Step 2: Comprovar la coherència de noms entre fitxers**

Run: `grep -rnE "Capa 5|Nota GEO/SEO|geo-seo.md" gencat/skills/gencat-tramits/`
Expected: el terme "Capa 5", "Nota GEO/SEO" i la ruta `geo-seo.md` apareixen de forma consistent a `SKILL.md`, `revisio-web.md` i `geo-seo.md` (mateixa nomenclatura, sense variants com "Capa GEO" o "nota IA").

- [ ] **Step 3: Lectura final**

Llegir `references/geo-seo.md` sencer i confirmar que les dues seccions són coherents amb l'spec i que el format de la Capa 5 coincideix amb el de `revisio-web.md`.

- [ ] **Step 4: Cap commit** (només verificació).

---

## Self-review notes

- **Cobertura de l'spec:** Secció A (Task 1) · Secció B criteris+scoring+spot-check (Task 1) · format Capa 5 (Task 1, Task 3) · doble vessant a SKILL (Task 2) · workflow+informe+consolidat (Task 3) · README (Task 4) · anti-duplicació (Task 1 nota + Task 5 verificació). Tots els fitxers de l'spec tenen tasca.
- **Sense placeholders:** tot el contingut Markdown a escriure és literal als steps.
- **Coherència de noms:** "Capa 5 — GEO/SEO", "Nota GEO/SEO: X/10", `references/geo-seo.md` usats igual a totes les tasques; verificat a Task 5.
