# Spec: gencat-documents-funcionals

**Data:** 2026-03-20
**Estat:** Aprovat

---

## Resum

Skill per validar documents funcionals d'aplicacions (especificacions de requisits, casos d'ús i documents híbrids) seguint l'estructura oficial del CTTI (DT_ERQ) i criteris de qualitat per garantir que el document és implementable sense sorpreses.

---

## Context

Els analistes i product owners de la Generalitat reben documents funcionals elaborats a partir d'entrevistes. Abans d'aprovar-los, cal verificar que compleixen l'estructura CTTI i que el contingut és prou clar i detallat per al desenvolupament. El procés actual és manual i inconsistent.

---

## Audiència

- Analistes funcionals i product owners (revisió prèvia)
- Developers i arquitectes (implementació)
- Validador final (aprovació)

---

## Nom i ubicació

```
gencat/skills/gencat-documents-funcionals/
├── SKILL.md
└── references/
    ├── estructura-ctti.md
    ├── criteris-qualitat.md
    └── puntuacio-i-informe.md
```

---

## Modes

| Situació | Mode |
|----------|------|
| L'usuari adjunta o enganxa un document funcional | REVISAR |
| Pregunta sobre com redactar o estructurar un DF | CONSULTAR |
| Dubte | Preguntar: "Vols revisar un document o tens una consulta sobre com redactar-lo?" |

**Input acceptat (mode REVISAR):**
- Text enganxat directament a la conversa
- Ruta de fitxer `.docx` local
- Múltiples documents: ≤3 en paral·lel, >3 un per un

---

## Nivell 1 — Estructura CTTI (DT_ERQ)

| Secció | Obligatòria |
|--------|-------------|
| Visió general del sistema (abast, diagrama de context o descripció equivalent, mòduls funcionals) | Sí |
| Usuaris de la solució (perfils, rols, responsabilitats) | Sí |
| Requisits funcionals (llista numerada, un requisit per ítem) | Sí |
| Requisits no funcionals (rendiment, seguretat, disponibilitat) | Sí |
| Casos d'ús o fluxos funcionals | Sí |
| Informació de suport (diccionari de dades, entitats, pantalles si escau) | Opcional — ⚠️ si absent |

Avaluació: ✅ si present amb contingut, ❌ si absent o buida.

---

## Nivell 2 — Criteris de qualitat

Per a cada secció present, avaluar els 5 criteris:

| Criteri | ❌ Error | ⚠️ Millora |
|---------|---------|-----------|
| **Claredat** | Redacció ambigua o amb múltiples interpretacions | Redacció confusa però interpretable |
| **Detall suficient** | Falta flux, condició o resposta del sistema per implementar | Detall mínim però incomplet |
| **Consistència** | Contradicció entre seccions | Inconsistència menor de terminologia |
| **Verificabilitat** | Requisit no comprovable ("ha de ser ràpid", "fàcil d'usar") | Criteri d'acceptació poc precís |
| **Traçabilitat** | Cap referència a necessitats de negoci o origen del requisit | Traçabilitat parcial |

---

## Puntuació i llindar d'aprovació

- Base: 100 punts
- −15 per cada ❌ en secció obligatòria (estructura o qualitat)
- −5 per cada ⚠️
- **Aprovat automàtic: ≥ 80 punts**
- Per sota de 80: recomanació "Retornar a l'autor"

---

## Format de l'informe (mode REVISAR)

```
## Informe de Validació — [Nom del document]

### Puntuació global
[XX/100] — Aprovat / Retornar a l'autor

### Nivell 1 — Estructura
| Secció | Estat | Observació |
|--------|-------|------------|
| Visió general | ✅/❌ | ... |
| Usuaris | ✅/❌ | ... |
| Requisits funcionals | ✅/❌ | ... |
| Requisits no funcionals | ✅/❌ | ... |
| Casos d'ús | ✅/❌ | ... |
| Informació de suport | ✅/⚠️ | ... |

### Nivell 2 — Qualitat del contingut
[Per cada secció present: indicar els criteris que fallen amb exemples concrets]

### Preguntes obertes per a l'autor
1. [Secció/Requisit]: [pregunta concreta]
2. ...

### Resum executiu (per al validador final)
Punts crítics que impedeixen aprovació: [llista]
Recomanació: ✅ Aprovat / 🔄 Retornar
```

---

## Referències

- Estructura DT_ERQ: https://qualitat.solucions.gencat.cat/procediments/analisi-disseny/especificacio_requisits/
- Checklist CHK_ERQ: disponible a l'àrea de lliurables del CTTI

---

## Decisions de disseny

| Decisió | Alternativa descartada | Motiu |
|---------|----------------------|-------|
| Un sol informe per a totes les audiències | Informe per rol (opció B) | Menys complexitat, consistent amb skills existents |
| Modes REVISAR + CONSULTAR | Mode APROVAR separat (opció C) | El resum executiu integrat al REVISAR cobreix el cas d'ús del validador final |
| Llindar ≥80 | ≥70 | Garantir qualitat real dels DF abans del desenvolupament |
