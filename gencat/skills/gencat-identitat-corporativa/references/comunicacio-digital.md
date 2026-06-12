# Normes d'Aplicació de Marca — Comunicació Digital

Per als valors de colors i tipografia base, consultar `marca-visual.md` (font canònica).

Font oficial: https://identitatcorporativa.gencat.cat/ca/aplicacions/signatura-de-correu/ (citar en respostes de consulta i informes de validació)

---

## Signatura de correu electrònic

### Estructura (ordre obligatori)

1. **Cos del missatge**
2. **Dades personals** — nom, càrrec, unitat, departament
3. **Imatge d'identificació** — opcional (veure variants)
4. **Clàusula legal** — obligatòria
5. **Avís d'impressió** — opcional

### Especificacions tècniques

| Element | Valor |
|---------|-------|
| Font | Arial (Arial Bold per a èmfasi) — veure `marca-visual.md` excepció tècnica de signatura |
| Fons | Blanc |
| Text | Negre |
| Enllaços (email/web) | Blau RGB 0,0,255 |
| Text de la clàusula legal | Gris RGB 111,111,111 |
| Resolució de la imatge | 96 dpi |
| Alçada del senyal | 8,1 mm |
| Alçada icones xarxes socials | Màxim 15 px |
| Color icones xarxes socials | Gris RGB 153,153,153 |

### 3 variants

| Variant | Quan usar |
|---------|-----------|
| **1. Sense imatge** (text only) | Correus lleugers; quan no es vol imatge al peu |
| **2. Amb identificació bàsica** | Identificació amb el senyal de la Generalitat |
| **3. Amb identificació pròpia** | Organismes autònoms: logotip propi + senyal de la Generalitat |

### Plantilla — Variant 1 (sense imatge)

```
Nom i cognoms
Càrrec
Unitat o direcció general
Departament
Tel. 93 XXX XX XX
nom.cognoms@gencat.cat

[CLÀUSULA LEGAL — text oficial; vegeu la nota de sota]
[AVÍS D'IMPRESSIÓ — opcional]
```

### Exemple HTML (per a clients de correu compatibles)

```html
<div style="font-family: Arial, sans-serif; font-size: 12px; color: #000000; background: #FFFFFF;">
  <p style="margin: 0;"><strong>Núria Vila i Serra</strong></p>
  <p style="margin: 0;">Tècnica de comunicació</p>
  <p style="margin: 0;">Direcció General d'Atenció Ciutadana</p>
  <p style="margin: 0;">Departament de la Presidència</p>
  <p style="margin: 0;">Tel. 93 402 46 00</p>
  <p style="margin: 0;">
    <a href="mailto:nuria.vila@gencat.cat" style="color: #0000FF;">nuria.vila@gencat.cat</a>
  </p>
  <p style="margin: 10px 0 0; font-size: 10px; color: #6F6F6F;">
    [Clàusula legal oficial]
  </p>
</div>
```

### Clàusula legal

**Obligatòria i amb text oficial fixat** — disponible en 6 idiomes: català, castellà, anglès, francès, alemany i occità.

> **No redactis cap versió pròpia de la clàusula legal.** Copia el text exacte de les plantilles Word editables de la font oficial: https://identitatcorporativa.gencat.cat/ca/aplicacions/signatura-de-correu/

---

## Newsletters i comunicació digital

- **Tipografia:** Open Sans (veure `marca-visual.md` → Digital)
- **Colors:** vermell corporatiu com a color d'accent; fons blanc preferentment (veure `marca-visual.md` → Colors corporatius)
- **Senyal:** present a la capçalera o al peu

---

## Codis QR

- Aplicar el senyal corporatiu seguint les normes estàndard de mida mínima (≥ 4,7 mm)
- El codi QR no ha d'incloure elements visuals que dificultin la lectura
- Normes detallades: https://identitatcorporativa.gencat.cat/ca/aplicacions/codis-qr/
