# Documents PDF Accessibles — Gencat

El Decret 216/2023 i l'EN 301 549 (clàusula 10) cobreixen també els **documents descarregables** publicats als webs de la Generalitat. Un PDF inaccessible és un incompliment igual que una pàgina inaccessible.

**Criteri general:** abans de publicar un PDF, valora si el contingut pot ser una **pàgina HTML** — sempre és més accessible, més indexable i més fàcil de mantenir. Publica PDF només quan calgui un document formal (resolucions, formularis oficials, documents per imprimir).

---

## Requisits mínims d'un PDF accessible

| Requisit | Com es compleix |
|----------|-----------------|
| **Etiquetatge (tagged PDF)** | El document ha de tenir etiquetes d'estructura (`H1`-`H6`, `P`, `L/LI`, `Table`, `Figure`). Sense etiquetes, el lector de pantalla llegeix un bloc pla |
| **Idioma del document** | Definit a les propietats (català: `ca-ES`); canvis d'idioma marcats per fragment |
| **Títol del document** | A les propietats (camp Títol, no només el nom del fitxer), i configurat perquè es mostri el títol i no el nom de fitxer |
| **Ordre de lectura** | L'ordre lògic de les etiquetes ha de coincidir amb l'ordre visual (verifica-ho amb el panell d'ordre de lectura) |
| **Text real, no imatge** | Mai publiquis un PDF escanejat sense OCR: el text ha de ser seleccionable |
| **Alternatives a imatges** | Tota figura informativa amb text alternatiu; les decoratives marcades com a artefacte |
| **Taules** | Files de capçalera marcades com a `TH`; evita taules per maquetar |
| **Enllaços** | Text d'enllaç descriptiu (no l'URL nua ni "cliqueu aquí") |
| **Contrast** | Mateixos ratios que en web: 4.5:1 text normal, 3:1 text gran |
| **Marcadors (bookmarks)** | Obligatoris en documents de més de ~20 pàgines, seguint l'estructura d'encapçalaments |

---

## Formularis PDF

- Cada camp amb **nom i descripció (tooltip)** que faci de label per al lector de pantalla
- Ordre de tabulació coherent amb l'ordre visual
- Camps obligatoris indicats al tooltip ("Nom i cognoms (obligatori)")
- Si el formulari s'ha de signar o emplenar en línia, valora substituir-lo per un formulari web del tràmit

---

## Flux de treball recomanat

1. **A l'origen (Word/Writer/InDesign):** usa estils d'encapçalament reals, llistes natives, text alternatiu a les imatges i taules amb fila de capçalera. La majoria de problemes d'un PDF venen del document d'origen.
2. **Exporta** amb l'opció "PDF etiquetat" / "Crea PDF accessible" activada (mai "Imprimir a PDF": perd les etiquetes).
3. **Verifica:**
   - Comprovació automàtica: comprovador d'accessibilitat d'Adobe Acrobat Pro o **PAC (PDF Accessibility Checker)** — gratuït, valida PDF/UA
   - Comprovació manual: ordre de lectura, lectura amb NVDA, títol i idioma a les propietats
4. **Corregeix a l'origen** sempre que sigui possible (no apedacis només el PDF: la pròxima exportació perdria els arranjaments).

---

## Errors freqüents en PDFs Gencat

| Error | Correcció |
|-------|-----------|
| PDF escanejat sense OCR | Aplica OCR o, millor, regenera des del document d'origen |
| Sense etiquetes (untagged) | Reexporta des de l'origen amb l'opció d'etiquetatge |
| Títol de document buit | Emplena el camp Títol a les propietats |
| Idioma sense definir | Defineix `ca-ES` (o el que correspongui) a les propietats |
| Encapçalaments fets amb negreta i mida | Usa estils d'encapçalament al document d'origen |
| Taules de maquetació | Substitueix per columnes o seccions reals |

---

## Referències

- EN 301 549, clàusula 10 (documents no web)
- PDF/UA (ISO 14289) — estàndard d'accessibilitat per a PDF
- Portal d'accessibilitat de Gencat: https://atenciociutadana.gencat.cat/ca/accessibilitat/
