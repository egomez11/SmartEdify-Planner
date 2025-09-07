# Visión a futuro (servicios posteriores al PMV)

Basado en `instrucciones/microservicios.docx`. Estos servicios se activarán cuando existan criterios de negocio/escala/regulatorios que lo justifiquen.

Servicios futuros (candidatos)
- Finance/Payments Service: integración con pasarelas de pago, conciliación de transacciones y validación de cobros. Inicialmente puede residir en Billing; separar cuando haya múltiples PSPs y conciliación compleja.
- Payroll/RRHH Service: nómina y RRHH (cálculo, boletas, obligaciones legales). Valor agregado para comunidades con gestión de personal.
- Operations Service: posible fusión/escisión de Maintenance y Reservations si escala o ritmos de evolución difieren.
- Marketplace Service: contratación de proveedores externos; catálogos, contratos y pagos; integra con Billing/Payments.
- Analytics/Dashboard Service: reportes de gobernanza, estados financieros y métricas de uso; tableros en tiempo real basados en eventos.
- Observability/Monitoring Service: componente dedicado a métricas/trazas/logs y dashboards unificados; integraciones con Prometheus/Grafana y alertas por SLOs.

Criterios de activación (ejemplos)
- Volumen/Complejidad: cuando un dominio supera SLAs/escala previstos o requiere tecnología específica.
- Regulatorio: nuevas obligaciones legales que demanden separación de responsabilidades.
- Negocio: nuevos modelos (marketplace, RRHH) con tracción validada.

