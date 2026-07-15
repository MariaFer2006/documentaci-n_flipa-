# 2. Onboarding digital

## Objetivo

Registrar al cliente empresarial mediante un proceso completamente digital, identificar su cupo preaprobado utilizando la información transaccional disponible, recopilar la información básica del negocio y del representante legal, validar los mecanismos de autenticación y seguridad, realizar la validación biométrica, registrar la cuenta bancaria para el débito automático y recopilar la documentación necesaria para dejar la solicitud preparada para el análisis crediticio y continuar con el proceso de Validación de Identidad (KYC).

---

## Journey

![Journey Colpatria B2B — página 2](imagenes/page-02.png)

**Figura 2. Journey de Onboarding Digital (Parte 1).**

![Journey Colpatria B2B — página 3](imagenes/page-03.png)

**Figura 3. Journey de Onboarding Digital (Parte 2).**


---

# Descripción general

El onboarding digital constituye el primer contacto del cliente con el producto y concentra todas las actividades necesarias para crear su perfil dentro de la plataforma.

El proceso inicia cuando el cliente recibe una invitación personalizada para acceder al producto. A partir de este momento registra la información básica del negocio, suministra los datos del representante legal y valida el número telefónico mediante un código OTP. Posteriormente configura un PIN de seguridad, realiza la validación biométrica utilizando un proveedor externo, registra la cuenta bancaria desde la cual se autorizarán los débitos automáticos, adjunta la documentación bancaria requerida y selecciona su localidad habitual de compra. Finalmente, toda la información recopilada es enviada para el análisis de crédito, dejando la solicitud preparada para continuar con el proceso de Validación de Identidad (KYC).

---

# Explicación paso a paso

## 1. Recepción de la invitación

El sistema envía al cliente un enlace personalizado por correo electrónico o WhatsApp para iniciar el proceso de onboarding digital.

Este enlace identifica al cliente y permite iniciar el proceso de forma segura.

---

## 2. Registro del documento de identificación

El cliente accede al enlace e ingresa su NIT o número de cédula, según corresponda.

Esta información permite identificar el tipo de cliente y recuperar la información previamente disponible.

---

## 3. Identificación del cupo preaprobado

Con la información registrada, el sistema consulta la información transaccional disponible en D1 para calcular el cupo preaprobado que podrá ofrecer al cliente.

Esta evaluación corresponde únicamente a una preaprobación y no representa la aprobación definitiva del crédito.

---

## 4. Registro de ubicación

El cliente registra la ciudad o municipio y la dirección donde desarrolla su actividad comercial.

Esta información hace parte del perfil inicial del negocio.

---

## 5. Clasificación del tipo de cliente

El sistema determina si el flujo continuará como Persona Jurídica (NIT) o Persona Natural (CC).

> **Pendiente de validación:** La lógica mostrada en el journey debe ser revisada con el dueño del proceso para confirmar el comportamiento definitivo del flujo.

---

## 6. Validación del representante legal

Cuando el flujo corresponde a una empresa, el sistema solicita la validación del representante legal antes de continuar.

---

## 7. Aceptación de términos y condiciones

El cliente acepta los términos y condiciones del producto.

Esta aceptación es obligatoria para continuar con la solicitud.

---

## 8. Registro del representante legal

El cliente registra la información solicitada del representante legal, incluyendo documento de identidad y número de teléfono.

---

## 9. Envío del código OTP

El sistema genera un código OTP y lo envía al número telefónico registrado.

Este código permitirá validar la titularidad del número.

---

## 10. Validación del código OTP

El cliente ingresa el código recibido.

Si el código es correcto el proceso continúa.

Si el código no es válido o no llega, el cliente puede solicitar un nuevo envío.

---

## 11. Creación del PIN de seguridad

Una vez validado el teléfono, el cliente crea un PIN de cuatro dígitos.

El sistema verifica que el PIN cumpla las políticas de seguridad definidas para evitar combinaciones inseguras.

---

## 12. Confirmación de creación de la cuenta

Después de registrar correctamente el PIN, el sistema informa que la cuenta del cliente ha sido creada exitosamente y habilita la siguiente etapa del proceso.

---

## 13. Envío del enlace para biometría

El sistema genera un enlace seguro hacia el proveedor externo encargado de realizar la validación biométrica y lo envía al cliente.

La biometría se realiza fuera de la aplicación.

---

## 14. Validación biométrica

El cliente realiza el proceso biométrico mediante el proveedor externo.

El resultado puede ser:

- Aprobado.
- En revisión.
- Rechazado.

---

## 15. Gestión del resultado biométrico

Si la biometría es aprobada, el cliente continúa automáticamente.

Si queda en revisión, un analista de riesgo evalúa el caso.

Si la biometría es rechazada, la solicitud finaliza.

---

## 16. Revisión manual por analista de riesgo

Cuando el resultado queda en revisión, el analista de riesgo revisa la evidencia disponible.

Si aprueba el caso, el flujo continúa.

Si rechaza la solicitud, el proceso finaliza.

---

## 17. Vinculación de la cuenta bancaria

El cliente selecciona la entidad financiera e ingresa la cuenta bancaria que utilizará para autorizar el débito automático.

La información es validada mediante la integración con Druo.

---

## 18. Carga de documentación bancaria

El cliente adjunta:

- Certificación bancaria.
- Extractos bancarios correspondientes a los últimos tres meses.

Esta documentación será utilizada durante el análisis crediticio.

---

## 19. Selección de localidad habitual

El cliente selecciona la localidad donde realiza habitualmente sus compras.

Esta información complementa el perfil comercial utilizado durante la evaluación del crédito.

---

## 20. Envío al análisis de crédito

Una vez completado el onboarding, el sistema envía toda la información recopilada al equipo encargado del análisis de crédito.

Se informa al cliente que deberá esperar la respuesta del estudio crediticio.

---

## 21. Continuación hacia KYC

Después del análisis inicial, la solicitud continúa con el proceso de Validación de Identidad (KYC), donde se realizan las verificaciones correspondientes antes de la originación del crédito.

---

# Reglas de negocio

- Cada cliente inicia el proceso mediante un enlace único.
- El cupo preaprobado se calcula utilizando información transaccional de D1.
- La aceptación de términos y condiciones es obligatoria.
- El número telefónico debe validarse mediante OTP.
- El cliente puede solicitar un nuevo código OTP cuando sea necesario.
- El cliente debe crear un PIN de cuatro dígitos.
- La biometría se realiza mediante un proveedor externo.
- Si la biometría queda en revisión, el caso es evaluado por un analista de riesgo.
- Si la biometría es rechazada, la solicitud finaliza.
- La cuenta bancaria debe validarse antes de autorizar el débito automático.
- El cliente debe adjuntar certificación bancaria y extractos bancarios.
- Solo las solicitudes que completen exitosamente el onboarding continúan hacia KYC.

---

# Entradas

- Enlace de invitación.
- Correo electrónico.
- Número de teléfono.
- Documento de identidad.
- NIT (cuando aplique).
- Ciudad.
- Dirección.
- Información del representante legal.
- Código OTP.
- PIN de seguridad.
- Cuenta bancaria.
- Certificación bancaria.
- Extractos bancarios.
- Localidad habitual de compra.

---

# Salidas

- Cliente registrado.
- Cuenta creada.
- Cupo preaprobado identificado.
- Teléfono validado.
- PIN registrado.
- Biometría completada.
- Cuenta bancaria vinculada.
- Documentación bancaria registrada.
- Solicitud enviada para análisis de crédito.
- Proceso preparado para continuar con KYC.

---

# Excepciones

- El cliente no abre la invitación.
- El cliente abandona el proceso.
- No acepta los términos y condiciones.
- El código OTP expira o es incorrecto.
- La biometría es rechazada.
- La biometría queda en revisión y posteriormente es rechazada.
- Error durante la validación biométrica.
- Error en la validación de la cuenta bancaria.
- No se adjunta la documentación bancaria.
- Error de integración con Druo.
- Error de integración con el proveedor biométrico.

---

# Consideraciones

- El onboarding corresponde a un proceso completamente digital.
- La identificación del cupo corresponde únicamente a una preaprobación.
- La biometría se realiza mediante un proveedor externo.
- La validación manual únicamente ocurre cuando la biometría queda en revisión.
- La documentación bancaria hace parte de los insumos para el análisis crediticio.
- El onboarding finaliza cuando la solicitud queda preparada para continuar con KYC.

---

# Notas

- Los tiempos de aprobación, número de cuotas y demás parámetros operativos pueden modificarse durante la evolución del producto.
- La lógica de la bifurcación entre NIT y CC debe validarse con el dueño del proceso.
- La integración con proveedores externos puede variar según la evolución del producto.

---

# Fuentes consultadas

- *Journeys Colpatria B2B* (junio de 2026), páginas 2 y 3.
- Documentación de integraciones.
- Documento de Alcance del Producto.
- Documento de Alcance del Producto.
