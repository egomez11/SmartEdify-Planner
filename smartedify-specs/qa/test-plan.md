# Plan de Pruebas — SmartEdify

> Versión: 0.1 (borrador)

## 1. Objetivos
- Validar requisitos del PRD y contratos (OpenAPI/AsyncAPI).
- Verificar cumplimiento legal por país con PDP/PEP.

## 2. Alcance y niveles
- Unitarias, contrato (contract tests), integración, e2e, seguridad, rendimiento.

## 3. Estrategia
- Contract-first: generar tests a partir de `api/openapi.yaml` y `api/asyncapi.yaml`.
- Incluir headers obligatorios `X-Tenant-Id`, `X-Local-Country` en pruebas.
- Simular políticas PDP por país (dobles o mocks configurables).

## 4. Entornos y datos
- Ambientes: dev/staging/prod. Datos sintéticos y datasets por país.
 - MVP: cubrir únicamente `local_country = PE` con datasets y textos de consentimiento de Perú.

## 5. Trazabilidad
- Ver `qa/traceability-matrix.md`.

## 6. Criterios de salida
- Cobertura mínima por nivel, 0 tests críticos fallando.
- Evidencias de cumplimiento por país aprobadas por Compliance.

## 7. Riesgos
- Cambios legales regionales; mantenimiento continuo de políticas.

## 8. Casos de prueba iniciales (ejemplo)
- API-HEALTH-001: GET `/health` responde 200.
- API-EX-001: GET `/v1/tenants/{tenant_id}/examples` con headers requeridos responde 200.
- PDP-COUNTRY-001: Acciones restringidas correctamente según `local_country`.
- API-CONSENT-POST-001: POST `/v1/tenants/{tenant_id}/consents` crea consentimiento (201) con headers requeridos.
- API-CONSENT-LIST-001: GET `/v1/tenants/{tenant_id}/consents` retorna lista filtrable por `user_id`.
- API-CONSENT-REVOKE-001: POST `/v1/tenants/{tenant_id}/consents/revoke` revoca y registra histórico (200).
- EVT-CONSENT-GRANTED-001: Publicación de `consent.events.granted` con headers y payload mínimos.
 - EVT-CONSENT-REVOKED-001: Publicación de `consent.events.revoked` correcta.
 - COUNTRY-PE-ONLY-001: Rechazar operaciones si `X-Local-Country` != `PE` en entornos MVP.

### Backlog — Casos de prueba (no MVP)
- COMP-REG-UPLOAD-001: POST `/compliance/regulations` registra metadatos y URI.
- COMP-ANALYSIS-START-001: POST `/compliance/analyses` inicia análisis MPC y retorna 202.
- COMP-ANALYSIS-STATUS-001: GET `/compliance/analyses/{id}` devuelve estado y `report_uri`.
- EVT-COMP-ANALYSIS-001: Recepción de `compliance.analysis.completed` y validación de `obligations`.
- EVT-COMM-OFFER-001: Recepción de `communication.offer.proposed` con canales esperados.
