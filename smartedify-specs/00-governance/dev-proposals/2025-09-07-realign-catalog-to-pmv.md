# Propuesta de cambio — Alinear catálogo a PMV (sin cambiar cantidad)

- Autor: CTO/Agente
- Tipo: Cambio de catálogo (composición)
- País/tenant: Global (PE MVP)
- Estado: Propuesta
- Fecha: 2025-09-07

## 1. Resumen
Actualizar la composición del catálogo de microservicios para que el PMV incluya los 10 servicios definidos en `instrucciones/microservicios.docx`, sin alterar la cantidad total.

## 2. Cambios propuestos (set de PMV)
- Incluir en PMV: Reservations Service, DocuCore, Billing/Subscriptions, Compliance Service (PDP).
- Mover a futuro: Finance/Payments, Payroll/RRHH.
- Mantener: Auth, Tenants, Users, AssemblyCore, Maintenance, Communications.
- API Gateway: transversal (no contado en la cantidad).

## 3. Impacto en artefactos
- PRD/ACORN: actualizar dominios y capacidades asociadas a Reservations/DocuCore/Billing/Compliance.
- OpenAPI/AsyncAPI: definir contratos mínimos para nuevos servicios PMV (placeholders si aplica).
- QA: test-plan y trazabilidad para PMV revisados según el nuevo set.
- Compliance: PDP/PEP roles por servicio; políticas y obligaciones por país donde aplique.
- Observabilidad/Deploy: diagramas y SLIs por servicio del PMV.

## 4. Riesgos y mitigaciones
- Riesgo: incremento de alcance PMV. Mitigación: mantener contratos mínimos y feature flags.
- Riesgo: confusión con conteo. Mitigación: ADR-0003 mantiene cantidad congelada; este cambio no la altera.

## 5. Aprobaciones
- PO: [ ]  TL: [ ]  Compliance: [ ]  QA: [ ]  CTO: [ ]

