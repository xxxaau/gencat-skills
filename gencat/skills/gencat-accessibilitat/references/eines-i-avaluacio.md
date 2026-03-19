# Eines d'Avaluació i Metodologia IRA — Gencat

## Eines recomanades per Gencat

### Avaluació automàtica (extensió de navegador / en línia)

| Eina | Plataforma | Ús | URL |
|------|-----------|-----|-----|
| **WAVE** | En línia + extensió Chrome/Firefox | Indicadors visuals d'accessibilitat, anàlisi de contrast | https://wave.webaim.org |
| **axe DevTools** | Extensió Chrome/Firefox | Biblioteca de regles WCAG extensa, sense falsos positius | https://www.deque.com/axe |
| **Siteimprove** | En línia + extensió | Ús intern Gencat; WCAG A/AA/AAA + qualitat | https://siteimprove.com |
| **HTML CodeSniffer** | Bookmarklet | Sense instal·lació | https://squizlabs.github.io/HTML_CodeSniffer/ |
| **TAW** | En línia | Disponible en català; WCAG 2.0 | https://www.tawdis.net |
| **AChecker** | En línia | Avaluació d'accessibilitat | https://achecker.achecks.ca |

### Validació de codi

| Eina | Ús | URL |
|------|----|-----|
| **W3C HTML Validator** | Validació HTML | https://validator.w3.org |
| **W3C CSS Validator** | Validació CSS | https://jigsaw.w3.org/css-validator/ |
| **Nu Html Checker** | Validador W3C millorat | https://validator.w3.org/nu/ |
| **W3C Unicorn** | HTML + CSS combinat | https://validator.w3.org/unicorn/ |

### Anàlisi manual (extensió de navegador)

| Eina | Ús | URL |
|------|----|-----|
| **HeadingsMap** | Visualitza jerarquia d'encapçalaments | Chrome Web Store / Firefox Add-ons |
| **Web Developer Toolbar** | Desactiva CSS, analitza imatges, mostra encapçalaments | https://chrispederick.com/work/web-developer/ |
| **Colour Contrast Analyser** (TPG) | Contrast W3C; aplicació d'escriptori | https://www.tpgi.com/color-contrast-checker/ |
| **WebAIM Contrast Checker** | Contrast en línia | https://webaim.org/resources/contrastchecker/ |
| **Link Contrast Checker** | Contrast d'enllaços vs text i fons | https://webaim.org/resources/linkcontrastchecker/ |

### Documents

| Eina | Ús | URL |
|------|----|-----|
| **PAC 2024** | Verificació d'accessibilitat de PDFs (WCAG 2.1) | Descarregable gratuïtament |
| **Adobe Acrobat Pro** | Verificació i reparació de PDFs | https://acrobat.adobe.com |

---

## Metodologia WCAG-EM (5 fases)

Metodologia oficial per a l'auditoria de llocs web. Base dels Informes de Revisió de l'Accessibilitat (IRA).

### Fase 1: Definició de l'abast
- Defineix el lloc web o app a avaluar
- Estableix el nivell de conformitat: **AA** (obligatori per a Gencat)
- Identifica les tecnologies d'assistència de referència
- Determina els tipus d'accés (escriptori, mòbil, etc.)

### Fase 2: Exploració del lloc web
- Identifica l'estructura general del lloc
- Analitza les tecnologies usades (HTML, CSS, JavaScript, frameworks)
- Identifica les pàgines representatives per tipus de contingut

### Fase 3: Selecció de la mostra
Pàgines obligatòries de la mostra:
- Pàgina principal (home)
- Avís legal
- Declaració d'accessibilitat
- Mapa web (si n'hi ha)
- Pàgina de contacte
- Pàgines que contenen: multimèdia, taules, formularis, imatges, PDFs
- Pàgines representatives de les seccions principals

### Fase 4: Auditoria de la mostra
Avalua els **137 criteris** de l'EN 301 549 V3.2.1 per a cada pàgina de la mostra:
- **C5** Generic requirements (3 criteris)
- **C6** ICT with two-way voice (1 criteri)
- **C7** ICT with video capabilities (9 criteris)
- **C9** Web (50 criteris — WCAG 2.1 A+AA)
- **C10** Non-web documents (49 criteris)
- **C11** Software/apps (6 criteris)
- **C12** Documentation (5 criteris)

### Fase 5: Documentació dels resultats
Crea l'Informe de Revisió de l'Accessibilitat (IRA) amb les 5 seccions obligatòries.

---

## Estructura de l'IRA (Informe de Revisió de l'Accessibilitat)

L'IRA és el document oficial d'auditoria d'accessibilitat. Plantilles en format ODS/XLSX disponibles a la web Gencat.

### Secció 1: Informació bàsica
- Nom i URL del lloc web
- Entitat responsable
- Data de l'avaluació i avaluador/a
- Abast de l'avaluació

### Secció 2: Tecnologies usades
- Versió HTML
- CSS
- WAI-ARIA
- JavaScript i frameworks
- Altres tecnologies rellevants

### Secció 3: Mostra de pàgines avaluades
- URL de cada pàgina
- Descripció del contingut representat

### Secció 4: Avaluació dels 137 criteris
Per a cada criteri, per a cada pàgina de la mostra:
- **Conforme** / **No conforme** / **No aplicable**
- Evidències i observacions

### Secció 5: Resultats i nivell de conformitat

| Estat | Condició |
|-------|---------|
| **Plenament conforme** | Tots els criteris aplicables complerts |
| **Parcialment conforme** | Majoria de criteris complerts |
| **No conforme** | Majoria de criteris no complerts |

**Escala de qualitat Gencat** (qualitat.solucions.gencat.cat):
| Puntuació | Criteri |
|-----------|---------|
| 5/5 | 100% conformitat Nivell A i AA |
| 4/5 | 100% Nivell A + 75–100% Nivell AA |
| 3/5 | 75–100% Nivells A+AA combinats |
| 2/5 | 50–75% combinat |
| 1/5 | Menys del 50% |

**Periodicitat**: Revisió completa manual cada **màxim 3 anys** (RD 1112/2018). Monitoratge automàtic continuat recomanat.

---

## Declaració d'Accessibilitat

Obligatòria per a tots els llocs web i apps de la Generalitat. Ha de contenir:

1. **Estat de conformitat**: plenament / parcialment / no conforme
2. **Seccions inaccessibles**: identificació, raons, alternatives disponibles
3. **Mecanisme de comunicació**: com reportar incompliments
4. **Procés de sol·licitud d'informació / reclamació**
5. **Procediment d'escalada**: si la resposta no és satisfactòria

**Ubicació**: al mateix lloc web (webs) o al web oficial (apps).
**Plantilles oficials** disponibles en 6 idiomes: català, castellà, aranès, anglès, francès, alemany.

---

## Calendari de compliment (RD 1112/2018)

| Data | Obligació |
|------|-----------|
| 20/09/2019 | Nous webs (publicats des del 20/09/2018) han de ser accessibles |
| 20/09/2020 | **Tots els webs existents** han de ser accessibles |
| 23/06/2021 | Apps mòbils han de ser accessibles |
| Màx. cada 3 anys | Revisió manual completa (IRA) |

---

## Guia ràpida: ordre de prioritat per a un nou projecte

### En fase de disseny (abans de codificar)
1. Defineix la paleta de colors i verifica ratios de contrast (1.4.3, 1.4.11)
2. Dissenya estats de focus visibles per a tots els components interactius (2.4.7)
3. Planifica l'estructura d'encapçalaments (1.3.1)
4. Revisa que la informació no depèn únicament del color (1.4.1)

### En fase de desenvolupament
1. HTML semàntic i vàlid (4.1.1)
2. `<html lang="ca">` i títols de pàgina descriptius (3.1.1, 2.4.2)
3. Skip link al body (2.4.1)
4. Labels per a tots els inputs (3.3.2, 4.1.2)
5. Alt text per a totes les imatges (1.1.1)
6. Focus trap i gestió de focus per a modals (2.1.1, 2.1.2)
7. `aria-live` per a contingut dinàmic (4.1.3)

### Abans del desplegament
1. Verificació automàtica: WAVE + axe (detecta ~30% dels errors)
2. Prova de navegació per teclat completa
3. Verificació de contrast amb Colour Contrast Analyser
4. Validació HTML amb W3C Validator
5. Test amb lector de pantalla (NVDA + Firefox o VoiceOver + Safari)

### Recursos de referència
- WCAG 2.1 en català: https://www.w3.org/Translations/WCAG21-ca/
- WCAG 2.2 en català: https://www.w3.org/Translations/WCAG22-ca/
- Hub accessibilitat Gencat: https://atenciociutadana.gencat.cat/ca/serveis/webs/accessibilitat/
- Guia d'avaluació Gencat: https://qualitat.solucions.gencat.cat/guies/accessibilitat_web/
- EN 301 549 V3.2.1 (PDF): https://www.etsi.org/deliver/etsi_en/301500_301599/301549/03.02.01_60/en_301549v030201p.pdf
