# gencat-skills — Guia de treball per a agents

Repo de skills corporatives de la Generalitat en format obert [Agent Skills](https://agentskills.io/specification). Projecte en fase d'investigació. Idioma de tot (contingut, commits, respostes): **català**.

## Estructura

- `gencat/skills/<nom>/SKILL.md` + `references/*.md` — una skill per directori.
- `.claude-plugin/` — manifests de marketplace i plugin (Claude Code); `.github/workflows/validate-skills.yml` — CI de validació.
- El repo real és `xxxaau/gencat-skills` (no `gencat/gencat-skills`).

## Convencions per crear o modificar una skill

1. **Frontmatter** (obligatori i res més): `name` (= nom del directori, minúscules i guions), `description` (què fa + quan activar-la, ≤1024 caràcters, amb paraules clau d'activació), `license: CC0-1.0`, `metadata:` amb `author: Generalitat de Catalunya` i `version` (string entre cometes).
2. **Progressive disclosure**: SKILL.md < 500 línies; el detall va a `references/` i es referencia amb ruta relativa (`references/x.md`), mai més d'un nivell.
3. **Agnòstic d'agent**: mai instruccions que depenguin d'eines concretes (WebFetch, Read, Playwright...). Formulació genèrica ("l'eina de lectura web de l'agent") amb l'eina concreta només com a exemple entre parèntesis.
4. **Abast**: cada SKILL.md manté les seccions "Què cobreix / Què NO cobreix / Skills complementàries". Les referències cross-skill (llegir fitxers d'una altra skill) sempre amb fallback explícit ("si no està instal·lada, continua amb...") — les skills es poden instal·lar individualment amb `npx skills --skill`.
5. **Valors canònics, no duplicats**: el vermell `#C00000` només es defineix a `gencat-identitat-corporativa/references/marca-visual.md` (marca, Pantone 485) i a `gencat-design-system/references/foundations.md` (tokens digitals). A tot arreu més: el token `--color-brand-primary`. Mateix criteri per a qualsevol altre valor de marca: una font canònica, referències a la resta.
6. Si afegeixes o reanomenes una skill: sincronitza la fitxa i l'arbre d'estructura del `README.md`, la taula de `gencat/README.md` i la descripció de `.claude-plugin/plugin.json`.

## Checklist de revisió abans de commitejar

- [ ] **Validació d'especificació**: el CI ho fa amb `skills-ref`; en local, valida frontmatter (YAML vàlid, name = directori, description dins de límits, metadata string→string). Nota: instal·lar `skills-ref` en local via pip+git pot quedar bloquejat pel sandbox — un script Python propi és el fallback acceptat.
- [ ] **Descoberta**: `npx -y skills add <ruta-local-del-repo> --list` ha de trobar les 7 skills (o el nou total).
- [ ] **Acoblament**: `grep -riE "claude|webfetch|playwright" gencat/skills/` → només mencions com a exemple entre parèntesis.
- [ ] **Referències relatives**: tota menció `references/x.md` dins d'una skill ha d'existir; les cross-skill també (a l'altra skill).
- [ ] **Enllaços externs** (si se n'han tocat o periòdicament): comprovar amb doble mètode — peticions HTTP amb User-Agent de navegador i, per als que fallin, re-verificar amb WebFetch abans de declarar-los trencats (W3C i similars retornen 403 anti-bot als scripts però funcionen). Els fixos es corregeixen amb substitut verificat, mai s'eliminen sense mirar si hi ha URL nova.
- [ ] **Diff complet** llegit línia a línia abans del commit.
- [ ] Després del push: comprovar que el workflow "Valida les skills" passa (`gh run list`).

## Distribució

- Multi-agent: `npx skills add xxxaau/gencat-skills` (estàndard Agent Skills, 70+ agents).
- Claude Code: `/plugin marketplace add xxxaau/gencat-skills` + `/plugin install gencat@gencat-skills`.
- Els warnings `LF will be replaced by CRLF` de git a Windows són normals (autocrlf), no un problema.
