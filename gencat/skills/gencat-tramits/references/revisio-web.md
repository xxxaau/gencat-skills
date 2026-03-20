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
| Pàgina sense estructura de tràmit reconeixible — mode ≤3 URLs | Demanar confirmació: "La pàgina [URL] no sembla una fitxa de tràmit estàndard. Vols que intenti revisar-la igualment?" |
| Pàgina sense estructura de tràmit reconeixible — mode >3 URLs | Marcar com a "no processada" i continuar sense interrompre el lot |
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
| **Títol de la modalitat** | No segueix l'estructura verb-infinitiu + tipus (p. ex. "Sol·licitar la subvenció") · conté nominalitzacions ("Sol·licitud de...") | |
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
| 0–4 | ALTA | 4 o més camps amb ❌ |

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
