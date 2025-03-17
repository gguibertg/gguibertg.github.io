---
title: "Arrays, Listas, Pilas y Colas"
date: 2025-03-17
categories: [Programación, Estructuras de Datos]
tags: [C++, Python]
---

# Arrays, Listas, Pilas y Colas

Las estructuras de datos son fundamentales en la programación. En este artículo exploraremos **arrays, listas, pilas y colas**, sus operaciones principales, ejemplos en **C++ y Python**, sus casos de uso y su complejidad temporal.

## 1. Arrays

### Descripción
Un **array** es una estructura de datos que almacena elementos del mismo tipo en posiciones contiguas de memoria.


> 💡 **Información útil**  
> Los arrays permiten acceso aleatorio en tiempo constante (O(1)), pero su tamaño es fijo en la mayoría de los lenguajes y modificar su tamaño puede ser costoso.  
{: .prompt-info }

### Operaciones principales
- Acceso por índice: O(1)
- Inserción: O(n) en el peor caso (cuando hay que desplazar elementos)
- Eliminación: O(n) en el peor caso
- Búsqueda: O(n) en el peor caso

### Ejemplo en C++
```cpp
#include <iostream>
using namespace std;

int main() {
    // Definición de un array de tamaño 5
    int arr[5] = {1, 2, 3, 4, 5};
    
    // Acceso a un elemento del array por su índice
    cout << "Elemento en la posición 2: " << arr[2] << endl;
    
    return 0;
}
```

### Ejemplo en Python
```python
# Importación de la librería array
import array

# Definición de un array de enteros
arr = array.array('i', [1, 2, 3, 4, 5])

# Acceso a un elemento del array por su índice
print("Elemento en la posición 2:", arr[2])
```

### Casos de uso
- Uso en algoritmos numéricos
- Representación de matrices
- Implementación de buffers

## 2. Listas

### Descripción
Una **lista enlazada** es una colección de nodos donde cada nodo contiene un valor y un puntero al siguiente nodo.

> 💡 **Dato clave**  
> A diferencia de los arrays, las listas enlazadas pueden crecer dinámicamente sin preocuparse por el tamaño inicial.  
{: .prompt-info }

### Operaciones principales
- Inserción: O(1) al inicio, O(n) en posición arbitraria
- Eliminación: O(1) en la cabeza, O(n) en posición arbitraria
- Búsqueda: O(n)

### Ejemplo en C++ con `<list>`
```cpp
#include <iostream>
#include <list>

using namespace std;

int main() {
    // Definición de una lista enlazada
    list<int> linkedList;
    
    // Insertar elementos al final de la lista
    linkedList.push_back(10);
    linkedList.push_back(20);
    
    // Insertar un elemento al inicio de la lista
    linkedList.push_front(5);
    
    // Mostrar los elementos de la lista
    for (int val : linkedList) {
        cout << val << " ";
    }
    
    return 0;
}
```

### Ejemplo en Python con `collections.deque`
```python
from collections import deque

# Creación de una lista enlazada con deque
linked_list = deque()

# Insertar elementos al final de la lista
linked_list.append(10)
linked_list.append(20)

# Insertar un elemento al inicio de la lista
linked_list.appendleft(5)

# Mostrar los elementos de la lista
print(list(linked_list))  
```

### Casos de uso
- Implementación de tablas hash
- Gestión de memoria en sistemas operativos
- Representación de grafos

## 3. Pilas (Stack)

### Descripción
Una **pila** sigue el principio **LIFO (Last In, First Out)**.

> ⚠️ **Importante**  
> Usar una lista para implementar una pila en Python puede ser ineficiente. Se recomienda `collections.deque`.  
{: .prompt-warning }

### Operaciones principales
- Push (insertar): O(1)
- Pop (extraer): O(1)
- Peek (observar el tope): O(1)

### Ejemplo en C++
```cpp
#include <iostream>
#include <stack>
using namespace std;

int main() {
    // Definición de una pila
    stack<int> s;
    
    // Insertar un elemento en la pila
    s.push(10);
    
    // Obtener el elemento en la cima de la pila
    cout << "Elemento en la cima: " << s.top() << endl;
    
    return 0;
}
```

### Ejemplo en Python
```python
from collections import deque

# Creación de una pila con deque
stack = deque()

# Insertar un elemento en la pila
stack.append(10)

# Obtener el elemento en la cima de la pila
print("Elemento en la cima:", stack[-1])
```

### Casos de uso
- Implementación de recursión
- Gestión de llamadas a funciones
- Deshacer/rehacer en editores de texto

## 4. Colas (Queue)

### Descripción
Una **cola** sigue el principio **FIFO (First In, First Out)**.

> 🔹 **Diferencia clave**  
> Mientras que en una pila el último en entrar es el primero en salir, en una cola el primero en entrar es el primero en salir.  
{: .prompt-tip }

### Operaciones principales
- Enqueue (insertar): O(1)
- Dequeue (extraer): O(1)
- Front (observar el primer elemento): O(1)

### Ejemplo en C++
```cpp
#include <iostream>
#include <queue>
using namespace std;

int main() {
    // Definición de una cola
    queue<int> q;
    
    // Insertar un elemento en la cola
    q.push(10);
    
    // Obtener el primer elemento de la cola
    cout << "Primer elemento: " << q.front() << endl;
    
    return 0;
}
```

### Ejemplo en Python
```python
from collections import deque

# Creación de una cola con deque
queue = deque()

# Insertar un elemento en la cola
queue.append(10)

# Obtener el primer elemento de la cola
print("Primer elemento:", queue[0])
```

### Casos de uso
- Gestión de procesos en sistemas operativos
- Algoritmos de búsqueda en grafos (BFS)
- Sistemas de impresión

## 5. Comparativa

| Estructura | Acceso | Inserción      | Eliminación    | Búsqueda | Uso Principal             |
| ---------- | ------ | -------------- | -------------- | -------- | ------------------------- |
| **Array**  | O(1)   | O(n)           | O(n)           | O(n)     | Almacenamiento secuencial |
| **Lista**  | O(n)   | O(1) al inicio | O(1) al inicio | O(n)     | Estructura flexible       |
| **Pila**   | O(n)   | O(1)           | O(1)           | O(n)     | Manejo LIFO               |
| **Cola**   | O(n)   | O(1)           | O(1)           | O(n)     | Manejo FIFO               |

> 🔹 **FIFO vs LIFO**  
> - **LIFO (Last In, First Out):** En una pila, el último elemento insertado es el primero en salir, como una pila de platos.  
> - **FIFO (First In, First Out):** En una cola, el primer elemento insertado es el primero en salir, como una fila en un supermercado.  
{: .prompt-tip }

> 🚨 **Advertencia**  
> Elegir una estructura de datos incorrecta puede impactar drásticamente el rendimiento de tu aplicación.  
{: .prompt-danger }

## Conclusión
Cada estructura de datos tiene sus ventajas y desventajas. Si se necesita **acceso rápido**, los arrays son la mejor opción. Para **inserciones y eliminaciones rápidas**, las listas enlazadas son más eficientes. Si el problema es de tipo **LIFO**, una pila es ideal, y si es **FIFO**, una cola es la mejor elección.

> "Cuando haces las cosas bien, la gente no está segura de si realmente hiciste algo." – Dios, Futurama