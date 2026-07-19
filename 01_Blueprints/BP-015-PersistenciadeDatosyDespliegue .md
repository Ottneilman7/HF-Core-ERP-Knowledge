# BP-015 Persistencia de Datos y Despliegue (Pendiente — Backlog priorizado)

Versión: 1.0
Última actualización: 19/07/2026
Origen: Decisión pendiente identificada en BP-014 ("¿dónde se guarda lo que se produce/vende/compra?").

---

## Objetivo

Hoy, todo el catálogo (`rawMaterials.ts`, `recipes.ts`, `products.ts`) son archivos de código estático — no hay dónde persistir cambios reales (ej. confirmar una producción y descontar stock de verdad). Este Blueprint registra el plan en dos fases, ya acordado con el CEO, para no bloquear el desarrollo mientras se toma con calma la decisión de backend definitivo.

## Fase 1 — Puente temporal: `localStorage` (próxima a construir)

- Guardar en el navegador (`localStorage`) las cantidades reales de `currentStock` de materia prima y semielaborados, en vez de los valores fijos en el código.
- Los archivos `.ts` (`rawMaterials.ts`, `recipes.ts`) pasan a ser el **valor inicial/semilla**; `localStorage` guarda el valor real vigente.
- Suficiente para seguir desarrollando y probando el flujo completo (Producción, futuro Compras/Ventas) sin esperar un backend.
- **Limitación explícita y aceptada:** solo vive en esa computadora y ese navegador. No sirve para trabajar en equipo ni desde el celular. Es una etapa de desarrollo, no la solución final.

## Fase 2 — Backend real: Firebase + despliegue en Vercel (decisión ya tomada por el CEO, pendiente de construir)

- Base de datos real (Firestore, vía Firebase) — permite multiusuario, respaldo, acceso desde cualquier dispositivo.
- Despliegue del frontend en Vercel — accesible desde una URL real, no solo `localhost`.
- Esto es un cambio de arquitectura importante: requiere su propio ADR antes de implementarse (autenticación, reglas de seguridad de Firestore, migración de los datos semilla actuales a la base de datos real).

## Estado

🔴 No iniciado. Registrado en Backlog como próxima gran decisión de arquitectura, después de que BP-011/012/013/014 queden cerrados y probados.