# Puntuació i Format de l'Informe

---

## Fórmula de puntuació

| Concepte | Valor |
|----------|-------|
| Base | 100 punts |
| Secció/vista obligatòria absent o buida (Nivell 1) | −15 per cada ❌ |
| Criteri de qualitat suspès globalment (Nivell 2) | −15 per cada ❌ |
| Avís d'estructura o qualitat (Nivell 1 o 2) | −5 per cada ⚠️ |
| **Floor** | 0 (mai negatiu) |
| **Llindar d'aprovació** | **≥ 80 punts** |

**Nota sobre la fórmula i el nombre de vistes:**
La deducció per vista absent és fixa (−15) sigui quin sigui el nombre de vistes obligatòries del tipus (Cloud Privat: 7, SaaS: 4), tot i que proporcionalment una vista absent pesa més en un SaaS (1 de 4) que en un Cloud Privat (1 de 7). És una simplificació deliberada: la fórmula única fa la puntuació predictible i comparable entre documents.

---

## Exemples de càlcul

**Exemple 1 — ERQ amb problemes menors (Aprovat)**
- Nivell 1: totes les seccions ✅ → 0 deduccions
- Nivell 2: Verificabilitat ⚠️, Traçabilitat ⚠️ → −10 punts
- **Total: 90/100 → ✅ Aprovat**

**Exemple 2 — ERQ amb problemes greus (Retornar)**
- Nivell 1: Casos d'ús ❌, Requisits no funcionals ❌ → −30 punts
- Nivell 2: Detall suficient ❌, Verificabilitat ❌ → −30 punts
- Avisos: Consistència ⚠️ → −5 punts
- **Total: 35/100 → ❌ Retornar a l'autor**

**Exemple 3 — Cloud Privat DA correcte (Aprovat)**
- Nivell 1: totes les 7 vistes ✅ → 0 deduccions
- Nivell 2: Traçabilitat ⚠️ → −5 punts
- **Total: 95/100 → ✅ Aprovat**

**Exemple 4 — SaaS DA amb una vista absent (Retornar)**
- Nivell 1: Vista d'Informació ❌ (de 4 obligatòries) → −15 punts
- Nivell 2: Detall suficient ❌ → −15 punts
- **Total: 70/100 → ❌ Retornar a l'autor**

---

## Plantilla de l'informe

Usa aquesta plantilla exacta per al mode REVISAR:

~~~markdown
## Informe de Validació — [Nom del document] ([ERQ/DA]) — [Data: YYYY-MM-DD]

### Puntuació global
**[XX/100]** — [✅ Aprovat / ❌ Retornar a l'autor]

### Nivell 1 — Estructura
| Secció/Vista | Estat | Observació |
|--------------|-------|------------|
| [nom secció/vista] | ✅/❌/N/A | [descripció breu del problema o confirmació] |

### Nivell 2 — Qualitat del contingut
| Criteri | Estat | Detall |
|---------|-------|--------|
| Claredat | ✅/⚠️/❌ | [exemple concret del problema si no és ✅] |
| Detall suficient | ✅/⚠️/❌ | [exemple concret] |
| Consistència | ✅/⚠️/❌ | [exemple concret] |
| Verificabilitat | ✅/⚠️/❌ | [exemple concret] |
| Traçabilitat | ✅/⚠️/❌ | [exemple concret] |

### Preguntes obertes per a l'autor
1. **[Secció/Vista/Requisit]:** [pregunta concreta que l'autor ha de respondre per poder aprovar]
2. ...
*(Ometre si no hi ha preguntes obertes)*

### Resum executiu (per al validador final)
**Punts crítics que impedeixen aprovació:**
- [llistat concís dels ❌ que fan baixar la puntuació per sota de 80]
*(Ometre si puntuació ≥ 80)*

**Recomanació: [✅ Aprovat / ❌ Retornar a l'autor]**
~~~

---

## Normes de redacció de l'informe

- Les observacions del Nivell 1 han de citar la secció/vista concreta i el que hi manca
- Els detalls del Nivell 2 han d'incloure un exemple extret del document (una frase o un RF concret)
- Les preguntes obertes han de ser accionables: l'autor ha de poder respondre-les per millorar el document
- El resum executiu ha de ser llegible en 30 segons — màxim 5 punts crítics

---

## Exemple complet d'informe (ERQ fictici)

~~~markdown
## Informe de Validació — Sistema de Gestió d'Expedients (ERQ) — Data: 2026-06-12

### Puntuació global
**40/100** — ❌ Retornar a l'autor

### Nivell 1 — Estructura
| Secció/Vista | Estat | Observació |
|--------------|-------|------------|
| Visió general del sistema | ✅ | Present; manca el diagrama de context de les integracions, però el text les descriu |
| Usuaris de la solució | ✅ | 5 perfils amb responsabilitats clares |
| Requisits funcionals | ✅ | 35 RF (RF-001 a RF-035) |
| Requisits no funcionals | ❌ | Secció absent: cap referència a rendiment, seguretat ni disponibilitat. Crític per a un sistema que tracta dades personals |
| Casos d'ús | ✅ | 8 casos d'ús amb flux principal i alternatius |

### Nivell 2 — Qualitat del contingut
| Criteri | Estat | Detall |
|---------|-------|--------|
| Claredat | ⚠️ | RF-015: "assignar expedients de manera flexible" — flexible com? Afecta 5 RF de 35 (menys d'un terç → ⚠️) |
| Detall suficient | ❌ | RF-012 "Cercar expedients" no diu quins camps es cerquen ni el límit de resultats; els 3 casos d'ús crítics no tenen fluxos d'error |
| Consistència | ⚠️ | La Visió general parla de 3 tipus d'expedient; els RF només treballen amb un de genèric |
| Verificabilitat | ❌ | RF-018: "el sistema ha de respondre ràpidament" — sense xifres; passa a 10+ RF |
| Traçabilitat | ⚠️ | Només 8 de 35 RF citen l'origen (normativa o necessitat de negoci) |

### Preguntes obertes per a l'autor
1. **Requisits no funcionals:** quins objectius de rendiment (temps de resposta, usuaris concurrents), seguretat (autenticació, xifratge, auditoria) i disponibilitat (SLA) ha de complir el sistema?
2. **RF-015:** quins usuaris poden assignar expedients i a qui (mateix grup, qualsevol grup)?
3. **Tipus d'expedient:** els 3 tipus de la Visió general tenen comportaments diferents? Si és així, calen RF específics.

### Resum executiu (per al validador final)
**Punts crítics que impedeixen aprovació:**
- Requisits no funcionals absents (−15): sistema amb dades personals sense cap requisit de seguretat
- Verificabilitat fallada (−15): més de 10 RF sense criteri mesurable
- Detall insuficient (−15): fluxos d'error absents als casos d'ús crítics

**Recomanació: ❌ Retornar a l'autor**
~~~

Desglossament del càlcul de l'exemple: 100 − 15×3 (❌: RNF absents, Detall suficient, Verificabilitat) − 5×3 (⚠️: Claredat, Consistència, Traçabilitat) = **40/100**. Recorda restar tots els ⚠️ (és l'oblit més habitual) i indica sempre el desglossament al costat de la puntuació.
