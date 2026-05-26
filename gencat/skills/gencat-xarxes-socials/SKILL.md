---
name: gencat-xarxes-socials
description: "Aplica la Guia de Xarxes Socials de la Generalitat de Catalunya quan generis, revisis o adaptis contingut per a plataformes digitals. Usa aquesta skill sempre que l'usuari treballi amb publicacions a X (Twitter), Facebook, Instagram, LinkedIn, YouTube, Threads o TikTok en el context de comunicació institucional de la Generalitat. Activa-la també quan mencioni 'post', 'publicació', 'hashtag', 'tweet', 'fil', 'thread', 'reel', 'story', 'contingut digital', 'xarxa social', o demani adaptar un comunicat, nota de premsa o tràmit per a xarxes socials."
---

# Xarxes Socials — Generalitat de Catalunya

Font oficial: https://atenciociutadana.gencat.cat/web/.content/manuals/xarxes/guia_xarxa.pdf

---

## Abast de la skill

### Què cobreix
- Generació i revisió de publicacions per xarxes socials institucionals
- Adaptació de missatges al format i límits de cada plataforma
- Validació de normes transversals de to, llengua i accessibilitat social

### Què NO cobreix
- Redacció formal de fitxes de tràmit administratiu (delegar a `gencat-tramits`)
- Definició de components i pantalles de producte digital (delegar a `gencat-design-system`)
- Validació de marca en documents ofimàtics o peces institucionals no socials (delegar a `gencat-identitat-corporativa`)

### Skills complementàries
- `gencat-comunicacio-clara` per simplificar i fer més entenedors els missatges
- `gencat-identitat-corporativa` per coherència de marca en campanyes institucionals
- `gencat-accessibilitat` per reforçar bones pràctiques d'alt text i llegibilitat

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
