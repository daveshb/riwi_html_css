# Clase: Introducción a JavaScript y Manipulación del DOM

## ¿Qué es JavaScript?

JavaScript es un lenguaje de programación que permite crear contenido dinámico e interactivo en páginas web. Es uno de los tres pilares del desarrollo web junto con HTML y CSS.

- **HTML**: Estructura del contenido
- **CSS**: Presentación y estilos
- **JavaScript**: Comportamiento e interactividad

## ¿Qué es el DOM?

DOM (Document Object Model) es una representación en forma de árbol de todos los elementos HTML de una página web. JavaScript puede acceder y manipular el DOM para:

- Cambiar contenido de elementos
- Modificar estilos CSS
- Agregar o eliminar elementos
- Responder a eventos del usuario (clics, teclas, etc.)

## Cómo vincular JavaScript a HTML

Existen tres formas principales de incluir JavaScript en un documento HTML:

### 1. JavaScript en línea (inline)

```html
<button onclick="alert('¡Hola!')">Hacer clic</button>
```

**⚠️ No recomendado**: Mezcla HTML con JavaScript.

### 2. JavaScript interno (en el mismo archivo HTML)

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Mi Página</title>
</head>
<body>
    <h1 id="titulo">Hola Mundo</h1>
    
    <script>
        // JavaScript aquí
        console.log("Hola desde JavaScript");
    </script>
</body>
</html>
```

**⚠️ Ubicación importante**: Coloca el `<script>` al final del `<body>` para asegurar que el DOM esté cargado.

### 3. JavaScript externo (archivo separado) ✅ RECOMENDADO

**archivo.html:**
```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Mi Página</title>
</head>
<body>
    <h1 id="titulo">Hola Mundo</h1>
    
    <!-- Vincular archivo JS externo -->
    <script src="./script.js"></script>
</body>
</html>
```

**script.js:**
```javascript
console.log("Hola desde archivo externo");
```

**Ventajas:**
- Código más organizado y mantenible
- Reutilización del código
- Separación de responsabilidades
- Mejor rendimiento (caché del navegador)

## Accediendo al DOM

### Métodos principales para seleccionar elementos:

```javascript
// 1. Por ID (devuelve un elemento)
const elemento = document.getElementById('miId');

// 2. Por clase (devuelve una colección)
const elementos = document.getElementsByClassName('miClase');

// 3. Por etiqueta (devuelve una colección)
const parrafos = document.getElementsByTagName('p');

// 4. Query Selector (más moderno y flexible)
const elemento = document.querySelector('.miClase'); // Primer elemento
const elementos = document.querySelectorAll('.miClase'); // Todos los elementos
```

### Ejemplos de uso:

```javascript
// HTML: <h1 id="titulo">Título Original</h1>

// Seleccionar el elemento
const titulo = document.getElementById('titulo');

// Leer contenido
console.log(titulo.textContent); // "Título Original"

// Cambiar contenido
titulo.textContent = "Nuevo Título";

// Cambiar estilos
titulo.style.color = "blue";
titulo.style.fontSize = "32px";

// Agregar/quitar clases
titulo.classList.add('destacado');
titulo.classList.remove('oculto');
titulo.classList.toggle('activo');
```

## Manejando Eventos

Los eventos son acciones que ocurren en la página web (clic, hover, tecla presionada, etc.).

### Sintaxis básica:

```javascript
elemento.addEventListener('evento', function() {
    // Código a ejecutar
});
```

### Eventos comunes:

- `click`: Cuando se hace clic
- `dblclick`: Doble clic
- `mouseenter`: Cuando el mouse entra al elemento
- `mouseleave`: Cuando el mouse sale del elemento
- `keydown`: Cuando se presiona una tecla
- `submit`: Cuando se envía un formulario
- `input`: Cuando cambia el valor de un input

### Ejemplo con click:

```javascript
// HTML: <button id="miBoton">Hacer clic</button>

const boton = document.getElementById('miBoton');

boton.addEventListener('click', function() {
    alert('¡Botón clickeado!');
});
```

## Consejos y Buenas Prácticas

1. **Espera a que el DOM esté listo**:
```javascript
document.addEventListener('DOMContentLoaded', function() {
    // Tu código aquí
});
```

2. **Usa nombres descriptivos**:
```javascript
// Mal
const x = document.getElementById('btn');

// Bien
const submitButton = document.getElementById('submitButton');
```

3. **Separa el JavaScript del HTML**:
   - Evita `onclick="..."` en HTML
   - Usa `addEventListener` en JavaScript

4. **Usa `const` y `let` en lugar de `var`**:
```javascript
const titulo = document.getElementById('titulo'); // No cambiará
let contador = 0; // Puede cambiar
```

## Recursos Adicionales

- [MDN Web Docs - JavaScript](https://developer.mozilla.org/es/docs/Web/JavaScript)
- [MDN Web Docs - DOM](https://developer.mozilla.org/es/docs/Web/API/Document_Object_Model)
- [JavaScript.info](https://javascript.info/)

---

## Próximos pasos

Practica con el ejercicio proporcionado para reforzar estos conceptos. La mejor forma de aprender JavaScript es escribiendo código y experimentando.
