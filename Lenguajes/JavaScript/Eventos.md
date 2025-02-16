# Eventos en JavaScript - Cheatsheet 🎉

## Escuchar Eventos 👂
```javascript
// Método 1: Usar addEventListener (recomendado)
elemento.addEventListener("evento", funcion);

// Método 2: Usar atributos HTML (no recomendado)
<button onclick="funcion()">Click</button>

// Método 3: Asignar directamente a propiedades del elemento (no recomendado)
elemento.onclick = function() { ... };
```

## Eliminar Eventos 🗑️
```javascript
elemento.removeEventListener("evento", funcion);
```

## Eventos Comunes ⚡

### Eventos del Mouse
```javascript
elemento.addEventListener("click", funcion); // Click
elemento.addEventListener("dblclick", funcion); // Doble click
elemento.addEventListener("mouseover", funcion); // Mouse sobre el elemento
elemento.addEventListener("mouseout", funcion); // Mouse fuera del elemento
elemento.addEventListener("mousemove", funcion); // Mouse moviéndose sobre el elemento
elemento.addEventListener("mousedown", funcion); // Botón del mouse presionado
elemento.addEventListener("mouseup", funcion); // Botón del mouse liberado
elemento.addEventListener("contextmenu", funcion); // Click derecho
```

### Eventos del Teclado ⌨️
```javascript
elemento.addEventListener("keydown", funcion); // Tecla presionada
elemento.addEventListener("keyup", funcion); // Tecla liberada
elemento.addEventListener("keypress", funcion); // Tecla presionada y liberada (obsoleto)
```

### Eventos de Formularios 📝
```javascript
elemento.addEventListener("submit", funcion); // Envío de formulario
elemento.addEventListener("change", funcion); // Cambio en un input/select/textarea
elemento.addEventListener("input", funcion); // Entrada de texto en un input/textarea
elemento.addEventListener("focus", funcion); // Enfoque en un elemento
elemento.addEventListener("blur", funcion); // Desenfoque de un elemento
elemento.addEventListener("reset", funcion); // Reseteo de formulario
```

### Eventos de la Ventana 🪟
```javascript
window.addEventListener("load", funcion); // Página completamente cargada
window.addEventListener("resize", funcion); // Cambio de tamaño de la ventana
window.addEventListener("scroll", funcion); // Desplazamiento de la página
window.addEventListener("beforeunload", funcion); // Antes de cerrar/recargar la página
```

### Eventos de Drag & Drop 🖱️➡️
```javascript
elemento.addEventListener("drag", funcion); // Elemento arrastrado
elemento.addEventListener("dragstart", funcion); // Inicio de arrastre
elemento.addEventListener("dragend", funcion); // Fin de arrastre
elemento.addEventListener("dragover", funcion); // Elemento arrastrado sobre otro
elemento.addEventListener("dragenter", funcion); // Elemento arrastrado entra en otro
elemento.addEventListener("dragleave", funcion); // Elemento arrastrado sale de otro
elemento.addEventListener("drop", funcion); // Elemento soltado
```

### Eventos de Touch (Pantallas Táctiles) 📱
```javascript
elemento.addEventListener("touchstart", funcion); // Toque iniciado
elemento.addEventListener("touchend", funcion); // Toque finalizado
elemento.addEventListener("touchmove", funcion); // Toque moviéndose
elemento.addEventListener("touchcancel", funcion); // Toque cancelado
```

### Eventos de Medios (Audio/Video) 🎵🎥
```javascript
elemento.addEventListener("play", funcion); // Reproducción iniciada
elemento.addEventListener("pause", funcion); // Reproducción pausada
elemento.addEventListener("ended", funcion); // Reproducción finalizada
elemento.addEventListener("timeupdate", funcion); // Tiempo de reproducción actualizado
elemento.addEventListener("volumechange", funcion); // Cambio de volumen
```
```` ▋
