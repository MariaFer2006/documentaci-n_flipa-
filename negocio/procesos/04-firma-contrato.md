# 4. Firma de contrato y activación

## Objetivo

Formalizar la aceptación del crédito aprobado mediante la firma electrónica del contrato y el pagaré, validar la identidad del cliente durante el proceso de firma, asignar el bono D1 y obtener la aprobación final de Core de Crédito/Originación que activa el crédito y da inicio al funcionamiento de la calculadora.

---

## Journey

![Journey Colpatria B2B — página 5](imagenes/page-05.png)

![Journey Colpatria B2B — página 6](imagenes/page-06.png)

**Figura 5. Journey de Firma de Contrato y Activación del Crédito.**

En el journey, las cajas moradas ("Lee el contrato y el pagaré", "Se genera contrato y pagaré firmados y se envía copia al cliente vía email" y "Se aprueba el crédito") corresponden a pasos ajustados en junio de 2026 (leyenda "Ajuste · jun 2026"); las demás cajas corresponden a pasos ya existentes del flujo.

---

## Descripción general

Una vez el crédito ha sido aprobado durante la evaluación de riesgo, el Core Bancario habilita la operación para iniciar el proceso de firma electrónica. El cliente recibe una invitación para continuar con la firma, autentica su identidad mediante su NIT y PIN de seguridad, y recibe la bienvenida a su cuenta junto con una primera comunicación sobre el crédito aprobado (funcionamiento en circuito cerrado, posibilidad de un próximo préstamo mayor, beneficios y congelación del cupo en caso de mora). Después de aceptar las condiciones, el cliente recibe una segunda comunicación con el detalle completo del crédito (cupo, plan de pagos, valor, fecha, tasa e inicio de uso), revisa el contrato y el pagaré, y confirma la firma mediante un código de verificación enviado a su correo electrónico.

Cuando la firma se completa correctamente, el sistema genera los documentos firmados, envía copia al correo del cliente, asigna el bono D1 y notifica al cliente que ya puede visualizar el código del bono desde su cuenta. Finalmente, un actor distinto al Core Bancario —Core de Crédito/Originación— aprueba el crédito, lo que da inicio al funcionamiento de la calculadora y continúa hacia la recepción y uso del bono.

---

## Explicación del Journey

### 1. Habilitación del crédito

**Actor:** Core Bancario.

**Resultado:** El Core Bancario habilita el crédito previamente aprobado para que pueda continuar con la etapa de formalización. A partir de este momento el sistema puede solicitar al cliente la firma del contrato.

---

### 2. Solicitud de continuar con la firma del contrato

**Actor:** Web (sistema).

**Sistemas involucrados:** Canales de contacto (correo electrónico, mensaje o llamada).

**Resultado:** El sistema contacta al cliente mediante correo electrónico, mensaje o llamada e informa que el crédito fue aprobado y que puede continuar con la firma electrónica.

---

### 3. Recepción del correo con el enlace

**Actor:** Cliente.

**Resultado:** El cliente recibe un correo con el enlace que permite ingresar nuevamente al proceso de firma.

---

### 4. Autenticación mediante NIT

**Actor:** Cliente.

**Información utilizada:** NIT del cliente.

**Resultado:** El cliente ingresa su NIT como primer factor de autenticación.

---

### 5. Autenticación mediante PIN de seguridad

**Actor:** Cliente.

**Información utilizada:** PIN de seguridad creado durante el onboarding.

**Resultado:** El cliente ingresa su PIN para verificar que quien realiza la firma corresponde al titular de la solicitud.

> **Excepción prevista en el journey:** si el cliente olvidó su PIN, el sistema lo redirige al canal de soporte; una vez recuperado el acceso, el cliente vuelve a recibir el correo con el enlace para continuar el proceso.

---

### 6. Bienvenida y primera comunicación del crédito aprobado

**Actor:** Web (sistema).

**Resultado:** El sistema da la bienvenida al cliente a su cuenta y comunica el monto del crédito aprobado junto con sus condiciones generales, incluyendo:

- Circuito cerrado.
- El próximo préstamo puede ser mayor.
- Beneficios de sacar el crédito.
- Congelación del cupo si hay retrasos del pago.

---

### 7. Aceptación de condiciones

**Actor:** Cliente.

**Resultado:** El cliente acepta las condiciones del crédito para continuar con la formalización. Esta aceptación es obligatoria antes de recibir el detalle completo del crédito.

---

### 8. Comunicación detallada de las condiciones del crédito

**Actor:** Web (sistema).

**Resultado:** El sistema comunica al cliente el detalle completo del crédito:

- Cupo aprobado.
- Plan de pagos.
- Valor a pagar.
- Fecha de pago.
- Tasa de interés.
- Cuándo podrá usarlo.

---

### 9. Comunicación de siguientes pasos

**Actor:** Web (sistema, vía app).

**Resultado:** La aplicación comunica al cliente los siguientes pasos: la firma del contrato y del pagaré.

---

### 10. Revisión del contrato y pagaré

**Actor:** Cliente.

**Resultado:** El cliente lee el contrato y el pagaré antes de continuar hacia la verificación de la firma electrónica.

> **Nota (Ajuste · jun 2026):** este paso está marcado en el journey como un paso ajustado en junio de 2026.

---

### 11. Envío del código de verificación

**Actor:** Web (sistema).

**Información utilizada:** Correo electrónico registrado por el cliente.

**Resultado:** El sistema envía un código de verificación al correo electrónico del cliente para completar la firma electrónica. El flujo continúa en la página siguiente del journey.

---

### 12. Ingreso del código de verificación

**Actor:** Cliente.

**Decisión:** ¿El código ingresado es válido?

- **Exitoso:** el proceso continúa hacia la generación de los documentos firmados.
- **Fallido:** el cliente es dirigido a contactar el servicio al cliente.

**Resultado:** El cliente tiene la opción de reenviar el código si no lo recibe.

---

### 13. Gestión de código fallido

**Actor:** Web (sistema) / Cliente.

**Resultado:** Cuando el código es incorrecto o expira, el sistema dirige al cliente a contactar al servicio de atención al cliente; desde allí el cliente puede volver a ingresar el código de verificación.

---

### 14. Generación de documentos firmados

**Actor:** Web (sistema).

**Resultado:** Una vez validado el código, el sistema genera automáticamente el contrato y el pagaré firmados electrónicamente y envía una copia de ambos documentos al correo electrónico del cliente como constancia de la operación.

> **Nota (Ajuste · jun 2026):** este paso está marcado en el journey como un paso ajustado en junio de 2026.

---

### 15. Confirmación de firma exitosa

**Actor:** Cliente.

**Resultado:** El cliente recibe la confirmación de que la firma del contrato y el pagaré fue exitosa.

---

### 16. Asignación del bono D1

**Actor:** Web (sistema).

**Resultado:** El sistema asigna automáticamente el bono D1 asociado al crédito aprobado.

---

### 17. Notificación del bono asignado

**Actor:** Web (sistema).

**Resultado:** El cliente recibe, a través de su cuenta, la notificación de que el bono ya se encuentra asignado.

---

### 18. Visualización del código del bono

**Actor:** Cliente.

**Resultado:** El cliente ve, a través de su cuenta, el código correspondiente al bono para utilizarlo durante sus compras.

---

### 19. Aprobación del crédito por Core de Crédito/Originación

**Actor:** Core de Crédito/Originación.

**Resultado:** Este actor —distinto del Core Bancario que habilitó el proceso en el paso 1— aprueba el crédito. Con esta aprobación se da inicio al funcionamiento de la calculadora.

> **Nota (Ajuste · jun 2026):** este paso está marcado en el journey como un paso ajustado en junio de 2026.

---

### 20. Cierre del journey

**Resultado:** Con la aprobación del crédito finaliza el journey de firma de contrato y activación. El flujo continúa hacia la recepción y uso del bono, y hacia el proceso de Calculadora y Cobro del Crédito.

---

## Reglas de negocio

- El crédito debe haber sido aprobado previamente antes de iniciar la firma.
- El cliente debe autenticarse mediante NIT y PIN para acceder al proceso.
- Si el cliente olvida el PIN, deberá recuperar el acceso a través del canal de soporte antes de continuar.
- La comunicación de las condiciones del crédito ocurre en dos momentos distintos: una primera comunicación general antes de la aceptación (circuito cerrado, próximo préstamo mayor, beneficios, congelación del cupo por mora) y una segunda comunicación con el detalle operativo después de la aceptación (cupo, plan de pagos, valor, fecha, tasa, inicio de uso).
- La aceptación de las condiciones del crédito es obligatoria antes de acceder al detalle completo y a los documentos legales.
- El contrato y el pagaré deben visualizarse antes de la firma electrónica.
- La firma solo se completa cuando el código de verificación es validado correctamente; si falla, el cliente puede reintentar o contactar al servicio al cliente.
- Una vez finalizada la firma, el sistema genera automáticamente los documentos legales firmados y envía copia al correo del cliente.
- El bono D1 únicamente se asigna cuando la firma ha sido completada exitosamente.
- La aprobación final del crédito la realiza Core de Crédito/Originación, un actor distinto del Core Bancario que habilita el proceso al inicio.
- La aprobación de Core de Crédito/Originación da inicio al funcionamiento de la calculadora.

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

---

## Excepciones

- El cliente no accede al enlace enviado por correo.
- El cliente olvidó el PIN.
- El código de verificación es incorrecto o expira, y el cliente debe contactar al servicio al cliente o reintentar.
- El cliente no acepta las condiciones del crédito.
- Se presenta un error durante la generación del contrato o del pagaré.
- No es posible asignar el bono D1.
- Se produce un error durante la aprobación del crédito por parte de Core de Crédito/Originación.

---

## Consideraciones

- La autenticación mediante NIT y PIN busca garantizar que únicamente el titular pueda acceder al proceso de firma.
- El journey distingue dos actores del Core distintos: Core Bancario, que habilita el proceso al inicio, y Core de Crédito/Originación, que aprueba el crédito al final y da inicio a la calculadora.
- La firma electrónica requiere una validación adicional mediante código enviado al correo electrónico del cliente.
- El contrato y el pagaré se generan automáticamente una vez finaliza la firma, y se envía copia al correo del cliente.
- La asignación del bono D1 y la aprobación final del crédito ocurren únicamente después de completar exitosamente todo el proceso de firma.

---

## Pendientes de validación

> **Pendiente de validar con el dueño del proceso:**
>
> - Confirmar el mecanismo definitivo de firma electrónica y autenticación (correo + PIN u otro mecanismo de no repudio).
> - Confirmar el número máximo de reenvíos del código de verificación y el tiempo de vigencia del código antes de su expiración.
> - Confirmar la diferencia funcional y de sistema entre Core Bancario y Core de Crédito/Originación.
> - Confirmar el contenido definitivo y la variabilidad de los mensajes "circuito cerrado" y "congelación del cupo si hay retrasos del pago".

---

## Fuentes consultadas

- *Journeys Colpatria B2B* (junio de 2026), páginas 5 y 6.
- Documento funcional del proceso de originación.
- Documento de Alcance del Producto.
