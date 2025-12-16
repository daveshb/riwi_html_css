# Animaciones y Keyframes en CSS

## Introducción

Las **animaciones en CSS** son una forma poderosa de añadir movimiento y vida a tus sitios web. Con las propiedades de CSS para animaciones y las `keyframes`, puedes crear efectos visuales complejos sin necesidad de JavaScript. Desde transiciones suaves hasta animaciones complejas con múltiples estados, CSS ofrece un control total sobre cómo se mueven y transforman los elementos en la página.

En esta clase aprenderás a crear animaciones profesionales que mejorarán significativamente la experiencia del usuario.

---

## ¿Qué son las Transiciones en CSS?

Las **transiciones** permiten cambiar los valores de las propiedades CSS de forma suave en un periodo de tiempo determinado. Son perfectas para efectos simples como cambios de color, tamaño o posición al pasar el ratón.

### Sintaxis

```css
.elemento {
  transition: propiedad duración timing-function retraso;
}
```

### Propiedades de Transición

- **`transition-property`**: Qué propiedad se anima (ej: color, width, opacity)
- **`transition-duration`**: Cuánto tiempo dura la transición (ej: 0.3s, 500ms)
- **`transition-timing-function`**: Cómo progresa la animación (ease, linear, ease-in, ease-out, etc.)
- **`transition-delay`**: Tiempo antes de que comience la transición (ej: 0.1s)

### Demostración de Transiciones

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Transiciones CSS</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: Arial, sans-serif;
      padding: 2rem;
      background-color: #ecf0f1;
    }

    .demo-section {
      margin-bottom: 3rem;
    }

    h3 {
      margin-bottom: 1rem;
      color: #2c3e50;
    }

    /* Transición básica de color */
    .box-color {
      width: 150px;
      height: 150px;
      background-color: #3498db;
      margin-bottom: 1rem;
      transition: background-color 0.3s ease;
    }

    .box-color:hover {
      background-color: #e74c3c;
    }

    /* Transición de tamaño */
    .box-size {
      width: 100px;
      height: 100px;
      background-color: #2ecc71;
      transition: width 0.4s ease, height 0.4s ease;
    }

    .box-size:hover {
      width: 200px;
      height: 200px;
    }

    /* Transición de múltiples propiedades */
    .box-multiple {
      width: 120px;
      height: 120px;
      background-color: #f39c12;
      border-radius: 0px;
      transform: rotate(0deg);
      transition: all 0.5s ease; /* Anima todas las propiedades */
    }

    .box-multiple:hover {
      background-color: #9b59b6;
      border-radius: 50%;
      transform: rotate(45deg);
    }

    /* Diferentes timing functions */
    .timing-box {
      width: 80px;
      height: 80px;
      margin: 10px;
      display: inline-block;
      background-color: #1abc9c;
      position: relative;
      left: 0;
    }

    .timing-box:hover {
      left: 200px;
    }

    .timing-linear {
      transition: left 2s linear;
    }

    .timing-ease {
      transition: left 2s ease;
    }

    .timing-ease-in {
      transition: left 2s ease-in;
    }

    .timing-ease-out {
      transition: left 2s ease-out;
    }

    .timing-ease-in-out {
      transition: left 2s ease-in-out;
    }

    /* Transición con retraso */
    .delay-box {
      width: 100px;
      height: 100px;
      background-color: #e67e22;
      margin: 10px;
      display: inline-block;
      opacity: 1;
    }

    .delay-box:nth-child(1) { transition: opacity 0.5s ease 0s; }
    .delay-box:nth-child(2) { transition: opacity 0.5s ease 0.2s; }
    .delay-box:nth-child(3) { transition: opacity 0.5s ease 0.4s; }
    .delay-box:nth-child(4) { transition: opacity 0.5s ease 0.6s; }

    .container-delay:hover .delay-box {
      opacity: 0.3;
    }
  </style>
</head>
<body>
  <h2>Transiciones CSS</h2>

  <div class="demo-section">
    <h3>1. Transición de Color</h3>
    <div class="box-color"></div>
    <p>Pasa el ratón para ver la transición de color</p>
  </div>

  <div class="demo-section">
    <h3>2. Transición de Tamaño</h3>
    <div class="box-size"></div>
    <p>Pasa el ratón para ver el cambio de tamaño</p>
  </div>

  <div class="demo-section">
    <h3>3. Transición de Múltiples Propiedades</h3>
    <div class="box-multiple"></div>
    <p>Pasa el ratón para ver color, forma y rotación</p>
  </div>

  <div class="demo-section">
    <h3>4. Diferentes Timing Functions</h3>
    <p>Pasa el ratón para ver la diferencia</p>
    <div class="timing-box timing-linear">linear</div>
    <div class="timing-box timing-ease">ease</div>
    <div class="timing-box timing-ease-in">ease-in</div>
    <div class="timing-box timing-ease-out">ease-out</div>
    <div class="timing-box timing-ease-in-out">ease-in-out</div>
  </div>

  <div class="demo-section">
    <h3>5. Transiciones con Retraso</h3>
    <p>Pasa el ratón al contenedor para ver efecto en cascada</p>
    <div class="container-delay">
      <div class="delay-box"></div>
      <div class="delay-box"></div>
      <div class="delay-box"></div>
      <div class="delay-box"></div>
    </div>
  </div>
</body>
</html>
```

---

## ¿Qué son las Animaciones CSS?

Las **animaciones CSS** permiten animar múltiples propiedades simultáneamente usando `@keyframes`. A diferencia de las transiciones, que requieren un evento trigger (como hover), las animaciones pueden ejecutarse automáticamente y repetirse.

### Sintaxis Básica

```css
@keyframes nombre-animacion {
  0% {
    /* Estilos al inicio */
  }
  50% {
    /* Estilos a mitad */
  }
  100% {
    /* Estilos al final */
  }
}

.elemento {
  animation: nombre-animacion duracion timing-function repeticiones;
}
```

### Propiedades de Animación

- **`animation-name`**: Nombre de la animación definida en @keyframes
- **`animation-duration`**: Duración total de la animación
- **`animation-timing-function`**: Curva de tiempo
- **`animation-delay`**: Retraso antes de iniciar
- **`animation-iteration-count`**: Cuántas veces se repite (number o infinite)
- **`animation-direction`**: normal, reverse, alternate, alternate-reverse
- **`animation-fill-mode`**: forwards, backwards, both, none
- **`animation-play-state`**: running, paused

### Demostración de Animaciones

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Animaciones CSS</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: Arial, sans-serif;
      padding: 2rem;
      background-color: #ecf0f1;
    }

    .demo-section {
      margin-bottom: 3rem;
    }

    h3 {
      margin-bottom: 1rem;
      color: #2c3e50;
    }

    /* Animación básica */
    @keyframes slide {
      0% {
        transform: translateX(0);
      }
      100% {
        transform: translateX(300px);
      }
    }

    .box-slide {
      width: 100px;
      height: 100px;
      background-color: #3498db;
      animation: slide 2s ease infinite;
    }

    /* Animación con múltiples keyframes */
    @keyframes bounce {
      0%, 100% {
        transform: translateY(0);
      }
      50% {
        transform: translateY(-50px);
      }
    }

    .box-bounce {
      width: 80px;
      height: 80px;
      background-color: #2ecc71;
      animation: bounce 1s ease infinite;
    }

    /* Animación de rotación */
    @keyframes spin {
      0% {
        transform: rotate(0deg);
      }
      100% {
        transform: rotate(360deg);
      }
    }

    .box-spin {
      width: 100px;
      height: 100px;
      background-color: #e74c3c;
      border-radius: 50%;
      animation: spin 2s linear infinite;
    }

    /* Animación de opacity */
    @keyframes fadeInOut {
      0% {
        opacity: 0;
      }
      50% {
        opacity: 1;
      }
      100% {
        opacity: 0;
      }
    }

    .box-fade {
      width: 150px;
      height: 150px;
      background-color: #f39c12;
      animation: fadeInOut 3s ease infinite;
    }

    /* Animación compleja */
    @keyframes complexAnimation {
      0% {
        transform: translate(0, 0) scale(1) rotate(0deg);
        background-color: #9b59b6;
      }
      25% {
        transform: translate(100px, -50px) scale(1.2) rotate(90deg);
        background-color: #3498db;
      }
      50% {
        transform: translate(150px, 0) scale(1) rotate(180deg);
        background-color: #2ecc71;
      }
      75% {
        transform: translate(100px, 50px) scale(1.2) rotate(270deg);
        background-color: #e74c3c;
      }
      100% {
        transform: translate(0, 0) scale(1) rotate(360deg);
        background-color: #9b59b6;
      }
    }

    .box-complex {
      width: 80px;
      height: 80px;
      animation: complexAnimation 4s ease infinite;
    }

    /* Animación con retraso */
    .loading {
      display: flex;
      gap: 10px;
      justify-content: center;
      align-items: center;
    }

    @keyframes loadingBounce {
      0%, 100% {
        transform: scale(0.8);
        opacity: 0.5;
      }
      50% {
        transform: scale(1.2);
        opacity: 1;
      }
    }

    .loading-dot {
      width: 15px;
      height: 15px;
      border-radius: 50%;
      background-color: #1abc9c;
      animation: loadingBounce 0.8s ease infinite;
    }

    .loading-dot:nth-child(1) { animation-delay: 0s; }
    .loading-dot:nth-child(2) { animation-delay: 0.2s; }
    .loading-dot:nth-child(3) { animation-delay: 0.4s; }

    /* Animación con pausa */
    .box-paused {
      width: 100px;
      height: 100px;
      background-color: #e67e22;
      animation: slide 3s ease infinite;
      margin-bottom: 1rem;
    }

    .box-paused:hover {
      animation-play-state: paused;
    }

    p.small {
      font-size: 0.9rem;
      color: #7f8c8d;
    }
  </style>
</head>
<body>
  <h2>Animaciones CSS con Keyframes</h2>

  <div class="demo-section">
    <h3>1. Animación Básica (Deslizamiento)</h3>
    <div class="box-slide"></div>
    <p class="small">Se desliza hacia la derecha infinitamente</p>
  </div>

  <div class="demo-section">
    <h3>2. Animación de Rebote</h3>
    <div class="box-bounce"></div>
    <p class="small">Efecto de rebote hacia arriba</p>
  </div>

  <div class="demo-section">
    <h3>3. Animación de Rotación</h3>
    <div class="box-spin"></div>
    <p class="small">Gira continuamente</p>
  </div>

  <div class="demo-section">
    <h3>4. Animación de Opacidad (Fade In/Out)</h3>
    <div class="box-fade"></div>
    <p class="small">Aparece y desaparece gradualmente</p>
  </div>

  <div class="demo-section">
    <h3>5. Animación Compleja</h3>
    <div class="box-complex"></div>
    <p class="small">Combina múltiples transformaciones</p>
  </div>

  <div class="demo-section">
    <h3>6. Animación con Retraso (Loading)</h3>
    <div class="loading">
      <div class="loading-dot"></div>
      <div class="loading-dot"></div>
      <div class="loading-dot"></div>
    </div>
    <p class="small">Efecto de carga con puntos en cascada</p>
  </div>

  <div class="demo-section">
    <h3>7. Animación con Pausa (Hover para pausar)</h3>
    <div class="box-paused"></div>
    <p class="small">Pasa el ratón para pausar la animación</p>
  </div>
</body>
</html>
```

---

## Keyframes: Puntos Clave

Los **keyframes** definen los estados de una animación en puntos específicos del tiempo. Pueden definirse usando porcentajes (0%, 50%, 100%) o palabras clave (from, to).

### Sintaxis Detallada

```css
@keyframes nombreAnimacion {
  from {
    /* Equivalente a 0% */
    property: value;
  }
  50% {
    /* Punto intermedio */
    property: value;
  }
  to {
    /* Equivalente a 100% */
    property: value;
  }
}
```

### Demostración Detallada de Keyframes

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Keyframes Detallado</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 2rem;
      background-color: #f5f5f5;
    }

    .demo-section {
      margin-bottom: 2rem;
    }

    /* Keyframes simples (from - to) */
    @keyframes simpleFade {
      from {
        opacity: 1;
        color: black;
      }
      to {
        opacity: 0;
        color: transparent;
      }
    }

    /* Keyframes con múltiples puntos */
    @keyframes colorChange {
      0% {
        background-color: #ff0000;
      }
      25% {
        background-color: #00ff00;
      }
      50% {
        background-color: #0000ff;
      }
      75% {
        background-color: #ffff00;
      }
      100% {
        background-color: #ff0000;
      }
    }

    /* Keyframes con múltiples propiedades */
    @keyframes slideAndFade {
      0% {
        transform: translateX(-100px);
        opacity: 0;
      }
      50% {
        opacity: 1;
      }
      100% {
        transform: translateX(100px);
        opacity: 0;
      }
    }

    .box {
      width: 100px;
      height: 100px;
      margin: 20px 0;
    }

    .box-fade {
      background-color: #3498db;
      animation: simpleFade 2s ease infinite;
    }

    .box-color {
      animation: colorChange 4s ease infinite;
    }

    .box-complex {
      background-color: #9b59b6;
      animation: slideAndFade 3s ease infinite;
    }
  </style>
</head>
<body>
  <h2>Keyframes Detallado</h2>

  <div class="demo-section">
    <h3>Keyframes Simple (from - to)</h3>
    <div class="box box-fade"></div>
  </div>

  <div class="demo-section">
    <h3>Keyframes con Múltiples Puntos (Cambio de Color)</h3>
    <div class="box box-color"></div>
  </div>

  <div class="demo-section">
    <h3>Keyframes Complejos (Deslizamiento + Opacidad)</h3>
    <div class="box box-complex"></div>
  </div>
</body>
</html>
```

---

## Transformaciones y Propiedades Animables

La propiedad **`transform`** es especialmente útil para animaciones porque es muy eficiente en términos de rendimiento. Las transformaciones incluyen:

- `translate()`: Mover elementos
- `rotate()`: Girar elementos
- `scale()`: Cambiar tamaño
- `skew()`: Sesgar elementos

### Demostración de Transformaciones

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Transformaciones en Animaciones</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 2rem;
      background-color: #ecf0f1;
    }

    .container {
      display: flex;
      gap: 2rem;
      flex-wrap: wrap;
      margin-bottom: 2rem;
    }

    .box {
      width: 100px;
      height: 100px;
      background-color: #3498db;
      margin: 20px 0;
      color: white;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    /* Translate */
    @keyframes moveRight {
      0%, 100% {
        transform: translateX(0);
      }
      50% {
        transform: translateX(200px);
      }
    }

    .box-translate {
      animation: moveRight 2s ease infinite;
    }

    /* Rotate */
    @keyframes fullRotate {
      0% {
        transform: rotate(0deg);
      }
      100% {
        transform: rotate(360deg);
      }
    }

    .box-rotate {
      background-color: #e74c3c;
      animation: fullRotate 2s linear infinite;
    }

    /* Scale */
    @keyframes grow {
      0%, 100% {
        transform: scale(1);
      }
      50% {
        transform: scale(1.5);
      }
    }

    .box-scale {
      background-color: #2ecc71;
      animation: grow 2s ease infinite;
    }

    /* Skew */
    @keyframes skewIt {
      0%, 100% {
        transform: skewX(0deg);
      }
      50% {
        transform: skewX(30deg);
      }
    }

    .box-skew {
      background-color: #f39c12;
      animation: skewIt 2s ease infinite;
    }

    /* Combinado */
    @keyframes combined {
      0% {
        transform: translate(0, 0) scale(1) rotate(0deg);
      }
      50% {
        transform: translate(150px, -50px) scale(1.2) rotate(180deg);
      }
      100% {
        transform: translate(0, 0) scale(1) rotate(360deg);
      }
    }

    .box-combined {
      background-color: #9b59b6;
      animation: combined 3s ease infinite;
    }

    /* Asegurar que todas las animaciones están constantemente activas */
    .box-translate,
    .box-rotate,
    .box-scale,
    .box-skew,
    .box-combined {
      animation-play-state: running;
    }
  </style>
</head>
<body>
  <h2>Transformaciones en Animaciones</h2>

  <h3>Translate (Mover)</h3>
  <div class="box box-translate">Translate</div>

  <h3>Rotate (Girar)</h3>
  <div class="box box-rotate">Rotate</div>

  <h3>Scale (Escalar)</h3>
  <div class="box box-scale">Scale</div>

  <h3>Skew (Sesgar)</h3>
  <div class="box box-skew">Skew</div>

  <h3>Combinado</h3>
  <div class="box box-combined">Combined</div>
</body>
</html>
```

---

## Propiedades CSS Animables

No todas las propiedades CSS se pueden animar. Aquí están las más comunes y su eficiencia:

### ✅ Propiedades Altamente Eficientes (GPU Accelerated)
- `transform`
- `opacity`

### ✅ Propiedades Animables Seguras
- `background-color`
- `color`
- `width`, `height`
- `padding`, `margin`
- `border-width`, `border-color`
- `box-shadow`
- `text-shadow`
- `filter`

### ❌ Evita Animar (Bajo Rendimiento)
- `top`, `left`, `bottom`, `right` (posicionamiento absoluto)
- `background-position` (sin GPU acceleration)

---

## Animation Fill Mode

La propiedad `animation-fill-mode` controla cómo se ven los estilos antes de que comience la animación y después de que termine.

### Demostración

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Animation Fill Mode</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 2rem;
      background-color: #ecf0f1;
    }

    @keyframes moveBox {
      0% {
        transform: translateX(0);
        background-color: #3498db;
      }
      100% {
        transform: translateX(200px);
        background-color: #e74c3c;
      }
    }

    .box {
      width: 100px;
      height: 100px;
      background-color: #3498db;
      margin: 20px 0;
      animation: moveBox 2s ease 1; /* No se repite */
    }

    /* none: Sin estilos finales */
    .fill-none {
      animation-fill-mode: none;
    }

    /* forwards: Mantiene los estilos finales */
    .fill-forwards {
      animation-fill-mode: forwards;
    }

    /* backwards: Usa estilos iniciales antes de comenzar */
    .fill-backwards {
      animation-fill-mode: backwards;
      animation-delay: 1s;
    }

    /* both: forwards + backwards */
    .fill-both {
      animation-fill-mode: both;
      animation-delay: 1s;
    }

    p {
      font-size: 0.9rem;
      color: #7f8c8d;
      margin-bottom: 1rem;
    }
  </style>
</head>
<body>
  <h2>Animation Fill Mode</h2>

  <p><strong>fill-mode: none</strong> - Vuelve al estilo original después</p>
  <div class="box fill-none"></div>

  <p><strong>fill-mode: forwards</strong> - Mantiene el estilo final</p>
  <div class="box fill-forwards"></div>

  <p><strong>fill-mode: backwards</strong> - Usa estilo inicial antes de comenzar</p>
  <div class="box fill-backwards"></div>

  <p><strong>fill-mode: both</strong> - Combina forwards y backwards</p>
  <div class="box fill-both"></div>
</body>
</html>
```

---

## Timing Functions Personalizadas

Puedes crear tus propias curvas de tiempo con `cubic-bezier()` para controlar precisamente cómo progresa una animación.

### Sintaxis

```css
animation-timing-function: cubic-bezier(x1, y1, x2, y2);
```

### Funciones Comunes

```css
/* Predefinidas */
ease                    /* cubic-bezier(0.25, 0.1, 0.25, 1) */
linear                  /* cubic-bezier(0, 0, 1, 1) */
ease-in                 /* cubic-bezier(0.42, 0, 1, 1) */
ease-out                /* cubic-bezier(0, 0, 0.58, 1) */
ease-in-out             /* cubic-bezier(0.42, 0, 0.58, 1) */

/* Personalizadas */
cubic-bezier(0.17, 0.67, 0.83, 0.67)  /* ease-out-bounce */
cubic-bezier(0.25, 0.46, 0.45, 0.94)  /* bounce */
```

### Demostración

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Cubic Bezier</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 2rem;
      background-color: #ecf0f1;
    }

    @keyframes move {
      0% {
        transform: translateX(0);
      }
      100% {
        transform: translateX(300px);
      }
    }

    .box {
      width: 50px;
      height: 50px;
      background-color: #3498db;
      margin: 20px 0;
      animation: move 3s 1; /* Sin repetición para ver el efecto */
    }

    .linear {
      animation-timing-function: linear;
    }

    .ease {
      animation-timing-function: ease;
    }

    .ease-in {
      animation-timing-function: ease-in;
    }

    .ease-out {
      animation-timing-function: ease-out;
    }

    .custom-bounce {
      animation-timing-function: cubic-bezier(0.17, 0.67, 0.83, 0.67);
    }

    label {
      display: block;
      margin-bottom: 0.5rem;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <h2>Cubic Bezier - Timing Functions</h2>

  <label>Linear</label>
  <div class="box linear"></div>

  <label>Ease (por defecto)</label>
  <div class="box ease"></div>

  <label>Ease In</label>
  <div class="box ease-in"></div>

  <label>Ease Out</label>
  <div class="box ease-out"></div>

  <label>Custom Bounce</label>
  <div class="box custom-bounce"></div>

  <p><em>Herramienta: https://cubic-bezier.com/</em></p>
</body>
</html>
```

---

## Animaciones Prácticas

### 1. Botón Hover con Animación

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Botón Animado</title>
  <style>
    .button {
      padding: 15px 30px;
      font-size: 1rem;
      border: none;
      border-radius: 5px;
      background-color: #3498db;
      color: white;
      cursor: pointer;
      position: relative;
      overflow: hidden;
      transition: all 0.3s ease;
    }

    .button:hover {
      background-color: #2980b9;
      transform: translateY(-2px);
      box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
    }

    .button:active {
      transform: translateY(0);
    }

    .button::before {
      content: '';
      position: absolute;
      top: 50%;
      left: 50%;
      width: 0;
      height: 0;
      border-radius: 50%;
      background-color: rgba(255, 255, 255, 0.5);
      transform: translate(-50%, -50%);
      transition: width 0.6s, height 0.6s;
    }

    .button:active::before {
      width: 300px;
      height: 300px;
    }
  </style>
</head>
<body>
  <button class="button">Click me</button>
</body>
</html>
```

### 2. Loader Animado

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Loader Animado</title>
  <style>
    .loader {
      width: 50px;
      height: 50px;
      border: 5px solid #f3f3f3;
      border-top: 5px solid #3498db;
      border-radius: 50%;
      animation: spin 1s linear infinite;
    }

    @keyframes spin {
      0% { transform: rotate(0deg); }
      100% { transform: rotate(360deg); }
    }

    .loader-dots {
      display: flex;
      gap: 5px;
      margin-top: 30px;
    }

    @keyframes bounce {
      0%, 100% {
        transform: translateY(0);
      }
      50% {
        transform: translateY(-20px);
      }
    }

    .dot {
      width: 15px;
      height: 15px;
      background-color: #3498db;
      border-radius: 50%;
      animation: bounce 0.8s ease infinite;
    }

    .dot:nth-child(1) { animation-delay: 0s; }
    .dot:nth-child(2) { animation-delay: 0.1s; }
    .dot:nth-child(3) { animation-delay: 0.2s; }
  </style>
</head>
<body>
  <h3>Spinner Loader</h3>
  <div class="loader"></div>

  <h3>Dots Loader</h3>
  <div class="loader-dots">
    <div class="dot"></div>
    <div class="dot"></div>
    <div class="dot"></div>
  </div>
</body>
</html>
```

### 3. Card Hover con Efecto

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Card Animada</title>
  <style>
    .card {
      width: 300px;
      background-color: white;
      border-radius: 10px;
      overflow: hidden;
      box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
      transition: all 0.3s ease;
      cursor: pointer;
    }

    .card:hover {
      transform: translateY(-10px);
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
    }

    .card-image {
      width: 100%;
      height: 200px;
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      position: relative;
      overflow: hidden;
    }

    @keyframes shimmer {
      0% {
        transform: translateX(-100%);
      }
      100% {
        transform: translateX(100%);
      }
    }

    .card-image::after {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.3), transparent);
      animation: shimmer 2s infinite;
    }

    .card-content {
      padding: 20px;
    }

    .card-title {
      font-size: 1.5rem;
      margin-bottom: 10px;
      color: #2c3e50;
    }

    .card-description {
      color: #7f8c8d;
      margin-bottom: 15px;
    }

    .card-button {
      padding: 10px 20px;
      background-color: #3498db;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      transition: all 0.3s ease;
    }

    .card-button:hover {
      background-color: #2980b9;
      transform: scale(1.05);
    }
  </style>
</head>
<body>
  <div class="card">
    <div class="card-image"></div>
    <div class="card-content">
      <h3 class="card-title">Proyecto Destacado</h3>
      <p class="card-description">Esta es una tarjeta con efectos de animación.</p>
      <button class="card-button">Ver Más</button>
    </div>
  </div>
</body>
</html>
```

---

## Conclusión

Las **animaciones y transiciones en CSS** son herramientas poderosas para crear experiencias visuales atractivas y profesionales. Con las `keyframes`, puedes animar casi cualquier propiedad CSS y crear efectos complejos sin necesidad de JavaScript.

**Puntos clave a recordar:**

- Usa **transiciones** para cambios simples y rápidos
- Usa **animaciones** para efectos más complejos y repetidos
- Prioriza la propiedad `transform` para mejor rendimiento
- Usa `animation-timing-function` para controlar la velocidad
- Prueba diferentes valores para encontrar el efecto perfecto

---

## Recursos Adicionales

- [MDN - CSS Animations](https://developer.mozilla.org/es/docs/Web/CSS/CSS_Animations)
- [MDN - CSS Transitions](https://developer.mozilla.org/es/docs/Web/CSS/CSS_Transitions)
- [cubic-bezier.com](https://cubic-bezier.com/)
- [Animista - CSS Animations Gallery](https://animista.net/)

---

## Ejercicio Práctico

### Enunciado: Página de Portafolio Animada

Crea una **página de portafolio profesional** con múltiples animaciones y transiciones que proporcionen una experiencia visual atractiva.

#### Requerimientos:

1. **Header Animado**
   - Logo que rota al pasar el ratón
   - Menú de navegación con subrayado animado
   - Efecto hover en cada enlace
   - Transición suave en cambio de color

2. **Sección Hero Animada**
   - Texto que aparece con efecto fade-in al cargar
   - Imagen de perfil que rota lentamente (animación continua)
   - Botones con efecto glow o scale al hover
   - Palabras clave que cambian de color (carousel)

3. **Sección de Servicios/Habilidades**
   - Tarjetas que se deslizan desde los lados
   - Efecto hover que levanta la tarjeta
   - Barra de progreso animada (HTML skill: 90%, CSS: 85%, etc.)
   - Ícono que gira al pasar el ratón

4. **Galería de Proyectos**
   - Imágenes con efecto zoom al hover
   - Overlay con información que aparece suavemente
   - Transición entre proyectos
   - Efecto parallax opcional

5. **Sección de Testimonios**
   - Carousel automático de testimonios
   - Transición suave entre items
   - Estrellas que aparecen con animación
   - Avatar que escala al cambiar testimonios

6. **Formulario de Contacto**
   - Campos con animación de enfoque (focus)
   - Botón submit con efecto de carga
   - Validación con animaciones
   - Mensaje de éxito con fade-in

7. **Footer Animado**
   - Enlaces que se subrayan con animación
   - Ícono flotante de "volver arriba" que sube suavemente
   - Transición de color al hover

#### Requisitos Técnicos:

##### ✅ Transiciones
- Usar `transition` en al menos 10 elementos
- Diferentes duraciones (0.2s, 0.3s, 0.5s, 1s)
- Diferentes timing functions (ease, ease-in, ease-out, cubic-bezier)

##### ✅ Animaciones
- Crear al menos 8 keyframes diferentes
- Usar `animation-iteration-count` (finite e infinite)
- Implementar `animation-delay` en cascadas
- Usar `animation-fill-mode` correctamente
- Implementar `animation-direction` (reverse, alternate)

##### ✅ Transformaciones
- Usar `translate()` en animaciones
- Usar `rotate()` en animaciones
- Usar `scale()` en interacciones
- Usar `skew()` en al menos un elemento
- Combinar múltiples transformaciones

##### ✅ Efectos Especiales
- Efecto de carga/spinner
- Efecto pulse o glow
- Efecto fade in/out
- Efecto bounce
- Efecto shimmer o gradient animado

#### Animaciones Específicas Requeridas:

```css
/* 1. Fade In */
@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

/* 2. Slide In desde la izquierda */
@keyframes slideInLeft {
  from {
    transform: translateX(-100px);
    opacity: 0;
  }
  to {
    transform: translateX(0);
    opacity: 1;
  }
}

/* 3. Slide In desde la derecha */
@keyframes slideInRight {
  from {
    transform: translateX(100px);
    opacity: 0;
  }
  to {
    transform: translateX(0);
    opacity: 1;
  }
}

/* 4. Bounce */
@keyframes bounce {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-20px);
  }
}

/* 5. Pulse */
@keyframes pulse {
  0% {
    transform: scale(1);
    opacity: 1;
  }
  50% {
    transform: scale(1.05);
    opacity: 0.8;
  }
  100% {
    transform: scale(1);
    opacity: 1;
  }
}

/* 6. Rotate */
@keyframes rotate {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

/* 7. Swing */
@keyframes swing {
  20% {
    transform: rotate(15deg);
  }
  40% {
    transform: rotate(-10deg);
  }
  60% {
    transform: rotate(5deg);
  }
  80% {
    transform: rotate(-5deg);
  }
  100% {
    transform: rotate(0deg);
  }
}

/* 8. Glow */
@keyframes glow {
  0%, 100% {
    box-shadow: 0 0 5px rgba(52, 152, 219, 0.5);
  }
  50% {
    box-shadow: 0 0 20px rgba(52, 152, 219, 1);
  }
}
```

#### Paleta de Colores Sugerida:

```css
:root {
  --primary: #3498db;
  --secondary: #2ecc71;
  --accent: #e74c3c;
  --dark: #2c3e50;
  --light: #ecf0f1;
  --text: #333;
  --border: #bdc3c7;
}
```

#### Estructura HTML Sugerida:

```
- Header (logo, nav)
- Hero (título, descripción, CTA)
- Servicios/Habilidades (tarjetas)
- Proyectos (galería)
- Testimonios (carousel)
- Contacto (formulario)
- Footer
```

#### Desafío Extra:

- 🌟 Crear un "loading" animado para la página
- 🌟 Implementar un parallax effect
- 🌟 Hacer un scroll trigger (animación al scroll)
- 🌟 Crear un menu hamburger con animación
- 🌟 Agregar 3D transforms (rotateX, rotateY)
- 🌟 Implementar un typewriter effect
- 🌟 Crear un contador animado de números
- 🌟 Agregar confetti effect en botón
- 🌟 Crear tema claro/oscuro con transiciones
- 🌟 Implementar un "scroll to top" botón flotante

#### Criterios de Evaluación:

- **Variedad de Animaciones (30%)**: Diferentes tipos de animaciones, bien implementadas
- **Transiciones Suaves (20%)**: Cambios visuales fluidos y agradables
- **Rendimiento (15%)**: Animaciones sin lag, uso eficiente de GPU
- **Diseño Visual (20%)**: Atractivo, profesional, coherente
- **Código (15%)**: Limpio, comentado, bien organizado

¡Buena suerte creando tu portafolio animado!
