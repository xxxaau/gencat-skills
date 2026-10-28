# Personalització de textos

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/736a26 · Font actualitzada el 2026-09-09 · Extret el 2026-10-28

## Personalització de textos dels components

Alguns components de la biblioteca inclouen textos predeterminats (etiquetes, botons d'acció, missatges d'estat, etc.). Es poden substituir pels de l'aplicació sense necessitat de modificar el component: n'hi ha prou d'invocar la funció `setLocale` una sola vegada a l'inici de l'aplicació. Les claus disponibles estan a [Referència de claus disponibles](dev-referencia-de-claus-disponibles.md).

### Com funciona

La funció `setLocale`, exportada des de `gencat-core`, accepta un objecte parcial amb els textos que es volen sobreescriure. Només cal indicar les claus que es volen canviar; la resta conserven el valor per defecte.

```ts
import { setLocale } from 'gencat-core';  

setLocale({   
    pagination: { previous: 'Anterior', next: 'Següent', pageSummary: 'Pàgina {current} de {total}' },   
    accordion: { expandAll: 'Expandeix-ho tot', collapseAll: 'Redueix-ho tot' },   // ... només els que necessitis canviar }); 
```

> **Important:** cal cridar `setLocale` abans que es munti qualsevol component. D'aquesta manera, quan es renderitzin per primera vegada ja tindran els textos correctes.

## Integració per framework

### Angular

Afegeix la crida a `setLocale` a `main.ts` (o a `app.component.ts`), abans de l'arrencada del mòdul:

```ts
import { setLocale } from 'gencat-core'; 
import { platformBrowserDynamic } from '@angular/platform-browser-dynamic'; 
import { AppModule } from './app/app.module';  

setLocale({ pagination: { previous: 'Anterior', next: 'Següent' }, });  

platformBrowserDynamic().bootstrapModule(AppModule); 
```

### React

Afegeix la crida a `setLocale` a `main.tsx` o `index.tsx`, abans del render inicial:

```tsx
import { setLocale } from 'gencat-core'; 
import ReactDOM from 'react-dom/client'; 
import App from './App';  

setLocale({   pagination: { previous: 'Anterior', next: 'Següent' }, });  
ReactDOM.createRoot(document.getElementById('root')!).render(<App />); 
```

### Vue

Afegeix la crida a `setLocale` a `main.ts`, abans del muntatge de l'aplicació:

```ts
import { setLocale } from 'gencat-core'; 
import { createApp } from 'vue'; 
import App from './App.vue';  

setLocale({   pagination: { previous: 'Anterior', next: 'Següent' }, });  
createApp(App).mount('#app'); 
```

## Notes

- `setLocale` és **acumulativa**: si es crida diverses vegades, cada crida sobreescriu únicament les claus indicades, sense afectar les que no s'han especificat.
- Els textos que accepten variables dinàmiques (com ara `pageSummary`) utilitzen la sintaxi `{nomVariable}`. No s'ha de modificar el nom de les variables, ja que el component les substitueix en temps d'execució.

## Vegeu també

[Canvi d'idioma dels components](dev-canvi-d-idioma-dels-components.md) · [Referència de claus disponibles](dev-referencia-de-claus-disponibles.md) · [Desenvolupament](dev-desenvolupament.md)
