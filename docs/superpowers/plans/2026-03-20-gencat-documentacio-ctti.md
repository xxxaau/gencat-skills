# gencat-documentacio-ctti Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Crear la skill `gencat-documentacio-ctti` per validar documents ERQ i DA del CTTI seguint l'estructura oficial i criteris de qualitat, generant informes estructurats amb puntuació i recomanació d'aprovació.

**Architecture:** Skill de Claude Code amb un `SKILL.md` lleuger que orquestra la detecció de mode/tipus i la càrrega de 4 fitxers de referència especialitzats. Dos fitxers d'estructura (un per ERQ, un per DA), un de criteris de qualitat comuns, i un de puntuació i format d'informe.

**Tech Stack:** Markdown (skill files), patró existent dels skills `gencat-*` del repositori.

**Spec:** `docs/superpowers/specs/2026-03-20-gencat-documentacio-ctti-design.md`

---

## Mapa de fitxers

| Fitxer | Acció | Responsabilitat |
|--------|-------|-----------------|
| `gencat/skills/gencat-documentacio-ctti/SKILL.md` | Crear | Frontmatter, detecció de mode/tipus, instruccions de càrrega de referències, checklist ràpida |
| `gencat/skills/gencat-documentacio-ctti/references/erq-estructura.md` | Crear | Seccions obligatòries ERQ, requisits de contingut per secció, errors habituals |
| `gencat/skills/gencat-documentacio-ctti/references/da-estructura.md` | Crear | 7 vistes DA, matriu de vistes per tipus d'arquitectura, requisits de contingut per vista |
| `gencat/skills/gencat-documentacio-ctti/references/criteris-qualitat.md` | Crear | 5 criteris de qualitat globals amb exemples ❌/⚠️/✅ per a ERQ i DA |
| `gencat/skills/gencat-documentacio-ctti/references/puntuacio-i-informe.md` | Crear | Fórmula de puntuació, llindar ≥80, plantilla d'informe, nota d'asimetria DA |
| `gencat/README.md` | Modificar | Afegir skill a la taula i a la llista de navegació |

---

## Task 1: Esquelet del directori i SKILL.md

**Files:**
- Create: `gencat/skills/gencat-documentacio-ctti/SKILL.md`

- [ ] **Step 1: Verificar que no existeix el directori**

  Comprova que `gencat/skills/gencat-documentacio-ctti/` no existeix. Si existeix, atura't i avisa.

- [ ] **Step 2: Crear SKILL.md**

  Crea `gencat/skills/gencat-documentacio-ctti/SKILL.md` amb aquest contingut exacte:

  ```markdown
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
  ```

- [ ] **Step 3: Verificar el contingut creat**

  Llegeix `gencat/skills/gencat-documentacio-ctti/SKILL.md` i comprova:
  - El frontmatter té `name` i `description`
  - La `description` conté paraules clau de trigger: "ERQ", "DA", "document funcional", "arquitectura"
  - Existeixen les 5 seccions principals: Detecció del mode, Detecció del tipus, Càrrega de referències, Input acceptat, Checklist
  - La taula de detecció NO inclou "arquitectura" com a paraula sola

- [ ] **Step 4: Commit**

  ```bash
  git add gencat/skills/gencat-documentacio-ctti/SKILL.md
  git commit -m "feat: gencat-documentacio-ctti — SKILL.md"
  ```

---

## Task 2: references/erq-estructura.md

**Files:**
- Create: `gencat/skills/gencat-documentacio-ctti/references/erq-estructura.md`

- [ ] **Step 1: Crear erq-estructura.md**

  Crea `gencat/skills/gencat-documentacio-ctti/references/erq-estructura.md`:

  ```markdown
  # Estructura ERQ — Especificació de Requisits (DT_ERQ)

  Font oficial: https://qualitat.solucions.gencat.cat/procediments/analisi-disseny/especificacio_requisits/

  ---

  ## Seccions obligatòries

  | Secció | Obligatòria | Avaluació |
  |--------|-------------|-----------|
  | Visió general del sistema | Sí | ✅ present amb contingut / ❌ absent o buida |
  | Usuaris de la solució | Sí | ✅ present amb contingut / ❌ absent o buida |
  | Requisits funcionals | Sí | ✅ present amb contingut / ❌ absent o buida |
  | Requisits no funcionals | Sí | ✅ present amb contingut / ❌ absent o buida |
  | Casos d'ús o fluxos funcionals | Sí | ✅ present amb contingut / ❌ absent o buida |
  | Informació de suport | Opcional | Vegeu regla especial |

  ---

  ## Requisits de contingut per secció

  ### 1. Visió general del sistema
  Ha d'incloure:
  - **Abast**: què fa el sistema i què queda fora
  - **Context**: diagrama de context o descripció de les integracions amb sistemes externs
  - **Mòduls funcionals**: llista o descripció dels grans blocs funcionals

  ❌ Errors habituals:
  - Abast massa vague ("sistema de gestió d'expedients" sense especificar quins tipus)
  - Context sense mencionar sistemes externs o integracions
  - Manca de mòduls funcionals — no queda clar com s'organitza el sistema

  ### 2. Usuaris de la solució
  Ha d'incloure:
  - **Perfils d'usuari**: nom del rol i descripció breu
  - **Responsabilitats**: què pot fer cada perfil
  - **Accés**: si hi ha diferències de permisos entre perfils

  ❌ Errors habituals:
  - Llista de rols sense cap descripció de les seves responsabilitats
  - Manca del perfil d'administrador o gestor si el sistema en necessita
  - Confusió entre "usuari" (persona) i "sistema extern" (integració)

  ### 3. Requisits funcionals
  Ha d'incloure:
  - **Identificador únic** per requisit (p. ex. RF-001)
  - **Un requisit per ítem** — no agrupar múltiples comportaments
  - **Subjecte clar**: qui fa l'acció o quin sistema ha de fer-la
  - **Comportament verificable**: com es comprova que es compleix

  ❌ Errors habituals:
  - Requisits sense identificador (impossibles de traçar)
  - Un ítem amb múltiples requisits: "El sistema ha de fer X i també Y i permetre Z"
  - Requisits no verificables: "el sistema ha de ser intuïtiu", "ha de respondre ràpidament"
  - Manca de requisits de seguretat i de tractament de dades personals (RGPD)

  ### 4. Requisits no funcionals
  Ha d'incloure com a mínim:
  - **Rendiment**: temps de resposta esperats, càrrega concurrent
  - **Seguretat**: autenticació, autorització, xifratge, auditoria
  - **Disponibilitat**: SLA, finestres de manteniment

  ❌ Errors habituals:
  - Valors no quantificats: "ha de ser ràpid" (sense xifres), "alta disponibilitat" (sense percentatge)
  - Manca de requisits de seguretat tot i que el sistema tracti dades personals
  - Secció present però buida o amb text genèric copiat

  ### 5. Casos d'ús o fluxos funcionals
  Ha d'incloure per a cada cas d'ús:
  - **Actor principal**
  - **Precondicions**
  - **Flux principal** (passos numerats)
  - **Fluxos alternatius / d'error** (si escau)
  - **Postcondicions**

  ❌ Errors habituals:
  - Cas d'ús sense flux principal detallat (només títol)
  - Manca de fluxos d'error per a operacions crítiques (login, pagament, signatura)
  - Actor no identificat o genèric ("l'usuari" sense especificar quin perfil)

  ---

  ## Regla especial: Informació de suport (opcional)

  Aquesta secció **no es penalitza si és absent**.

  S'afegeix una nota ⚠️ informativa (sense deducció de punts) quan:
  - El document fa referència a entitats de dades sense definir-les
  - El document menciona pantalles o mockups sense que existeixin

  Si la secció **és present** però té problemes de qualitat, les penalitzacions s'apliquen al ritme de ⚠️ (−5) independentment de la gravetat (vegeu `criteris-qualitat.md`).

  Contingut recomanat quan és present:
  - Diccionari de dades o model d'entitats
  - Mockups o wireframes referenciats al document
  - Models analítics o càlculs complexos
  ```

- [ ] **Step 2: Verificar el contingut**

  Llegeix el fitxer i comprova:
  - Existeix una taula de seccions amb columna "Obligatòria"
  - Cada secció obligatòria té subsecció de "Requisits de contingut" i "Errors habituals"
  - La secció "Informació de suport" té la regla especial documentada
  - La columna "Avaluació" usa els símbols ✅/❌

- [ ] **Step 3: Commit**

  ```bash
  git add gencat/skills/gencat-documentacio-ctti/references/erq-estructura.md
  git commit -m "feat: gencat-documentacio-ctti — references/erq-estructura.md"
  ```

---

## Task 3: references/da-estructura.md

**Files:**
- Create: `gencat/skills/gencat-documentacio-ctti/references/da-estructura.md`

- [ ] **Step 1: Crear da-estructura.md**

  Crea `gencat/skills/gencat-documentacio-ctti/references/da-estructura.md`:

  ```markdown
  # Estructura DA — Descripció d'Arquitectura

  Font oficial (AiDA): https://canigo.ctti.gencat.cat/arquitectura/da/aida/

  ---

  ## Tipus d'arquitectura suportats

  Abans de validar, confirmar el tipus:
  - **Cloud Privat** — infraestructura CTTI gestionada
  - **Cloud Públic** — hyperscaler (Azure, AWS, GCP)
  - **SaaS** — solució de software com a servei
  - **Low Code** — plataformes low-code (Power Platform, Mendix, etc.)
  - **On-Premise** — infraestructura pròpia del departament

  Si el tipus no consta al document: preguntar: "Quin tipus d'arquitectura és? (Cloud Privat, Cloud Públic, SaaS, Low Code, On-Premise)"

  ---

  ## Matriu de vistes obligatòries per tipus

  | Vista | Cloud Privat | Cloud Públic | SaaS | Low Code | On-Premise |
  |-------|:-----------:|:------------:|:----:|:--------:|:----------:|
  | Context | ✓ | ✓ | ✓ | ✓ | ✓ |
  | Funcional | ✓ | ✓ | ✓ | ✓ | ✓ |
  | Informació | ✓ | ✓ | ✓ | ✓ | ✓ |
  | Concurrència | ✓ | ✓ | ✓ | ✓ | ✓ |
  | Desenvolupament | ✓ | ✓ | — | — | ✓ |
  | Desplegament | ✓ | ✓ | — | ✓ | ✓ |
  | Operacional | ✓ | ✓ | — | — | ✓ |

  **Low Code:** Desplegament és obligatòria perquè cal documentar les integracions i configuracions de la plataforma. Desenvolupament i Operacional no apliquen perquè la plataforma Low Code els gestiona transparentment.

  **SaaS:** Només les 4 vistes de base (Context, Funcional, Informació, Concurrència) — el proveïdor SaaS gestiona la resta.

  Avaluació: ✅ present amb contingut | ❌ absent/buida i obligatòria | N/A no aplica al tipus

  ---

  ## Requisits de contingut per vista

  ### Vista de Context
  Ha d'incloure:
  - Diagrama o descripció de les relacions del sistema amb actors externs i sistemes adjacents
  - Identificació dels sistemes d'integració (GICAR, PICA, e.notum, etc.)
  - Fluxos d'informació principals entre sistemes

  ❌ Errors habituals:
  - Diagrama sense llegenda o amb sistemes no identificats
  - Integracions mencionades al text però no reflectides al diagrama
  - Manca d'identificació dels protocols d'integració (REST, SOAP, missatgeria)

  ### Vista Funcional
  Ha d'incloure:
  - Descomposició del sistema en components o mòduls funcionals
  - Responsabilitats de cada component
  - Interaccions i dependències entre components

  ❌ Errors habituals:
  - Components sense responsabilitats definides
  - Manca de descripció de les interfícies entre components
  - Diagrama de components sense text explicatiu

  ### Vista d'Informació
  Ha d'incloure:
  - Model de dades principal (entitats i relacions)
  - Fluxos d'informació entre components
  - Polítiques de persistència i retenció de dades

  ❌ Errors habituals:
  - Model de dades sense atributs o tipus
  - Manca de referència al RGPD si es tracten dades personals
  - No s'especifica on es desen les dades (BD relacional, documental, fitxers...)

  ### Vista de Concurrència
  Ha d'incloure:
  - Processos i fils d'execució principals
  - Mecanismes de sincronització o cues de missatges
  - Gestió d'estats i transaccions

  ❌ Errors habituals:
  - Vista buida o amb text genèric ("el sistema és stateless") sense justificació
  - Manca de descripció de com es gestionen les concurrències crítiques
  - No s'esmenten cues o batches si el sistema en fa servir

  ### Vista de Desenvolupament
  *(No aplica a SaaS ni Low Code)*

  Ha d'incloure:
  - Stack tecnològic: llenguatges, frameworks, versions
  - Estructura de paquets o mòduls del codi
  - Dependències externes i llibreries principals
  - Alineació amb el full de ruta tecnològic del CTTI

  ❌ Errors habituals:
  - Tecnologies no alineades amb el full de ruta CTTI sense justificació
  - Versions no especificades (p. ex. "Java" sense indicar versió)
  - Manca d'estructura de paquets o repositoris

  ### Vista de Desplegament
  *(No aplica a SaaS)*

  Ha d'incloure:
  - Diagrama d'infraestructura: servidors, contenidors, xarxes
  - Entorns: desenvolupament, preproducció, producció
  - Estratègia de desplegament (CI/CD, blue-green, canary...)

  ❌ Errors habituals:
  - Diagrama d'infraestructura sense especificar mides/capacitats
  - Manca de descripció dels entorns pre-productius
  - No s'especifica com es fan els desplegaments (manual, automatitzat)

  ### Vista Operacional
  *(No aplica a SaaS ni Low Code)*

  Ha d'incloure:
  - Monitoratge i alertes: eines, mètriques clau
  - Còpies de seguretat: política, freqüència, retenció
  - Recuperació davant desastres (RTO/RPO)
  - Procediments d'operació habituals

  ❌ Errors habituals:
  - Manca de RTO/RPO per a sistemes crítics
  - Monitoratge sense especificar mètriques ni llindars d'alerta
  - No s'especifica qui és responsable de les operacions (equip CTTI, proveïdor, departament)
  ```

- [ ] **Step 2: Verificar el contingut**

  Llegeix el fitxer i comprova:
  - Existeix la taula de tipus d'arquitectura suportats
  - Existeix la matriu de vistes obligatòries (7 vistes × 5 tipus)
  - Cada vista té subsecció de contingut i errors habituals
  - Les vistes Desenvolupament, Desplegament i Operacional indiquen per a quins tipus no apliquen

- [ ] **Step 3: Commit**

  ```bash
  git add gencat/skills/gencat-documentacio-ctti/references/da-estructura.md
  git commit -m "feat: gencat-documentacio-ctti — references/da-estructura.md"
  ```

---

## Task 4: references/criteris-qualitat.md

**Files:**
- Create: `gencat/skills/gencat-documentacio-ctti/references/criteris-qualitat.md`

- [ ] **Step 1: Crear criteris-qualitat.md**

  Crea `gencat/skills/gencat-documentacio-ctti/references/criteris-qualitat.md`:

  ```markdown
  # Criteris de Qualitat — ERQ i DA

  Els 5 criteris s'avaluen **globalment** per al document sencer (no per secció ni vista).
  Cada criteri es puntua **una sola vegada**, independentment de quantes seccions el violin.

  **Seccions/vistes opcionals presents:** si la secció opcional existeix però té problemes, les
  penalitzacions s'apliquen sempre al ritme de ⚠️ (−5) independentment de la gravetat.

  ---

  ## 1. Claredat

  Avalua si la redacció és unívoca i interpretable per qualsevol membre de l'equip.

  | Estat | Criteri | Exemples |
  |-------|---------|---------|
  | ✅ | Tota la redacció té una sola interpretació possible | "El sistema denegarà l'accés i mostrarà el missatge ERR-401 si les credencials no són vàlides" |
  | ⚠️ | La redacció és confusa però interpretable amb esforç | "El sistema gestionarà els errors adequadament" |
  | ❌ | Redacció amb múltiples interpretacions possibles | "El sistema processarà les sol·licituds de forma òptima" (ERQ) / "L'arquitectura ha de ser flexible" (DA) |

  Preguntes de detecció:
  - Podrien dos developers implementar-ho de manera diferent llegint el mateix text?
  - Hi ha adjectius subjectius sense criteri mesurable? (ràpid, senzill, robust, escalable, flexible)

  ---

  ## 2. Detall suficient

  Avalua si el document té prou informació per implementar sense haver de prendre decisions de disseny no documentades.

  | Estat | Criteri | Exemples |
  |-------|---------|---------|
  | ✅ | Cada funcionalitat/vista té flux, condicions i resposta del sistema | Cas d'ús amb flux principal, fluxos d'error i postcondicions |
  | ⚠️ | Detall mínim però incomplet — cal inferir alguns comportaments | Cas d'ús amb flux principal però sense fluxos d'error |
  | ❌ | Falta informació essencial per implementar | Requisit "RF-012: Gestió d'usuaris" sense cap detall / Vista de Desplegament buida |

  Preguntes de detecció (ERQ):
  - Pot un developer implementar cada RF sense preguntar res?
  - Estan coberts els casos d'error i els límits de cada funcionalitat?

  Preguntes de detecció (DA):
  - Pot un arquitecte fer el disseny tècnic detallat a partir d'aquesta DA?
  - Estan justificades les decisions d'arquitectura clau?

  ---

  ## 3. Consistència

  Avalua la coherència interna del document: que no hi hagi contradiccions entre seccions/vistes.

  | Estat | Criteri | Exemples |
  |-------|---------|---------|
  | ✅ | Cap contradicció entre seccions; terminologia uniforme | El mateix concepte s'anomena igual a tot el document |
  | ⚠️ | Inconsistències menors de terminologia | "expedient" i "sol·licitud" usats per al mateix concepte |
  | ❌ | Contradicció directa entre seccions | RF-005 diu "l'usuari pot modificar" però el cas d'ús diu que és de "només lectura" / Vista Funcional descriu un component que no apareix a la Vista de Desplegament |

  Preguntes de detecció:
  - Hi ha termes que s'usen de manera diferent en seccions/vistes diferents?
  - Les entitats del model de dades (Informació) coincideixen amb les mencionades als RF o a la Vista Funcional?

  ---

  ## 4. Verificabilitat

  Avalua si cada requisit o decisió d'arquitectura es pot comprovar objectivament.

  | Estat | Criteri | Exemples |
  |-------|---------|---------|
  | ✅ | Criteri d'acceptació clar i mesurable | "Temps de resposta < 2 s per al 95% de les peticions amb càrrega de 100 usuaris simultanis" |
  | ⚠️ | Criteri poc precís però parcialment mesurable | "Temps de resposta acceptable en condicions normals d'ús" |
  | ❌ | No és comprovable | "El sistema ha de ser ràpid i fàcil d'usar" / "L'arquitectura ha de ser escalable" |

  Paraules de risc (probable ❌ si no s'acompanyen de xifres):
  - ràpid, lent, eficient, òptim, escalable, robust, flexible, segur, fàcil, intuïtiu, modern

  ---

  ## 5. Traçabilitat

  Avalua si es pot seguir l'origen de cada requisit o decisió fins a una necessitat de negoci documentada.

  | Estat | Criteri | Exemples |
  |-------|---------|---------|
  | ✅ | Cada RF/vista referencia el seu origen (necessitat de negoci, normativa, cas d'ús) | "RF-015 [origen: requeriment legal RGPD art. 17]" |
  | ⚠️ | Traçabilitat parcial — alguns RF o decisions sense origen documentat | La majoria de RF tenen origen però uns quants no |
  | ❌ | Cap referència a l'origen de cap requisit o decisió | Document que llista RF numerats sense cap referència a objectius de negoci o normativa |

  Preguntes de detecció:
  - Si un stakeholder demana "per què tenim aquest requisit?", pot el document respondre-ho?
  - Les decisions d'arquitectura clau (DA) justifiquen per què s'ha triat una solució sobre les alternatives?
  ```

- [ ] **Step 2: Verificar el contingut**

  Llegeix el fitxer i comprova:
  - Existeixen els 5 criteris com a seccions separades
  - Cada criteri té una taula amb ✅/⚠️/❌ i exemples concrets
  - Els exemples cobreixen tant ERQ com DA
  - Hi ha la nota sobre seccions opcionals a l'encapçalament

- [ ] **Step 3: Commit**

  ```bash
  git add gencat/skills/gencat-documentacio-ctti/references/criteris-qualitat.md
  git commit -m "feat: gencat-documentacio-ctti — references/criteris-qualitat.md"
  ```

---

## Task 5: references/puntuacio-i-informe.md

**Files:**
- Create: `gencat/skills/gencat-documentacio-ctti/references/puntuacio-i-informe.md`

- [ ] **Step 1: Crear puntuacio-i-informe.md**

  Crea `gencat/skills/gencat-documentacio-ctti/references/puntuacio-i-informe.md`:

  ```markdown
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
  ```

- [ ] **Step 2: Verificar el contingut**

  Llegeix el fitxer i comprova:
  - La taula de fórmula inclou el floor a 0 i el llindar ≥80
  - Hi ha 4 exemples de càlcul (2 ERQ + 2 DA)
  - La plantilla d'informe usa les seccions correctes: Puntuació global, Nivell 1, Nivell 2, Preguntes obertes, Resum executiu
  - La plantilla indica quan ometre seccions ("Ometre si...")

- [ ] **Step 3: Commit**

  ```bash
  git add gencat/skills/gencat-documentacio-ctti/references/puntuacio-i-informe.md
  git commit -m "feat: gencat-documentacio-ctti — references/puntuacio-i-informe.md"
  ```

---

## Task 6: Actualitzar gencat/README.md

**Files:**
- Modify: `gencat/README.md`

- [ ] **Step 1: Llegir l'estat actual del README**

  Llegeix `gencat/README.md` i identifica:
  - La línia de la llista de navegació on s'ha d'afegir `gencat-documentacio-ctti`
  - La fila de la taula on s'ha d'afegir

- [ ] **Step 2: Afegir a la llista de navegació**

  Afegeix `- [gencat-documentacio-ctti](#gencat-documentacio-ctti)` a la llista de navegació, en ordre alfabètic respecte als altres skills.

- [ ] **Step 3: Afegir a la taula de skills**

  Afegeix aquesta fila a la taula:

  ```markdown
  | <a name="gencat-documentacio-ctti"></a>`gencat-documentacio-ctti` | Documentació Tècnica CTTI — valida i orienta sobre ERQ (Especificació de Requisits) i DA (Descripció d'Arquitectura) |
  ```

- [ ] **Step 4: Afegir a la secció de Documentació oficial**

  Afegeix aquestes línies a la secció de Documentació oficial:

  ```markdown
  - Especificació de Requisits (ERQ): https://qualitat.solucions.gencat.cat/procediments/analisi-disseny/especificacio_requisits/
  - Descripció d'Arquitectura (DA / AiDA): https://canigo.ctti.gencat.cat/arquitectura/da/aida/
  ```

- [ ] **Step 5: Verificar el README**

  Llegeix `gencat/README.md` i comprova que:
  - `gencat-documentacio-ctti` apareix a la llista de navegació
  - `gencat-documentacio-ctti` apareix a la taula amb la descripció correcta
  - L'anchor `#gencat-documentacio-ctti` de la llista apunta correctament a la taula
  - Les dues URLs de Documentació oficial (ERQ i AiDA) apareixen a la secció corresponent

- [ ] **Step 6: Commit**

  ```bash
  git add gencat/README.md
  git commit -m "docs: afegeix gencat-documentacio-ctti al README del marketplace"
  ```

---

## Task 7: Verificació final de l'skill

- [ ] **Step 1: Verificar l'estructura de fitxers completa**

  Comprova que existeixen exactament aquests fitxers:
  ```
  gencat/skills/gencat-documentacio-ctti/SKILL.md
  gencat/skills/gencat-documentacio-ctti/references/erq-estructura.md
  gencat/skills/gencat-documentacio-ctti/references/da-estructura.md
  gencat/skills/gencat-documentacio-ctti/references/criteris-qualitat.md
  gencat/skills/gencat-documentacio-ctti/references/puntuacio-i-informe.md
  ```

- [ ] **Step 2: Verificar coherència entre fitxers**

  Comprova:
  - El nom i el nombre de seccions de `erq-estructura.md` corresponen als ítems del checklist de `SKILL.md` (el SKILL.md no reprodueix la llista de seccions, però el seu checklist ha de reflectir el nombre correcte)
  - Les 7 vistes DA de `SKILL.md` coincideixen amb les de `da-estructura.md`
  - La matriu de vistes de `SKILL.md` coincideix amb la de `da-estructura.md`
  - El llindar ≥80 de `SKILL.md` (checklist) coincideix amb `puntuacio-i-informe.md`
  - Els 5 criteris de `SKILL.md` (checklist) coincideixen amb `criteris-qualitat.md`

- [ ] **Step 3: Verificar que el SKILL.md no descriu el contingut dels references**

  El `SKILL.md` ha d'orquestrar (quan carregar quin fitxer) però NO duplicar el contingut dels references. Si hi ha contingut duplicat, eliminar-lo del SKILL.md i deixar-lo als references.

- [ ] **Step 4: Commit final si cal**

  Si s'han fet correccions:
  ```bash
  git add gencat/skills/gencat-documentacio-ctti/
  git commit -m "fix: gencat-documentacio-ctti — coherència entre SKILL.md i references"
  ```
