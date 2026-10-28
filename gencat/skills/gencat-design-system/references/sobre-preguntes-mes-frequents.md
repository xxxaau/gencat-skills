# Preguntes més freqüents

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/72240b · Font actualitzada el 2024-12-11 · Extret el 2026-10-28

Respostes a les preguntes més habituals sobre el funcionament del sistema de disseny.

## General

### 1. Què és un sistema de disseny?
Es tracta d'un conjunt de principis, normes, components i directrius que s'utilitzen de manera consistent en el desenvolupament de productes o serveis per garantir coherència i eficiència en el disseny i desenvolupament.

### 2. Per què és important un sistema de disseny?
Un sistema de disseny garanteix la coherència visual i funcional en tots els productes o serveis d'una organització. Ajuda a reduir els temps de desenvolupament, facilita la col·laboració entre equips i millora l'experiència de l'usuari.

### 3. Qui utilitza el sistema de disseny?
El sistema pot ser usat per dissenyadors, desenvolupadors, gestors de producte i altres professionals involucrats en la creació i manteniment de productes o serveis digitals.

### 4. Què inclou un sistema de disseny?
Conté tots els components d'interfície d'usuari com ara botons, targetes, formularis, regles d'estil, guies de disseny i documentació tècnica, entre d'altres.

### 5. Com es manté un sistema de disseny?
El sistema s'actualitza de forma contínua a mesura que evolucionen les necessitats del negoci i les tendències de disseny. Això pot implicar la incorporació de nous components, ajustos en les regles d'estil i l'actualització de documentació.

### 6. Com puc contribuir al sistema de disseny?
Es pot contribuir al sistema de disseny formant part de la comunitat de dissenyadors i desenvolupadors. Es poden compartir idees, intercanviar opinions i aportar millores al sistema.
- [Uneix-te a la comunitat](sobre-comunitat.md)

### 7. Com puc sol·licitar suport o demanar nous components o modificacions?
Per sol·licitar suport, demanar nous components o modificacions, cal utilitzar els formularis de sol·licitud disponibles. Cal proporcionar la màxima informació possible sobre la petició.
- [Fes una sol·licitud](suport-sollicituds.md)

### 8. Com puc accedir al sistema de disseny?
L'accés es pot proporcionar a través d'una plataforma en línia, un repositori de codi o una eina de gestió de projectes. L'equip o departament de disseny i desenvolupament podrà proporcionar més detalls sobre com accedir i utilitzar el sistema de disseny de l'organització.

## Disseny

### 1. Quines directrius de disseny he de seguir: les publicades a la Guia Web o les del sistema de disseny?
Si es dissenya una web pública, cal seguir les directrius de la [Guia Web](https://guiaweb.gencat.cat/ca/inici). Per a la resta de pàgines, cal utilitzar les directrius del present sistema de disseny.

## Desenvolupament

### 1. Existeix una adaptació del codi per a Angular o altres *frameworks*?
Actualment, el sistema de disseny és adaptable a qualsevol *framework*, sigui Angular, React o qualsevol altre. Per integrar-lo en un projecte Angular, cal seguir aquest procediment:
- Si no es té el codi complet, afegeix els arxius (.js) inclosos dins la carpeta *build*, que es troba dins la carpeta *www* proporcionada, a una carpeta dins del projecte Angular.
- A continuació, inclou aquests arxius en la secció de *scripts* de l'arxiu *angular.json* per assegurar que Angular els carregui.
- Si es té el codi complet, incorpora el contingut de la carpeta *src* del sistema de disseny a la carpeta *src* del projecte Angular.

Per a més dubtes sobre com fer la implementació del projecte amb Angular, vegeu les [instruccions de la font](https://sistemadedisseny.gencat.cat/38669693e/p/04d901) i [Projectes Angular](dev-projectes-angular.md).

### 2. Disposeu d'un full d'estils global (SCSS)?
El sistema de disseny utilitza components web, cadascun amb el seu propi full d'estils, i inclou un arxiu global on s'especifiquen variables comunes (colors, fonts, espaiats i arrodoniments). Tot i que no es recomana fer servir un full d'estils global, en cas necessari es pot proporcionar el codi complet per accedir-hi i modificar-lo. Qualsevol modificació en aquest arxiu queda sota la responsabilitat de l'usuari i pot afectar el comportament del sistema.
Per a qualsevol consulta o dubte addicional sobre aquests procediments, [sol·licita una sessió de suport](suport-sollicita-suport.md).
