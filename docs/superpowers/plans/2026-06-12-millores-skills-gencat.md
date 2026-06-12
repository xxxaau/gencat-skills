# Pla d'implementació — Millores de les skills gencat

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Aplicar les millores de la revisió exhaustiva (2026-06-11) a les 7 skills del plugin gencat, una skill per tasca, amb commit per skill.

**Architecture:** Edicions de documentació (SKILL.md + references) per skill. Criteris: descriptions = només disparadors (~350 caràcters); zero duplicació SKILL.md ↔ references (delegació explícita); exemples copiables on falten; correcció d'errors tècnics citats. No es toquen les seccions que afegirà el PR #1 (Abast de la skill) per minimitzar conflictes.

**Tech Stack:** Markdown, frontmatter YAML. Verificació: relectura del fitxer editat, comprovació que els enllaços a `references/` existeixen, longitud de description < 400 caràcters.

**Spec:** L'informe de revisió consolidat de la conversa (2026-06-11), validat per l'usuari. Les troballes descartades (WCAG 2.2.3, ratio 3.8:1 del vermell) NO s'apliquen.

---

### Task 1: gencat-design-system

**Files:**
- Modify: `gencat/skills/gencat-design-system/SKILL.md`
- Modify: `gencat/skills/gencat-design-system/references/foundations.md`
- Modify: `gencat/skills/gencat-design-system/references/components.md`
- Modify: `gencat/skills/gencat-design-system/references/patterns.md`

- [ ] **Step 1: Reescriure la description** (línia 3) a:
  > "Aplica el Sistema de Disseny oficial de la Generalitat de Catalunya quan construeixis, estilitzis o revisis interfícies web per a serveis digitals Gencat. Activa-la quan es mencioni Gencat, sistema de disseny, components UI, tokens, colors o tipografia corporativa en el desenvolupament web per a la Generalitat de Catalunya."
- [ ] **Step 2: SKILL.md — eliminar duplicacions.** Substituir les seccions "Font" (l.63-72), "Colors principals" (l.74-89) i "Accessibilitat obligatòria" (l.91-98) per una referència compacta: tokens → `references/foundations.md`; accessibilitat → 3 regles crítiques + delegació a `gencat-accessibilitat`.
- [ ] **Step 3: SKILL.md — distingir Tooltip/Popover** a la nomenclatura: `Descripció emergent (hover)` / `Descripció emergent (click)`.
- [ ] **Step 4: foundations.md — nota sobre el doble ús de #C00000** (marca/CTA i error) després de la taula de colors d'estat, amb estratègia de desambiguació (context + icona).
- [ ] **Step 5: foundations.md — completar tokens** amb `--font-weight-*` i `--line-height-*` al bloc CSS final, i exemple CSS de grid responsive després de la taula de punts de tall.
- [ ] **Step 6: components.md — separar Tooltip i Popover** en dues files; afegir exemple HTML de `Botons` amb estats (primari/secundari/perill/desactivat) i remissions als exemples de formulari i taula de `patterns.md` (DRY).
- [ ] **Step 7: patterns.md — correccions:** (a) treure `aria-required="true"` redundant on hi ha `required`; (b) afegir `aria-invalid` a les regles de validació; (c) substituir la checklist d'accessibilitat per 4 ítems crítics + delegació a `gencat-accessibilitat`; (d) corregir "vostè" → "vós" i delegar el tractament a `gencat-comunicacio-clara`.
- [ ] **Step 8: nota sobre la URL del Storybook** (build de Chromatic, pot canviar; la font estable és sistemadedisseny.gencat.cat) a SKILL.md i components.md.
- [ ] **Step 9: Verificar** — relectura, enllaços vàlids, description < 400 caràcters.
- [ ] **Step 10: Commit** `git commit -m "feat(design-system): dedupe SKILL.md, nota #C00000, tokens complets, fix vostè->vós"`

### Task 2: gencat-comunicacio-clara

**Files:**
- Modify: `gencat/skills/gencat-comunicacio-clara/SKILL.md`
- Modify: `gencat/skills/gencat-comunicacio-clara/references/redaccio.md`
- Modify: `gencat/skills/gencat-comunicacio-clara/references/ui-literals.md`
- Modify: `gencat/skills/gencat-comunicacio-clara/references/vocabulari.md`

- [ ] **Step 1: Reescriure la description** a:
  > "Aplica la Guia de Comunicació Clara de la Generalitat quan redactis o revisis textos per a serveis digitals Gencat: literals d'UI, missatges d'error, formularis, avisos i notificacions. Activa-la quan es mencioni comunicació clara, llenguatge planer, literals, microcopy o textos administratius per simplificar."
- [ ] **Step 2: Resoldre la incoherència de puntuació de llistes** entre `redaccio.md:40` i `titols-i-estructura.md:100-105` (adoptar el criteri de titols-i-estructura.md, corregir l'exemple de redaccio.md o viceversa segons la guia oficial — decidir en llegir els fitxers).
- [ ] **Step 3: Taula context → tractament (tu/vós)** a ui-literals.md, coherent amb SKILL.md:33.
- [ ] **Step 4: Comprimir SKILL.md** — eliminar les taules duplicades amb redaccio.md (l.24-50), deixar principis + 3 regles vitals + delegació.
- [ ] **Step 5: ui-literals.md — afegir seccions:** errors d'autenticació/seguretat (contrasenya, intents, certificat digital, sessió) i notificacions (email/push: assumpte, cos, límits).
- [ ] **Step 6: redaccio.md — completar la regla dels gerundis** amb exemple correcte de simultaneïtat i exemple incorrecte addicional.
- [ ] **Step 7: vocabulari.md — aclarir formes inclusives** (col·lectius genèrics vs formes amb barra: quan és acceptable cada una).
- [ ] **Step 8: Verificar i commit** `feat(comunicacio-clara): coherència tu/vós i llistes, errors seguretat, notificacions`

### Task 3: gencat-accessibilitat

**Files:**
- Modify: `gencat/skills/gencat-accessibilitat/SKILL.md`
- Modify: `gencat/skills/gencat-accessibilitat/references/components-accessibles.md`
- Modify: `gencat/skills/gencat-accessibilitat/references/errors-habituals.md`
- Modify: `gencat/skills/gencat-accessibilitat/references/wcag-criteris.md`
- Create: `gencat/skills/gencat-accessibilitat/references/pdf-accessibilitat.md`

- [ ] **Step 1: Corregir errors ARIA citats:** (a) `aria-disabled` + `disabled` redundant; (b) `required` + `aria-required` redundant; (c) `aria-label` que duplica text visible al botó d'ordenació de taula.
- [ ] **Step 2: Completar el patró de pestanyes** amb el bloc JavaScript de gestió de teclat (fletxes, Home/End, activació).
- [ ] **Step 3: Crear `references/pdf-accessibilitat.md`** (etiquetatge, ordre de lectura, alt text, formularis i taules en PDF, validació) i enllaçar-lo des de SKILL.md.
- [ ] **Step 4: Ajustar l'abast d'apps mòbils natives:** o cobertura mínima (VoiceOver/TalkBack, criteris aplicables) o retirar la promesa de la description — decisió: nota explícita d'abast amb remissió a EN 301 549 C11, i description sense prometre apps natives.
- [ ] **Step 5: Reescriure la description** a:
  > "Aplica les directrius d'accessibilitat digital de la Generalitat de Catalunya (WCAG 2.1 AA, EN 301 549, Decret 216/2023) quan implementis, revisis o auditis interfícies i documents per a serveis Gencat. Activa-la quan es mencioni accessibilitat, WCAG, a11y, ARIA, contrast, focus, lector de pantalla, IRA o daltonisme."
- [ ] **Step 6: WCAG 2.2 —** nota d'estatus prudent (criteris llistats, exigibilitat legal pendent de confirmació amb la font oficial; recomanar-ne el compliment).
- [ ] **Step 7: Afegits menors:** patró de modal de timeout de sessió; nota CAPTCHA accessible a errors-habituals; definició de "component UI" per al contrast 3:1 amb exemples; secció "Antipatrons ARIA freqüents".
- [ ] **Step 8: Consolidar** `aria-label` vs `aria-labelledby` en una sola secció referenciada.
- [ ] **Step 9: Verificar i commit** `feat(accessibilitat): fix antipatrons ARIA, teclat a pestanyes, PDF, abast apps`

### Task 4: gencat-xarxes-socials

**Files:**
- Create: `gencat/skills/gencat-xarxes-socials/references/normes-transversals.md`
- Modify: `gencat/skills/gencat-xarxes-socials/SKILL.md` + els 8 fitxers de plataforma + `plantilles.md`

- [ ] **Step 1: Crear `normes-transversals.md`** amb el contingut comú (hashtags CamelCase, alt text, subtítols, emojis, to institucional, errors genèrics a evitar) extret dels 8 fitxers.
- [ ] **Step 2: Reduir cada fitxer de plataforma** al contingut específic (límits, formats, to particular, exemples propis) + capçalera "Normes comunes: `normes-transversals.md`".
- [ ] **Step 3: Taula unificada de límits al SKILL.md** (plataforma × límit × hashtags × to) i regla de quan preguntar la plataforma vs deduir-la.
- [ ] **Step 4: plantilles.md — protocol de resposta a crítiques/crisi** i guia de fils (quan usar fil, estructura ganxo-desenvolupament-CTA).
- [ ] **Step 5: Actualitzar la nota de Threads** (desfasada) i marcar com a "per verificar amb la guia vigent" el comportament de links a Instagram (sense afirmar canvis no verificats).
- [ ] **Step 6: Reescriure la description** a:
  > "Aplica la Guia de Xarxes Socials de la Generalitat quan generis, revisis o adaptis contingut per a X, Facebook, Instagram, LinkedIn, YouTube, Threads o TikTok en comunicació institucional. Activa-la quan es mencioni post, publicació, hashtag, fil, reel, story o l'adaptació de comunicats i tràmits a xarxes socials."
- [ ] **Step 7: Verificar i commit** `feat(xarxes-socials): normes transversals comunes, taula de límits, protocol de crisi`

### Task 5: gencat-tramits

**Files:**
- Modify: `gencat/skills/gencat-tramits/SKILL.md`
- Modify: `gencat/skills/gencat-tramits/references/camps.md`
- Modify: `gencat/skills/gencat-tramits/references/revisio-web.md`
- Modify: `gencat/skills/gencat-tramits/references/vocabulari.md`

- [ ] **Step 1: Reescriure la description** (971 → ~330 caràcters) a:
  > "Aplica el Manual de redacció i estil de fitxes de tràmit de la Generalitat (febrer 2026) quan redactis, revisis o auditis fitxes de tràmit de gencat.cat. Activa-la quan es mencioni fitxa de tràmit, modalitat, silenci administratiu, passos de tramitació, GECO, OGE, SAC o quan l'usuari proporcioni URLs de tramit.gencat.cat per revisar."
- [ ] **Step 2: revisio-web.md — exemple complet d'informe** (fitxa fictícia amb 5-6 errors realistes, informe de 4 capes omplert).
- [ ] **Step 3: revisio-web.md — taula camp × obligatorietat** per resoldre l'ambigüitat "camp absent".
- [ ] **Step 4: SKILL.md — delegar redacció genèrica** a gencat-comunicacio-clara (treure veu activa/llargada de frase duplicades; deixar només regles específiques de fitxes) i referenciar gencat-accessibilitat fora del mode REVISAR WEB.
- [ ] **Step 5: camps.md — casos límit:** modalitats amb terminis diferents, taxes variables/bonificacions, tràmits sense termini, nota sobre fitxes multilingües.
- [ ] **Step 6: Objectivar criteris vagues** de revisio-web.md (definir com es mesura "frases >30 paraules de mitjana").
- [ ] **Step 7: Verificar i commit** `feat(tramits): description curta, exemple d'informe, casos límit, delegació`

### Task 6: gencat-identitat-corporativa

**Files:**
- Modify: `gencat/skills/gencat-identitat-corporativa/SKILL.md`
- Modify: `gencat/skills/gencat-identitat-corporativa/references/comunicacio-digital.md`
- Modify: `gencat/skills/gencat-identitat-corporativa/references/documents.md`
- Modify: `gencat/skills/gencat-identitat-corporativa/references/marca-visual.md`
- Modify: `gencat/skills/gencat-identitat-corporativa/references/validacio.md`

- [ ] **Step 1: Reescriure la description** (838 → ~330 caràcters) a:
  > "Aplica les normes d'identitat corporativa de la Generalitat quan creïs o validis material institucional fora del web: documents, presentacions, signatures de correu, cartes o newsletters. Activa-la quan es mencioni identitat corporativa, marca o logotip Gencat, colors o tipografia corporativa, o quan s'enviï material per validar."
- [ ] **Step 2: comunicacio-digital.md — plantilla de signatura** (text pla + HTML amb les especificacions ja documentades) i text de la clàusula legal en català i castellà (resta d'idiomes: remissió a la font oficial, sense inventar).
- [ ] **Step 3: documents.md — expandir** amb estructura de carta oficial (capçalera/cos/peu), taula de mides de font per element i marges.
- [ ] **Step 4: marca-visual.md — taula de versions del logotip** (positiu/negatiu/monocrom) i subsecció de coexistència de marques (sense inventar normes: principis generals + remissió a identitatcorporativa.gencat.cat per a casos d'organismes amb marca pròpia i emblema UE).
- [ ] **Step 5: validacio.md — protocol de validació visual operatiu** (ordre de comprovacions sobre una imatge, com reportar) i unificar amb la checklist del SKILL.md (la checklist remet al workflow).
- [ ] **Step 6: Verificar i commit** `feat(identitat): plantilles de signatura, documents amb mides, versions logotip`

### Task 7: gencat-documentacio-ctti

**Files:**
- Modify: `gencat/skills/gencat-documentacio-ctti/SKILL.md`
- Modify: `gencat/skills/gencat-documentacio-ctti/references/da-estructura.md`
- Modify: `gencat/skills/gencat-documentacio-ctti/references/criteris-qualitat.md`
- Modify: `gencat/skills/gencat-documentacio-ctti/references/puntuacio-i-informe.md`

- [ ] **Step 1: Suport ERQ+DA híbrid** — fila nova a la taula de detecció i a la de càrrega de references.
- [ ] **Step 2: Traçabilitat ERQ→DA** — estendre el criteri 5 de criteris-qualitat.md (components/integracions de la DA tracen als RF de l'ERQ associat).
- [ ] **Step 3: Arquitectures mixtes** — nota a da-estructura.md (vistes del tipus principal + complementàries; pregunta si no consta).
- [ ] **Step 4: Exemple complet d'informe** (un ERQ i un DA) a puntuacio-i-informe.md.
- [ ] **Step 5: Objectivar ⚠️ vs ❌ a Claredat** (abast quantitatiu) i regla anti doble-penalització entre Detall i Verificabilitat.
- [ ] **Step 6: Secció "Fora d'abast"** al SKILL.md (DT_PRB, DT_MOP, etc.) i reformular la nota d'asimetria del llindar 80.
- [ ] **Step 7: Reescriure la description** a:
  > "Valida i orienta sobre documents tècnics CTTI: l'Especificació de Requisits (ERQ/DT_ERQ) i la Descripció d'Arquitectura (DA). Activa-la quan es mencioni ERQ, DA, document funcional, especificació de requisits o vistes d'arquitectura, o quan l'usuari enganxi un document tècnic per revisar o pregunti com redactar-lo."
- [ ] **Step 8: Verificar i commit** `feat(documentacio-ctti): híbrids ERQ+DA, traçabilitat creuada, exemples d'informe`

### Task 8: transversal (final)

- [ ] **Step 1: Unificar encapçalaments** a totes les skills: `## Detecció del mode`, `## Llista de verificació`.
- [ ] **Step 2: Comprovar** que cap description supera 400 caràcters i que tots els enllaços `references/` resolen.
- [ ] **Step 3: Commit** `chore: unifica encapçalaments i descriptions de les skills gencat`

---

**Notes d'execució:**
- No tocar les zones on el PR #1 inserirà "## Abast de la skill" (just després del títol/intro de cada SKILL.md) — les edicions se situen en altres seccions per minimitzar conflictes de merge.
- No afirmar fets externs no verificats (estatus legal WCAG 2.2, links a captions d'Instagram): redactar en condicional o marcar "verifica amb la font oficial".
- Verificació per task: relectura del resultat + enllaços + longitud de description. Test d'activació amb subagent al final del conjunt (Task 8).
