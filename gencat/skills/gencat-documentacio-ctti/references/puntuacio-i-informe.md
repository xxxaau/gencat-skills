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

**Nota important sobre asimetria per tipus de DA:**
El nombre de vistes obligatòries varia per tipus (Cloud Privat: 7, SaaS: 4). Amb la mateixa fórmula, el llindar de 80 és proporcionalment més difícil d'assolir en documents amb poques vistes. Això és **intencionat**: fallar una vista en un SaaS DA (1 de 4) és un problema proporcional a fallar-ne dues en un Cloud Privat DA (2 de 7).

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
