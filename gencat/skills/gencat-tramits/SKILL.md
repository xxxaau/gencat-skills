---
name: gencat-tramits
description: "Aplica el Manual de redacció i estil de fitxes de tràmit de la Generalitat (febrer 2026) quan redactis, revisis o auditis fitxes de tràmit de gencat.cat. Activa-la quan es mencioni fitxa de tràmit, modalitat, silenci administratiu, passos de tramitació, GECO, OGE, SAC, o quan l'usuari proporcioni URLs de tramit.gencat.cat per revisar. Inclou avaluació GEO/SEO (posicionament en motors d'IA i de cerca, Schema.org, recuperabilitat) tant en redacció com a REVISAR WEB."
---

# Manual de Redacció de Fitxes de Tràmit — Gencat (febrer 2026)

Font oficial: https://atenciociutadana.gencat.cat/ca/serveis/tramits/manuals-i-guies/
Contacte: tramits@gencat.cat

---

## Abast de la skill

### Què cobreix
- Redacció i revisió dels camps de fitxes de tràmit de gencat.cat
- Passos de tramitació, vocabulari i criteris formals del manual oficial
- Revisió web de fitxes amb informe de compliment

### Què NO cobreix
- Definició de components o arquitectura d'interfície (delegar a `gencat-design-system`)
- Auditoria tècnica completa de compliment WCAG fora del contingut de la fitxa (delegar a `gencat-accessibilitat`)
- Estratègia de publicació per xarxes socials o campanyes (delegar a `gencat-xarxes-socials`)

### Skills complementàries
- `gencat-comunicacio-clara` per reforçar llenguatge planer en tots els camps
- `gencat-accessibilitat` per validar comprensió i accessibilitat del contingut publicat
- `gencat-design-system` si la fitxa es tradueix en fluxos o pantalles noves de tramitació

---

## Criteris generals de redacció

### Tractament personal

| Destinatari | Tractament | Exemple |
|------------|-----------|---------|
| Persona individual (ciutadà) | **tu** | "Pots sol·licitar...", "Has de presentar..." |
| Organitzacions (empreses, entitats) | Tercera persona (l'empresa/entitat...) o **vós** si no és possible | "L'empresa ha de presentar..." / "Heu signat..." |
| Tràmit adreçat a ciutadans I organitzacions | **vós** | "Podeu sol·licitar..." |
| Referència a l'Administració | Primera persona plural | "Si necessitem més informació, t'enviarem..." |

El tractament ha de ser **coherent** al llarg de tot el tràmit (avisos, literals, passos).

### Estil de redacció

Els criteris generals de redacció (frases de 20-30 paraules, ordre subjecte + verb + complements, veu activa, nominalitzacions, verbs buits) són els de la skill **gencat-comunicacio-clara** — és la font d'autoritat; no els dupliquis.

Específic de fitxes de tràmit:
- **Frases en positiu** (les afirmatives són més clares)
- **Negreta** per a paraules clau (amb moderació)
- **Llistes** per a enumeracions o informació llarga
- Si uses sigles, desplega-les el primer cop: "idCAT Mòbil (identificació digital)"
- Si cites normativa, usa denominació abreujada amb enllaç: "La Llei de transparència"

Per a l'accessibilitat del contingut (textos d'enllaços descriptius, jerarquia de títols, instruccions no sensorials), usa **gencat-accessibilitat** — també en mode redacció, no només a REVISAR WEB.

---

## Estructura d'una fitxa de tràmit

Llegeix `references/camps.md` per a les regles de redacció detallades de cada camp.
Llegeix `references/passos.md` per als passos de tramitació i els textos estàndard.
Llegeix `references/vocabulari.md` per a substitucions de vocabulari i bones pràctiques.
Llegeix `references/geo-seo.md` per als principis GEO/SEO de redacció i per a l'avaluació GEO/SEO on-page.

---

## Llista de verificació ràpida

### Títol
- [ ] Menys de 80 caràcters (sense espais, any, acrònims ni sigles)?
- [ ] Estructura: tipus + objecte (opcional) + concreció?
- [ ] Sense termes administratius: sol·licitud, inscripció, convocatòria?
- [ ] Sense punt final?
- [ ] Si és conegut per acrònim, el desplegues al títol?

### Redacció general
- [ ] Frases entre 20 i 30 paraules?
- [ ] Ordre subjecte + verb + complements?
- [ ] Veu activa?
- [ ] Sense nominalitzacions ni verbs buits?
- [ ] Tractament personal coherent al llarg de tot el tràmit?
- [ ] Termes tècnics explicats entre parèntesis o amb enllaç?

### Camps
- [ ] **A qui va dirigit**: preposició "a" davant de cada destinatari?
- [ ] **Terminis**: format de data i hora correcte?
- [ ] **Documentació**: en forma de llista, sense el formulari de sol·licitud?
- [ ] **Requisits**: en forma de llista directa, sense frase introductòria?
- [ ] **Taxes**: informat sempre (gratuït o import)?
- [ ] **Passos**: avisos obligatoris sobre tramitació per internet inclosos?
- [ ] **Silenci administratiu**: positiu o negatiu indicat al pas 4?

### GEO/SEO en redacció
- [ ] Títol directe i comprensible sense context?
- [ ] Cada camp és autocontingut i citable per separat?
- [ ] Imports, terminis i convocatòria amb data concreta?
- [ ] Cap dada crítica només en PDF o imatge?
- [ ] Encapçalaments en forma de pregunta on tingui sentit?

Vegeu `references/geo-seo.md` (Secció A) per al detall.

---

## Mode REVISAR WEB

S'activa quan l'usuari proporciona una o més URLs de fitxes de tràmit de gencat.cat.

Pas 0 obligatori: llegir `references/camps.md`, `references/passos.md`, `references/vocabulari.md` i `references/geo-seo.md` (Secció B) per tenir les normes carregades. Carregar també els criteris dels skills `gencat-comunicacio-clara` i `gencat-accessibilitat` per a l'avaluació transversal de qualitat lingüística i accessibilitat de contingut.

Llegeix `references/revisio-web.md` per al workflow complet, el criteri de puntuació i el format de l'informe.

La revisió inclou una **Capa 5 — GEO/SEO** amb nota independent i spot-check de risc de desinformació. Vegeu `references/geo-seo.md` (Secció B).
