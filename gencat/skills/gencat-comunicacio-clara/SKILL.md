---
name: gencat-comunicacio-clara
description: "Aplica la Guia de Comunicació Clara de la Generalitat quan redactis o revisis textos per a serveis digitals Gencat: literals d'UI, missatges d'error, formularis, avisos i notificacions. Activa-la quan es mencioni comunicació clara, llenguatge planer, literals, microcopy o textos administratius per simplificar."
---

# Comunicació Clara — Generalitat de Catalunya

Tots els textos de les aplicacions Gencat han de complir la **Guia de Comunicació Clara** (2025) de la Generalitat. L'objectiu és que qualsevol persona entengui el missatge a la primera lectura, sense necessitat d'ajuda externa.

**Norma de referència:** UNE-ISO 24495-1:2024 (Llenguatge planer)
**Font oficial:** https://atenciociutadana.gencat.cat/ca/comunicacio-clara/

---

## Abast de la skill

### Què cobreix
- Redacció i revisió de textos UI: botons, errors, formularis, avisos, confirmacions
- Simplificació de llenguatge administratiu i aplicació de llenguatge planer
- Coherència de tractament, to i estructura textual

### Què NO cobreix
- Definició visual de components i patrons d'interfície (delegar a `gencat-design-system`)
- Verificació tècnica WCAG/ARIA o auditories d'accessibilitat (delegar a `gencat-accessibilitat`)
- Validació formal d'estructures documentals ERQ/DA (delegar a `gencat-documentacio-ctti`)

### Skills complementàries
- `gencat-tramits` per adaptar el llenguatge als camps i passos de fitxes de tràmit
- `gencat-xarxes-socials` per adaptar missatges a plataformes concretes
- `gencat-accessibilitat` per reforçar comprensió i accessibilitat textual en context de producte

---

## Els 4 principis fonamentals (ISO 24495-1)

1. **Rellevància** — Inclou només la informació que el lector necessita
2. **Localitzabilitat** — Organitza perquè sigui fàcil trobar la informació
3. **Comprensibilitat** — Usa un llenguatge que el públic objectiu entengui
4. **Usabilitat** — El lector pot aplicar la informació immediatament

---

## Regles d'aplicació immediata

- **Frase**: ordre subjecte + verb + complements; una idea per frase; màxim **30 paraules**; veu activa.
- **Tractament**: **vós** en textos administratius; **tu** només en aplicacions per a joves o contextos informals. Mai barrejats en un mateix flux. Taula de contextos a `references/ui-literals.md`.
- **Vocabulari**: paraula curta i comuna > paraula llarga i tècnica (`usar` > `utilitzar`); explica els tecnicismes inevitables.
- **Llengua inclusiva**: col·lectius genèrics (`ciutadania`, `alumnat`, `la gerència`); `persona amb discapacitat`. Detall a `references/vocabulari.md`.

El detall complet (taules d'exemples, nominalitzacions, gerundis, paraules buit) és a `references/redaccio.md`.

---

## Guies detallades

- `references/redaccio.md` — Regles de redacció, veu activa, nominalitzacions
- `references/vocabulari.md` — Paraules a evitar i alternatives recomanades
- `references/ui-literals.md` — Patrons específics per a botons, errors, formularis, notificacions
- `references/titols-i-estructura.md` — Títols, encapçalaments, llistes, paràgrafs

---

## Workflow per a nous textos

1. **Identifica el context**: qui llegirà el text i amb quin objectiu
2. **Aplica les regles** de redacció i vocabulari (llegeix `references/redaccio.md`)
3. **Usa els patrons UI** adequats (`references/ui-literals.md`)
4. **Revisa** amb la llista de verificació al final d'aquest fitxer

---

## Llista de verificació ràpida

Abans de lliurar qualsevol text, verifica:

- [ ] La frase té menys de 30 paraules?
- [ ] Usa veu activa?
- [ ] Segueix l'ordre subjecte + verb + complements?
- [ ] Evita paraules tècniques innecessàries?
- [ ] El tractament (vós/tu) és consistent en tot el text?
- [ ] El títol o encapçalament té menys de 100 caràcters?
- [ ] La informació més important apareix primer?
- [ ] El text és inclusiu (evita biaix de gènere, edat, discapacitat)?
- [ ] S'han eliminat les paraules que no aporten significat?
