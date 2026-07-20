# Proyecto HF Core ERP

Versión 0.8 — 19/07/2026

Sprint actual: SPR-002 — Configuración (BP-016)

Estado MVP: 🟡 En desarrollo

Última ENT finalizada: ENT-011/012/013/014 (sesión anterior, cerrada).

Última ENT en curso: **ENT-015 — Configuración (BP-016)**. Origen: auditoría del proyecto (ver AUDITORIA-MVP-EIF.md) detectó que el Flujo 1 del verdadero MVP ("Configurar el negocio": Empresa, Parámetros, Impuestos) nunca se había construido, pese a que Catálogo/Producción/Centro de Decisiones ya existían. Se prioriza sobre Compras/Ventas/Finanzas porque esos módulos necesitan moneda e impuestos ya definidos.

Próxima ENT (tras cerrar Configuración): **Flujo 3 — Compras** (Proveedores, Órdenes de compra, Recepción, Actualización de costos), siguiendo el orden del verdadero MVP (EL-Verdadero-MVP-EIF.md).

Blueprint activo: BP-016 (Configuración) — 🟡 En desarrollo, pendiente checklist Regla 20.

Blueprints finalizados: BP-001, BP-005, BP-007, BP-008, BP-009 (extendido), BP-010 (extendido), BP-011, BP-012, BP-013, BP-014

Blueprints en Backlog (registrados, no iniciados): BP-015 (Persistencia local completa + Firebase/Vercel — Fase 1 ya arrancó parcialmente vía BP-016, solo para Configuración)

Pendiente de reconciliación (no bloqueante): `data/productPresentations.ts` vs. el patrón de `Product` independiente usado en BP-012 para Granola.

ADR registradas: ADR-001, ADR-003, ADR-004 (con adenda)

Arquitectura: Estable

Bloqueos: Ninguno

Última actualización: 19/07/2026

---

## Nota de auditoría — 19/07/2026

Ver `AUDITORIA-MVP-EIF.md` para el detalle completo de qué existe, qué falta y por qué se prioriza Configuración antes de Compras/Ventas/Finanzas (opciones que estaban abiertas al CEO en la versión anterior de este documento).

## Nota de cierre — ENT-009

Se detectó que esta versión de PROJECT_STATUS no reflejaba el estado real documentado en BP-009 (que ya indicaba "Finalizado"). Se corrigió y se agregó la Regla 20 en TEAM_RULES.md.