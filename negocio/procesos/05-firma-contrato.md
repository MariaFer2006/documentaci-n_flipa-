# 5. Firma de contrato y activación

## Objetivo

Formalizar la aceptación del crédito aprobado mediante la firma electrónica del contrato y el pagaré, validar la identidad del cliente durante el proceso de firma y activar el crédito para que el cliente pueda utilizar su cupo y recibir el bono D1 asociado al producto.

---

## Journey

![Journey Colpatria B2B — página 5](imagenes/page-05.png)

![Journey Colpatria B2B — página 6](imagenes/page-06.png)

**Figura 5. Journey de Firma de Contrato y Activación del Crédito.**

Las imágenes muestran el proceso completo que inicia cuando el crédito ha sido aprobado y finaliza con la activación del cupo y la asignación del bono D1. El flujo incluye la autenticación del cliente, la aceptación de las condiciones del crédito, la firma electrónica del contrato y del pagaré, la validación mediante código de verificación y la activación definitiva del crédito.

---

## Descripción general

Una vez el crédito ha sido aprobado durante la evaluación de riesgo, el Core Bancario habilita la operación para iniciar el proceso de firma electrónica. El cliente recibe una invitación para continuar con la firma, autentica su identidad mediante su NIT y PIN de seguridad, revisa las condiciones del crédito y los documentos legales, y finalmente confirma la firma utilizando un código de verificación enviado a su correo electrónico.

Cuando la firma se completa correctamente, el sistema genera los documentos firmados, activa el crédito, asigna el bono D1 y notifica al cliente que el proceso ha finalizado exitosamente.

---

## Explicación del Journey

### 1. Habilitación del crédito

El proceso inicia cuando el Core Bancario habilita el crédito previamente aprobado para que pueda continuar con la etapa de formalización. A partir de este momento el sistema puede solicitar al cliente la firma del contrato.

---

### 2. Invitación para continuar con la firma

El sistema contacta al cliente mediante los canales definidos (correo electrónico, mensaje o llamada) e informa que el crédito fue aprobado y que puede continuar con la firma electrónica.

Posteriormente se envía un correo con el enlace que permite ingresar nuevamente al proceso.

---

### 3. Autenticación del cliente

Al acceder al enlace, el cliente ingresa su NIT y posteriormente introduce el PIN de seguridad creado durante el proceso de onboarding.

Esta autenticación permite verificar que quien realiza la firma corresponde al titular de la solicitud.

Si el cliente olvidó el PIN, el sistema lo redirige al canal de soporte para recuperar el acceso antes de continuar.

---

### 4. Bienvenida y presentación del crédito

Una vez autenticado, el sistema da la bienvenida al cliente y presenta la información principal del crédito aprobado.

En esta etapa se comunica el monto aprobado y las condiciones generales del producto, incluyendo beneficios asociados al crédito y las condiciones de uso del cupo.

Posteriormente se presenta el detalle completo del crédito, donde el cliente puede revisar información como:

- Cupo aprobado.
- Plan de pagos.
- Valor total a pagar.
- Fecha de pago.
- Tasa de interés.
- Momento en el que podrá utilizar el cupo.

---

### 5. Aceptación de condiciones

Después de revisar la información presentada, el cliente acepta las condiciones del crédito para continuar con la formalización.

Esta aceptación es obligatoria antes de acceder a los documentos legales.

---

### 6. Revisión del contrato y pagaré

El sistema presenta el contrato de crédito y el pagaré para que el cliente pueda leerlos completamente antes de realizar la firma electrónica.

El cliente revisa toda la documentación legal y, una vez conforme con su contenido, continúa con el proceso de validación.

---

### 7. Verificación mediante código

Para completar la firma electrónica, el sistema envía un código de verificación al correo electrónico registrado por el cliente.

El cliente ingresa el código recibido.

- Si el código es válido, la firma continúa normalmente.
- Si el código es incorrecto o expira, el cliente puede solicitar un nuevo envío o contactar al servicio de atención al cliente para recibir asistencia.

---

### 8. Generación de documentos firmados

Una vez validado el código, el sistema genera automáticamente el contrato y el pagaré firmados electrónicamente.

Una copia de ambos documentos es enviada al correo electrónico del cliente como constancia de la operación realizada.

Al mismo tiempo el cliente recibe la confirmación de que la firma fue exitosa.

---

### 9. Activación del bono D1

Con la firma completada, el sistema asigna automáticamente el bono D1 asociado al crédito aprobado.

Posteriormente el cliente recibe una notificación indicando que el bono ya se encuentra disponible dentro de su cuenta.

Desde la aplicación el cliente puede visualizar el código correspondiente al bono para utilizarlo durante sus compras.

---

### 10. Activación definitiva del crédito

Como último paso del proceso, el crédito queda oficialmente activado y disponible para su utilización.

Con esta acción finaliza el proceso de originación y el cliente puede comenzar a utilizar el cupo aprobado junto con el bono D1 asignado.

---

## Reglas de negocio

- El crédito debe haber sido aprobado previamente antes de iniciar la firma.
- El cliente debe autenticarse mediante NIT y PIN para acceder al proceso.
- Si el cliente olvida el PIN, deberá recuperar el acceso antes de continuar.
- La aceptación de las condiciones del crédito es obligatoria.
- El contrato y el pagaré deben visualizarse antes de la firma electrónica.
- La firma solo se completa cuando el código de verificación es validado correctamente.
- Una vez finalizada la firma, el sistema genera automáticamente los documentos legales firmados.
- El bono D1 únicamente se asigna cuando la firma ha sido completada exitosamente.
- Solo después de la activación final el cliente puede utilizar el cupo de crédito.

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
- Crédito activado.
- Cupo disponible para utilización.

---

## Excepciones

- El cliente no accede al enlace enviado por correo.
- El cliente olvidó el PIN.
- El código de verificación es incorrecto o expira.
- El cliente no acepta las condiciones del crédito.
- Se presenta un error durante la generación del contrato o del pagaré.
- No es posible asignar el bono D1.
- Se produce un error durante la activación del crédito.

---

## Consideraciones

- La autenticación mediante NIT y PIN busca garantizar que únicamente el titular pueda acceder al proceso de firma.
- La firma electrónica requiere una validación adicional mediante código enviado al correo electrónico del cliente.
- El contrato y el pagaré se generan automáticamente una vez finaliza la firma.
- El cliente recibe una copia de los documentos firmados para su consulta posterior.
- La asignación del bono D1 y la activación del crédito ocurren únicamente después de completar exitosamente todo el proceso de firma.

---

## Pendientes de validación

> **Pendiente de validar con el dueño del proceso:** confirmar el mecanismo definitivo de firma electrónica y autenticación (correo + PIN u otro mecanismo de no repudio), el número máximo de reenvíos del código de verificación y el tiempo de vigencia del código antes de su expiración.

---

## Fuentes consultadas

- *Journeys Colpatria B2B* (junio de 2026), páginas 5 y 6.
- Documento funcional del proceso de originación.
- Documento de Alcance del Producto.
