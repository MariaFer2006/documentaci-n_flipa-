# 4. Evaluación de riesgo

[← Volver a Procesos](README.md)

## Fuentes y criterios

| Fuente | Uso |
|--------|-----|
| Experian | Score crediticio y validación de la cuenta bancaria contra productos reportados |
| Histórico transaccional D1 | Contraste con la tienda habitual declarada |
| Score mínimo | Criterio de aprobación |
| Capacidad de endeudamiento | Criterio de aprobación |

## Flujo

```mermaid
flowchart TD
    A[Consulta Experian +\nhistórico D1] --> B[Valida cuenta bancaria\ncontra Experian]
    B --> C[Evalúa score mínimo,\ncapacidad de endeudamiento\ny coincidencia de tienda]
    C --> D{Cumple\nrequisitos}
    D -->|Sí| E[Aprueba o ajusta cupo]
    E --> F[Continúa a firma\nde contrato]
    D -->|No| G[Rechaza crédito,\nemite alarma]
    G --> H[Notifica rechazo\npor correo]
```
