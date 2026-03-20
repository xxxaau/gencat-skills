# Mode VALIDAR — Workflow d'Auditoria de Marca

Font de normes: `marca-visual.md`, `documents.md`, `comunicacio-digital.md`

---

## Pas 0 — Identificació del material (obligatori)

Abans de validar, identificar:
- **Tipus de material:** document Word, presentació PowerPoint, PDF, signatura de correu, newsletter...
- **Input rebut:** imatge, fitxer local, text enganxat, o combinació

Si el tipus no és identificable, preguntar: *"De quin tipus de material es tracta? (document Word/PowerPoint, signatura de correu, PDF...)"*

Carregar el fitxer de referència corresponent:
- Document/Presentació/PDF → `documents.md`
- Signatura de correu / Newsletter → `comunicacio-digital.md`
- Consulta sobre marca en general → `marca-visual.md`

---

## Inputs acceptats i mecanisme

| Input | Com l'aporta l'usuari | Valida |
|-------|----------------------|--------|
| Imatge (captura de pantalla) | Adjunt a la conversa | Colors, logotip, tipografia aparent, composició |
| Fitxer PDF | Ruta de fitxer local (Claude usa `Read`) o adjunt | Estructura, elements obligatoris, clàusules |
| Fitxer .docx / .pptx | Ruta de fitxer local (Claude usa `Read` sobre el XML intern) | Estructura i elements obligatoris |
| Text enganxat | Text directament a la conversa | Contingut textual, elements obligatoris |
| Combinació imatge + fitxer/text | Ambdós en la mateixa conversa | Validació completa visual + contingut |

---

## Workflow per a cada material

1. **Identificació** → determinar el tipus de material i l'input rebut (Pas 0)
2. **Validació visual** (si hi ha imatge) → aplicar la taula de criteris visuals
3. **Validació de contingut** (si hi ha fitxer o text) → aplicar la taula de criteris d'estructura
4. **Generació de l'informe** → tres capes (veure format d'informe)

### Pas de validació visual (imatge)

- Color dominant: és el vermell corporatiu (#C00000) el color principal?
- Logotip: present? No distorsionat? Mida aparentment ≥ 4,7 mm?
- Tipografia visible: sembla Arial / Helvetica Neue / Open Sans? (no Calibri ni altres)
- Composició: espai de seguretat respectat al voltant del logotip?

### Pas de validació de contingut (fitxer/text)

- Estructura del document: conté els elements obligatoris per al tipus de suport?
- Signatura de correu: tots els camps presents i en l'ordre correcte (dades > imatge > clàusula)?
- Clàusula legal: present i en la llengua correcta?
- Colors especificats (p. ex. al HTML d'una signatura): coincideixen amb els valors de `marca-visual.md`?

---

## Gestió de múltiples materials

| Situació | Acció |
|----------|-------|
| ≤ 3 materials | Processar en paral·lel → informe consolidat al final |
| > 3 materials | Processar un a un → resum parcial entre cada material → informe consolidat al final |
| Material no identificable | Preguntar el tipus abans de processar |

---

## Taula de criteris d'avaluació

Cada element val **1 punt** si passa sense errors (cap ❌).

| Element | ❌ Error (obligatori corregir) | ⚠️ Millora (recomanada) |
|---------|-------------------------------|------------------------|
| **Color** | Ús d'un color no corporatiu com a color principal | Ús excessiu de groc o or fora del context específic |
| **Logotip** | Absent en comunicació a la ciutadania · distorsionat · mida inferior a 4,7 mm · logotip departamental en lloc del de la Generalitat | Posicionament no òptim |
| **Tipografia** | Ús de Calibri · Helvetica Neue sense llicència en documents Office | Arial en lloc d'Open Sans per a publicacions digitals |
| **Estructura** | Elements obligatoris absents (clàusula legal en signatura, senyal en capçalera...) | Ordre incorrecte dels elements |
| **Composició** | Text o elements sobre el senyal (espai de seguretat no respectat) | — (no hi ha millores parcials: o es respecta o no) |

---

## Puntuació global

```
Puntuació = (elements sense ❌) / (total elements avaluats) × 10
```

> **Nota:** El total d'elements avaluats depèn de l'input rebut (imatge sola: fins a 4 elements visuals; fitxer/text sol: elements d'estructura; combinació: fins a 5 elements). La prioritat es determina pel rang numèric.

| Puntuació | Prioritat | Descripció |
|-----------|-----------|------------|
| 8–10 | BAIXA | Sense errors; possibles millores menors (⚠️) |
| 5–7 | MITJANA | Compliment parcial; errors en elements no crítics |
| 0–4 | ALTA | Errors greus en elements fonamentals (logotip, color principal, estructura) |

---

## Format de l'informe per material

### Capa 1 — Avaluació per element

```
## [Nom de l'element]
✅ Correcte — [breu justificació]

⚠️ Millora recomanada — [descripció del problema]

❌ Error — [descripció del problema i norma incomplerta]
```

### Capa 2 — Puntuació global

```
**Puntuació: X/10**
Elements correctes: N | Millores recomanades: N | Errors: N
Prioritat de revisió: ALTA / MITJANA / BAIXA
```

### Capa 3 — Proposta de correcció

Només per als elements amb ⚠️ o ❌:

```
### [Element] — Proposta
[Descripció concreta del canvi correctiu amb els valors correctes de marca-visual.md]
```

---

## Informe consolidat (múltiples materials)

Quan es validen múltiples materials, afegir al final:

```markdown
## Resum de la revisió

| Material | Puntuació | Prioritat | Principals problemes |
|----------|-----------|-----------|---------------------|
| [Tipus material 1] | X/10 | ALTA | Calibri, logotip absent |
| [Tipus material 2] | X/10 | BAIXA | — |

**Elements problemàtics comuns:** [llista dels elements amb més errors al conjunt]
```
