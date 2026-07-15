# 2. Onboarding digital

## Objetivo

Registrar los datos iniciales del cliente empresarial mediante un proceso completamente digital, identificar su cupo preaprobado con base en información transaccional de D1, recopilar la información básica del representante legal y validar el número de teléfono mediante un código OTP antes de continuar con el proceso de validación de identidad (KYC).

---

## Journey

![Journey Colpatria B2B — página 2](imagenes/page-02.png)

**Figura 2. Journey de Onboarding Digital.**

Este journey describe el proceso inicial que realiza el cliente desde que recibe la invitación al producto hasta completar la validación del número telefónico mediante un código OTP. Su propósito es registrar la información básica del cliente, identificar el cupo preaprobado y preparar la información necesaria para continuar con la validación de identidad (KYC).

---

## Descripción general

El onboarding digital es el primer contacto del cliente con el producto. El proceso inicia con el envío de una invitación personalizada y continúa con el registro de la información básica del negocio y del representante legal. Durante este recorrido el sistema identifica el cupo preaprobado utilizando información transaccional previamente disponible y valida el número de teléfono mediante un código OTP. Una vez finalizada esta etapa, el cliente continúa con el proceso de validación de identidad (KYC).

---

## Explicación paso a paso

### 1. Recepción del enlace de invitación

El sistema envía al cliente un enlace único de invitación por medio de los canales habilitados (correo electrónico o WhatsApp). Este enlace permite iniciar el proceso de onboarding de forma segura.

---

### 2. Ingreso del documento de identificación

El cliente abre el enlace recibido e ingresa su NIT o número de cédula, según corresponda. Esta información permite identificar al cliente dentro del proceso.

---

### 3. Identificación del cupo preaprobado

De manera automática, el sistema identifica el cupo preaprobado del cliente utilizando los criterios definidos a partir de la información transaccional disponible en D1.

---

### 4. Registro de ubicación

El cliente registra la ciudad o municipio y la dirección donde desarrolla su actividad comercial.

---

### 5. Clasificación del tipo de cliente

El sistema determina si el cliente continúa el flujo como NIT o como CC.

> **Pendiente de validación:** el journey muestra que la rama **NIT** pasa por el reconocimiento del representante legal, mientras que la rama **CC** continúa directamente hacia la aceptación de términos y condiciones. Debido a que esta lógica resulta poco intuitiva, debe confirmarse con el dueño del proceso antes de considerarse definitiva.

---

### 6. Reconocimiento del representante legal

(Según la rama indicada en el journey).

El cliente confirma que actúa como representante legal y el sistema realiza una validación interna antes de continuar con el proceso.

---

### 7. Aceptación de términos y condiciones

El cliente acepta los términos y condiciones del producto para continuar con el proceso de originación.

---

### 8. Registro de información del representante legal

El cliente proporciona la información requerida del representante legal, incluyendo el documento de identidad y el número de teléfono.

---

### 9. Envío del código OTP

El sistema genera y envía un código OTP al número de teléfono registrado para validar que el contacto pertenece al cliente.

---

### 10. Validación del código OTP

El cliente ingresa el código recibido.

Si el código es válido, el onboarding continúa hacia el proceso de Validación de Identidad (KYC).

Si el código no es válido o no llega al cliente, el sistema permite solicitar un nuevo envío del código.

---

## Reglas de negocio

- Cada cliente debe iniciar el proceso mediante un enlace único e individual.
- El cupo preaprobado se identifica utilizando información transaccional disponible de D1.
- La aceptación de términos y condiciones es obligatoria para continuar.
- El número telefónico debe validarse mediante un código OTP.
- Si el código OTP no es válido, el cliente puede solicitar un nuevo envío.
- Una vez validado el teléfono, el cliente continúa con el proceso de Validación de Identidad (KYC).
- La lógica de la bifurcación entre NIT y CC debe validarse con el dueño del proceso.

---

## Entradas

- Correo electrónico del cliente.
- Enlace único de invitación.
- NIT o número de cédula.
- Ciudad o municipio.
- Dirección.
- Documento del representante legal.
- Número de teléfono.
- Código OTP.

---

## Salidas

- Cliente identificado.
- Cupo preaprobado identificado.
- Información básica del representante legal registrada.
- Número telefónico validado.
- Solicitud preparada para continuar con el proceso de Validación de Identidad (KYC).

---

## Excepciones

- El cliente no abre el enlace de invitación.
- El cliente abandona el proceso antes de finalizar el registro.
- El cliente no acepta los términos y condiciones.
- El código OTP es incorrecto o expira.
- El cliente solicita un nuevo envío del código OTP.
- La lógica de la bifurcación NIT/CC continúa pendiente de validación funcional.

---

## Consideraciones

- El journey estima una duración aproximada de tres minutos.
- La identificación del cupo preaprobado corresponde únicamente a una validación preliminar.
- La validación de identidad (KYC), biometría, cuenta bancaria y evaluación de riesgo pertenecen a procesos posteriores y no hacen parte de este journey.
- Este proceso depende de los servicios de mensajería utilizados para el envío de invitaciones y códigos OTP.

---

## Notas

- La duración del proceso es una referencia de diseño y puede variar según la conexión o el dispositivo del cliente.
- El límite de reintentos para el código OTP no se encuentra documentado y deberá validarse con el dueño del proceso.
- La lógica de la decisión entre NIT y CC deberá confirmarse antes de la versión final de la documentación.

---

## Fuentes consultadas

- *Journeys Colpatria B2B* (junio de 2026), página 2.
- Documentación de integraciones (Sendgrid y Zenvia).
- Documento de Alcance del Producto.
