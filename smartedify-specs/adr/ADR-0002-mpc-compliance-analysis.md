# ADR-0002 — MPC en Compliance Service para análisis de reglamentos

Estado: Propuesto
Fecha: 2025-09-07

## Contexto
- Cada condominio (tenant) aporta su reglamento como base legal interna.
- Se requiere validar su alineación con leyes locales sin exponer contenido sensible a terceros.

## Decisión (propuesta)
- Usar técnicas de Multi-Party Computation (MPC) en Compliance Service para analizar reglamentos cargados por el cliente.
- Generar obligaciones y recomendaciones que alimenten políticas PDP por tenant/país.
- Orquestar comunicación de resultados y oferta de asesoría legal vía Communication Service.

## Consecuencias
- Infraestructura y librerías MPC; mayor complejidad operativa.
- Diseñar modelo de `obligations` interoperable con PDP y trazabilidad QA.
- Nuevos endpoints/eventos (definidos como backlog en OpenAPI/AsyncAPI).

## Estado y próximos pasos
- Validar viabilidad técnica y riesgos legales.
- Definir piloto en Perú (PE) post-MVP.

