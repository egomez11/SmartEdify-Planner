# Propuesta de cambio — Ajustes de consentimiento PE (MVP)

- Autor: Equipo SmartEdify
- Servicio(s) impactado(s): consent-service, compliance-service
- Tipo: Cambio de contrato
- País/tenant: PE
- Estado: Propuesta
- Fecha: 2025-09-07

## 1. Resumen
Ajustar el contrato de consentimiento para PE: agregar `evidence_uri` opcional al crear consentimiento y `revocation_reason_code` catalogado en la revocación.

## 2. Impacto en artefactos (contracts-first)
- PRD: docs/PRD.md (PRD-CONSENT-001/002)
- ACORN: docs/ACORN.md (ACAP-CONSENT-001/002)
- OpenAPI: api/openapi.yaml (`POST /consents` y `/consents/revoke`)
- QA: qa/test-plan.md (nuevos casos), qa/traceability-matrix.md
- Compliance: compliance/PDP.md (validaciones/obligations para PE)

## 3. Consideraciones legales (PE)
- Evidencias de consentimiento podrían requerir almacenamiento y retención definidos (validar con Legal PE).

## 4. Riesgos y mitigaciones
- Riesgo: incremento de complejidad de payload. Mitigación: mantener campos opcionales y validar esquema.

## 5. Aprobaciones
- Por aprobar: PO [ ], TL [ ], Compliance [ ], QA [ ], CTO/Agente [ ]

