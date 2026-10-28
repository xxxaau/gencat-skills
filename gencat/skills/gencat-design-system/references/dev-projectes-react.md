# Projectes React

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/58b5cb · Font actualitzada el 2026-07-07 · Extret el 2026-10-28

## Rutes de configuració de projecte

Hi ha dues maneres possibles de configurar el projecte React per utilitzar la llibreria de components:

- Utilitzant els components com a Define Custom Elements.
- Utilitzant el Wrapper de React.

La diferència rau en què els Define Custom Elements registren els components com a Web Components nadius del navegador (Custom Elements), permetent utilitzar-los com a etiquetes HTML personalitzades. En canvi, en utilitzar el Wrapper de React, els components s'integren directament dins de l'ecosistema React com a components tradicionals. Això permet una millor integració amb el sistema de mòduls, injecció de dependències, change detection, tipatge fort i altres característiques pròpies de React.

La decisió d'utilitzar una via o una altra queda en mans del projecte consumidor. Cal tenir precaució de barrejar les dues vies d'implementació.

Prerequisit: haver instal·lat el paquet (vegeu [Desenvolupament](dev-desenvolupament.md)).

## Utilització dels components com a Custom Elements

### 1. Configura el fitxer `App.tsx`

Al projecte React, ves a la carpeta `src` i obre el fitxer `App.tsx`. Els estils relatius a tokens de color, tipografies i estils de bootstrap s'han d'importar en aquest fitxer afegint la línia següent:

```js
import "gencat-core/dist/gencat/gencat.css"
```

### 2. Configura el fitxer `index.js`

Ves a `src`, obre el fitxer `index.js` i defineix els components que utilitzaràs al projecte. Exemple:

```js
import { defineCustomElement as defineSwitch } from "gencat-core/dist/components/switch-component.js";

defineSwitch();
```

### 3. Configura el fitxer `package.json`

Es crea un script que copia la carpeta `assets` del paquet NPM de la llibreria Stencil a la carpeta `public` de l'aplicació React (es pot fer manualment cada vegada que s'instal·li la llibreria, però es recomana aquesta via).

Si no tens instal·lat al projecte un paquet per copiar fitxers, executa:

```
npm install --save-dev ncp
```

A l'aplicació React, obre `package.json` i escriu l'script:

```
"postinstall": "echo 'Postinstall script ejecutado' && ncp node_modules/gencat-core/dist/assets public/assets"
```

Els scripts de `package.json` haurien d'assemblar-se a:

```json
"scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject",
    "postinstall": "echo 'Postinstall script ejecutado' && ncp node_modules/gencat-core/dist/assets public/assets"
  },
```

Cada vegada que s'instal·li via NPM la llibreria de Stencil, la carpeta `assets` es copiarà automàticament a la carpeta `public` de l'aplicació React. Per comprovar-ho, instal·la de nou la llibreria:

```
npm install gencat-core
```

Comprova que a la carpeta `public` de l'aplicació React hi ha la carpeta `assets`. Si no hi és, l'script no s'ha executat bé. Per resoldre-ho, executa:

```
npm run postinstall
```

Un cop fet això, hauries de tenir la carpeta `assets` a la carpeta `public` de l'aplicació React.

### 4. Comprova que es visualitza un component

A la carpeta `App.js` de l'aplicació React, introdueix a la crida de qualsevol component el codi següent:

```html
<switch-component
      title-switch="Etiqueta"
      description-switch="Descripció"
      is-disabled="false"
></switch-component>
```

Després, executa `npm start` i al servidor local ja hauries de veure el component commutador (vegeu [Commutador](component-commutador.md)).

## Utilització del wrapper de React

> La instal·lació del wrapper React de la llibreria es va realitzar en un projecte **React versió ^19.2.7** amb **Vite versió ^7.3.1**.

### 1. Configura el fitxer `App.tsx`

Al projecte React, ves a la carpeta `src` i obre el fitxer `App.tsx`. Cal introduir-hi la importació del component que vols utilitzar, així com la instància del component. La ruta des d'on s'han d'importar els components és: `gencat-core/plugins/react/react-output/src/generated/NomComponent`.

A més, els estils relatius a tokens de color, tipografies i estils de bootstrap s'han d'importar en aquest fitxer afegint la línia següent:

```js
import "gencat-core/dist/gencat/gencat.css"
```

Exemple:

```tsx
import './App.css'
import { ButtonComponent } from "gencat-core/plugins/react/react-output/src/generated/ButtonComponent"

function App() {

  return (
    <>
      <ButtonComponent 
        class-name-button="btn-primary"
        class-name-icon="" 
        size-button="btn-size-L"
        mode-color-button="mode-color-primary-light" 
        text="Botó"
        left-icon-chevron={true} 
        right-icon-chevron={false}
        left-icon={false} 
        right-icon={false}
        text-tooltip=""
        is-spinner={false}
        custom-id=""
        type-button="button"
        badge={true}
        text-badge="12">
      </ButtonComponent>
    </>
  )
}

export default App
```

(Component d'exemple: [Botons](component-botons.md).)

### 2. Configura el fitxer `package.json`

Es crea un script que copia la carpeta `assets` del paquet NPM de la llibreria Stencil a la carpeta `public` de l'aplicació React (es pot fer manualment, però es recomana aquesta via).

Si no tens instal·lat al projecte un paquet per copiar fitxers, executa:

```
npm install --save-dev ncp
```

A l'aplicació React, obre `package.json` i escriu l'script:

```
"postinstall": "echo 'Postinstall script ejecutado' && ncp node_modules/gencat-core/dist/assets public/assets"
```

Els scripts de `package.json` haurien d'assemblar-se a:

```json
"scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject",
    "postinstall": "echo 'Postinstall script ejecutado' && ncp node_modules/gencat-core/dist/assets public/assets"
  },
```

Cada vegada que s'instal·li via NPM la llibreria de Stencil, la carpeta `assets` es copiarà automàticament a la carpeta `public` de l'aplicació React. Per comprovar-ho, instal·la de nou la llibreria:

```
npm install gencat-core
```

Comprova que a la carpeta `public` hi ha la carpeta `assets`. Si no, executa:

```
npm run postinstall
```

Un cop fet això, hauries de tenir la carpeta `assets` a la carpeta `public` de l'aplicació React.

### 3. Instal·lació de `@stencil/react-output-target`

El wrapper generat per cada component fa ús de la dependència `@stencil/react-output-target`, que cal instal·lar al projecte per poder utilitzar els components. Executa l'ordre següent al projecte React. Posteriorment, no cal fer cap acció addicional.

```
npm install @stencil/react-output-target
```

### 4. Comprova que el component es visualitza correctament

Inicia l'aplicació React per comprovar que el component de la llibreria es visualitza correctament:

```
npm run dev
```

## Vegeu també

[Desenvolupament](dev-desenvolupament.md) · [Projectes Vue](dev-projectes-vue.md) · [Projectes Angular](dev-projectes-angular.md) · [Personalització de textos](dev-personalitzacio-de-textos.md) · [Canvi d'idioma dels components](dev-canvi-d-idioma-dels-components.md)
