# JavaScript 🌟

<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/6a/JavaScript-logo.png/640px-JavaScript-logo.png" alt="JavaScript Logo" width="300"/>
</p>

JavaScript es un lenguaje de programación interpretado, orientado a objetos, débilmente tipado y dinámico. Es uno de los tres lenguajes fundamentales para el desarrollo web, junto con HTML y CSS. JavaScript permite crear contenido dinámico y funcionalidades interactivas en los sitios web. 💻✨

## Índice 📑

- [Tipos de Datos 📊](#tipos-de-datos-)
- [Operadores ➕➖✖️➗](#operadores-)
- [Estructuras de Control 🔄](#estructuras-de-control-)
- [Funciones 🔧](#funciones-)
- [Arrays 📚](#arrays-)
- [Objetos 🧩](#objetos-)
- [Clases 🏫](#clases-)
- [Promesas y Async/Await ⏳](#promesas-y-asyncawait-)
- [Métodos de Strings 📝](#métodos-de-strings-)
- [Métodos de Números 🔢](#métodos-de-números-)
- [DOM Manipulation 🌐](#dom-manipulation-)
- [JSON 📦](#json-)
- [Módulos (ES6) 📦](#módulos-es6-)
- [Errores y Excepciones ❗](#errores-y-excepciones-)
- [Temporizadores ⏲️](#temporizadores-)
- [LocalStorage y SessionStorage 💾](#localstorage-y-sessionstorage-)
- [Fetch API 🌐](#fetch-api-)
- [Spread y Rest 📌](#spread-y-rest-)
- [Destructuración 📥📤](#destructuración-)
- [Template Literals 📝](#template-literals-)
- [Map y Set 🗺️🗄️](#map-y-set-)
- [Proxy 🛡️](#proxy-)
- [Generadores 🔄](#generadores-)
- [Symbol 🔑](#symbol-)
- [WeakMap y WeakSet 🗺️🗄️](#weakmap-y-weakset-)
- [Internacionalización (Intl) 🌍](#internacionalización-intl-)
- [BigInt 🔢](#bigint-)
- [Optional Chaining ❓](#optional-chaining-)
- [Nullish Coalescing ❓](#nullish-coalescing-)
- [Atomics ⚛️](#atomics-)
- [Finalización Registrada 🏁](#finalización-registrada-)
- [Importación Dinámica 📥](#importación-dinámica-)
- [Top-Level Await ⏳](#top-level-await-)

## Características 🔍

- **Lenguaje interpretado**: JavaScript no necesita ser compilado antes de ser ejecutado, el navegador lo interpreta directamente. 🚀
- **Orientado a objetos**: JavaScript soporta la programación orientada a objetos mediante prototipos. 🧩
- **Débilmente tipado**: Las variables en JavaScript no tienen un tipo de dato fijo, lo que permite flexibilidad pero también puede causar errores difíciles de detectar. ⚠️
- **Dinámico**: Las propiedades y métodos de los objetos pueden ser añadidos, modificados o eliminados en tiempo de ejecución. 🔄

## Usos de JavaScript 🌍

1. **Desarrollo Web**: JavaScript se utiliza principalmente para el desarrollo de aplicaciones web, permitiendo la creación de interfaces de usuario interactivas. 🌐
2. **Desarrollo del lado del servidor**: Con la llegada de Node.js, JavaScript puede ser utilizado para el desarrollo del lado del servidor. 🖥️
3. **Aplicaciones móviles**: Frameworks como React Native permiten el desarrollo de aplicaciones móviles utilizando JavaScript. 📱
4. **Desarrollo de videojuegos**: Librerías como Phaser permiten la creación de videojuegos en 2D. 🎮

## Hoja de Trucos 📝

### Tipos de Datos 📊

```javascript
// Primitivos
let string = "Hola"; // Cadena de texto
let number = 42; // Número
let boolean = true; // Booleano
let nulo = null; // Valor nulo
let indefinido = undefined; // Valor indefinido
let simbolo = Symbol("id"); // Símbolo único

// Objetos
let objeto = { clave: "valor" }; // Objeto
let array = [1, 2, 3]; // Arreglo
let funcion = function() {}; // Función
```

### Operadores ➕➖✖️➗

```javascript
// Aritméticos
let suma = 1 + 2; // 3
let resta = 5 - 3; // 2
let multiplicacion = 2 * 3; // 6
let division = 10 / 2; // 5
let modulo = 10 % 3; // 1

// Comparación
let igual = 5 == "5"; // true (solo valor)
let igualEstricto = 5 === "5"; // false (valor y tipo)
let diferente = 5 != "5"; // false
let diferenteEstricto = 5 !== "5"; // true
let mayorQue = 10 > 5; // true
let menorQue = 10 < 5; // false

// Lógicos
let and = true && false; // false
let or = true || false; // true
let not = !true; // false
```

### Estructuras de Control 🔄

```javascript
// Condicionales
if (condicion) {
  // Código si es verdadero
} else if (otraCondicion) {
  // Código si otraCondicion es verdadero
} else {
  // Código si ninguna es verdadera
}

// Operador Ternario
let resultado = condicion ? "verdadero" : "falso";

// Switch
switch (valor) {
  case 1:
    // Código para valor 1
    break;
  case 2:
    // Código para valor 2
    break;
  default:
    // Código si no coincide ningún caso
}

// Bucles
for (let i = 0; i < 5; i++) {
  // Código que se repite 5 veces
}

while (condicion) {
  // Código mientras la condición sea verdadera
}

do {
  // Código que se ejecuta al menos una vez
} while (condicion);
```

### Funciones 🔧

```javascript
// Declaración de función
function saludar(nombre) {
  return "Hola, " + nombre;
}

// Expresión de función
const saludar = function(nombre) {
  return "Hola, " + nombre;
};

// Función flecha (arrow function)
const saludar = (nombre) => "Hola, " + nombre;

// Parámetros por defecto
const sumar = (a = 1, b = 2) => a + b;
```

### Arrays 📚

```javascript
let array = [1, 2, 3];

// Métodos comunes
array.push(4); // Añade al final: [1, 2, 3, 4]
array.pop(); // Elimina el último elemento: [1, 2, 3]
array.shift(); // Elimina el primer elemento: [2, 3]
array.unshift(0); // Añade al inicio: [0, 2, 3]
array.slice(1, 2); // Extrae una porción: [2]
array.splice(1, 1, 4); // Cambia contenido: [0, 4, 3]

// Iteración
array.forEach((item) => console.log(item));
let nuevoArray = array.map((item) => item * 2);
let filtrado = array.filter((item) => item > 2);
```

### Objetos 🧩

```javascript
let objeto = {
  clave: "valor",
  metodo: function() {
    return this.clave;
  }
};

// Acceso
objeto.clave; // "valor"
objeto["clave"]; // "valor"

// Añadir/Modificar
objeto.nuevaClave = "nuevoValor";

// Eliminar
delete objeto.clave;

// Iteración
for (let clave in objeto) {
  console.log(clave, objeto[clave]);
}
```

### Clases 🏫

```javascript
class Persona {
  constructor(nombre, edad) {
    this.nombre = nombre;
    this.edad = edad;
  }

  saludar() {
    return `Hola, soy ${this.nombre}`;
  }
}

let persona = new Persona("Juan", 30);
persona.saludar(); // "Hola, soy Juan"
```

### Promesas y Async/Await ⏳

```javascript
// Promesa
let promesa = new Promise((resolve, reject) => {
  setTimeout(() => resolve("Éxito"), 1000);
});

promesa.then((resultado) => console.log(resultado));

// Async/Await
async function obtenerDatos() {
  let resultado = await promesa;
  console.log(resultado);
}
```

### Métodos de Strings 📝

```javascript
let str = "Hola Mundo";

str.length; // 10
str.toUpperCase(); // "HOLA MUNDO"
str.toLowerCase(); // "hola mundo"
str.indexOf("Mundo"); // 5
str.slice(0, 4); // "Hola"
str.replace("Mundo", "JavaScript"); // "Hola JavaScript"
```

### Métodos de Números 🔢

```javascript
let num = 123.456;

num.toFixed(2); // "123.46"
num.toString(); // "123.456"
parseInt("123"); // 123
parseFloat("123.456"); // 123.456
Math.round(num); // 123
Math.floor(num); // 123
Math.ceil(num); // 124
```

### DOM Manipulation 🌐

```javascript
// Selección
document.getElementById("id"); // Selecciona por ID
document.querySelector(".clase"); // Selecciona el primer elemento con la clase
document.querySelectorAll("p"); // Selecciona todos los elementos <p>

// Modificación
elemento.textContent = "Nuevo texto";
elemento.innerHTML = "<strong>Texto</strong>";
elemento.setAttribute("atributo", "valor");

// Eventos
elemento.addEventListener("click", function() {
  console.log("Clickeado");
});
```

### JSON 📦

```javascript
let objeto = { nombre: "Juan", edad: 30 };

// Convertir a JSON
let json = JSON.stringify(objeto); // '{"nombre":"Juan","edad":30}'

// Convertir de JSON
let nuevoObjeto = JSON.parse(json); // { nombre: "Juan", edad: 30 }
```

### Módulos (ES6) 📦

```javascript
// Exportar
export const nombre = "Juan";
export function saludar() { return "Hola"; }

// Importar
import { nombre, saludar } from './modulo.js';
```

### Errores y Excepciones ❗

```javascript
try {
  // Código que puede fallar
} catch (error) {
  console.error(error);
} finally {
  // Código que siempre se ejecuta
}
```

### Temporizadores ⏲️

```javascript
setTimeout(() => {
  console.log("Después de 1 segundo");
}, 1000);

setInterval(() => {
  console.log("Cada 1 segundo");
}, 1000);
```

### LocalStorage y SessionStorage 💾

```javascript
// Guardar datos
localStorage.setItem("clave", "valor");
sessionStorage.setItem("clave", "valor");

// Obtener datos
let valor = localStorage.getItem("clave");

// Eliminar datos
localStorage.removeItem("clave");
localStorage.clear(); // Limpia todo
```

### Fetch API 🌐

```javascript
fetch("https://api.ejemplo.com/datos")
  .then((response) => response.json())
  .then((data) => console.log(data))
  .catch((error) => console.error(error));
```

### Spread y Rest 📌

```javascript
// Spread (expandir)
let array1 = [1, 2, 3];
let array2 = [...array1, 4, 5]; // [1, 2, 3, 4, 5]

// Rest (agrupar)
function sumar(...numeros) {
  return numeros.reduce((a, b) => a + b);
}
sumar(1, 2, 3); // 6
```

### Destructuración 📥📤

```javascript
let objeto = { nombre: "Juan", edad: 30 };
let { nombre, edad } = objeto; // nombre = "Juan", edad = 30

let array = [1, 2, 3];
let [a, b, c] = array; // a = 1, b = 2, c = 3
```

### Template Literals 📝

```javascript
let nombre = "Juan";
let saludo = `Hola, ${nombre}`; // "Hola, Juan"
```

### Map y Set 🗺️🗄️

```javascript
// Map
let mapa = new Map();
mapa.set("clave", "valor");
mapa.get("clave"); // "valor"

// Set
let conjunto = new Set([1, 2, 3]);
conjunto.add(4); // {1, 2, 3, 4}
conjunto.has(2); // true
```

### Proxy 🛡️

```javascript
let objetivo = { mensaje: "Hola" };
let manejador = {
  get: function(objeto, propiedad) {
    return propiedad in objeto ? objeto[propiedad] : "No existe";
  }
};
let proxy = new Proxy(objetivo, manejador);
proxy.mensaje; // "Hola"
proxy.otraClave; // "No existe"
```

### Generadores 🔄

```javascript
function* generador() {
  yield 1;
  yield 2;
  yield 3;
}

let gen = generador();
gen.next().value; // 1
gen.next().value; // 2
gen.next().value; // 3
```

### Symbol 🔑

```javascript
let id = Symbol("id");
let objeto = { [id]: 123 };
objeto[id]; // 123
```

### WeakMap y WeakSet 🗺️🗄️

```javascript
// WeakMap
let weakMap = new WeakMap();
let obj = {};
weakMap.set(obj, "valor");
weakMap.get(obj); // "valor"

// WeakSet
let weakSet = new WeakSet();
weakSet.add(obj);
weakSet.has(obj); // true
```

### Internacionalización (Intl) 🌍

```javascript
let fecha = new Date();
let formateador = new Intl.DateTimeFormat("es-ES", { dateStyle: "full" });
formateador.format(fecha); // "viernes, 13 de octubre de 2023"
```

### BigInt 🔢

```javascript
let grande = BigInt(9007199254740991);
grande + 1n; // 9007199254740992n
```

### Optional Chaining ❓

```javascript
let usuario = { nombre: "Juan" };
let edad = usuario?.edad; // undefined (no lanza error)
```

### Nullish Coalescing ❓

```javascript
let valor = null;
let resultado = valor ?? "valor por defecto"; // "valor por defecto"
```

### Atomics ⚛️

```javascript
let buffer = new SharedArrayBuffer(16);
let vista = new Int32Array(buffer);
Atomics.add(vista, 0, 5); // 5
```

### Finalización Registrada 🏁

```javascript
let registro = new FinalizationRegistry((valor) => {
  console.log(`Recolectado: ${valor}`);
});
registro.register({}, "objeto");
```

### Importación Dinámica 📥

```javascript
import('./modulo.js')
  .then((modulo) => {
    modulo.funcion();
  });
```

### Top-Level Await ⏳

```javascript
let datos = await fetch("https://api.ejemplo.com/datos").then((res) => res.json());
```

## Recursos 📚

- [MDN Web Docs - JavaScript](https://developer.mozilla.org/es/docs/Web/JavaScript)
- [W3Schools - JavaScript](https://www.w3schools.com/js/)
- [JavaScript.info](https://javascript.info/)

## Contribuciones 🤝

¡Las contribuciones son bienvenidas! Si tienes alguna mejora o sugerencia, no dudes en abrir un pull request o una issue en el repositorio. 🛠️

## Licencia 📄

Este proyecto está licenciado bajo la Licencia MIT. Puedes ver más detalles en el archivo LICENSE. 🔓
```` ▋
