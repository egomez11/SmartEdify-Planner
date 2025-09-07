# PRD — SmartEdify

> Producto: Identidad y Consentimiento (V1)
> Versión: 0.2 (borrador)
> Owner: [PM/PO]

## 1. Resumen ejecutivo
- Problema a resolver, hipótesis y objetivos.
- Métricas de éxito (North Star, KPIs).
 - País objetivo MVP: Perú (PE). Siguientes: Venezuela (VE), Chile (CL), Colombia (CO).

## 2. Alcance
- In scope: …
- Out of scope: …
 
### Backlog (no MVP)
- Análisis de reglamentos de condominios por cliente (Compliance Service) usando MPC.
- Generación de reporte y oferta de asesoría legal (Communication Service).

## 3. Personas y casos de uso
- Persona A: …
- Caso de uso 1: …

## 4. Requisitos funcionales
- PRD-CONSENT-001: Registrar consentimiento del usuario con metadatos (tipo, versión, timestamp, canal).
- PRD-CONSENT-002: Revocar consentimiento y persistir histórico/auditoría.
- PRD-CONSENT-003: Consultar consentimientos vigentes por usuario/tenant.
- PRD-CONSENT-004: Emitir eventos de concesión y revocación.

### Requisitos backlog — Análisis de reglamentos (no MVP)
- PRD-COMP-001: Cargar reglamento de condominio (documento + metadatos) por tenant.
- PRD-COMP-002: Analizar reglamento mediante MPC en Compliance Service, asumiendo el rol aplicable para validar cumplimiento con leyes locales.
- PRD-COMP-003: Generar reporte de hallazgos y obligaciones/adecuaciones necesarias.
- PRD-COMP-004: Communication Service envía reporte y oferta de asesoría legal y seguimiento de trámites.

## 5. Requisitos no funcionales (NFR)
- Seguridad: autenticación/autorización, cifrado en tránsito y reposo.
- Disponibilidad, rendimiento, observabilidad.
- Cumplimiento y privacidad por país.

## 6. Localización y cumplimiento por país
- Contexto obligatorio en cada request/evento: `tenant_id`, `local_country` (ISO-3166-1 alpha-2).
- Referencias a `compliance/legal/` para cada país soportado.
- Reglas PDP que aplican por país y excepciones (ver `compliance/PDP.md`).
- Los textos de consentimiento son por país/idioma y versionados.
 - Soporte inicial (MVP): PE. Backlog: VE, CL, CO.

## 7. Dependencias y restricciones
- Sistemas externos, datos maestros, licencias.
 - Requisito de MPC para preservar confidencialidad en análisis de reglamentos (backlog).

## 8. Aceptación y métricas
- Criterios de aceptación por requisito (vincular con QA/test-plan).
- Plan de rollout, flags y migraciones.
- Métricas: tasa de consentimiento por país, latencia PEP/PDP, ratio de revocación.

## 9. Anexos
- Diagramas, referencias legales, enlaces a Drive (si aplica).
