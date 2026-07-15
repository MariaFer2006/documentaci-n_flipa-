# 3. Validación de identidad (KYC)

## Objetivo

Validar automáticamente la identidad del cliente y evaluar si cumple los criterios mínimos de riesgo utilizando información proveniente de Experian, el historial transaccional de D1 y las reglas de negocio definidas para el producto. Al finalizar este proceso se determina si la solicitud continúa hacia la firma del contrato o si el crédito es rechazado.

---

## Journey

![Journey Colpatria B2B — página 4](imagenes/page-04.png)

**Figura 4. Journey de Validación de Identidad (KYC) y Evaluación Inicial de Riesgo.**

Este journey representa el proceso de validación automática de identidad y riesgo que se ejecuta una vez finalizado el onboarding digital. Durante esta etapa el sistema consulta la información disponible en Experian y el historial transaccional del cliente en D1, aplica las reglas automáticas de KYC y valida la cuenta bancaria antes de decidir si la solicitud continúa hacia la firma del contrato o es rechazada.

---

## Descripción general

Después de completar el onboarding digital, la solicitud ingresa automáticamente al proceso de Validación de Identidad (KYC). En esta etapa el sistema centraliza la información obtenida durante el onboarding y realiza consultas adicionales a fuentes externas como Experian y la información transaccional de D1.

Con esta información se ejecutan automáticamente las reglas de negocio definidas para el proceso KYC. Si el cliente cumple los criterios mínimos establecidos, el sistema valida la consistencia de la cuenta bancaria registrada y determina si la solicitud puede continuar hacia la firma del contrato. Si alguna validación falla, la solicitud es rechazada automáticamente y el cliente recibe la notificación correspondiente.

---

## Explicación del Journey

### 1. Recepción de la solicitud

Una vez finalizado el onboarding digital, el sistema recibe la solicitud y crea automáticamente el caso dentro del módulo administrativo para iniciar el proceso de validación.

Esta etapa marca el inicio del análisis automático de identidad y riesgo.

---

### 2. Consulta de información externa

El sistema consulta simultáneamente la información disponible en Experian y el historial transaccional del cliente registrado en D1.

Estas consultas permiten complementar la información recopilada durante el onboarding y obtener los datos necesarios para ejecutar las validaciones automáticas.

---

### 3. Evaluación automática de criterios KYC

Con la información obtenida, el sistema ejecuta automáticamente las reglas de negocio definidas para el proceso de Validación de Identidad (KYC).

Entre los criterios evaluados se encuentran:

- Score mínimo requerido.
- Capacidad de endeudamiento.
- Información transaccional del cliente.
- Tienda habitual registrada.
- Reglas definidas para el producto.

Toda esta evaluación se realiza sin intervención manual.

---

### 4. Validación de cumplimiento

Una vez finalizada la evaluación automática, el sistema determina si el cliente cumple los requisitos mínimos para continuar.

Si el cliente no cumple alguno de los criterios establecidos, la solicitud es rechazada automáticamente y se genera una alerta para registrar la decisión.

Si cumple los requisitos, el proceso continúa con la validación de la cuenta bancaria.

---

### 5. Validación de la cuenta bancaria

El sistema compara la cuenta bancaria registrada durante el onboarding con la información reportada por Experian y otros productos financieros asociados al cliente.

Esta validación busca garantizar la consistencia de la información bancaria antes de continuar con el proceso de originación.

---

### 6. Verificación de la cuenta

El sistema determina si la cuenta bancaria es válida.

Si la validación es exitosa, la solicitud continúa.

Si la información presenta inconsistencias, el crédito es rechazado automáticamente.

---

### 7. Ajuste del cupo y aprobación

Cuando todas las validaciones son satisfactorias, el sistema aprueba la solicitud o ajusta el cupo de crédito de acuerdo con los resultados obtenidos durante la evaluación.

Posteriormente el proceso continúa hacia la firma del contrato.

---

### 8. Rechazo del crédito

Si cualquiera de las validaciones automáticas falla, el sistema rechaza la solicitud y registra una alerta dentro del proceso.

Posteriormente el cliente recibe una notificación informando que su solicitud no fue aprobada.

---

### 9. Notificación al cliente

Cuando el crédito es rechazado, el sistema envía automáticamente una notificación al cliente mediante correo electrónico.

Con esta notificación finaliza el proceso de Validación de Identidad (KYC).

---

## Reglas de negocio

- El proceso KYC se ejecuta completamente de forma automática.
- La información de Experian y el historial transaccional de D1 son obligatorios para realizar la evaluación.
- El cliente debe cumplir el score mínimo definido por el producto.
- Se valida automáticamente la capacidad de endeudamiento del cliente.
- La tienda habitual registrada hace parte de las reglas de evaluación.
- La cuenta bancaria debe coincidir con la información reportada en Experian.
- Si cualquier validación falla, la solicitud es rechazada automáticamente.
- Solo las solicitudes aprobadas continúan hacia la firma del contrato.

---

## Entradas

- Información del cliente registrada durante el onboarding.
- Resultado de la biometría.
- Historial transaccional de D1.
- Información de Experian.
- Cuenta bancaria registrada.
- Reglas de negocio del motor KYC.

---

## Salidas

- Cliente aprobado para continuar con la firma del contrato.
- Cupo de crédito aprobado o ajustado.
- Solicitud rechazada.
- Alerta registrada en el sistema.
- Notificación enviada al cliente.

---

## Excepciones

- El cliente no cumple el score mínimo requerido.
- La capacidad de endeudamiento no cumple las políticas del producto.
- La información de Experian presenta inconsistencias.
- La cuenta bancaria no coincide con la información consultada.
- Error en la consulta de Experian.
- Error en la consulta del historial transaccional de D1.
- Error en la validación automática de las reglas KYC.

---

## Consideraciones

- El proceso KYC es completamente automático y no requiere intervención manual del analista.
- La biometría se realiza durante el proceso de onboarding y su resultado es utilizado como insumo para esta evaluación.
- La aprobación obtenida en esta etapa permite continuar con la firma del contrato.
- Cualquier validación fallida genera el rechazo automático de la solicitud.

---

## Pendientes de validación

> **Pendiente de validar con el dueño del proceso:** confirmar si el ajuste del cupo se realiza mediante reglas completamente automáticas o si existe alguna parametrización adicional antes de la firma del contrato.

---

## Fuentes consultadas

- *Journeys Colpatria B2B* (junio de 2026), página 4.
- Documento de reglas de negocio KYC.
- Documentación funcional del producto.

