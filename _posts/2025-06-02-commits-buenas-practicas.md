---
title: "📝 Buenas Prácticas para Escribir Commits Claros y Efectivos"
date: 2025-06-05
categories: [Programación, Git]
tags: [git, buenas prácticas, commits, control de versiones]
description: "Aprende cómo escribir mensajes de commit que realmente aporten valor al historial de tu proyecto. Mejora la comunicación, el mantenimiento del código y la colaboración en equipo."
author: gabriel
---

# 📝 Buenas Prácticas para Escribir Commits Claros y Efectivos

Si trabajas con Git —ya sea en proyectos personales o colaborativos— escribir buenos commits es casi tan importante como escribir buen código. Un historial bien documentado no solo facilita entender la evolución del proyecto, sino también depurar errores, colaborar eficazmente y mantener la salud del código a largo plazo.

En este artículo, exploraremos **por qué importa escribir buenos mensajes de commit**, y te comparto una serie de buenas prácticas que puedes aplicar desde hoy.

---

## 📌 ¿Por qué es tan importante un buen commit?

Un mal mensaje de commit puede ser como un diario sin fechas ni contexto. Te imaginas algo así:

```bash
git log
commit 34af0b2 - "cambios"
commit a8123d9 - "fix"
commit 9e123f8 - "final final V2"
```

Esto no solo es frustrante, también impide que puedas:

- Entender qué cambio resolvió un bug.
- Saber por qué se tomó una decisión técnica.
- Revertir errores sin miedo a romper algo más.

>Un buen commit comunica qué se cambió y por qué, no solo cómo se hizo.
{: .prompt-info }

---

### 🧠 Principios Básicos para Commits Claros

✅ 1. Haz commits pequeños

Un commit debería enfocarse en un solo propósito: arreglar un bug, agregar una función, refactorizar algo puntual, etc.

>Commits más pequeños hacen que sea más fácil revisar, entender y revertir cambios.
{: .prompt-tip }

✅ 2. Usa verbos en imperativo

En vez de "Arreglado bug en login", usa: "Arregla bug en login".

📌 ¿Por qué? Porque los mensajes de commit completan la frase:

- Este commit [arregla bug en login]

El imperativo crea una narrativa activa y coherente en el historial del repositorio.

✅ 3. Escribe el título como un resumen

El encabezado del commit debe ser breve y directo (menos de 72 caracteres).

Ejemplos:

- Agrega validación de email en el registro

- Refactoriza componente Navbar

- Corrige error al calcular el total en carrito

✅ 4. Agrega una descripción opcional si el cambio lo amerita

Cuando el cambio es complejo, incluye un bloque de descripción explicando el por qué y cómo. Usa una línea en blanco entre título y cuerpo.

**Corrige error en cálculo de impuestos**

Se ajustó la fórmula para tener en cuenta el IVA dependiendo del país.
El error se generaba solo si el usuario no seleccionaba ubicación antes.

>Usa esta parte para explicar decisiones técnicas, edge cases o efectos secundarios.
{: .prompt-info }

---

## 📦 Convenciones útiles: Conventional Commits

Si quieres llevarlo a un siguiente nivel, puedes adoptar Conventional Commits:

- feat: agrega opción de pago con criptomonedas
- fix: corrige error de validación en formulario
- chore: actualiza dependencias de seguridad
- refactor: simplifica función de filtrado
- docs: añade sección sobre despliegue en README

>Esto permite automatizar versiones, generar changelogs y mantener orden en proyectos grandes.
{: .prompt-tip }

---

## 🧮 Cómo se relacionan los commits con el versionado semántico

Cuando seguimos convenciones claras al escribir commits, podemos incluso automatizar el versionado de nuestro software usando herramientas como semantic-release.

Este sistema se basa en SemVer (Semantic Versioning), que estructura las versiones en tres niveles:

| Tipo de Cambio | Ejemplo de Versión | Descripción                                 |
| -------------- | ------------------ | ------------------------------------------- |
| Major          | 5.0.0              | Cambios grandes que rompen compatibilidad.  |
| Minor          | 4.8.0              | Nuevas funciones, sin romper la API actual. |
| Patch          | 4.7.7              | Corrección de errores o mejoras menores.    |

>Por ejemplo, un commit con prefijo fix: genera un patch. Uno con feat: genera un minor. Y si usamos BREAKING CHANGE, puede desencadenar un cambio major automáticamente.
{: .prompt-info }

---

## 🚫 Qué evitar en tus commits

Evita caer en estos malos hábitos:

| ❌ Mal ejemplo     | ✅ Mejor opción                            |
| ----------------- | ----------------------------------------- |
| "arreglos varios" | fix: corrige validación en el login       |
| "cosas"           | refactor: mejora legibilidad de funciones |
| "final"           | feat: implementa paginación en productos  |
| "merge"           | chore: resuelve conflictos con rama dev   |

>Los commits no deberían necesitar “traducción” para ser entendidos.
{: .prompt-warning }

>Los mensajes como "merge" pueden ser automáticos. Si haces un merge manual, aprovecha para explicar qué ramas se integran y por qué.
{: .prompt-tip }

---

## 🛠️ Herramientas que te ayudan a mejorar tus commits

🔹 **Commitizen**  
Te guía para escribir commits que siguen convenciones de forma interactiva.

🔹 **GitLens (para VSCode)**  
Te da contexto visual de cada commit en tu código directamente desde el editor.

---

## 🧾 Mini Cheatsheet para tus Commits

- Escribe en imperativo → "Corrige", "Agrega", "Refactoriza"
- Mantén el título < 72 caracteres
- Usa Conventional Commits si trabajas en equipo
- Explica el porqué si el cambio es complejo

---

## ✅ Conclusión

Un buen mensaje de commit no es solo un requisito de estilo: es una herramienta de comunicación poderosa. Escribir mejores commits te hace un mejor desarrollador, facilita el trabajo en equipo y reduce errores en producción.

>Escribe commits como si otra persona tuviera que entender tu código… porque eventualmente lo hará. Y ese alguien podrías ser tú en 6 meses.”
{: .prompt-info }

---

💬 ¿Y tú, cómo escribes tus commits?

¿Tienes alguna convención, alias o herramienta favorita que usas?  
¡Compártela en los comentarios y hagamos entre todos un historial de Git más legible! 🚀

---

🗨️ “El lenguaje es la base de la civilización.”
— **Dra. Louise Banks, *La llegada* (2016)**
