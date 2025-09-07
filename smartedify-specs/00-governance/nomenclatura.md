# Nomenclatura — SmartEdify

- Repos: `smartedify-<dominio>-<servicio>`
- Servicios: `*-service` (ej.: `compliance-service`, `auth-service`).
- APIs: prefijo `/v1/tenants/{tenant_id}/...`; headers `X-Tenant-Id`, `X-Local-Country`.
- Eventos: `<dominio>.<entidad>.<accion>` (ej.: `consent.events.granted`).
- IDs: `snake_case` en payloads; recursos en `kebab-case` cuando aplique.

