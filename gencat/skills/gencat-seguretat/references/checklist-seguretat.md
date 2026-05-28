# Checklist de seguretat d'aplicacions

## Objectiu
Aquesta referència resumeix els punts mínims que cal revisar quan una funcionalitat tracta autenticació, permisos, tokens, accés a documents o dades sensibles.

## Referències institucionals de qualitat 

- Model de Qualitat de Solucions: https://qualitat.solucions.gencat.cat/
- Quality Gates: https://qualitat.solucions.gencat.cat/qualitygates

Quan la seguretat forma part d'un projecte amb lliurables o gates de qualitat, aquests enllaços ajuden a alinear la revisió amb el marc oficial.

## Punts de revisió

### Identitat i accés
- Hi ha autenticació quan la funcionalitat dona accés a dades o accions sensibles?
- L'autorització es valida al servidor i no només a la interfície?
- Els rols i permisos es defineixen amb el principi de mínim privilegi?
- L'usuari només veu i manipula els recursos que li corresponen?

### Tokens i credencials
- Els tokens, claus i secrets no apareixen en logs, respostes ni pantalles?
- Les credencials es guarden i transmeten amb protecció adequada?
- Hi ha expiració, revocació o rotació quan escau?

### API i dades
- Cada petició a l'API valida autenticació i permisos?
- Es comprova la propietat del recurs abans de retornar o modificar dades?
- Les dades sensibles s'anonimitzen o minimitzen quan no són necessàries?
- Els errors eviten exposar estructura interna, IDs o detalls tècnics innecessaris?

### Sessió i rastreig
- La sessió expira quan toca i es tanca correctament?
- Els canvis sensibles queden registrats amb traçabilitat suficient?
- Els missatges d'error i auditoria no revelen informació delicada?

### Enllaços de referència
- OWASP Top 10: https://owasp.org/Top10/2025/
- OWASP ASVS: https://owasp.org/www-project-application-security-verification-standard/
- OWASP Cheat Sheet Series: https://cheatsheetseries.owasp.org/

## Criteri pràctic
Si una funcionalitat permet llegir, modificar o exportar dades sensibles, la pregunta mínima és: qui hi pot accedir, com es valida i què passa si falla.
