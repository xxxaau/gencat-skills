# gencat-skills

Plugin de Claude Code amb les skills corporatives de la **Generalitat de Catalunya**.

## Instal·lació

```bash
# Registra el marketplace
/plugin marketplace add gencat/gencat-skills

# Instal·la el plugin
/plugin install gencat@gencat-skills
```

O afegeix manualment a `~/.claude/settings.json`:

```json
"extraKnownMarketplaces": {
  "gencat-skills": {
    "source": {
      "source": "github",
      "repo": "gencat/gencat-skills"
    }
  }
}
```

## Skills disponibles

### `gencat-design-system`
Aplica el [Sistema de Disseny](https://sistemadedisseny.gencat.cat) oficial de la Generalitat quan desenvolupes interfícies web. Inclou:
- Colors, tipografia i tokens CSS corporatius
- Catàleg complet de components (60+) amb nomenclatura oficial en català
- Patrons per a formularis, àrea privada, cercadors i gestió interna
- Regles d'accessibilitat WCAG

**S'activa** quan menciones Gencat, Generalitat de Catalunya, o desarrolles components per a serveis digitals catalans.

---

### `gencat-comunicacio-clara`
Genera literals i textos per a UI seguint la [Guia de Comunicació Clara](https://atenciociutadana.gencat.cat/ca/comunicacio-clara/) (2025), basada en la norma UNE-ISO 24495-1. Inclou:
- Regles de redacció: veu activa, frases curtes, ordre natural
- Vocabulari planer: substitucions administratiu → comú
- Patrons per a botons, errors, confirmacions, etiquetes i avisos
- Llengua inclusiva i tractament consistent

**S'activa** quan generes textos, literals o missatges per a aplicacions corporatives de la Generalitat.

---

### `gencat-accessibilitat`
Garanteix el compliment de les directrius d'accessibilitat digital de la Generalitat, basades en el [Decret 216/2023](https://dogc.gencat.cat/ca/document-del-dogc/?documentId=973470), l'EN 301 549 V3.2.1 i la [WCAG 2.1 AA](https://www.w3.org/Translations/WCAG21-ca/). Inclou:
- 50 criteris WCAG A+AA obligatoris amb implementació tècnica
- 12 errors habituals en webs Gencat amb correccions i exemples de codi
- Patrons HTML/ARIA per a 15+ components accessibles
- Metodologia IRA/WCAG-EM i eines d'avaluació recomanades

**S'activa** quan implementes o revises components, formularis, navegació, contingut multimèdia o qualsevol interfície per a serveis Gencat.

---

### `gencat-seguretat`
Orienta sobre seguretat d'aplicacions quan treballes amb autenticació, permisos, tokens, credencials, accés a documents o dades sensibles i peticions a API. Inclou:
- Criteris de mínim privilegi i validació d'accés al servidor
- Bones pràctiques per a tokens, claus, secrets i sessions
- Revisió de riscos en fluxos amb dades sensibles o recursos interns
- Checklist pràctica amb enllaços a referències OWASP

**S'activa** quan revises o dissenyes fluxos de login, autorització, gestió de permisos, protecció de dades o qualsevol funcionalitat amb risc de seguretat aplicacional.

---

### `gencat-tramits`
Aplica el [Manual de redacció i estil de fitxes de tràmit](https://atenciociutadana.gencat.cat/ca/serveis/tramits/manuals-i-guies/) (febrer 2026) quan redactes o revises fitxes de tràmit per a gencat.cat. Inclou:
- Regles de redacció per a tots els camps: títol, descripció, requisits, documentació, terminis, taxes
- Passos de tramitació i textos estàndard obligatoris
- Vocabulari i substitucions per a un llenguatge clar i proper
- Tractament personal coherent (tu / vós) i frases de 20-30 paraules

**S'activa** quan treballes amb tràmits administratius, fitxes de tràmit, GECO, OGE, SAC o qualsevol camp d'una fitxa de tràmit gencat.

---

### `gencat-xarxes-socials`
Genera i revisa contingut per a xarxes socials seguint la [Guia de Xarxes Socials](https://atenciociutadana.gencat.cat/web/.content/manuals/xarxes/guia_xarxa.pdf) de la Generalitat. Inclou:
- Normes específiques per a 7 plataformes: X (Twitter), Facebook, Instagram, LinkedIn, YouTube, Threads i TikTok
- Workflow dual: GENERAR (des de zero) i REVISAR (amb informe ✅/⚠️/❌)
- 6 plantilles reutilitzables: avís, convocatòria, emergència, campanya, resposta a comentari, fil/thread
- Normes d'accessibilitat transversals: alt text, CamelCase en hashtags, emojis

**S'activa** quan generes o revises posts, publicacions, hashtags, fils o qualsevol contingut per a xarxes socials institucionals de la Generalitat.

---

### `gencat-identitat-corporativa`
Aplica les normes d'[Identitat Corporativa](https://www.gencat.cat/web/.content/manuals/guia_identitatcorporativa_2023.pdf) de la Generalitat quan crees o revises materials de comunicació. Inclou:
- Colors corporatius (Pantone, CMYK, RGB, Hex), tipografia per suport i normes d'ús del senyal
- Normes per a documents Word, PowerPoint i PDF institucionals
- Signatures de correu electrònic i newsletters
- Workflow de validació amb modes CONSULTAR, CREAR i VALIDAR

**S'activa** quan crees o revises documents, presentacions, materials de comunicació o qualsevol element visual d'una entitat de la Generalitat de Catalunya.

---

### `gencat-documentacio-ctti`
Valida i redacta documentació tècnica seguint els estàndards del [CTTI](https://ctti.gencat.cat) (Centre de Telecomunicacions i Tecnologies de la Informació). Inclou:
- Estructura obligatòria de l'ERQ (Especificació de Requisits) i el DA (Descripció d'Arquitectura)
- Criteris de qualitat i escala de puntuació per a la revisió de documents tècnics
- Modes REVISAR (informe detallat amb puntuació) i CONSULTAR (resposta directa)
- Detecció automàtica del tipus de document i càrrega dinàmica de referències

**S'activa** quan treballes amb documents tècnics CTTI, ERQ, DA, arquitectures de sistemes o documentació d'aprovisionament de la Generalitat de Catalunya.

---

## Criteri comú d'abast i combinació

Per mantenir el repositori coherent i evitar solapaments, cada skill defineix:

- **Què cobreix**: l'àmbit principal de treball
- **Què NO cobreix**: límits explícits de la skill
- **Skills complementàries**: quines skills cal combinar segons el cas

Combinacions recomanades més habituals:

- **gencat-tramits** + **gencat-comunicacio-clara** + **gencat-accessibilitat**
- **gencat-design-system** + **gencat-accessibilitat** + **gencat-comunicacio-clara**
- **gencat-seguretat** + **gencat-accessibilitat** + **gencat-comunicacio-clara** quan hi ha login, permisos, dades sensibles o fluxos amb API
- **gencat-xarxes-socials** + **gencat-comunicacio-clara** (+ **gencat-identitat-corporativa** quan hi ha requeriments de marca)
- **gencat-documentacio-ctti** (+ **gencat-accessibilitat** o **gencat-design-system** quan hi ha requisits funcionals de UI o no funcionals)

---

## Estructura del repositori

```
gencat-skills/
└── gencat/                          ← plugin
    ├── README.md
    ├── package.json
    └── skills/
        ├── gencat-design-system/
        │   ├── SKILL.md
        │   └── references/
        │       ├── foundations.md        ← colors, tipografia, tokens CSS
        │       ├── components.md         ← catàleg de components
        │       └── patterns.md           ← patrons d'ús
        ├── gencat-comunicacio-clara/
        │   ├── SKILL.md
        │   └── references/
        │       ├── redaccio.md           ← 10 pilars, veu activa, nominalitzacions
        │       ├── vocabulari.md         ← substitucions, anglicismes, inclusiu
        │       ├── ui-literals.md        ← botons, errors, formularis, avisos
        │       └── titols-i-estructura.md ← títols, llistes, format
        ├── gencat-accessibilitat/
        │   ├── SKILL.md
        │   └── references/
        │       ├── wcag-criteris.md      ← 50 criteris A+AA + WCAG 2.2
        │       ├── errors-habituals.md   ← 12 errors freqüents + correccions
        │       ├── components-accessibles.md ← patrons HTML/ARIA
        │       └── eines-i-avaluacio.md  ← eines, IRA, metodologia
        ├── gencat-seguretat/
        │   ├── SKILL.md
        │   └── references/
        │       └── checklist-seguretat.md ← checklist i referències OWASP
        ├── gencat-documentacio-ctti/
        │   ├── SKILL.md
        │   └── references/
        │       ├── erq-estructura.md     ← seccions obligatòries ERQ
        │       ├── da-estructura.md      ← seccions obligatòries DA
        │       ├── criteris-qualitat.md  ← criteris de qualitat global
        │       └── puntuacio-i-informe.md ← escala de puntuació i informe
        ├── gencat-identitat-corporativa/
        │   ├── SKILL.md
        │   └── references/
        │       ├── marca-visual.md       ← colors, tipografia, senyal, logotip
        │       ├── documents.md          ← Word, PowerPoint, PDF institucionals
        │       ├── comunicacio-digital.md ← signatures de correu, newsletters
        │       └── validacio.md          ← workflow de validació
        ├── gencat-tramits/
        │   ├── SKILL.md
        │   └── references/
        │       ├── camps.md              ← regles per a cada camp de la fitxa
        │       ├── passos.md             ← passos de tramitació i textos estàndard
        │       ├── vocabulari.md         ← substitucions i bones pràctiques
        │       └── revisio-web.md        ← workflow revisió fitxes a gencat.cat
        └── gencat-xarxes-socials/
            ├── SKILL.md
            └── references/
                ├── x-twitter.md          ← normes X (Twitter)
                ├── facebook.md           ← normes Facebook
                ├── instagram.md          ← normes Instagram
                ├── linkedin.md           ← normes LinkedIn
                ├── youtube.md            ← normes YouTube (elements textuals)
                ├── threads.md            ← normes Threads
                ├── tiktok.md             ← normes TikTok (elements textuals)
                └── plantilles.md         ← 6 plantilles reutilitzables
```

## Contribució

Les skills segueixen el format estàndard de Claude Code. Consulta la [documentació de skills](https://docs.anthropic.com/claude-code/plugins) per a contribuir.

## Llicència

CC0 1.0 Universal — igual que la documentació oficial de la Generalitat de Catalunya.
