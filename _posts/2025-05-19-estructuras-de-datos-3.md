---
title: "📚 Pilas (Stacks)"
date: 2025-05-19
layout: post
categories: [Programación, Estructuras de Datos]
tags: [C++, Python]
description: "Descubre qué es una pila (stack), cómo funciona su estructura LIFO, y cómo implementar operaciones como push, pop y peek con ejemplos prácticos en C++ y Python."
author: gabriel
---

# 📚 Stacks

> **¿Por qué aprender Stacks?**

Las **pilas (stacks)** son estructuras de datos fundamentales que siguen una lógica muy natural: el último en entrar es el primero en salir (**LIFO**, por sus siglas en inglés). Desde el historial de tu navegador hasta el control de llamadas a funciones en programación, las pilas están en todas partes. Dominar su funcionamiento te permitirá resolver problemas con mayor claridad, especialmente en algoritmos recursivos, evaluaciones de expresiones o gestión de estados temporales.

---

## 📘 ¿Qué es una Stack?

Un **stack** (o pila) es una estructura de datos lineal que sigue el principio **LIFO** (*Last In, First Out*), lo que significa que el **último elemento que se agrega es el primero en salir**.

Puedes imaginar una pila de platos: solo puedes colocar (push) o retirar (pop) el plato que está en la parte superior. En programación, este comportamiento es ideal para gestionar tareas temporales, controlar el flujo de ejecución o revertir acciones.

> Los stacks son ampliamente utilizados en compiladores, algoritmos recursivos, sistemas de deshacer/rehacer, análisis de expresiones matemáticas y gestión de memoria.
{: .prompt-info }

### Términos básicos sobre Stacks

- **Top (Cima)**: Es el elemento que está en la parte superior de la pila, el único al que se puede acceder directamente.
- **Push**: Operación que añade un nuevo elemento a la cima de la pila.
- **Pop**: Operación que elimina el elemento que está en la cima.
- **Peek (o Top)**: Permite ver cuál es el elemento en la cima sin eliminarlo.
- **isEmpty**: Verifica si la pila está vacía, es decir, si no contiene elementos.

---

## ⚙️ Operaciones con Stacks

Los **stacks** permiten realizar operaciones muy eficientes sobre el elemento que se encuentra en la cima. Todas las interacciones se realizan desde un único extremo, lo que simplifica su comportamiento y lo hace ideal para contextos donde se necesita orden **LIFO**.

### 1️⃣ Push

La operación **push** consiste en **añadir un elemento en la cima de la pila**.

#### 🧠 ¿Cómo funciona?

1. Se incrementa el puntero de la cima.
2. Se almacena el nuevo valor en esa posición.

> Si la pila está implementada con un array de tamaño fijo y está llena, puede producirse un error de desbordamiento (*stack overflow*).
{: .prompt-warning }

**Complejidad temporal:** O(1)

---

### 2️⃣ Pop

La operación **pop** elimina el **elemento que está en la cima** de la pila.

#### 🧠 ¿Cómo funciona?

1. Se accede al valor en la cima.
2. Se disminuye el puntero o índice superior.

> Si intentas hacer `pop` sobre una pila vacía, se produce un error de **underflow**.
{: .prompt-danger }

**Complejidad temporal:** O(1)

---

### 3️⃣ Peek (o Top)

La operación **peek** (también llamada `top`) permite **ver el valor que está en la cima**, sin eliminarlo.

#### 🧠 ¿Cómo funciona?

Simplemente se accede al valor en la posición actual de la cima sin modificar la pila.

**Complejidad temporal:** O(1)

---

### 4️⃣ isEmpty

La operación **isEmpty** devuelve un valor booleano indicando si la pila está vacía.

#### 🧠 ¿Cómo funciona?

Se compara el puntero de la cima con el valor inicial o se verifica la longitud en el caso de estructuras dinámicas.

**Complejidad temporal:** O(1)

---

## 📊 Resumen de Complejidad Temporal en Operaciones con Stacks

| Operación | Descripción breve               | Complejidad Temporal |
| --------- | ------------------------------- | -------------------- |
| Push      | Agregar un elemento a la cima   | O(1)                 |
| Pop       | Eliminar el elemento de la cima | O(1)                 |
| Peek/Top  | Ver el elemento en la cima      | O(1)                 |
| isEmpty   | Verificar si la pila está vacía | O(1)                 |

> Las operaciones en stacks son extremadamente rápidas porque no requieren recorrer ni reorganizar elementos.
{: .prompt-info }

---

## 💻 Implementación en C++ para Stacks

> La STL de C++ incluye la clase `std::stack`, una implementación basada en adaptadores que utiliza por defecto `deque` como contenedor subyacente. Es sencilla de usar y segura para la mayoría de casos de uso.
{: .prompt-info }

```cpp
#include <iostream>
#include <stack> // Importante para usar std::stack
using namespace std;

int main() {
    stack<int> pila;

    // Insertar elementos (push)
    pila.push(10);
    pila.push(20);
    pila.push(30);

    // Mostrar el elemento en la cima
    cout << "Elemento en la cima: " << pila.top() << endl; // 30

    // Eliminar elemento de la cima (pop)
    pila.pop();

    // Ver nueva cima
    cout << "Elemento en la cima tras pop: " << pila.top() << endl; // 20

    // Verificar si está vacía
    if (pila.empty()) {
        cout << "La pila está vacía" << endl;
    } else {
        cout << "La pila NO está vacía" << endl;
    }

    return 0;
}

```

> También puedes usar stack<string> o cualquier otro tipo de dato, siempre que sea compatible con el contenedor subyacente (deque, vector o list).
{: .prompt-tip }

---

## 💻 Implementación en Python para Stacks

Python no tiene una estructura llamada `Stack` como tal, pero podemos usar:

- Listas (`list`) con los métodos `append()` y `pop()`
- `collections.deque` para mayor eficiencia en inserciones y eliminaciones
- `queue.LifoQueue` para uso en entornos multihilo o cuando se necesita sincronización

A continuación, se muestra la implementación más común con `list`:

### 📦 Usando listas (`list`)

```python
# Crear una pila vacía
pila = []

# Agregar elementos (push)
pila.append(10)
pila.append(20)
pila.append(30)

# Ver el elemento en la cima (peek)
print("Elemento en la cima:", pila[-1])  # 30

# Eliminar elemento de la cima (pop)
pila.pop()

# Nueva cima
print("Elemento en la cima tras pop:", pila[-1])  # 20

# Verificar si está vacía
if not pila:
    print("La pila está vacía")
else:
    print("La pila NO está vacía")

```

> Aunque list es la forma más directa de crear una pila, si vas a realizar muchas inserciones y extracciones, es recomendable usar collections.deque, que es más eficiente.
{: .prompt-tip }

---

## 💬 ¿Te ha servido este contenido?

Si te ha ayudado a entender mejor cómo funcionan las stacks, ¡déjame un comentario!  
Cuéntame qué parte te resultó más útil o qué estructura te gustaría ver en el próximo post. 🚀

---

🗨️ "A veces la ciencia es más arte que ciencia, Morty. Mucha gente no lo entiende." — *Rick and Morty* (2017)