```markdown
# Introducción a CSS (Cascading Style Sheets)

CSS es el lenguaje que define cómo se presenta el contenido HTML en una página web.  
Nos permite separar la estructura (HTML) de la presentación (CSS), haciendo que el diseño
sea flexible, mantenible y reutilizable.

En esta clase veremos:

1. Sintaxis básica de CSS  
2. Selectores y especificidad  
3. Colores, fondos, bordes y sombras  
4. Propiedades de texto y fuentes  
5. Modelo de caja (Box Model)  
6. Display y position  
7. Transformaciones, pseudoclases, pseudoelementos y animaciones  
8. Enunciado de un ejercicio final

---

## 1. Sintaxis básica de CSS

La forma general de una regla CSS es:

```css
selector {
  propiedad: valor;
  otra-propiedad: otro-valor;
}
```

Ejemplo aplicado a un título:

```css
h1 {
  color: #5b4bff;
  text-align: center;
}
```

Y un HTML mínimo para verlo:

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <title>Ejemplo CSS</title>
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <h1>Hola, Coders!</h1>
</body>
</html>
```

---

## 2. Selectores y especificidad

Los selectores indican **a qué elementos** del HTML se aplican las reglas.

### 2.1 Tipos de selectores básicos

```css
/* Selector de elemento */
p {
  color: #333;
}

/* Selector de clase */
.destacado {
  color: #5b4bff;
}

/* Selector de ID */
#titulo-principal {
  font-size: 2.5rem;
}

/* Selector descendente */
article p {
  line-height: 1.6;
}

/* Selector de atributo */
input[type="text"] {
  border: 1px solid #ccc;
}
```

HTML de demostración:

```html
<h1 id="titulo-principal">Hola, Coders!</h1>
<p>Este párrafo es normal.</p>
<p class="destacado">Este párrafo está destacado.</p>

<article>
  <p>Este párrafo está dentro de un article.</p>
</article>

<input type="text" placeholder="Escribe tu nombre" />
<input type="password" placeholder="Contraseña" />
```

### 2.2 Especificidad (¿qué regla “gana”?)

Regla general (simplificada):

1. **Estilos inline** (atributo `style`)  
2. **IDs**  
3. **Clases / pseudoclases / atributos**  
4. **Elementos / pseudoelementos**  
5. Si empatan: gana la **regla escrita más abajo** en el CSS.

Ejemplo:

```html
<p id="mensaje" class="advertencia">Cuidado con la especificidad</p>
```

```css
p {
  color: green;       /* especificidad baja */
}

.advertencia {
  color: orange;      /* más específica que p */
}

#mensaje {
  color: red;         /* más específica que .advertencia */
}
```

El texto se verá **rojo**, porque el selector `#mensaje` es el más específico.

---

## 3. Colores, fondos, bordes y sombras

### 3.1 Colores

```css
body {
  background-color: #f5f5f5;
}

h1 {
  color: rgb(91, 75, 255);     /* morado */
}

.resaltado {
  color: hsl(130, 60%, 40%);   /* verde */
}
```

### 3.2 Fondos

```css
.section-hero {
  background-image: url("fondo.webp");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}
```

### 3.3 Bordes y esquinas redondeadas

```css
.caja {
  border: 2px solid #5b4bff;
  border-radius: 20px;
  padding: 1rem 2rem;
}
```

### 3.4 Sombras

```css
.carta {
  background: white;
  padding: 1.5rem;
  border-radius: 16px;
  box-shadow: 0 10px 25px rgba(0,0,0,0.12);
}
```

HTML de demostración:

```html
<div class="carta">
  <h2 class="resaltado">Tarjeta con sombra</h2>
  <p>Esta caja combina borde redondeado, relleno y una sombra suave.</p>
</div>
```

---

## 4. Propiedades de texto y fuentes

```css
body {
  font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
  line-height: 1.5;
}

/* Títulos */
h1, h2, h3 {
  font-weight: 700;
}

/* Párrafos */
p {
  font-size: 1rem;
  color: #222;
}

/* Texto centrado y transformado */
.titulo-seccion {
  text-align: center;
  text-transform: uppercase;
  letter-spacing: 0.08em;
}

/* Enlaces */
a {
  color: #5b4bff;
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}
```

HTML de demostración:

```html
<h2 class="titulo-seccion">Propiedades de texto y fuentes</h2>
<p>
  CSS te permite controlar el tamaño, el peso, el interlineado y muchos otros
  aspectos de la tipografía.
  <a href="#">Este es un enlace de ejemplo</a>.
</p>
```

---

## 5. Modelo de caja (Box Model)

Todo elemento de bloque en CSS se representa como una **caja**:

- **content** – el contenido (texto, imagen...)
- **padding** – espacio entre el contenido y el borde
- **border** – borde alrededor del padding
- **margin** – espacio externo hasta otros elementos

```css
.box-model-demo {
  background: #ffffff;
  padding: 20px;
  border: 4px solid #5b4bff;
  margin: 20px;
}
```

HTML:

```html
<div class="box-model-demo">
  Soy una caja que demuestra el modelo de caja de CSS.
</div>
```

### 5.1 `box-sizing`

Por defecto, el `width` solo cuenta el contenido. Con `box-sizing: border-box` la anchura incluye padding y borde, lo que suele ser más cómodo.

```css
*,
*::before,
*::after {
  box-sizing: border-box;
}
```

---

## 6. Display y position

### 6.1 `display`

```css
/* Elemento de bloque */
.bloque {
  display: block;
}

/* Elemento en línea */
.en-linea {
  display: inline;
}

/* Elemento en línea pero puede tener alto y ancho */
.en-linea-bloque {
  display: inline-block;
}

/* Contenedor flexible (flexbox) */
.contenedor-flex {
  display: flex;
  gap: 1rem;
  justify-content: center;
}
```

HTML:

```html
<div class="contenedor-flex">
  <button class="en-linea-bloque">Botón 1</button>
  <button class="en-linea-bloque">Botón 2</button>
  <button class="en-linea-bloque">Botón 3</button>
</div>
```

### 6.2 `position`

```css
.caja-relativa {
  position: relative;
  padding: 2rem;
  background: #e6e8ff;
}

.caja-absoluta {
  position: absolute;
  top: 10px;
  right: 10px;
  background: #5b4bff;
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 999px;
}

.barra-fija {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  background: #111;
  color: white;
  padding: 0.75rem 1rem;
}
```

HTML de demostración:

```html
<div class="barra-fija">Barra fija arriba</div>

<div class="caja-relativa" style="margin-top:4rem;">
  Caja relativa
  <span class="caja-absoluta">Etiqueta</span>
</div>
```

---

## 7. Transformaciones, pseudoclases, pseudoelementos y animaciones

### 7.1 Pseudoclases

Las pseudoclases aplican estilos según el **estado** de un elemento.

```css
.boton {
  padding: 0.75rem 1.5rem;
  border-radius: 999px;
  border: none;
  background: #5b4bff;
  color: white;
  cursor: pointer;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.boton:hover {             /* estado al pasar el mouse */
  transform: translateY(-2px);
  box-shadow: 0 8px 18px rgba(0,0,0,0.15);
}

.boton:active {            /* estado al hacer clic */
  transform: translateY(0);
  box-shadow: none;
}

.boton:disabled {          /* estado deshabilitado */
  background: #ccc;
  cursor: not-allowed;
}
```

### 7.2 Pseudoelementos

Permiten crear contenido “virtual” antes o después de un elemento.

```css
.titulo-decorado {
  position: relative;
  display: inline-block;
  padding-bottom: 0.4rem;
}

.titulo-decorado::after {
  content: "";
  position: absolute;
  left: 0;
  bottom: 0;
  width: 60%;
  height: 4px;
  border-radius: 999px;
  background: #5b4bff;
}
```

HTML:

```html
<h2 class="titulo-decorado">Transformaciones y animaciones</h2>
```

### 7.3 Transformaciones (`transform`)

```css
.tarjeta-3d {
  width: 240px;
  padding: 1.5rem;
  margin: 2rem auto;
  text-align: center;
  border-radius: 20px;
  background: white;
  box-shadow: 0 10px 24px rgba(0,0,0,0.12);
  transition: transform 0.3s ease;
}

.tarjeta-3d:hover {
  transform: translateY(-8px) scale(1.03);
}
```

HTML:

```html
<div class="tarjeta-3d">
  <h3>Tarjeta interactiva</h3>
  <p>Pasa el mouse para ver la transformación.</p>
</div>
```

### 7.4 Animaciones (`@keyframes`)

```css
@keyframes rebotar {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-10px);
  }
}

.boton-animado {
  display: inline-block;
  margin-top: 1rem;
  animation: rebotar 1.2s infinite;
}
```

HTML:

```html
<button class="boton boton-animado">¡Saltar!</button>
```

---

## 8. Ejercicio final

> **Objetivo:** Crear una mini “portada” de curso de CSS similar a las pantallas que viste.

### Enunciado

Crea una página llamada `index.html` con un archivo de estilos `styles.css` donde:

1. Tenga un **encabezado** grande con el texto  
   `Introducción a CSS`  
   - Centrado, en mayúsculas y color morado (`#5b4bff`).  
   - Debajo, un párrafo corto de bienvenida.

2. Incluya una sección titulada **“Estructura CSS”** que muestre **al menos 6 botones** con los temas:
   - Sintaxis de CSS  
   - Selectores  
   - Colores y fondos  
   - Bordes y sombras  
   - Propiedades de texto y fuentes  
   - Modelo de caja  
   - Display y position  
   - Transformaciones, pseudoclases, pseudoelementos y animaciones  
   (elige mínimo 6, si quieres puedes usar todos).

   Requisitos de los botones:
   - Deben tener fondo morado, texto blanco y bordes redondeados.
   - Deben estar distribuidos en 2 columnas en pantallas grandes (usa `display: flex` o `grid`).
   - Al pasar el mouse sobre ellos (`:hover`) deben crecer ligeramente (`transform: scale(1.03)`) y mostrar una sombra.

3. Crea una **sección de conclusión**:
   - Un título “Conclusión”.
   - Un párrafo motivacional (puedes inventarlo).
   - Un botón verde que diga “Ver bibliografía” con una animación suave (por ejemplo, usando `@keyframes` para que “respire” o haga un pequeño bounce).

4. Aplica:
   - Al menos **un pseudoelemento** (`::before` o `::after`) para decorar un título.
   - Al menos **dos pseudoclases** (`:hover`, `:focus`, `:active`, `:first-child`, etc.).
   - `box-sizing: border-box` global.
   - Una tipografía limpia (por ejemplo `system-ui` o similar).

5. Opcional (bonus):
   - Agrega un cuadro flotante (modal) que aparezca centrado (como en la primera captura) usando `position: fixed` y que tenga un botón de cierre con `position: absolute`.

