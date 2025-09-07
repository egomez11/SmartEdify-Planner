# Metodología Unificada — SmartEdify

> Fuente base revisada: `C:\Edgar\IDEs\ChatGPT\adaptar.txt` (adaptada a este repo).

## Principios
- Contracts-first: PRD, ACORN, OpenAPI/AsyncAPI, plan de pruebas antes de desarrollar.
- Documentación viva y estandarizada por microservicio, con trazabilidad end-to-end.
- Cumplimiento por país: `tenant_id` y `local_country` obligatorios; PEP en microservicios, PDP centralizado.
- MVP: Perú (PE). Siguientes: VE, CL, CO.

## Flujo operativo (equipo y agente)
1) Revisar `00-governance/dev-proposals/INBOX.md` (bandeja de entrada).
2) Si hay propuestas, evaluar, aceptar/rechazar y mover a `processed/` con resultado.
3) Actualizar PRD/ACORN del servicio impactado y contratos OpenAPI/AsyncAPI.
4) Actualizar QA: test-plan y `qa/traceability-matrix.md`.
5) Ajustar Compliance: `compliance/legal/`, `compliance/PDP.md`, `compliance/PEP.md`.
6) Registrar ADR si hay decisión arquitectónica.
7) Abrir PR con checklist y referencias a propuestas procesadas.

## Estructura objetivo (simplificada)
- `02-adr/` (en este repo: `adr/`);
- `03-microservicios/<servicio>/` con PRD, ACORN, OpenAPI/AsyncAPI, test-plan;
- `00-governance/` con RACI, cadencia, nomenclatura, y `dev-proposals/`.

## Definición de Hecho (DoD)
- Documentos actualizados, contratos validados, pruebas definidas, compliance verificado para PE.
- PR con checklist completo y enlace a propuestas procesadas.

