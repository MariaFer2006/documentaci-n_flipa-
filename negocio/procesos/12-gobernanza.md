# 8. Cobranza

## Objetivo

Gestionar la recuperación de la cartera vencida mediante un proceso escalonado que inicia con el cobro automático, continúa con acciones preventivas y de negociación, y finaliza con el escalamiento a procesos jurídicos cuando el cliente no regulariza su obligación.

## Journey

El recorrido se explica a continuación en texto narrativo, y la imagen del journey sirve como referencia visual para validar la secuencia operativa.

![Journey Colpatria B2B — página 10](imagenes/page-10.png)

**Figura 12. Journey de Cobranza.**

El journey describe el proceso de gestión de cobranza cuando un cliente no realiza el pago en la fecha de corte. El flujo inicia con intentos automáticos de recaudo, continúa con recordatorios y gestión preventiva, y escala progresivamente hacia negociación, reporte a centrales de riesgo y recuperación jurídica si la mora persiste.

## Descripción general

Cuando el cliente no realiza el pago antes de la fecha de corte, el sistema intenta recaudar automáticamente mediante débito con Druo. Si el recaudo falla, se realizan nuevos intentos durante los primeros días de mora y posteriormente se inicia una gestión preventiva mediante mensajes y llamadas del analista de cobranza.

Si el cliente regulariza el pago, el proceso finaliza. En caso contrario, se ofrecen alternativas de restructuración o acuerdos de pago. Cuando el incumplimiento continúa, la obligación puede reportarse a centrales de riesgo y finalmente escalar a un proceso de recuperación jurídica, conforme a las políticas de cartera definidas por la organización.

## Actores involucrados

| Actor | Rol dentro del proceso |
|--------|------------------------|
| Cliente | Realiza el pago del crédito, responde a las gestiones de cobranza y puede aceptar acuerdos de pago para normalizar su obligación. |
| Sistema de cobranza | Ejecuta automáticamente los intentos de recaudo, envía notificaciones y controla el avance del proceso según los días de mora. |
| Druo | Procesa los débitos automáticos desde la cuenta bancaria registrada por el cliente. |
| Analista de cobranza | Contacta al cliente, identifica la causa de la mora, negocia acuerdos de pago y realiza el seguimiento de la recuperación de la cartera. |
| Plataforma PSE | Permite al cliente realizar el pago mediante el enlace enviado durante la gestión de cobranza. |
| Centrales de riesgo | Reciben el reporte de la obligación cuando la mora cumple las condiciones definidas por la política de crédito. |
| Área Jurídica | Gestiona el proceso de recuperación judicial cuando las acciones de cobranza no logran normalizar la obligación. |

## Explicación del Journey

### 1. Inicio de la mora

El proceso comienza cuando el cliente no realiza el pago correspondiente antes de la fecha de corte establecida para su crédito.

**Sistemas involucrados**

- Plataforma de crédito.
- Sistema de recaudo.

**Información utilizada**

- Fecha de corte.
- Estado del crédito.
- Valor pendiente de pago.

**Resultado**

Se inicia automáticamente el proceso de cobranza.

---

### 2. Primer intento de débito automático (Día 0)

El sistema intenta realizar el recaudo automático mediante Druo utilizando la cuenta bancaria registrada por el cliente.

**Sistemas involucrados**

- Druo.
- Plataforma de recaudo.

**Información utilizada**

- Cuenta bancaria registrada.
- Valor de la cuota.

**Decisión**

¿El débito automático fue exitoso?

**Si la respuesta es Sí**

- El pago queda registrado.
- Finaliza el proceso de cobranza.

**Si la respuesta es No**

- Se programa un nuevo intento de recaudo.

---

### 3. Reintento de débito automático (Días 1 al 5)

Durante los primeros días de mora el sistema realiza un nuevo intento de recaudo automático.

**Sistemas involucrados**

- Druo.
- Plataforma de recaudo.

**Información utilizada**

- Estado del intento anterior.
- Cuenta bancaria registrada.

**Decisión**

¿El reintento fue exitoso?

**Si la respuesta es Sí**

- El pago queda registrado.
- El proceso finaliza.

**Si la respuesta es No**

- Se continúa con la gestión preventiva de cobranza.

---

### 4. Gestión preventiva mediante mensajes (Días 6 al 15)

Cuando los intentos automáticos fallan, el sistema envía una notificación por WhatsApp o SMS solicitando el pago de la cuota e informando las consecuencias de mantener la mora.

**Sistemas involucrados**

- Plataforma de mensajería.
- Sistema de cobranza.

**Información utilizada**

- Estado de mora.
- Datos de contacto.
- Valor pendiente.

**Resultado**

El cliente puede realizar el pago mediante el enlace enviado.

---

### 5. Pago mediante PSE

El cliente puede utilizar el enlace recibido para realizar el pago de la obligación mediante PSE.

**Sistemas involucrados**

- Plataforma PSE.
- Sistema de recaudo.

**Información utilizada**

- Enlace de pago.
- Valor pendiente.

**Decisión**

¿El pago fue exitoso?

**Si la respuesta es Sí**

- El pago queda registrado.
- Finaliza el proceso de cobranza.

**Si la respuesta es No**

- El caso continúa hacia la gestión telefónica.

---

### 6. Gestión telefónica del analista (Días 6 al 15)

El analista de cobranza contacta al cliente para identificar la causa del incumplimiento utilizando un guion estandarizado.

Durante esta etapa se bloquea el cupo de crédito y se informa al cliente sobre las consecuencias de mantener la mora.

**Sistemas involucrados**

- Portal administrativo.
- Sistema de cartera.

**Información utilizada**

- Historial del crédito.
- Días de mora.
- Resultado de las gestiones anteriores.

**Resultado**

Se determina si el cliente acepta negociar la obligación.

---

### 7. Restructuración o acuerdo de pago (Días 16 al 30)

Si el cliente acepta negociar, se establece una restructuración o un acuerdo de pago para normalizar la obligación.

El journey también contempla la posibilidad de aplicar un castigo parcial acompañado de la cancelación del cupo de crédito.

Además, cuando la mora alcanza treinta días, el cupo queda bloqueado de forma permanente.

**Sistemas involucrados**

- Sistema de cartera.

**Información utilizada**

- Capacidad de pago.
- Estado del crédito.
- Política de cartera.

**Resultado**

Se formaliza un acuerdo o el proceso continúa hacia etapas de recuperación más estrictas.

---

### 8. Reporte a centrales de riesgo (Días 16 al 30)

Si el cliente no acepta las condiciones de negociación o continúa sin realizar el pago, la obligación puede ser reportada a las centrales de riesgo conforme a las políticas establecidas.

El journey indica como referencia el reporte después de quince días de mora y antes de alcanzar cuarenta y cinco días de incumplimiento.

**Sistemas involucrados**

- Plataforma de reporte a centrales.

**Información utilizada**

- Días de mora.
- Estado de la obligación.

**Resultado**

Se registra el reporte correspondiente en las centrales de riesgo.

---

### 9. Castigo de cartera y cobro jurídico

Cuando las acciones de cobranza no permiten recuperar la obligación, se aplica el castigo de cartera definido por la organización y el caso se transfiere al proceso de recuperación jurídica.

Con esta actividad concluye el journey de cobranza.

**Sistemas involucrados**

- Sistema de cartera.
- Sistema jurídico.

**Información utilizada**

- Historial de mora.
- Gestión realizada.
- Política de recuperación.

**Resultado**

Se inicia el proceso jurídico para la recuperación de la obligación.

## Reglas de negocio

- El proceso inicia automáticamente cuando el cliente no realiza el pago en la fecha de corte.
- El sistema realiza un intento inicial de recaudo mediante débito automático con Druo.
- Si el recaudo falla, se ejecuta un nuevo intento durante los primeros días de mora.
- La gestión preventiva incluye notificaciones por WhatsApp o SMS antes del escalamiento a gestión humana.
- El cliente puede regularizar la obligación mediante PSE durante la etapa preventiva.
- El analista de cobranza puede negociar restructuraciones o acuerdos de pago.
- El cupo de crédito puede bloquearse durante la gestión de cobranza y quedar bloqueado permanentemente cuando la mora alcanza los criterios definidos por la política.
- El incumplimiento prolongado puede generar reportes a centrales de riesgo.
- Cuando no es posible recuperar la obligación mediante cobranza administrativa, el caso se remite a recuperación jurídica.

## Entradas

- Crédito con pago vencido.
- Fecha de corte.
- Cuenta bancaria registrada.
- Información del cliente.
- Estado de la cartera.

## Salidas

- Pago exitoso del crédito.
- Acuerdo de pago o restructuración.
- Reporte a centrales de riesgo.
- Castigo de cartera.
- Inicio del proceso de recuperación jurídica.

## Excepciones

- El débito automático falla.
- El cliente no realiza el pago mediante PSE.
- El cliente rechaza la negociación propuesta.
- Se aplica bloqueo permanente del cupo por política de mora.
- La obligación debe escalar al proceso jurídico para su recuperación.

## Pendientes de validación

> **Pendiente de validar con el dueño del proceso.**

