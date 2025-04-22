---
title: "🧮 Arrays"
date: 2025-04-21
layout: post
categories: [Programación, Estructuras de Datos]
tags: [C++, Python]
description: "Aprende qué es un array, los distintos tipos (estáticos, dinámicos, multidimensionales) y cómo realizar operaciones básicas como recorrido, inserción, borrado, búsqueda y actualización, con ejemplos prácticos en C++ y Python."
author: gabriel
---

# 🧮 Arrays

> **¿Por qué aprender Arrays?**

Los arrays son fundamentales en programación porque permiten organizar grandes volúmenes de datos de manera eficiente. Ya sea para analizar información, construir juegos o procesar imágenes, saber manipular arrays te abrirá la puerta a resolver problemas reales con elegancia y velocidad.

---

## 📘 ¿Qué es un Array?

Un **array** es una estructura de datos que almacena una colección de elementos del mismo tipo, organizados en ubicaciones de memoria contiguas. Es una de las estructuras más simples y utilizadas en la programación.

> Los arrays también se conocen como vectores en algunos lenguajes (como C++). Aunque el concepto es el mismo, el nombre puede variar.
{: .prompt-info }

### Términos básicos sobre Arrays

- **Índice del array**: Cada elemento dentro de un array se identifica por su **índice**, el cual comienza desde **0**. Por ejemplo, el primer elemento está en la posición 0, el segundo en la posición 1, y así sucesivamente.
- **Elemento del array**: Son los valores o datos que se almacenan dentro del array. Puedes acceder a cada uno utilizando su índice.
- **Longitud del array**: Es la cantidad total de elementos que puede contener un array. Esta longitud puede estar fija desde el momento en que se declara (dependiendo del lenguaje de programación).

---

## 🧩 Tipos de Arrays

Los **arrays** permiten almacenar múltiples valores bajo un mismo nombre. Dependiendo de cómo se comportan y se organizan, podemos clasificarlos en diferentes tipos. Aquí te explico los más comunes, desde lo más básico:

### Array Estático

Un **array estático** tiene un tamaño fijo, es decir, la cantidad de elementos que puede almacenar se define **desde el principio** y **no se puede cambiar** durante la ejecución del programa.

- ✅ **Ventajas**: Simples de usar, más rápidos y consumen menos recursos.
- ⚠️ **Inconvenientes**: Si el array es demasiado grande y usas pocos elementos, desperdicias memoria. Si es demasiado pequeño, no podrás guardar todos los datos que necesitas.

> Si usas un array estático en un lenguaje como C o C++, asegúrate de no acceder fuera de los límites definidos; esto puede provocar errores graves o comportamientos inesperados.
> Además, si reservas espacio para 10 números pero solo usas 3, estarás desperdiciando memoria innecesariamente. Este tipo de ineficiencia es una desventaja típica de los arrays estáticos.
{: .prompt-warning }

### Array Dinámico

Un **array dinámico** puede **cambiar de tamaño durante la ejecución del programa**, lo que lo hace mucho más flexible.

- ✅ **Ventajas**: Puedes añadir o eliminar elementos según lo necesites, sin preocuparte por el tamaño inicial.
- ⚠️ **Inconvenientes**: A veces pueden ser un poco más lentos, ya que se necesita gestionar la memoria de forma dinámica.

> Usa estructuras como `list` en Python o `vector` en C++ cuando necesites agregar o eliminar elementos sin saber cuántos necesitarás desde el principio.
{: .prompt-tip }

> En muchos lenguajes de programación modernos (como Python con listas, o JavaScript con arrays), los arrays que usamos son dinámicos por defecto.
{: .prompt-info }

### Matriz (Array Multidimensional)

Una **matriz** es un tipo especial de array donde los datos están organizados en **dos o más dimensiones**. La más común es la **matriz 2D**, que puedes imaginar como una tabla con **filas y columnas**.

- ✅ **Ideal** para representar datos como tableros de juegos, imágenes, o tablas numéricas.
- 📐 También existen matrices 3D o de más dimensiones, pero no son tan comunes en el día a día.

> En Python, las matrices reales no existen por defecto, pero puedes usar listas de listas o bibliotecas como `numpy` para trabajar con estructuras multidimensionales.
{: .prompt-info }

---

## ⚙️ Operaciones con Arrays

Los arrays no solo se utilizan para almacenar datos, también permiten realizar una variedad de operaciones fundamentales que encontrarás en prácticamente cualquier programa. A continuación, un repaso de las más importantes:

### 1️⃣ Recorrido 

El **recorrido** de un array se refiere al proceso de **acceder y procesar cada uno de sus elementos**, normalmente en orden. Es una de las operaciones más comunes en programación.

#### 🧠 ¿Cómo funciona?

Cuando se crea un array, sus elementos se almacenan en posiciones de memoria contiguas. Cada uno tiene un **índice**, que suele empezar en `0`. Para recorrerlo, se suele usar un bucle que va del primer al último índice (o al revés).

#### 🔄 Tipos de recorrido

- **Recorrido Secuencial (o Lineal)**  
  Desde el primer elemento hasta el último.  
  Se usa para imprimir, buscar, o hacer cálculos como sumas o promedios.  
  **Complejidad temporal:** O(n)

- **Recorrido Inverso**  
  Desde el último elemento hasta el primero.  
  Útil cuando se quiere procesar los elementos "de atrás hacia adelante".  
  **Complejidad temporal:** O(n)

### 2️⃣ Inserción

La **inserción** consiste en **agregar un nuevo elemento** en una posición específica del array, manteniendo el orden del resto.

#### 🧠 ¿Cómo funciona?

1. Se determina **dónde** insertar el nuevo valor.
2. Se **desplazan** los elementos hacia la derecha para hacer espacio.
3. Se **inserta** el nuevo valor.
4. Si el array es dinámico, se actualiza su tamaño automáticamente.

#### 📌 Tipos de inserción

- **Al inicio (índice 0):**  
  Todos los elementos deben desplazarse.  
  **Complejidad temporal:** O(n)

- **En un índice específico:**  
  Solo se desplazan los elementos desde ese índice hacia la derecha.  
  **Complejidad temporal:** O(n)

- **Al final:**  
  No requiere desplazamiento si hay espacio disponible (en arrays dinámicos).  
  **Complejidad temporal:** O(1) en arrays dinámicos (amortizada)

### 3️⃣ Borrado 

El **borrado** consiste en **quitar un elemento** del array en una posición específica, y reorganizar el resto para mantener la estructura.

#### 🧠 ¿Cómo funciona?

1. Se identifica el **índice del elemento** a borrar.
2. Se **desplazan** los elementos posteriores hacia la izquierda para llenar el hueco.
3. Si el array es dinámico, se puede reducir su tamaño.

#### 📌 Tipos de borrado

- **Al inicio (índice 0):**  
  Todos los elementos se mueven una posición a la izquierda.  
  **Complejidad temporal:** O(n)

- **En un índice específico:**  
  Solo los elementos posteriores al índice se mueven.  
  **Complejidad temporal:** O(n)

- **Al final:**  
  No se requiere desplazamiento.  
  **Complejidad temporal:** O(1)

### 4️⃣ Búsqueda

La **búsqueda** es el proceso de **encontrar un valor** dentro del array. Puede devolver el índice del elemento o simplemente indicar si está presente.

#### 🔍 Tipos de búsqueda

- **Búsqueda Lineal (o Secuencial):**  
  Se recorre el array elemento por elemento comparando con el valor buscado.  
  Si encuentra el elemento, devuelve el índice.  
  Si no lo encuentra, continúa hasta el final.  
  **Complejidad temporal:** O(n)

- **Búsqueda Binaria**

  Es un método mucho más eficiente, pero **requiere que el array esté ordenado**.  
  Se compara el elemento del centro con el valor buscado y se decide si continuar en la mitad izquierda o derecha.  
  Este proceso se repite hasta encontrar el valor o quedarse sin opciones.  
  **Complejidad temporal:** O(log n)  
  **Nota:** Si el array no está ordenado, esta técnica no funcionará correctamente.

> ¡No uses búsqueda binaria en arrays desordenados! Puede devolverte resultados erróneos o hacer que tu programa falle silenciosamente.
{: .prompt-danger }

> La búsqueda binaria es ideal cuando se realizan muchas búsquedas en un array ordenado, ya que reduce drásticamente el número de comparaciones.
{: .prompt-tip }


### 5️⃣ Actualización en un Array (Array Update)

La **actualización** consiste en **modificar el valor de un elemento existente** en una posición específica del array. Es una operación sencilla y directa.

#### 🧠 ¿Cómo funciona?

Se accede al índice donde se encuentra el elemento y se reemplaza su valor por uno nuevo. No es necesario mover ni reorganizar otros elementos.

#### 🔄 Casos comunes de actualización

- Cambiar un valor temporal por uno definitivo.
- Corregir un dato incorrecto.
- Modificar el estado de un elemento (por ejemplo, marcar algo como "completo").
- 
> Si necesitas actualizar elementos frecuentemente, asegúrate de que tu estructura de datos permita acceso rápido por índice (como un array o lista), para mantener una complejidad de O(1).
{: .prompt-tip }

#### ⏱️ Complejidad temporal

- **Complejidad:** O(1)  
  Como los arrays permiten acceso directo por índice, actualizar un valor es una operación muy rápida.

---

## 📊 Resumen de Complejidad Temporal en Operaciones con Arrays

| Operación          | Descripción breve                                            | Complejidad Temporal |
| ------------------ | ------------------------------------------------------------ | -------------------- |
| Recorrido          | Acceder a todos los elementos del array                      | O(n)                 |
| Inserción (inicio) | Agregar un elemento al principio, desplazando los demás      | O(n)                 |
| Inserción (medio)  | Insertar en una posición específica, desplazando posteriores | O(n)                 |
| Inserción (final)  | Agregar al final (sin desplazamiento en arrays dinámicos)    | O(1) *               |
| Borrado (inicio)   | Eliminar el primer elemento y desplazar el resto             | O(n)                 |
| Borrado (medio)    | Eliminar un elemento en una posición intermedia              | O(n)                 |
| Borrado (final)    | Eliminar el último elemento                                  | O(1)                 |
| Búsqueda lineal    | Buscar elemento uno a uno hasta encontrarlo                  | O(n)                 |
| Búsqueda binaria   | Buscar dividiendo el array en mitades (array ordenado)       | O(log n)             |
| Actualización      | Reemplazar un valor en una posición específica               | O(1)                 |

> En arrays dinámicos como listas en Python o ArrayList en Java, insertar al final suele ser O(1) en promedio (amortizado), aunque ocasionalmente puede ser más si se necesita redimensionar.
{: .prompt-info }

--- 

## 💻 Implementación en C++

> Recuerda liberar la memoria reservada dinámicamente con `delete[]` si usas `new` en C++. Usar `vector` es más seguro y recomendable para evitar fugas de memoria.
{: .prompt-warning }

```cpp
#include <iostream>
#include <vector>
using namespace std;

const int MAX = 100;

// === CREACIÓN DE ARRAYS ===

// Método 1: Array de tamaño fijo (memoria en tiempo de compilación)
int arr1[5]; // Declaración simple
int arr2[5] = {1, 2, 3, 4, 5}; // Declaración + inicialización

// Método 2: Array de tamaño fijo (memoria en tiempo de ejecución)
int* arr3 = new int[5]; // Array dinámico (manual)

// Método 3: Usando vector (array dinámico moderno)
vector<int> v; // Vector vacío

// === FUNCIONES CON ARRAYS ESTÁTICOS ===

void recorrer(int arr[], int n) {
    cout << "Recorrido del array: ";
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";
    cout << endl;
}

void insertar(int arr[], int& n, int valor, int pos) {
    if (n >= MAX || pos < 0 || pos > n) return;

    for (int i = n; i > pos; i--)
        arr[i] = arr[i - 1];

    arr[pos] = valor;
    n++;
}

void borrar(int arr[], int& n, int pos) {
    if (n == 0 || pos < 0 || pos >= n) return;

    for (int i = pos; i < n - 1; i++)
        arr[i] = arr[i + 1];

    n--;
}

void actualizar(int arr[], int pos, int nuevoValor) {
    if (pos < 0 || pos >= MAX) return;

    arr[pos] = nuevoValor;
}

int buscarLineal(int arr[], int n, int valor) {
    for (int i = 0; i < n; i++) {
        if (arr[i] == valor)
            return i;
    }
    return -1;
}

int buscarBinaria(int arr[], int n, int valor) {
    int inicio = 0, fin = n - 1;
    while (inicio <= fin) {
        int medio = (inicio + fin) / 2;
        if (arr[medio] == valor)
            return medio;
        else if (arr[medio] < valor)
            inicio = medio + 1;
        else
            fin = medio - 1;
    }
    return -1;
}

// === PROGRAMA PRINCIPAL ===

int main() {
    int arr[MAX] = {10, 20, 30, 40, 50};
    int n = 5;

    recorrer(arr, n);

    cout << "Insertar 25 en la posición 2:\n";
    insertar(arr, n, 25, 2);
    recorrer(arr, n);

    cout << "Borrar el elemento en la posición 3:\n";
    borrar(arr, n, 3);
    recorrer(arr, n);

    cout << "Actualizar la posición 1 con valor 99:\n";
    actualizar(arr, 1, 99);
    recorrer(arr, n);

    cout << "Buscar 40 con búsqueda lineal: ";
    int posLineal = buscarLineal(arr, n, 40);
    if (posLineal != -1)
        cout << "Encontrado en índice " << posLineal << endl;
    else
        cout << "No encontrado\n";

    cout << "Buscar 25 con búsqueda binaria (requiere array ordenado): ";
    int posBinaria = buscarBinaria(arr, n, 25);
    if (posBinaria != -1)
        cout << "Encontrado en índice " << posBinaria << endl;
    else
        cout << "No encontrado\n";

    // Mostrar uso básico de vector
    cout << "\nVector dinámico (std::vector):\n";
    vector<int> v = {1, 2, 3};
    v.push_back(4); // Inserción
    v[0] = 10;       // Actualización
    for (int x : v)
        cout << x << " ";
    cout << endl;

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

Si te ha ayudado a entender mejor los arrays, ¡déjame un comentario!  
Cuéntame qué parte te pareció más útil o en qué tema te gustaría profundizar en el siguiente post. 🚀

---

> 🗨️ "Cuando haces las cosas bien, la gente no está segura de si realmente hiciste algo." – Dios, Futurama