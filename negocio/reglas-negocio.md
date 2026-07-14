# Reglas Negocio

| Documento | Reglas Negocio |
|-----------|-----------------|
| **Proyecto** | Fliipa |
| **Versión** | 1.2 |
| **Estado** | En revisión |
| **Responsable** | Negocio y operaciones |
| **Última actualización** | 2026-07-09 |

---

## Control de versiones

| Versión | Fecha | Autor | Descripción |
|---------|-------|-------|-------------|
| 0.1 | 2026-07-06 | María Fernanda Herazo | Borrador vacío (pendiente de completar). |
| 1.0 | 2026-07-08 | María Fernanda Herazo | Primera versión completa: reglas de cupo, mora, alivios, escalamiento jurídico, control de riesgo operativo y tipificación de contactos, con base en el Modelo de Cobranza B2B e Investigación B2B. |
| 1.1 | 2026-07-08 | María Fernanda Herazo | Se agregaron reglas de KYC automático, dispersión (fiducia) y servicio al cliente, con base en los Journeys Colpatria B2B (junio 2026). |
| 1.2 | 2026-07-09 | María Fernanda Herazo| Se agrega la regla de abono parcial (faltaba como tipo de alivio) y se precisa el plazo máximo del congelamiento de intereses (5 días calendario), con base en el Modelo y Proceso de Cobranza B2B. |

---

## Objetivo

Documentar las reglas de negocio que rigen el otorgamiento, uso, mora y recuperación del crédito Fliipa, para mantener consistencia entre comercial, riesgo, cobranza y jurídico.

## Alcance

Este documento cubre las reglas asociadas al cupo, la mora, los alivios y negociaciones, el escalamiento de cobranza y jurídico, y el control de riesgo operativo. No incluye reglas de validación de campos ni de sistema, que se documentan en Funcional.

## Documentos relacionados

- [Negocio](README.md)
- [Flipa - Biblioteca de Conocimiento](../README.md)
- [Mapa Del Conocimiento](../MAPA_DEL_CONOCIMIENTO.md)
- [Onboarding](../ONBOARDING.md)
- [Convenciones](../CONVENCIONES.md)
- [Producto](../producto/README.md)
- [Funcional](../funcional/README.md)
- [Qa](../qa/README.md)
 - [Descripcion Negocio](descripcion_negocio/README.md)
 - [Actores](Actores/README.md)
 - [Procesos](procesos/README.md)
- [Indicadores](indicadores/README.md)

## Contenido

### Reglas del cupo y el crédito

- El cupo es preaprobado y rotativo: al pagar una cuota se libera el monto correspondiente y puede volver a usarse.
- El crédito se difiere hasta en 3 cuotas.
- La aprobación o el rechazo de la solicitud se comunican al cliente en un máximo de 72 horas.
- El cupo se bloquea automáticamente ante atrasos de pago y se reporta a centrales de riesgo según los plazos legales.
- Durante el MVP, el cupo solo puede utilizarse para compras en tiendas D1.

### Reglas de mora y buckets

- La cartera se segmenta en seis estados: pago anticipado (antes del vencimiento), bucket 1 (1-30 días), bucket 2 (31-60 días), bucket 3 (61-90 días), bucket 4 (91-120 días) y bucket 5 (120+ días).
- Preaviso formal de reporte negativo: día 15 en mora.
- Aviso formal de reporte negativo a centrales de información: día 30 en mora.
- Preaviso de proceso jurídico: dentro del bucket 3 (61-90 días de mora).
- Aviso formal de inicio de proceso jurídico: dentro del bucket 4 (91-120 días de mora).
- Radicación de la demanda: a partir del bucket 5 (120+ días de mora).
- El cupo permanece bloqueado durante todo el periodo de mora.

> **Pendiente de validar:** el journey de Colpatria B2B (junio 2026) describe una escalada más corta —bloqueo permanente del cupo y cobro jurídico desde el día 30 de mora—, distinta a los plazos de bucket anteriores (61 a 120+ días). Ambas reglas quedan documentadas hasta que el equipo confirme cuál está vigente. Ver la nota en [Procesos](procesos/09-cobranza.md).

### Reglas de alivios y negociación

**Abono parcial**

- Objetivo: reactivar el compromiso de pago, evitar el escalamiento de la mora (reporte, visita, proceso jurídico) y mantener al cliente vinculado al modelo.
- Se ofrece cuando el cliente responde y demuestra intención real de pago, y el negocio está activo (no cerrado).
- Monto mínimo del abono: 30% del saldo vencido.
- El saldo restante debe quedar con una fecha límite clara (máximo 5 días calendario) o dentro de un acuerdo de pago firmado.
- El abono no libera el cupo hasta que el crédito quede al día.
- Ante incumplimiento del compromiso posterior: se pierde cualquier beneficio otorgado y continúa la cobranza normal (intereses y reporte); si el cliente sigue en mora, se reporta a centrales de riesgo.

**Congelamiento de intereses**

- Disponible desde los 15 días de mora y hasta antes de formalizar el proceso jurídico.
- El congelamiento tiene un plazo máximo de 5 días calendario por solicitud.
- Aplica una sola vez por crédito.
- No se generan intereses durante el periodo acordado.
- Requiere el pago del 100% del saldo vencido.
- Solo se otorga a clientes que demuestren intención de pago.
- Ante incumplimiento: se pierde el beneficio automáticamente, se recalcula la totalidad de los intereses y no se vuelve a otorgar este alivio para ese crédito.

**Condonación**

- Entre 60 y 90 días de mora: condonación parcial de intereses.
- A partir de 90 días de mora: se evalúa la condonación sobre capital.
- Hasta el 50% de los intereses de mora, caso a caso.
- Condonación de capital únicamente en mora mayor a 120 días, según análisis particular.
- Condiciones obligatorias: pago inmediato del saldo acordado, aceptación expresa o acuerdo de pago documentado, y cancelación del cupo.
- No aplica a clientes sin negocio en funcionamiento o con incumplimientos previos de acuerdos.

### Reglas de gestión y escalamiento

- El Comité de Cartera se reúne semanalmente y prioriza casos según: días de mora (con foco en 20 o más días), flujo de caja y tipo de negocio, número de cuotas vencidas, historial y respuesta del cliente, y monto adeudado alto.
- Las visitas de cobro y gestión especial se priorizan a partir de las decisiones del Comité de Cartera.
- Toda interacción con el cliente debe registrarse: correos, llamadas, notificaciones formales, evidencia de promesas de pago, y fotos y ubicación del establecimiento cuando aplique visita.
- Los indicadores de comercial y cobranza deben compartirse entre ambas áreas, para evitar que un cliente quede sin ningún contacto durante el ciclo del crédito.

### Reglas de control de riesgo operativo

- Validación mensual de los datos de contacto (teléfono, WhatsApp y correo obligatorios), para mitigar el riesgo de no poder contactar al cliente.
- Contrato estándar y validación del propietario y la ubicación del negocio, para mitigar el riesgo de que una persona natural actúe como responsable sin la formalidad requerida.
- Visita inicial con registro fotográfico y validación jurídica, para mitigar el riesgo de fraude o negocios ficticios.
- Tableros semanales y alertas automáticas, para evitar la pérdida de control de la cartera.
- Segmentación, automatización y rutas de gestión claras, para evitar la saturación del área de cobranza.

### Tipificación de contactos y gestión

Cada interacción comercial o de cobranza debe clasificarse con una taxonomía estándar:

- **Canal:** llamada, WhatsApp, correo electrónico o visita presencial.
- **Tipo de contacto:** contacto directo, contacto indirecto (contesta un tercero) o número equivocado.
- **Resultado o promesa de pago:** sin compromiso, refinanciación, congelamiento, condonación de intereses, condonación de capital, o gestión comercial (llamada por preaprobación, confirmación de visita de originación, validación de datos, activación de cupo, consulta de beneficios, solicitud de ampliación de cupo).
- **Motivo de contacto (cuando aplica mora):** reducción de ingresos, dificultad con medios de pago, no reconoce el crédito, el crédito lo paga un tercero, olvido, calamidad o accidente, posible fraude, gastos imprevistos, problemas de débito, cliente fallecido, o cliente fuera de la ciudad o el país.

### Reglas de KYC y evaluación de riesgo

- La validación de identidad (KYC) es automática: se apoya en un proveedor externo de biometría, en la consulta a Experian y en el histórico transaccional de D1.
- Si el resultado de la biometría queda "en revisión", un analista de riesgo resuelve el caso manualmente; si es rechazado, el proceso termina y se notifica al cliente.
- La evaluación de riesgo valida automáticamente el score mínimo, la capacidad de endeudamiento y que la tienda habitual declarada coincida con la registrada en el histórico de D1.
- Cualquier validación fallida (cuenta bancaria inválida, score insuficiente, inconsistencia de datos) termina en rechazo automático de la solicitud.

### Reglas de dispersión de fondos

- Los fondos del crédito se administran a través de una fiducia constituida por el aliado de core bancario (Colpatria), que concentra el origen y el retorno del dinero.
- El bono se activa cuando se detecta la compra del cliente en D1; el pago posterior del cliente retorna a la fiducia, no directamente a D1.
- El giro de la fiducia hacia D1 genera un GMF (4x1000) de $4.000 por cada ciclo de $1.000.000 (0,4%); en 12 ciclos anuales sobre el mismo capital, el costo equivale al 4,8% anual. Si la fiducia se constituye en el mismo banco donde ya están los fondos, se ahorra el 4x1000 del fondeo inicial.

### Reglas de servicio al cliente

- El primer nivel de atención lo resuelve un asistente virtual basado en IA; si no puede resolver el caso, escala a un agente humano con el contexto completo de la conversación.
- Los casos críticos (suplantación, desconocimiento de una compra, uso indebido del cupo) requieren validación de identidad y aprobación manual explícita de un agente; no pueden resolverse de forma autónoma por la IA.
- Los casos legales o de PQR (tutela, derecho de petición) se enrutan al área legal con un SLA de respuesta inmediata.
- Todo caso de servicio se registra en el portal administrativo y se mide mediante NPS/CSAT al cierre.

## Fuentes consultadas

- Modelo y Proceso de Cobranza B2B — *Modelo Cobranza/Modelo_de_Cobranza_B2B_.pptx* y *Modelo Cobranza/Modelo y gestion de cobranza.docx*

### Reglas de dispersión de fondos

- Los fondos del crédito se administran a través de una fiducia constituida por el aliado de core bancario (Colpatria), que concentra el origen y el retorno del dinero.
- El bono se activa cuando se detecta la compra del cliente en D1; el pago posterior del cliente retorna a la fiducia, no directamente a D1.
- El giro de la fiducia hacia D1 genera un GMF (4x1000) de $4.000 por cada ciclo de $1.000.000 (0,4%); en 12 ciclos anuales sobre el mismo capital, el costo equivale al 4,8% anual. Si la fiducia se constituye en el mismo banco donde ya están los fondos, se ahorra el 4x1000 del fondeo inicial.

### Reglas de servicio al cliente

- El primer nivel de atención lo resuelve un asistente virtual basado en IA; si no puede resolver el caso, escala a un agente humano con el contexto completo de la conversación.
- Los casos críticos (suplantación, desconocimiento de una compra, uso indebido del cupo) requieren validación de identidad y aprobación manual explícita de un agente; no pueden resolverse de forma autónoma por la IA.
- Los casos legales o de PQR (tutela, derecho de petición) se enrutan al área legal con un SLA de respuesta inmediata.
- Todo caso de servicio se registra en el portal administrativo y se mide mediante NPS/CSAT al cierre.
