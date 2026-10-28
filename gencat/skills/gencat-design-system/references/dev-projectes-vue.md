# Projectes Vue

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/37cfe3 · Font actualitzada el 2026-07-07 · Extret el 2026-10-28

## Rutes de configuració de projecte

Hi ha dues maneres possibles de configurar el projecte Vue per utilitzar la llibreria de components:

- Utilitzant els components com a Define Custom Elements.
- Utilitzant el Wrapper de Vue.

La diferència rau en què els Define Custom Elements registren els components com a Web Components nadius del navegador (Custom Elements), permetent utilitzar-los com a etiquetes HTML personalitzades. En canvi, en utilitzar el Wrapper de Vue, els components s'integren directament dins de l'ecosistema Vue com a components tradicionals. Això permet una millor integració amb el sistema de mòduls, injecció de dependències, change detection, tipatge fort i altres característiques pròpies de Vue.

La decisió d'utilitzar una via o una altra queda en mans del projecte consumidor. Cal tenir precaució de barrejar les dues vies d'implementació.

> La configuració del projecte Vue per a la integració dels components del Sistema de Disseny es va realitzar sobre un projecte base que utilitza **Vue** en la versió **^3.50.30** i **Vite** en la versió **^8.0.0**.

## Utilització dels components com a Custom Elements

### 1. Configura el fitxer `main.js`

A l'aplicació Vue, ves a `src`, obre el fitxer `main.js` i defineix com a `defineCustomElements` els components que utilitzaràs al projecte:

```js
import { defineCustomElement as defineSwitch } from "gencat-core/dist/components/switch-component.js";

defineSwitch();
```

A més, els estils relatius a tokens de color, tipografies i estils de bootstrap s'han d'importar en aquest fitxer afegint la línia següent:

```js
import "gencat-core/dist/gencat/gencat.css"
```

### 2. Configura el fitxer `vite.config.js`

Cal indicar al compilador Vite que, si observa un component amb un nom d'etiqueta en concret, sàpiga que és un Web Component i no un component nadiu de Vue. Cal tenir definit el següent a `vite.config.js`:

```js
import { defineConfig } from "vite";
import vue from "@vitejs/plugin-vue";

export default defineConfig({
  plugins: [
    vue({
      template: {
        compilerOptions: {
          isCustomElement: (tag) => tag === "switch-component",
        },
      },
    }),
  ],
});
```

A `compilerOptions` s'hauran de definir tots els components que utilitzis al projecte.

### 3. Configura el fitxer `package.json`

Es crea un script que copia la carpeta `assets` del paquet NPM de la llibreria Stencil a la carpeta `public` de l'aplicació Vue. Aquesta tasca es pot fer manualment cada vegada que s'instal·li la llibreria, però es recomana seguir aquesta via per comoditat.

Si no tens instal·lat al projecte un paquet per copiar fitxers, executa:

```
npm install --save-dev ncp
```

A l'aplicació Vue, obre el fitxer `package.json` i escriu l'script:

```
"postinstall": "echo 'Postinstall script ejecutado' && ncp node_modules/gencat-core/dist/assets public/assets"
```

Els scripts de `package.json` haurien d'assemblar-se a:

```json
"scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview",
    "postinstall": "echo 'Postinstall script ejecutado' && ncp node_modules/gencat-core/dist/assets public/assets"
  },
```

Un cop fet això, cada vegada que s'instal·li via NPM la llibreria de Stencil, la carpeta `assets` es copiarà automàticament a la carpeta `public` de l'aplicació Vue. Per comprovar que l'script funciona, instal·la de nou la llibreria:

```
npm install gencat-core
```

Comprova que a la carpeta `public` de l'aplicació Vue hi ha la carpeta `assets`. Si no hi és, l'script no s'ha executat bé. Per resoldre-ho, executa:

```
npm run postinstall
```

Un cop fet això, hauries de tenir la carpeta `assets` a la carpeta `public` de l'aplicació Vue.

### 4. Comprova que es visualitza un component

A la carpeta `components` ubicada dins de `src`, a qualsevol fitxer `component.vue` de l'aplicació Vue, introdueix dins d'una etiqueta `<template>` el codi següent:

```html
<switch-component
      title-switch="Etiqueta"
      description-switch="Descripció"
      is-disabled="false"
></switch-component>
```

Després, executa `npm run dev` i al servidor local ja hauries de veure el component commutador (vegeu [Commutador](component-commutador.md)).

## Utilització del wrapper de Vue

### 1. Configura el fitxer `main.js`

Al projecte Vue, ves a la carpeta `src` i obre el fitxer `main.js`. Els estils relatius a tokens de color, tipografies i estils de bootstrap s'han d'importar en aquest fitxer afegint la línia següent:

```js
import "gencat-core/dist/gencat/gencat.css"
```

### 2. Configura el fitxer `App.vue`

Ves a la carpeta `src` i obre el fitxer `App.vue`. Cal introduir-hi la importació del component que vols utilitzar, així com la instància del component. La ruta des d'on s'han d'importar els components és: `gencat-core/plugins/vue/vue-output/src/NomComponent`.

Exemple:

```vue
<script setup>
import HelloWorld from './components/HelloWorld.vue'
import { SwitchComponent } from "gencat-core/plugins/vue/vue-output/src/SwitchComponent"
</script>

<template>
  <SwitchComponent
      title-switch="Etiqueta"
      description-switch="Descripció"
      is-disabled="false"
></SwitchComponent>
  <HelloWorld />
</template>
```

### 3. Configura el fitxer `package.json`

Es crea un script que copia la carpeta `assets` del paquet NPM de la llibreria Stencil a la carpeta `public` de l'aplicació Vue (es pot fer manualment, però es recomana aquesta via).

Si no tens instal·lat al projecte un paquet per copiar fitxers, executa:

```
npm install --save-dev ncp
```

A l'aplicació Vue, obre `package.json` i escriu l'script:

```
"postinstall": "echo 'Postinstall script ejecutado' && ncp node_modules/gencat-core/dist/assets public/assets"
```

Els scripts de `package.json` haurien d'assemblar-se a:

```json
"scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview",
    "postinstall": "echo 'Postinstall script ejecutado' && ncp node_modules/gencat-core/dist/assets public/assets"
  },
```

Cada vegada que s'instal·li via NPM la llibreria de Stencil, la carpeta `assets` es copiarà automàticament a la carpeta `public` de l'aplicació Vue. Per comprovar-ho, instal·la de nou la llibreria:

```
npm install gencat-core
```

Comprova que a la carpeta `public` hi ha la carpeta `assets`. Si no, executa:

```
npm run postinstall
```

Un cop fet això, hauries de tenir la carpeta `assets` a la carpeta `public` de l'aplicació Vue.

### 4. Instal·lació de `@stencil/vue-output-target`

El wrapper generat per cada component fa ús de la dependència `@stencil/vue-output-target`, que cal instal·lar al projecte per poder utilitzar els components. Executa l'ordre següent al projecte Vue. Posteriorment, no cal fer cap acció addicional.

```
npm install @stencil/vue-output-target
```

### 5. Comprova que el component es visualitza correctament

Inicia l'aplicació Vue per comprovar que el component de la llibreria es visualitza correctament:

```
npm run dev
```

## Vegeu també

[Desenvolupament](dev-desenvolupament.md) · [Projectes React](dev-projectes-react.md) · [Projectes Angular](dev-projectes-angular.md) · [Personalització de textos](dev-personalitzacio-de-textos.md) · [Canvi d'idioma dels components](dev-canvi-d-idioma-dels-components.md)
