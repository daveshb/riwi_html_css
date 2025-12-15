# CSS Grid - Clase Completa

## Introducción

**CSS Grid** es un método de diseño que nos permite crear layouts de páginas web en una estructura de filas y columnas. Es una herramienta más intuitiva y robusta para desarrollar layouts complejos, ya que a diferencia de Flexbox, que funciona en una dimensión (ya sea en fila o columna), Grid trabaja en dos dimensiones simultáneamente, facilitando el control sobre el diseño global de una página.

---

## ¿Qué es CSS Grid?

**CSS Grid Layout** es un sistema de diseño bidimensional que organiza el contenido en filas y columnas. A diferencia de Flexbox, Grid es más potente para crear layouts complejos porque:

- **Controla filas y columnas**: Puedes definir el tamaño y número de filas y columnas
- **Trabaja en 2 dimensiones**: Alinea elementos tanto horizontal como verticalmente de forma simultánea
- **Mayor control**: Permite colocar elementos de forma más precisa en la cuadrícula
- **Ideal para layouts complejos**: Perfecto para diseñar páginas completas con múltiples secciones

---

## Sintaxis Básica de CSS Grid

Para usar CSS Grid, aplicamos la propiedad `display: grid` a un contenedor. El contenedor Grid permite a sus elementos hijos ser distribuidos de manera controlada mediante propiedades adicionales.

```css
.container {
  display: grid;
}
```

### Demostración

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Grid Básico</title>
  <style>
    .container {
      display: grid;
      background-color: #f0f0f0;
      padding: 20px;
      gap: 10px;
    }

    .item {
      background-color: #3498db;
      color: white;
      padding: 20px;
      text-align: center;
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

---

## Propiedad `grid-template-columns` y `grid-template-rows`

Las propiedades `grid-template-columns` y `grid-template-rows` son las que definen cuántas columnas y filas tendrá el grid y el tamaño de cada una.

- **`grid-template-columns`**: Define el tamaño de las columnas
- **`grid-template-rows`**: Define el tamaño de las filas

### Demostración

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>grid-template-columns y grid-template-rows</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
    }

    .container {
      display: grid;
      grid-template-columns: 200px 1fr;
      grid-template-rows: 100px auto;
      background-color: #ecf0f1;
      gap: 10px;
      margin: 20px 0;
    }

    .item {
      background-color: #2ecc71;
      color: white;
      padding: 20px;
      text-align: center;
    }

    .item1 { grid-column: 1; grid-row: 1; }
    .item2 { grid-column: 2; grid-row: 1; }
    .item3 { grid-column: 1 / 3; grid-row: 2; }
  </style>
</head>
<body>
  <h3>Grid con columnas fijas y flex</h3>
  <p>Primera columna: 200px (fija) | Segunda columna: 1fr (flexible)</p>
  <p>Primera fila: 100px (fija) | Segunda fila: auto (automática)</p>
  
  <div class="container">
    <div class="item">Encabezado 1</div>
    <div class="item">Encabezado 2</div>
    <div class="item">Contenido que abarca todo</div>
  </div>

  <h3>Ejemplo con 3 columnas iguales</h3>
  <div style="display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 10px; background-color: #ecf0f1; padding: 20px;">
    <div style="background-color: #e74c3c; color: white; padding: 20px; text-align: center;">Columna 1</div>
    <div style="background-color: #e74c3c; color: white; padding: 20px; text-align: center;">Columna 2</div>
    <div style="background-color: #e74c3c; color: white; padding: 20px; text-align: center;">Columna 3</div>
  </div>
</body>
</html>
```

---

## La Unidad `fr` (Fracción)

Una unidad clave en CSS Grid es la unidad **Fr (Fracción)**, que distribuye el espacio restante disponible entre las columnas o filas. A diferencia de las unidades como `px` o `%`, la unidad `fr` es muy flexible para crear layouts adaptativos.

### Cómo funciona:

- `1fr` = una fracción del espacio disponible
- `2fr` = dos fracciones (el doble del espacio)
- Puedes combinar `fr` con unidades fijas como `px`

### Demostración

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Unidad fr en Grid</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
    }

    .container {
      display: grid;
      grid-template-columns: 1fr 2fr 1fr;
      background-color: #ecf0f1;
      gap: 10px;
      margin: 20px 0;
    }

    .item {
      background-color: #9b59b6;
      color: white;
      padding: 20px;
      text-align: center;
    }

    .container2 {
      display: grid;
      grid-template-columns: 200px 1fr 1fr;
      background-color: #ecf0f1;
      gap: 10px;
      margin: 20px 0;
    }
  </style>
</head>
<body>
  <h3>Ejemplo 1: 1fr 2fr 1fr</h3>
  <p>La segunda columna ocupa el doble de espacio que la primera y tercera</p>
  <div class="container">
    <div class="item">1fr</div>
    <div class="item">2fr (doble)</div>
    <div class="item">1fr</div>
  </div>

  <h3>Ejemplo 2: Combinando px y fr</h3>
  <p>Primera columna: 200px fijos | Otras dos columnas: iguales y flexibles</p>
  <div class="container2">
    <div class="item">200px</div>
    <div class="item">1fr</div>
    <div class="item">1fr</div>
  </div>
</body>
</html>
```

---

## Propiedad `gap`

Para crear espacio entre las filas y columnas de un grid, usamos la propiedad `gap` (en versiones modernas) o `grid-gap`. Esto es equivalente a los márgenes entre los elementos, pero aplicado dentro del grid.

### Demostración

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>gap en Grid</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
    }

    .container-no-gap {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      background-color: #ecf0f1;
      padding: 20px;
      margin: 20px 0;
    }

    .container-gap {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 20px;
      background-color: #ecf0f1;
      padding: 20px;
      margin: 20px 0;
    }

    .item {
      background-color: #f39c12;
      color: white;
      padding: 20px;
      text-align: center;
    }
  </style>
</head>
<body>
  <h3>Sin gap</h3>
  <div class="container-no-gap">
    <div class="item">Item 1</div>
    <div class="item">Item 2</div>
    <div class="item">Item 3</div>
    <div class="item">Item 4</div>
    <div class="item">Item 5</div>
    <div class="item">Item 6</div>
  </div>

  <h3>Con gap: 20px</h3>
  <div class="container-gap">
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

---

## Propiedades `grid-column` y `grid-row`

Cada elemento dentro del grid puede ocupar más de una celda, ya sea en la dirección de las columnas o las filas. Para ello, se utilizan las propiedades:

- **`grid-column`**: Controla cuántas columnas ocupa un elemento y su posición
- **`grid-row`**: Controla cuántas filas ocupa un elemento y su posición

### Demostración

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>grid-column y grid-row</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
    }

    .container {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 10px;
      background-color: #ecf0f1;
      padding: 20px;
      margin: 20px 0;
    }

    .item {
      background-color: #1abc9c;
      color: white;
      padding: 20px;
      text-align: center;
    }

    .item-span-2-cols {
      grid-column: span 2;
    }

    .item-span-2-rows {
      grid-row: span 2;
    }

    .item-pos-1-1 {
      grid-column: 1;
      grid-row: 1;
    }
  </style>
</head>
<body>
  <h3>Elementos que abarcan múltiples celdas</h3>
  <div class="container">
    <div class="item">Item 1</div>
    <div class="item item-span-2-cols">Item 2 (abarca 2 columnas)</div>
    <div class="item">Item 3</div>
    <div class="item item-span-2-rows">Item 4<br>(abarca 2 filas)</div>
    <div class="item">Item 5</div>
    <div class="item">Item 6</div>
  </div>

  <h3>Usando notación grid-column: start / end</h3>
  <div style="display: grid; grid-template-columns: repeat(4, 1fr); gap: 10px; background-color: #ecf0f1; padding: 20px;">
    <div style="background-color: #34495e; color: white; padding: 20px; grid-column: 1 / 3;">Abarca de columna 1 a 3</div>
    <div style="background-color: #34495e; color: white; padding: 20px; grid-column: 3 / 5;">Abarca de columna 3 a 5</div>
    <div style="background-color: #34495e; color: white; padding: 20px;">Normal</div>
    <div style="background-color: #34495e; color: white; padding: 20px;">Normal</div>
    <div style="background-color: #34495e; color: white; padding: 20px;">Normal</div>
    <div style="background-color: #34495e; color: white; padding: 20px;">Normal</div>
  </div>
</body>
</html>
```

---

## Función `repeat()` y `auto-fit` / `auto-fill`

CSS Grid también ofrece funciones muy útiles como `repeat()`, que nos permite repetir un patrón de columnas o filas sin tener que escribir cada una manualmente. Además, podemos hacer uso de `auto-fit` y `auto-fill` para crear layouts que se ajusten automáticamente al tamaño de la pantalla.

### Valores:

- **`repeat(n, value)`**: Repite un número específico de columnas o filas
- **`auto-fit`**: Llena el espacio disponible con tantas columnas o filas como quepan
- **`auto-fill`**: Similar a `auto-fit`, pero deja el espacio vacío al final

### Demostración

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>repeat(), auto-fit y auto-fill</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
    }

    .container-repeat {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 10px;
      background-color: #ecf0f1;
      padding: 20px;
      margin: 20px 0;
    }

    .container-auto-fit {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      gap: 10px;
      background-color: #ecf0f1;
      padding: 20px;
      margin: 20px 0;
    }

    .item {
      background-color: #e67e22;
      color: white;
      padding: 20px;
      text-align: center;
    }
  </style>
</head>
<body>
  <h3>repeat(3, 1fr) - 3 columnas iguales</h3>
  <div class="container-repeat">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
    <div class="item">4</div>
    <div class="item">5</div>
    <div class="item">6</div>
  </div>

  <h3>repeat(auto-fit, minmax(150px, 1fr)) - Responsivo</h3>
  <p>Se adapta automáticamente: tantas columnas de al menos 150px como quepan</p>
  <div class="container-auto-fit">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
    <div class="item">4</div>
    <div class="item">5</div>
    <div class="item">6</div>
  </div>
</body>
</html>
```

---

## Alineación en CSS Grid

CSS Grid también ofrece control sobre la alineación y distribución de los elementos, tanto a nivel global (contenedor) como de cada elemento.

### Propiedades principales:

- **`justify-items`**: Alinea los elementos dentro del grid en el eje horizontal
- **`align-items`**: Alinea los elementos dentro del grid en el eje vertical
- **`justify-content`**: Alinea el grid completo en el eje horizontal
- **`align-content`**: Alinea el grid completo en el eje vertical

### Demostración

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Alineación en Grid</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
    }

    .container {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      height: 300px;
      gap: 10px;
      background-color: #ecf0f1;
      padding: 20px;
      margin: 20px 0;
    }

    .justify-center {
      justify-items: center;
    }

    .align-center {
      align-items: center;
    }

    .both-center {
      justify-items: center;
      align-items: center;
    }

    .item {
      background-color: #16a085;
      color: white;
      padding: 20px;
      text-align: center;
      width: 80px;
      height: 80px;
      display: flex;
      align-items: center;
      justify-content: center;
    }
  </style>
</head>
<body>
  <h3>justify-items: center</h3>
  <div class="container justify-center">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
    <div class="item">4</div>
    <div class="item">5</div>
    <div class="item">6</div>
  </div>

  <h3>align-items: center</h3>
  <div class="container align-center">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
    <div class="item">4</div>
    <div class="item">5</div>
    <div class="item">6</div>
  </div>

  <h3>justify-items: center + align-items: center</h3>
  <div class="container both-center">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
    <div class="item">4</div>
    <div class="item">5</div>
    <div class="item">6</div>
  </div>
</body>
</html>
```

---

## Grid Areas con `grid-template-areas`

Una de las características más poderosas de CSS Grid es la capacidad de definir áreas de la cuadrícula, lo que nos permite asignar nombres a secciones específicas del grid. Esto facilita mucho la disposición de los elementos en la página.

### Demostración

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Grid Areas</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
    }

    .container {
      display: grid;
      grid-template-columns: 1fr 2fr 1fr;
      grid-template-rows: 100px 200px 100px;
      grid-template-areas:
        "header header header"
        "sidebar main main"
        "footer footer footer";
      gap: 10px;
      background-color: #ecf0f1;
      padding: 20px;
      height: 400px;
      margin: 20px 0;
    }

    .header {
      grid-area: header;
      background-color: #34495e;
      color: white;
      padding: 20px;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .sidebar {
      grid-area: sidebar;
      background-color: #3498db;
      color: white;
      padding: 20px;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .main {
      grid-area: main;
      background-color: #2ecc71;
      color: white;
      padding: 20px;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .footer {
      grid-area: footer;
      background-color: #e74c3c;
      color: white;
      padding: 20px;
      display: flex;
      align-items: center;
      justify-content: center;
    }
  </style>
</head>
<body>
  <h3>Layout con Grid Areas</h3>
  <p>Header (3 columnas) | Sidebar (1 col) + Main (2 cols) | Footer (3 columnas)</p>
  
  <div class="container">
    <div class="header">Header</div>
    <div class="sidebar">Sidebar</div>
    <div class="main">Main Content</div>
    <div class="footer">Footer</div>
  </div>
</body>
</html>
```

---

## Conclusión

Con **CSS Grid Layout** a tu disposición, tienes el poder de crear estructuras complejas de diseño de forma fácil y rápida. Gracias a sus capacidades bidimensionales, Grid facilita la creación de layouts más precisos, flexibles y responsive. Ya sea que estés diseñando una página sencilla o un proyecto con múltiples secciones, CSS Grid te permitirá organizar los elementos de forma efectiva y adaptativa, ajustándose a diferentes tamaños de pantalla sin esfuerzo.


---

## Recursos Adicionales

- [MDN Web Docs - CSS Grid Layout](https://developer.mozilla.org/es/docs/Web/CSS/CSS_Grid_Layout)
- [CSS-Tricks - A Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [Web.dev - Grid](https://web.dev/learn/css/grid/)

---

## Ejercicio Práctico

### Enunciado

Crea una página web de un **blog de tecnología** utilizando CSS Grid. La página debe tener la siguiente estructura:

#### Requerimientos:

1. **Header (Encabezado)**
   - Logo o nombre del blog a la izquierda
   - Menú de navegación a la derecha (Home, Blog, Categorías, Contacto)
   - Altura de 80px
   - Debe estar pegado a la parte superior

2. **Sección Hero**
   - Banner grande con imagen de fondo (color sólido)
   - Título principal: "Bienvenido a TechBlog"
   - Subtítulo: "Descubre artículos sobre las últimas tendencias en tecnología"
   - Altura mínima de 300px
   - Centrado vertical y horizontal

3. **Sección Principal con Sidebar**
   - Sidebar a la izquierda (25% del ancho):
     - Categorías (enlaces)
     - Búsqueda
     - Artículos destacados
   - Área principal (75% del ancho):
     - Grid de 2 columnas con tarjetas de artículos
     - Cada tarjeta contiene:
       - Imagen (placeholder)
       - Categoría (etiqueta)
       - Título del artículo
       - Descripción breve
       - Fecha de publicación
       - Autor

4. **Footer (Pie de página)**
   - Debe ocupar el 100% del ancho
   - Información de contacto a la izquierda
   - Enlaces de redes sociales a la derecha
   - Copyright al centro

#### Requisitos CSS:

- ✅ Usar `display: grid` en al menos 4 elementos diferentes
- ✅ Utilizar `grid-template-columns` para crear columnas
- ✅ Utilizar `grid-template-rows` para crear filas
- ✅ Usar `grid-template-areas` para al menos 1 layout
- ✅ Aplicar `gap` para espaciado
- ✅ Usar `grid-column` y `grid-row` para hacer que elementos abarquen múltiples celdas
- ✅ Implementar `repeat()` o `auto-fit` para grids responsivos
- ✅ Usar `justify-items` y `align-items` para alineación
- ✅ Aplicar al menos 2 media queries para responsividad

#### Sugerencias de colores:

- Color primario: `#2c3e50` (azul oscuro)
- Color secundario: `#3498db` (azul claro)
- Color acentuado: `#e74c3c` (rojo)
- Fondo: `#ecf0f1` (gris claro)
- Texto: `#2c3e50` (gris oscuro)
- Bordes: `#bdc3c7` (gris)

#### Contenido de ejemplo:

```
Header:
  Logo: "TechBlog"
  Nav: Home | Blog | Categorías | Contacto

Hero:
  Título: "Bienvenido a TechBlog"
  Subtítulo: "Descubre artículos sobre las últimas tendencias"

Sidebar:
  - Categorías: Web, Mobile, IA, Cloud
  - Búsqueda: [Input]
  - Artículos Destacados (3)

Artículos (6 ejemplos):
  1. "Introducción a React" - 15 Dic 2025 - Por Juan
  2. "CSS Grid vs Flexbox" - 14 Dic 2025 - Por María
  3. "JavaScript ES2025" - 13 Dic 2025 - Por Carlos
  4. "WebAssembly" - 12 Dic 2025 - Por Ana
  5. "Next.js 14" - 11 Dic 2025 - Por Pedro
  6. "TypeScript Tips" - 10 Dic 2025 - Por Sofia

Footer:
  Contacto: info@techblog.com | +34 123 456 789
  Redes: GitHub | LinkedIn | Twitter | Instagram
  Copyright: "© 2025 TechBlog. Todos los derechos reservados."
```

#### Desafío Extra:

- Implementa un grid de comentarios en los artículos individuales
- Crea un sistema de etiquetas/tags usando Grid
- Agrega un carrusel de testimonios con Grid
- Implementa un dashboard con múltiples secciones usando Grid Areas
- Usa `grid-auto-flow` para controlar cómo se colocan los elementos automáticamente
- Crea diferentes layouts para diferentes dispositivos (mobile, tablet, desktop)
