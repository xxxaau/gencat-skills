# gencat-identitat-corporativa — Spec de disseny

**Data:** 2026-03-20
**Estat:** Aprovat per l'usuari
**Audiència del skill:** Comunicadors i dissenyadors de la Generalitat de Catalunya

---

## Resum

Nou skill `gencat-identitat-corporativa` per al plugin `gencat`. Permet als comunicadors i dissenyadors aplicar correctament la identitat corporativa de la Generalitat de Catalunya en documents, presentacions i comunicació digital. Ofereix dos modes: **CONSULTAR/CREAR** (referència i generació de contingut) i **VALIDAR** (auditoria d'un document o imatge contra les normes de marca).

---

## Cas d'ús

Un comunicador o dissenyador que treballa en documents institucionals (Word, PowerPoint, PDF), comunicació digital (signatura de correu, newsletters) o material de comunicació necessita saber com aplicar la marca Gencat correctament sense consultar el portal cada vegada. Opcionalment, pot enviar una captura de pantalla i/o fitxer (o text enganxat) per obtenir una auditoria del compliment normatiu.

---

## Fitxers afectats

| Fitxer | Acció | Descripció |
|--------|-------|------------|
| `gencat/skills/gencat-identitat-corporativa/SKILL.md` | Crear | Frontmatter, triggers, detecció de mode i instruccions de càrrega de referències |
| `gencat/skills/gencat-identitat-corporativa/references/marca-visual.md` | Crear | Colors (hex/RGB/CMYK/Pantone), tipografia per suport (font canònica), normes del senyal i logotip |
| `gencat/skills/gencat-identitat-corporativa/references/documents.md` | Crear | Normes per a Word, PowerPoint, PDF, cartes, formularis, certificats (referència `marca-visual.md` per a valors de tipografia i color) |
| `gencat/skills/gencat-identitat-corporativa/references/comunicacio-digital.md` | Crear | Signatura de correu (3 variants, valors exactes), newsletters, codis QR |
| `gencat/skills/gencat-identitat-corporativa/references/validacio.md` | Crear | Workflow del mode VALIDAR: criteris visuals i de contingut, puntuació, format d'informe |
| `gencat/README.md` | Modificar | Afegir el nou skill a la taula i a la secció de documentació oficial |

---

## SKILL.md — Disseny

### Frontmatter

```yaml
---
name: gencat-identitat-corporativa
description: "Aplica les normes d'identitat corporativa de la Generalitat de Catalunya quan creïs o validis documents, presentacions, signatures de correu o qualsevol material de comunicació institucional. Usa aquesta skill quan l'usuari treballi amb la marca Gencat fora del web: documents Word, presentacions PowerPoint, PDFs, cartes oficials, formularis, newsletters o signatures de correu. Activa-la quan mencioni 'identitat corporativa', 'marca gencat', 'logotip generalitat', 'colors corporatius', 'tipografia corporativa gencat', 'signatura correu corporativa', 'presentació corporativa', 'document oficial gencat', 'Open Sans gencat', 'Helvetica Neue gencat', o demani crear o validar material institucional de la Generalitat. Activa-la també en mode VALIDAR quan l'usuari enviï una imatge o fitxer per comprovar el compliment de la marca."
---
```

*Nota: els triggers de tipografia inclouen sempre el context "gencat" per evitar falsos positius amb mencions genèriques de les fonts.*

### Detecció de mode

| Situació | Mode |
|----------|------|
| Pregunta de referència ("quin color...?", "quina tipografia...?") | CONSULTAR |
| Petició de creació ("redacta una signatura", "crea una plantilla") | CREAR |
| Imatge o fitxer adjunt / ruta de fitxer / text enganxat per revisar | VALIDAR |
| Dubte | Preguntar: "Vols crear contingut nou o validar un material existent?" |

### Càrrega de referències

- Consulta sobre colors, tipografia o logotip → carregar `references/marca-visual.md`
- Consulta sobre documents, presentacions, PDFs → carregar `references/documents.md`
- Consulta sobre signatura de correu, newsletters → carregar `references/comunicacio-digital.md`
- Mode VALIDAR → carregar `references/validacio.md` + el fitxer de referència corresponent al tipus de material; si el tipus no és identificable, preguntar: "De quin tipus de material es tracta? (document Word/PowerPoint, signatura de correu, PDF...)"

---

## references/marca-visual.md — Contingut (font canònica)

Aquest fitxer és la **font canònica** per a colors i tipografia. Els altres fitxers de referència no repeteixen els valors: fan referència explícita a `marca-visual.md`.

### Colors corporatius

| Color | Pantone | CMYK | RGB | Hex | RAL |
|-------|---------|------|-----|-----|-----|
| Vermell (principal) | 485 | 0/100/91/0 | 192/0/0 | #C00000 | 3020 |
| Negre | Process Black | — | 0/0/0 | #000000 | — |
| Blanc | — | — | 255/255/255 | #FFFFFF | — |
| Groc (ús específic) | 109 | — | — | #FFD100 | — |
| Or (ús específic) | 871 | — | — | #857040 | — |

Regla: el vermell és l'únic color corporatiu principal. Blanc i negre proporcionen contrast. Groc i or s'usen només en aplicacions específiques.

### Tipografia per suport

| Suport | Tipografia | Notes |
|--------|-----------|-------|
| Corporativa (logotip) | Helvetica Neue 75 Bold / 45 Light | Llicència de pagament |
| Documents Office (Word, PowerPoint, formularis) | Arial / Arial Bold | Gratuïta, substitut oficial |
| Digital (web, newsletters, infografies, vídeo) | Open Sans | Preferida per legibilitat en pantalla |
| Signatura de correu electrònic | Arial | **Excepció tècnica:** la signatura s'ha de renderitzar al client de correu del receptor, que no té accés a fonts web. Arial és una font del sistema disponible a tots els SO. Open Sans **no** s'ha d'usar a signatures de correu. |
| ❌ Prohibida | Calibri | No és tipografia corporativa |

### Normes del senyal i logotip

- **Mida mínima:** 4,7 mm d'alçada
- **Colors permesos:** vermell (#C00000) o negre (#000000); versió 3 colors només en casos específics
- **Espai de seguretat:** no superposar text ni elements sobre el senyal
- **Prohibit:** distorsionar, estirar, comprimir o canviar les proporcions
- **Escriptura correcta:** "Generalitat de Catalunya" (G i C en majúscula, la resta en minúscula)
- **Regla clau:** en comunicacions adreçades a la ciutadania, usar el logotip de la Generalitat, NO el departamental

---

## references/documents.md — Contingut

Per als valors de tipografia i color, consultar `references/marca-visual.md` (font canònica).

Normes d'aplicació per suport:

- **Word / cartes oficials:** Arial (veure `marca-visual.md`); capçalera amb el senyal corporatiu a mida mínima; colors corporatius per a títols i separadors
- **PowerPoint / presentacions:** Arial (veure `marca-visual.md`); vermell corporatiu per a elements destacats; fons blanc o negre preferentment; senyal a la portada i al peu de cada diapositiva
- **PDF / publicacions digitals:** Open Sans (veure `marca-visual.md`); estructura amb espai per al senyal a la coberta
- **Formularis:** Arial; capçalera amb senyal corporatiu
- **Certificats i diplomes:** seguir la plantilla oficial disponible al portal d'identitat corporativa

---

## references/comunicacio-digital.md — Contingut

Per als valors de tipografia i color, consultar `references/marca-visual.md` (font canònica).

### Signatura de correu electrònic

**Estructura (ordre obligatori):**
1. Cos del missatge
2. Dades personals (nom, càrrec, unitat, departament)
3. Imatge d'identificació bàsica (opcional)
4. Clàusula legal
5. Avís d'impressió (opcional)

**Especificacions tècniques:**
- Font: Arial (Arial Bold per a èmfasi) — veure `marca-visual.md`
- Fons: blanc
- Text: negre
- Enllaços (email/web): blau RGB 0,0,255
- Text legal: gris RGB 111,111,111
- Resolució imatge: 96 dpi
- Alçada senyal: 8,1 mm
- Alçada icones xarxes socials: màx. 15 px; color gris RGB 153,153,153

**3 variants:**
1. Sense imatge (text only) — per a correus lleugers
2. Amb identificació bàsica de la Generalitat
3. Amb identificació pròpia — per a organismes autònoms (logotip propi + senyal Generalitat)

**Clàusula legal disponible en:** català, castellà, anglès, francès, alemany i occità.

---

## references/validacio.md — Contingut

### Mode VALIDAR — Workflow

**Input acceptat i mecanisme:**

| Input | Com l'aporta l'usuari | Valida |
|-------|----------------------|--------|
| Imatge (captura de pantalla) | Adjunt a la conversa | Colors, logotip, tipografia aparent, composició |
| Fitxer PDF | Ruta de fitxer local (Claude usa `Read`) o adjunt | Estructura, elements obligatoris, clàusules |
| Fitxer .docx/.pptx | Ruta de fitxer local (Claude usa `Read` sobre el XML intern) | Estructura i elements obligatoris |
| Text enganxat | Text directament a la conversa | Contingut textual, elements obligatoris |
| Combinació imatge + fitxer/text | Ambdós en la mateixa conversa | Validació completa visual + contingut |

**Pas 0 — Identificació del material:**
- Detectar el tipus de material (document, presentació, signatura de correu...) a partir de l'input rebut
- Si el tipus no és identificable: preguntar "De quin tipus de material es tracta? (document Word/PowerPoint, signatura de correu, PDF...)"
- Carregar `references/validacio.md` + el fitxer de referència del tipus detectat

**Pas 1 — Validació visual (si hi ha imatge):**
- Color dominant: és el vermell #C00000 el corporatiu?
- Logotip: present? No distorsionat? Mida aparentment ≥ 4,7mm?
- Tipografia visible: sembla Arial/Helvetica Neue/Open Sans? (no Calibri ni altres)
- Composició: espai de seguretat respectat al voltant del logotip?

**Pas 2 — Validació de contingut (si hi ha fitxer o text):**
- Estructura del document: conté els elements obligatoris per al tipus de suport?
- Per a signatura de correu: tots els camps presents i en l'ordre correcte?
- Clàusula legal: present i en la llengua correcta?

### Taula de criteris de validació

| Element | ❌ Error | ⚠️ Millora |
|---------|---------|-----------|
| **Color** | Ús d'un color no corporatiu com a color principal | Ús excessiu de groc o or fora del context específic |
| **Logotip** | Absent en comunicació a la ciutadania · distorsionat · mida inferior a 4,7mm · logotip departamental en lloc del de la Generalitat | Posicionament no òptim |
| **Tipografia** | Ús de Calibri · ús de Helvetica Neue sense llicència en documents Office | Arial en lloc d'Open Sans per a publicacions digitals |
| **Estructura** | Elements obligatoris absents (clàusula legal en signatura, senyal en capçalera...) | Ordre incorrecte dels elements |
| **Composició** | Text o elements sobre el senyal (espai de seguretat no respectat) | — (no hi ha millores parcials: o es respecta o no) |

### Puntuació global

```
Puntuació = (elements sense ❌) / (total elements avaluats) × 10
```

> **Nota:** El total d'elements avaluats depèn de l'input rebut (imatge sola: 4 elements visuals; fitxer/text sol: elements d'estructura; combinació: fins a 5 elements). La prioritat es determina pel rang numèric, no pel recompte absolut d'errors.

| Puntuació | Prioritat | Descripció |
|-----------|-----------|------------|
| 8–10 | BAIXA | Sense errors; possibles millores menors |
| 5–7 | MITJANA | Compliment parcial; errors en elements no crítics |
| 0–4 | ALTA | Errors greus en elements fonamentals (logotip, color principal, estructura) |

### Format de l'informe

**Capa 1 — Avaluació per element:**
```
## [Nom de l'element]
✅ Correcte — [justificació]
⚠️ Millora recomanada — [descripció]
❌ Error — [descripció i norma incomplerta]
```

**Capa 2 — Puntuació global:**
```
Puntuació: X/10
Elements correctes: N | Millores: N | Errors: N
Prioritat de revisió: ALTA / MITJANA / BAIXA
```

**Capa 3 — Proposta de correcció:**
Només per als elements amb ⚠️ o ❌:
```
### [Element] — Proposta
[Descripció concreta del canvi correctiu amb els valors correctes]
```

### Gestió de múltiples materials

| Situació | Acció |
|----------|-------|
| ≤ 3 materials | Processar en paral·lel → informe consolidat al final |
| > 3 materials | Processar un a un → resum parcial entre cada material → informe consolidat al final |
| Material no identificable | Preguntar el tipus abans de processar |

---

## Decisions de disseny

| Decisió | Raó |
|---------|-----|
| Skill independent (no fusionat amb `gencat-design-system`) | Audiència diferent: comunicadors vs. developers. Contingut diferent: marca aplicada vs. implementació en codi |
| 3 fitxers de referència per suport + 1 de validació | Consistent amb el patró dels altres skills gencat; cada fitxer s'actualitza de forma independent |
| `marca-visual.md` com a font canònica per a colors i tipografia | Evita duplicació de valors entre fitxers i garanteix consistència en actualitzacions futures |
| Mode VALIDAR amb doble canal (imatge + fitxer/text) | La imatge valida elements visuals; el fitxer/text valida contingut i estructura. Compatibles amb les capacitats de Claude (multimodal + `Read`) |
| Triggers de tipografia amb context "gencat" | Evita falsos positius amb mencions genèriques de fonts com "Arial" o "Open Sans" en contextos no-Gencat |
| Exclusió d'identitat verbal | Treballar-ho en una iteració futura com a skill propi o extensió d'aquest |
| Exclusió de suports físics (vehicles, estands, senyalística) | Claude no interactuarà mai amb aquests contextos; afegir-los inflaria el skill sense valor real |
| Exclusió de noves marques pròpies | Cas d'ús molt específic i poc freqüent; es pot afegir com a extensió futura |
