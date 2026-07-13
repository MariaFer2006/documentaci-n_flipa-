# 2. Onboarding digital

[← Volver a Procesos](README.md)

Duración total aproximada: **3 minutos**.

## Flujo

```mermaid
flowchart TD
    A[Link único de invitación\npor correo, SMS o WhatsApp\nSendgrid / Zenvia] --> B[Ingresa NIT o cédula]
    B --> C[Ingresa ubicación\nciudad y dirección]
    C --> D[Ingresa correo]
    D --> E[Sistema valida contra\nbase de datos Flipa]
    E --> F[Identifica cupo preaprobado\nsegún consumo en D1]
    F --> G[Valida teléfono\ncon código OTP]
    G --> H[Acepta términos\ny condiciones]
    H --> I[Ingresa datos del\nrepresentante legal]
    I --> J[Continúa a KYC]
```

## Datos y validaciones

| Dato solicitado | Mecanismo de validación |
|------------------|--------------------------|
| NIT / cédula de ciudadanía | Contra base de datos de Flipa |
| Ubicación (ciudad, dirección) | Registro directo |
| Correo | Registro directo |
| Cupo preaprobado | Calculado con criterios de consumo en D1 |
| Teléfono | Código OTP (reenviable) |
| Representante legal | Registro directo |
