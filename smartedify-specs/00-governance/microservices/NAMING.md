# Convenciones de nombres de microservicios

Objetivo: nombres claros, consistentes y fáciles de usar en procesos humanos y automatizados. No cambia la CANTIDAD de servicios.

Convenciones
- Nombre visible (humano): Title Case, evitar acrónimos ambiguos.
- Identificador canónico: kebab-case terminado en `-service` (ej.: `notification-service`).
- Repositorio: `smartedify-<identificador-canónico>`.
- K8s/Helm: `app.kubernetes.io/name=<identificador-canónico>`.
- Eventos: `<dominio>.<entidad>.<acción>` versionados (ej.: `notification.message.sent.v1`).
- APIs: prefijo `/v1/tenants/{tenant_id}/...`; headers `X-Tenant-Id`, `X-Local-Country`.

Nota: Cambiar nombres puede impactar contratos y tooling; aplicar vía propuesta y plan de migración.

