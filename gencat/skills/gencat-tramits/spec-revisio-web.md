# Spec: gencat-tramits — Mode REVISAR WEB

**Data:** 2026-03-20
**Estat:** Aprovat per l'usuari
**Skill base:** `gencat-tramits`

---

## Resum

Nou mode `REVISAR WEB` per al skill `gencat-tramits`. Permet revisar fitxes de tràmit publicades al web gencat.cat a partir d'una llista d'URLs, generar una valoració estructurada i proposar millores de redacció basades en el Manual de redacció de fitxes de tràmit (febrer 2026).

---

## Cas d'ús

L'usuari proporciona una o més URLs de fitxes de tràmit de gencat.cat. Claude accedeix a cada URL, extreu el contingut dels camps, l'avalua contra les normes del manual i retorna un informe amb tres capes: avaluació per camp, puntuació global i proposta de nova redacció.

---

## Fitxers afectats

| Fitxer | Acció | Descripció |
|--------|-------|------------|
| `gencat/skills/gencat-tramits/SKILL.md` | Modificar | Afegir paraules clau al `description` i secció Mode REVISAR WEB |
| `gencat/skills/gencat-tramits/references/revisio-web.md` | Crear | Workflow complet, criteri de puntuació i format d'informe |

Els fitxers `camps.md`, `passos.md` i `vocabulari.md` no es modifiquen: el mode REVISAR WEB els consumeix com a font de normes.

---

## Canvis al SKILL.md

### Frontmatter — paraules clau afegides al `description`

Afegir al final de la cadena `description` existent:
```
"[...] Activa-la també per al mode REVISAR WEB quan l'usuari proporcioni URLs de fitxes de tràmit de gencat.cat per revisar, auditar o avaluar, o mencioni 'revisió de tràmit', 'auditoria de tràmit', 'revisar tràmit web' o 'llista d'URLs de tràmits'."
```

### Nova secció al SKILL.md

```markdown
## Mode REVISAR WEB

S'activa quan l'usuari proporciona una o més URLs de fitxes de tràmit de gencat.cat.

Llegeix `references/revisio-web.md` per al workflow complet, el criteri de puntuació i el format de l'informe.
```

---

## references/revisio-web.md — Contingut complet

### Detecció del nombre d'URLs

| URLs proporcionades | Mode de processament |
|--------------------|---------------------|
| ≤ 3 URLs | Processa en paral·lel → informe consolidat al final |
| > 3 URLs | Processa una a una → resum parcial entre cada tràmit → informe consolidat al final |

### Workflow per a cada URL

1. **Fetch** → obtenir el contingut de la fitxa amb WebFetch
2. **Identificació de camps** → buscar els 8 camps estàndard (veure taula de camps)
3. **Avaluació camp per camp** → aplicar les normes de `references/camps.md`, `references/passos.md` i `references/vocabulari.md`
4. **Generació de l'informe** → tres capes (veure format d'informe)

### Gestió d'errors

- **URL no accessible** → avisar l'usuari ("No he pogut accedir a [URL]. Continuo amb les altres.") i seguir
- **Pàgina sense estructura de tràmit reconeixible** → avisar i demanar confirmació: "La pàgina [URL] no sembla una fitxa de tràmit estàndard. Vols que intenti revisar-la igualment?"
- **Camp no trobat** → marcar directament com ❌ "camp absent"

### Taula de camps i criteris d'avaluació

Cada camp val **1 punt** si passa la revisió sense errors.

| Camp | ❌ Error (obligatori corregir) | ⚠️ Millora (recomanada) |
|------|-------------------------------|------------------------|
| **Títol** | >80 caràcters · conté "sol·licitud", "inscripció" o "convocatòria" · té punt final | Estructura incorrecta (no segueix tipus+objecte+concreció) |
| **Descripció** | Cita departament o normativa a l'inici · repeteix literalment el títol | Frases de >30 paraules de mitjana |
| **A qui va dirigit** | Falta la preposició "a" davant de cada destinatari · camp absent | Redacció poc clara o massa genèrica |
| **Terminis** | Format de data incorrecte (p. ex. 17/02/2025 en lloc de 17 de febrer de 2025) | |
| **Documentació** | Inclou el formulari de sol·licitud · no és en forma de llista | |
| **Requisits** | Conté frase introductòria · no és en forma de llista directa | |
| **Taxes** | Camp absent o buit (ha d'indicar sempre import o "gratuït") | Import sense format clar |
| **Passos** | Falta avís obligatori de tramitació al pas 1 · falta silenci administratiu al pas 4 | Textos no estàndard (apartat `references/passos.md`) |

### Puntuació global

```
Puntuació = (camps sense ❌) / (total camps trobats) × 10
```

| Puntuació | Prioritat de revisió |
|-----------|---------------------|
| 8-10 | BAIXA — tot ✅ o quasi |
| 5-7 | MITJANA — tot ⚠️, cap ❌ |
| 0-4 | ALTA — hi ha algun ❌ |

### Format de l'informe per tràmit

#### Capa 1 — Avaluació per camp

```
## [Nom del camp]
✅ Correcte — [breu justificació]
⚠️ Millora recomanada — [descripció del problema]
❌ Error — [descripció del problema i norma incomplerta]
```

#### Capa 2 — Puntuació global

```
**Puntuació: X/10**
Camps correctes: N | Millores recomanades: N | Errors: N
Prioritat de revisió: ALTA / MITJANA / BAIXA
```

#### Capa 3 — Proposta de nova redacció

Només per als camps amb ⚠️ o ❌. Format:

```
### [Nom del camp] — Proposta
[Text corregit seguint les normes de camps.md / passos.md / vocabulari.md]
```

### Informe consolidat (múltiples URLs)

Quan es revisen múltiples tràmits, afegir al final una taula resum:

```markdown
## Resum de la revisió

| Tràmit | Puntuació | Prioritat | Principals problemes |
|--------|-----------|-----------|---------------------|
| [Títol tràmit 1] | X/10 | ALTA | Taxes absent, Requisits amb frase introductòria |
| [Títol tràmit 2] | X/10 | MITJANA | Frases llargues a Descripció |

**Camps problemàtics comuns:** [llista dels camps amb més errors al conjunt]
```

---

## Decisions de disseny

| Decisió | Raó |
|---------|-----|
| Mode dins del skill existent (no skill nou) | El workflow comparteix totes les normes de `gencat-tramits`; una skill separada duplicaria la base de coneixement |
| WebFetch per accedir a les URLs | Eina disponible a Claude Code; suficient per a pàgines HTML públiques |
| Camp absent = ❌ | Tots els camps de la fitxa de tràmit són obligatoris segons el manual |
| Proposta de redacció només per a ⚠️/❌ | Evita generar text innecessari per als camps ja correctes |
| Processament ≤3 paral·lel / >3 seqüencial | Equilibri entre velocitat (llistes curtes) i control (llistes llargues) |
