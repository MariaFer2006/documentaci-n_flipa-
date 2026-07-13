# 11. Servicio al cliente

[← Volver a Procesos](README.md)

## Flujo

```mermaid
flowchart TD
    A[Cliente contacta:\nWhatsApp, correo, llamada\no contacto outbound] --> B[Asistente virtual\nIA clasifica el caso]
    B --> C{IA resuelve\nel caso}
    C -->|Sí| D[Comunica solución\ny cierra en portal]
    C -->|No| E[Escala a agente humano\ncon contexto completo]
    E --> F{Caso crítico}
    F -->|Suplantación, uso indebido,\ndesconocimiento de compra| G[Validación de identidad +\naprobación manual explícita]
    F -->|Legal / PQR| H[Enrutado al área legal\nSLA de respuesta inmediata]
    D --> I[Se mide NPS/CSAT\nal cierre]
    G --> I
    H --> I
```

Todo caso se registra en el portal administrativo. El asistente virtual se clasifica como una funcionalidad de **largo plazo**; los agentes humanos se encargan de validación de identidad y aprobación de casos críticos.
