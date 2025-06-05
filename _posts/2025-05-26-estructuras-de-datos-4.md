---
title: "🚦 Queues (Colas)"
date: 2025-05-26
layout: post
categories: [Programación, Estructuras de Datos]
tags: [C++, Python]
description: "Aprende qué es una cola (queue), cómo funciona su estructura FIFO, y cómo implementar operaciones como enqueue, dequeue y peek con ejemplos prácticos en C++ y Python."
author: gabriel
---

## 🚦 Queues (Colas)

> **¿Por qué aprender Queues?**

Las **colas (queues)** son estructuras de datos esenciales que siguen el principio **FIFO** (*First In, First Out*), es decir, el **primer elemento que entra es el primero en salir**. Este comportamiento refleja muchos procesos reales: desde las colas en una tienda hasta la gestión de tareas en sistemas operativos o el envío de datos en redes.

Dominar cómo funcionan las colas te permitirá implementar soluciones más ordenadas y eficientes en áreas como:

- Sistemas de impresión
- Procesamiento de tareas en segundo plano
- Algoritmos de búsqueda en grafos
- Comunicaciones en redes

---

## 📘 ¿Qué es una Queue?

Una **queue** (o cola) es una estructura de datos lineal que sigue el principio **FIFO** (*First In, First Out*), lo que significa que el **primer elemento que entra es el primero que sale**.

Puedes imaginarla como una fila de personas esperando en una tienda: el primero en llegar es el primero en ser atendido. En programación, este comportamiento es ideal cuando se necesita procesar elementos en el orden en que fueron recibidos.

> Las colas son ampliamente utilizadas en programación concurrente, gestión de tareas, redes, sistemas operativos y algoritmos como la búsqueda en anchura (BFS).
{: .prompt-info }

### Términos básicos sobre Queues

- **Front (Frente)**: Es el extremo desde donde se elimina el primer elemento de la cola.
- **Rear (Final)**: Es el extremo donde se insertan nuevos elementos.
- **Enqueue**: Operación que **inserta** un nuevo elemento al final de la cola.
- **Dequeue**: Operación que **elimina** el elemento que está al frente.
- **Peek (o Front)**: Permite ver el primer elemento sin retirarlo.
- **isEmpty**: Verifica si la cola está vacía.

---

## 🧩 Tipos de Queues

Dependiendo del contexto y de las necesidades del programa, existen diferentes variantes de colas. A continuación, te presento las más comunes:

### Cola Lineal (Linear Queue)

Es la forma más básica de cola. Los elementos se insertan al final y se eliminan desde el frente. Sin embargo, si no se gestiona adecuadamente, puede haber desperdicio de espacio cuando se realizan muchas operaciones `dequeue`.

- ✅ **Ventajas**: Simple de implementar.
- ⚠️ **Inconvenientes**: El espacio al inicio puede quedar inutilizado si no se reinicializa correctamente el puntero del frente.

### Cola Circular (Circular Queue)

En una cola circular, el último elemento está conectado al primero, formando un ciclo. Esto permite reutilizar las posiciones liberadas por operaciones `dequeue`.

- ✅ **Ventajas**: Aprovecha mejor el espacio de memoria.
- ⚠️ **Inconvenientes**: La lógica para detectar cola llena o vacía es más compleja.

> Las colas circulares son muy utilizadas en buffers de audio, controladores de dispositivos o redes.
{: .prompt-tip }

### Cola de Prioridad (Priority Queue)

En lugar de seguir estrictamente el orden de llegada, cada elemento tiene una **prioridad**. El elemento con la mayor prioridad se atiende primero, sin importar cuándo llegó.

- ✅ **Ventajas**: Ideal para sistemas donde ciertas tareas deben atenderse antes que otras (como en sistemas operativos).
- ⚠️ **Inconvenientes**: Insertar elementos puede requerir ordenamiento.

> En C++ puedes usar `std::priority_queue` y en Python `heapq` para implementar este tipo de colas.
{: .prompt-info }

### Cola Doble (Deque - Double Ended Queue)

Permite **insertar y eliminar elementos desde ambos extremos** (inicio y final).

- ✅ **Ventajas**: Muy flexible. Puede comportarse como cola o como pila.
- ⚠️ **Inconvenientes**: Mayor complejidad en la implementación si se hace desde cero.

> En Python, el módulo `collections.deque` implementa esta estructura de forma muy eficiente.
{: .prompt-tip }

---

## ⚙️ Operaciones con Queues

Las **queues** permiten realizar operaciones simples y eficientes para manejar elementos en orden de llegada. Estas son las principales:

### 1️⃣ Enqueue

La operación **enqueue** agrega un nuevo elemento **al final** de la cola.

#### 🧠 ¿Cómo funciona?

1. Se coloca el nuevo elemento en la posición `rear`.
2. Se actualiza el puntero `rear` (final de la cola).

> En una cola de tamaño fijo, asegúrate de no superar la capacidad máxima. Si se llena, puedes necesitar usar una cola circular o redimensionarla dinámicamente.
{: .prompt-warning }

**Complejidad temporal:** O(1)

---

### 2️⃣ Dequeue

La operación **dequeue** elimina el **primer elemento** de la cola (el que está en el frente).

#### 🧠 ¿Cómo funciona?

1. Se accede al valor en la posición `front`.
2. Se elimina ese valor.
3. Se actualiza el puntero `front` para apuntar al siguiente elemento.

> Si haces `dequeue` sobre una cola vacía, deberías manejar el error adecuadamente o lanzar una excepción.
{: .prompt-danger }

**Complejidad temporal:** O(1)

---

### 3️⃣ Peek (o Front)

Permite **ver el primer elemento** sin eliminarlo, útil para saber qué se va a procesar a continuación.

**Complejidad temporal:** O(1)

---

### 4️⃣ isEmpty

Verifica si la cola no contiene ningún elemento.

**Complejidad temporal:** O(1)

---

## 📊 Resumen de Complejidad Temporal en Operaciones con Queues

| Operación  | Descripción breve               | Complejidad Temporal |
| ---------- | ------------------------------- | -------------------- |
| Enqueue    | Agregar elemento al final       | O(1)                 |
| Dequeue    | Eliminar elemento del frente    | O(1)                 |
| Peek/Front | Ver el primer elemento          | O(1)                 |
| isEmpty    | Comprobar si la cola está vacía | O(1)                 |

> Las queues son ideales para sistemas de gestión de tareas, algoritmos de búsqueda en anchura (BFS), programación concurrente, y estructuras reactivas como los buffers de datos.
{: .prompt-tip }

---

## 💻 Implementación en C++ para Queues

> En C++, puedes usar la clase `std::queue` de la STL, que ofrece una implementación robusta y eficiente basada en el contenedor `deque` por defecto.
{: .prompt-info }

```cpp
#include <iostream>
#include <queue>
using namespace std;

int main() {
    queue<int> q;

    // Insertar elementos (enqueue)
    q.push(10);
    q.push(20);
    q.push(30);

    // Mostrar el elemento del frente (peek)
    cout << "Elemento en el frente: " << q.front() << endl; // 10

    // Eliminar el primer elemento (dequeue)
    q.pop();

    // Nuevo frente
    cout << "Nuevo frente tras pop: " << q.front() << endl; // 20

    // Verificar si la cola está vacía
    if (q.empty()) {
        cout << "La cola está vacía" << endl;
    } else {
        cout << "La cola NO está vacía" << endl;
    }

    // Tamaño de la cola
    cout << "Tamaño actual de la cola: " << q.size() << endl;

    return 0;
}
```

### ✅ Métodos principales de `std::queue`

| Método    | Descripción                                  |
| --------- | -------------------------------------------- |
| `push(x)` | Inserta un elemento al final de la cola      |
| `pop()`   | Elimina el elemento del frente               |
| `front()` | Devuelve el primer elemento                  |
| `back()`  | Devuelve el último elemento                  |
| `empty()` | Devuelve `true` si la cola está vacía        |
| `size()`  | Devuelve la cantidad de elementos en la cola |

> Si necesitas acceder directamente a ambos extremos o realizar inserciones rápidas desde el inicio, considera usar `std::deque` directamente o un `std::priority_queue` si quieres ordenar por prioridad.
{: .prompt-tip }

---

## 🐍 Implementación en Python para Queues

Python ofrece varias formas de implementar colas, cada una adecuada para diferentes contextos:

---

### 📦 Usando `collections.deque`

El módulo `collections` proporciona la clase `deque`, que permite operaciones eficientes de inserción y eliminación en ambos extremos de la cola.

```python
from collections import deque

# Crear una cola vacía
cola = deque()

# Insertar elementos (enqueue)
cola.append('a')
cola.append('b')
cola.append('c')

print("Cola inicial:")
print(cola)

# Eliminar elementos (dequeue)
print("\nElementos eliminados de la cola:")
print(cola.popleft())
print(cola.popleft())
print(cola.popleft())

print("\nCola después de eliminar elementos:")
print(cola)
```

**Ventajas:**

- Operaciones `append()` y `popleft()` en tiempo O(1).
- Ideal para aplicaciones donde se requieren inserciones y eliminaciones rápidas en ambos extremos.

---

### 🧰 Usando `queue.Queue`

El módulo `queue` proporciona una clase `Queue` que es segura para subprocesos, lo que la hace adecuada para aplicaciones multihilo.

```python
from queue import Queue

# Crear una cola vacía
cola = Queue()

# Insertar elementos (enqueue)
cola.put('a')
cola.put('b')
cola.put('c')

print("Cola inicial:")
print(list(cola.queue))

# Eliminar elementos (dequeue)
print("\nElementos eliminados de la cola:")
print(cola.get())
print(cola.get())
print(cola.get())

print("\n¿La cola está vacía?:", cola.empty())
```

**Ventajas:**

- Seguridad en entornos multihilo.
- Métodos `put()` y `get()` para insertar y eliminar elementos.

---

> **Recomendación:** Para la mayoría de las aplicaciones, especialmente aquellas que no requieren seguridad en subprocesos, se recomienda usar `collections.deque` debido a su eficiencia en operaciones de cola.
{: .prompt-tip }

---

## 💬 ¿Te ha servido este contenido?

Si este post te ha ayudado a entender mejor cómo funcionan las **queues**, ¡déjame un comentario!  
Cuéntame qué parte te pareció más clara o qué estructura te gustaría que abordemos en el próximo artículo. 🚀

---

🗨️ “No puedes saltarte la cola. Así no funciona.”
— **TVA Agent, Loki (2021, Marvel)**
