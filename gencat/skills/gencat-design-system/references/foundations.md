# Foundations — Sistema de Disseny Gencat

## Colors

### Color de marca
| Token | Valor | Ús |
|-------|-------|-----|
| `--color-brand-primary` | `#C00000` | Vermell Gencat — accions, links, accents, CTA |

### Colors de text
| Token | Valor | Ús |
|-------|-------|-----|
| `--color-text-primary` | `#333333` | Text principal, títols, cos de text |
| `--color-text-secondary` | `#5C5C5C` | Text secundari, metadades, captions |
| `--color-text-disabled` | `#9E9E9E` | Text desactivat |
| `--color-text-inverse` | `#FFFFFF` | Text sobre fons fosc o de color |

### Colors de fons
| Token | Valor | Ús |
|-------|-------|-----|
| `--color-bg-default` | `rgb(250, 250, 250)` | Fons de pàgina |
| `--color-bg-white` | `#FFFFFF` | Fons de targetes, panells |
| `--color-bg-subtle` | `#F5F5F5` | Fons de seccions secundàries |

### Colors d'estat
| Estat | Color | Ús |
|-------|-------|-----|
| Èxit / Success | `#2E7D32` | Confirmació, validació positiva |
| Avís / Warning | `#ED6C02` | Alertes, avisos d'atenció |
| Error | `#C00000` | Errors, validació negativa |
| Informatiu / Info | `#0288D1` | Informació neutral |

---

## Tipografia

**Font exclusiva:** Open Sans (Google Fonts)

```css
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,300..800;1,300..800&display=swap');
```

### Escala tipogràfica

| Element | Mida | Pes | Line-height | Ús |
|---------|------|-----|-------------|-----|
| H1 | 2rem (32px) | 700 | 1.25 | Títol principal de pàgina |
| H2 | 1.5rem (24px) | 700 | 1.3 | Títol de secció |
| H3 | 1.25rem (20px) | 600 | 1.4 | Subtítol |
| H4 | 1.125rem (18px) | 600 | 1.4 | Títol de component |
| H5 | 1rem (16px) | 600 | 1.5 | Títol menor |
| Body L | 1rem (16px) | 400 | 1.5 | Cos de text estàndard |
| Body M | 0.875rem (14px) | 400 | 1.5 | Text secundari, descripcions |
| Body S | 0.75rem (12px) | 400 | 1.5 | Captions, etiquetes petites |
| Label | 0.875rem (14px) | 600 | 1.4 | Etiquetes de formulari |
| Button | 0.875rem (14px) | 600 | 1 | Text de botons |

---

## Espaiat

Base: `8px` (0.5rem)

| Token | Valor | Ús típic |
|-------|-------|----------|
| `--space-1` | 4px | Espaiat intern mínim |
| `--space-2` | 8px | Espaiat base |
| `--space-3` | 12px | Espaiat petit |
| `--space-4` | 16px | Espaiat estàndard |
| `--space-5` | 20px | Espaiat mitjà |
| `--space-6` | 24px | Espaiat entre elements |
| `--space-8` | 32px | Espaiat gran |
| `--space-10` | 40px | Espaiat de secció |
| `--space-12` | 48px | Espaiat de bloc |
| `--space-16` | 64px | Espaiat entre seccions |

---

## Grid i punts de tall

| Breakpoint | Amplada | Columnes | Gutter |
|-----------|---------|----------|--------|
| Mobile (xs) | < 576px | 4 | 16px |
| Tablet (sm) | ≥ 576px | 8 | 24px |
| Tablet L (md) | ≥ 768px | 12 | 24px |
| Desktop (lg) | ≥ 992px | 12 | 24px |
| Desktop L (xl) | ≥ 1200px | 12 | 32px |

---

## Arrodoniment (Border Radius)

| Token | Valor | Ús |
|-------|-------|-----|
| `--radius-sm` | 4px | Inputs, botons petits |
| `--radius-md` | 8px | Targetes, modals |
| `--radius-lg` | 12px | Contenidors grans |
| `--radius-xl` | 16px | Panells destacats |
| `--radius-full` | 9999px | Xips, badges, botons arrodonits |

---

## Elevació (Ombres)

| Token | Valor | Ús |
|-------|-------|-----|
| `--shadow-sm` | `0 1px 3px rgba(0,0,0,0.12)` | Targetes en repòs |
| `--shadow-md` | `0 4px 6px rgba(0,0,0,0.1)` | Targetes en hover |
| `--shadow-lg` | `0 10px 15px rgba(0,0,0,0.1)` | Modals, dropdowns |
| `--shadow-xl` | `0 20px 25px rgba(0,0,0,0.1)` | Panells emergents |

---

## Iconografia

El sistema utilitza un conjunt estandarditzat d'icones. Sempre usa les icones del sistema; evita introduir biblioteques externes d'icones si no formen part del sistema.

---

## Variables CSS (Tokens complets)

```css
:root {
  /* Marca */
  --color-brand-primary:    #C00000;

  /* Text */
  --color-text-primary:     #333333;
  --color-text-secondary:   #5C5C5C;
  --color-text-disabled:    #9E9E9E;
  --color-text-inverse:     #FFFFFF;

  /* Fons */
  --color-bg-default:       #FAFAFA;
  --color-bg-white:         #FFFFFF;
  --color-bg-subtle:        #F5F5F5;

  /* Estat */
  --color-success:          #2E7D32;
  --color-warning:          #ED6C02;
  --color-error:            #C00000;
  --color-info:             #0288D1;

  /* Font */
  --font-family:            'Open Sans', sans-serif;
  --font-size-base:         16px;

  /* Espaiat */
  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-5: 20px;
  --space-6: 24px;
  --space-8: 32px;
  --space-10: 40px;
  --space-12: 48px;
  --space-16: 64px;

  /* Arrodoniment */
  --radius-sm:   4px;
  --radius-md:   8px;
  --radius-lg:   12px;
  --radius-xl:   16px;
  --radius-full: 9999px;

  /* Ombres */
  --shadow-sm: 0 1px 3px rgba(0,0,0,0.12);
  --shadow-md: 0 4px 6px rgba(0,0,0,0.10);
  --shadow-lg: 0 10px 15px rgba(0,0,0,0.10);
  --shadow-xl: 0 20px 25px rgba(0,0,0,0.10);
}
```
