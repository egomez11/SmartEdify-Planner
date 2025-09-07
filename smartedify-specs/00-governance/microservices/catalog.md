# Catálogo de Microservicios (congelado)

> Fuente: `instrucciones/microservicios.txt` dentro del repo. La CANTIDAD de microservicios está CONGELADA y no puede cambiarse sin aprobación explícita del CTO. Los puertos son configurables y NO forman parte del congelamiento.

Servicios actuales (10):
- API Gateway — Gateway/API Edge (enrutamiento, auth, rate limiting, CORS).
- Auth Service — Identidad (JWT/OIDC), RBAC, MFA, sesiones/tokens.
- User Profiles Service — Perfiles/roles por condominio, organización, datos maestros de usuarios.
- Tenant Management Service — Multi-tenant: condominios, unidades, alícuotas, onboarding, aislamiento de datos.
- Security Analytics Service — Seguridad avanzada: amenazas, comportamiento, device fingerprinting, geolocalización.
- Notification Service — Mensajería multicanal, plantillas, tracking, mural, schema registry de eventos.
- Finance Service — Finanzas/contabilidad/tesorería/pagos, cuotas por alícuota, pasarelas PE, SUNAT, Sagas.
- Payroll Service — Nóminas y obligaciones laborales (PLAME) integrado con finanzas.
- Maintenance Service — Activos, incidencias/órdenes, mantenimiento preventivo, proveedores, costos.
- AssemblyCore — Asambleas: convocatoria→acta, votación por alícuota, quórum tiempo real, actas certificadas, IA/NLP.

Notas
- El documento de origen menciona “12 servicios” pero lista explícitamente 10. Se mantiene el catálogo con 10, y se registra pendiente para aclarar los 2 faltantes con el CTO.
- Cualquier cambio en la CANTIDAD requiere el proceso descrito en `00-governance/microservices/CHANGE_CONTROL.md`.
