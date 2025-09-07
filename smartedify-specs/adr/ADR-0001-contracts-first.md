# ADR-0001 — Contracts-first para SmartEdify

Estado: Aceptado
Fecha: 2025-09-07

## Contexto
- Necesitamos precisión legal por país, contratos API claros y trazabilidad.
- Multi-tenant requiere `tenant_id` y `local_country` en todo el flujo.

## Decisión
- Adoptar proceso contracts-first: PRD/ACORN → OpenAPI/AsyncAPI → Test plan/QA → Implementación.
- PEP en microservicios y PDP centralizado para decisiones de política.

## Consecuencias
- Cambios funcionales deben actualizar artefactos antes del desarrollo.
- Automatizar contratos y pruebas de compatibilidad.
- Mantenimiento de políticas por país y por tenant.

## Alternativas consideradas
- Código primero (descartado por menor alineación legal/QA).

