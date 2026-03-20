---
name: gencat-documentacio-ctti
description: "Valida documents tècnics CTTI quan l'usuari comparteixi o demani revisar un document funcional o d'arquitectura. Usa aquesta skill per a l'Especificació de Requisits (ERQ / DT_ERQ) i la Descripció d'Arquitectura (DA). Activa-la quan l'usuari mencioni 'document funcional', 'especificació de requisits', 'ERQ', 'document d'arquitectura', 'DA', 'DT_ERQ', 'descripció d'arquitectura', 'vistes d'arquitectura', 'CTTI document', o quan enganxi el contingut d'un document tècnic per revisar. Activa-la també en mode CONSULTAR quan l'usuari pregunti sobre com redactar o estructurar un ERQ o una DA."
---

# Documentació Tècnica CTTI — Generalitat de Catalunya

Skill per validar i orientar sobre els dos documents tècnics principals del cicle de vida de projectes CTTI: l'**Especificació de Requisits (ERQ)** i la **Descripció d'Arquitectura (DA)**.

**Font oficial ERQ:** https://qualitat.solucions.gencat.cat/procediments/analisi-disseny/especificacio_requisits/
**Font oficial DA (AiDA):** https://canigo.ctti.gencat.cat/arquitectura/da/aida/

---

## Detecció del mode

| Situació | Mode |
|----------|------|
| L'usuari enganxa o comparteix un document tècnic | REVISAR |
| L'usuari pregunta sobre com redactar o estructurar un document CTTI | CONSULTAR |
| Dubte | Preguntar: "Vols revisar un document o tens una consulta sobre com redactar-lo?" |

---

## Detecció del tipus de document

| Indicis al text | Tipus |
|-----------------|-------|
| Conté "requisits funcionals", "RF-", "casos d'ús", "especificació de requisits" | ERQ |
| Conté almenys un de: "vista de context", "vista funcional", "vista de desplegament", "vista operacional", "Descripció d'Arquitectura", "DA" com a codi | DA |
| Ambigú o cap indicador clar | Preguntar: "És un document de requisits funcionals (ERQ) o una descripció d'arquitectura (DA)?" |

> La paraula "arquitectura" per si sola **no** és indicador de DA — pot aparèixer en la Visió general d'un ERQ.

---

## Càrrega de referències

| Mode | Tipus | Fitxers a carregar |
|------|-------|--------------------|
| REVISAR | ERQ | `references/erq-estructura.md` + `references/criteris-qualitat.md` + `references/puntuacio-i-informe.md` |
| REVISAR | DA | `references/da-estructura.md` + `references/criteris-qualitat.md` + `references/puntuacio-i-informe.md` |
| CONSULTAR | ERQ | `references/erq-estructura.md` + `references/criteris-qualitat.md` |
| CONSULTAR | DA | `references/da-estructura.md` + `references/criteris-qualitat.md` |
| CONSULTAR | tipus no determinat | Preguntar: "La consulta és sobre un ERQ (requisits funcionals) o una DA (arquitectura)?" |

---

## Input acceptat (mode REVISAR)

- Text enganxat directament a la conversa (preferit)
- Contingut copiat d'un fitxer `.docx` — si l'usuari proporciona una ruta `.docx`, demanar: "Els fitxers .docx no es poden llegir directament. Pots enganxar el contingut del document aquí?"
- Múltiples documents: ≤3 en paral·lel si tots tenen el tipus declarat; si algun DA no té tipus d'arquitectura declarat, processar-los un per un

---

## Checklist ràpida (mode REVISAR)

Abans de lliurar l'informe, verifica:

- [ ] S'ha identificat correctament el tipus (ERQ o DA)?
- [ ] Per a DA: s'ha confirmat el tipus d'arquitectura?
- [ ] S'han avaluat totes les seccions/vistes obligatòries (Nivell 1)?
- [ ] S'han avaluat els 5 criteris de qualitat globalment (Nivell 2)?
- [ ] La puntuació és correcta i té floor a 0?
- [ ] El resum executiu indica clarament si el document és ✅ Aprovat o ❌ Retornar a l'autor?
