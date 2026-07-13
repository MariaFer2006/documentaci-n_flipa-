# 5. Firma de contrato y activación

[← Volver a Procesos](README.md)

| Documento | Firma de contrato y activación |
|-----------|----------------------------------|
| **Proyecto** | Fliipa |
| **Versión** | 2.1 |
| **Estado** | Borrador para validación |
| **Responsable** | Riesgo y crédito |
| **Última actualización** | 2026-07-13 |

---

## Control de versiones

| Versión | Fecha | Autor | Descripción |
|---------|-------|-------|-------------|
| 1.0 | 2026-07-09 | María Fernanda Herazo | Versión inicial, como sección 5 del `procesos.md` original (monolítico). |
| 2.0 | 2026-07-13 | María Fernanda Herazo  | Reorganización en archivo independiente con diagrama Mermaid, dentro del split de `negocio/procesos/`. |
| 2.1 | 2026-07-13 | María Fernanda Herazo  | Corrección solicitada tras validar contra las páginas 5 y 6 de `Journeys Fran finales.pdf`: se agrega el arranque del proceso (habilitación del crédito, solicitud de continuar la firma, link por correo); se corrige el orden — el cliente **acepta condiciones** (resumen general) antes de que el sistema muestre el detalle y el cliente **lea el contrato y el pagaré** (paso nuevo de junio 2026), no al revés; se agregan las bifurcaciones de PIN olvidado y de código de verificación fallido; se agregan los pasos finales de notificación del bono y visualización del código, que faltaban antes de "se aprueba el crédito". |

---

## Elementos revisados por el cliente

| Elemento | Detalle |
|----------|---------|
| Cupo aprobado | Monto final |
| Plan de pagos | Cuotas y fechas |
| Valor a pagar | Total con intereses |
| Fecha de pago | Fecha de corte |
| Tasa de interés | Tasa aplicable |
| Cuándo podrá usarlo | Momento de activación del cupo |

## Flujo

```mermaid
flowchart TD
    A[Core bancario habilita\nla aprobación del crédito] --> B[Solicita al cliente continuar\ncon la firma - correo, mensaje o llamada]
    B --> C[Cliente recibe correo\ncon link para continuar]
    C --> D[Ingresa NIT]
    D --> E[Ingresa PIN\nde seguridad]
    E -->|Olvidó el PIN| F[Se redirige al\ncanal de soporte]
    F --> B
    E -->|OK| G[Da bienvenida a la cuenta]
    G --> H[Comunica monto de crédito\naprobado y condiciones generales]
    H --> I[Cliente acepta\ncondiciones]
    I --> J[Comunica el detalle:\ncupo, plan de pagos, valor,\nfecha, tasa, cuándo usarlo]
    J --> K[Cliente lee el\ncontrato y el pagaré]
    K --> L[App comunica siguientes\npasos de la firma]
    L --> M[Se envía código de\nverificación al correo]
    M --> N[Cliente ingresa\ncódigo de verificación]
    N -->|Fallido| O[Contacta servicio\nal cliente]
    N -->|Exitoso| P[Se genera contrato y pagaré\nfirmados; se envía copia al\ncliente vía email]
    P --> Q[Asigna el bono\nde D1 al usuario]
    Q --> R[Notifica al cliente, a través\nde su cuenta, el bono asignado]
    R --> S[Cliente ve el código\na través de su cuenta]
    S --> T[Se aprueba el crédito]
    T --> U[Fin: continúa a la\nrecepción y uso del bono]
```

## Fuentes consultadas

- `Journeys Fran finales.pdf` (Journeys Colpatria B2B, junio 2026), páginas 5 y 6 ("Firma de contrato", swimlanes Cliente / Web / Core Bancario / Core de Crédito-Originación)
