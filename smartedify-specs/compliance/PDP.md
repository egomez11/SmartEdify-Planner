# PDP (Policy Decision Point) — Lineamientos

Objetivo: Centralizar evaluación de políticas con sensibilidad a `tenant_id` y `local_country`.

## Modelo de decisión
- Entrada: contexto `{ tenant_id, local_country, subject, action, resource, attrs }`.
- Orden: reglas globales → reglas por país (`compliance/legal/`) → reglas por tenant.
- Salida: `allow` | `deny` | `obligations`.

## Ejemplo de política (JSON)
```json
{
  "id": "POL-COUNTRY-DATA-EXPORT",
  "effect": "deny",
  "when": {
    "local_country": {"in": ["BR", "DE"]},
    "action": {"equals": "POST /v1/tenants/*/export"}
  },
  "reason": "Restricción de transferencia internacional"
}
```

## Stubs de políticas por país (placeholder)
> Nota: Estas reglas son placeholders y deben ser confirmadas por Legal.

```json
[
  {
    "id": "POL-MVP-COUNTRY-ALLOWLIST",
    "effect": "deny",
    "when": {
      "local_country": {"notIn": ["PE"]}
    },
    "reason": "MVP restringido a Perú (PE)"
  },
  {
    "id": "POL-CONSENT-REQUIRED",
    "effect": "deny",
    "when": {
      "action": {"matches": "POST /v1/tenants/*/consents*"},
      "attrs.missing": ["user_id", "consent_type", "version", "locale"]
    },
    "reason": "Campos mínimos de consentimiento requeridos"
  },
  {
    "id": "POL-EXPORT-COUNTRY-RESTRICTED",
    "effect": "deny",
    "when": {
      "local_country": {"in": ["PE", "VE", "CL", "CO"]},
      "action": {"equals": "POST /v1/tenants/*/export"}
    },
    "reason": "Restricciones de transferencia internacional (confirmar por país)"
  }
]
```

## Integración con análisis de reglamentos (Backlog)
- El análisis MPC puede producir `obligations` que se traduzcan a políticas PDP parametrizadas por tenant/país.
- Ejemplos de obligaciones: cláusulas prohibidas, requisitos de transparencia, plazos de retención, canales de comunicación.
- Flujo propuesto: Compliance Service publica `compliance.analysis.completed` → Orquestación actualiza catálogo de políticas de ese tenant → PDP carga/activa políticas.

## Gobernanza
- Versionado de políticas, revisión legal, pruebas automatizadas por país.
