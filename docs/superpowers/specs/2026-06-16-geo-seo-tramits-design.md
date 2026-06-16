# Disseny — Avaluació GEO/SEO de fitxes de tràmit (`gencat-tramits`)

**Data:** 2026-06-16
**Skill afectada:** `gencat/skills/gencat-tramits`

## Context i motivació

Els models d'IA (ChatGPT, Gemini, Copilot, Perplexity) són cada cop més la via per la qual la ciutadania pregunta sobre tràmits públics. Dues fonts marquen el problema i el marc:

- **Presentació "Auditoria GEO de tràmits de la Generalitat" (CTTI, juny 2026)** — sistema *black-box* que pregunta a models reals sobre cada tràmit i un *judge* separat puntua la resposta contra un *ground truth* oficial, amb 5 criteris (Atribució, Precisió factual, Recuperació de font oficial, Completitud, Actualitat) i una etiqueta de risc Baix/Mitjà/Alt.
- **Article Mainmind sobre GEO** — marc de mesura de visibilitat en motors generatius: 7 mètriques (Share of Voice, taxa de citació, cobertura de prompts, posició/context, sentiment, fonts que alimenten el model, tràfic des de LLMs) i tàctiques concretes (Schema.org, estadístiques/cites, títols directes, llenguatge clar). Punt clau: GEO i SEO són sistemes paral·lels; la posició a Google ja no prediu la visibilitat en IA.

La skill `gencat-tramits` ja avalua editorialment una fitxa contra el manual (mode REVISAR WEB, informe en 4 capes amb nota /10). Falta una dimensió que mesuri **com de recuperable, citable i correctament resumible** és una fitxa per part de motors d'IA i de cerca.

## Objectiu

Incorporar una avaluació GEO/SEO a `gencat-tramits` en **les dues vessants** de la skill:

- **Redacció** — principis GEO aplicables quan s'escriu el text d'una fitxa nova.
- **REVISAR WEB** — auditoria GEO/SEO on-page d'una fitxa publicada, amb nota pròpia i detecció de risc de desinformació.

## Decisions de disseny (preses amb l'usuari)

1. **Enfocament híbrid:** anàlisi on-page determinista com a base + spot-check *black-box* autocontingut opcional.
2. **Integració:** nova **Capa 5 — GEO/SEO** dins de REVISAR WEB, amb **nota GEO/10 independent** de la nota editorial /10 (dos eixos diferents: compliment del manual vs recuperabilitat per IA; no es barregen). Sempre activa.
3. **Spot-check black-box autocontingut:** l'agent respon de memòria i es compara amb la fitxa recuperada com a ground truth; no requereix Excel ni APIs externes.
4. **Doble vessant:** GEO/SEO s'aplica tant a la redacció com a REVISAR WEB.

## Principi anti-duplicació

No es repliquen criteris que ja són autoritat d'altres skills:
- Llargada de frases, veu activa, vocabulari planer → `gencat-comunicacio-clara`.
- Jerarquia de títols, textos d'enllaços, instruccions sensorials → `gencat-accessibilitat`.

La Capa 5 s'hi **remet** quan és rellevant (p. ex. la jerarquia de títols ajuda la recuperació per fragments, però no es re-puntua aquí).

## Arquitectura de continguts

Un únic reference nou, `references/geo-seo.md`, amb dues seccions independents segons la vessant.

### Secció A — GEO/SEO en redacció

Subconjunt de principis **controlables per qui redacta el text** (es descarten Schema.org, `canonical` i `meta description`, que són de plantilla/CMS, no de l'editor):

1. **Títol directe i autocontingut** — angle "recuperable per IA" sobre les normes de títol ja existents.
2. **Respostes extractables** — cada camp resol una pregunta del ciutadà de forma autocontinguda, apta per ser citada per un model.
3. **Dades datades i explícites** — imports, terminis i convocatòria amb data; mai "properament".
4. **Contingut crític en text**, no només en PDF o imatge.
5. **Encapçalaments en forma de pregunta** quan ajudi (afinitat amb FAQ).

Es referencia des d'un bloc curt "GEO/SEO en redacció" a la Llista de verificació ràpida del `SKILL.md`, seguint el patró que ja s'usa amb accessibilitat ("també en redacció, no només a REVISAR WEB").

### Secció B — GEO/SEO on-page (REVISAR WEB)

#### Criteris puntuables (nota GEO/10)

5 criteris, cadascun val 1 punt si passa sense ❌; nota = (criteris sense ❌) / 5 × 10.

| # | Criteri | ❌ Error | ⚠️ Millora | Serveix |
|---|---------|---------|-----------|---------|
| 1 | **Dades estructurades** | Sense cap JSON-LD Schema.org rellevant | Schema.org present però incomplet (manca `HowTo`/`FAQPage`/`BreadcrumbList`) | GEO+SEO |
| 2 | **Títol i metadades** | `<title>` absent o genèric · sense `meta description` · `canonical` absent o incorrecte | `<title>` >60 car · `meta description` fora de 120-160 car | SEO+GEO |
| 3 | **Atribució oficial** | Òrgan responsable no identificable a la pàgina | Atribució present però poc visible | GEO |
| 4 | **Extractabilitat** | Informació crítica (requisits, terminis, imports, passos) només en PDF/imatge o no autocontinguda | Camps dispersos que dificulten l'extracció per fragments | GEO |
| 5 | **Actualitat datada** | Sense data d'actualització/convocatòria · imports o terminis sense data | Data present però poc visible | GEO |

#### Spot-check black-box (opcional, NO entra a la nota GEO/10)

Protocol autocontingut en 3 passos:

1. **Resposta cega** — l'agent respon "què diries a un ciutadà sobre aquest tràmit?" (~10 frases) NOMÉS des del seu coneixement, sense consultar la fitxa.
2. **Contrast** — es compara amb la fitxa recuperada (ground truth): contradiccions materials en imports, terminis, requisits o passos.
3. **Sortida** — **etiqueta de risc Baix/Mitjà/Alt** + llista de contradiccions/al·lucinacions detectades.

Criteri de risc:
- **Alt** — contradicció material en dades crítiques (imports, terminis, requisits) o invenció de la font canònica.
- **Mitjà** — imprecisions menors o orientació incompleta sense contradicció material.
- **Baix** — sense contradiccions; resposta alineada amb la fitxa.

#### Format de l'informe — Capa 5

S'afegeix al final de l'informe per tràmit:

```
## Capa 5 — GEO/SEO
[5 criteris amb ✅/⚠️/❌ + exemple literal del problema]

**Nota GEO/SEO: X/10** (independent de la nota editorial)
Risc de desinformació (spot-check): Baix/Mitjà/Alt — [contradiccions detectades]

### Recomanacions GEO accionables
- [p. ex. afegir JSON-LD GovernmentService; <title> més directe; datar la convocatòria]
```

Al resum consolidat (>1 URL) s'afegeixen columnes **GEO/10** i **Risc** a la taula resum.

## Fitxers a modificar

| Fitxer | Canvi |
|--------|-------|
| `references/geo-seo.md` | **Nou.** Secció A (redacció) + Secció B (on-page: criteris, scoring, spot-check, format Capa 5). |
| `SKILL.md` | Disparadors GEO/SEO/Schema.org/posicionament IA a la descripció; bloc "GEO/SEO en redacció" a la verificació ràpida; remissió a `geo-seo.md` a la secció REVISAR WEB. |
| `references/revisio-web.md` | Carregar `geo-seo.md` al Pas 0; afegir pas "Avaluació GEO/SEO" al workflow; Capa 5 al format d'informe; columnes GEO/Risc al consolidat; actualitzar l'exemple d'informe. |
| `gencat/README.md` | Actualitzar la descripció de capacitats de `gencat-tramits` amb la dimensió GEO/SEO. |

## Criteris d'èxit

- Una fitxa publicada revisada amb REVISAR WEB produeix una nota editorial /10 i una nota GEO/SEO /10 separades, més una etiqueta de risc.
- La redacció d'una fitxa nova pot seguir el bloc "GEO/SEO en redacció" sense entrar a inspeccions on-page no controlables per l'editor.
- Cap criteri de comunicació clara o accessibilitat es duplica; s'hi remet.
- Les recomanacions GEO de l'informe són accionables i concretes (Schema.org, títol, datació).

## Fora d'abast (YAGNI)

- Replicar el pipeline complet de CTTI (multi-model, repeticions, ground truth Excel, agregació mensual).
- Mètriques de monitoratge continu de l'article Mainmind (Share of Voice, tràfic GA4, logs de crawlers) — depenen d'eines i dades externes, no d'una revisió de fitxa.
- Consultes a APIs de LLMs externs; el spot-check és autocontingut amb el propi agent.
