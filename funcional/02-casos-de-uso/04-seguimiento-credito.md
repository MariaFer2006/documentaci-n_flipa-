# 4. Dar seguimiento al crédito

[← Volver a Casos De Uso](README.md)

## Diagrama de caso de uso

![Diagrama del caso de uso: Dar seguimiento al crédito](diagramas/04-seguimiento-credito.svg)

Actor principal: **administrador / analista de cartera**.

> ⚠️ **Corrección (2026-07-30):** se mantiene al administrador como actor (a diferencia de CU-1, CU-2 y CU-3), pero se precisa que en la práctica esta labor la ejecuta también el analista de cartera desde el mismo panel `apps/admin`.

Objetivo: registrar y monitorear el cumplimiento del crédito una vez aprobado.

**Fuente:** `apps/admin/src/app/credit-lines/[id]/page.tsx`, `backends/admin/src/controllers/credit-lines.controller.ts`.
