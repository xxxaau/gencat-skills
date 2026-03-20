# Spec: gencat-xarxes-socials

**Data:** 2026-03-20
**Estat:** Aprovat per l'usuari
**Font oficial:** https://atenciociutadana.gencat.cat/web/.content/manuals/xarxes/guia_xarxa.pdf

---

## Resum

Skill per a Claude Code que aplica la Guia de Xarxes Socials de la Generalitat de Catalunya. Permet generar contingut nou optimitzat per a cada plataforma i revisar contingut existent contra les normes corporatives.

---

## Cas d'ús

- **Generar** posts nous a partir d'un tema o contingut font
- **Revisar/adaptar** contingut existent (nota de premsa, tràmit, comunicat) per a xarxes socials
- **Verificar** que un post compleix les normes Gencat abans de publicar

---

## Estructura de fitxers

```
gencat/skills/gencat-xarxes-socials/
├── SKILL.md
└── references/
    ├── x-twitter.md
    ├── facebook.md
    ├── instagram.md
    ├── linkedin.md
    ├── youtube.md
    ├── threads.md
    ├── tiktok.md
    └── plantilles.md
```

---

## SKILL.md

### Frontmatter (format exacte requerit)

```yaml
---
name: gencat-xarxes-socials
description: "Aplica la Guia de Xarxes Socials de la Generalitat de Catalunya quan generis, revisis o adaptis contingut per a plataformes digitals. Usa aquesta skill sempre que l'usuari treballi amb publicacions a X (Twitter), Facebook, Instagram, LinkedIn, YouTube, Threads o TikTok en el context de comunicació institucional de la Generalitat. Activa-la també quan mencioni 'post', 'publicació', 'hashtag', 'tweet', 'fil', 'thread', 'reel', 'story', 'contingut digital', 'xarxa social', o demani adaptar un comunicat, nota de premsa o tràmit per a xarxes socials."
---
```

### Detecció del mode (GENERAR vs REVISAR)

- Si l'usuari **proporciona text existent** → mode REVISAR per defecte (revisar i proposar versió corregida)
- Si l'usuari **no proporciona text** → mode GENERAR
- Si l'usuari demana "millora" o "adapta" text existent → mode REVISAR amb proposta de nova versió
- En cas de dubte → preguntar: "Vols que generi un post nou o que revisi un text que ja tens?"

### Normes transversals (al SKILL.md)

- **Llengua:** català per defecte; castellà si la xarxa o campanya ho requereix explícitament
- **To:** institucional però proper, mai burocràtic; veu activa; frases curtes
- **Accessibilitat:**
  - Alt text descriptiu per a totes les imatges
  - Hashtags en CamelCase: `#GeneralitatDeCatalunya` no `#generalitat de catalunya`
  - Evitar emojis consecutius (dificulten lectors de pantalla)
  - Evitar emojis com a substituts de paraules
- **Contingut sensible:** per a temes de salut, menors o violència, afegir un avís al post generat indicant que cal revisió humana abans de publicar. La plantilla "Emergència / alerta" (PROCICAT, METEOCAT) és l'excepció: és contingut planificat i l'usuari la invoca explícitament.
- **Sigles:** desplegar sempre la primera vegada

### Workflow — Mode GENERAR

1. Si no s'especifica la xarxa objectiu → preguntar abans de fer res
2. Llegir `references/<xarxa>.md` per als límits, normes i exemples de la plataforma
3. Si no s'indica el to → preguntar (informatiu / divulgatiu / d'urgència / de campanya)
4. Generar el post respectant: límit de caràcters, hashtags màxims, to corporatiu i accessibilitat
5. Oferir adaptació a altres xarxes si escau
6. Mostrar checklist de verificació específica de la plataforma

### Workflow — Mode REVISAR

1. Identificar la xarxa del contingut (o preguntar si no és evident)
2. Llegir `references/<xarxa>.md`
3. Verificar cada norma, distingint entre **obligatòries** (marcades com a tal al fitxer de xarxa) i **recomanades**
4. Lliurar informe estructurat:
   - ✅ Aspectes correctes
   - ⚠️ Recomanació no seguida (millora opcional, amb proposta)
   - ❌ Norma obligatòria incomplerta (cal corregir abans de publicar, amb correcció)
5. Oferir sempre versió corregida si hi ha algun ❌

> **Criteri de severitat:** és ❌ quan incompleix un límit tècnic (caràcters, hashtags màxims) o una norma d'accessibilitat. És ⚠️ quan és una recomanació d'estil o to.

---

## references/<xarxa>.md — Estructura tipus

Cada fitxer de xarxa inclou:

Cada secció del fitxer indica si la norma és **obligatòria** o **recomanada**, per facilitar la classificació ❌/⚠️ al mode REVISAR.

| Secció | Contingut |
|--------|-----------|
| **Límits** | Caràcters per post, per comentari, per bio, per hashtag |
| **Hashtags** | Nombre màxim recomanat, posició (al final), estil CamelCase |
| **Emojis** | Ús recomanat, posició, restriccions |
| **To i estil** | Característiques de la veu per a aquesta plataforma |
| **Formats recomanats** | Text, imatge, vídeo, carrusel, story, reel, etc. |
| **Tipus de contingut** | Quins continguts funcionen millor en aquesta xarxa |
| **Evitar** | Errors habituals i pràctiques prohibides |
| **Accessibilitat** | Requisits específics de la plataforma |
| **Exemple bo** | Post model amb anotacions |
| **Exemple dolent** | Post incorrecte amb explicació dels errors |
| **Checklist** | 5-7 ítems de verificació específics de la plataforma |

### Xarxes cobertes

| Xarxa | Fitxer | Abast del skill |
|-------|--------|----------------|
| X (Twitter) | `references/x-twitter.md` | Posts, fils (threads), respostes |
| Facebook | `references/facebook.md` | Posts, esdeveniments, respostes |
| Instagram | `references/instagram.md` | Posts, stories, reels (descripció), captions |
| LinkedIn | `references/linkedin.md` | Posts, articles (títol+intro), respostes |
| YouTube | `references/youtube.md` | Títol, descripció i etiquetes del vídeo (no guions) |
| Threads | `references/threads.md` | Posts, fils |
| TikTok | `references/tiktok.md` | Descripció del vídeo, hashtags |

> **Nota YouTube i TikTok:** el skill cobreix els **elements textuals** (títol, descripció, etiquetes, hashtags). No guionitza vídeos.

---

## references/plantilles.md

Plantilles reutilitzables per tipus de contingut. Cada plantilla inclou:
- Estructura amb `[VARIABLES]` en majúscules
- Exemple real omplert
- Notes d'ús (quan usar-la, xarxes recomanades)

### Tipus de plantilles

| Tipus | Descripció |
|-------|-----------|
| **Avís / informació** | Notificació d'un servei, canvi d'horari, nova prestació |
| **Convocatòria / ajut** | Obertura de terminis, subvencions, beques |
| **Emergència / alerta** | METEOCAT, PROCICAT — to i estructura especials |
| **Campanya institucional** | Missatge de campanya amb crida a l'acció (CTA) |
| **Resposta a comentari** | Gestió de comunitat, to empàtic i resolutiu. To varia: formal (LinkedIn) vs proper (Instagram/TikTok). Cobreix totes les xarxes amb variants per plataforma. |
| **Fil / thread** | Estructura per desglossar temes complexos (X / Threads) |

---

## Llista de verificació ràpida (al SKILL.md)

- [ ] La xarxa objectiu està identificada?
- [ ] El post respecta el límit de caràcters de la plataforma?
- [ ] Els hashtags estan en CamelCase i al final del post?
- [ ] No hi ha més hashtags dels recomanats per la plataforma?
- [ ] El to és proper, en veu activa i sense burocratisme?
- [ ] Les imatges tenen alt text descriptiu?
- [ ] Els emojis no substitueixen paraules ni apareixen consecutivament?
- [ ] Les sigles estan desplegades la primera vegada?
- [ ] El contingut és en català (o castellà si la campanya ho requereix)?

---

## Decisions de disseny

| Decisió | Raó |
|---------|-----|
| Un fitxer per xarxa (no per tema) | Facilita la consulta ràpida quan es treballa en una plataforma concreta |
| Workflow dual explícit (generar/revisar) | Comportament predictible; Claude sap exactament què fer en cada cas |
| Plantilles en fitxer separat | Reutilitzables sense contaminar les normes de cada xarxa |
| Normes d'accessibilitat transversals al SKILL.md | Apliquen a totes les xarxes; no cal repetir-les a cada fitxer |
| Llengua: català per defecte | Alineació amb la política lingüística de la Generalitat |
