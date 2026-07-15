# 3. Validación de identidad (KYC)

## Objetivo

Validar automáticamente la identidad del cliente y evaluar si cumple los criterios mínimos de riesgo utilizando información proveniente de Experian, RUES, el historial transaccional de D1 y las reglas de negocio (reglas de Colpatria) definidas para el producto. Al finalizar este proceso se determina si la solicitud continúa hacia la firma del contrato o si el crédito es rechazado.

---

## Journey

![Journey Colpatria B2B — página 4](imagenes/page-04.png)

**Figura 4. Journey de Validación de Identidad (KYC) y Evaluación Inicial de Riesgo.**

En el journey, las dos cajas moradas ("Evalúa criterios de KYC automáticamente" y "Valida la información de la cuenta contra los productos reportados en Experian") corresponden a pasos ajustados en junio de 2026 (leyenda "Ajuste · jun 2026"); las demás cajas corresponden a pasos ya existentes del flujo.

---

## Descripción general

Una vez el cliente finaliza el proceso de onboarding digital, la solicitud ingresa automáticamente al proceso de Validación de Identidad (KYC). En esta etapa el sistema recibe el caso en el Admin, consulta y almacena información de fuentes externas —Experian, RUES y el historial transaccional de D1— y ejecuta de forma automática las reglas de negocio de Colpatria establecidas para evaluar la elegibilidad del cliente. El resultado de la validación biométrica obtenida durante el onboarding, realizada por el proveedor externo, también queda registrado en el Admin y hace parte del expediente consultado en esta etapa.

Si el cliente cumple con todos los criterios definidos, el sistema valida la cuenta bancaria registrada contra los productos financieros reportados en Experian y aprueba o ajusta el cupo de crédito antes de continuar con la firma del contrato. En caso de que alguna validación falle —ya sea el cumplimiento de requisitos o la validez de la cuenta—, la solicitud es rechazada automáticamente, el sistema emite una alarma y el cliente recibe una notificación por correo electrónico. Según las notas del journey, este proceso de KYC es ahora 100% automático y elimina el estudio manual que anteriormente realizaba un analista.

---

## Explicación del Journey

### 1. Recepción de la solicitud

**Actor:** Sistema.

**Sistemas involucrados:** Admin (módulo administrativo).

**Información utilizada:** Solicitud finalizada durante el onboarding digital.

**Resultado:** El sistema recibe la solicitud y abre automáticamente el caso dentro del Admin, sin intervención del cliente. A partir de este momento inicia el proceso de KYC.

---

### 2. Consulta y almacenamiento de información en Experian y D1

**Actor:** Sistema.

**Sistemas involucrados:** Experian, RUES, base de datos transaccional de D1.

**Información utilizada:** Información del cliente registrada durante el onboarding.

**Resultado:** El sistema consulta y almacena en el Admin la información de Experian, RUES y el historial transaccional de D1. El resultado de la validación biométrica del onboarding (realizada por el proveedor externo) también queda almacenado en el Admin como parte del expediente del caso.

> **Nota:** el journey señala RUES como fuente adicional de consulta, junto con Experian y el histórico transaccional de D1.

---

### 3. Evaluación automática de criterios KYC

**Actor:** Sistema.

**Sistemas involucrados:** Motor de reglas (reglas de Colpatria).

**Información utilizada:**

- Score (puntaje) mínimo requerido.
- Capacidad de endeudamiento.
- Tienda habitual declarada por el cliente durante el onboarding, comparada de forma automática contra la tienda habitual registrada en el histórico transaccional de D1.
- Reglas de riesgo definidas para el producto.

**Resultado:** El sistema aplica automáticamente las reglas de Colpatria definidas para el proceso KYC.

> **Nota (Ajuste · jun 2026):** este paso está marcado en el journey como un paso ajustado en junio de 2026.

---

### 4. Verificación de cumplimiento de requisitos

**Actor:** Sistema.

**Decisión:** ¿El cliente cumple con los requisitos?

- **Sí:** el proceso continúa hacia la validación de la cuenta bancaria.
- **No:** el proceso continúa hacia el rechazo del crédito y la emisión de la alarma (paso 8).

---

### 5. Validación de la cuenta bancaria

**Actor:** Sistema.

**Sistemas involucrados:** Experian.

**Información utilizada:** Cuenta bancaria registrada durante el onboarding; productos financieros reportados en Experian.

**Resultado:** El sistema contrasta la cuenta bancaria registrada por el cliente contra los productos financieros reportados en Experian, con el fin de confirmar que la cuenta corresponde al cliente y que la información es consistente antes de continuar con la originación del crédito.

> **Nota (Ajuste · jun 2026):** este paso está marcado en el journey como un paso ajustado en junio de 2026.

---

### 6. Verificación de la cuenta bancaria

**Actor:** Sistema.

**Decisión:** ¿La cuenta es válida?

- **Sí:** el proceso continúa hacia la aprobación o ajuste del cupo de crédito.
- **No:** el proceso continúa hacia el rechazo del crédito y la emisión de la alarma (paso 8).

---

### 7. Aprobación o ajuste del cupo de crédito

**Actor:** Sistema.

**Resultado:** Cuando todas las validaciones son satisfactorias, el sistema aprueba la solicitud o ajusta el cupo de crédito de acuerdo con las reglas de negocio y los resultados obtenidos durante la evaluación. La solicitud continúa hacia la firma del contrato.

---

### 8. Rechazo del crédito y emisión de alarma

**Actor:** Sistema.

**Resultado:** Cuando el cliente no cumple los requisitos evaluados en el paso 4, o cuando la cuenta bancaria no es válida en el paso 6, el sistema rechaza el crédito y emite una alarma para mantener la trazabilidad de la decisión. Ambos caminos ("No" del paso 4 y "No" del paso 6) confluyen en este mismo paso.

---

### 9. Notificación al cliente

**Actor:** Sistema.

**Sistemas involucrados:** Correo electrónico.

**Resultado:** El sistema envía automáticamente una notificación al cliente por correo electrónico informando que la solicitud no fue aprobada. Con esta acción finaliza el proceso de Validación de Identidad (KYC).

---

## Reglas de negocio

- El proceso KYC se ejecuta completamente de forma automática; según el journey, esto elimina el estudio manual que antes realizaba un analista.
- La consulta a Experian, RUES y al historial transaccional de D1 es obligatoria, y el resultado se almacena en el Admin junto con el resultado de la biometría del onboarding.
- El cliente debe cumplir el puntaje mínimo definido para el producto.
- Se evalúa automáticamente la capacidad de endeudamiento del cliente.
- La tienda habitual declarada por el cliente se compara automáticamente contra la tienda habitual registrada en el histórico transaccional de D1.
- La evaluación de criterios de KYC se realiza mediante las reglas de Colpatria.
- La cuenta bancaria debe coincidir con los productos financieros reportados en Experian.
- Si el cliente no cumple los requisitos o la cuenta bancaria no es válida, el sistema rechaza el crédito y emite una alarma.
- Solo las solicitudes aprobadas continúan hacia la firma del contrato.

---

## Entradas

- Información del cliente registrada durante el onboarding.
- Resultado de la validación biométrica (almacenado en el Admin).
- Historial transaccional de D1.
- Información consultada en Experian.
- Información consultada en RUES.
- Cuenta bancaria registrada por el cliente.
- Reglas de negocio de Colpatria definidas para el proceso KYC.

---

## Salidas

- Cliente aprobado para continuar con la firma del contrato.
- Cupo de crédito aprobado o ajustado.
- Solicitud rechazada.
- Alarma emitida y registrada en el sistema.
- Notificación de rechazo enviada al cliente por correo electrónico.

---

## Excepciones

- El cliente no cumple el puntaje mínimo requerido.
- La capacidad de endeudamiento supera los límites permitidos.
- La tienda habitual declarada no coincide con la registrada en el histórico transaccional.
- La información consultada en Experian o RUES presenta inconsistencias.
- La cuenta bancaria registrada no coincide con la información validada en Experian.
- Error durante la consulta a Experian, RUES o al historial transaccional de D1.
- Error en la ejecución de las reglas automáticas de Colpatria del proceso KYC.

---

## Consideraciones

- El proceso de Validación de Identidad (KYC) es completamente automático y no requiere intervención manual; el journey indica que esto elimina el estudio manual que antes realizaba un analista.
- El resultado de la biometría obtenida durante el onboarding (proveedor externo) queda almacenado en el Admin y es uno de los insumos utilizados en esta evaluación.
- La validación de la cuenta bancaria se realiza contra los productos reportados en Experian, antes de aprobar definitivamente el cupo de crédito.
- Cualquier validación fallida —requisitos de KYC o validez de la cuenta— genera el rechazo automático de la solicitud y la emisión de una alarma.
- Las reglas de evaluación (reglas de Colpatria) pueden modificarse conforme evolucione la estrategia de riesgo del producto.

---

## Pendientes de validación

> **Pendiente de validar con el dueño del proceso:**
>
> - Confirmar si el ajuste del cupo de crédito puede realizarse mediante reglas parametrizadas adicionales antes de la firma del contrato.
> - Validar si existen criterios complementarios no reflejados en el journey.
> - Confirmar el alcance exacto de la consulta a RUES y qué datos específicos aporta a la evaluación.
> - Confirmar cómo se define y mide la comparación entre "tienda habitual declarada" y "tienda habitual registrada".
> - Confirmar si el rechazo por incumplimiento de requisitos (paso 4) y el rechazo por cuenta bancaria inválida (paso 6) generan el mismo tipo de alarma o si existen niveles de severidad diferentes.

---

## Fuentes consultadas

- *Journeys Colpatria B2B* (junio de 2026), página 4.
- Documentación funcional del proceso KYC.
- Documento de reglas de negocio del producto.
- Documento de Alcance del Producto.
