SmartEdify — Instrucciones para Agentes (solo este repositorio)

Ámbito: estas reglas aplican únicamente al repositorio `smartedify-specs` y no deben propagarse a otros repos sin aprobación explícita.

1) Ritual de inicio de sesión
- Revisar primero `00-governance/dev-proposals/INBOX.md` y cualquier archivo Markdown en esa carpeta.
- Si hay propuestas pendientes, procesarlas y reflejar decisiones en PRD/ACORN/OpenAPI/AsyncAPI/test-plan/traceability/Compliance antes de cualquier otra acción.

2) Contracts-first y cumplimiento
- Todo cambio funcional debe actualizar: PRD, ACORN, OpenAPI/AsyncAPI, `qa/test-plan.md`, `qa/traceability-matrix.md`.
- Incluir siempre `tenant_id` y `local_country` en contexto de APIs/eventos.
- PEP en microservicios; PDP central en `compliance/PDP.md`.

3) Países y MVP
- MVP: Perú (PE) únicamente; países siguientes en backlog.

4) Trazabilidad
- Mantener enlaces cruzados entre PRD ↔ ACORN ↔ API/Eventos ↔ QA ↔ Compliance.

5) Microservicios
- Respetar la política de congelamiento de cantidad en `00-governance/microservices/catalog.md` y el procedimiento en `00-governance/microservices/CHANGE_CONTROL.md`.
- No proponer ni crear servicios nuevos ni eliminar existentes sin propuesta aprobada por el CTO.
- Los puertos son configurables y no requieren aprobación de cantidad.
