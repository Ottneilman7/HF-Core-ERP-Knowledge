# v0.0.8

## ENT-008 20260714

### Agregado

- Customer Model
- CustomersPage
- Indicadores
- Prioridad de clientes
- Preparación para Motor de Decisiones

# v0.0.9

## ENT-008A 20260715

### Agregado

- React Router
- AppRouter
- Sidebar navegable
- Arquitectura desacoplada
---

# Corrección de documentación

Sincronizado PROJECT_STATUS.md con BP-009: ENT-009 (Recetas de Producción) queda registrado como cerrado en ambos documentos.
Agregada Regla 20 a TEAM_RULES.md: checklist obligatorio de cierre de entregable para evitar desfases entre Blueprint y PROJECT_STATUS.
Reconstruido BP-005 (Materia Prima), previamente listado en PROJECT_STATUS pero no documentado como archivo independiente. Pendiente de validación de campos contra el código real.

Added — ENT-010 (BP-010)

models/ProductionNeed.ts
services/productionCalculatorService.ts (getActiveRecipe, calculateProductionNeeds, getShortages, toDecisionMessage)
services/productionCalculatorService.test.ts
components/MaterialShortageAlert.tsx (Centro de Decisiones)
components/ProductionSimulator.tsx (RecipesPage)

⚠️ Pendiente antes de cerrar ENT-010: integrar contra el código real del repo HF-CORE-ERP y confirmar el campo de stock en RawMaterial (ver BP-005
--- 

# Corrección de documentación (previa a integración)

Sincronizado PROJECT_STATUS.md con BP-009: ENT-009 cerrado en ambos documentos.
Agregada Regla 20 a TEAM_RULES.md: checklist obligatorio de cierre de entregable.
BP-005 (Materia Prima) confirmado v2.0 contra el modelo real (category, supplier, minimumStock, unitCost).
Adenda a ADR-003: corrección de estado — el Centro de Decisiones (Nivel 2) no estaba realmente implementado pese a decir "Aprobada e implementada". Corregido en ENT-010.

Added — ENT-010 (BP-010 v2.0)

models/ProductionNeed.ts (con remainingStock / belowMinimumAfterProduction, aprovechando RawMaterial.minimumStock)
services/productionCalculatorService.ts (tipado contra modelos reales del repo)
services/productionCalculatorService.test.ts (11 casos, con datos reales de rawMaterials.ts / recipes.ts)
contexts/ProductionAlertsContext.tsx (nuevo)
components/MaterialShortageAlert.tsx (alertas urgentes + preventivas)
components/ProductionSimulator.tsx (embebido en RecipesPage)

Changed

pages/RecipesPage.tsx: integra ProductionSimulator por receta, sin alterar el diseño existente.
pages/HomePage.tsx: pasa de tarjeta estática a Centro de Decisiones real.
router/AppRouter.tsx: "/" ahora enruta a HomePage (antes iba, por error, a CustomersPage, que queda solo en /customers). Envuelto con ProductionAlertsProvider.


✅ Finalizado: checklist de Regla 20 (copiados archivos al repo real, npx vitest run, prueba en navegador, confirmación del CEO, commit + push).
---

Added — ENT-011 (BP-011, ADR-004)

* models/Recipe.ts: RecipeItem extendido con componentRecipeId (producto intermedio); Recipe con isIntermediate.
* models/Product.ts: agregado code (SKU real, opcional, retrocompatible).
* data/rawMaterials.ts: catálogo real de 14 materias primas con unitCost derivado de BOM_HonestlyFoods.xlsx. Id "3" (Mantequilla de Maní) deprecada.
* data/products.ts: catálogo real (HB_C1, HB_R1, HB_E1).
* data/recipes.ts: recetas reales multinivel — "Granola Base Honestly" y "Honestly Peanut Butter" (intermedias) + las 3 barras finales de 50g con cantidades corregidas por el CEO.
* services/productionCalculatorService.ts: calculateProductionNeeds ahora resuelve recursivamente productos intermedios hasta materia prima real (nuevo parámetro recipes), con salvaguarda de profundidad máxima (5) contra referencias circulares.
* services/productionCalculatorService.test.ts: pruebas con los datos reales, incluyendo el caso de una materia prima (Fruit Roll) que aparece en dos ramas del árbol y debe sumarse.
* ADR-004-RecetasMultinivel.md, BP-011-RecetasMultinivelYCatalogoReal.md.

Changed

*components/ProductionSimulator.tsx: reenvía recipes al servicio (nueva firma); mejoras de estilo pedidas por el usuario (input más grande, botón más pequeño y con color).
* pages/RecipesPage.tsx: espaciado entre ingredientes corregido; solo muestra recetas finales (no intermedias); soporta mostrar ingredientes que son productos intermedios.
* BP-005-MATERIAPRIMA.md, BP-009-RECETASDEPRODUCCION.md, BP-010-CALCULODEMATERIAPRIMA.md: adendas documentando la extensión y el reemplazo de datos de ejemplo por datos reales.

Backlog (registrado, no implementado — Regla 8 TEAM_RULES)

* BOM detallado de Fruit Rolls (costeo y composición exacta por unidad).
* SKUs de empaque (Pack x3 / Pack x6) como variantes de venta de la misma receta.
* Costeo automático por receta (la arquitectura multinivel ya lo habilita).
* Carga de inventario real (currentStock) de las materias primas nuevas.

⚠️ Pendiente antes de marcar ENT-011 como ✅ Finalizado: checklist de Regla 20 (copiar archivos al repo real, npx vitest run, prueba en navegador con HB_C1 en /recipes, confirmación del CEO, commit + push).

--- 

## [0.7] — 19/07/2026 — Cierre de sesión

### Closed — BP-011/012 (Recetas Multinivel)
- Semielaborados con inventario propio (Granola, Peanut Butter) que ya no se desarman en cascada al calcular una barra.
- Presentaciones reales de venta de Granola (50g/200g/400g).
- Catálogo real de materia prima con costo por gramo.

### Closed — BP-013 (Landing + Navegación)
- `/` es una landing con frase motivadora diaria y accesos a las tareas del día.
- Centro de Decisiones movido a `/decisions`.
- Recetas retirada de la navegación (no se expone la fórmula).

### Closed — BP-014 (Producción por Demanda)
- Flujo "elige qué producir, dice cuánto, calcula qué sacar de almacén".
- Máximo producible con el stock actual.
- Botón de reinicio de consulta (estilo moderno, `ResetButton`).
- Centro de Decisiones limpio: se retiró la alerta automática de stock mínimo (esos mínimos eran placeholders, no datos reales del emprendedor).

### Fixed
- Duplicación de `calculateMaxProducible` en `productionCalculatorService.ts`.
- `ProductsPage.tsx` recuperado desde git tras sobrescritura accidental.
- `ProductionPage.tsx` faltante en el repo (nunca se había guardado).

### Backlog registrado (no iniciado)
- BP-015: persistencia local (`localStorage`) como puente, luego backend real con Firebase + despliegue en Vercel.
- Reconciliar `data/productPresentations.ts` con el patrón de `Product` usado para las presentaciones de Granola (BP-012) — dos soluciones paralelas al mismo problema.
- Compras, Ventas/Clientes, Finanzas — capacidades completas, aún no iniciadas.