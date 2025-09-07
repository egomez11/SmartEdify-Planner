# Propuesta de cambio — Mejora de nombres de microservicios (sin cambiar cantidad)

- Autor: CTO/Agente
- Tipo: Estandarización de nombres
- Estado: Aprobada
- Fecha: 2025-09-07

Alcance
- Mantener: Auth Service, Maintenance Service, AssemblyCore.
- Renombrar DocuCore a: Document Core.
- Proponer nuevos nombres para los demás servicios siguiendo `00-governance/microservices/NAMING.md`.

Mapa de nombres (propuesto)
- API Gateway → API Gateway (identificador: `api-gateway`)
- Auth Service → Auth Service (identificador: `auth-service`)
- Users Service → User Profiles Service (identificador: `user-profiles-service`)
- Tenants Service → Tenant Management Service (identificador: `tenant-management-service`)
- Security Service → Security Analytics Service (identificador: `security-analytics-service`)
- Communications Service → Notification Service (identificador: `notification-service`)
- Billing/Subscriptions Service → Billing Subscriptions Service (identificador: `billing-subscriptions-service`)
- Compliance Service (PDP) → Policy Decision Service (identificador: `policy-decision-service`)
- Reservations Service → Amenities Reservations Service (identificador: `amenities-reservations-service`)
- Maintenance Service → Maintenance Service (identificador: `maintenance-service`)
- AssemblyCore → AssemblyCore (identificador: `assemblycore-service`)
- DocuCore → Document Core (identificador: `document-core-service`)

Impacto y mitigación
- Contratos: revisar nombres en documentación, repos, despliegues, dashboards; los endpoints y topics NO cambian aún.
- Eventos y APIs: mantener compatibilidad; cualquier cambio de namespace/versionado requerirá propuesta separada.
- Tooling/Observabilidad: alinear etiquetas `app.kubernetes.io/name` y paneles.

Plan de adopción
1) Aprobación de nombres (esta propuesta).
2) Actualizar documentación (catálogo, visión, readmes) sin tocar contratos.
3) Posterior PR para alinear identificadores en despliegues/observabilidad.

Aprobaciones
- PO: [ ]  TL: [ ]  Compliance: [ ]  QA: [ ]  CTO: [ ]
