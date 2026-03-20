# gencat-tramits: Mode REVISAR WEB — Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Afegir el mode `REVISAR WEB` al skill `gencat-tramits` per permetre revisar fitxes de tràmit de gencat.cat a partir d'URLs, generant una avaluació per camp, puntuació global i proposta de nova redacció.

**Architecture:** Dos canvis: (1) modificació del `SKILL.md` existent per afegir paraules clau de trigger i la secció del nou mode; (2) creació del fitxer `references/revisio-web.md` amb el workflow complet, la taula de camps i el format d'informe. Els fitxers `camps.md`, `passos.md` i `vocabulari.md` no es toquen — el nou mode els consumeix com a font de normes.

**Tech Stack:** Markdown pur. Cap codi. Eina d'accés web: WebFetch (disponible a Claude Code).

---

> **Nota per a l'implementador:** Aquest és un projecte de creació de fitxers Markdown (skill per a Claude Code), no de codi de programació. Les "verificacions" són comprovacions manuals de contingut contra la spec.

---

## Mapa de fitxers

| Fitxer | Acció | Responsabilitat |
|--------|-------|----------------|
| `gencat/skills/gencat-tramits/SKILL.md` | Modificar | Afegir trigger REVISAR WEB al `description` + nova secció al final |
| `gencat/skills/gencat-tramits/references/revisio-web.md` | Crear | Workflow complet: pas 0, detecció d'URLs, taula de camps, puntuació, format d'informe |

---

## Task 1: Modificar SKILL.md

**Fitxers:**
- Modificar: `gencat/skills/gencat-tramits/SKILL.md`

- [ ] **Pas 1: Actualitza el camp `description` del frontmatter**

Obre `gencat/skills/gencat-tramits/SKILL.md`. El `description` actual acaba amb:
```
[...] o qualsevol camp d'una fitxa de tràmit gencat."
```

Substitueix el tancament de cometes i afegeix el nou text. El `description` complet ha de quedar:
```yaml
description: "Aplica el Manual de redacció i estil de fitxes de tràmit de la Generalitat de Catalunya (febrer 2026) quan redactis, revisis o generis contingut per a fitxes de tràmit al web gencat.cat. Usa aquesta skill sempre que l'usuari treballi amb tràmits administratius, fitxes de tràmit, modalitats, camps de tràmit (títol, descripció, requisits, documentació, terminis, taxes, passos), o demani redactar textos per a tràmits en línia. Activa-la també quan mencioni 'fitxa de tràmit', 'modalitat de tràmit', 'silenci administratiu', 'pas de tramitació', 'canal de tramitació', 'GECO', 'OGE', 'SAC' o qualsevol camp d'una fitxa de tràmit gencat. Activa-la també per al mode REVISAR WEB quan l'usuari proporcioni URLs de fitxes de tràmit de gencat.cat per revisar, auditar o avaluar, o mencioni 'revisió de tràmit', 'auditoria de tràmit', 'revisar tràmit web', 'llista d\'URLs de tràmits', o enganxi directament una URL de tramit.gencat.cat o cat.gencat.cat."
```

- [ ] **Pas 2: Afegeix la secció Mode REVISAR WEB al final del fitxer**

Al final del fitxer (després de la llista de verificació ràpida), afegeix:

```markdown
---

## Mode REVISAR WEB

S'activa quan l'usuari proporciona una o més URLs de fitxes de tràmit de gencat.cat.

Pas 0 obligatori: llegir `references/camps.md`, `references/passos.md` i `references/vocabulari.md` per tenir les normes carregades abans de començar la revisió.

Llegeix `references/revisio-web.md` per al workflow complet, el criteri de puntuació i el format de l'informe.
```

- [ ] **Pas 3: Verifica els canvis**

Comprova:
- El `description` al frontmatter conté les paraules clau: `'revisió de tràmit'`, `'auditoria de tràmit'`, `'revisar tràmit web'`, `tramit.gencat.cat`
- La secció `## Mode REVISAR WEB` apareix al final del fitxer
- El fitxer comença i acaba amb el bloc `---` del frontmatter intacte
- La resta del SKILL.md no ha canviat

- [ ] **Pas 4: Commit**

```bash
cd "D:\40361989w\Dev\gencat-skills"
git add gencat/skills/gencat-tramits/SKILL.md
git commit -m "feat: gencat-tramits — afegeix mode REVISAR WEB al SKILL.md

Co-Authored-By: Claude Sonnet 4.6 <noreply@anthropic.com>"
```

---

## Task 2: Crear references/revisio-web.md

**Fitxers:**
- Crear: `gencat/skills/gencat-tramits/references/revisio-web.md`

- [ ] **Pas 1: Crea el fitxer amb el contingut complet**

El fitxer ha de contenir exactament les seccions en aquest ordre:

```markdown
# Revisió Web de Fitxes de Tràmit — Workflow

Font de normes: `camps.md`, `passos.md`, `vocabulari.md`

---

## Pas 0 — Càrrega de normes (obligatori)

Abans de revisar cap URL, llegir:
- `references/camps.md` — normes per a cada camp
- `references/passos.md` — textos estàndard per als passos
- `references/vocabulari.md` — substitucions i bones pràctiques

---

## Detecció del nombre d'URLs

| URLs proporcionades | Mode de processament |
|--------------------|---------------------|
| ≤ 3 URLs | Processa en paral·lel → informe consolidat al final |
| > 3 URLs | Processa una a una → resum parcial entre cada tràmit → informe consolidat al final |

---

## Workflow per a cada URL

1. **Fetch** → obtenir el contingut de la fitxa amb WebFetch
2. **Identificació de camps** → buscar els camps estàndard (veure taula de camps)
3. **Avaluació camp per camp** → aplicar les normes de `camps.md`, `passos.md` i `vocabulari.md`
4. **Generació de l'informe** → tres capes (veure format d'informe)

---

## Gestió d'errors

| Situació | Acció |
|----------|-------|
| URL no accessible | Avisar: "No he pogut accedir a [URL]. Continuo amb les altres." i seguir |
| Contingut truncat (fitxa molt llarga) | Avisar: "He recuperat el contingut parcialment. Els camps no trobats es marcaran com a absents." i continuar |
| Pàgina sense estructura de tràmit — mode ≤3 URLs | Demanar confirmació: "La pàgina [URL] no sembla una fitxa de tràmit estàndard. Vols que intenti revisar-la igualment?" |
| Pàgina sense estructura de tràmit — mode >3 URLs | Marcar com a "no processada" i continuar sense interrompre el lot |
| Camp no trobat | Marcar com ❌ "camp absent" — compta com a camp trobat amb error al denominador |

---

## Tràmits amb múltiples modalitats

Quan una fitxa té diverses modalitats, revisar cadascuna de forma independent per als camps específics de modalitat (títol de modalitat, passos). Els camps globals (títol principal, descripció, taxes) es revisen una sola vegada per al tràmit.

---

## Taula de camps i criteris d'avaluació

Cada camp val **1 punt** si passa la revisió sense errors (cap ❌).
Si un camp té simultàniament un ❌ i un ⚠️, mostrar tots dos problemes però comptar-lo com a erroni (0 punts).

| Camp | ❌ Error (obligatori corregir) | ⚠️ Millora (recomanada) |
|------|-------------------------------|------------------------|
| **Títol** | Conté "sol·licitud", "inscripció" o "convocatòria" · té punt final · >80 caràcters *sense comptar espais, any de convocatòria, acrònims i sigles* | Estructura incorrecta (no segueix tipus+objecte+concreció) |
| **Títol de la modalitat** | No segueix l'estructura verb-infinitiu + tipus · conté nominalitzacions ("Sol·licitud de...") | |
| **Avís general del tràmit** | Falta la frase obligatòria per a subjectes obligats · frase present però incorrecta (no coincideix amb el text estàndard de `camps.md`) | |
| **Descripció** | Cita departament o normativa a l'inici · repeteix literalment el títol | Frases de >30 paraules de mitjana |
| **A qui va dirigit** | Falta la preposició "a" davant de cada destinatari · camp absent | Redacció poc clara o massa genèrica |
| **Terminis** | Format de data incorrecte (p. ex. 17/02/2025 en lloc de "17 de febrer de 2025") | |
| **Documentació** | Inclou el formulari de sol·licitud · no és en forma de llista · redacció no esquemàtica (frases completes en lloc d'ítems breus) | |
| **Requisits** | Conté frase introductòria · no és en forma de llista directa | |
| **Taxes** | Camp absent o buit (ha d'indicar sempre import o "gratuït") | Import sense format clar |
| **Passos** | Falta avís obligatori de tramitació al pas 1 · falta indicació de silenci administratiu al pas 4 | Textos no estàndard (comparar amb `passos.md`) |

---

## Puntuació global

```
Puntuació = (camps sense ❌) / (total camps trobats o absents) × 10
```

> **Nota:** Un camp absent compta com a "trobat amb ❌", no s'exclou del denominador.

| Puntuació | Prioritat de revisió | Descripció |
|-----------|---------------------|------------|
| 8–10 | BAIXA | Sense errors; possibles millores menors (⚠️) |
| 5–7 | MITJANA | 3–5 camps amb ❌ |
| 0–4 | ALTA | 6 o més camps amb ❌ |

---

## Format de l'informe per tràmit

### Capa 1 — Avaluació per camp

Si un camp té múltiples problemes, mostrar-los tots:

```
## [Nom del camp]
✅ Correcte — [breu justificació]

⚠️ Millora recomanada — [descripció del problema]

❌ Error — [descripció del problema i norma incomplerta]
❌ Error — [segon problema si n'hi ha]
```

### Capa 2 — Puntuació global

```
**Puntuació: X/10**
Camps correctes: N | Millores recomanades: N | Errors: N
Prioritat de revisió: ALTA / MITJANA / BAIXA
```

### Capa 3 — Proposta de nova redacció

Només per als camps amb ⚠️ o ❌:

```
### [Nom del camp] — Proposta
[Text corregit seguint les normes de camps.md / passos.md / vocabulari.md]
```

---

## Informe consolidat (múltiples URLs)

Quan es revisen múltiples tràmits, afegir al final:

```markdown
## Resum de la revisió

| Tràmit | Puntuació | Prioritat | Principals problemes |
|--------|-----------|-----------|---------------------|
| [Títol tràmit 1] | X/10 | ALTA | Taxes absent, Requisits amb frase introductòria |
| [Títol tràmit 2] | X/10 | MITJANA | Frases llargues a Descripció |

**Camps problemàtics comuns:** [llista dels camps amb més errors al conjunt]
```
```

- [ ] **Pas 2: Verifica l'estructura del fitxer**

Comprova que el fitxer conté aquestes seccions en ordre:
1. `## Pas 0 — Càrrega de normes`
2. `## Detecció del nombre d'URLs`
3. `## Workflow per a cada URL`
4. `## Gestió d'errors`
5. `## Tràmits amb múltiples modalitats`
6. `## Taula de camps i criteris d'avaluació` (10 camps)
7. `## Puntuació global` (fórmula + taula BAIXA/MITJANA/ALTA)
8. `## Format de l'informe per tràmit` (3 capes)
9. `## Informe consolidat`

- [ ] **Pas 3: Commit**

```bash
cd "D:\40361989w\Dev\gencat-skills"
git add gencat/skills/gencat-tramits/references/revisio-web.md
git commit -m "feat: gencat-tramits — crea references/revisio-web.md

Co-Authored-By: Claude Sonnet 4.6 <noreply@anthropic.com>"
```

---

## Task 3: Validació final

- [ ] **Pas 1: Verifica l'estructura de fitxers del skill**

```bash
find gencat/skills/gencat-tramits -type f | sort
```

Resultat esperat:
```
gencat/skills/gencat-tramits/SKILL.md
gencat/skills/gencat-tramits/plan-revisio-web.md
gencat/skills/gencat-tramits/spec-revisio-web.md
gencat/skills/gencat-tramits/references/camps.md
gencat/skills/gencat-tramits/references/passos.md
gencat/skills/gencat-tramits/references/revisio-web.md
gencat/skills/gencat-tramits/references/vocabulari.md
```

- [ ] **Pas 2: Verifica el trigger al SKILL.md**

```bash
grep "REVISAR WEB" gencat/skills/gencat-tramits/SKILL.md
```

Resultat esperat: almenys 2 línies (una al `description`, una a la secció).

- [ ] **Pas 3: Verifica els 10 camps a revisio-web.md**

```bash
grep -c "OBLIGATORI\|Error\|Millora" gencat/skills/gencat-tramits/references/revisio-web.md
```

Ha de retornar un nombre > 0. Verificar manualment que la taula té 10 files de camps.

- [ ] **Pas 4: Verifica els últims commits**

```bash
git log --oneline -5
```

Resultat esperat: els 2 commits de les tasks 1 i 2 al capdamunt.

- [ ] **Pas 5: Push**

```bash
git push
```
