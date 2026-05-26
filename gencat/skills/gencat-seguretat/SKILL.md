---
name: gencat-seguretat
description: "Aplica criteris de seguretat d'aplicacions quan dissenyes, revises o implementes serveis digitals de la Generalitat de Catalunya. Usa aquesta skill quan parlis d'autenticació, autorització, permisos, tokens, credencials, accés a documents o dades sensibles, peticions a API, protecció de secrets, sessions, controls d'accés o riscos de seguretat en aplicacions i serveis digitals."
---

# Seguretat d'aplicacions — Generalitat de Catalunya

Aquesta skill ajuda a revisar i orientar criteris de seguretat per a aplicacions i serveis digitals de la Generalitat de Catalunya. No substitueix una revisió de codi completa ni una auditoria de pentesting, però sí serveix per detectar riscos habituals i establir criteris de base coherents.

## Abast de la skill

### Què cobreix
- Autenticació i autorització
- Gestió de permisos i rols
- Ús segur de tokens, claus i credencials
- Protecció d'accés a documents, dades i recursos interns
- Revisió de peticions a API i fluxos que manipulen dades sensibles
- Bones pràctiques bàsiques de sessió, traçabilitat i exposició d'informació

### Què NO cobreix
- Implementació funcional del producte principal
- Disseny visual de components o interfície (delegar a `gencat-design-system`)
- Redacció de textos o microcopy (delegar a `gencat-comunicacio-clara`)
- Auditoria formal d'accessibilitat o compliment WCAG (delegar a `gencat-accessibilitat`)
- Revisió legal o de compliment normatiu específica de protecció de dades o ENS

### Skills complementàries
- `gencat-design-system` quan la seguretat afecta components o fluxos de UI
- `gencat-comunicacio-clara` per missatges d'error, alerta i confirmació
- `gencat-accessibilitat` per no comprometre l'ús per teclat, focus o feedback visible
- `gencat-documentacio-ctti` quan la seguretat s'hagi de reflectir en ERQ o DA

## Flux ràpid de revisió

1. Identifica si hi ha autenticació, permisos o dades sensibles.
2. Revisa si el flux exposa credencials, tokens o informació interna.
3. Comprova que l'accés es limita al mínim necessari.
4. Valida que els errors no revelen informació sensible.
5. Confirma que qualsevol recomanació concreta es pot documentar a `references/checklist-seguretat.md`.

## Checklist ràpid

- [ ] L'accés està protegit per autenticació si cal?
- [ ] Els permisos s'apliquen al servidor i no només a la UI?
- [ ] Els tokens i secrets no es mostren ni es registren innecessàriament?
- [ ] Les peticions a API validen permisos i propietat del recurs?
- [ ] Els errors no revelen dades internes ni detalls útils per a atacants?
- [ ] Les dades sensibles es transmeten i emmagatzemen amb proteccions adequades?
