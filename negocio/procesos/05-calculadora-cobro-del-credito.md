# 5. Calculadora y cobro del crédito

## Objetivo

Administrar el ciclo de pago del crédito una vez el cliente utiliza el bono D1, calculando automáticamente el plan de pagos, permitiendo realizar pagos anticipados o esperar el débito automático, actualizando el saldo del crédito y determinando si la obligación queda al día, se liquida completamente o continúa hacia el proceso de cobranza.

---

## Journey

![Journey Colpatria B2B — página 7](imagenes/page-07.png)

**Figura 6. Journey de Calculadora y Cobro del Crédito.**

El journey se organiza en tres carriles (swimlanes): **Cliente**, **Calculadora** y **Medios de pago**. La caja "No — espera cobro automático en corte" está marcada como ajuste de junio de 2026.

*Los elementos marcados con asterisco (\*) corresponden a puntos aún no definidos técnicamente o pendientes de confirmación con el dueño del proceso; se detallan en cada paso y se listan de forma consolidada en "Pendientes de validación".*

---

## Descripción general

Una vez el cliente recibe y accede a su bono D1 (asignado en el proceso de Firma de Contrato, documento 4) y lo utiliza para realizar una compra, un **worker periódico**\* detecta ese uso en D1 y dispara el inicio de los cálculos de cobro. La calculadora genera automáticamente el plan de pagos (cuotas, fechas, tasa y saldo inicial), información que el cliente puede consultar desde la plataforma web.

El cliente decide entonces si desea realizar un prepago mediante PSE desde la web, o esperar el cobro automático que se ejecuta con Drúo al cierre del ciclo. Una vez recibido el pago, el sistema lo registra, aplica la amortización correspondiente y actualiza el saldo. Si el crédito queda al día, se liquida y el cupo se libera para un nuevo ciclo; si el cliente se encuentra en mora, el caso continúa automáticamente hacia el proceso de Cobranza (documento 8).

---

## Explicación paso a paso

Cada paso incluye el **proceso** (qué ocurre técnica u operativamente) y un **tiempo estimado** de referencia, pendiente de validar con Producto/Tecnología.

### 1. Recepción y acceso al bono

**Actor:** Cliente.

**Proceso:** El cliente recibe y accede a su bono D1 por medio de la plataforma web (bono asignado en el paso 16 del documento 4, Firma de contrato y activación). Posteriormente utiliza el bono para realizar una compra en una tienda D1 (documento 6, Dispersión de fondos).

**Resultado:** Bono utilizado en una compra en D1.

**Tiempo estimado:** Depende de cuándo el cliente decida usar el bono; no es un tiempo fijo del sistema.

---

### 2. Detección del uso del bono e inicio de cálculos

**Actor:** Calculadora (sistema).

**Proceso:** Un **worker periódico**\* revisa de forma programada las transacciones en D1 y detecta cuándo el cliente utilizó su bono. Al detectarlo, dispara automáticamente el inicio de los cálculos de cobro sobre esa obligación.

**Resultado:** Inicio del cálculo de la obligación financiera.

**Tiempo estimado:** No es instantáneo: depende de la frecuencia de ejecución del worker periódico (por ejemplo, cada X minutos), la cual aún no está definida.

**Placeholder\*:** no está definida la periodicidad exacta con la que corre el worker que detecta el uso del bono en D1 (¿cada minuto?, ¿cada hora?, ¿en tiempo real vía evento en lugar de polling?). Esto determina el tiempo real entre el uso del bono y la generación del crédito, ya señalado como pendiente en versiones anteriores de este documento.

---

### 3. Cálculo del plan de pagos

**Actor:** Calculadora (sistema).

**Proceso:** La calculadora financiera genera el plan de pagos correspondiente a la obligación: cuotas, fechas de vencimiento, tasa de interés y saldo inicial, aplicando las reglas de cálculo de intereses y amortización definidas para el producto\*.

**Resultado:** Plan de pagos generado y disponible para consulta del cliente.

**Tiempo estimado:** Instantáneo una vez el worker detecta el uso del bono (cálculo automático).

**Placeholder\*:** las reglas exactas de cálculo de intereses y amortización (tasa aplicada, método de amortización, redondeos) no están detalladas en el journey; pendientes de confirmar con el dueño del proceso.

---

### 4. Consulta del estado del crédito

**Actor:** Cliente.

**Proceso:** El cliente ingresa a la plataforma web y visualiza el saldo pendiente y la fecha de pago de su crédito, además del valor de las cuotas y el estado general de la obligación.

**Resultado:** Cliente informado del estado de su crédito.

**Tiempo estimado:** Consulta a demanda del cliente; no aplica un tiempo fijo.

---

### 5. Decisión sobre el método de pago

**Actor:** Cliente.

**Proceso:** Con la información consultada, el cliente decide cómo realizar el pago de su crédito.

**Decisión:** ¿Desea realizar prepago?

- **Sí:** el pago se registra en PSE desde la web.
- **No:** el cliente espera el cobro automático en la fecha de corte/cierre del ciclo.

**Resultado:** Método de pago seleccionado (prepago o espera de débito automático).

**Tiempo estimado:** ~20-30 segundos si decide hacer prepago de inmediato; indefinido si opta por esperar el débito automático.

**Placeholder\*:** no están definidas las condiciones para permitir pagos anticipados **parciales** (¿se puede prepagar solo una parte de la cuota o del saldo total?, ¿hay un monto mínimo de prepago?).

---

### 6a. Pago registrado en PSE

**Actor:** Medios de pago (PSE).

**Proceso:** Si el cliente eligió prepagar, la plataforma PSE procesa el pago desde la web y lo entrega al sistema para su registro.

**Resultado:** Pago recibido vía PSE.

**Tiempo estimado:** Depende del tiempo de procesamiento de PSE (generalmente segundos a minutos).

---

### 6b. Espera del cobro automático en corte

**Actor:** Medios de pago (Drúo).

**Proceso:** Si el cliente no realiza un prepago, el sistema espera hasta la fecha de corte/cierre del ciclo para ejecutar el débito automático con **Drúo** sobre la cuenta bancaria previamente vinculada (documento 2, Onboarding — paso 18).

**Resultado:** Débito automático ejecutado en la fecha de corte.

**Tiempo estimado:** Asíncrono; ocurre en la fecha de corte definida para el ciclo del crédito.

> **Nota (Ajuste · jun 2026):** esta ruta ("No — espera cobro automático en corte") está marcada en el journey como un ajuste de junio de 2026.

**Placeholder\*:** no está definida la frecuencia exacta de ejecución del débito automático (¿un único intento en la fecha de corte, o varios intentos como en el proceso de Cobranza, documento 8, días 0 y 1-5?). Debe alinearse con las reglas ya definidas en el documento de Cobranza para evitar duplicidad o inconsistencia entre ambos procesos.

---

### 7. Registro del pago y actualización del saldo

**Actor:** Calculadora (sistema).

**Proceso:** Una vez recibido el pago —por PSE o por débito automático—, el sistema lo registra, aplica la amortización correspondiente sobre el saldo y actualiza el estado de la obligación.

**Resultado:** Saldo del crédito actualizado.

**Tiempo estimado:** Instantáneo (procesamiento automático tras la confirmación del pago).

---

### 8. Validación del estado del crédito

**Actor:** Calculadora (sistema).

**Proceso:** El sistema evalúa si, tras la actualización del saldo, el crédito quedó al día.

**Decisión:** ¿Crédito al día?

- **Sí:** el crédito se liquida y el cupo se libera.
- **No:** el cliente se encuentra en mora y el caso continúa hacia el proceso de cobranza.

**Resultado:** Determinación del estado final del ciclo de crédito.

**Tiempo estimado:** Instantáneo.

---

### 9a. Liquidación del crédito y liberación del cupo

**Actor:** Calculadora (sistema).

**Proceso:** Cuando el saldo llega a cero, el sistema marca el crédito como liquidado y libera nuevamente el cupo aprobado, siguiendo las reglas de liberación de cupo definidas para el producto\*.

**Resultado:** Crédito liquidado; cupo nuevamente disponible para futuras compras. Con este paso finaliza el ciclo operativo del crédito.

**Tiempo estimado:** Instantáneo.

**Placeholder\*:** no están definidas con precisión las reglas para liberar nuevamente el cupo tras la liquidación (¿el cupo vuelve exactamente al mismo valor previo?, ¿puede ajustarse según el comportamiento de pago, en línea con la evaluación de renovación descrita en el documento 6, Dispersión de fondos?).

---

### 9b. Mora e inicio del proceso de cobranza

**Actor:** Cliente / Calculadora (sistema).

**Proceso:** Si el cliente incumple la fecha de pago, el crédito queda marcado en estado de mora y el sistema clasifica automáticamente la obligación como cartera en mora, transfiriendo el caso al proceso de Cobranza (documento 8).

**Resultado:** Caso enviado al proceso de cobranza.

**Tiempo estimado:** Instantáneo (clasificación automática); el proceso de cobranza en sí sigue su propia línea de tiempo (documento 8: Día 0 en adelante).

---

## Reglas de negocio

- El crédito se origina cuando un worker periódico detecta el uso del bono D1 por parte del cliente, no en el momento exacto de la compra.
- El sistema genera automáticamente el plan de pagos después de detectar el uso del bono.
- El cliente puede realizar pagos anticipados mediante PSE desde la plataforma web.
- Si el cliente no realiza un prepago, el sistema ejecuta el débito automático con Drúo en la fecha de corte/cierre del ciclo, utilizando la cuenta bancaria previamente vinculada.
- Cada pago recibido (PSE o débito automático) actualiza automáticamente el saldo del crédito.
- Cuando el saldo llega a cero, el crédito se liquida y el cupo vuelve a estar disponible.
- Si el pago no se realiza oportunamente, el caso continúa hacia el proceso de cobranza.

---

## Entradas

- Bono D1 asignado y utilizado por el cliente.
- Detección del uso del bono (worker periódico).
- Información financiera del crédito.
- Plan de pagos generado.
- Cuenta bancaria registrada (vinculada durante el onboarding).
- Pago recibido mediante PSE o débito automático (Drúo).

---

## Salidas

- Plan de pagos calculado.
- Saldo del crédito actualizado.
- Crédito liquidado.
- Cupo nuevamente disponible.
- Caso enviado al proceso de cobranza cuando exista mora.

---

## Excepciones

- El cliente no realiza el prepago.
- El débito automático con Drúo no puede ejecutarse correctamente.
- El pago es rechazado por la entidad financiera.
- El cliente incurre en mora.
- Se presenta un error durante la actualización del saldo.
- El worker periódico no detecta oportunamente el uso del bono (retraso en la originación del crédito).
- El caso debe ser transferido al proceso de cobranza.

---

## Consideraciones

- La originación del crédito no es instantánea: depende de la periodicidad del worker que detecta el uso del bono en D1.
- El cliente tiene dos vías de pago: prepago voluntario por PSE, o cobro automático con Drúo al cierre del ciclo — consistente con el mecanismo de débito automático ya usado en Onboarding (documento 2) y en Cobranza (documento 8).
- La liberación del cupo tras la liquidación debe ser coherente con las reglas de renovación de cupo descritas en el documento 6 (Dispersión de fondos), que evalúa el comportamiento de pago del cliente.
- Si el cliente entra en mora, el proceso se articula directamente con el documento 8 (Cobranza), que ya define reintentos de débito automático en los días 0 y 1-5; se debe evitar duplicar o contradecir esas reglas dentro de este proceso.

---

## Pendientes de validación

> **Pendiente de validar con el dueño del proceso:**
>
> - Confirmar la periodicidad exacta del worker que detecta el uso del bono en D1 y, por lo tanto, el tiempo real entre el uso del bono y la generación del crédito. *(placeholder — paso 2)*
> - Confirmar las reglas de cálculo de intereses y amortización (tasa, método, redondeos). *(placeholder — paso 3)*
> - Confirmar las condiciones para permitir pagos anticipados parciales (monto mínimo, si se puede prepagar solo una parte del saldo). *(placeholder — paso 5)*
> - Confirmar la frecuencia de ejecución del débito automático con Drúo (un único intento en la fecha de corte o varios intentos, y cómo se articula con los reintentos ya definidos en el proceso de Cobranza). *(placeholder — paso 6b)*
> - Confirmar las reglas exactas para liberar nuevamente el cupo de crédito después de la liquidación, y su relación con la evaluación de renovación de cupo del documento de Dispersión de fondos. *(placeholder — paso 9a)*

---

## Fuentes consultadas

- *Journeys Colpatria B2B* (junio de 2026), página 7.
- Documento de Alcance del Producto.
