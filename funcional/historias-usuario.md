# Historias Usuario

| Documento | Historias Usuario |
|-----------|---------------------|
| **Proyecto** | Fliipa |
| **Versión** | 1.2 |
| **Estado** | En revisión |
| **Responsable** | Producto y negocio |
| **Última actualización** | 2026-07-10 |

---

## Control de versiones

| Versión | Fecha | Autor | Descripción |
|---------|-------|-------|-------------|
| 0.1 | 2026-07-06 | Maria Fernanda Herazo | Borrador vacío (pendiente de completar). |
| 1.0 | 2026-07-10 | María Fernanda Herazo | Primera versión completa: 28 historias de usuario por actor, en línea con Actores y Casos de Uso. |
| 1.1 | 2026-07-10 | María Fernanda Herazo  | Se organizan las historias en tablas por actor, con prioridad y casos de uso relacionados. |
| 1.2 | 2026-07-10 | María Fernanda Herazo | Se convierte cada historia en una ficha individual (formato adaptado de plantilla de actor: descripción, criterios de aceptación, relaciones, referencias, autor/fecha/versión y comentarios). |

---

## Objetivo

Describir las necesidades de cada actor de Fliipa en lenguaje de negocio, como base para la priorización y el desarrollo de las funcionalidades del sistema.

## Alcance

Cubre historias de usuario para el cliente empresarial (tendero), el asesor comercial, el analista de riesgo, el analista de cartera, el agente de servicio al cliente y el administrador del producto, en línea con los actores descritos en [Actores](../negocio/actores.md) y los casos de uso en [Casos De Uso](casos-de-uso.md). Usa la numeración `HU-XXX` definida en [Convenciones](../CONVENCIONES.md).

## Documentos relacionados

- [Funcional](README.md)
- [Flipa - Biblioteca de Conocimiento](../README.md)
- [Mapa Del Conocimiento](../MAPA_DEL_CONOCIMIENTO.md)
- [Onboarding](../ONBOARDING.md)
- [Convenciones](../CONVENCIONES.md)
- [Negocio](../negocio/README.md)
- [Tecnico](../tecnico/README.md)
- [Qa](../qa/README.md)
- [Documento Funcional](documento-funcional.md)
- [Casos De Uso](casos-de-uso.md)
- [Requerimientos Funcionales](requerimientos-funcionales.md)
- [Requerimientos No Funcionales](requerimientos-no-funcionales.md)

## Contenido

Cada historia se documenta como una ficha individual, con el mismo espíritu de la plantilla de especificación de actor: identificador, descripción, criterios de aceptación (equivalente a "características"), relaciones con otros elementos del desarrollo, referencias de origen, control de autor/fecha/versión y comentarios adicionales.

### Cliente empresarial (tendero)

#### HU-001: Recibir enlace único de solicitud

| Campo | Detalle |
|-------|---------|
| **Actor** | Cliente empresarial |
| **Historia** | Como cliente empresarial, quiero recibir un enlace único de solicitud por WhatsApp, para poder iniciar mi proceso de crédito sin tener que buscarlo. |
| **Prioridad** | Alta |
| **Criterios de aceptación** | El cliente recibe el enlace por WhatsApp como parte del contacto simultáneo (correo, WhatsApp, llamada). El enlace crea un checkout nuevo o reanuda uno existente en `REQUEST_STARTED` para su documento. |
| **Relaciones** | Casos de uso: CU-001, CU-002. Historias relacionadas: HU-002, HU-013. |
| **Referencias** | [Procesos](../negocio/procesos.md#1-captación-comercial); `backends/b2b/src/controllers/checkouts/create-checkout.ts` |
| **Autor / Fecha / Versión** | María Fernanda Herazo (con asistencia de Claude) / 2026-07-10 / 1.0 |
| **Comentarios** | — |

#### HU-002: Ver cupo preaprobado antes de completar el formulario

| Campo | Detalle |
|-------|---------|
| **Actor** | Cliente empresarial |
| **Historia** | Como cliente empresarial, quiero ver mi cupo preaprobado antes de completar todo el formulario, para decidir si vale la pena continuar. | 
| **Prioridad** | Alta |
| **Criterios de aceptación** | El sistema muestra el cupo preaprobado calculado a partir del histórico de consumo en D1, antes de exigir todos los pasos del onboarding. |
| **Relaciones** | Casos de uso: CU-002. Requerimiento: RF-005. |
| **Referencias** | [Procesos](../negocio/procesos.md#2-onboarding-digital) |
| **Autor / Fecha / Versión** | María Fernanda Herazo (con asistencia de Claude) / 2026-07-10 / 1.0 |
| **Comentarios** | RF-005 está marcado como "no verificable" en el código de `backends/b2b` disponible; validar con el equipo técnico dónde vive el cálculo. |

#### HU-003: Confirmar identidad por OTP

| Campo | Detalle |
|-------|---------|
| **Actor** | Cliente empresarial |
| **Historia** | Como cliente empresarial, quiero confirmar mi identidad con un código enviado por WhatsApp, correo o SMS, para proteger mi cuenta sin procesos complicados. |
| **Prioridad** | Alta |
| **Criterios de aceptación** | El cliente recibe un OTP por el canal elegido y puede solicitar reenvío tras 60 segundos, con un máximo de 3 intentos. |
| **Relaciones** | Casos de uso: CU-003. Requerimiento: RF-006. |
| **Referencias** | `backends/b2b/src/controllers/otp/send-otp.ts`, `otp/validate-otp.ts` |
| **Autor / Fecha / Versión** | María Fernanda Herazo (con asistencia de Claude) / 2026-07-10 / 1.0 |
| **Comentarios** | Ver hallazgo de seguridad RNF-001 (código comodín de OTP) y RNF-007 (canal SMS no envía realmente el mensaje). |

#### HU-004: Completar KYC y cargar soportes desde el celular

| Campo | Detalle |
|-------|---------|
| **Actor** | Cliente empresarial |
| **Historia** | Como cliente empresarial, quiero completar la validación biométrica y cargar mis extractos bancarios desde el celular, para no tener que ir a una oficina. |
| **Prioridad** | Alta |
| **Criterios de aceptación** | El cliente completa la biometría con el proveedor externo y carga certificación bancaria y extractos de los últimos 3 meses, todo desde el flujo móvil de onboarding. |
| **Relaciones** | Casos de uso: CU-004, CU-005. |
| **Referencias** | [Procesos](../negocio/procesos.md#3-validación-de-identidad-kyc); `backends/b2b/src/controllers/clients/upload-document.ts` |
| **Autor / Fecha / Versión** | María Fernanda Herazo (con asistencia de Claude) / 2026-07-10 / 1.0 |
| **Comentarios** | No se encontró en el código el nombre del proveedor de biometría (Olimpia); probablemente vive en un microservicio no incluido en el repositorio revisado. |

#### HU-005: Conocer el resultado en máximo 72 horas

| Campo | Detalle |
|-------|---------|
| **Actor** | Cliente empresarial |
| **Historia** | Como cliente empresarial, quiero conocer el resultado de mi solicitud en máximo 72 horas, para poder planear mis compras en D1. |
| **Prioridad** | Alta |
| **Criterios de aceptación** | El cliente recibe notificación de aprobación o rechazo dentro de las 72 horas siguientes a completar la validación de identidad. |
| **Relaciones** | Casos de uso: CU-006. Requerimientos: RF-010, RF-011, RF-012. |
| **Referencias** | [Reglas Negocio](../negocio/reglas-negocio.md#reglas-del-cupo-y-el-crédito) |
| **Autor / Fecha / Versión** | María Fernanda Herazo (con asistencia de Claude) / 2026-07-10 / 1.0 |
| **Comentarios** | La lógica de invocación real a Experian no se encontró en el código de `backends/b2b` disponible. |

#### HU-006: Firmar contrato y pagaré desde el celular

| Campo | Detalle |
|-------|---------|
| **Actor** | Cliente empresarial |
| **Historia** | Como cliente empresarial, quiero firmar mi contrato y pagaré desde el celular con un código de verificación, para activar mi cupo sin papeleo físico. |
| **Prioridad** | Alta |
| **Criterios de aceptación** | El cliente revisa el contrato y el pagaré, recibe un OTP de firma válido por 24 horas, y el sistema genera el PDF firmado y lo envía por correo. |
| **Relaciones** | Casos de uso: CU-007. Requerimientos: RF-013, RF-014. |
| **Referencias** | `backends/b2b/src/controllers/otp/send-signature-otp.ts`, `clients/sign-contract.ts` |
| **Autor / Fecha / Versión** | María Fernanda Herazo (con asistencia de Claude) / 2026-07-10 / 1.0 |
| **Comentarios** | La firma se bloquea 24 horas tras agotar los intentos (RNF-013). |

#### HU-007: Consultar cupo, plan de pagos y movimientos

| Campo | Detalle |
|-------|---------|
| **Actor** | Cliente empresarial |
| **Historia** | Como cliente empresarial, quiero consultar mi cupo disponible, mi plan de pagos y mis movimientos, para saber cuánto puedo usar y cuánto debo. |
| **Prioridad** | Alta |
| **Criterios de aceptación** | El cliente accede al dashboard de redención y visualiza cupo disponible, plan de pagos y movimientos, solo si su línea de crédito está en estado `approved` o `active`. |
| **Relaciones** | Casos de uso: CU-009. Requerimientos: RF-016, RF-017. |
| **Referencias** | `backends/b2b/src/controllers/credit-line/get-credit-status.ts`, `apps/redemption/actions/auth.ts` |
| **Autor / Fecha / Versión** | María Fernanda Herazo (con asistencia de Claude) / 2026-07-10 / 1.0 |
| **Comentarios** | — |

#### HU-008: Usar el cupo en tienda D1

| Campo | Detalle |
|-------|---------|
| **Actor** | Cliente empresarial |
| **Historia** | Como cliente empresarial, quiero generar un código QR o un código de compra para usar mi cupo en la tienda D1, para pagar mi mercancía sin dinero en efectivo. |
| **Prioridad** | Alta |
| **Criterios de aceptación** | El cliente genera un QR con TTL o revela un código de compra, y el punto de venta D1 lo valida para aplicar el cupo a la compra. |
| **Relaciones** | Casos de uso: CU-010. Requerimientos: RF-019, RF-020. |
| **Referencias** | `backends/b2b/src/controllers/qr/get-or-create-qr.ts`, `clients/get-client-coupon.ts` |
| **Autor / Fecha / Versión** | María Fernanda Herazo (con asistencia de Claude) / 2026-07-10 / 1.0 |
| **Comentarios** | Coexisten dos mecanismos de canje (QR y código de compra); pendiente de definir con negocio cuál es el vigente. |

#### HU-009: Pagar por débito automático o prepago

| Campo | Detalle |
|-------|---------|
| **Actor** | Cliente empresarial |
| **Historia** | Como cliente empresarial, quiero que mi cuota se debite automáticamente o poder prepagar por PSE, para no tener que hacer trámites adicionales de pago. |
| **Prioridad** | Alta |
| **Criterios de aceptación** | El sistema debita automáticamente vía Druo en la fecha de corte, o permite prepago voluntario por PSE en cualquier momento antes del corte. |
| **Relaciones** | Casos de uso: CU-011. Requerimiento: RF-022. |
| **Referencias** | [Procesos](../negocio/procesos.md#8-cobro-y-pago-del-crédito) |
| **Autor / Fecha / Versión** | María Fernanda Herazo (con asistencia de Claude) / 2026-07-10 / 1.0 |
| **Comentarios** | La ejecución real del prepago por PSE no se encontró en el código de `backends/b2b` disponible. |

#### HU-010: Recibir alivios ante dificultades de pago

| Campo | Detalle |
|-------|---------|
| **Actor** | Cliente empresarial |
| **Historia** | Como cliente empresarial, quiero recibir alivios (abono parcial, congelamiento de intereses) cuando tengo dificultades temporales de pago, para no perder mi cupo ni mi historial. |
| **Prioridad** | Alta |
| **Criterios de aceptación** | El cliente puede acceder a abono parcial, congelamiento de intereses o condonación, según las condiciones y topes definidos por bucket de mora. |
| **Relaciones** | Casos de uso: CU-013. |
| **Referencias** | [Reglas Negocio](../negocio/reglas-negocio.md#reglas-de-alivios-y-negociación) |
| **Autor / Fecha / Versión** | María Fernanda Herazo (con asistencia de Claude) / 2026-07-10 / 1.0 |
| **Comentarios** | — |

#### HU-011: Resolver dudas por WhatsApp con respuesta inmediata

| Campo | Detalle |
|-------|---------|
| **Actor** | Cliente empresarial |
| **Historia** | Como cliente empresarial, quiero resolver mis dudas o reclamos por WhatsApp con respuesta inmediata, para no depender de canales lentos o presenciales. |
| **Prioridad** | Alta |
| **Criterios de aceptación** | Un asistente virtual atiende el primer contacto y, si no resuelve el caso, escala a un agente humano con el contexto completo. |
| **Relaciones** | Casos de uso: CU-014. Requerimientos: RF-028, RF-029. |
| **Referencias** | [Reglas Negocio](../negocio/reglas-negocio.md#reglas-de-servicio-al-cliente) |
| **Autor / Fecha / Versión** | María Fernanda Herazo (con asistencia de Claude) / 2026-07-10 / 1.0 |
| **Comentarios** | No se encontró un módulo de asistente de IA en el código de `backends` revisado; puede residir en una herramienta externa. |

#### HU-012: Recuperar PIN o desbloquear la cuenta

| Campo | Detalle |
|-------|---------|
| **Actor** | Cliente empresarial |
| **Historia** | Como cliente empresarial, quiero recuperar mi PIN si lo olvido o mi cuenta se bloquea, para no perder el acceso a mi cupo. |
| **Prioridad** | Media |
| **Criterios de aceptación** | El cliente puede iniciar un flujo de reseteo de PIN tras un bloqueo por intentos fallidos. |
| **Relaciones** | Requerimiento: RNF-014 (bloqueo de acceso). |
| **Referencias** | `backends/b2b/src/db/models/Client.ts` (`loginAttempts`, `lockedAt`) |
| **Autor / Fecha / Versión** | María Fernanda Herazo (con asistencia de Claude) / 2026-07-10 / 1.0 |
| **Comentarios** | — |

### Asesor comercial

#### HU-013: Contacto simultáneo multicanal

| Campo | Detalle |
|-------|---------|
| **Actor** | Asesor comercial |
| **Historia** | Como asesor comercial, quiero contactar simultáneamente por correo, WhatsApp y llamada a los clientes preaprobados, para maximizar la tasa de respuesta. |
| **Prioridad** | Alta |
| **Criterios de aceptación** | El asesor cuenta con la base de clientes preaprobados y las plantillas de contacto por los tres canales. |
| **Relaciones** | Casos de uso: CU-001. Requerimiento: RF-001. Historia relacionada: HU-001. |
| **Referencias** | [Procesos](../negocio/procesos.md#1-captación-comercial) |
| **Autor / Fecha / Versión** | María Fernanda Herazo (con asistencia de Claude) / 2026-07-10 / 1.0 |
| **Comentarios** | — |

#### HU-014: Acompañar la originación del cliente

| Campo | Detalle |
|-------|---------|
| **Actor** | Asesor comercial |
| **Historia** | Como asesor comercial, quiero acompañar al cliente durante la originación (dudas, visita de confirmación), para reducir el abandono del proceso. |
| **Prioridad** | Alta |
| **Criterios de aceptación** | El asesor da seguimiento al cliente durante el onboarding y coordina, cuando aplica, la visita de originación (hunter/visitador). |
| **Relaciones** | Casos de uso: CU-001. |
| **Referencias** | [Actores](../negocio/actores.md#actores-comerciales-y-de-cobranza) |
| **Autor / Fecha / Versión** | María Fernanda Herazo (con asistencia de Claude) / 2026-07-10 / 1.0 |
| **Comentarios** | — |

#### HU-015: Seguimiento de primera compra

| Campo | Detalle |
|-------|---------|
| **Actor** | Asesor comercial |
| **Historia** | Como asesor comercial, quiero identificar a los clientes que no han usado su cupo 7 días después de la activación, para hacer seguimiento de primera compra. |
| **Prioridad** | Media |
| **Criterios de aceptación** | El asesor recibe o consulta la lista de clientes activados sin uso del cupo a los 7 días. |
| **Relaciones** | — |
| **Referencias** | [Procesos](../negocio/procesos.md#1-captación-comercial) |
| **Autor / Fecha / Versión** | María Fernanda Herazo (con asistencia de Claude) / 2026-07-10 / 1.0 |
| **Comentarios** | No se encontró un reporte automatizado de este seguimiento en el código revisado. |

### Analista de riesgo

#### HU-016: Resolver manualmente casos de biometría en revisión

| Campo | Detalle |
|-------|---------|
| **Actor** | Analista de riesgo |
| **Historia** | Como analista de riesgo, quiero revisar manualmente los casos de biometría marcados "en revisión", para decidir si el cliente puede continuar el proceso. |
| **Prioridad** | Alta |
| **Criterios de aceptación** | El analista visualiza los casos "en revisión" y registra la decisión (continuar o rechazar), notificando al cliente. |
| **Relaciones** | Casos de uso: CU-005. |
| **Referencias** | [Reglas Negocio](../negocio/reglas-negocio.md#reglas-de-kyc-y-evaluación-de-riesgo) |
| **Autor / Fecha / Versión** | María Fernanda Herazo (con asistencia de Claude) / 2026-07-10 / 1.0 |
| **Comentarios** | — |

#### HU-017: Ver score, Experian e histórico D1 en un solo lugar

| Campo | Detalle |
|-------|---------|
| **Actor** | Analista de riesgo |
| **Historia** | Como analista de riesgo, quiero ver en un solo lugar el resultado de Experian, el histórico transaccional de D1 y el score calculado, para validar o ajustar la decisión automática. |
| **Prioridad** | Alta |
| **Criterios de aceptación** | El analista consulta, para un cliente dado, el resultado de Experian, el histórico D1 y el score consolidado antes de aprobar o rechazar. |
| **Relaciones** | Casos de uso: CU-006. Requerimiento: RF-010. |
| **Referencias** | `companies/lookup-company.ts`, `institutions/get-advance-score.ts` |
| **Autor / Fecha / Versión** | María Fernanda Herazo (con asistencia de Claude) / 2026-07-10 / 1.0 |
| **Comentarios** | La lógica de invocación real a Experian no está en el código de `backends/b2b` disponible. |

### Analista de cartera / Comité de Cartera

#### HU-018: Ver cartera segmentada por bucket de mora

| Campo | Detalle |
|-------|---------|
| **Actor** | Analista de cartera |
| **Historia** | Como analista de cartera, quiero ver la cartera segmentada por bucket de mora, para priorizar mi gestión de cobro diaria. |
| **Prioridad** | Alta |
| **Criterios de aceptación** | El analista consulta la cartera agrupada en pago anticipado y buckets 1 a 5, con los datos necesarios para priorizar su gestión. |
| **Relaciones** | Casos de uso: CU-012. |
| **Referencias** | [Reglas Negocio](../negocio/reglas-negocio.md#reglas-de-mora-y-buckets) |
| **Autor / Fecha / Versión** | María Fernanda Herazo (con asistencia de Claude) / 2026-07-10 / 1.0 |
| **Comentarios** | Existe una discrepancia documentada entre el esquema de buckets y el journey de Colpatria B2B sobre los plazos de escalamiento (ver RNF-017). |

#### HU-019: Registrar cada interacción de cobranza

| Campo | Detalle |
|-------|---------|
| **Actor** | Analista de cartera |
| **Historia** | Como analista de cartera, quiero registrar cada interacción de cobranza (canal, tipo de contacto, resultado, compromiso de pago), para mantener trazabilidad completa del caso. |
| **Prioridad** | Alta |
| **Criterios de aceptación** | El analista registra canal, tipo de contacto, resultado y monto comprometido de cada interacción, quedando disponible en el resumen de atención del cliente. |
| **Relaciones** | Casos de uso: CU-012. Requerimientos: RF-025, RF-026. |
| **Referencias** | `backends/b2b/src/controllers/clients/collection-notes.ts` |
| **Autor / Fecha / Versión** | María Fernanda Herazo (con asistencia de Claude) / 2026-07-10 / 1.0 |
| **Comentarios** | Este módulo está implementado en el código pero no descrito explícitamente en el alcance de producto (ver informe de hallazgos de negocio y producto). |

#### HU-020: Tablero semanal de priorización del Comité de Cartera

| Campo | Detalle |
|-------|---------|
| **Actor** | Comité de Cartera |
| **Historia** | Como miembro del Comité de Cartera, quiero un tablero semanal con los casos priorizados (días de mora, monto, historial), para decidir alivios, visitas o escalamiento jurídico. |
| **Prioridad** | Alta |
| **Criterios de aceptación** | El comité visualiza semanalmente los casos priorizados según días de mora, flujo de caja, cuotas vencidas, historial y monto adeudado. |
| **Relaciones** | Casos de uso: CU-012, CU-013. |
| **Referencias** | [Reglas Negocio](../negocio/reglas-negocio.md#reglas-de-gestión-y-escalamiento) |
| **Autor / Fecha / Versión** | María Fernanda Herazo (con asistencia de Claude) / 2026-07-10 / 1.0 |
| **Comentarios** | No se encontró un tablero de priorización automatizado en el código revisado. |

#### HU-021: Recibir casos de escalamiento jurídico automáticamente

| Campo | Detalle |
|-------|---------|
| **Actor** | Analista jurídico / abogado |
| **Historia** | Como analista jurídico, quiero recibir automáticamente los casos que llegan al bucket de escalamiento legal, para iniciar el proceso de cobro jurídico sin depender de un traspaso manual. |
| **Prioridad** | Media |
| **Criterios de aceptación** | Los casos que alcanzan el bucket de escalamiento jurídico se enrutan automáticamente al analista jurídico. |
| **Relaciones** | — |
| **Referencias** | [Actores](../negocio/actores.md#actores-comerciales-y-de-cobranza) |
| **Autor / Fecha / Versión** | María Fernanda Herazo (con asistencia de Claude) / 2026-07-10 / 1.0 |
| **Comentarios** | Depende de resolver primero la discrepancia de plazos de escalamiento (RNF-017). |

### Agente de servicio al cliente

#### HU-022: Recibir el caso escalado con contexto completo

| Campo | Detalle |
|-------|---------|
| **Actor** | Agente de servicio al cliente |
| **Historia** | Como agente de servicio al cliente, quiero recibir el caso escalado por la IA con el contexto completo de la conversación, para no pedirle al cliente que repita su problema. |
| **Prioridad** | Alta |
| **Criterios de aceptación** | Cuando la IA escala un caso, el agente humano ve el historial completo de la conversación antes de responder. |
| **Relaciones** | Casos de uso: CU-014. Requerimiento: RF-028. |
| **Referencias** | [Reglas Negocio](../negocio/reglas-negocio.md#reglas-de-servicio-al-cliente) |
| **Autor / Fecha / Versión** | María Fernanda Herazo (con asistencia de Claude) / 2026-07-10 / 1.0 |
| **Comentarios** | No verificable en el código de `backends` disponible. |

#### HU-023: Validar identidad en casos críticos

| Campo | Detalle |
|-------|---------|
| **Actor** | Agente de servicio al cliente |
| **Historia** | Como agente de servicio al cliente, quiero validar la identidad del cliente antes de aprobar un caso crítico (suplantación, uso indebido del cupo), para evitar fraude. |
| **Prioridad** | Alta |
| **Criterios de aceptación** | Los casos críticos requieren validación de identidad y aprobación manual explícita del agente antes de cerrarse. |
| **Relaciones** | Casos de uso: CU-014. Requerimiento: RF-029. |
| **Referencias** | [Reglas Negocio](../negocio/reglas-negocio.md#reglas-de-servicio-al-cliente) |
| **Autor / Fecha / Versión** | María Fernanda Herazo (con asistencia de Claude) / 2026-07-10 / 1.0 |
| **Comentarios** | — |

### Administrador del producto (portal administrativo)

#### HU-024: Buscar cliente y ver historial auditado

| Campo | Detalle |
|-------|---------|
| **Actor** | Administrador del producto |
| **Historia** | Como administrador, quiero buscar un cliente por documento y ver su historial completo de operaciones auditadas, para resolver dudas o disputas rápidamente. |
| **Prioridad** | Media |
| **Criterios de aceptación** | El administrador busca por documento y consulta hasta 500 registros de auditoría del cliente (línea de crédito, desembolsos, pagos). |
| **Relaciones** | Casos de uso: CU-015. Requerimientos: RF-030, RF-031. |
| **Referencias** | `backends/admin/src/controllers/clients.controller.ts` (`getClientAuditedOperations`) |
| **Autor / Fecha / Versión** | María Fernanda Herazo (con asistencia de Claude) / 2026-07-10 / 1.0 |
| **Comentarios** | — |

#### HU-025: Ajustar cupo o fecha de corte

| Campo | Detalle |
|-------|---------|
| **Actor** | Administrador del producto |
| **Historia** | Como administrador, quiero ajustar el cupo o la fecha de corte de una línea de crédito, para corregir casos excepcionales autorizados por negocio. |
| **Prioridad** | Media |
| **Criterios de aceptación** | El administrador ajusta `lineCap` y `cutoffDay` dentro de los rangos válidos, quedando la acción registrada en auditoría. |
| **Relaciones** | Casos de uso: CU-015. Requerimiento: RF-018. |
| **Referencias** | `backends/admin/src/controllers/credit-lines.controller.ts` |
| **Autor / Fecha / Versión** | María Fernanda Herazo (con asistencia de Claude) / 2026-07-10 / 1.0 |
| **Comentarios** | El rango válido de `cutoffDay` no es consistente con el de redemption (ver RNF-016). |

#### HU-026: Simular plan de pago con distintas tasas

| Campo | Detalle |
|-------|---------|
| **Actor** | Administrador del producto |
| **Historia** | Como administrador, quiero simular el plan de pago de un cliente en mora con distintas tasas, para preparar acuerdos de pago o alivios. |
| **Prioridad** | Media |
| **Criterios de aceptación** | El administrador ingresa tasa corriente, tasa de mora y umbral de días, y obtiene el plan de pago diario descargable en CSV. |
| **Relaciones** | Casos de uso: CU-016. Requerimiento: RF-024. |
| **Referencias** | `backends/admin/src/controllers/calculator.controller.ts` |
| **Autor / Fecha / Versión** | María Fernanda Herazo (con asistencia de Claude) / 2026-07-10 / 1.0 |
| **Comentarios** | — |

#### HU-027: Administrar la lista negra (blacklist)

| Campo | Detalle |
|-------|---------|
| **Actor** | Administrador del producto |
| **Historia** | Como administrador, quiero agregar o retirar clientes de la lista negra, para bloquear casos de fraude confirmado. |
| **Prioridad** | Alta |
| **Criterios de aceptación** | El administrador agrega o retira clientes de la blacklist, validando que el cliente exista. |
| **Relaciones** | Casos de uso: CU-017. Requerimiento: RF-027. |
| **Referencias** | `backends/b2b/src/controllers/blacklist/*.ts` |
| **Autor / Fecha / Versión** | María Fernanda Herazo (con asistencia de Claude) / 2026-07-10 / 1.0 |
| **Comentarios** | No se encontró enforcement de la blacklist sobre checkout, riesgo o desembolso en el código revisado (ver RF-027). |

#### HU-028: Monitorear salud del sistema en tiempo real

| Campo | Detalle |
|-------|---------|
| **Actor** | Administrador con rol de sistema (SYS_ADMIN) |
| **Historia** | Como administrador con rol de sistema, quiero ver el estado del core bancario y de la base de datos en tiempo real, para detectar incidentes antes de que afecten a los clientes. |
| **Prioridad** | Media |
| **Criterios de aceptación** | El administrador de sistema consulta latencia y disponibilidad del core bancario y de Cloud SQL desde el panel. |
| **Relaciones** | Casos de uso: CU-018. Requerimiento: RF-033. |
| **Referencias** | `backends/admin/src/controllers/system-core-health.controller.ts`, `system-cloud-sql.controller.ts` |
| **Autor / Fecha / Versión** | María Fernanda Herazo (con asistencia de Claude) / 2026-07-10 / 1.0 |
| **Comentarios** | El monitoreo de "terceros" no cubre a los proveedores de negocio (ver RNF-012). |

## Fuentes consultadas

- [Actores](../negocio/actores.md)
- [Procesos](../negocio/procesos.md)
- [Reglas Negocio](../negocio/reglas-negocio.md)
- [Casos De Uso](casos-de-uso.md)
- [Requerimientos Funcionales](requerimientos-funcionales.md)
- [Requerimientos No Funcionales](requerimientos-no-funcionales.md)
- Inventario funcional del código fuente `credits-platform-main`, realizado como parte de esta actualización.
