# 6. Dispersión de fondos

## Objetivo

Gestionar el desembolso de los recursos del crédito desde la fiducia hacia D1, emitir el bono correspondiente al cupo aprobado, registrar el uso del crédito por parte del cliente y administrar el retorno de los pagos para evaluar la renovación del cupo en futuros ciclos.

---

## Journey

El recorrido se explica a continuación en texto narrativo y la imagen del journey sirve como referencia visual para validar la secuencia operativa.

![Journey Colpatria B2B — página 8](imagenes/page-08.png)

**Figura 8. Journey de Dispersión de Fondos.**

Este journey describe el flujo financiero del crédito una vez ha sido aprobado y firmado. Durante esta etapa se administran los recursos del crédito mediante una cuenta fiduciaria, se realiza el desembolso hacia D1, se emite el bono para el cliente, se registra el pago del crédito y finalmente se evalúa si el cliente puede recibir una renovación de su cupo.

---

## Descripción general

Una vez el contrato ha sido firmado y el crédito queda activo, Colpatria crea y fondea una cuenta fiduciaria desde donde se administran los recursos del piloto. Posteriormente la fiducia desembolsa el dinero a D1 para emitir el bono correspondiente al valor del cupo utilizado.

Cuando el cliente utiliza el bono en una tienda D1, el sistema registra la utilización del crédito y bloquea el cupo remanente hasta finalizar el ciclo de pago. Posteriormente el cliente paga su obligación y el dinero retorna nuevamente a la fiducia como cuenta de recaudo. Finalmente, el sistema analiza el comportamiento de pago para determinar si el cliente puede recibir una renovación de su cupo de crédito.

---

## Explicación paso a paso

### 1. Creación y fondeo de la cuenta fiduciaria

El proceso inicia cuando Colpatria crea una cuenta fiduciaria destinada exclusivamente a administrar los recursos del piloto. En esta cuenta se depositan los fondos que posteriormente serán utilizados para realizar los desembolsos de los créditos aprobados.

La fiducia centraliza tanto la salida del dinero hacia D1 como el retorno de los pagos realizados por los clientes.

---

### 2. Concentración de los fondos

Una vez creada la cuenta fiduciaria, todos los recursos del crédito quedan concentrados en esta cuenta. Desde aquí se administra el origen del dinero para cada desembolso y posteriormente el recaudo de los pagos efectuados por los clientes.

De acuerdo con el journey, este diseño reduce el impacto del GMF (4x1000), ya que únicamente se genera el movimiento correspondiente entre la fiducia y D1.

---

### 3. Desembolso hacia D1 y emisión del bono

Cuando el crédito queda disponible, la fiducia realiza el desembolso del valor aprobado hacia D1.

Posteriormente D1 recibe los recursos y genera un bono equivalente al valor del cupo utilizado, el cual queda disponible para que el cliente pueda realizar su compra.

En esta etapa todavía no existe una obligación financiera activa hasta que el bono sea utilizado.

---

### 4. Uso del bono por parte del cliente

El cliente recibe el bono y realiza la compra en una tienda D1.

Una vez el bono es utilizado, el sistema registra la utilización efectiva del crédito y comienza formalmente el ciclo de vida de la obligación financiera.

Según el journey, después del primer uso el sistema bloquea automáticamente el cupo remanente para evitar compras adicionales durante el mismo ciclo de crédito.

---

### 5. Pago del crédito

Cuando llega la fecha de pago, el cliente realiza el pago correspondiente a su obligación.

El dinero no retorna a D1, sino que es consignado nuevamente en la cuenta fiduciaria, la cual funciona como cuenta de recaudo del producto.

Este pago permite cerrar correctamente el ciclo financiero del crédito.

---

### 6. Evaluación para renovación del cupo

Una vez registrado el pago, el sistema analiza el comportamiento del cliente para determinar si puede otorgarse una nueva disponibilidad de crédito.

Si el cliente presenta un buen comportamiento de pago y existe disponibilidad de cupo, el sistema puede renovar automáticamente su línea de crédito para un nuevo ciclo.

En caso contrario, el proceso finaliza sin renovación.

---

## Reglas de negocio

- Colpatria debe crear y fondear la cuenta fiduciaria antes de realizar cualquier desembolso.
- Todos los desembolsos del piloto se realizan desde la cuenta fiduciaria hacia D1.
- D1 únicamente recibe los recursos para emitir el bono correspondiente al cliente.
- El bono representa el valor del cupo utilizado por el cliente.
- El crédito se considera utilizado únicamente cuando el bono es redimido en una tienda D1.
- Después del primer uso del bono, el sistema bloquea el cupo remanente hasta finalizar el ciclo.
- Los pagos del cliente retornan siempre a la cuenta fiduciaria.
- La renovación del cupo depende del comportamiento de pago y de la disponibilidad definida por la política de crédito.

---

## Entradas

- Crédito aprobado y firmado.
- Recursos disponibles para el piloto.
- Cuenta fiduciaria creada.
- Valor del cupo aprobado.
- Información del cliente.
- Compra realizada en D1.
- Pago realizado por el cliente.

---

## Salidas

- Recursos desembolsados hacia D1.
- Bono emitido al cliente.
- Crédito activado mediante el uso del bono.
- Pago recibido por la fiducia.
- Decisión sobre la renovación del cupo.

---

## Excepciones

- La cuenta fiduciaria no puede ser creada o fondeada.
- El desembolso hacia D1 falla.
- El bono no puede emitirse correctamente.
- El cliente no utiliza el bono.
- El cliente no realiza el pago del crédito.
- El pago no retorna correctamente a la fiducia.
- El cliente no cumple las políticas para renovar el cupo.

---

## Consideraciones

- La cuenta fiduciaria concentra tanto el origen como el recaudo de los recursos del crédito.
- El journey indica que este modelo reduce el impacto del GMF (4x1000) durante la operación.
- El crédito inicia efectivamente cuando el bono es utilizado por el cliente.
- El bloqueo del cupo remanente evita nuevas compras durante el mismo ciclo.
- La renovación del cupo corresponde a una evaluación posterior al pago y depende de las políticas vigentes.

---

## Notas

- El cálculo del GMF mostrado en el journey corresponde al diseño financiero del piloto y puede modificarse en futuras versiones del producto.
- Las políticas de renovación del cupo deberán confirmarse con el equipo de Riesgo antes de la versión definitiva de la documentación.
- El monto del fondo fiduciario y las reglas de renovación son parámetros sujetos a cambios durante la evolución del producto.

---

## Fuentes consultadas

- *Journeys Colpatria B2B* (junio de 2026), página 8.
- Documentación del modelo operativo del producto.
- Documento de alcance del producto.

