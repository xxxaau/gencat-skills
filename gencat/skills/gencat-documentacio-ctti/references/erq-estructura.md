# Estructura ERQ — Especificació de Requisits (DT_ERQ)

Font oficial: https://qualitat.solucions.gencat.cat/procediments/analisi-disseny/especificacio_requisits/

---

## Seccions obligatòries

| Secció | Obligatòria | Avaluació |
|--------|-------------|-----------|
| Visió general del sistema | Sí | ✅ present amb contingut / ❌ absent o buida |
| Usuaris de la solució | Sí | ✅ present amb contingut / ❌ absent o buida |
| Requisits funcionals | Sí | ✅ present amb contingut / ❌ absent o buida |
| Requisits no funcionals | Sí | ✅ present amb contingut / ❌ absent o buida |
| Casos d'ús o fluxos funcionals | Sí | ✅ present amb contingut / ❌ absent o buida |
| Informació de suport | Opcional | Vegeu regla especial |

---

## Requisits de contingut per secció

### 1. Visió general del sistema
Ha d'incloure:
- **Abast**: què fa el sistema i què queda fora
- **Context**: diagrama de context o descripció de les integracions amb sistemes externs
- **Mòduls funcionals**: llista o descripció dels grans blocs funcionals

❌ Errors habituals:
- Abast massa vague ("sistema de gestió d'expedients" sense especificar quins tipus)
- Context sense mencionar sistemes externs o integracions
- Manca de mòduls funcionals — no queda clar com s'organitza el sistema

### 2. Usuaris de la solució
Ha d'incloure:
- **Perfils d'usuari**: nom del rol i descripció breu
- **Responsabilitats**: què pot fer cada perfil
- **Accés**: si hi ha diferències de permisos entre perfils

❌ Errors habituals:
- Llista de rols sense cap descripció de les seves responsabilitats
- Manca del perfil d'administrador o gestor si el sistema en necessita
- Confusió entre "usuari" (persona) i "sistema extern" (integració)

### 3. Requisits funcionals
Ha d'incloure:
- **Identificador únic** per requisit (p. ex. RF-001)
- **Un requisit per ítem** — no agrupar múltiples comportaments
- **Subjecte clar**: qui fa l'acció o quin sistema ha de fer-la
- **Comportament verificable**: com es comprova que es compleix

❌ Errors habituals:
- Requisits sense identificador (impossibles de traçar)
- Un ítem amb múltiples requisits: "El sistema ha de fer X i també Y i permetre Z"
- Requisits no verificables: "el sistema ha de ser intuïtiu", "ha de respondre ràpidament"
- Manca de requisits de seguretat i de tractament de dades personals (RGPD)

### 4. Requisits no funcionals
Ha d'incloure com a mínim:
- **Rendiment**: temps de resposta esperats, càrrega concurrent
- **Seguretat**: autenticació, autorització, xifratge, auditoria
- **Disponibilitat**: SLA, finestres de manteniment

❌ Errors habituals:
- Valors no quantificats: "ha de ser ràpid" (sense xifres), "alta disponibilitat" (sense percentatge)
- Manca de requisits de seguretat tot i que el sistema tracti dades personals
- Secció present però buida o amb text genèric copiat

### 5. Casos d'ús o fluxos funcionals
Ha d'incloure per a cada cas d'ús:
- **Actor principal**
- **Precondicions**
- **Flux principal** (passos numerats)
- **Fluxos alternatius / d'error** (si escau)
- **Postcondicions**

❌ Errors habituals:
- Cas d'ús sense flux principal detallat (només títol)
- Manca de fluxos d'error per a operacions crítiques (login, pagament, signatura)
- Actor no identificat o genèric ("l'usuari" sense especificar quin perfil)

---

## Regla especial: Informació de suport (opcional)

Aquesta secció **no es penalitza si és absent**.

S'afegeix una nota ⚠️ informativa (sense deducció de punts) quan:
- El document fa referència a entitats de dades sense definir-les
- El document menciona pantalles o mockups sense que existeixin

Si la secció **és present** però té problemes de qualitat, les penalitzacions s'apliquen al ritme de ⚠️ (−5) independentment de la gravetat (vegeu `criteris-qualitat.md`).

Contingut recomanat quan és present:
- Diccionari de dades o model d'entitats
- Mockups o wireframes referenciats al document
- Models analítics o càlculs complexos
