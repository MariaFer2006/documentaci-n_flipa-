# 5. Firma de contrato y activación

[← Volver a Procesos](README.md)

## Elementos revisados por el cliente

| Elemento | Detalle |
|----------|---------|
| Cupo aprobado | Monto final |
| Plan de pagos | Cuotas y fechas |
| Valor a pagar | Total con intereses |
| Fecha de pago | Fecha de corte |
| Tasa de interés | Tasa aplicable |

## Flujo

```mermaid
flowchart TD
    A[Ingresa NIT y PIN] --> B[Revisa contrato\ny pagaré]
    B --> C[Acepta condiciones]
    C --> D[Recibe código de\nverificación al correo]
    D --> E[Confirma firma]
    E --> F[Se generan contrato\ny pagaré firmados]
    F --> G[Se envía copia\nal cliente]
    G --> H[Se asigna el\nbono de D1]
    H --> I[Crédito aprobado,\ncontinúa a uso del bono]
```
