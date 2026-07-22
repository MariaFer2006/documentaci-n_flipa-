# 4. Firma de contrato y activación

*Versión corregida para alinear el documento con el estándar de trazabilidad por Slack y el manejo de excepciones acordados en la reunión "Producto: Check-in" del 21 de julio de 2026, y para resolver una inconsistencia de formato en el uso de asteriscos.*

## Objetivo

Formalizar la aceptación del crédito aprobado mediante la firma electrónica del contrato y el pagaré, validar la identidad del cliente durante el proceso de firma, asignar el bono D1 y obtener la aprobación final de Core de Crédito/Originación* que activa el crédito y da inicio al funcionamiento de la calculadora.

> **Referencia comercial:** según el *Modelo Comercial B2B* (portal del cliente), la firma de contrato debe completarse de forma **digital, desde el celular, en minutos** — este journey detalla técnicamente cómo se logra esa experiencia.

---

## Journey

![Journey Colpatria B2B — página 5](imagenes/page-05.png)

![Journey Colpatria B2B — página 6](imagenes/page-06.png)

**Figura 5. Journey de Firma de Contrato y Activación del Crédito.**

En el journey, las cajas moradas ("Lee el contrato y el pagaré", "Se genera contrato y pagaré firmados y se envía copia al cliente vía email" y "Se aprueba el crédito") corresponden a pasos ajustados en junio de 2026 (leyenda "Ajuste · jun 2026"); las demás cajas corresponden a pasos ya existentes del flujo.

*Los elementos marcados con asterisco (\*) corresponden a puntos aún no definidos técnicamente o pendientes de confirmación con el dueño del proceso; se detallan en cada paso y se listan de forma consolidada en "Pendientes de validación".*

---

## Descripción general

Una vez el crédito ha sido aprobado durante la evaluación de riesgo, el Core Bancario habilita la operación para iniciar el proceso de firma electrónica. El cliente recibe una invitación para continuar con la firma, autentica su identidad mediante su NIT y PIN de seguridad (creado durante el onboarding), y recibe la bienvenida a su cuenta junto con una primera comunicación sobre el crédito aprobado (funcionamiento en circuito cerrado, posibilidad de un próximo préstamo mayor, beneficios y congelación del cupo en caso de mora). Después de aceptar las condiciones, el cliente recibe una segunda comunicación con el detalle completo del crédito (cupo, plan de pagos, valor, fecha, tasa e inicio de uso), revisa el contrato y el pagaré, y confirma la firma mediante un código de verificación enviado a su correo electrónico.

Cuando la firma se completa correctamente, el sistema genera los documentos firmados, envía copia al correo del cliente, asigna el bono D1 y notifica al cliente que ya puede visualizar el código del bono desde su cuenta. Finalmente, un actor distinto al Core Bancario —Core de Crédito/Originación*— aprueba el crédito, lo que da inicio al funcionamiento de la calculadora y continúa hacia la recepción y uso del bono.

En consistencia con el estándar de trazabilidad definido para el ciclo del crédito, el sistema notifica por Slack al equipo de operaciones los eventos relevantes de este proceso: firma exitosa, fallas de verificación reiteradas, y cualquier caso en que el crédito firmado no sea finalmente aprobado por Core de Crédito/Originación.

---

## Explicación paso a paso

Cada paso incluye el **proceso** (qué ocurre técnica u operativamente) y un **tiempo estimado** de referencia. Estos tiempos son estimaciones de planeación para UX, consistentes con la meta comercial de que la firma se complete "en minutos, desde el celular" (*Modelo Comercial B2B*), y están pendientes de validar con Producto/Tecnología.

### 1. Habilitación del crédito

**Actor:** Core Bancario.

**Proceso:** Tras la aprobación del crédito en el proceso de KYC/riesgo (documento 3), el Core Bancario habilita la operación correspondiente para que el caso pueda continuar hacia la etapa de formalización. A partir de este momento el sistema puede solicitar al cliente la firma del contrato.

**Resultado:** Crédito habilitado para iniciar la firma. A partir de este momento el sistema puede solicitar al cliente la firma del contrato.

**Tiempo estimado:** Instantáneo (disparado automáticamente al recibir la aprobación de KYC/riesgo).

---

### 2. Solicitud de continuar con la firma del contrato

**Actor:** Web (sistema).

**Sistemas involucrados:** Canales de contacto (correo electrónico, mensaje o llamada)*.

**Proceso:** El sistema contacta al cliente mediante correo electrónico, mensaje o llamada, informando que el crédito fue aprobado y que puede continuar con la firma electrónica.

**Resultado:** Cliente contactado con la invitación a continuar el proceso de firma.

**Tiempo estimado:** Instantáneo del lado del sistema; la recepción depende del canal y es asíncrona.

**Placeholder\*:** no está definida la plataforma técnica exacta usada para este contacto (¿Sendgrid/Zenvia, igual que en onboarding y captación comercial, u otro proveedor para mensaje/llamada?), ni el criterio para elegir entre correo, mensaje o llamada.

---

### 3. Recepción del correo con el enlace

**Actor:** Cliente.

**Proceso:** El cliente recibe el correo enviado en el paso anterior y hace clic en el enlace, lo que lo redirige nuevamente a la plataforma web para retomar el proceso en el punto de la firma.

**Resultado:** El cliente ingresa nuevamente al proceso de firma.

**Tiempo estimado:** Asíncrono (depende de cuándo el cliente revisa su correo).

---

### 4. Autenticación mediante NIT

**Actor:** Cliente.

**Información utilizada:** NIT del cliente.

**Proceso:** El cliente ingresa su NIT como primer factor de autenticación; el sistema lo valida contra el registro creado durante el onboarding.

**Resultado:** Primer factor de autenticación validado.

**Tiempo estimado:** ~15 segundos.

---

### 5. Autenticación mediante PIN de seguridad

**Actor:** Cliente.

**Información utilizada:** PIN de seguridad creado durante el onboarding (paso 12 del documento 2).

**Proceso:** El cliente ingresa su PIN de cuatro dígitos; el sistema lo verifica para confirmar que quien realiza la firma corresponde al titular de la solicitud.

**Resultado:** Segundo factor de autenticación validado.

**Tiempo estimado:** ~10 segundos.

> **Excepción prevista en el journey:** si el cliente olvidó su PIN, el sistema lo redirige al canal de soporte; una vez recuperado el acceso, el cliente vuelve a recibir el correo con el enlace para continuar el proceso.

**Placeholder\*:** no está definido el procedimiento exacto de recuperación de PIN en el canal de soporte (¿validación de identidad adicional?, ¿tiempo de resolución?).

---

### 6. Bienvenida y primera comunicación del crédito aprobado

**Actor:** Web (sistema).

**Proceso:** El sistema da la bienvenida al cliente a su cuenta y comunica el monto del crédito aprobado junto con sus condiciones generales:

- Circuito cerrado.
- El próximo préstamo puede ser mayor.
- Beneficios de sacar el crédito.
- Congelación del cupo si hay retrasos del pago.

**Resultado:** Cliente informado de las condiciones generales del crédito aprobado.

**Tiempo estimado:** ~20-30 segundos de lectura.

**Placeholder\*:** el contenido definitivo y la variabilidad de los mensajes de "circuito cerrado" y "congelación del cupo por mora" aún no están confirmados.

---

### 7. Aceptación de condiciones

**Actor:** Cliente.

**Proceso:** El cliente revisa y acepta las condiciones del crédito comunicadas en el paso anterior. Esta aceptación es obligatoria antes de recibir el detalle completo del crédito; si no acepta, el flujo no permite continuar.

**Resultado:** Condiciones generales aceptadas.

**Tiempo estimado:** ~10 segundos.

---

### 8. Comunicación detallada de las condiciones del crédito

**Actor:** Web (sistema).

**Proceso:** El sistema comunica al cliente el detalle operativo completo del crédito:

- Cupo aprobado.
- Plan de pagos.
- Valor a pagar.
- Fecha de pago.
- Tasa de interés.
- Cuándo podrá usarlo.

**Resultado:** Cliente informado del detalle completo del crédito.

**Tiempo estimado:** ~20-30 segundos de lectura.

---

### 9. Comunicación de siguientes pasos

**Actor:** Web (sistema, vía app).

**Proceso:** La aplicación web comunica al cliente los siguientes pasos del proceso: la firma del contrato y del pagaré.

**Resultado:** Cliente informado de que debe continuar hacia la revisión y firma de los documentos legales.

**Tiempo estimado:** Instantáneo.

---

### 10. Revisión del contrato y pagaré

**Actor:** Cliente.

**Proceso:** El cliente lee el contrato y el pagaré desplegados en la plataforma antes de continuar hacia la verificación de la firma electrónica.

**Resultado:** Contrato y pagaré revisados por el cliente.

**Tiempo estimado:** Variable según la disposición del cliente a leer el documento completo; no contabilizado dentro de un tiempo fijo por tratarse de un paso de lectura libre.

> **Nota (Ajuste · jun 2026):** este paso está marcado en el journey como un paso ajustado en junio de 2026.

---

### 11. Envío del código de verificación

**Actor:** Web (sistema).

**Información utilizada:** Correo electrónico registrado por el cliente.

**Proceso:** El sistema envía un código de verificación al correo electrónico del cliente para completar la firma electrónica. El flujo continúa en la página siguiente del journey (Figura 6).

**Resultado:** Código de verificación enviado.

**Tiempo estimado:** Instantáneo del lado del sistema; recepción asíncrona según el proveedor de correo.

---

### 12. Ingreso del código de verificación

**Actor:** Cliente.

**Proceso:** El cliente ingresa el código recibido; el sistema valida su vigencia y coincidencia. Tiene la opción de reenviar el código si no lo recibe.

**Decisión:** ¿El código ingresado es válido?

- **Exitoso:** el proceso continúa hacia la generación de los documentos firmados.
- **Fallido:** el cliente es dirigido a contactar el servicio al cliente, y el sistema envía una alerta al canal de Slack de operaciones para dar trazabilidad al caso.

**Resultado:** Titularidad del correo confirmada para efectos de la firma.

**Tiempo estimado:** ~30-45 segundos (depende de la entrega del correo).

**Placeholder\*:** no está definido el número máximo de reenvíos del código ni el tiempo de vigencia antes de su expiración, ni si toda falla debe alertar por Slack o solo a partir de cierto número de intentos fallidos.

---

### 13. Gestión de código fallido

**Actor:** Web (sistema) / Cliente.

**Proceso:** Cuando el código es incorrecto o expira, el sistema dirige al cliente a contactar al servicio de atención al cliente (documento 7); desde allí el cliente puede volver a ingresar el código de verificación. La alerta enviada por Slack en el paso 12 permite al equipo de operaciones hacer seguimiento del caso mientras el cliente es atendido.

**Resultado:** Cliente atendido por el canal de soporte para poder continuar con la firma.

**Tiempo estimado:** Depende del tiempo de atención del servicio al cliente (asíncrono, fuera del control directo de este journey).

---

### 14. Generación de documentos firmados

**Actor:** Web (sistema).

**Proceso:** Una vez validado el código, el sistema genera automáticamente el contrato y el pagaré firmados electrónicamente, aplicando el mecanismo de firma/no repudio definido para el producto*, y envía una copia de ambos documentos al correo electrónico del cliente como constancia de la operación.

**Resultado:** Contrato y pagaré firmados electrónicamente, con copia enviada al cliente.

**Tiempo estimado:** Instantáneo (generación automática).

> **Nota (Ajuste · jun 2026):** este paso está marcado en el journey como un paso ajustado en junio de 2026.

**Placeholder\*:** el mecanismo definitivo de firma electrónica y no repudio (más allá de correo + PIN) todavía no está confirmado. El journey señala la necesidad de **revisar referencias de mercado como Dineria** para validar qué mecanismo de no repudio usar; pendiente de definición técnica y legal.

---

### 15. Confirmación de firma exitosa

**Actor:** Cliente.

**Proceso:** El cliente recibe en pantalla la confirmación de que la firma del contrato y el pagaré fue exitosa. El sistema envía adicionalmente una alerta al canal de Slack de operaciones confirmando la firma exitosa, en línea con el estándar de trazabilidad del ciclo del crédito.

**Resultado:** Firma confirmada.

**Tiempo estimado:** Instantáneo.

---

### 16. Asignación del bono D1

**Actor:** Web (sistema).

**Proceso:** El sistema asigna automáticamente el bono D1 asociado al valor del crédito aprobado, quedando disponible para su uso en tienda.

**Resultado:** Bono D1 asignado.

**Tiempo estimado:** Instantáneo.

---

### 17. Notificación del bono asignado

**Actor:** Web (sistema).

**Proceso:** El sistema notifica al cliente, a través de su cuenta, que el bono ya se encuentra asignado y disponible para consulta.

**Resultado:** Cliente notificado de la asignación del bono.

**Tiempo estimado:** Instantáneo.

---

### 18. Visualización del código del bono

**Actor:** Cliente.

**Proceso:** El cliente ingresa a su cuenta y visualiza el código numérico correspondiente al bono, el cual podrá canjear en cualquier tienda D1 (consistente con el paso 6 del portal del cliente descrito en *Modelo Comercial B2B*: "Usa su cupo — código numérico para canjear en cualquier tienda D1").

**Resultado:** Código del bono visible y disponible para su uso.

**Tiempo estimado:** ~10 segundos.

---

### 19. Aprobación del crédito por Core de Crédito/Originación

**Actor:** Core de Crédito/Originación*.

**Proceso:** Este actor —distinto del Core Bancario que habilitó el proceso en el paso 1— aprueba formalmente el crédito ya firmado. Con esta aprobación se da inicio al funcionamiento de la calculadora (documento 5).

**Decisión:** ¿Core de Crédito/Originación aprueba el crédito firmado?

- **Sí:** se da inicio al funcionamiento de la calculadora y el flujo continúa hacia el cierre del journey (paso 20).
- **No:** el sistema envía una alerta al canal de Slack de operaciones para que el equipo revise el caso; **el flujo de resolución para un crédito firmado que no es aprobado por Core de Crédito/Originación no está definido** y debe confirmarse con el dueño del proceso (ver Pendientes de validación).

**Resultado:** Crédito aprobado por Core de Crédito/Originación; inicio del funcionamiento de la calculadora. En caso de no aprobación, caso escalado por Slack a la espera de definición de flujo.

**Tiempo estimado:** Instantáneo, si el proceso es automático (pendiente de confirmar).

> **Nota (Ajuste · jun 2026):** este paso está marcado en el journey como un paso ajustado en junio de 2026.

**Placeholder\*:** no está definida con precisión la diferencia funcional y de sistema entre **Core Bancario** (paso 1) y **Core de Crédito/Originación** (este paso): qué reglas aplica cada uno, si esta aprobación es automática o requiere alguna validación adicional, y qué ocurriría —y qué pasos concretos seguiría el flujo— si Core de Crédito/Originación no aprobara un crédito que ya fue firmado por el cliente.

---

### 20. Cierre del journey

**Proceso:** Con la aprobación de Core de Crédito/Originación finaliza el journey de firma de contrato y activación.

**Resultado:** El flujo continúa hacia la recepción y uso del bono (documento 6, Dispersión de fondos) y hacia el proceso de Calculadora y Cobro del Crédito (documento 5).

**Tiempo estimado:** Instantáneo (transición automática entre procesos).

---

## Reglas de negocio

- El crédito debe haber sido aprobado previamente (KYC + riesgo) antes de iniciar la firma.
- El cliente debe autenticarse mediante NIT y PIN para acceder al proceso.
- Si el cliente olvida el PIN, deberá recuperar el acceso a través del canal de soporte antes de continuar.
- La comunicación de las condiciones del crédito ocurre en dos momentos distintos: una primera comunicación general antes de la aceptación (circuito cerrado, próximo préstamo mayor, beneficios, congelación del cupo por mora) y una segunda comunicación con el detalle operativo después de la aceptación (cupo, plan de pagos, valor, fecha, tasa, inicio de uso).
- La aceptación de las condiciones del crédito es obligatoria antes de acceder al detalle completo y a los documentos legales.
- El contrato y el pagaré deben visualizarse antes de la firma electrónica.
- La firma solo se completa cuando el código de verificación es validado correctamente; si falla, el cliente puede reintentar o contactar al servicio al cliente.
- Una vez finalizada la firma, el sistema genera automáticamente los documentos legales firmados y envía copia al correo del cliente.
- El mecanismo de firma electrónica debe garantizar el no repudio de la operación; se debe validar contra referencias de mercado (p. ej. Dineria) antes de confirmarlo como definitivo.
- El bono D1 únicamente se asigna cuando la firma ha sido completada exitosamente.
- La aprobación final del crédito la realiza Core de Crédito/Originación, un actor distinto del Core Bancario que habilita el proceso al inicio.
- La aprobación de Core de Crédito/Originación da inicio al funcionamiento de la calculadora.
- Según el modelo comercial del producto, todo el proceso de firma debe poder completarse de forma digital, desde el celular, en minutos.
- En línea con el estándar de trazabilidad acordado para el ciclo del crédito, toda falla de verificación, la firma exitosa, y cualquier caso de no aprobación por parte de Core de Crédito/Originación se notifican en tiempo real por el canal de Slack de operaciones.

---

## Entradas

- Crédito aprobado.
- Datos de autenticación del cliente (NIT y PIN).
- Condiciones del crédito.
- Contrato y pagaré.
- Correo electrónico registrado.
- Código de verificación.

---

## Salidas

- Contrato firmado electrónicamente.
- Pagaré firmado electrónicamente.
- Confirmación de firma exitosa.
- Bono D1 asignado.
- Crédito aprobado por Core de Crédito/Originación.
- Inicio del funcionamiento de la calculadora.
- Cupo disponible para utilización.
- Alertas registradas en Slack (fallas de verificación, firma exitosa, no aprobación de Core de Crédito/Originación).

---

## Excepciones

- El cliente no accede al enlace enviado por correo.
- El cliente olvidó el PIN.
- El código de verificación es incorrecto o expira, y el cliente debe contactar al servicio al cliente o reintentar (con alerta Slack asociada).
- El cliente no acepta las condiciones del crédito.
- Se presenta un error durante la generación del contrato o del pagaré.
- No es posible asignar el bono D1.
- Se produce un error durante la aprobación del crédito por parte de Core de Crédito/Originación.
- Core de Crédito/Originación no aprueba un crédito ya firmado por el cliente (caso alertado por Slack; flujo de resolución pendiente de definir).

---

## Consideraciones

- La autenticación mediante NIT y PIN busca garantizar que únicamente el titular pueda acceder al proceso de firma.
- El journey distingue dos actores del Core distintos: Core Bancario, que habilita el proceso al inicio, y Core de Crédito/Originación*, que aprueba el crédito al final y da inicio a la calculadora. Esta distinción es uno de los principales placeholders del proceso.
- La firma electrónica requiere una validación adicional mediante código enviado al correo electrónico del cliente; el mecanismo de no repudio definitivo aún debe validarse contra referencias de mercado como Dineria.
- El contrato y el pagaré se generan automáticamente una vez finaliza la firma, y se envía copia al correo del cliente.
- La asignación del bono D1 y la aprobación final del crédito ocurren únicamente después de completar exitosamente todo el proceso de firma.
- El objetivo comercial (firma digital, desde el celular, en minutos) debe validarse frente a los tiempos estimados detallados en este documento una vez el flujo esté implementado.
- Por consistencia con el proceso de KYC (documento 3), se incorporó la trazabilidad por Slack para los eventos críticos de este journey; sin embargo, a diferencia de KYC —que ya cuenta con un estado de "posible rechazo" y revisión manual definidos— este documento aún no define un flujo concreto para el caso en que Core de Crédito/Originación no apruebe un crédito ya firmado. Se recomienda evaluar con el dueño del proceso si aplica un patrón similar (estado intermedio + revisión manual) para mantener consistencia entre ambos journeys.

---

## Pendientes de validación

> **Pendiente de validar con el dueño del proceso:**
>
> - Confirmar el mecanismo definitivo de firma electrónica y autenticación (correo + PIN u otro mecanismo de no repudio), incluyendo la revisión de referencias de mercado como **Dineria**. *(placeholder — paso 14)*
> - Confirmar la plataforma técnica exacta usada para el contacto inicial del paso 2 (correo, mensaje o llamada) y el criterio de selección de canal. *(placeholder — paso 2)*
> - Confirmar el procedimiento de recuperación de PIN vía canal de soporte. *(placeholder — paso 5)*
> - Confirmar el contenido definitivo y la variabilidad de los mensajes "circuito cerrado" y "congelación del cupo si hay retrasos del pago". *(placeholder — paso 6)*
> - Confirmar el número máximo de reenvíos del código de verificación, el tiempo de vigencia del código antes de su expiración, y si toda falla de verificación debe alertar por Slack o solo a partir de cierto número de intentos. *(placeholder — paso 12)*
> - Confirmar la diferencia funcional y de sistema entre Core Bancario y Core de Crédito/Originación, si la aprobación final (paso 19) es automática o requiere validación adicional, y **definir el flujo de resolución cuando Core de Crédito/Originación no apruebe un crédito ya firmado** (posible alineación con el patrón de "posible rechazo" usado en KYC). *(placeholder — paso 19)*

---

## Fuentes consultadas

- *Journeys Colpatria B2B* (junio de 2026), páginas 5 y 6.
- Documento funcional del proceso de originación.
- Documento de Alcance del Producto.
- *Modelo Comercial B2B.pptx* (Sumz, junio de 2026) — diapositiva 8, "El portal: simple, digital, en WhatsApp".
- Estándar de trazabilidad por Slack y manejo de excepciones (posible rechazo/revisión manual) acordado en la reunión "Producto: Check-in" (21 de julio de 2026), aplicado por consistencia a este documento.
