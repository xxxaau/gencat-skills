---
name: gencat-identitat-corporativa
description: "Aplica les normes d'identitat corporativa de la Generalitat de Catalunya quan creïs o validis documents, presentacions, signatures de correu o qualsevol material de comunicació institucional. Usa aquesta skill quan l'usuari treballi amb la marca Gencat fora del web: documents Word, presentacions PowerPoint, PDFs, cartes oficials, formularis, newsletters o signatures de correu. Activa-la quan mencioni 'identitat corporativa', 'marca gencat', 'logotip generalitat', 'colors corporatius', 'tipografia corporativa gencat', 'signatura correu corporativa', 'presentació corporativa', 'document oficial gencat', 'Open Sans gencat', 'Helvetica Neue gencat', o demani crear o validar material institucional de la Generalitat. Activa-la també en mode VALIDAR quan l'usuari enviï una imatge o fitxer per comprovar el compliment de la marca."
---

# Identitat Corporativa — Generalitat de Catalunya

Font oficial: https://identitatcorporativa.gencat.cat/ca/inici (citar en respostes de consulta i informes de validació)

---

## Abast de la skill

### Què cobreix
- Normes de marca visual (color, tipografia, logotip i aplicacions)
- Validació de materials institucionals (documents, presentacions, signatura i newsletter)
- Creació de contingut corporatiu no centrat en implementació web

### Què NO cobreix
- Disseny funcional de components web i patrons d'interfície (delegar a `gencat-design-system`)
- Auditories tècniques d'accessibilitat WCAG de productes digitals (delegar a `gencat-accessibilitat`)
- Redacció específica de camps de fitxes de tràmit (delegar a `gencat-tramits`)

### Skills complementàries
- `gencat-comunicacio-clara` per assegurar llenguatge planer en peces corporatives
- `gencat-xarxes-socials` quan les peces es publiquen en canals socials
- `gencat-design-system` quan una decisió de marca impacta UI web corporativa

---

## Detecció del mode

| Situació | Mode |
|----------|------|
| Pregunta de referència ("quin color...?", "quina tipografia...?") | CONSULTAR |
| Petició de creació ("redacta una signatura", "crea una plantilla") | CREAR |
| Imatge o fitxer adjunt / ruta de fitxer / text enganxat per revisar | VALIDAR |
| Dubte | Preguntar: "Vols crear contingut nou o validar un material existent?" |

---

## Càrrega de referències

- Colors, tipografia o logotip → llegir `references/marca-visual.md`
- Documents, presentacions, PDFs → llegir `references/documents.md`
- Signatura de correu, newsletters → llegir `references/comunicacio-digital.md`
- Mode VALIDAR → llegir `references/validacio.md` + el fitxer de referència corresponent al tipus de material; si el tipus no és identificable, preguntar: "De quin tipus de material es tracta? (document Word/PowerPoint, signatura de correu, PDF...)"

---

## Mode CONSULTAR / CREAR

1. Identificar el suport (o preguntar si no és clar)
2. Llegir el fitxer de referència corresponent
3. Respondre o generar el contingut aplicant les normes
4. Per a valors de colors i tipografia: usar sempre els de `references/marca-visual.md` (font canònica)

---

## Mode VALIDAR

Llegir `references/validacio.md` per al workflow complet, els criteris d'avaluació, la puntuació i el format de l'informe.

---

## Llista de verificació ràpida

- [ ] Colors: s'usa el vermell #C00000 com a color corporatiu principal?
- [ ] Tipografia: Arial per a documents Office (Helvetica Neue amb llicència com a alternativa); Open Sans per a digital; cap Calibri?
- [ ] Logotip: mida mínima 4,7 mm; no distorsionat; espai de seguretat respectat?
- [ ] Comunicacions a la ciutadania: logotip de la Generalitat (no el departamental)?
- [ ] Signatura de correu: estructura correcta amb les 3 seccions obligatòries?
