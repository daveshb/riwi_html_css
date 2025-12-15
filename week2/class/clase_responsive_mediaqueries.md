# Responsive Design con Media Queries y Optimización CSS

## Introducción

Con el auge de los dispositivos móviles y la variedad de pantallas, las **Media Queries** se han convertido en una herramienta esencial para el desarrollo web. Permiten aplicar estilos CSS específicos dependiendo del tamaño de la pantalla, la orientación, la resolución y otras características del dispositivo.

En esta clase aprenderás a crear diseños responsivos y a optimizar tu código CSS para mejorar el rendimiento de tus sitios web.

---

## ¿Qué son las Media Queries?

Las **Media Queries** son reglas CSS que permiten aplicar estilos condicionales basados en características del dispositivo, como:

- Ancho y alto de la pantalla
- Orientación (portrait o landscape)
- Resolución de pantalla
- Tipo de dispositivo (screen, print, etc.)

### Sintaxis Básica

```css
@media (condición) {
  /* Estilos que se aplicarán cuando la condición sea verdadera */
}
```

### Ejemplo Básico

```css
@media (max-width: 768px) {
  body {
    background-color: lightblue;
  }
}
```

En este ejemplo, el fondo del sitio cambiará a color azul claro en pantallas de menos de 768 píxeles de ancho, lo que incluye la mayoría de las tablets y dispositivos móviles.

---

## Breakpoints Sugeridos para Diferentes Dispositivos

Los **breakpoints** son los puntos en los que el diseño cambia para adaptarse a diferentes tamaños de pantalla. Aquí están los breakpoints estándar recomendados:

### Breakpoints Tradicionales

```css
/* Extra small devices (phones, menos de 600px) */
@media (max-width: 599px) {
  /* Estilos para móviles pequeños */
}

/* Small devices (phones, 600px y más) */
@media (min-width: 600px) {
  /* Estilos para móviles grandes */
}

/* Medium devices (tablets, 768px y más) */
@media (min-width: 768px) {
  /* Estilos para tablets */
}

/* Large devices (desktops, 992px y más) */
@media (min-width: 992px) {
  /* Estilos para laptops/desktops */
}

/* Extra large devices (large desktops, 1200px y más) */
@media (min-width: 1200px) {
  /* Estilos para pantallas grandes */
}

/* XXL devices (larger desktops, 1400px y más) */
@media (min-width: 1400px) {
  /* Estilos para pantallas extra grandes */
}
```

### Breakpoints Modernos (Mobile-First)

El enfoque **Mobile-First** implica diseñar primero para dispositivos móviles y luego añadir estilos para pantallas más grandes:

```css
/* Base styles: Mobile (por defecto) */
body {
  font-size: 16px;
}

/* Small tablets (600px y más) */
@media (min-width: 37.5em) {  /* 600px / 16 = 37.5em */
  body {
    font-size: 17px;
  }
}

/* Tablets (768px y más) */
@media (min-width: 48em) {  /* 768px / 16 = 48em */
  body {
    font-size: 18px;
  }
}

/* Desktop (1024px y más) */
@media (min-width: 64em) {  /* 1024px / 16 = 64em */
  body {
    font-size: 19px;
  }
}

/* Large Desktop (1280px y más) */
@media (min-width: 80em) {  /* 1280px / 16 = 80em */
  body {
    font-size: 20px;
  }
}
```

---

## Forma Moderna de Escribir Media Queries

### 1. Media Queries con Rangos (Sintaxis Moderna)

La nueva sintaxis de rangos hace que las Media Queries sean más legibles y fáciles de escribir:

#### Sintaxis Antigua vs Moderna

```css
/* ❌ Sintaxis antigua */
@media (min-width: 768px) and (max-width: 1023px) {
  /* Estilos para tablets */
}

/* ✅ Sintaxis moderna con rangos */
@media (768px <= width < 1024px) {
  /* Estilos para tablets */
}

/* ✅ También puedes usar operadores de comparación */
@media (width >= 768px) {
  /* Estilos para tablets y superiores */
}

@media (width < 768px) {
  /* Estilos para móviles */
}
```

### 2. Container Queries (Consultas de Contenedor)

Las **Container Queries** permiten aplicar estilos basados en el tamaño del contenedor padre, no del viewport:

```css
/* Definir un contenedor */
.container {
  container-type: inline-size;
  container-name: main;
}

/* Consulta basada en el contenedor */
@container main (min-width: 500px) {
  .card {
    display: flex;
  }
}
```

### 3. Media Queries con Lógica Moderna

```css
/* Operador OR (,) */
@media (width < 600px), (orientation: portrait) {
  /* Se aplica si el ancho es menor a 600px O está en orientación portrait */
}

/* Operador AND (and) */
@media (width >= 768px) and (height >= 600px) {
  /* Se aplica si AMBAS condiciones son verdaderas */
}

/* Operador NOT */
@media not (width < 768px) {
  /* Se aplica cuando el ancho NO es menor a 768px */
}
```

### 4. Prefers Color Scheme (Modo oscuro)

```css
/* Modo claro (por defecto) */
:root {
  --bg-color: #ffffff;
  --text-color: #000000;
}

/* Modo oscuro */
@media (prefers-color-scheme: dark) {
  :root {
    --bg-color: #1a1a1a;
    --text-color: #ffffff;
  }
}

body {
  background-color: var(--bg-color);
  color: var(--text-color);
}
```

---

## Diseño Responsive con Flexbox y Grid

Gracias a las Media Queries, los diseños pueden cambiar dependiendo del ancho de la pantalla. Esto asegura que la estructura de tu página web sea accesible y fácil de navegar en dispositivos móviles, tablets, laptops y monitores de escritorio.

### Demostración con Flexbox

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Responsive Flexbox</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    .container {
      display: flex;
      flex-direction: column;
      gap: 1rem;
      padding: 1rem;
    }

    .item {
      background-color: #3498db;
      color: white;
      padding: 2rem;
      text-align: center;
      border-radius: 8px;
    }

    /* Tablets (768px y más) */
    @media (min-width: 48em) {
      .container {
        flex-direction: row;
        flex-wrap: wrap;
      }

      .item {
        flex: 1 1 calc(50% - 1rem);
      }
    }

    /* Desktop (1024px y más) */
    @media (min-width: 64em) {
      .item {
        flex: 1 1 calc(33.333% - 1rem);
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="item">Item 1</div>
    <div class="item">Item 2</div>
    <div class="item">Item 3</div>
    <div class="item">Item 4</div>
    <div class="item">Item 5</div>
    <div class="item">Item 6</div>
  </div>
</body>
</html>
```

### Demostración con Grid

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Responsive Grid</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    .grid-container {
      display: grid;
      grid-template-columns: 1fr;
      gap: 1rem;
      padding: 1rem;
    }

    .grid-item {
      background-color: #2ecc71;
      color: white;
      padding: 2rem;
      text-align: center;
      border-radius: 8px;
    }

    /* Tablets (768px y más) */
    @media (min-width: 48em) {
      .grid-container {
        grid-template-columns: repeat(2, 1fr);
      }
    }

    /* Desktop (1024px y más) */
    @media (min-width: 64em) {
      .grid-container {
        grid-template-columns: repeat(3, 1fr);
      }
    }

    /* Large Desktop (1280px y más) */
    @media (min-width: 80em) {
      .grid-container {
        grid-template-columns: repeat(4, 1fr);
      }
    }
  </style>
</head>
<body>
  <div class="grid-container">
    <div class="grid-item">Item 1</div>
    <div class="grid-item">Item 2</div>
    <div class="grid-item">Item 3</div>
    <div class="grid-item">Item 4</div>
    <div class="grid-item">Item 5</div>
    <div class="grid-item">Item 6</div>
    <div class="grid-item">Item 7</div>
    <div class="grid-item">Item 8</div>
  </div>
</body>
</html>
```

---

## Imágenes Responsivas

Las imágenes deben adaptarse automáticamente al tamaño del contenedor usando el valor `max-width: 100%`.

### Demostración

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Imágenes Responsivas</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    .image-container {
      padding: 1rem;
      max-width: 1200px;
      margin: 0 auto;
    }

    /* Método 1: max-width */
    .responsive-img {
      max-width: 100%;
      height: auto;
      display: block;
      border-radius: 8px;
      margin-bottom: 2rem;
    }

    /* Método 2: object-fit */
    .cover-img {
      width: 100%;
      height: 300px;
      object-fit: cover;
      border-radius: 8px;
    }

    /* Método 3: picture element con diferentes imágenes */
    .picture-responsive img {
      width: 100%;
      height: auto;
      border-radius: 8px;
    }
  </style>
</head>
<body>
  <div class="image-container">
    <h2>Método 1: max-width: 100%</h2>
    <img src="https://via.placeholder.com/1200x600" alt="Imagen responsive" class="responsive-img">

    <h2>Método 2: object-fit: cover</h2>
    <img src="https://via.placeholder.com/1200x600" alt="Imagen con cover" class="cover-img">

    <h2>Método 3: Picture Element</h2>
    <picture class="picture-responsive">
      <source media="(min-width: 1024px)" srcset="https://via.placeholder.com/1200x600">
      <source media="(min-width: 768px)" srcset="https://via.placeholder.com/800x400">
      <img src="https://via.placeholder.com/600x300" alt="Imagen adaptativa">
    </picture>
  </div>
</body>
</html>
```

---

---

## Optimización CSS

La **optimización del CSS** es fundamental para garantizar que las hojas de estilo sean ligeras, rápidas y fáciles de mantener. El uso excesivo de reglas o estilos ineficientes puede ralentizar el tiempo de carga de una página, afectar la experiencia del usuario y dificultar el mantenimiento del código.

### 1. Minificación de CSS

La **minificación** implica eliminar todos los espacios, saltos de línea y comentarios del archivo CSS, reduciendo su tamaño sin afectar su funcionalidad.

```css
/* ❌ CSS sin minificar */
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 20px;
  background-color: #f0f0f0;
}

/* ✅ CSS minificado */
.container{display:flex;justify-content:center;align-items:center;padding:20px;background-color:#f0f0f0}
```

**Herramientas de minificación:**
- [cssnano](https://cssnano.co/)
- [clean-css](https://github.com/clean-css/clean-css)
- [PostCSS](https://postcss.org/)

### 2. Evitar Selectores Complejos

Evita el uso de selectores CSS demasiado específicos o anidados innecesariamente, ya que esto puede aumentar la carga del navegador. Opta por selectores simples y directos.

```css
/* ❌ Selector complejo e ineficiente */
div.container > ul > li > a.link:hover {
  color: blue;
}

/* ✅ Selector simple y directo */
.nav-link:hover {
  color: blue;
}
```

### 3. Agrupar Reglas Comunes

Agrupa reglas comunes para evitar la duplicación de código y mejorar la legibilidad.

```css
/* ❌ Código duplicado */
.header {
  font-family: Arial, sans-serif;
  color: #333;
}

.footer {
  font-family: Arial, sans-serif;
  color: #333;
}

.sidebar {
  font-family: Arial, sans-serif;
  color: #333;
}

/* ✅ Código agrupado */
.header,
.footer,
.sidebar {
  font-family: Arial, sans-serif;
  color: #333;
}
```

### 4. Usar Variables CSS (Custom Properties)

Las **variables CSS** ayudan a mantener un código más limpio y fácil de actualizar, además de evitar errores.

```css
/* Definir variables */
:root {
  --primary-color: #3498db;
  --secondary-color: #2ecc71;
  --text-color: #333;
  --spacing-unit: 1rem;
  --border-radius: 8px;
}

/* Usar variables */
.button {
  background-color: var(--primary-color);
  color: white;
  padding: var(--spacing-unit);
  border-radius: var(--border-radius);
}

.button-secondary {
  background-color: var(--secondary-color);
  color: white;
  padding: var(--spacing-unit);
  border-radius: var(--border-radius);
}
```

### 5. Preprocesadores CSS

Preprocesadores como **Sass** o **LESS** permiten escribir código CSS de forma más modular, utilizando variables, anidaciones, mixins y otras características avanzadas que mejoran la estructura y mantenibilidad del CSS.

```scss
// Ejemplo con Sass
$primary-color: #3498db;
$secondary-color: #2ecc71;

@mixin button-styles {
  padding: 1rem 2rem;
  border-radius: 8px;
  border: none;
  cursor: pointer;
}

.button {
  @include button-styles;
  background-color: $primary-color;
  
  &:hover {
    background-color: darken($primary-color, 10%);
  }
}

.button-secondary {
  @include button-styles;
  background-color: $secondary-color;
}
```

### 6. CSS Crítico y Carga Diferida

La **carga diferida de CSS** implica cargar primero los estilos más esenciales (CSS crítico) y luego el resto de la hoja de estilos de manera asíncrona o bajo demanda, optimizando el tiempo de carga inicial.

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS Crítico</title>
  
  <!-- CSS Crítico inline para carga rápida -->
  <style>
    /* Estilos críticos para la primera vista */
    body {
      margin: 0;
      font-family: Arial, sans-serif;
    }
    .header {
      background-color: #333;
      color: white;
      padding: 1rem;
    }
  </style>

  <!-- Preload para CSS no crítico -->
  <link rel="preload" href="styles.css" as="style" onload="this.onload=null;this.rel='stylesheet'">
  <noscript><link rel="stylesheet" href="styles.css"></noscript>
</head>
<body>
  <header class="header">
    <h1>Mi Sitio Web</h1>
  </header>
  <main>
    <!-- Contenido -->
  </main>
</body>
</html>
```

---

## Ejemplo Completo: Sitio Responsive Optimizado

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Sitio Responsive Completo</title>
  <style>
    /* Variables CSS */
    :root {
      --primary-color: #3498db;
      --secondary-color: #2ecc71;
      --dark-color: #2c3e50;
      --light-color: #ecf0f1;
      --text-color: #333;
      --spacing: 1rem;
      --border-radius: 8px;
      --transition: all 0.3s ease;
    }

    /* Reset y base */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: Arial, sans-serif;
      line-height: 1.6;
      color: var(--text-color);
    }

    /* Header */
    .header {
      background-color: var(--dark-color);
      color: white;
      padding: var(--spacing);
    }

    .nav {
      display: flex;
      flex-direction: column;
      gap: var(--spacing);
    }

    .nav-link {
      color: white;
      text-decoration: none;
      padding: 0.5rem;
      transition: var(--transition);
    }

    .nav-link:hover {
      background-color: var(--primary-color);
      border-radius: var(--border-radius);
    }

    /* Hero Section */
    .hero {
      background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
      color: white;
      text-align: center;
      padding: 3rem var(--spacing);
    }

    .hero h1 {
      font-size: 2rem;
      margin-bottom: var(--spacing);
    }

    /* Main Content */
    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: var(--spacing);
    }

    .grid {
      display: grid;
      grid-template-columns: 1fr;
      gap: var(--spacing);
    }

    .card {
      background-color: white;
      border-radius: var(--border-radius);
      padding: var(--spacing);
      box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
      transition: var(--transition);
    }

    .card:hover {
      transform: translateY(-5px);
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    }

    .card img {
      max-width: 100%;
      height: auto;
      border-radius: var(--border-radius);
    }

    /* Footer */
    .footer {
      background-color: var(--dark-color);
      color: white;
      text-align: center;
      padding: 2rem var(--spacing);
      margin-top: 2rem;
    }

    /* Tablets (768px y más) */
    @media (min-width: 48em) {
      .nav {
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
      }

      .hero h1 {
        font-size: 3rem;
      }

      .grid {
        grid-template-columns: repeat(2, 1fr);
      }
    }

    /* Desktop (1024px y más) */
    @media (min-width: 64em) {
      .hero h1 {
        font-size: 4rem;
      }

      .grid {
        grid-template-columns: repeat(3, 1fr);
      }
    }

    /* Modo oscuro */
    @media (prefers-color-scheme: dark) {
      :root {
        --text-color: #ecf0f1;
        --light-color: #2c3e50;
      }

      body {
        background-color: #1a1a1a;
      }

      .card {
        background-color: #2c3e50;
        color: white;
      }
    }
  </style>
</head>
<body>
  <header class="header">
    <nav class="nav">
      <div class="logo">Mi Sitio</div>
      <div>
        <a href="#" class="nav-link">Inicio</a>
        <a href="#" class="nav-link">Sobre Mí</a>
        <a href="#" class="nav-link">Proyectos</a>
        <a href="#" class="nav-link">Contacto</a>
      </div>
    </nav>
  </header>

  <section class="hero">
    <h1>Bienvenido a Mi Sitio</h1>
    <p>Diseño responsive y optimizado</p>
  </section>

  <main class="container">
    <div class="grid">
      <div class="card">
        <img src="https://via.placeholder.com/400x300" alt="Proyecto 1">
        <h3>Proyecto 1</h3>
        <p>Descripción del proyecto</p>
      </div>
      <div class="card">
        <img src="https://via.placeholder.com/400x300" alt="Proyecto 2">
        <h3>Proyecto 2</h3>
        <p>Descripción del proyecto</p>
      </div>
      <div class="card">
        <img src="https://via.placeholder.com/400x300" alt="Proyecto 3">
        <h3>Proyecto 3</h3>
        <p>Descripción del proyecto</p>
      </div>
    </div>
  </main>

  <footer class="footer">
    <p>&copy; 2025 Mi Sitio. Todos los derechos reservados.</p>
  </footer>
</body>
</html>
```

---

## Conclusión

**¡Felicitaciones, Coder!**

Ahora que entiendes cómo usar Media Queries para crear diseños responsivos y aplicar buenas prácticas de optimización, estás en camino de diseñar sitios web eficientes y adaptables a cualquier dispositivo. La capacidad de CSS para crear layouts flexibles es solo una parte del proceso; asegurarse de que el código sea optimizado y escalable es lo que verdaderamente separa a un desarrollador avanzado.

**Así que, ¡sigue practicando!**

Implementa Media Queries para mejorar la experiencia en diferentes dispositivos y pon en marcha las estrategias de optimización para hacer que tus páginas carguen más rápido y sean más fáciles de mantener.

---

## Recursos Adicionales

- [MDN Web Docs - Media Queries](https://developer.mozilla.org/es/docs/Web/CSS/Media_Queries)
- [Can I Use - CSS Features](https://caniuse.com/)
- [web.dev - Responsive Design](https://web.dev/responsive-web-design-basics/)
- [CSS-Tricks - Media Queries Guide](https://css-tricks.com/a-complete-guide-to-css-media-queries/)

---

## Ejercicio Práctico

### Enunciado: Tienda en Línea Responsive

Crea una página web de una **tienda en línea de electrónicos** que sea completamente responsive y optimizada. La página debe adaptarse perfectamente a móviles, tablets y desktops.

#### Requerimientos:

1. **Header Responsive**
   - Logo a la izquierda
   - Menú de navegación:
     - Móvil: Hamburger menu (vertical)
     - Tablet+: Menú horizontal
   - Carrito de compras (ícono)
   - Barra de búsqueda
   - Altura: 60px en móvil, 80px en desktop

2. **Banner Hero**
   - Imagen de fondo responsive
   - Título principal
   - Subtítulo
   - Botón CTA "Ver Ofertas"
   - Altura mínima: 300px móvil, 500px desktop

3. **Categorías (Grid Responsive)**
   - Móvil: 2 columnas
   - Tablet: 3 columnas
   - Desktop: 4 columnas
   - Large Desktop: 6 columnas
   - Cada categoría con:
     - Ícono o imagen
     - Nombre de categoría
     - Hover effect

4. **Productos Destacados (Grid Responsive)**
   - Móvil: 1 columna
   - Tablet: 2 columnas
   - Desktop: 3 columnas
   - Large Desktop: 4 columnas
   - Cada tarjeta de producto:
     - Imagen responsive
     - Nombre del producto
     - Precio (antes y después de descuento)
     - Calificación (estrellas)
     - Botón "Agregar al carrito"
     - Badge de "Nuevo" o "Descuento"

5. **Newsletter Section**
   - Centrado en todas las pantallas
   - Input de email + botón
   - Móvil: Stack vertical
   - Desktop: En línea horizontal

6. **Footer Responsive**
   - Móvil: 1 columna (apilado)
   - Tablet: 2 columnas
   - Desktop: 4 columnas
   - Contenido:
     - Sobre nosotros
     - Enlaces rápidos
     - Contacto
     - Redes sociales
   - Copyright al final

#### Requisitos Técnicos CSS:

##### ✅ Media Queries
- Usar al menos 4 breakpoints diferentes
- Implementar sintaxis moderna de rangos (width >= X)
- Usar media query para `prefers-color-scheme` (modo oscuro)
- Media query para orientación (portrait/landscape)

##### ✅ Responsive
- Mobile-first approach
- Imágenes responsive (`max-width: 100%`)
- Usar `picture` element para imágenes adaptativas
- Grid responsive con `repeat(auto-fit, minmax())`

##### ✅ Unidades
- Usar `rem` para font-size
- Usar `em` para padding/margin relativos
- Usar `%` o `fr` para layouts
- Evitar px fijos excepto borders

##### ✅ Optimización
- Usar variables CSS (al menos 8 variables)
- Agrupar selectores comunes
- Evitar selectores complejos
- Código limpio y comentado
- CSS crítico separado del resto

##### ✅ Características Modernas
- Container queries (opcional)
- Custom properties con fallbacks
- `clamp()` para responsive typography
- `aspect-ratio` para mantener proporciones

#### Breakpoints Requeridos:

```css
/* Mobile (base) */
/* Por defecto, sin media query */

/* Small Mobile (375px) */
@media (min-width: 23.4375em) { }

/* Mobile Large (480px) */
@media (min-width: 30em) { }

/* Tablet Small (600px) */
@media (min-width: 37.5em) { }

/* Tablet (768px) */
@media (min-width: 48em) { }

/* Desktop Small (992px) */
@media (min-width: 62em) { }

/* Desktop (1024px) */
@media (min-width: 64em) { }

/* Desktop Large (1280px) */
@media (min-width: 80em) { }

/* Desktop XL (1440px) */
@media (min-width: 90em) { }
```

#### Contenido de Ejemplo:

```
Header:
  Logo: "TechStore"
  Nav: Inicio | Productos | Ofertas | Soporte | Contacto
  
Categorías:
  - Laptops
  - Smartphones
  - Tablets
  - Accesorios
  - Audio
  - Gaming

Productos (6 ejemplos):
  1. "MacBook Pro 16" - $2,499 (antes $2,799) - ⭐⭐⭐⭐⭐
  2. "iPhone 15 Pro" - $999 (antes $1,099) - ⭐⭐⭐⭐½
  3. "iPad Air" - $599 (antes $649) - ⭐⭐⭐⭐⭐
  4. "AirPods Pro" - $249 (antes $279) - ⭐⭐⭐⭐
  5. "PlayStation 5" - $499 - ⭐⭐⭐⭐⭐
  6. "Galaxy Watch" - $299 (antes $349) - ⭐⭐⭐⭐

Footer:
  Sobre Nosotros | Enlaces | Contacto | Síguenos
  © 2025 TechStore. Todos los derechos reservados.
```

#### Paleta de Colores:

```css
:root {
  --primary: #2563eb;      /* Azul */
  --secondary: #7c3aed;    /* Púrpura */
  --accent: #f59e0b;       /* Amarillo/Naranja */
  --success: #10b981;      /* Verde */
  --danger: #ef4444;       /* Rojo */
  --dark: #1f2937;         /* Gris oscuro */
  --light: #f3f4f6;        /* Gris claro */
  --white: #ffffff;
  --text: #374151;
  --border: #d1d5db;
}

/* Modo oscuro */
@media (prefers-color-scheme: dark) {
  :root {
    --dark: #f3f4f6;
    --light: #1f2937;
    --white: #111827;
    --text: #e5e7eb;
    --border: #4b5563;
  }
}
```

#### Desafío Extra:

-  Agregar animaciones y transiciones suaves
-  Implementar un carrusel de productos con CSS
-  Crear un sistema de filtros responsive
-  Agregar lazy loading para imágenes
-  Implementar skeleton loaders
-  Usar `clamp()` para fluid typography
-  Implementar Container Queries
-  Agregar estados hover, focus y active detallados
-  Crear un modal responsive para producto
-  Implementar un sistema de notificaciones toast

#### Criterios de Evaluación:

- **Responsive (30%)**: Se adapta perfectamente a todos los tamaños
- **Optimización (25%)**: Código limpio, variables CSS, selectores eficientes
- **Media Queries (20%)**: Uso correcto y moderno de media queries
- **Diseño Visual (15%)**: Atractivo, consistente, buena UX
- **Código (10%)**: Limpio, comentado, bien estructurado

¡Buena suerte con tu proyecto!
