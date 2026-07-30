# CU-007. Firmar contrato y pagaré desde el celular

[← Volver a Casos De Uso](README.md)

## Diagrama de caso de uso

![Diagrama del caso de uso: Firmar contrato y pagaré desde el celular](diagramas/07-firmar-contrato-pagare.svg)


Actor principal: **cliente empresarial**.

Objetivo: permitir al cliente firmar digitalmente el contrato y el pagaré de su línea de crédito desde el celular.

Flujo principal:
1. El sistema genera el contrato y el pagaré del cliente.
2. El cliente recibe un código de verificación para confirmar la firma.
3. El cliente ingresa el código y firma digitalmente.
4. Si se agotan los intentos permitidos, el sistema bloquea temporalmente la firma para prevenir fuerza bruta.

**Fuente:** `apps/redemption/actions/sign-contract.ts`, `backends/b2b/src/config/constants.ts` (`signatureValidityMs`, `blockDurationMs`).

**Historias de usuario relacionadas:** HU-006 (firmar contrato y pagaré desde el celular).
**Requerimientos relacionados:** RF-013, RF-014.

> ✅ Confirmado en código: el bloqueo tras agotar intentos existe y dura 24 horas (`blockDurationMs`), consistente con [RNF-013](../04-requerimientos/02-requerimientos-no-funcionales.md).
