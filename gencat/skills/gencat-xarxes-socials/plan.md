# gencat-xarxes-socials Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Crear el skill `gencat-xarxes-socials` que aplica la Guia de Xarxes Socials de la Generalitat de Catalunya per generar i revisar contingut per a 7 plataformes.

**Architecture:** Un `SKILL.md` central amb workflow dual (GENERAR / REVISAR) + un fitxer de referència per xarxa social + un fitxer de plantilles reutilitzables. Les normes transversals (accessibilitat, llengua, to) viuen al `SKILL.md`; les normes específiques de cada plataforma, als fitxers `references/`.

**Tech Stack:** Markdown pur. Cap codi. Font de veritat: https://atenciociutadana.gencat.cat/web/.content/manuals/xarxes/guia_xarxa.pdf

---

> **Nota per a l'implementador:** La guia oficial (PDF) no és accessible directament per la seva codificació binària. El contingut de cada fitxer `references/` s'ha de basar en: (1) els límits tècnics oficials de cada plataforma (2026), (2) les normes d'estil Gencat documentades als skills `gencat-comunicacio-clara` i `gencat-tramits`, i (3) la guia PDF si s'aconsegueix accés. Quan un límit o norma sigui incert, marcar-lo amb `<!-- VERIFICAR amb guia PDF -->`.

---

## Mapa de fitxers

| Fitxer | Acció | Responsabilitat |
|--------|-------|----------------|
| `gencat/skills/gencat-xarxes-socials/SKILL.md` | Crear | Frontmatter, detecció de mode, normes transversals, workflows, checklist |
| `gencat/skills/gencat-xarxes-socials/references/x-twitter.md` | Crear | Normes específiques de X (Twitter) |
| `gencat/skills/gencat-xarxes-socials/references/facebook.md` | Crear | Normes específiques de Facebook |
| `gencat/skills/gencat-xarxes-socials/references/instagram.md` | Crear | Normes específiques d'Instagram |
| `gencat/skills/gencat-xarxes-socials/references/linkedin.md` | Crear | Normes específiques de LinkedIn |
| `gencat/skills/gencat-xarxes-socials/references/youtube.md` | Crear | Normes específiques de YouTube (elements textuals) |
| `gencat/skills/gencat-xarxes-socials/references/threads.md` | Crear | Normes específiques de Threads |
| `gencat/skills/gencat-xarxes-socials/references/tiktok.md` | Crear | Normes específiques de TikTok (elements textuals) |
| `gencat/skills/gencat-xarxes-socials/references/plantilles.md` | Crear | 6 plantilles reutilitzables per tipus de contingut |
| `gencat/README.md` | Modificar | Afegir entrada del nou skill a la taula |
| `gencat/package.json` | Modificar | Incrementar versió si escau |

---

## Task 1: SKILL.md

**Fitxers:**
- Crear: `gencat/skills/gencat-xarxes-socials/SKILL.md`

- [ ] **Pas 1: Crea el fitxer SKILL.md**

El fitxer ha de tenir exactament aquesta estructura (en ordre):

```markdown
---
name: gencat-xarxes-socials
description: "Aplica la Guia de Xarxes Socials de la Generalitat de Catalunya quan generis, revisis o adaptis contingut per a plataformes digitals. Usa aquesta skill sempre que l'usuari treballi amb publicacions a X (Twitter), Facebook, Instagram, LinkedIn, YouTube, Threads o TikTok en el context de comunicació institucional de la Generalitat. Activa-la també quan mencioni 'post', 'publicació', 'hashtag', 'tweet', 'fil', 'thread', 'reel', 'story', 'contingut digital', 'xarxa social', o demani adaptar un comunicat, nota de premsa o tràmit per a xarxes socials."
---

# Xarxes Socials — Generalitat de Catalunya

Font oficial: https://atenciociutadana.gencat.cat/web/.content/manuals/xarxes/guia_xarxa.pdf

---

## Detecció del mode

- **Text existent proporcionat** → mode REVISAR (revisar i proposar versió corregida)
- **Sense text** → mode GENERAR
- **"Millora" o "adapta" + text** → mode REVISAR amb proposta de nova versió
- **Dubte** → preguntar: "Vols que generi un post nou o que revisi un text que ja tens?"

---

## Normes transversals

### Llengua
- **Català per defecte**
- Castellà només si la xarxa o la campanya ho requereix explícitament

### To
- Institucional però proper, mai burocràtic
- Veu activa, frases curtes
- Primera persona del plural per referir-se a la Generalitat ("us informem", "us convoquem")

### Accessibilitat [OBLIGATORI]
- Alt text descriptiu per a totes les imatges (màx. 125 caràcters)
- Hashtags en **CamelCase**: `#GeneralitatDeCatalunya`, mai `#generalitat de catalunya`
- Evitar emojis consecutius (dificulten els lectors de pantalla)
- Evitar emojis com a substituts de paraules

### Sigles
- Desplegar la primera vegada: "idCAT Mòbil (identificació digital)"

### Contingut sensible
- Temes de salut, menors o violència: afegir avís al post generat → "⚠️ Revisió humana recomanada abans de publicar"
- Plantilla "Emergència / alerta" (PROCICAT, METEOCAT): excepció, és contingut planificat

---

## Workflow — Mode GENERAR

1. Si no s'especifica la xarxa → preguntar abans de fer res
2. Llegir `references/<xarxa>.md` (límits, normes, exemples)
3. Si no s'indica el to → preguntar: informatiu / divulgatiu / d'urgència / de campanya
4. Generar respectant: límit de caràcters, nombre màxim de hashtags, to corporatiu, accessibilitat
5. Oferir adaptació a altres xarxes si escau
6. Mostrar la checklist de verificació de la plataforma (del fitxer `references/<xarxa>.md`)

---

## Workflow — Mode REVISAR

1. Identificar la xarxa (o preguntar)
2. Llegir `references/<xarxa>.md`
3. Verificar cada norma (les **obligatòries** estan marcades al fitxer de xarxa)
4. Informe:
   - ✅ Correcte
   - ⚠️ Recomanació no seguida — proposta de millora
   - ❌ Norma obligatòria incomplerta — cal corregir abans de publicar
5. Oferir versió corregida si hi ha algun ❌

> **Criteri:** ❌ = límit tècnic (caràcters, hashtags màxims) o accessibilitat. ⚠️ = estil o to.

---

## Plantilles

Llegeix `references/plantilles.md` per a estructures reutilitzables: avís, convocatòria, emergència, campanya, resposta a comentari, fil/thread.

---

## Llista de verificació ràpida

- [ ] Xarxa objectiu identificada?
- [ ] Límit de caràcters respectat?
- [ ] Hashtags en CamelCase i al final?
- [ ] Nombre de hashtags dins del màxim de la plataforma?
- [ ] To proper, veu activa, sense burocratisme?
- [ ] Imatges amb alt text descriptiu?
- [ ] Emojis sense substituir paraules ni en seqüències?
- [ ] Sigles desplegades la primera vegada?
- [ ] Contingut en català (o castellà si la campanya ho requereix)?
```

- [ ] **Pas 2: Verifica l'estructura**

Comprova:
- El frontmatter té `name` i `description` exactes de la spec
- Les seccions apareixen en ordre: Detecció → Normes → Workflow GENERAR → Workflow REVISAR → Plantilles → Checklist
- Les normes d'accessibilitat estan marcades com `[OBLIGATORI]`

- [ ] **Pas 3: Commit**

```bash
git add gencat/skills/gencat-xarxes-socials/SKILL.md
git commit -m "feat: skill gencat-xarxes-socials — SKILL.md"
```

---

## Task 2: references/x-twitter.md

**Fitxers:**
- Crear: `gencat/skills/gencat-xarxes-socials/references/x-twitter.md`

- [ ] **Pas 1: Crea el fitxer**

Estructura obligatòria per a tots els fitxers de xarxa (adapta els valors a X):

```markdown
# X (Twitter) — Normes Gencat

## Límits tècnics [OBLIGATORI]

| Element | Límit |
|---------|-------|
| Post | 280 caràcters |
| Post llarg (X Premium) | 25.000 caràcters |
| Bio | 160 caràcters |
| Nom de perfil | 50 caràcters |
| URL acortada | compta com 23 caràcters |

## Hashtags [OBLIGATORI: màxim 2]

- **Màxim 2 hashtags per post** — més redueix l'abast orgànic
- **Posició: al final** del text, mai intercalats
- **Format CamelCase**: `#FocsMediterrani`, `#AjutsGeneralitat`
- Evitar hashtags genèrics sense valor informatiu (`#Catalunya`, `#Gencat` sols)

## Emojis [RECOMANAT]

- Màxim 2-3 per post
- Posició: al principi de línia o al final de frase, mai al mig de text
- Mai substituir paraules per emojis
- Mai dos o més emojis consecutius

## To i estil

- **Directe i concís**: una idea per post
- **Informatiu**: dades concretes, dates, xifres
- Evitar retòrica política o valors absoluts ("el millor", "únic", "imprescindible")
- Frases curtes (X penalitza el text dens)
- Preguntes retòriques: amb moderació

## Formats recomanats

| Format | Ús recomanat |
|--------|-------------|
| Text | Notícies breus, cites, dades |
| Imatge (1200×675 px) | Contingut visual que requereix context |
| Fil (thread) | Temes complexos, passos, llistes llargues |
| Vídeo (màx. 2:20 min) | Campanya, explicació visual |
| Enquesta | Participació ciutadana, consultes |

## Tipus de contingut recomanat

- Notícies i avisos de servei
- Dades i estadístiques rellevants
- Enllaços a tràmits oberts
- Respostes ràpides a dubtes freqüents (via fils)
- Emergències i alertes (format especial, veure plantilles)

## Evitar

- ❌ Posts de més de 280 caràcters sense justificació (usar fil)
- ❌ Més de 2 hashtags
- ❌ Majúscules excessives (sembla crit)
- ❌ Sigles sense desplegar la primera vegada
- ❌ Ironies o humor que pugui malinterpretar-se
- ❌ Retuitear sense comentari crític propi

## Accessibilitat [OBLIGATORI]

- Alt text a totes les imatges (X permet fins a 1.000 caràcters)
- Subtítols als vídeos
- Hashtags en CamelCase (obligatori)
- Evitar text incrustrat a imatges (no llegible per lectors de pantalla)

## Exemple bo ✅

```
Ja pots consultar el calendari de vacunació 2026 al web de Salut.

Data límit per demanar cita: 31 de març.

➡️ [enllaç]

#SalutCatalunya
```
*Per què funciona: concís, data clara, un hashtag, CTA evident, emoji posicionat correctament.*

## Exemple dolent ❌

```
🚨🚨 ATENCIÓ!! El DEPARTAMENT DE SALUT DE LA GENERALITAT DE CATALUNYA comunica que el CALENDARI DE VACUNACIÓ per a l'any 2026 ja es troba disponible a la seva pàgina web oficial!! No t'oblidis de demanar cita!! #salut #vacunació #Catalunya #Gencat #2026 #salutpública
```
*Errors: excés d'emojis, majúscules innecessàries, hashtags en minúscules, 6 hashtags, to alarmista.*

## Checklist X (Twitter)

- [ ] El text té 280 caràcters o menys (o és un fil justificat)?
- [ ] Màxim 2 hashtags, en CamelCase i al final?
- [ ] Emojis (si n'hi ha) posicionats correctament i sense seqüències?
- [ ] Alt text afegit a la imatge (si n'hi ha)?
- [ ] Les sigles estan desplegades?
- [ ] El to és directe i informatiu, sense majúscules innecessàries?
- [ ] Hi ha una crida a l'acció clara (CTA) si el post ho requereix?
```

- [ ] **Pas 2: Verifica**

Comprova que el fitxer té totes les seccions de l'estructura tipus de la spec:
Límits · Hashtags · Emojis · To i estil · Formats · Tipus de contingut · Evitar · Accessibilitat · Exemple bo · Exemple dolent · Checklist

- [ ] **Pas 3: Commit**

```bash
git add gencat/skills/gencat-xarxes-socials/references/x-twitter.md
git commit -m "feat: skill gencat-xarxes-socials — references/x-twitter"
```

---

## Task 3: references/facebook.md

**Fitxers:**
- Crear: `gencat/skills/gencat-xarxes-socials/references/facebook.md`

- [ ] **Pas 1: Crea el fitxer**

Segueix l'estructura exacta del Task 2 adaptada a Facebook. Valors clau:

| Element | Valor |
|---------|-------|
| Post | 63.206 caràcters màxim tècnic; recomanat < 400 |
| Hashtags màxims | 3 (recomanat) |
| Imatge recomanada | 1200×630 px |
| Formats clau | Post de text, imatge, vídeo, carrusel, event, story |
| To | Proper i explicatiu, més llarg que X, admet context |
| Particularitat | Facebook penalitza posts amb masses hashtags i links a primera línia |

Exemple bo: post amb context (2-3 frases), una imatge, 1-2 hashtags al final, CTA clar.
Exemple dolent: post copiat de nota de premsa sense adaptar, ple de tecnicismes.

- [ ] **Pas 2: Verifica estructura completa** (igual que Task 2, pas 2)

- [ ] **Pas 3: Commit**

```bash
git add gencat/skills/gencat-xarxes-socials/references/facebook.md
git commit -m "feat: skill gencat-xarxes-socials — references/facebook"
```

---

## Task 4: references/instagram.md

**Fitxers:**
- Crear: `gencat/skills/gencat-xarxes-socials/references/instagram.md`

- [ ] **Pas 1: Crea el fitxer**

Valors clau per Instagram:

| Element | Valor |
|---------|-------|
| Caption post | 2.200 caràcters màxim; recomanat < 300 visible (la resta queda "veure més") |
| Hashtags | Màxim 30 tècnic; **recomanat 5-10 rellevants** |
| Story (text) | Limitat per espai visual; recomanat < 100 caràcters |
| Reels (descripció) | 2.200 caràcters; recomanat < 150 |
| Imatge feed | 1080×1080 px (quadrat) o 1080×1350 px (portrait) |
| Formats clau | Post imatge/vídeo, carrusel, story, reel |
| To | Visual i proper; el text complementa la imatge, no la repeteix |
| Particularitat | Links no funcionen al caption (usar "link a la bio" o link sticker a stories) |

Abast del skill: posts (caption), stories (text), reels (descripció), captions.

Exemple bo: caption breu que complementa la imatge, hashtags rellevants al final o en comentari.
Exemple dolent: caption que descriu literalment la imatge, 20+ hashtags genèrics.

- [ ] **Pas 2: Verifica estructura completa**

- [ ] **Pas 3: Commit**

```bash
git add gencat/skills/gencat-xarxes-socials/references/instagram.md
git commit -m "feat: skill gencat-xarxes-socials — references/instagram"
```

---

## Task 5: references/linkedin.md

**Fitxers:**
- Crear: `gencat/skills/gencat-xarxes-socials/references/linkedin.md`

- [ ] **Pas 1: Crea el fitxer**

Valors clau per LinkedIn:

| Element | Valor |
|---------|-------|
| Post | 3.000 caràcters màxim; recomanat 1.300 (la resta queda "veure més") |
| Article (títol) | 100 caràcters |
| Article (cos) | 110.000 caràcters |
| Hashtags | **Màxim 3-5**, sempre al final |
| To | Més formal que Instagram/X; professional, analític, constructiu |
| Formats clau | Text, imatge, document (PDF carrusel), vídeo, article, enquesta |
| Particularitat | LinkedIn premia posts que generen comentaris; fer preguntes al final ajuda |

Abast del skill: posts, articles (títol + introducció), respostes a comentaris.

To de resposta a comentaris: formal i resolutiu, primera persona plural.

Exemple bo: post que aporta dades + reflexió breu + pregunta al final + 3 hashtags.
Exemple dolent: post que sembla una nota de premsa copiada íntegrament.

- [ ] **Pas 2: Verifica estructura completa**

- [ ] **Pas 3: Commit**

```bash
git add gencat/skills/gencat-xarxes-socials/references/linkedin.md
git commit -m "feat: skill gencat-xarxes-socials — references/linkedin"
```

---

## Task 6: references/youtube.md

**Fitxers:**
- Crear: `gencat/skills/gencat-xarxes-socials/references/youtube.md`

- [ ] **Pas 1: Crea el fitxer**

Valors clau per YouTube. **Recordar:** el skill cobreix elements textuals, NO guionitza vídeos.

| Element | Valor |
|---------|-------|
| Títol | 100 caràcters màxim; recomanat 60-70 (per no truncar-se als resultats) |
| Descripció | 5.000 caràcters màxim; primers 150 visibles sense expandir |
| Etiquetes (tags) | Recomanat 5-8 etiquetes rellevants |
| Hashtags a la descripció | Màxim 15 (YouTube mostra els 3 primers al títol) |
| To del títol | Descriptiu i directe; evitar clickbait |
| Estructura descripció recomanada | 1r paràgraf: resum del vídeo (150 c.) · 2n: context i detalls · 3r: CTA i enllaços · 4t: hashtags |

Abast explícit: "Aquest skill redacta el **títol**, la **descripció** i les **etiquetes** del vídeo. No elabora guions ni escaletes."

Exemple bo: títol clar amb paraula clau al principi, descripció estructurada amb CTA.
Exemple dolent: títol vague ("Vídeo informatiu del Departament"), descripció buida.

- [ ] **Pas 2: Verifica estructura completa**

- [ ] **Pas 3: Commit**

```bash
git add gencat/skills/gencat-xarxes-socials/references/youtube.md
git commit -m "feat: skill gencat-xarxes-socials — references/youtube"
```

---

## Task 7: references/threads.md

**Fitxers:**
- Crear: `gencat/skills/gencat-xarxes-socials/references/threads.md`

- [ ] **Pas 1: Crea el fitxer**

Valors clau per Threads:

| Element | Valor |
|---------|-------|
| Post | 500 caràcters màxim |
| Hashtags | Màxim 5; recomanat 1-3 |
| To | Similar a X però lleugerament menys formal; conversacional |
| Formats clau | Text, imatge, vídeo (màx. 5 min), fil (thread) |
| Particularitat | Plataforma nova (2023); audiència jove; integrada amb Instagram. No té funció de RT directe. |

Afegir nota: "Threads és la plataforma amb menys historial d'ús institucional. Aplicar criteri conservador: preferir X per a comunicació oficial urgent."

- [ ] **Pas 2: Verifica estructura completa**

- [ ] **Pas 3: Commit**

```bash
git add gencat/skills/gencat-xarxes-socials/references/threads.md
git commit -m "feat: skill gencat-xarxes-socials — references/threads"
```

---

## Task 8: references/tiktok.md

**Fitxers:**
- Crear: `gencat/skills/gencat-xarxes-socials/references/tiktok.md`

- [ ] **Pas 1: Crea el fitxer**

Valors clau per TikTok. **Recordar:** el skill cobreix elements textuals, NO guionitza vídeos.

| Element | Valor |
|---------|-------|
| Descripció del vídeo | 2.200 caràcters màxim; recomanat < 150 (visible sense expandir) |
| Hashtags | Màxim 5 rellevants; evitar hashtags massa genèrics |
| To | Proper, directe, gens burocràtic; públic jove |
| Formats | Vídeo vertical (9:16); durada recomanada 15-60 s per a contingut institucional |
| Particularitat | L'algoritme prioritza el contingut que reté l'usuari; la descripció ha d'enganxar els primers 3 s |

Abast explícit: "Aquest skill redacta la **descripció** i els **hashtags** del vídeo. No elabora guions ni escaletes."

Nota sobre to: "TikTok és la plataforma on el to institutional pot semblar més forçat. Prioritzar naturalitat i claredat per sobre de formalitat."

- [ ] **Pas 2: Verifica estructura completa**

- [ ] **Pas 3: Commit**

```bash
git add gencat/skills/gencat-xarxes-socials/references/tiktok.md
git commit -m "feat: skill gencat-xarxes-socials — references/tiktok"
```

---

## Task 9: references/plantilles.md

**Fitxers:**
- Crear: `gencat/skills/gencat-xarxes-socials/references/plantilles.md`

- [ ] **Pas 1: Crea el fitxer**

Cada plantilla té: estructura amb `[VARIABLES]`, exemple real omplert, notes d'ús.

```markdown
# Plantilles de contingut — Xarxes Socials Gencat

---

## 1. Avís / informació de servei

**Quan usar-la:** Notificació d'un servei, canvi d'horari, nova prestació, incidència.
**Xarxes recomanades:** Totes.

**Estructura:**
```
[EMOJI OPCIONAL] [TÍTOL BREU DE L'AVÍS].

[DETALL: qui es veu afectat, quan, on o com].

[CTA: enllaç o instrucció d'acció] ➡️ [URL]

[1-2 HASHTAGS]
```

**Exemple (X):**
```
ℹ️ Canvi d'horari a les oficines del Registre Civil de Barcelona.

A partir del 7 d'abril, l'atenció presencial serà de 9 a 14 h (de dilluns a divendres).

Consulta la resta d'oficines: ➡️ [URL]

#RegistreCivil
```

---

## 2. Convocatòria / ajut

**Quan usar-la:** Obertura de terminis, subvencions, beques, premis.
**Xarxes recomanades:** Totes; LinkedIn i Facebook per a subvencions a empreses/entitats.

**Estructura:**
```
[EMOJI] [NOM DE L'AJUT O CONVOCATÒRIA].

[A QUI VA DIRIGIT]. Termini: [DATA].

[IMPORT O CONDICIONS CLAU en una línia].

Presenta la sol·licitud: ➡️ [URL]

[1-2 HASHTAGS]
```

**Exemple (LinkedIn):**
```
📢 Subvencions per a projectes de digitalització de pimes catalanes.

Dirigides a empreses de menys de 50 treballadors. Termini: 30 d'abril de 2026.

Import màxim: 15.000 € per projecte.

Presenta la sol·licitud: ➡️ [URL]

#Digitalització #PimesCatalunya
```

---

## 3. Emergència / alerta

**Quan usar-la:** Avisos METEOCAT, activacions PROCICAT, emergències actives.
**Xarxes recomanades:** X (prioritari), Facebook, Threads.
**⚠️ Nota:** Sempre revisar amb el gabinet de comunicació i el departament responsable abans de publicar.

**Estructura:**
```
🔴 [TIPUS D'ALERTA en majúscules]: [NOM DEL FENOMEN o INCIDENT].

[ÀREA AFECTADA]. [INTENSITAT o NIVELL si escau].

[INSTRUCCIONS CLAU per a la ciutadania — llista breu].

Segueix les indicacions de [AUTORITAT RESPONSABLE]: ➡️ [URL]

#[HashtagEmergència]
```

**Exemple (X):**
```
🔴 ALERTA METEOCAT: Risc de pluges intenses al litoral de Tarragona.

Afectació prevista de 15 a 22 h. Nivell de perill: taronja.

- Evita desplaçaments innecessaris
- Allunyeu-vos de rieres i barrancs
- Segueix el trànsit a Twitter de @transit

Més informació: ➡️ [URL METEOCAT]

#AlertaMeteo
```

---

## 4. Campanya institucional

**Quan usar-la:** Missatge de campanya amb crida a l'acció (CTA), dies commemoratius, llançament de serveis.
**Xarxes recomanades:** Totes, adaptar el to per plataforma.

**Estructura:**
```
[MISSATGE PRINCIPAL de la campanya — 1-2 frases impactants].

[CONTEXT o DADA que reforça el missatge — opcional].

[CTA clar]: ➡️ [URL]

[1-2 HASHTAGS DE CAMPANYA]
```

**Exemple (Instagram caption):**
```
Cada gota compta. Estalvia aigua a casa i ajuda a protegir els rius de Catalunya.

El consum domèstic representa el 20% de l'aigua consumida al país.

Descobreix consells pràctics: ➡️ [URL]

#AiguaCatalunya #EstalviaAigua
```

---

## 5. Resposta a comentari

**Quan usar-la:** Gestió de comunitat, respostes a queixes, dubtes o agraïments.
**Xarxes recomanades:** Totes.
**To per plataforma:** Formal (LinkedIn) · Proper (X, Facebook, Instagram, TikTok) · Molt proper (Threads, TikTok).

**Estructura general:**
```
[SALUTACIÓ si escau] [RECONEIXEMENT del comentari].

[RESPOSTA O INFORMACIÓ ÚTIL].

[CTA si cal — derivar a canal adequat].
```

**Exemple formal (LinkedIn):**
```
Gràcies pel vostre comentari.

La convocatòria preveu una pròrroga del termini en cas de força major, d'acord amb les bases reguladores publicades al DOGC.

Si teniu alguna consulta addicional, podeu contactar amb el departament a través de: ➡️ [URL bústia]
```

**Exemple proper (X / Instagram):**
```
Hola! El termini s'ha ampliat fins al 30 d'abril.

Pots consultar tota la informació actualitzada aquí: ➡️ [URL]
```

---

## 6. Fil / thread

**Quan usar-la:** Temes complexos, processos amb passos, notícies llargues, explicació de normatives.
**Xarxes recomanades:** X, Threads.

**Estructura:**
```
POST 1 (ganxo): [AFIRMACIÓ IMPACTANT o PREGUNTA]. 🧵 [1/N]

POST 2-N (desenvolupament): [UN PUNT per post, concís].

POST FINAL: [RESUM o CTA] ➡️ [URL]
```

**Exemple (X, fil de 4 posts):**
```
1/4 — Saps quins tràmits de la Generalitat pots fer des del mòbil en menys de 5 minuts? Et fem un resum. 🧵

2/4 — Renovar el carnet de biblioteca: accedeix a biblioteques.gencat.cat, inicia sessió amb idCAT i segueix els 3 passos. Sense cues, sense papers.

3/4 — Sol·licitar el certificat de convivència: tramita.gencat.cat > cerca "convivència" > identifica't. El certificat arriba al teu correu en 24-48 h.

4/4 — Consulta el catàleg complet de tràmits en línia: ➡️ [URL] #TràmitsGencat
```
```

- [ ] **Pas 2: Verifica**

Comprova que cada plantilla té: estructura amb variables, exemple real, notes d'ús (quan usar-la, xarxes recomanades).

- [ ] **Pas 3: Commit**

```bash
git add gencat/skills/gencat-xarxes-socials/references/plantilles.md
git commit -m "feat: skill gencat-xarxes-socials — references/plantilles"
```

---

## Task 10: Actualitza README i marketplace

**Fitxers:**
- Modificar: `gencat/README.md`
- Revisar: `gencat/package.json`

- [ ] **Pas 1: Afegeix el skill al README**

Obre `gencat/README.md` i afegeix una fila a la taula de skills:

```markdown
| `gencat-xarxes-socials` | Xarxes Socials — genera i revisa contingut per a X, Facebook, Instagram, LinkedIn, YouTube, Threads i TikTok seguint la guia corporativa |
```

Afegeix també l'enllaç a la documentació oficial a la secció "Documentació oficial":
```markdown
- Guia de Xarxes Socials: https://atenciociutadana.gencat.cat/web/.content/manuals/xarxes/guia_xarxa.pdf
```

- [ ] **Pas 2: Commit**

```bash
git add gencat/README.md
git commit -m "docs: afegeix gencat-xarxes-socials al README"
```

---

## Task 11: Validació final

- [ ] **Pas 1: Comprova l'estructura completa de fitxers**

```bash
find gencat/skills/gencat-xarxes-socials -type f | sort
```

Resultat esperat:
```
gencat/skills/gencat-xarxes-socials/SKILL.md
gencat/skills/gencat-xarxes-socials/plan.md
gencat/skills/gencat-xarxes-socials/spec.md
gencat/skills/gencat-xarxes-socials/references/facebook.md
gencat/skills/gencat-xarxes-socials/references/instagram.md
gencat/skills/gencat-xarxes-socials/references/linkedin.md
gencat/skills/gencat-xarxes-socials/references/plantilles.md
gencat/skills/gencat-xarxes-socials/references/threads.md
gencat/skills/gencat-xarxes-socials/references/tiktok.md
gencat/skills/gencat-xarxes-socials/references/x-twitter.md
gencat/skills/gencat-xarxes-socials/references/youtube.md
```

- [ ] **Pas 2: Verifica el frontmatter del SKILL.md**

```bash
head -5 gencat/skills/gencat-xarxes-socials/SKILL.md
```

Resultat esperat: bloc `---` amb `name: gencat-xarxes-socials` i `description:` complet.

- [ ] **Pas 3: Comprova que tots els fitxers de xarxa tenen les 11 seccions**

Per a cada fitxer `references/<xarxa>.md`, verifica que conté les seccions:
`Límits tècnics` · `Hashtags` · `Emojis` · `To i estil` · `Formats recomanats` · `Tipus de contingut recomanat` · `Evitar` · `Accessibilitat` · `Exemple bo` · `Exemple dolent` · `Checklist`

- [ ] **Pas 4: Verifica que `plantilles.md` té les 6 plantilles**

Les 6 plantilles: Avís/informació · Convocatòria/ajut · Emergència/alerta · Campanya institucional · Resposta a comentari · Fil/thread

- [ ] **Pas 5: Commit final si tot és correcte**

```bash
git log --oneline -10
```

Comprova que hi ha un commit per cada fitxer creat (Tasks 1-10).
