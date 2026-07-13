# 3. Validación de identidad (KYC)

[← Volver a Procesos](README.md)

## Pasos

| Paso | Detalle |
|------|---------|
| PIN de seguridad | 4 dígitos |
| Verificación biométrica | Proveedor externo **Olimpia** (fuera de la app) |
| Certificación bancaria | Extractos de los últimos 3 meses |
| Cuenta bancaria | Vinculada y validada contra **Druo** |
| Localidad de compra | Selección de la localidad habitual |

## Flujo y resultado de la biometría

```mermaid
flowchart TD
    A[PIN + biometría Olimpia +\nextractos + cuenta bancaria Druo] --> B{Resultado\nbiometría}
    B -->|Exitoso| C[Continúa a\nevaluación de riesgo]
    B -->|En revisión| D[Analista resuelve\nel caso manualmente\nrespuesta en 2 días]
    D --> C
    B -->|Rechazado| E[Proceso termina,\nse notifica al cliente]
```
