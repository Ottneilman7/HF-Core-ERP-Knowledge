# HF CORE ERP

# AI CONTEXT

Versión: 1.0

---

# Objetivo

Este documento define el contexto permanente que cualquier Inteligencia Artificial deberá utilizar antes de colaborar en el desarrollo del proyecto HF Core ERP.

Su propósito es garantizar continuidad entre conversaciones, diferentes modelos de IA y futuros desarrolladores.

Este documento tiene prioridad sobre cualquier supuesto que la IA pueda realizar.

---

# Qué es HF Core ERP

HF Core ERP es un ERP moderno diseñado inicialmente para Honestly Foods CA.

El objetivo del proyecto es evolucionar hasta convertirse en un ERP comercial dirigido a:

- Startups
- Emprendedores
- PyMEs

Su filosofía consiste en ofrecer herramientas empresariales profesionales sin la complejidad de los ERP tradicionales.

---

# Filosofía de Desarrollo

La IA deberá priorizar siempre:

- simplicidad
- claridad
- reutilización
- escalabilidad
- documentación
- código limpio

El proyecto nunca debe crecer mediante código duplicado.

Siempre debe evolucionar reutilizando componentes existentes.

---

# Filosofía del Producto

HF Core ERP debe ayudar al emprendedor a organizar su empresa desde el primer día.

No busca competir con SAP.

Busca convertirse en el mejor ERP para Startups.

Cada decisión deberá favorecer:

- facilidad de uso
- rapidez
- aprendizaje
- productividad

---

# Metodología

Todo desarrollo deberá seguir el siguiente flujo.

RFC (cuando aplique)

↓

Blueprint

↓

Arquitectura

↓

Código

↓

Pruebas

↓

Documentación

↓

Git

Nunca generar código sin considerar la arquitectura existente.

---

# Reglas Obligatorias

La IA deberá cumplir siempre las siguientes reglas.

1.

Nunca reemplazar trabajo existente si puede reutilizarse.

---

2.

Nunca crear código duplicado.

---

3.

Explicar primero.

Programar después.

---

4.

Trabajar únicamente mediante entregables completos.

---

5.

Cada entregable debe indicar claramente:

Objetivo

Archivos

Código

Pruebas

Git

Próximo paso

---

6.

Toda decisión importante deberá registrarse.

---

7.

La documentación tiene el mismo valor que el código.

---

8.

El MVP siempre tiene prioridad sobre funcionalidades futuras.

---

9.

Las funcionalidades futuras deberán registrarse en el Backlog.

No implementarse inmediatamente.

---

10.

Todo módulo deberá ser escalable.

Aunque inicialmente sea sencillo.

---

# Tecnologías

Frontend

React

TypeScript

Vite

---

Lenguaje

TypeScript estricto.

---

Arquitectura

Componentes reutilizables.

Modelos separados.

Servicios separados.

Reglas de negocio separadas de la interfaz.

---

Git

Todo cambio debe terminar con:

git status

git add .

git commit

git push

---

# Convenciones

Modelos

PascalCase

Product.ts

RawMaterial.ts

Customer.ts

---

Componentes

PascalCase

Sidebar.tsx

InventoryPage.tsx

Card.tsx

---

Datos temporales

camelCase

products.ts

rawMaterials.ts

customers.ts

---

Interfaces

Siempre importar utilizando:

import type

Nunca:

import

cuando se trate únicamente de interfaces.

---

# Documentación

Cada desarrollo debe actualizar:

PROJECT_INDEX

CHANGELOG

Blueprint correspondiente

ADR cuando aplique

Lessons Learned cuando corresponda

---

# Forma de Responder

La IA debe explicar de forma pedagógica.

El usuario está aprendiendo desarrollo de software.

Las respuestas deben enseñar mientras construyen.

Evitar respuestas excesivamente resumidas.

Evitar asumir conocimientos avanzados.

---

# Objetivo Final

Construir un ERP moderno, escalable y completamente documentado que pueda evolucionar desde Honestly Foods CA hasta convertirse en un producto comercial para miles de Startups y PyMEs.

Toda decisión debe acercar al proyecto a ese objetivo.

---

# Regla del 80/20

La IA deberá priorizar siempre entregar una solución funcional que resuelva el 80% del problema con el 20% del esfuerzo.

Se evitará retrasar el MVP por intentar construir soluciones perfectas desde la primera versión.

La perfección se logrará mediante iteraciones.

Primero se entrega valor.

Después se optimiza.

# Cómo Colaaborar con este Proyecto

Indicando:

Leer START_HERE.
Leer PROJECT_STATUS.
Revisar Blueprint.
Revisar ADR.
Programar. 


Fin del Documento.
