# 🐍 Cheatsheet de Python en Español

## Índice

1. [Sintaxis Básica](#sintaxis-básica)
2. [Estructuras de Control](#estructuras-de-control)
3. [Funciones](#funciones)
4. [Colecciones](#colecciones)
5. [Manipulación de Cadenas](#manipulación-de-cadenas)
6. [Manejo de Errores](#manejo-de-errores)
7. [Programación Orientada a Objetos](#programación-orientada-a-objetos)
8. [Trucos y Atajos](#trucos-y-atajos)
9. [Conversiones](#conversiones)

---

## 🛠️ Sintaxis Básica

```python
# Variables y tipos de datos
x = 10            # Entero
pi = 3.14         # Flotante
nombre = "Python" # Cadena
es_valido = True  # Booleano

# Comentarios
# Esto es un comentario de una línea
"""Este es un
comentario de varias líneas"""

# Entrada y salida
nombre = input("¿Cómo te llamas?")
print(f"Hola, {nombre}!")
```

---

## 🔄 Estructuras de Control

```python
# Condicionales
edad = 20
if edad >= 18:
    print("Adulto")
elif edad >= 13:
    print("Adolescente")
else:
    print("Niño")

# Bucles
for i in range(5):
    print(i)  # 0 1 2 3 4

contador = 0
while contador < 5:
    print(contador)
    contador += 1

# Comprensión de listas
cuadrados = [x**2 for x in range(5)]  # [0, 1, 4, 9, 16]
```

---

## 🧩 Funciones

```python
# Definición de funciones

def saludar(nombre="Mundo"):
    return f"Hola, {nombre}!"

print(saludar("Carlos"))
```

- **Funciones Lambda**:

```python
suma = lambda x, y: x + y
print(suma(3, 5))  # 8
```

---

## 📦 Colecciones

```python
# Listas
numeros = [1, 2, 3]
numeros.append(4)
print(numeros)  # [1, 2, 3, 4]

# Tuplas (inmutables)
coordenadas = (10, 20)

# Conjuntos (sin duplicados)
colores = {"rojo", "verde", "azul"}

# Diccionarios (clave-valor)
estudiante = {"nombre": "Ana", "edad": 22}
print(estudiante["nombre"])  # Ana
```

---

## 🛠️ Manipulación de Cadenas

```python
texto = "Python"
print(texto.upper())  # PYTHON
print(texto.lower())  # python
print(texto.replace("Py", "My"))  # Mython
print(f"Hola, {texto}!")
```

---

## ⚠️ Manejo de Errores

```python
try:
    x = int("abc")
except ValueError as e:
    print(f"Error: {e}")
finally:
    print("Fin del manejo de errores")
```

---

## 🧱 Programación Orientada a Objetos

```python
class Persona:
    def __init__(self, nombre, edad):
        self.nombre = nombre
        self.edad = edad

    def saludar(self):
        print(f"Hola, soy {self.nombre}")

p = Persona("Carlos", 30)
p.saludar()
```

---

## 🚀 Trucos y Atajos

```python
# Unir listas
lista = [1, 2, 3] + [4, 5]

# Desempaquetado
x, y, z = [1, 2, 3]

# Enumerar elementos
for i, valor in enumerate(["a", "b", "c"]):
    print(i, valor)

# Operador ternario
mensaje = "Adulto" if edad >= 18 else "Menor"
```

---

## 🔄 Conversiones

```python
# Conversión entre tipos
int("123")  # 123
float("3.14")  # 3.14
str(123)  # '123'
list("abc")  # ['a', 'b', 'c']
tuple([1, 2, 3])  # (1, 2, 3)
set([1, 2, 2, 3])  # {1, 2, 3}

# Conversión binaria, octal y hexadecimal
bin(10)  # '0b1010'
oct(10)  # '0o12'
hex(10)  # '0xa'

# Conversión entre estructuras de datos
int(True)  # 1
int(False)  # 0
```

---
