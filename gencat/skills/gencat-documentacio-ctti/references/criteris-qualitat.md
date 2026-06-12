# Criteris de Qualitat — ERQ i DA

Els 5 criteris s'avaluen **globalment** per al document sencer (no per secció ni vista).
Cada criteri es puntua **una sola vegada**, independentment de quantes seccions el violin.

**Seccions/vistes opcionals presents:** si la secció opcional existeix però té problemes, les
penalitzacions s'apliquen sempre al ritme de ⚠️ (−5) independentment de la gravetat.

---

## 1. Claredat

Avalua si la redacció és unívoca i interpretable per qualsevol membre de l'equip.

| Estat | Criteri | Exemples |
|-------|---------|---------|
| ✅ | Tota la redacció té una sola interpretació possible | "El sistema denegarà l'accés i mostrarà el missatge ERR-401 si les credencials no són vàlides" |
| ⚠️ | Redacció vaga en punts concrets o en seccions secundàries (afecta **menys d'un terç** del document) | "El sistema gestionarà els errors adequadament" en una secció de suport |
| ❌ | Redacció ambigua estesa (**un terç o més** del document) o en seccions/vistes obligatòries senceres | "El sistema processarà les sol·licituds de forma òptima" com a patró repetit (ERQ) / "L'arquitectura ha de ser flexible" com a única descripció (DA) |

Preguntes de detecció:
- Podrien dos developers implementar-ho de manera diferent llegint el mateix text?
- Hi ha adjectius subjectius sense criteri mesurable? (ràpid, senzill, robust, escalable, flexible)

---

## 2. Detall suficient

Avalua si el document té prou informació per implementar sense haver de prendre decisions de disseny no documentades.

> **Frontera amb Verificabilitat (evita la doble penalització):** si **falta informació** (no hi ha mètrica, no hi ha flux d'error), penalitza només *Detall suficient*. Si la informació hi és però **no es pot comprovar objectivament** (condicions vagues, xifres sense context), penalitza només *Verificabilitat*. Un mateix defecte no pot puntuar ❌ als dos criteris.

| Estat | Criteri | Exemples |
|-------|---------|---------|
| ✅ | Cada funcionalitat/vista té flux, condicions i resposta del sistema | Cas d'ús amb flux principal, fluxos d'error i postcondicions |
| ⚠️ | Detall mínim però incomplet — cal inferir alguns comportaments | Cas d'ús amb flux principal però sense fluxos d'error |
| ❌ | Falta informació essencial per implementar | Requisit "RF-012: Gestió d'usuaris" sense cap detall / Vista de Desplegament buida |

Preguntes de detecció (ERQ):
- Pot un developer implementar cada RF sense preguntar res?
- Estan coberts els casos d'error i els límits de cada funcionalitat?

Preguntes de detecció (DA):
- Pot un arquitecte fer el disseny tècnic detallat a partir d'aquesta DA?
- Estan justificades les decisions d'arquitectura clau?

---

## 3. Consistència

Avalua la coherència interna del document: que no hi hagi contradiccions entre seccions/vistes.

| Estat | Criteri | Exemples |
|-------|---------|---------|
| ✅ | Cap contradicció entre seccions; terminologia uniforme | El mateix concepte s'anomena igual a tot el document |
| ⚠️ | Inconsistències menors de terminologia | "expedient" i "sol·licitud" usats per al mateix concepte |
| ❌ | Contradicció directa entre seccions | RF-005 diu "l'usuari pot modificar" però el cas d'ús diu que és de "només lectura" / Vista Funcional descriu un component que no apareix a la Vista de Desplegament |

Preguntes de detecció:
- Hi ha termes que s'usen de manera diferent en seccions/vistes diferents?
- Les entitats del model de dades (Informació) coincideixen amb les mencionades als RF o a la Vista Funcional?

---

## 4. Verificabilitat

Avalua si cada requisit o decisió d'arquitectura es pot comprovar objectivament.

| Estat | Criteri | Exemples |
|-------|---------|---------|
| ✅ | Criteri d'acceptació clar i mesurable | "Temps de resposta < 2 s per al 95% de les peticions amb càrrega de 100 usuaris simultanis" |
| ⚠️ | Criteri poc precís però parcialment mesurable | "Temps de resposta acceptable en condicions normals d'ús" |
| ❌ | No és comprovable | "El sistema ha de ser ràpid i fàcil d'usar" / "L'arquitectura ha de ser escalable" |

Paraules de risc (probable ❌ si no s'acompanyen de xifres):
- ràpid, lent, eficient, òptim, escalable, robust, flexible, segur, fàcil, intuïtiu, modern

---

## 5. Traçabilitat

Avalua si es pot seguir l'origen de cada requisit o decisió fins a una necessitat de negoci documentada. Per a una DA, inclou també la **traçabilitat cap als RF de l'ERQ associat** (si n'hi ha o es revisen junts).

| Estat | Criteri | Exemples |
|-------|---------|---------|
| ✅ | Cada RF/vista referencia el seu origen (necessitat de negoci, normativa, cas d'ús). En una DA: components i integracions traçables als RF | "RF-015 [origen: requeriment legal RGPD art. 17]" / Vista Funcional: "El component de tràmits implementa RF-001 a RF-010" |
| ⚠️ | Traçabilitat parcial — alguns RF o decisions sense origen documentat | La majoria de RF tenen origen però uns quants no / Alguns components de la DA no es relacionen amb cap RF |
| ❌ | Cap referència a l'origen de cap requisit o decisió | Document que llista RF numerats sense cap referència a objectius de negoci o normativa / DA desconnectada del seu ERQ |

Preguntes de detecció:
- Si un stakeholder demana "per què tenim aquest requisit?", pot el document respondre-ho?
- Les decisions d'arquitectura clau (DA) justifiquen per què s'ha triat una solució sobre les alternatives?
- (DA amb ERQ conegut) Les integracions i components esmentats a l'ERQ apareixen a les vistes? Hi ha components a la DA que cap RF justifica?
