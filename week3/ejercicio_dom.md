# Ejercicio: Cambiador de Textos Interactivo

##  Objetivo
Crear una página web interactiva donde el usuario pueda cambiar el contenido de textos mediante clics en botones.

##  Requerimientos

### Parte 1: Estructura HTML
1. Crea un archivo `index.html` con la siguiente estructura:
   - Un título principal (`<h1>`) con el id `titulo` que diga "Bienvenido a mi página"
   - Un párrafo (`<p>`) con el id `descripcion` que contenga un texto descriptivo
   - Tres botones con los siguientes ids:
     - `btnCambiarTitulo`
     - `btnCambiarDescripcion`
     - `btnReset`

2. Vincula un archivo de estilos `styles.css` para darle diseño a tu página
3. Vincula un archivo de JavaScript `script.js` al final del body

### Parte 2: Estilos CSS
Diseña tu página de forma atractiva. Algunos requisitos mínimos:
- Usa Flexbox o Grid para centrar el contenido
- Aplica colores y tipografías agradables
- Los botones deben tener estilos hover
- Usa espaciado apropiado (padding, margin)

### Parte 3: Funcionalidad JavaScript
Implementa las siguientes funcionalidades en `script.js`:

1. **Botón Cambiar Título**: Al hacer clic, debe cambiar el texto del `<h1>` a "¡Título Cambiado!"

2. **Botón Cambiar Descripción**: Al hacer clic, debe cambiar el texto del párrafo a un nuevo texto de tu elección

3. **Botón Reset**: Al hacer clic, debe restaurar los textos originales

### Bonus (Opcional)
- Agrega un contador que muestre cuántas veces se han hecho clics en total
- Cambia el color de fondo del título cuando se cambia
- Añade animaciones CSS cuando cambian los textos
- Crea un botón que genere textos aleatorios de un array

## 💡 Pistas

### Para cambiar el texto de un elemento:
```javascript
elemento.textContent = "Nuevo texto";
// o
elemento.innerHTML = "Nuevo texto";
```

### Para seleccionar elementos:
```javascript
const elemento = document.getElementById('idDelElemento');
```

### Para escuchar eventos de clic:
```javascript
boton.addEventListener('click', function() {
    // Tu código aquí
});
```

##  Criterios de Evaluación

- [ ] El HTML está correctamente estructurado y validado
- [ ] El archivo JavaScript está vinculado correctamente
- [ ] Los botones responden a los clics
- [ ] El contenido de los elementos cambia correctamente
- [ ] El botón reset funciona
- [ ] El código está bien organizado y comentado
- [ ] Los estilos CSS están aplicados
- [ ] No hay errores en la consola del navegador

##  Entrega

1. Crea los tres archivos: `index.html`, `styles.css`, `script.js`
2. Prueba que todo funcione correctamente en el navegador
3. Verifica que no haya errores en la consola (F12 en el navegador)

##  Desafío Extra

Si terminas rápido, intenta crear una versión más avanzada:
- Un sistema de temas (modo claro/oscuro) con un botón
- Varios elementos que cambien al mismo tiempo
- Efectos de transición suaves
- Almacenar el estado en localStorage para que persista al recargar

