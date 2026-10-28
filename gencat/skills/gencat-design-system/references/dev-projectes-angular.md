# Projectes Angular

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/3901f7 · Font actualitzada el 2026-07-07 · Extret el 2026-10-28

## Rutes de configuració de projecte

Hi ha dues maneres possibles de configurar el projecte Angular per utilitzar la llibreria de components:

- Utilitzant els components com a Define Custom Elements.
- Utilitzant el Wrapper d'Angular.

La diferència rau en què els Define Custom Elements registren els components com a Web Components nadius del navegador (Custom Elements), permetent utilitzar-los com a etiquetes HTML personalitzades. En canvi, en utilitzar el Wrapper d'Angular, els components s'integren directament dins de l'ecosistema Angular com a components tradicionals. Això permet una millor integració amb el sistema de mòduls, injecció de dependències, change detection, tipatge fort i altres característiques pròpies d'Angular.

La decisió d'utilitzar una via o una altra queda en mans del projecte consumidor. Cal tenir precaució de barrejar les dues vies d'implementació.

Per a la instal·lació del paquet, vegeu [Desenvolupament](dev-desenvolupament.md).

## Utilització dels components com a Custom Elements

### 1. Creació del fitxer `loader.ts`

A l'hora d'utilitzar la biblioteca, el més òptim és carregar de manera individual cada component que necessitis al projecte. Així s'eviten fitxers innecessaris al bundle.

Per exemple, per utilitzar el component **switch**, el primer pas és crear, dins la carpeta `src/app`, el fitxer `switch.loader.ts` i afegir-hi el codi següent:

```ts
let loaded = false;

export async function loadSwitch() {
  if (loaded) return;
  loaded = true;

  const { defineCustomElement } = await import(
    'gencat-core/dist/components/switch-component.js'
  );

  defineCustomElement();
}
```

### 2. Configura el fitxer `app.component.ts` (Standalone) o el fitxer `app.module.ts` (modular)

**Angular Standalone.** Dins l'aplicació Angular, accedeix a la carpeta `src/app`, obre el fitxer `app.component.ts` i introdueix les línies de codi següents:

```ts
/*Importa l'esquema_d'elements_personalitzats*/
import { CUSTOM_ELEMENTS_SCHEMA } from '@angular/core';

/*Al decorador @Component declara la variable schemas.*/
schemas: [CUSTOM_ELEMENTS_SCHEMA],

/*Carrega el component Switch*/
import { loadSwitch } from './switch.loader';
async ngOnInit() {
    await loadSwitch();
  }
```

El fitxer `app.component.ts` hauria d'incloure el codi següent:

```ts
import { Component } from '@angular/core';
import { RouterOutlet } from '@angular/router';
import { CUSTOM_ELEMENTS_SCHEMA } from '@angular/core';
import { loadSwitch } from './switch.loader';

@Component({
  selector: 'app-root',
  imports: [RouterOutlet],
  templateUrl: './app.component.html',
  styleUrl: './app.component.scss',
  schemas: [CUSTOM_ELEMENTS_SCHEMA]
})
export class AppComponent {
  title = 'angular-app';

  async ngOnInit() {
    await loadSwitch();
  }

}
```

**Angular modular.** Dins l'aplicació Angular, accedeix a la carpeta `src/app`, obre el fitxer `app.module.ts` i introdueix les línies de codi següents:

```ts
/*Importa l'esquema_d'elements_personalitzats*/
import { CUSTOM_ELEMENTS_SCHEMA, APP_INITIALIZER } from '@angular/core';

/*Al decorador @Component declara la variable schemas.*/
schemas: [CUSTOM_ELEMENTS_SCHEMA],

/*Carrega el component Switch*/
import { loadSwitch } from './switch.loader';

export function switchInitializer() {
  return () => loadSwitch();
}

providers: [
    {
      provide: APP_INITIALIZER,
      useFactory: switchInitializer,
      multi: true
    }
  ],
```

El fitxer `app.module.ts` hauria d'incloure el codi següent:

```ts
import { NgModule, CUSTOM_ELEMENTS_SCHEMA, APP_INITIALIZER } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';

import { AppRoutingModule } from './app-routing.module';
import { AppComponent } from './app.component';
import { loadSwitch } from './switch.loader';

export function switchInitializer() {
  return () => loadSwitch();
}

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    AppRoutingModule
  ],
  providers: [
    {
      provide: APP_INITIALIZER,
      useFactory: switchInitializer,
      multi: true
    }
  ],
  bootstrap: [AppComponent],
  schemas: [CUSTOM_ELEMENTS_SCHEMA] 
})
export class AppModule { }
```

### 3. Configura el fitxer `angular.json`

Tant si el projecte Angular és Standalone com modular, a l'arrel de l'aplicació Angular accedeix al fitxer `angular.json` i, a la secció "architect", "build", "options", introdueix aquest codi, que s'encarrega de consumir fonts i fitxers emmagatzemats a la carpeta `assets` del paquet npm:

```json
{  "glob": "**/*",  
    "input": "node_modules/gencat-core/dist/assets",  
    "output": "assets/"
}
```

A més, a l'apartat "styles" cal afegir els estils relatius a tokens de color, tipografies i estils de bootstrap:

```json
"styles": [
    "node_modules/gencat-core/dist/gencat/gencat.css"
],
```

El codi hauria de ser el següent (les línies marcades com `Codi introduït` són les afegides):

```json
"architect": {
        "build": {
          "builder": "@angular-devkit/build-angular:application",
          "options": {
            "outputPath": "dist/angular-test-app",
            "index": "src/index.html",
            "browser": "src/main.ts",
            "polyfills": [
              "zone.js"
            ],
            "tsConfig": "tsconfig.app.json",
            "inlineStyleLanguage": "scss",
            "assets": [
              {
                "glob": "**/*",
                "input": "public"
              },
              {  "glob": "**/*",  /*Codi introduït*/
                 "input": "node_modules/gencat-core/dist/assets",  /*Codi introduït*/
                 "output": "assets/" /*Codi introduït*/
              } 
            ],
            "styles": [
              "src/styles.scss",
              "node_modules/gencat-core/dist/gencat/gencat.css"    /*Codi introduït*/
            ],
            "scripts": []
          },
```

### 4. Comprova que es visualitza un component

Al fitxer `app.component.html`, que és a `src/app`, fes la crida a un component qualsevol, per exemple el commutador (vegeu [Commutador](component-commutador.md)):

```html
<switch-component
    [titleSwitch]="'Etiqueta'"
    [descriptionSwitch]="'Descripció'"
    [isDisabled]="false"
></switch-component>
```

Si el component es visualitza correctament, la llibreria està ben instal·lada i el projecte està ben configurat. Si no és així i tens algun problema, posa't en contacte amb l'equip del Sistema de Disseny al correu electrònic que hi ha a l'enllaç https://sistemadedisseny.gencat.cat/38669693e/p/57c57a (vegeu [Suport i contacte](suport-suport-i-contacte.md)).

## Utilització del wrapper d'Angular

El wrapper d'Angular és compatible amb **Angular 19 o versions superiors** i està preparat per funcionar en entorns **Standalone**. Facilita l'ús dels components com si fossin nadius d'Angular sense necessitat de configuració manual addicional.

### 1. Configura el fitxer `app.component.ts`

Dins l'aplicació Angular, accedeix a la carpeta `src/app`, obre el fitxer `app.component.ts` i introdueix les línies següents per importar el component botó com a exemple:

```ts
/*Importar el component desitjat*/
import { ButtonComponent } from 'gencat-core/plugins/angular/angular-output/src/directives/button-component';

/*Al decorador @Component*/
imports: [RouterOutlet, ButtonComponent],
```

El fitxer `app.component.ts` ha d'incloure el codi següent:

```ts
import { Component } from '@angular/core';
import { RouterOutlet } from '@angular/router';
import { ButtonComponent } from 'gencat-core/plugins/angular/angular-output/src/directives/button-component';

@Component({
  selector: 'app-root',
  imports: [RouterOutlet, ButtonComponent],
  templateUrl: './app.component.html',
  styleUrl: './app.component.scss',
})
export class AppComponent {
  title = 'angular-app';
}
```

### 2. Configura el fitxer `tsconfig.json`

Accedeix al fitxer `tsconfig.json` ubicat a l'arrel del projecte Angular. A la secció `compilerOptions` afegeix les línies següents:

```json
"compilerOptions": {
    ...
    "baseUrl": "./",
    "paths": {
      "gencat-core/plugins/angular/*": ["node_modules/gencat-core/plugins/angular/*"]
    }
  },
```

### 3. Configura el fitxer `tsconfig.app.json`

Accedeix al fitxer `tsconfig.app.json` ubicat a l'arrel del projecte Angular i afegeix les seccions `include` i `exclude` de la manera següent:

```json
"include": [
    "src/**/*.d.ts",
    "src/**/*.ts",
    "node_modules/gencat-core/plugins/angular/angular-output/src/**/*.ts"
  ],
   "exclude": [
    "src/**/*.spec.ts",
    "src/test.ts"
  ]
```

El fitxer `tsconfig.app.json` ha d'incloure el codi següent:

```json
{
  "extends": "./tsconfig.json",
  "compilerOptions": {
    "outDir": "./out-tsc/app",
    "types": [
      "node"
    ]
  },
  "files": [
    "src/main.ts",
    "src/main.server.ts",
    "src/server.ts"
  ],
  "include": [
    "src/**/*.d.ts",
    "src/**/*.ts",
    "node_modules/gencat-core/plugins/angular/angular-output/src/**/*.ts"
  ],
   "exclude": [
    "src/**/*.spec.ts",
    "src/test.ts"
  ]
}
```

### 4. Configura el fitxer `angular.json`

A l'arrel de l'aplicació Angular, accedeix al fitxer `angular.json` i, a la secció architect, build, options, introdueix aquest codi, que s'encarrega de consumir fonts i fitxers emmagatzemats a la carpeta `assets` del paquet npm:

```json
{  "glob": "**/*",  
    "input": "node_modules/gencat-core/dist/assets",  
    "output": "assets/"
}
```

A més, a l'apartat "styles" cal afegir els estils relatius a tokens de color, tipografies i estils de bootstrap:

```json
"styles": [
    "node_modules/gencat-core/dist/gencat/gencat.css"
],
```

El codi ha de ser el següent:

```json
"architect": {
        "build": {
          "builder": "@angular-devkit/build-angular:application",
          "options": {
            "outputPath": "dist/angular-test-app",
            "index": "src/index.html",
            "browser": "src/main.ts",
            "polyfills": [
              "zone.js"
            ],
            "tsConfig": "tsconfig.app.json",
            "inlineStyleLanguage": "scss",
            "assets": [
              {
                "glob": "**/*",
                "input": "public"
              },
              {  "glob": "**/*",  /*Codi introduït*/
                 "input": "node_modules/gencat-core/dist/assets",  /*Codi introduït*/
                 "output": "assets/" /*Codi introduït*/
              } 
            ],
            "styles": [
              "src/styles.scss",
              "node_modules/gencat-core/dist/gencat/gencat.css"   /*Codi introduït*/
            ],
            "scripts": []
          },
```

### 5. Comprova que es visualitza el component

Al fitxer `app.component.html`, que és a `src/app`, fes la crida al component botó (vegeu [Botons](component-botons.md)):

```html
<button-component 
  class-name-button="btn-primary"
  class-name-icon="" 
  size-button="btn-size-L"
  mode-color-button="mode-color-primary-light" 
  text="Botó"
  href-button=""
  left-icon-chevron="true" 
  right-icon-chevron="false"
  left-icon=false 
  right-icon=false
  text-tooltip=""
  is-spinner=false
  custom-id=""
  type-button="button"
  badge="true"
  text-badge="12">
</button-component>
```

Si el component es visualitza correctament, la llibreria està ben instal·lada i el projecte està ben configurat. Si no és així i tens algun problema, posa't en contacte amb l'equip del Sistema de Disseny al correu electrònic que hi ha a l'enllaç https://sistemadedisseny.gencat.cat/38669693e/p/57c57a.

## Vegeu també

[Desenvolupament](dev-desenvolupament.md) · [Projectes React](dev-projectes-react.md) · [Projectes Vue](dev-projectes-vue.md) · [Personalització de textos](dev-personalitzacio-de-textos.md) · [Canvi d'idioma dels components](dev-canvi-d-idioma-dels-components.md)
