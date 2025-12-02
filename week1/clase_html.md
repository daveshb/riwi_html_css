# Clase: Introducción a HTML

## Introducción  
En este tema exploraremos HTML, el lenguaje que constituye la columna vertebral de una página web. Conocerás sus conceptos básicos, la historia, la estructura del documento, el DOM, elementos esenciales, atributos, metadatos y comentarios.

## ¿Qué es HTML y para qué sirve?

HTML (HyperText Markup Language) es el lenguaje de marcado estándar para crear páginas web. Su objetivo principal es estructurar el contenido y definir cómo se presenta en el navegador.

### Capacidades clave:
- Estructurar el contenido mediante encabezados, párrafos, listas y tablas.
- Crear enlaces para navegar entre páginas o secciones.
- Incluir elementos multimedia como imágenes, videos y audio.
- Garantizar compatibilidad entre navegadores.
- Soporte para aplicaciones web modernas gracias a HTML5.

## Historia del HTML

HTML fue creado en 1989 por Tim Berners-Lee en el CERN para compartir documentos científicos. Ha evolucionado hasta convertirse en un estándar global.

| Versión | Año | Descripción |
|--------|-----|-------------|
| HTML 1.0 | 1993 | Primera versión básica. |
| HTML 2.0 | 1995 | Estructura más sólida. |
| HTML 3.2 | 1997 | Tablas, formularios y hojas de estilo. |
| HTML 4.01 | 1999 | Mejor organización y estandarización. |
| HTML5 | 2014 | Soporte multimedia, semántica y APIs avanzadas. |

## Estructura y sintaxis básica de HTML

La estructura básica de un documento HTML incluye:

### Etiqueta `<html>`
Define el inicio y el final del documento HTML.

### Etiqueta `<head>`
Contiene metadatos, enlaces a estilos, scripts y configuraciones del documento.

### Etiqueta `<body>`
Incluye todo el contenido visible de la página.

### Ejemplo:
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Mi página</title>
</head>
<body>
  <h1>Hola Mundo</h1>
</body>
</html>
```

## El DOM: Document Object Model

El DOM es una representación estructurada del documento HTML en forma de árbol. Cada etiqueta se convierte en un nodo que el navegador puede interpretar, manipular y modificar mediante JavaScript.

### Cómo funciona el DOM:
- Cuando el navegador carga una página, convierte el HTML en un árbol de nodos.
- Cada elemento (div, h1, p, a, etc.) se vuelve un objeto al que se puede acceder.
- Permite cambiar estilos, texto, atributos y estructura dinámica sin recargar la página.
- Es el puente entre HTML estático y páginas web interactivas.

Ejemplo del árbol DOM simplificado:
```
html
 ├── head
 └── body
      ├── h1
      └── p
```

## Elementos principales y sus atributos básicos

### Elementos comunes:
- `<p>`: párrafos de texto.
- `<h1>` a `<h6>`: encabezados.
- `<a>`: enlaces externos e internos.
- `<div>` y `<span>`: contenedores utilizados para estructura y estilos.

### Atributos comunes:
- `class`: permite aplicar estilos a múltiples elementos.
- `id`: identifica un elemento de forma única.
- `style`: agrega estilos en línea.
- `href`: define la URL destino de un enlace.

Ejemplo:
```html
<a href="https://example.com" class="boton">Ir al sitio</a>
```

## Metadatos dentro de `<head>`

Los metadatos son información que no se muestra directamente en la página, pero afectan su funcionamiento.

### Ejemplos:
```html
<meta charset="UTF-8">
<meta name="description" content="Página de ejemplo">
<meta name="keywords" content="HTML, desarrollo web">
<meta name="author" content="Tu Nombre">
```

### Configuraciones de viewport
El viewport controla cómo se adapta la página a diferentes pantallas, especialmente móviles.

Ejemplo:
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

### Estándares SEO
Son prácticas que ayudan a que los motores de búsqueda comprendan mejor el contenido.

Ejemplos de metadatos SEO:
```html
<meta name="robots" content="index, follow">
<meta property="og:title" content="Título en redes sociales">
```

## Comentarios en HTML

Los comentarios ayudan a documentar el código o desactivar partes sin eliminarlas.

### Sintaxis:
```html
<!-- Este es un comentario -->
```

### Usos:
- Explicar secciones del código
- Deshabilitar temporalmente un bloque
- Mejorar la organización del proyecto

## Conclusión

HTML es la base del desarrollo web moderno. Permite estructurar contenido, definir el comportamiento del navegador, mejorar la accesibilidad, optimizar para buscadores y trabajar de forma ordenada mediante el DOM y los metadatos.

## Ejercicio propuesto

Crea un documento HTML que incluya:

1. La estructura básica completa (`DOCTYPE`, `html`, `head`, `body`).
2. Un título y al menos tres metadatos (charset, description, keywords, viewport).
3. Un encabezado `<h1>` y dos subsecciones `<h2>`.
4. Un párrafo con un `<span>` estilizado.
5. Un `<div>` con `id` y `class`.
6. Un enlace externo con `target="_blank"`.
7. Un enlace interno a otra sección.
8. Dos comentarios explicativos.
9. Un ejemplo visual del DOM representado con etiquetas reales.
10. Adicione una imagen.


Guarda el archivo como `actividad.html`.


https://github.com/daveshb/riwi_html_css
