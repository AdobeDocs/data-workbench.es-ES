---
description: Métricas del perfil de valores
title: Métricas del perfil de valores
uuid: 68951e33-013a-466b-b0f3-839eaef89cb5
exl-id: 9e95008c-1162-4f50-89d2-dcf5fcf8746a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 17%

---

# Métricas del perfil de valores{#value-profile-metrics}

{{eol}}

| Métrica | Fórmula | Nivel | Descripción |
|---|---|---|---|
| Conversión | `Sessions[not Session_Value=#0]/Sessions` | Sesión | El porcentaje de sesiones que generaron valor comercial (tal como se define en el modelo de valor comercial). |
| Pct del valor | `Value/total(Value)` | Sesión | El porcentaje del valor general generado a partir del conjunto seleccionado de sesiones. |
| Valor | `sum(Session_Value, Session)*0.01` | Sesión | El valor comercial total generado, en dólares (definido por el Modelo de Valor Empresarial). |
| Eventos de valor | `Sessions[not Session_Value=#0]` | Sesión | Recuento de sesiones que generaron valor comercial (tal como se define en el Modelo de Valor Empresarial). |
| Eventos de valor por visitante | `(Value_Events/Visitors) by Visitor` | Visitante | Número promedio de sesiones para cada visitante que generó valor comercial (según se define en el Modelo de valor comercial). |
| Valor por visitante | `(Value/Visitors) by Visitor` | Visitante | El valor comercial promedio que genera cada visitante, en dólares. |
