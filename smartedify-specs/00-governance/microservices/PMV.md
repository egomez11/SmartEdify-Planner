# Servicios del PMV (Producto Mínimo Viable)

Fuente: `instrucciones/microservicios.docx` (extraído en esta sesión). La cantidad total de microservicios permanece congelada; este documento solo redefine el conjunto del PMV sin alterar la cantidad.

Servicios PMV (10)
- Auth Service: identidad central (JWT/OIDC), RBAC, MFA, sesiones/tokens.
- Tenant Management Service: alta/configuración de condominios, `local_country`, datos legales básicos, onboarding y estado de suscripción.
- User Profiles Service: perfiles y datos personales; relaciones propietario/arrendatario/familiar; eventos de alta/cambio de usuario.
- AssemblyCore: ciclo de asambleas (pre, en vivo, post); agendas, quórum y mayorías, votación en tiempo real, actas; integra Policy Decision/Notification/Document Core.
- Maintenance Service: activos, mantenimiento preventivo/correctivo, incidencias, proveedores y costos (coordina con Billing Subscriptions).
- Amenities Reservations Service: disponibilidad y reservas de áreas comunes; pre-reserva, cobro de tarifas (vía Billing Subscriptions), cancelaciones; verifica habilitaciones y envía recordatorios.
- Document Core: generación y versionado de documentos; plantillas; firma y sellado; verificación de autenticidad.
- Notification Service: notificaciones multicanal (correo, SMS, push); plantillas, preferencias e historial; orquesta envíos a partir de eventos.
- Billing Subscriptions Service: planes y facturación; ciclos de pago; addons por microservicio; estados de suscripción; coordina con Finance/Payments.
- Policy Decision Service (PDP): políticas legales por país/acto; decide quórums, mayorías, retención; valida consentimientos; actúa como PDP, con PEP en otros servicios; versionado y firmas.

Notas
- API Gateway: previsto para enrutamiento, auth, rate limiting y trazabilidad; componente transversal no necesariamente contabilizado dentro del límite de cantidad.
- PEP y PDP: los servicios de dominio actúan como PEP consultando al PDP (Policy Decision Service).
