---
name: gencat-documentacio-ctti
description: "Valida i orienta sobre documents tècnics CTTI: l'Especificació de Requisits (ERQ/DT_ERQ) i la Descripció d'Arquitectura (DA). Activa-la quan es mencioni ERQ, DA, document funcional, especificació de requisits o vistes d'arquitectura, o quan l'usuari enganxi un document tècnic per revisar o pregunti com redactar-lo."
---

# Documentació Tècnica CTTI — Generalitat de Catalunya

Skill per validar i orientar sobre els dos documents tècnics principals del cicle de vida de projectes CTTI: l'**Especificació de Requisits (ERQ)** i la **Descripció d'Arquitectura (DA)**.

**Font oficial ERQ:** https://qualitat.solucions.gencat.cat/procediments/analisi-disseny/especificacio_requisits/
**Font oficial DA (AiDA):** https://canigo.ctti.gencat.cat/arquitectura/da/aida/

---

## Abast de la skill

### Què cobreix
- Revisió estructural i de qualitat de documents ERQ i DA
- Orientació sobre seccions obligatòries, criteris i puntuació
- Flux de revisió formal en modes REVISAR i CONSULTAR

### Què NO cobreix
- Implementació tècnica de codi, components o interfícies finals
- Revisió funcional de marca corporativa o maquetació institucional
- Auditoria WCAG completa de productes digitals (fora de l'abast documental)

### Skills complementàries
- `gencat-design-system` quan els requisits afecten components i patrons de UI
- `gencat-accessibilitat` quan cal concretar requisits no funcionals d'accessibilitat
- `gencat-comunicacio-clara` per millorar llegibilitat en resums executius i contingut textual

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
| Conté indicis d'ERQ **i** de DA alhora (p. ex. RF numerats i vistes d'arquitectura) | **ERQ+DA** (document integrat) — confirmar amb l'usuari i revisar les dues parts |
| Ambigú o cap indicador clar | Preguntar: "És un document de requisits funcionals (ERQ) o una descripció d'arquitectura (DA)?" |

> La paraula "arquitectura" per si sola **no** és indicador de DA — pot aparèixer en la Visió general d'un ERQ. Els indicadors fiables de DA són els noms de les vistes ("vista de context", "vista de desplegament"...).

---

## Càrrega de referències

| Mode | Tipus | Fitxers a carregar |
|------|-------|--------------------|
| REVISAR | ERQ | `references/erq-estructura.md` + `references/criteris-qualitat.md` + `references/puntuacio-i-informe.md` |
| REVISAR | DA | `references/da-estructura.md` + `references/criteris-qualitat.md` + `references/puntuacio-i-informe.md` |
| REVISAR | ERQ+DA | Tots quatre fitxers — avaluar cada part amb la seva estructura (dos informes de Nivell 1, un de Nivell 2 conjunt) i validar la traçabilitat creuada RF → components |
| CONSULTAR | ERQ | `references/erq-estructura.md` + `references/criteris-qualitat.md` |
| CONSULTAR | DA | `references/da-estructura.md` + `references/criteris-qualitat.md` |
| CONSULTAR | tipus no determinat | Preguntar: "La consulta és sobre un ERQ (requisits funcionals) o una DA (arquitectura)?" |

---

## Input acceptat (mode REVISAR)

- Text enganxat directament a la conversa (preferit)
- Contingut copiat d'un fitxer `.docx` — si l'usuari proporciona una ruta `.docx`, demanar: "Els fitxers .docx no es poden llegir directament. Pots enganxar el contingut del document aquí?"
- Múltiples documents: ≤3 en paral·lel si tots tenen el tipus declarat; si algun DA no té tipus d'arquitectura declarat, processar-los un per un

---

## Llista de verificació ràpida (mode REVISAR)

Abans de lliurar l'informe, verifica:

- [ ] S'ha identificat correctament el tipus (ERQ o DA)?
- [ ] Per a DA: s'ha confirmat el tipus d'arquitectura?
- [ ] S'han avaluat totes les seccions/vistes obligatòries (Nivell 1)?
- [ ] S'han avaluat els 5 criteris de qualitat globalment (Nivell 2)?
- [ ] La puntuació és correcta i té floor a 0?
- [ ] El resum executiu indica clarament si el document és ✅ Aprovat o ❌ Retornar a l'autor?

---

## Fora d'abast

Aquesta skill només cobreix **ERQ i DA**. Resten fora d'abast els altres documents del cicle de vida CTTI: pla de proves, manual d'operació, document de desplegament, documentació de seguretat, conformitat RGPD i manuals d'usuari.

Si l'usuari demana revisar-ne un, indica-ho: "Aquesta skill es limita a l'ERQ i la DA; per a [document], consulta el procediment corresponent a https://qualitat.solucions.gencat.cat/procediments/". Pots fer-ne una lectura general si l'usuari ho vol, però sense aplicar la puntuació ni la plantilla d'informe d'aquesta skill.
