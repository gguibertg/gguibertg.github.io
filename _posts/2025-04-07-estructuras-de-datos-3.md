---
title: "🥞 Pilas"
date: 2025-04-07
layout: post
categories: [Programación, Estructuras de Datos]
tags: [C++, Python]
description: "Guía práctica sobre pilas: teoría, operaciones, ejemplos y código en C++ y Python."
---

# 🥞 Pilas

## 📘 1. ¿Qué es una Pila?

Una **pila** es una estructura de datos lineal que sigue el principio **LIFO** (*Last In, First Out*), lo que significa que el último elemento en entrar es el primero en salir. 

> Imagina una pila de platos: solo puedes acceder al último que colocaste. Para llegar al de abajo, primero debes retirar los de arriba.
{:.prompt-info }

---

## 🧩 2. Características Principales

- **Acceso restringido**: Solo se puede insertar o eliminar desde un extremo (el tope).
- **Orden LIFO**: El último elemento añadido es el primero en salir.
- **Simplicidad**: Es una de las estructuras más simples y rápidas.

> Las pilas no permiten acceso aleatorio directo a los elementos, como sí ocurre con arrays.
{:.prompt-warning }

---

## 🛠️ 3. Operaciones Comunes en Pilas

| **Operación** | **Descripción**                                  |
| ------------- | ------------------------------------------------ |
| **Push**      | Inserta un nuevo elemento en el tope de la pila. |
| **Pop**       | Elimina el elemento que está en el tope.         |
| **Top/Peek**  | Muestra el elemento en el tope sin eliminarlo.   |
| **IsEmpty**   | Verifica si la pila está vacía.                  |
| **Size**      | Devuelve la cantidad de elementos en la pila.    |

---

## 💻 4. Implementación en C++ y Python

> Las bibliotecas estándar de C++ (`std::stack`) y Python (`list`) proporcionan herramientas para trabajar con pilas de manera eficiente y simple.
{:.prompt-tip }

### C++: Pila con `std::stack`

```cpp
#include <iostream>
#include <stack>

int main() {
    std::stack<int> pila;

    // Push
    pila.push(10);
    pila.push(20);
    pila.push(30);

    // Top
    std::cout << "Tope: " << pila.top() << std::endl;

    // Pop
    pila.pop();

    // Nuevo tope
    std::cout << "Nuevo Tope: " << pila.top() << std::endl;

    // Verificar si está vacía
    if (pila.empty()) {
        std::cout << "La pila está vacía." << std::endl;
    }

    return 0;
}
```

### Python: Pila con `list`

```py
# Declaración de la pila
pila = []

# Push
pila.append(10)
pila.append(20)
pila.append(30)

# Peek
print("Tope:", pila[-1])

# Pop
pila.pop()

# Nuevo tope
print("Nuevo Tope:", pila[-1])

# Verificar si está vacía
if not pila:
    print("La pila está vacía.")

```

> En Python, list es la forma más común de implementar una pila, ideal para la mayoría de los casos prácticos y ejemplos simples. Sin embargo, si esperas que la pila crezca mucho o necesitas un rendimiento más robusto en operaciones repetitivas, considera usar collections.deque, que garantiza tiempo constante O(1) incluso bajo alta carga. 
{:.prompt-info }

--- 

## 🧮 5. Complejidad Temporal de las Operaciones

| **Operación** | **Promedio** | **Peor Caso** |
| ------------- | ------------ | ------------- |
| Push          | O(1)         | O(1)          |
| Pop           | O(1)         | O(1)          |
| Top/Peek      | O(1)         | O(1)          |
| IsEmpty       | O(1)         | O(1)          |
| Size          | O(1)         | O(1)          |

> Todas las operaciones de una pila bien implementada son de tiempo constante.
{:.prompt-info }

---

## 🚀 6. Casos de Uso Recomendados

Las pilas son ideales cuando:

- Se necesita almacenar elementos en orden inverso.
- Las operaciones siguen un patrón LIFO.
- Se requiere una estructura temporal para resolver problemas complejos.

### 💡 Ejemplos de aplicaciones prácticas:

- Deshacer acciones en editores de texto.
- Evaluación de expresiones matemáticas (notación postfija).
- Recorridos en profundidad (DFS) en grafos o árboles.
- Manejo de llamadas y retorno en funciones recursivas.

> Usa una pila cuando debas recordar el camino recorrido o invertir un orden.
{:.prompt-tip }

---

## ⚖️ 7. ¿Qué estructura usar según el problema?

| 🧩 **Estructura**     | 📌 **Úsala cuando...**                                         | 💡 **Ejemplos**                                                          |
| -------------------- | ------------------------------------------------------------- | ----------------------------------------------------------------------- |
| 🧮 **Array Estático** | Sabes el tamaño de antemano y necesitas acceso directo rápido | Tablas de datos, buffers, matrices                                      |
| 🔗 **Lista Enlazada** | Inserciones y eliminaciones frecuentes                        | Listas dinámicas, administración de memoria, estructuras personalizadas |
| 🥞 **Pila**           | Necesitas revertir, deshacer o volver atrás                   | Historial de acciones, evaluación de expresiones, DFS                   |

---

> "Hazlo simple. Pero no más simple de lo necesario." — Albert Einstein.
