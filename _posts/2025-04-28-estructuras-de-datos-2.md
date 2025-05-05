---
title: "🔗 Linked Lists"
date: 2025-05-05
layout: post
categories: [Programación, Estructuras de Datos]
tags: [C++, Python]
description: "Aprende qué es una Linked List, los distintos tipos (simples, dobles, circulares) y cómo realizar operaciones básicas como recorrido, inserción y borrado, con ejemplos prácticos en C++ y Python."
author: gabriel
---

# 🔗 Linked Lists

> **¿Por qué aprender Linked Lists?**

Las listas enlazadas son estructuras clave en programación porque permiten **insertar y eliminar elementos de forma eficiente**, especialmente cuando la cantidad de datos es variable o desconocida de antemano. Desde sistemas operativos hasta compiladores, las linked lists están en el corazón de muchas aplicaciones.

---

## 📘 ¿Qué es una Linked List?

Una **linked list** es una estructura de datos compuesta por **nodos**. Cada nodo contiene dos partes:

- El **dato** que almacena (por ejemplo, un número, texto, etc.)
- Un **puntero** (o referencia) al siguiente nodo de la lista

El primer nodo se llama **cabeza (head)** y el último apunta a `null` (o `None`, según el lenguaje), indicando el final de la lista.

> Las linked lists no requieren que los datos estén almacenados en posiciones contiguas de memoria. Esto las hace más flexibles que muchas otras estructuras.
{: .prompt-info }

### Términos básicos sobre Linked Lists

- **Nodo**: Unidad básica que contiene un dato y una referencia al siguiente nodo.
- **Head**: Primer nodo de la lista. Desde aquí empieza el recorrido.
- **Null (o None)**: Valor especial que indica el final de la lista (cuando un nodo no apunta a ningún otro).

---

## 🧩 Tipos de Linked Lists

Las **linked lists** pueden adoptar varias formas, dependiendo de cómo se conectan sus nodos. A continuación, los tipos más comunes:

### Lista Enlazada Simple (Singly Linked List)

Cada nodo contiene un dato y un puntero al **siguiente nodo**. Solo se puede recorrer hacia adelante.

- ✅ **Ventajas**: Más ligera en memoria que otras variantes.
- ⚠️ **Inconvenientes**: No se puede recorrer hacia atrás; requiere más tiempo si necesitas insertar al final.

> La estructura básica de una lista enlazada simple es ideal para pilas, colas y listas de tareas.
{: .prompt-tip }

### Lista Doblemente Enlazada (Doubly Linked List)

Cada nodo tiene dos punteros: uno al siguiente nodo y otro al anterior. Esto permite recorrer la lista **en ambas direcciones**.

- ✅ **Ventajas**: Navegación fácil en ambos sentidos.
- ⚠️ **Inconvenientes**: Ocupa más memoria y requiere cuidado adicional al insertar o eliminar nodos.

> Si necesitas recorrer los datos hacia adelante y hacia atrás con frecuencia, una lista doble es una gran opción.
{: .prompt-info }

### Lista Circular

En este tipo, el último nodo **no apunta a null**, sino que enlaza de nuevo con el primero, formando un ciclo cerrado.

- ✅ **Ventajas**: No hay "final", útil para estructuras que se reinician como relojes o buffers.
- ⚠️ **Inconvenientes**: Hay que tener cuidado con bucles infinitos al recorrerla.

> Una lista circular requiere lógica especial para detener el recorrido, ya que nunca termina de forma natural.
{: .prompt-warning }

---

## ⚙️ Operaciones con Linked Lists

Las linked lists permiten realizar operaciones comunes como insertar, borrar, buscar y recorrer nodos. A continuación, te explico cada una de ellas con claridad y ejemplos conceptuales.

### 1️⃣ Recorrido

El **recorrido** consiste en visitar cada nodo, de principio a fin, accediendo a sus datos y moviéndonos mediante sus punteros.

#### 🧠 ¿Cómo funciona?

1. Se empieza desde el nodo `head`.
2. Se accede al dato del nodo actual.
3. Se sigue el puntero al siguiente nodo.
4. Se repite el proceso hasta llegar a `null`.

> El recorrido es esencial para imprimir, buscar valores o procesar cada nodo.
{: .prompt-tip }

**Complejidad temporal:** O(n)

---

### 2️⃣ Inserción

Insertar significa **agregar un nuevo nodo** en algún punto de la lista.

#### 📌 Lugares donde se puede insertar

- **Al inicio** (antes del head)
- **En medio** (después de un nodo específico)
- **Al final** (cuando `siguiente` es `null`)

#### 🧠 ¿Cómo funciona?

- Se crea un nodo nuevo.
- Se ajustan los punteros para que se enlace correctamente con los nodos adyacentes.

> Es importante enlazar correctamente el nodo anterior y el nuevo para no perder referencias en listas dobles o circulares.
{: .prompt-warning }

**Complejidad temporal:**  
- Al inicio: O(1)  
- Al final o en medio: O(n)

---

### 3️⃣ Borrado

La **eliminación** consiste en quitar un nodo específico y ajustar los punteros para mantener la continuidad de la lista.

#### 🧠 ¿Cómo funciona?

1. Se busca el nodo anterior al que se quiere eliminar.
2. Se ajusta su puntero para que salte el nodo eliminado.
3. Se libera la memoria del nodo (en lenguajes como C/C++).

#### 📌 Tipos de borrado

- **Por posición**
- **Por valor**
- **Al inicio o final**

> Si no actualizas correctamente los enlaces al borrar un nodo, puedes perder acceso al resto de la lista.
{: .prompt-warning }

**Complejidad temporal:** O(n)

---

### 4️⃣ Búsqueda

La **búsqueda** consiste en recorrer la lista nodo por nodo hasta encontrar el dato deseado.

#### 🔍 Tipos de búsqueda

- **Por valor**: se compara el dato de cada nodo.
- **Por referencia**: se busca un nodo específico si tienes su dirección o puntero.

> La búsqueda en listas enlazadas no permite acceso directo, así que siempre es lineal.
{: .prompt-info }

**Complejidad temporal:** O(n)

---

### 5️⃣ Actualización

La **actualización** significa cambiar el dato contenido en un nodo ya existente.

#### 🧠 ¿Cómo funciona?

1. Se recorre la lista hasta llegar al nodo deseado.
2. Se modifica el valor del campo `dato`.

> La actualización es eficiente si ya conoces la posición del nodo.
{: .prompt-tip }

**Complejidad temporal:** O(n)

---

## 📊 Resumen de Complejidad Temporal en Operaciones con Linked Lists

| Operación               | Descripción breve                   | Complejidad Temporal |
| ----------------------- | ----------------------------------- | -------------------- |
| Recorrido               | Acceder a cada nodo desde el `head` | O(n)                 |
| Inserción (inicio)      | Agregar al principio                | O(1)                 |
| Inserción (final/medio) | Requiere recorrido previo           | O(n)                 |
| Borrado                 | Eliminar nodo y re-enlazar          | O(n)                 |
| Búsqueda                | Comparar uno a uno                  | O(n)                 |
| Actualización           | Cambiar dato de un nodo existente   | O(n)                 |

> Aunque muchas operaciones son lineales, su ventaja radica en que no requieren mover bloques de memoria como en los arrays.
{: .prompt-info }

---

## 💻 Implementación en C++ para Linked Lists

> Recuerda liberar la memoria de los nodos eliminados usando `delete` para evitar fugas. En estructuras dinámicas como las listas enlazadas, cada nodo se reserva manualmente.
{: .prompt-warning }

```cpp
#include <iostream>
using namespace std;

struct Nodo {
    int dato;
    Nodo* siguiente;
};

// Inserta un nodo al inicio de la lista
void insertarInicio(Nodo*& cabeza, int valor) {
    Nodo* nuevo = new Nodo{valor, cabeza};
    cabeza = nuevo;
}

// Recorre la lista e imprime sus valores
void recorrer(Nodo* cabeza) {
    while (cabeza != nullptr) {
        cout << cabeza->dato << " → ";
        cabeza = cabeza->siguiente;
    }
    cout << "null" << endl;
}

// Elimina el primer nodo que contenga el valor dado
void eliminarPorValor(Nodo*& cabeza, int valor) {
    if (!cabeza) return;

    if (cabeza->dato == valor) {
        Nodo* temp = cabeza;
        cabeza = cabeza->siguiente;
        delete temp;
        return;
    }

    Nodo* actual = cabeza;
    while (actual->siguiente && actual->siguiente->dato != valor) {
        actual = actual->siguiente;
    }

    if (actual->siguiente) {
        Nodo* temp = actual->siguiente;
        actual->siguiente = temp->siguiente;
        delete temp;
    }
}

// Busca un valor en la lista y devuelve un puntero al nodo
Nodo* buscar(Nodo* cabeza, int valor) {
    while (cabeza) {
        if (cabeza->dato == valor) return cabeza;
        cabeza = cabeza->siguiente;
    }
    return nullptr;
}

// Actualiza el valor del primer nodo que contenga un dato específico
void actualizar(Nodo* cabeza, int valorAnterior, int nuevoValor) {
    Nodo* nodo = buscar(cabeza, valorAnterior);
    if (nodo) nodo->dato = nuevoValor;
}

int main() {
    Nodo* lista = nullptr;

    insertarInicio(lista, 30);
    insertarInicio(lista, 20);
    insertarInicio(lista, 10);

    cout << "Lista inicial:
";
    recorrer(lista);

    cout << "Eliminar 20:
";
    eliminarPorValor(lista, 20);
    recorrer(lista);

    cout << "Actualizar 30 a 99:
";
    actualizar(lista, 30, 99);
    recorrer(lista);

    return 0;
}
```

---

## 💻 Implementación en Python

En Python, las listas (`list`) funcionan como arrays dinámicos. Son muy flexibles y permiten realizar todas las operaciones que hemos visto: insertar, eliminar, buscar, actualizar, etc.

A continuación, te muestro cómo crear listas de diferentes formas y cómo aplicar todas las operaciones fundamentales.

> Aprovecha que las listas de Python soportan slicing (`arr[1:4]`) para acceder a subconjuntos de datos de forma rápida y elegante.
{: .prompt-tip }

### 📦 Creación de listas

```python
# Crear una lista de tamaño fijo (rellena con ceros)
arr = [0] * 5

# Mostrar la lista fija
print(arr)  # [0, 0, 0, 0, 0]

# Crear una lista dinámica (vacía)
arr = []

# Agregar elementos dinámicamente
arr.append(1)
arr.append(2)
print(arr)  # [1, 2]

# Lista de ejemplo
arr = [10, 20, 30, 40, 50]

# Recorrido
print("Recorrido:")
for elemento in arr:
    print(elemento, end=" ")
print()

# Inserción
# Insertar en una posición específica
arr.insert(2, 25)  # Inserta 25 en la posición 2
print("Después de insertar 25 en la posición 2:", arr)

# Inserción al final
arr.append(60)
print("Después de insertar 60 al final:", arr)

# Borrado
# Borrar por índice
arr.pop(3)  # Elimina el elemento en la posición 3
print("Después de borrar el elemento en la posición 3:", arr)

# Borrar por valor
arr.remove(25)  # Elimina el valor 25 (si existe)
print("Después de eliminar el valor 25:", arr)

# Actualización
arr[1] = 99  # Cambia el valor en la posición 1
print("Después de actualizar el índice 1 a 99:", arr)

# Búsqueda lineal
valor = 40
if valor in arr:
    print(f"{valor} encontrado en el índice {arr.index(valor)}")
else:
    print(f"{valor} no está en la lista")

# Búsqueda binaria (requiere lista ordenada)
import bisect

arr.sort()  # Aseguramos que esté ordenada
valor = 99
pos = bisect.bisect_left(arr, valor)
if pos < len(arr) and arr[pos] == valor:
    print(f"{valor} encontrado en el índice {pos} (búsqueda binaria)")
else:
    print(f"{valor} no encontrado (búsqueda binaria)")
```

---

## 💬 ¿Te ha servido este contenido?

Si te ha ayudado a entender mejor las linked lists, ¡déjame un comentario!  
Cuéntame qué parte te pareció más clara o qué tema quieres que explore en el próximo post. 🚀

---

🗨️ "Para poder avanzar, tienes que dejar algo atrás." — Interestelar (2014)