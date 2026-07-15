# 7. Servicio al cliente

## Objetivo

Gestionar las solicitudes, consultas, incidentes y reclamaciones de los clientes mediante un proceso de atención que prioriza la resolución en el primer contacto a través de inteligencia artificial y, cuando es necesario, escala el caso a un agente humano o al área especializada correspondiente.

## Journey

El recorrido se explica a continuación en texto narrativo, y la imagen del journey sirve como referencia visual para validar la secuencia operativa.

![Journey Colpatria B2B — página 9](imagenes/page-09.png)

**Figura 11. Journey de Servicio al Cliente.**

El journey describe el flujo de atención al cliente desde el momento en que se recibe una solicitud hasta su resolución y cierre. El proceso combina atención automatizada mediante inteligencia artificial con la intervención de agentes humanos y áreas especializadas cuando el caso requiere validaciones adicionales o tratamiento especializado.

## Descripción general

Cuando un cliente necesita soporte puede comunicarse mediante WhatsApp, correo electrónico o llamada telefónica. Inicialmente el caso es atendido por un asistente basado en inteligencia artificial, encargado de clasificar la solicitud e intentar resolverla durante el primer contacto.

Si la IA no logra resolver el caso, este se transfiere a un agente humano junto con todo el contexto recopilado. Dependiendo de la naturaleza de la solicitud, el agente puede resolverla directamente o escalarla hacia las áreas responsables, como Riesgo, Cobranza, Tecnología o Legal/PQR. Una vez solucionado el requerimiento, el caso se registra como cerrado en el sistema administrativo y el cliente recibe la respuesta correspondiente.

## Explicación del Journey

### 1. Contacto inicial del cliente

El proceso inicia cuando el cliente se comunica con el servicio de atención mediante WhatsApp, correo electrónico o una llamada telefónica. El sistema registra automáticamente la solicitud y genera un caso para su gestión.

**Actor:** Cliente.

**Sistemas involucrados:**

- Canales de atención.
- Portal administrativo.

**Información utilizada:**

- Datos del cliente.
- Canal de contacto.
- Motivo de la solicitud.

**Resultado:**

- Se crea el caso y continúa hacia la clasificación automática.

---

### 2. Clasificación y atención mediante IA

La inteligencia artificial recibe el caso, identifica el tipo de solicitud y consulta el contexto disponible del cliente para intentar resolverla durante el primer contacto.

**Actor:** Inteligencia Artificial.

**Sistemas involucrados:**

- Motor de IA.
- Base de conocimiento.
- Portal administrativo.

**Información utilizada:**

- Historial del cliente.
- Clasificación del caso.
- Reglas de atención.

**Decisión:**

¿La IA logra resolver el caso?

**Si la respuesta es Sí:**

- La IA genera la respuesta.
- El caso continúa hacia el cierre.

**Si la respuesta es No:**

- El caso es escalado automáticamente a un agente humano junto con todo el contexto recopilado.

---

### 3. Recepción del caso por el agente humano

Cuando la IA no logra resolver el requerimiento, un agente humano recibe el caso con toda la información recopilada durante la atención inicial.

El journey identifica especialmente algunos casos críticos, entre ellos:

- Suplantación de identidad.
- Desconocimiento de compra.
- Uso indebido del cupo.

Para estos escenarios el agente debe validar la identidad del cliente antes de aprobar cualquier gestión.

**Actor:** Agente humano.

**Sistemas involucrados:**

- Portal administrativo.

**Información utilizada:**

- Historial del caso.
- Conversación previa con la IA.
- Datos del cliente.
- Resultado de la validación de identidad.

**Resultado:**

- El agente determina el tipo de caso y define el tratamiento correspondiente.

---

### 4. Clasificación del tipo de caso

Después de revisar la información, el agente identifica la naturaleza del requerimiento.

El journey contempla tres posibles escenarios:

#### Caso estándar

Corresponde a solicitudes operativas que el agente puede resolver directamente.

**Resultado:**

- El agente resuelve el caso de manera autónoma.

#### Caso especializado

Cuando la solicitud requiere intervención técnica o funcional.

Puede escalarse hacia áreas como:

- Riesgo.
- Cobranza.
- Tecnología (TI).

Estas áreas analizan el caso y generan la solución correspondiente.

#### Caso Legal o PQR

Si la solicitud corresponde a una tutela, derecho de petición o una PQR, el flujo se dirige al proceso Legal/PQR, donde se administra bajo los tiempos de respuesta (SLA) definidos por la organización.

---

### 5. Resolución del caso

Una vez resuelto el requerimiento, ya sea por el agente humano o por el área especializada, la solución se registra en el sistema administrativo.

Posteriormente se comunica la respuesta al cliente y se realiza el cierre formal del caso.

Durante este cierre también se registran las métricas de satisfacción (NPS/CSAT) indicadas en el journey.

**Resultado:**

- Caso cerrado.
- Cliente informado.
- Registro administrativo actualizado.

---

### 6. Recepción de la solución por el cliente

Finalmente el cliente recibe la respuesta mediante el canal correspondiente y el proceso de atención concluye.

## Reglas de negocio

- Todo contacto debe registrarse como un caso dentro del portal administrativo.
- La inteligencia artificial siempre realiza el primer intento de resolución.
- Si la IA no resuelve el caso, este debe escalarse con todo el contexto disponible.
- Los casos críticos requieren validación de identidad y aprobación manual por parte de un agente.
- Los casos Legal/PQR deben seguir el flujo especializado y cumplir los SLA establecidos.
- Todos los casos finalizados deben registrarse en el sistema administrativo.
- Al cierre del caso se registran las métricas de satisfacción (NPS/CSAT).

## Entradas

- Solicitud del cliente.
- Canal de atención (WhatsApp, correo o llamada).
- Historial del cliente.
- Información del caso.
- Base de conocimiento para IA.

## Salidas

- Caso resuelto.
- Cliente notificado.
- Caso cerrado en el portal administrativo.
- Registro de métricas NPS/CSAT.
- Escalamiento al área correspondiente cuando aplique.

## Excepciones

- La IA no logra resolver el caso.
- Se detecta un caso crítico que requiere validación manual.
- El caso corresponde a un proceso Legal/PQR.
- El requerimiento debe ser atendido por Riesgo, Cobranza o Tecnología.
- Se requiere seguimiento adicional antes del cierre definitivo.

## Pendientes de validación

> **Pendiente de validar con el dueño del proceso.**
