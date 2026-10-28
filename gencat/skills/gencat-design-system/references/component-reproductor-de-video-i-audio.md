# Reproductor de vídeo i àudio (Video and Audio Player)

> Font: https://sistemadedisseny.gencat.cat/38669693e/p/85c389 · Web component: `<video-audio-player-component>` (paquet core) · Font actualitzada el 2026-10-22 · Extret el 2026-10-28

## Què és i quan usar-lo
El reproductor de vídeo i àudio és un component que permet integrar contingut multimèdia. Permet visualitzar i escoltar contingut multimèdia dins de l'experiència digital. Inclou controls bàsics per gestionar la reproducció, el volum, el progrés i el mode de pantalla completa (en el cas dels vídeos).

Quan s'utilitza:
- Per mostrar contingut multimèdia que complementa o enriqueix la informació d'una pàgina o funcionalitat.
- En formacions, tutorials, entrevistes, podcasts o altres recursos audiovisuals.

### Modes de presentació
**Reproductor de vídeo.** Hi ha dos modes principals de presentació:
- **Integrat en pàgina:** el vídeo es mostra dins del flux habitual del contingut.
- **Vista ampliada:** el vídeo s'amplia centrat a la pantalla, per sobre d'una capa enfosquida que bloqueja la interacció amb el contingut del fons. Aquesta capa utilitza un color negre (#000000) amb una opacitat del 90 %.

**Reproductor d'àudio.** Es presenta sempre **integrat en pàgina**. Aquest tipus de reproductor **no inclou vista ampliada.**

## Quan NO usar-lo / alternatives
- Quan una imatge o un text poden transmetre el mateix missatge de manera més eficient i accessible.
- Si no és possible oferir una alternativa accessible (com subtítols o transcripció) per al contingut multimèdia.

## Anatomia

### Reproductor de vídeo
1. **Botó activador de reproducció**: inicia la reproducció del vídeo quan es prem.
2. **Vídeo**: contingut audiovisual que es mostra al reproductor.
3. **Controls de vídeo**: eines proporcionades per la plataforma per gestionar la reproducció.
4. **Peu de vídeo (opcional)**: text complementari que aporta informació addicional sobre el vídeo.

Els controls són proporcionats per la plataforma d'origen (com YouTube, Vimeo o altres). L'aparença i les funcionalitats poden variar segons la plataforma. Principals controls que poden aparèixer:
1. **Reprodueix/Pausa**: permet iniciar o aturar la reproducció del vídeo.
2. **Temps transcorregut**: mostra el temps que ha passat des de l'inici del vídeo.
3. **Indicador de progrés**: barra que mostra visualment el progrés de la reproducció.
4. **Durada**: indica la durada total del vídeo.
5. **Volum**: control per ajustar el nivell de so.
6. **Subtítols**: opció per activar o desactivar els subtítols disponibles.
7. **Denunciar**: botó per informar de contingut inadequat.
8. **Picture-in-Picture (vídeo en finestra)**: permet continuar veient el vídeo en una finestra flotant mentre es navega per altres continguts.
9. **Menú addicional / Desplegable**: accés a funcions addicionals com la velocitat de reproducció, qualitat del vídeo, etc.
10. **Ampliar/Reduir**: control per ampliar el vídeo a pantalla completa o tornar a la mida original.
11. **Botó de retrocedir 10 segons.**
12. **Botó d'avançar 10 segons.**

La visualització dels controls depèn de les funcionalitats disponibles al reproductor. Els botons d'avançar i retrocedir són excloents amb les accions de Denunciar i Subtítols: quan es mostren els primers, aquestes accions s'agrupen dins del botó d'accions, i viceversa.

### Reproductor d'àudio
1. **Portada d'àudio**: imatge destacada que representa el contingut, com la portada d'un àlbum o episodi.
2. **Controls d'àudio**: eines proporcionades per la plataforma per gestionar la reproducció.
3. **Nom de l'artista o del pòdcast**: indica l'autor o intèrpret de la cançó, o bé el nom del pòdcast al qual pertany l'episodi.
4. **Títol del contingut**: mostra el nom específic de la pista, sigui el títol d'una cançó o el nom d'un episodi de pòdcast.
5. **Peu d'àudio (opcional)**: text complementari que aporta informació addicional sobre l'àudio.

## Variants, tipus i estats

### Reproductor de vídeo

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Type | Enabled / Working / Expanded | Enabled |
| Breakpoint | Extra Large - Medium / Small | Extra Large - Medium |
| Show video captions | True / False | True |

Figma: `Video_Integrat en pàgina`, `Video_vista ampliada`; es va afegir la propietat *Show skip buttons* al *Controls Container* de vídeo (botons de salt de 10 segons i botons de pujar i baixar el volum).

### Reproductor d'àudio

| Propietat | Valor | Valor per defecte |
|---|---|---|
| Breakpoint | Extra Large - Medium / Small | Extra Large - Medium |
| Show audio captions | True / False | True |

Figma: `Audio_Integrat a pagina`.

### Gestió d'errors
En cas que es produeixi un error en carregar un vídeo o àudio, es mostrarà una imatge específica d'error. A més, s'inclourà un text alternatiu per informar l'usuari que s'ha produït un error (Figma: `Error carrega video`, `Error carrega audio`).

## Comportament i interacció

### Reproductor de vídeo
- **Inicialment**, abans de reproduir-se, es mostra únicament un botó de **reproducció centrat** sobre la miniatura del vídeo.
- No es permet la **reproducció automàtica** del vídeo; la reproducció s'inicia únicament mitjançant una acció explícita de l'usuari.
- Un cop l'usuari fa clic al **botó de reproducció**, aquest botó centrat **desapareix**, i es mostren els **controls essencials**: línia de temps, pausa, volum, pantalla completa, etc.
- Aquests controls es mantenen visibles **mentre hi ha interacció** (per exemple, moviments del cursor).
- Si no hi ha activitat durant **3 segons**, els controls **desapareixen automàticament** per no interferir amb el contingut.
- Es mostren *tooltips* ([indicadors de funció](component-indicador-de-funcio.md)) sobre cada control quan l'usuari hi passa el cursor o fa focus.
- Els controls són els que proporciona la **plataforma d'origen** (com YouTube, Vimeo, Watchity o altres).

### Reproductor d'àudio
- Els **controls es mostren sempre visibles**.
- Inclou elements com el botó de reproducció/pausa, barra de progrés, durada i volum.
- Es mostren *tooltips* (indicadors de funció) sobre cada control quan l'usuari hi passa el cursor o fa focus.
- Els controls són els que proporciona la **plataforma d'origen** (com Spotify, iVoox o altres).

### Adaptació responsiva
El reproductor té variants per als punts de tall Extra Large - Medium i Small (vegeu propietat Breakpoint).

### Compatibilitat
Es pot incrustar tant dins del contingut principal com en elements interactius, com per exemple pestanyes i acordions.

## Bones pràctiques

**Càrrega i rendiment (reproductor de vídeo)**
- **FER:** Mantingues el pes dels arxius de vídeo per sota dels 500 MB i limita la durada a 20-30 minuts per garantir una càrrega ràpida.
- **NO FER:** No utilitzis vídeos amb pes excessiu o durada molt llarga.

**Càrrega i rendiment (reproductor d'àudio)**
- **FER:** Mantingues el pes dels arxius d'àudio per sota dels 50 MB i limita la durada a 90 minuts.
- **NO FER:** No utilitzis arxius d'àudio massa pesats o de durada excessiva.

**Context i informació**
- **FER:** Acompanya el reproductor amb títols i descripcions per contextualitzar el contingut.
- **NO FER:** No deixis el reproductor aïllat, sense cap referència o explicació complementària.

## Accessibilitat
No hi ha control sobre les pautes d'accessibilitat que segueixen els controls dels components de reproductor de vídeo i àudio que provenen de plataformes externes.

### Pautes WCAG
- **Només àudio i només vídeo (preenregistrat) (A)**: àudio preenregistrat: s'ha de proporcionar una alternativa que presenti informació equivalent, com una transcripció textual. Vídeo preenregistrat: s'ha de proporcionar una alternativa que presenti informació equivalent, com una pista d'àudio o una transcripció textual. [1.2.1 - CAT](https://www.w3.org/Translations/WCAG22-ca/#audio-only-and-video-only-prerecorded) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/audio-only-and-video-only-prerecorded.html)
- **Subtítols (preenregistrat) (A)**: han d'estar disponibles per a tot el contingut d'àudio en vídeos preenregistrats, excepte quan el mitjà és una alternativa per a text i està clarament etiquetat com a tal. [1.2.2 - CAT](https://www.w3.org/Translations/WCAG22-ca/#captions-prerecorded) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/captions-prerecorded.html)
- **Audiodescripció o format alternatiu (preenregistrat) (A)**: la descripció d'àudio ha d'estar disponible per a tot el contingut de vídeo pregravat, proporcionant una narració de les accions, personatges, canvis d'escena i text en pantalla durant les pauses en el diàleg. [1.2.3 - CAT](https://www.w3.org/Translations/WCAG22-ca/#audio-description-or-media-alternative-prerecorded) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/audio-description-prerecorded.html)
- **Subtítols (en directe) (AA)**: han d'estar disponibles per a tot el contingut d'àudio en vídeos en directe. [1.2.4 - CAT](https://www.w3.org/Translations/WCAG22-ca/#captions-live) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/captions-live.html)
- **Audiodescripció (preenregistrada) (AA)**: la descripció d'àudio ha d'estar disponible per a tot el contingut de vídeo preenregistrat, proporcionant una narració de les accions, personatges, canvis d'escena i text en pantalla durant les pauses en el diàleg. [1.2.5 - CAT](https://www.w3.org/Translations/WCAG22-ca/#audio-description-prerecorded) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/audio-description-prerecorded.html)
- **Ús del color (A)**: el color no es fa servir com l'únic mitjà visual per transmetre informació, indicar una acció, provocar una resposta o distingir un element visual. Per a indicar el pas, percentatge, etc. en el qual es troba el procés o tasca s'utilitza informació textual a part de gràfica. [1.4.1 - CAT](https://www.w3.org/Translations/WCAG22-ca/#use-of-color) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color)
- **Contrast mínim (AA)**: els elements textuals tenen una relació de contrast d'almenys 4,5:1. Els elements inactius o deshabilitats són una excepció d'aquesta norma. [1.4.3 - CAT](https://www.w3.org/Translations/WCAG22-ca/#contrast-minimum) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum)
- **Canvia la mida del text (AA)**: excepte els subtítols i les imatges de text, el text es pot canviar de mida sense tecnologia d'assistència fins al 200 % sense pèrdua de contingut ni de funcionalitat. [1.4.4 - CAT](https://www.w3.org/Translations/WCAG22-ca/#resize-text) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/resize-text)
- **Contrast d'elements no textuals (AA)**: els elements gràfics presenten un contrast mínim de 3:1. [1.4.11 - CAT](https://www.w3.org/Translations/WCAG22-ca/#non-text-contrast) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast)
- **Teclat (A)**: tota la funcionalitat del contingut es pot operar a través d'una interfície de teclat sense requerir temps específics per a pulsacions de tecles individuals. [2.1.1 - CAT](https://www.w3.org/Translations/WCAG22-ca/#keyboard) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- **Focus visible (AA)**: la navegació pels diferents elements mitjançant teclat és visible a través d'un rectangle. [2.4.7 - CAT](https://www.w3.org/Translations/WCAG22-ca/#focus-visible) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- **Arrossegament (AA)**: els elements que requereixen arrossegament per controlar la reproducció o el volum disposen d'una alternativa que no requereix aquesta acció. El Controls Container inclou botons de salt de 10 segons com a alternativa a l'arrossegament de la barra de progrés, i botons +/- com a alternativa a l'arrossegament de la barra de volum. Per als reproductors que integrin plataformes externes (YouTube, Vimeo, Spotify, iVoox, etc.), es recomana utilitzar plataformes que ofereixin alternatives al desplaçament de les barres sense necessitat d'arrossegar. [2.5.7 - CAT](https://www.w3.org/Translations/WCAG22-ca/#dragging-movements) / [EN](https://www.w3.org/WAI/WCAG22/Understanding/dragging-movements)

### Navegació per teclat

| Tecla | Acció |
|---|---|
| Tabulació | Navegació al següent element interactiu |
| Enter | Activar element interactiu |
| Fletxes dreta / esquerra | Avançar o retrocedir 5 segons al vídeo |
| Fletxes amunt / avall | Dins la configuració de volum, apuja i abaixa el volum; dins altres configuracions navega dins de les opcions |
| Esc | Surt de configuració; tanca la finestra expandida |

## Implementació (component web)

### `<video-audio-player-component>`

Paquet: core. Sense esdeveniments declarats.

**Propietats**

| Propietat | Atribut HTML | Descripció | Tipus | Per defecte |
|---|---|---|---|---|
| `aspectRatio` | `aspect-ratio` | Relació d'aspecte del reproductor: proporció entre l'amplada i l'alçada del reproductor multimèdia. Opcions: `16:9`, `1:1`, `4:3`. Opcional | string | `16:9` |
| `caption` | `caption` | Text sota l'àudio o vídeo (peu). Opcional | string | `undefined` |
| `titleVideoAudio` | `title-video-audio` | Títol per a accessibilitat. Opcional | string | `undefined` |
| `url` | `url` | URL de l'àudio o vídeo. Opcional | string | `undefined` |

**Variants**

| Propietat | Opcions | Valor predeterminat |
|---|---|---|
| `aspectRatio` | `16:9` `4:3` `1:1` | `16:9` |

**Exemple d'ús**

```html
<!-- /index.html -->
<video-audio-player-component
    aspect-ratio="16:9"
    url="https://youtu.be/8Win0ACfdNo?si=F9k_d364xXaSnORY" 
    title-video-audio="Vídeo de ejemplo Youtube" 
    caption="Este es el pie del vídeo de Youtube"
  >
</video-audio-player-component>
```

**Exemple d'instància (PDF)**

```html
<video-audio-player-component
aspect-ratio='16:9'
caption="texto-ejemplo"
title-video-audio="texto-ejemplo"
url="texto-ejemplo"
></video-audio-player-component>
```

## Historial de versions

| Versió Figma | Versió Github | Data | Descripció |
|---|---|---|---|
| 12.5.0 | 9.1.0 | 02 octubre, 2026 | Disseny: s'han afegit botons de salt de 10 segons com a alternativa a l'arrossegament de la barra de progrés; s'ha afegit la propietat Show skip buttons al Controls Container de vídeo; s'han afegit botons de pujar i baixar el volum |
| 6.0.0 | 11.0.0 | 19 juny, 2026 | Desenvolupament: es corregeix un avís de la consola de Google Chrome i la relació d'aspecte en prémer play al vídeo |
| 6.0.0 | 6.2.1 | 3 octubre, 2025 | Desenvolupament: nova propietat afegida o eliminada |
| 6.0.0 | 6.1.0 | 12 setembre, 2025 | Desenvolupament: resolució de problemes |
| 6.0.0 | 6.0.1 | 28 juliol, 2025 | Desenvolupament: resolució de problemes |
| 6.0.0 | 5.0.0 | 8 juliol, 2025 | Disseny: s'ha ajustat l'amplada màxima dels vídeos |
| 4.0.0 | 5.0.0 | 9 juny, 2025 | Desenvolupament del component |
| 4.0.0 | - | 2 maig, 2025 | Disseny i documentació del component |

## Vegeu també
- [Botons](component-botons.md): per a realitzar accions.
- [Imatge](fonaments-imatge.md)
- [Indicador de funció](component-indicador-de-funcio.md): per mostrar un text breu en passar el cursor per sobre d'una icona o activador.
