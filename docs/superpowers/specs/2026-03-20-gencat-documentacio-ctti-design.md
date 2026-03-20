# Spec: gencat-documentacio-ctti

**Data:** 2026-03-20
**Estat:** Aprovat

---

## Resum

Skill per validar els documents tècnics principals del cicle de vida de projectes CTTI: l'Especificació de Requisits (ERQ) i la Descripció d'Arquitectura (DA). Cobreix l'estructura oficial CTTI i criteris de qualitat per garantir que els documents són implementables sense sorpreses.

---

## Context

Els analistes, product owners i arquitectes de la Generalitat reben documents funcionals i d'arquitectura elaborats a partir d'entrevistes i decisions de disseny. Abans d'aprovar-los cal verificar que compleixen l'estructura CTTI i que el contingut és prou clar i detallat per al desenvolupament. El procés actual és manual i inconsistent.

---

## Audiència

- Analistes funcionals i product owners (revisió ERQ)
- Arquitectes i developers (revisió DA)
- Validador final (aprovació de tots dos)

---

## Nom i ubicació

```
gencat/skills/gencat-documentacio-ctti/
├── SKILL.md
└── references/
    ├── erq-estructura.md        ← seccions obligatòries ERQ + criteris per secció
    ├── da-estructura.md         ← 7 vistes DA + variacions per tipus d'arquitectura
    ├── criteris-qualitat.md     ← 5 criteris de qualitat comuns (claredat, detall, consistència, verificabilitat, traçabilitat)
    └── puntuacio-i-informe.md   ← fórmula de puntuació, llindar ≥80, format de l'informe
```

---

## Modes

| Situació | Mode |
|----------|------|
| L'usuari adjunta o enganxa un document tècnic | REVISAR |
| Pregunta sobre com redactar o estructurar un document CTTI | CONSULTAR |
| Dubte | Preguntar: "Vols revisar un document o tens una consulta sobre com redactar-lo?" |

**Input acceptat (mode REVISAR):**
- Text enganxat directament a la conversa (preferit)
- Contingut copiat d'un fitxer `.docx` (nota: els fitxers `.docx` binaris no es poden llegir directament; demanar a l'usuari que enganxi el text)
- Múltiples documents: ≤3 en paral·lel si tots tenen el tipus declarat; si algun DA no té tipus d'arquitectura declarat, processar-los un per un

**Càrrega de referències:**
- Mode REVISAR (ERQ) → carregar `erq-estructura.md` + `criteris-qualitat.md` + `puntuacio-i-informe.md`
- Mode REVISAR (DA) → carregar `da-estructura.md` + `criteris-qualitat.md` + `puntuacio-i-informe.md`
- Mode CONSULTAR (ERQ) → carregar `erq-estructura.md` + `criteris-qualitat.md`
- Mode CONSULTAR (DA) → carregar `da-estructura.md` + `criteris-qualitat.md`
- Mode CONSULTAR (tipus no determinat) → preguntar: "La consulta és sobre un ERQ (requisits funcionals) o una DA (arquitectura)?"

---

## Detecció del tipus de document

| Indicis | Tipus |
|---------|-------|
| Conté "requisits funcionals", "RF-", "casos d'ús", "especificació de requisits" | ERQ |
| Conté almenys un de: "vista de context", "vista funcional", "vista de desplegament", "vista operacional", "Descripció d'Arquitectura", "DA" com a codi de document | DA |
| Ambigú o cap indicador clar | Preguntar: "És un document de requisits funcionals (ERQ) o una descripció d'arquitectura (DA)?" |

**Nota:** la paraula "arquitectura" per si sola no és indicador de DA — pot aparèixer en l'apartat de Visió general d'un ERQ. Cal detectar els noms específics de vistes o el codi "DA".

---

## ERQ — Estructura CTTI (DT_ERQ)

| Secció | Obligatòria |
|--------|-------------|
| Visió general del sistema (abast, diagrama de context o descripció equivalent, mòduls funcionals) | Sí |
| Usuaris de la solució (perfils, rols, responsabilitats) | Sí |
| Requisits funcionals (llista numerada, un requisit per ítem) | Sí |
| Requisits no funcionals (rendiment, seguretat, disponibilitat) | Sí |
| Casos d'ús o fluxos funcionals | Sí |
| Informació de suport (diccionari de dades, entitats, pantalles si escau) | Opcional |

Avaluació: ✅ si present amb contingut, ❌ si absent o buida (seccions obligatòries).

**Informació de suport (opcional):** no es penalitza si és absent. S'afegeix una nota ⚠️ informativa (sense deducció de punts) únicament si el document fa referència a entitats de dades o mockups sense que existeixi aquesta secció. Si és present però té problemes de qualitat, s'apliquen les penalitzacions estàndard al ritme de ⚠️ (−5).

---

## DA — Vistes obligatòries per tipus d'arquitectura

| Vista | Cloud Privat | Cloud Públic | SaaS | Low Code | On-Premise |
|-------|:-----------:|:------------:|:----:|:--------:|:----------:|
| Context | ✓ | ✓ | ✓ | ✓ | ✓ |
| Funcional | ✓ | ✓ | ✓ | ✓ | ✓ |
| Informació | ✓ | ✓ | ✓ | ✓ | ✓ |
| Concurrència | ✓ | ✓ | ✓ | ✓ | ✓ |
| Desenvolupament | ✓ | ✓ | — | — | ✓ |
| Desplegament | ✓ | ✓ | — | ✓ | ✓ |
| Operacional | ✓ | ✓ | — | — | ✓ |

Font: documentació oficial AiDA — https://canigo.ctti.gencat.cat/arquitectura/da/aida/

**Low Code:** Desplegament és obligatòria perquè cal documentar les integracions i configuracions de la plataforma. Desenvolupament i Operacional no s'apliquen perquè la plataforma Low Code els gestiona de manera transparent.

**Si el tipus d'arquitectura no consta al document:** preguntar abans de validar: "Quin tipus d'arquitectura és? (Cloud Privat, Cloud Públic, SaaS, Low Code, On-Premise)"

Avaluació: ✅ si la vista és present amb contingut, ❌ si és absent/buida i és obligatòria per al tipus, N/A si no aplica al tipus.

---

## Criteris de qualitat (comuns a ERQ i DA)

Els 5 criteris s'avaluen **globalment** per al document sencer (no per secció/vista). Cada criteri es puntua un cop, independentment del nombre de seccions afectades:

| Criteri | ❌ Error | ⚠️ Millora |
|---------|---------|-----------|
| **Claredat** | Redacció ambigua o amb múltiples interpretacions | Redacció confusa però interpretable |
| **Detall suficient** | Falta flux, condició o resposta del sistema per implementar | Detall mínim però incomplet |
| **Consistència** | Contradicció entre seccions/vistes | Inconsistència menor de terminologia |
| **Verificabilitat** | Requisit/vista no comprovable ("ha de ser ràpid", "escalable") | Criteri d'acceptació poc precís |
| **Traçabilitat** | Cap referència a necessitats de negoci o origen del requisit/decisió | Traçabilitat parcial |

**Seccions/vistes opcionals presents:** els criteris de qualitat s'apliquen però les penalitzacions es compten al ritme de ⚠️ (−5) independentment de la gravetat.

---

## Puntuació i llindar d'aprovació

- Base: 100 punts
- Nivell 1: −15 per cada ❌ en secció/vista obligatòria absent o buida
- Nivell 2: −15 per cada criteri de qualitat ❌ (avaluat globalment, 1 cop per criteri)
- −5 per cada ⚠️ (tant d'estructura com de qualitat)
- La puntuació no pot ser inferior a 0
- **Aprovat automàtic: ≥ 80 punts**
- Per sota de 80: recomanació "Retornar a l'autor"

**Nota sobre asimetria per tipus de DA:** el nombre màxim de penalitzacions de Nivell 1 varia per tipus (Cloud Privat té 7 vistes obligatòries; SaaS en té 4). La fórmula és la mateixa per a tots dos però el llindar de 80 és proporcionalment més difícil d'assolir com menys vistes obligatòries té el document. Això és intencionat: un SaaS DA que falla en una vista dels 4 és un problema proporcional a un Cloud Privat DA que en falla dues de 7.

---

## Format de l'informe (mode REVISAR)

```
## Informe de Validació — [Nom del document] ([ERQ/DA]) — [Data]

### Puntuació global
[XX/100] — Aprovat / Retornar a l'autor

### Nivell 1 — Estructura
| Secció/Vista | Estat | Observació |
|--------------|-------|------------|
| [nom] | ✅/❌/N/A | ... |
...

### Nivell 2 — Qualitat del contingut
| Criteri | Estat | Detall |
|---------|-------|--------|
| Claredat | ✅/⚠️/❌ | ... |
| Detall suficient | ✅/⚠️/❌ | ... |
| Consistència | ✅/⚠️/❌ | ... |
| Verificabilitat | ✅/⚠️/❌ | ... |
| Traçabilitat | ✅/⚠️/❌ | ... |

### Preguntes obertes per a l'autor
1. [Secció/Vista/Requisit]: [pregunta concreta]
2. ...

### Resum executiu (per al validador final)
Punts crítics que impedeixen aprovació: [llista]
Recomanació: ✅ Aprovat / ❌ Retornar a l'autor
```

---

## Referències CTTI

- ERQ: https://qualitat.solucions.gencat.cat/procediments/analisi-disseny/especificacio_requisits/
- DA (AiDA): https://canigo.ctti.gencat.cat/arquitectura/da/aida/
- Lliurables tècnics: https://qualitat.solucions.gencat.cat/estandards/estandard-lliurables-tecnics/

---

## Decisions de disseny

| Decisió | Alternativa descartada | Motiu |
|---------|----------------------|-------|
| Skill únic per ERQ + DA | Skills separats per document | Visió global, criteris de qualitat compartits, menys duplicació |
| Scope ERQ + DA (no DTE ni manuals) | Tots els lliurables CTTI | ERQ i DA són els documents crítics pre-desenvolupament; DTE i manuals en depenen |
| Criteris de qualitat globals (no per secció) | Avaluació per secció | Evita scores negatius, més manejable per l'analista |
| Llindar ≥80 | ≥70 | Garantir qualitat real dels documents abans del desenvolupament |
| Un sol informe per a totes les audiències | Informe per rol | Menys complexitat, consistent amb skills existents |
| "Informació de suport" ERQ sense penalització per absència | ⚠️ automàtic si absent | Secció genuïnament opcional; penalitzar-la sempre seria injust |
| Detecció DA per noms de vistes, no per "arquitectura" | Paraula genèrica "arquitectura" | Evita falsos positius en ERQs que mencionen l'arquitectura al context |
| Processar batch DA un per un si manca tipus d'arquitectura | Bloquejar el batch | Manté la usabilitat; el cas habitual és que el tipus consti al document |
