# 7. Diagrama: ecosistema de actores

[← Volver a Actores](README.md)

```mermaid
graph TD
    subgraph Estrategico["Nivel estratégico"]
        GSD["Grupo Santo Domingo"]
        SUMZ["Sumz"]
    end

    subgraph Comercial["Canal y captación comercial"]
        D1["D1"]
        ASESOR["Asesor comercial"]
        HUNTER["Hunter / Visitador"]
    end

    CLIENTE["Cliente empresarial"]
    ADMIN["Administrador del producto"]

    subgraph RiesgoKYC["Riesgo y cumplimiento"]
        RIESGO["Analista de riesgo"]
        EXPERIAN["Experian"]
        OLIMPIA["Olimpia"]
    end

    subgraph Cobranza["Cobranza y jurídico"]
        CARTERA["Analista de cartera"]
        LIDER["Líder de Cartera"]
        COMCARTERA["Comité de Cartera"]
        JURIDICO["Analista jurídico / Representante Jurídico"]
        COMLEGAL["Comité Legal"]
    end

    subgraph SAC["Servicio al cliente"]
        IA["Asistente virtual IA"]
        AGENTE["Agente humano SAC"]
        LEGALPQR["Área Legal / PQR"]
    end

    subgraph Fondeo["Fondeo y pagos"]
        COLPATRIA["Colpatria"]
        DRUO["Druo"]
    end

    subgraph Notif["Notificaciones"]
        ZENVIA["Zenvia"]
        SENDGRID["Sendgrid"]
    end

    GSD --> SUMZ --> ADMIN
    D1 --> CLIENTE
    ASESOR --> CLIENTE
    HUNTER --> CLIENTE
    CLIENTE --> RIESGO
    RIESGO --> EXPERIAN
    RIESGO --> OLIMPIA
    RIESGO --> ADMIN
    ADMIN --> CARTERA
    CARTERA --> LIDER --> COMCARTERA
    COMCARTERA --> JURIDICO --> COMLEGAL
    CLIENTE --> IA --> AGENTE --> LEGALPQR
    COLPATRIA --> CLIENTE
    DRUO --> CLIENTE
    ZENVIA --> CLIENTE
    SENDGRID --> CLIENTE
```

## Fuentes consultadas

- Elaboración propia a partir de Modelo Comercial B2B, Modelo y Proceso de Cobranza B2B, Investigación B2B y Journeys Colpatria B2B.
