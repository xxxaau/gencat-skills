# Estructura DA — Descripció d'Arquitectura

Font oficial (AiDA): https://canigo.ctti.gencat.cat/arquitectura/da/aida/

---

## Tipus d'arquitectura suportats

Abans de validar, confirmar el tipus:
- **Cloud Privat** — infraestructura CTTI gestionada
- **Cloud Públic** — hyperscaler (Azure, AWS, GCP)
- **SaaS** — solució de software com a servei
- **Low Code** — plataformes low-code (Power Platform, Mendix, etc.)
- **On-Premise** — infraestructura pròpia del departament

Si el tipus no consta al document: preguntar: "Quin tipus d'arquitectura és? (Cloud Privat, Cloud Públic, SaaS, Low Code, On-Premise)"

**Arquitectures mixtes** (p. ex. Cloud Públic per a l'aplicatiu + On-Premise per a una BD legacy):
- Aplicar les vistes obligatòries del **tipus principal** (el que cobreix la major part del sistema)
- Afegir les vistes dels tipus secundaris quan siguin rellevants (p. ex. Vista Operacional per al component On-Premise)
- Exigir que la Vista de Context identifiqui explícitament cada tipus i la seva responsabilitat
- Si no és clar quin tipus predomina, preguntar-ho abans de validar

---

## Matriu de vistes obligatòries per tipus

| Vista | Cloud Privat | Cloud Públic | SaaS | Low Code | On-Premise |
|-------|:-----------:|:------------:|:----:|:--------:|:----------:|
| Context | ✓ | ✓ | ✓ | ✓ | ✓ |
| Funcional | ✓ | ✓ | ✓ | ✓ | ✓ |
| Informació | ✓ | ✓ | ✓ | ✓ | ✓ |
| Concurrència | ✓ | ✓ | ✓ | ✓ | ✓ |
| Desenvolupament | ✓ | ✓ | — | — | ✓ |
| Desplegament | ✓ | ✓ | — | ✓ | ✓ |
| Operacional | ✓ | ✓ | — | — | ✓ |

**Low Code:** Desplegament és obligatòria perquè cal documentar les integracions i configuracions de la plataforma. Desenvolupament i Operacional no apliquen perquè la plataforma Low Code els gestiona transparentment.

**SaaS:** Només les 4 vistes de base (Context, Funcional, Informació, Concurrència) — el proveïdor SaaS gestiona la resta.

Avaluació: ✅ present amb contingut | ❌ absent/buida i obligatòria | N/A no aplica al tipus

---

## Requisits de contingut per vista

### Vista de Context
Ha d'incloure:
- Diagrama o descripció de les relacions del sistema amb actors externs i sistemes adjacents
- Identificació dels sistemes d'integració (GICAR, PICA, e.notum, etc.)
- Fluxos d'informació principals entre sistemes

❌ Errors habituals:
- Diagrama sense llegenda o amb sistemes no identificats
- Integracions mencionades al text però no reflectides al diagrama
- Manca d'identificació dels protocols d'integració (REST, SOAP, missatgeria)

### Vista Funcional
Ha d'incloure:
- Descomposició del sistema en components o mòduls funcionals
- Responsabilitats de cada component
- Interaccions i dependències entre components

❌ Errors habituals:
- Components sense responsabilitats definides
- Manca de descripció de les interfícies entre components
- Diagrama de components sense text explicatiu

### Vista d'Informació
Ha d'incloure:
- Model de dades principal (entitats i relacions)
- Fluxos d'informació entre components
- Polítiques de persistència i retenció de dades

❌ Errors habituals:
- Model de dades sense atributs o tipus
- Manca de referència al RGPD si es tracten dades personals
- No s'especifica on es desen les dades (BD relacional, documental, fitxers...)

### Vista de Concurrència
Ha d'incloure:
- Processos i fils d'execució principals
- Mecanismes de sincronització o cues de missatges
- Gestió d'estats i transaccions

❌ Errors habituals:
- Vista buida o amb text genèric ("el sistema és stateless") sense justificació
- Manca de descripció de com es gestionen les concurrències crítiques
- No s'esmenten cues o batches si el sistema en fa servir

### Vista de Desenvolupament
*(No aplica a SaaS ni Low Code)*

Ha d'incloure:
- Stack tecnològic: llenguatges, frameworks, versions
- Estructura de paquets o mòduls del codi
- Dependències externes i llibreries principals
- Alineació amb el full de ruta tecnològic del CTTI

❌ Errors habituals:
- Tecnologies no alineades amb el full de ruta CTTI sense justificació
- Versions no especificades (p. ex. "Java" sense indicar versió)
- Manca d'estructura de paquets o repositoris

### Vista de Desplegament
*(No aplica a SaaS)*

Ha d'incloure:
- Diagrama d'infraestructura: servidors, contenidors, xarxes
- Entorns: desenvolupament, preproducció, producció
- Estratègia de desplegament (CI/CD, blue-green, canary...)

❌ Errors habituals:
- Diagrama d'infraestructura sense especificar mides/capacitats
- Manca de descripció dels entorns pre-productius
- No s'especifica com es fan els desplegaments (manual, automatitzat)

### Vista Operacional
*(No aplica a SaaS ni Low Code)*

Ha d'incloure:
- Monitoratge i alertes: eines, mètriques clau
- Còpies de seguretat: política, freqüència, retenció
- Recuperació davant desastres (RTO/RPO)
- Procediments d'operació habituals

❌ Errors habituals:
- Manca de RTO/RPO per a sistemes crítics
- Monitoratge sense especificar mètriques ni llindars d'alerta
- No s'especifica qui és responsable de les operacions (equip CTTI, proveïdor, departament)
