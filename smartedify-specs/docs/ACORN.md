# Modelo ACORN — SmartEdify

> Versión: 0.1 (borrador)

ACORN: Actores, Capacidades, Outcomes, Reglas, NFRs.

## 1. Actores
- Usuario final (estudiante/docente): concede/revoca consentimiento.
- Admin de tenant: consulta estados y reportes.
- Servicio de cumplimiento: define políticas y textos.
 - Admin de condominio: carga y mantiene reglamentos (backlog).
 - Compliance Service (MPC): analiza reglamentos (backlog).
 - Communication Service: envía reportes y ofertas (backlog).

## 2. Capacidades (Capabilities)
- ACAP-CONSENT-001: Registrar consentimiento (por país/idioma/versión).
- ACAP-CONSENT-002: Revocar consentimiento (soft-delete con histórico).
- ACAP-CONSENT-003: Consultar vigencias por usuario/tenant.
- ACAP-CONSENT-004: Publicar eventos de cambios de consentimiento.
 
### Backlog — Capacidades de reglamentos
- ACAP-COMP-001: Cargar reglamento por tenant con metadatos.
- ACAP-COMP-002: Ejecutar análisis MPC del reglamento con perfil legal local.
- ACAP-COMP-003: Emitir reporte y obligaciones sugeridas; generar oferta de asesoría.

## 3. Outcomes (Resultados esperados)
- OC-CONSENT-001: Porcentaje de consentimientos vigentes por país > X%.
- OC-CONSENT-002: Tiempos de respuesta PEP < 50ms p95.

## 4. Reglas (Policies/Rules)
- PEP en microservicios para exigir `tenant_id` y `local_country` y consultar PDP.
- PDP central evalúa políticas por país/tenant (ver `compliance/PDP.md`).
- Contexto requerido: `tenant_id`, `local_country`.

## 5. NFRs
- Seguridad, rendimiento, auditoría, multi-tenant.

## 6. Mapeo con PRD y API
- ACAP-CONSENT-001 ↔ PRD-CONSENT-001 ↔ POST /consents, evento consent.granted
- ACAP-CONSENT-002 ↔ PRD-CONSENT-002 ↔ POST /consents:revoke, evento consent.revoked
- ACAP-CONSENT-003 ↔ PRD-CONSENT-003 ↔ GET /consents
- ACAP-CONSENT-004 ↔ PRD-CONSENT-004 ↔ AsyncAPI consent.events.*

### Backlog — Mapeo reglamentos
- ACAP-COMP-001 ↔ PRD-COMP-001 ↔ POST /compliance/regulations (No MVP)
- ACAP-COMP-002 ↔ PRD-COMP-002 ↔ POST /compliance/analyses (No MVP) · Evento compliance.analysis.completed
- ACAP-COMP-003 ↔ PRD-COMP-003/004 ↔ GET /compliance/analyses/{id} · Evento communication.offer.proposed (No MVP)
