---
title: "🔗 Listas Enlazadas"
date: 2025-03-31
layout: post
categories: [Programación, Estructuras de Datos]
tags: [C++, Python]
description: "Guía completa sobre listas enlazadas con teoría, operaciones básicas y ejemplos en C++ y Python."
---

# 🔗 Listas Enlazadas

## 📘 1. ¿Qué es una Lista Enlazada?

Una **lista enlazada** es una estructura de datos lineal compuesta por nodos. Cada nodo contiene un dato y una referencia (o puntero) al siguiente nodo de la lista. A diferencia de los arrays estáticos, las listas enlazadas permiten **crecimiento dinámico** durante la ejecución.

> Las listas enlazadas se pueden implementar en distintas variantes: simples, dobles o circulares, según cuántos enlaces contiene cada nodo.
{:.prompt-info }

---

## 🧩 2. Características Principales

- **Tamaño dinámico**: Pueden crecer o reducirse durante la ejecución.
- **Memoria no contigua**: Los nodos se almacenan en distintas ubicaciones de memoria.
- **Inserciones y eliminaciones eficientes**: No requieren desplazamiento de elementos como en un array.

> El acceso a elementos no es directo, se necesita recorrer la lista desde el nodo inicial.
{:.prompt-warning }

---

## 🛠️ 3. Operaciones Comunes en Listas Enlazadas

| **Operación**    | **Descripción**                                             |
| ---------------- | ----------------------------------------------------------- |
| **Inserción**    | Agregar un nuevo nodo al inicio, medio o final de la lista. |
| **Borrado**      | Eliminar un nodo específico actualizando los enlaces.       |
| **Modificación** | Cambiar el valor de un nodo determinado.                    |
| **Acceso**       | Obtener el valor de un nodo tras recorrer la lista.         |
| **Búsqueda**     | Recorrer la lista hasta encontrar un valor específico.      |

---

## 💻 4. Implementación en C++ y Python

> Se utilizan `std::list` en C++ y `collections.deque` en Python porque ambas implementaciones proporcionan listas doblemente enlazadas optimizadas. Permiten inserciones y eliminaciones eficientes en ambos extremos y acceso secuencial, cumpliendo con el comportamiento típico de una lista enlazada.
{:.prompt-tip }

### C++: Lista Enlazada con `std::list`

```cpp
#include <iostream>
#include <list>
#include <algorithm>

int main() {
    std::list<int> lista = {1, 2, 3};

    // Inserción al final
    lista.push_back(4);

    // Inserción al inicio
    lista.push_front(0);

    // Modificación (recorremos hasta encontrar y modificamos)
    for (auto it = lista.begin(); it != lista.end(); ++it) {
        if (*it == 2) {
            *it = 99;
            break;
        }
    }

    // Recorrido
    for (int elemento : lista) {
        std::cout << elemento << " -> ";
    }
    std::cout << "NULL" << std::endl;

    // Búsqueda
    auto it = std::find(lista.begin(), lista.end(), 99);
    if (it != lista.end()) {
        std::cout << "Elemento encontrado: " << *it << std::endl;
    }

    return 0;
}
```

### Python: Lista Enlazada con `collections.deque`

```python
from collections import deque

# Declaración e inserción
lista = deque([1, 2, 3])
lista.append(4)       # Inserta al final
lista.appendleft(0)   # Inserta al inicio

# Modificación (reconstrucción con comprensión)
lista = deque([99 if x == 2 else x for x in lista])

# Recorrido
for x in lista:
    print(f"{x} -> ", end="")
print("None")

# Búsqueda
if 99 in lista:
    print("Elemento encontrado: 99")
```

> `deque` en Python es la estructura más cercana a una lista doblemente enlazada real. A diferencia de `list`, permite inserciones y eliminaciones eficientes en ambos extremos, sin el costo de realineación de memoria.
{:.prompt-info }

---

## 🧮 5. Complejidad Temporal de las Operaciones

| **Operación** | **Promedio** | **Peor Caso** |
| ------------- | ------------ | ------------- |
| Acceso        | O(n)         | O(n)          |
| Inserción     | O(1)–O(n)    | O(n)          |
| Borrado       | O(1)–O(n)    | O(n)          |
| Modificación  | O(n)         | O(n)          |
| Búsqueda      | O(n)         | O(n)          |

> La inserción en la cabeza es O(1), pero insertar al final requiere recorrer la lista si no se mantiene un puntero al final. Lo mismo pasa con el borrado.
{:.prompt-warning }

---

## 🚀 6. Casos de Uso Recomendados

Las listas enlazadas son útiles cuando:

- Se desconoce el número exacto de elementos por adelantado.
- Se realizan muchas inserciones o eliminaciones.
- El uso de memoria debe ser dinámico y eficiente.

### 💡 Ejemplos de aplicaciones prácticas:

- Implementación de colas y pilas.
- Sistemas que requieren estructuras flexibles (e.g., manejo de historial).
- Administración de memoria libre (listas de bloques).

> Utiliza listas enlazadas cuando la inserción/borrado es más frecuente que el acceso aleatorio.
{:.prompt-tip }

---

## ⚖️ 7. ¿Qué estructura usar según el problema?

| 🧩 **Estructura**     | 📌 **Úsala cuando...**                                         | 💡 **Ejemplos**                                                          |
| -------------------- | ------------------------------------------------------------- | ----------------------------------------------------------------------- |
| 🧮 **Array Estático** | Sabes el tamaño de antemano y necesitas acceso directo rápido | Tablas de datos, buffers, matrices                                      |
| 🔗 **Lista Enlazada** | Inserciones y eliminaciones frecuentes                        | Listas dinámicas, administración de memoria, estructuras personalizadas |
| 🥞 **Pila**           | Necesitas revertir, deshacer o volver atrás                   | Historial de acciones, evaluación de expresiones, DFS                   |

---

> "El universo es grande. Es vasto, complicado y ridículo. Y, a veces, muy raramente, suceden cosas imposibles y las llamamos milagros." – El Doctor, Doctor Who (Onceavo Doctor)