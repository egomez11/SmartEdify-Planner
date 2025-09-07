# Matriz de Trazabilidad — SmartEdify

| PRD-ID | ACORN-Cap | API/Evento | Caso de prueba | Compliance | Estado |
|---|---|---|---|---|---|
| PRD-CONSENT-001 | ACAP-CONSENT-001 | POST /v1/tenants/{tenant_id}/consents | API-CONSENT-POST-001 | PE | Draft |
| PRD-CONSENT-003 | ACAP-CONSENT-003 | GET /v1/tenants/{tenant_id}/consents | API-CONSENT-LIST-001 | PE | Draft |
| PRD-CONSENT-002 | ACAP-CONSENT-002 | POST /v1/tenants/{tenant_id}/consents/revoke | API-CONSENT-REVOKE-001 | PE | Draft |
| PRD-CONSENT-004 | ACAP-CONSENT-004 | consent.events.granted | EVT-CONSENT-GRANTED-001 | PE | Draft |
| PRD-CONSENT-004 | ACAP-CONSENT-004 | consent.events.revoked | EVT-CONSENT-REVOKED-001 | PE | Draft |

| PRD-COMP-001 | ACAP-COMP-001 | POST /v1/tenants/{tenant_id}/compliance/regulations | COMP-REG-UPLOAD-001 | PE | Backlog |
| PRD-COMP-002 | ACAP-COMP-002 | POST /v1/tenants/{tenant_id}/compliance/analyses | COMP-ANALYSIS-START-001 | PE | Backlog |
| PRD-COMP-003 | ACAP-COMP-003 | GET /v1/tenants/{tenant_id}/compliance/analyses/{id} | COMP-ANALYSIS-STATUS-001 | PE | Backlog |
| PRD-COMP-003 | ACAP-COMP-003 | compliance.analysis.completed | EVT-COMP-ANALYSIS-001 | PE | Backlog |
| PRD-COMP-004 | ACAP-COMP-003 | communication.offer.proposed | EVT-COMM-OFFER-001 | PE | Backlog |

Notas:
- Mantener esta tabla en cada cambio funcional (contracts-first).
