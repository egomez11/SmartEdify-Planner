# Control de Cambios — Cantidad de Microservicios

Política
- La cantidad de microservicios del catálogo está CONGELADA. No se pueden agregar ni eliminar servicios sin aprobación explícita del CTO.
- Los puertos son configurables y pueden cambiarse siguiendo buenas prácticas (no requieren aprobación de cantidad).

Procedimiento iterativo de cambio (alta/baja de servicios)
1) Propuesta: crear un archivo en `00-governance/dev-proposals/` usando `TEMPLATE.md` indicando:
   - Motivación, alternativas, impacto en dominios, contratos, cumplimiento y operación.
   - Riesgos, mitigaciones y plan de migración/rollback.
2) Análisis de impacto (obligatorio):
   - PRD/ACORN afectados, OpenAPI/AsyncAPI, QA (test-plan y trazabilidad), Compliance (PDP/legal/PEP), Observabilidad y Deploy.
3) ADR: agregar uno nuevo con la decisión propuesta y consecuencias.
4) Revisión y ciclo iterativo: CTO, PO, TL, Compliance y QA revisan; se itera hasta Aprobado/Rechazado.
5) Aprobación explícita del CTO: si Aprobado → actualizar `catalog.md`, ADR y artefactos; si Rechazado → cerrar propuesta con justificación.
6) PR: abrir PR con checklist completo y referencias a la propuesta/ADR.

Registro
- Mantener historial de cambios de catálogo vía PRs y ADRs.

