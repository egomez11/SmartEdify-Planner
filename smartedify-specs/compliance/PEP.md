# PEP (Policy Enforcement Point) — Lineamientos

Objetivo: Aplicar decisiones de política en el borde de cada microservicio.

## Principios
- Siempre exigir `X-Tenant-Id` y `X-Local-Country` en requests/eventos.
- Consultar PDP antes de ejecutar acciones sensibles.
- Registrar decisiones para auditoría (siempre sin datos sensibles innecesarios).

## Patrón (pseudocódigo)
```pseudo
middleware(request):
  ctx = {
    tenant_id: request.headers['X-Tenant-Id'],
    local_country: request.headers['X-Local-Country'],
    subject: request.user.id,
    action: request.method + " " + request.route,
    resource: request.route,
  }
  decision = PDP.evaluate(ctx)
  if decision == 'deny':
    return 403
  next()
```

## Telemetría mínima
- `decision`, `policy_id`, `tenant_id`, `local_country`, `latency_ms`.

