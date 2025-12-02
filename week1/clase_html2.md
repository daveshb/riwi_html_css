# Clase: Etiquetas HTML5 y estructura semántica de una página web

## 0. Estructura básica de un documento HTML5

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Mi primera página semántica</title>
</head>
<body>
</body>
</html>
```

## 1. Etiquetas semánticas principales

### `<header>`
```html
<header>
  <h1>Blog de Coder</h1>
  <p>Aprendiendo HTML5 paso a paso</p>
</header>
```

### `<nav>`
```html
<nav>
  <ul>
    <li><a href="#inicio">Inicio</a></li>
    <li><a href="#articulos">Artículos</a></li>
    <li><a href="#contacto">Contacto</a></li>
  </ul>
</nav>
```

### `<main>`
```html
<main>
  <h2 id="inicio">Bienvenido</h2>
  <p>Este es el contenido principal del sitio.</p>
</main>
```

### `<section>`
```html
<section id="articulos">
  <h2>Artículos recientes</h2>
  <p>Aquí irán las últimas publicaciones.</p>
</section>
```

### `<article>`
```html
<article>
  <h3>Cómo crear tu primera tabla</h3>
  <p>En este artículo aprenderás los elementos básicos de una tabla HTML.</p>
</article>
```

### `<aside>`
```html
<aside>
  <h3>Sobre el autor</h3>
  <p>Coder es un estudiante apasionado por el desarrollo web.</p>
</aside>
```

### `<footer>`
```html
<footer>
  <p>&copy; 2024 Coder - Todos los derechos reservados.</p>
</footer>
```

## 2. Etiquetas de texto comunes

### Encabezados
```html
<h1>Título principal</h1>
<h2>Subtítulo</h2>
<h3>Subsección</h3>
```

### `<p>`
```html
<p>HTML5 permite estructurar el contenido de forma clara y semántica.</p>
```

### `<strong>` y `<em>`
```html
<p>Es <strong>muy importante</strong> escribir código <em>limpio</em>.</p>
```

## 3. Enlaces
```html
<a href="https://developer.mozilla.org/es/" target="_blank">Documentación HTML</a>
```

## 4. Listas

### Desordenada
```html
<ul>
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
</ul>
```

### Ordenada
```html
<ol>
  <li>Analizar</li>
  <li>Escribir HTML</li>
  <li>Añadir CSS</li>
</ol>
```

## 5. Citas
```html
<blockquote>“La simplicidad es la clave de la elegancia.”</blockquote>
<cite>Coco Chanel</cite>
<p><q>El mejor código es el que se entiende.</q></p>
```

## 6. Imágenes y mapas de imagen
```html
<img src="logo.png" alt="Logo del sitio">
```

## 7. Tablas
```html
<table border="1">
  <caption>Horario</caption>
  <tr>
    <th>Día</th>
    <th>Materia</th>
  </tr>
  <tr>
    <td>Lunes</td>
    <td>HTML</td>
  </tr>
</table>
```

## 8. Formularios
```html
<form>
  <label for="nombre">Nombre:</label>
  <input id="nombre" type="text">

  <label>Email:</label>
  <input type="email">

  <textarea></textarea>

  <button type="submit">Enviar</button>
</form>
```

## 9. Multimedia
```html
<video controls>
  <source src="intro.mp4" type="video/mp4">
</video>
```

## 10. Separadores
```html
<hr>
```

## 11. Estilos
```html
<p style="color: purple;">Texto con estilo en línea</p>
```

## 12. Mini estructura completa
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Portafolio</title>
</head>
<body>
<header>
  <h1>Portafolio de Coder</h1>
</header>

<nav>
  <ul>
    <li><a href="#sobre-mi">Sobre mí</a></li>
    <li><a href="#proyectos">Proyectos</a></li>
  </ul>
</nav>

<main>
  <section id="sobre-mi">
    <h2>Sobre mí</h2>
    <p>Soy desarrollador web en formación.</p>
  </section>

  <aside>
    <blockquote>“Codificar es crear.”</blockquote>
  </aside>
</main>

<footer>
  <p>&copy; 2024 Coder</p>
</footer>

</body>
</html>
```

## 13. Ejercicio final
Crea un archivo HTML que incluya:  
- Estructura semántica completa  
- Encabezados, párrafos, listas  
- Enlaces  
- Imágenes y mapa de imagen  
- Tabla  
- Formulario  
- Multimedia  
- Estilos internos y en línea  
