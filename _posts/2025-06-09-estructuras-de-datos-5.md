---
title: "🌳 Árboles"
date: 2025-06-09
layout: post
categories: [Programación, Estructuras de Datos]
tags: [C++, Python]
description: "Descubre qué es un árbol en programación, los tipos más comunes (binarios, N-arios, AVL, etc.), y cómo se implementan y recorren con ejemplos básicos en C++ y Python."
author: gabriel
---

# 🌳 Árboles (Trees)

> **¿Por qué aprender árboles?**

Los **árboles** son estructuras de datos jerárquicas esenciales para representar relaciones padre-hijo. Se usan en sistemas de archivos, motores de bases de datos, inteligencia artificial, y más. Comprender su lógica te permite modelar datos estructurados y optimizar operaciones como búsqueda, inserción y recorrido.

---

## 📘 ¿Qué es un Árbol?

Un **árbol** es una estructura de datos no lineal compuesta por nodos conectados jerárquicamente. Cada nodo puede tener **cero o más hijos**, y existe un **nodo raíz (root)** desde donde se origina toda la estructura.

> A diferencia de arrays, pilas o colas, los árboles no almacenan los elementos en una secuencia lineal, sino en forma de **estructura jerárquica**.
{: .prompt-info }

### Términos clave

- **Nodo raíz (Root)**: El nodo superior del árbol.
- **Hijo (Child)**: Nodo descendiente de otro.
- **Padre (Parent)**: Nodo del cual desciende otro.
- **Nodo hoja (Leaf)**: Nodo sin hijos.
- **Subárbol**: Cualquier estructura que desciende de un nodo dado.
- **Altura del árbol**: Número máximo de niveles desde la raíz hasta una hoja.

---

## 🧩 Tipos más comunes de Árboles

Los árboles pueden adoptar distintas formas, según cuántos hijos tenga cada nodo y cómo se gestionen los valores. Aquí te presento los tipos más utilizados en programación:

### 🔢 Árbol Binario

Es el tipo más básico. Cada nodo puede tener como máximo **dos hijos**: uno izquierdo y uno derecho.

- ✅ **Ventajas**: Sencillo de implementar, base para estructuras más avanzadas.
- ⚠️ **Inconvenientes**: Si no se gestiona bien, puede volverse muy desequilibrado y perder eficiencia.

> Ideal para representar datos jerárquicos simples, como expresiones matemáticas o decisiones binarias.
{: .prompt-info }

### ⚖️ Árbol Binario de Búsqueda (Binary Search Tree - BST)

Es un árbol binario que **mantiene los valores ordenados**:  
- Los valores **menores** al nodo se colocan a la izquierda.  
- Los **mayores**, a la derecha.

- ✅ **Ventajas**: Permite búsquedas, inserciones y eliminaciones en **O(log n)** (si está equilibrado).
- ⚠️ **Inconvenientes**: Si los datos están ya ordenados, puede degradarse a una lista (O(n)).

> Si necesitas ordenar y buscar datos con frecuencia, un BST bien construido es una herramienta muy potente.
{: .prompt-tip }

### ♻️ Árbol AVL

Es un **árbol binario de búsqueda auto-balanceado**. Tras cada inserción o borrado, ajusta su estructura para que la **diferencia de altura entre subárboles no supere 1**.

- ✅ **Ventajas**: Mantiene siempre la eficiencia de O(log n).
- ⚠️ **Inconvenientes**: Su implementación es más compleja.

> Los árboles AVL evitan que un BST se vuelva lento al desequilibrarse.
{: .prompt-warning }

### 🌲 Árbol N-ario

Cada nodo puede tener **cualquier número de hijos** (no solo dos). Es más flexible que un árbol binario.

- ✅ **Ventajas**: Ideal para representar jerarquías más amplias, como menús, árboles de carpetas o estructuras XML.
- ⚠️ **Inconvenientes**: Las operaciones básicas (como búsqueda) pueden requerir más tiempo y memoria.

> Se usan en procesamiento de lenguaje, compiladores, y estructuras como los árboles sintácticos.
{: .prompt-info }

---

## ⚙️ Operaciones básicas con Árboles

Los árboles permiten representar y organizar datos jerárquicamente. Pero su verdadero poder se revela cuando aprendemos a **manipularlos** mediante operaciones clave como insertar, buscar, eliminar y recorrer.

### 1️⃣ Inserción

Consiste en **agregar un nuevo nodo** al árbol respetando las reglas de su tipo (por ejemplo, en un BST: menor a la izquierda, mayor a la derecha).

#### 🧠 ¿Cómo funciona?

- Se compara el valor con el nodo actual.
- Se decide si ir al subárbol izquierdo o derecho.
- Se repite el proceso hasta encontrar un espacio vacío.

**Complejidad temporal:**  
- O(log n) en árboles balanceados (como AVL)  
- O(n) en el peor caso (árboles desequilibrados)

### 2️⃣ Búsqueda

Recorrer el árbol para **encontrar un valor específico**.

#### 🧠 ¿Cómo funciona?

- Se compara el valor buscado con el nodo actual.
- Si es menor, se explora el subárbol izquierdo; si es mayor, el derecho.
- Se repite hasta encontrar el valor o llegar a un nodo nulo.

**Complejidad temporal:**  
- O(log n) en árboles balanceados  
- O(n) en árboles desequilibrados

> En un árbol binario de búsqueda balanceado, la búsqueda es muy eficiente.
{: .prompt-tip }

### 3️⃣ Eliminación

Quitar un nodo específico del árbol. Existen tres casos:

1. **Nodo hoja** (sin hijos): se elimina directamente.  
2. **Nodo con un hijo**: se reemplaza por su hijo.  
3. **Nodo con dos hijos**: se reemplaza con su sucesor inorden (el menor en su subárbol derecho) o su predecesor.

> La eliminación es la operación más compleja porque puede implicar reorganizar varias conexiones.
{: .prompt-warning }

**Complejidad temporal:**  
- O(log n) en árboles balanceados  
- O(n) en árboles desequilibrados

### 4️⃣ Recorridos (Traversals)

Un recorrido consiste en **visitar todos los nodos** de un árbol en un orden específico. Los principales son:

- **Inorden (Inorder)**: izquierda → nodo → derecha  
  → Útil para imprimir los valores en orden creciente en un BST.

- **Preorden (Preorder)**: nodo → izquierda → derecha  
  → Se usa para copiar árboles o generar expresiones prefijas.

- **Postorden (Postorder)**: izquierda → derecha → nodo  
  → Común en eliminaciones y evaluaciones de expresiones.

- **Por niveles (Level Order)**: se recorre nivel por nivel (usando una cola, BFS)

> Elegir el recorrido adecuado depende del propósito del algoritmo.
{: .prompt-info }

**Complejidad temporal:** O(n) en todos los casos, ya que se visitan todos los nodos.

## 📊 Complejidad Temporal (Resumen)

| Operación   | Árbol Balanceado (AVL, etc.) | Árbol Desequilibrado |
| ----------- | ---------------------------- | -------------------- |
| Inserción   | O(log n)                     | O(n)                 |
| Búsqueda    | O(log n)                     | O(n)                 |
| Eliminación | O(log n)                     | O(n)                 |
| Recorridos  | O(n)                         | O(n)                 |

---

## 💻 Implementación en C++: Recorridos clásicos de un Árbol Binario

> Los árboles pueden recorrerse de distintas formas, dependiendo del orden en que se quieran visitar sus nodos. Aquí te muestro cómo implementar los cuatro recorridos clásicos: inorden, preorden, postorden y por niveles.
{: .prompt-info }

## 💻 Implementación completa en C++: Árbol Binario de Búsqueda (BST)

> Este ejemplo implementa un árbol binario de búsqueda (BST) en C++ con todas las operaciones clave: insertar, buscar, eliminar, actualizar y recorrer en los cuatro órdenes principales.
{: .prompt-info }

```cpp
#include <iostream>
#include <queue>
using namespace std;

// Definición del nodo
struct Nodo {
    int dato;
    Nodo* izq;
    Nodo* der;
};

// Crear nuevo nodo
Nodo* crearNodo(int valor) {
    Nodo* nuevo = new Nodo();
    nuevo->dato = valor;
    nuevo->izq = nullptr;
    nuevo->der = nullptr;
    return nuevo;
}

// Inserción en BST
Nodo* insertar(Nodo* raiz, int valor) {
    if (raiz == nullptr)
        return crearNodo(valor);

    if (valor < raiz->dato)
        raiz->izq = insertar(raiz->izq, valor);
    else
        raiz->der = insertar(raiz->der, valor);

    return raiz;
}

// Búsqueda en BST
bool buscar(Nodo* raiz, int valor) {
    if (raiz == nullptr) return false;
    if (raiz->dato == valor) return true;

    if (valor < raiz->dato)
        return buscar(raiz->izq, valor);
    else
        return buscar(raiz->der, valor);
}

// Encontrar nodo mínimo
Nodo* minimo(Nodo* raiz) {
    while (raiz && raiz->izq != nullptr)
        raiz = raiz->izq;
    return raiz;
}

// Eliminación de un nodo
Nodo* eliminar(Nodo* raiz, int valor) {
    if (raiz == nullptr) return raiz;

    if (valor < raiz->dato)
        raiz->izq = eliminar(raiz->izq, valor);
    else if (valor > raiz->dato)
        raiz->der = eliminar(raiz->der, valor);
    else {
        // Caso 1: sin hijos
        if (raiz->izq == nullptr && raiz->der == nullptr) {
            delete raiz;
            return nullptr;
        }
        // Caso 2: un hijo
        else if (raiz->izq == nullptr) {
            Nodo* temp = raiz->der;
            delete raiz;
            return temp;
        } else if (raiz->der == nullptr) {
            Nodo* temp = raiz->izq;
            delete raiz;
            return temp;
        }
        // Caso 3: dos hijos
        Nodo* sucesor = minimo(raiz->der);
        raiz->dato = sucesor->dato;
        raiz->der = eliminar(raiz->der, sucesor->dato);
    }

    return raiz;
}

// Actualizar un valor: eliminar + insertar nuevo
Nodo* actualizar(Nodo* raiz, int valorAntiguo, int valorNuevo) {
    if (buscar(raiz, valorAntiguo)) {
        raiz = eliminar(raiz, valorAntiguo);
        raiz = insertar(raiz, valorNuevo);
    }
    return raiz;
}

// Recorrido inorden
void inorden(Nodo* raiz) {
    if (raiz != nullptr) {
        inorden(raiz->izq);
        cout << raiz->dato << " ";
        inorden(raiz->der);
    }
}

// Recorrido preorden
void preorden(Nodo* raiz) {
    if (raiz != nullptr) {
        cout << raiz->dato << " ";
        preorden(raiz->izq);
        preorden(raiz->der);
    }
}

// Recorrido postorden
void postorden(Nodo* raiz) {
    if (raiz != nullptr) {
        postorden(raiz->izq);
        postorden(raiz->der);
        cout << raiz->dato << " ";
    }
}

// Recorrido por niveles (BFS)
void porNiveles(Nodo* raiz) {
    if (raiz == nullptr) return;

    queue<Nodo*> q;
    q.push(raiz);

    while (!q.empty()) {
        Nodo* actual = q.front();
        q.pop();
        cout << actual->dato << " ";
        if (actual->izq != nullptr)
            q.push(actual->izq);
        if (actual->der != nullptr)
            q.push(actual->der);
    }
}

int main() {
    Nodo* raiz = nullptr;

    // Insertar valores de ejemplo
    int valores[] = {50, 30, 70, 20, 40, 60, 80};
    for (int valor : valores)
        raiz = insertar(raiz, valor);

    cout << "📌 Recorridos iniciales:\n";
    cout << "Inorden: "; inorden(raiz); cout << endl;
    cout << "Preorden: "; preorden(raiz); cout << endl;
    cout << "Postorden: "; postorden(raiz); cout << endl;
    cout << "Por niveles: "; porNiveles(raiz); cout << endl;

    cout << "\n🔍 ¿Está el valor 40 en el árbol?: ";
    cout << (buscar(raiz, 40) ? "Sí" : "No") << endl;

    cout << "\n🗑️ Eliminamos el nodo con valor 30" << endl;
    raiz = eliminar(raiz, 30);
    cout << "Inorden tras eliminar 30: "; inorden(raiz); cout << endl;

    cout << "\n🔁 Actualizamos el valor 70 → 75" << endl;
    raiz = actualizar(raiz, 70, 75);
    cout << "Inorden tras actualización: "; inorden(raiz); cout << endl;

    return 0;
}
```

---

## 🐍 Implementación completa en Python: Árbol Binario de Búsqueda (BST)

> Este ejemplo en Python implementa un BST con todas las operaciones fundamentales: insertar, buscar, eliminar y recorrer en diferentes órdenes.
{: .prompt-info }

```python
from collections import deque

# Definición del nodo del árbol
class Nodo:
    def __init__(self, dato):
        self.dato = dato
        self.izq = None
        self.der = None

# Inserción en BST
def insertar(raiz, valor):
    if raiz is None:
        return Nodo(valor)
    if valor < raiz.dato:
        raiz.izq = insertar(raiz.izq, valor)
    else:
        raiz.der = insertar(raiz.der, valor)
    return raiz

# Búsqueda en BST
def buscar(raiz, valor):
    if raiz is None:
        return False
    if raiz.dato == valor:
        return True
    if valor < raiz.dato:
        return buscar(raiz.izq, valor)
    else:
        return buscar(raiz.der, valor)

# Mínimo valor (usado en eliminación)
def minimo(raiz):
    actual = raiz
    while actual.izq:
        actual = actual.izq
    return actual

# Eliminación de un nodo
def eliminar(raiz, valor):
    if raiz is None:
        return raiz
    if valor < raiz.dato:
        raiz.izq = eliminar(raiz.izq, valor)
    elif valor > raiz.dato:
        raiz.der = eliminar(raiz.der, valor)
    else:
        if raiz.izq is None:
            return raiz.der
        elif raiz.der is None:
            return raiz.izq
        temp = minimo(raiz.der)
        raiz.dato = temp.dato
        raiz.der = eliminar(raiz.der, temp.dato)
    return raiz

# Actualización de un valor (eliminar e insertar)
def actualizar(raiz, valor_antiguo, valor_nuevo):
    if buscar(raiz, valor_antiguo):
        raiz = eliminar(raiz, valor_antiguo)
        raiz = insertar(raiz, valor_nuevo)
    return raiz

# Recorridos
def inorden(raiz):
    if raiz:
        inorden(raiz.izq)
        print(raiz.dato, end=" ")
        inorden(raiz.der)

def preorden(raiz):
    if raiz:
        print(raiz.dato, end=" ")
        preorden(raiz.izq)
        preorden(raiz.der)

def postorden(raiz):
    if raiz:
        postorden(raiz.izq)
        postorden(raiz.der)
        print(raiz.dato, end=" ")

def por_niveles(raiz):
    if raiz is None:
        return
    cola = deque([raiz])
    while cola:
        actual = cola.popleft()
        print(actual.dato, end=" ")
        if actual.izq:
            cola.append(actual.izq)
        if actual.der:
            cola.append(actual.der)

# Programa principal
if __name__ == "__main__":
    raiz = None
    for v in [50, 30, 70, 20, 40, 60, 80]:
        raiz = insertar(raiz, v)

    print("📌 Recorridos iniciales:")
    print("Inorden: ", end=""); inorden(raiz); print()
    print("Preorden: ", end=""); preorden(raiz); print()
    print("Postorden: ", end=""); postorden(raiz); print()
    print("Por niveles: ", end=""); por_niveles(raiz); print()

    print("\n🔍 ¿Está el valor 40 en el árbol?:", "Sí" if buscar(raiz, 40) else "No")

    print("\n🗑️ Eliminamos el nodo con valor 30")
    raiz = eliminar(raiz, 30)
    print("Inorden tras eliminar 30: ", end=""); inorden(raiz); print()

    print("\n🔁 Actualizamos el valor 70 → 75")
    raiz = actualizar(raiz, 70, 75)
    print("Inorden tras actualización: ", end=""); inorden(raiz); print()
```

---

## 💬 ¿Te ha servido este contenido?

Si este post te ha ayudado a entender mejor cómo funcionan los árboles binarios y por qué son fundamentales en programación, ¡déjame un comentario!  
Puedes contarme qué parte te resultó más útil o qué estructura de datos te gustaría que exploremos en la próxima entrega. 🚀

🗨️ *“Burrárum…”* — **Bárbol, El Señor de los Anillos: Las Dos Torres**
