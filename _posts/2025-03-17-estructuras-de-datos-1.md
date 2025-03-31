---
title: "Arrays estáticos"
date: 2025-03-17
layout: post
categories: [Programación, Estructuras de Datos]
tags: [C++, Python]
description: "Guía completa sobre arrays estáticos con teoría, operaciones y ejemplos en C++ y Python."
---

# 📦 Arrays Estáticos

## 📘 1. ¿Qué es un Array?

Un **array estático** es una estructura de datos que almacena una colección de elementos del mismo tipo en posiciones de memoria contiguas. La principal característica que lo define es que **su tamaño se establece en el momento de su declaración y no puede cambiar durante la ejecución del programa**.

> A diferencia de otras estructuras como las listas dinámicas, los arrays estáticos no permiten redimensionamiento, lo cual implica una mayor eficiencia en el uso de memoria y velocidad de acceso, a costa de una menor flexibilidad.
{:.prompt-info }

---

## 🧩 2. Características Principales

- **Tamaño fijo**: El tamaño del array se define al momento de su creación y no puede ser alterado durante la ejecución.
- **Almacenamiento contiguo en memoria**: Todos los elementos del array se almacenan uno junto al otro, lo que permite un acceso eficiente.
- **Acceso rápido mediante índices**: Se puede acceder a cualquier elemento de forma directa utilizando su índice.

---

## 🛠️ 3. Operaciones Comunes en Arrays Estáticos

| **Operación**    | **Descripción**                                                                                        |
| ---------------- | ------------------------------------------------------------------------------------------------------ |
| **Inserción**    | Agregar un elemento en una posición específica si hay espacio disponible.                              |
| **Borrado**      | Eliminar un elemento en una posición determinada, desplazando los elementos restantes si es necesario. |
| **Modificación** | Cambiar el valor de un elemento en una posición específica.                                            |
| **Acceso**       | Obtener el valor de un elemento en una posición dada.                                                  |
| **Búsqueda**     | Encontrar la posición de un elemento en el array, si existe.                                           |

---

## 💻 4. Implementación en C++

```cpp
#include <iostream>
using namespace std;

int main() {
    const int SIZE = 5;
    int arr[SIZE] = {1, 2, 3, 4, 5}; // Declaración e inicialización

    // Inserción (modificamos la posición 2)
    arr[2] = 99;

    // Acceso
    cout << "Elemento en posición 2: " << arr[2] << endl;

    // Modificación
    arr[0] = 10;

    // Borrado (simulado con desplazamiento)
    for (int i = 1; i < SIZE - 1; i++) {
        arr[i] = arr[i + 1];
    }
    arr[SIZE - 1] = 0;

    // Recorrido
    cout << "Array completo: ";
    for (int i = 0; i < SIZE; i++) {
        cout << arr[i] << " ";
    }
    cout << endl;

    // Búsqueda
    int target = 99;
    for (int i = 0; i < SIZE; i++) {
        if (arr[i] == target) {
            cout << "Elemento encontrado en posición: " << i << endl;
            break;
        }
    }

    return 0;
}
```
---

## 💻 5. Implementación en Python

> En Python, se utiliza el módulo `array` del paquete estándar para simular arrays estáticos, ya que no se permite el uso de listas dinámicas (`list`). También es posible usar `numpy.array`, pero `array.array` es más adecuado en este caso por su similitud conceptual con los arrays de C++.
{:.prompt-tip }

```py
import array

# Declaración e inicialización
arr = array.array('i', [1, 2, 3, 4, 5])  # 'i' indica enteros con signo

# Inserción (modificamos la posición 2)
arr[2] = 99

# Acceso
print("Elemento en posición 2:", arr[2])

# Modificación
arr[0] = 10

# Borrado (simulado con desplazamiento manual)
for i in range(1, len(arr) - 1):
    arr[i] = arr[i + 1]
arr[-1] = 0

# Recorrido
print("Array completo:", list(arr))

# Búsqueda
target = 99
for i in range(len(arr)):
    if arr[i] == target:
        print("Elemento encontrado en posición:", i)
        break
```
--- 

## 🧮 5. Complejidad Temporal de las Operaciones

| **Operación** | **Promedio** | **Peor Caso** |
| ------------- | ------------ | ------------- |
| Acceso        | O(1)         | O(1)          |
| Inserción     | O(n)         | O(n)          |
| Borrado       | O(n)         | O(n)          |
| Modificación  | O(1)         | O(1)          |
| Búsqueda      | O(n)         | O(n)          |

> El acceso es constante en arrays porque el índice permite ir directamente a la dirección de memoria del elemento.
{:.prompt-info }

---

## 🚀 6. Casos de Uso Recomendados

Los arrays estáticos son recomendables cuando:

- Se conoce de antemano el número exacto de elementos a almacenar.
- Se necesita **máxima eficiencia** en tiempo de acceso y uso de memoria.
- La aplicación no requiere modificaciones frecuentes del tamaño del array.

### 💡 Ejemplos de aplicaciones prácticas

- Almacenamiento de **matrices fijas** en gráficos y videojuegos.
- Gestión de **buffers** en sistemas embebidos.
- **Tablas de búsqueda** en algoritmos numéricos o de procesamiento de señales.

Utiliza arrays estáticos para tareas donde el control de recursos y la predictibilidad son más importantes que la flexibilidad.
{:.prompt-tip }

---

## ⚖️ 7. Comparativa de Complejidad Temporal con otras estructuras de datos

| **Operación**    | **Arrays Estáticos** | **Listas Enlazadas** |
| ---------------- | -------------------- | -------------------- |
| **Acceso**       | O(1)                 | O(n)                 |
| **Inserción**    | O(n)                 | O(1)–O(n)            |
| **Borrado**      | O(n)                 | O(1)–O(n)            |
| **Modificación** | O(1)                 | O(n)                 |
| **Búsqueda**     | O(n)                 | O(n)                 |

---

> "Cuando haces las cosas bien, la gente no está segura de si realmente hiciste algo." – Dios, Futurama