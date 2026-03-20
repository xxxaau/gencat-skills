# Revisió Web de Fitxes de Tràmit — Workflow

Font de normes: `camps.md`, `passos.md`, `vocabulari.md`, `gencat-comunicacio-clara`, `gencat-accessibilitat`

---

## Pas 0 — Càrrega de normes (obligatori)

Abans de revisar cap URL, llegir:
- `references/camps.md` — normes per a cada camp
- `references/passos.md` — textos estàndard per als passos
- `references/vocabulari.md` — substitucions i bones pràctiques
- Skill `gencat-comunicacio-clara` → `references/redaccio.md` i `references/vocabulari.md` — criteris de text clar i vocabulari planer
- Skill `gencat-accessibilitat` → `references/wcag-criteris.md` i `references/errors-habituals.md` — criteris d'accessibilitat de contingut

---

## Detecció del nombre d'URLs

| URLs proporcionades | Mode de processament |
|--------------------|---------------------|
| ≤ 3 URLs | Processa en paral·lel → informe consolidat al final |
| > 3 URLs | Processa una a una → resum parcial entre cada tràmit → informe consolidat al final |

---

## Fetch de la fitxa

El contingut de tramits.gencat.cat és **server-side rendered**: tot el text (incloent el contingut dels passos expandibles) és present al HTML inicial sense necessitat de JavaScript ni de navegador complet.

**Mètode preferit: WebFetch directe a la URL HTML** (temps de resposta ~200ms). No cal Playwright.

El contingut dels passos "Saber-ne més" ja és al DOM (classe `step-hidden-content`) — no cal fer clic per expandir-lo.

Per obtenir totes les modalitats d'un tràmit, fer un fetch per a cada valor de `moda=N` (1, 2, 3...) fins que no hi hagi contingut.

**Playwright només cal si WebFetch no retorna el contingut** (pàgines amb renderitzat client-side excepcional). En aquest cas, usar navegador i expandir manualment els passos.

---

## Workflow per a cada URL

1. **Fetch** → WebFetch directe a la URL HTML (un fetch per modalitat: `?moda=1`, `?moda=2`, etc.)
2. **Identificació de camps** → buscar els camps estàndard pels ancles `id=` de la pàgina (`id="que-es"`, `id="requisits"`, `id="documentacio"`, `id="taxes"`, `id="steps"`, etc.)
3. **Avaluació camp per camp** → aplicar les normes de `camps.md`, `passos.md` i `vocabulari.md`
4. **Avaluació transversal** → aplicar criteris de comunicació clara i accessibilitat de contingut (veure taula transversal)
5. **Generació de l'informe** → quatre capes (veure format d'informe)

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
| **Avís general del tràmit** | Falta la frase obligatòria per a subjectes obligats · frase present però incorrecta (no coincideix amb el text estàndard de `camps.md`) · *Nota: si el tràmit és únicament per a persones físiques (no hi ha subjectes obligats a tramitació electrònica exclusiva), l'absència és ✅ correcta i no compta com a error* | |
| **Descripció** | Cita departament o normativa a l'inici · reprodueix el títol o inicia amb la mateixa estructura (p. ex. títol "Prestació per a famílies amb infants" → descripció "Prestació per a famílies que han tingut un fill...") | Frases de >30 paraules de mitjana |
| **A qui va dirigit** | Falta la preposició "a" davant de cada destinatari · camp absent | Inclou condicions econòmiques o d'edat que haurien d'anar als Requisits · Redacció poc clara o massa genèrica |
| **Terminis** | Format de data incorrecte (p. ex. 17/02/2025 en lloc de "17 de febrer de 2025") | |
| **Documentació** | Inclou el formulari de sol·licitud · no és en forma de llista · redacció no esquemàtica (frases completes en lloc d'ítems breus) | |
| **Requisits** | Conté frase introductòria · no és en forma de llista directa | |
| **Taxes** | Camp absent o buit (ha d'indicar sempre import o "gratuït") | Import sense format clar |
| **Passos** | Falta avís obligatori de tramitació al pas 1 · falta indicació de silenci administratiu al pas de resposta de l'Administració (Pas 3 si el tràmit és gratuït, Pas 4 si té taxa) | Textos no estàndard (comparar amb `passos.md`) |

---

## Criteris transversals

S'apliquen al conjunt del contingut de la fitxa. Complementen l'avaluació per camp sense modificar la puntuació /10.

### Comunicació clara

Aplicar els criteris de `gencat-comunicacio-clara` al text de tots els camps:

| Criteri | ❌ Error | ⚠️ Millora |
|---------|---------|-----------|
| **Llargada de frases** | Mitjana >30 paraules a la Descripció o als Passos | Frases d'entre 20 i 30 paraules (recomanat ≤20) |
| **Veu activa** | Passiva sistemàtica ("serà resolt", "ha estat aprovat", "es presentarà") | Passiva puntual en contextos formals |
| **Tractament personal** | Barreja de tu/vós en el mateix tràmit | |
| **Vocabulari planer** | Termes administratius evitables (contrastar amb `gencat-comunicacio-clara/references/vocabulari.md`) | |
| **Frases en positiu** | Dobles negatius ("no s'acceptarà si no s'adjunta") | |

### Accessibilitat de contingut

Aplicar els criteris de contingut de `gencat-accessibilitat` (no s'avalua el codi HTML, només el text visible):

| Criteri | ❌ Error | ⚠️ Millora |
|---------|---------|-----------|
| **Textos d'enllaços** | Textos genèrics: "aquí", "clica aquí", "llegir més", "accedeix" | Textos poc descriptius fora de context |
| **Jerarquia de títols** | Salt de nivells de títol (p. ex. h2 → h4 sense h3) | |
| **Instruccions sensorials** | Instruccions basades en color o posició: "el botó vermell", "a la dreta", "la icona blava" | |
| **Majúscules** | Blocs de text íntegrament en majúscules | |

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

### Capa 4 — Avaluació transversal

Per a cada criteri transversal, indicar resultat i exemple del text problemàtic:

```
## Comunicació clara
✅ / ⚠️ / ❌ [Criteri] — [descripció del problema i exemple literal del text]

## Accessibilitat de contingut
✅ / ⚠️ / ❌ [Criteri] — [descripció del problema i exemple literal del text]
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
