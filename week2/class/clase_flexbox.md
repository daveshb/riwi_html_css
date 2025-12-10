# CSS Flexbox - Clase Completa

## Introducción

¡Hola, Coders!

Hoy vamos a explorar **CSS Flexbox**, una poderosa herramienta que nos permite diseñar layouts más flexibles. Con Flexbox, podemos controlar la alineación, distribución y orden de los elementos dentro de un contenedor, lo que facilita la creación de diseños responsivos y adaptables.

Comenzaremos con una introducción general y luego profundizaremos en cada propiedad clave que hace de Flexbox una opción imprescindible para el diseño web moderno.

---

## ¿Qué es CSS Flexbox?

**CSS Flexbox (Flexible Box Layout)** es un modelo de diseño unidimensional que organiza los elementos en un contenedor flexible. A diferencia de otros sistemas de diseño, Flexbox permite alinear los elementos tanto horizontal como verticalmente, ajustándose automáticamente al espacio disponible.

El uso de Flexbox es especialmente útil para crear layouts responsivos, ya que los elementos dentro del contenedor pueden crecer, reducirse o reorganizarse en función del tamaño del contenedor.

---

## Sintaxis Básica de Flexbox

Para usar Flexbox, aplicamos la propiedad `display: flex` a un contenedor, lo que convierte a todos sus elementos hijos en flex items. A partir de ahí, podemos controlar la alineación, el tamaño y la disposición de estos elementos.

```css
.container {
  display: flex;
}
```

Una vez activado Flexbox en un contenedor, podemos usar varias propiedades para controlar el diseño y la posición de los elementos.

### Demostración

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Flexbox Básico</title>
  <style>
    .container {
      display: flex;
      background-color: #f0f0f0;
      padding: 20px;
      margin: 20px 0;
    }

    .item {
      background-color: #3498db;
      color: white;
      padding: 20px;
      margin: 5px;
      flex: 1;
      text-align: center;
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="item">Item 1</div>
    <div class="item">Item 2</div>
    <div class="item">Item 3</div>
  </div>
</body>
</html>
```

Este es el código más simple para activar Flexbox. Sin propiedades adicionales, los elementos se distribuyen uniformemente en una fila.

---

## Eje Principal y Eje Cruzado

Para entender Flexbox correctamente, debemos conocer dos conceptos fundamentales:

### Eje Principal (Main Axis)
Define la dirección en la que se distribuyen los elementos, que puede ser horizontal (por defecto) o vertical.

### Eje Cruzado (Cross Axis)
Perpendicular al eje principal; este eje es usado para la alineación vertical u horizontal de los elementos, según sea la disposición del eje principal.

---

## Propiedad `flex-direction`

Controla la dirección en la que se distribuyen los elementos flex dentro del contenedor.

### Valores disponibles:

- **`row`**: Distribuye los elementos en una fila (de izquierda a derecha).
- **`row-reverse`**: Distribuye los elementos en una fila, pero en orden inverso (de derecha a izquierda).
- **`column`**: Distribuye los elementos en una columna (de arriba hacia abajo).
- **`column-reverse`**: Distribuye los elementos en una columna, pero en orden inverso (de abajo hacia arriba).

### Demostración

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>flex-direction</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
    }

    .container {
      display: flex;
      background-color: #ecf0f1;
      padding: 20px;
      margin: 20px 0;
      height: 200px;
    }

    .row {
      flex-direction: row;
    }

    .row-reverse {
      flex-direction: row-reverse;
    }

    .column {
      flex-direction: column;
      height: auto;
    }

    .column-reverse {
      flex-direction: column-reverse;
      height: auto;
    }

    .item {
      background-color: #e74c3c;
      color: white;
      padding: 20px;
      margin: 5px;
      flex: 1;
      text-align: center;
    }
  </style>
</head>
<body>
  <h3>flex-direction: row</h3>
  <div class="container row">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
  </div>

  <h3>flex-direction: row-reverse</h3>
  <div class="container row-reverse">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
  </div>

  <h3>flex-direction: column</h3>
  <div class="container column">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
  </div>

  <h3>flex-direction: column-reverse</h3>
  <div class="container column-reverse">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
  </div>
</body>
</html>
```

---

## Propiedad `justify-content`

Controla la alineación de los elementos a lo largo del **eje principal**.

### Valores disponibles:

- **`flex-start`**: Alinea los elementos al inicio.
- **`flex-end`**: Alinea los elementos al final.
- **`center`**: Alinea los elementos al centro.
- **`space-between`**: Deja el máximo espacio entre los elementos.
- **`space-around`**: Deja un espacio igual alrededor de cada elemento.
- **`space-evenly`**: Distribuye el espacio de manera uniforme entre todos los elementos.

### Demostración

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>justify-content</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
    }

    .container {
      display: flex;
      background-color: #ecf0f1;
      padding: 20px;
      margin: 20px 0;
      height: 100px;
    }

    .flex-start {
      justify-content: flex-start;
    }

    .flex-end {
      justify-content: flex-end;
    }

    .center {
      justify-content: center;
    }

    .space-between {
      justify-content: space-between;
    }

    .space-around {
      justify-content: space-around;
    }

    .space-evenly {
      justify-content: space-evenly;
    }

    .item {
      background-color: #3498db;
      color: white;
      padding: 20px;
      margin: 5px;
      width: 100px;
      text-align: center;
    }
  </style>
</head>
<body>
  <h3>justify-content: flex-start</h3>
  <div class="container flex-start">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
  </div>

  <h3>justify-content: flex-end</h3>
  <div class="container flex-end">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
  </div>

  <h3>justify-content: center</h3>
  <div class="container center">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
  </div>

  <h3>justify-content: space-between</h3>
  <div class="container space-between">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
  </div>

  <h3>justify-content: space-around</h3>
  <div class="container space-around">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
  </div>

  <h3>justify-content: space-evenly</h3>
  <div class="container space-evenly">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
  </div>
</body>
</html>
```

---

## Propiedad `align-items`

Controla la alineación de los elementos a lo largo del **eje cruzado**.

### Valores disponibles:

- **`stretch`**: Los elementos se estiran para llenar el contenedor (valor por defecto).
- **`flex-start`**: Alinea los elementos al inicio del eje cruzado.
- **`flex-end`**: Alinea los elementos al final.
- **`center`**: Alinea los elementos en el centro.
- **`baseline`**: Alinea los elementos según su línea base.

### Demostración

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>align-items</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
    }

    .container {
      display: flex;
      background-color: #ecf0f1;
      padding: 20px;
      margin: 20px 0;
      height: 200px;
    }

    .stretch {
      align-items: stretch;
    }

    .flex-start {
      align-items: flex-start;
    }

    .flex-end {
      align-items: flex-end;
    }

    .center {
      align-items: center;
    }

    .item {
      background-color: #2ecc71;
      color: white;
      padding: 20px;
      margin: 5px;
      flex: 1;
      text-align: center;
    }
  </style>
</head>
<body>
  <h3>align-items: stretch (por defecto)</h3>
  <div class="container stretch">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
  </div>

  <h3>align-items: flex-start</h3>
  <div class="container flex-start">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
  </div>

  <h3>align-items: flex-end</h3>
  <div class="container flex-end">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
  </div>

  <h3>align-items: center</h3>
  <div class="container center">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
  </div>
</body>
</html>
```

---

## Propiedad `flex-wrap`

Por defecto, los elementos flexibles se distribuyen en una sola línea. Sin embargo, podemos usar `flex-wrap` para permitir que los elementos pasen a varias líneas si no hay espacio suficiente en el contenedor.

### Valores disponibles:

- **`nowrap`**: Mantiene los elementos en una sola línea (valor por defecto).
- **`wrap`**: Los elementos se dividen en varias líneas si es necesario.
- **`wrap-reverse`**: Los elementos se dividen en varias líneas, pero en el orden inverso.

### Demostración

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>flex-wrap</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
    }

    .container {
      display: flex;
      background-color: #ecf0f1;
      padding: 20px;
      margin: 20px 0;
      width: 400px;
    }

    .nowrap {
      flex-wrap: nowrap;
    }

    .wrap {
      flex-wrap: wrap;
    }

    .wrap-reverse {
      flex-wrap: wrap-reverse;
    }

    .item {
      background-color: #f39c12;
      color: white;
      padding: 20px;
      margin: 5px;
      width: 150px;
      text-align: center;
      flex-shrink: 0;
    }
  </style>
</head>
<body>
  <h3>flex-wrap: nowrap (por defecto)</h3>
  <div class="container nowrap">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
    <div class="item">4</div>
  </div>

  <h3>flex-wrap: wrap</h3>
  <div class="container wrap">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
    <div class="item">4</div>
  </div>

  <h3>flex-wrap: wrap-reverse</h3>
  <div class="container wrap-reverse">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
    <div class="item">4</div>
  </div>
</body>
</html>
```

---

## Propiedad `align-content`

Cuando los elementos se distribuyen en múltiples líneas, podemos usar `align-content` para controlar cómo se distribuyen las líneas a lo largo del contenedor.

### Valores disponibles:

- **`flex-start`**: Alinea las líneas al inicio.
- **`flex-end`**: Alinea las líneas al final.
- **`center`**: Alinea las líneas al centro.
- **`space-between`**: Deja el máximo espacio entre las líneas.
- **`space-around`**: Deja un espacio igual alrededor de cada línea.
- **`space-evenly`**: Distribuye el espacio de manera uniforme.
- **`stretch`**: Las líneas se estiran para llenar el contenedor.

---

## Orden y Flexibilidad de los Elementos

Flexbox permite controlar no solo la alineación, sino también el orden y el comportamiento de los elementos dentro de un contenedor flexible.

### Propiedad `order`

Permite cambiar el orden visual de los elementos sin modificar el HTML.

### Propiedad `flex-grow`

Define cuánto espacio disponible ocupará un elemento en relación a otros flex items.

### Propiedad `flex-shrink`

Define cuánto se reducirá un elemento cuando no hay suficiente espacio en el contenedor.

### Demostración

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>order, flex-grow y flex-shrink</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
    }

    .container {
      display: flex;
      background-color: #ecf0f1;
      padding: 20px;
      margin: 20px 0;
    }

    .item {
      background-color: #9b59b6;
      color: white;
      padding: 20px;
      margin: 5px;
      text-align: center;
    }

    /* Ejemplo 1: order */
    .container1 .item1 { order: 3; }
    .container1 .item2 { order: 1; }
    .container1 .item3 { order: 2; }

    /* Ejemplo 2: flex-grow */
    .container2 .item1 { flex-grow: 1; }
    .container2 .item2 { flex-grow: 2; }
    .container2 .item3 { flex-grow: 1; }

    /* Ejemplo 3: flex-shrink */
    .container3 {
      width: 400px;
    }
    .container3 .item1 { flex-basis: 200px; flex-shrink: 1; }
    .container3 .item2 { flex-basis: 200px; flex-shrink: 2; }
    .container3 .item3 { flex-basis: 200px; flex-shrink: 1; }
  </style>
</head>
<body>
  <h3>Propiedad order - Cambia el orden visual</h3>
  <div class="container container1">
    <div class="item item1">Primero (order: 3)</div>
    <div class="item item2">Segundo (order: 1)</div>
    <div class="item item3">Tercero (order: 2)</div>
  </div>

  <h3>Propiedad flex-grow - Distribuye espacio disponible</h3>
  <div class="container container2">
    <div class="item item1">flex-grow: 1</div>
    <div class="item item2">flex-grow: 2</div>
    <div class="item item3">flex-grow: 1</div>
  </div>

  <h3>Propiedad flex-shrink - Reduce proporcional cuando falta espacio</h3>
  <div class="container container3">
    <div class="item item1">flex-shrink: 1</div>
    <div class="item item2">flex-shrink: 2 (se reduce más)</div>
    <div class="item item3">flex-shrink: 1</div>
  </div>
</body>
</html>
```

Estas propiedades permiten un control total sobre cómo se comportan los elementos dentro de un contenedor flexible.

---

## Ajustes Específicos

Además de las propiedades que afectan a todos los elementos dentro de un contenedor, Flexbox permite ajustar la alineación de elementos individuales.

### Propiedad `align-self`

Permite alinear un elemento individual de manera diferente al resto, anulando el valor de `align-items` del contenedor.

### Demostración

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>align-self</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
    }

    .container {
      display: flex;
      background-color: #ecf0f1;
      padding: 20px;
      margin: 20px 0;
      height: 200px;
      align-items: flex-start;
    }

    .item {
      background-color: #e67e22;
      color: white;
      padding: 20px;
      margin: 5px;
      flex: 1;
      text-align: center;
    }

    .item-center {
      align-self: center;
    }

    .item-end {
      align-self: flex-end;
    }

    .item-stretch {
      align-self: stretch;
    }
  </style>
</head>
<body>
  <h3>Propiedad align-self - Alineación individual</h3>
  <p>El contenedor tiene align-items: flex-start, pero algunos elementos tienen align-self diferente:</p>
  <div class="container">
    <div class="item">flex-start (por defecto)</div>
    <div class="item item-center">center</div>
    <div class="item item-end">flex-end</div>
    <div class="item item-stretch">stretch</div>
  </div>
</body>
</html>
```

Estas propiedades te permiten ajustar la alineación a nivel de elemento y línea, brindando un control total sobre el layout.

---

## Conclusión

Ahora que has aprendido cómo funciona Flexbox, tienes a tu disposición una herramienta poderosa para crear layouts flexibles y responsivos. Flexbox elimina muchas de las complicaciones de diseño que los desarrolladores enfrentaban antes y te permite construir diseños adaptables sin esfuerzo.

Con Flexbox, puedes ajustar la alineación, el orden y la distribución de los elementos con una facilidad impresionante. El poder de Flexbox no está solo en lo que hace por sí mismo, sino en cómo se adapta a diferentes pantallas y tamaños de dispositivos, haciendo que el desarrollo de sitios web modernos sea más fluido.

---

## Recursos Adicionales

- [MDN Web Docs - CSS Flexible Box Layout](https://developer.mozilla.org/es/docs/Web/CSS/CSS_Flexible_Box_Layout)
- [CSS-Tricks - A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [Web.dev - Flexbox](https://web.dev/learn/css/flexbox/)

---

## Ejercicio Práctico

### Enunciado

Crea una página web de un **portfolio personal** utilizando CSS Flexbox. La página debe tener la siguiente estructura:

#### Requerimientos:

1. **Header (Encabezado)**
   - Logo o nombre a la izquierda
   - Menú de navegación a la derecha (Home, Sobre Mí, Proyectos, Contacto)
   - Debe estar centrado verticalmente
   - Usa `justify-content: space-between`

2. **Sección Hero**
   - Imagen de perfil (círculo)
   - Título principal con nombre
   - Subtítulo con profesión
   - Botón "Ver Proyectos"
   - Los elementos deben estar centrados tanto horizontal como verticalmente
   - Altura mínima de 400px

3. **Sección de Proyectos**
   - Título "Mis Proyectos"
   - Grid de 3 columnas con tarjetas de proyectos (usa `flex-wrap: wrap`)
   - Cada tarjeta debe contener:
     - Imagen (placeholder)
     - Título del proyecto
     - Descripción breve
   - Las tarjetas deben distribuirse equitativamente
   - Deben ser responsivas (cambiar a 2 columnas en pantallas medianas)

4. **Footer (Pie de página)**
   - Copyright a la izquierda
   - Enlaces de redes sociales a la derecha
   - Usa `justify-content: space-between`
   - Debe estar pegado al fondo

#### Requisitos CSS:

- ✅ Usar `display: flex` en al menos 5 elementos diferentes
- ✅ Utilizar `flex-direction` para organizar elementos
- ✅ Aplicar `justify-content` con al menos 3 valores diferentes
- ✅ Usar `align-items` para alineación vertical
- ✅ Implementar `flex-wrap` para el grid de proyectos
- ✅ Usar `gap` para espaciado entre elementos
- ✅ Implementar `order` para reordenar al menos 2 elementos

#### Sugerencias de colores:

- Color primario: `#3498db` (azul)
- Color secundario: `#2c3e50` (gris oscuro)
- Color acentuado: `#e74c3c` (rojo)
- Fondo: `#ecf0f1` (gris claro)
- Texto: `#2c3e50` (gris oscuro)

#### Contenido de ejemplo:

```
Header:
  Logo: "Mi Portfolio"
  Nav: Home | Sobre Mí | Proyectos | Contacto

Hero:
  Título: "Hola, Soy [Tu Nombre]"
  Subtítulo: "Desarrollador Web"

Proyectos (3 ejemplos):
  1. "Tienda Online" - Descripción breve
  2. "App de Tareas" - Descripción breve
  3. "Blog Personal" - Descripción breve

Footer:
  Copyright: "© 2025 Mi Nombre. Todos los derechos reservados."
  Redes: GitHub | LinkedIn | Twitter
```

#### Desafío Extra:

- Agrega un formulario de contacto con Flexbox
- Implementa un diseño responsivo con media queries
- Usa transiciones CSS para efectos hover en las tarjetas
- Agrega una barra de habilidades (HTML, CSS, JavaScript) con progreso visual usando Flexbox
