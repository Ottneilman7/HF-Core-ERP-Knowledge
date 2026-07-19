# Proyecto HF Core ERP

Versión 0.7 — CIERRE DE SESIÓN 19/07/2026

Sprint actual: SPR-001

Estado MVP: 🟡 En desarrollo

Última ENT finalizada: **ENT-011/012/013/014**, cerradas juntas en esta sesión:
- Recetas Multinivel + Semielaborados con Inventario Propio + Presentaciones de Granola (BP-011/012)
- Landing + Centro de Decisiones interno, sin exponer recetas (BP-013)
- Producción por Demanda: "voy a producir X, dime qué sacar", con máximo producible y botón de reinicio (BP-014)

Próxima ENT: A elegir por el CEO entre — Compras (versión simple), Ventas y Clientes, Finanzas, o Persistencia Local (BP-015, Fase 1).

Blueprint activo: Ninguno (a la espera de la próxima prioridad del CEO)

Blueprints finalizados: BP-001, BP-005, BP-007, BP-008, BP-009 (extendido), BP-010 (extendido), BP-011, BP-012, BP-013, BP-014

Blueprints en Backlog (registrados, no iniciados): BP-015 (Persistencia Local + Firebase/Vercel)

Pendiente de reconciliación (no bloqueante): `data/productPresentations.ts` vs. el patrón de `Product` independiente usado en BP-012 para Granola — mismo problema, dos soluciones en paralelo. Resolver en la próxima sesión.

ADR registradas: ADR-001, ADR-003, ADR-004 (con adenda)

Última actualización: 19/07/2026, 01:40 a.m.

Arquitectura: Estable

Bloqueos: Ninguno

Última actualización: 17/07/2026

---

## Nota de cierre — ENT-009

Se detectó que esta versión de PROJECT_STATUS no reflejaba el estado real documentado en BP-009 (que ya indicaba "Finalizado"). Se corrige aquí y se agrega la Regla 20 en TEAM_RULES.md para que este desfase no vuelva a ocurrir (ver archivo adjunto).