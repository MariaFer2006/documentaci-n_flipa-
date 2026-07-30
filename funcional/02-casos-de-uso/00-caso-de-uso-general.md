# CU-000. Caso de uso general: gestión del ciclo de vida del crédito empresarial

[← Volver a Casos De Uso](README.md)

## Diagrama general

![Diagrama de casos de uso: Administrador](diagramas/00-diagrama-general.svg)

## Descripción

Este es el caso de uso "paraguas" que agrupa los 18 casos de uso específicos (CU-001 a CU-018) ya referenciados por [Historias de Usuario](../03-historias-usuario/README.md). Describe, de principio a fin, el ciclo de vida completo de una solicitud de crédito empresarial en Fliipa: desde que el cliente recibe el enlace de solicitud, pasando por el onboarding, la evaluación de riesgo, la firma del contrato, el uso del cupo, los pagos y la cobranza, hasta la administración del producto por parte del equipo interno.

> ✅ **Corrección (2026-07-30):** esta página se amplía de 4 a 18 casos de uso, cerrando el vacío que el propio documento venía advirtiendo desde la versión 2.0. También se corrige el actor de los 4 casos de uso originales, que se habían documentado como ejecutados enteramente por el administrador: el flujo real tiene actores mixtos (cliente empresarial, sistema automático, analista de riesgo, analista de cartera, Comité de Cartera, agente de servicio al cliente y administrador del producto).

| Campo | Detalle |
|---|---|
| **Actores** | Cliente empresarial, sistema (motor de reglas / evaluación automática), analista de riesgo, asesor comercial, analista de cartera, Comité de Cartera, agente de servicio al cliente, administrador del producto, administrador con rol de sistema |
| **Precondición** | Existe un cliente empresarial identificado como potencial sujeto de crédito. |
| **Postcondición (éxito)** | La solicitud queda registrada, evaluada, decidida (aprobada o rechazada), y si fue aprobada, el cliente puede usar y pagar su cupo, con seguimiento activo por parte del equipo interno. |
| **Postcondición (fallo)** | La solicitud queda registrada como rechazada, con el motivo documentado. |
| **Disparador (trigger)** | El cliente empresarial recibe el enlace único de solicitud e inicia el proceso desde el checkout. |

## Flujo general por etapa

### Originación

1. **[CU-001 — Registrar una solicitud de crédito](01-registrar-solicitud-credito.md):** cliente empresarial.
2. **[CU-002 — Conocer el cupo preaprobado](02-evaluar-riesgo.md):** sistema (automático).
3. **[CU-003 — Confirmar identidad por OTP](03-confirmar-identidad-otp.md):** cliente empresarial.
4. **[CU-004 — Completar KYC y cargar soportes](04-completar-kyc.md):** cliente empresarial.
5. **[CU-005 — Resolver manualmente casos de KYC en revisión](05-resolver-kyc-en-revision.md):** analista de riesgo.
6. **[CU-006 — Conocer el resultado de la evaluación](06-conocer-resultado-evaluacion.md):** cliente empresarial / analista de riesgo.
7. **[CU-007 — Firmar contrato y pagaré](07-firmar-contrato-pagare.md):** cliente empresarial.
8. **[CU-008 — Aprobar y activar la línea de crédito](08-aprobar-activar-linea-credito.md):** sistema (automático), con override manual del administrador. **Incluye** siempre a CU-002/CU-006, porque no puede haber decisión sin evaluación previa.

### Administración del crédito

9. **[CU-009 — Consultar cupo, plan de pagos y movimientos](09-consultar-cupo-plan-pagos.md):** cliente empresarial.
10. **[CU-010 — Usar el cupo en tienda D1](10-usar-cupo-tienda-d1.md):** cliente empresarial.
11. **[CU-011 — Pagar por débito automático o prepago](11-pagar-debito-prepago.md):** cliente empresarial.

### Cobranza

12. **[CU-012 — Cobranza y segmentación por mora](12-cobranza-segmentacion-mora.md):** analista de cartera / Comité de Cartera.
13. **[CU-013 — Alivios de pago](13-alivios-pago.md):** cliente empresarial / Comité de Cartera.

### Servicio al cliente

14. **[CU-014 — Atención por IA, escalamiento y validación en casos críticos](14-atencion-ia-escalamiento.md):** cliente empresarial / asistente virtual / agente de servicio al cliente.

### Portal administrativo

15. **[CU-015 — Buscar cliente, historial auditado, ajustar cupo/corte y seguimiento](15-buscar-cliente-ajustar-cupo.md):** administrador del producto.
16. **[CU-016 — Simular plan de pago con distintas tasas](16-simular-plan-pago-admin.md):** administrador del producto.
17. **[CU-017 — Administrar la lista negra (blacklist)](17-administrar-blacklist.md):** administrador del producto.
18. **[CU-018 — Monitorear la salud del sistema en tiempo real](18-monitorear-salud-sistema.md):** administrador con rol de sistema.

## Alcance actual

Con esta ampliación, el documento cubre los 18 casos de uso referenciados en Historias de Usuario, correspondientes a 10 de los 11 procesos de negocio definidos en [Alcance del Producto](../../producto/alcance.md) (no se documenta un caso de uso específico para "Captación comercial", cubierto tangencialmente por CU-001).

Un resumen honesto del estado de implementación (detalle en cada caso de uso):

| Estado | Casos de uso |
|---|---|
| ✅ Implementado y confirmado en código | CU-001, CU-002, CU-003 (con hallazgo de seguridad), CU-007, CU-008, CU-009, CU-010, CU-012 (parcial), CU-015, CU-016, CU-017 (implementado pero sin enforcement real), CU-018 (parcial) |
| ⚠️ Implementado parcialmente / con mocks | CU-004 (captura sí, biometría automatizada no), CU-006 (Experian parcialmente mockeado), CU-011 (webhook de Druo no confirma acción posterior) |
| ❌ Sin respaldo verificable en el código | CU-005, CU-012 (segmentación por bucket de mora), CU-013, CU-014 |

## Documentos relacionados

- [Casos De Uso](README.md)
- [Historias Usuario](../03-historias-usuario/README.md)
- [Requerimientos Funcionales](../04-requerimientos/01-requerimientos-funcionales.md)
- [Requerimientos No Funcionales](../04-requerimientos/02-requerimientos-no-funcionales.md)
- [Actores](../../negocio/Actores/README.md)
- [Alcance del Producto](../../producto/alcance.md)

