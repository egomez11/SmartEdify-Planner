# SmartEdify Specs

Repositorio de especificaciones para preparar contratos y documentación antes del desarrollo (contracts-first).

- Prioridades: (1) precisión legal por país, (2) contratos API claros, (3) trazabilidad y QA.
- Contexto requerido: `tenant_id` y `local_country` deben acompañar cada petición/sesión.
- Cumplimiento: PEP en microservicios, PDP centralizado en Compliance.

## Estructura
- `00-governance/`: Método, RACI, cadencia, nomenclatura y `dev-proposals/`.
- `01-vision/`: visión y mapa de dominios.
- `03-microservicios/`: vistas por servicio (compliance-service, consent-service,…).
- `docs/PRD.md`: Requisitos de producto con foco legal por país.
- `docs/ACORN.md`: Modelo ACORN (Actores, Capacidades, Outcomes, Reglas, NFRs).
- `api/openapi.yaml`: Contrato síncrono HTTP (OpenAPI).
- `api/asyncapi.yaml`: Contrato de eventos (AsyncAPI), si aplica.
- `qa/test-plan.md`: Plan de pruebas y criterios de aceptación.
- `qa/traceability-matrix.md`: Trazabilidad PRD → ACORN → API → QA → Compliance.
- `compliance/PEP.md`: Lineamientos de PEP por microservicio.
- `compliance/PDP.md`: Lineamientos de PDP central y políticas por país.
- `compliance/legal/`: Perfiles legales por país y registro.
- `adr/ADR-0001-contracts-first.md`: Decisión de arquitectura y proceso.
- `.github/pull_request_template.md`: Checklist de cumplimiento contracts-first.

## Flujo Contracts-first
0) Revisar `00-governance/dev-proposals/INBOX.md` y procesar propuestas.
1) Actualizar `PRD` y `ACORN`.
2) Actualizar contratos `OpenAPI/AsyncAPI` con `tenant_id` y `local_country`.
3) Actualizar `test-plan` y `traceability-matrix`.
4) Revisar/crear políticas en `compliance/legal/` y reglas PDP.
5) Abrir PR con checklist completo.

## Origen de verdad (Drive)
- Si existe carpeta de Drive oficial, documentarla en `docs/IMPORT_SOURCES.md`. No se hallaron fuentes locales en este repo.
