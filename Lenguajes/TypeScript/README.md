# TypeScript 🌟

<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/4c/Typescript_logo_2020.svg/1200px-Typescript_logo_2020.svg.png" alt="TypeScript Logo" width="300"/>
</p>

TypeScript es un lenguaje de programación desarrollado y mantenido por Microsoft. Es un superset de JavaScript que añade tipado estático opcional y otras características avanzadas. TypeScript se transpila a JavaScript, lo que permite su uso en cualquier entorno donde JavaScript se ejecute. 💻✨

## Índice 📑

- [Tipos de Datos 📊](#tipos-de-datos-)
- [Interfaces y Tipos 📝](#interfaces-y-tipos-)
- [Clases 🏫](#clases-)
- [Funciones 🔧](#funciones-)
- [Genéricos 🧬](#genéricos-)
- [Módulos 📦](#módulos-)
- [Namespaces 📚](#namespaces-)
- [Decoradores 🎨](#decoradores-)
- [Manipulación del DOM 🌐](#manipulación-del-dom-)
- [Configuración de tsconfig.json ⚙️](#configuración-de-tsconfigjson-)
- [Errores y Excepciones ❗](#errores-y-excepciones-)
- [Tipado Avanzado 🔍](#tipado-avanzado-)
- [Utilidades de Tipos 📦](#utilidades-de-tipos-)

## Características 🔍

- **Tipado estático**: TypeScript permite definir tipos estáticos, lo que ayuda a detectar errores en tiempo de desarrollo. 🚀
- **Superset de JavaScript**: Todo código JavaScript válido es también válido en TypeScript. 🧩
- **Transpilación**: TypeScript se convierte a JavaScript, lo que permite su ejecución en cualquier entorno JavaScript. 🔄
- **Soporte para ES6+**: TypeScript incluye características de ES6 y versiones posteriores, incluso antes de que sean implementadas en todos los navegadores. ✨

## Usos de TypeScript 🌍

1. **Desarrollo Web**: TypeScript es ampliamente utilizado en el desarrollo de aplicaciones web, especialmente con frameworks como Angular y React. 🌐
2. **Desarrollo del lado del servidor**: Con Node.js, TypeScript se puede utilizar para desarrollar aplicaciones del lado del servidor. 🖥️
3. **Desarrollo de aplicaciones móviles**: Frameworks como React Native también soportan TypeScript. 📱

## Hoja de Trucos 📝

### Tipos de Datos 📊

```typescript
// Primitivos
let cadena: string = "Hola";
let numero: number = 42;
let booleano: boolean = true;
let nulo: null = null;
let indefinido: undefined = undefined;
let simbolo: symbol = Symbol("id");

// Arrays
let lista: number[] = [1, 2, 3];
let listaGenerica: Array<number> = [1, 2, 3];

// Tuplas
let tupla: [string, number];
tupla = ["Hola", 42];

// Enum
enum Color { Rojo, Verde, Azul }
let color: Color = Color.Verde;

// Any
let cualquierValor: any = 4;
cualquierValor = "cadena"; // También válido

// Void
function saludar(): void {
  console.log("Hola");
}

// Never
function error(mensaje: string): never {
  throw new Error(mensaje);
}
```

### Interfaces y Tipos 📝

```typescript
interface Persona {
  nombre: string;
  edad: number;
  saludar(): void;
}

let juan: Persona = {
  nombre: "Juan",
  edad: 30,
  saludar() {
    console.log(`Hola, soy ${this.nombre}`);
  }
};

type Punto = {
  x: number;
  y: number;
};

let punto: Punto = { x: 10, y: 20 };
```

### Clases 🏫

```typescript
class Animal {
  nombre: string;

  constructor(nombre: string) {
    this.nombre = nombre;
  }

  mover(distancia: number = 0) {
    console.log(`${this.nombre} se movió ${distancia} metros.`);
  }
}

class Perro extends Animal {
  ladrar() {
    console.log("¡Guau! ¡Guau!");
  }
}

let perro = new Perro("Firulais");
perro.ladrar();
perro.mover(10);
```

### Funciones 🔧

```typescript
function suma(a: number, b: number): number {
  return a + b;
}

// Función anónima
const multiplicar = (a: number, b: number): number => a * b;

// Parámetros opcionales y por defecto
function construirNombre(nombre: string, apellido?: string): string {
  return apellido ? `${nombre} ${apellido}` : nombre;
}

let resultado = construirNombre("Juan"); // "Juan"
```

### Genéricos 🧬

```typescript
function identidad<T>(arg: T): T {
  return arg;
}

let salida = identidad<string>("Hola");
let numero = identidad<number>(42);

interface Caja<T> {
  contenido: T;
}

let caja: Caja<string> = { contenido: "Regalo" };
```

### Módulos 📦

```typescript
// Exportar
export const nombre: string = "Juan";
export function saludar(): string { return "Hola"; }

// Importar
import { nombre, saludar } from './modulo';
```

### Namespaces 📚

```typescript
namespace EspacioDeNombres {
  export function saludar() {
    console.log("Hola desde el namespace");
  }
}

EspacioDeNombres.saludar();
```

### Decoradores 🎨

```typescript
function decoradorDeClase(constructor: Function) {
  console.log(`Clase decorada: ${constructor.name}`);
}

@decoradorDeClase
class MiClase {
  constructor() {
    console.log("Instancia creada");
  }
}

let instancia = new MiClase();
```

### Manipulación del DOM 🌐

```typescript
let elemento = document.getElementById("miElemento") as HTMLElement;
elemento.textContent = "Nuevo texto";

elemento.addEventListener("click", () => {
  console.log("Elemento clickeado");
});
```

### Configuración de tsconfig.json ⚙️

```json
{
  "compilerOptions": {
    "target": "es5",
    "module": "commonjs",
    "strict": true,
    "esModuleInterop": true,
    "skipLibCheck": true,
    "forceConsistentCasingInFileNames": true
  }
}
```

### Errores y Excepciones ❗

```typescript
try {
  // Código que puede fallar
} catch (error) {
  console.error(error);
} finally {
  // Código que siempre se ejecuta
}
```

### Tipado Avanzado 🔍

```typescript
type Combinado = string | number;

function imprimirId(id: Combinado) {
  if (typeof id === "string") {
    console.log("ID: " + id.toUpperCase());
  } else {
    console.log("ID: " + id);
  }
}
```

### Utilidades de Tipos 📦

```typescript
interface Todo {
  titulo: string;
  descripcion: string;
  completado: boolean;
}

type TodoParcial = Partial<Todo>;
type TodoSoloLectura = Readonly<Todo>;

let todo: TodoSoloLectura = {
  titulo: "Aprender TypeScript",
  descripcion: "Estudiar la documentación oficial",
  completado: false
};

// todo.completado = true; // Error: no se puede modificar una propiedad de solo lectura
```

## Recursos 📚

- [TypeScript Official Documentation](https://www.typescriptlang.org/docs/)
- [MDN Web Docs - TypeScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeScript)
- [TypeScript Deep Dive](https://basarat.gitbook.io/typescript/)

## Contribuciones 🤝

¡Las contribuciones son bienvenidas! Si tienes alguna mejora o sugerencia, no dudes en abrir un pull request o una issue en el repositorio. 🛠️

## Licencia 📄

Este proyecto está licenciado bajo la Licencia MIT. Puedes ver más detalles en el archivo LICENSE. 🔓
