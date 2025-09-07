# ADR-0003 — Congelamiento de cantidad de microservicios

Estado: Aceptado
Fecha: 2025-09-07

Contexto
- Se definió un catálogo base de microservicios para SmartEdify. Para mantener gobernanza y coherencia, se congela la CANTIDAD inicial.

Decisión
- La cantidad de microservicios queda congelada según `00-governance/microservices/catalog.md`.
- Cambios en la cantidad requieren aprobación explícita del CTO y seguir `00-governance/microservices/CHANGE_CONTROL.md`.
- Los puertos no están congelados; son configurables y pueden ajustarse con buenas prácticas.

Consecuencias
- Evita proliferación no controlada de servicios y costes operativos.
- Cambios estructurales pasan por análisis de impacto, ADR y aprobación.

