# Desenvolupament

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/61ee3b · Font actualitzada el 2026-04-27 · Extret el 2026-10-28

Guia d'instal·lació, configuració i ús de la llibreria de components als diferents marcs tecnològics.

## Accés a la visualització de components

Els components es poden visualitzar a través de la URL estàtica generada per GitHub Pages, que actua com a proveïdor d'allotjament de la llibreria de components. Per poder accedir a aquesta URL, cal tenir accés a GitHub. Passos:

1. **Coneix el teu codi GICAR.** Per conèixer aquest codi, accedeix a l'enllaç [codi GICAR](https://sistemadedisseny.gencat.cat/38669693e/p/146e5b). Un cop obtingut, podràs sol·licitar accés a GitHub a través de l'enllaç [accessos](https://sistemadedisseny.gencat.cat/38669693e/p/860a8b-accessos) (vegeu [Accessos](suport-accessos.md)).
2. **Inicia sessió a GitHub.** Un cop se't concedeixi l'accés al repositori, podràs iniciar sessió al teu compte de GitHub a través de: [https://ctti.ghe.com/enterprises/ctti/sso](https://ctti.ghe.com/enterprises/ctti/sso)
3. **Dins del repositori GitHub.** Un cop iniciada la sessió, podràs accedir al repositori de la llibreria a través de: [https://ctti.ghe.com/ctti-dev/3693.00-sdc-eixam-library](https://ctti.ghe.com/ctti-dev/3693.00-sdc-eixam-library)

Des d'allà, podràs visualitzar els components i les seves propietats a Storybook mitjançant la URL estàtica generada per GitHub Pages: [https://ctti-dev-3693-00-sdc-eixam-library.pages.ctti.ghe.com/](https://ctti-dev-3693-00-sdc-eixam-library.pages.ctti.ghe.com/)

## Paquets de la llibreria

La llibreria de components està formada per dos paquets d'instal·lació:

- **gencat-core**: conté els components web principals de la llibreria.
- **gencat-conversational**: conté components web utilitzats en entorns conversacionals, com ara xatbots.

> Per utilitzar el paquet **Conversational** cal tenir instal·lat també el paquet **Core** al teu projecte.

L'estructura interna de tots dos paquets és la mateixa. L'única diferència està en els components que contenen, de manera que la guia d'implementació de la llibreria és vàlida per a tots dos paquets. Vegeu l'inventari de components per paquet a [Visió general dels paquets](dev-visio-general-paquets-web-components.md).

### Publicació dels paquets

Els paquets `gencat-core` i `gencat-conversational` es publiquen a **JFrog** dins del dipòsit npm-public a partir de la versió 9.2.2.

Per descarregar-los, ja no cal disposar d'accés al repositori de GitHub de la llibreria. Només caldrà generar un **token des de JFrog** o iniciar sessió mitjançant **npm login** contra el registre de JFrog per disposar de permisos de descàrrega dels paquets.

Consulta la [documentació](https://canigo.ctti.gencat.cat/plataformes/ghec/gh-repositori-artefactes/) del Centre de Telecomunicacions i Tecnologies de la Informació per saber com iniciar sessió a JFrog i com s'hi gestionen els artefactes.

## Instal·lació via npm i

Independentment del *framework* (marc tecnològic) amb què treballis, el primer pas per utilitzar la llibreria és la instal·lació via `npm install`.

Prèviament a la instal·lació del paquet via `npm install` cal oferir permisos a través de la generació d'un token a JFrog o fent `npm login`. Hi ha dues alternatives.

### Alternativa 1: generació de token a JFrog

**1. Crea el fitxer `.npmrc`.** Si a l'arrel del projecte no existeix el fitxer `.npmrc`, cal crear-lo i definir a l'interior el codi següent:

```
registry=https://ctti.jfrog.io/artifactory/api/npm/repo-apps-npm/
//ctti.jfrog.io/artifactory/api/npm/repo-apps-npm/:_authToken=<your-token>
always-auth=true
```

A `authToken` cal escriure el token d'autenticació generat per JFrog.

**2. Genera el token a JFrog.** Accedeix a [https://ctti.jfrog.io/ui/packages](https://ctti.jfrog.io/ui/packages) i inicia sessió amb les credencials amb les quals et van donar accés al repositori (sol ser usuari GICAR). Fes clic a la teva icona d'usuari situada a dalt a la dreta. S'obre un desplegable amb opcions. Accedeix a "Edit Profile". A continuació fes clic al botó "Generate an Identity Token" i genera el token seguint els passos que s'indiquin. Un cop finalitzat el procés apareixerà en pantalla el token: copia'l i enganxa'l al fitxer `.npmrc` substituint `<your-token>` de l'`authToken`. És recomanable guardar aquest token en un altre lloc per evitar perdre'l. Després d'aquest pas el token ja estarà generat i en funcionament al fitxer `.npmrc`.

**3. Executa `npm i` per instal·lar el paquet.** Executa l'ordre següent a la carpeta encarregada de gestionar el projecte (en funció del *framework*, s'haurà d'executar en una carpeta o l'altra):

```
Per paquet core:
npm install gencat-core

Per paquet conversational:
npm install gencat-conversational
```

Un cop executada, la llibreria queda instal·lada al projecte.

### Alternativa 2: inici de sessió a JFrog mitjançant npm login

Cal iniciar sessió al registre de JFrog des de la carpeta del projecte amb l'ordre:

```
npm login --registry=https://ctti.jfrog.io/artifactory/api/npm/repo-apps-npm/
```

Posteriorment, la consola sol·licita usuari i contrasenya. Cal seguir els passos per finalitzar l'inici de sessió.

Finalment, executa l'ordre següent a la carpeta encarregada de gestionar el projecte (en funció del *framework*, s'haurà d'executar en una carpeta o l'altra):

```
Per paquet core:
npm install gencat-core

Per paquet conversational:
npm install gencat-conversational
```

Un cop executada, la llibreria queda instal·lada al projecte.

## Configuració del projecte

Un cop instal·lada la llibreria al projecte, cal ajustar alguns fitxers de configuració perquè funcioni correctament.

Stencil és un framework agnòstic que genera Web Components i permet crear wrappers per a Angular, React i Vue, facilitant la integració dels components en aquests frameworks.

Els apartats següents expliquen com configurar projectes Angular, React i Vue utilitzant Custom Elements o bé els wrappers generats per Stencil, ubicats dins la carpeta `plugins` dels paquets npm:

- [Projectes Angular](dev-projectes-angular.md) (https://sistemadedisseny.gencat.cat/38669693e/p/3901f7-projectes-angular): configura Angular per usar la llibreria de components.
- [Projectes React](dev-projectes-react.md) (https://sistemadedisseny.gencat.cat/38669693e/p/58b5cb-projectes-react): configura React per usar la llibreria de components.
- [Projectes Vue](dev-projectes-vue.md) (https://sistemadedisseny.gencat.cat/38669693e/p/37cfe3-projectes-vue): configura Vue per usar la llibreria de components.

## Plataformes i eines utilitzades

### Github

On està emmagatzemat tot el codi corresponent als components, així com les dependències de Bootstrap i Stencil. Es pot accedir al repositori, amb els permisos necessaris, a: [https://ctti.ghe.com/ctti-dev/3693.00-sdc-eixam-library](https://ctti.ghe.com/ctti-dev/3693.00-sdc-eixam-library)

### JFrog

Programari a través del qual es gestiona, emmagatzema i distribueix els artefactes generats per la llibreria durant el procés de desenvolupament. El panell d'usuari és a: [https://ctti.jfrog.io/ui/packages](https://ctti.jfrog.io/ui/packages)

### Bootstrap

Eina a disposició dels desenvolupadors per crear interfícies i experiències en llocs web i serveis públics digitals. La versió de Bootstrap utilitzada en aquest projecte és la **5.3.3**. Més informació: [https://getbootstrap.com/](https://getbootstrap.com/)

### Stencil

Biblioteca per construir biblioteques de components reutilitzables i escalables. Genera components web petits i ràpids que funcionen a tot arreu. La versió utilitzada en aquest projecte és la **4.7**. Més informació: [https://stenciljs.com](https://stenciljs.com)

## Com et podem ajudar?

Per a ajuda, sol·licitar un nou component o modificar-ne un d'existent, o dubtes sobre l'ús del sistema de disseny, consulta la [secció de suport](https://zeroheight.com/38669693e/p/57c57a-suport-i-contacte).

- [Consulta les preguntes freqüents](https://zeroheight.com/38669693e/p/72240b-preguntes-frequents)
- [Fes una sol·licitud](https://zeroheight.com/38669693e/p/690b45)
- [Accedeix a les guies d'ús](https://zeroheight.com/38669693e/p/342611)

## Vegeu també

[Projectes Angular](dev-projectes-angular.md) · [Projectes React](dev-projectes-react.md) · [Projectes Vue](dev-projectes-vue.md) · [Personalització de textos](dev-personalitzacio-de-textos.md) · [Canvi d'idioma dels components](dev-canvi-d-idioma-dels-components.md) · [Referència de claus](dev-referencia-de-claus-disponibles.md) · [Visió general dels paquets](dev-visio-general-paquets-web-components.md) · [Github](suport-github.md) · [Accessos](suport-accessos.md)
