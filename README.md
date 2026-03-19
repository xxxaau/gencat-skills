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
        │       ├── foundations.md   ← colors, tipografia, tokens CSS
        │       ├── components.md    ← catàleg de components
        │       └── patterns.md      ← patrons d'ús
        └── gencat-comunicacio-clara/
            ├── SKILL.md
            └── references/
                ├── redaccio.md      ← 10 pilars, veu activa, nominalitzacions
                ├── vocabulari.md    ← substitucions, anglicismes, inclusiu
                ├── ui-literals.md   ← botons, errors, formularis, avisos
                └── titols-i-estructura.md  ← títols, llistes, format
```

## Contribució

Les skills segueixen el format estàndard de Claude Code. Consulta la [documentació de skills](https://docs.anthropic.com/claude-code/plugins) per a contribuir.

## Llicència

CC0 1.0 Universal — igual que la documentació oficial de la Generalitat de Catalunya.
