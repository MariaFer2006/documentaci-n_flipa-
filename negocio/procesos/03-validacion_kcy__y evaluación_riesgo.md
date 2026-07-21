# 3. Validación de identidad (KYC)

## Objetivo

Validar automáticamente la identidad del cliente y evaluar si cumple los criterios mínimos de riesgo utilizando información proveniente de Experian, el historial transaccional de D1 y las reglas de negocio (reglas de Colpatria)* definidas para el producto. Al finalizar este proceso se determina si la solicitud continúa hacia la firma del contrato o si el crédito es rechazado.

*Los elementos marcados con asterisco (\*) corresponden a puntos aún no definidos técnicamente o pendientes de confirmación con el dueño del proceso; se detallan en cada paso y se listan de forma consolidada en "Pendientes de validación".*

---

## Journey

![Journey Colpatria B2B — página 4](imagenes/page-04.png)

**Figura 4. Journey de Validación de Identidad (KYC) y Evaluación Inicial de Riesgo.**

En el journey, las dos cajas moradas ("Evalúa criterios de KYC automáticamente" y "Valida la información de la cuenta contra los productos reportados en Experian") corresponden a pasos ajustados en junio de 2026 (leyenda "Ajuste · jun 2026"); las demás cajas corresponden a pasos ya existentes del flujo.

---

## Descripción general

Una vez el cliente finaliza el proceso de onboarding digital, la solicitud ingresa automáticamente al proceso de Validación de Identidad (KYC). En esta etapa el sistema recibe el caso en el Admin, consulta y almacena información de fuentes externas —Experian, RUES* y el historial transaccional de D1— y ejecuta de forma automática las reglas de negocio de Colpatria* establecidas para evaluar la elegibilidad del cliente. El resultado de la validación biométrica obtenida durante el onboarding, realizada por el proveedor externo (Olimpia)*, también queda registrado en el Admin y hace parte del expediente consultado en esta etapa.

Si el cliente cumple con todos los criterios definidos, el sistema valida la cuenta bancaria registrada contra los productos financieros reportados en Experian y aprueba o ajusta* el cupo de crédito antes de continuar con la firma del contrato. En caso de que alguna validación falle —ya sea el cumplimiento de requisitos o la validez de la cuenta—, la solicitud es rechazada automáticamente, el sistema emite una alarma* y el cliente recibe una notificación por correo electrónico. Este proceso de KYC es 100% automático y elimina el estudio manual que anteriormente realizaba un analista.

---

## Explicación paso a paso

### 1. Recepción de la solicitud

**Actor:** Sistema.

**Sistemas involucrados:** Admin (módulo administrativo).

**Información utilizada:** Solicitud finalizada durante el onboarding digital.

**Proceso:** Al cerrarse exitosamente el onboarding (solicitud enviada en el paso 21 del journey de Onboarding), el sistema dispara automáticamente la apertura de un caso nuevo en el Admin, sin que el cliente deba realizar ninguna acción adicional. Este caso queda como el contenedor donde se centraliza toda la información consultada durante el KYC.

**Resultado:** El sistema recibe la solicitud y abre automáticamente el caso dentro del Admin. A partir de este momento inicia el proceso de KYC.

**Tiempo estimado:** Instantáneo (disparado automáticamente al cierre del onboarding).

---

### 2. Consulta y almacenamiento de información en Experian, RUES y D1

**Actor:** Sistema.

**Sistemas involucrados:** Experian, RUES*, base de datos transaccional de D1.

**Información utilizada:** Información del cliente registrada durante el onboarding.

**Proceso:** El sistema ejecuta, en el caso abierto en el Admin, las consultas correspondientes a Experian (productos financieros del cliente), RUES* (validación de existencia/estado de la empresa, en el caso NIT) y el histórico transaccional de D1 del cliente. Cada resultado se almacena como parte del expediente del caso. Adicionalmente, el resultado de la validación biométrica obtenida durante el onboarding con el proveedor externo (Olimpia)* se registra en el Admin como un insumo más del expediente, sin volver a ejecutarse en esta etapa.

**Resultado:** El sistema consulta y almacena en el Admin la información de Experian, RUES y el historial transaccional de D1, junto con el resultado biométrico del onboarding.

**Tiempo estimado:** Depende del tiempo de respuesta de las APIs externas (Experian y RUES); procesamiento automático, sin intervención humana.

> **Placeholder\*:** el alcance exacto de la consulta a RUES (qué campos específicos se traen y cómo se usan en la evaluación) aún no está definido; pendiente de confirmar con el dueño del proceso.

> **Nota:** el journey señala RUES como fuente adicional de consulta, junto con Experian y el histórico transaccional de D1.

---

### 3. Evaluación automática de criterios KYC

**Actor:** Sistema.

**Sistemas involucrados:** Motor de reglas (reglas de Colpatria)*.

**Información utilizada:**

- Score (puntaje) mínimo requerido*.
- Capacidad de endeudamiento*.
- Tienda habitual declarada por el cliente durante el onboarding, comparada de forma automática contra la tienda habitual registrada en el histórico transaccional de D1*.
- Reglas de riesgo definidas para el producto*.

**Proceso:** El motor de reglas toma la información consolidada en el paso 2 (Experian, RUES, D1 y biometría) y la evalúa de forma automática contra los criterios de riesgo configurados para el producto. Este paso fue ajustado en junio de 2026 para incorporar la comparación automática entre la tienda habitual declarada y la registrada en D1.

**Resultado:** El sistema aplica automáticamente las reglas de Colpatria definidas para el proceso KYC y determina si el cliente cumple o no los criterios.

**Tiempo estimado:** Instantáneo a segundos (procesamiento interno del motor de reglas).

> **Placeholder\*:** no están definidos con precisión (a) el valor exacto del score mínimo, (b) la fórmula/límites de la capacidad de endeudamiento, (c) la metodología para comparar "tienda habitual declarada" vs. "tienda habitual registrada" (¿coincidencia exacta?, ¿radio geográfico?, ¿tolerancia?), y (d) el detalle completo de las reglas de riesgo de Colpatria más allá de lo señalado en el journey. Todo esto queda pendiente de validar con el dueño del proceso.

> **Nota (Ajuste · jun 2026):** este paso está marcado en el journey como un paso ajustado en junio de 2026.

---

### 4. Verificación de cumplimiento de requisitos

**Actor:** Sistema.

**Proceso:** El sistema evalúa el resultado del paso 3 y bifurca el flujo según el cliente cumpla o no la totalidad de los criterios definidos.

**Decisión:** ¿El cliente cumple con los requisitos?

- **Sí:** el proceso continúa hacia la validación de la cuenta bancaria.
- **No:** el proceso continúa hacia el rechazo del crédito y la emisión de la alarma (paso 8).

**Tiempo estimado:** Instantáneo.

---

### 5. Validación de la cuenta bancaria contra Experian

**Actor:** Sistema.

**Sistemas involucrados:** Experian.

**Información utilizada:** Cuenta bancaria registrada durante el onboarding; productos financieros reportados en Experian.

**Proceso:** El sistema contrasta la cuenta bancaria registrada por el cliente (entidad + número de cuenta, capturados en el onboarding) contra los productos financieros que Experian reporta a nombre del mismo cliente, con el fin de confirmar que la cuenta le pertenece y que la información es consistente antes de continuar con la originación del crédito.

**Resultado:** Confirmación de que la cuenta bancaria corresponde al cliente evaluado.

**Tiempo estimado:** Depende del tiempo de respuesta de la API de Experian.

> **Placeholder\*:** no está definido el detalle exacto de qué campos de "productos financieros reportados en Experian" se usan para el cruce (¿tipo de producto, titularidad, antigüedad?) ni el criterio de coincidencia mínima aceptado. Pendiente de definición técnica.

> **Nota (Ajuste · jun 2026):** este paso está marcado en el journey como un paso ajustado en junio de 2026.

---

### 6. Verificación de la cuenta bancaria

**Actor:** Sistema.

**Proceso:** El sistema evalúa el resultado del paso 5 y bifurca el flujo según la cuenta resulte válida o no.

**Decisión:** ¿La cuenta es válida?

- **Sí:** el proceso continúa hacia la aprobación o ajuste del cupo de crédito.
- **No:** el proceso continúa hacia el rechazo del crédito y la emisión de la alarma (paso 8).

**Tiempo estimado:** Instantáneo.

---

### 7. Aprobación o ajuste del cupo de crédito

**Actor:** Sistema.

**Proceso:** Cuando todas las validaciones (pasos 3 a 6) son satisfactorias, el sistema calcula la decisión final: aprueba la solicitud con el cupo preaprobado del onboarding, o lo ajusta* de acuerdo con las reglas de negocio y los resultados obtenidos durante la evaluación (score, capacidad de endeudamiento, información de Experian).

**Resultado:** Solicitud aprobada o con cupo ajustado; la solicitud continúa hacia la firma del contrato.

**Tiempo estimado:** Instantáneo (cálculo automático).

> **Placeholder\*:** no está definido si el ajuste del cupo se realiza mediante reglas parametrizadas adicionales (por ejemplo, un porcentaje de reducción según score) o si se maneja caso a caso; pendiente de validar con el dueño del proceso.

---

### 8. Rechazo del crédito y emisión de alarma

**Actor:** Sistema.

**Proceso:** Cuando el cliente no cumple los requisitos evaluados en el paso 4, o cuando la cuenta bancaria no es válida en el paso 6, el sistema ejecuta el rechazo automático de la solicitud y genera una alarma* interna para mantener la trazabilidad de la decisión. Ambos caminos ("No" del paso 4 y "No" del paso 6) confluyen en este mismo paso.

**Resultado:** Crédito rechazado y alarma emitida y registrada en el sistema.

**Tiempo estimado:** Instantáneo.

> **Placeholder\*:** no está definido si el rechazo por incumplimiento de requisitos (paso 4) y el rechazo por cuenta bancaria inválida (paso 6) generan el mismo tipo/severidad de alarma, o si existen niveles diferenciados (por ejemplo, alarma informativa vs. alarma que requiere revisión). Pendiente de confirmar con el dueño del proceso.

---

### 9. Notificación al cliente

**Actor:** Sistema.

**Sistemas involucrados:** Correo electrónico.

**Proceso:** Tras registrarse el rechazo y la alarma en el paso 8, el sistema dispara automáticamente un correo electrónico al cliente informando que la solicitud no fue aprobada. Con esta acción finaliza el proceso de Validación de Identidad (KYC) para ese caso.

**Resultado:** Notificación de rechazo enviada al cliente por correo electrónico.

**Tiempo estimado:** Instantáneo del lado del sistema; recepción asíncrona según el proveedor de correo.

> **Placeholder\*:** no está definido el contenido/copy exacto del correo de rechazo, ni si existe algún canal adicional (SMS/WhatsApp vía Zenvia, como en el onboarding) para esta notificación.

---

## Reglas de negocio

- El proceso KYC se ejecuta completamente de forma automática; esto elimina el estudio manual que antes realizaba un analista.
- La consulta a Experian, RUES* y al historial transaccional de D1 es obligatoria, y el resultado se almacena en el Admin junto con el resultado de la biometría del onboarding.
- El cliente debe cumplir el puntaje mínimo definido para el producto*.
- Se evalúa automáticamente la capacidad de endeudamiento del cliente*.
- La tienda habitual declarada por el cliente se compara automáticamente contra la tienda habitual registrada en el histórico transaccional de D1*.
- La evaluación de criterios de KYC se realiza mediante las reglas de Colpatria*.
- La cuenta bancaria debe coincidir con los productos financieros reportados en Experian*.
- Si el cliente no cumple los requisitos o la cuenta bancaria no es válida, el sistema rechaza el crédito y emite una alarma*.
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

- El proceso de Validación de Identidad (KYC) es completamente automático y no requiere intervención manual; esto elimina el estudio manual que antes realizaba un analista.
- El resultado de la biometría obtenida durante el onboarding (proveedor externo Olimpia) queda almacenado en el Admin y es uno de los insumos utilizados en esta evaluación.
- La validación de la cuenta bancaria se realiza contra los productos reportados en Experian, antes de aprobar definitivamente el cupo de crédito.
- Cualquier validación fallida —requisitos de KYC o validez de la cuenta— genera el rechazo automático de la solicitud y la emisión de una alarma.
- Las reglas de evaluación (reglas de Colpatria) pueden modificarse conforme evolucione la estrategia de riesgo del producto.
- Varios de los parámetros críticos de este proceso (score mínimo, límites de endeudamiento, metodología de comparación de tienda habitual, reglas de ajuste de cupo y severidad de alarmas) todavía son placeholders* y deben confirmarse antes de pasar este journey a desarrollo.

---

## Pendientes de validación

> **Pendiente de validar con el dueño del proceso:**
>
> - Confirmar si el ajuste del cupo de crédito puede realizarse mediante reglas parametrizadas adicionales antes de la firma del contrato, o si es un ajuste manual caso a caso. *(placeholder — paso 7)*
> - Validar si existen criterios complementarios no reflejados en el journey. *(placeholder — paso 3)*
> - Confirmar el alcance exacto de la consulta a RUES y qué datos específicos aporta a la evaluación. *(placeholder — paso 2)*
> - Confirmar cómo se define y mide la comparación entre "tienda habitual declarada" y "tienda habitual registrada" (coincidencia exacta, radio geográfico, tolerancia). *(placeholder — paso 3)*
> - Confirmar el valor del score mínimo y la fórmula/límites de la capacidad de endeudamiento. *(placeholder — paso 3)*
> - Confirmar qué campos específicos de "productos financieros reportados en Experian" se usan para validar la cuenta bancaria y el criterio de coincidencia mínima. *(placeholder — paso 5)*
> - Confirmar si el rechazo por incumplimiento de requisitos (paso 4) y el rechazo por cuenta bancaria inválida (paso 6) generan el mismo tipo de alarma o si existen niveles de severidad diferentes. *(placeholder — paso 8)*
> - Confirmar el copy/contenido exacto de la notificación de rechazo y si existe algún canal adicional al correo (SMS/WhatsApp). *(placeholder — paso 9)*

---

## Fuentes consultadas

- *Journeys Colpatria B2B* (junio de 2026), página 4.
- Documentación funcional del proceso KYC.
- Documento de reglas de negocio del producto.
- Documento de Alcance del Producto.
- Indicación de Iván Aponte (16 de julio de 2026): detallar el proceso de KYC paso a paso, incorporando los procesos técnicos de cada paso y marcando con asteriscos los puntos aún no definidos (placeholders).
