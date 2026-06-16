# GEO/SEO de fitxes de tràmit

GEO (Generative Engine Optimization) és l'optimització perquè una fitxa sigui **recuperada, citada i correctament resumida** pels motors d'IA (ChatGPT, Gemini, Copilot, Perplexity). SEO i GEO són sistemes paral·lels: la posició a Google no prediu la visibilitat en IA.

Aquest reference té dues seccions independents:
- **Secció A — Redacció:** principis aplicables quan s'escriu el text d'una fitxa nova.
- **Secció B — On-page (REVISAR WEB):** auditoria GEO/SEO d'una fitxa publicada, amb nota pròpia i spot-check de risc.

> **No es dupliquen** criteris de `gencat-comunicacio-clara` (frases, veu activa, vocabulari) ni de `gencat-accessibilitat` (jerarquia de títols, textos d'enllaços, instruccions sensorials). S'hi remet quan és rellevant.

---

## Secció A — GEO/SEO en redacció

Principis controlables per qui redacta el text (Schema.org, `canonical` i `meta description` són de plantilla/CMS, no de l'editor → no hi entren):

1. **Títol directe i autocontingut** — el títol ha de dir de què va el tràmit sense context previ. Reforça les normes de títol existents amb l'angle "recuperable per IA".
2. **Respostes extractables** — cada camp resol una pregunta del ciutadà de forma autocontinguda, apta per ser citada per un model sense dependre d'altres camps.
3. **Dades datades i explícites** — imports, terminis i convocatòria amb data concreta; mai "properament" ni "consulteu la convocatòria".
4. **Contingut crític en text** — requisits, terminis, imports i passos en text, no només dins d'un PDF o una imatge.
5. **Encapçalaments en forma de pregunta** quan ajudi ("Qui ho pot demanar?", "Quan puc demanar-ho?") — afinitat amb estructures FAQ que els models recuperen bé.

### Verificació ràpida — GEO/SEO en redacció

- [ ] Títol directe i comprensible sense context?
- [ ] Cada camp és autocontingut i citable per separat?
- [ ] Imports, terminis i convocatòria amb data concreta?
- [ ] Cap dada crítica només en PDF o imatge?
- [ ] Encapçalaments en forma de pregunta on tingui sentit?

---

## Secció B — GEO/SEO on-page (REVISAR WEB)

### Criteris puntuables (nota GEO/SEO /10)

5 criteris, cadascun val **1 punt** si passa sense ❌. Nota = (criteris sense ❌) / 5 × 10.

| # | Criteri | ❌ Error | ⚠️ Millora | Serveix |
|---|---------|---------|-----------|---------|
| 1 | **Dades estructurades** | Sense cap JSON-LD Schema.org rellevant a la pàgina | Schema.org present però incomplet (manca `HowTo`, `FAQPage` o `BreadcrumbList`) | GEO+SEO |
| 2 | **Títol i metadades** | `<title>` absent o genèric · sense `meta description` · `canonical` absent o incorrecte | `<title>` >60 caràcters · `meta description` fora del rang 120-160 caràcters | SEO+GEO |
| 3 | **Atribució oficial** | Òrgan responsable no identificable a la pàgina | Atribució present però poc visible | GEO |
| 4 | **Extractabilitat** | Informació crítica (requisits, terminis, imports, passos) només en PDF/imatge o no autocontinguda | Camps dispersos que dificulten l'extracció per fragments | GEO |
| 5 | **Actualitat datada** | Sense data d'actualització o de convocatòria · imports o terminis sense data | Data present però poc visible | GEO |

> **Com inspeccionar Schema.org:** buscar al HTML blocs `<script type="application/ld+json">`. Els tipus rellevants per a un tràmit són `GovernmentService`, `HowTo`, `FAQPage` i `BreadcrumbList`.

### Spot-check black-box (opcional — NO entra a la nota GEO/10)

Detecta el risc de desinformació quan un model respon sobre el tràmit. Protocol autocontingut en 3 passos:

1. **Resposta cega** — l'agent respon "què diries a un ciutadà sobre aquest tràmit?" (~10 frases) NOMÉS des del seu coneixement, **sense consultar la fitxa**.
2. **Contrast** — es compara la resposta cega amb la fitxa recuperada (ground truth): es busquen contradiccions materials en imports, terminis, requisits o passos.
3. **Sortida** — etiqueta de risc + llista de contradiccions/al·lucinacions detectades.

Criteri de risc:

| Etiqueta | Quan |
|----------|------|
| **Alt** | Contradicció material en dades crítiques (imports, terminis, requisits) o invenció de la font canònica |
| **Mitjà** | Imprecisions menors o orientació incompleta, sense contradicció material |
| **Baix** | Sense contradiccions; resposta alineada amb la fitxa |

### Format de l'informe — Capa 5

S'afegeix al final de l'informe per tràmit, després de la Capa 4:

```
## Capa 5 — GEO/SEO

[Per a cada criteri: ✅/⚠️/❌ + exemple literal del problema]
✅ Dades estructurades — JSON-LD GovernmentService present.
❌ Títol i metadades — Sense meta description.
...

**Nota GEO/SEO: X/10** (independent de la nota editorial)
Risc de desinformació (spot-check): Baix/Mitjà/Alt — [contradiccions detectades, o "cap"]

### Recomanacions GEO accionables
- [p. ex. afegir JSON-LD GovernmentService amb camps del tràmit]
- [p. ex. <title> més directe sense l'any de convocatòria]
- [p. ex. datar la convocatòria al cos de la fitxa]
```
